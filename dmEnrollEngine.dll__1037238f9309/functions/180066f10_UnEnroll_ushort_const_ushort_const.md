# UnEnroll(ushort const *,ushort const *)

- ea: `0x180066f10`
- end: `0x1800674ea`
- name: `?UnEnroll@@YAJPEBG0@Z`
- size: `1498`
- prototype: `__int64 __fastcall(unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `28`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003b1f0`

## callees

- `0x1800067a0`
- `0x180006950`
- `0x18000de50`
- `0x18000e1b0`
- `0x1800172e4`
- `0x180017de4`
- `0x180019e8c`
- `0x18001a6a4`
- `0x18001aec8`
- `0x18001cca4`
- `0x18001e2c8`
- `0x18002e1a0`
- `0x18003083c`
- `0x180030940`
- `0x18003b068`
- `0x18003b0bc`
- `0x18003b118`
- `0x18003b170`
- `0x18004234c`
- `0x1800424fc`
- `0x180043820`
- `0x1800668fc`
- `0x180066980`
- `0x180066c40`
- `0x180066f10`
- `0x180072dd0`
- `0x180072e5c`
- `0x18007b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstod` at `0x180067156`
- `api-ms-win-crt-private-l1-1-0!_o_wcstod` at `0x180067156`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006708a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006708a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180067054`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180067054`
- `omadmapi!__imp_?OmaDmWaitForAllSessionsCompletion@@YAJPEBGW4tagDMACCOUNTLOOKUPTYPE@@K@Z` at `0x1800670bc`
- `omadmapi!__imp_?OmaDmWaitForAllSessionsCompletion@@YAJPEBGW4tagDMACCOUNTLOOKUPTYPE@@K@Z` at `0x1800670bc`
- `RPCRT4!UuidFromStringW` at `0x180066f79`
- `RPCRT4!UuidFromStringW` at `0x180066f8b`
- `RPCRT4!UuidFromStringW` at `0x180066f79`
- `RPCRT4!UuidFromStringW` at `0x180066f8b`
- `dsreg!DsrBeginDeviceUnjoin` at `0x180067071`
- `dsreg!DsrBeginDeviceUnjoin` at `0x180067071`

## string_xrefs

