# CTSSession::IsSafeToDisconnect(int)

- ea: `0x180030a7c`
- end: `0x180030ba3`
- name: `?IsSafeToDisconnect@CTSSession@@AEAAHH@Z`
- size: `295`
- prototype: `__int64 __fastcall(CTSSession *__hidden this, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180034508`

## callees

- `0x1800077a0`
- `0x18000af60`
- `0x18000bcc8`
- `0x180020094`
- `0x180026124`
- `0x180030a7c`

## import_xrefs

- `ntdll!NtFreeVirtualMemory` at `0x180030b7e`
- `ntdll!NtFreeVirtualMemory` at `0x180030b7e`
- `ntdll!NtAllocateVirtualMemory` at `0x180030b4a`
- `ntdll!NtAllocateVirtualMemory` at `0x180030b4a`

## string_xrefs

- `0x180030afd`: `MinPerSessionPageCommit`
- `0x180030b5a`: `Glass session cannot disconnect. Not enough memory to create a new session!`

## pseudocode

```c

```
