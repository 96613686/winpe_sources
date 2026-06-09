# RundownNotifyEvents(_LIST_ENTRY *,CLUSTER_OBJECT_TYPE,wchar_t const *)

- ea: `0x18005e270`
- end: `0x18005e597`
- name: `?RundownNotifyEvents@@YAXPEAU_LIST_ENTRY@@W4CLUSTER_OBJECT_TYPE@@PEB_W@Z`
- size: `807`
- prototype: `void __high(struct _LIST_ENTRY *, enum CLUSTER_OBJECT_TYPE, const wchar_t *)`
- caller_count: `8`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18002a7a0`
- `0x18004b238`
- `0x18004d528`
- `0x1800559c4`
- `0x180057c9c`
- `0x180063cb0`
- `0x18006c010`
- `0x18008652c`

## callees

- `0x18001236c`
- `0x180025478`
- `0x18005c960`
- `0x18005cea0`
- `0x18005e270`
- `0x18006f910`
- `0x18009e2d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005e570`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005e570`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005e527`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005e527`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005e4ec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005e4ec`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005e326`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005e45c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005e326`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005e45c`

## string_xrefs

- `0x18005e40d`: `Failed to create handle close notification - %d`
- `0x18005e4c2`: `Failed to copy name for handle close notification - %d`

## pseudocode

```c

```
