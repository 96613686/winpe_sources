# CWin32CDROM::LoadMediaPropertyValues(CInstance *,CConfigMgrDevice *,CHString const &,CHString const &,ushort const * &,ulong,int)

- ea: `0x180046094`
- end: `0x1800468f4`
- name: `?LoadMediaPropertyValues@CWin32CDROM@@IEAAJPEAVCInstance@@PEAVCConfigMgrDevice@@AEBVCHString@@2AEAPEBGKH@Z`
- size: `2144`
- prototype: `__int64 __usercall@<rax>(CWin32CDROM *__hidden this@<rcx>, struct CInstance *@<rdx>, struct CConfigMgrDevice *@<r8>, const struct CHString *@<r9>, const struct CHString *, const unsigned __int16 **, unsigned int, int)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180070208`

## callees

- `0x18000bef0`
- `0x18000cd50`
- `0x1800127e0`
- `0x180013ae0`
- `0x180014c58`
- `0x180016900`
- `0x180017680`
- `0x18001c8a8`
- `0x180020e5c`
- `0x180046094`
- `0x1800468fc`
- `0x1800e9c98`
- `0x1800fc902`
- `0x1800fc980`
- `0x180110010`

## import_xrefs

- `msvcrt!_wcsupr` at `0x180046670`
- `msvcrt!_wcsupr` at `0x180046670`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046878`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004688b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046878`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004688b`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x1800465b9`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x1800465b9`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceW` at `0x180046826`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceW` at `0x180046826`
- `framedynos!?SetDOUBLE@CInstance@@QEAA_NPEBGN@Z` at `0x1800464bb`
- `framedynos!?SetDOUBLE@CInstance@@QEAA_NPEBGN@Z` at `0x1800464bb`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180046124`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180046157`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18004657c`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180046768`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180046804`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180046124`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180046157`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18004657c`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180046768`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180046804`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180046610`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18004662b`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180046646`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180046610`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18004662b`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180046646`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x18004651a`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800465d8`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800468aa`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x18004651a`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800465d8`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800468aa`
- `framedynos!??0CHString@@QEAA@AEBV0@@Z` at `0x1800460e6`
- `framedynos!??0CHString@@QEAA@AEBV0@@Z` at `0x180046498`
- `framedynos!??0CHString@@QEAA@AEBV0@@Z` at `0x1800460e6`
- `framedynos!??0CHString@@QEAA@AEBV0@@Z` at `0x180046498`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800460fe`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180046137`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18004616a`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18004647e`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800465f5`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180046684`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800460fe`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180046137`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18004616a`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18004647e`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800465f5`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180046684`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800464d2`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x18004669f`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800466b3`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800464d2`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x18004669f`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800466b3`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x180046115`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x180046148`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x1800464f9`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x180046115`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x180046148`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x1800464f9`
- `framedynos!??H@YA?AVCHString@@AEBV0@0@Z` at `0x1800466c4`
- `framedynos!??H@YA?AVCHString@@AEBV0@0@Z` at `0x1800466d5`
- `framedynos!??H@YA?AVCHString@@AEBV0@0@Z` at `0x1800466c4`
- `framedynos!??H@YA?AVCHString@@AEBV0@0@Z` at `0x1800466d5`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800467ba`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x180046870`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800467ba`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x180046870`
- `framedynos!?SetVariant@CInstance@@QEAA_NPEBGAEBUtagVARIANT@@@Z` at `0x1800463b3`
- `framedynos!?SetVariant@CInstance@@QEAA_NPEBGAEBUtagVARIANT@@@Z` at `0x1800463cb`
- `framedynos!?SetVariant@CInstance@@QEAA_NPEBGAEBUtagVARIANT@@@Z` at `0x1800463b3`
- `framedynos!?SetVariant@CInstance@@QEAA_NPEBGAEBUtagVARIANT@@@Z` at `0x1800463cb`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180046526`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800466e0`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800466eb`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800466f6`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180046883`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800468b6`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800468c2`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180046526`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800466e0`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800466eb`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800466f6`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180046883`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800468b6`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800468c2`
- `OLEAUT32!__imp_SysAllocString` at `0x18004626c`
- `OLEAUT32!__imp_SysAllocString` at `0x18004635f`
- `OLEAUT32!__imp_SysAllocString` at `0x18004626c`
- `OLEAUT32!__imp_SysAllocString` at `0x18004635f`
- `OLEAUT32!__imp_VariantInit` at `0x1800461af`
- `OLEAUT32!__imp_VariantInit` at `0x1800461ba`
- `OLEAUT32!__imp_VariantInit` at `0x1800461af`
- `OLEAUT32!__imp_VariantInit` at `0x1800461ba`
- `OLEAUT32!__imp_VariantClear` at `0x1800463ff`
- `OLEAUT32!__imp_VariantClear` at `0x180046415`
- `OLEAUT32!__imp_VariantClear` at `0x1800463ff`
- `OLEAUT32!__imp_VariantClear` at `0x180046415`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800461d0`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800461ed`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800461d0`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800461ed`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180046202`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180046240`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1800462a7`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1800462d0`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180046302`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180046330`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18004639b`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180046240`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1800462a7`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1800462d0`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180046302`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180046330`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18004639b`

## string_xrefs

- `0x180046265`: `Random Access`
- `0x180046606`: `MaximumComponentLength`
- `0x1800460f4`: `CompressionMethod`
- `0x180046449`: `DVD Writer`
- `0x18004645b`: `CD Writer`

## pseudocode

```c

```
