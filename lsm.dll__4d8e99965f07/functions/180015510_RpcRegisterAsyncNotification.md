# RpcRegisterAsyncNotification

- ea: `0x180015510`
- end: `0x1800163ab`
- name: `RpcRegisterAsyncNotification`
- size: `3739`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800077a0`
- `0x180009580`
- `0x18000c62c`
- `0x18000f260`
- `0x1800101b0`
- `0x180010260`
- `0x180014b20`
- `0x180015510`
- `0x1800163b4`
- `0x180016740`
- `0x180016788`
- `0x180016834`
- `0x180029158`
- `0x18004e850`
- `0x18004ec5c`
- `0x18004f174`
- `0x18004f354`
- `0x1800637cc`
- `0x18009c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180016050`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180016050`
- `ntdll!RtlReleaseResource` at `0x1800159bc`
- `ntdll!RtlReleaseResource` at `0x1800159bc`
- `ntdll!RtlCaptureStackBackTrace` at `0x1800162f9`
- `ntdll!RtlCaptureStackBackTrace` at `0x1800162f9`
- `ntdll!NtQueryInformationProcess` at `0x18001602e`
- `ntdll!NtQueryInformationProcess` at `0x18001602e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015caa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015f89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016399`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015caa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015f89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016399`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180015c96`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180016385`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180015c96`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180016385`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180015629`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180015629`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016080`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016080`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015837`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015837`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180015878`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016223`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180015878`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016223`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800158a2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800161ad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800158a2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800161ad`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180015593`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180015593`
- `RPCRT4!RpcImpersonateClient` at `0x180015689`
- `RPCRT4!RpcImpersonateClient` at `0x180015a75`
- `RPCRT4!RpcImpersonateClient` at `0x180015689`
- `RPCRT4!RpcImpersonateClient` at `0x180015a75`
- `RPCRT4!RpcRevertToSelf` at `0x1800156aa`
- `RPCRT4!RpcRevertToSelf` at `0x180015adb`
- `RPCRT4!RpcRevertToSelf` at `0x1800156aa`
- `RPCRT4!RpcRevertToSelf` at `0x180015adb`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180015a46`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180015a46`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180015608`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800156c6`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180015b16`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180015608`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800156c6`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180015b16`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180016000`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180016000`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180015abd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180015abd`

## string_xrefs

- `0x180015cbe`: `Cannot impersonate client: %d`
- `0x180015d8f`: `CObjectAccessTracker<class IPublicNotification,5000>::CObjectAccessTracker`
- `0x180015db3`: `CObjectAccessTracker<class IPublicNotification,5000>::GetInstanceOfObject`
- `0x180015dbd`: `new CAccessTracker failed: 0x%x in %s`
- `0x180016314`: `RpcImpersonateClient failed: 0x%x in %s`
- `0x180015e60`: `%s with Trace ID 0x%x Completed`
- `0x180015fb6`: `GetTokenInformation failed: 0x%x in %s`
- `0x180015fac`: `CObjectAccessTracker<class IPublicNotification,5000>::GetCallerSessionId`
- `0x18001630a`: `CObjectAccessTracker<class IPublicNotification,5000>::GetCallerSessionId`
- `0x180015f2a`: `TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC`
- `0x180015e98`: `RPC Caller: PID %d, SessID %d, Process Name: <%S>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RpcRegisterAsyncNotification(__int64 a1, unsigned int a2, unsigned int a3, _QWORD *a4)
{
  _QWORD *v4; // r15
  unsigned int v5; // r13d
  struct ISessionManagerInternal *v6; // rdi
  struct ISessionManagerInternal *v7; // rbx
  unsigned int v8; // r14d
  RPC_STATUS v9; // eax
  int v10; // esi
  struct ISessionManagerInternal *v11; // rax
  RPC_STATUS v12; // eax
  BOOL v13; // esi
  BOOL v14; // r14d
  RPC_STATUS v15; // eax
  unsigned int v16; // r12d
  char *v17; // rax
  char *v18; // r15
  int v19; // eax
  signed int v20; // r14d
  int v21; // eax
  __int64 v22; // r12
  _QWORD *v23; // rax
  _QWORD *v24; // rsi
  _QWORD *v25; // rdi
  _QWORD *v26; // r14
  void **v27; // rcx
  char v28; // al
  RPC_STATUS IsClientLocal; // eax
  bool v30; // sf
  RPC_STATUS v31; // eax
  signed int v32; // edi
  signed int v33; // eax
  bool v34; // sf
  RPC_STATUS v35; // eax
  int v36; // eax
  _QWORD *v37; // r12
  signed int LastError; // eax
  HANDLE v40; // rax
  void *v41; // r15
  NTSTATUS InformationProcess; // eax
  wchar_t *v43; // rax
  wchar_t *v44; // rax
  CSessionManager *v45; // rax
  struct ISessionManagerInternal *v46; // rax
  CSessionManager *v47; // rax
  struct ISessionManagerInternal *v48; // rax
  DWORD ReturnLength; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  DWORD Type; // [rsp+38h] [rbp-C8h] BYREF
  struct CTraceBase *v52; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v53; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v54; // [rsp+4Ch] [rbp-B4h]
  __int64 v55; // [rsp+50h] [rbp-B0h] BYREF
  void **v56; // [rsp+58h] [rbp-A8h] BYREF
  LPBYTE lpData; // [rsp+60h] [rbp-A0h]
  int v58; // [rsp+68h] [rbp-98h]
  HKEY hKey[2]; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v60; // [rsp+80h] [rbp-80h]
  _QWORD *v61; // [rsp+88h] [rbp-78h]
  PRTL_RESOURCE Resource; // [rsp+90h] [rbp-70h] BYREF
  int v63; // [rsp+98h] [rbp-68h]
  void **v64; // [rsp+A0h] [rbp-60h] BYREF
  GUID pguid; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v66[2]; // [rsp+B8h] [rbp-48h] BYREF
  struct CTraceBase *v67; // [rsp+C0h] [rbp-40h] BYREF
  int v68; // [rsp+C8h] [rbp-38h]
  const char *v69; // [rsp+D0h] [rbp-30h]
  unsigned int Pid[2]; // [rsp+D8h] [rbp-28h] BYREF
  int v71; // [rsp+E0h] [rbp-20h]
  unsigned __int16 v72[262]; // [rsp+E4h] [rbp-1Ch] BYREF
  char ProcessInformation[8]; // [rsp+2F0h] [rbp+1F0h] BYREF
  wchar_t *Str; // [rsp+2F8h] [rbp+1F8h]

  v4 = a4;
  v61 = a4;
  v60 = a3;
  v54 = a2;
  v5 = 0;
  v6 = 0;
  v53 = -1;
  v7 = 0;
  v55 = 0;
  v64 = &CTraceBase::`vftable';
  v66[1] = 1;
  v67 = 0;
  if ( CTraceBase::g_bEnabled )
  {
    if ( (g_DebugTraceComponent & 1) != 0 )
      _DbgPrintMessage(2, "Adding trace %p, %d, %s", &v64, 1, "RpcRegisterAsyncNotification");
    v52 = 0;
    if ( (int)CTraceBase::GetThreadCurrentOperationTrace(&v52) >= 0 && v52 && (g_DebugTraceComponent & 1) != 0 )
      _DbgPrintMessage(
        2,
        "TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC",
        1);
    CTraceBase::ResetThreadCurrentOperationTrace(0, 0);
    if ( (int)CTraceBase::GetThreadCurrentOperationTrace(&v67) >= 0 && v67 )
    {
      (*(void (__fastcall **)(struct CTraceBase *, GUID *))(*(_QWORD *)v67 + 32LL))(v67, &pguid);
      v66[0] = (*(__int64 (__fastcall **)(struct CTraceBase *))(*(_QWORD *)v67 + 24LL))(v67);
      v68 = 1;
      goto LABEL_4;
    }
    CTraceBase::ResetThreadCurrentOperationTrace((struct CTraceBase *)&v64, "RpcRegisterAsyncNotification");
    CTraceBase::GenerateTraceID(&pguid, v66);
  }
  else
  {
    CoCreateGuid(&pguid);
    v66[0] = _InterlockedIncrement((volatile signed __int32 *)&CTraceBase::g_NextShortActivityID);
  }
  v68 = 0;
LABEL_4:
  v64 = &CRpcCallTrace::`vftable';
  v69 = "RpcRegisterAsyncNotification";
  *(_QWORD *)Pid = -1;
  v71 = 0;
  memset_0(v72, 0, 0x208u);
  if ( v71 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "TRACE RPC %s with Trace ID 0x%x", v69, v66[0]);
  v8 = 0;
  if ( (g_DebugTraceComponent & 1) != 0 )
    v8 = 260;
  *(_QWORD *)Pid = -1;
  v9 = I_RpcBindingInqLocalClientPID(0, &Pid[1]);
  v10 = v9;
  if ( v9 > 0 )
    v10 = (unsigned __int16)v9 | 0x80070000;
  if ( v10 >= 0 )
  {
    ProcessIdToSessionId(Pid[1], Pid);
    if ( v8 )
    {
      v40 = OpenProcess(0x400u, 0, Pid[1]);
      v41 = v40;
      if ( v40 )
      {
        InformationProcess = NtQueryInformationProcess(v40, ProcessImageFileName, ProcessInformation, 0x110u, 0);
        v10 = InformationProcess | 0x10000000;
        if ( InformationProcess >= 0 )
        {
          v43 = wcsrchr(Str, 0x5Cu);
          if ( v43 )
            v44 = v43 + 1;
          else
            v44 = Str;
          StringCchCopyW(v72, v8, v44);
        }
        CloseHandle(v41);
      }
      v4 = v61;
    }
  }
  if ( v71 )
  {
    if ( v10 < 0 )
    {
      if ( (g_DebugTraceComponent & 1) != 0 )
        _DbgPrintMessage(2, "RPC Caller: Unknown");
    }
    else if ( (g_DebugTraceComponent & 1) != 0 )
    {
      _DbgPrintMessage(2, "RPC Caller: PID %d, SessID %d, Process Name: <%S>", Pid[1], Pid[0], v72);
    }
  }
  if ( !v4 )
  {
    _DbgPrintMessage(8, "Missing paramter %s in %s", "phNotify", "RpcRegisterAsyncNotification");
    v20 = -2147024809;
    goto LABEL_73;
  }
  LOBYTE(v5) = v54 == -1;
  LODWORD(v52) = -2147467263;
  v11 = ISessionManagerInternal::pSMGlobalInstance;
  if ( ISessionManagerInternal::pSMGlobalInstance )
    goto LABEL_14;
  v45 = (CSessionManager *)operator new(0x758u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v45 )
  {
    v46 = CSessionManager::CSessionManager(v45, (int *)&v52);
    ISessionManagerInternal::pSMGlobalInstance = v46;
    if ( v46 )
    {
      (*(void (__fastcall **)(struct ISessionManagerInternal *))(*(_QWORD *)v46 + 8LL))(v46);
      v11 = ISessionManagerInternal::pSMGlobalInstance;
LABEL_14:
      LODWORD(v52) = 0;
      v7 = v11;
      (*(void (__fastcall **)(struct ISessionManagerInternal *))(*(_QWORD *)v11 + 8LL))(v11);
    }
  }
  else
  {
    ISessionManagerInternal::pSMGlobalInstance = 0;
  }
  v12 = RpcImpersonateClient(0);
  if ( !v12 )
  {
    v13 = CUtils::IsCallerSystem() == 0;
    v14 = 0;
    if ( !RpcRevertToSelf() )
      v14 = v13;
    v15 = I_RpcBindingInqLocalClientPID(0, &v53);
    if ( v15 )
      _DbgPrintMessage(8, "I_RpcBindingInqLocalClientPID: %d", v15);
    v16 = v53;
    v17 = (char *)operator new(0xD30u, (const struct std::nothrow_t *)&std::nothrow);
    v18 = v17;
    if ( !v17 )
    {
      v20 = -2147024882;
      goto LABEL_98;
    }
    CTSPrivateObject<IPublicNotification>::CTSPrivateObject<IPublicNotification>(v17);
    *(_QWORD *)v18 = &CPublicNotification::`vftable';
    *((_DWORD *)v18 + 422) = 0;
    *((_QWORD *)v18 + 212) = 0;
    *((_QWORD *)v18 + 213) = 0;
    *((_QWORD *)v18 + 214) = 0;
    *((_DWORD *)v18 + 430) = -1;
    *(_QWORD *)(v18 + 1724) = 0;
    *((_DWORD *)v18 + 438) = 0;
    *((_DWORD *)v18 + 439) = v14;
    *((_DWORD *)v18 + 440) = 0;
    *((_DWORD *)v18 + 441) = 256;
    *((_DWORD *)v18 + 442) = v16;
    CDefTSNotifySink::CDefTSNotifySink((CDefTSNotifySink *)(v18 + 1776));
    *((_QWORD *)v18 + 222) = &CPublicNotification::CTSNotifySink::`vftable';
    v56 = &CRegistry::`vftable';
    lpData = 0;
    v58 = 0;
    hKey[0] = 0;
    hKey[1] = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
    *((_QWORD *)v18 + 218) = v18 + 1736;
    *((_QWORD *)v18 + 217) = v18 + 1736;
    v19 = CResource::Initialize((CResource *)(v18 + 1592));
    v20 = v19;
    if ( v19 < 0 )
    {
      _DbgPrintMessage(8, "Lock->Initialize failed: 0x%x in %s", v19, "CPublicNotification::CPublicNotification");
LABEL_28:
      v56 = &CRegistry::`vftable';
      if ( hKey[0] )
      {
        RegCloseKey(hKey[0]);
        hKey[0] = 0;
      }
      if ( lpData )
        operator delete(lpData);
      v58 = 0;
      lpData = 0;
      if ( v6 )
        (*(void (__fastcall **)(struct ISessionManagerInternal *))(*(_QWORD *)v6 + 16LL))(v6);
      (*(void (__fastcall **)(char *))(*(_QWORD *)v18 + 8LL))(v18);
      if ( v20 >= 0 )
      {
        v21 = (*(__int64 (__fastcall **)(struct ISessionManagerInternal *, __int64 *))(*(_QWORD *)v7 + 200LL))(v7, &v55);
        v20 = v21;
        if ( v21 < 0 )
        {
          _DbgPrintMessage(8, "GetRpcClientTrackerMgr failed: 0x%x in %s", v21, "RpcRegisterAsyncNotification");
          v6 = (struct ISessionManagerInternal *)v18;
          goto LABEL_73;
        }
        v22 = v55;
        v23 = operator new(0x658u, (const struct std::nothrow_t *)&std::nothrow);
        v24 = v23;
        if ( !v23 )
        {
          v24 = 0;
          v20 = -2147024882;
          goto LABEL_96;
        }
        *v23 = &CTSPrivateObject<IUnknown>::`vftable';
        v23[2] = "PUBLICNOTIFICATIONTRACKER";
        *((_DWORD *)v23 + 2) = 0;
        *((_DWORD *)v23 + 3) = 1;
        v25 = v23 + 197;
        v23[198] = v23 + 197;
        v23[197] = v23 + 197;
        v26 = g_pObjectTracker;
        if ( g_pObjectTracker )
        {
          CAutoExclusiveLock::CAutoExclusiveLock(
            (CAutoExclusiveLock *)&Resource,
            (struct CResource *)((char *)g_pObjectTracker + 24));
          v27 = (void **)v26[2];
          if ( *v27 != v26 + 1 )
            __fastfail(3u);
          *v25 = v26 + 1;
          v24[198] = v27;
          *v27 = v25;
          v26[2] = v25;
          if ( v63 )
          {
            v63 = 0;
            if ( LODWORD(Resource[1].Lock.DebugInfo) )
              RtlReleaseResource(Resource);
          }
        }
        v24[3] = 0;
        *((_DWORD *)v24 + 8) = 0;
        ReturnLength = 0;
        v28 = _InterlockedIncrement((volatile signed __int32 *)v24 + 8);
        if ( g_bCaptureObjectStackTrace == 1 )
          RtlCaptureStackBackTrace(1u, 6u, (PVOID *)&v24[6 * (v28 & 0x1F) + 5], &ReturnLength);
        *v24 = &CObjectAccessTracker<IPublicNotification,5000>::`vftable';
        v24[199] = v18;
        (*(void (__fastcall **)(char *))(*(_QWORD *)v18 + 8LL))(v18);
        v24[200] = -1;
        v24[201] = v22;
        if ( v22 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 8LL))(v22);
        v24[202] = 0;
        Type = 0;
        IsClientLocal = I_RpcBindingIsClientLocal(0, &Type);
        v30 = IsClientLocal < 0;
        if ( IsClientLocal > 0 )
          v30 = 1;
        if ( v30 || !Type )
          goto LABEL_64;
        ReturnLength = 0;
        cbData = 0;
        v31 = RpcImpersonateClient(0);
        v20 = v31;
        ReturnLength = v31;
        if ( v31 > 0 )
          v20 = (unsigned __int16)v31 | 0x80070000;
        v32 = v20;
        if ( v20 < 0 )
        {
          _DbgPrintMessage(
            8,
            "RpcImpersonateClient failed: 0x%x in %s",
            v20,
            "CObjectAccessTracker<class IPublicNotification,5000>::GetCallerSessionId");
        }
        else
        {
          if ( GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFBLL, TokenSessionId, &cbData, 4u, &ReturnLength) )
            goto LABEL_54;
          LastError = GetLastError();
          v32 = LastError;
          if ( LastError > 0 )
            v32 = (unsigned __int16)LastError | 0x80070000;
          if ( v32 >= 0 )
LABEL_54:
            *((_DWORD *)v24 + 401) = cbData;
          else
            _DbgPrintMessage(
              8,
              "GetTokenInformation failed: 0x%x in %s",
              v32,
              "CObjectAccessTracker<class IPublicNotification,5000>::GetCallerSessionId");
          v33 = RpcRevertToSelf();
          ReturnLength = v33;
          v34 = v33 < 0;
          if ( v33 > 0 )
          {
            v33 = (unsigned __int16)v33 | 0x80070000;
            v34 = v33 < 0;
          }
          if ( v34 )
            _DbgPrintMessage(8, "RpcRevertToSelf failed 0x%08x", v33);
          v20 = v32;
          if ( v32 >= 0 )
          {
            if ( !*((_DWORD *)v24 + 401) )
              goto LABEL_66;
            v35 = I_RpcBindingInqLocalClientPID(0, (unsigned int *)v24 + 400);
            v20 = v35;
            if ( v35 > 0 )
              v20 = (unsigned __int16)v35 | 0x80070000;
            if ( v20 < 0 )
            {
              _DbgPrintMessage(
                8,
                "I_RpcBindingInqLocalClientPID failed: 0x%x in %s",
                (unsigned int)v20,
                "CObjectAccessTracker<class IPublicNotification,5000>::CObjectAccessTracker");
              goto LABEL_66;
            }
LABEL_64:
            v36 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD *))(*(_QWORD *)v24[201] + 24LL))(
                    v24[201],
                    5000,
                    v24 + 202);
            v20 = v36;
            if ( v36 < 0 )
              _DbgPrintMessage(
                8,
                "m_pCientTracker->TrackCaller failed: 0x%x in %s",
                (unsigned int)v36,
                "CObjectAccessTracker<class IPublicNotification,5000>::CObjectAccessTracker");
