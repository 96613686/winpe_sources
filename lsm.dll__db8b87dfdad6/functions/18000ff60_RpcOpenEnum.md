# RpcOpenEnum

- ea: `0x18000ff60`
- end: `0x180010905`
- name: `RpcOpenEnum`
- size: `2469`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800074c0`
- `0x18000b190`
- `0x18000c700`
- `0x18000ff60`
- `0x180010fb0`
- `0x18001aa50`
- `0x1800271d0`
- `0x18004b460`
- `0x18004b86c`
- `0x18004bf44`
- `0x18005fcc4`
- `0x180097010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180010782`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180010782`
- `ntdll!RtlReleaseResource` at `0x1800101b6`
- `ntdll!RtlReleaseResource` at `0x1800101b6`
- `ntdll!RtlCaptureStackBackTrace` at `0x18001085e`
- `ntdll!RtlCaptureStackBackTrace` at `0x18001085e`
- `ntdll!NtQueryInformationProcess` at `0x180010766`
- `ntdll!NtQueryInformationProcess` at `0x180010766`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010418`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800106c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800108f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010418`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800106c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800108f9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001040a`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800108eb`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001040a`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800108eb`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180010060`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180010060`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800107ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800107ab`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000ffd5`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000ffd5`
- `RPCRT4!RpcImpersonateClient` at `0x180010267`
- `RPCRT4!RpcImpersonateClient` at `0x180010267`
- `RPCRT4!RpcRevertToSelf` at `0x1800102bf`
- `RPCRT4!RpcRevertToSelf` at `0x1800102bf`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x18001023e`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x18001023e`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180010045`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18001045f`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180010045`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18001045f`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001073e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001073e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800102a7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800102a7`

## string_xrefs

- `0x18000ffbc`: `RpcOpenEnum`
- `0x1800108c3`: `RpcOpenEnum`
- `0x18001052b`: `new CAccessTracker failed: 0x%x in %s`
- `0x180010521`: `CObjectAccessTracker<struct ISessionEnum,5000>::GetInstanceOfObject`
- `0x180010873`: `RpcImpersonateClient failed: 0x%x in %s`
- `0x180010581`: `%s with Trace ID 0x%x Completed`
- `0x1800104aa`: `CObjectAccessTracker<struct ISessionEnum,5000>::CObjectAccessTracker`
- `0x1800106f3`: `GetTokenInformation failed: 0x%x in %s`
- `0x1800106e9`: `CObjectAccessTracker<struct ISessionEnum,5000>::GetCallerSessionId`
- `0x180010869`: `CObjectAccessTracker<struct ISessionEnum,5000>::GetCallerSessionId`
- `0x180010668`: `TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC`
- `0x1800105b9`: `RPC Caller: PID %d, SessID %d, Process Name: <%S>`

## pseudocode

