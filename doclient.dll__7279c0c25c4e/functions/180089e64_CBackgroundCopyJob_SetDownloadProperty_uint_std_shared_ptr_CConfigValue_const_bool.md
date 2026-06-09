# CBackgroundCopyJob::SetDownloadProperty(uint,std::shared_ptr<CConfigValue> const &,bool)

- ea: `0x180089e64`
- end: `0x18008b65e`
- name: `?SetDownloadProperty@CBackgroundCopyJob@@QEAAJIAEBV?$shared_ptr@VCConfigValue@@@std@@_N@Z`
- size: `6138`
- prototype: `__int64 __fastcall(CBackgroundCopyJob *this, char *, unsigned __int8 **, char)`
- caller_count: `14`
- callee_count: `33`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18000fba0`
- `0x180010730`
- `0x180010d80`
- `0x180010f60`
- `0x180011840`
- `0x180011990`
- `0x180012840`
- `0x180012d90`
- `0x180013000`
- `0x1800136d0`
- `0x180013b40`
- `0x180088104`
- `0x180092914`
- `0x1800934d4`

## callees

- `0x1800089f8`
- `0x18000933c`
- `0x1800095a0`
- `0x180009ab4`
- `0x18000a4fc`
- `0x18000cdd0`
- `0x18000f014`
- `0x1800179a4`
- `0x1800199b4`
- `0x180019c5c`
- `0x18001d5fc`
- `0x18001dfc4`
- `0x1800604f8`
- `0x18007d138`
- `0x180082d0c`
- `0x180087f0c`
- `0x180089e64`
- `0x18008cc84`
- `0x18008e068`
- `0x1800928e4`
- `0x1800943c4`
- `0x180094518`
- `0x180094720`
- `0x18009fa14`
- `0x1800a1c5c`
- `0x1800a1ea4`
- `0x1800a6ae4`
- `0x1800a9af0`
- `0x1800ac0e0`
- `0x1800e86a8`
- `0x1800f8110`
- `0x1800f82f0`
- `0x180108e50`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008a565`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008a5ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008a565`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008a5ac`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18008a54f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18008a592`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18008a54f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18008a592`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008a0f6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008a199`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008a20d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008a246`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008a267`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008a82a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008a9ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008aa6a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008ab33`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008acc9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008ad69`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008ae0e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008ae7e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008afb1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008b126`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008b471`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008b4d8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008a0f6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008a199`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008a20d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008a246`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008a267`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008a82a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008a9ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008aa6a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008ab33`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008acc9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008ad69`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008ae0e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008ae7e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008afb1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008b126`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008b471`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008b4d8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18008a9dc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18008a9dc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18008aa07`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18008aa07`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008a22a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008a37e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008a416`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008a62c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008a80b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008a87c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008a9aa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008aa4b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008aaca`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008ab14`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008acaa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008ad4a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008adef`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008ae5f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008af92`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008b022`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008b107`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008b2d5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008b393`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008b438`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008b4b9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008a22a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008a37e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008a416`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008a62c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008a80b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008a87c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008a9aa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008aa4b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008aaca`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008ab14`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008acaa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008ad4a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008adef`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008ae5f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008af92`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008b022`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008b107`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008b2d5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008b393`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008b438`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008b4b9`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18008a821`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18008aa61`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18008ab2a`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18008acc0`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18008ad60`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18008ae05`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18008ae75`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18008afa8`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18008b11d`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18008b4cf`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18008a821`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18008aa61`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18008ab2a`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18008acc0`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18008ad60`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18008ae05`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18008ae75`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18008afa8`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18008b11d`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18008b4cf`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressSingle` at `0x18008a932`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressSingle` at `0x18008a932`

## string_xrefs

- `0x180089eb0`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x180089edc`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x180089f09`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x180089f36`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x180089f63`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x180089f90`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x180089fc8`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x18008a004`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x18008a057`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x18008a0c8`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x18008a176`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x18008a1ea`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x18008a308`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x18008a52d`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x18008a701`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x18008a7a0`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x18008a7f6`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x18008aa36`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x18008aaff`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x18008ac95`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x18008ad35`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x18008adda`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x18008ae4a`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x18008af7d`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x18008b0f2`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x18008a753`: `Job %s, URI: %s`
- `0x18008a34f`: `CBackgroundCopyJob::SetDownloadProperty`
- `0x18008a3dc`: `CBackgroundCopyJob::SetDownloadProperty`
- `0x18008a49d`: `CBackgroundCopyJob::SetDownloadProperty`
- `0x18008a5f2`: `CBackgroundCopyJob::SetDownloadProperty`
- `0x18008a6c1`: `CBackgroundCopyJob::SetDownloadProperty`
- `0x18008a760`: `CBackgroundCopyJob::SetDownloadProperty`
- `0x18008a85c`: `CBackgroundCopyJob::SetDownloadProperty`
- `0x18008a8f0`: `CBackgroundCopyJob::SetDownloadProperty`
- `0x18008a975`: `CBackgroundCopyJob::SetDownloadProperty`
- `0x18008aa9b`: `CBackgroundCopyJob::SetDownloadProperty`
- `0x18008ab64`: `CBackgroundCopyJob::SetDownloadProperty`
- `0x18008ac23`: `CBackgroundCopyJob::SetDownloadProperty`
- `0x18008acf6`: `CBackgroundCopyJob::SetDownloadProperty`
- `0x18008aec4`: `CBackgroundCopyJob::SetDownloadProperty`
- `0x18008af27`: `CBackgroundCopyJob::SetDownloadProperty`
- `0x18008aff2`: `CBackgroundCopyJob::SetDownloadProperty`
- `0x18008b081`: `CBackgroundCopyJob::SetDownloadProperty`
- `0x18008b0c8`: `CBackgroundCopyJob::SetDownloadProperty`
- `0x18008b16c`: `CBackgroundCopyJob::SetDownloadProperty`
- `0x18008b2b5`: `CBackgroundCopyJob::SetDownloadProperty`
- `0x18008b359`: `CBackgroundCopyJob::SetDownloadProperty`
- `0x18008b3fe`: `CBackgroundCopyJob::SetDownloadProperty`
- `0x18008a490`: `Job %s, LocalPath: %s`
- `0x18008a84f`: `Job %s, SecurityFlags: 0x%x`
- `0x18008ace9`: `Job %s, NetworkToken`
- `0x18008b30c`: `Job %s, TempLocalFileUsage: %u`
- `0x18008b34c`: `Job %s, UpdateId: %s`

## pseudocode