LABEL_66:
            (*(void (__fastcall **)(_QWORD *))(*v24 + 8LL))(v24);
            if ( v20 >= 0 )
            {
              v37 = v24;
              (*(void (__fastcall **)(_QWORD *))(*v24 + 8LL))(v24);
              v6 = (struct ISessionManagerInternal *)v18;
              goto LABEL_68;
            }
LABEL_96:
            v6 = (struct ISessionManagerInternal *)v18;
            v37 = 0;
            _DbgPrintMessage(
              8,
              "new CAccessTracker failed: 0x%x in %s",
              v20,
              "CObjectAccessTracker<class IPublicNotification,5000>::GetInstanceOfObject");
LABEL_68:
            if ( v24 )
              (*(void (__fastcall **)(_QWORD *))(*v24 + 16LL))(v24);
            if ( v20 < 0 )
            {
              _DbgPrintMessage(
                8,
                "PUBLICNOTIFICATIONTRACKER::GetInstanceOfObject failed: 0x%x in %s",
                (unsigned int)v20,
                "RpcRegisterAsyncNotification");
            }
            else
            {
              v20 = (*(__int64 (__fastcall **)(struct ISessionManagerInternal *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v6 + 24LL))(
                      v6,
                      v54,
                      v5,
                      v60);
              if ( v20 >= 0 )
              {
                *v61 = v37;
                v20 = 0;
                goto LABEL_73;
              }
              _DbgPrintMessage(
                8,
                "Notification->Register failed: 0x%x in %s",
                (unsigned int)v20,
                "RpcRegisterAsyncNotification");
            }
            if ( v37 )
              (*(void (__fastcall **)(_QWORD *))(*v37 + 16LL))(v37);
LABEL_73:
            v64 = &CRpcCallTrace::`vftable';
            if ( v71 && (g_DebugTraceComponent & 1) != 0 )
              _DbgPrintMessage(2, "%s with Trace ID 0x%x Completed", v69, v66[0]);
            v64 = &CTraceBase::`vftable';
            if ( !CTraceBase::g_bEnabled || v68 || CTraceBase::g_TLSIndex == -1 )
              goto LABEL_75;
            if ( TlsSetValue(CTraceBase::g_TLSIndex, 0) )
            {
              if ( TlsSetValue(CTraceBase::g_CreatorFunctionTLSIndex, 0) )
              {
LABEL_75:
                v67 = 0;
                if ( v55 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
                if ( v7 )
                  (*(void (__fastcall **)(struct ISessionManagerInternal *))(*(_QWORD *)v7 + 16LL))(v7);
                if ( v6 )
                  (*(void (__fastcall **)(struct ISessionManagerInternal *))(*(_QWORD *)v6 + 16LL))(v6);
                return (unsigned int)v20;
              }
            }
            else
            {
              GetLastError();
            }
            GetLastError();
            goto LABEL_75;
          }
        }
        _DbgPrintMessage(
          8,
          "GetCallerSessionId failed: 0x%x in %s",
          (unsigned int)v32,
          "CObjectAccessTracker<class IPublicNotification,5000>::CObjectAccessTracker");
        goto LABEL_66;
      }
      _DbgPrintMessage(
        8,
        "CPublicNotification failed: 0x%x in %s",
        v20,
        "IPublicNotification::GetInstanceOfNotification");
      (*(void (__fastcall **)(char *))(*(_QWORD *)v18 + 16LL))(v18);
      v6 = 0;
