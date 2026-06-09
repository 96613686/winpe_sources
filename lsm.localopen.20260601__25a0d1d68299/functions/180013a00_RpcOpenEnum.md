# RpcOpenEnum

- ea: `0x180013a00`
- end: `0x18001441c`
- name: `RpcOpenEnum`
- size: `2588`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800077a0`
- `0x180009580`
- `0x1800101b0`
- `0x180010260`
- `0x180013a00`
- `0x180014b20`
- `0x180029158`
- `0x18004e850`
- `0x18004ec5c`
- `0x18004f354`
- `0x1800637cc`
- `0x18009c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18001427b`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18001427b`
- `ntdll!RtlReleaseResource` at `0x180013c68`
- `ntdll!RtlReleaseResource` at `0x180013c68`
- `ntdll!RtlCaptureStackBackTrace` at `0x180014363`
- `ntdll!RtlCaptureStackBackTrace` at `0x180014363`
- `ntdll!NtQueryInformationProcess` at `0x180014259`
- `ntdll!NtQueryInformationProcess` at `0x180014259`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013eef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800141af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001440a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013eef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800141af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001440a`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180013edb`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800143f6`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180013edb`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800143f6`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180013b0c`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180013b0c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800142aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800142aa`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180013a75`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180013a75`
- `RPCRT4!RpcImpersonateClient` at `0x180013d25`
- `RPCRT4!RpcImpersonateClient` at `0x180013d25`
- `RPCRT4!RpcRevertToSelf` at `0x180013d89`
- `RPCRT4!RpcRevertToSelf` at `0x180013d89`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180013cf6`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180013cf6`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180013aeb`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180013f3c`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180013aeb`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180013f3c`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001422b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001422b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180013d6b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180013d6b`

## string_xrefs