```c
__int64 __fastcall CBackgroundCopyJob::SetDownloadProperty(
        CBackgroundCopyJob *this,
        char *a2,
        unsigned __int8 **a3,
        char a4)
{
  unsigned int v6; // ebx
  __int64 result; // rax
  int v9; // r8d
  int v10; // edx
  char *v11; // rdi
  int v12; // eax
  int v13; // eax
  unsigned int v14; // r13d
  const char *v15; // r9
  int v16; // edx
  unsigned __int8 *v17; // rax
  __int64 v18; // r13
  int v19; // edi
  RTL_SRWLOCK *v20; // rsi
  RTL_SRWLOCK *v21; // rcx
  unsigned __int8 *v22; // rax
  RTL_SRWLOCK *v23; // r13
  unsigned __int8 *v24; // rsi
  RTL_SRWLOCK *v25; // rdi
  void *v26; // rsi
  __int64 v27; // rax
  unsigned __int8 *v28; // rax
  unsigned __int8 *v29; // rcx
  unsigned __int8 *v30; // rcx
  HANDLE v31; // rbx
  wil::details::in1diag3 *v32; // rcx
  HANDLE v33; // rdi
  unsigned __int8 *v34; // rax
  __int64 v35; // r13
  unsigned __int8 *v36; // rdi
  _QWORD *v37; // rsi
  size_t v38; // r8
  unsigned __int8 *v39; // rax
  unsigned __int8 *v40; // rcx
  int v41; // eax
  unsigned int v42; // edi
  unsigned __int8 *v43; // rax
  unsigned __int8 *v44; // rcx
  int v45; // eax
  unsigned int v46; // edi
  int v47; // r12d
  __int64 v48; // rdi
  int v49; // r12d
  __int64 v50; // rdi
  CBackgroundCopyFile **v51; // rdi
  CBackgroundCopyFile **v52; // r13
  unsigned __int8 *v53; // rax
  __int64 v54; // r13
  int v55; // edi
  unsigned __int8 *v56; // rax
  bool v57; // zf
  unsigned int v58; // eax
  int v59; // eax
  unsigned int v60; // edi
  unsigned __int8 *v61; // rax
  unsigned __int64 v62; // rdi
  int v63; // eax
  __int64 v64; // r13
  unsigned __int8 v65; // di
  int v66; // r12d
  __int64 *v67; // rax
  __int64 v68; // r13
  void (__fastcall ***v69)(_QWORD, __int64); // rcx
  void (__fastcall ***v70)(_QWORD, __int64); // rcx
  unsigned __int8 *v71; // rax
  int v72; // r12d
  __int64 v73; // rdi
  unsigned __int8 *v74; // rax
  RTL_SRWLOCK *v75; // r13
  unsigned __int8 *v76; // rdi
  size_t v77; // r8
  unsigned __int8 *v78; // rax
  RTL_SRWLOCK *v79; // r13
  unsigned __int8 *v80; // rsi
  void *v81; // rsi
  unsigned __int8 *v82; // rax
  int v83; // [rsp+20h] [rbp-E8h]
  int v84; // [rsp+20h] [rbp-E8h]
  int v85; // [rsp+20h] [rbp-E8h]
  char *v86; // [rsp+28h] [rbp-E0h]
  HANDLE Token[2]; // [rsp+40h] [rbp-C8h] BYREF
  unsigned int v88; // [rsp+50h] [rbp-B8h]
  __int128 v89; // [rsp+58h] [rbp-B0h]
  char *v90; // [rsp+68h] [rbp-A0h] BYREF
  __int128 v91; // [rsp+70h] [rbp-98h]
  _BYTE v92[32]; // [rsp+80h] [rbp-88h] BYREF
  char v93[40]; // [rsp+A0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  v6 = (unsigned int)a2;
  v88 = (unsigned int)a2;
  if ( (unsigned int)a2 >= 0x20 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1DB,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
      (const char *)0x80D02011LL,
      v83);
    return 2161123345LL;
  }
  switch ( (_DWORD)a2 )
  {
    case 0:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1DC,
        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
        (const char *)0x80D02012LL,
        v83);
      return 2161123346LL;
    case 0x1C:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1DE,
        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
        (const char *)0x80D02012LL,
        v83);
      return 2161123346LL;
    case 0x1D:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1E0,
        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
        (const char *)0x80D02012LL,
        v83);
      return 2161123346LL;
    case 0x1E:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1E2,
        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
        (const char *)0x80D02012LL,
        v83);
      return 2161123346LL;
    case 0x1F:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1E3,
        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
        (const char *)0x80D02012LL,
        v83);
      return 2161123346LL;
  }
  v9 = *((_DWORD *)qword_180136920 + (unsigned int)a2);
  if ( !v9 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E6,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
      (const char *)0x8000FFFFLL,
      v83);
    return 2147549183LL;
  }
  v10 = (char)(*a3)[32];
  if ( v9 != ((*a3)[32] < 8u ? v10 : 0) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E9,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
      (const char *)0x80070057LL,
      v83);
    return 2147942487LL;
  }
  if ( (_BYTE)v10 == 7 && !*((_QWORD *)*a3 + 2) && (v6 != 3 || !*(_BYTE *)(*((_QWORD *)this + 31) + 396LL)) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1EC,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
      (const char *)0x80070057LL,
      v83);
    return 2147942487LL;
  }
  v11 = (char *)this + 136;
  v91 = (unsigned __int64)this + 136;
  v12 = mtx_do_lock((char *)this + 136);
  try
  {
    if ( v12 )
      std::_Throw_Cpp_error(5);
    if ( *((_DWORD *)this + 53) == 0x7FFFFFFF )
    {
      *((_DWORD *)this + 53) = 2147483646;
      std::_Throw_Cpp_error(6);
    }
    BYTE8(v91) = 1;
    v13 = CBackgroundCopyJob::_IsJobActiveForIncomingCall(this);
    v14 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1EF,
        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
        (const char *)(unsigned int)v13,
        v83);
      v57 = (*((_DWORD *)this + 53))-- == 1;
      if ( v57 )
      {
        *((_DWORD *)this + 52) = -1;
        ReleaseSRWLockExclusive((PSRWLOCK)this + 19);
      }
      return v14;
    }
    v16 = *((_DWORD *)this + 98);
    if ( v16 )
    {
      if ( v6 > 0xA )
      {
        if ( v6 != 11 && v6 != 16 && v6 != 22 && v6 != 23 && v6 - 26 >= 2 )
          goto LABEL_47;
      }
      else
      {
        if ( v6 == 10 )
          goto LABEL_50;
        if ( v6 != 1 )
        {
          if ( v6 == 5 || v6 == 6 || v6 == 7 || v6 - 8 <= 1 )
            goto LABEL_50;
LABEL_47:
          LODWORD(v86) = v6;
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x20C,
            (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
            (const char *)0x80D02013LL,
            (int)"Property %u not allowed to change in state %d",
            v86,
            *((_DWORD *)this + 98));
          v57 = (*((_DWORD *)v11 + 19))-- == 1;
          if ( v57 )
          {
            *((_DWORD *)v11 + 18) = -1;
            ReleaseSRWLockExclusive((PSRWLOCK)v11 + 2);
          }
          return 2161123347LL;
        }
        if ( v16 == 1 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x207,
            (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
            (const char *)0x80D02013LL,
            v83);
          v57 = (*((_DWORD *)v11 + 19))-- == 1;
          if ( v57 )
          {
            *((_DWORD *)v11 + 18) = -1;
            ReleaseSRWLockExclusive((PSRWLOCK)v11 + 2);
          }
          return 2161123347LL;
        }
      }
    }
LABEL_50:
    AcquireSRWLockExclusive((PSRWLOCK)this + 29);
    if ( ++*((_DWORD *)this + 61) == 1 )
      _InterlockedExchange((volatile __int32 *)this + 60, 0);
    v90 = (char *)this + 232;
    ReleaseSRWLockExclusive((PSRWLOCK)this + 29);
    if ( !v11 )
      std::_Throw_system_error(1);
    v57 = (*((_DWORD *)v11 + 19))-- == 1;
    if ( v57 )
    {
      *((_DWORD *)v11 + 18) = -1;
      ReleaseSRWLockExclusive((PSRWLOCK)v11 + 2);
    }
    BYTE8(v91) = 0;
    CGuidToString::CGuidToString((CGuidToString *)v93, (const struct _GUID *)(*((_QWORD *)this + 31) + 16LL));
    if ( v88 > 0x10 )
    {
      if ( v88 > 0x16 )
      {
        switch ( v88 )
        {
          case 0x17u:
            if ( !a4 )
            {
              v78 = *a3;
              if ( (*a3)[32] != 7 )
                std::_Throw_bad_variant_access();
              if ( *((_QWORD *)v78 + 3) > 0xFu )
                v78 = *(unsigned __int8 **)v78;
              LogMessage(
                4u,
                "CBackgroundCopyJob::SetDownloadProperty",
                0x23Du,
                "Job %s, HttpCustomAuthHeaders: %s",
                v93,
                (const char *)v78);
            }
            v79 = (RTL_SRWLOCK *)*((_QWORD *)this + 31);
            v80 = *a3;
            if ( (*a3)[32] != 7 )
              std::_Throw_bad_variant_access();
            v25 = v79 + 34;
            v89 = (unsigned __int64)&v79[34];
            AcquireSRWLockExclusive(v79 + 34);
            BYTE8(v89) = 1;
            v81 = (void *)std::string::string(v92, v80);
            std::string::operator=(&v79[26], v81);
            std::string::~string(v81);
            goto LABEL_289;
          case 0x18u:
            if ( !a4 )
            {
              v74 = *a3;
              if ( (*a3)[32] != 7 )
                std::_Throw_bad_variant_access();
              if ( *((_QWORD *)v74 + 3) > 0xFu )
                v74 = *(unsigned __int8 **)v74;
              LogMessage(
                4u,
                "CBackgroundCopyJob::SetDownloadProperty",
                0x2B6u,
                "Job %s, UpdateId: %s",
                v93,
                (const char *)v74);
            }
            v75 = (RTL_SRWLOCK *)*((_QWORD *)this + 31);
            v76 = *a3;
            if ( (*a3)[32] != 7 )
              std::_Throw_bad_variant_access();
            v20 = v75 + 34;
            v89 = (unsigned __int64)&v75[34];
            AcquireSRWLockExclusive(v75 + 34);
            BYTE8(v89) = 1;
            if ( &v75[12] != (RTL_SRWLOCK *)v76 )
            {
              v77 = *((_QWORD *)v76 + 2);
              if ( *((_QWORD *)v76 + 3) > 0xFu )
                v76 = *(unsigned __int8 **)v76;
              std::string::assign(&v75[12], v76, v77);
            }
            goto LABEL_72;
          case 0x19u:
            if ( !a4 )
            {
              if ( (*a3)[32] != 1 )
                std::_Throw_bad_variant_access();
              LogMessage(
                4u,
                "CBackgroundCopyJob::SetDownloadProperty",
                0x2A7u,
                "Job %s, TempLocalFileUsage: %u",
                v93,
                **a3);
            }
            goto LABEL_291;
          case 0x1Au:
            v71 = *a3;
            if ( (*a3)[32] != 1 )
              std::_Throw_bad_variant_access();
            v72 = *v71;
            if ( !a4 )
              LogMessage(
                4u,
                "CBackgroundCopyJob::SetDownloadProperty",
                0x244u,
                "Job %s, HttpAllowSecureToNonSecureRedirect: %u",
                v93,
                *v71);
            v73 = *((_QWORD *)this + 31);
            v20 = (RTL_SRWLOCK *)(v73 + 272);
            AcquireSRWLockExclusive((PSRWLOCK)(v73 + 272));
            *(_DWORD *)(v73 + 252) = (v72 != 0) + 1;
            goto LABEL_72;
        }
        if ( v88 != 27 )
          goto LABEL_244;
        if ( (*a3)[32] != 1 )
          std::_Throw_bad_variant_access();
        v66 = **a3;
        if ( !a4 )
          LogMessage(4u, "CBackgroundCopyJob::SetDownloadProperty", 0x2BDu, "Job %s, NonVolatile: %u", v93, v66);
        if ( (*((_QWORD *)this + 40) != 0) == (_BYTE)v66 )
          goto LABEL_291;
        v89 = (unsigned __int64)v11;
        if ( (unsigned int)mtx_do_lock(v11) )
          std::_Throw_Cpp_error(5);
        if ( *((_DWORD *)this + 53) == 0x7FFFFFFF )
        {
          *((_DWORD *)this + 53) = 2147483646;
          std::_Throw_Cpp_error(6);
        }
        BYTE8(v89) = 1;
        if ( (_BYTE)v66 )
        {
          v67 = (__int64 *)std::make_unique<CPersistedEntityRegJob<CAppRegistryEntityLocation>,_GUID const &,0>(
                             Token,
                             *((_QWORD *)this + 31) + 16LL);
          v68 = *v67;
          *v67 = 0;
          if ( Token[0] )
            (**(void (__fastcall ***)(HANDLE, __int64))Token[0])(Token[0], 1);
          v69 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 40);
          *((_QWORD *)this + 40) = v68;
          if ( v69 )
            (**v69)(v69, 1);
        }
        if ( !a4 )
        {
          if ( (_BYTE)v66 )
          {
            CBackgroundCopyJob::_SaveJobInfo(this);
          }
          else
          {
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 40) + 120LL))(*((_QWORD *)this + 40));
            v70 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 40);
            *((_QWORD *)this + 40) = 0;
            if ( v70 )
              (**v70)(v70, 1);
          }
        }
        v57 = (*((_DWORD *)v11 + 19))-- == 1;
        goto LABEL_183;
      }
      if ( v88 == 22 )
      {
        if ( !a4 )
        {
          if ( (*a3)[32] != 1 )
            std::_Throw_bad_variant_access();
          LogMessage(4u, "CBackgroundCopyJob::SetDownloadProperty", 0x2B1u, "Job %s, DisallowOnCellular: %u", v93, **a3);
        }
        v64 = *((_QWORD *)this + 31);
        if ( (*a3)[32] != 1 )
          std::_Throw_bad_variant_access();
        v65 = **a3;
        v20 = (RTL_SRWLOCK *)(v64 + 272);
        AcquireSRWLockExclusive((PSRWLOCK)(v64 + 272));
        *(_BYTE *)(v64 + 398) = v65;
        goto LABEL_72;
      }
      if ( v88 != 17 )
      {
        switch ( v88 )
        {
          case 0x12u:
            if ( !a4 )
              LogMessage(4u, "CBackgroundCopyJob::SetDownloadProperty", 0x29Bu, "Job %s, DecryptionInfo", v93);
            goto LABEL_291;
          case 0x13u:
            if ( !a4 )
              LogMessage(4u, "CBackgroundCopyJob::SetDownloadProperty", 0x29Fu, "Job %s, IntegrityCheckInfo", v93);
            goto LABEL_291;
          case 0x14u:
            if ( !a4 )
            {
              if ( (*a3)[32] != 1 )
                std::_Throw_bad_variant_access();
              LogMessage(
                4u,
                "CBackgroundCopyJob::SetDownloadProperty",
                0x2A3u,
                "Job %s, IntegrityCheckMandatory: %u",
                v93,
                **a3);
            }
            goto LABEL_291;
        }
        v61 = *a3;
        if ( (*a3)[32] != 5 )
          std::_Throw_bad_variant_access();
        if ( *(_QWORD *)v61 )
        {
          v62 = *(_QWORD *)v61;
          if ( v62 > (unsigned __int64)(unsigned int)CGlobalConfigManager::GetConfigValue<unsigned int>(
                                                       *((_QWORD *)this + 47),
                                                       85) << 30 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x2AB,
              (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
              (const char *)0x800700DFLL,
              v83);
            AcquireSRWLockExclusive((PSRWLOCK)this + 29);
            v57 = (*((_DWORD *)this + 61))-- == 1;
            if ( v57 )
            {
              *((_DWORD *)this + 60) = 1;
              WakeByAddressAll((char *)this + 240);
            }
            ReleaseSRWLockExclusive((PSRWLOCK)this + 29);
            return 2147942623LL;
          }
          if ( !a4 )
          {
            if ( (*a3)[32] != 5 )
              std::_Throw_bad_variant_access();
            LogMessage(
              4u,
              "CBackgroundCopyJob::SetDownloadProperty",
              0x2ADu,
              "Job %s, TotalSizeBytes: %llu",
              v93,
              *(_QWORD *)*a3);
          }
          goto LABEL_291;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2AA,
          (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
          (const char *)0x80070057LL,
          v83);
        AcquireSRWLockExclusive((PSRWLOCK)this + 29);
        v57 = (*((_DWORD *)this + 61))-- == 1;
        if ( v57 )
        {
          *((_DWORD *)this + 60) = 1;
          WakeByAddressAll((char *)this + 240);
        }
        goto LABEL_214;
      }
      if ( (*a3)[32] != 7 )
        std::_Throw_bad_variant_access();
      v63 = CBackgroundCopyJob::_SetCorrelationVector(this);
      v60 = v63;
      if ( v63 >= 0 )
        goto LABEL_294;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x296,
        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
        (const char *)(unsigned int)v63,
        v83);
      AcquireSRWLockExclusive((PSRWLOCK)this + 29);
      v57 = (*((_DWORD *)this + 61))-- == 1;
      if ( v57 )
      {
        *((_DWORD *)this + 60) = 1;
        WakeByAddressAll((char *)this + 240);
      }
    }
    else
    {
      if ( v88 != 16 )
      {
        if ( v88 <= 7 )
        {
          if ( v88 != 7 )
          {
            switch ( v88 )
            {
              case 1u:
                if ( !a4 )
                {
                  v43 = *a3;
                  if ( (*a3)[32] != 7 )
                    std::_Throw_bad_variant_access();
                  if ( *((_QWORD *)v43 + 3) > 0xFu )
                    v43 = *(unsigned __int8 **)v43;
                  LogMessage(
                    4u,
                    "CBackgroundCopyJob::SetDownloadProperty",
                    0x21Du,
                    "Job %s, URI: %s",
                    v93,
                    (const char *)v43);
                }
                v44 = *a3;
                if ( (*a3)[32] != 7 )
                  std::_Throw_bad_variant_access();
                if ( *((_QWORD *)v44 + 3) > 0xFu )
                  v44 = *(unsigned __int8 **)v44;
                v45 = ValidateUrl((const char *)v44);
                v46 = v45;
                if ( v45 >= 0 )
                  goto LABEL_291;
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x21E,
                  (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
                  (const char *)(unsigned int)v45,
                  v83);
                CWaitableCounter::scope_exit::~scope_exit((CWaitableCounter::scope_exit *)&v90);
                return v46;
              case 2u:
                if ( !a4 )
                {
                  v39 = *a3;
                  if ( (*a3)[32] != 7 )
                    std::_Throw_bad_variant_access();
                  if ( *((_QWORD *)v39 + 3) > 0xFu )
                    v39 = *(unsigned __int8 **)v39;
                  LogMessage(
                    4u,
                    "CBackgroundCopyJob::SetDownloadProperty",
                    0x222u,
                    "Job %s, ContentId: %s",
                    v93,
                    (const char *)v39);
                }
                v40 = *a3;
                if ( (*a3)[32] != 7 )
                  std::_Throw_bad_variant_access();
                if ( *((_QWORD *)v40 + 3) > 0xFu )
                  v40 = *(unsigned __int8 **)v40;
                v41 = ValidateFileId(v40);
                v42 = v41;
                if ( v41 >= 0 )
                  goto LABEL_291;
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x223,
                  (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
                  (const char *)(unsigned int)v41,
                  v83);
                CWaitableCounter::scope_exit::~scope_exit((CWaitableCounter::scope_exit *)&v90);
                return v42;
              case 3u:
                if ( !a4 )
                {
                  v34 = *a3;
                  if ( (*a3)[32] != 7 )
                    std::_Throw_bad_variant_access();
                  if ( *((_QWORD *)v34 + 3) > 0xFu )
                    v34 = *(unsigned __int8 **)v34;
                  LogMessage(
                    4u,
                    "CBackgroundCopyJob::SetDownloadProperty",
                    0x227u,
                    "Job %s, DisplayName: %s",
                    v93,
                    (const char *)v34);
                }
                v35 = *((_QWORD *)this + 31);
                v36 = *a3;
                if ( (*a3)[32] != 7 )
                  std::_Throw_bad_variant_access();
                v89 = (unsigned __int64)(v35 + 272);
                AcquireSRWLockExclusive((PSRWLOCK)(v35 + 272));
                BYTE8(v89) = 1;
                v37 = (_QWORD *)(v35 + 32);
                if ( (unsigned __int8 *)(v35 + 32) != v36 )
                {
                  v38 = *((_QWORD *)v36 + 2);
                  if ( *((_QWORD *)v36 + 3) > 0xFu )
                    v36 = *(unsigned __int8 **)v36;
                  std::string::assign((void *)(v35 + 32), v36, v38);
                }
                if ( *(_QWORD *)(v35 + 56) > 0xFu )
                  v37 = (_QWORD *)*v37;
                *(_BYTE *)(v35 + 399) = (unsigned int)o__stricmp_0(v37, "Xbox XVC Streaming") == 0;
                v21 = (RTL_SRWLOCK *)(v35 + 272);
                goto LABEL_290;
              case 4u:
                if ( a4 )
                  goto LABEL_291;
                if ( (*a3)[32] != 7 )
                  std::_Throw_bad_variant_access();
                v27 = RemovePIIFromFilePath(v92, *a3);
                if ( *(_QWORD *)(v27 + 24) > 0xFu )
                  v27 = *(_QWORD *)v27;
                LogMessage(
                  4u,
                  "CBackgroundCopyJob::SetDownloadProperty",
                  0x22Du,
                  "Job %s, LocalPath: %s",
                  v93,
                  (const char *)v27);
                std::string::~string(v92);
                v28 = *a3;
                if ( (*a3)[32] != 7 )
                  std::_Throw_bad_variant_access();
                v29 = *a3;
                if ( *((_QWORD *)v28 + 3) > 0xFu )
                  v29 = *(unsigned __int8 **)v28;
                if ( v29[*((_QWORD *)v28 + 2) - 1] == 92 )
                  goto LABEL_291;
                Token[0] = 0;
                CJobSharedData::ImpersonateOwner(*((CJobSharedData **)this + 31), Token);
                v30 = *a3;
                if ( (*a3)[32] != 7 )
                  std::_Throw_bad_variant_access();
                if ( *((_QWORD *)v30 + 3) > 0xFu )
                  v30 = *(unsigned __int8 **)v30;
                if ( CPath::Exists((const char *)v30) )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x232,
                    (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
                    (const char *)0x800700B7LL,
                    v84);
                  v31 = Token[0];
                  if ( Token[0] == (HANDLE)-1LL )
                  {
LABEL_96:
                    CWaitableCounter::scope_exit::~scope_exit((CWaitableCounter::scope_exit *)&v90);
                    return 2147942583LL;
                  }
                  if ( SetThreadToken(0, Token[0]) )
                  {
                    if ( v31 )
                      CloseHandle(v31);
                    goto LABEL_96;
                  }
LABEL_305:
                  wil::details::in1diag3::_FailFastImmediate_Unexpected(v32);
                }
                v33 = Token[0];
                if ( Token[0] != (HANDLE)-1LL )
                {
                  if ( SetThreadToken(0, Token[0]) )
                  {
                    if ( v33 )
                      CloseHandle(v33);
                    goto LABEL_291;
                  }
                  goto LABEL_305;
                }
LABEL_291:
                *(_OWORD *)Token = 0;
                v82 = a3[1];
                if ( v82 )
                  _InterlockedIncrement((volatile signed __int32 *)v82 + 2);
                Token[0] = *a3;
                Token[1] = a3[1];
                CConfigStore::Add((char *)this + 16, v88, Token);
LABEL_294:
                if ( this != (CBackgroundCopyJob *)-232LL )
                {
                  AcquireSRWLockExclusive((PSRWLOCK)this + 29);
                  v57 = (*((_DWORD *)this + 61))-- == 1;
                  if ( v57 )
                  {
                    *((_DWORD *)this + 60) = 1;
                    WakeByAddressAll((char *)this + 240);
                  }
                  ReleaseSRWLockExclusive((PSRWLOCK)this + 29);
                }
                return 0;
              case 5u:
                if ( !a4 )
                {
                  v22 = *a3;
                  if ( (*a3)[32] != 7 )
                    std::_Throw_bad_variant_access();
                  if ( *((_QWORD *)v22 + 3) > 0xFu )
                    v22 = *(unsigned __int8 **)v22;
                  LogMessage(
                    4u,
                    "CBackgroundCopyJob::SetDownloadProperty",
                    0x238u,
                    "Job %s, HttpCustomHeaders: %s",
                    v93,
                    (const char *)v22);
                }
                v23 = (RTL_SRWLOCK *)*((_QWORD *)this + 31);
                v24 = *a3;
                if ( (*a3)[32] != 7 )
                  std::_Throw_bad_variant_access();
                v25 = v23 + 34;
                v89 = (unsigned __int64)&v23[34];
                AcquireSRWLockExclusive(v23 + 34);
                BYTE8(v89) = 1;
                v26 = (void *)std::string::string(v92, v24);
                std::string::operator=(&v23[22], v26);
                std::string::~string(v26);
LABEL_289:
                v21 = v25;
                goto LABEL_290;
              case 6u:
                v17 = *a3;
                if ( (*a3)[32] != 3 )
                  std::_Throw_bad_variant_access();
                if ( *(_DWORD *)v17 >= 5u )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x249,
                    (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
                    (const char *)0x80070057LL,
                    v83);
                  CWaitableCounter::scope_exit::~scope_exit((CWaitableCounter::scope_exit *)&v90);
                  return 2147942487LL;
                }
                if ( !a4 )
                  LogMessage(
                    4u,
                    "CBackgroundCopyJob::SetDownloadProperty",
                    0x24Bu,
                    "Job %s, CostPolicy: %u",
                    v93,
                    *(_DWORD *)v17);
                v18 = *((_QWORD *)this + 31);
                if ( (*a3)[32] != 3 )
                  std::_Throw_bad_variant_access();
                v19 = *(_DWORD *)*a3;
                v20 = (RTL_SRWLOCK *)(v18 + 272);
                AcquireSRWLockExclusive((PSRWLOCK)(v18 + 272));
                LODWORD(Token[0]) = v19;
                BYTE4(Token[0]) = 1;
                *(HANDLE *)(v18 + 388) = Token[0];
                goto LABEL_72;
              default:
LABEL_244:
                LogMessage(
                  3u,
                  "CBackgroundCopyJob::SetDownloadProperty",
                  0x2D6u,
                  "Job %s, Unhandled set property: %u",
                  v93,
                  v88);
                LogMessage(
                  2u,
                  "CBackgroundCopyJob::SetDownloadProperty",
                  0x2D7u,
                  "TelemetryAssert (%s): %s (0x%x, 0x%x)",
                  "false",
                  "Failed",
                  v88,
                  0);
                DOTelemetryAssertTriggered(v88, 0);
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x2D8,
                  (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
                  (const char *)0x8000FFFFLL,
                  v85);
                AcquireSRWLockExclusive((PSRWLOCK)this + 29);
                v57 = (*((_DWORD *)this + 61))-- == 1;
                if ( v57 )
                {
                  *((_DWORD *)this + 60) = 1;
                  WakeByAddressAll((char *)this + 240);
                }
                ReleaseSRWLockExclusive((PSRWLOCK)this + 29);
                return 2147549183LL;
            }
          }
          if ( (*a3)[32] != 3 )
            std::_Throw_bad_variant_access();
          v47 = *(_DWORD *)*a3;
          if ( v47 != 1 && (v47 & 0xFFFFCCFF) != 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x254,
              (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
              (const char *)0x80070057LL,
              v83);
            AcquireSRWLockExclusive((PSRWLOCK)this + 29);
            v57 = (*((_DWORD *)this + 61))-- == 1;
            if ( v57 )
            {
              *((_DWORD *)this + 60) = 1;
              WakeByAddressAll((char *)this + 240);
            }
LABEL_214:
            ReleaseSRWLockExclusive((PSRWLOCK)this + 29);
            return 2147942487LL;
          }
          if ( !a4 )
            LogMessage(4u, "CBackgroundCopyJob::SetDownloadProperty", 0x256u, "Job %s, SecurityFlags: 0x%x", v93, v47);
          v48 = *((_QWORD *)this + 31);
          v20 = (RTL_SRWLOCK *)(v48 + 272);
          AcquireSRWLockExclusive((PSRWLOCK)(v48 + 272));
          *(_DWORD *)(v48 + 248) = v47;
          goto LABEL_72;
        }
        switch ( v88 )
        {
          case 8u:
            if ( (*a3)[32] != 3 )
              std::_Throw_bad_variant_access();
            v58 = *(_DWORD *)*a3;
            if ( !v58 || v58 > 0x64 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x25C,
                (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
                (const char *)0x80070057LL,
                v83);
              AcquireSRWLockExclusive((PSRWLOCK)this + 29);
              v57 = (*((_DWORD *)this + 61))-- == 1;
              if ( v57 )
              {
                *((_DWORD *)this + 60) = 1;
                WakeByAddressAll((char *)this + 240);
              }
              goto LABEL_214;
            }
            if ( !a4 )
              LogMessage(
                4u,
                "CBackgroundCopyJob::SetDownloadProperty",
                0x25Eu,
                "Job %s, CallbackFreqPercent: %u",
                v93,
                v58);
            Token[1] = 0;
            Token[0] = v11;
            if ( (unsigned int)mtx_do_lock(v11) )
              std::_Throw_Cpp_error(5);
            if ( *((_DWORD *)this + 53) == 0x7FFFFFFF )
            {
              *((_DWORD *)this + 53) = 2147483646;
              std::_Throw_Cpp_error(6);
            }
            LOBYTE(Token[1]) = 1;
            if ( (*a3)[32] != 3 )
              std::_Throw_bad_variant_access();
            *((_DWORD *)this + 92) = *(_DWORD *)*a3;
            break;
          case 9u:
            v56 = *a3;
            if ( (*a3)[32] != 3 )
              std::_Throw_bad_variant_access();
            if ( !*(_DWORD *)v56 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x265,
                (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
                (const char *)0x80070057LL,
                v83);
              AcquireSRWLockExclusive((PSRWLOCK)this + 29);
              v57 = (*((_DWORD *)this + 61))-- == 1;
              if ( v57 )
              {
                *((_DWORD *)this + 60) = 1;
                WakeByAddressAll((char *)this + 240);
              }
              goto LABEL_214;
            }
            if ( !a4 )
              LogMessage(
                4u,
                "CBackgroundCopyJob::SetDownloadProperty",
                0x267u,
                "Job %s, CallbackFreqSeconds: %u",
                v93,
                *(_DWORD *)v56);
            Token[1] = 0;
            Token[0] = v11;
            if ( (unsigned int)mtx_do_lock(v11) )
              std::_Throw_Cpp_error(5);
            if ( *((_DWORD *)this + 53) == 0x7FFFFFFF )
            {
              *((_DWORD *)this + 53) = 2147483646;
              std::_Throw_Cpp_error(6);
            }
            LOBYTE(Token[1]) = 1;
            if ( (*a3)[32] != 3 )
              std::_Throw_bad_variant_access();
            *((_QWORD *)this + 45) = *(unsigned int *)*a3;
            break;
          case 0xAu:
            v53 = *a3;
            if ( (*a3)[32] != 3 )
              std::_Throw_bad_variant_access();
            if ( *(_DWORD *)v53 < 0x3Cu )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x26E,
                (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
                (const char *)0x80070057LL,
                v83);
              AcquireSRWLockExclusive((PSRWLOCK)this + 29);
              v57 = (*((_DWORD *)this + 61))-- == 1;
              if ( v57 )
              {
                *((_DWORD *)this + 60) = 1;
                WakeByAddressAll((char *)this + 240);
              }
              goto LABEL_214;
            }
            if ( !a4 )
              LogMessage(
                4u,
                "CBackgroundCopyJob::SetDownloadProperty",
                0x270u,
                "Job %s, NoProgressTimeout: %u s",
                v93,
                *(_DWORD *)v53);
            v54 = *((_QWORD *)this + 31);
            if ( (*a3)[32] != 3 )
              std::_Throw_bad_variant_access();
            v55 = *(_DWORD *)*a3;
            v20 = (RTL_SRWLOCK *)(v54 + 272);
            AcquireSRWLockExclusive((PSRWLOCK)(v54 + 272));
            *(_DWORD *)(v54 + 384) = v55;
LABEL_72:
            v21 = v20;
LABEL_290:
            ReleaseSRWLockExclusive(v21);
            goto LABEL_291;
          case 0xBu:
            if ( (*a3)[32] != 1 )
              std::_Throw_bad_variant_access();
            v49 = **a3;
            if ( !a4 )
              LogMessage(
                4u,
                "CBackgroundCopyJob::SetDownloadProperty",
                0x277u,
                "Job %s, ForegroundPriority: %u",
                v93,
                v49);
            if ( (_BYTE)v49 != CJobSharedData::IsForeground(*((CJobSharedData **)this + 31)) )
            {
              v50 = *((_QWORD *)this + 31);
              AcquireSRWLockExclusive((PSRWLOCK)(v50 + 272));
              *(_BYTE *)(v50 + 397) = v49;
              ReleaseSRWLockExclusive((PSRWLOCK)(v50 + 272));
              *((_QWORD *)&v89 + 1) = 1;
              *(_QWORD *)&v89 = (char *)this + 224;
              AcquireSRWLockShared((PSRWLOCK)this + 28);
              v51 = (CBackgroundCopyFile **)*((_QWORD *)this + 8);
              v52 = (CBackgroundCopyFile **)*((_QWORD *)this + 9);
              while ( v51 != v52 )
              {
                CBackgroundCopyFile::SetBackground(*v51, (_BYTE)v49 == 0);
                v51 += 2;
              }
              ReleaseSRWLockShared((PSRWLOCK)this + 28);
            }
            goto LABEL_291;
          case 0xCu:
            if ( !a4 )
            {
              if ( (*a3)[32] != 1 )
                std::_Throw_bad_variant_access();
              LogMessage(4u, "CBackgroundCopyJob::SetDownloadProperty", 0x286u, "Job %s, BlockingMode: %u", v93, **a3);
            }
            if ( (*a3)[32] != 1 )
              std::_Throw_bad_variant_access();
            *((_BYTE *)this + 400) = **a3;
            if ( !*((_BYTE *)this + 400) )
            {
              *((_DWORD *)this + 99) = 1;
              WakeByAddressSingle((char *)this + 396);
            }
            goto LABEL_291;
          default:
            goto LABEL_244;
        }
        v57 = (*((_DWORD *)this + 53))-- == 1;
LABEL_183:
        if ( v57 )
        {
          *((_DWORD *)v11 + 18) = -1;
          v21 = (RTL_SRWLOCK *)(v11 + 16);
          goto LABEL_290;
        }
        goto LABEL_291;
      }
      if ( !a4 )
        LogMessage(4u, "CBackgroundCopyJob::SetDownloadProperty", 0x290u, "Job %s, NetworkToken", v93);
      if ( (*a3)[32] != 1 )
        std::_Throw_bad_variant_access();
      v59 = CJobSharedData::SetNetworkToken(*((CJobSharedData **)this + 31), **a3);
      v60 = v59;
      if ( v59 >= 0 )
        goto LABEL_294;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x292,
        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
        (const char *)(unsigned int)v59,
        v83);
      AcquireSRWLockExclusive((PSRWLOCK)this + 29);
      v57 = (*((_DWORD *)this + 61))-- == 1;
      if ( v57 )
      {
        *((_DWORD *)this + 60) = 1;
        WakeByAddressAll((char *)this + 240);
      }
    }
    ReleaseSRWLockExclusive((PSRWLOCK)this + 29);
    result = v60;
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x2E2,
                           (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
                           v15);
  }
  return result;
}

```

