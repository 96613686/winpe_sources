# CCrashReport::ReportCrash(ulong,ulong,void *)

- ea: `0x180014c34`
- end: `0x180015415`
- name: `?ReportCrash@CCrashReport@@QEAAJKKPEAX@Z`
- size: `2017`
- prototype: `__int64 __fastcall(CCrashReport *__hidden this, DWORD dwProcessId, DWORD, void *)`
- caller_count: `1`
- callee_count: `25`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000e7c0`

## callees

- `0x180002890`
- `0x180003474`
- `0x180003b38`
- `0x1800045a8`
- `0x180009ed8`
- `0x180009f00`
- `0x180009f40`
- `0x1800124b8`
- `0x1800138bc`
- `0x180014c34`
- `0x18001541c`
- `0x180015554`
- `0x180015e5c`
- `0x180016bb8`
- `0x18001b828`
- `0x18001bec8`
- `0x18001c370`
- `0x18001ce20`
- `0x18002539c`
- `0x180025798`
- `0x18003b45c`
- `0x18003b6e8`
- `0x18003bdf0`
- `0x18003bf38`
- `0x18003e5a8`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800152af`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800152af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014cd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014cd6`
- `ntdll!RtlNtStatusToDosError` at `0x180014e1f`
- `ntdll!RtlNtStatusToDosError` at `0x180014e1f`
- `ntdll!NtQueryInformationProcess` at `0x180014ddb`
- `ntdll!NtQueryInformationProcess` at `0x180014ddb`
- `api-ms-win-core-windowserrorreporting-l1-1-0!WerGetFlags` at `0x180014f39`
- `api-ms-win-core-windowserrorreporting-l1-1-0!WerGetFlags` at `0x180014f39`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015252`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015252`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001527a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001527a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014cc1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800152ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800153b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800153cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014cc1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800152ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800153b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800153cf`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180014c9e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180014c9e`
- `RMCLIENT!HamConnectToServer` at `0x180015268`
- `RMCLIENT!HamConnectToServer` at `0x180015268`
- `ext-ms-win-kernel32-package-l1-1-0!GetPackageFullName` at `0x180015055`
- `ext-ms-win-kernel32-package-l1-1-0!GetPackageFullName` at `0x180015055`
- `ext-ms-win-ntuser-window-l1-1-0!GetShellWindow` at `0x180014e65`
- `ext-ms-win-ntuser-window-l1-1-0!GetShellWindow` at `0x180014e65`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180014e73`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180014e73`
- `ext-ms-win-imm-l1-1-0!ImmDisableIME` at `0x180014c8e`
- `ext-ms-win-imm-l1-1-0!ImmDisableIME` at `0x180014c8e`

## pseudocode

```c
__int64 __fastcall CCrashReport::ReportCrash(CCrashReport *this, DWORD dwProcessId, DWORD a3, void *a4)
{
  HANDLE v8; // rax
  char *v9; // rcx
  signed int LastError; // eax
  signed int v11; // edi
  int CrashData; // eax
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  int IsProcessNative; // eax
  NTSTATUS v17; // eax
  NTSTATUS v18; // edi
  signed int v19; // eax
  int v20; // ecx
  HWND ShellWindow; // rax
  int v22; // eax
  void *v23; // rcx
  _QWORD *v24; // rcx
  __int64 v25; // rdx
  void *v26; // rdx
  void *v27; // rcx
  int v28; // eax
  int *v29; // rdi
  HRESULT Flags; // eax
  int v31; // ecx
  int v32; // eax
  __int64 v33; // rax
  void *v34; // rcx
  LONG v35; // eax
  bool v36; // sf
  BOOL v37; // edi
  __int64 v38; // rdx
  __int64 v39; // r8
  const char *v40; // r9
  __int64 v41; // rdx
  _BYTE *v42; // r14
  _OWORD *v43; // rax
  _OWORD *v44; // rcx
  __int128 v45; // xmm1
  __int128 v46; // xmm0
  __int128 v47; // xmm1
  __int128 v48; // xmm0
  __int128 v49; // xmm1
  __int128 v50; // xmm0
  __int128 v51; // xmm1
  __int128 v52; // xmm1
  __int128 v53; // xmm0
  __int128 v54; // xmm1
  __int128 v55; // xmm0
  void *v56; // rcx
  const wchar_t *v57; // rdx
  BOOL v58; // edi
  int matched; // eax
  int v60; // edi
  void **v61; // r14
  void *v62; // rcx
  void *v63; // rcx
  void *v64; // rcx
  int ProcessInformation; // [rsp+30h] [rbp-D0h] BYREF
  DWORD dwProcessIda; // [rsp+34h] [rbp-CCh] BYREF
  UINT32 packageFullNameLength; // [rsp+38h] [rbp-C8h] BYREF
  struct _WER_RUNTIME_DLL *v69; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v70[592]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR packageFullName[128]; // [rsp+2A0h] [rbp+1A0h] BYREF

  dwProcessIda = 0;
  v69 = 0;
  packageFullNameLength = 0;
  if ( (unsigned __int8)IsImmDisableIMEPresent() )
    ImmDisableIME(0xFFFFFFFF);
  v8 = OpenProcess(0x1FFFFFu, 0, a3);
  v9 = (char *)*((_QWORD *)this + 93);
  *((_QWORD *)this + 93) = v8;
  if ( v9 != (char *)-1LL && v9 + 1 != (char *)1 )
    CloseHandle(v9);
  if ( (unsigned __int64)(*((_QWORD *)this + 93) + 1LL) <= 1 )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    if ( v11 >= 0 )
      v11 = -2147467259;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids, a3, v11);
    goto LABEL_119;
  }
  if ( !a4 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  *((_QWORD *)this + 94) = a4;
  CrashData = CCrashReport::LoadCrashData(this);
  v11 = CrashData;
  if ( CrashData < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_119;
    v14 = 11;
    v15 = (unsigned int)CrashData;
LABEL_19:
    WPP_SF_d(v13[2], v14, WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids, v15);
    goto LABEL_119;
  }
  *(_DWORD *)this = UtilIsProcessAService(*((HANDLE *)this + 6)) == 0;
  IsProcessNative = UtilIsProcessNative(*((HANDLE *)this + 6));
  ProcessInformation = 0;
  *((_DWORD *)this + 1) = IsProcessNative == 0;
  v17 = NtQueryInformationProcess(*((HANDLE *)this + 6), ProcessBreakOnTermination, &ProcessInformation, 4u, 0);
  v18 = v17;
  if ( v17 >= 0 )
  {
    v20 = ProcessInformation == 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        92,
        WPP_988ce82756cb3ec502560a762615dae0_Traceguids,
        (unsigned int)v17);
    v19 = RtlNtStatusToDosError(v18);
    v20 = v19;
    if ( v19 > 0 )
      v20 = (unsigned __int16)v19 | 0x80070000;
    if ( v20 >= 0 )
      v20 = -2147467259;
  }
  *((_DWORD *)this + 3) = v20 == 0;
  if ( !(unsigned __int8)IsGetShellWindowPresent()
    || !(unsigned __int8)IsGetShellWindowPresent()
    || (ShellWindow = GetShellWindow(), !GetWindowThreadProcessId(ShellWindow, &dwProcessIda))
    || (v22 = 1, *((_DWORD *)this + 184) != dwProcessIda) )
  {
    v22 = 0;
  }
  v23 = (void *)*((_QWORD *)this + 6);
  *((_DWORD *)this + 2) = v22;
  if ( (UtilReadErrorModeForProcess(v23) & 2) != 0 )
  {
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_40;
    v25 = 12;
LABEL_39:
    WPP_SF_(v24[2], v25, WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids);
LABEL_40:
    *(_DWORD *)(*((_QWORD *)this + 5) + 176LL) = 1769475;
LABEL_41:
    v11 = 0;
    goto LABEL_119;
  }
  v26 = (void *)*((_QWORD *)this + 7);
  v27 = (void *)*((_QWORD *)this + 6);
  ProcessInformation = 0;
  v28 = UtilReadTEB(v27, v26, &ProcessInformation, 0x16B0u, 4u);
  if ( v28 >= 0 )
  {
    if ( (ProcessInformation & 0x20) != 0 )
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_40;
      v25 = 13;
      goto LABEL_39;
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      93,
      WPP_988ce82756cb3ec502560a762615dae0_Traceguids,
      (unsigned int)v28);
  }
  v29 = (int *)((char *)this + 28);
  Flags = WerGetFlags(*((HANDLE *)this + 6), (PDWORD)this + 7);
  if ( Flags < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids,
        (unsigned int)Flags);
    *v29 = 0;
    LOWORD(v31) = 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids,
        (unsigned int)*v29);
    v31 = *v29;
    *((_DWORD *)this + 8) |= (*v29 >> 31) & 2;
  }
  if ( *((_DWORD *)this + 1) || *((_DWORD *)this + 3) || (v32 = 0, (v31 & 0x600) != 0) )
    v32 = 1;
  *((_DWORD *)this + 8) |= v32;
  v14 = 16;
  v33 = *((_QWORD *)this + 5);
  if ( (*(_BYTE *)(v33 + 236) & 0x10) != 0 && !*((_QWORD *)this + 617) )
  {
    v11 = -2145681401;
    *(_DWORD *)(v33 + 176) = -2145681401;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_119;
LABEL_67:
    v15 = (unsigned int)v11;
    goto LABEL_19;
  }
  v34 = (void *)*((_QWORD *)this + 6);
  packageFullNameLength = 128;
  v35 = GetPackageFullName(v34, &packageFullNameLength, packageFullName);
  v36 = v35 < 0;
  if ( v35 > 0 )
    v36 = 1;
  if ( v36 )
    packageFullName[0] = 0;
  v37 = 0;
  if ( (int)WerpGetRuntimeDllsListStart(*((void **)this + 6), &v69) >= 0 )
    v37 = v69 != 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v40 = "true";
    if ( !v37 )
      v40 = "false";
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), v38, v39, v40);
  }
  memset_0(v70, 0, sizeof(v70));
  v41 = 4;
  v42 = (char *)this + 4280;
  v43 = (_OWORD *)((char *)this + 4280);
  v44 = v70;
  do
  {
    v45 = v44[1];
    *v43 = *v44;
    v46 = v44[2];
    v43[1] = v45;
    v47 = v44[3];
    v43[2] = v46;
    v48 = v44[4];
    v43[3] = v47;
    v49 = v44[5];
    v43[4] = v48;
    v50 = v44[6];
    v43[5] = v49;
    v51 = v44[7];
    v44 += 8;
    v43[6] = v50;
    v43[7] = v51;
    v43 += 8;
    --v41;
  }
  while ( v41 );
  v52 = v44[1];
  *v43 = *v44;
  v53 = v44[2];
  v43[1] = v52;
  v54 = v44[3];
  v43[2] = v53;
  v55 = v44[4];
  v56 = (void *)*((_QWORD *)this + 6);
  v43[3] = v54;
  v43[4] = v55;
  if ( (int)WerpGetDebugger(v56) >= 0 && (*v42 & 1) == 0 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( (*(_BYTE *)(*((_QWORD *)this + 5) + 236LL) & 2) == 0 && (*v42 & 1) != 0 && *((_WORD *)this + 2142) && !v37 )
  {
    v58 = 0;
    if ( (*v42 & 2) != 0 )
      goto LABEL_95;
    if ( packageFullName[0] )
    {
      matched = CCrashReport::MatchRemoteEnvironmentVariable(*((HANDLE *)this + 6), v57, packageFullName);
      v58 = matched >= 0;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids, matched >= 0);
    }
    if ( (*v42 & 2) != 0 || v58 )
    {
LABEL_95:
      if ( (int)WerpLaunchAeDebug(*((HANDLE *)this + 6), *((HANDLE *)this + 7), (__int64)this + 4280) >= 0 )
      {
        v11 = 1769472;
        *(_DWORD *)(*((_QWORD *)this + 5) + 176LL) = 1769472;
        goto LABEL_119;
      }
    }
  }
  if ( packageFullName[0] )
  {
    AcquireSRWLockExclusive((PSRWLOCK)this + 1317);
    v60 = *((_QWORD *)this + 1318) ? -1073740528 : HamConnectToServer(HamConnector::HamActivityCallback);
    ReleaseSRWLockExclusive((PSRWLOCK)this + 1317);
    if ( v60 >= 0 )
    {
      HamConnector::AddExemptionForProcess(
        (PSRWLOCK)this + 1317,
        dwProcessId,
        *((void **)this + 96),
        (*(_DWORD *)(*((_QWORD *)this + 5) + 236LL) & 4) == 0);
      *((_DWORD *)this + 1219) = GetTickCount();
    }
  }
  v61 = (void **)((char *)this + 4928);
  v11 = WerpAcquireReportingForProcess(*((unsigned int *)this + 184), (char *)this + 4920, (char *)this + 4928);
  if ( v11 < 0 )
  {
    v62 = *v61;
    *v61 = 0;
    if ( (unsigned __int64)v62 + 1 > 1 )
      CloseHandle(v62);
  }
  if ( v11 == -2145681404 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids,
        *((unsigned int *)this + 184));
    *(_DWORD *)(*((_QWORD *)this + 5) + 176LL) = -2145681404;
    goto LABEL_41;
  }
  if ( v11 < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_119;
    v14 = 20;
    goto LABEL_67;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      21,
      WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids,
      *((unsigned int *)this + 184));
  CCrashReport::SuspendProcess(this);
  CCrashReport::ReportCrashSEH(this);