- `0x180013a5c`: `RpcOpenEnum`
- `0x1800143ce`: `RpcOpenEnum`
- `0x18001400e`: `new CAccessTracker failed: 0x%x in %s`
- `0x180014004`: `CObjectAccessTracker<struct ISessionEnum,5000>::GetInstanceOfObject`
- `0x18001437e`: `RpcImpersonateClient failed: 0x%x in %s`
- `0x180014064`: `%s with Trace ID 0x%x Completed`
- `0x180013f8d`: `CObjectAccessTracker<struct ISessionEnum,5000>::CObjectAccessTracker`
- `0x1800141e0`: `GetTokenInformation failed: 0x%x in %s`
- `0x1800141d6`: `CObjectAccessTracker<struct ISessionEnum,5000>::GetCallerSessionId`
- `0x180014374`: `CObjectAccessTracker<struct ISessionEnum,5000>::GetCallerSessionId`
- `0x18001414b`: `TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC`
- `0x18001409c`: `RPC Caller: PID %d, SessID %d, Process Name: <%S>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180013a00  push    rbp
0x180013a02  push    rbx
0x180013a03  push    rsi
0x180013a04  push    rdi
0x180013a05  push    r12
0x180013a07  push    r13
0x180013a09  push    r14
0x180013a0b  push    r15
0x180013a0d  lea     rbp, [rsp-2E8h]
0x180013a15  sub     rsp, 3E8h
0x180013a1c  mov     rax, cs:__security_cookie
0x180013a23  xor     rax, rsp
0x180013a26  mov     [rbp+320h+var_50], rax
0x180013a2d  mov     r12, rdx
0x180013a30  xor     r13d, r13d
0x180013a33  mov     ebx, r13d
0x180013a36  mov     [rsp+420h+var_3C8], r13
0x180013a3b  mov     [rsp+420h+var_3D0], r13
0x180013a40  mov     [rsp+420h+var_3D8], r13
0x180013a45  lea     r14, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x180013a4c  mov     [rsp+420h+var_3B0], r14
0x180013a51  mov     [rbp+320h+var_394], 1
0x180013a58  mov     [rbp+320h+var_390], r13
0x180013a5c  lea     r15, aRpcopenenum; "RpcOpenEnum"
0x180013a63  cmp     cs:?g_bEnabled@CTraceBase@@0HA, r13d; int CTraceBase::g_bEnabled
0x180013a6a  jnz     loc_1800140F8
0x180013a70  lea     rcx, [rsp+420h+pguid]; pguid
0x180013a75  call    cs:__imp_CoCreateGuid
0x180013a7c  nop     dword ptr [rax+rax+00h]
0x180013a81  mov     eax, 1
0x180013a86  lock xadd cs:?g_NextShortActivityID@CTraceBase@@0KA, eax; ulong CTraceBase::g_NextShortActivityID
0x180013a8e  inc     eax
0x180013a90  mov     [rbp+320h+var_398], eax
0x180013a93  mov     [rbp+320h+var_388], r13d
0x180013a97  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x180013a9e  mov     [rsp+420h+var_3B0], rax
0x180013aa3  mov     [rbp+320h+var_380], r15
0x180013aa7  mov     qword ptr [rbp+320h+Pid], 0FFFFFFFFFFFFFFFFh
0x180013aaf  mov     [rbp+320h+var_370], r13d
0x180013ab3  xor     edx, edx; Val
0x180013ab5  mov     r8d, 208h; Size
0x180013abb  lea     rcx, [rbp+320h+var_36C]; void *
0x180013abf  call    memset_0
0x180013ac4  cmp     [rbp+320h+var_370], ebx
0x180013ac7  jnz     loc_180014024
0x180013acd  mov     esi, r13d
0x180013ad0  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x180013ad7  jnz     loc_180014216
0x180013add  mov     qword ptr [rbp+320h+Pid], 0FFFFFFFFFFFFFFFFh
0x180013ae5  lea     rdx, [rbp+320h+Pid+4]; Pid
0x180013ae9  xor     ecx, ecx; Binding
0x180013aeb  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x180013af2  nop     dword ptr [rax+rax+00h]
0x180013af7  mov     edi, eax
0x180013af9  test    eax, eax
0x180013afb  jg      loc_180013F25
0x180013b01  test    edi, edi
0x180013b03  js      short loc_180013B20
0x180013b05  lea     rdx, [rbp+320h+Pid]; pSessionId
0x180013b09  mov     ecx, [rbp+320h+Pid+4]; dwProcessId
0x180013b0c  call    cs:__imp_ProcessIdToSessionId
0x180013b13  nop     dword ptr [rax+rax+00h]
0x180013b18  test    esi, esi
0x180013b1a  jnz     loc_180014220
0x180013b20  cmp     [rbp+320h+var_370], ebx
0x180013b23  jnz     loc_18001407A
0x180013b29  test    r12, r12
0x180013b2c  jz      loc_180013F00
0x180013b32  mov     [rsp+420h+var_3E0], 80004001h
0x180013b3a  mov     rax, cs:?pSMGlobalInstance@ISessionManagerInternal@@0PEAV1@EA; ISessionManagerInternal * ISessionManagerInternal::pSMGlobalInstance
0x180013b41  test    rax, rax
0x180013b44  jz      loc_1800142C2
0x180013b4a  mov     [rsp+420h+var_3E0], r13d
0x180013b4f  mov     rbx, rax
0x180013b52  mov     rax, [rax]
0x180013b55  mov     rcx, rbx
0x180013b58  mov     rax, [rax+8]
0x180013b5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b61  mov     rax, [rbx]
0x180013b64  lea     rdx, [rsp+420h+var_3D8]
0x180013b69  mov     rcx, rbx
0x180013b6c  mov     rax, [rax+0C8h]
0x180013b73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b78  mov     edi, eax
0x180013b7a  test    eax, eax
0x180013b7c  js      loc_180013FC0
0x180013b82  mov     rax, [rbx]
0x180013b85  lea     rdx, [rsp+420h+var_3C8]
0x180013b8a  mov     rcx, rbx
0x180013b8d  mov     rax, [rax+18h]
0x180013b91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b96  mov     edi, eax
0x180013b98  test    eax, eax
0x180013b9a  js      loc_1800140B2
0x180013ba0  mov     rcx, [rsp+420h+var_3C8]
0x180013ba5  mov     rax, [rcx]
0x180013ba8  lea     rdx, [rsp+420h+var_3D0]
0x180013bad  mov     rax, [rax+20h]
0x180013bb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013bb6  mov     edi, eax
0x180013bb8  test    eax, eax
0x180013bba  js      loc_18001431F
0x180013bc0  mov     r15, [rsp+420h+var_3D8]
0x180013bc5  mov     r14, [rsp+420h+var_3D0]
0x180013bca  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180013bd1  mov     ecx, 658h; unsigned __int64
0x180013bd6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180013bdb  mov     rsi, rax
0x180013bde  test    rax, rax
0x180013be1  jz      loc_180013FF9
0x180013be7  lea     rax, ??_7?$CTSPrivateObject@UIUnknown@@@@6B@; const CTSPrivateObject<IUnknown>::`vftable'
0x180013bee  mov     [rsi], rax
0x180013bf1  lea     rax, aSessionenumtra_0; "SESSIONENUMTRACKER"
0x180013bf8  mov     [rsi+10h], rax
0x180013bfc  mov     [rsi+8], r13d
0x180013c00  mov     dword ptr [rsi+0Ch], 1
0x180013c07  lea     rdi, [rsi+628h]
0x180013c0e  mov     [rdi+8], rdi
0x180013c12  mov     [rdi], rdi
0x180013c15  mov     r13, cs:?g_pObjectTracker@@3PEAVCObjectTracker@@EA; CObjectTracker * g_pObjectTracker
0x180013c1c  test    r13, r13
0x180013c1f  jz      loc_1800140CE
0x180013c25  lea     rdx, [r13+18h]; struct CResource *
0x180013c29  lea     rcx, [rsp+420h+Resource]; this
0x180013c2e  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x180013c33  lea     rax, [r13+8]
0x180013c37  mov     rcx, [rax+8]
0x180013c3b  cmp     [rcx], rax
0x180013c3e  jnz     loc_18001433B
0x180013c44  mov     [rdi], rax
0x180013c47  mov     [rdi+8], rcx
0x180013c4b  mov     [rcx], rdi
0x180013c4e  mov     [rax+8], rdi
0x180013c52  xor     edi, edi
0x180013c54  cmp     [rsp+420h+var_3B8], edi
0x180013c58  jz      short loc_180013C75
0x180013c5a  mov     [rsp+420h+var_3B8], edi
0x180013c5e  mov     rcx, [rsp+420h+Resource]; Resource
0x180013c63  cmp     [rcx+60h], edi
0x180013c66  jz      short loc_180013C75
0x180013c68  call    cs:__imp_RtlReleaseResource
0x180013c6f  nop     dword ptr [rax+rax+00h]
0x180013c74  nop
0x180013c75  mov     [rsi+18h], rdi
0x180013c79  mov     [rsi+20h], edi
0x180013c7c  mov     dword ptr [rsp+420h+TokenInformation], edi
0x180013c80  mov     eax, 1
0x180013c85  lock xadd [rsi+20h], eax
0x180013c8a  inc     eax
0x180013c8c  cmp     cs:?g_bCaptureObjectStackTrace@@3HA, 1; int g_bCaptureObjectStackTrace
0x180013c93  jz      loc_180014342
0x180013c99  lea     rax, ??_7?$CObjectAccessTracker@UISessionEnum@@$0BDII@@@6B@; const CObjectAccessTracker<ISessionEnum,5000>::`vftable'
0x180013ca0  mov     [rsi], rax
0x180013ca3  mov     [rsi+638h], r14
0x180013caa  test    r14, r14
0x180013cad  jz      short loc_180013CBE
0x180013caf  mov     rax, [r14]
0x180013cb2  mov     rcx, r14
0x180013cb5  mov     rax, [rax+8]
0x180013cb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013cbe  mov     qword ptr [rsi+640h], 0FFFFFFFFFFFFFFFFh
0x180013cc9  mov     [rsi+648h], r15
0x180013cd0  test    r15, r15
0x180013cd3  jz      short loc_180013CE4
0x180013cd5  mov     rax, [r15]
0x180013cd8  mov     rcx, r15
0x180013cdb  mov     rax, [rax+8]
0x180013cdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ce4  mov     [rsi+650h], rdi
0x180013ceb  mov     [rsp+420h+ClientLocalFlag], edi
0x180013cef  lea     rdx, [rsp+420h+ClientLocalFlag]; ClientLocalFlag
0x180013cf4  xor     ecx, ecx; BindingHandle
0x180013cf6  call    cs:__imp_I_RpcBindingIsClientLocal
0x180013cfd  nop     dword ptr [rax+rax+00h]
0x180013d02  test    eax, eax
0x180013d04  jg      loc_180013FA3
0x180013d0a  js      loc_180013F5A
0x180013d10  cmp     [rsp+420h+ClientLocalFlag], 0
0x180013d15  jz      loc_180013F5A
0x180013d1b  mov     [rsp+420h+var_3F0], edi
0x180013d1f  mov     dword ptr [rsp+420h+TokenInformation], edi
0x180013d23  xor     ecx, ecx; BindingHandle
0x180013d25  call    cs:__imp_RpcImpersonateClient
0x180013d2c  nop     dword ptr [rax+rax+00h]
0x180013d31  mov     edi, eax
0x180013d33  mov     [rsp+420h+var_3F0], eax
0x180013d37  test    eax, eax
0x180013d39  jg      loc_180013FB2
0x180013d3f  mov     r14d, edi
0x180013d42  test    edi, edi
0x180013d44  js      loc_180014374
0x180013d4a  lea     rax, [rsp+420h+var_3F0]
0x180013d4f  mov     [rsp+420h+ReturnLength], rax; ReturnLength
0x180013d54  mov     r9d, 4; TokenInformationLength
0x180013d5a  lea     r8, [rsp+420h+TokenInformation]; TokenInformation
0x180013d5f  mov     edx, 0Ch; TokenInformationClass
0x180013d64  mov     rcx, 0FFFFFFFFFFFFFFFBh; TokenHandle
0x180013d6b  call    cs:__imp_GetTokenInformation
0x180013d72  nop     dword ptr [rax+rax+00h]
0x180013d77  test    eax, eax
0x180013d79  jz      loc_1800141AF
0x180013d7f  mov     eax, dword ptr [rsp+420h+TokenInformation]
0x180013d83  mov     [rsi+644h], eax
0x180013d89  call    cs:__imp_RpcRevertToSelf
0x180013d90  nop     dword ptr [rax+rax+00h]
0x180013d95  mov     [rsp+420h+var_3F0], eax
0x180013d99  test    eax, eax
0x180013d9b  jg      loc_180013FDC
0x180013da1  js      loc_18001439E
0x180013da7  mov     edi, r14d
0x180013daa  test    r14d, r14d
0x180013dad  js      loc_18001438F
0x180013db3  cmp     dword ptr [rsi+644h], 0
0x180013dba  jnz     loc_180013F33
0x180013dc0  mov     rax, [rsi]
0x180013dc3  mov     rcx, rsi
0x180013dc6  mov     rax, [rax+8]
0x180013dca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013dcf  test    edi, edi
0x180013dd1  js      loc_1800143C6
0x180013dd7  mov     r14, rsi
0x180013dda  mov     rax, [rsi]
0x180013ddd  mov     rcx, rsi
0x180013de0  mov     rax, [rax+8]
0x180013de4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013de9  xor     r13d, r13d
0x180013dec  test    rsi, rsi
0x180013def  jz      short loc_180013E01
0x180013df1  mov     rax, [rsi]
0x180013df4  mov     rcx, rsi
0x180013df7  mov     rax, [rax+10h]
0x180013dfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e00  nop
0x180013e01  test    edi, edi
0x180013e03  js      loc_1800143CE
0x180013e09  mov     [r12], r14
0x180013e0d  lea     r14, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x180013e14  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x180013e1b  mov     [rsp+420h+var_3B0], rax
0x180013e20  cmp     [rbp+320h+var_370], 0
0x180013e24  jnz     loc_18001404F
0x180013e2a  mov     [rsp+420h+var_3B0], r14
0x180013e2f  cmp     cs:?g_bEnabled@CTraceBase@@0HA, 0; int CTraceBase::g_bEnabled
0x180013e36  jnz     loc_180013EC0
0x180013e3c  mov     [rbp+320h+var_390], r13
0x180013e40  mov     rcx, [rsp+420h+var_3D8]
0x180013e45  test    rcx, rcx
0x180013e48  jz      short loc_180013E57
0x180013e4a  mov     rax, [rcx]
0x180013e4d  mov     rax, [rax+10h]
0x180013e51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e56  nop
0x180013e57  mov     rcx, [rsp+420h+var_3D0]
0x180013e5c  test    rcx, rcx
0x180013e5f  jz      short loc_180013E6E
0x180013e61  mov     rax, [rcx]
0x180013e64  mov     rax, [rax+10h]
0x180013e68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e6d  nop
0x180013e6e  mov     rcx, [rsp+420h+var_3C8]
0x180013e73  test    rcx, rcx
0x180013e76  jz      short loc_180013E85
0x180013e78  mov     rax, [rcx]
0x180013e7b  mov     rax, [rax+10h]
0x180013e7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e84  nop
0x180013e85  test    rbx, rbx
0x180013e88  jz      short loc_180013E9A
0x180013e8a  mov     rax, [rbx]
0x180013e8d  mov     rcx, rbx
0x180013e90  mov     rax, [rax+10h]
0x180013e94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e99  nop
0x180013e9a  mov     eax, edi
0x180013e9c  mov     rcx, [rbp+320h+var_50]
0x180013ea3  xor     rcx, rsp; StackCookie
0x180013ea6  call    __security_check_cookie
0x180013eab  add     rsp, 3E8h
0x180013eb2  pop     r15
0x180013eb4  pop     r14
0x180013eb6  pop     r13
0x180013eb8  pop     r12
0x180013eba  pop     rdi
0x180013ebb  pop     rsi
0x180013ebc  pop     rbx
0x180013ebd  pop     rbp
0x180013ebe  retn
0x180013ec0  cmp     [rbp+320h+var_388], 0
0x180013ec4  jnz     loc_180013E3C
0x180013eca  mov     ecx, cs:?g_TLSIndex@CTraceBase@@0KA; dwTlsIndex
0x180013ed0  cmp     ecx, 0FFFFFFFFh
0x180013ed3  jz      loc_180013E3C
0x180013ed9  xor     edx, edx; lpTlsValue
0x180013edb  call    cs:__imp_TlsSetValue
0x180013ee2  nop     dword ptr [rax+rax+00h]
0x180013ee7  test    eax, eax
0x180013ee9  jnz     loc_1800143EE
0x180013eef  call    cs:__imp_GetLastError
0x180013ef6  nop     dword ptr [rax+rax+00h]
0x180013efb  jmp     loc_18001440A
  ... truncated ...
```
