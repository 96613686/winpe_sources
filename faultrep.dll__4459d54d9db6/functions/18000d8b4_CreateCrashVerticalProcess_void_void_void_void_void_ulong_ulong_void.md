# CreateCrashVerticalProcess(void *,void *,void *,void *,void * *,ulong,ulong,void * *)

- ea: `0x18000d8b4`
- end: `0x18000e2cb`
- name: `?CreateCrashVerticalProcess@@YAJPEAX000PEAPEAXKK1@Z`
- size: `2583`
- prototype: `__int64 __fastcall(HANDLE Process, void *, void *, void *, void **, unsigned int, char, void **)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000e7c0`

## callees

- `0x180002890`
- `0x180003474`
- `0x180009ed8`
- `0x180009f00`
- `0x18000d864`
- `0x18000d8b4`
- `0x18000e71c`
- `0x180038d54`
- `0x18003b45c`
- `0x18003bb10`
- `0x18003e5a8`
- `0x1800419b8`
- `0x180042504`
- `0x1800492ec`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18000d99b`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18000d99b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000dc50`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000de1d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000df5b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000e061`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000e105`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000dc50`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000de1d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000df5b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000e061`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000e105`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000d9da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000d9da`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000d9eb`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000da60`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000d9eb`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000da60`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18000e018`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18000e018`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18000de80`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18000df8b`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18000e1a5`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18000de80`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18000df8b`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18000e1a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d9f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000da6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000daff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dbb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000df1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e022`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e0ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e17c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d9f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000da6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000daff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dbb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000df1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e022`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e0ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e17c`
- `ntdll!DbgPrintEx` at `0x18000dc73`
- `ntdll!DbgPrintEx` at `0x18000de40`
- `ntdll!DbgPrintEx` at `0x18000df7e`
- `ntdll!DbgPrintEx` at `0x18000e147`
- `ntdll!DbgPrintEx` at `0x18000dc73`
- `ntdll!DbgPrintEx` at `0x18000de40`
- `ntdll!DbgPrintEx` at `0x18000df7e`
- `ntdll!DbgPrintEx` at `0x18000e147`
- `ntdll!NtClose` at `0x18000e1d2`
- `ntdll!NtClose` at `0x18000e1d2`
- `KERNELBASE!CreateProcessAsUserW` at `0x18000df0e`
- `KERNELBASE!CreateProcessAsUserW` at `0x18000e0e1`
- `KERNELBASE!CreateProcessAsUserW` at `0x18000df0e`
- `KERNELBASE!CreateProcessAsUserW` at `0x18000e0e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e268`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800496c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e268`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800496c0`
- `api-ms-win-security-base-l1-1-0!AdjustTokenGroups` at `0x18000daf5`
- `api-ms-win-security-base-l1-1-0!AdjustTokenGroups` at `0x18000daf5`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000dbac`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000dbac`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000e198`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000e214`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180049675`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000e198`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000e214`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180049675`
- `api-ms-win-core-errorhandling-l1-1-3!SetThreadErrorMode` at `0x18000de94`
- `api-ms-win-core-errorhandling-l1-1-3!SetThreadErrorMode` at `0x18000df97`
- `api-ms-win-core-errorhandling-l1-1-3!SetThreadErrorMode` at `0x18000e1b1`
- `api-ms-win-core-errorhandling-l1-1-3!SetThreadErrorMode` at `0x18000de94`
- `api-ms-win-core-errorhandling-l1-1-3!SetThreadErrorMode` at `0x18000df97`
- `api-ms-win-core-errorhandling-l1-1-3!SetThreadErrorMode` at `0x18000e1b1`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18000e232`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180049690`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18000e232`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180049690`
- `USERENV!DestroyEnvironmentBlock` at `0x18000e242`
- `USERENV!DestroyEnvironmentBlock` at `0x1800496a0`
- `USERENV!DestroyEnvironmentBlock` at `0x18000e242`
- `USERENV!DestroyEnvironmentBlock` at `0x1800496a0`
- `USERENV!CreateEnvironmentBlock` at `0x18000db6b`
- `USERENV!CreateEnvironmentBlock` at `0x18000db6b`

## string_xrefs

- `0x18000dc65`: `WER/CrashExp/%u:%u: ERROR Failed to get the paths for the crash vertical. Error was 0x%x\n`
- `0x18000de32`: `WER/CrashExp/%u:%u: ERROR WerpBuildCreateProcessAttributeList failed: 0x%x\n`
- `0x18000df6d`: `WER/CrashExp/%u:%u: ERROR CreateProcess(SECURITY_DISABLED) failed with 0x%x\n`
- `0x18000e073`: `WER/CrashExp/%u:%u: ERROR CreateProcess(service/restricted) failed with 0x%x\n`
- `0x18000e139`: `WER/CrashExp/%u:%u: ERROR Failed to create the process "%S", cmdline "%S", creationflags %u, HRESULT %08X\n`