LABEL_119:
  v63 = (void *)*((_QWORD *)this + 616);
  *((_QWORD *)this + 616) = 0;
  if ( (unsigned __int64)v63 + 1 > 1 )
    CloseHandle(v63);
  v64 = (void *)*((_QWORD *)this + 615);
  *((_QWORD *)this + 615) = 0;
  if ( (unsigned __int64)v64 + 1 > 1 )
    CloseHandle(v64);
  CCrashReport::ResumeProcess(this);
  HamConnector::Disconnect((PSRWLOCK)this + 1317);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180014c34  mov     [rsp-8+arg_18], rbx
0x180014c39  push    rbp
0x180014c3a  push    rsi
0x180014c3b  push    rdi
0x180014c3c  push    r12
0x180014c3e  push    r13
0x180014c40  push    r14
0x180014c42  push    r15
0x180014c44  lea     rbp, [rsp-2B0h]
0x180014c4c  sub     rsp, 3B0h
0x180014c53  mov     rax, cs:__security_cookie
0x180014c5a  xor     rax, rsp
0x180014c5d  mov     [rbp+2E0h+var_40], rax
0x180014c64  xor     r13d, r13d
0x180014c67  mov     rdi, r9
0x180014c6a  mov     [rsp+3E0h+dwProcessId], r13d
0x180014c6f  mov     r14d, r8d
0x180014c72  mov     [rsp+3E0h+var_3A0], r13
0x180014c77  mov     r12d, edx
0x180014c7a  mov     [rsp+3E0h+packageFullNameLength], r13d
0x180014c7f  mov     rbx, rcx
0x180014c82  call    IsImmDisableIMEPresent
0x180014c87  test    al, al
0x180014c89  jz      short loc_180014C94
0x180014c8b  or      ecx, 0FFFFFFFFh; DWORD
0x180014c8e  call    cs:__imp_ImmDisableIME
0x180014c94  mov     r8d, r14d; dwProcessId
0x180014c97  xor     edx, edx; bInheritHandle
0x180014c99  mov     ecx, 1FFFFFh; dwDesiredAccess
0x180014c9e  call    cs:__imp_OpenProcess
0x180014ca4  mov     rcx, [rbx+2E8h]; hObject
0x180014cab  mov     r15d, 1
0x180014cb1  mov     [rbx+2E8h], rax
0x180014cb8  lea     rax, [rcx+1]
0x180014cbc  cmp     rax, r15
0x180014cbf  jbe     short loc_180014CC7
0x180014cc1  call    cs:__imp_CloseHandle
0x180014cc7  mov     rax, [rbx+2E8h]
0x180014cce  add     rax, r15
0x180014cd1  cmp     rax, r15
0x180014cd4  ja      short loc_180014D37
0x180014cd6  call    cs:__imp_GetLastError
0x180014cdc  mov     edi, eax
0x180014cde  test    eax, eax
0x180014ce0  jle     short loc_180014CEB
0x180014ce2  movzx   edi, ax
0x180014ce5  or      edi, 80070000h
0x180014ceb  test    edi, edi
0x180014ced  mov     eax, 80004005h
0x180014cf2  cmovns  edi, eax
0x180014cf5  mov     rcx, cs:WPP_GLOBAL_Control
0x180014cfc  lea     rsi, WPP_GLOBAL_Control
0x180014d03  cmp     rcx, rsi
0x180014d06  jz      loc_180015399
0x180014d0c  test    [rcx+1Ch], r15b
0x180014d10  jz      loc_180015399
0x180014d16  mov     rcx, [rcx+10h]
0x180014d1a  lea     r8, WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids
0x180014d21  mov     edx, 0Ah
0x180014d26  mov     dword ptr [rsp+3E0h+ReturnLength], edi
0x180014d2a  mov     r9d, r14d
0x180014d2d  call    WPP_SF_Dd
0x180014d32  jmp     loc_180015399
0x180014d37  test    rdi, rdi
0x180014d3a  jnz     short loc_180014D41
0x180014d3c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180014d41  mov     rcx, rbx; this
0x180014d44  mov     [rbx+2F0h], rdi
0x180014d4b  call    ?LoadCrashData@CCrashReport@@AEAAJXZ; CCrashReport::LoadCrashData(void)
0x180014d50  mov     edi, eax
0x180014d52  test    eax, eax
0x180014d54  jns     short loc_180014D94
0x180014d56  mov     rcx, cs:WPP_GLOBAL_Control
0x180014d5d  lea     rsi, WPP_GLOBAL_Control
0x180014d64  cmp     rcx, rsi
0x180014d67  jz      loc_180015399
0x180014d6d  test    [rcx+1Ch], r15b
0x180014d71  jz      loc_180015399
0x180014d77  mov     edx, 0Bh
0x180014d7c  mov     r9d, eax
0x180014d7f  mov     rcx, [rcx+10h]
0x180014d83  lea     r8, WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids
0x180014d8a  call    WPP_SF_d
0x180014d8f  jmp     loc_180015399
0x180014d94  mov     rcx, [rbx+30h]; ProcessHandle
0x180014d98  call    ?UtilIsProcessAService@@YAJPEAX@Z; UtilIsProcessAService(void *)
0x180014d9d  mov     ecx, r13d
0x180014da0  test    eax, eax
0x180014da2  setz    cl
0x180014da5  mov     [rbx], ecx
0x180014da7  mov     rcx, [rbx+30h]; ProcessHandle
0x180014dab  call    ?UtilIsProcessNative@@YAJPEAX@Z; UtilIsProcessNative(void *)
0x180014db0  mov     ecx, r13d
0x180014db3  mov     [rsp+3E0h+ProcessInformation], r13d
0x180014db8  test    eax, eax
0x180014dba  mov     [rsp+3E0h+ReturnLength], r13; ReturnLength
0x180014dbf  mov     r14d, 4
0x180014dc5  lea     r8, [rsp+3E0h+ProcessInformation]; ProcessInformation
0x180014dca  setz    cl
0x180014dcd  mov     r9d, r14d; ProcessInformationLength
0x180014dd0  mov     [rbx+4], ecx
0x180014dd3  mov     rcx, [rbx+30h]; ProcessHandle
0x180014dd7  lea     edx, [r14+19h]; ProcessInformationClass
0x180014ddb  call    cs:__imp_NtQueryInformationProcess
0x180014de1  mov     r15d, 80070000h
0x180014de7  lea     rsi, WPP_GLOBAL_Control
0x180014dee  mov     edi, eax
0x180014df0  test    eax, eax
0x180014df2  jns     short loc_180014E3D
0x180014df4  mov     rcx, cs:WPP_GLOBAL_Control
0x180014dfb  cmp     rcx, rsi
0x180014dfe  jz      short loc_180014E1D
0x180014e00  test    byte ptr [rcx+1Ch], 1
0x180014e04  jz      short loc_180014E1D
0x180014e06  mov     rcx, [rcx+10h]
0x180014e0a  lea     edx, [r14+58h]
0x180014e0e  mov     r9d, eax
0x180014e11  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x180014e18  call    WPP_SF_d
0x180014e1d  mov     ecx, edi; Status
0x180014e1f  call    cs:__imp_RtlNtStatusToDosError
0x180014e25  mov     ecx, eax
0x180014e27  test    eax, eax
0x180014e29  jle     short loc_180014E31
0x180014e2b  movzx   ecx, ax
0x180014e2e  or      ecx, r15d
0x180014e31  test    ecx, ecx
0x180014e33  mov     eax, 80004005h
0x180014e38  cmovns  ecx, eax
0x180014e3b  jmp     short loc_180014E48
0x180014e3d  cmp     [rsp+3E0h+ProcessInformation], r13d
0x180014e42  mov     ecx, r13d
0x180014e45  setz    cl
0x180014e48  mov     eax, r13d
0x180014e4b  test    ecx, ecx
0x180014e4d  setz    al
0x180014e50  mov     [rbx+0Ch], eax
0x180014e53  call    IsGetShellWindowPresent
0x180014e58  test    al, al
0x180014e5a  jz      short loc_180014E8E
0x180014e5c  call    IsGetShellWindowPresent
0x180014e61  test    al, al
0x180014e63  jz      short loc_180014E8E
0x180014e65  call    cs:__imp_GetShellWindow
0x180014e6b  mov     rcx, rax; hWnd
0x180014e6e  lea     rdx, [rsp+3E0h+dwProcessId]; lpdwProcessId
0x180014e73  call    cs:__imp_GetWindowThreadProcessId
0x180014e79  test    eax, eax
0x180014e7b  jz      short loc_180014E8E
0x180014e7d  mov     eax, [rsp+3E0h+dwProcessId]
0x180014e81  cmp     [rbx+2E0h], eax
0x180014e87  mov     eax, 1
0x180014e8c  jz      short loc_180014E91
0x180014e8e  mov     eax, r13d
0x180014e91  mov     rcx, [rbx+30h]; void *
0x180014e95  mov     [rbx+8], eax
0x180014e98  call    ?UtilReadErrorModeForProcess@@YAKPEAX@Z; UtilReadErrorModeForProcess(void *)
0x180014e9d  test    al, 2
0x180014e9f  jz      short loc_180014EDE
0x180014ea1  mov     rcx, cs:WPP_GLOBAL_Control
0x180014ea8  cmp     rcx, rsi
0x180014eab  jz      short loc_180014EC8
0x180014ead  test    [rcx+1Ch], r14b
0x180014eb1  jz      short loc_180014EC8
0x180014eb3  mov     edx, 0Ch
0x180014eb8  mov     rcx, [rcx+10h]
0x180014ebc  lea     r8, WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids
0x180014ec3  call    WPP_SF_
0x180014ec8  mov     rax, [rbx+28h]
0x180014ecc  mov     dword ptr [rax+0B0h], 1B0003h
0x180014ed6  mov     edi, r13d
0x180014ed9  jmp     loc_180015399
0x180014ede  mov     rdx, [rbx+38h]; ThreadHandle
0x180014ee2  lea     r8, [rsp+3E0h+ProcessInformation]; lpBuffer
0x180014ee7  mov     rcx, [rbx+30h]; hProcess
0x180014eeb  mov     r9d, 16B0h; unsigned int
0x180014ef1  mov     [rsp+3E0h+ProcessInformation], r13d
0x180014ef6  mov     dword ptr [rsp+3E0h+ReturnLength], r14d; unsigned int
0x180014efb  call    ?UtilReadTEB@@YAJPEAX00KK@Z; UtilReadTEB(void *,void *,void *,ulong,ulong)
0x180014f00  test    eax, eax
0x180014f02  jns     short loc_180014F7C
0x180014f04  mov     rcx, cs:WPP_GLOBAL_Control
0x180014f0b  cmp     rcx, rsi
0x180014f0e  jz      short loc_180014F2E
0x180014f10  test    byte ptr [rcx+1Ch], 1
0x180014f14  jz      short loc_180014F2E
0x180014f16  mov     rcx, [rcx+10h]
0x180014f1a  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x180014f21  mov     edx, 5Dh ; ']'
0x180014f26  mov     r9d, eax
0x180014f29  call    WPP_SF_d
0x180014f2e  mov     rcx, [rbx+30h]; hProcess
0x180014f32  lea     rdi, [rbx+1Ch]
0x180014f36  mov     rdx, rdi; pdwFlags
0x180014f39  call    cs:__imp_WerGetFlags
0x180014f3f  test    eax, eax
0x180014f41  js      short loc_180014FA7
0x180014f43  mov     rcx, cs:WPP_GLOBAL_Control
0x180014f4a  cmp     rcx, rsi
0x180014f4d  jz      short loc_180014F6D
0x180014f4f  test    byte ptr [rcx+1Ch], 8
0x180014f53  jz      short loc_180014F6D
0x180014f55  mov     r9d, [rdi]
0x180014f58  lea     r8, WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids
0x180014f5f  mov     rcx, [rcx+10h]
0x180014f63  mov     edx, 0Eh
0x180014f68  call    WPP_SF_d
0x180014f6d  mov     ecx, [rdi]
0x180014f6f  mov     eax, ecx
0x180014f71  sar     eax, 1Fh
0x180014f74  and     eax, 2
0x180014f77  or      [rbx+20h], eax
0x180014f7a  jmp     short loc_180014FD7
0x180014f7c  test    byte ptr [rsp+3E0h+ProcessInformation], 20h
0x180014f81  jz      short loc_180014F2E
0x180014f83  mov     rcx, cs:WPP_GLOBAL_Control
0x180014f8a  cmp     rcx, rsi
0x180014f8d  jz      loc_180014EC8
0x180014f93  test    [rcx+1Ch], r14b
0x180014f97  jz      loc_180014EC8
0x180014f9d  mov     edx, 0Dh
0x180014fa2  jmp     loc_180014EB8
0x180014fa7  mov     rcx, cs:WPP_GLOBAL_Control
0x180014fae  cmp     rcx, rsi
0x180014fb1  jz      short loc_180014FD1
0x180014fb3  test    byte ptr [rcx+1Ch], 2
0x180014fb7  jz      short loc_180014FD1
0x180014fb9  mov     rcx, [rcx+10h]
0x180014fbd  lea     r8, WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids
0x180014fc4  mov     edx, 0Fh
0x180014fc9  mov     r9d, eax
0x180014fcc  call    WPP_SF_d
0x180014fd1  mov     [rdi], r13d
0x180014fd4  mov     ecx, r13d
0x180014fd7  cmp     [rbx+4], r13d
0x180014fdb  jnz     short loc_180014FEE
0x180014fdd  cmp     [rbx+0Ch], r13d
0x180014fe1  jnz     short loc_180014FEE
0x180014fe3  mov     eax, r13d
0x180014fe6  test    ecx, 600h
0x180014fec  jz      short loc_180014FF3
0x180014fee  mov     eax, 1
0x180014ff3  or      [rbx+20h], eax
0x180014ff6  mov     edx, 10h
0x180014ffb  mov     rax, [rbx+28h]
0x180014fff  test    [rax+0ECh], dl
0x180015005  jz      short loc_18001503D
0x180015007  cmp     [rbx+1348h], r13
0x18001500e  jnz     short loc_18001503D
0x180015010  mov     edi, 801B8007h
0x180015015  mov     [rax+0B0h], edi
0x18001501b  mov     rcx, cs:WPP_GLOBAL_Control
0x180015022  cmp     rcx, rsi
0x180015025  jz      loc_180015399
0x18001502b  test    [rcx+1Ch], r14b
0x18001502f  jz      loc_180015399
0x180015035  mov     r9d, edi
0x180015038  jmp     loc_180014D7F
0x18001503d  mov     rcx, [rbx+30h]; hProcess
0x180015041  lea     r8, [rbp+2E0h+packageFullName]; packageFullName
0x180015048  lea     rdx, [rsp+3E0h+packageFullNameLength]; packageFullNameLength
0x18001504d  mov     [rsp+3E0h+packageFullNameLength], 80h
0x180015055  call    cs:__imp_GetPackageFullName
0x18001505b  test    eax, eax
0x18001505d  jle     short loc_180015067
0x18001505f  movzx   eax, ax
0x180015062  or      eax, r15d
0x180015065  test    eax, eax
0x180015067  jns     short loc_180015071
0x180015069  mov     [rbp+2E0h+packageFullName], r13w
0x180015071  mov     rcx, [rbx+30h]; void *
0x180015075  lea     rdx, [rsp+3E0h+var_3A0]; struct _WER_RUNTIME_DLL **
0x18001507a  mov     edi, r13d
0x18001507d  call    ?WerpGetRuntimeDllsListStart@@YAJPEAXPEAPEAU_WER_RUNTIME_DLL@@@Z; WerpGetRuntimeDllsListStart(void *,_WER_RUNTIME_DLL * *)
0x180015082  mov     r15d, 1
0x180015088  test    eax, eax
0x18001508a  js      short loc_180015095
0x18001508c  cmp     [rsp+3E0h+var_3A0], r13
0x180015091  cmovnz  edi, r15d
0x180015095  mov     rcx, cs:WPP_GLOBAL_Control
0x18001509c  cmp     rcx, rsi
0x18001509f  jz      short loc_1800150C4
0x1800150a1  test    [rcx+1Ch], r14b
0x1800150a5  jz      short loc_1800150C4
0x1800150a7  mov     rcx, [rcx+10h]
0x1800150ab  lea     rax, aFalse; "false"
0x1800150b2  test    edi, edi
0x1800150b4  lea     r9, aTrue; "true"
0x1800150bb  cmovz   r9, rax
0x1800150bf  call    WPP_SF_s
0x1800150c4  xor     edx, edx; Val
0x1800150c6  lea     rcx, [rsp+3E0h+var_390]; void *
0x1800150cb  mov     r8d, 250h; Size
0x1800150d1  call    memset_0
0x1800150d6  mov     edx, 4
0x1800150db  lea     r14, [rbx+10B8h]
0x1800150e2  mov     rax, r14
0x1800150e5  lea     rcx, [rsp+3E0h+var_390]
0x1800150ea  lea     r8d, [rdx+7Ch]
0x1800150ee  movups  xmm0, xmmword ptr [rcx]
  ... truncated ...
```
