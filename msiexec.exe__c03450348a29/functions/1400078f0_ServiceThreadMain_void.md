# ServiceThreadMain(void *)

- ea: `0x1400078f0`
- end: `0x1400080bc`
- name: `?ServiceThreadMain@@YAKPEAX@Z`
- size: `1996`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x140003aec`
- `0x140003ba0`
- `0x140005014`
- `0x1400057a0`
- `0x14000580c`
- `0x140006d4c`
- `0x140007110`
- `0x140007374`
- `0x140007500`
- `0x1400078f0`
- `0x140008280`
- `0x140009820`
- `0x14000a010`

## import_xrefs

- `ADVAPI32!MakeAbsoluteSD` at `0x140007ac0`
- `ADVAPI32!MakeAbsoluteSD` at `0x140007ac0`
- `ADVAPI32!RegOpenKeyExW` at `0x140007967`
- `ADVAPI32!RegOpenKeyExW` at `0x140007967`
- `ADVAPI32!RegCloseKey` at `0x140007975`
- `ADVAPI32!RegCloseKey` at `0x140007975`
- `KERNEL32!EnterCriticalSection` at `0x140007f6d`
- `KERNEL32!EnterCriticalSection` at `0x140007f9c`
- `KERNEL32!EnterCriticalSection` at `0x140007fcb`
- `KERNEL32!EnterCriticalSection` at `0x140007f6d`
- `KERNEL32!EnterCriticalSection` at `0x140007f9c`
- `KERNEL32!EnterCriticalSection` at `0x140007fcb`
- `KERNEL32!LeaveCriticalSection` at `0x140007f8a`
- `KERNEL32!LeaveCriticalSection` at `0x140007fb9`
- `KERNEL32!LeaveCriticalSection` at `0x140007fe8`
- `KERNEL32!LeaveCriticalSection` at `0x140007f8a`
- `KERNEL32!LeaveCriticalSection` at `0x140007fb9`
- `KERNEL32!LeaveCriticalSection` at `0x140007fe8`
- `KERNEL32!InitializeCriticalSection` at `0x140007c98`
- `KERNEL32!InitializeCriticalSection` at `0x140007c98`
- `KERNEL32!CreateEventW` at `0x140007cb6`
- `KERNEL32!CreateEventW` at `0x140007ccd`
- `KERNEL32!CreateEventW` at `0x140007cb6`
- `KERNEL32!CreateEventW` at `0x140007ccd`
- `KERNEL32!GetLastError` at `0x140007ad4`
- `KERNEL32!GetLastError` at `0x140007b25`
- `KERNEL32!GetLastError` at `0x140007c1b`
- `KERNEL32!GetLastError` at `0x140007d11`
- `KERNEL32!GetLastError` at `0x140007d4a`
- `KERNEL32!GetLastError` at `0x140007edd`
- `KERNEL32!GetLastError` at `0x140007ee3`
- `KERNEL32!GetLastError` at `0x140007f37`
- `KERNEL32!GetLastError` at `0x140007f4b`
- `KERNEL32!GetLastError` at `0x140007ad4`
- `KERNEL32!GetLastError` at `0x140007b25`
- `KERNEL32!GetLastError` at `0x140007c1b`
- `KERNEL32!GetLastError` at `0x140007d11`
- `KERNEL32!GetLastError` at `0x140007d4a`
- `KERNEL32!GetLastError` at `0x140007edd`
- `KERNEL32!GetLastError` at `0x140007ee3`
- `KERNEL32!GetLastError` at `0x140007f37`
- `KERNEL32!GetLastError` at `0x140007f4b`
- `KERNEL32!CloseHandle` at `0x140007f7a`
- `KERNEL32!CloseHandle` at `0x140007fa9`
- `KERNEL32!CloseHandle` at `0x140007fd8`
- `KERNEL32!CloseHandle` at `0x140007f7a`
- `KERNEL32!CloseHandle` at `0x140007fa9`
- `KERNEL32!CloseHandle` at `0x140007fd8`
- `KERNEL32!DeleteCriticalSection` at `0x14000800d`
- `KERNEL32!DeleteCriticalSection` at `0x14000800d`
- `USER32!MsgWaitForMultipleObjects` at `0x140007e46`
- `USER32!MsgWaitForMultipleObjects` at `0x140007e46`
- `USER32!DispatchMessageW` at `0x140007e6f`
- `USER32!DispatchMessageW` at `0x140007e6f`
- `USER32!PeekMessageW` at `0x140007e85`
- `USER32!PeekMessageW` at `0x140007e85`
- `USER32!TranslateMessage` at `0x140007e65`
- `USER32!TranslateMessage` at `0x140007e65`
- `USER32!PostThreadMessageW` at `0x140007f16`
- `USER32!PostThreadMessageW` at `0x140007f16`
- `ole32!CoUninitialize` at `0x1400079c4`
- `ole32!CoUninitialize` at `0x140007ace`
- `ole32!CoUninitialize` at `0x140007c32`
- `ole32!CoUninitialize` at `0x140007ff2`
- `ole32!CoUninitialize` at `0x140008055`
- `ole32!CoUninitialize` at `0x1400079c4`
- `ole32!CoUninitialize` at `0x140007ace`
- `ole32!CoUninitialize` at `0x140007c32`
- `ole32!CoUninitialize` at `0x140007ff2`
- `ole32!CoUninitialize` at `0x140008055`
- `ole32!CoRegisterClassObject` at `0x140007db6`
- `ole32!CoRegisterClassObject` at `0x140007db6`
- `ole32!CoRevokeClassObject` at `0x140007f26`
- `ole32!CoRevokeClassObject` at `0x140007f26`

## string_xrefs

- `0x140007959`: `CLSID`
- `0x140007b19`: `ServiceThreadMain: CoInitializeSecurity failed`
- `0x140007b76`: `CoCreateInstance of CLSID_GlobalOptions failed.`
- `0x140007bc9`: `Set of COMGLB_UNMARSHALING_POLICY failed.`
- `0x140007c0f`: `ServiceThreadMain: CreateSD for CreateWaitableTimer failed.`
- `0x140007f3d`: `ServiceThreadMain: CreateEvent failed.`
- `0x140007d17`: `ServiceThreadMain: CreateWaitableTimer failed.`
- `0x140007d50`: `ServiceThreadMain: SetWaitableTimer failed.`
- `0x140007f2e`: `ServiceThreadMain: Class registration failed`

## pseudocode

```c
__int64 __fastcall ServiceThreadMain(ServiceStatus *Parameter)
{
  int v2; // edi
  unsigned int SecurityDescriptor; // ebx
  unsigned int v4; // eax
  ServiceStatus *v5; // rcx
  DWORD LastError; // eax
  ServiceStatus *v7; // rcx
  signed int v8; // esi
  BYTE *v9; // rcx
  ServiceStatus *v10; // rcx
  HANDLE EventW; // rax
  void *v12; // rax
  unsigned int v13; // eax
  wchar_t *v14; // rcx
  ServiceStatus *v15; // rcx
  char v16; // r14
  unsigned int i; // esi
  ServiceStatus *v18; // rcx
  DWORD v19; // eax
  ServiceStatus *v20; // rcx
  DWORD v21; // eax
  DWORD v22; // eax
  ServiceStatus *v23; // rcx
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int *phkResulta; // [rsp+20h] [rbp-E0h]
  unsigned int phkResultb; // [rsp+20h] [rbp-E0h]
  DWORD v27; // [rsp+60h] [rbp-A0h] BYREF
  DWORD dwPrimaryGroupSize; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD dwOwnerSize; // [rsp+68h] [rbp-98h] BYREF
  DWORD dwSaclSize; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD dwDaclSize; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v32[2]; // [rsp+78h] [rbp-88h] BYREF
  DWORD dwAbsoluteSecurityDescriptorSize; // [rsp+80h] [rbp-80h] BYREF
  int v34; // [rsp+84h] [rbp-7Ch] BYREF
  HKEY hKey; // [rsp+88h] [rbp-78h] BYREF
  __int64 v36; // [rsp+90h] [rbp-70h] BYREF
  __int128 v37; // [rsp+98h] [rbp-68h] BYREF
  __int64 v38; // [rsp+A8h] [rbp-58h]
  MSG Msg; // [rsp+B0h] [rbp-50h] BYREF
  PSECURITY_DESCRIPTOR pAbsoluteSecurityDescriptor[66]; // [rsp+E0h] [rbp-20h] BYREF
  PSID pPrimaryGroup[66]; // [rsp+2F0h] [rbp+1F0h] BYREF
  PSID pOwner[66]; // [rsp+500h] [rbp+400h] BYREF
  PACL pSacl[66]; // [rsp+710h] [rbp+610h] BYREF
  PACL pDacl[66]; // [rsp+920h] [rbp+820h] BYREF
  HANDLE pHandles[4]; // [rsp+B30h] [rbp+A30h] BYREF
  _BYTE pSelfRelativeSecurityDescriptor[512]; // [rsp+B50h] [rbp+A50h] BYREF

  hKey = 0;
  if ( !(unsigned int)ServiceStatus::ReportStatusToSCMgr(Parameter, 2u, 0, 0x7530u, phkResult) )
    return 0;
  if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, L"CLSID", 0, 0x20019u, &hKey) )
    RegCloseKey(hKey);
  v2 = ((__int64 (__fastcall *)(_QWORD, _QWORD))OLE32::CoInitializeEx)(0, 0);
  SetTestFlags();
  v27 = 512;
  RefCountedTokenPrivilegesCore();
  SecurityDescriptor = GetSecurityDescriptor(pSelfRelativeSecurityDescriptor, &v27, 5);
  if ( SecurityDescriptor )
  {
    if ( v2 >= 0 )
      CoUninitialize();
    return SecurityDescriptor;
  }
  dwAbsoluteSecurityDescriptorSize = v27;
  dwDaclSize = v27;
  dwSaclSize = v27;
  dwOwnerSize = v27;
  dwPrimaryGroupSize = v27;
  CTempBuffer<char,512>::CTempBuffer<char,512>(pAbsoluteSecurityDescriptor);
  CTempBuffer<char,512>::CTempBuffer<char,512>(pDacl);
  CTempBuffer<char,512>::CTempBuffer<char,512>(pSacl);
  CTempBuffer<char,512>::CTempBuffer<char,512>(pOwner);
  CTempBuffer<char,512>::CTempBuffer<char,512>(pPrimaryGroup);
  if ( !pAbsoluteSecurityDescriptor[0] || !pDacl[0] || !pSacl[0] || !pOwner[0] || !pPrimaryGroup[0] )
  {
    if ( v2 >= 0 )
      CoUninitialize();
    CTempBuffer<char,512>::~CTempBuffer<char,512>(pPrimaryGroup);
    CTempBuffer<char,512>::~CTempBuffer<char,512>(pOwner);
    CTempBuffer<char,512>::~CTempBuffer<char,512>(pSacl);
    CTempBuffer<char,512>::~CTempBuffer<char,512>(pDacl);
    CTempBuffer<char,512>::~CTempBuffer<char,512>(pAbsoluteSecurityDescriptor);
    return 14;
  }
  if ( !MakeAbsoluteSD(
          pSelfRelativeSecurityDescriptor,
          pAbsoluteSecurityDescriptor[0],
          &dwAbsoluteSecurityDescriptorSize,
          pDacl[0],
          &dwDaclSize,
          pSacl[0],
          &dwSaclSize,
          pOwner[0],
          &dwOwnerSize,
          pPrimaryGroup[0],
          &dwPrimaryGroupSize) )
  {
    if ( v2 >= 0 )
      CoUninitialize();
    SecurityDescriptor = GetLastError();
    goto LABEL_33;
  }
  LODWORD(phkResulta) = 2;
  v4 = ((__int64 (__fastcall *)(PSECURITY_DESCRIPTOR, __int64, _QWORD, _QWORD))OLE32::CoInitializeSecurity)(
         pAbsoluteSecurityDescriptor[0],
         0xFFFFFFFFLL,
         0,
         0);
  if ( v4 )
  {
    ReportErrorToDebugOutput((BYTE *)L"ServiceThreadMain: CoInitializeSecurity failed", v4);
    LastError = GetLastError();
LABEL_29:
    ServiceStatus::ReportStatusToSCMgr(v7, 1u, LastError, 0, (unsigned int)phkResulta);
LABEL_30:
    if ( v2 < 0 )
    {
LABEL_32:
      SecurityDescriptor = 0;
LABEL_33:
      CTempBuffer<char,512>::~CTempBuffer<char,512>(pPrimaryGroup);
      CTempBuffer<char,512>::~CTempBuffer<char,512>(pOwner);
      CTempBuffer<char,512>::~CTempBuffer<char,512>(pSacl);
      CTempBuffer<char,512>::~CTempBuffer<char,512>(pDacl);
      CTempBuffer<char,512>::~CTempBuffer<char,512>(pAbsoluteSecurityDescriptor);
      return SecurityDescriptor;
    }
LABEL_31:
    CoUninitialize();
    goto LABEL_32;
  }
  if ( v2 >= 0 )
  {
    *(_QWORD *)v32 = 0;
    phkResulta = v32;
    v8 = ((__int64 (__fastcall *)(GUID *, _QWORD, __int64, GUID *))OLE32::CoCreateInstance)(
           &CLSID_GlobalOptions,
           0,
           1,
           &GUID_0000015b_0000_0000_c000_000000000046);
    if ( v8 < 0 )
    {
      v9 = (BYTE *)L"CoCreateInstance of CLSID_GlobalOptions failed.";
LABEL_23:
      ReportErrorToDebugOutput(v9, v8);
      ServiceStatus::ReportStatusToSCMgr(v10, 1u, v8, 0, (unsigned int)v32);
      goto LABEL_31;
    }
    v8 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)v32 + 24LL))(*(_QWORD *)v32, 5, 1);
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v32 + 16LL))(*(_QWORD *)v32);
    *(_QWORD *)v32 = 0;
    if ( v8 < 0 )
    {
      v9 = (BYTE *)L"Set of COMGLB_UNMARSHALING_POLICY failed.";
      goto LABEL_23;
    }
  }
  if ( !(unsigned int)ServiceStatus::ReportStatusToSCMgr(v5, 2u, 0, 0x7530u, (unsigned int)phkResulta) )
    goto LABEL_30;
  v34 = 0;
  v37 = 0;
  LODWORD(v37) = 24;
  v38 = 0;
  if ( (unsigned int)GetSecureSecurityDescriptor((char *)&v37 + 8, &v34) )
  {
    ReportErrorToDebugOutput((BYTE *)L"ServiceThreadMain: CreateSD for CreateWaitableTimer failed.", 0);
    LastError = GetLastError();
    goto LABEL_29;
  }
  g_hCallbackEvent = 0;
  g_hFatalShutdownEvent = 0;
  g_hShutdownTimer = 0;
  InitializeCriticalSection(&g_csServiceHandles);
  v36 = -3000000000LL;
  g_hFatalShutdownEvent = CreateEventW(0, 1, 0, 0);
  EventW = CreateEventW(0, 0, 0, 0);
  g_hCallbackEvent = EventW;
  if ( !g_hFatalShutdownEvent || !EventW )
  {
    v13 = GetLastError();
    v14 = (wchar_t *)L"ServiceThreadMain: CreateEvent failed.";
    goto LABEL_68;
  }
  v12 = (void *)((__int64 (__fastcall *)(__int128 *, __int64, _QWORD))KERNEL32::CreateWaitableTimerW)(&v37, 1, 0);
  g_hShutdownTimer = v12;
  if ( !v12 )
  {
    v13 = GetLastError();
    v14 = L"ServiceThreadMain: CreateWaitableTimer failed.";
LABEL_68:
    ReportErrorToDebugOutput((BYTE *)v14, v13);
    v22 = GetLastError();
    ServiceStatus::ReportStatusToSCMgr(v23, 1u, v22, 0, (unsigned int)phkResulta);
    v16 = 0;
    goto LABEL_69;
  }
  LODWORD(phkResulta) = 0;
  if ( !(unsigned int)((__int64 (__fastcall *)(void *, __int64 *, _QWORD, _QWORD))KERNEL32::SetWaitableTimer)(
                        v12,
                        &v36,
                        0,
                        0) )
  {
    v13 = GetLastError();
    v14 = L"ServiceThreadMain: SetWaitableTimer failed.";
    goto LABEL_68;
  }
  v16 = 1;
  for ( i = 0; (int)i < 1; ++i )
  {
    if ( !(unsigned int)ServiceStatus::ReportStatusToSCMgr(v15, 2u, 0, 0x7530u, (unsigned int)phkResulta) )
      goto LABEL_69;
    v13 = CoRegisterClassObject(&rgCLSID + i, (LPUNKNOWN)&g_rgcfModule + i, 0x15u, 1u, &g_rghRegClass + i);
    if ( v13 )
    {
      v14 = L"ServiceThreadMain: Class registration failed";
      goto LABEL_68;
    }
  }
  if ( !(unsigned int)ServiceStatus::ReportStatusToSCMgr(v15, 4u, 0, 0, (unsigned int)phkResulta) )
    goto LABEL_69;
  pHandles[0] = g_hShutdownTimer;
  pHandles[1] = g_hFatalShutdownEvent;
  pHandles[2] = g_hCallbackEvent;
  while ( !g_fWeWantToStop || !(unsigned int)FCanStopService() || g_cInstances > 0 )
  {
    v19 = MsgWaitForMultipleObjects(3u, pHandles, 0, 0xFFFFFFFF, 0x1CFFu);
    switch ( v19 )
    {
      case 3u:
        memset(&Msg, 0, sizeof(Msg));
        while ( PeekMessageW(&Msg, 0, 0, 0, 1u) )
        {
          TranslateMessage(&Msg);
          DispatchMessageW(&Msg);
        }
        continue;
      case 0u:
        g_fWeWantToStop = 1;
        if ( (unsigned int)FCanStopService() )
          goto LABEL_63;
        g_fWeWantToStop = 0;
        goto LABEL_57;
      case 1u:
LABEL_63:
        ServiceStatus::ReportStatusToSCMgr(v20, 3u, 0, 0, phkResultb);
        goto LABEL_64;
      case 2u:
        ServiceStatus::ReportStatusToSCMgr(v20, ServiceStatus.dwCurrentState, 0, 0, phkResultb);
LABEL_57:
        ResetServiceShutdownTimer();
        continue;
      case 0xFFFFFFFF:
        GetLastError();
        v21 = GetLastError();
        ReportErrorToDebugOutput((BYTE *)L"Wait Failed in MsgWait.", v21);
        goto LABEL_64;
    }
  }
