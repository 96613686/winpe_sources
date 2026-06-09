# CWin32Processor::LoadProcessorValues(ulong,_PROCESSOR_NUMBER *,CInstance *,CFrameworkQuery &,ulong,ulong,tagPROCESSOR_CACHE_DETAILS)

- ea: `0x1800c6ca8`
- end: `0x1800c786d`
- name: `?LoadProcessorValues@CWin32Processor@@IEAAHKPEAU_PROCESSOR_NUMBER@@PEAVCInstance@@AEAVCFrameworkQuery@@KKUtagPROCESSOR_CACHE_DETAILS@@@Z`
- size: `3013`
- prototype: `int __high(unsigned int, struct _PROCESSOR_NUMBER *, struct CInstance *, struct CFrameworkQuery *, unsigned int, unsigned int, struct tagPROCESSOR_CACHE_DETAILS)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800c5ec0`
- `0x1800c66f0`

## callees

- `0x180016900`
- `0x180019374`
- `0x18002540c`
- `0x18002befc`
- `0x18002c580`
- `0x180041110`
- `0x180044958`
- `0x18004b720`
- `0x180061394`
- `0x1800c6ca8`
- `0x1800fc902`
- `0x1800fc980`

## import_xrefs

- `msvcrt!_itow` at `0x1800c701c`
- `msvcrt!_itow` at `0x1800c701c`
- `api-ms-win-core-processthreads-l1-1-1!IsProcessorFeaturePresent` at `0x1800c7733`
- `api-ms-win-core-processthreads-l1-1-1!IsProcessorFeaturePresent` at `0x1800c7769`
- `api-ms-win-core-processthreads-l1-1-1!IsProcessorFeaturePresent` at `0x1800c77cd`
- `api-ms-win-core-processthreads-l1-1-1!IsProcessorFeaturePresent` at `0x1800c77ee`
- `api-ms-win-core-processthreads-l1-1-1!IsProcessorFeaturePresent` at `0x1800c7733`
- `api-ms-win-core-processthreads-l1-1-1!IsProcessorFeaturePresent` at `0x1800c7769`
- `api-ms-win-core-processthreads-l1-1-1!IsProcessorFeaturePresent` at `0x1800c77cd`
- `api-ms-win-core-processthreads-l1-1-1!IsProcessorFeaturePresent` at `0x1800c77ee`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800c704c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800c704c`
- `framedynos!?captainsLog@@3VProviderLog@@A` at `0x1800c6dac`
- `framedynos!?LocalLogMessage@ProviderLog@@QEAAXPEBG0HW4LogLevel@1@@Z` at `0x1800c6db3`
- `framedynos!?LocalLogMessage@ProviderLog@@QEAAXPEBG0HW4LogLevel@1@@Z` at `0x1800c6db3`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800c6e9a`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800c6f19`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800c6f25`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800c6f35`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800c6e9a`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800c6f19`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800c6f25`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800c6f35`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800c6eed`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800c6f00`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800c70a5`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800c714c`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800c7248`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800c7264`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800c7280`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800c72b3`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800c737f`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800c739f`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800c73ec`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800c740b`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800c7431`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800c7469`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800c74ca`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800c7514`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800c752d`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800c7696`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800c76a9`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800c76c3`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800c6eed`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800c6f00`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800c70a5`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800c714c`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800c7248`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800c7264`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800c7280`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800c72b3`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800c737f`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800c739f`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800c73ec`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800c740b`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800c7431`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800c7469`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800c74ca`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800c7514`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800c752d`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800c7696`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800c76a9`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800c76c3`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x1800c6e39`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x1800c7226`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x1800c6e39`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x1800c7226`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800c6e0b`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800c774b`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800c775e`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800c7788`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800c779b`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800c77c2`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800c77e3`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800c7804`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800c6e0b`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800c774b`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800c775e`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800c7788`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800c779b`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800c77c2`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800c77e3`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800c7804`
- `framedynos!?GetBuffer@CHString@@QEAAPEAGH@Z` at `0x1800c6f48`
- `framedynos!?GetBuffer@CHString@@QEAAPEAGH@Z` at `0x1800c6f48`
- `framedynos!?Format@CHString@@QEAAXPEBGZZ` at `0x1800c6f79`
- `framedynos!?Format@CHString@@QEAAXPEBGZZ` at `0x1800c6f79`
- `framedynos!??0CRegistry@@QEAA@XZ` at `0x1800c6f0d`
- `framedynos!??0CRegistry@@QEAA@XZ` at `0x1800c6f0d`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x1800c7835`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x1800c7835`
- `framedynos!?IsPropertyRequired@CFrameworkQuery@@QEAA_NPEBG@Z` at `0x1800c6fb0`
- `framedynos!?IsPropertyRequired@CFrameworkQuery@@QEAA_NPEBG@Z` at `0x1800c6fb0`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800c6d1f`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800c6de1`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800c6df8`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800c6e22`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800c6ec0`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800c6ed5`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800c70e4`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800c70fb`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800c7112`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800c71d8`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800c71ed`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800c736c`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800c6d1f`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800c6de1`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800c6df8`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800c6e22`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800c6ec0`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800c6ed5`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800c70e4`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800c70fb`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800c7112`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800c71d8`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800c71ed`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800c736c`
- `framedynos!?s_strComputerName@Provider@@0VCHString@@A` at `0x1800c6e28`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800c6dca`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800c74b5`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800c7558`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800c7594`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800c75fe`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800c7629`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800c7654`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800c770b`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800c6dca`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800c74b5`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800c7558`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800c7594`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800c75fe`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800c7629`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800c7654`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800c770b`
- `framedynos!?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z` at `0x1800c6e58`
- `framedynos!?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z` at `0x1800c6e72`
- `framedynos!?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z` at `0x1800c6e8f`
- `framedynos!?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z` at `0x1800c7130`
- `framedynos!?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z` at `0x1800c716d`
- `framedynos!?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z` at `0x1800c72d1`
- `framedynos!?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z` at `0x1800c72ef`
- `framedynos!?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z` at `0x1800c75c6`
- `framedynos!?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z` at `0x1800c76f7`
- `framedynos!?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z` at `0x1800c6e58`
- `framedynos!?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z` at `0x1800c6e72`
- `framedynos!?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z` at `0x1800c6e8f`
- `framedynos!?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z` at `0x1800c7130`
- `framedynos!?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z` at `0x1800c716d`
- `framedynos!?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z` at `0x1800c72d1`
- `framedynos!?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z` at `0x1800c72ef`
- `framedynos!?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z` at `0x1800c75c6`
- `framedynos!?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z` at `0x1800c76f7`
- `framedynos!?OpenLocalMachineKeyAndReadValue@CRegistry@@QEAAJPEBG0AEAVCHString@@@Z` at `0x1800c6f97`
- `framedynos!?OpenLocalMachineKeyAndReadValue@CRegistry@@QEAAJPEBG0AEAVCHString@@@Z` at `0x1800c71bc`
- `framedynos!?OpenLocalMachineKeyAndReadValue@CRegistry@@QEAAJPEBG0AEAVCHString@@@Z` at `0x1800c720a`
- `framedynos!?OpenLocalMachineKeyAndReadValue@CRegistry@@QEAAJPEBG0AEAVCHString@@@Z` at `0x1800c6f97`
- `framedynos!?OpenLocalMachineKeyAndReadValue@CRegistry@@QEAAJPEBG0AEAVCHString@@@Z` at `0x1800c71bc`
- `framedynos!?OpenLocalMachineKeyAndReadValue@CRegistry@@QEAAJPEBG0AEAVCHString@@@Z` at `0x1800c720a`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800c780f`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800c781b`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800c7827`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800c7841`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800c780f`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800c781b`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800c7827`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800c7841`

## string_xrefs

- `0x1800c6e11`: `Win32_ComputerSystem`
- `0x1800c769f`: `ThreadCount`
- `0x1800c6f84`: `Component Information`
- `0x1800c7276`: `L3CacheSpeed`
- `0x1800c72a9`: `L3CacheSize`
- `0x1800c723e`: `L2CacheSize`
- `0x1800c725a`: `L2CacheSpeed`
- `0x1800c7741`: `VMMonitorModeExtensions`
- `0x1800c777e`: `VMMonitorModeExtensions`
- `0x1800c77b8`: `VMMonitorModeExtensions`
- `0x1800c776f`: `SecondLevelAddressTranslationExtensions`
- `0x1800c7791`: `SecondLevelAddressTranslationExtensions`
- `0x1800c77d9`: `SecondLevelAddressTranslationExtensions`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CWin32Processor::LoadProcessorValues(
        __int64 a1,
        unsigned int a2,
        struct _PROCESSOR_NUMBER *a3,
        CInstance *a4,
        __int64 a5,
        unsigned int a6,
        int a7,
        __int64 a8)
{
  unsigned int v11; // r12d
  __int64 result; // rax
  unsigned int v13; // esi
  __int64 i; // r8
  unsigned __int16 *v15; // rax
  unsigned int PerfIndex; // r14d
  unsigned int v17; // eax
  unsigned int v18; // ebx
  CPerformanceData *v19; // rcx
  CPerformanceData *v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rbx
  unsigned int v23; // r8d
  unsigned int v24; // r8d
  int v25; // edx
  CSMBios *v26; // rcx
  struct _tagSHF *NthStruct; // rax
  struct _tagSHF *v28; // rbx
  unsigned int v29; // r14d
  unsigned int v30; // ecx
  unsigned int v31; // r8d
  unsigned int v32; // eax
  int v33; // ecx
  unsigned int v34; // r8d
  const unsigned __int16 *v35; // rdx
  int v36; // ecx
  int v37; // ecx
  unsigned int v38; // r8d
  CSMBios *v39; // rcx
  CSMBios *v40; // rcx
  CSMBios *v41; // rcx
  CSMBios *v42; // rcx
  CSMBios *v43; // rcx
  unsigned int v44; // r8d
  unsigned int v45; // esi
  __int16 v46; // ax
  bool v47; // bl
  BOOL v48; // eax
  const unsigned __int16 *v49; // rdx
  bool v50; // r8
  BOOL v51; // eax
  unsigned __int8 *v52; // [rsp+20h] [rbp-E0h]
  unsigned __int64 *v53; // [rsp+28h] [rbp-D8h]
  __int64 v54; // [rsp+30h] [rbp-D0h]
  __int64 v55; // [rsp+50h] [rbp-B0h] BYREF
  const unsigned __int16 *v56; // [rsp+58h] [rbp-A8h] BYREF
  const unsigned __int16 *v57; // [rsp+60h] [rbp-A0h] BYREF
  int v58; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v59; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int8 v60[8]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v61[8]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 v62; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int64 v63; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int8 v64[8]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v65; // [rsp+A0h] [rbp-60h]
  _WORD v66[24]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v67[200]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v68[100]; // [rsp+270h] [rbp+170h] BYREF
  unsigned __int16 v69[40]; // [rsp+338h] [rbp+238h] BYREF
  unsigned __int16 v70[18]; // [rsp+388h] [rbp+288h] BYREF
  unsigned int v71; // [rsp+3ACh] [rbp+2ACh]
  unsigned int v72; // [rsp+3B0h] [rbp+2B0h]
  unsigned int v73; // [rsp+3B4h] [rbp+2B4h]
  unsigned int v74; // [rsp+3CCh] [rbp+2CCh]
  unsigned int v75; // [rsp+3D0h] [rbp+2D0h]
  int v76; // [rsp+3D4h] [rbp+2D4h]
  unsigned __int16 v77; // [rsp+3D8h] [rbp+2D8h]
  unsigned __int16 v78; // [rsp+3DAh] [rbp+2DAh]
  unsigned __int16 v79; // [rsp+3DCh] [rbp+2DCh]
  unsigned __int16 v80; // [rsp+3DEh] [rbp+2DEh]
  __int16 v81; // [rsp+3E0h] [rbp+2E0h]
  __int16 v82; // [rsp+3E2h] [rbp+2E2h]
  int v83; // [rsp+3E8h] [rbp+2E8h]
  _BYTE v84[608]; // [rsp+3F0h] [rbp+2F0h] BYREF
  wchar_t Buffer[104]; // [rsp+650h] [rbp+550h] BYREF
  unsigned __int16 v86[104]; // [rsp+720h] [rbp+620h] BYREF

  *(_QWORD *)v60 = a5;
  v65 = a8;
  StringCbPrintfW(v86, 0xC8u, L"CPU%d", a2);
  CInstance::SetCharSplat(a4, L"DeviceID", v86);
  v11 = 0;
  if ( *(_BYTE *)(a5 + 72) )
    return 1;
  memset_0(v66, 0, 0x340u);
  result = GetSystemInfoEx(a2, a3, (struct _tagSYSTEM_INFO_EX *)v66);
  if ( !(_DWORD)result )
    return result;
  v13 = a6;
  if ( !a6 || !a7 )
  {
    StringCbPrintfW(Buffer, 0xC8u, L"Zero processor speed returned from kernel: Max: %d, Current %d.", a6, a7);
    ProviderLog::LocalLogMessage(
      captainsLog,
      Buffer,
      L"onecore\\admin\\wmi\\wbem\\providers\\win32provider\\providers\\processor.cpp",
      831,
      1);
  }
  CInstance::SetCHString(a4, L"Role", L"CPU");
  CInstance::SetCharSplat(a4, L"Status", L"OK");
  CInstance::SetCharSplat(a4, L"CreationClassName", L"Win32_Processor");
  CInstance::Setbool(a4, L"PowerManagementSupported", 0);
  CInstance::SetCharSplat(a4, L"SystemCreationClassName", L"Win32_ComputerSystem");
  CInstance::SetCHString(a4, L"SystemName", Provider::s_strComputerName);
  LOWORD(v55) = 3;
  CInstance::SetWBEMINT16(a4, L"Availability", (const __int16 *)&v55);
  LOWORD(v55) = 3;
  CInstance::SetWBEMINT16(a4, L"StatusInfo", (const __int16 *)&v55);
  LOWORD(v55) = 2;
  CInstance::SetWBEMINT16(a4, L"Family", (const __int16 *)&v55);
  CHString::CHString((CHString *)&v59);
  Format((struct CHString *)&v59, 0x2Cu, a2);
  CInstance::SetCharSplat(a4, L"Caption", v59);
  CInstance::SetCharSplat(a4, L"Description", v59);
  CInstance::SetDWORD(a4, L"AddressWidth", 0x40u);
  CInstance::SetDWORD(a4, L"DataWidth", 0x40u);
  CRegistry::CRegistry((CRegistry *)v84);
  CHString::CHString((CHString *)&v57);
  CHString::CHString((CHString *)&v56);
  v58 = 0;
  CHString::CHString((CHString *)v61);
  for ( i = 0; ; i = v11 )
  {
    CHString::Format((CHString *)&v56, L"HARDWARE\\DESCRIPTION\\System\\CentralProcessor\\%d", i);
    if ( CRegistry::OpenLocalMachineKeyAndReadValue(
           (CRegistry *)v84,
           v56,
           L"Component Information",
           (struct CHString *)&v57) )
    {
      break;
    }
    v15 = CHString::GetBuffer((CHString *)&v57, 0);
    if ( v15[6] == a3->Group && v15[7] == a3->Number )
    {
      if ( !CRegistry::OpenLocalMachineKeyAndReadValue((CRegistry *)v84, v56, L"Identifier", (struct CHString *)&v57) )
      {
        CInstance::SetCharSplat(a4, L"Description", v57);
        CInstance::SetCharSplat(a4, L"Caption", v57);
      }
      if ( !CRegistry::OpenLocalMachineKeyAndReadValue(
              (CRegistry *)v84,
              v56,
              L"ProcessorNameString",
              (struct CHString *)v61) )
      {
        CInstance::SetCHString(a4, L"Name", (const struct CHString *)v61);
        v58 = 1;
      }
      break;
    }
    ++v11;
  }
  if ( CFrameworkQuery::IsPropertyRequired(*(CFrameworkQuery **)v60, L"LoadPercentage") )
  {
    *(_QWORD *)v60 = 0;
    *(_QWORD *)v64 = 0;
    v63 = 0;
    v62 = 0;
    v55 = 0;
    PerfIndex = CPerformanceData::GetPerfIndex((CPerformanceData *)&v55, L"Processor");
    v17 = CPerformanceData::GetPerfIndex((CPerformanceData *)&v55, L"% Processor Time");
    v18 = v17;
    if ( PerfIndex )
    {
      if ( v17 )
      {
        _itow(v11, Buffer, 10);
        CPerformanceData::GetValue(v19, PerfIndex, v18, Buffer, v60, &v63);
        Sleep(0x3E8u);
        CPerformanceData::GetValue(v20, PerfIndex, v18, Buffer, v64, &v62);
        if ( v62 != v63 )
          CInstance::SetDWORD(a4, L"LoadPercentage", 100 - 100LL * (*(_QWORD *)v64 - *(_QWORD *)v60) / (v62 - v63));
      }
    }
    CSmartBuffer::~CSmartBuffer((CSmartBuffer *)&v55);
  }
  v21 = -1;
  do
    ++v21;
  while ( v70[v21] );
  if ( v21 )
    CInstance::SetCharSplat(a4, L"Stepping", v70);
  CInstance::SetCharSplat(a4, L"Version", v68);
  CInstance::SetCharSplat(a4, L"Manufacturer", v69);
  LOWORD(v55) = v66[0];
  CInstance::SetWBEMINT16(a4, L"Architecture", (const __int16 *)&v55);
  if ( v71 )
    CInstance::SetDWORD(a4, L"CurrentClockSpeed", v71);
  LOWORD(v55) = v82;
  CInstance::SetWBEMINT16(a4, L"UpgradeMethod", (const __int16 *)&v55);
  v22 = v65;
  v23 = v72;
  if ( *(_DWORD *)(v65 + 4) == -1 )
  {
    if ( v72 == -1 )
      goto LABEL_33;
  }
  else if ( v72 == -1 || *(_DWORD *)(v65 + 4) >= v72 )
  {
    v23 = *(_DWORD *)(v65 + 4);
  }
  CInstance::SetDWORD(a4, L"L2CacheSize", v23);
LABEL_33:
  if ( v73 != -1 )
    CInstance::SetDWORD(a4, L"L2CacheSpeed", v73);
  if ( v75 != -1 )
    CInstance::SetDWORD(a4, L"L3CacheSpeed", v75);
  v24 = v74;
  if ( *(_DWORD *)(v22 + 8) == -1 )
  {
    if ( v74 == -1 )
      goto LABEL_43;
  }
  else if ( v74 == -1 || *(_DWORD *)(v22 + 8) >= v74 )
  {
    v24 = *(_DWORD *)(v22 + 8);
  }
  CInstance::SetDWORD(a4, L"L3CacheSize", v24);
LABEL_43:
  LOWORD(v55) = v66[22];
  CInstance::SetWBEMINT16(a4, L"Level", (const __int16 *)&v55);
  LOWORD(v55) = v66[23];
  CInstance::SetWBEMINT16(a4, L"Revision", (const __int16 *)&v55);
  if ( v76 )
  {
    LODWORD(v53) = v78;
    LODWORD(v52) = (unsigned __int16)v76;
    StringCbPrintfW(Buffer, 0xC8u, L"%04X-%04X-%04X-%04X-%04X-%04X", HIWORD(v76), v52, v53, v77, v80, v79);
    CInstance::SetCharSplat(a4, L"UniqueId", Buffer);
  }
  CInstance::SetDWORD(a4, L"CpuStatus", 0);
  if ( v71 > a6 )
    v13 = v71;
  CInstance::SetDWORD(a4, L"MaxClockSpeed", v13);
  LODWORD(v55) = 0;
  if ( (unsigned int)CSMBios::Init((CSMBios *)&v55, v25) )
  {
    NthStruct = CSMBios::GetNthStruct(v26, 4u, a2);
    v28 = NthStruct;
    if ( NthStruct )
    {
      v29 = CSMBios::m_Version;
      CInstance::SetDWORD(a4, L"CpuStatus", *((_BYTE *)NthStruct + 24) & 7);
      if ( *((_WORD *)v28 + 9) )
        CInstance::SetDWORD(a4, L"ExtClock", *((unsigned __int16 *)v28 + 9));
      v30 = v71;
      if ( !v71 )
      {
        v31 = *((unsigned __int16 *)v28 + 11);
        v71 = v31;
        CInstance::SetDWORD(a4, L"CurrentClockSpeed", v31);
        v30 = v71;
      }
      if ( !v13 )
      {
        v32 = *((unsigned __int16 *)v28 + 10);
        if ( v30 > v32 )
        {
          *((_WORD *)v28 + 10) = v71;
          LOWORD(v32) = v71;
        }
        CInstance::SetDWORD(a4, L"MaxClockSpeed", (unsigned __int16)v32);
      }
      LODWORD(v54) = *((unsigned __int16 *)v28 + 4);
      LODWORD(v53) = *((unsigned __int16 *)v28 + 5);
      LODWORD(v52) = *((unsigned __int16 *)v28 + 6);
      StringCbPrintfW(Buffer, 0x82u, L"%04X%04X%04X%04X", *((unsigned __int16 *)v28 + 7), v52, v53, v54);
      CInstance::SetCHString(a4, L"ProcessorId", Buffer);
      CInstance::SetDWORD(a4, L"ProcessorType", *((unsigned __int8 *)v28 + 5));
      v33 = *((unsigned __int8 *)v28 + 17);
      if ( (v33 & 0x80u) != 0 )
      {
        v34 = v33 & 0x7F;
        v35 = L"CurrentVoltage";
        goto LABEL_67;
      }
      v36 = v33 - 1;
      if ( v36 )
      {
        v37 = v36 - 1;
        if ( v37 )
        {
          if ( v37 != 2 )
          {
LABEL_66:
            v34 = *((_BYTE *)v28 + 17) & 7;
            v35 = L"VoltageCaps";
LABEL_67:
            CInstance::SetDWORD(a4, v35, v34);
            CSMBios::GetStringAtOffset(v39, v28, Buffer, *((unsigned __int8 *)v28 + 4));
            CInstance::SetCHString(a4, L"SocketDesignation", Buffer);
            CSMBios::GetStringAtOffset(v40, v28, Buffer, *((unsigned __int8 *)v28 + 16));
            if ( Buffer[0] && !v58 )
              CInstance::SetCHString(a4, L"Name", Buffer);
            LOWORD(v55) = *((unsigned __int8 *)v28 + 6);
            if ( v29 >= 0x20006 )
              LOWORD(v55) = *((_WORD *)v28 + 20);
            CInstance::SetWBEMINT16(a4, L"Family", (const __int16 *)&v55);
            if ( v29 >= 0x20003 )
            {
              CSMBios::GetStringAtOffset(v41, v28, Buffer, *((unsigned __int8 *)v28 + 32));
              CInstance::SetCHString(a4, L"SerialNumber", Buffer);
              CSMBios::GetStringAtOffset(v42, v28, Buffer, *((unsigned __int8 *)v28 + 33));
              CInstance::SetCHString(a4, L"AssetTag", Buffer);
              CSMBios::GetStringAtOffset(v43, v28, Buffer, *((unsigned __int8 *)v28 + 34));
              CInstance::SetCHString(a4, L"PartNumber", Buffer);
            }
            if ( v29 >= 0x20005 )
            {
              v44 = *((unsigned __int8 *)v28 + 36);
              v45 = *((unsigned __int8 *)v28 + 37);
              if ( v29 >= 0x30000 )
              {
                if ( v44 == 255 )
                  v44 = *((unsigned __int16 *)v28 + 22);
                if ( v45 == 255 )
                  v45 = *((unsigned __int16 *)v28 + 23);
              }
              CInstance::SetDWORD(a4, L"NumberOfEnabledCore", v44);
              CInstance::SetDWORD(a4, L"ThreadCount", v45);
            }
            if ( v29 >= 0x20006 )
              CInstance::SetDWORD(a4, L"Characteristics", *((unsigned __int16 *)v28 + 19));
            goto LABEL_83;
          }
          v38 = 29;
        }
        else
        {
          v38 = 33;
        }
      }
      else
      {
        v38 = 50;
      }
      CInstance::SetDWORD(a4, L"CurrentVoltage", v38);
      goto LABEL_66;
    }
  }
LABEL_83:
  v46 = v66[0];
  if ( v66[0] == 6 || v66[0] == 5 )
  {
    LOWORD(v55) = v81;
    CInstance::SetWBEMINT16(a4, L"Family", (const __int16 *)&v55);
    CInstance::SetCHString(a4, L"Name", v67);
    v46 = v66[0];
  }
  if ( v46 == 9 || !v46 )
  {
    CInstance::Setbool(a4, L"VMMonitorModeExtensions", v83 != 0);
    v51 = IsProcessorFeaturePresent(0x14u);
    CInstance::Setbool(a4, L"SecondLevelAddressTranslationExtensions", v51);
    v48 = IsProcessorFeaturePresent(0x15u);
    v49 = L"VirtualizationFirmwareEnabled";
    goto LABEL_92;
  }
  if ( v46 == 12 )
  {
    v47 = IsProcessorFeaturePresent(0x15u);
    CInstance::Setbool(a4, L"VMMonitorModeExtensions", v47);
    CInstance::Setbool(a4, L"VirtualizationFirmwareEnabled", v47);
    v48 = IsProcessorFeaturePresent(0x14u);
    v49 = L"SecondLevelAddressTranslationExtensions";
LABEL_92:
    v50 = v48;
    goto LABEL_93;
  }
  CInstance::Setbool(a4, L"VMMonitorModeExtensions", 0);
  CInstance::Setbool(a4, L"SecondLevelAddressTranslationExtensions", 0);
  v50 = 0;
  v49 = L"VirtualizationFirmwareEnabled";
LABEL_93:
  CInstance::Setbool(a4, v49, v50);
  CHString::~CHString((CHString *)v61);
  CHString::~CHString((CHString *)&v56);
  CHString::~CHString((CHString *)&v57);
  CRegistry::~CRegistry((CRegistry *)v84);
  CHString::~CHString((CHString *)&v59);
  return 1;
}

```

