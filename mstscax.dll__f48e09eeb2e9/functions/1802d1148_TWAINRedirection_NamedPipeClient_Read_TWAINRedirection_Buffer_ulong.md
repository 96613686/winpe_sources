# TWAINRedirection::NamedPipeClient::Read(TWAINRedirection::Buffer &,ulong)

- ea: `0x1802d1148`
- end: `0x1802d12bc`
- name: `?Read@NamedPipeClient@TWAINRedirection@@QEAA_NAEAVBuffer@2@K@Z`
- size: `372`
- prototype: `bool __fastcall(TWAINRedirection::NamedPipeClient *this, struct TWAINRedirection::Buffer *, DWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1802cfa54`
- `0x1802d0180`

## callees

- `0x180129c38`
- `0x180129c50`
- `0x1802cf3ec`
- `0x1802d1148`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x1802d11ec`
- `KERNEL32!WaitForSingleObject` at `0x1802d11ec`
- `KERNEL32!CloseHandle` at `0x1802d1245`
- `KERNEL32!CloseHandle` at `0x1802d1292`
- `KERNEL32!CloseHandle` at `0x1802d1245`
- `KERNEL32!CloseHandle` at `0x1802d1292`
- `KERNEL32!GetLastError` at `0x1802d11d5`
- `KERNEL32!GetLastError` at `0x1802d11d5`
- `KERNEL32!ReadFile` at `0x1802d11cb`
- `KERNEL32!ReadFile` at `0x1802d11cb`
- `KERNEL32!CreateEventA` at `0x1802d11a5`
- `KERNEL32!CreateEventA` at `0x1802d11a5`
- `KERNEL32!GetOverlappedResult` at `0x1802d120b`
- `KERNEL32!GetOverlappedResult` at `0x1802d120b`
- `KERNEL32!CancelIo` at `0x1802d1285`
- `KERNEL32!CancelIo` at `0x1802d12b0`
- `KERNEL32!CancelIo` at `0x1802d1285`
- `KERNEL32!CancelIo` at `0x1802d12b0`

## pseudocode

```c

```
