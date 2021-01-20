## Code Smells

1) In books-search.component.ts, subscription is not unsubscribed this may cause potential memory leaks.
   This can be done in multiple ways, since reading-list.component is already using async pipe for data observable I have corrected books.component subscription in ngOnDestroy.
   For next tasks I have used async pipe in book-search.component. [Fixed]
2) Defined missing reducers to reading-list.reducer.ts which will also fix reading-list.reducer.spec.ts. [Fixed]
3) I would have imposed constraints on how projects can depend on each other.  https://nx.dev/latest/angular/workspace/structure/monorepo-tags. [Improvement]

## Accessibility issues reported by Lighthouse.
1) Buttons do not have an accessible name, added aria-label tags. [Fixed]
2) Background and foreground colors do not have a sufficient contrast ratio, brighter color needs to be used for this.

## Accessibility issues found manually and fixed.
1) Images are missing alt attributes, added empty alt tags to avoid repetition from screen-reader for books-search.component.html and reading-list.component.html.  [Fixed] 
2) Search mat-icon button is missing label, added label with class name screen-reader so that it is available in DOM and screen reader can access it but visually hidden for user.
   Similarly, this can be added for remove-circle icon. [Fixed for search icon]
3) Aria-labels are missing for multiple, added for search and remove icons. [Fixed]

## Task 4 Mark as read
1) Added Checkboxes to mark book as read and disabling the checkbox once user has marked as reading finished.
   This can be done, by using mat-icon, but I have used checkboxes since delete from reading list is already using mat-icon.
2) Added new PUT endpoint.
3) Used primary color for text finished reading.
