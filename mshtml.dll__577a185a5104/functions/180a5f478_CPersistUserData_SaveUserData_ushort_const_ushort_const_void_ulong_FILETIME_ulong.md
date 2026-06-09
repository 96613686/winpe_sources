# CPersistUserData::SaveUserData(ushort const *,ushort const *,void *,ulong,_FILETIME,ulong)

- ea: `0x180a5f478`
- end: `0x180a5f6f8`
- name: `?SaveUserData@CPersistUserData@@AEAAJPEBG0PEAXKU_FILETIME@@K@Z`
- size: `640`
- prototype: `__int64 __fastcall(CPersistUserData *__hidden this, LPCWSTR pcszURL, const unsigned __int16 *Source, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite, struct _FILETIME, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180a604f0`

## callees

- `0x18005e684`
- `0x1806cdaac`
- `0x1807967d0`
- `0x180a5dc08`
- `0x180a5de8c`
- `0x180a5e08c`
- `0x180a5e4ec`
- `0x180a5eb8c`
- `0x180a5f0cc`
- `0x180a5f478`
- `0x1810f65c0`

## import_xrefs

- `KERNEL32!WriteFile` at `0x180a5f5bc`
- `KERNEL32!WriteFile` at `0x180a5f60e`
- `KERNEL32!WriteFile` at `0x180a5f5bc`
- `KERNEL32!WriteFile` at `0x180a5f60e`
- `KERNEL32!CreateFileW` at `0x180a5f584`
- `KERNEL32!CreateFileW` at `0x180a5f584`
- `KERNEL32!GetLastError` at `0x180a5f54e`
- `KERNEL32!GetLastError` at `0x180a5f5cc`
- `KERNEL32!GetLastError` at `0x180a5f662`
- `KERNEL32!GetLastError` at `0x180a5f54e`
- `KERNEL32!GetLastError` at `0x180a5f5cc`
- `KERNEL32!GetLastError` at `0x180a5f662`
- `KERNEL32!CloseHandle` at `0x180a5f5ea`
- `KERNEL32!CloseHandle` at `0x180a5f621`
- `KERNEL32!CloseHandle` at `0x180a5f5ea`
- `KERNEL32!CloseHandle` at `0x180a5f621`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x180a5f62d`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x180a5f62d`

## pseudocode

```c

```