LABEL_98:
      _DbgPrintMessage(
        8,
        "IPublicNotification::GetInstanceOfNotification failed: 0x%x in %s",
        v20,
        "RpcRegisterAsyncNotification");
      goto LABEL_73;
    }
    *((_QWORD *)v18 + 421) = v18;
    ReturnLength = -2147467263;
    v6 = ISessionManagerInternal::pSMGlobalInstance;
    if ( ISessionManagerInternal::pSMGlobalInstance )
      goto LABEL_23;
    v47 = (CSessionManager *)operator new(0x758u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v47 )
    {
      v48 = CSessionManager::CSessionManager(v47, (int *)&ReturnLength);
      ISessionManagerInternal::pSMGlobalInstance = v48;
      if ( v48 )
      {
        (*(void (__fastcall **)(struct ISessionManagerInternal *))(*(_QWORD *)v48 + 8LL))(v48);
        v6 = ISessionManagerInternal::pSMGlobalInstance;
LABEL_23:
        ReturnLength = 0;
        (*(void (__fastcall **)(struct ISessionManagerInternal *))(*(_QWORD *)v6 + 8LL))(v6);
        v20 = ReturnLength;
LABEL_24:
        if ( hKey[0] )
        {
          RegCloseKey(hKey[0]);
          hKey[0] = 0;
        }
        if ( RegOpenKeyExW(
               HKEY_LOCAL_MACHINE,
               L"System\\CurrentControlSet\\Control\\Terminal Server",
               0,
               0x20019u,
               hKey) )
        {
          hKey[0] = 0;
        }
        else
        {
          Type = 0;
          cbData = 0;
          if ( !RegQueryValueExW(hKey[0], L"MaxQueuedNotificationEvents", 0, &Type, 0, &cbData)
            && Type == 4
            && CRegistry::Allocate((CRegistry *)&v56, cbData)
            && !RegQueryValueExW(hKey[0], L"MaxQueuedNotificationEvents", 0, &Type, lpData, &cbData)
            && Type == 4 )
          {
            *((_DWORD *)v18 + 441) = *(_DWORD *)lpData;
          }
        }
        goto LABEL_28;
      }
    }
    else
    {
      ISessionManagerInternal::pSMGlobalInstance = 0;
    }
    v6 = 0;
    v20 = -2147024882;
    goto LABEL_24;
  }
  _DbgPrintMessage(8, "Cannot impersonate client: %d", v12);
  CRpcCallTrace::~CRpcCallTrace((CRpcCallTrace *)&v64);
  if ( v55 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
  if ( v7 )
    (*(void (__fastcall **)(struct ISessionManagerInternal *))(*(_QWORD *)v7 + 16LL))(v7);
  return 5;
}