```c
__int64 __fastcall RpcOpenEnum(__int64 a1, _QWORD *a2)
{
  struct ISessionManagerInternal *v3; // rbx
  unsigned int v4; // esi
  RPC_STATUS v5; // eax
  int v6; // edi
  struct ISessionManagerInternal *v7; // rax
  int v8; // eax
  signed int v9; // edi
  int v10; // eax
  int v11; // eax
  __int64 v12; // r15
  __int64 v13; // r14
  _QWORD *v14; // rax
  _QWORD *v15; // rsi
  _QWORD *v16; // rdi
  _QWORD *v17; // r13
  void **v18; // rcx
  char v19; // al
  RPC_STATUS IsClientLocal; // eax
  bool v21; // sf
  RPC_STATUS v22; // eax
  signed int v23; // r14d
  signed int v24; // eax
  bool v25; // sf
  _QWORD *v26; // r14
  RPC_STATUS v28; // eax
  int v29; // eax
  signed int LastError; // eax
  HANDLE v31; // rax
  void *v32; // r14
  NTSTATUS InformationProcess; // eax
  wchar_t *v34; // rax
  wchar_t *v35; // rax
  CSessionManager *v36; // rax
  struct ISessionManagerInternal *v37; // rax
  DWORD ReturnLength; // [rsp+30h] [rbp-D0h] BYREF
  struct CTraceBase *TokenInformation; // [rsp+38h] [rbp-C8h] BYREF
  int v40; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int ClientLocalFlag; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v42; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v43; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v44; // [rsp+58h] [rbp-A8h] BYREF
  PRTL_RESOURCE Resource; // [rsp+60h] [rbp-A0h] BYREF
  int v46; // [rsp+68h] [rbp-98h]
  void **v47; // [rsp+70h] [rbp-90h] BYREF
  GUID pguid; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v49[2]; // [rsp+88h] [rbp-78h] BYREF
  struct CTraceBase *v50; // [rsp+90h] [rbp-70h] BYREF
  int v51; // [rsp+98h] [rbp-68h]
  const char *v52; // [rsp+A0h] [rbp-60h]
  unsigned int Pid[2]; // [rsp+A8h] [rbp-58h] BYREF
  int v54; // [rsp+B0h] [rbp-50h]
  unsigned __int16 v55[262]; // [rsp+B4h] [rbp-4Ch] BYREF
  char ProcessInformation[8]; // [rsp+2C0h] [rbp+1C0h] BYREF
  wchar_t *Str; // [rsp+2C8h] [rbp+1C8h]

  v3 = 0;
  v44 = 0;
  v43 = 0;
  v42 = 0;
  v47 = &CTraceBase::`vftable';
  v49[1] = 1;
  v50 = 0;
  if ( CTraceBase::g_bEnabled )
  {
    if ( (g_DebugTraceComponent & 1) != 0 )
      _DbgPrintMessage(2, "Adding trace %p, %d, %s", &v47, 1, "RpcOpenEnum");
    TokenInformation = 0;
    if ( (int)CTraceBase::GetThreadCurrentOperationTrace(&TokenInformation) >= 0
      && TokenInformation
      && (g_DebugTraceComponent & 1) != 0 )
    {
      _DbgPrintMessage(
        2,
        "TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC",
        1);
    }
    CTraceBase::ResetThreadCurrentOperationTrace(0, 0);
    if ( (int)CTraceBase::GetThreadCurrentOperationTrace(&v50) >= 0 && v50 )
    {
      (*(void (__fastcall **)(struct CTraceBase *, GUID *))(*(_QWORD *)v50 + 32LL))(v50, &pguid);
      v49[0] = (*(__int64 (__fastcall **)(struct CTraceBase *))(*(_QWORD *)v50 + 24LL))(v50);
      v51 = 1;
      goto LABEL_4;
    }
    CTraceBase::ResetThreadCurrentOperationTrace((struct CTraceBase *)&v47, "RpcOpenEnum");
    CTraceBase::GenerateTraceID(&pguid, v49);
  }
  else
  {
    CoCreateGuid(&pguid);
    v49[0] = _InterlockedIncrement((volatile signed __int32 *)&CTraceBase::g_NextShortActivityID);
  }
  v51 = 0;