LABEL_64:
  PostThreadMessageW(g_dwThreadId, 0x12u, 0, 0);
  v18 = (ServiceStatus *)g_rghRegClass;
  if ( g_rghRegClass )
    CoRevokeClassObject(g_rghRegClass);
LABEL_69:
  if ( g_hShutdownTimer )
  {
    EnterCriticalSection(&g_csServiceHandles);
    CloseHandle(g_hShutdownTimer);
    g_hShutdownTimer = 0;
    LeaveCriticalSection(&g_csServiceHandles);
  }
  if ( g_hFatalShutdownEvent )
  {
    EnterCriticalSection(&g_csServiceHandles);
    CloseHandle(g_hFatalShutdownEvent);
    g_hFatalShutdownEvent = 0;
    LeaveCriticalSection(&g_csServiceHandles);
  }
  if ( g_hCallbackEvent )
  {
    EnterCriticalSection(&g_csServiceHandles);
    CloseHandle(g_hCallbackEvent);
    g_hCallbackEvent = 0;
    LeaveCriticalSection(&g_csServiceHandles);
  }
  if ( v2 >= 0 )
    CoUninitialize();
  if ( v16 )
    ServiceStatus::ReportStatusToSCMgr(v18, 1u, 0, 0, phkResultb);
  DeleteCriticalSection(&g_csServiceHandles);
  CTempBuffer<char,512>::~CTempBuffer<char,512>(pPrimaryGroup);
  CTempBuffer<char,512>::~CTempBuffer<char,512>(pOwner);
  CTempBuffer<char,512>::~CTempBuffer<char,512>(pSacl);
  CTempBuffer<char,512>::~CTempBuffer<char,512>(pDacl);
  CTempBuffer<char,512>::~CTempBuffer<char,512>(pAbsoluteSecurityDescriptor);
  return 0;
}

