# KerbLoopback::RememberClient(_KERB_CONTEXT *)

- ea: `0x180060fd0`
- end: `0x180061192`
- name: `?RememberClient@KerbLoopback@@YAJPEAU_KERB_CONTEXT@@@Z`
- size: `450`
- prototype: `__int64 __fastcall(KerbLoopback *__hidden this, struct _KERB_CONTEXT *)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180045970`
- `0x18008a714`

## callees

- `0x180012640`
- `0x180012680`
- `0x180030b50`
- `0x180060fd0`
- `0x180070a50`
- `0x18007408c`
- `0x1800740f4`
- `0x1800744cf`
- `0x18008b70c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006106e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006106e`
- `ntdll!RtlAvlInsertNodeEx` at `0x180061123`
- `ntdll!RtlAvlInsertNodeEx` at `0x180061123`
- `ntdll!RtlEnterCriticalSection` at `0x180061099`
- `ntdll!RtlEnterCriticalSection` at `0x180061099`
- `ntdll!RtlLeaveCriticalSection` at `0x180061155`
- `ntdll!RtlLeaveCriticalSection` at `0x180061155`

## string_xrefs

- `0x1800610ec`: `%hs - Session key already found in the table.`

## pseudocode

```c

```
