# TcpConnection::WaitForCompletion(int)

- ea: `0x10043731c`
- end: `0x10043743d`
- name: `?WaitForCompletion@TcpConnection@@QEAAKH@Z`
- size: `289`
- prototype: `unsigned int __fastcall(TcpConnection *__hidden this, DWORD dwMilliseconds)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x100436dc0`

## callees

- `0x100432b50`
- `0x10043731c`
- `0x100545d84`
- `0x1005468d8`
- `0x100546aa8`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x10043737b`
- `KERNEL32!WaitForSingleObject` at `0x10043737b`
- `KERNEL32!GetLastError` at `0x1004373ae`
- `KERNEL32!GetLastError` at `0x1004373ae`

## pseudocode

```c

```
