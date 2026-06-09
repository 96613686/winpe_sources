# LsapDbFindNextSid(void *,ulong *,_LSAP_DB_OBJECT_TYPE_ID,_LSAPR_SID * *)

- ea: `0x18010d0ac`
- end: `0x18010d391`
- name: `?LsapDbFindNextSid@@YAJPEAXPEAKW4_LSAP_DB_OBJECT_TYPE_ID@@PEAPEAU_LSAPR_SID@@@Z`
- size: `741`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800b3a20`

## callees

- `0x18000c300`
- `0x180011278`
- `0x180016f70`
- `0x180053e80`
- `0x18010d0ac`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18010d2e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18010d2e0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18010d26e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18010d26e`
- `ntdll!RtlpNtOpenKey` at `0x18010d144`
- `ntdll!RtlpNtOpenKey` at `0x18010d1f7`
- `ntdll!RtlpNtOpenKey` at `0x18010d144`
- `ntdll!RtlpNtOpenKey` at `0x18010d1f7`
- `ntdll!RtlpNtEnumerateSubKey` at `0x18010d191`
- `ntdll!RtlpNtEnumerateSubKey` at `0x18010d191`
- `ntdll!RtlpNtQueryValueKey` at `0x18010d228`
- `ntdll!RtlpNtQueryValueKey` at `0x18010d298`
- `ntdll!RtlpNtQueryValueKey` at `0x18010d228`
- `ntdll!RtlpNtQueryValueKey` at `0x18010d298`
- `ntdll!RtlFreeUnicodeString` at `0x18010d35d`
- `ntdll!RtlFreeUnicodeString` at `0x18010d35d`
- `ntdll!NtClose` at `0x18010d332`
- `ntdll!NtClose` at `0x18010d347`
- `ntdll!NtClose` at `0x18010d332`
- `ntdll!NtClose` at `0x18010d347`

## pseudocode

```c

```
