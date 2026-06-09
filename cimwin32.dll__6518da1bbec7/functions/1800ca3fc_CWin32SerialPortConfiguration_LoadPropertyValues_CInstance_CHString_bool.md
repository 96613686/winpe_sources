# CWin32SerialPortConfiguration::LoadPropertyValues(CInstance *,CHString &,bool)

- ea: `0x1800ca3fc`
- end: `0x1800ca8a2`
- name: `?LoadPropertyValues@CWin32SerialPortConfiguration@@AEAAJPEAVCInstance@@AEAVCHString@@_N@Z`
- size: `1190`
- prototype: `int(CWin32SerialPortConfiguration *__hidden this, struct CInstance *, struct CHString *, bool)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800c9d90`
- `0x1800c9f30`

## callees

- `0x18001a310`
- `0x180031800`
- `0x180088a30`
- `0x1800ca3fc`
- `0x1800ca8a8`
- `0x1800fc980`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ca50f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ca50f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800ca4ff`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800ca4ff`
- `api-ms-win-core-comm-l1-1-0!GetCommState` at `0x1800ca563`
- `api-ms-win-core-comm-l1-1-0!GetCommState` at `0x1800ca563`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800ca45d`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800ca479`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800ca495`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800ca4bb`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800ca45d`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800ca479`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800ca495`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800ca4bb`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800ca581`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800ca597`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800ca5ad`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800ca5c3`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800ca5d9`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800ca5ef`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800ca605`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800ca7e5`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800ca7fb`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800ca581`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800ca597`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800ca5ad`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800ca5c3`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800ca5d9`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800ca5ef`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800ca605`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800ca7e5`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800ca7fb`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800ca454`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800ca54b`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800ca61d`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800ca638`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800ca654`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800ca670`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800ca68c`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800ca6a8`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800ca6c4`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800ca6e0`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800ca6fc`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800ca718`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800ca734`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800ca454`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800ca54b`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800ca61d`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800ca638`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800ca654`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800ca670`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800ca68c`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800ca6a8`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800ca6c4`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800ca6e0`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800ca6fc`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800ca718`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800ca734`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800ca470`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800ca48c`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800ca470`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800ca48c`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800ca771`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800ca7ac`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800ca83e`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800ca874`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800ca771`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800ca7ac`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800ca83e`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800ca874`

## string_xrefs

- `0x1800ca72a`: `AbortReadWriteOnError`
- `0x1800ca5cf`: `ErrorReplaceCharacter`
- `0x1800ca6f2`: `ErrorReplacementEnabled`

## pseudocode

```c

```
