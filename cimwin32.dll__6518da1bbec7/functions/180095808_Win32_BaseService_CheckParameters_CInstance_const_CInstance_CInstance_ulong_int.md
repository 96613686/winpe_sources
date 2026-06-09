# Win32_BaseService::CheckParameters(CInstance const &,CInstance *,CInstance *,ulong &,int)

- ea: `0x180095808`
- end: `0x180096ed3`
- name: `?CheckParameters@Win32_BaseService@@IEAAKAEBVCInstance@@PEAV2@1AEAKH@Z`
- size: `5835`
- prototype: `__int64 __fastcall(Win32_BaseService *this, const struct CInstance *, struct CInstance *, struct CInstance *, unsigned int *, unsigned int cbBufSize)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180096fb8`
- `0x180097420`

## callees

- `0x18000ab30`
- `0x180013ae0`
- `0x18002f1cc`
- `0x180044b1c`
- `0x18008bb9c`
- `0x180095808`
- `0x1800981e4`
- `0x180098390`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095fbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096ba7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095fbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096ba7`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18009584e`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180095941`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800959ed`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180095c79`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180095dc4`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180095e62`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180096148`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18009584e`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180095941`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800959ed`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180095c79`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180095dc4`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180095e62`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180096148`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800958a5`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800959b9`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x180095a5f`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x180095cf4`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x180095e2d`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x180095ec6`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800961b2`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800958a5`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800959b9`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x180095a5f`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x180095cf4`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x180095e2d`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x180095ec6`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800961b2`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x180095d19`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x180095d40`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x180095d62`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x180095d88`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x180095dae`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x180095d19`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x180095d40`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x180095d62`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x180095d88`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x180095dae`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180095f69`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18009633c`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180096576`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800967a9`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800967d1`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800968fb`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180096922`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180096a25`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180096a36`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180096a4c`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180096a6c`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180096a88`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180096aa6`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180096b56`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180096bfb`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180096c25`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180096c45`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180096c63`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180096c83`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180095f69`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18009633c`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180096576`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800967a9`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800967d1`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800968fb`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180096922`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180096a25`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180096a36`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180096a4c`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180096a6c`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180096a88`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180096aa6`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180096b56`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180096bfb`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180096c25`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180096c45`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180096c63`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180096c83`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800960cb`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800960cb`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x18009632d`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x180096567`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x18009679a`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800968ec`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x18009632d`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x180096567`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x18009679a`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800968ec`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x1800958b9`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x1800959cf`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x180095a75`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x180095e3f`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x1800961c4`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x1800958b9`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x1800959cf`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x180095a75`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x180095e3f`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x1800961c4`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x180095876`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x18009595c`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x180095a08`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x180095a9f`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x180095bb3`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x180095c94`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x180095ddf`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x180095e7d`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x180095ef6`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x180096163`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x18009620b`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x180096449`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x180095876`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x18009595c`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x180095a08`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x180095a9f`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x180095bb3`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x180095c94`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x180095ddf`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x180095e7d`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x180095ef6`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x180096163`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x18009620b`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x180096449`
- `framedynos!?GetStringArray@CInstance@@QEBA_NPEBGAEAPEAUtagSAFEARRAY@@@Z` at `0x180096257`
- `framedynos!?GetStringArray@CInstance@@QEBA_NPEBGAEAPEAUtagSAFEARRAY@@@Z` at `0x180096496`
- `framedynos!?GetStringArray@CInstance@@QEBA_NPEBGAEAPEAUtagSAFEARRAY@@@Z` at `0x180096257`
- `framedynos!?GetStringArray@CInstance@@QEBA_NPEBGAEAPEAUtagSAFEARRAY@@@Z` at `0x180096496`
- `framedynos!?Getbool@CInstance@@QEBA_NPEBGAEA_N@Z` at `0x1800960f6`
- `framedynos!?Getbool@CInstance@@QEBA_NPEBGAEA_N@Z` at `0x1800960f6`
- `framedynos!?GetByte@CInstance@@QEBA_NPEBGAEAE@Z` at `0x180095b06`
- `framedynos!?GetByte@CInstance@@QEBA_NPEBGAEAE@Z` at `0x180095c10`
- `framedynos!?GetByte@CInstance@@QEBA_NPEBGAEAE@Z` at `0x180095b06`
- `framedynos!?GetByte@CInstance@@QEBA_NPEBGAEAE@Z` at `0x180095c10`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180096075`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180096084`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180096093`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800960a2`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180096365`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800963b6`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800963c5`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800963d4`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800963e3`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800963f2`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180096401`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180096410`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18009659d`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180096611`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180096620`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18009662f`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18009663e`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18009664d`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18009665c`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18009666b`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800967fa`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180096949`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180096d90`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180096dbd`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180096de0`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180096e03`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180096e26`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180096e49`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180096e58`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180096e74`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180096e83`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180096e9c`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180096eab`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180096075`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180096084`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180096093`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800960a2`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180096365`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800963b6`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800963c5`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800963d4`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800963e3`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800963f2`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180096401`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180096410`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18009659d`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180096611`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180096620`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18009662f`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18009663e`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18009664d`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18009665c`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18009666b`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800967fa`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180096949`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180096d90`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180096dbd`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180096de0`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180096e03`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180096e26`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180096e49`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180096e58`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180096e74`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180096e83`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180096e9c`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180096eab`

## string_xrefs

- `0x180095a95`: `ServiceType`
- `0x180095afc`: `ServiceType`
- `0x1800959fe`: `PathName`
- `0x180095a55`: `PathName`
- `0x18009643f`: `ServiceDependencies`
- `0x18009648c`: `ServiceDependencies`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Win32_BaseService::CheckParameters(
        Win32_BaseService *this,
        const struct CInstance *a2,
        struct CInstance *a3,
        struct CInstance *a4,
        unsigned int *a5,
        unsigned int cbBufSize)
{
  unsigned int *v9; // r14
  Win32_BaseService *v10; // rcx
  unsigned int v11; // r12d
  int ServiceStatus; // ebx
  Win32_BaseService *v13; // rcx
  SC_HANDLE v14; // r12
  const WCHAR *v15; // rax
  Win32_BaseService *v16; // rcx
  SC_HANDLE v17; // r13
  DWORD *v18; // r12
  Win32_BaseService *v19; // rcx
  OLECHAR *v20; // rax
  BOOL ServiceConfigW; // eax
  unsigned int ServiceErrorCode; // eax
  int v23; // r15d
  int v24; // r12d
  int i; // eax
  __int64 v26; // rax
  __int64 v27; // rcx
  bool StringArray; // al
  int v29; // esi
  int j; // eax
  __int64 v31; // rax
  __int64 v32; // rcx
  int v34; // r13d
  LONG v35; // eax
  unsigned __int16 *v36; // r12
  const unsigned __int16 *v37; // rax
  __int64 v38; // rax
  __int64 v39; // rcx
  const WCHAR *lpLoadOrderGroup; // r12
  LONG v41; // eax
  unsigned __int16 *v42; // r15
  const unsigned __int16 *v43; // rax
  __int64 v44; // rax
  __int64 v45; // rcx
  Win32_BaseService *v46; // rcx
  SC_HANDLE v47; // rsi
  const WCHAR *v48; // r13
  const WCHAR *lpPassword; // rax
  const WCHAR *lpServiceStartName; // r15
  unsigned int v51; // eax
  BSTR *p_pcbBytesNeeded; // rcx
  const WCHAR *v53; // rax
  SC_HANDLE v54; // rax
  Win32_BaseService *v55; // rcx
  SC_HANDLE v56; // rsi
  struct _QUERY_SERVICE_CONFIGW *v57; // rdi
  Win32_BaseService *v58; // rcx
  const WCHAR *v59; // r13
  const WCHAR *v60; // r15
  const WCHAR *v61; // rax
  DWORD v62; // r8d
  DWORD v63; // edx
  DWORD v64; // r10d
  unsigned int v65; // eax
  bool v66[4]; // [rsp+70h] [rbp-118h] BYREF
  unsigned __int16 v67[2]; // [rsp+74h] [rbp-114h] BYREF
  bool v68; // [rsp+78h] [rbp-110h]
  char v69; // [rsp+79h] [rbp-10Fh]
  DWORD dwServiceType; // [rsp+7Ch] [rbp-10Ch]
  unsigned __int8 v71; // [rsp+80h] [rbp-108h] BYREF
  unsigned __int8 v72; // [rsp+81h] [rbp-107h] BYREF
  bool v73; // [rsp+82h] [rbp-106h] BYREF
  char v74; // [rsp+83h] [rbp-105h]
  char v75; // [rsp+84h] [rbp-104h]
  bool v76; // [rsp+85h] [rbp-103h]
  bool v77; // [rsp+86h] [rbp-102h]
  DWORD dwStartType; // [rsp+88h] [rbp-100h]
  LONG rgIndices; // [rsp+8Ch] [rbp-FCh] BYREF
  _BYTE v80[8]; // [rsp+90h] [rbp-F8h] BYREF
  LPCWSTR lpDisplayName; // [rsp+98h] [rbp-F0h] BYREF
  LONG plLbound; // [rsp+A0h] [rbp-E8h] BYREF
  _BYTE v83[8]; // [rsp+A8h] [rbp-E0h] BYREF
  _BYTE v84[8]; // [rsp+B0h] [rbp-D8h] BYREF
  SAFEARRAY *psa; // [rsp+B8h] [rbp-D0h] BYREF
  LONG plUbound; // [rsp+C0h] [rbp-C8h] BYREF
  unsigned __int16 *pv; // [rsp+C8h] [rbp-C0h] BYREF
  bool v88; // [rsp+D0h] [rbp-B8h] BYREF
  bool v89; // [rsp+D1h] [rbp-B7h] BYREF
  _BYTE v90[8]; // [rsp+D8h] [rbp-B0h] BYREF
  DWORD dwErrorControl; // [rsp+E0h] [rbp-A8h]
  SAFEARRAY *v92; // [rsp+E8h] [rbp-A0h] BYREF
  _BYTE v93[8]; // [rsp+F0h] [rbp-98h] BYREF
  _BYTE v94[8]; // [rsp+F8h] [rbp-90h] BYREF
  BSTR v95; // [rsp+100h] [rbp-88h] BYREF
  _BYTE v96[8]; // [rsp+108h] [rbp-80h] BYREF
  BSTR bstrString; // [rsp+110h] [rbp-78h] BYREF
  LONG v98; // [rsp+118h] [rbp-70h] BYREF
  LONG v99; // [rsp+11Ch] [rbp-6Ch] BYREF
  int v100; // [rsp+120h] [rbp-68h]
  int v101; // [rsp+124h] [rbp-64h]
  int v102; // [rsp+128h] [rbp-60h]
  LONG v103; // [rsp+12Ch] [rbp-5Ch] BYREF
  int pExceptionObject; // [rsp+130h] [rbp-58h] BYREF
  int v105; // [rsp+134h] [rbp-54h] BYREF
  int v106; // [rsp+138h] [rbp-50h] BYREF
  int v107; // [rsp+13Ch] [rbp-4Ch] BYREF
  int v108; // [rsp+140h] [rbp-48h] BYREF
  _DWORD v109[3]; // [rsp+144h] [rbp-44h] BYREF
  unsigned __int16 *v110; // [rsp+150h] [rbp-38h]
  SC_HANDLE pcbBytesNeeded; // [rsp+190h] [rbp+8h] BYREF

  pcbBytesNeeded = (SC_HANDLE)this;
  v9 = a5;
  *a5 = 0;
  v66[0] = 0;
  v67[0] = 0;
  CHString::CHString((CHString *)v94);
  v11 = cbBufSize;
  if ( cbBufSize )
  {
    if ( !CInstance::GetStatus(a3, L"Name", v66, v67) )
    {
      ServiceStatus = -2147217404;
      goto LABEL_9;
    }
    if ( !v66[0]
      || v67[0] != 8
      || !CInstance::GetCHString(a3, L"Name", (struct CHString *)v94)
      || (ServiceStatus = 0, CHString::IsEmpty((CHString *)v94)) )
    {
      ServiceStatus = 0;
LABEL_9:
      *v9 = 21;
LABEL_277:
      CHString::~CHString((CHString *)v94);
      return (unsigned int)ServiceStatus;
    }
  }
  else
  {
    LODWORD(pcbBytesNeeded) = 0;
    v89 = 0;
    v88 = 0;
    ServiceStatus = Win32_BaseService::GetServiceStatus(
                      v10,
                      a2,
                      (struct CHString *)v94,
                      (unsigned int *)&pcbBytesNeeded,
                      &v89,
                      &v88);
    if ( ServiceStatus < 0 )
    {
      *v9 = 8;
      goto LABEL_277;
    }
  }
  CHString::CHString((CHString *)v80);
  if ( CInstance::GetStatus(a3, L"DisplayName", v66, v67) )
  {
    if ( v66[0] && (v67[0] == 8 || v67[0] == 1) )
    {
      if ( v67[0] == 1 )
      {
        if ( !v11 )
        {
          v74 = 0;
LABEL_22:
          CHString::CHString((CHString *)v83);
          if ( !CInstance::GetStatus(a3, L"PathName", v66, v67) )
            goto LABEL_273;
          if ( !v66[0] || v67[0] != 8 && v67[0] != 1 )
            goto LABEL_272;
          if ( v67[0] == 1 )
          {
            if ( v11 )
              goto LABEL_272;
            v75 = 0;
          }
          else
          {
            if ( !CInstance::GetCHString(a3, L"PathName", (struct CHString *)v83) || CHString::IsEmpty((CHString *)v83) )
              goto LABEL_272;
            v75 = 1;
          }
          if ( !CInstance::GetStatus(a3, L"ServiceType", v66, v67) )
          {
LABEL_273:
            *v9 = 21;
            goto LABEL_274;
          }
          if ( !v66[0] || ((v67[0] - 1) & 0xFFEF) != 0 )
            goto LABEL_272;
          if ( v67[0] == 1 )
          {
            dwServiceType = 16;
            v68 = v11 != 0;
          }
          else
          {
            v71 = 0;
            if ( !CInstance::GetByte(a3, L"ServiceType", &v71) )
              goto LABEL_272;
            v68 = 1;
            if ( v71 == 1 )
            {
              dwServiceType = 1;
            }
            else
            {
              if ( v71 != 2 )
              {
                dwStartType = 4;
                switch ( v71 )
                {
                  case 4u:
                    dwServiceType = 4;
                    break;
                  case 8u:
                    dwServiceType = 8;
                    break;
                  case 0x10u:
                    dwServiceType = 16;
                    break;
                  case 0x20u:
                    dwServiceType = 32;
                    break;
                  default:
                    goto LABEL_272;
                }
                v11 = cbBufSize;
LABEL_52:
                v72 = 0;
                if ( CInstance::GetStatus(a3, L"ErrorControl", v66, v67) )
                {
                  if ( v66[0] && ((v67[0] - 1) & 0xFFEF) == 0 )
                  {
                    if ( v67[0] == 1 )
                    {
                      dwErrorControl = 0;
                      v76 = v11 != 0;
LABEL_66:
                      CHString::CHString((CHString *)v84);
                      if ( !CInstance::GetStatus(a3, L"StartMode", v66, v67) )
                      {
                        *v9 = 21;
                        goto LABEL_271;
                      }
                      if ( v66[0] && (v67[0] == 8 || v67[0] == 1) )
                      {
                        if ( v67[0] == 1 )
                        {
                          dwStartType = 2;
                          v77 = v11 != 0;
                          goto LABEL_82;
                        }
                        if ( CInstance::GetCHString(a3, L"StartMode", (struct CHString *)v84) )
                        {
                          v77 = 1;
                          if ( !CHString::CompareNoCase((CHString *)v84, L"Boot") )
                          {
                            dwStartType = 0;
                            goto LABEL_82;
                          }
                          if ( !CHString::CompareNoCase((CHString *)v84, L"System") )
                          {
                            dwStartType = 1;
                            goto LABEL_82;
                          }
                          if ( !CHString::CompareNoCase((CHString *)v84, L"Automatic") )
                          {
                            dwStartType = 2;
                            goto LABEL_82;
                          }
                          if ( !CHString::CompareNoCase((CHString *)v84, L"Manual") )
                          {
                            dwStartType = 3;
                            goto LABEL_82;
                          }
                          if ( !CHString::CompareNoCase((CHString *)v84, L"Disabled") )
                          {
LABEL_82:
                            CHString::CHString((CHString *)v90);
                            if ( !CInstance::GetStatus(a3, L"StartName", v66, v67) )
                            {
                              *v9 = 21;
                              goto LABEL_268;
                            }
                            if ( v66[0] && (v67[0] == 8 || v67[0] == 1) )
                            {
                              if ( v67[0] == 1 )
                              {
                                LOBYTE(a5) = 0;
                                goto LABEL_92;
                              }
                              if ( CInstance::GetCHString(a3, L"StartName", (struct CHString *)v90)
                                && !CHString::IsEmpty((CHString *)v90)
                                || !v11 )
                              {
                                LOBYTE(a5) = 1;
LABEL_92:
                                CHString::CHString((CHString *)v93);
                                if ( CInstance::GetStatus(a3, L"StartPassword", v66, v67) )
                                {
                                  if ( !v66[0] || v67[0] != 8 && v67[0] != 1 )
                                    goto LABEL_263;
                                  v69 = 0;
                                  if ( v67[0] != 1 )
                                  {
                                    if ( !CInstance::GetCHString(a3, L"StartPassword", (struct CHString *)v93) )
                                      goto LABEL_263;
                                    v69 = 1;
                                  }
                                  v73 = 0;
                                  if ( CInstance::GetStatus(a3, L"DesktopInteract", v66, v67) )
                                  {
                                    if ( !v66[0] || v67[0] != 11 && v67[0] != 1 )
                                      goto LABEL_263;
                                    if ( v67[0] == 1 )
                                      goto LABEL_134;
                                    if ( !v68 )
                                    {
                                      if ( v11 )
                                        goto LABEL_263;
                                      v14 = OpenSCManagerW(0, 0, 0xAu);
                                      v95 = (BSTR)v14;
                                      if ( v14 )
                                      {
                                        v15 = (const WCHAR *)CHString::operator unsigned short const *(v94);
                                        v17 = OpenServiceW(v14, v15, 3u);
                                        lpDisplayName = (LPCWSTR)v17;
                                        if ( v17 )
                                        {
                                          LODWORD(pcbBytesNeeded) = 0;
                                          v18 = 0;
                                          if ( QueryServiceConfigW(v17, 0, 0, (LPDWORD)&pcbBytesNeeded) )
                                            goto LABEL_113;
                                          if ( GetLastError() != 122 )
                                            goto LABEL_116;
                                          v20 = (OLECHAR *)operator new((unsigned int)pcbBytesNeeded);
                                          v18 = (DWORD *)v20;
                                          bstrString = v20;
                                          if ( !v20 )
                                          {
                                            pExceptionObject = 0;
                                            throw (CHeap_Exception *)&pExceptionObject;
                                          }
                                          try
                                          {
                                            ServiceConfigW = QueryServiceConfigW(
                                                               v17,
                                                               (LPQUERY_SERVICE_CONFIGW)v20,
                                                               (DWORD)pcbBytesNeeded,
                                                               (LPDWORD)&pcbBytesNeeded);
                                            v109[1] = ServiceConfigW;
                                          }
                                          catch ( ... )
                                          {
                                            operator delete(bstrString);
                                            throw;
                                          }
                                          if ( ServiceConfigW )
LABEL_113:
                                            dwServiceType = *v18;
                                          else
LABEL_116:
                                            *v9 = Win32_BaseService::GetServiceErrorCode(v19);
                                          operator delete(v18);
                                        }
                                        else
                                        {
                                          *v9 = Win32_BaseService::GetServiceErrorCode(v16);
                                        }
                                        if ( *v9 )
                                        {
                                          SmartCloseServiceHandle::~SmartCloseServiceHandle((SmartCloseServiceHandle *)&lpDisplayName);
                                          SmartCloseServiceHandle::~SmartCloseServiceHandle((SmartCloseServiceHandle *)&v95);
LABEL_120:
                                          CHString::~CHString((CHString *)v93);
LABEL_121:
                                          CHString::~CHString((CHString *)v90);
LABEL_122:
                                          CHString::~CHString((CHString *)v84);
LABEL_123:
                                          CHString::~CHString((CHString *)v83);
LABEL_276:
                                          CHString::~CHString((CHString *)v80);
                                          goto LABEL_277;
                                        }
                                        SmartCloseServiceHandle::~SmartCloseServiceHandle((SmartCloseServiceHandle *)&lpDisplayName);
                                      }
                                      else if ( a4 )
                                      {
                                        ServiceErrorCode = Win32_BaseService::GetServiceErrorCode(v13);
                                        CInstance::SetDWORD(a4, L"ReturnValue", ServiceErrorCode);
                                      }
                                      v68 = 1;
                                      SmartCloseServiceHandle::~SmartCloseServiceHandle((SmartCloseServiceHandle *)&v95);
                                    }
                                    if ( CInstance::Getbool(a3, L"DesktopInteract", &v73)
                                      && ((dwServiceType & 0xFFFFFEFF) == 0x10 || (dwServiceType & 0xFFFFFEFF) == 0x20) )
                                    {
                                      if ( v73 )
                                        dwServiceType |= 0x100u;
                                      else
                                        dwServiceType &= ~0x100u;
LABEL_134:
                                      CHString::CHString((CHString *)v96);
                                      if ( CInstance::GetStatus(a3, L"LoadOrderGroup", v66, v67) )
                                      {
                                        if ( !v66[0] || v67[0] != 8 && v67[0] != 1 )
                                          goto LABEL_258;
                                        v23 = 0;
                                        LOBYTE(pcbBytesNeeded) = 0;
                                        if ( v67[0] != 1 )
                                        {
                                          if ( (!CInstance::GetCHString(a3, L"LoadOrderGroup", (struct CHString *)v96)
                                             || CHString::IsEmpty((CHString *)v96))
                                            && cbBufSize )
                                          {
                                            goto LABEL_258;
                                          }
                                          LOBYTE(pcbBytesNeeded) = 1;
                                        }
                                        v24 = 0;
                                        v101 = 0;
                                        psa = 0;
                                        if ( CInstance::GetStatus(a3, L"LoadOrderGroupDependencies", v66, v67) )
                                        {
                                          if ( !v66[0] || v67[0] != 8200 && v67[0] != 1 )
                                            goto LABEL_258;
                                          if ( v67[0] != 1 )
                                          {
                                            if ( !CInstance::GetStringArray(a3, L"LoadOrderGroupDependencies", &psa)
                                              || !psa )
                                            {
                                              goto LABEL_258;
                                            }
                                            if ( SafeArrayGetDim(psa) != 1 )
                                              goto LABEL_177;
                                            plLbound = 0;
                                            SafeArrayGetLBound(psa, 1u, &plLbound);
                                            plUbound = 0;
                                            SafeArrayGetUBound(psa, 1u, &plUbound);
                                            v24 = 0;
                                            v101 = 0;
                                            for ( i = plLbound; ; i = rgIndices + 1 )
                                            {
                                              rgIndices = i;
                                              if ( i > plUbound )
                                                break;
                                              pv = 0;
                                              if ( SafeArrayGetElement(psa, &rgIndices, &pv) )
                                              {
                                                v105 = 0;
                                                throw (CHeap_Exception *)&v105;
                                              }
                                              try
                                              {
                                                CHString::CHString((CHString *)&lpDisplayName, pv);
                                                v26 = CHString::operator unsigned short const *(&lpDisplayName);
                                                v27 = -1;
                                                do
                                                  ++v27;
                                                while ( *(_WORD *)(v26 + 2 * v27) );
                                                v24 += v27 + 2;
                                                v101 = v24;
                                                CHString::~CHString((CHString *)&lpDisplayName);
                                              }
                                              catch ( ... )
                                              {
                                                SysFreeString(pv);
                                                throw;
                                              }
                                              SysFreeString(pv);
                                            }
                                          }
                                          v100 = 0;
                                          v92 = 0;
                                          if ( CInstance::GetStatus(a3, L"ServiceDependencies", v66, v67) )
                                          {
                                            if ( v66[0] && (v67[0] == 8200 || v67[0] == 1) )
                                            {
                                              if ( v67[0] == 1 )
                                              {
                                                v29 = 0;
LABEL_179:
                                                pv = 0;
                                                try
                                                {
                                                  v34 = v23 + v24;
                                                  v109[2] = v23 + v24;
                                                  if ( v23 + v24 )
                                                  {
                                                    pv = (unsigned __int16 *)operator new(saturated_mul(v34 + 1, 2u));
                                                    v110 = pv;
                                                    if ( !pv )
                                                    {
                                                      v109[0] = 0;
                                                      throw (CHeap_Exception *)v109;
                                                    }
                                                    try
                                                    {
                                                      v102 = 0;
                                                      if ( v24 )
                                                      {
                                                        plUbound = 0;
                                                        SafeArrayGetLBound(psa, 1u, &plUbound);
                                                        v99 = 0;
                                                        SafeArrayGetUBound(psa, 1u, &v99);
                                                        v35 = plUbound;
                                                        rgIndices = plUbound;
                                                        v36 = pv;
                                                        while ( v35 <= v99 )
                                                        {
                                                          bstrString = 0;
                                                          if ( SafeArrayGetElement(psa, &rgIndices, &bstrString) )
                                                          {
                                                            v107 = 0;
                                                            throw (CHeap_Exception *)&v107;
                                                          }
                                                          try
                                                          {
                                                            v36[v29] = 43;
                                                            CHString::CHString((CHString *)&lpDisplayName, bstrString);
                                                            v37 = (const unsigned __int16 *)CHString::operator unsigned short const *(&lpDisplayName);
                                                            StringCchCopyW(&v36[v29 + 1], v34 - v29, v37);
                                                            v38 = CHString::operator unsigned short const *(&lpDisplayName);
                                                            v39 = -1;
                                                            do
                                                              ++v39;
                                                            while ( *(_WORD *)(v38 + 2 * v39) );
                                                            v29 += v39 + 2;
                                                            v102 = v29;
                                                            CHString::~CHString((CHString *)&lpDisplayName);
                                                          }
                                                          catch ( ... )
                                                          {
                                                            SysFreeString(bstrString);
                                                            throw;
                                                          }
                                                          SysFreeString(bstrString);
                                                          v35 = ++rgIndices;
                                                        }
                                                      }
                                                      lpLoadOrderGroup = 0;
                                                      if ( v23 )
                                                      {
                                                        v98 = 0;
                                                        SafeArrayGetLBound(v92, 1u, &v98);
                                                        v103 = 0;
                                                        SafeArrayGetUBound(v92, 1u, &v103);
                                                        v41 = v98;
                                                        plLbound = v98;
                                                        v42 = pv;
                                                        while ( v41 <= v103 )
                                                        {
                                                          v95 = 0;
                                                          if ( SafeArrayGetElement(v92, &plLbound, &v95) )
                                                          {
                                                            v108 = 0;
                                                            throw (CHeap_Exception *)&v108;
                                                          }
                                                          try
                                                          {
                                                            CHString::CHString((CHString *)&lpDisplayName, v95);
                                                            v43 = (const unsigned __int16 *)CHString::operator unsigned short const *(&lpDisplayName);
                                                            StringCchCopyW(&v42[v29], v34 - v29 + 1, v43);
                                                            v44 = CHString::operator unsigned short const *(&lpDisplayName);
                                                            v45 = -1;
                                                            do
                                                              ++v45;
                                                            while ( *(_WORD *)(v44 + 2 * v45) );
                                                            v29 += v45 + 1;
                                                            v102 = v29;
                                                            CHString::~CHString((CHString *)&lpDisplayName);
                                                          }
                                                          catch ( ... )
                                                          {
                                                            SysFreeString(v95);
                                                            throw;
                                                          }
                                                          SysFreeString(v95);
                                                          v41 = ++plLbound;
                                                        }
                                                      }
                                                      else
                                                      {
                                                        v42 = pv;
                                                      }
                                                      v42[v34] = 0;
                                                    }
                                                    catch ( ... )
                                                    {
                                                      operator delete(v110);
                                                      throw;
                                                    }
                                                  }
                                                  else
                                                  {
                                                    lpLoadOrderGroup = 0;
                                                  }
                                                }
                                                catch ( ... )
                                                {
                                                  if ( psa )
                                                    SafeArrayDestroy(psa);
                                                  if ( v92 )
                                                    SafeArrayDestroy(v92);
                                                  throw;
                                                }
                                                if ( psa )
                                                  SafeArrayDestroy(psa);
                                                if ( v92 )
                                                  SafeArrayDestroy(v92);
                                                v47 = OpenSCManagerW(0, 0, 0xAu);
                                                bstrString = (BSTR)v47;
                                                if ( v47 )
                                                {
                                                  if ( cbBufSize )
                                                  {
                                                    cbBufSize = 0;
                                                    v48 = (const WCHAR *)CHString::operator unsigned short const *(v94);
                                                    v95 = (BSTR)CHString::operator unsigned short const *(v80);
                                                    lpDisplayName = (LPCWSTR)CHString::operator unsigned short const *(v83);
                                                    if ( (_BYTE)pcbBytesNeeded )
                                                      lpLoadOrderGroup = (const WCHAR *)CHString::operator unsigned short const *(v96);
                                                    lpPassword = 0;
                                                    if ( (_BYTE)a5 )
                                                    {
                                                      lpServiceStartName = (const WCHAR *)CHString::operator unsigned short const *(v90);
                                                      lpPassword = 0;
                                                    }
                                                    else
                                                    {
                                                      lpServiceStartName = 0;
                                                    }
                                                    if ( v69 )
                                                      lpPassword = (const WCHAR *)CHString::operator unsigned short const *(v93);
                                                    pcbBytesNeeded = CreateServiceW(
                                                                       v47,
                                                                       v48,
                                                                       v95,
                                                                       0xF01FFu,
                                                                       dwServiceType,
                                                                       dwStartType,
                                                                       dwErrorControl,
                                                                       lpDisplayName,
                                                                       lpLoadOrderGroup,
                                                                       (LPDWORD)((unsigned __int64)&cbBufSize
                                                                               & -(__int64)((dwServiceType & 1) != 0)),
                                                                       pv,
                                                                       lpServiceStartName,
                                                                       lpPassword);
                                                    if ( pcbBytesNeeded )
                                                      v51 = 0;
                                                    else
                                                      v51 = Win32_BaseService::GetServiceErrorCode(0);
                                                    *v9 = v51;
                                                    p_pcbBytesNeeded = (BSTR *)&pcbBytesNeeded;
                                                  }
                                                  else
                                                  {
                                                    v53 = (const WCHAR *)CHString::operator unsigned short const *(v94);
                                                    v54 = OpenServiceW(v47, v53, 3u);
                                                    v56 = v54;
                                                    v95 = (BSTR)v54;
                                                    if ( v54 )
                                                    {
                                                      cbBufSize = 0;
                                                      v57 = 0;
                                                      if ( !QueryServiceConfigW(v54, 0, 0, &cbBufSize) )
                                                      {
                                                        if ( GetLastError() != 122 )
                                                          goto LABEL_248;
                                                        v57 = (struct _QUERY_SERVICE_CONFIGW *)operator new(cbBufSize);
                                                        if ( !QueryServiceConfigW(v56, v57, cbBufSize, &cbBufSize) )
                                                          goto LABEL_248;
                                                      }
                                                      if ( v74 )
                                                        lpDisplayName = (LPCWSTR)CHString::operator unsigned short const *(v80);
                                                      else
                                                        lpDisplayName = 0;
                                                      if ( v75 )
                                                        v59 = (const WCHAR *)CHString::operator unsigned short const *(v83);
                                                      else
                                                        v59 = 0;
                                                      if ( (_BYTE)pcbBytesNeeded )
                                                        lpLoadOrderGroup = (const WCHAR *)CHString::operator unsigned short const *(v96);
                                                      if ( (_BYTE)a5 )
                                                        v60 = (const WCHAR *)CHString::operator unsigned short const *(v90);
                                                      else
                                                        v60 = 0;
                                                      if ( v69 )
                                                        v61 = (const WCHAR *)CHString::operator unsigned short const *(v93);
                                                      else
                                                        v61 = 0;
                                                      v62 = dwErrorControl;
                                                      if ( !v76 )
                                                        v62 = v57->dwErrorControl;
                                                      v63 = dwStartType;
                                                      if ( !v77 )
                                                        v63 = v57->dwStartType;
                                                      v64 = dwServiceType;
                                                      if ( !v68 )
                                                        v64 = v57->dwServiceType;
                                                      if ( ChangeServiceConfigW(
                                                             v56,
                                                             v64,
                                                             v63,
                                                             v62,
                                                             v59,
                                                             lpLoadOrderGroup,
                                                             0,
                                                             pv,
                                                             v60,
                                                             v61,
                                                             lpDisplayName) )
                                                      {
                                                        v65 = 0;
                                                      }
                                                      else
                                                      {
LABEL_248:
                                                        v65 = Win32_BaseService::GetServiceErrorCode(v58);
                                                      }
                                                      *v9 = v65;
                                                      if ( v57 )
                                                        operator delete(v57);
                                                    }
                                                    else
                                                    {
                                                      *v9 = Win32_BaseService::GetServiceErrorCode(v55);
                                                    }
                                                    p_pcbBytesNeeded = &v95;
                                                  }
                                                  SmartCloseServiceHandle::~SmartCloseServiceHandle((SmartCloseServiceHandle *)p_pcbBytesNeeded);
                                                }
                                                else
                                                {
                                                  *v9 = Win32_BaseService::GetServiceErrorCode(v46);
                                                }
                                                operator delete(pv);
                                                SmartCloseServiceHandle::~SmartCloseServiceHandle((SmartCloseServiceHandle *)&bstrString);
                                                goto LABEL_259;
                                              }
                                              StringArray = CInstance::GetStringArray(a3, L"ServiceDependencies", &v92);
                                              v29 = 0;
                                              if ( StringArray )
                                              {
                                                if ( v92 )
                                                {
                                                  if ( SafeArrayGetDim(v92) == 1 )
                                                  {
                                                    plUbound = 0;
                                                    SafeArrayGetLBound(v92, 1u, &plUbound);
                                                    plLbound = 0;
                                                    SafeArrayGetUBound(v92, 1u, &plLbound);
                                                    v23 = 0;
                                                    v100 = 0;
                                                    for ( j = plUbound; ; j = rgIndices + 1 )
                                                    {
                                                      rgIndices = j;
                                                      if ( j > plLbound )
                                                        break;
                                                      pv = 0;
                                                      if ( SafeArrayGetElement(v92, &rgIndices, &pv) )
                                                      {
                                                        v106 = 0;
                                                        throw (CHeap_Exception *)&v106;
                                                      }
                                                      try
                                                      {
                                                        CHString::CHString((CHString *)&lpDisplayName, pv);
                                                        v31 = CHString::operator unsigned short const *(&lpDisplayName);
                                                        v32 = -1;
                                                        do
                                                          ++v32;
                                                        while ( *(_WORD *)(v31 + 2 * v32) );
                                                        v23 += v32 + 1;
                                                        v100 = v23;
                                                        CHString::~CHString((CHString *)&lpDisplayName);
                                                      }
                                                      catch ( ... )
                                                      {
                                                        SysFreeString(pv);
                                                        throw;
                                                      }
                                                      SysFreeString(pv);
                                                    }
                                                    goto LABEL_179;
                                                  }
                                                  SafeArrayDestroy(v92);
                                                  if ( psa )
                                                    SafeArrayDestroy(psa);
LABEL_177:
                                                  *v9 = 21;
                                                  CHString::~CHString((CHString *)v96);
                                                  CHString::~CHString((CHString *)v93);
                                                  CHString::~CHString((CHString *)v90);
                                                  CHString::~CHString((CHString *)v84);
                                                  CHString::~CHString((CHString *)v83);
                                                  CHString::~CHString((CHString *)v80);
                                                  CHString::~CHString((CHString *)v94);
                                                  return (unsigned int)ServiceStatus;
                                                }
                                              }
                                            }
                                            if ( psa )
                                              SafeArrayDestroy(psa);
LABEL_258:
                                            *v9 = 21;
LABEL_259:
                                            CHString::~CHString((CHString *)v96);
                                            goto LABEL_120;
                                          }
                                          if ( psa )
                                            SafeArrayDestroy(psa);
                                        }
                                      }
                                      *v9 = 21;
                                      CHString::~CHString((CHString *)v96);
                                      goto LABEL_265;
                                    }
LABEL_263:
                                    *v9 = 21;
                                    goto LABEL_120;
                                  }
                                }
                                *v9 = 21;
LABEL_265:
                                CHString::~CHString((CHString *)v93);
LABEL_268:
                                CHString::~CHString((CHString *)v90);
LABEL_271:
                                CHString::~CHString((CHString *)v84);
LABEL_274:
                                CHString::~CHString((CHString *)v83);
                                CHString::~CHString((CHString *)v80);
                                ServiceStatus = -2147217404;
                                goto LABEL_277;
                              }
                            }
                            *v9 = 21;
                            goto LABEL_121;
                          }
                        }
                      }
                      *v9 = 21;
                      goto LABEL_122;
                    }
                    if ( CInstance::GetByte(a3, L"ErrorControl", &v72) )
                    {
                      v76 = 1;
                      switch ( v72 )
                      {
                        case 0u:
                          dwErrorControl = 0;
                          goto LABEL_66;
                        case 1u:
                          dwErrorControl = 1;
                          goto LABEL_66;
                        case 2u:
                          dwErrorControl = 2;
                          goto LABEL_66;
                        case 3u:
                          dwErrorControl = 3;
                          goto LABEL_66;
                      }
                    }
                  }
LABEL_272:
                  *v9 = 21;
                  goto LABEL_123;
                }
                goto LABEL_273;
              }
              dwServiceType = 2;
            }
          }
          dwStartType = 4;
          goto LABEL_52;
        }
      }
      else if ( CInstance::GetCHString(a3, L"DisplayName", (struct CHString *)v80)
             && !CHString::IsEmpty((CHString *)v80) )
      {
        v74 = 1;
        goto LABEL_22;
      }
    }
    *v9 = 21;
    goto LABEL_276;
  }
  *v9 = 21;
  CHString::~CHString((CHString *)v80);
  CHString::~CHString((CHString *)v94);
  return 2147749892LL;
}

```

