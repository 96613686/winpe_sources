# LsaDbpSidOnFtInfo(_UNICODE_STRING *,void *)

- ea: `0x18000c8ec`
- end: `0x18000c959`
- name: `?LsaDbpSidOnFtInfo@@YAJPEAU_UNICODE_STRING@@PEAX@Z`
- size: `109`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String1, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180016ae0`
- `0x180033188`

## callees

- `0x18000c8ec`
- `0x180024da0`

## import_xrefs

- `LSASRV!LsaIFree_LSAPR_UNICODE_STRING_BUFFER` at `0x18000c946`
- `LSASRV!LsaIFree_LSAPR_UNICODE_STRING_BUFFER` at `0x18000c946`
- `ntdll!RtlInitUnicodeString` at `0x18000c90b`
- `ntdll!RtlInitUnicodeString` at `0x18000c90b`
- `ntdll!RtlEqualUnicodeString` at `0x18000c931`
- `ntdll!RtlEqualUnicodeString` at `0x18000c931`

## pseudocode

```c

```
