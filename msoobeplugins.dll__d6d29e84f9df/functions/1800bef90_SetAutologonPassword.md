# _SetAutologonPassword

- ea: `0x1800bef90`
- end: `0x1800bf057`
- name: `_SetAutologonPassword`
- size: `199`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800be388`
- `0x1800be424`

## callees

- `0x180008544`
- `0x180031f90`
- `0x1800bef90`

## import_xrefs

- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800befcc`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800befcc`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaStorePrivateData` at `0x1800bf02e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaStorePrivateData` at `0x1800bf02e`
- `ntdll!RtlInitUnicodeString` at `0x1800bf00f`
- `ntdll!RtlInitUnicodeString` at `0x1800bf01c`
- `ntdll!RtlInitUnicodeString` at `0x1800bf00f`
- `ntdll!RtlInitUnicodeString` at `0x1800bf01c`

## string_xrefs

- `0x1800befe0`: `shell\oobe\common\lib\autologon.cpp`

## pseudocode

```c

```
