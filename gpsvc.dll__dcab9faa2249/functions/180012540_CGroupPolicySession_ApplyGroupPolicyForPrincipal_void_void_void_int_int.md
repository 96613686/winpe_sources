# CGroupPolicySession::ApplyGroupPolicyForPrincipal(void *,void *,void *,int,int)

- ea: `0x180012540`
- end: `0x18001406f`
- name: `?ApplyGroupPolicyForPrincipal@CGroupPolicySession@@AEAAKPEAX00HH@Z`
- size: `6959`
- prototype: `__int64 __fastcall(CGroupPolicySession *this, void *, void *, void *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180011bc0`

## callees

- `0x180012540`
- `0x180014080`
- `0x180014290`
- `0x1800144e4`
- `0x180016640`
- `0x1800183d4`
- `0x18002206c`
- `0x1800234e4`
- `0x180023b34`
- `0x180030944`
- `0x180039004`
- `0x180046de0`
- `0x18004df78`
- `0x180063c74`
- `0x180068650`
- `0x18006b620`
- `0x180075ec0`
- `0x18007d320`
- `0x18007de08`
- `0x180089de0`
- `0x18008ab80`
- `0x180091728`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001308b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001308b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180012b00`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180012b47`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180012e24`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180012f7f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001318e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180013a50`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180013fad`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180012b00`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180012b47`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180012e24`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180012f7f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001318e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180013a50`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180013fad`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001367e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180013782`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001367e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180013782`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180012a4a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180012e6d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180012a4a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180012e6d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180012d20`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180012d20`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800130ae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800130ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012c4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013283`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800133a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013937`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013ad5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013c18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013c56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013f96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012c4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013283`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800133a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013937`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013ad5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013c18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013c56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013f96`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180013110`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180013110`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180013122`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180013122`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012ce0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013099`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012ce0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013099`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012dbf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013958`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012dbf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013958`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012821`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012c37`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012df9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013218`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013949`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012821`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012c37`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012df9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013218`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013949`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180012a08`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180012a08`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001293b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001293b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800125af`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180012b63`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800130b9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800130c7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800131aa`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800125af`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180012b63`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800130b9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800130c7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800131aa`
- `api-ms-win-core-sysinfo-l1-2-0!GetOsSafeBootMode` at `0x18001289b`
- `api-ms-win-core-sysinfo-l1-2-0!GetOsSafeBootMode` at `0x18001289b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180013108`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180013108`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180012ea1`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180012ea1`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180013aad`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180013aad`
- `api-ms-win-core-kernel32-legacy-l1-1-5!SetThreadExecutionState` at `0x1800125c1`
- `api-ms-win-core-kernel32-legacy-l1-1-5!SetThreadExecutionState` at `0x180012cb8`
- `api-ms-win-core-kernel32-legacy-l1-1-5!SetThreadExecutionState` at `0x1800125c1`
- `api-ms-win-core-kernel32-legacy-l1-1-5!SetThreadExecutionState` at `0x180012cb8`
- `ntdll!EtwEventWrite` at `0x18001280b`
- `ntdll!EtwEventWrite` at `0x180012c21`
- `ntdll!EtwEventWrite` at `0x18001280b`
- `ntdll!EtwEventWrite` at `0x180012c21`
- `ntdll!EtwEventActivityIdControl` at `0x180012f11`
- `ntdll!EtwEventActivityIdControl` at `0x180012fc8`
- `ntdll!EtwEventActivityIdControl` at `0x180012f11`
- `ntdll!EtwEventActivityIdControl` at `0x180012fc8`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x18001296c`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x18001296c`
- `DSROLE!DsRoleFreeMemory` at `0x180012f9c`
- `DSROLE!DsRoleFreeMemory` at `0x180012f9c`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180012ddd`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18001397a`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180012ddd`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18001397a`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180012da8`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180012da8`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180012d7d`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180012d7d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180012e02`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180012e0b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180012e02`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180012e0b`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800130e5`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800130e5`
- `SAMLIB!SamRegisterObjectChangeNotification` at `0x180012ebf`
- `SAMLIB!SamRegisterObjectChangeNotification` at `0x180012ebf`

## string_xrefs

