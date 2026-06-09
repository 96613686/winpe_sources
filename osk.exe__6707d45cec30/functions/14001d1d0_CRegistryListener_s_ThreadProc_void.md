# CRegistryListener::s_ThreadProc(void *)

- ea: `0x14001d1d0`
- end: `0x14001d248`
- name: `?s_ThreadProc@CRegistryListener@@CAKPEAX@Z`
- size: `120`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x14001cc50`
- `0x14001d1d0`

## import_xrefs

- `ADVAPI32!RegNotifyChangeKeyValue` at `0x14001d225`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x14001d225`
- `KERNEL32!WaitForSingleObject` at `0x14001d1e9`
- `KERNEL32!WaitForSingleObject` at `0x14001d1e9`
- `USER32!SendMessageW` at `0x14001d208`
- `USER32!SendMessageW` at `0x14001d208`

## pseudocode

```c

```