```

## disassembly

```asm
0x180015510  mov     [rsp-8+arg_0], rbx
0x180015515  push    rbp
0x180015516  push    rsi
0x180015517  push    rdi
0x180015518  push    r12
0x18001551a  push    r13
0x18001551c  push    r14
0x18001551e  push    r15
0x180015520  lea     rbp, [rsp-310h]
0x180015528  sub     rsp, 410h
0x18001552f  mov     rax, cs:__security_cookie
0x180015536  xor     rax, rsp
0x180015539  mov     [rbp+340h+var_40], rax
0x180015540  mov     r15, r9
0x180015543  mov     [rbp+340h+var_3B8], r9
0x180015547  mov     [rbp+340h+var_3C0], r8d
0x18001554b  mov     [rsp+440h+var_3F4], edx
0x18001554f  xor     r13d, r13d
0x180015552  mov     edi, r13d
0x180015555  mov     [rsp+440h+var_3F8], 0FFFFFFFFh
0x18001555d  mov     ebx, r13d
0x180015560  mov     [rsp+440h+var_3F0], r13
0x180015565  lea     rax, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x18001556c  mov     [rbp+340h+var_3A0], rax
0x180015570  mov     [rbp+340h+var_384], 1
0x180015577  mov     [rbp+340h+var_380], r13
0x18001557b  lea     r12, aRpcregisterasy; "RpcRegisterAsyncNotification"
0x180015582  cmp     cs:?g_bEnabled@CTraceBase@@0HA, r13d; int CTraceBase::g_bEnabled
0x180015589  jnz     loc_180015ED8
0x18001558f  lea     rcx, [rbp+340h+pguid]; pguid
0x180015593  call    cs:__imp_CoCreateGuid
0x18001559a  nop     dword ptr [rax+rax+00h]
0x18001559f  mov     eax, 1
0x1800155a4  lock xadd cs:?g_NextShortActivityID@CTraceBase@@0KA, eax; ulong CTraceBase::g_NextShortActivityID
0x1800155ac  inc     eax
0x1800155ae  mov     [rbp+340h+var_388], eax
0x1800155b1  mov     [rbp+340h+var_378], r13d
0x1800155b5  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x1800155bc  mov     [rbp+340h+var_3A0], rax
0x1800155c0  mov     [rbp+340h+var_370], r12
0x1800155c4  mov     qword ptr [rbp+340h+Pid], 0FFFFFFFFFFFFFFFFh
0x1800155cc  mov     [rbp+340h+var_360], r13d
0x1800155d0  xor     edx, edx; Val
0x1800155d2  mov     r8d, 208h; Size
0x1800155d8  lea     rcx, [rbp+340h+var_35C]; void *
0x1800155dc  call    memset_0
0x1800155e1  cmp     [rbp+340h+var_360], ebx
0x1800155e4  jnz     loc_180015E20
0x1800155ea  mov     r14d, r13d
0x1800155ed  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x1800155f4  jnz     loc_180015FEA
0x1800155fa  mov     qword ptr [rbp+340h+Pid], 0FFFFFFFFFFFFFFFFh
0x180015602  lea     rdx, [rbp+340h+Pid+4]; Pid
0x180015606  xor     ecx, ecx; Binding
0x180015608  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18001560f  nop     dword ptr [rax+rax+00h]
0x180015614  mov     esi, eax
0x180015616  test    eax, eax
0x180015618  jg      loc_180015D0F
0x18001561e  test    esi, esi
0x180015620  js      short loc_18001563E
0x180015622  lea     rdx, [rbp+340h+Pid]; pSessionId
0x180015626  mov     ecx, [rbp+340h+Pid+4]; dwProcessId
0x180015629  call    cs:__imp_ProcessIdToSessionId
0x180015630  nop     dword ptr [rax+rax+00h]
0x180015635  test    r14d, r14d
0x180015638  jnz     loc_180015FF5
0x18001563e  cmp     [rbp+340h+var_360], ebx
0x180015641  jnz     loc_180015E76
0x180015647  test    r15, r15
0x18001564a  jz      loc_180016095
0x180015650  cmp     [rsp+440h+var_3F4], 0FFFFFFFFh
0x180015655  setz    r13b
0x180015659  mov     dword ptr [rsp+440h+var_400], 80004001h
0x180015661  mov     rax, cs:?pSMGlobalInstance@ISessionManagerInternal@@0PEAV1@EA; ISessionManagerInternal * ISessionManagerInternal::pSMGlobalInstance
0x180015668  test    rax, rax
0x18001566b  jz      loc_1800160BB
0x180015671  mov     dword ptr [rsp+440h+var_400], ebx
0x180015675  mov     rbx, rax
0x180015678  mov     rax, [rax]
0x18001567b  mov     rcx, rbx
0x18001567e  mov     rax, [rax+8]
0x180015682  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015687  xor     ecx, ecx; BindingHandle
0x180015689  call    cs:__imp_RpcImpersonateClient
0x180015690  nop     dword ptr [rax+rax+00h]
0x180015695  test    eax, eax
0x180015697  jnz     loc_180015CBB
0x18001569d  call    ?IsCallerSystem@CUtils@@SAJXZ; CUtils::IsCallerSystem(void)
0x1800156a2  xor     esi, esi
0x1800156a4  test    eax, eax
0x1800156a6  setz    sil
0x1800156aa  call    cs:__imp_RpcRevertToSelf
0x1800156b1  nop     dword ptr [rax+rax+00h]
0x1800156b6  xor     r14d, r14d
0x1800156b9  test    eax, eax
0x1800156bb  cmovz   r14d, esi
0x1800156bf  lea     rdx, [rsp+440h+var_3F8]; Pid
0x1800156c4  xor     ecx, ecx; Binding
0x1800156c6  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x1800156cd  nop     dword ptr [rax+rax+00h]
0x1800156d2  mov     esi, 8
0x1800156d7  test    eax, eax
0x1800156d9  jnz     loc_180016118
0x1800156df  mov     r12d, [rsp+440h+var_3F8]
0x1800156e4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800156eb  mov     ecx, 0D30h; unsigned __int64
0x1800156f0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800156f5  mov     r15, rax
0x1800156f8  test    rax, rax
0x1800156fb  jz      loc_180015DD7
0x180015701  mov     rcx, rax
0x180015704  call    ??0?$CTSPrivateObject@VIPublicNotification@@@@QEAA@PEBD@Z; CTSPrivateObject<IPublicNotification>::CTSPrivateObject<IPublicNotification>(char const *)
0x180015709  lea     rax, ??_7CPublicNotification@@6B@; const CPublicNotification::`vftable'
0x180015710  mov     [r15], rax
0x180015713  xor     eax, eax
0x180015715  mov     [r15+698h], eax
0x18001571c  mov     [r15+6A0h], rax
0x180015723  mov     [r15+6A8h], rax
0x18001572a  mov     [r15+6B0h], rax
0x180015731  mov     dword ptr [r15+6B8h], 0FFFFFFFFh
0x18001573c  mov     [r15+6BCh], rax
0x180015743  mov     [r15+6D8h], eax
0x18001574a  mov     [r15+6DCh], r14d
0x180015751  mov     [r15+6E0h], eax
0x180015758  mov     dword ptr [r15+6E4h], 100h
0x180015763  mov     [r15+6E8h], r12d
0x18001576a  lea     rcx, [r15+6F0h]; this
0x180015771  call    ??0CDefTSNotifySink@@QEAA@XZ; CDefTSNotifySink::CDefTSNotifySink(void)
0x180015776  lea     rax, ??_7CTSNotifySink@CPublicNotification@@6B@; const CPublicNotification::CTSNotifySink::`vftable'
0x18001577d  mov     [r15+6F0h], rax
0x180015784  lea     rax, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x18001578b  mov     [rsp+440h+var_3E8], rax
0x180015790  xor     r12d, r12d
0x180015793  mov     [rsp+440h+lpData], r12
0x180015798  mov     [rsp+440h+var_3D8], r12d
0x18001579d  mov     [rsp+440h+hKey], r12
0x1800157a2  mov     [rsp+440h+var_3C8], 0FFFFFFFFFFFFFFFFh
0x1800157ab  lea     rax, [r15+6C8h]
0x1800157b2  mov     [rax+8], rax
0x1800157b6  mov     [rax], rax
0x1800157b9  lea     rcx, [r15+638h]; this
0x1800157c0  call    ?Initialize@CResource@@QEAAJXZ; CResource::Initialize(void)
0x1800157c5  mov     r14d, eax
0x1800157c8  test    eax, eax
0x1800157ca  js      loc_18001612E
0x1800157d0  mov     [r15+0D28h], r15
0x1800157d7  mov     [rsp+440h+ReturnLength], 80004001h
0x1800157df  mov     rdi, cs:?pSMGlobalInstance@ISessionManagerInternal@@0PEAV1@EA; ISessionManagerInternal * ISessionManagerInternal::pSMGlobalInstance
0x1800157e6  test    rdi, rdi
0x1800157e9  jz      loc_18001614B
0x1800157ef  mov     [rsp+440h+ReturnLength], r12d
0x1800157f4  mov     rax, [rdi]
0x1800157f7  mov     rcx, rdi
0x1800157fa  mov     rax, [rax+8]
0x1800157fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015803  mov     r14d, [rsp+440h+ReturnLength]
0x180015808  mov     rcx, [rsp+440h+hKey]; hKey
0x18001580d  test    rcx, rcx
0x180015810  jnz     loc_1800161AD
0x180015816  lea     rax, [rsp+440h+hKey]
0x18001581b  mov     [rsp+440h+phkResult], rax; phkResult
0x180015820  mov     r9d, 20019h; samDesired
0x180015826  xor     r8d, r8d; ulOptions
0x180015829  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Ter"...
0x180015830  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180015837  call    cs:__imp_RegOpenKeyExW
0x18001583e  nop     dword ptr [rax+rax+00h]
0x180015843  test    eax, eax
0x180015845  jnz     loc_1800161C3
0x18001584b  mov     [rsp+440h+Type], r12d
0x180015850  mov     [rsp+440h+cbData], r12d
0x180015855  lea     rax, [rsp+440h+cbData]
0x18001585a  mov     [rsp+440h+lpcbData], rax; lpcbData
0x18001585f  mov     [rsp+440h+phkResult], r12; lpData
0x180015864  lea     r9, [rsp+440h+Type]; lpType
0x180015869  xor     r8d, r8d; lpReserved
0x18001586c  lea     rdx, aMaxqueuednotif; "MaxQueuedNotificationEvents"
0x180015873  mov     rcx, [rsp+440h+hKey]; hKey
0x180015878  call    cs:__imp_RegQueryValueExW
0x18001587f  nop     dword ptr [rax+rax+00h]
0x180015884  test    eax, eax
0x180015886  jz      loc_1800161CD
0x18001588c  lea     rax, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x180015893  mov     [rsp+440h+var_3E8], rax
0x180015898  mov     rcx, [rsp+440h+hKey]; hKey
0x18001589d  test    rcx, rcx
0x1800158a0  jz      short loc_1800158B3
0x1800158a2  call    cs:__imp_RegCloseKey
0x1800158a9  nop     dword ptr [rax+rax+00h]
0x1800158ae  mov     [rsp+440h+hKey], r12
0x1800158b3  mov     rdx, [rsp+440h+lpData]
0x1800158b8  test    rdx, rdx
0x1800158bb  jnz     loc_180016292
0x1800158c1  mov     [rsp+440h+var_3D8], r12d
0x1800158c6  mov     [rsp+440h+lpData], r12
0x1800158cb  test    rdi, rdi
0x1800158ce  jz      short loc_1800158E0
0x1800158d0  mov     rax, [rdi]
0x1800158d3  mov     rcx, rdi
0x1800158d6  mov     rax, [rax+10h]
0x1800158da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800158df  nop
0x1800158e0  mov     rax, [r15]
0x1800158e3  mov     rcx, r15
0x1800158e6  mov     rax, [rax+8]
0x1800158ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800158ef  test    r14d, r14d
0x1800158f2  js      loc_18001629F
0x1800158f8  mov     rax, [rbx]
0x1800158fb  lea     rdx, [rsp+440h+var_3F0]
0x180015900  mov     rcx, rbx
0x180015903  mov     rax, [rax+0C8h]
0x18001590a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001590f  mov     r14d, eax
0x180015912  test    eax, eax
0x180015914  js      loc_180015DFD
0x18001591a  mov     r12, [rsp+440h+var_3F0]
0x18001591f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180015926  mov     ecx, 658h; unsigned __int64
0x18001592b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180015930  mov     rsi, rax
0x180015933  test    rax, rax
0x180015936  jz      loc_180015DA5
0x18001593c  lea     rax, ??_7?$CTSPrivateObject@UIUnknown@@@@6B@; const CTSPrivateObject<IUnknown>::`vftable'
0x180015943  mov     [rsi], rax
0x180015946  lea     rax, aPublicnotifica_0; "PUBLICNOTIFICATIONTRACKER"
0x18001594d  mov     [rsi+10h], rax
0x180015951  mov     dword ptr [rsi+8], 0
0x180015958  mov     dword ptr [rsi+0Ch], 1
0x18001595f  lea     rdi, [rsi+628h]
0x180015966  mov     [rdi+8], rdi
0x18001596a  mov     [rdi], rdi
0x18001596d  mov     r14, cs:?g_pObjectTracker@@3PEAVCObjectTracker@@EA; CObjectTracker * g_pObjectTracker
0x180015974  test    r14, r14
0x180015977  jz      loc_180015EAE
0x18001597d  lea     rdx, [r14+18h]; struct CResource *
0x180015981  lea     rcx, [rbp+340h+Resource]; this
0x180015985  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x18001598a  lea     rax, [r14+8]
0x18001598e  mov     rcx, [rax+8]
0x180015992  cmp     [rcx], rax
0x180015995  jnz     loc_1800162D1
0x18001599b  mov     [rdi], rax
0x18001599e  mov     [rdi+8], rcx
0x1800159a2  mov     [rcx], rdi
0x1800159a5  mov     [rax+8], rdi
0x1800159a9  xor     edi, edi
0x1800159ab  cmp     [rbp+340h+var_3A8], edi
0x1800159ae  jz      short loc_1800159C9
0x1800159b0  mov     [rbp+340h+var_3A8], edi
0x1800159b3  mov     rcx, [rbp+340h+Resource]; Resource
0x1800159b7  cmp     [rcx+60h], edi
0x1800159ba  jz      short loc_1800159C9
0x1800159bc  call    cs:__imp_RtlReleaseResource
0x1800159c3  nop     dword ptr [rax+rax+00h]
0x1800159c8  nop
0x1800159c9  mov     [rsi+18h], rdi
0x1800159cd  mov     [rsi+20h], edi
0x1800159d0  mov     [rsp+440h+ReturnLength], edi
0x1800159d4  mov     eax, 1
0x1800159d9  lock xadd [rsi+20h], eax
0x1800159de  inc     eax
0x1800159e0  cmp     cs:?g_bCaptureObjectStackTrace@@3HA, 1; int g_bCaptureObjectStackTrace
0x1800159e7  jz      loc_1800162D8
0x1800159ed  lea     rax, ??_7?$CObjectAccessTracker@VIPublicNotification@@$0BDII@@@6B@; const CObjectAccessTracker<IPublicNotification,5000>::`vftable'
0x1800159f4  mov     [rsi], rax
0x1800159f7  mov     [rsi+638h], r15
0x1800159fe  mov     rax, [r15]
0x180015a01  mov     rcx, r15
0x180015a04  mov     rax, [rax+8]
0x180015a08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a0d  mov     qword ptr [rsi+640h], 0FFFFFFFFFFFFFFFFh
0x180015a18  mov     [rsi+648h], r12
0x180015a1f  test    r12, r12
0x180015a22  jz      short loc_180015A34
0x180015a24  mov     rax, [r12]
0x180015a28  mov     rcx, r12
0x180015a2b  mov     rax, [rax+8]
0x180015a2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a34  mov     [rsi+650h], rdi
0x180015a3b  mov     [rsp+440h+Type], edi
0x180015a3f  lea     rdx, [rsp+440h+Type]; ClientLocalFlag
0x180015a44  xor     ecx, ecx; BindingHandle
0x180015a46  call    cs:__imp_I_RpcBindingIsClientLocal
0x180015a4d  nop     dword ptr [rax+rax+00h]
0x180015a52  test    eax, eax
0x180015a54  jg      loc_180015D1D
0x180015a5a  js      loc_180015B36
0x180015a60  cmp     [rsp+440h+Type], 0
0x180015a65  jz      loc_180015B36
0x180015a6b  mov     [rsp+440h+ReturnLength], edi
0x180015a6f  mov     [rsp+440h+cbData], edi
0x180015a73  xor     ecx, ecx; BindingHandle
0x180015a75  call    cs:__imp_RpcImpersonateClient
0x180015a7c  nop     dword ptr [rax+rax+00h]
0x180015a81  mov     r14d, eax
0x180015a84  mov     [rsp+440h+ReturnLength], eax
0x180015a88  test    eax, eax
0x180015a8a  jg      loc_180015D2C
  ... truncated ...
```