LABEL_4:
  v47 = &CRpcCallTrace::`vftable';
  v52 = "RpcOpenEnum";
  *(_QWORD *)Pid = -1;
  v54 = 0;
  memset_0(v55, 0, 0x208u);
  if ( v54 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "TRACE RPC %s with Trace ID 0x%x", v52, v49[0]);
  v4 = 0;
  if ( (g_DebugTraceComponent & 1) != 0 )
    v4 = 260;
  *(_QWORD *)Pid = -1;
  v5 = I_RpcBindingInqLocalClientPID(0, &Pid[1]);
  v6 = v5;
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
  if ( v6 >= 0 )
  {
    ProcessIdToSessionId(Pid[1], Pid);
    if ( v4 )
    {
      v31 = OpenProcess(0x400u, 0, Pid[1]);
      v32 = v31;
      if ( v31 )
      {
        InformationProcess = NtQueryInformationProcess(v31, ProcessImageFileName, ProcessInformation, 0x110u, 0);
        v6 = InformationProcess | 0x10000000;
        if ( InformationProcess >= 0 )
        {
          v34 = wcsrchr(Str, 0x5Cu);
          if ( v34 )
            v35 = v34 + 1;
          else
            v35 = Str;
          StringCchCopyW(v55, v4, v35);
        }
        CloseHandle(v32);
      }
    }
  }
  if ( v54 )
  {
    if ( v6 < 0 )
    {
      if ( (g_DebugTraceComponent & 1) != 0 )
        _DbgPrintMessage(2, "RPC Caller: Unknown");
    }
    else if ( (g_DebugTraceComponent & 1) != 0 )
    {
      _DbgPrintMessage(2, "RPC Caller: PID %d, SessID %d, Process Name: <%S>", Pid[1], Pid[0], v55);
    }
  }
  if ( !a2 )
  {
    _DbgPrintMessage(8, "Missing paramter %s in %s", "phEnum", "RpcOpenEnum");
    v9 = -2147024809;
    goto LABEL_51;
  }
  v40 = -2147467263;
  v7 = ISessionManagerInternal::pSMGlobalInstance;
  if ( ISessionManagerInternal::pSMGlobalInstance )
    goto LABEL_14;
  v36 = (CSessionManager *)operator new(0x758u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v36 )
  {
    v37 = CSessionManager::CSessionManager(v36, &v40);
    ISessionManagerInternal::pSMGlobalInstance = v37;
    if ( v37 )
    {
      (*(void (__fastcall **)(struct ISessionManagerInternal *))(*(_QWORD *)v37 + 8LL))(v37);
      v7 = ISessionManagerInternal::pSMGlobalInstance;
LABEL_14:
      v40 = 0;
      v3 = v7;
      (*(void (__fastcall **)(struct ISessionManagerInternal *))(*(_QWORD *)v7 + 8LL))(v7);
    }
  }
  else
  {
    ISessionManagerInternal::pSMGlobalInstance = 0;
  }
  v8 = (*(__int64 (__fastcall **)(struct ISessionManagerInternal *, __int64 *))(*(_QWORD *)v3 + 200LL))(v3, &v42);
  v9 = v8;
  if ( v8 < 0 )
  {
    _DbgPrintMessage(8, "GetRpcClientTrackerMgr failed: 0x%x in %s", v8, "RpcOpenEnum");
    goto LABEL_51;
  }
  v10 = (*(__int64 (__fastcall **)(struct ISessionManagerInternal *, __int64 *))(*(_QWORD *)v3 + 24LL))(v3, &v44);
  v9 = v10;
  if ( v10 < 0 )
  {
    _DbgPrintMessage(8, "GetSessionList failed: 0x%x in %s", v10, "RpcOpenEnum");
    goto LABEL_51;
  }
  v11 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v44 + 32LL))(v44, &v43);
  v9 = v11;
  if ( v11 < 0 )
  {
    _DbgPrintMessage(8, "GetInstanceOfEnum failed: 0x%x in %s", v11, "RpcOpenEnum");
    goto LABEL_51;
  }
  v12 = v42;
  v13 = v43;
  v14 = operator new(0x658u, (const struct std::nothrow_t *)&std::nothrow);
  v15 = v14;
  if ( !v14 )
  {
    v9 = -2147024882;
    v15 = 0;
LABEL_74:
    v26 = 0;
    _DbgPrintMessage(
      8,
      "new CAccessTracker failed: 0x%x in %s",
      v9,
      "CObjectAccessTracker<struct ISessionEnum,5000>::GetInstanceOfObject");
    goto LABEL_47;
  }
  *v14 = &CTSPrivateObject<IUnknown>::`vftable';
  v14[2] = "SESSIONENUMTRACKER";
  *((_DWORD *)v14 + 2) = 0;
  *((_DWORD *)v14 + 3) = 1;
  v16 = v14 + 197;
  v14[198] = v14 + 197;
  v14[197] = v14 + 197;
  v17 = g_pObjectTracker;
  if ( g_pObjectTracker )
  {
    CAutoExclusiveLock::CAutoExclusiveLock(
      (CAutoExclusiveLock *)&Resource,
      (struct CResource *)((char *)g_pObjectTracker + 24));
    v18 = (void **)v17[2];
    if ( *v18 != v17 + 1 )
      __fastfail(3u);
    *v16 = v17 + 1;
    v15[198] = v18;
    *v18 = v16;
    v17[2] = v16;
    if ( v46 )
    {
      v46 = 0;
      if ( LODWORD(Resource[1].Lock.DebugInfo) )
        RtlReleaseResource(Resource);
    }
  }
  v15[3] = 0;
  *((_DWORD *)v15 + 8) = 0;
  LODWORD(TokenInformation) = 0;
  v19 = _InterlockedIncrement((volatile signed __int32 *)v15 + 8);
  if ( g_bCaptureObjectStackTrace == 1 )
    RtlCaptureStackBackTrace(1u, 6u, (PVOID *)&v15[6 * (v19 & 0x1F) + 5], (PULONG)&TokenInformation);
  *v15 = &CObjectAccessTracker<ISessionEnum,5000>::`vftable';
  v15[199] = v13;
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13);
  v15[200] = -1;
  v15[201] = v12;
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
  v15[202] = 0;
  ClientLocalFlag = 0;
  IsClientLocal = I_RpcBindingIsClientLocal(0, &ClientLocalFlag);
  v21 = IsClientLocal < 0;
  if ( IsClientLocal > 0 )
    v21 = 1;
  if ( v21 || !ClientLocalFlag )
    goto LABEL_70;
  LODWORD(TokenInformation) = 0;
  v22 = RpcImpersonateClient(0);
  v9 = v22;
  ReturnLength = v22;
  if ( v22 > 0 )
    v9 = (unsigned __int16)v22 | 0x80070000;
  v23 = v9;
  if ( v9 < 0 )
  {
    _DbgPrintMessage(
      8,
      "RpcImpersonateClient failed: 0x%x in %s",
      v9,
      "CObjectAccessTracker<struct ISessionEnum,5000>::GetCallerSessionId");
LABEL_115:
    _DbgPrintMessage(
      8,
      "GetCallerSessionId failed: 0x%x in %s",
      (unsigned int)v23,
      "CObjectAccessTracker<struct ISessionEnum,5000>::CObjectAccessTracker");
    goto LABEL_45;
  }
  if ( GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFBLL, TokenSessionId, &TokenInformation, 4u, &ReturnLength) )
    goto LABEL_38;
  LastError = GetLastError();
  v23 = LastError;
  if ( LastError > 0 )
    v23 = (unsigned __int16)LastError | 0x80070000;
  if ( v23 >= 0 )
LABEL_38:
    *((_DWORD *)v15 + 401) = (_DWORD)TokenInformation;
  else
    _DbgPrintMessage(
      8,
      "GetTokenInformation failed: 0x%x in %s",
      v23,
      "CObjectAccessTracker<struct ISessionEnum,5000>::GetCallerSessionId");
  v24 = RpcRevertToSelf();
  ReturnLength = v24;
  v25 = v24 < 0;
  if ( v24 > 0 )
  {
    v24 = (unsigned __int16)v24 | 0x80070000;
    v25 = v24 < 0;
  }
  if ( v25 )
    _DbgPrintMessage(8, "RpcRevertToSelf failed 0x%08x", v24);
  v9 = v23;
  if ( v23 < 0 )
    goto LABEL_115;
  if ( !*((_DWORD *)v15 + 401) )
    goto LABEL_45;
  v28 = I_RpcBindingInqLocalClientPID(0, (unsigned int *)v15 + 400);
  v9 = v28;
  if ( v28 > 0 )
    v9 = (unsigned __int16)v28 | 0x80070000;
  if ( v9 < 0 )
  {
    _DbgPrintMessage(
      8,
      "I_RpcBindingInqLocalClientPID failed: 0x%x in %s",
      (unsigned int)v9,
      "CObjectAccessTracker<struct ISessionEnum,5000>::CObjectAccessTracker");
    goto LABEL_45;
  }
LABEL_70:
  v29 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD *))(*(_QWORD *)v15[201] + 24LL))(v15[201], 5000, v15 + 202);
  v9 = v29;
  if ( v29 < 0 )
    _DbgPrintMessage(
      8,
      "m_pCientTracker->TrackCaller failed: 0x%x in %s",
      (unsigned int)v29,
      "CObjectAccessTracker<struct ISessionEnum,5000>::CObjectAccessTracker");
LABEL_45:
  (*(void (__fastcall **)(_QWORD *))(*v15 + 8LL))(v15);
  if ( v9 < 0 )
    goto LABEL_74;
  v26 = v15;
  (*(void (__fastcall **)(_QWORD *))(*v15 + 8LL))(v15);
LABEL_47:
  if ( v15 )
    (*(void (__fastcall **)(_QWORD *))(*v15 + 16LL))(v15);
  if ( v9 < 0 )
    _DbgPrintMessage(8, "SESSIONENUMTRACKER::GetInstanceOfObject failed: 0x%x in %s", v9, "RpcOpenEnum");
  else
    *a2 = v26;
LABEL_51:
  v47 = &CRpcCallTrace::`vftable';
  if ( v54 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "%s with Trace ID 0x%x Completed", v52, v49[0]);
  v47 = &CTraceBase::`vftable';
  if ( CTraceBase::g_bEnabled && !v51 && CTraceBase::g_TLSIndex != -1 )
  {
    if ( TlsSetValue(CTraceBase::g_TLSIndex, 0) )
    {
      if ( TlsSetValue(CTraceBase::g_CreatorFunctionTLSIndex, 0) )
        goto LABEL_53;
    }
    else
    {
      GetLastError();
    }
    GetLastError();
  }
LABEL_53:
  v50 = 0;
  if ( v42 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
  if ( v43 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
  if ( v44 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
  if ( v3 )
    (*(void (__fastcall **)(struct ISessionManagerInternal *))(*(_QWORD *)v3 + 16LL))(v3);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000ff60  push    rbp
0x18000ff62  push    rbx
0x18000ff63  push    rsi
0x18000ff64  push    rdi
0x18000ff65  push    r12
0x18000ff67  push    r13
0x18000ff69  push    r14
0x18000ff6b  push    r15
0x18000ff6d  lea     rbp, [rsp-2E8h]
0x18000ff75  sub     rsp, 3E8h
0x18000ff7c  mov     rax, cs:__security_cookie
0x18000ff83  xor     rax, rsp
0x18000ff86  mov     [rbp+320h+var_50], rax
0x18000ff8d  mov     r12, rdx
0x18000ff90  xor     r13d, r13d
0x18000ff93  mov     ebx, r13d
0x18000ff96  mov     [rsp+420h+var_3C8], r13
0x18000ff9b  mov     [rsp+420h+var_3D0], r13
0x18000ffa0  mov     [rsp+420h+var_3D8], r13
0x18000ffa5  lea     r14, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x18000ffac  mov     [rsp+420h+var_3B0], r14
0x18000ffb1  mov     [rbp+320h+var_394], 1
0x18000ffb8  mov     [rbp+320h+var_390], r13
0x18000ffbc  lea     r15, aRpcopenenum; "RpcOpenEnum"
0x18000ffc3  cmp     cs:?g_bEnabled@CTraceBase@@0HA, r13d; int CTraceBase::g_bEnabled
0x18000ffca  jnz     loc_180010615
0x18000ffd0  lea     rcx, [rsp+420h+pguid]; pguid
0x18000ffd5  call    cs:__imp_CoCreateGuid
0x18000ffdb  mov     eax, 1
0x18000ffe0  lock xadd cs:?g_NextShortActivityID@CTraceBase@@0KA, eax; ulong CTraceBase::g_NextShortActivityID
0x18000ffe8  inc     eax
0x18000ffea  mov     [rbp+320h+var_398], eax
0x18000ffed  mov     [rbp+320h+var_388], r13d
0x18000fff1  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x18000fff8  mov     [rsp+420h+var_3B0], rax
0x18000fffd  mov     [rbp+320h+var_380], r15
0x180010001  mov     qword ptr [rbp+320h+Pid], 0FFFFFFFFFFFFFFFFh
0x180010009  mov     [rbp+320h+var_370], r13d
0x18001000d  xor     edx, edx; Val
0x18001000f  mov     r8d, 208h; Size
0x180010015  lea     rcx, [rbp+320h+var_36C]; void *
0x180010019  call    memset_0
0x18001001e  cmp     [rbp+320h+var_370], ebx
0x180010021  jnz     loc_180010541
0x180010027  mov     esi, r13d
0x18001002a  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x180010031  jnz     loc_180010729
0x180010037  mov     qword ptr [rbp+320h+Pid], 0FFFFFFFFFFFFFFFFh
0x18001003f  lea     rdx, [rbp+320h+Pid+4]; Pid
0x180010043  xor     ecx, ecx; Binding
0x180010045  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18001004b  mov     edi, eax
0x18001004d  test    eax, eax
0x18001004f  jg      loc_180010448
0x180010055  test    edi, edi
0x180010057  js      short loc_18001006E
0x180010059  lea     rdx, [rbp+320h+Pid]; pSessionId
0x18001005d  mov     ecx, [rbp+320h+Pid+4]; dwProcessId
0x180010060  call    cs:__imp_ProcessIdToSessionId
0x180010066  test    esi, esi
0x180010068  jnz     loc_180010733
0x18001006e  cmp     [rbp+320h+var_370], ebx
0x180010071  jnz     loc_180010597
0x180010077  test    r12, r12
0x18001007a  jz      loc_180010423
0x180010080  mov     [rsp+420h+var_3E0], 80004001h
0x180010088  mov     rax, cs:?pSMGlobalInstance@ISessionManagerInternal@@0PEAV1@EA; ISessionManagerInternal * ISessionManagerInternal::pSMGlobalInstance
0x18001008f  test    rax, rax
0x180010092  jz      loc_1800107BD
0x180010098  mov     [rsp+420h+var_3E0], r13d
0x18001009d  mov     rbx, rax
0x1800100a0  mov     rax, [rax]
0x1800100a3  mov     rcx, rbx
0x1800100a6  mov     rax, [rax+8]
0x1800100aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100af  mov     rax, [rbx]
0x1800100b2  lea     rdx, [rsp+420h+var_3D8]
0x1800100b7  mov     rcx, rbx
0x1800100ba  mov     rax, [rax+0C8h]
0x1800100c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100c6  mov     edi, eax
0x1800100c8  test    eax, eax
0x1800100ca  js      loc_1800104DD
0x1800100d0  mov     rax, [rbx]
0x1800100d3  lea     rdx, [rsp+420h+var_3C8]
0x1800100d8  mov     rcx, rbx
0x1800100db  mov     rax, [rax+18h]
0x1800100df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100e4  mov     edi, eax
0x1800100e6  test    eax, eax
0x1800100e8  js      loc_1800105CF
0x1800100ee  mov     rcx, [rsp+420h+var_3C8]
0x1800100f3  mov     rax, [rcx]
0x1800100f6  lea     rdx, [rsp+420h+var_3D0]
0x1800100fb  mov     rax, [rax+20h]
0x1800100ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010104  mov     edi, eax
0x180010106  test    eax, eax
0x180010108  js      loc_18001081A
0x18001010e  mov     r15, [rsp+420h+var_3D8]
0x180010113  mov     r14, [rsp+420h+var_3D0]
0x180010118  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001011f  mov     ecx, 658h; unsigned __int64
0x180010124  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180010129  mov     rsi, rax
0x18001012c  test    rax, rax
0x18001012f  jz      loc_180010516
0x180010135  lea     rax, ??_7?$CTSPrivateObject@UIUnknown@@@@6B@; const CTSPrivateObject<IUnknown>::`vftable'
0x18001013c  mov     [rsi], rax
0x18001013f  lea     rax, aSessionenumtra_0; "SESSIONENUMTRACKER"
0x180010146  mov     [rsi+10h], rax
0x18001014a  mov     [rsi+8], r13d
0x18001014e  mov     dword ptr [rsi+0Ch], 1
0x180010155  lea     rdi, [rsi+628h]
0x18001015c  mov     [rdi+8], rdi
0x180010160  mov     [rdi], rdi
0x180010163  mov     r13, cs:?g_pObjectTracker@@3PEAVCObjectTracker@@EA; CObjectTracker * g_pObjectTracker
0x18001016a  test    r13, r13
0x18001016d  jz      loc_1800105EB
0x180010173  lea     rdx, [r13+18h]; struct CResource *
0x180010177  lea     rcx, [rsp+420h+Resource]; this
0x18001017c  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x180010181  lea     rax, [r13+8]
0x180010185  mov     rcx, [rax+8]
0x180010189  cmp     [rcx], rax
0x18001018c  jnz     loc_180010836
0x180010192  mov     [rdi], rax
0x180010195  mov     [rdi+8], rcx
0x180010199  mov     [rcx], rdi
0x18001019c  mov     [rax+8], rdi
0x1800101a0  xor     edi, edi
0x1800101a2  cmp     [rsp+420h+var_3B8], edi
0x1800101a6  jz      short loc_1800101BD
0x1800101a8  mov     [rsp+420h+var_3B8], edi
0x1800101ac  mov     rcx, [rsp+420h+Resource]; Resource
0x1800101b1  cmp     [rcx+60h], edi
0x1800101b4  jz      short loc_1800101BD
0x1800101b6  call    cs:__imp_RtlReleaseResource
0x1800101bc  nop
0x1800101bd  mov     [rsi+18h], rdi
0x1800101c1  mov     [rsi+20h], edi
0x1800101c4  mov     dword ptr [rsp+420h+TokenInformation], edi
0x1800101c8  mov     eax, 1
0x1800101cd  lock xadd [rsi+20h], eax
0x1800101d2  inc     eax
0x1800101d4  cmp     cs:?g_bCaptureObjectStackTrace@@3HA, 1; int g_bCaptureObjectStackTrace
0x1800101db  jz      loc_18001083D
0x1800101e1  lea     rax, ??_7?$CObjectAccessTracker@UISessionEnum@@$0BDII@@@6B@; const CObjectAccessTracker<ISessionEnum,5000>::`vftable'
0x1800101e8  mov     [rsi], rax
0x1800101eb  mov     [rsi+638h], r14
0x1800101f2  test    r14, r14
0x1800101f5  jz      short loc_180010206
0x1800101f7  mov     rax, [r14]
0x1800101fa  mov     rcx, r14
0x1800101fd  mov     rax, [rax+8]
0x180010201  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010206  mov     qword ptr [rsi+640h], 0FFFFFFFFFFFFFFFFh
0x180010211  mov     [rsi+648h], r15
0x180010218  test    r15, r15
0x18001021b  jz      short loc_18001022C
0x18001021d  mov     rax, [r15]
0x180010220  mov     rcx, r15
0x180010223  mov     rax, [rax+8]
0x180010227  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001022c  mov     [rsi+650h], rdi
0x180010233  mov     [rsp+420h+ClientLocalFlag], edi
0x180010237  lea     rdx, [rsp+420h+ClientLocalFlag]; ClientLocalFlag
0x18001023c  xor     ecx, ecx; BindingHandle
0x18001023e  call    cs:__imp_I_RpcBindingIsClientLocal
0x180010244  test    eax, eax
0x180010246  jg      loc_1800104C0
0x18001024c  js      loc_180010477
0x180010252  cmp     [rsp+420h+ClientLocalFlag], 0
0x180010257  jz      loc_180010477
0x18001025d  mov     [rsp+420h+var_3F0], edi
0x180010261  mov     dword ptr [rsp+420h+TokenInformation], edi
0x180010265  xor     ecx, ecx; BindingHandle
0x180010267  call    cs:__imp_RpcImpersonateClient
0x18001026d  mov     edi, eax
0x18001026f  mov     [rsp+420h+var_3F0], eax
0x180010273  test    eax, eax
0x180010275  jg      loc_1800104CF
0x18001027b  mov     r14d, edi
0x18001027e  test    edi, edi
0x180010280  js      loc_180010869
0x180010286  lea     rax, [rsp+420h+var_3F0]
0x18001028b  mov     [rsp+420h+ReturnLength], rax; ReturnLength
0x180010290  mov     r9d, 4; TokenInformationLength
0x180010296  lea     r8, [rsp+420h+TokenInformation]; TokenInformation
0x18001029b  mov     edx, 0Ch; TokenInformationClass
0x1800102a0  mov     rcx, 0FFFFFFFFFFFFFFFBh; TokenHandle
0x1800102a7  call    cs:__imp_GetTokenInformation
0x1800102ad  test    eax, eax
0x1800102af  jz      loc_1800106C8
0x1800102b5  mov     eax, dword ptr [rsp+420h+TokenInformation]
0x1800102b9  mov     [rsi+644h], eax
0x1800102bf  call    cs:__imp_RpcRevertToSelf
0x1800102c5  mov     [rsp+420h+var_3F0], eax
0x1800102c9  test    eax, eax
0x1800102cb  jg      loc_1800104F9
0x1800102d1  js      loc_180010893
0x1800102d7  mov     edi, r14d
0x1800102da  test    r14d, r14d
0x1800102dd  js      loc_180010884
0x1800102e3  cmp     dword ptr [rsi+644h], 0
0x1800102ea  jnz     loc_180010456
0x1800102f0  mov     rax, [rsi]
0x1800102f3  mov     rcx, rsi
0x1800102f6  mov     rax, [rax+8]
0x1800102fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102ff  test    edi, edi
0x180010301  js      loc_1800108BB
0x180010307  mov     r14, rsi
0x18001030a  mov     rax, [rsi]
0x18001030d  mov     rcx, rsi
0x180010310  mov     rax, [rax+8]
0x180010314  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010319  xor     r13d, r13d
0x18001031c  test    rsi, rsi
0x18001031f  jz      short loc_180010331
0x180010321  mov     rax, [rsi]
0x180010324  mov     rcx, rsi
0x180010327  mov     rax, [rax+10h]
0x18001032b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010330  nop
0x180010331  test    edi, edi
0x180010333  js      loc_1800108C3
0x180010339  mov     [r12], r14
0x18001033d  lea     r14, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x180010344  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x18001034b  mov     [rsp+420h+var_3B0], rax
0x180010350  cmp     [rbp+320h+var_370], 0
0x180010354  jnz     loc_18001056C
0x18001035a  mov     [rsp+420h+var_3B0], r14
0x18001035f  cmp     cs:?g_bEnabled@CTraceBase@@0HA, 0; int CTraceBase::g_bEnabled
0x180010366  jnz     loc_1800103EF
0x18001036c  mov     [rbp+320h+var_390], r13
0x180010370  mov     rcx, [rsp+420h+var_3D8]
0x180010375  test    rcx, rcx
0x180010378  jz      short loc_180010387
0x18001037a  mov     rax, [rcx]
0x18001037d  mov     rax, [rax+10h]
0x180010381  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010386  nop
0x180010387  mov     rcx, [rsp+420h+var_3D0]
0x18001038c  test    rcx, rcx
0x18001038f  jz      short loc_18001039E
0x180010391  mov     rax, [rcx]
0x180010394  mov     rax, [rax+10h]
0x180010398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001039d  nop
0x18001039e  mov     rcx, [rsp+420h+var_3C8]
0x1800103a3  test    rcx, rcx
0x1800103a6  jz      short loc_1800103B5
0x1800103a8  mov     rax, [rcx]
0x1800103ab  mov     rax, [rax+10h]
0x1800103af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103b4  nop
0x1800103b5  test    rbx, rbx
0x1800103b8  jz      short loc_1800103CA
0x1800103ba  mov     rax, [rbx]
0x1800103bd  mov     rcx, rbx
0x1800103c0  mov     rax, [rax+10h]
0x1800103c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103c9  nop
0x1800103ca  mov     eax, edi
0x1800103cc  mov     rcx, [rbp+320h+var_50]
0x1800103d3  xor     rcx, rsp; StackCookie
0x1800103d6  call    __security_check_cookie
0x1800103db  add     rsp, 3E8h
0x1800103e2  pop     r15
0x1800103e4  pop     r14
0x1800103e6  pop     r13
0x1800103e8  pop     r12
0x1800103ea  pop     rdi
0x1800103eb  pop     rsi
0x1800103ec  pop     rbx
0x1800103ed  pop     rbp
0x1800103ee  retn
0x1800103ef  cmp     [rbp+320h+var_388], 0
0x1800103f3  jnz     loc_18001036C
0x1800103f9  mov     ecx, cs:?g_TLSIndex@CTraceBase@@0KA; dwTlsIndex
0x1800103ff  cmp     ecx, 0FFFFFFFFh
0x180010402  jz      loc_18001036C
0x180010408  xor     edx, edx; lpTlsValue
0x18001040a  call    cs:__imp_TlsSetValue
0x180010410  test    eax, eax
0x180010412  jnz     loc_1800108E3
0x180010418  call    cs:__imp_GetLastError
0x18001041e  jmp     loc_1800108F9
0x180010423  mov     r9, r15
0x180010426  lea     r8, aPhenum_0; "phEnum"
0x18001042d  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x180010434  mov     ecx, 8; int
0x180010439  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001043e  mov     edi, 80070057h
0x180010443  jmp     loc_180010344
0x180010448  movzx   edi, ax
0x18001044b  or      edi, 80070000h
0x180010451  jmp     loc_180010055
  ... truncated ...
```