## disassembly

```asm
0x180095808  mov     rax, rsp
0x18009580b  mov     [rax+10h], rbx
0x18009580f  mov     [rax+18h], rsi
0x180095813  mov     [rax+8], rcx
0x180095817  push    rdi
0x180095818  push    r12
0x18009581a  push    r13
0x18009581c  push    r14
0x18009581e  push    r15
0x180095820  sub     rsp, 160h
0x180095827  mov     r13, r9
0x18009582a  mov     rsi, r8
0x18009582d  mov     rbx, rdx
0x180095830  xor     edi, edi
0x180095832  mov     r14, [rsp+188h+arg_20]
0x18009583a  mov     [r14], edi
0x18009583d  mov     [rsp+188h+var_118], dil
0x180095842  mov     [rsp+188h+var_114], di
0x180095847  lea     rcx, [rax-90h]
0x18009584e  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x180095854  nop
0x180095855  mov     r12d, [rsp+188h+cbBufSize]
0x18009585d  test    r12d, r12d
0x180095860  jz      short loc_1800958D8
0x180095862  lea     r9, [rsp+188h+var_114]
0x180095867  lea     r8, [rsp+188h+var_118]
0x18009586c  lea     rdx, aName; "Name"
0x180095873  mov     rcx, rsi
0x180095876  call    cs:__imp_?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z; CInstance::GetStatus(ushort const *,bool &,ushort &)
0x18009587c  test    al, al
0x18009587e  jz      short loc_1800958C7
0x180095880  cmp     [rsp+188h+var_118], dil
0x180095885  jz      short loc_1800958C3
0x180095887  lea     r15d, [rdi+8]
0x18009588b  cmp     [rsp+188h+var_114], r15w
0x180095891  jnz     short loc_1800958C3
0x180095893  lea     r8, [rsp+188h+var_90]
0x18009589b  lea     rdx, aName; "Name"
0x1800958a2  mov     rcx, rsi
0x1800958a5  call    cs:__imp_?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z; CInstance::GetCHString(ushort const *,CHString &)
0x1800958ab  test    al, al
0x1800958ad  jz      short loc_1800958C3
0x1800958af  mov     ebx, edi
0x1800958b1  lea     rcx, [rsp+188h+var_90]
0x1800958b9  call    cs:__imp_?IsEmpty@CHString@@QEBAHXZ; CHString::IsEmpty(void)
0x1800958bf  test    eax, eax
0x1800958c1  jz      short loc_180095939
0x1800958c3  mov     ebx, edi
0x1800958c5  jmp     short loc_1800958CC
0x1800958c7  mov     ebx, 80041004h
0x1800958cc  mov     dword ptr [r14], 15h
0x1800958d3  jmp     loc_180096E7B
0x1800958d8  mov     dword ptr [rsp+188h+pcbBytesNeeded], edi
0x1800958df  mov     [rsp+188h+var_B7], dil
0x1800958e7  mov     [rsp+188h+var_B8], dil
0x1800958ef  lea     rax, [rsp+188h+var_B8]
0x1800958f7  mov     qword ptr [rsp+188h+dwStartType], rax; bool *
0x1800958fc  lea     rax, [rsp+188h+var_B7]
0x180095904  mov     qword ptr [rsp+188h+dwServiceType], rax; bool *
0x180095909  lea     r9, [rsp+188h+pcbBytesNeeded]; unsigned int *
0x180095911  lea     r8, [rsp+188h+var_90]; struct CHString *
0x180095919  mov     rdx, rbx; struct CInstance *
0x18009591c  call    ?GetServiceStatus@Win32_BaseService@@IEAAJAEBVCInstance@@AEAVCHString@@AEAKAEA_N3@Z; Win32_BaseService::GetServiceStatus(CInstance const &,CHString &,ulong &,bool &,bool &)
0x180095921  mov     ebx, eax
0x180095923  test    eax, eax
0x180095925  jns     short loc_180095933
0x180095927  mov     dword ptr [r14], 8
0x18009592e  jmp     loc_180096E7B
0x180095933  mov     r15d, 8
0x180095939  lea     rcx, [rsp+188h+var_F8]
0x180095941  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x180095947  nop
0x180095948  lea     r9, [rsp+188h+var_114]
0x18009594d  lea     r8, [rsp+188h+var_118]
0x180095952  lea     rdx, aDisplayname; "DisplayName"
0x180095959  mov     rcx, rsi
0x18009595c  call    cs:__imp_?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z; CInstance::GetStatus(ushort const *,bool &,ushort &)
0x180095962  test    al, al
0x180095964  jz      loc_180096E8D
0x18009596a  cmp     [rsp+188h+var_118], dil
0x18009596f  jz      loc_180096E65
0x180095975  movzx   eax, [rsp+188h+var_114]
0x18009597a  mov     edi, 1
0x18009597f  cmp     ax, r15w
0x180095983  jz      short loc_18009598E
0x180095985  cmp     ax, di
0x180095988  jnz     loc_180096E65
0x18009598e  cmp     ax, di
0x180095991  jnz     short loc_1800959A7
0x180095993  xor     eax, eax
0x180095995  test    r12d, r12d
0x180095998  jnz     loc_180096E65
0x18009599e  mov     [rsp+188h+var_105], al
0x1800959a5  jmp     short loc_1800959E5
0x1800959a7  lea     r8, [rsp+188h+var_F8]
0x1800959af  lea     rdx, aDisplayname; "DisplayName"
0x1800959b6  mov     rcx, rsi
0x1800959b9  call    cs:__imp_?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z; CInstance::GetCHString(ushort const *,CHString &)
0x1800959bf  test    al, al
0x1800959c1  jz      loc_180096E65
0x1800959c7  lea     rcx, [rsp+188h+var_F8]
0x1800959cf  call    cs:__imp_?IsEmpty@CHString@@QEBAHXZ; CHString::IsEmpty(void)
0x1800959d5  test    eax, eax
0x1800959d7  jnz     loc_180096E65
0x1800959dd  mov     [rsp+188h+var_105], dil
0x1800959e5  lea     rcx, [rsp+188h+var_E0]
0x1800959ed  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x1800959f3  nop
0x1800959f4  lea     r9, [rsp+188h+var_114]
0x1800959f9  lea     r8, [rsp+188h+var_118]
0x1800959fe  lea     rdx, aPathname; "PathName"
0x180095a05  mov     rcx, rsi
0x180095a08  call    cs:__imp_?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z; CInstance::GetStatus(ushort const *,bool &,ushort &)
0x180095a0e  xor     ecx, ecx
0x180095a10  test    al, al
0x180095a12  jz      loc_180096E3A
0x180095a18  cmp     [rsp+188h+var_118], cl
0x180095a1c  jz      loc_180096E2E
0x180095a22  movzx   eax, [rsp+188h+var_114]
0x180095a27  cmp     ax, r15w
0x180095a2b  jz      short loc_180095A36
0x180095a2d  cmp     ax, di
0x180095a30  jnz     loc_180096E2E
0x180095a36  cmp     ax, di
0x180095a39  jnz     short loc_180095A4D
0x180095a3b  test    r12d, r12d
0x180095a3e  jnz     loc_180096E2E
0x180095a44  mov     [rsp+188h+var_104], cl
0x180095a4b  jmp     short loc_180095A8B
0x180095a4d  lea     r8, [rsp+188h+var_E0]
0x180095a55  lea     rdx, aPathname; "PathName"
0x180095a5c  mov     rcx, rsi
0x180095a5f  call    cs:__imp_?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z; CInstance::GetCHString(ushort const *,CHString &)
0x180095a65  test    al, al
0x180095a67  jz      loc_180096E2E
0x180095a6d  lea     rcx, [rsp+188h+var_E0]
0x180095a75  call    cs:__imp_?IsEmpty@CHString@@QEBAHXZ; CHString::IsEmpty(void)
0x180095a7b  test    eax, eax
0x180095a7d  jnz     loc_180096E2E
0x180095a83  mov     [rsp+188h+var_104], dil
0x180095a8b  lea     r9, [rsp+188h+var_114]
0x180095a90  lea     r8, [rsp+188h+var_118]
0x180095a95  lea     rdx, aServicetype; "ServiceType"
0x180095a9c  mov     rcx, rsi
0x180095a9f  call    cs:__imp_?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z; CInstance::GetStatus(ushort const *,bool &,ushort &)
0x180095aa5  test    al, al
0x180095aa7  jz      loc_180096E3A
0x180095aad  cmp     [rsp+188h+var_118], 0
0x180095ab2  jz      loc_180096E2E
0x180095ab8  movzx   eax, [rsp+188h+var_114]
0x180095abd  sub     ax, di
0x180095ac0  mov     ecx, 0FFEFh
0x180095ac5  test    cx, ax
0x180095ac8  jnz     loc_180096E2E
0x180095ace  cmp     [rsp+188h+var_114], di
0x180095ad3  jnz     short loc_180095AEC
0x180095ad5  mov     [rsp+188h+var_10C], 10h
0x180095add  xor     edx, edx
0x180095adf  test    r12d, r12d
0x180095ae2  setnz   [rsp+188h+var_110]
0x180095ae7  jmp     loc_180095B8D
0x180095aec  mov     [rsp+188h+var_108], 0
0x180095af4  lea     r8, [rsp+188h+var_108]
0x180095afc  lea     rdx, aServicetype; "ServiceType"
0x180095b03  mov     rcx, rsi
0x180095b06  call    cs:__imp_?GetByte@CInstance@@QEBA_NPEBGAEAE@Z; CInstance::GetByte(ushort const *,uchar &)
0x180095b0c  test    al, al
0x180095b0e  jz      loc_180096E2E
0x180095b14  mov     [rsp+188h+var_110], dil
0x180095b19  movzx   ecx, [rsp+188h+var_108]
0x180095b21  sub     ecx, 1
0x180095b24  jz      short loc_180095B87
0x180095b26  sub     ecx, 1
0x180095b29  jz      short loc_180095B7D
0x180095b2b  sub     ecx, 2
0x180095b2e  mov     r12d, 4
0x180095b34  mov     [rsp+188h+var_100], r12d
0x180095b3c  jz      short loc_180095B76
0x180095b3e  sub     ecx, r12d
0x180095b41  jz      short loc_180095B65
0x180095b43  sub     ecx, r15d
0x180095b46  jz      short loc_180095B5B
0x180095b48  cmp     ecx, 10h
0x180095b4b  jnz     loc_180096E2E
0x180095b51  mov     [rsp+188h+var_10C], 20h ; ' '
0x180095b59  jmp     short loc_180095B6A
0x180095b5b  mov     [rsp+188h+var_10C], 10h
0x180095b63  jmp     short loc_180095B6A
0x180095b65  mov     [rsp+188h+var_10C], r15d
0x180095b6a  mov     r12d, [rsp+188h+cbBufSize]
0x180095b72  xor     edx, edx
0x180095b74  jmp     short loc_180095B98
0x180095b76  mov     [rsp+188h+var_10C], r12d
0x180095b7b  jmp     short loc_180095B6A
0x180095b7d  mov     [rsp+188h+var_10C], 2
0x180095b85  jmp     short loc_180095B8B
0x180095b87  mov     [rsp+188h+var_10C], edi
0x180095b8b  xor     edx, edx
0x180095b8d  mov     [rsp+188h+var_100], 4
0x180095b98  mov     [rsp+188h+var_107], dl
0x180095b9f  lea     r9, [rsp+188h+var_114]
0x180095ba4  lea     r8, [rsp+188h+var_118]
0x180095ba9  lea     rdx, aErrorcontrol; "ErrorControl"
0x180095bb0  mov     rcx, rsi
0x180095bb3  call    cs:__imp_?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z; CInstance::GetStatus(ushort const *,bool &,ushort &)
0x180095bb9  xor     ecx, ecx
0x180095bbb  test    al, al
0x180095bbd  jz      loc_180096E3A
0x180095bc3  cmp     [rsp+188h+var_118], cl
0x180095bc7  jz      loc_180096E2E
0x180095bcd  movzx   eax, [rsp+188h+var_114]
0x180095bd2  sub     ax, di
0x180095bd5  mov     edx, 0FFEFh
0x180095bda  test    dx, ax
0x180095bdd  jnz     loc_180096E2E
0x180095be3  cmp     [rsp+188h+var_114], di
0x180095be8  jnz     short loc_180095BFE
0x180095bea  mov     [rsp+188h+var_A8], ecx
0x180095bf1  test    r12d, r12d
0x180095bf4  setnz   [rsp+188h+var_103]
0x180095bfc  jmp     short loc_180095C71
0x180095bfe  lea     r8, [rsp+188h+var_107]
0x180095c06  lea     rdx, aErrorcontrol; "ErrorControl"
0x180095c0d  mov     rcx, rsi
0x180095c10  call    cs:__imp_?GetByte@CInstance@@QEBA_NPEBGAEAE@Z; CInstance::GetByte(ushort const *,uchar &)
0x180095c16  xor     edx, edx
0x180095c18  test    al, al
0x180095c1a  jz      loc_180096E2E
0x180095c20  mov     [rsp+188h+var_103], dil
0x180095c28  movzx   ecx, [rsp+188h+var_107]
0x180095c30  test    ecx, ecx
0x180095c32  jz      short loc_180095C6A
0x180095c34  sub     ecx, 1
0x180095c37  jz      short loc_180095C61
0x180095c39  sub     ecx, 1
0x180095c3c  jz      short loc_180095C54
0x180095c3e  cmp     ecx, 1
0x180095c41  jnz     loc_180096E2E
0x180095c47  mov     [rsp+188h+var_A8], 3
0x180095c52  jmp     short loc_180095C71
0x180095c54  mov     [rsp+188h+var_A8], 2
0x180095c5f  jmp     short loc_180095C71
0x180095c61  mov     [rsp+188h+var_A8], edi
0x180095c68  jmp     short loc_180095C71
0x180095c6a  mov     [rsp+188h+var_A8], edx
0x180095c71  lea     rcx, [rsp+188h+var_D8]
0x180095c79  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x180095c7f  nop
0x180095c80  lea     r9, [rsp+188h+var_114]
0x180095c85  lea     r8, [rsp+188h+var_118]
0x180095c8a  lea     rdx, aStartmode; "StartMode"
0x180095c91  mov     rcx, rsi
0x180095c94  call    cs:__imp_?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z; CInstance::GetStatus(ushort const *,bool &,ushort &)
0x180095c9a  xor     ecx, ecx
0x180095c9c  test    al, al
0x180095c9e  jz      loc_180096E17
0x180095ca4  cmp     [rsp+188h+var_118], cl
0x180095ca8  jz      loc_180096E0B
0x180095cae  movzx   eax, [rsp+188h+var_114]
0x180095cb3  cmp     ax, r15w
0x180095cb7  jz      short loc_180095CC2
0x180095cb9  cmp     ax, di
0x180095cbc  jnz     loc_180096E0B
0x180095cc2  cmp     ax, di
0x180095cc5  jnz     short loc_180095CE2
0x180095cc7  mov     [rsp+188h+var_100], 2
0x180095cd2  test    r12d, r12d
0x180095cd5  setnz   [rsp+188h+var_102]
0x180095cdd  jmp     loc_180095DBC
0x180095ce2  lea     r8, [rsp+188h+var_D8]
0x180095cea  lea     rdx, aStartmode; "StartMode"
0x180095cf1  mov     rcx, rsi
0x180095cf4  call    cs:__imp_?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z; CInstance::GetCHString(ushort const *,CHString &)
0x180095cfa  test    al, al
0x180095cfc  jz      loc_180096E0B
0x180095d02  mov     [rsp+188h+var_102], dil
0x180095d0a  lea     rdx, aBoot; "Boot"
0x180095d11  lea     rcx, [rsp+188h+var_D8]
0x180095d19  call    cs:__imp_?CompareNoCase@CHString@@QEBAHPEBG@Z; CHString::CompareNoCase(ushort const *)
0x180095d1f  xor     ecx, ecx
0x180095d21  test    eax, eax
0x180095d23  jnz     short loc_180095D31
0x180095d25  mov     [rsp+188h+var_100], ecx
0x180095d2c  jmp     loc_180095DBC
0x180095d31  lea     rdx, aSystem_0; "System"
0x180095d38  lea     rcx, [rsp+188h+var_D8]
0x180095d40  call    cs:__imp_?CompareNoCase@CHString@@QEBAHPEBG@Z; CHString::CompareNoCase(ushort const *)
0x180095d46  test    eax, eax
0x180095d48  jnz     short loc_180095D53
0x180095d4a  mov     [rsp+188h+var_100], edi
0x180095d51  jmp     short loc_180095DBC
0x180095d53  lea     rdx, aAutomatic; "Automatic"
0x180095d5a  lea     rcx, [rsp+188h+var_D8]
0x180095d62  call    cs:__imp_?CompareNoCase@CHString@@QEBAHPEBG@Z; CHString::CompareNoCase(ushort const *)
0x180095d68  test    eax, eax
0x180095d6a  jnz     short loc_180095D79
0x180095d6c  mov     [rsp+188h+var_100], 2
0x180095d77  jmp     short loc_180095DBC
0x180095d79  lea     rdx, aManual; "Manual"
0x180095d80  lea     rcx, [rsp+188h+var_D8]
  ... truncated ...
```
