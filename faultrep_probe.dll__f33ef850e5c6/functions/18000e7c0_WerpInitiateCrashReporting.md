# WerpInitiateCrashReporting

- ea: `0x18000e7c0`
- end: `0x18000edd6`
- name: `WerpInitiateCrashReporting`
- size: `1558`
- prototype: ``
- caller_count: `0`
- callee_count: `25`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002890`
- `0x1800028b4`
- `0x180004888`
- `0x180007704`
- `0x180009ed8`
- `0x180009f00`
- `0x18000d8b4`
- `0x18000e30c`
- `0x18000e330`
- `0x18000e438`
- `0x18000e524`
- `0x18000e7c0`
- `0x18000eddc`
- `0x18000f2dc`
- `0x180014c34`
- `0x180016c20`
- `0x180024c44`
- `0x180024df8`
- `0x180024edc`
- `0x1800250fc`
- `0x18003c08c`
- `0x18003c178`
- `0x18003e4e8`
- `0x18003e5a8`
- `0x180049280`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18000ed6f`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18000ed7c`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18000ed6f`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18000ed7c`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18000ed66`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18000ed66`
- `ntdll!NtSetSystemInformation` at `0x18000e8b0`
- `ntdll!NtSetSystemInformation` at `0x18000e8b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ea4e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000eae1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000eb8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000eba7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ec30`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ec44`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ec71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ec85`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ec99`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ea4e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000eae1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000eb8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000eba7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ec30`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ec44`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ec71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ec85`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ec99`
- `wer!WerpCreateMachineStore` at `0x18000e9bc`
- `wer!WerpCreateMachineStore` at `0x18000e9bc`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18000eb40`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18000eb40`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18000eb18`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18000eb18`

## string_xrefs

- `0x18000ea61`: `DisableWerFaultSecurity`
- `0x18000ed27`: `faultrep.dll`

## pseudocode

