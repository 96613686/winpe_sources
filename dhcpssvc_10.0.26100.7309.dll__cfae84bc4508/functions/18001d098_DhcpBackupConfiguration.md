# DhcpBackupConfiguration

- ea: `0x18001d098`
- end: `0x18001d200`
- name: `DhcpBackupConfiguration`
- size: `360`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x1800277f8`
- `0x18004d6f0`
- `0x180050260`
- `0x180051cfc`

## callees

- `0x180002854`
- `0x1800055ec`
- `0x1800056c0`
- `0x1800058cc`
- `0x18001d098`
- `0x18009bb68`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18001d0f8`
- `KERNEL32!HeapAlloc` at `0x18001d0f8`
- `KERNEL32!EnterCriticalSection` at `0x18001d174`
- `KERNEL32!EnterCriticalSection` at `0x18001d174`
- `KERNEL32!LeaveCriticalSection` at `0x18001d1c3`
- `KERNEL32!LeaveCriticalSection` at `0x18001d1c3`
- `KERNEL32!HeapFree` at `0x18001d1db`
- `KERNEL32!HeapFree` at `0x18001d1db`

## string_xrefs

- `0x18001d13a`: `System\CurrentControlSet\Services\DhcpServer`

## pseudocode

```c

```
