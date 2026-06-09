# SecurityDescriptor::MakeSelfRelative(void)

- ea: `0x1401c7db8`
- end: `0x1401c7f57`
- name: `?MakeSelfRelative@SecurityDescriptor@@QEAAPEAVFrsStatus@@XZ`
- size: `415`
- prototype: `struct FrsStatus *__fastcall(SecurityDescriptor *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140203318`

## callees

- `0x1400036d0`
- `0x1400046cc`
- `0x1401af7c0`
- `0x1401b9494`
- `0x1401c665c`
- `0x1401c6fac`
- `0x1401c7db8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1401c7e5b`
- `KERNEL32!GetLastError` at `0x1401c7e7a`
- `KERNEL32!GetLastError` at `0x1401c7ee3`
- `KERNEL32!GetLastError` at `0x1401c7e5b`
- `KERNEL32!GetLastError` at `0x1401c7e7a`
- `KERNEL32!GetLastError` at `0x1401c7ee3`
- `KERNEL32!GetCurrentThreadId` at `0x1401c7dd4`
- `KERNEL32!GetCurrentThreadId` at `0x1401c7e6c`
- `KERNEL32!GetCurrentThreadId` at `0x1401c7ed5`
- `KERNEL32!GetCurrentThreadId` at `0x1401c7dd4`
- `KERNEL32!GetCurrentThreadId` at `0x1401c7e6c`
- `KERNEL32!GetCurrentThreadId` at `0x1401c7ed5`
- `ADVAPI32!MakeSelfRelativeSD` at `0x1401c7e4f`
- `ADVAPI32!MakeSelfRelativeSD` at `0x1401c7ec5`
- `ADVAPI32!MakeSelfRelativeSD` at `0x1401c7e4f`
- `ADVAPI32!MakeSelfRelativeSD` at `0x1401c7ec5`

## string_xrefs

- `0x1401c7e03`: `base\fs\remotefs\frs\src\util\securityutil.cpp`
- `0x1401c7f17`: `base\fs\remotefs\frs\src\util\securityutil.cpp`
- `0x1401c7df7`: `SecurityDescriptor::MakeSelfRelative`
- `0x1401c7ef4`: `SecurityDescriptor::MakeSelfRelative`

## pseudocode

```c

```