## disassembly

```asm
0x180089e64  push    rbx
0x180089e66  push    rsi
0x180089e67  push    rdi
0x180089e68  push    r12
0x180089e6a  push    r13
0x180089e6c  push    r14
0x180089e6e  push    r15
0x180089e70  sub     rsp, 0D0h
0x180089e77  mov     rax, cs:__security_cookie
0x180089e7e  xor     rax, rsp
0x180089e81  mov     [rsp+108h+var_40], rax
0x180089e89  mov     sil, r9b
0x180089e8c  mov     r15, r8
0x180089e8f  mov     ebx, edx
0x180089e91  mov     [rsp+108h+var_B8], ebx
0x180089e95  mov     r14, rcx
0x180089e98  xor     r13d, r13d
0x180089e9b  cmp     ebx, 20h ; ' '
0x180089e9e  jb      short loc_180089EC8
0x180089ea0  mov     rcx, [rsp+108h]; this
0x180089ea8  mov     ebx, 80D02011h
0x180089ead  mov     r9d, ebx; char *
0x180089eb0  lea     r8, aCW1SSrcDeliver_24; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x180089eb7  mov     edx, 1DBh; void *
0x180089ebc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180089ec1  mov     eax, ebx
0x180089ec3  jmp     loc_18008B4EE
0x180089ec8  test    edx, edx
0x180089eca  jnz     short loc_180089EF4
0x180089ecc  mov     rcx, [rsp+108h]; this
0x180089ed4  mov     ebx, 80D02012h
0x180089ed9  mov     r9d, ebx; char *
0x180089edc  lea     r8, aCW1SSrcDeliver_24; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x180089ee3  mov     edx, 1DCh; void *
0x180089ee8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180089eed  mov     eax, ebx
0x180089eef  jmp     loc_18008B4EE
0x180089ef4  cmp     ebx, 1Ch
0x180089ef7  jnz     short loc_180089F21
0x180089ef9  mov     rcx, [rsp+108h]; this
0x180089f01  mov     ebx, 80D02012h
0x180089f06  mov     r9d, ebx; char *
0x180089f09  lea     r8, aCW1SSrcDeliver_24; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x180089f10  mov     edx, 1DEh; void *
0x180089f15  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180089f1a  mov     eax, ebx
0x180089f1c  jmp     loc_18008B4EE
0x180089f21  cmp     ebx, 1Dh
0x180089f24  jnz     short loc_180089F4E
0x180089f26  mov     rcx, [rsp+108h]; this
0x180089f2e  mov     ebx, 80D02012h
0x180089f33  mov     r9d, ebx; char *
0x180089f36  lea     r8, aCW1SSrcDeliver_24; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x180089f3d  mov     edx, 1E0h; void *
0x180089f42  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180089f47  mov     eax, ebx
0x180089f49  jmp     loc_18008B4EE
0x180089f4e  cmp     ebx, 1Eh
0x180089f51  jnz     short loc_180089F7B
0x180089f53  mov     rcx, [rsp+108h]; this
0x180089f5b  mov     ebx, 80D02012h
0x180089f60  mov     r9d, ebx; char *
0x180089f63  lea     r8, aCW1SSrcDeliver_24; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x180089f6a  mov     edx, 1E2h; void *
0x180089f6f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180089f74  mov     eax, ebx
0x180089f76  jmp     loc_18008B4EE
0x180089f7b  cmp     ebx, 1Fh
0x180089f7e  jnz     short loc_180089FA8
0x180089f80  mov     rcx, [rsp+108h]; this
0x180089f88  mov     ebx, 80D02012h
0x180089f8d  mov     r9d, ebx; char *
0x180089f90  lea     r8, aCW1SSrcDeliver_24; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x180089f97  mov     edx, 1E3h; void *
0x180089f9c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180089fa1  mov     eax, ebx
0x180089fa3  jmp     loc_18008B4EE
0x180089fa8  lea     r8, qword_180136920
0x180089faf  mov     r8d, [r8+rbx*4]
0x180089fb3  test    r8d, r8d
0x180089fb6  jnz     short loc_180089FE0
0x180089fb8  mov     rcx, [rsp+108h]; this
0x180089fc0  mov     edi, 8000FFFFh
0x180089fc5  mov     r9d, edi; char *
0x180089fc8  lea     r8, aCW1SSrcDeliver_24; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x180089fcf  mov     edx, 1E6h; void *
0x180089fd4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180089fd9  mov     eax, edi
0x180089fdb  jmp     loc_18008B4EE
0x180089fe0  mov     r9, [r15]
0x180089fe3  movsx   edx, byte ptr [r9+20h]
0x180089fe8  cmp     dl, 8
0x180089feb  sbb     eax, eax
0x180089fed  and     eax, edx
0x180089fef  cmp     r8d, eax
0x180089ff2  jz      short loc_18008A01C
0x180089ff4  mov     rcx, [rsp+108h]; this
0x180089ffc  mov     edi, 80070057h
0x18008a001  mov     r9d, edi; char *
0x18008a004  lea     r8, aCW1SSrcDeliver_24; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18008a00b  mov     edx, 1E9h; void *
0x18008a010  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008a015  mov     eax, edi
0x18008a017  jmp     loc_18008B4EE
0x18008a01c  mov     r12d, 7
0x18008a022  cmp     dl, 8
0x18008a025  jnb     short loc_18008A06F
0x18008a027  cmp     dl, r12b
0x18008a02a  jnz     short loc_18008A06F
0x18008a02c  cmp     [r9+10h], r13
0x18008a030  jnz     short loc_18008A06F
0x18008a032  cmp     ebx, 3
0x18008a035  jnz     short loc_18008A047
0x18008a037  mov     rax, [rcx+0F8h]
0x18008a03e  cmp     [rax+18Ch], r13b
0x18008a045  jnz     short loc_18008A06F
0x18008a047  mov     rcx, [rsp+108h]; this
0x18008a04f  mov     edi, 80070057h
0x18008a054  mov     r9d, edi; char *
0x18008a057  lea     r8, aCW1SSrcDeliver_24; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18008a05e  mov     edx, 1ECh; void *
0x18008a063  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008a068  mov     eax, edi
0x18008a06a  jmp     loc_18008B4EE
0x18008a06f  xorps   xmm0, xmm0
0x18008a072  movups  [rsp+108h+var_98], xmm0
0x18008a077  lea     rdi, [rcx+88h]
0x18008a07e  mov     qword ptr [rsp+108h+var_98], rdi
0x18008a083  mov     byte ptr [rsp+108h+var_98+8], r13b
0x18008a088  mov     rcx, rdi
0x18008a08b  call    mtx_do_lock
0x18008a090  test    eax, eax
0x18008a092  jnz     loc_18008B511
0x18008a098  cmp     dword ptr [r14+0D4h], 7FFFFFFFh
0x18008a0a3  jz      loc_18008B51B
0x18008a0a9  mov     byte ptr [rsp+108h+var_98+8], 1
0x18008a0ae  mov     rcx, r14; this
0x18008a0b1  call    ?_IsJobActiveForIncomingCall@CBackgroundCopyJob@@AEBAJXZ; CBackgroundCopyJob::_IsJobActiveForIncomingCall(void)
0x18008a0b6  mov     r13d, eax
0x18008a0b9  test    eax, eax
0x18008a0bb  jns     short loc_18008A104
0x18008a0bd  mov     rcx, [rsp+108h]; this
0x18008a0c5  mov     r9d, eax; char *
0x18008a0c8  lea     r8, aCW1SSrcDeliver_24; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18008a0cf  mov     edx, 1EFh; void *
0x18008a0d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008a0d9  nop
0x18008a0da  sub     dword ptr [r14+0D4h], 1
0x18008a0e2  jnz     short loc_18008A0FC
0x18008a0e4  mov     dword ptr [r14+0D0h], 0FFFFFFFFh
0x18008a0ef  lea     rcx, [r14+98h]; SRWLock
0x18008a0f6  call    cs:__imp_ReleaseSRWLockExclusive
0x18008a0fc  mov     eax, r13d
0x18008a0ff  jmp     loc_18008B4EE
0x18008a104  mov     edx, [r14+188h]
0x18008a10b  test    edx, edx
0x18008a10d  jz      loc_18008A21A
0x18008a113  cmp     ebx, 0Ah
0x18008a116  ja      loc_18008A1A6
0x18008a11c  jz      loc_18008A21A
0x18008a122  mov     eax, ebx
0x18008a124  sub     eax, 1
0x18008a127  jz      short loc_18008A15D
0x18008a129  mov     r13d, 4
0x18008a12f  sub     eax, r13d
0x18008a132  jz      loc_18008A220
0x18008a138  sub     eax, 1
0x18008a13b  jz      loc_18008A220
0x18008a141  sub     eax, 1
0x18008a144  jz      loc_18008A220
0x18008a14a  sub     eax, 1
0x18008a14d  jz      loc_18008A220
0x18008a153  cmp     eax, 1
0x18008a156  jnz     short loc_18008A1C6
0x18008a158  jmp     loc_18008A220
0x18008a15d  cmp     edx, 1
0x18008a160  jnz     loc_18008A21A
0x18008a166  mov     rcx, [rsp+108h]; this
0x18008a16e  mov     ebx, 80D02013h
0x18008a173  mov     r9d, ebx; char *
0x18008a176  lea     r8, aCW1SSrcDeliver_24; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18008a17d  mov     edx, 207h; void *
0x18008a182  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008a187  nop
0x18008a188  sub     dword ptr [rdi+4Ch], 1
0x18008a18c  jnz     short loc_18008A19F
0x18008a18e  mov     dword ptr [rdi+48h], 0FFFFFFFFh
0x18008a195  lea     rcx, [rdi+10h]; SRWLock
0x18008a199  call    cs:__imp_ReleaseSRWLockExclusive
0x18008a19f  mov     eax, ebx
0x18008a1a1  jmp     loc_18008B4EE
0x18008a1a6  mov     eax, ebx
0x18008a1a8  sub     eax, 0Bh
0x18008a1ab  jz      short loc_18008A21A
0x18008a1ad  sub     eax, 5
0x18008a1b0  jz      short loc_18008A21A
0x18008a1b2  sub     eax, 6
0x18008a1b5  jz      short loc_18008A21A
0x18008a1b7  sub     eax, 1
0x18008a1ba  jz      short loc_18008A21A
0x18008a1bc  sub     eax, 3
0x18008a1bf  jz      short loc_18008A21A
0x18008a1c1  cmp     eax, 1
0x18008a1c4  jz      short loc_18008A21A
0x18008a1c6  mov     rcx, [rsp+108h]; this
0x18008a1ce  mov     [rsp+108h+var_D8], edx
0x18008a1d2  mov     dword ptr [rsp+108h+var_E0], ebx; char *
0x18008a1d6  lea     rax, aPropertyUNotAl; "Property %u not allowed to change in st"...
0x18008a1dd  mov     qword ptr [rsp+108h+var_E8], rax; int
0x18008a1e2  mov     ebx, 80D02013h
0x18008a1e7  mov     r9d, ebx; char *
0x18008a1ea  lea     r8, aCW1SSrcDeliver_24; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18008a1f1  mov     edx, 20Ch; void *
0x18008a1f6  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18008a1fb  nop
0x18008a1fc  sub     dword ptr [rdi+4Ch], 1
0x18008a200  jnz     short loc_18008A213
0x18008a202  mov     dword ptr [rdi+48h], 0FFFFFFFFh
0x18008a209  lea     rcx, [rdi+10h]; SRWLock
0x18008a20d  call    cs:__imp_ReleaseSRWLockExclusive
0x18008a213  mov     eax, ebx
0x18008a215  jmp     loc_18008B4EE
0x18008a21a  mov     r13d, 4
0x18008a220  lea     rbx, [r14+0E8h]
0x18008a227  mov     rcx, rbx; SRWLock
0x18008a22a  call    cs:__imp_AcquireSRWLockExclusive
0x18008a230  inc     dword ptr [rbx+0Ch]
0x18008a233  cmp     dword ptr [rbx+0Ch], 1
0x18008a237  jnz     short loc_18008A23E
0x18008a239  xor     eax, eax
0x18008a23b  xchg    eax, [rbx+8]
0x18008a23e  mov     [rsp+108h+var_A0], rbx
0x18008a243  mov     rcx, rbx; SRWLock
0x18008a246  call    cs:__imp_ReleaseSRWLockExclusive
0x18008a24c  nop
0x18008a24d  test    rdi, rdi
0x18008a250  jz      loc_18008B652
0x18008a256  sub     dword ptr [rdi+4Ch], 1
0x18008a25a  jnz     short loc_18008A26D
0x18008a25c  mov     dword ptr [rdi+48h], 0FFFFFFFFh
0x18008a263  lea     rcx, [rdi+10h]; SRWLock
0x18008a267  call    cs:__imp_ReleaseSRWLockExclusive
0x18008a26d  mov     byte ptr [rsp+108h+var_98+8], 0
0x18008a272  mov     rdx, [r14+0F8h]
0x18008a279  add     rdx, 10h; struct _GUID *
0x18008a27d  lea     rcx, [rsp+108h+var_68]; this
0x18008a285  call    ??0CGuidToString@@QEAA@AEBU_GUID@@@Z; CGuidToString::CGuidToString(_GUID const &)
0x18008a28a  mov     ecx, [rsp+108h+var_B8]
0x18008a28e  cmp     ecx, 10h
0x18008a291  ja      loc_18008AD77
0x18008a297  jz      loc_18008ACD7
0x18008a29d  cmp     ecx, r12d
0x18008a2a0  ja      loc_18008A88E
0x18008a2a6  jz      loc_18008A7C4
0x18008a2ac  mov     eax, ecx
0x18008a2ae  sub     eax, 1
0x18008a2b1  jz      loc_18008A725
0x18008a2b7  sub     eax, 1
0x18008a2ba  jz      loc_18008A686
0x18008a2c0  sub     eax, 1
0x18008a2c3  jz      loc_18008A5B7
0x18008a2c9  sub     eax, 1
0x18008a2cc  jz      loc_18008A451
0x18008a2d2  sub     eax, 1
0x18008a2d5  jz      loc_18008A3A1
0x18008a2db  cmp     eax, 1
0x18008a2de  jnz     loc_18008B063
0x18008a2e4  mov     rax, [r15]
0x18008a2e7  cmp     byte ptr [rax+20h], 3
0x18008a2eb  jnz     loc_18008B536
0x18008a2f1  mov     ecx, [rax]
0x18008a2f3  cmp     ecx, 5
0x18008a2f6  jb      short loc_18008A32C
0x18008a2f8  mov     rcx, [rsp+108h]; this
0x18008a300  mov     edi, 80070057h
0x18008a305  mov     r9d, edi; char *
0x18008a308  lea     r8, aCW1SSrcDeliver_24; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18008a30f  mov     edx, 249h; void *
0x18008a314  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008a319  nop
0x18008a31a  lea     rcx, [rsp+108h+var_A0]; this
0x18008a31f  call    ??1scope_exit@CWaitableCounter@@QEAA@XZ; CWaitableCounter::scope_exit::~scope_exit(void)
0x18008a324  nop
0x18008a325  mov     eax, edi
0x18008a327  jmp     loc_18008B4EE
0x18008a32c  test    sil, sil
0x18008a32f  jnz     short loc_18008A35E
0x18008a331  mov     dword ptr [rsp+108h+var_E0], ecx
0x18008a335  lea     rax, [rsp+108h+var_68]
0x18008a33d  mov     qword ptr [rsp+108h+var_E8], rax
0x18008a342  lea     r9, aJobSCostpolicy; "Job %s, CostPolicy: %u"
0x18008a349  mov     r8d, 24Bh; unsigned int
0x18008a34f  lea     rdx, aCbackgroundcop_5; "CBackgroundCopyJob::SetDownloadProperty"
0x18008a356  mov     ecx, r13d; unsigned __int8
0x18008a359  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x18008a35e  mov     r13, [r14+0F8h]
0x18008a365  mov     rdi, [r15]
0x18008a368  cmp     byte ptr [rdi+20h], 3
0x18008a36c  jnz     loc_18008B531
0x18008a372  mov     edi, [rdi]
  ... truncated ...
```
