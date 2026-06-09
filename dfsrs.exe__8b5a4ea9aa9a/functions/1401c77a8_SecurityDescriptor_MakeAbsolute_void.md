# SecurityDescriptor::MakeAbsolute(void)

- ea: `0x1401c77a8`
- end: `0x1401c7a34`
- name: `?MakeAbsolute@SecurityDescriptor@@QEAAPEAVFrsStatus@@XZ`
- size: `652`
- prototype: `struct FrsStatus *__fastcall(SecurityDescriptor *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1401c84cc`

## callees

- `0x1401af7b0`
- `0x1401af7c0`
- `0x1401b9494`
- `0x1401c665c`
- `0x1401c6fac`
- `0x1401c77a8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1401c7898`
- `KERNEL32!GetLastError` at `0x1401c78b7`
- `KERNEL32!GetLastError` at `0x1401c799f`
- `KERNEL32!GetLastError` at `0x1401c7898`
- `KERNEL32!GetLastError` at `0x1401c78b7`
- `KERNEL32!GetLastError` at `0x1401c799f`
- `KERNEL32!GetCurrentThreadId` at `0x1401c77cd`
- `KERNEL32!GetCurrentThreadId` at `0x1401c78a9`
- `KERNEL32!GetCurrentThreadId` at `0x1401c7991`
- `KERNEL32!GetCurrentThreadId` at `0x1401c77cd`
- `KERNEL32!GetCurrentThreadId` at `0x1401c78a9`
- `KERNEL32!GetCurrentThreadId` at `0x1401c7991`
- `ADVAPI32!MakeAbsoluteSD` at `0x1401c788c`
- `ADVAPI32!MakeAbsoluteSD` at `0x1401c797d`
- `ADVAPI32!MakeAbsoluteSD` at `0x1401c788c`
- `ADVAPI32!MakeAbsoluteSD` at `0x1401c797d`

## string_xrefs

- `0x1401c77fd`: `base\fs\remotefs\frs\src\util\securityutil.cpp`
- `0x1401c79d3`: `base\fs\remotefs\frs\src\util\securityutil.cpp`
- `0x1401c77f1`: `SecurityDescriptor::MakeAbsolute`
- `0x1401c79b0`: `SecurityDescriptor::MakeAbsolute`

## pseudocode

```c

```