```

## disassembly

```asm
0x1400078f0  push    rbp
0x1400078f2  push    rbx
0x1400078f3  push    rsi
0x1400078f4  push    rdi
0x1400078f5  push    r12
0x1400078f7  push    r13
0x1400078f9  push    r14
0x1400078fb  push    r15
0x1400078fd  lea     rbp, [rsp-0C68h]
0x140007905  sub     rsp, 0D68h
0x14000790c  mov     rax, cs:__security_cookie
0x140007913  xor     rax, rsp
0x140007916  mov     [rbp+0CA0h+var_50], rax
0x14000791d  xor     r15d, r15d
0x140007920  mov     r14d, 7530h
0x140007926  mov     r9d, r14d; unsigned int
0x140007929  mov     [rbp+0CA0h+hKey], r15
0x14000792d  xor     r8d, r8d; unsigned int
0x140007930  lea     r13d, [r15+2]
0x140007934  mov     edx, r13d; unsigned int
0x140007937  call    ?ReportStatusToSCMgr@ServiceStatus@@QEAAHKKKK@Z; ServiceStatus::ReportStatusToSCMgr(ulong,ulong,ulong,ulong)
0x14000793c  test    eax, eax
0x14000793e  jnz     short loc_140007947
0x140007940  xor     eax, eax
0x140007942  jmp     loc_140008099
0x140007947  lea     rax, [rbp+0CA0h+hKey]
0x14000794b  mov     r9d, 20019h; samDesired
0x140007951  xor     r8d, r8d; ulOptions
0x140007954  mov     [rsp+0DA0h+phkResult], rax; phkResult
0x140007959  lea     rdx, aClsid; "CLSID"
0x140007960  mov     rcx, 0FFFFFFFF80000000h; hKey
0x140007967  call    cs:__imp_RegOpenKeyExW
0x14000796d  test    eax, eax
0x14000796f  jnz     short loc_14000797B
0x140007971  mov     rcx, [rbp+0CA0h+hKey]; hKey
0x140007975  call    cs:__imp_RegCloseKey
0x14000797b  mov     rax, cs:?CoInitializeEx@OLE32@@3P6AJPEAXK@ZEA; long (*OLE32::CoInitializeEx)(void *,ulong)
0x140007982  xor     edx, edx
0x140007984  xor     ecx, ecx
0x140007986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000798b  mov     edi, eax
0x14000798d  call    ?SetTestFlags@@YA_NXZ; SetTestFlags(void)
0x140007992  mov     [rsp+0DA0h+var_D40], 200h
0x14000799a  call    ?RefCountedTokenPrivilegesCore@@YA_NW4itkpEnum@@_N@Z; RefCountedTokenPrivilegesCore(itkpEnum,bool)
0x14000799f  xor     r9d, r9d
0x1400079a2  lea     rdx, [rsp+0DA0h+var_D40]
0x1400079a7  lea     rcx, [rbp+0CA0h+pSelfRelativeSecurityDescriptor]
0x1400079ae  lea     r12d, [r9+5]
0x1400079b2  mov     r8d, r12d
0x1400079b5  call    ?GetSecurityDescriptor@@YAKPEADAEAKW4sdSecurityDescriptor@@W4Bool@@@Z; GetSecurityDescriptor(char *,ulong &,sdSecurityDescriptor,Bool)
0x1400079ba  mov     ebx, eax
0x1400079bc  test    eax, eax
0x1400079be  jz      short loc_1400079D1
0x1400079c0  test    edi, edi
0x1400079c2  js      short loc_1400079CA
0x1400079c4  call    cs:__imp_CoUninitialize
0x1400079ca  mov     eax, ebx
0x1400079cc  jmp     loc_140008099
0x1400079d1  mov     edx, [rsp+0DA0h+var_D40]
0x1400079d5  lea     rcx, [rbp+0CA0h+pAbsoluteSecurityDescriptor]
0x1400079d9  mov     [rbp+0CA0h+dwAbsoluteSecurityDescriptorSize], edx
0x1400079dc  mov     [rsp+0DA0h+dwDaclSize], edx
0x1400079e0  mov     [rsp+0DA0h+dwSaclSize], edx
0x1400079e4  mov     [rsp+0DA0h+dwOwnerSize], edx
0x1400079e8  mov     [rsp+0DA0h+dwPrimaryGroupSize], edx
0x1400079ec  call    ??0?$CTempBuffer@D$0CAA@@@QEAA@H@Z; CTempBuffer<char,512>::CTempBuffer<char,512>(int)
0x1400079f1  mov     edx, [rsp+0DA0h+dwDaclSize]
0x1400079f5  lea     rcx, [rbp+0CA0h+pDacl]
0x1400079fc  call    ??0?$CTempBuffer@D$0CAA@@@QEAA@H@Z; CTempBuffer<char,512>::CTempBuffer<char,512>(int)
0x140007a01  mov     edx, [rsp+0DA0h+dwSaclSize]
0x140007a05  lea     rcx, [rbp+0CA0h+var_690]
0x140007a0c  call    ??0?$CTempBuffer@D$0CAA@@@QEAA@H@Z; CTempBuffer<char,512>::CTempBuffer<char,512>(int)
0x140007a11  mov     edx, [rsp+0DA0h+dwOwnerSize]
0x140007a15  lea     rcx, [rbp+0CA0h+var_8A0]
0x140007a1c  call    ??0?$CTempBuffer@D$0CAA@@@QEAA@H@Z; CTempBuffer<char,512>::CTempBuffer<char,512>(int)
0x140007a21  mov     edx, [rsp+0DA0h+dwPrimaryGroupSize]
0x140007a25  lea     rcx, [rbp+0CA0h+var_AB0]
0x140007a2c  call    ??0?$CTempBuffer@D$0CAA@@@QEAA@H@Z; CTempBuffer<char,512>::CTempBuffer<char,512>(int)
0x140007a31  mov     rdx, [rbp+0CA0h+pAbsoluteSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x140007a35  test    rdx, rdx
0x140007a38  jz      loc_140008051
0x140007a3e  mov     r9, [rbp+0CA0h+pDacl]; pDacl
0x140007a45  test    r9, r9
0x140007a48  jz      loc_140008051
0x140007a4e  mov     rax, [rbp+0CA0h+var_690]
0x140007a55  test    rax, rax
0x140007a58  jz      loc_140008051
0x140007a5e  mov     rcx, [rbp+0CA0h+var_8A0]
0x140007a65  test    rcx, rcx
0x140007a68  jz      loc_140008051
0x140007a6e  mov     r8, [rbp+0CA0h+var_AB0]
0x140007a75  test    r8, r8
0x140007a78  jz      loc_140008051
0x140007a7e  lea     r10, [rsp+0DA0h+dwPrimaryGroupSize]
0x140007a83  mov     [rsp+0DA0h+lpdwPrimaryGroupSize], r10; lpdwPrimaryGroupSize
0x140007a88  mov     [rsp+0DA0h+pPrimaryGroup], r8; pPrimaryGroup
0x140007a8d  lea     r8, [rsp+0DA0h+dwOwnerSize]
0x140007a92  mov     [rsp+0DA0h+lpdwOwnerSize], r8; lpdwOwnerSize
0x140007a97  lea     r8, [rbp+0CA0h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x140007a9b  mov     [rsp+0DA0h+pOwner], rcx; pOwner
0x140007aa0  lea     rcx, [rsp+0DA0h+dwSaclSize]
0x140007aa5  mov     [rsp+0DA0h+lpdwSaclSize], rcx; lpdwSaclSize
0x140007aaa  lea     rcx, [rbp+0CA0h+pSelfRelativeSecurityDescriptor]; pSelfRelativeSecurityDescriptor
0x140007ab1  mov     [rsp+0DA0h+pSacl], rax; pSacl
0x140007ab6  lea     rax, [rsp+0DA0h+dwDaclSize]
0x140007abb  mov     [rsp+0DA0h+phkResult], rax; lpdwDaclSize
0x140007ac0  call    cs:__imp_MakeAbsoluteSD
0x140007ac6  test    eax, eax
0x140007ac8  jnz     short loc_140007AE1
0x140007aca  test    edi, edi
0x140007acc  js      short loc_140007AD4
0x140007ace  call    cs:__imp_CoUninitialize
0x140007ad4  call    cs:__imp_GetLastError
0x140007ada  mov     ebx, eax
0x140007adc  jmp     loc_140007C3B
0x140007ae1  mov     rcx, [rbp+0CA0h+pAbsoluteSecurityDescriptor]
0x140007ae5  xor     r9d, r9d
0x140007ae8  mov     rax, cs:?CoInitializeSecurity@OLE32@@3P6AJPEAXJPEAUtagSOLE_AUTHENTICATION_SERVICE@@PEAGKK0K0@ZEA; long (*OLE32::CoInitializeSecurity)(void *,long,tagSOLE_AUTHENTICATION_SERVICE *,ushort *,ulong,ulong,void *,ulong,void *)
0x140007aef  xor     r8d, r8d
0x140007af2  mov     [rsp+0DA0h+lpdwOwnerSize], r15
0x140007af7  or      edx, 0FFFFFFFFh
0x140007afa  mov     dword ptr [rsp+0DA0h+pOwner], r15d
0x140007aff  mov     [rsp+0DA0h+lpdwSaclSize], r15
0x140007b04  mov     dword ptr [rsp+0DA0h+pSacl], r13d
0x140007b09  mov     dword ptr [rsp+0DA0h+phkResult], r13d; unsigned int
0x140007b0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007b13  test    eax, eax
0x140007b15  jz      short loc_140007B35
0x140007b17  mov     edx, eax; unsigned int
0x140007b19  lea     rcx, aServicethreadm_1; "ServiceThreadMain: CoInitializeSecurity"...
0x140007b20  call    ?ReportErrorToDebugOutput@@YAXPEBGK@Z; ReportErrorToDebugOutput(ushort const *,ulong)
0x140007b25  call    cs:__imp_GetLastError
0x140007b2b  mov     edx, 1
0x140007b30  jmp     loc_140007C23
0x140007b35  mov     ebx, 1
0x140007b3a  test    edi, edi
0x140007b3c  js      loc_140007BD2
0x140007b42  lea     rax, [rsp+0DA0h+var_D28]
0x140007b47  mov     qword ptr [rsp+0DA0h+var_D28], r15
0x140007b4c  mov     [rsp+0DA0h+phkResult], rax; unsigned int
0x140007b51  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046
0x140007b58  mov     rax, cs:?CoCreateInstance@OLE32@@3P6AJAEBU_GUID@@PEAUIUnknown@@K0PEAPEAX@ZEA; long (*OLE32::CoCreateInstance)(_GUID const &,IUnknown *,ulong,_GUID const &,void * *)
0x140007b5f  lea     rcx, CLSID_GlobalOptions
0x140007b66  mov     r8d, ebx
0x140007b69  xor     edx, edx
0x140007b6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007b70  mov     esi, eax
0x140007b72  test    eax, eax
0x140007b74  jns     short loc_140007B96
0x140007b76  lea     rcx, aCocreateinstan_0; "CoCreateInstance of CLSID_GlobalOptions"...
0x140007b7d  mov     edx, esi; unsigned int
0x140007b7f  call    ?ReportErrorToDebugOutput@@YAXPEBGK@Z; ReportErrorToDebugOutput(ushort const *,ulong)
0x140007b84  xor     r9d, r9d; unsigned int
0x140007b87  mov     r8d, esi; unsigned int
0x140007b8a  mov     edx, ebx; unsigned int
0x140007b8c  call    ?ReportStatusToSCMgr@ServiceStatus@@QEAAHKKKK@Z; ServiceStatus::ReportStatusToSCMgr(ulong,ulong,ulong,ulong)
0x140007b91  jmp     loc_140007C32
0x140007b96  mov     rcx, qword ptr [rsp+0DA0h+var_D28]
0x140007b9b  mov     r8, rbx
0x140007b9e  mov     edx, r12d
0x140007ba1  mov     rax, [rcx]
0x140007ba4  mov     rax, [rax+18h]
0x140007ba8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007bad  mov     rcx, qword ptr [rsp+0DA0h+var_D28]
0x140007bb2  mov     esi, eax
0x140007bb4  mov     rdx, [rcx]
0x140007bb7  mov     rax, [rdx+10h]
0x140007bbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007bc0  mov     qword ptr [rsp+0DA0h+var_D28], r15
0x140007bc5  test    esi, esi
0x140007bc7  jns     short loc_140007BD2
0x140007bc9  lea     rcx, aSetOfComglbUnm; "Set of COMGLB_UNMARSHALING_POLICY faile"...
0x140007bd0  jmp     short loc_140007B7D
0x140007bd2  mov     r9d, r14d; unsigned int
0x140007bd5  xor     r8d, r8d; unsigned int
0x140007bd8  mov     edx, r13d; unsigned int
0x140007bdb  call    ?ReportStatusToSCMgr@ServiceStatus@@QEAAHKKKK@Z; ServiceStatus::ReportStatusToSCMgr(ulong,ulong,ulong,ulong)
0x140007be0  test    eax, eax
0x140007be2  jz      short loc_140007C2E
0x140007be4  xorps   xmm0, xmm0
0x140007be7  mov     [rbp+0CA0h+var_D1C], r15d
0x140007beb  xor     eax, eax
0x140007bed  lea     rdx, [rbp+0CA0h+var_D1C]
0x140007bf1  movups  [rbp+0CA0h+var_D08], xmm0
0x140007bf5  lea     rcx, [rbp+0CA0h+var_D08+8]
0x140007bf9  mov     dword ptr [rbp+0CA0h+var_D08], 18h
0x140007c00  mov     [rbp+0CA0h+var_CF8], rax
0x140007c04  call    ?GetSecureSecurityDescriptor@@YAKPEAPEADPEAIW4Bool@@_N@Z; GetSecureSecurityDescriptor(char * *,uint *,Bool,bool)
0x140007c09  test    eax, eax
0x140007c0b  jz      short loc_140007C79
0x140007c0d  xor     edx, edx; unsigned int
0x140007c0f  lea     rcx, aServicethreadm_2; "ServiceThreadMain: CreateSD for CreateW"...
0x140007c16  call    ?ReportErrorToDebugOutput@@YAXPEBGK@Z; ReportErrorToDebugOutput(ushort const *,ulong)
0x140007c1b  call    cs:__imp_GetLastError
0x140007c21  mov     edx, ebx; unsigned int
0x140007c23  xor     r9d, r9d; unsigned int
0x140007c26  mov     r8d, eax; unsigned int
0x140007c29  call    ?ReportStatusToSCMgr@ServiceStatus@@QEAAHKKKK@Z; ServiceStatus::ReportStatusToSCMgr(ulong,ulong,ulong,ulong)
0x140007c2e  test    edi, edi
0x140007c30  js      short loc_140007C38
0x140007c32  call    cs:__imp_CoUninitialize
0x140007c38  mov     ebx, r15d
0x140007c3b  lea     rcx, [rbp+0CA0h+var_AB0]
0x140007c42  call    ??1?$CTempBuffer@D$0CAA@@@QEAA@XZ; CTempBuffer<char,512>::~CTempBuffer<char,512>(void)
0x140007c47  lea     rcx, [rbp+0CA0h+var_8A0]
0x140007c4e  call    ??1?$CTempBuffer@D$0CAA@@@QEAA@XZ; CTempBuffer<char,512>::~CTempBuffer<char,512>(void)
0x140007c53  lea     rcx, [rbp+0CA0h+var_690]
0x140007c5a  call    ??1?$CTempBuffer@D$0CAA@@@QEAA@XZ; CTempBuffer<char,512>::~CTempBuffer<char,512>(void)
0x140007c5f  lea     rcx, [rbp+0CA0h+pDacl]
0x140007c66  call    ??1?$CTempBuffer@D$0CAA@@@QEAA@XZ; CTempBuffer<char,512>::~CTempBuffer<char,512>(void)
0x140007c6b  lea     rcx, [rbp+0CA0h+pAbsoluteSecurityDescriptor]
0x140007c6f  call    ??1?$CTempBuffer@D$0CAA@@@QEAA@XZ; CTempBuffer<char,512>::~CTempBuffer<char,512>(void)
0x140007c74  jmp     loc_1400079CA
0x140007c79  lea     r12, ?g_csServiceHandles@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_csServiceHandles
0x140007c80  mov     cs:?g_hCallbackEvent@@3PEAXEA, r15; void * g_hCallbackEvent
0x140007c87  mov     rcx, r12; lpCriticalSection
0x140007c8a  mov     cs:?g_hFatalShutdownEvent@@3PEAXEA, r15; void * g_hFatalShutdownEvent
0x140007c91  mov     cs:?g_hShutdownTimer@@3PEAXEA, r15; void * g_hShutdownTimer
0x140007c98  call    cs:__imp_InitializeCriticalSection
0x140007c9e  mov     rax, 0FFFFFFFF4D2FA200h
0x140007ca8  xor     r9d, r9d; lpName
0x140007cab  xor     r8d, r8d; bInitialState
0x140007cae  mov     [rbp+0CA0h+var_D10], rax
0x140007cb2  mov     edx, ebx; bManualReset
0x140007cb4  xor     ecx, ecx; lpEventAttributes
0x140007cb6  call    cs:__imp_CreateEventW
0x140007cbc  xor     r9d, r9d; lpName
0x140007cbf  xor     r8d, r8d; bInitialState
0x140007cc2  xor     edx, edx; bManualReset
0x140007cc4  mov     cs:?g_hFatalShutdownEvent@@3PEAXEA, rax; void * g_hFatalShutdownEvent
0x140007ccb  xor     ecx, ecx; lpEventAttributes
0x140007ccd  call    cs:__imp_CreateEventW
0x140007cd3  cmp     cs:?g_hFatalShutdownEvent@@3PEAXEA, r15; void * g_hFatalShutdownEvent
0x140007cda  mov     cs:?g_hCallbackEvent@@3PEAXEA, rax; void * g_hCallbackEvent
0x140007ce1  jz      loc_140007F37
0x140007ce7  test    rax, rax
0x140007cea  jz      loc_140007F37
0x140007cf0  mov     rax, cs:?CreateWaitableTimerW@KERNEL32@@3P6APEAXPEAU_SECURITY_ATTRIBUTES@@HPEBG@ZEA; void * (*KERNEL32::CreateWaitableTimerW)(_SECURITY_ATTRIBUTES *,int,ushort const *)
0x140007cf7  lea     rcx, [rbp+0CA0h+var_D08]
0x140007cfb  xor     r8d, r8d
0x140007cfe  mov     edx, ebx
0x140007d00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007d05  mov     cs:?g_hShutdownTimer@@3PEAXEA, rax; void * g_hShutdownTimer
0x140007d0c  test    rax, rax
0x140007d0f  jnz     short loc_140007D23
0x140007d11  call    cs:__imp_GetLastError
0x140007d17  lea     rcx, aServicethreadm; "ServiceThreadMain: CreateWaitableTimer "...
0x140007d1e  jmp     loc_140007F44
0x140007d23  mov     rcx, rax
0x140007d26  mov     dword ptr [rsp+0DA0h+pSacl], r15d
0x140007d2b  mov     rax, cs:?SetWaitableTimer@KERNEL32@@3P6AHPEAXPEBT_LARGE_INTEGER@@JP6AX0KK@Z0H@ZEA; int (*KERNEL32::SetWaitableTimer)(void *,_LARGE_INTEGER const *,long,void (*)(void *,ulong,ulong),void *,int)
0x140007d32  lea     rdx, [rbp+0CA0h+var_D10]
0x140007d36  xor     r9d, r9d
0x140007d39  mov     [rsp+0DA0h+phkResult], r15; unsigned int
0x140007d3e  xor     r8d, r8d
0x140007d41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007d46  test    eax, eax
0x140007d48  jnz     short loc_140007D5C
0x140007d4a  call    cs:__imp_GetLastError
0x140007d50  lea     rcx, aServicethreadm_3; "ServiceThreadMain: SetWaitableTimer fai"...
0x140007d57  jmp     loc_140007F44
0x140007d5c  mov     r14b, bl
0x140007d5f  mov     esi, r15d
0x140007d62  mov     r9d, 7530h; unsigned int
0x140007d68  xor     r8d, r8d; unsigned int
0x140007d6b  mov     edx, r13d; unsigned int
0x140007d6e  call    ?ReportStatusToSCMgr@ServiceStatus@@QEAAHKKKK@Z; ServiceStatus::ReportStatusToSCMgr(ulong,ulong,ulong,ulong)
0x140007d73  test    eax, eax
0x140007d75  jz      loc_140007F61
0x140007d7b  mov     ecx, esi
0x140007d7d  lea     r8, ?rgCLSID@@3QBU_GUID@@B; _GUID const near * const rgCLSID
0x140007d84  lea     rdx, __ImageBase
0x140007d8b  mov     r9d, ebx; flags
0x140007d8e  lea     rax, rva ?g_rghRegClass@@3PAKA[rdx]; ulong near * g_rghRegClass ...
0x140007d95  lea     rax, [rax+rcx*4]
0x140007d99  lea     rdx, [rdx+rcx*8]
0x140007d9d  mov     [rsp+0DA0h+phkResult], rax; unsigned int
0x140007da2  shl     rcx, 4
0x140007da6  lea     rdx, [rdx+0F0A8h]; pUnk
0x140007dad  add     rcx, r8; rclsid
0x140007db0  mov     r8d, 15h; dwClsContext
0x140007db6  call    cs:__imp_CoRegisterClassObject
0x140007dbc  test    eax, eax
0x140007dbe  jnz     loc_140007F2E
0x140007dc4  add     esi, ebx
0x140007dc6  cmp     esi, ebx
0x140007dc8  jl      short loc_140007D62
0x140007dca  xor     r9d, r9d; unsigned int
0x140007dcd  lea     edx, [rax+4]; unsigned int
0x140007dd0  xor     r8d, r8d; unsigned int
0x140007dd3  call    ?ReportStatusToSCMgr@ServiceStatus@@QEAAHKKKK@Z; ServiceStatus::ReportStatusToSCMgr(ulong,ulong,ulong,ulong)
0x140007dd8  test    eax, eax
0x140007dda  jz      loc_140007F61
0x140007de0  mov     rax, cs:?g_hShutdownTimer@@3PEAXEA; void * g_hShutdownTimer
0x140007de7  mov     esi, 3
0x140007dec  mov     [rbp+0CA0h+pHandles], rax
0x140007df3  mov     rax, cs:?g_hFatalShutdownEvent@@3PEAXEA; void * g_hFatalShutdownEvent
0x140007dfa  mov     [rbp+0CA0h+var_268], rax
0x140007e01  mov     rax, cs:?g_hCallbackEvent@@3PEAXEA; void * g_hCallbackEvent
0x140007e08  mov     [rbp+0CA0h+var_260], rax
  ... truncated ...
```