- `0x180013479`: `CGroupPolicySession::ApplyGroupPolicyForPrincipal: Beginning Wait AsyncInitializationCompletedEvent.`
- `0x1800134ab`: `CGroupPolicySession::ApplyGroupPolicyForPrincipal: Beginning Wait AsyncInitializationCompletedEvent.`
- `0x1800134da`: `CGroupPolicySession::ApplyGroupPolicyForPrincipal: Wait AsyncInitializationCompletedEvent timeout.`
- `0x18001350c`: `CGroupPolicySession::ApplyGroupPolicyForPrincipal: Wait AsyncInitializationCompletedEvent timeout.`
- `0x18001352e`: `CGroupPolicySession::ApplyGroupPolicyForPrincipal: Ending Wait AsyncInitializationCompletedEvent.`
- `0x180013560`: `CGroupPolicySession::ApplyGroupPolicyForPrincipal: Ending Wait AsyncInitializationCompletedEvent.`
- `0x1800138f1`: `Machine joined to workgroup. Waiting for SamSs service to start...`
- `0x180013921`: `Machine joined to workgroup. Waiting for SamSs service to start...`
- `0x18001399f`: `Wait for SamSs service to start failed after wait of %d ms`
- `0x1800139d7`: `Wait for SamSs service to start failed after wait of %d ms`
- `0x180013bb7`: `CGroupPolicySession::ApplyGroupPolicyForPrincipal Setting m_pPolicyInfoReadyEvent`
- `0x180013be9`: `CGroupPolicySession::ApplyGroupPolicyForPrincipal Setting m_pPolicyInfoReadyEvent`
- `0x180013c21`: `CGroupPolicySession::ApplyGroupPolicyForPrincipal Set m_pPolicyInfoReadyEvent return with error 0x%x`
- `0x180013c5f`: `CGroupPolicySession::ApplyGroupPolicyForPrincipal Set m_pPolicyInfoReadyEvent return with error 0x%x`
- `0x180013cb8`: `No tasks created. Background policy processing is disabled by policy.`
- `0x180013ced`: `No tasks created. Background policy processing is disabled by policy.`
- `0x180013e4c`: `CreatePolicyTask failed with 0x%x.`
- `0x180013e84`: `CreatePolicyTask failed with 0x%x.`
- `0x180013eb3`: `CreatePolicyTask succeeded.`
- `0x180013ee8`: `CreatePolicyTask succeeded.`
- `0x180013f0a`: `Setting m_hApplyGroupPolicyCompletedEvent via SUCCESS.`
- `0x180013f3f`: `Setting m_hApplyGroupPolicyCompletedEvent via SUCCESS.`
- `0x180013fcc`: `Setting m_hApplyGroupPolicyCompletedEvent via ERROR.`
- `0x180013ffe`: `Setting m_hApplyGroupPolicyCompletedEvent via ERROR.`
- `0x180013699`: `CGroupPolicySession::WaitForMachinePolicyEventsToBeSignaled (foreground): Completed WaitForSingleObject.`
- `0x1800136c5`: `CGroupPolicySession::WaitForMachinePolicyEventsToBeSignaled (foreground): Completed WaitForSingleObject.`
- `0x1800136e3`: `UserPolicy: Waiting for machine policy complete event with timeout %d ms`
- `0x180013716`: `UserPolicy: Waiting for machine policy complete event with timeout %d ms`
- `0x1800137a1`: `CGroupPolicySession::WaitForMachinePolicyEventsToBeSignaled: Completed WaitForSingleObject.`
- `0x1800137d1`: `CGroupPolicySession::WaitForMachinePolicyEventsToBeSignaled: Completed WaitForSingleObject.`
- `0x1800137f9`: `GetAOACConfig: dwAOACConfig was 0, setting to %d.`
- `0x18001382f`: `GetAOACConfig: dwAOACConfig was 0, setting to %d.`
- `0x180013031`: `GetAOACConfig: dwAOACConfig is %d.`
- `0x180013857`: `GetAOACConfig: dwAOACConfig is %d.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CGroupPolicySession::ApplyGroupPolicyForPrincipal(
        CGroupPolicySession *this,
        void *a2,
        void *a3,
        void *a4,
        unsigned int a5,
        unsigned int a6)
{
  char *v7; // rbx
  DWORD TickCount; // r12d
  char *v9; // r13
  CGroupPolicySession *v10; // rcx
  unsigned int LastError; // edi
  unsigned int v12; // eax
  int v13; // r12d
  char *v14; // rax
  unsigned __int64 v15; // rcx
  unsigned int v16; // r15d
  int v17; // eax
  int v18; // ecx
  DWORD dwWin32ExitCode; // edx
  __int64 v20; // rcx
  __int64 v21; // rax
  DWORD v22; // edx
  __int64 v23; // rcx
  __int64 v24; // rax
  unsigned int EventDataDescriptorStorage; // eax
  _QWORD *v26; // r14
  DWORD v27; // edi
  __int64 v28; // rax
  unsigned __int64 v29; // r12
  __int64 v30; // rax
  int v31; // edi
  HANDLE v32; // r14
  int v33; // r14d
  void (*v34)(unsigned int, const unsigned __int16 *, ...); // rax
  HANDLE v35; // r14
  DWORD PrimaryDomainInformation; // eax
  __int64 v37; // r8
  void (*v38)(unsigned int, const unsigned __int16 *, ...); // rax
  __int64 v39; // r14
  HANDLE v40; // rax
  __int64 v41; // r14
  DWORD v42; // edx
  __int64 v43; // rcx
  __int64 v44; // rax
  unsigned int v45; // eax
  _QWORD *v46; // r15
  DWORD v47; // r14d
  __int64 v48; // rax
  unsigned __int64 v49; // r12
  __int64 v50; // rdx
  DWORD v51; // eax
  __int64 v52; // r8
  __int64 v53; // rdx
  CGroupPolicySession *v54; // rcx
  CGroupPolicySession *v55; // rcx
  SC_HANDLE v57; // rax
  SC_HANDLE v58; // rdi
  SC_HANDLE v59; // r12
  struct _QUERY_SERVICE_CONFIGW *v60; // rax
  struct _QUERY_SERVICE_CONFIGW *v61; // r14
  void *v62; // rcx
  HANDLE EventW; // rax
  HANDLE *v64; // rdi
  __int64 v65; // rax
  int v66; // eax
  unsigned int v67; // eax
  void *v68; // rcx
  unsigned int v69; // edx
  unsigned int v70; // eax
  void (*v71)(unsigned int, const unsigned __int16 *, ...); // rax
  struct _RTL_CRITICAL_SECTION *v72; // r14
  HANDLE CurrentProcess; // rax
  HANDLE v74; // r14
  DWORD v75; // edi
  void (*v76)(unsigned int, const unsigned __int16 *, ...); // rax
  struct _QUERY_SERVICE_CONFIGW *v77; // rax
  unsigned int v78; // edi
  void *v79; // rcx
  void (*v80)(unsigned int, const unsigned __int16 *, ...); // r14
  DWORD v81; // eax
  DWORD v82; // eax
  __int64 *v83; // rdx
  __int64 v84; // rdx
  int ProcessingInterval; // eax
  int PolicyTask; // eax
  void *v87; // rcx
  SIZE_T uBytes; // [rsp+50h] [rbp-B0h] BYREF
  BOOL v89; // [rsp+58h] [rbp-A8h] BYREF
  int v90; // [rsp+60h] [rbp-A0h] BYREF
  DWORD v91; // [rsp+64h] [rbp-9Ch]
  int v92; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v93; // [rsp+70h] [rbp-90h] BYREF
  DWORD pcbData; // [rsp+78h] [rbp-88h] BYREF
  HANDLE hHandle; // [rsp+80h] [rbp-80h] BYREF
  void *TokenHandle; // [rsp+88h] [rbp-78h] BYREF
  HANDLE v97; // [rsp+90h] [rbp-70h] BYREF
  PBYTE Buffer; // [rsp+98h] [rbp-68h] BYREF
  char *v99; // [rsp+A0h] [rbp-60h]
  HANDLE v100; // [rsp+A8h] [rbp-58h]
  __int64 v101; // [rsp+B0h] [rbp-50h]
  unsigned int v102; // [rsp+C0h] [rbp-40h] BYREF
  void *v103; // [rsp+C8h] [rbp-38h]
  PCWSTR SourceString; // [rsp+108h] [rbp+8h]
  struct _SERVICE_STATUS hMem; // [rsp+200h] [rbp+100h] BYREF

  v97 = a4;
  v100 = a3;
  hHandle = a2;
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(
        4u,
        L"CGroupPolicySession::ApplyGroupPolicyForPrincipal::++ (bTriggered: %ld, bConsole: %ld)",
        a5,
        a6);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(
        4u,
        L"CGroupPolicySession::ApplyGroupPolicyForPrincipal::++ (bTriggered: %ld, bConsole: %ld)",
        a5,
        a6);
    }
  }
  TokenHandle = 0;
  v90 = 0;
  LODWORD(uBytes) = 0;
  v7 = 0;
  v99 = 0;
  Buffer = 0;
  TickCount = GetTickCount();
  v91 = TickCount;
  SetThreadExecutionState(0x80000001);
  v89 = 0;
  v9 = (char *)this + 184;
  LastError = (*(__int64 (__fastcall **)(char *, BOOL *))(*((_QWORD *)this + 23) + 16LL))((char *)this + 184, &v89);
  if ( !LastError )
  {
    v12 = v89
        ? CGroupPolicySession::GetMachineAccountInfo(v10, &v90, (int *)&uBytes)
        : CGroupPolicySession::GetUserAccountInfo(this, &v90, (int *)&uBytes);
    LastError = v12;
    if ( !v12 )
    {
      v13 = v90;
      *((_DWORD *)this + 110) = v90;
      v92 = 0;
      LastError = (*(__int64 (__fastcall **)(char *, int *))(*(_QWORD *)v9 + 16LL))((char *)this + 184, &v92);
      if ( LastError )
        goto LABEL_89;
      if ( v92 )
      {
        CurrentProcess = GetCurrentProcess();
        if ( OpenProcessToken(CurrentProcess, 0xEu, &TokenHandle) )
        {
          v14 = (char *)TokenHandle;
        }
        else
        {
          GetLastError();
          v14 = 0;
          TokenHandle = 0;
        }
        v7 = v14;
        v99 = v14;
      }
      else
      {
        if ( (*(unsigned int (__fastcall **)(char *, void **))(*(_QWORD *)v9 + 8LL))((char *)this + 184, &TokenHandle) )
        {
          TokenHandle = 0;
          goto LABEL_175;
        }
        v14 = (char *)TokenHandle;
      }
      if ( v14 )
      {
        v15 = (v92 != 0) | 0x10u;
        if ( !a5 )
          v15 = v92 != 0;
        v16 = v15 | 0x20;
        if ( !a6 )
          v16 = v15;
        v17 = *((_DWORD *)this + 99);
        if ( v17 == 1 )
        {
          v16 |= 8u;
        }
        else if ( v17 == 2 )
        {
          v16 |= 0x200000u;
        }
        if ( v13 )
        {
          if ( !(unsigned int)CGroupPolicySession::IsBackgroundPolicyEnabledForWorkgroups((CGroupPolicySession *)v15) )
            goto LABEL_20;
        }
        else if ( !(unsigned int)CGroupPolicySession::IsBackgroundPolicyEnabled((CGroupPolicySession *)v15) )
        {
LABEL_20:
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(4u, L"GP_BACKGROUND_REFRESH is not enabled.");
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(4u, L"GP_BACKGROUND_REFRESH is not enabled.");
            }
          }
LABEL_21:
          *(_QWORD *)&hMem.dwServiceType = 0;
          *(_QWORD *)&hMem.dwControlsAccepted = 0;
          v18 = *((_DWORD *)this + 99);
          pcbData = v18 == 2;
          v89 = v18 == 1;
          v93 = v92;
          if ( !COperationalBaseEvent::VerifyAndAllocateEventDataDescriptorStorage((COperationalBaseEvent *)&hMem) )
          {
            dwWin32ExitCode = hMem.dwWin32ExitCode;
            v20 = 2LL * hMem.dwWin32ExitCode;
            v21 = *(_QWORD *)&hMem.dwServiceType;
            *(_QWORD *)(*(_QWORD *)&hMem.dwServiceType + 8 * v20) = &v93;
            *(_QWORD *)(v21 + 8 * v20 + 8) = 4;
            hMem.dwWin32ExitCode = dwWin32ExitCode + 1;
          }
          if ( !COperationalBaseEvent::VerifyAndAllocateEventDataDescriptorStorage((COperationalBaseEvent *)&hMem) )
          {
            v22 = hMem.dwWin32ExitCode;
            v23 = 2LL * hMem.dwWin32ExitCode;
            v24 = *(_QWORD *)&hMem.dwServiceType;
            *(_QWORD *)(*(_QWORD *)&hMem.dwServiceType + 8 * v23) = &pcbData;
            *(_QWORD *)(v24 + 8 * v23 + 8) = 4;
            hMem.dwWin32ExitCode = v22 + 1;
          }
          EventDataDescriptorStorage = COperationalBaseEvent::VerifyAndAllocateEventDataDescriptorStorage((COperationalBaseEvent *)&hMem);
          v26 = *(_QWORD **)&hMem.dwServiceType;
          v27 = hMem.dwWin32ExitCode;
          if ( !EventDataDescriptorStorage )
          {
            v28 = 2LL * hMem.dwWin32ExitCode;
            *(_QWORD *)(*(_QWORD *)&hMem.dwServiceType + 8 * v28) = &v89;
            v26[v28 + 1] = 4;
            hMem.dwWin32ExitCode = ++v27;
          }
          v29 = CGPServiceEventReporting::s_pEventProviderHandle;
          v30 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
          v101 = v30;
          if ( *(_BYTE *)(v30 + 8) == 1 )
          {
            v67 = EtwEventActivityIdControl(2, v30 + 16);
            if ( v67 )
            {
              if ( *(_DWORD *)&g_dwDebugLevel )
              {
                if ( g_lpDebugMsg )
                {
                  g_lpDebugMsg(
                    2u,
                    L"COperationalBaseEvent::ReportOperationalEvent: Failed to set the activity id with error 0x%x",
                    v67);
                }
                else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                {
                  RedirectDebugMsg(
                    2u,
                    L"COperationalBaseEvent::ReportOperationalEvent: Failed to set the activity id with error 0x%x",
                    v67);
                }
              }
            }
          }
          if ( (unsigned int)EtwEventWrite(v29, gpEvent_GP_SESSION_START, v27, v26) )
            GetLastError();
          if ( v26 )
            LocalFree(v26);
          v31 = v90;
          if ( v90 || (_DWORD)uBytes || (unsigned int)CSKU::IsDomainIncapableSystem() )
          {
            if ( *(_DWORD *)&g_dwDebugLevel )
            {
              if ( g_lpDebugMsg )
              {
                g_lpDebugMsg(4u, L"Not applying DS policy");
              }
              else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              {
                RedirectDebugMsg(4u, L"Not applying DS policy");
              }
            }
          }
          else
          {
            if ( *(_DWORD *)&g_dwDebugLevel )
            {
              if ( g_lpDebugMsg )
              {
                g_lpDebugMsg(4u, L" CGroupPolicySession::ApplyGroupPolicyForPrincipal setting GP_APPLY_DS_POLICY flag");
              }
              else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              {
                RedirectDebugMsg(
                  4u,
                  L" CGroupPolicySession::ApplyGroupPolicyForPrincipal setting GP_APPLY_DS_POLICY flag");
              }
            }
            v16 |= 4u;
          }
          memset_0(&v102, 0, 0x140u);
          v102 = v16;
          v103 = TokenHandle;
          CanStartFromLocalDataStore((struct _GPOINFO *)&v102);
          if ( SourceString )
            DeleteSidString(SourceString);
          v32 = hHandle;
          if ( hHandle )
          {
            if ( *(_DWORD *)&g_dwDebugLevel )
            {
              if ( g_lpDebugMsg )
              {
                g_lpDebugMsg(
                  4u,
                  L"CGroupPolicySession::ApplyGroupPolicyForPrincipal: Beginning Wait AsyncInitializationCompletedEvent.");
              }
              else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              {
                RedirectDebugMsg(
                  4u,
                  L"CGroupPolicySession::ApplyGroupPolicyForPrincipal: Beginning Wait AsyncInitializationCompletedEvent.");
              }
            }
            LastError = WaitForSingleObject(v32, 0xFFFFFFFF);
            if ( LastError )
            {
              if ( *(_DWORD *)&g_dwDebugLevel )
              {
                if ( g_lpDebugMsg )
                {
                  g_lpDebugMsg(
                    2u,
                    L"CGroupPolicySession::ApplyGroupPolicyForPrincipal: Wait AsyncInitializationCompletedEvent timeout.");
                }
                else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                {
                  RedirectDebugMsg(
                    2u,
                    L"CGroupPolicySession::ApplyGroupPolicyForPrincipal: Wait AsyncInitializationCompletedEvent timeout.");
                }
              }
              goto LABEL_89;
            }
            if ( *(_DWORD *)&g_dwDebugLevel )
            {
              if ( g_lpDebugMsg )
              {
                g_lpDebugMsg(
                  4u,
                  L"CGroupPolicySession::ApplyGroupPolicyForPrincipal: Ending Wait AsyncInitializationCompletedEvent.");
              }
              else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              {
                RedirectDebugMsg(
                  4u,
                  L"CGroupPolicySession::ApplyGroupPolicyForPrincipal: Ending Wait AsyncInitializationCompletedEvent.");
              }
            }
            v31 = v90;
          }
          if ( !*((_QWORD *)this + 41) )
          {
            if ( !CDefaultPolicyApplier::s_pInstance )
            {
              LastError = 21;
              goto LABEL_89;
            }
            *((_QWORD *)this + 41) = CDefaultPolicyApplier::s_pInstance;
          }
          LODWORD(uBytes) = 0;
          GetOsSafeBootMode(&uBytes);
          if ( (_DWORD)uBytes == 3 )
          {
            LastError = 50;
            CGPOperationalTraceEvent::ReportOperationalEventInternal(1, 4104, 50, 0);
            goto LABEL_89;
          }
          v33 = 0;
          v89 = 0;
          v93 = 0;
          if ( v92 || *((_DWORD *)this + 101) )
            goto LABEL_45;
          if ( *((_DWORD *)this + 99) )
          {
            v34 = g_lpDebugMsg;
            if ( !*(_DWORD *)&g_dwDebugLevel )
              goto LABEL_43;
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(4u, L"UserPolicy: Waiting for machine policy complete event with timeout %d ms", 600000);
            }
            else
            {
              if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
              {
LABEL_43:
                v35 = v100;
                if ( v100 )
                {
                  if ( *(_DWORD *)&g_dwDebugLevel )
                  {
                    if ( v34 )
                    {
                      v34(
                        4u,
                        L"CGroupPolicySession::WaitForMachinePolicyEventsToBeSignaled: Beginning WaitForSingleObject.");
                    }
                    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                    {
                      RedirectDebugMsg(
                        4u,
                        L"CGroupPolicySession::WaitForMachinePolicyEventsToBeSignaled: Beginning WaitForSingleObject.");
                    }
                  }
                  WaitForSingleObjectEx(v35, 0x927C0u, 0);
                  if ( *(_DWORD *)&g_dwDebugLevel )
                  {
                    if ( g_lpDebugMsg )
                    {
                      g_lpDebugMsg(
                        4u,
                        L"CGroupPolicySession::WaitForMachinePolicyEventsToBeSignaled: Completed WaitForSingleObject.");
                    }
                    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                    {
                      RedirectDebugMsg(
                        4u,
                        L"CGroupPolicySession::WaitForMachinePolicyEventsToBeSignaled: Completed WaitForSingleObject.");
                    }
                  }
                }
                goto LABEL_44;
              }
              RedirectDebugMsg(4u, L"UserPolicy: Waiting for machine policy complete event with timeout %d ms", 600000);
            }
            v34 = g_lpDebugMsg;
            goto LABEL_43;
          }
          if ( v31 )
          {
LABEL_45:
            LODWORD(uBytes) = 0;
            pcbData = 4;
            RegGetValueW(
              HKEY_LOCAL_MACHINE,
              L"Software\\Policies\\Microsoft\\Windows\\System",
              L"DisableAOACProcessing",
              0x10u,
              0,
              &uBytes,
              &pcbData);
            if ( (_DWORD)uBytes )
            {
              if ( !*(_DWORD *)&g_dwDebugLevel )
                goto LABEL_47;
              v71 = g_lpDebugMsg;
              if ( g_lpDebugMsg )
              {
                g_lpDebugMsg(4u, L"GetAOACConfig: dwAOACConfig is %d.", (unsigned int)uBytes);
LABEL_139:
                v71 = g_lpDebugMsg;
                goto LABEL_140;
              }
              if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              {
                RedirectDebugMsg(4u, L"GetAOACConfig: dwAOACConfig is %d.", (unsigned int)uBytes);
                goto LABEL_139;
              }
            }
            else
            {
              LODWORD(uBytes) = 600;
              if ( !*(_DWORD *)&g_dwDebugLevel )
                goto LABEL_47;
              v71 = g_lpDebugMsg;
              if ( g_lpDebugMsg )
              {
                g_lpDebugMsg(4u, L"GetAOACConfig: dwAOACConfig was 0, setting to %d.", 600);
                goto LABEL_139;
              }
              if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              {
                RedirectDebugMsg(4u, L"GetAOACConfig: dwAOACConfig was 0, setting to %d.", 600);
                goto LABEL_139;
              }
            }
LABEL_140:
            if ( *(_DWORD *)&g_dwDebugLevel )
            {
              if ( v71 )
              {
                v71(
                  4u,
                  L"CGroupPolicySession::ApplyGroupPolicyForPrincipal: Check if machine is a domain controller starts.");
              }
              else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              {
                RedirectDebugMsg(
                  4u,
                  L"CGroupPolicySession::ApplyGroupPolicyForPrincipal: Check if machine is a domain controller starts.");
              }
            }
LABEL_47:
            PrimaryDomainInformation = DsRoleGetPrimaryDomainInformation(0, DsRolePrimaryDomainInfoBasic, &Buffer);
            v37 = PrimaryDomainInformation;
            if ( PrimaryDomainInformation )
            {
              v38 = g_lpDebugMsg;
              if ( !*(_DWORD *)&g_dwDebugLevel )
                goto LABEL_49;
              if ( g_lpDebugMsg )
              {
                g_lpDebugMsg(2u, L"DsRoleGetPrimaryDomainInformation() failed with error=0x%x", v37);
LABEL_284:
                v38 = g_lpDebugMsg;
                goto LABEL_49;
              }
              if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              {
                RedirectDebugMsg(2u, L"DsRoleGetPrimaryDomainInformation() failed with error=0x%x", v37);
                goto LABEL_284;
              }
            }
            else
            {
              v69 = *(_DWORD *)Buffer;
              if ( (unsigned int)(*(_DWORD *)Buffer - 4) > 1 )
              {
                v93 = 1;
                if ( v69 <= 1 )
                {
                  if ( (_DWORD)uBytes != 1 )
                    v33 = 1;
                  v89 = v33;
                }
              }
              DsRoleFreeMemory(Buffer);
              v38 = g_lpDebugMsg;
              if ( v33 )
                v16 |= 0x40u;
            }
LABEL_49:
            if ( !v92 )
              goto LABEL_50;
            if ( !v31 )
            {
              if ( a5 )
              {
                v68 = (void *)*((_QWORD *)this + 37);
                if ( v68 )
                  SetEvent(v68);
              }
              else
              {
                if ( *(_DWORD *)&g_dwDebugLevel )
                {
                  if ( v38 )
                  {
                    v38(2u, L"Waiting for connectivity before applying policies", v37);
                  }
                  else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                  {
                    RedirectDebugMsg(2u, L"Waiting for connectivity before applying policies", v37);
                  }
                }
                v78 = CGroupPolicySession::WaitForMachineConnectivity(this, 1);
                v79 = (void *)*((_QWORD *)this + 37);
                if ( v79 )
                  SetEvent(v79);
                if ( v78 )
                  CGPOperationalTraceEvent::ReportOperationalEventInternal(1, 4103, v78, 0);
              }
LABEL_114:
              if ( !v93 )
                goto LABEL_50;
              goto LABEL_115;
            }
            if ( *(_DWORD *)&g_dwDebugLevel )
            {
              if ( v38 )
              {
                v38(4u, L"Machine joined to workgroup. Waiting for SamSs service to start...", v37);
              }
              else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              {
                RedirectDebugMsg(4u, L"Machine joined to workgroup. Waiting for SamSs service to start...", v37);
              }
            }
            LODWORD(uBytes) = 512;
            memset(&hMem, 0, sizeof(hMem));
            v57 = OpenSCManagerW(0, 0, 1u);
            v58 = v57;
            hHandle = v57;
            if ( !v57 )
            {
LABEL_113:
              if ( *(_DWORD *)&g_dwDebugLevel )
              {
                if ( g_lpDebugMsg )
                {
                  g_lpDebugMsg(2u, L"Wait for SamSs service to start failed after wait of %d ms", 120000);
                }
                else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                {
                  RedirectDebugMsg(2u, L"Wait for SamSs service to start failed after wait of %d ms", 120000);
                }
              }
              goto LABEL_114;
            }
            pcbData = 0;
            v59 = OpenServiceW(v57, L"SamSs", 5u);
            if ( !v59 )
            {
LABEL_108:
              CloseServiceHandle(v58);
              if ( pcbData )
              {
                v62 = (void *)*((_QWORD *)this + 37);
                if ( v62 )
                  SetEvent(v62);
LABEL_115:
                EventW = CreateEventW(0, 0, 0, 0);
                v64 = (HANDLE *)((char *)this + 376);
                *((_QWORD *)this + 47) = EventW;
                if ( EventW )
                {
                  v65 = RegisterWaitForSingleObjectEx(
                          EventW,
                          CGroupPolicySession::DeleteStaleLGPOsCallback,
                          this,
                          0xFFFFFFFFLL,
                          0);
                  *((_QWORD *)this + 48) = v65;
                  if ( v65 )
                  {
                    v66 = SamRegisterObjectChangeNotification(2, *v64);
                    if ( v66 < 0 )
                    {
                      if ( *(_DWORD *)&g_dwDebugLevel )
                      {
                        if ( g_lpDebugMsg )
                        {
                          g_lpDebugMsg(
                            2u,
                            L"SamRegisterObjectChangeNotification() for m_hLocalUserAccountChangeEvent handle=%p failed due to error=%d.",
                            *v64,
                            (unsigned int)v66);
                        }
                        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                        {
                          RedirectDebugMsg(
                            2u,
                            L"SamRegisterObjectChangeNotification() for m_hLocalUserAccountChangeEvent handle=%p failed due to error=%d.",
                            *v64,
                            (unsigned int)v66);
                        }
                      }
                      UnregisterWaitEx(*((HANDLE *)this + 48), (HANDLE)0xFFFFFFFFFFFFFFFFLL);
                      *((_QWORD *)this + 48) = 0;
                      CGroupPolicySession::SafeCloseHandle(this, (void **)this + 47);
                    }
                  }
                  else
                  {
                    v72 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 13);
                    if ( v72 )
                      EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 13));
                    if ( *v64 )
                    {
                      CloseHandle(*v64);
                      *v64 = 0;
                    }
                    if ( v72 )
                      LeaveCriticalSection(v72);
                  }
                }
LABEL_50:
                v39 = 0;
                v93 = 0;
                LastError = (*(__int64 (__fastcall **)(char *, unsigned int *, __int64))(*(_QWORD *)v9 + 16LL))(
                              (char *)this + 184,
                              &v93,
                              v37);
                if ( !LastError )
                {
                  if ( v93 )
                  {
                    v39 = -2147483646;
                    goto LABEL_59;
                  }
                  if ( *((_QWORD *)this + 21) )
                  {
                    v39 = *((_QWORD *)this + 21);
                    goto LABEL_59;
                  }
                  hHandle = 0;
                  LastError = (*(__int64 (__fastcall **)(char *, HANDLE *))(*(_QWORD *)v9 + 32LL))(
                                (char *)this + 184,
                                &hHandle);
                  if ( !LastError )
                  {
                    LastError = RegOpenCurrentUser(0x2001Fu, (PHKEY)this + 21);
                    if ( !LastError )
                      v39 = *((_QWORD *)this + 21);
                    (*(void (__fastcall **)(char *, HANDLE *))(*(_QWORD *)v9 + 40LL))((char *)this + 184, &hHandle);
                  }
                }
                if ( LastError )
                  goto LABEL_89;
LABEL_59:
                LastError = 0;
                v40 = CreateEventW(0, 1, 0, 0);
                *((_QWORD *)this + 22) = v40;
                if ( !v40 )
                  LastError = GetLastError();
                if ( LastError || !v39 )
                  goto LABEL_72;
                if ( *(_DWORD *)&g_dwDebugLevel )
                {
                  if ( g_lpDebugMsg )
                  {
                    g_lpDebugMsg(
                      4u,
                      L"CGroupPolicySession::ApplyGroupPolicyForPrincipal::ApplyGroupPolicy (dwFlags: %ld).",
                      v16);
                  }
                  else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                  {
                    RedirectDebugMsg(
                      4u,
                      L"CGroupPolicySession::ApplyGroupPolicyForPrincipal::ApplyGroupPolicy (dwFlags: %ld).",
                      v16);
                  }
                }
                v41 = (***((__int64 (__fastcall ****)(_QWORD, _QWORD, void *, _QWORD, __int64, unsigned int (*)(int, unsigned __int16 *), _QWORD, char *, _DWORD))this
                         + 41))(
                        *((_QWORD *)this + 41),
                        v16,
                        TokenHandle,
                        *((_QWORD *)this + 22),
                        v39,
                        CStatusMessage::UpdateStatusMessage,
                        *(_QWORD *)(*((_QWORD *)this + 42) + 344LL),
                        (char *)this + 8,
                        *((_DWORD *)this + 100));
                if ( v92 && !a5 )
                {
                  if ( *(_DWORD *)&g_dwDebugLevel )
                  {
                    if ( g_lpDebugMsg )
                    {
                      g_lpDebugMsg(
                        4u,
                        L"CGroupPolicySession::ApplyGroupPolicyForPrincipal::ExecuteGPOScriptsForThePrincipal");
                    }
                    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                    {
                      RedirectDebugMsg(
                        4u,
                        L"CGroupPolicySession::ApplyGroupPolicyForPrincipal::ExecuteGPOScriptsForThePrincipal");
                    }
                  }
                  CGroupPolicySession::ExecuteGPOScriptsForThePrincipal(this, 1, 0);
                }
                *((_QWORD *)this + 26) = v41;
                if ( *(_DWORD *)&g_dwDebugLevel )
                {
                  if ( g_lpDebugMsg )
                  {
                    g_lpDebugMsg(
                      4u,
                      L"CGroupPolicySession::ApplyGroupPolicyForPrincipal Setting m_pPolicyInfoReadyEvent");
                  }
                  else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                  {
                    RedirectDebugMsg(
                      4u,
                      L"CGroupPolicySession::ApplyGroupPolicyForPrincipal Setting m_pPolicyInfoReadyEvent");
                  }
                }
                if ( !SetEvent(*((HANDLE *)this + 27)) && *(_DWORD *)&g_dwDebugLevel )
                {
                  v80 = g_lpDebugMsg;
                  if ( g_lpDebugMsg )
                  {
                    v81 = GetLastError();
                    v80(
                      2u,
                      L"CGroupPolicySession::ApplyGroupPolicyForPrincipal Set m_pPolicyInfoReadyEvent return with error 0x%x",
                      v81);
                  }
                  else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                  {
                    v82 = GetLastError();
                    RedirectDebugMsg(
                      2u,
                      L"CGroupPolicySession::ApplyGroupPolicyForPrincipal Set m_pPolicyInfoReadyEvent return with error 0x%x",
                      v82);
                  }
                }
                if ( !*((_QWORD *)this + 26) )
                  CGroupPolicySession::SafeCloseHandle(this, (void **)this + 22);
                *((_DWORD *)this + 56) = 0;
                if ( a5 )
                {
LABEL_70:
                  if ( *(_DWORD *)&g_dwDebugLevel )
                  {
                    if ( g_lpDebugMsg )
                    {
                      g_lpDebugMsg(4u, L"Setting m_hApplyGroupPolicyCompletedEvent via SUCCESS.");
                    }
                    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                    {
                      RedirectDebugMsg(4u, L"Setting m_hApplyGroupPolicyCompletedEvent via SUCCESS.");
                    }
                  }
                  SetEvent(*((HANDLE *)this + 36));
LABEL_72:
                  *(_QWORD *)&hMem.dwServiceType = 0;
                  *(_QWORD *)&hMem.dwControlsAccepted = 0;
                  v93 = GetTickCount() - v91;
                  LODWORD(v97) = v92;
                  if ( !COperationalBaseEvent::VerifyAndAllocateEventDataDescriptorStorage((COperationalBaseEvent *)&hMem) )
                  {
                    v42 = hMem.dwWin32ExitCode;
                    v43 = 2LL * hMem.dwWin32ExitCode;
                    v44 = *(_QWORD *)&hMem.dwServiceType;
                    *(_QWORD *)(*(_QWORD *)&hMem.dwServiceType + 8 * v43) = &v97;
                    *(_QWORD *)(v44 + 8 * v43 + 8) = 4;
                    hMem.dwWin32ExitCode = v42 + 1;
                  }
                  v45 = COperationalBaseEvent::VerifyAndAllocateEventDataDescriptorStorage((COperationalBaseEvent *)&hMem);
                  v46 = *(_QWORD **)&hMem.dwServiceType;
                  v47 = hMem.dwWin32ExitCode;
                  if ( !v45 )
                  {
                    v48 = 2LL * hMem.dwWin32ExitCode;
                    *(_QWORD *)(*(_QWORD *)&hMem.dwServiceType + 8 * v48) = &v93;
                    v46[v48 + 1] = 4;
                    hMem.dwWin32ExitCode = ++v47;
                  }
                  v49 = CGPServiceEventReporting::s_pEventProviderHandle;
                  if ( *(_BYTE *)(v101 + 8) == 1 )
                  {
                    v70 = EtwEventActivityIdControl(2, v101 + 16);
                    if ( v70 )
                    {
                      if ( *(_DWORD *)&g_dwDebugLevel )
                      {
                        if ( g_lpDebugMsg )
                        {
                          g_lpDebugMsg(
                            2u,
                            L"COperationalBaseEvent::ReportOperationalEvent: Failed to set the activity id with error 0x%x",
                            v70);
                        }
                        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                        {
                          RedirectDebugMsg(
                            2u,
                            L"COperationalBaseEvent::ReportOperationalEvent: Failed to set the activity id with error 0x%x",
                            v70);
                        }
                      }
                    }
                  }
                  if ( (unsigned int)EtwEventWrite(v49, gpEvent_GP_SESSION_END, v47, v46) )
                    GetLastError();
                  if ( v46 )
                    LocalFree(v46);
                  goto LABEL_89;
                }
                v50 = *((_QWORD *)this + 26);
                if ( v50 )
                {
                  v52 = 0;
                  v53 = *(unsigned int *)(v50 + 16);
                }
                else
                {
                  v51 = GetLastError();
                  v52 = v51;
                  if ( !v51 )
                    v52 = 13;
                  v53 = 0;
                }
                LastError = (**((__int64 (__fastcall ***)(char *, __int64, __int64, _QWORD, _DWORD, int))this + 1))(
                              (char *)this + 8,
                              v53,
                              v52,
                              0,
                              0,
                              1);
                if ( !v89 )
                  goto LABEL_88;
                if ( v90 )
                {
                  if ( !(unsigned int)CGroupPolicySession::IsBackgroundPolicyEnabledForWorkgroups(v54) )
                    goto LABEL_88;
                }
                else if ( !(unsigned int)CGroupPolicySession::IsBackgroundPolicyEnabled(v54) )
                {
                  goto LABEL_88;
                }
                if ( (unsigned int)CGroupPolicySession::IsBackgroundPolicyEnabled(v55) )
                {
                  if ( !(unsigned int)CSKU::WaitForNetwork() )
                  {
                    v83 = (__int64 *)*((_QWORD *)this + 26);
                    if ( v83 )
                    {
                      v84 = *v83;
                      if ( v84 )
                      {
                        LODWORD(uBytes) = 0;
                        ProcessingInterval = GetProcessingInterval(
                                               v92,
                                               *(HKEY *)(v84 + 40),
                                               *(_DWORD *)(v84 + 4),
                                               (unsigned int *)&uBytes);
                        if ( ProcessingInterval >= 0 )
                        {
                          if ( *(_DWORD *)&g_dwDebugLevel )
                          {
                            if ( g_lpDebugMsg )
                            {
                              g_lpDebugMsg(4u, L"GetProcessingIntervals() returned %d.", (unsigned int)uBytes / 0xEA60);
                            }
                            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                            {
                              RedirectDebugMsg(
                                4u,
                                L"GetProcessingIntervals() returned %d.",
                                (unsigned int)uBytes / 0xEA60);
                            }
                          }
                          PolicyTask = CreatePolicyTask(v92, (unsigned int)uBytes / 0xEA60);
                          if ( PolicyTask >= 0 )
                          {
                            if ( *(_DWORD *)&g_dwDebugLevel )
                            {
                              if ( g_lpDebugMsg )
                              {
                                g_lpDebugMsg(4u, L"CreatePolicyTask succeeded.");
                              }
                              else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                              {
                                RedirectDebugMsg(4u, L"CreatePolicyTask succeeded.");
                              }
                            }
                          }
                          else if ( *(_DWORD *)&g_dwDebugLevel )
                          {
                            if ( g_lpDebugMsg )
                            {
                              g_lpDebugMsg(4u, L"CreatePolicyTask failed with 0x%x.", (unsigned int)PolicyTask);
                            }
                            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                            {
                              RedirectDebugMsg(4u, L"CreatePolicyTask failed with 0x%x.", (unsigned int)PolicyTask);
                            }
                          }
                        }
                        else if ( *(_DWORD *)&g_dwDebugLevel )
                        {
                          if ( g_lpDebugMsg )
                          {
                            g_lpDebugMsg(
                              4u,
                              L"GetProcessingIntervals failed with 0x%x: Using the default values.",
                              (unsigned int)ProcessingInterval);
                          }
                          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                          {
                            RedirectDebugMsg(
                              4u,
                              L"GetProcessingIntervals failed with 0x%x: Using the default values.",
                              (unsigned int)ProcessingInterval);
                          }
                        }
                      }
                    }
                  }
                }
                else if ( *(_DWORD *)&g_dwDebugLevel )
                {
                  if ( g_lpDebugMsg )
                  {
                    g_lpDebugMsg(4u, L"No tasks created. Background policy processing is disabled by policy.");
                  }
                  else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                  {
                    RedirectDebugMsg(4u, L"No tasks created. Background policy processing is disabled by policy.");
                  }
                }
LABEL_88:
                if ( !LastError )
                  goto LABEL_70;
LABEL_89:
                TickCount = v91;
                goto LABEL_90;
              }
              goto LABEL_113;
            }
            v60 = (struct _QUERY_SERVICE_CONFIGW *)LocalAlloc(0x40u, (unsigned int)uBytes);
            v61 = v60;
            if ( v60 )
            {
              if ( QueryServiceConfigW(v59, v60, uBytes, (LPDWORD)&uBytes) )
                goto LABEL_105;
              if ( GetLastError() == 122 )
              {
                LocalFree(v61);
                v77 = (struct _QUERY_SERVICE_CONFIGW *)LocalAlloc(0x40u, (unsigned int)uBytes);
                v61 = v77;
                if ( !v77 )
                  goto LABEL_107;
                if ( QueryServiceConfigW(v59, v77, uBytes, (LPDWORD)&uBytes) )
                {
LABEL_105:
                  if ( v61->dwStartType == 2 )
                  {
                    LODWORD(v97) = GetTickCount();
                    while ( GetTickCount() - (unsigned int)v97 <= 0x1D4C0 && QueryServiceStatus(v59, &hMem) )
                    {
                      if ( hMem.dwCurrentState == 1 )
                      {
                        if ( hMem.dwWin32ExitCode != 1077 )
                          break;
                      }
                      else if ( hMem.dwCurrentState - 4 <= 3 )
                      {
                        pcbData = 1;
                        break;
                      }
                      Sleep(0x32u);
                    }
                    v58 = (SC_HANDLE)hHandle;
                  }
                }
              }
              LocalFree(v61);
            }
LABEL_107:
            CloseServiceHandle(v59);
            goto LABEL_108;
          }
          v74 = v97;
          if ( !v97
            || (LODWORD(uBytes) = 0,
                CGPApplicationService::GetTimeToWaitOnNetwork(
                  *((CGPApplicationService **)this + 42),
                  (unsigned int *)&uBytes)) )
          {
LABEL_44:
            v33 = 0;
            goto LABEL_45;
          }
          v75 = uBytes;
          v76 = g_lpDebugMsg;
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(
                4u,
                L"UserPolicy: Waiting for machine policy wait for network event with timeout %d ms",
                (unsigned int)uBytes);
            }
            else
            {
              if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
                goto LABEL_236;
              RedirectDebugMsg(
                4u,
                L"UserPolicy: Waiting for machine policy wait for network event with timeout %d ms",
                (unsigned int)uBytes);
            }
            v76 = g_lpDebugMsg;
          }
LABEL_236:
          if ( v75 )
          {
            if ( *(_DWORD *)&g_dwDebugLevel )
            {
              if ( v76 )
              {
                v76(
                  4u,
                  L"CGroupPolicySession::WaitForMachinePolicyEventsToBeSignaled (foreground): Beginning WaitForSingleObject.");
              }
              else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              {
                RedirectDebugMsg(
                  4u,
                  L"CGroupPolicySession::WaitForMachinePolicyEventsToBeSignaled (foreground): Beginning WaitForSingleObject.");
              }
            }
            WaitForSingleObjectEx(v74, v75, 0);
            if ( *(_DWORD *)&g_dwDebugLevel )
            {
              if ( g_lpDebugMsg )
              {
                g_lpDebugMsg(
                  4u,
                  L"CGroupPolicySession::WaitForMachinePolicyEventsToBeSignaled (foreground): Completed WaitForSingleObject.");
              }
              else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              {
                RedirectDebugMsg(
                  4u,
                  L"CGroupPolicySession::WaitForMachinePolicyEventsToBeSignaled (foreground): Completed WaitForSingleObject.");
              }
            }
          }
          v31 = v90;
          goto LABEL_44;
        }
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(4u, L" CGroupPolicySession::ApplyGroupPolicyForPrincipal setting GP_BACKGROUND_REFRESH flag");
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(
              4u,
              L" CGroupPolicySession::ApplyGroupPolicyForPrincipal setting GP_BACKGROUND_REFRESH flag");
          }
        }
        v16 |= 2u;
        goto LABEL_21;
      }
LABEL_175:
      LastError = 1008;
      goto LABEL_89;
    }
  }
LABEL_90:
  SetThreadExecutionState(0x80000000);
  if ( LastError )
  {
    v87 = (void *)*((_QWORD *)this + 37);
    if ( v87 )
      SetEvent(v87);
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"Setting m_hApplyGroupPolicyCompletedEvent via ERROR.");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"Setting m_hApplyGroupPolicyCompletedEvent via ERROR.");
      }
    }
    SetEvent(*((HANDLE *)this + 36));
    *(_QWORD *)&hMem.dwServiceType = 0;
    *(_QWORD *)&hMem.dwControlsAccepted = 0;
    pcbData = GetTickCount() - TickCount;
    LODWORD(v97) = v92;
    v93 = LastError;
    COperationalBaseEvent::AddArg((COperationalBaseEvent *)&hMem, (unsigned int *)&v97);
    COperationalBaseEvent::AddArg((COperationalBaseEvent *)&hMem, &v93);
    COperationalBaseEvent::AddArg((COperationalBaseEvent *)&hMem, &pcbData);
    COperationalBaseEvent::ReportOperationalEvent((COperationalBaseEvent *)&hMem, &gpEvent_GP_SESSION_END_ERROR);
    if ( *(_QWORD *)&hMem.dwServiceType )
      LocalFree(*(HLOCAL *)&hMem.dwServiceType);
  }
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"CGroupPolicySession::ApplyGroupPolicyForPrincipal::-- (Status: %ld)", LastError);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"CGroupPolicySession::ApplyGroupPolicyForPrincipal::-- (Status: %ld)", LastError);
    }
  }
  if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v7);
  return LastError;
}

```