```c
__int64 __fastcall WerpInitiateCrashReporting(
        void *a1,
        void *a2,
        void *a3,
        void **a4,
        unsigned int a5,
        int a6,
        int a7,
        _QWORD *a8)
{
  HANDLE v9; // rsi
  int v10; // ebx
  int v11; // r15d
  int TimeDeltaInHours; // eax
  __int64 v13; // rax
  int MachineStore; // eax
  HANDLE v15; // rcx
  int ProcessToken; // eax
  unsigned int DWORD; // eax
  unsigned int v18; // ebx
  char v19; // r15
  int UserToken; // eax
  void *v21; // rcx
  HANDLE v22; // rcx
  __int64 v23; // rax
  void *v24; // rcx
  HANDLE v25; // rbx
  void **v26; // rax
  int CrashVerticalProcess; // eax
  HANDLE v28; // rax
  HANDLE v29; // rcx
  DWORD ProcessId; // ebx
  DWORD v32; // eax
  int v33; // eax
  bool *v34; // [rsp+20h] [rbp-E0h]
  bool v35; // [rsp+28h] [rbp-D8h]
  bool v36; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE TokenHandle; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE v38; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v39; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE hObject; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE SystemInformation; // [rsp+68h] [rbp-98h] BYREF
  __int64 v42; // [rsp+70h] [rbp-90h] BYREF
  void *v43; // [rsp+78h] [rbp-88h]
  void *v44; // [rsp+80h] [rbp-80h]
  _WORD *v45; // [rsp+88h] [rbp-78h]
  _WORD v46[8]; // [rsp+90h] [rbp-70h] BYREF
  void *v47; // [rsp+A0h] [rbp-60h]
  _WORD *v48; // [rsp+A8h] [rbp-58h]
  _WORD v49[8]; // [rsp+B0h] [rbp-50h] BYREF
  void *v50; // [rsp+C0h] [rbp-40h]
  _WORD *v51; // [rsp+C8h] [rbp-38h]
  _WORD v52[8]; // [rsp+D0h] [rbp-30h] BYREF
  void **v53; // [rsp+E0h] [rbp-20h]
  _BYTE v54[10576]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A98h] [rbp+2998h]

  SystemInformation = a1;
  v53 = a4;
  v43 = a3;
  CCrashReport::CCrashReport((CCrashReport *)v54);
  v50 = v52;
  v51 = v52;
  v47 = v49;
  v48 = v49;
  v44 = v46;
  v45 = v46;
  v9 = 0;
  v52[0] = 0;
  v49[0] = 0;
  v46[0] = 0;
  v39 = 0;
  TokenHandle = 0;
  v42 = 0;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_9c3b68551b0139bf402022d307f73d71_Traceguids);
    v10 = -2147024809;
    goto LABEL_71;
  }
  NtSetSystemInformation(SystemSessionInformation|0x80, &SystemInformation, 8u);
  v11 = IsCrashVerticalReportingOnSelf(SystemInformation);
  if ( !v11 )
    goto LABEL_18;
  LODWORD(v38) = 0;
  v36 = 0;
  TimeDeltaInHours = UtilRegGetTimeDeltaInHours(
                       HKEY_CURRENT_USER,
                       L"Software\\Microsoft\\Windows\\Windows Error Reporting",
                       L"LastCrashSelfReportTime",
                       (unsigned int *)&v38,
                       &v36);
  if ( TimeDeltaInHours < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        &WPP_53d7d5032f353c7111b5bf691d3dce61_Traceguids,
        (unsigned int)TimeDeltaInHours);
    goto LABEL_13;
  }
  if ( v36 && !(_DWORD)v38 )
  {
LABEL_13:
    MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_9c3b68551b0139bf402022d307f73d71_Traceguids);
    v10 = -2147024739;
    goto LABEL_71;
  }
  v10 = UtilRegSetCurrentTime(
          HKEY_CURRENT_USER,
          L"Software\\Microsoft\\Windows\\Windows Error Reporting",
          L"LastCrashSelfReportTime");
  if ( v10 >= 0 )
  {
LABEL_18:
    if ( !a7 )
    {
      if ( v11 )
      {
        if ( (MEMORY[0x7FFE02F0] & 1) == 0 )
        {
          MicrosoftTelemetryAssertTriggeredArgs("faultrep.dll", 3221226323LL);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_9c3b68551b0139bf402022d307f73d71_Traceguids);
          v10 = -2147467259;
          goto LABEL_71;
        }
      }
      else
      {
        SetErrorMode(0);
      }
      ProcessId = GetProcessId(a2);
      v32 = GetProcessId(SystemInformation);
      v33 = CCrashReport::ReportCrash((CCrashReport *)v54, v32, ProcessId, v43);
      v10 = v33;
      if ( v33 < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            26,
            &WPP_9c3b68551b0139bf402022d307f73d71_Traceguids,
            (unsigned int)v33);
        goto LABEL_71;
      }
LABEL_70:
      v10 = 0;
      goto LABEL_71;
    }
    hObject = 0;
    v13 = tlx::replace<tlx::file_handle_traits>(&hObject);
    MachineStore = WerpCreateMachineStore(v13);
    v10 = MachineStore;
    if ( MachineStore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x25F,
        (unsigned int)"onecore\\windows\\feedback\\core\\faultrep\\libex\\crashreportexp.cpp",
        (const char *)(unsigned int)MachineStore,
        (int)v34);
      v15 = hObject;
      if ( (unsigned __int64)hObject + 1 <= 1 )
        goto LABEL_74;
      goto LABEL_73;
    }
    ProcessToken = UserTokenUtility::GetProcessToken(a2);
    v10 = ProcessToken;
    if ( ProcessToken < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          23,
          &WPP_9c3b68551b0139bf402022d307f73d71_Traceguids,
          (unsigned int)ProcessToken);
      if ( (unsigned __int64)hObject + 1 > 1 )
        CloseHandle(hObject);
      v9 = TokenHandle;
      goto LABEL_71;
    }
    DWORD = UtilRegGetDWORD(
              HKEY_LOCAL_MACHINE,
              L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Debug",
              L"DisableWerFaultSecurity",
              0,
              v34,
              v35);
    v9 = TokenHandle;
    v18 = DWORD;
    if ( DWORD >= 2 )
      goto LABEL_33;
    v19 = 0;
    if ( (unsigned int)UtilIsLowRightsToken(TokenHandle) )
    {
LABEL_55:
      v38 = 0;
      v26 = (void **)tlx::replace<tlx::file_handle_traits>(&v38);
      CrashVerticalProcess = CreateCrashVerticalProcess(SystemInformation, a2, v9, v43, v53, a5, v19, v26);
      v10 = CrashVerticalProcess;
      if ( CrashVerticalProcess < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            24,
            &WPP_9c3b68551b0139bf402022d307f73d71_Traceguids,
            (unsigned int)CrashVerticalProcess);
        if ( (unsigned __int64)v38 + 1 > 1 )
          CloseHandle(v38);
        if ( (unsigned __int64)hObject + 1 > 1 )
          CloseHandle(hObject);
        goto LABEL_71;
      }
      if ( a8 )
      {
        v28 = v38;
        v29 = 0;
        v38 = 0;
        *a8 = v28;
      }
      else
      {
        v29 = v38;
      }
      if ( (unsigned __int64)v29 + 1 > 1 )
        CloseHandle(v29);
      if ( (unsigned __int64)hObject + 1 > 1 )
        CloseHandle(hObject);
      goto LABEL_70;
    }
    if ( v18 )
    {
LABEL_33:
      v19 = 1;
      goto LABEL_55;
    }
    if ( (unsigned int)UtilIsVirtualAccountToken(v9) )
    {
      if ( !(unsigned __int8)IsUMgrQueryUserContextPresent()
        || !(unsigned __int8)IsUMgrQueryUserContextPresent()
        || (int)UMgrQueryUserContext(v9, &v42) < 0
        || !v42 )
      {
        if ( (int)UserTokenUtility::GetTokenSessionId(v9, &v39) < 0 || !v39 )
          goto LABEL_55;
        TokenHandle = 0;
        if ( (int)UserTokenUtility::GetUserToken(SystemInformation) < 0 )
        {
          v25 = TokenHandle;
        }
        else
        {
          v24 = v9;
          v25 = 0;
          v9 = TokenHandle;
          if ( (unsigned __int64)v24 + 1 > 1 )
            CloseHandle(v24);
        }
        if ( (unsigned __int64)v25 + 1 <= 1 )
          goto LABEL_55;
        v22 = v25;
LABEL_54:
        CloseHandle(v22);
        goto LABEL_55;
      }
      TokenHandle = 0;
      v23 = tlx::replace<tlx::file_handle_traits>(&TokenHandle);
      UserToken = UMgrQueryUserToken(v42, v23);
    }
    else
    {
      TokenHandle = 0;
      UserToken = UserTokenUtility::GetVirtualAccountTokenFromProcessToken(v9, &TokenHandle);
    }
    if ( UserToken >= 0 )
    {
      v21 = v9;
      v9 = TokenHandle;
      TokenHandle = 0;
      if ( (unsigned __int64)v21 + 1 > 1 )
        CloseHandle(v21);
    }
    v22 = TokenHandle;
    if ( (unsigned __int64)TokenHandle + 1 <= 1 )
      goto LABEL_55;
    goto LABEL_54;
  }
LABEL_71:
  if ( (unsigned __int64)v9 + 1 <= 1 )
    goto LABEL_74;
  v15 = v9;
LABEL_73:
  CloseHandle(v15);
LABEL_74:
  if ( v44 != v46 )
    operator delete(v44, (const struct std::nothrow_t *)&std::nothrow);
  if ( v47 != v49 )
    operator delete(v47, (const struct std::nothrow_t *)&std::nothrow);
  if ( v50 != v52 )
    operator delete(v50, (const struct std::nothrow_t *)&std::nothrow);
  CCrashReport::~CCrashReport((CCrashReport *)v54);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000e7c0  push    rbp
0x18000e7c2  push    rbx
0x18000e7c3  push    rsi
0x18000e7c4  push    rdi
0x18000e7c5  push    r12
0x18000e7c7  push    r13
0x18000e7c9  push    r14
0x18000e7cb  push    r15
0x18000e7cd  lea     rbp, [rsp-2958h]
0x18000e7d5  mov     eax, 2A58h
0x18000e7da  call    _alloca_probe
0x18000e7df  sub     rsp, rax
0x18000e7e2  mov     rax, cs:__security_cookie
0x18000e7e9  xor     rax, rsp
0x18000e7ec  mov     [rbp+2990h+var_50], rax
0x18000e7f3  mov     r12, [rbp+2990h+arg_38]
0x18000e7fa  mov     r13, rdx
0x18000e7fd  mov     [rsp+2A90h+SystemInformation], rcx
0x18000e802  lea     rcx, [rbp+2990h+var_29A0]; this
0x18000e806  mov     [rbp+2990h+var_29B0], r9
0x18000e80a  mov     [rsp+2A90h+var_2A18], r8
0x18000e80f  call    ??0CCrashReport@@QEAA@XZ; CCrashReport::CCrashReport(void)
0x18000e814  xor     ebx, ebx
0x18000e816  lea     rax, [rbp+2990h+var_29C0]
0x18000e81a  mov     [rbp+2990h+var_29D0], rax
0x18000e81e  lea     rax, [rbp+2990h+var_29C0]
0x18000e822  mov     [rbp+2990h+var_29C8], rax
0x18000e826  lea     rax, [rbp+2990h+var_29E0]
0x18000e82a  mov     [rbp+2990h+var_29F0], rax
0x18000e82e  lea     rax, [rbp+2990h+var_29E0]
0x18000e832  mov     [rbp+2990h+var_29E8], rax
0x18000e836  lea     rax, [rbp+2990h+var_2A00]
0x18000e83a  mov     [rbp+2990h+var_2A10], rax
0x18000e83e  lea     rax, [rbp+2990h+var_2A00]
0x18000e842  mov     [rbp+2990h+var_2A08], rax
0x18000e846  mov     esi, ebx
0x18000e848  mov     [rbp+2990h+var_29C0], bx
0x18000e84c  mov     [rbp+2990h+var_29E0], bx
0x18000e850  mov     [rbp+2990h+var_2A00], bx
0x18000e854  mov     [rsp+2A90h+var_2A38], ebx
0x18000e858  mov     [rsp+2A90h+TokenHandle], rbx
0x18000e85d  mov     [rsp+2A90h+var_2A20], rbx
0x18000e862  test    r13, r13
0x18000e865  jnz     short loc_18000E8A0
0x18000e867  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e86e  lea     r14, WPP_GLOBAL_Control
0x18000e875  lea     edi, [rbx+1]
0x18000e878  cmp     rcx, r14
0x18000e87b  jz      short loc_18000E896
0x18000e87d  test    [rcx+1Ch], dil
0x18000e881  jz      short loc_18000E896
0x18000e883  mov     rcx, [rcx+10h]
0x18000e887  lea     edx, [rbx+15h]
0x18000e88a  lea     r8, WPP_9c3b68551b0139bf402022d307f73d71_Traceguids
0x18000e891  call    WPP_SF_
0x18000e896  mov     ebx, 80070057h
0x18000e89b  jmp     loc_18000EC8D
0x18000e8a0  mov     r8d, 8; SystemInformationLength
0x18000e8a6  lea     rdx, [rsp+2A90h+SystemInformation]; SystemInformation
0x18000e8ab  mov     ecx, 0B1h; SystemInformationClass
0x18000e8b0  call    cs:__imp_NtSetSystemInformation
0x18000e8b6  mov     rcx, [rsp+2A90h+SystemInformation]; hProcess
0x18000e8bb  call    ?IsCrashVerticalReportingOnSelf@@YAHPEAX@Z; IsCrashVerticalReportingOnSelf(void *)
0x18000e8c0  mov     r15d, eax
0x18000e8c3  mov     edi, 1
0x18000e8c8  test    eax, eax
0x18000e8ca  jz      loc_18000E9FA
0x18000e8d0  lea     rax, [rsp+2A90h+var_2A50]
0x18000e8d5  mov     dword ptr [rsp+2A90h+var_2A40], ebx
0x18000e8d9  lea     r9, [rsp+2A90h+var_2A40]; unsigned int *
0x18000e8de  mov     [rsp+2A90h+var_2A70], rax; bool *
0x18000e8e3  lea     r8, aLastcrashselfr; "LastCrashSelfReportTime"
0x18000e8ea  mov     [rsp+2A90h+var_2A50], bl
0x18000e8ee  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\Windows\\Windows E"...
0x18000e8f5  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x18000e8fc  call    ?UtilRegGetTimeDeltaInHours@@YAJPEAUHKEY__@@PEB_W1PEAKPEA_N@Z; UtilRegGetTimeDeltaInHours(HKEY__ *,wchar_t const *,wchar_t const *,ulong *,bool *)
0x18000e901  lea     r14, WPP_GLOBAL_Control
0x18000e908  test    eax, eax
0x18000e90a  jns     short loc_18000E936
0x18000e90c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e913  cmp     rcx, r14
0x18000e916  jz      short loc_18000E942
0x18000e918  test    byte ptr [rcx+1Ch], 2
0x18000e91c  jz      short loc_18000E942
0x18000e91e  mov     rcx, [rcx+10h]
0x18000e922  lea     edx, [rdi+9]
0x18000e925  mov     r9d, eax
0x18000e928  lea     r8, WPP_53d7d5032f353c7111b5bf691d3dce61_Traceguids
0x18000e92f  call    WPP_SF_d
0x18000e934  jmp     short loc_18000E942
0x18000e936  cmp     [rsp+2A90h+var_2A50], bl
0x18000e93a  jz      short loc_18000E978
0x18000e93c  cmp     dword ptr [rsp+2A90h+var_2A40], edi
0x18000e940  jnb     short loc_18000E978
0x18000e942  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000e947  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e94e  cmp     rcx, r14
0x18000e951  jz      short loc_18000E96E
0x18000e953  test    [rcx+1Ch], dil
0x18000e957  jz      short loc_18000E96E
0x18000e959  mov     rcx, [rcx+10h]
0x18000e95d  lea     r8, WPP_9c3b68551b0139bf402022d307f73d71_Traceguids
0x18000e964  mov     edx, 16h
0x18000e969  call    WPP_SF_
0x18000e96e  mov     ebx, 8007009Dh
0x18000e973  jmp     loc_18000EC8D
0x18000e978  lea     r8, aLastcrashselfr; "LastCrashSelfReportTime"
0x18000e97f  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18000e986  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\Windows\\Windows E"...
0x18000e98d  call    ?UtilRegSetCurrentTime@@YAJPEAUHKEY__@@PEB_W1@Z; UtilRegSetCurrentTime(HKEY__ *,wchar_t const *,wchar_t const *)
0x18000e992  mov     ebx, eax
0x18000e994  test    eax, eax
0x18000e996  js      loc_18000EC8D
0x18000e99c  xor     ebx, ebx
0x18000e99e  cmp     [rbp+2990h+arg_30], ebx
0x18000e9a4  jz      loc_18000ED13
0x18000e9aa  lea     rcx, [rsp+2A90h+hObject]
0x18000e9af  mov     [rsp+2A90h+hObject], rbx
0x18000e9b4  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x18000e9b9  mov     rcx, rax
0x18000e9bc  call    cs:__imp_WerpCreateMachineStore
0x18000e9c2  mov     ebx, eax
0x18000e9c4  test    eax, eax
0x18000e9c6  jns     short loc_18000EA03
0x18000e9c8  mov     rcx, [rbp+2998h]; this
0x18000e9cf  lea     r8, aOnecoreWindows_1; "onecore\\windows\\feedback\\core\\fault"...
0x18000e9d6  mov     r9d, eax; char *
0x18000e9d9  mov     edx, 25Fh; void *
0x18000e9de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e9e3  mov     rcx, [rsp+2A90h+hObject]
0x18000e9e8  lea     rdx, [rcx+1]
0x18000e9ec  cmp     rdx, rdi
0x18000e9ef  jbe     loc_18000EC9F
0x18000e9f5  jmp     loc_18000EC99
0x18000e9fa  lea     r14, WPP_GLOBAL_Control
0x18000ea01  jmp     short loc_18000E99E
0x18000ea03  lea     r8, [rsp+2A90h+TokenHandle]
0x18000ea08  mov     rcx, r13; ProcessHandle
0x18000ea0b  call    ?GetProcessToken@UserTokenUtility@@SAJPEAXHPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z; UserTokenUtility::GetProcessToken(void *,int,tlx::unique_any<tlx::file_handle_traits> *)
0x18000ea10  mov     ebx, eax
0x18000ea12  test    eax, eax
0x18000ea14  jns     short loc_18000EA5E
0x18000ea16  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ea1d  cmp     rcx, r14
0x18000ea20  jz      short loc_18000EA40
0x18000ea22  test    [rcx+1Ch], dil
0x18000ea26  jz      short loc_18000EA40
0x18000ea28  mov     rcx, [rcx+10h]
0x18000ea2c  lea     r8, WPP_9c3b68551b0139bf402022d307f73d71_Traceguids
0x18000ea33  mov     edx, 17h
0x18000ea38  mov     r9d, eax
0x18000ea3b  call    WPP_SF_d
0x18000ea40  mov     rcx, [rsp+2A90h+hObject]; hObject
0x18000ea45  lea     rax, [rcx+1]
0x18000ea49  cmp     rax, rdi
0x18000ea4c  jbe     short loc_18000EA54
0x18000ea4e  call    cs:__imp_CloseHandle
0x18000ea54  mov     rsi, [rsp+2A90h+TokenHandle]
0x18000ea59  jmp     loc_18000EC8D
0x18000ea5e  xor     r9d, r9d; unsigned int
0x18000ea61  lea     r8, aDisablewerfaul; "DisableWerFaultSecurity"
0x18000ea68  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\Windows E"...
0x18000ea6f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000ea76  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x18000ea7b  mov     rsi, [rsp+2A90h+TokenHandle]
0x18000ea80  mov     ebx, eax
0x18000ea82  cmp     eax, 2
0x18000ea85  jnb     short loc_18000EA9E
0x18000ea87  mov     rcx, rsi; TokenHandle
0x18000ea8a  xor     r15d, r15d
0x18000ea8d  call    ?UtilIsLowRightsToken@@YAJPEAX@Z; UtilIsLowRightsToken(void *)
0x18000ea92  test    eax, eax
0x18000ea94  jnz     loc_18000EBAD
0x18000ea9a  cmp     ebx, edi
0x18000ea9c  jb      short loc_18000EAA6
0x18000ea9e  mov     r15d, edi
0x18000eaa1  jmp     loc_18000EBAD
0x18000eaa6  mov     rcx, rsi; void *
0x18000eaa9  call    ?UtilIsVirtualAccountToken@@YAJPEAX@Z; UtilIsVirtualAccountToken(void *)
0x18000eaae  test    eax, eax
0x18000eab0  jnz     short loc_18000EAFE
0x18000eab2  lea     rdx, [rsp+2A90h+TokenHandle]
0x18000eab7  mov     [rsp+2A90h+TokenHandle], r15
0x18000eabc  mov     rcx, rsi
0x18000eabf  call    ?GetVirtualAccountTokenFromProcessToken@UserTokenUtility@@SAJPEAXPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z; UserTokenUtility::GetVirtualAccountTokenFromProcessToken(void *,tlx::unique_any<tlx::file_handle_traits> *)
0x18000eac4  test    eax, eax
0x18000eac6  js      short loc_18000EAE7
0x18000eac8  mov     rax, [rsp+2A90h+TokenHandle]
0x18000eacd  mov     rcx, rsi; hObject
0x18000ead0  mov     rsi, rax
0x18000ead3  mov     [rsp+2A90h+TokenHandle], r15
0x18000ead8  lea     rax, [rcx+1]
0x18000eadc  cmp     rax, rdi
0x18000eadf  jbe     short loc_18000EAE7
0x18000eae1  call    cs:__imp_CloseHandle
0x18000eae7  mov     rcx, [rsp+2A90h+TokenHandle]
0x18000eaec  lea     rax, [rcx+1]
0x18000eaf0  cmp     rax, rdi
0x18000eaf3  jbe     loc_18000EBAD
0x18000eaf9  jmp     loc_18000EBA7
0x18000eafe  call    IsUMgrQueryUserContextPresent
0x18000eb03  test    al, al
0x18000eb05  jz      short loc_18000EB4B
0x18000eb07  call    IsUMgrQueryUserContextPresent
0x18000eb0c  test    al, al
0x18000eb0e  jz      short loc_18000EB4B
0x18000eb10  lea     rdx, [rsp+2A90h+var_2A20]
0x18000eb15  mov     rcx, rsi
0x18000eb18  call    cs:__imp_UMgrQueryUserContext
0x18000eb1e  test    eax, eax
0x18000eb20  js      short loc_18000EB4B
0x18000eb22  cmp     [rsp+2A90h+var_2A20], r15
0x18000eb27  jz      short loc_18000EB4B
0x18000eb29  lea     rcx, [rsp+2A90h+TokenHandle]
0x18000eb2e  mov     [rsp+2A90h+TokenHandle], r15
0x18000eb33  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x18000eb38  mov     rcx, [rsp+2A90h+var_2A20]
0x18000eb3d  mov     rdx, rax
0x18000eb40  call    cs:__imp_UMgrQueryUserToken
0x18000eb46  jmp     loc_18000EAC4
0x18000eb4b  lea     rdx, [rsp+2A90h+var_2A38]; unsigned int *
0x18000eb50  mov     rcx, rsi; void *
0x18000eb53  call    ?GetTokenSessionId@UserTokenUtility@@SAJPEAXPEAK@Z; UserTokenUtility::GetTokenSessionId(void *,ulong *)
0x18000eb58  test    eax, eax
0x18000eb5a  js      short loc_18000EBAD
0x18000eb5c  cmp     [rsp+2A90h+var_2A38], r15d
0x18000eb61  jz      short loc_18000EBAD
0x18000eb63  mov     rcx, [rsp+2A90h+SystemInformation]; ProcessHandle
0x18000eb68  lea     r8, [rsp+2A90h+TokenHandle]
0x18000eb6d  mov     [rsp+2A90h+TokenHandle], r15
0x18000eb72  call    ?GetUserToken@UserTokenUtility@@SAJPEAXHPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z; UserTokenUtility::GetUserToken(void *,int,tlx::unique_any<tlx::file_handle_traits> *)
0x18000eb77  test    eax, eax
0x18000eb79  js      short loc_18000EB96
0x18000eb7b  mov     rcx, rsi; hObject
0x18000eb7e  xor     ebx, ebx
0x18000eb80  mov     rsi, [rsp+2A90h+TokenHandle]
0x18000eb85  lea     rax, [rcx+1]
0x18000eb89  cmp     rax, rdi
0x18000eb8c  jbe     short loc_18000EB9B
0x18000eb8e  call    cs:__imp_CloseHandle
0x18000eb94  jmp     short loc_18000EB9B
0x18000eb96  mov     rbx, [rsp+2A90h+TokenHandle]
0x18000eb9b  lea     rax, [rbx+1]
0x18000eb9f  cmp     rax, rdi
0x18000eba2  jbe     short loc_18000EBAD
0x18000eba4  mov     rcx, rbx; hObject
0x18000eba7  call    cs:__imp_CloseHandle
0x18000ebad  lea     rcx, [rsp+2A90h+var_2A40]
0x18000ebb2  mov     [rsp+2A90h+var_2A40], 0
0x18000ebbb  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x18000ebc0  mov     r9, [rsp+2A90h+var_2A18]; void *
0x18000ebc5  mov     r8, rsi; void *
0x18000ebc8  mov     rcx, [rsp+2A90h+SystemInformation]; Process
0x18000ebcd  mov     rdx, r13; void *
0x18000ebd0  mov     [rsp+2A90h+var_2A58], rax; void **
0x18000ebd5  mov     eax, [rbp+2990h+arg_20]
0x18000ebdb  mov     [rsp+2A90h+var_2A60], r15d; unsigned int
0x18000ebe0  mov     dword ptr [rsp+2A90h+var_2A68], eax; unsigned int
0x18000ebe4  mov     rax, [rbp+2990h+var_29B0]
0x18000ebe8  mov     [rsp+2A90h+var_2A70], rax; void **
0x18000ebed  call    ?CreateCrashVerticalProcess@@YAJPEAX000PEAPEAXKK1@Z; CreateCrashVerticalProcess(void *,void *,void *,void *,void * *,ulong,ulong,void * *)
0x18000ebf2  mov     ebx, eax
0x18000ebf4  test    eax, eax
0x18000ebf6  jns     short loc_18000EC4C
0x18000ebf8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ebff  cmp     rcx, r14
0x18000ec02  jz      short loc_18000EC22
0x18000ec04  test    [rcx+1Ch], dil
0x18000ec08  jz      short loc_18000EC22
0x18000ec0a  mov     rcx, [rcx+10h]
0x18000ec0e  lea     r8, WPP_9c3b68551b0139bf402022d307f73d71_Traceguids
0x18000ec15  mov     edx, 18h
0x18000ec1a  mov     r9d, eax
0x18000ec1d  call    WPP_SF_d
0x18000ec22  mov     rcx, [rsp+2A90h+var_2A40]; hObject
0x18000ec27  lea     rax, [rcx+1]
0x18000ec2b  cmp     rax, rdi
0x18000ec2e  jbe     short loc_18000EC36
0x18000ec30  call    cs:__imp_CloseHandle
0x18000ec36  mov     rcx, [rsp+2A90h+hObject]; hObject
0x18000ec3b  lea     rax, [rcx+1]
0x18000ec3f  cmp     rax, rdi
0x18000ec42  jbe     short loc_18000EC8D
0x18000ec44  call    cs:__imp_CloseHandle
0x18000ec4a  jmp     short loc_18000EC8D
0x18000ec4c  test    r12, r12
0x18000ec4f  jz      short loc_18000EC63
0x18000ec51  mov     rax, [rsp+2A90h+var_2A40]
0x18000ec56  xor     ecx, ecx
0x18000ec58  mov     [rsp+2A90h+var_2A40], rcx
0x18000ec5d  mov     [r12], rax
0x18000ec61  jmp     short loc_18000EC68
0x18000ec63  mov     rcx, [rsp+2A90h+var_2A40]; hObject
0x18000ec68  lea     rax, [rcx+1]
0x18000ec6c  cmp     rax, rdi
0x18000ec6f  jbe     short loc_18000EC77
0x18000ec71  call    cs:__imp_CloseHandle
0x18000ec77  mov     rcx, [rsp+2A90h+hObject]; hObject
0x18000ec7c  lea     rax, [rcx+1]
0x18000ec80  cmp     rax, rdi
  ... truncated ...
```