## disassembly

```asm
0x1800c6ca8  push    rbp
0x1800c6caa  push    rbx
0x1800c6cab  push    rsi
0x1800c6cac  push    rdi
0x1800c6cad  push    r12
0x1800c6caf  push    r13
0x1800c6cb1  push    r14
0x1800c6cb3  lea     rbp, [rsp-700h]
0x1800c6cbb  sub     rsp, 800h
0x1800c6cc2  mov     rax, cs:__security_cookie
0x1800c6cc9  xor     rax, rsp
0x1800c6ccc  mov     [rbp+730h+var_40], rax
0x1800c6cd3  mov     rdi, r9
0x1800c6cd6  mov     r14, r8
0x1800c6cd9  mov     r13d, edx
0x1800c6cdc  mov     rbx, [rbp+730h+arg_20]
0x1800c6ce3  mov     qword ptr [rsp+830h+var_7B8], rbx
0x1800c6ce8  mov     rax, [rbp+730h+arg_38]
0x1800c6cef  mov     [rbp+730h+var_790], rax
0x1800c6cf3  mov     r9d, edx
0x1800c6cf6  lea     r8, aCpuD; "CPU%d"
0x1800c6cfd  mov     edx, 0C8h; unsigned __int64
0x1800c6d02  lea     rcx, [rbp+730h+var_110]; unsigned __int16 *
0x1800c6d09  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800c6d0e  lea     r8, [rbp+730h+var_110]
0x1800c6d15  lea     rdx, aDeviceid; "DeviceID"
0x1800c6d1c  mov     rcx, rdi
0x1800c6d1f  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x1800c6d25  xor     r12d, r12d
0x1800c6d28  cmp     [rbx+48h], r12b
0x1800c6d2c  jnz     loc_1800C7847
0x1800c6d32  xor     edx, edx; Val
0x1800c6d34  mov     r8d, 340h; Size
0x1800c6d3a  lea     rcx, [rbp+730h+var_780]; void *
0x1800c6d3e  call    memset_0
0x1800c6d43  mov     ebx, [rbp+730h+arg_30]
0x1800c6d49  mov     r9d, ebx
0x1800c6d4c  lea     r8, [rbp+730h+var_780]; struct _tagSYSTEM_INFO_EX *
0x1800c6d50  mov     rdx, r14; struct _PROCESSOR_NUMBER *
0x1800c6d53  mov     ecx, r13d; unsigned int
0x1800c6d56  call    GetSystemInfoEx
0x1800c6d5b  test    eax, eax
0x1800c6d5d  jz      loc_1800C784C
0x1800c6d63  mov     esi, [rbp+730h+arg_28]
0x1800c6d69  test    esi, esi
0x1800c6d6b  jz      short loc_1800C6D71
0x1800c6d6d  test    ebx, ebx
0x1800c6d6f  jnz     short loc_1800C6DB9
0x1800c6d71  mov     dword ptr [rsp+830h+var_810], ebx
0x1800c6d75  mov     r9d, esi
0x1800c6d78  lea     r8, aZeroProcessorS; "Zero processor speed returned from kern"...
0x1800c6d7f  mov     edx, 0C8h; unsigned __int64
0x1800c6d84  lea     rcx, [rbp+730h+Buffer]; unsigned __int16 *
0x1800c6d8b  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800c6d90  mov     dword ptr [rsp+830h+var_810], 1
0x1800c6d98  mov     r9d, 33Fh
0x1800c6d9e  lea     r8, aOnecoreAdminWm_13; "onecore\\admin\\wmi\\wbem\\providers\\w"...
0x1800c6da5  lea     rdx, [rbp+730h+Buffer]
0x1800c6dac  mov     rcx, cs:__imp_?captainsLog@@3VProviderLog@@A; ProviderLog captainsLog
0x1800c6db3  call    cs:__imp_?LocalLogMessage@ProviderLog@@QEAAXPEBG0HW4LogLevel@1@@Z; ProviderLog::LocalLogMessage(ushort const *,ushort const *,int,ProviderLog::LogLevel)
0x1800c6db9  lea     r8, aCpu; "CPU"
0x1800c6dc0  lea     rdx, aRole; "Role"
0x1800c6dc7  mov     rcx, rdi
0x1800c6dca  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCHString(ushort const *,ushort const *)
0x1800c6dd0  lea     r8, aOk; "OK"
0x1800c6dd7  lea     rdx, aStatus; "Status"
0x1800c6dde  mov     rcx, rdi
0x1800c6de1  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x1800c6de7  lea     r8, aWin32Processor; "Win32_Processor"
0x1800c6dee  lea     rdx, aCreationclassn; "CreationClassName"
0x1800c6df5  mov     rcx, rdi
0x1800c6df8  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x1800c6dfe  xor     r8d, r8d
0x1800c6e01  lea     rdx, aPowermanagemen_0; "PowerManagementSupported"
0x1800c6e08  mov     rcx, rdi
0x1800c6e0b  call    cs:__imp_?Setbool@CInstance@@QEAA_NPEBG_N@Z; CInstance::Setbool(ushort const *,bool)
0x1800c6e11  lea     r8, aWin32Computers_0; "Win32_ComputerSystem"
0x1800c6e18  lea     rdx, aSystemcreation; "SystemCreationClassName"
0x1800c6e1f  mov     rcx, rdi
0x1800c6e22  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x1800c6e28  mov     r8, cs:__imp_?s_strComputerName@Provider@@0VCHString@@A; CHString Provider::s_strComputerName
0x1800c6e2f  lea     rdx, aSystemname; "SystemName"
0x1800c6e36  mov     rcx, rdi
0x1800c6e39  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z; CInstance::SetCHString(ushort const *,CHString const &)
0x1800c6e3f  mov     ebx, 3
0x1800c6e44  mov     word ptr [rsp+830h+var_7E0], bx
0x1800c6e49  lea     r8, [rsp+830h+var_7E0]
0x1800c6e4e  lea     rdx, aAvailability; "Availability"
0x1800c6e55  mov     rcx, rdi
0x1800c6e58  call    cs:__imp_?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z; CInstance::SetWBEMINT16(ushort const *,short const &)
0x1800c6e5e  mov     word ptr [rsp+830h+var_7E0], bx
0x1800c6e63  lea     r8, [rsp+830h+var_7E0]
0x1800c6e68  lea     rdx, aStatusinfo; "StatusInfo"
0x1800c6e6f  mov     rcx, rdi
0x1800c6e72  call    cs:__imp_?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z; CInstance::SetWBEMINT16(ushort const *,short const &)
0x1800c6e78  lea     eax, [rbx-1]
0x1800c6e7b  mov     word ptr [rsp+830h+var_7E0], ax
0x1800c6e80  lea     r8, [rsp+830h+var_7E0]
0x1800c6e85  lea     rdx, aFamily; "Family"
0x1800c6e8c  mov     rcx, rdi
0x1800c6e8f  call    cs:__imp_?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z; CInstance::SetWBEMINT16(ushort const *,short const &)
0x1800c6e95  lea     rcx, [rsp+830h+var_7C0]
0x1800c6e9a  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x1800c6ea0  nop
0x1800c6ea1  mov     r8d, r13d
0x1800c6ea4  lea     edx, [rbx+29h]; unsigned int
0x1800c6ea7  lea     rcx, [rsp+830h+var_7C0]; struct CHString *
0x1800c6eac  call    ?Format@@YAXAEAVCHString@@IZZ; Format(CHString &,uint,...)
0x1800c6eb1  mov     r8, [rsp+830h+var_7C0]
0x1800c6eb6  lea     rdx, aCaption; "Caption"
0x1800c6ebd  mov     rcx, rdi
0x1800c6ec0  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x1800c6ec6  mov     r8, [rsp+830h+var_7C0]
0x1800c6ecb  lea     rdx, aDescription; "Description"
0x1800c6ed2  mov     rcx, rdi
0x1800c6ed5  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x1800c6edb  mov     ebx, 40h ; '@'
0x1800c6ee0  mov     r8d, ebx
0x1800c6ee3  lea     rdx, aAddresswidth; "AddressWidth"
0x1800c6eea  mov     rcx, rdi
0x1800c6eed  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x1800c6ef3  mov     r8d, ebx
0x1800c6ef6  lea     rdx, aDatawidth; "DataWidth"
0x1800c6efd  mov     rcx, rdi
0x1800c6f00  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x1800c6f06  lea     rcx, [rbp+730h+var_440]
0x1800c6f0d  call    cs:__imp_??0CRegistry@@QEAA@XZ; CRegistry::CRegistry(void)
0x1800c6f13  nop
0x1800c6f14  lea     rcx, [rsp+830h+var_7D0]
0x1800c6f19  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x1800c6f1f  nop
0x1800c6f20  lea     rcx, [rsp+830h+var_7D8]
0x1800c6f25  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x1800c6f2b  nop
0x1800c6f2c  mov     [rsp+830h+var_7C8], r12d
0x1800c6f31  lea     rcx, [rbp+730h+var_7B0]
0x1800c6f35  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x1800c6f3b  nop
0x1800c6f3c  xor     r8d, r8d
0x1800c6f3f  jmp     short loc_1800C6F6D
0x1800c6f41  xor     edx, edx
0x1800c6f43  lea     rcx, [rsp+830h+var_7D0]
0x1800c6f48  call    cs:__imp_?GetBuffer@CHString@@QEAAPEAGH@Z; CHString::GetBuffer(int)
0x1800c6f4e  movzx   ecx, word ptr [r14]
0x1800c6f52  cmp     [rax+0Ch], cx
0x1800c6f56  jnz     short loc_1800C6F67
0x1800c6f58  movzx   ecx, byte ptr [r14+2]
0x1800c6f5d  cmp     [rax+0Eh], cx
0x1800c6f61  jz      loc_1800C71A4
0x1800c6f67  inc     r12d
0x1800c6f6a  mov     r8d, r12d
0x1800c6f6d  lea     rdx, aHardwareDescri_1; "HARDWARE\\DESCRIPTION\\System\\CentralP"...
0x1800c6f74  lea     rcx, [rsp+830h+var_7D8]
0x1800c6f79  call    cs:__imp_?Format@CHString@@QEAAXPEBGZZ; CHString::Format(ushort const *,...)
0x1800c6f7f  lea     r9, [rsp+830h+var_7D0]
0x1800c6f84  lea     r8, aComponentInfor; "Component Information"
0x1800c6f8b  mov     rdx, [rsp+830h+var_7D8]
0x1800c6f90  lea     rcx, [rbp+730h+var_440]
0x1800c6f97  call    cs:__imp_?OpenLocalMachineKeyAndReadValue@CRegistry@@QEAAJPEBG0AEAVCHString@@@Z; CRegistry::OpenLocalMachineKeyAndReadValue(ushort const *,ushort const *,CHString &)
0x1800c6f9d  test    eax, eax
0x1800c6f9f  jz      short loc_1800C6F41
0x1800c6fa1  xor     r14d, r14d
0x1800c6fa4  lea     rdx, aLoadpercentage; "LoadPercentage"
0x1800c6fab  mov     rcx, qword ptr [rsp+830h+var_7B8]
0x1800c6fb0  call    cs:__imp_?IsPropertyRequired@CFrameworkQuery@@QEAA_NPEBG@Z; CFrameworkQuery::IsPropertyRequired(ushort const *)
0x1800c6fb6  test    al, al
0x1800c6fb8  jz      loc_1800C70B9
0x1800c6fbe  mov     qword ptr [rsp+830h+var_7B8], r14
0x1800c6fc3  mov     qword ptr [rbp+730h+var_798], r14
0x1800c6fc7  mov     [rbp+730h+var_7A0], r14
0x1800c6fcb  mov     [rbp+730h+var_7A8], r14
0x1800c6fcf  mov     [rsp+830h+var_7E0], r14
0x1800c6fd4  lea     rdx, aProcessor; "Processor"
0x1800c6fdb  lea     rcx, [rsp+830h+var_7E0]; this
0x1800c6fe0  call    ?GetPerfIndex@CPerformanceData@@QEAAKPEBG@Z; CPerformanceData::GetPerfIndex(ushort const *)
0x1800c6fe5  mov     r14d, eax
0x1800c6fe8  lea     rdx, aProcessorTime; "% Processor Time"
0x1800c6fef  lea     rcx, [rsp+830h+var_7E0]; this
0x1800c6ff4  call    ?GetPerfIndex@CPerformanceData@@QEAAKPEBG@Z; CPerformanceData::GetPerfIndex(ushort const *)
0x1800c6ff9  mov     ebx, eax
0x1800c6ffb  test    r14d, r14d
0x1800c6ffe  jz      loc_1800C70AC
0x1800c7004  test    eax, eax
0x1800c7006  jz      loc_1800C70AC
0x1800c700c  mov     r8d, 0Ah; Radix
0x1800c7012  lea     rdx, [rbp+730h+Buffer]; Buffer
0x1800c7019  mov     ecx, r12d; Value
0x1800c701c  call    cs:__imp__itow
0x1800c7022  lea     rax, [rbp+730h+var_7A0]
0x1800c7026  mov     [rsp+830h+var_808], rax; unsigned __int64 *
0x1800c702b  lea     rax, [rsp+830h+var_7B8]
0x1800c7030  mov     [rsp+830h+var_810], rax; unsigned __int8 *
0x1800c7035  lea     r9, [rbp+730h+Buffer]; unsigned __int16 *
0x1800c703c  mov     r8d, ebx; unsigned int
0x1800c703f  mov     edx, r14d; unsigned int
0x1800c7042  call    ?GetValue@CPerformanceData@@QEAA_NKKPEBGPEAEPEA_K@Z; CPerformanceData::GetValue(ulong,ulong,ushort const *,uchar *,unsigned __int64 *)
0x1800c7047  mov     ecx, 3E8h; dwMilliseconds
0x1800c704c  call    cs:__imp_Sleep
0x1800c7052  lea     rax, [rbp+730h+var_7A8]
0x1800c7056  mov     [rsp+830h+var_808], rax; unsigned __int64 *
0x1800c705b  lea     rax, [rbp+730h+var_798]
0x1800c705f  mov     [rsp+830h+var_810], rax; unsigned __int8 *
0x1800c7064  lea     r9, [rbp+730h+Buffer]; unsigned __int16 *
0x1800c706b  mov     r8d, ebx; unsigned int
0x1800c706e  mov     edx, r14d; unsigned int
0x1800c7071  call    ?GetValue@CPerformanceData@@QEAA_NKKPEBGPEAEPEA_K@Z; CPerformanceData::GetValue(ulong,ulong,ushort const *,uchar *,unsigned __int64 *)
0x1800c7076  mov     rcx, [rbp+730h+var_7A8]
0x1800c707a  sub     rcx, [rbp+730h+var_7A0]
0x1800c707e  jz      short loc_1800C70AC
0x1800c7080  mov     rax, qword ptr [rbp+730h+var_798]
0x1800c7084  sub     rax, qword ptr [rsp+830h+var_7B8]
0x1800c7089  imul    rax, 64h ; 'd'
0x1800c708d  xor     edx, edx
0x1800c708f  div     rcx
0x1800c7092  mov     r8d, 64h ; 'd'
0x1800c7098  sub     r8d, eax
0x1800c709b  lea     rdx, aLoadpercentage; "LoadPercentage"
0x1800c70a2  mov     rcx, rdi
0x1800c70a5  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x1800c70ab  nop
0x1800c70ac  lea     rcx, [rsp+830h+var_7E0]; this
0x1800c70b1  call    ??1CSmartBuffer@@QEAA@XZ; CSmartBuffer::~CSmartBuffer(void)
0x1800c70b6  xor     r14d, r14d
0x1800c70b9  lea     rcx, [rbp+730h+var_4A8]
0x1800c70c0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800c70c4  inc     rax
0x1800c70c7  cmp     [rcx+rax*2], r14w
0x1800c70cc  jnz     short loc_1800C70C4
0x1800c70ce  test    rax, rax
0x1800c70d1  jz      short loc_1800C70EA
0x1800c70d3  lea     r8, [rbp+730h+var_4A8]
0x1800c70da  lea     rdx, aStepping; "Stepping"
0x1800c70e1  mov     rcx, rdi
0x1800c70e4  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x1800c70ea  lea     r8, [rbp+730h+var_5C0]
0x1800c70f1  lea     rdx, aVersion; "Version"
0x1800c70f8  mov     rcx, rdi
0x1800c70fb  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x1800c7101  lea     r8, [rbp+730h+var_4F8]
0x1800c7108  lea     rdx, aManufacturer; "Manufacturer"
0x1800c710f  mov     rcx, rdi
0x1800c7112  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x1800c7118  movzx   eax, [rbp+730h+var_780]
0x1800c711c  mov     word ptr [rsp+830h+var_7E0], ax
0x1800c7121  lea     r8, [rsp+830h+var_7E0]
0x1800c7126  lea     rdx, aArchitecture; "Architecture"
0x1800c712d  mov     rcx, rdi
0x1800c7130  call    cs:__imp_?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z; CInstance::SetWBEMINT16(ushort const *,short const &)
0x1800c7136  mov     r8d, [rbp+730h+var_484]
0x1800c713d  test    r8d, r8d
0x1800c7140  jz      short loc_1800C7152
0x1800c7142  lea     rdx, aCurrentclocksp; "CurrentClockSpeed"
0x1800c7149  mov     rcx, rdi
0x1800c714c  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x1800c7152  movzx   eax, [rbp+730h+var_44E]
0x1800c7159  mov     word ptr [rsp+830h+var_7E0], ax
0x1800c715e  lea     r8, [rsp+830h+var_7E0]
0x1800c7163  lea     rdx, aUpgrademethod; "UpgradeMethod"
0x1800c716a  mov     rcx, rdi
0x1800c716d  call    cs:__imp_?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z; CInstance::SetWBEMINT16(ushort const *,short const &)
0x1800c7173  or      r12d, 0FFFFFFFFh
0x1800c7177  mov     rbx, [rbp+730h+var_790]
0x1800c717b  mov     r8d, [rbp+730h+var_480]
0x1800c7182  cmp     [rbx+4], r12d
0x1800c7186  jz      loc_1800C7239
0x1800c718c  cmp     r8d, r12d
0x1800c718f  jz      short loc_1800C719B
0x1800c7191  cmp     [rbx+4], r8d
0x1800c7195  jb      loc_1800C723E
0x1800c719b  mov     r8d, [rbx+4]
0x1800c719f  jmp     loc_1800C723E
0x1800c71a4  lea     r9, [rsp+830h+var_7D0]
0x1800c71a9  lea     r8, aIdentifier; "Identifier"
0x1800c71b0  mov     rdx, [rsp+830h+var_7D8]
0x1800c71b5  lea     rcx, [rbp+730h+var_440]
0x1800c71bc  call    cs:__imp_?OpenLocalMachineKeyAndReadValue@CRegistry@@QEAAJPEBG0AEAVCHString@@@Z; CRegistry::OpenLocalMachineKeyAndReadValue(ushort const *,ushort const *,CHString &)
0x1800c71c2  xor     r14d, r14d
0x1800c71c5  test    eax, eax
0x1800c71c7  jnz     short loc_1800C71F3
0x1800c71c9  mov     r8, [rsp+830h+var_7D0]
0x1800c71ce  lea     rdx, aDescription; "Description"
0x1800c71d5  mov     rcx, rdi
0x1800c71d8  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x1800c71de  mov     r8, [rsp+830h+var_7D0]
0x1800c71e3  lea     rdx, aCaption; "Caption"
0x1800c71ea  mov     rcx, rdi
0x1800c71ed  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x1800c71f3  lea     r9, [rbp+730h+var_7B0]
0x1800c71f7  lea     r8, aProcessornames; "ProcessorNameString"
0x1800c71fe  mov     rdx, [rsp+830h+var_7D8]
0x1800c7203  lea     rcx, [rbp+730h+var_440]
0x1800c720a  call    cs:__imp_?OpenLocalMachineKeyAndReadValue@CRegistry@@QEAAJPEBG0AEAVCHString@@@Z; CRegistry::OpenLocalMachineKeyAndReadValue(ushort const *,ushort const *,CHString &)
0x1800c7210  test    eax, eax
0x1800c7212  jnz     loc_1800C6FA4
0x1800c7218  lea     r8, [rbp+730h+var_7B0]
0x1800c721c  lea     rdx, aName; "Name"
0x1800c7223  mov     rcx, rdi
0x1800c7226  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z; CInstance::SetCHString(ushort const *,CHString const &)
0x1800c722c  mov     [rsp+830h+var_7C8], 1
0x1800c7234  jmp     loc_1800C6FA4
  ... truncated ...
```
