# LsapDPAPIPasswordChangeForGMSA(ushort *,ushort *,_UNICODE_STRING,_UNICODE_STRING)

- ea: `0x1800cc8e0`
- end: `0x1800ccf28`
- name: `?LsapDPAPIPasswordChangeForGMSA@@YAJPEAG0U_UNICODE_STRING@@1@Z`
- size: `1608`
- prototype: `__int64 __fastcall(unsigned __int16 *, PCWSTR SourceString, struct _UNICODE_STRING *__struct_ptr, struct _UNICODE_STRING *__struct_ptr)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18000c300`
- `0x180011278`
- `0x180014954`
- `0x180016f70`
- `0x180078250`
- `0x1800ada18`
- `0x1800b86d0`
- `0x1800c7258`
- `0x1800cbb98`
- `0x1800cc8e0`
- `0x18012cebc`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x1800ccda8`
- `ntdll!RtlReleaseResource` at `0x1800ccda8`
- `ntdll!RtlAcquireResourceShared` at `0x1800ccc1e`
- `ntdll!RtlAcquireResourceShared` at `0x1800ccc1e`
- `ntdll!NtClose` at `0x1800cceb2`
- `ntdll!NtClose` at `0x1800cceb2`
- `ntdll!NtDuplicateToken` at `0x1800cccf2`
- `ntdll!NtDuplicateToken` at `0x1800cccf2`
- `ntdll!RtlEqualUnicodeString` at `0x1800ccc64`
- `ntdll!RtlEqualUnicodeString` at `0x1800ccc8b`
- `ntdll!RtlEqualUnicodeString` at `0x1800cccbb`
- `ntdll!RtlEqualUnicodeString` at `0x1800ccc64`
- `ntdll!RtlEqualUnicodeString` at `0x1800ccc8b`
- `ntdll!RtlEqualUnicodeString` at `0x1800cccbb`
- `ntdll!RtlInitUnicodeString` at `0x1800cc9b9`
- `ntdll!RtlInitUnicodeString` at `0x1800cc9cc`
- `ntdll!RtlInitUnicodeString` at `0x1800ccb03`
- `ntdll!RtlInitUnicodeString` at `0x1800cc9b9`
- `ntdll!RtlInitUnicodeString` at `0x1800cc9cc`
- `ntdll!RtlInitUnicodeString` at `0x1800ccb03`

## pseudocode

```c

```