## disassembly

```asm
0x180012540  push    rbp
0x180012542  push    rbx
0x180012543  push    rsi
0x180012544  push    rdi
0x180012545  push    r12
0x180012547  push    r13
0x180012549  push    r14
0x18001254b  push    r15
0x18001254d  lea     rbp, [rsp-138h]
0x180012555  sub     rsp, 238h
0x18001255c  mov     rax, cs:__security_cookie
0x180012563  xor     rax, rsp
0x180012566  mov     [rbp+170h+var_50], rax
0x18001256d  mov     [rbp+170h+var_1E0], r9
0x180012571  mov     [rbp+170h+var_1C8], r8
0x180012575  mov     [rbp+170h+hHandle], rdx
0x180012579  mov     rsi, rcx
0x18001257c  mov     r14d, [rbp+170h+arg_28]
0x180012583  mov     r15d, [rbp+170h+arg_20]
0x18001258a  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x180012591  jnz     loc_180013223
0x180012597  xor     edi, edi
0x180012599  mov     [rbp+170h+TokenHandle], rdi
0x18001259d  mov     [rsp+270h+var_210], edi
0x1800125a1  mov     dword ptr [rsp+270h+uBytes], edi
0x1800125a5  mov     ebx, edi
0x1800125a7  mov     [rbp+170h+var_1D0], rbx
0x1800125ab  mov     [rbp+170h+Buffer], rdi
0x1800125af  call    cs:__imp_GetTickCount
0x1800125b5  mov     r12d, eax
0x1800125b8  mov     [rsp+270h+var_20C], eax
0x1800125bc  mov     ecx, 80000001h; esFlags
0x1800125c1  call    cs:__imp_SetThreadExecutionState
0x1800125c7  mov     [rsp+270h+var_218], edi
0x1800125cb  lea     r13, [rsi+0B8h]
0x1800125d2  mov     rcx, [r13+0]
0x1800125d6  mov     rax, [rcx+10h]
0x1800125da  lea     rdx, [rsp+270h+var_218]
0x1800125df  mov     rcx, r13
0x1800125e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125e7  mov     edi, eax
0x1800125e9  test    eax, eax
0x1800125eb  jnz     loc_180012CB3
0x1800125f1  lea     r8, [rsp+270h+uBytes]; int *
0x1800125f6  lea     rdx, [rsp+270h+var_210]; int *
0x1800125fb  cmp     [rsp+270h+var_218], eax
0x1800125ff  jnz     loc_180012F58
0x180012605  mov     rcx, rsi; this
0x180012608  call    ?GetUserAccountInfo@CGroupPolicySession@@AEAAKPEAH0@Z; CGroupPolicySession::GetUserAccountInfo(int *,int *)
0x18001260d  mov     edi, eax
0x18001260f  test    eax, eax
0x180012611  jnz     loc_180012CB3
0x180012617  mov     r12d, [rsp+270h+var_210]
0x18001261c  mov     [rsi+1B8h], r12d
0x180012623  mov     [rsp+270h+var_208], eax
0x180012627  mov     rax, [r13+0]
0x18001262b  lea     rdx, [rsp+270h+var_208]
0x180012630  mov     rcx, r13
0x180012633  mov     rax, [rax+10h]
0x180012637  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001263c  mov     edi, eax
0x18001263e  test    eax, eax
0x180012640  jnz     loc_180012CAE
0x180012646  cmp     [rsp+270h+var_208], eax
0x18001264a  jnz     loc_180013110
0x180012650  mov     rax, [r13+0]
0x180012654  lea     rdx, [rbp+170h+TokenHandle]
0x180012658  mov     rcx, r13
0x18001265b  mov     rax, [rax+8]
0x18001265f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012664  test    eax, eax
0x180012666  jnz     loc_180013294
0x18001266c  mov     rax, [rbp+170h+TokenHandle]
0x180012670  test    rax, rax
0x180012673  jz      loc_18001329C
0x180012679  xor     edi, edi
0x18001267b  mov     eax, edi
0x18001267d  mov     ecx, 1
0x180012682  cmp     [rsp+270h+var_208], edi
0x180012686  cmovnz  eax, ecx
0x180012689  mov     ecx, eax
0x18001268b  or      ecx, 10h
0x18001268e  test    r15d, r15d
0x180012691  cmovz   ecx, eax; this
0x180012694  mov     r15d, ecx
0x180012697  or      r15d, 20h
0x18001269b  test    r14d, r14d
0x18001269e  cmovz   r15d, ecx
0x1800126a2  mov     eax, [rsi+18Ch]
0x1800126a8  cmp     eax, 1
0x1800126ab  jz      loc_1800132A6
0x1800126b1  cmp     eax, 2
0x1800126b4  jnz     short loc_1800126BB
0x1800126b6  bts     r15d, 15h
0x1800126bb  test    r12d, r12d
0x1800126be  jz      loc_1800132AF
0x1800126c4  call    ?IsBackgroundPolicyEnabledForWorkgroups@CGroupPolicySession@@AEAAHXZ; CGroupPolicySession::IsBackgroundPolicyEnabledForWorkgroups(void)
0x1800126c9  test    eax, eax
0x1800126cb  jnz     loc_1800132BC
0x1800126d1  cmp     cs:?g_dwDebugLevel@@3KA, edi; ulong g_dwDebugLevel
0x1800126d7  jnz     loc_18001330F
0x1800126dd  mov     [rbp+170h+hMem], rdi
0x1800126e4  mov     [rbp+170h+hMem+8], rdi
0x1800126eb  mov     ecx, [rsi+18Ch]
0x1800126f1  mov     eax, edi
0x1800126f3  cmp     ecx, 2
0x1800126f6  setz    al
0x1800126f9  mov     [rsp+270h+var_1F8], eax
0x1800126fd  mov     eax, edi
0x1800126ff  cmp     ecx, 1
0x180012702  setz    al
0x180012705  mov     [rsp+270h+var_218], eax
0x180012709  mov     eax, [rsp+270h+var_208]
0x18001270d  mov     [rsp+270h+var_200], eax
0x180012711  lea     rcx, [rbp+170h+hMem]; this
0x180012718  call    ?VerifyAndAllocateEventDataDescriptorStorage@COperationalBaseEvent@@AEAAKXZ; COperationalBaseEvent::VerifyAndAllocateEventDataDescriptorStorage(void)
0x18001271d  test    eax, eax
0x18001271f  jnz     short loc_18001274D
0x180012721  mov     edx, dword ptr [rbp+170h+hMem+0Ch]
0x180012727  mov     ecx, edx
0x180012729  add     rcx, rcx
0x18001272c  mov     rax, [rbp+170h+hMem]
0x180012733  lea     r8, [rsp+270h+var_200]
0x180012738  mov     [rax+rcx*8], r8
0x18001273c  mov     qword ptr [rax+rcx*8+8], 4
0x180012745  inc     edx
0x180012747  mov     dword ptr [rbp+170h+hMem+0Ch], edx
0x18001274d  lea     rcx, [rbp+170h+hMem]; this
0x180012754  call    ?VerifyAndAllocateEventDataDescriptorStorage@COperationalBaseEvent@@AEAAKXZ; COperationalBaseEvent::VerifyAndAllocateEventDataDescriptorStorage(void)
0x180012759  test    eax, eax
0x18001275b  jnz     short loc_180012789
0x18001275d  mov     edx, dword ptr [rbp+170h+hMem+0Ch]
0x180012763  mov     ecx, edx
0x180012765  add     rcx, rcx
0x180012768  mov     rax, [rbp+170h+hMem]
0x18001276f  lea     r8, [rsp+270h+var_1F8]
0x180012774  mov     [rax+rcx*8], r8
0x180012778  mov     qword ptr [rax+rcx*8+8], 4
0x180012781  inc     edx
0x180012783  mov     dword ptr [rbp+170h+hMem+0Ch], edx
0x180012789  lea     rcx, [rbp+170h+hMem]; this
0x180012790  call    ?VerifyAndAllocateEventDataDescriptorStorage@COperationalBaseEvent@@AEAAKXZ; COperationalBaseEvent::VerifyAndAllocateEventDataDescriptorStorage(void)
0x180012795  mov     r14, [rbp+170h+hMem]
0x18001279c  test    eax, eax
0x18001279e  jnz     loc_180013361
0x1800127a4  mov     edi, dword ptr [rbp+170h+hMem+0Ch]
0x1800127aa  mov     eax, edi
0x1800127ac  add     rax, rax
0x1800127af  lea     rcx, [rsp+270h+var_218]
0x1800127b4  mov     [r14+rax*8], rcx
0x1800127b8  mov     qword ptr [r14+rax*8+8], 4
0x1800127c1  inc     edi
0x1800127c3  mov     dword ptr [rbp+170h+hMem+0Ch], edi
0x1800127c9  mov     r12, cs:?s_pEventProviderHandle@CGPServiceEventReporting@@0_KA; unsigned __int64 CGPServiceEventReporting::s_pEventProviderHandle
0x1800127d0  mov     ecx, cs:_tls_index
0x1800127d6  mov     rax, gs:58h
0x1800127df  mov     rax, [rax+rcx*8]
0x1800127e3  mov     [rbp+170h+var_1C0], rax
0x1800127e7  mov     ecx, 8
0x1800127ec  mov     edx, 10h
0x1800127f1  cmp     byte ptr [rcx+rax], 1
0x1800127f5  jz      loc_180012F09
0x1800127fb  mov     r9, r14
0x1800127fe  mov     r8d, edi
0x180012801  lea     rdx, gpEvent_GP_SESSION_START
0x180012808  mov     rcx, r12
0x18001280b  call    cs:__imp_EtwEventWrite
0x180012811  test    eax, eax
0x180012813  jnz     loc_1800133A1
0x180012819  test    r14, r14
0x18001281c  jz      short loc_180012827
0x18001281e  mov     rcx, r14; hMem
0x180012821  call    cs:__imp_LocalFree
0x180012827  mov     edi, [rsp+270h+var_210]
0x18001282b  test    edi, edi
0x18001282d  jz      loc_1800133AC
0x180012833  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x18001283a  jnz     loc_180013419
0x180012840  xor     edx, edx; Val
0x180012842  mov     r8d, 140h; Size
0x180012848  lea     rcx, [rbp+170h+var_1B0]; void *
0x18001284c  call    memset_0
0x180012851  mov     [rbp+170h+var_1B0], r15d
0x180012855  mov     rax, [rbp+170h+TokenHandle]
0x180012859  mov     [rbp+170h+var_1A8], rax
0x18001285d  lea     rcx, [rbp+170h+var_1B0]; struct _GPOINFO *
0x180012861  call    ?CanStartFromLocalDataStore@@YAHPEAU_GPOINFO@@@Z; CanStartFromLocalDataStore(_GPOINFO *)
0x180012866  mov     rcx, [rbp+170h+SourceString]; SourceString
0x18001286a  test    rcx, rcx
0x18001286d  jnz     loc_180013075
0x180012873  mov     r14, [rbp+170h+hHandle]
0x180012877  test    r14, r14
0x18001287a  jnz     loc_180012D0B
0x180012880  cmp     qword ptr [rsi+148h], 0
0x180012888  jz      loc_180012E2C
0x18001288e  xor     r12d, r12d
0x180012891  mov     dword ptr [rsp+270h+uBytes], r12d
0x180012896  lea     rcx, [rsp+270h+uBytes]
0x18001289b  call    cs:__imp_GetOsSafeBootMode
0x1800128a1  cmp     dword ptr [rsp+270h+uBytes], 3
0x1800128a6  jz      loc_180013580
0x1800128ac  mov     r14d, r12d
0x1800128af  mov     [rsp+270h+var_218], r12d
0x1800128b4  mov     [rsp+270h+var_200], r12d
0x1800128b9  cmp     [rsp+270h+var_208], r12d
0x1800128be  jnz     short loc_1800128FA
0x1800128c0  cmp     [rsi+194h], r12d
0x1800128c7  jnz     short loc_1800128FA
0x1800128c9  cmp     [rsi+18Ch], r12d
0x1800128d0  jz      loc_18001359F
0x1800128d6  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800128dd  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800128e4  jnz     loc_1800136D8
0x1800128ea  mov     r14, [rbp+170h+var_1C8]
0x1800128ee  test    r14, r14
0x1800128f1  jnz     loc_180013733
0x1800128f7  mov     r14d, r12d
0x1800128fa  mov     dword ptr [rsp+270h+uBytes], r12d
0x1800128ff  mov     [rsp+270h+var_1F8], 4
0x180012907  lea     rax, [rsp+270h+var_1F8]
0x18001290c  mov     [rsp+270h+pcbData], rax; pcbData
0x180012911  lea     rax, [rsp+270h+uBytes]
0x180012916  mov     [rsp+270h+pvData], rax; pvData
0x18001291b  mov     [rsp+270h+pdwType], r12; pdwType
0x180012920  mov     r9d, 10h; dwFlags
0x180012926  lea     r8, Value; "DisableAOACProcessing"
0x18001292d  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x180012934  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001293b  call    cs:__imp_RegGetValueW
0x180012941  cmp     dword ptr [rsp+270h+uBytes], r12d
0x180012946  jnz     loc_18001300F
0x18001294c  mov     dword ptr [rsp+270h+uBytes], 258h
0x180012954  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x18001295b  jnz     loc_1800137E7
0x180012961  lea     r8, [rbp+170h+Buffer]; Buffer
0x180012965  mov     edx, 1; InfoLevel
0x18001296a  xor     ecx, ecx; lpServer
0x18001296c  call    cs:__imp_DsRoleGetPrimaryDomainInformation
0x180012972  mov     r8d, eax
0x180012975  test    eax, eax
0x180012977  jz      loc_180012F8A
0x18001297d  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180012984  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x18001298b  jnz     loc_18001389D
0x180012991  cmp     [rsp+270h+var_208], r12d
0x180012996  jnz     loc_180012D45
0x18001299c  mov     r14, r12
0x18001299f  mov     [rsp+270h+var_200], r12d
0x1800129a4  mov     rax, [r13+0]
0x1800129a8  lea     rdx, [rsp+270h+var_200]
0x1800129ad  mov     rcx, r13
0x1800129b0  mov     rax, [rax+10h]
0x1800129b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800129b9  mov     edi, eax
0x1800129bb  test    eax, eax
0x1800129bd  jnz     short loc_180012A32
0x1800129bf  cmp     [rsp+270h+var_200], eax
0x1800129c3  jz      short loc_1800129CE
0x1800129c5  mov     r14, 0FFFFFFFF80000002h
0x1800129cc  jmp     short loc_180012A3A
0x1800129ce  mov     rax, [rsi+0A8h]
0x1800129d5  test    rax, rax
0x1800129d8  jnz     loc_180013ACA
0x1800129de  mov     [rbp+170h+hHandle], rax
0x1800129e2  mov     rax, [r13+0]
0x1800129e6  lea     rdx, [rbp+170h+hHandle]
0x1800129ea  mov     rcx, r13
0x1800129ed  mov     rax, [rax+20h]
0x1800129f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800129f6  mov     edi, eax
0x1800129f8  test    eax, eax
0x1800129fa  jnz     short loc_180012A2F
0x1800129fc  lea     rdx, [rsi+0A8h]; phkResult
0x180012a03  mov     ecx, 2001Fh; samDesired
0x180012a08  call    cs:__imp_RegOpenCurrentUser
0x180012a0e  mov     edi, eax
0x180012a10  test    eax, eax
0x180012a12  jnz     short loc_180012A1B
0x180012a14  mov     r14, [rsi+0A8h]
0x180012a1b  mov     rax, [r13+0]
0x180012a1f  lea     rdx, [rbp+170h+hHandle]
0x180012a23  mov     rcx, r13
0x180012a26  mov     rax, [rax+28h]
0x180012a2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a2f  xor     r12d, r12d
0x180012a32  test    edi, edi
0x180012a34  jnz     loc_180012CAE
0x180012a3a  mov     edi, r12d
0x180012a3d  xor     r9d, r9d; lpName
0x180012a40  xor     r8d, r8d; bInitialState
0x180012a43  mov     edx, 1; bManualReset
0x180012a48  xor     ecx, ecx; lpEventAttributes
0x180012a4a  call    cs:__imp_CreateEventW
0x180012a50  mov     [rsi+0B0h], rax
0x180012a57  test    rax, rax
0x180012a5a  jz      loc_180013AD5
0x180012a60  test    edi, edi
0x180012a62  jnz     loc_180012B4D
0x180012a68  test    r14, r14
0x180012a6b  jz      loc_180012B4D
  ... truncated ...
```
