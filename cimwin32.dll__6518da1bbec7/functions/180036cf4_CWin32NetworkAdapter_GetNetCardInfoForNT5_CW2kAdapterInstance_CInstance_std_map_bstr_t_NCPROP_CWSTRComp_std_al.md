# CWin32NetworkAdapter::GetNetCardInfoForNT5(CW2kAdapterInstance *,CInstance *,std::map<_bstr_t,NCPROP,CWSTRComp,std::allocator<std::pair<_bstr_t const,NCPROP>>> &,std::map<ulong,std::map<CHString,unsigned __int64,std::less<CHString>,std::allocator<std::pair<CHString const,unsigned __int64>>>,std::less<ulong>,std::allocator<std::pair<ulong const,std::map<CHString,unsigned __int64,std::less<CHString>,std::allocator<std::pair<CHString const,unsigned __int64>>>>>> &)

- ea: `0x180036cf4`
- end: `0x18003724a`
- name: `?GetNetCardInfoForNT5@CWin32NetworkAdapter@@QEAAJPEAVCW2kAdapterInstance@@PEAVCInstance@@AEAV?$map@V_bstr_t@@VNCPROP@@VCWSTRComp@@V?$allocator@U?$pair@$$CBV_bstr_t@@VNCPROP@@@std@@@std@@@std@@AEAV?$map@KV?$map@VCHString@@_KU?$less@VCHString@@@std@@V?$allocator@U?$pair@$$CBVCHString@@_K@std@@@3@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$map@VCHString@@_KU?$less@VCHString@@@std@@V?$allocator@U?$pair@$$CBVCHString@@_K@std@@@3@@std@@@std@@@2@@5@@Z`
- size: `1366`
- prototype: `__int64 __usercall@<rax>(CWin32NetworkAdapter *this@<rcx>, __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180036a48`
- `0x180036ba0`

## callees

- `0x180008a6c`
- `0x1800182ec`
- `0x180018560`
- `0x1800209e8`
- `0x180036758`
- `0x18003686c`
- `0x180036cf4`
- `0x1800fc980`
- `0x180110010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180037052`
- `msvcrt!_wcsicmp` at `0x180037052`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800371db`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800371db`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800370e2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800370e2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800370c2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800370c2`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180036d2d`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180036ecd`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180036ed8`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180036ee3`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180036f2a`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180036d2d`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180036ecd`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180036ed8`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180036ee3`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180036f2a`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180036d58`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180037015`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18003703d`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18003711e`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180036d58`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180037015`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18003703d`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18003711e`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180036e7e`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18003706a`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180037149`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180036e7e`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18003706a`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180037149`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180036dd8`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180036dec`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180036e00`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180036e1c`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180036f7c`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180036fa9`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x1800371b2`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180036dd8`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180036dec`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180036e00`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180036e1c`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180036f7c`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180036fa9`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x1800371b2`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180036e58`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180036e6b`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180036fd0`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180036ff9`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180036e58`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180036e6b`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180036fd0`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180036ff9`
- `framedynos!??4CHString@@QEAAAEBV0@AEBV0@@Z` at `0x180036db5`
- `framedynos!??4CHString@@QEAAAEBV0@AEBV0@@Z` at `0x180036db5`
- `framedynos!?Format@CHString@@QEAAXPEBGZZ` at `0x180036f68`
- `framedynos!?Format@CHString@@QEAAXPEBGZZ` at `0x180036f68`
- `framedynos!??0CHString@@QEAA@AEBV0@@Z` at `0x180036d71`
- `framedynos!??0CHString@@QEAA@AEBV0@@Z` at `0x180036d80`
- `framedynos!??0CHString@@QEAA@AEBV0@@Z` at `0x180036d71`
- `framedynos!??0CHString@@QEAA@AEBV0@@Z` at `0x180036d80`
- `framedynos!?SetDateTime@CInstance@@QEAA_NPEBGAEBVWBEMTime@@@Z` at `0x180036ec3`
- `framedynos!?SetDateTime@CInstance@@QEAA_NPEBGAEBVWBEMTime@@@Z` at `0x180036ec3`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180036e95`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180037028`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180036e95`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180037028`
- `framedynos!?SetCreationClassName@Provider@@IEAA_NPEAVCInstance@@@Z` at `0x180036e28`
- `framedynos!?SetCreationClassName@Provider@@IEAA_NPEAVCInstance@@@Z` at `0x180036e28`
- `framedynos!?GetLocalComputerName@Provider@@IEAAAEBVCHString@@XZ` at `0x180036e09`
- `framedynos!?GetLocalComputerName@Provider@@IEAAAEBVCHString@@XZ` at `0x180036e09`
- `framedynos!?SetWBEMINT64@CInstance@@QEAA_NPEBG_K@Z` at `0x1800371c6`
- `framedynos!?SetWBEMINT64@CInstance@@QEAA_NPEBG_K@Z` at `0x1800371c6`
- `framedynos!??0WBEMTime@@QEAA@AEBU_FILETIME@@@Z` at `0x180036eb0`
- `framedynos!??0WBEMTime@@QEAA@AEBU_FILETIME@@@Z` at `0x180036eb0`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x180036d3f`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800370ff`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x180036d3f`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800370ff`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x180036d8b`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x180036da3`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x180036f91`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x180037003`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x1800370a8`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x180036d8b`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x180036da3`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x180036f91`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x180037003`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x1800370a8`
- `framedynos!?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z` at `0x180036e45`
- `framedynos!?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z` at `0x180036fbd`
- `framedynos!?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z` at `0x180036e45`
- `framedynos!?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z` at `0x180036fbd`
- `framedynos!??YCHString@@QEAAAEBV0@AEBV0@@Z` at `0x180036d4e`
- `framedynos!??YCHString@@QEAAAEBV0@AEBV0@@Z` at `0x18003710d`
- `framedynos!??YCHString@@QEAAAEBV0@AEBV0@@Z` at `0x180036d4e`
- `framedynos!??YCHString@@QEAAAEBV0@AEBV0@@Z` at `0x18003710d`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180036f87`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800371d1`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800371e6`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800371f1`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800371fc`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180037207`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180037212`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18003721d`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180037228`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180036f87`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800371d1`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800371e6`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800371f1`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800371fc`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180037207`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180037212`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18003721d`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180037228`

## string_xrefs

- `0x180036e84`: `Win32_ComputerSystem`
- `0x1800370bb`: `iphlpapi.dll`
- `0x180036e4e`: `Installed`

## pseudocode

```c

```