- `0x1800672df`: `RemoveAWA`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UnEnroll(unsigned __int16 *a1, const unsigned __int16 *a2)
{
  unsigned int ServerVersion; // ebx
  int EnrollmentType; // eax
  int v6; // ebx
  int v7; // eax
  CEnrollmentLogger *Logger; // rax
  unsigned int v9; // edi
  const wchar_t *v10; // r14
  int EnrollmentString; // eax
  int v12; // edi
  __int64 v13; // rbx
  const unsigned __int16 *v14; // rcx
  char *v15; // rcx
  CEnrollmentLogger *v16; // rax
  __int64 v17; // rcx
  int EnrollmentState; // eax
  int v19; // eax
  int v20; // edi
  __int64 v21; // r8
  __int64 v22; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v23; // [rsp+38h] [rbp-C8h] BYREF
  int v24; // [rsp+40h] [rbp-C0h] BYREF
  int v25[3]; // [rsp+44h] [rbp-BCh] BYREF
  struct _GUID v26; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v27; // [rsp+60h] [rbp-A0h] BYREF
  UUID Uuid; // [rsp+70h] [rbp-90h] BYREF
  HANDLE hHandle[2]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v30[264]; // [rsp+90h] [rbp-70h] BYREF

  v22 = 0;
  Uuid = 0;
  if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 2) != 0 )
    McTemplateU0z_EventWriteTransfer(
      MDM_ENTERPRISE_DIAGNOSTICS_Context,
      EnterpriseDiagnosticsUnEnrollmentNotInitiatedByTheUser,
      a1);
  if ( UuidFromStringW(a1, &Uuid) )
  {
    ServerVersion = UuidFromStringW(a1, &Uuid) | 0x80010000;
    if ( (Microsoft_WindowsPhone_EnrollmentClient_ProviderEnableBits & 2) != 0 )
      McTemplateU0q_EventWriteTransfer(
        WP_ENROLLMENT_CLIENT_PROVIDER_Context,
        StartingUnenrollmentFailedEvent,
        ServerVersion);
LABEL_6:
    ATL::CComPtrBase<IEnrollEngine>::~CComPtrBase<IEnrollEngine>(&v22);
    return ServerVersion;
  }
  v24 = 0;
  *(UUID *)hHandle = Uuid;
  EnrollmentType = EEDBManager::GetEnrollmentType((struct _GUID *)hHandle, (enum EnrollmentEnrollType *)&v24);
  ServerVersion = EnrollmentType;
  if ( EnrollmentType < 0 )
  {
    if ( (Microsoft_WindowsPhone_EnrollmentClient_ProviderEnableBits & 2) != 0 )
      McTemplateU0q_EventWriteTransfer(
        WP_ENROLLMENT_CLIENT_PROVIDER_Context,
        StartingUnenrollmentFailedEvent,
        (unsigned int)EnrollmentType);
    goto LABEL_6;
  }
  if ( v24 == 6 )
  {
    if ( (unsigned __int8)IsConvertLocalAccountToAADAccountPresent()
      || (unsigned __int8)IsCreateAndSignInAADUserPresent() )
    {
      if ( (Microsoft_WindowsPhone_EnrollmentClient_ProviderEnableBits & 2) != 0 )
        McTemplateU0q_EventWriteTransfer(
          WP_ENROLLMENT_CLIENT_PROVIDER_Context,
          StartingUnenrollmentFailedEvent,
          2147500033LL);
      ATL::CComPtrBase<IEnrollEngine>::~CComPtrBase<IEnrollEngine>(&v22);
      return 2147500033LL;
    }
    *(_OWORD *)hHandle = 0;
    hHandle[0] = CreateEventW(0, 0, 0, 0);
    v23 = (unsigned __int16 *)hHandle[0];
    v6 = DsrBeginDeviceUnjoin(UnjoinCallback, hHandle, 0);
    if ( v6 < 0 || !WaitForSingleObject(hHandle[0], 0x493E0u) && (v6 = (int)hHandle[1], SLODWORD(hHandle[1]) < 0) )
    {
      Logger = CEnrollmentLogger::GetLogger();
      v26 = Uuid;
      CEnrollmentLogger::LogServerUnenrollAADUnjoinFailed(Logger, v6, &v26);
      *(_QWORD *)&v26.Data1 = 0;
      v9 = 0;
      v10 = L"2";
      ServerVersion = GetServerVersion(a1, &v26);
      if ( (ServerVersion & 0x80000000) == 0 && _o_wcstod(*(_QWORD *)&v26.Data1, 0) >= 4.0 )
      {
        v9 = 1;
        v10 = L"AADJ Unregister Failed";
      }
      AlertServerForUnenroll(a1, v10, v9);
      if ( (Microsoft_WindowsPhone_EnrollmentClient_ProviderEnableBits & 2) != 0 )
        McTemplateU0q_EventWriteTransfer(
          WP_ENROLLMENT_CLIENT_PROVIDER_Context,
          StartingUnenrollmentFailedEvent,
          ServerVersion);
      CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>(&v26);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v23);
      ATL::CComPtrBase<IEnrollEngine>::~CComPtrBase<IEnrollEngine>(&v22);
      return ServerVersion;
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v23);
  }
  else if ( v24 == 13 )
  {
    *(_QWORD *)&v26.Data1 = 0;
    v23 = 0;
    *(UUID *)hHandle = Uuid;
    EnrollmentString = EEDBManager::GetEnrollmentString(
                         (struct _GUID *)hHandle,
                         L"PartnerOpaqueID",
                         (unsigned __int16 **)&v26);
    ServerVersion = EnrollmentString;
    if ( EnrollmentString < 0 )
    {
      if ( (Microsoft_WindowsPhone_EnrollmentClient_ProviderEnableBits & 2) != 0 )
        McTemplateU0q_EventWriteTransfer(
          WP_ENROLLMENT_CLIENT_PROVIDER_Context,
          StartingUnenrollmentFailedEvent,
          (unsigned int)EnrollmentString);
      CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>(&v23);
      CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>(&v26);
      ATL::CComPtrBase<IEnrollEngine>::~CComPtrBase<IEnrollEngine>(&v22);
      return ServerVersion;
    }
    *(UUID *)hHandle = Uuid;
    v12 = EEDBManager::GetEnrollmentString((struct _GUID *)hHandle, L"SID", &v23);
    if ( v12 < 0 )
      goto LABEL_61;
    LOBYTE(hHandle[0]) = 0;
    BYTE2(hHandle[0]) = 0;
    AutoImpersonate::ImpersonateSID((AutoImpersonate *)hHandle, v23);
    v13 = *(_QWORD *)&v26.Data1;
    v12 = DeleteAWAAccount(v14, *(const unsigned __int16 **)&v26.Data1);
    AutoImpersonate::~AutoImpersonate((AutoImpersonate *)hHandle);
    if ( v12 < 0 )
    {
      v12 = StringCchPrintfW(v30, 0x104u, L"-%s %s", L"RemoveAWA", v13);
      if ( v12 < 0 )
        goto LABEL_61;
      v12 = RunCmdAsUser(v15, v30, v23);
      if ( v12 < 0 )
        goto LABEL_61;
    }
    if ( v12 == 267011 )
    {
LABEL_61:
      v16 = CEnrollmentLogger::GetLogger();
      *(UUID *)hHandle = Uuid;
      CEnrollmentLogger::LogServerUnenrollTBRemoveAccountFailed(v16, v12, (struct _GUID *)hHandle);
      if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
        McTemplateU0d_EventWriteTransfer(v17, EnterpriseDiagnosticsUnenrollmentDeleteAccountFailed, (unsigned int)v12);
    }
    v25[0] = 63;
    *(UUID *)hHandle = Uuid;
    EnrollmentState = EEDBManager::GetEnrollmentState((struct _GUID *)hHandle, (enum EnrollmentStateTag *)v25);
    if ( v25[0] == 4 || EnrollmentState == -2147024894 )
    {
      CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>(&v23);
      CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>(&v26);
      ATL::CComPtrBase<IEnrollEngine>::~CComPtrBase<IEnrollEngine>(&v22);
      return 0;
    }
    CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>(&v23);
    CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>(&v26);
  }
  CleanupExpiredOMADMSessions(a1);
  OmaDmWaitForAllSessionsCompletion(a1, 1, 10000);
  v7 = EnrollEngineInitialize(1);
  ServerVersion = v7;
  if ( v7 < 0 )
  {
    if ( (Microsoft_WindowsPhone_EnrollmentClient_ProviderEnableBits & 2) != 0 )
      McTemplateU0q_EventWriteTransfer(
        WP_ENROLLMENT_CLIENT_PROVIDER_Context,
        StartingUnenrollmentFailedEvent,
        (unsigned int)v7);
    goto LABEL_6;
  }
  v27 = 0;
  v19 = (*(__int64 (__fastcall **)(__int64, UUID *, const wchar_t *, __int64 *))(*(_QWORD *)v22 + 32LL))(
          v22,
          &Uuid,
          L"SysprepGeneralize",
          &v27);
  v20 = v19;
  if ( v19 >= 0 )
  {
    *(UUID *)hHandle = Uuid;
    v20 = WaitForUnenrollment(v22, v27, hHandle);
    v27 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 120LL))(v22);
    if ( v20 >= 0 )
    {
      if ( (Microsoft_WindowsPhone_EnrollmentClient_ProviderEnableBits & 1) != 0 )
        McGenEventWrite_EventWriteTransfer(
          WP_ENROLLMENT_CLIENT_PROVIDER_Context,
          UnenrollmentFinishedEvent,
          v21,
          1,
          hHandle);
    }
    else if ( (Microsoft_WindowsPhone_EnrollmentClient_ProviderEnableBits & 2) != 0 )
    {
      McTemplateU0q_EventWriteTransfer(
        WP_ENROLLMENT_CLIENT_PROVIDER_Context,
        StartingUnenrollmentFailedEvent,
        (unsigned int)v20);
    }
  }
  else if ( (Microsoft_WindowsPhone_EnrollmentClient_ProviderEnableBits & 2) != 0 )
  {
    McTemplateU0q_EventWriteTransfer(
      WP_ENROLLMENT_CLIENT_PROVIDER_Context,
      StartingUnenrollmentFailedEvent,
      (unsigned int)v19);
  }
  ATL::CComPtrBase<IEnrollEngine>::~CComPtrBase<IEnrollEngine>(&v22);
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x180066f10  mov     [rsp-8+arg_8], rbx
0x180066f15  mov     [rsp-8+arg_10], rsi
0x180066f1a  push    rbp
0x180066f1b  push    rdi
0x180066f1c  push    r14
0x180066f1e  lea     rbp, [rsp-1B0h]
0x180066f26  sub     rsp, 2B0h
0x180066f2d  mov     rax, cs:__security_cookie
0x180066f34  xor     rax, rsp
0x180066f37  mov     [rbp+1C0h+var_20], rax
0x180066f3e  mov     rsi, rcx
0x180066f41  mov     [rsp+2C0h+var_290], 0
0x180066f4a  xorps   xmm0, xmm0
0x180066f4d  movups  xmmword ptr [rsp+2C0h+Uuid.Data1], xmm0
0x180066f52  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 2
0x180066f59  jz      short loc_180066F71
0x180066f5b  mov     r8, rcx
0x180066f5e  lea     rdx, EnterpriseDiagnosticsUnEnrollmentNotInitiatedByTheUser
0x180066f65  lea     rcx, MDM_ENTERPRISE_DIAGNOSTICS_Context
0x180066f6c  call    McTemplateU0z_EventWriteTransfer
0x180066f71  lea     rdx, [rsp+2C0h+Uuid]; Uuid
0x180066f76  mov     rcx, rsi; StringUuid
0x180066f79  call    cs:__imp_UuidFromStringW
0x180066f7f  test    eax, eax
0x180066f81  jz      short loc_180066FCB
0x180066f83  lea     rdx, [rsp+2C0h+Uuid]; Uuid
0x180066f88  mov     rcx, rsi; StringUuid
0x180066f8b  call    cs:__imp_UuidFromStringW
0x180066f91  mov     ebx, eax
0x180066f93  or      ebx, 80010000h
0x180066f99  test    cs:Microsoft_WindowsPhone_EnrollmentClient_ProviderEnableBits, 2
0x180066fa0  jz      short loc_180066FB9
0x180066fa2  mov     r8d, ebx
0x180066fa5  lea     rdx, StartingUnenrollmentFailedEvent
0x180066fac  lea     rcx, WP_ENROLLMENT_CLIENT_PROVIDER_Context
0x180066fb3  call    McTemplateU0q_EventWriteTransfer
0x180066fb8  nop
0x180066fb9  lea     rcx, [rsp+2C0h+var_290]
0x180066fbe  call    ??1?$CComPtrBase@UIEnrollEngine@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnrollEngine>::~CComPtrBase<IEnrollEngine>(void)
0x180066fc3  nop
0x180066fc4  mov     eax, ebx
0x180066fc6  jmp     loc_1800674C3
0x180066fcb  mov     [rsp+2C0h+var_280], 0
0x180066fd3  movaps  xmm0, xmmword ptr [rsp+2C0h+Uuid.Data1]
0x180066fd8  movdqa  xmmword ptr [rbp+1C0h+hHandle], xmm0
0x180066fdd  lea     rdx, [rsp+2C0h+var_280]; enum EnrollmentEnrollType *
0x180066fe2  lea     rcx, [rbp+1C0h+hHandle]; struct _GUID
0x180066fe6  call    ?GetEnrollmentType@EEDBManager@@SAJU_GUID@@PEAW4EnrollmentEnrollType@@@Z; EEDBManager::GetEnrollmentType(_GUID,EnrollmentEnrollType *)
0x180066feb  mov     ebx, eax
0x180066fed  test    eax, eax
0x180066fef  jns     short loc_18006701E
0x180066ff1  test    cs:Microsoft_WindowsPhone_EnrollmentClient_ProviderEnableBits, 2
0x180066ff8  jz      short loc_180067011
0x180066ffa  mov     r8d, eax
0x180066ffd  lea     rdx, StartingUnenrollmentFailedEvent
0x180067004  lea     rcx, WP_ENROLLMENT_CLIENT_PROVIDER_Context
0x18006700b  call    McTemplateU0q_EventWriteTransfer
0x180067010  nop
0x180067011  lea     rcx, [rsp+2C0h+var_290]
0x180067016  call    ??1?$CComPtrBase@UIEnrollEngine@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnrollEngine>::~CComPtrBase<IEnrollEngine>(void)
0x18006701b  nop
0x18006701c  jmp     short loc_180066FC4
0x18006701e  cmp     [rsp+2C0h+var_280], 6
0x180067023  jnz     loc_1800671FD
0x180067029  call    IsConvertLocalAccountToAADAccountPresent
0x18006702e  test    al, al
0x180067030  jnz     loc_1800671C5
0x180067036  call    IsCreateAndSignInAADUserPresent
0x18006703b  test    al, al
0x18006703d  jnz     loc_1800671C5
0x180067043  xorps   xmm0, xmm0
0x180067046  movups  xmmword ptr [rbp+1C0h+hHandle], xmm0
0x18006704a  xor     r9d, r9d; lpName
0x18006704d  xor     r8d, r8d; bInitialState
0x180067050  xor     edx, edx; bManualReset
0x180067052  xor     ecx, ecx; lpEventAttributes
0x180067054  call    cs:__imp_CreateEventW
0x18006705a  mov     [rbp+1C0h+hHandle], rax
0x18006705e  mov     [rsp+2C0h+var_288], rax
0x180067063  xor     r8d, r8d
0x180067066  lea     rdx, [rbp+1C0h+hHandle]
0x18006706a  lea     rcx, UnjoinCallback
0x180067071  call    cs:__imp_DsrBeginDeviceUnjoin
0x180067077  mov     ebx, eax
0x180067079  test    eax, eax
0x18006707b  js      loc_18006710B
0x180067081  mov     edx, 493E0h; dwMilliseconds
0x180067086  mov     rcx, [rbp+1C0h+hHandle]; hHandle
0x18006708a  call    cs:__imp_WaitForSingleObject
0x180067090  test    eax, eax
0x180067092  jnz     short loc_18006709B
0x180067094  mov     ebx, dword ptr [rbp+1C0h+hHandle+8]
0x180067097  test    ebx, ebx
0x180067099  js      short loc_18006710B
0x18006709b  lea     rcx, [rsp+2C0h+var_288]
0x1800670a0  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800670a5  nop
0x1800670a6  mov     rcx, rsi; unsigned __int16 *
0x1800670a9  call    ?CleanupExpiredOMADMSessions@@YAXPEBG@Z; CleanupExpiredOMADMSessions(ushort const *)
0x1800670ae  mov     edx, 1
0x1800670b3  mov     r8d, 2710h
0x1800670b9  mov     rcx, rsi
0x1800670bc  call    cs:__imp_?OmaDmWaitForAllSessionsCompletion@@YAJPEBGW4tagDMACCOUNTLOOKUPTYPE@@K@Z; OmaDmWaitForAllSessionsCompletion(ushort const *,tagDMACCOUNTLOOKUPTYPE,ulong)
0x1800670c2  lea     r8, [rsp+2C0h+var_290]
0x1800670c7  xor     edx, edx
0x1800670c9  lea     ecx, [rdx+1]; int
0x1800670cc  call    EnrollEngineInitialize
0x1800670d1  mov     ebx, eax
0x1800670d3  test    eax, eax
0x1800670d5  jns     loc_1800673C0
0x1800670db  test    cs:Microsoft_WindowsPhone_EnrollmentClient_ProviderEnableBits, 2
0x1800670e2  jz      short loc_1800670FB
0x1800670e4  mov     r8d, eax
0x1800670e7  lea     rdx, StartingUnenrollmentFailedEvent
0x1800670ee  lea     rcx, WP_ENROLLMENT_CLIENT_PROVIDER_Context
0x1800670f5  call    McTemplateU0q_EventWriteTransfer
0x1800670fa  nop
0x1800670fb  lea     rcx, [rsp+2C0h+var_290]
0x180067100  call    ??1?$CComPtrBase@UIEnrollEngine@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnrollEngine>::~CComPtrBase<IEnrollEngine>(void)
0x180067105  nop
0x180067106  jmp     loc_180066FC4
0x18006710b  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180067110  movaps  xmm0, xmmword ptr [rsp+2C0h+Uuid.Data1]
0x180067115  movdqa  xmmword ptr [rsp+2C0h+var_270.Data1], xmm0
0x18006711b  lea     r8, [rsp+2C0h+var_270]; struct _GUID
0x180067120  mov     edx, ebx; int
0x180067122  mov     rcx, rax; this
0x180067125  call    ?LogServerUnenrollAADUnjoinFailed@CEnrollmentLogger@@QEAAXJU_GUID@@@Z; CEnrollmentLogger::LogServerUnenrollAADUnjoinFailed(long,_GUID)
0x18006712a  mov     qword ptr [rsp+2C0h+var_270.Data1], 0
0x180067133  xor     edi, edi
0x180067135  lea     r14, a2; "2"
0x18006713c  lea     rdx, [rsp+2C0h+var_270]
0x180067141  mov     rcx, rsi
0x180067144  call    GetServerVersion
0x180067149  mov     ebx, eax
0x18006714b  test    eax, eax
0x18006714d  js      short loc_180067172
0x18006714f  xor     edx, edx
0x180067151  mov     rcx, qword ptr [rsp+2C0h+var_270.Data1]
0x180067156  call    cs:__imp__o_wcstod
0x18006715c  comisd  xmm0, cs:__real@4010000000000000
0x180067164  jb      short loc_180067172
0x180067166  mov     edi, 1
0x18006716b  lea     r14, aAadjUnregister; "AADJ Unregister Failed"
0x180067172  mov     r8d, edi
0x180067175  mov     rdx, r14
0x180067178  mov     rcx, rsi
0x18006717b  call    AlertServerForUnenroll
0x180067180  test    cs:Microsoft_WindowsPhone_EnrollmentClient_ProviderEnableBits, 2
0x180067187  jz      short loc_18006719F
0x180067189  mov     r8d, ebx
0x18006718c  lea     rdx, StartingUnenrollmentFailedEvent
0x180067193  lea     rcx, WP_ENROLLMENT_CLIENT_PROVIDER_Context
0x18006719a  call    McTemplateU0q_EventWriteTransfer
0x18006719f  lea     rcx, [rsp+2C0h+var_270]
0x1800671a4  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x1800671a9  nop
0x1800671aa  lea     rcx, [rsp+2C0h+var_288]
0x1800671af  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800671b4  nop
0x1800671b5  lea     rcx, [rsp+2C0h+var_290]
0x1800671ba  call    ??1?$CComPtrBase@UIEnrollEngine@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnrollEngine>::~CComPtrBase<IEnrollEngine>(void)
0x1800671bf  nop
0x1800671c0  jmp     loc_180066FC4
0x1800671c5  test    cs:Microsoft_WindowsPhone_EnrollmentClient_ProviderEnableBits, 2
0x1800671cc  jz      short loc_1800671E8
0x1800671ce  mov     r8d, 80004001h
0x1800671d4  lea     rdx, StartingUnenrollmentFailedEvent
0x1800671db  lea     rcx, WP_ENROLLMENT_CLIENT_PROVIDER_Context
0x1800671e2  call    McTemplateU0q_EventWriteTransfer
0x1800671e7  nop
0x1800671e8  lea     rcx, [rsp+2C0h+var_290]
0x1800671ed  call    ??1?$CComPtrBase@UIEnrollEngine@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnrollEngine>::~CComPtrBase<IEnrollEngine>(void)
0x1800671f2  nop
0x1800671f3  mov     eax, 80004001h
0x1800671f8  jmp     loc_1800674C3
0x1800671fd  cmp     [rsp+2C0h+var_280], 0Dh
0x180067202  jnz     loc_1800670A6
0x180067208  mov     qword ptr [rsp+2C0h+var_270.Data1], 0
0x180067211  mov     [rsp+2C0h+var_288], 0
0x18006721a  movaps  xmm0, xmmword ptr [rsp+2C0h+Uuid.Data1]
0x18006721f  movdqa  xmmword ptr [rbp+1C0h+hHandle], xmm0
0x180067224  lea     r8, [rsp+2C0h+var_270]; unsigned __int16 **
0x180067229  lea     rdx, aPartneropaquei; "PartnerOpaqueID"
0x180067230  lea     rcx, [rbp+1C0h+hHandle]; struct _GUID
0x180067234  call    ?GetEnrollmentString@EEDBManager@@CAJU_GUID@@PEBGPEAPEAG@Z; EEDBManager::GetEnrollmentString(_GUID,ushort const *,ushort * *)
0x180067239  mov     ebx, eax
0x18006723b  test    eax, eax
0x18006723d  jns     short loc_180067283
0x18006723f  test    cs:Microsoft_WindowsPhone_EnrollmentClient_ProviderEnableBits, 2
0x180067246  jz      short loc_18006725E
0x180067248  mov     r8d, eax
0x18006724b  lea     rdx, StartingUnenrollmentFailedEvent
0x180067252  lea     rcx, WP_ENROLLMENT_CLIENT_PROVIDER_Context
0x180067259  call    McTemplateU0q_EventWriteTransfer
0x18006725e  lea     rcx, [rsp+2C0h+var_288]
0x180067263  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x180067268  lea     rcx, [rsp+2C0h+var_270]
0x18006726d  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x180067272  nop
0x180067273  lea     rcx, [rsp+2C0h+var_290]
0x180067278  call    ??1?$CComPtrBase@UIEnrollEngine@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnrollEngine>::~CComPtrBase<IEnrollEngine>(void)
0x18006727d  nop
0x18006727e  jmp     loc_180066FC4
0x180067283  movaps  xmm0, xmmword ptr [rsp+2C0h+Uuid.Data1]
0x180067288  movdqa  xmmword ptr [rbp+1C0h+hHandle], xmm0
0x18006728d  lea     r8, [rsp+2C0h+var_288]; unsigned __int16 **
0x180067292  lea     rdx, aSid; "SID"
0x180067299  lea     rcx, [rbp+1C0h+hHandle]; struct _GUID
0x18006729d  call    ?GetEnrollmentString@EEDBManager@@CAJU_GUID@@PEBGPEAPEAG@Z; EEDBManager::GetEnrollmentString(_GUID,ushort const *,ushort * *)
0x1800672a2  mov     edi, eax
0x1800672a4  test    eax, eax
0x1800672a6  js      short loc_18006731D
0x1800672a8  mov     byte ptr [rbp+1C0h+hHandle], 0
0x1800672ac  mov     byte ptr [rbp+1C0h+hHandle+2], 0
0x1800672b0  mov     rdx, [rsp+2C0h+var_288]; unsigned __int16 *
0x1800672b5  lea     rcx, [rbp+1C0h+hHandle]; this
0x1800672b9  call    ?ImpersonateSID@AutoImpersonate@@QEAAJPEBG@Z; AutoImpersonate::ImpersonateSID(ushort const *)
0x1800672be  mov     rbx, qword ptr [rsp+2C0h+var_270.Data1]
0x1800672c3  mov     rdx, rbx; unsigned __int16 *
0x1800672c6  call    ?DeleteAWAAccount@@YAJPEBG0@Z; DeleteAWAAccount(ushort const *,ushort const *)
0x1800672cb  mov     edi, eax
0x1800672cd  lea     rcx, [rbp+1C0h+hHandle]; this
0x1800672d1  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x1800672d6  test    edi, edi
0x1800672d8  jns     short loc_180067315
0x1800672da  mov     [rsp+2C0h+var_2A0], rbx
0x1800672df  lea     r9, aRemoveawa; "RemoveAWA"
0x1800672e6  lea     r8, aSS; "-%s %s"
0x1800672ed  mov     edx, 104h; unsigned __int64
0x1800672f2  lea     rcx, [rbp+1C0h+var_230]; unsigned __int16 *
0x1800672f6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800672fb  mov     edi, eax
0x1800672fd  test    eax, eax
0x1800672ff  js      short loc_18006731D
0x180067301  mov     r8, [rsp+2C0h+var_288]; unsigned __int16 *
0x180067306  lea     rdx, [rbp+1C0h+var_230]; unsigned __int16 *
0x18006730a  call    ?RunCmdAsUser@@YAJPEBG00@Z; RunCmdAsUser(ushort const *,ushort const *,ushort const *)
0x18006730f  mov     edi, eax
0x180067311  test    eax, eax
0x180067313  js      short loc_18006731D
0x180067315  cmp     edi, 41303h
0x18006731b  jnz     short loc_180067352
0x18006731d  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180067322  movaps  xmm0, xmmword ptr [rsp+2C0h+Uuid.Data1]
0x180067327  movdqa  xmmword ptr [rbp+1C0h+hHandle], xmm0
0x18006732c  lea     r8, [rbp+1C0h+hHandle]; struct _GUID
0x180067330  mov     edx, edi; int
0x180067332  mov     rcx, rax; this
0x180067335  call    ?LogServerUnenrollTBRemoveAccountFailed@CEnrollmentLogger@@QEAAXJU_GUID@@@Z; CEnrollmentLogger::LogServerUnenrollTBRemoveAccountFailed(long,_GUID)
0x18006733a  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x180067341  jz      short loc_180067352
0x180067343  mov     r8d, edi
0x180067346  lea     rdx, EnterpriseDiagnosticsUnenrollmentDeleteAccountFailed
0x18006734d  call    McTemplateU0d_EventWriteTransfer
0x180067352  mov     [rsp+2C0h+var_27C], 3Fh ; '?'
0x18006735a  movaps  xmm0, xmmword ptr [rsp+2C0h+Uuid.Data1]
0x18006735f  movdqa  xmmword ptr [rbp+1C0h+hHandle], xmm0
0x180067364  lea     rdx, [rsp+2C0h+var_27C]; enum EnrollmentStateTag *
0x180067369  lea     rcx, [rbp+1C0h+hHandle]; struct _GUID
0x18006736d  call    ?GetEnrollmentState@EEDBManager@@SAJU_GUID@@PEAW4EnrollmentStateTag@@@Z; EEDBManager::GetEnrollmentState(_GUID,EnrollmentStateTag *)
0x180067372  cmp     [rsp+2C0h+var_27C], 4
0x180067377  jz      short loc_180067399
0x180067379  cmp     eax, 80070002h
0x18006737e  jz      short loc_180067399
0x180067380  lea     rcx, [rsp+2C0h+var_288]
0x180067385  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x18006738a  lea     rcx, [rsp+2C0h+var_270]
0x18006738f  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x180067394  jmp     loc_1800670A6
0x180067399  lea     rcx, [rsp+2C0h+var_288]
0x18006739e  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x1800673a3  lea     rcx, [rsp+2C0h+var_270]
0x1800673a8  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x1800673ad  nop
0x1800673ae  lea     rcx, [rsp+2C0h+var_290]
0x1800673b3  call    ??1?$CComPtrBase@UIEnrollEngine@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnrollEngine>::~CComPtrBase<IEnrollEngine>(void)
0x1800673b8  nop
0x1800673b9  xor     eax, eax
0x1800673bb  jmp     loc_1800674C3
0x1800673c0  mov     [rsp+2C0h+var_260], 0
0x1800673c9  mov     rbx, [rsp+2C0h+var_290]
0x1800673ce  mov     rax, [rbx]
0x1800673d1  lea     r9, [rsp+2C0h+var_260]
0x1800673d6  lea     r8, aSysprepgeneral_0; "SysprepGeneralize"
0x1800673dd  lea     rdx, [rsp+2C0h+Uuid]
0x1800673e2  mov     rcx, rbx
0x1800673e5  mov     rax, [rax+20h]
0x1800673e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800673ee  mov     edi, eax
0x1800673f0  test    eax, eax
0x1800673f2  jns     short loc_180067424
0x1800673f4  test    cs:Microsoft_WindowsPhone_EnrollmentClient_ProviderEnableBits, 2
0x1800673fb  jz      short loc_180067414
0x1800673fd  mov     r8d, eax
0x180067400  lea     rdx, StartingUnenrollmentFailedEvent
0x180067407  lea     rcx, WP_ENROLLMENT_CLIENT_PROVIDER_Context
0x18006740e  call    McTemplateU0q_EventWriteTransfer
0x180067413  nop
0x180067414  lea     rcx, [rsp+2C0h+var_290]
  ... truncated ...
```
