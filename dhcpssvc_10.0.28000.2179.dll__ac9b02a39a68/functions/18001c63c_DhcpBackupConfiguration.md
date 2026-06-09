# DhcpBackupConfiguration

- ea: `0x18001c63c`
- end: `0x18001c7a4`
- name: `DhcpBackupConfiguration`
- size: `360`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x180026d78`
- `0x18004d330`
- `0x18004ff20`
- `0x180051a00`

## callees

- `0x18000282c`
- `0x1800055e8`
- `0x1800056ac`
- `0x1800058bc`
- `0x18001c63c`
- `0x18009c828`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18001c69c`
- `KERNEL32!HeapAlloc` at `0x18001c69c`
- `KERNEL32!EnterCriticalSection` at `0x18001c718`
- `KERNEL32!EnterCriticalSection` at `0x18001c718`
- `KERNEL32!LeaveCriticalSection` at `0x18001c767`
- `KERNEL32!LeaveCriticalSection` at `0x18001c767`
- `KERNEL32!HeapFree` at `0x18001c77f`
- `KERNEL32!HeapFree` at `0x18001c77f`

## string_xrefs

- `0x18001c6de`: `System\CurrentControlSet\Services\DhcpServer`

## pseudocode

```c

```
