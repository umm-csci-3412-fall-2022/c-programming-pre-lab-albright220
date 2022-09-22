# Leak report

the memory leak in checkwhitespace.c comes from the allocation of memory to the result variable in strip(), which is called by is clean, and that by main.
the fix here would be to unallocate the memory top level (main) after it is done being used.

the many memory leaks in checkwhitespacetest.cpp comes from the tests using the leaking strip(). The fix here is to unallocate the memory after each test finishes