## pseudocode

```c
__int64 __fastcall CreateCrashVerticalProcess(
        HANDLE Process,
        void *a2,
        void *a3,
        void *a4,
        void **a5,
        unsigned int a6,
        char a7,
        void **a8)
{
  int v11; // r13d
  bool v12; // zf
  int v13; // r15d
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  int v18; // r12d
  signed int v20; // eax
  bool v21; // sf
  signed int v22; // eax
  bool v23; // sf
  int CrashVerticalPaths; // eax
  int v25; // edi
  DWORD CurrentProcessId; // eax
  int v27; // r15d
  HANDLE *p_ProcessHandle; // rdx
  int ProcessAttributeList; // eax
  signed int v30; // edi
  DWORD v31; // eax
  int v32; // r15d
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // r9
  void *v36; // rcx
  signed int v37; // eax
  unsigned int v38; // edi
  DWORD v39; // eax
  signed int v40; // eax
  unsigned int v41; // edi
  DWORD v42; // eax
  signed int v43; // eax
  DWORD v44; // eax
  int v45; // edx
  int v46; // r8d
  __int64 v47; // [rsp+0h] [rbp-3D8h] BYREF
  PTOKEN_GROUPS PreviousState; // [rsp+20h] [rbp-3B8h]
  PDWORD ReturnLength; // [rsp+28h] [rbp-3B0h]
  DWORD dwCreationFlags[2]; // [rsp+30h] [rbp-3A8h]
  LPCWSTR lpCurrentDirectory; // [rsp+40h] [rbp-398h]
  unsigned int v52; // [rsp+60h] [rbp-378h]
  unsigned __int16 v53[2]; // [rsp+64h] [rbp-374h] BYREF
  unsigned __int16 v54[2]; // [rsp+68h] [rbp-370h] BYREF
  DWORD OldMode; // [rsp+6Ch] [rbp-36Ch] BYREF
  void *TokenHandle; // [rsp+70h] [rbp-368h] BYREF
  LPVOID Environment; // [rsp+78h] [rbp-360h] BYREF
  int v58; // [rsp+80h] [rbp-358h]
  int v59; // [rsp+84h] [rbp-354h]
  UINT uMode[2]; // [rsp+88h] [rbp-350h]
  HANDLE Processa; // [rsp+90h] [rbp-348h] BYREF
  int v62; // [rsp+98h] [rbp-340h] BYREF
  HANDLE ProcessHandle; // [rsp+A0h] [rbp-338h] BYREF
  LPVOID lpAddress; // [rsp+A8h] [rbp-330h] BYREF
  int v65; // [rsp+B0h] [rbp-328h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+B8h] [rbp-320h] BYREF
  void **v67; // [rsp+D0h] [rbp-308h]
  void **v68; // [rsp+D8h] [rbp-300h]
  _BYTE StartupInfo[112]; // [rsp+E0h] [rbp-2F8h] BYREF
  __int64 *v70; // [rsp+150h] [rbp-288h]
  __int128 v71; // [rsp+158h] [rbp-280h] BYREF
  __int128 v72; // [rsp+168h] [rbp-270h]
  __int128 v73; // [rsp+178h] [rbp-260h]
  __int128 v74; // [rsp+188h] [rbp-250h]
  __int128 v75; // [rsp+198h] [rbp-240h]
  __int128 v76; // [rsp+1A8h] [rbp-230h]
  __int128 v77; // [rsp+1B8h] [rbp-220h]
  WCHAR ApplicationName[64]; // [rsp+1D0h] [rbp-208h] BYREF
  wchar_t v79[32]; // [rsp+250h] [rbp-188h] BYREF
  WCHAR CommandLine[128]; // [rsp+290h] [rbp-148h] BYREF
  unsigned int v81; // [rsp+410h] [rbp+38h]

  v70 = &v47;
  *(_QWORD *)uMode = a4;
  Processa = Process;
  ProcessHandle = a2;
  v67 = a5;
  v68 = a8;
  v11 = 0;
  TokenHandle = 0;
  Environment = 0;
  *(_QWORD *)StartupInfo = 0;
  memset_0(&StartupInfo[8], 0, 0x68u);
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  lpAddress = 0;
  OldMode = 0;
  v62 = 0;
  v65 = 2;
  if ( Process && a4 && a8 )
  {
    GetProcessId(Process);
    v79[0] = 0;
    ApplicationName[0] = 0;
    CommandLine[0] = 0;
    TokenHandle = a3;
    v12 = (a7 & 1) == 0;
    v13 = a7 & 1;
    v81 = v13;
    if ( v12 )
    {
      v18 = 0;
      v59 = 0;
      if ( a3 )
        goto LABEL_25;
      if ( !OpenProcessToken(ProcessHandle, 0xBu, &TokenHandle) )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        if ( LastError >= 0 )
          LastError = -2147467259;
        v52 = LastError;
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return v52;
        v17 = 12;
        goto LABEL_22;
      }
    }
    else
    {
      CurrentProcess = GetCurrentProcess();
      if ( !OpenProcessToken(CurrentProcess, 0xBu, &TokenHandle) )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        if ( LastError >= 0 )
          LastError = -2147467259;
        v52 = LastError;
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return v52;
        v17 = 11;
LABEL_22:
        WPP_SF_d(v16[2], v17, WPP_9c3b68551b0139bf402022d307f73d71_Traceguids, (unsigned int)LastError);
        return v52;
      }
    }
    v59 = 1;
    v18 = 1;
LABEL_25:
    v58 = 0;
    v52 = -2147467259;
    if ( !AdjustTokenGroups(TokenHandle, 1, 0, 0, 0, 0) )
    {
      v20 = GetLastError();
      v21 = v20 < 0;
      if ( v20 > 0 )
      {
        v20 = (unsigned __int16)v20 | 0x80070000;
        v21 = v20 < 0;
      }
      if ( !v21 )
        v20 = -2147467259;
      v52 = v20;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          WPP_9c3b68551b0139bf402022d307f73d71_Traceguids,
          (unsigned int)v20);
    }
    if ( !CreateEnvironmentBlock(&Environment, TokenHandle, 0) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_9c3b68551b0139bf402022d307f73d71_Traceguids);
      Environment = 0;
    }
    if ( !v13 )
    {
      if ( !ImpersonateLoggedOnUser(TokenHandle) )
      {
        v22 = GetLastError();
        v23 = v22 < 0;
        if ( v22 > 0 )
        {
          v22 = (unsigned __int16)v22 | 0x80070000;
          v23 = v22 < 0;
        }
        if ( !v23 )
          v22 = -2147467259;
        v52 = v22;
        goto LABEL_95;
      }
      v11 = 1;
      v58 = 1;
    }
    CrashVerticalPaths = GetCrashVerticalPaths(
                           Processa,
                           ProcessHandle,
                           *(void **)uMode,
                           ApplicationName,
                           (unsigned int)PreviousState,
                           CommandLine,
                           dwCreationFlags[0],
                           v79,
                           (unsigned int)lpCurrentDirectory);
    v25 = CrashVerticalPaths;
    v52 = CrashVerticalPaths;
    if ( CrashVerticalPaths < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          WPP_9c3b68551b0139bf402022d307f73d71_Traceguids,
          (unsigned int)CrashVerticalPaths);
      CurrentProcessId = GetCurrentProcessId();
      DbgPrintEx(
        0x96u,
        0,
        "WER/CrashExp/%u:%u: ERROR Failed to get the paths for the crash vertical. Error was 0x%x\n",
        CurrentProcessId,
        263,
        v25);
      goto LABEL_95;
    }
    memset_0(&v71, 0, 0x70u);
    *(_OWORD *)StartupInfo = v71;
    *(_QWORD *)&StartupInfo[24] = *((_QWORD *)&v72 + 1);
    *(_OWORD *)&StartupInfo[32] = v73;
    *(_OWORD *)&StartupInfo[48] = v74;
    *(_OWORD *)&StartupInfo[64] = v75;
    *(_OWORD *)&StartupInfo[80] = v76;
    *(_OWORD *)&StartupInfo[96] = v77;
    *(_DWORD *)StartupInfo = 112;
    *(_QWORD *)&StartupInfo[16] = &dword_18004FE4C;
    *(_DWORD *)&StartupInfo[60] = 1;
    *(_WORD *)&StartupInfo[64] = 0;
    v27 = UtilIsProtectedProcess(Processa) << 18;
    v62 = 4;
    v53[0] = 0;
    v54[0] = 0;
    WerpGetProcessArchitecture(Processa, v53, v54);
    if ( v54[0] != 0xAA64 || v53[0] != 0x8664 )
      v53[0] = 0;
    p_ProcessHandle = &ProcessHandle;
    if ( !ProcessHandle )
      p_ProcessHandle = &Processa;
    ProcessAttributeList = BuildCreateProcessAttributeList(
                             (unsigned int)&lpAddress,
                             (_DWORD)p_ProcessHandle,
                             (unsigned int)&v62,
                             (_DWORD)v67,
                             a6,
                             (__int64)&v65,
                             (__int64)v53);
    v30 = ProcessAttributeList;
    v52 = ProcessAttributeList;
    if ( ProcessAttributeList < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          WPP_9c3b68551b0139bf402022d307f73d71_Traceguids,
          (unsigned int)ProcessAttributeList);
      v31 = GetCurrentProcessId();
      DbgPrintEx(
        0x96u,
        0,
        "WER/CrashExp/%u:%u: ERROR WerpBuildCreateProcessAttributeList failed: 0x%x\n",
        v31,
        319,
        v30);
      local_unwind_0(v70, &loc_18000DABA);
    }
    *(_QWORD *)&StartupInfo[104] = lpAddress;
    v32 = (lpAddress != 0 ? 525312 : 1024) | v27;
    uMode[0] = SetErrorMode(1u);
    SetThreadErrorMode(1u, &OldMode);
    if ( v81 )
    {
      v36 = TokenHandle;
      if ( !TokenHandle )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs(0, v33, v34, v35);
        v36 = TokenHandle;
      }
      if ( !CreateProcessAsUserW(
              v36,
              ApplicationName,
              CommandLine,
              0,
              0,
              1,
              v32,
              Environment,
              0,
              (LPSTARTUPINFOW)StartupInfo,
              &ProcessInformation) )
      {
        v37 = GetLastError();
        v38 = v37;
        if ( v37 > 0 )
          v38 = (unsigned __int16)v37 | 0x80070000;
        v52 = v38;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_9c3b68551b0139bf402022d307f73d71_Traceguids, v38);
        v39 = GetCurrentProcessId();
        LODWORD(ReturnLength) = v38;
        LODWORD(PreviousState) = 350;
        DbgPrintEx(
          0x96u,
          0,
          "WER/CrashExp/%u:%u: ERROR CreateProcess(SECURITY_DISABLED) failed with 0x%x\n",
          v39,
          PreviousState,
          ReturnLength);
LABEL_71:
        SetErrorMode(uMode[0]);
        SetThreadErrorMode(OldMode, 0);
LABEL_95:
        if ( v11 )
          RevertToSelf();
        if ( lpAddress )
          VirtualFree(lpAddress, 0, 0x8000u);
        if ( Environment )
        {
          DestroyEnvironmentBlock(Environment);
          Environment = 0;
        }
        if ( TokenHandle && v18 )
          CloseHandle(TokenHandle);
        return v52;
      }
    }
    else
    {
      if ( (unsigned int)UtilIsProcessAService(Processa) || !UtilIsWriteRestrictedProcess(Processa) )
      {
        if ( !CreateProcessAsUserW(
                TokenHandle,
                ApplicationName,
                CommandLine,
                0,
                0,
                1,
                v32,
                Environment,
                0,
                (LPSTARTUPINFOW)StartupInfo,
                &ProcessInformation) )
        {
          v43 = GetLastError();
          v30 = v43;
          if ( v43 > 0 )
            v30 = (unsigned __int16)v43 | 0x80070000;
          v52 = v30;
          v44 = GetCurrentProcessId();
          DbgPrintEx(
            0x96u,
            0,
            "WER/CrashExp/%u:%u: ERROR Failed to create the process \"%S\", cmdline \"%S\", creationflags %u, HRESULT %08X\n",
            v44,
            401,
            ApplicationName,
            CommandLine,
            v32,
            v30);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_DSD(*((_QWORD *)WPP_GLOBAL_Control + 2), v45, v46, v30, (__int64)CommandLine, v32);
          if ( GetLastError() != 1346 )
            goto LABEL_71;
          v11 = 0;
          v58 = 0;
          RevertToSelf();
        }
LABEL_90:
        SetErrorMode(uMode[0]);
        SetThreadErrorMode(OldMode, 0);
        *v68 = ProcessInformation.hProcess;
        NtClose(ProcessInformation.hThread);
        if ( v30 >= 0 )
        {
          v52 = 0;
        }
        else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            20,
            WPP_9c3b68551b0139bf402022d307f73d71_Traceguids,
            (unsigned int)v30);
        }
        goto LABEL_95;
      }
      if ( !CreateProcessW(
              ApplicationName,
              CommandLine,
              0,
              0,
              1,
              v32,
              Environment,
              0,
              (LPSTARTUPINFOW)StartupInfo,
              &ProcessInformation) )
      {
        v40 = GetLastError();
        v41 = v40;
        if ( v40 > 0 )
          v41 = (unsigned __int16)v40 | 0x80070000;
        v52 = v41;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_9c3b68551b0139bf402022d307f73d71_Traceguids, v41);
        v42 = GetCurrentProcessId();
        LODWORD(ReturnLength) = v41;
        LODWORD(PreviousState) = 377;
        DbgPrintEx(
          0x96u,
          0,
          "WER/CrashExp/%u:%u: ERROR CreateProcess(service/restricted) failed with 0x%x\n",
          v42,
          PreviousState,
          ReturnLength);
        goto LABEL_71;
      }
    }
    v30 = 0;
    v52 = 0;
    goto LABEL_90;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_9c3b68551b0139bf402022d307f73d71_Traceguids);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18000d8b4  mov     r11, rsp
0x18000d8b7  push    rbx
0x18000d8b8  push    rsi
0x18000d8b9  push    rdi
0x18000d8ba  push    r12
0x18000d8bc  push    r13
0x18000d8be  push    r14
0x18000d8c0  push    r15
0x18000d8c2  sub     rsp, 3A0h
0x18000d8c9  mov     rax, cs:__security_cookie
0x18000d8d0  xor     rax, rsp
0x18000d8d3  mov     [rsp+3D8h+var_48], rax
0x18000d8db  mov     [rsp+3D8h+var_288], rsp
0x18000d8e3  mov     rsi, r9
0x18000d8e6  mov     qword ptr [rsp+3D8h+uMode], r9
0x18000d8ee  mov     rdi, r8
0x18000d8f1  mov     rbx, rcx
0x18000d8f4  mov     [r11-348h], rcx
0x18000d8fb  mov     [r11-338h], rdx
0x18000d902  mov     rax, [rsp+3D8h+arg_20]
0x18000d90a  mov     [rsp+3D8h+var_308], rax
0x18000d912  mov     r14, [rsp+3D8h+arg_38]
0x18000d91a  mov     [rsp+3D8h+var_300], r14
0x18000d922  xor     r13d, r13d
0x18000d925  mov     [rsp+3D8h+TokenHandle], r13
0x18000d92a  mov     [rsp+3D8h+Environment], r13
0x18000d92f  mov     [r11-2F8h], r13
0x18000d936  xor     edx, edx; Val
0x18000d938  lea     r8d, [r13+68h]; Size
0x18000d93c  lea     rcx, [r11-2F0h]; void *
0x18000d943  call    memset_0
0x18000d948  xorps   xmm0, xmm0
0x18000d94b  xor     eax, eax
0x18000d94d  movups  xmmword ptr [rsp+3D8h+ProcessInformation.hProcess], xmm0
0x18000d955  mov     qword ptr [rsp+3D8h+ProcessInformation.dwProcessId], rax
0x18000d95d  mov     [rsp+3D8h+lpAddress], r13
0x18000d965  mov     [rsp+3D8h+OldMode], r13d
0x18000d96a  mov     [rsp+3D8h+var_340], r13d
0x18000d972  mov     [rsp+3D8h+var_328], 2
0x18000d97d  test    rbx, rbx
0x18000d980  jz      loc_18000E273
0x18000d986  test    rsi, rsi
0x18000d989  jz      loc_18000E273
0x18000d98f  test    r14, r14
0x18000d992  jz      loc_18000E273
0x18000d998  mov     rcx, rbx; Process
0x18000d99b  call    cs:__imp_GetProcessId
0x18000d9a1  mov     [rsp+3D8h+var_188], r13w
0x18000d9aa  mov     [rsp+3D8h+ApplicationName], r13w
0x18000d9b3  mov     [rsp+3D8h+CommandLine], r13w
0x18000d9bc  mov     [rsp+3D8h+TokenHandle], rdi
0x18000d9c1  lea     ebx, [r13+1]
0x18000d9c5  mov     r15d, [rsp+3D8h+arg_30]
0x18000d9cd  and     r15d, ebx
0x18000d9d0  mov     [rsp+3D8h+arg_30], r15d
0x18000d9d8  jz      short loc_18000DA40
0x18000d9da  call    cs:__imp_GetCurrentProcess
0x18000d9e0  mov     rcx, rax; ProcessHandle
0x18000d9e3  lea     r8, [rsp+3D8h+TokenHandle]; TokenHandle
0x18000d9e8  lea     edx, [rbx+0Ah]; DesiredAccess
0x18000d9eb  call    cs:__imp_OpenProcessToken
0x18000d9f1  test    eax, eax
0x18000d9f3  jnz     loc_18000DAC3
0x18000d9f9  call    cs:__imp_GetLastError
0x18000d9ff  test    eax, eax
0x18000da01  jle     short loc_18000DA0B
0x18000da03  movzx   eax, ax
0x18000da06  or      eax, 80070000h
0x18000da0b  mov     edi, 80004005h
0x18000da10  test    eax, eax
0x18000da12  cmovns  eax, edi
0x18000da15  mov     [rsp+3D8h+var_378], eax
0x18000da19  lea     rsi, WPP_GLOBAL_Control
0x18000da20  mov     rcx, cs:WPP_GLOBAL_Control
0x18000da27  cmp     rcx, rsi
0x18000da2a  jz      loc_18000DABA
0x18000da30  test    [rcx+1Ch], bl
0x18000da33  jz      loc_18000DABA
0x18000da39  mov     edx, 0Bh
0x18000da3e  jmp     short loc_18000DAA7
0x18000da40  mov     r12d, r13d
0x18000da43  mov     [rsp+3D8h+var_354], r13d
0x18000da4b  test    rdi, rdi
0x18000da4e  jnz     short loc_18000DACD
0x18000da50  lea     r8, [rsp+3D8h+TokenHandle]; TokenHandle
0x18000da55  lea     edx, [rdi+0Bh]; DesiredAccess
0x18000da58  mov     rcx, [rsp+3D8h+ProcessHandle]; ProcessHandle
0x18000da60  call    cs:__imp_OpenProcessToken
0x18000da66  test    eax, eax
0x18000da68  jnz     short loc_18000DAC3
0x18000da6a  call    cs:__imp_GetLastError
0x18000da70  test    eax, eax
0x18000da72  jle     short loc_18000DA7C
0x18000da74  movzx   eax, ax
0x18000da77  or      eax, 80070000h
0x18000da7c  mov     edi, 80004005h
0x18000da81  test    eax, eax
0x18000da83  cmovns  eax, edi
0x18000da86  mov     [rsp+3D8h+var_378], eax
0x18000da8a  lea     rsi, WPP_GLOBAL_Control
0x18000da91  mov     rcx, cs:WPP_GLOBAL_Control
0x18000da98  cmp     rcx, rsi
0x18000da9b  jz      short loc_18000DABA
0x18000da9d  test    [rcx+1Ch], bl
0x18000daa0  jz      short loc_18000DABA
0x18000daa2  mov     edx, 0Ch
0x18000daa7  mov     r9d, eax
0x18000daaa  lea     r8, WPP_9c3b68551b0139bf402022d307f73d71_Traceguids
0x18000dab1  mov     rcx, [rcx+10h]
0x18000dab5  call    WPP_SF_d
0x18000daba  mov     eax, [rsp+3D8h+var_378]
0x18000dabe  jmp     loc_18000E2A8
0x18000dac3  mov     [rsp+3D8h+var_354], ebx
0x18000daca  mov     r12d, ebx
0x18000dacd  mov     [rsp+3D8h+var_358], r13d
0x18000dad5  mov     edi, 80004005h
0x18000dada  mov     [rsp+3D8h+var_378], edi
0x18000dade  mov     [rsp+3D8h+ReturnLength], r13; ReturnLength
0x18000dae3  mov     [rsp+3D8h+PreviousState], r13; unsigned int
0x18000dae8  xor     r9d, r9d; BufferLength
0x18000daeb  xor     r8d, r8d; NewState
0x18000daee  mov     edx, ebx; ResetToDefault
0x18000daf0  mov     rcx, [rsp+3D8h+TokenHandle]; TokenHandle
0x18000daf5  call    cs:__imp_AdjustTokenGroups
0x18000dafb  test    eax, eax
0x18000dafd  jnz     short loc_18000DB51
0x18000daff  call    cs:__imp_GetLastError
0x18000db05  mov     r14d, 80070000h
0x18000db0b  test    eax, eax
0x18000db0d  jle     short loc_18000DB17
0x18000db0f  movzx   eax, ax
0x18000db12  or      eax, r14d
0x18000db15  test    eax, eax
0x18000db17  cmovns  eax, edi
0x18000db1a  mov     [rsp+3D8h+var_378], eax
0x18000db1e  lea     rsi, WPP_GLOBAL_Control
0x18000db25  mov     rcx, cs:WPP_GLOBAL_Control
0x18000db2c  cmp     rcx, rsi
0x18000db2f  jz      short loc_18000DB5E
0x18000db31  test    byte ptr [rcx+1Ch], 2
0x18000db35  jz      short loc_18000DB5E
0x18000db37  mov     edx, 0Dh
0x18000db3c  mov     r9d, eax
0x18000db3f  lea     r8, WPP_9c3b68551b0139bf402022d307f73d71_Traceguids
0x18000db46  mov     rcx, [rcx+10h]
0x18000db4a  call    WPP_SF_d
0x18000db4f  jmp     short loc_18000DB5E
0x18000db51  mov     r14d, 80070000h
0x18000db57  lea     rsi, WPP_GLOBAL_Control
0x18000db5e  xor     r8d, r8d; bInherit
0x18000db61  mov     rdx, [rsp+3D8h+TokenHandle]; hToken
0x18000db66  lea     rcx, [rsp+3D8h+Environment]; lpEnvironment
0x18000db6b  call    cs:__imp_CreateEnvironmentBlock
0x18000db71  test    eax, eax
0x18000db73  jnz     short loc_18000DBA2
0x18000db75  mov     rcx, cs:WPP_GLOBAL_Control
0x18000db7c  cmp     rcx, rsi
0x18000db7f  jz      short loc_18000DB99
0x18000db81  test    [rcx+1Ch], bl
0x18000db84  jz      short loc_18000DB99
0x18000db86  lea     edx, [rax+0Eh]
0x18000db89  lea     r8, WPP_9c3b68551b0139bf402022d307f73d71_Traceguids
0x18000db90  mov     rcx, [rcx+10h]
0x18000db94  call    WPP_SF_
0x18000db99  mov     [rsp+3D8h+Environment], 0
0x18000dba2  test    r15d, r15d
0x18000dba5  jnz     short loc_18000DBDE
0x18000dba7  mov     rcx, [rsp+3D8h+TokenHandle]; hToken
0x18000dbac  call    cs:__imp_ImpersonateLoggedOnUser
0x18000dbb2  test    eax, eax
0x18000dbb4  jnz     short loc_18000DBD4
0x18000dbb6  call    cs:__imp_GetLastError
0x18000dbbc  test    eax, eax
0x18000dbbe  jle     short loc_18000DBC8
0x18000dbc0  movzx   eax, ax
0x18000dbc3  or      eax, r14d
0x18000dbc6  test    eax, eax
0x18000dbc8  cmovns  eax, edi
0x18000dbcb  mov     [rsp+3D8h+var_378], eax
0x18000dbcf  jmp     loc_18000E20F
0x18000dbd4  mov     r13d, ebx
0x18000dbd7  mov     [rsp+3D8h+var_358], ebx
0x18000dbde  lea     rax, [rsp+3D8h+var_188]
0x18000dbe6  mov     [rsp+3D8h+lpEnvironment], rax; wchar_t *
0x18000dbeb  lea     rax, [rsp+3D8h+CommandLine]
0x18000dbf3  mov     [rsp+3D8h+ReturnLength], rax; wchar_t *
0x18000dbf8  lea     r9, [rsp+3D8h+ApplicationName]; wchar_t *
0x18000dc00  mov     r8, qword ptr [rsp+3D8h+uMode]; void *
0x18000dc08  mov     rdx, [rsp+3D8h+ProcessHandle]; HANDLE
0x18000dc10  mov     rcx, [rsp+3D8h+Process]; Process
0x18000dc18  call    ?GetCrashVerticalPaths@@YAJPEAX00PEA_WK1K1K@Z; GetCrashVerticalPaths(void *,void *,void *,wchar_t *,ulong,wchar_t *,ulong,wchar_t *,ulong)
0x18000dc1d  mov     edi, eax
0x18000dc1f  mov     [rsp+3D8h+var_378], eax
0x18000dc23  test    eax, eax
0x18000dc25  jns     short loc_18000DC7E
0x18000dc27  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dc2e  cmp     rcx, rsi
0x18000dc31  jz      short loc_18000DC50
0x18000dc33  test    [rcx+1Ch], bl
0x18000dc36  jz      short loc_18000DC50
0x18000dc38  mov     edx, 0Fh
0x18000dc3d  mov     r9d, eax
0x18000dc40  lea     r8, WPP_9c3b68551b0139bf402022d307f73d71_Traceguids
0x18000dc47  mov     rcx, [rcx+10h]
0x18000dc4b  call    WPP_SF_d
0x18000dc50  call    cs:__imp_GetCurrentProcessId
0x18000dc56  mov     r9d, eax
0x18000dc59  mov     dword ptr [rsp+3D8h+ReturnLength], edi
0x18000dc5d  mov     dword ptr [rsp+3D8h+PreviousState], 107h
0x18000dc65  lea     r8, Format; "WER/CrashExp/%u:%u: ERROR Failed to get"...
0x18000dc6c  xor     edx, edx; Level
0x18000dc6e  mov     ecx, 96h; ComponentId
0x18000dc73  call    cs:__imp_DbgPrintEx
0x18000dc79  jmp     loc_18000E20F
0x18000dc7e  mov     edi, 70h ; 'p'
0x18000dc83  mov     r8d, edi; Size
0x18000dc86  xor     edx, edx; Val
0x18000dc88  lea     rcx, [rsp+3D8h+var_280]; void *
0x18000dc90  call    memset_0
0x18000dc95  movups  xmm0, [rsp+3D8h+var_280]
0x18000dc9d  movaps  xmmword ptr [rsp+3D8h+StartupInfo], xmm0
0x18000dca5  movups  xmm1, [rsp+3D8h+var_270]
0x18000dcad  movaps  xmmword ptr [rsp+3D8h+StartupInfo+10h], xmm1
0x18000dcb5  movups  xmm0, [rsp+3D8h+var_260]
0x18000dcbd  movaps  xmmword ptr [rsp+3D8h+StartupInfo+20h], xmm0
0x18000dcc5  movups  xmm1, [rsp+3D8h+var_250]
0x18000dccd  movaps  xmmword ptr [rsp+3D8h+StartupInfo+30h], xmm1
0x18000dcd5  movups  xmm0, [rsp+3D8h+var_240]
0x18000dcdd  movaps  xmmword ptr [rsp+3D8h+StartupInfo+40h], xmm0
0x18000dce5  movups  xmm1, [rsp+3D8h+var_230]
0x18000dced  movaps  xmmword ptr [rsp+3D8h+StartupInfo+50h], xmm1
0x18000dcf5  movups  xmm0, [rsp+3D8h+var_220]
0x18000dcfd  movaps  xmmword ptr [rsp+3D8h+StartupInfo+60h], xmm0
0x18000dd05  mov     dword ptr [rsp+3D8h+StartupInfo], edi
0x18000dd0c  lea     rax, dword_18004FE4C
0x18000dd13  mov     qword ptr [rsp+3D8h+StartupInfo+10h], rax
0x18000dd1b  mov     dword ptr [rsp+3D8h+StartupInfo+3Ch], ebx
0x18000dd22  xor     eax, eax
0x18000dd24  mov     word ptr [rsp+3D8h+StartupInfo+40h], ax
0x18000dd2c  mov     rcx, [rsp+3D8h+Process]; void *
0x18000dd34  call    ?UtilIsProtectedProcess@@YA_NPEAX@Z; UtilIsProtectedProcess(void *)
0x18000dd39  movzx   r15d, al
0x18000dd3d  shl     r15d, 12h
0x18000dd41  mov     [rsp+3D8h+var_340], 4
0x18000dd4c  xor     eax, eax
0x18000dd4e  mov     [rsp+3D8h+var_374], ax
0x18000dd53  mov     [rsp+3D8h+var_370], ax
0x18000dd58  lea     r8, [rsp+3D8h+var_370]; unsigned __int16 *
0x18000dd5d  lea     rdx, [rsp+3D8h+var_374]; unsigned __int16 *
0x18000dd62  mov     rcx, [rsp+3D8h+Process]; void *
0x18000dd6a  call    ?WerpGetProcessArchitecture@@YAJPEAXPEAG1@Z; WerpGetProcessArchitecture(void *,ushort *,ushort *)
0x18000dd6f  mov     eax, 0AA64h
0x18000dd74  cmp     [rsp+3D8h+var_370], ax
0x18000dd79  jnz     short loc_18000DD87
0x18000dd7b  mov     eax, 8664h
0x18000dd80  cmp     [rsp+3D8h+var_374], ax
0x18000dd85  jz      short loc_18000DD8E
0x18000dd87  xor     eax, eax
0x18000dd89  mov     [rsp+3D8h+var_374], ax
0x18000dd8e  lea     rdx, [rsp+3D8h+ProcessHandle]
0x18000dd96  lea     rax, [rsp+3D8h+Process]
0x18000dd9e  cmp     [rsp+3D8h+ProcessHandle], 0
0x18000dda7  cmovz   rdx, rax
0x18000ddab  lea     rax, [rsp+3D8h+var_374]
0x18000ddb0  mov     qword ptr [rsp+3D8h+dwCreationFlags], rax
0x18000ddb5  lea     rax, [rsp+3D8h+var_328]
0x18000ddbd  mov     [rsp+3D8h+ReturnLength], rax
0x18000ddc2  mov     eax, [rsp+3D8h+arg_28]
0x18000ddc9  mov     dword ptr [rsp+3D8h+PreviousState], eax
0x18000ddcd  mov     r9, [rsp+3D8h+var_308]
0x18000ddd5  lea     r8, [rsp+3D8h+var_340]
0x18000dddd  lea     rcx, [rsp+3D8h+lpAddress]
0x18000dde5  call    BuildCreateProcessAttributeList
0x18000ddea  mov     edi, eax
0x18000ddec  mov     [rsp+3D8h+var_378], eax
0x18000ddf0  test    eax, eax
0x18000ddf2  jns     short loc_18000DE5A
0x18000ddf4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ddfb  cmp     rcx, rsi
0x18000ddfe  jz      short loc_18000DE1D
0x18000de00  test    [rcx+1Ch], bl
0x18000de03  jz      short loc_18000DE1D
0x18000de05  mov     edx, 10h
0x18000de0a  mov     r9d, eax
0x18000de0d  lea     r8, WPP_9c3b68551b0139bf402022d307f73d71_Traceguids
0x18000de14  mov     rcx, [rcx+10h]
0x18000de18  call    WPP_SF_d
0x18000de1d  call    cs:__imp_GetCurrentProcessId
0x18000de23  mov     r9d, eax
0x18000de26  mov     dword ptr [rsp+3D8h+ReturnLength], edi
0x18000de2a  mov     dword ptr [rsp+3D8h+PreviousState], 13Fh
0x18000de32  lea     r8, aWerCrashexpUUE_0; "WER/CrashExp/%u:%u: ERROR WerpBuildCrea"...
0x18000de39  xor     edx, edx; Level
0x18000de3b  mov     ecx, 96h; ComponentId
0x18000de40  call    cs:__imp_DbgPrintEx
0x18000de46  lea     rdx, loc_18000DABA
0x18000de4d  mov     rcx, [rsp+3D8h+var_288]
0x18000de55  call    _local_unwind_0
0x18000de5a  mov     rax, [rsp+3D8h+lpAddress]
0x18000de62  mov     qword ptr [rsp+3D8h+StartupInfo+68h], rax
  ... truncated ...
```
