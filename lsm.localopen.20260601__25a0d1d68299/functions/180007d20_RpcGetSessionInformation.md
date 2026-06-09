# RpcGetSessionInformation

- ea: `0x180007d20`
- end: `0x180008960`
- name: `RpcGetSessionInformation`
- size: `3136`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800077a0`
- `0x180007d20`
- `0x180009580`
- `0x1800101b0`
- `0x180010260`
- `0x180029158`
- `0x18004e850`
- `0x18004ec5c`
- `0x18004f354`
- `0x1800637cc`
- `0x18009c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180008660`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180008660`
- `ntdll!NtQueryInformationProcess` at `0x18000863e`
- `ntdll!NtQueryInformationProcess` at `0x18000863e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000839d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008915`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000839d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008915`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180008389`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180008901`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180008389`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180008901`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180007e42`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180007e42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000868f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000868f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800080aa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008138`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800081fa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800080aa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008138`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800081fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000888f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800088a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800088bb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000888f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800088a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800088bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008290`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800082a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008290`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800082a6`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180007dad`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180007dad`
- `RPCRT4!RpcImpersonateClient` at `0x180007eef`
- `RPCRT4!RpcImpersonateClient` at `0x180007eef`
- `RPCRT4!RpcRevertToSelf` at `0x180007f2e`
- `RPCRT4!RpcRevertToSelf` at `0x180007f2e`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180007e21`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180007e21`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180008610`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180008610`

## string_xrefs

- `0x1800083ae`: `GetCommonSessionInformation`
- `0x18000875a`: `GetCommonSessionInformation`
- `0x1800084d5`: `AccessCheckEx failed: 0x%X`
- `0x18000872e`: `CheckAccessToSession`
- `0x18000877a`: `Cannot impersonate client: %d`
- `0x180008461`: `%s with Trace ID 0x%x Completed`
- `0x1800087c2`: `GetCommonSessionInformation failed: 0x%x in %s`
- `0x18000857e`: `TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC`
- `0x180008499`: `RPC Caller: PID %d, SessID %d, Process Name: <%S>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RpcGetSessionInformation(__int64 a1, unsigned int a2, _QWORD *a3)
{
  _QWORD *v3; // r15
  __int64 v5; // rbx
  int v6; // r14d
  unsigned int v7; // esi
  RPC_STATUS v8; // eax
  int v9; // edi
  struct ISessionManagerInternal *v10; // rsi
  int v11; // eax
  int v12; // edi
  int v13; // eax
  __int64 v14; // rdi
  RPC_STATUS v15; // eax
  int v16; // eax
  int v17; // r15d
  RPC_STATUS v18; // eax
  int v19; // eax
  int v20; // edx
  int v21; // eax
  void *v22; // r15
  void *v23; // r14
  void *v24; // r12
  __int64 v25; // rsi
  __int64 v26; // r13
  int v27; // eax
  int v28; // eax
  __int64 v29; // rax
  unsigned __int64 v30; // rdi
  _WORD *v31; // rax
  __int64 v32; // rcx
  __int16 *v33; // rdx
  _WORD *v34; // r8
  __int16 v35; // ax
  _WORD *v36; // rcx
  __int64 v37; // rax
  unsigned __int64 v38; // rdi
  _WORD *v39; // rax
  __int64 v40; // rcx
  __int16 *v41; // rdx
  _WORD *v42; // r8
  __int16 v43; // ax
  _WORD *v44; // rcx
  int v45; // eax
  unsigned __int64 v46; // rsi
  _WORD *v47; // rax
  __int16 *v48; // rcx
  __int16 v49; // dx
  _WORD *v50; // rcx
  HANDLE v52; // rax
  void *v53; // r15
  NTSTATUS InformationProcess; // eax
  wchar_t *v55; // rax
  wchar_t *v56; // rax
  CSessionManager *v57; // rax
  struct ISessionManagerInternal *v58; // rax
  int v59; // r9d
  struct CTraceBase *v61; // [rsp+38h] [rbp-C8h] BYREF
  int v62; // [rsp+40h] [rbp-C0h] BYREF
  int v63; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v64; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID v66; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v67; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v68; // [rsp+68h] [rbp-98h] BYREF
  void **v69; // [rsp+70h] [rbp-90h] BYREF
  GUID pguid; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v71[2]; // [rsp+88h] [rbp-78h] BYREF
  struct CTraceBase *v72; // [rsp+90h] [rbp-70h] BYREF
  int v73; // [rsp+98h] [rbp-68h]
  const char *v74; // [rsp+A0h] [rbp-60h]
  unsigned int Pid[2]; // [rsp+A8h] [rbp-58h] BYREF
  int v76; // [rsp+B0h] [rbp-50h]
  unsigned __int16 v77[262]; // [rsp+B4h] [rbp-4Ch] BYREF
  char ProcessInformation[8]; // [rsp+2C0h] [rbp+1C0h] BYREF
  wchar_t *Str; // [rsp+2C8h] [rbp+1C8h]
  _WORD v80[40]; // [rsp+3D0h] [rbp+2D0h] BYREF

  v3 = a3;
  pv = 0;
  v66 = 0;
  v67 = 0;
  v68 = 0;
  v63 = 0;
  v5 = 0;
  v69 = &CTraceBase::`vftable';
  v6 = 1;
  v71[1] = 1;
  v72 = 0;
  if ( CTraceBase::g_bEnabled )
  {
    if ( (g_DebugTraceComponent & 1) != 0 )
      _DbgPrintMessage(2, "Adding trace %p, %d, %s", &v69, 1, "RpcGetSessionInformation");
    v61 = 0;
    if ( (int)CTraceBase::GetThreadCurrentOperationTrace(&v61) >= 0 && v61 && (g_DebugTraceComponent & 1) != 0 )
      _DbgPrintMessage(
        2,
        "TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC",
        1);
    CTraceBase::ResetThreadCurrentOperationTrace(0, 0);
    if ( (int)CTraceBase::GetThreadCurrentOperationTrace(&v72) >= 0 && v72 )
    {
      (*(void (__fastcall **)(struct CTraceBase *, GUID *))(*(_QWORD *)v72 + 32LL))(v72, &pguid);
      v71[0] = (*(__int64 (__fastcall **)(struct CTraceBase *))(*(_QWORD *)v72 + 24LL))(v72);
      v73 = 1;
      goto LABEL_4;
    }
    CTraceBase::ResetThreadCurrentOperationTrace((struct CTraceBase *)&v69, "RpcGetSessionInformation");
    CTraceBase::GenerateTraceID(&pguid, v71);
  }
  else
  {
    CoCreateGuid(&pguid);
    v71[0] = _InterlockedIncrement((volatile signed __int32 *)&CTraceBase::g_NextShortActivityID);
  }
  v73 = 0;
LABEL_4:
  v69 = &CRpcCallTrace::`vftable';
  v74 = "RpcGetSessionInformation";
  *(_QWORD *)Pid = -1;
  v76 = 0;
  memset_0(v77, 0, 0x208u);
  if ( v76 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "TRACE RPC %s with Trace ID 0x%x", v74, v71[0]);
  v7 = 0;
  if ( (g_DebugTraceComponent & 1) != 0 )
    v7 = 260;
  *(_QWORD *)Pid = -1;
  v8 = I_RpcBindingInqLocalClientPID(0, &Pid[1]);
  v9 = v8;
  if ( v8 > 0 )
    v9 = (unsigned __int16)v8 | 0x80070000;
  if ( v9 >= 0 )
  {
    ProcessIdToSessionId(Pid[1], Pid);
    if ( v7 )
    {
      v52 = OpenProcess(0x400u, 0, Pid[1]);
      v53 = v52;
      if ( v52 )
      {
        InformationProcess = NtQueryInformationProcess(v52, ProcessImageFileName, ProcessInformation, 0x110u, 0);
        v9 = InformationProcess | 0x10000000;
        if ( InformationProcess >= 0 )
        {
          v55 = wcsrchr(Str, 0x5Cu);
          if ( v55 )
            v56 = v55 + 1;
          else
            v56 = Str;
          StringCchCopyW(v77, v7, v56);
        }
        CloseHandle(v53);
      }
      v3 = a3;
    }
  }
  if ( v76 )
  {
    if ( v9 < 0 )
    {
      if ( (g_DebugTraceComponent & 1) != 0 )
        _DbgPrintMessage(2, "RPC Caller: Unknown");
    }
    else if ( (g_DebugTraceComponent & 1) != 0 )
    {
      _DbgPrintMessage(2, "RPC Caller: PID %d, SessID %d, Process Name: <%S>", Pid[1], Pid[0], v77);
    }
  }
  if ( !v3 )
  {
    _DbgPrintMessage(8, "Missing paramter %s in %s", "pSessInfo", "RpcGetSessionInformation");
    v12 = -2147024809;
    goto LABEL_76;
  }
  v61 = 0;
  v64 = 0;
  v62 = -2147467263;
  v10 = ISessionManagerInternal::pSMGlobalInstance;
  if ( ISessionManagerInternal::pSMGlobalInstance )
    goto LABEL_14;
  v10 = 0;
  v57 = (CSessionManager *)operator new(0x758u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v57 )
  {
    v58 = CSessionManager::CSessionManager(v57, &v62);
    ISessionManagerInternal::pSMGlobalInstance = v58;
    if ( v58 )
    {
      (*(void (__fastcall **)(struct ISessionManagerInternal *))(*(_QWORD *)v58 + 8LL))(v58);
      v10 = ISessionManagerInternal::pSMGlobalInstance;
LABEL_14:
      v62 = 0;
      (*(void (__fastcall **)(struct ISessionManagerInternal *))(*(_QWORD *)v10 + 8LL))(v10);
    }
  }
  else
  {
    ISessionManagerInternal::pSMGlobalInstance = 0;
  }
  v11 = (*(__int64 (__fastcall **)(struct ISessionManagerInternal *, struct CTraceBase **))(*(_QWORD *)v10 + 24LL))(
          v10,
          &v61);
  v12 = v11;
  if ( v11 < 0 )
  {
    _DbgPrintMessage(8, "GetSessionList failed: 0x%x in %s", v11, "GetCommonSessionInformation");
  }
  else
  {
    v13 = (*(__int64 (__fastcall **)(struct CTraceBase *, _QWORD, __int64 *))(*(_QWORD *)v61 + 24LL))(v61, a2, &v64);
    v12 = v13;
    if ( v13 < 0 )
    {
      _DbgPrintMessage(4, "FindSessionById failed: 0x%x", v13);
    }
    else
    {
      v14 = v64;
      if ( v64 )
      {
        v15 = RpcImpersonateClient(0);
        if ( v15 )
        {
          _DbgPrintMessage(8, "Cannot impersonate client: %d", v15);
          v12 = -2147024891;
          v59 = -2147024891;
        }
        else
        {
          v16 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64))(*(_QWORD *)v14 + 144LL))(v14, 1, 0, 1);
          v17 = v16;
          v12 = -2147024891;
          if ( v16 < 0 )
          {
            _DbgPrintMessage(8, "AccessCheckEx failed: 0x%X", v16);
            v17 = -2147024891;
          }
          v18 = RpcRevertToSelf();
          if ( v18 )
          {
            _DbgPrintMessage(8, "RpcRevertToSelf failed: %d", v18);
            v59 = -2147024891;
          }
          else
          {
            v12 = v17;
            if ( v17 >= 0 )
            {
              v5 = v64;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 8LL))(v64);
              v3 = a3;
              goto LABEL_24;
            }
            v59 = v17;
          }
          v3 = a3;
        }
      }
      else
      {
        _DbgPrintMessage(8, "Missing paramter %s in %s", "pSession", "CheckAccessToSession");
        v12 = -2147024809;
        v59 = -2147024809;
      }
      _DbgPrintMessage(
        8,
        "%s failed 0x%x: Caller does not have WINSTATION_QUERY right to session %d",
        "GetCommonSessionInformation",
        v59,
        a2);
    }
  }
LABEL_24:
  if ( v64 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
  if ( v61 )
    (*(void (__fastcall **)(struct CTraceBase *))(*(_QWORD *)v61 + 16LL))(v61);
  (*(void (__fastcall **)(struct ISessionManagerInternal *))(*(_QWORD *)v10 + 16LL))(v10);
  if ( v12 < 0 )
  {
    _DbgPrintMessage(4, "GetCommonSessionInformation failed: 0x%x in %s", v12, "RpcGetSessionInformation");
    goto LABEL_76;
  }
  v19 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v5 + 88LL))(v5, &v63);
  v12 = v19;
  if ( v19 < 0 )
  {
    _DbgPrintMessage(8, "Session->getState failed: 0x%x in %s", v19, "RpcGetSessionInformation");
    goto LABEL_76;
  }
  v20 = v63;
  if ( v63 == 1 )
  {
LABEL_31:
    v6 = 9;
  }
  else if ( v63 == 12 )
  {
LABEL_91:
    v6 = 0;
  }
  else
  {
    switch ( v63 )
    {
      case 0:
        goto LABEL_31;
      case 2:
      case 6:
        break;
      case 3:
      case 4:
      case 13:
        v6 = 4;
        break;
      case 5:
        goto LABEL_91;
      case 7:
        v6 = 3;
        break;
      case 8:
      case 9:
        v6 = 2;
        break;
      default:
        v6 = 8;
        break;
    }
  }
  *((_DWORD *)v3 + 6) = v6;
  *((_DWORD *)v3 + 7) = v20 == 12;
  v21 = (*(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD *, _QWORD *))(*(_QWORD *)v5 + 200LL))(
          v5,
          v3 + 4,
          v3 + 5,
          v3 + 6);
  v12 = v21;
  if ( v21 < 0 )
  {
    _DbgPrintMessage(8, "Session->GetTimes failed: 0x%x in %s", v21, "RpcGetSessionInformation");
    goto LABEL_76;
  }
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v25 = -1;
  v26 = 2147483646;
  if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v5 + 96LL))(v5, &v67) < 0 )
  {
LABEL_60:
    if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v5 + 104LL))(v5, &v68) < 0 )
    {
      v12 = 0;
LABEL_75:
      *a3 = v22;
      a3[1] = v23;
      a3[2] = v24;
      goto LABEL_76;
    }
    v45 = (*(__int64 (__fastcall **)(__int64, _WORD *))(*(_QWORD *)v68 + 104LL))(v68, v80);
    v12 = v45;
    if ( v45 < 0 )
    {
      _DbgPrintMessage(8, "Terminal->GetTerminalName failed: 0x%x in %s", v45, "RpcGetSessionInformation");
    }
    else
    {
      do
        ++v25;
      while ( v80[v25] );
      v46 = v25 + 1;
      v47 = LocalAlloc(0x40u, 2 * v46);
      v24 = v47;
      if ( v47 )
      {
        if ( v46 )
        {
          if ( v46 > 0x7FFFFFFF )
          {
            v12 = -2147024809;
            *v47 = 0;
          }
          else
          {
            v48 = v80;
            do
            {
              if ( !v26 )
                break;
              v49 = *v48;
              if ( !*v48 )
                break;
              ++v48;
              *v47++ = v49;
              --v26;
              --v46;
            }
            while ( v46 );
            v50 = v47 - 1;
            if ( v46 )
              v50 = v47;
            *v50 = 0;
            v12 = -2147024774;
            if ( v46 )
              v12 = 0;
          }
        }
        else
        {
          v12 = -2147024809;
        }
        if ( v12 >= 0 )
          goto LABEL_75;
      }
      else
      {
        v12 = -2147024882;
      }
    }
    if ( !v22 )
      goto LABEL_153;
    goto LABEL_152;
  }
  v27 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v67 + 40LL))(v67, &pv);
  v12 = v27;
  if ( v27 < 0 )
  {
    _DbgPrintMessage(8, "UserName->GetUserStr failed: 0x%x in %s", v27, "RpcGetSessionInformation");
    goto LABEL_76;
  }
  v28 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v67 + 48LL))(v67, &v66);
  v12 = v28;
  if ( v28 < 0 )
  {
    _DbgPrintMessage(8, "UserName->GetDomain failed: 0x%x in %s", v28, "RpcGetSessionInformation");
    goto LABEL_76;
  }
  v29 = -1;
  do
    ++v29;
  while ( *((_WORD *)pv + v29) );
  v30 = v29 + 1;
  v31 = LocalAlloc(0x40u, 2 * (v29 + 1));
  v22 = v31;
  if ( !v31 )
  {
    v12 = -2147024882;
    goto LABEL_76;
  }
  if ( v30 )
  {
    if ( v30 > 0x7FFFFFFF )
    {
      *v31 = 0;
    }
    else
    {
      v32 = 2147483646;
      v33 = (__int16 *)pv;
      v34 = v31;
      do
      {
        if ( !v32 )
          break;
        v35 = *v33;
        if ( !*v33 )
          break;
        ++v33;
        *v34++ = v35;
        --v32;
        --v30;
      }
      while ( v30 );
      v36 = v34 - 1;
      if ( v30 )
        v36 = v34;
      *v36 = 0;
    }
  }
  v37 = -1;
  do
    ++v37;
  while ( *((_WORD *)v66 + v37) );
  v38 = v37 + 1;
  v39 = LocalAlloc(0x40u, 2 * (v37 + 1));
  v23 = v39;
  if ( v39 )
  {
    if ( v38 )
    {
      if ( v38 > 0x7FFFFFFF )
      {
        *v39 = 0;
      }
      else
      {
        v40 = 2147483646;
        v41 = (__int16 *)v66;
        v42 = v39;
        do
        {
          if ( !v40 )
            break;
          v43 = *v41;
          if ( !*v41 )
            break;
          ++v41;
          *v42++ = v43;
          --v40;
          --v38;
        }
        while ( v38 );
        v44 = v42 - 1;
        if ( v38 )
          v44 = v42;
        *v44 = 0;
      }
    }
    goto LABEL_60;
  }
  v12 = -2147024882;
LABEL_152:
  LocalFree(v22);
LABEL_153:
  if ( v23 )
    LocalFree(v23);
  if ( v24 )
    LocalFree(v24);
LABEL_76:
  if ( pv )
    CoTaskMemFree(pv);
  if ( v66 )
    CoTaskMemFree(v66);
  v69 = &CRpcCallTrace::`vftable';
  if ( v76 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "%s with Trace ID 0x%x Completed", v74, v71[0]);
  v69 = &CTraceBase::`vftable';
  if ( CTraceBase::g_bEnabled && !v73 && CTraceBase::g_TLSIndex != -1 )
  {
    if ( TlsSetValue(CTraceBase::g_TLSIndex, 0) )
    {
      if ( TlsSetValue(CTraceBase::g_CreatorFunctionTLSIndex, 0) )
        goto LABEL_82;
    }
    else
    {
      GetLastError();
    }
    GetLastError();
  }
LABEL_82:
  v72 = 0;
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  if ( v68 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
  if ( v67 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180007d20  mov     [rsp-8+arg_0], rbx
0x180007d25  push    rbp
0x180007d26  push    rsi
0x180007d27  push    rdi
0x180007d28  push    r12
0x180007d2a  push    r13
0x180007d2c  push    r14
0x180007d2e  push    r15
0x180007d30  lea     rbp, [rsp-330h]
0x180007d38  sub     rsp, 430h
0x180007d3f  mov     rax, cs:__security_cookie
0x180007d46  xor     rax, rsp
0x180007d49  mov     [rbp+360h+var_40], rax
0x180007d50  mov     r15, r8
0x180007d53  mov     [rsp+460h+var_430], r8
0x180007d58  mov     r12d, edx
0x180007d5b  xor     r13d, r13d
0x180007d5e  mov     [rsp+460h+pv], r13
0x180007d63  mov     [rsp+460h+var_408], r13
0x180007d68  mov     [rsp+460h+var_400], r13
0x180007d6d  mov     [rsp+460h+var_3F8], r13
0x180007d72  mov     [rsp+460h+var_41C], r13d
0x180007d77  mov     ebx, r13d
0x180007d7a  lea     rax, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x180007d81  mov     [rsp+460h+var_3F0], rax
0x180007d86  mov     r14d, 1
0x180007d8c  mov     [rbp+360h+var_3D4], r14d
0x180007d90  mov     [rbp+360h+var_3D0], r13
0x180007d94  lea     rdi, aRpcgetsessioni; "RpcGetSessionInformation"
0x180007d9b  cmp     cs:?g_bEnabled@CTraceBase@@0HA, r13d; int CTraceBase::g_bEnabled
0x180007da2  jnz     loc_180008531
0x180007da8  lea     rcx, [rsp+460h+pguid]; pguid
0x180007dad  call    cs:__imp_CoCreateGuid
0x180007db4  nop     dword ptr [rax+rax+00h]
0x180007db9  mov     eax, r14d
0x180007dbc  lock xadd cs:?g_NextShortActivityID@CTraceBase@@0KA, eax; ulong CTraceBase::g_NextShortActivityID
0x180007dc4  inc     eax
0x180007dc6  mov     [rbp+360h+var_3D8], eax
0x180007dc9  mov     [rbp+360h+var_3C8], r13d
0x180007dcd  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x180007dd4  mov     [rsp+460h+var_3F0], rax
0x180007dd9  mov     [rbp+360h+var_3C0], rdi
0x180007ddd  mov     qword ptr [rbp+360h+Pid], 0FFFFFFFFFFFFFFFFh
0x180007de5  mov     [rbp+360h+var_3B0], r13d
0x180007de9  xor     edx, edx; Val
0x180007deb  mov     r8d, 208h; Size
0x180007df1  lea     rcx, [rbp+360h+var_3AC]; void *
0x180007df5  call    memset_0
0x180007dfa  cmp     [rbp+360h+var_3B0], ebx
0x180007dfd  jnz     loc_180008421
0x180007e03  mov     esi, r13d
0x180007e06  test    byte ptr cs:?g_DebugTraceComponent@@3KA, r14b; ulong g_DebugTraceComponent
0x180007e0d  jnz     loc_1800085FB
0x180007e13  mov     qword ptr [rbp+360h+Pid], 0FFFFFFFFFFFFFFFFh
0x180007e1b  lea     rdx, [rbp+360h+Pid+4]; Pid
0x180007e1f  xor     ecx, ecx; Binding
0x180007e21  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x180007e28  nop     dword ptr [rax+rax+00h]
0x180007e2d  mov     edi, eax
0x180007e2f  test    eax, eax
0x180007e31  jg      loc_1800083CE
0x180007e37  test    edi, edi
0x180007e39  js      short loc_180007E56
0x180007e3b  lea     rdx, [rbp+360h+Pid]; pSessionId
0x180007e3f  mov     ecx, [rbp+360h+Pid+4]; dwProcessId
0x180007e42  call    cs:__imp_ProcessIdToSessionId
0x180007e49  nop     dword ptr [rax+rax+00h]
0x180007e4e  test    esi, esi
0x180007e50  jnz     loc_180008605
0x180007e56  cmp     [rbp+360h+var_3B0], ebx
0x180007e59  jnz     loc_180008477
0x180007e5f  test    r15, r15
0x180007e62  jz      loc_1800086A5
0x180007e68  mov     [rsp+460h+var_428], r13
0x180007e6d  mov     [rsp+460h+var_418], r13
0x180007e72  mov     [rsp+460h+var_420], 80004001h
0x180007e7a  mov     rsi, cs:?pSMGlobalInstance@ISessionManagerInternal@@0PEAV1@EA; ISessionManagerInternal * ISessionManagerInternal::pSMGlobalInstance
0x180007e81  test    rsi, rsi
0x180007e84  jz      loc_1800086CE
0x180007e8a  mov     [rsp+460h+var_420], r13d
0x180007e8f  mov     rax, [rsi]
0x180007e92  mov     rcx, rsi
0x180007e95  mov     rax, [rax+8]
0x180007e99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e9e  mov     rax, [rsi]
0x180007ea1  lea     rdx, [rsp+460h+var_428]
0x180007ea6  mov     rcx, rsi
0x180007ea9  mov     rax, [rax+18h]
0x180007ead  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007eb2  mov     edi, eax
0x180007eb4  test    eax, eax
0x180007eb6  js      loc_1800083AE
0x180007ebc  mov     rcx, [rsp+460h+var_428]
0x180007ec1  mov     rax, [rcx]
0x180007ec4  lea     r8, [rsp+460h+var_418]
0x180007ec9  mov     edx, r12d
0x180007ecc  mov     rax, [rax+18h]
0x180007ed0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ed5  mov     edi, eax
0x180007ed7  test    eax, eax
0x180007ed9  js      loc_180008408
0x180007edf  mov     rdi, [rsp+460h+var_418]
0x180007ee4  test    rdi, rdi
0x180007ee7  jz      loc_18000872E
0x180007eed  xor     ecx, ecx; BindingHandle
0x180007eef  call    cs:__imp_RpcImpersonateClient
0x180007ef6  nop     dword ptr [rax+rax+00h]
0x180007efb  test    eax, eax
0x180007efd  jnz     loc_180008777
0x180007f03  mov     rax, [rdi]
0x180007f06  mov     r9d, r14d
0x180007f09  xor     r8d, r8d
0x180007f0c  mov     edx, r14d
0x180007f0f  mov     rcx, rdi
0x180007f12  mov     rax, [rax+90h]
0x180007f19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f1e  mov     r15d, eax
0x180007f21  mov     edi, 80070005h
0x180007f26  test    eax, eax
0x180007f28  js      loc_1800084D2
0x180007f2e  call    cs:__imp_RpcRevertToSelf
0x180007f35  nop     dword ptr [rax+rax+00h]
0x180007f3a  test    eax, eax
0x180007f3c  jnz     loc_180008795
0x180007f42  mov     edi, r15d
0x180007f45  test    r15d, r15d
0x180007f48  js      loc_1800087AE
0x180007f4e  mov     rbx, [rsp+460h+var_418]
0x180007f53  mov     rax, [rbx]
0x180007f56  mov     rcx, rbx
0x180007f59  mov     rax, [rax+8]
0x180007f5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f62  mov     r15, [rsp+460h+var_430]
0x180007f67  mov     rcx, [rsp+460h+var_418]
0x180007f6c  test    rcx, rcx
0x180007f6f  jz      short loc_180007F7E
0x180007f71  mov     rax, [rcx]
0x180007f74  mov     rax, [rax+10h]
0x180007f78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f7d  nop
0x180007f7e  mov     rcx, [rsp+460h+var_428]
0x180007f83  test    rcx, rcx
0x180007f86  jz      short loc_180007F95
0x180007f88  mov     rax, [rcx]
0x180007f8b  mov     rax, [rax+10h]
0x180007f8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f94  nop
0x180007f95  mov     rax, [rsi]
0x180007f98  mov     rcx, rsi
0x180007f9b  mov     rax, [rax+10h]
0x180007f9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fa4  nop
0x180007fa5  test    edi, edi
0x180007fa7  js      loc_1800087B8
0x180007fad  mov     rax, [rbx]
0x180007fb0  lea     rdx, [rsp+460h+var_41C]
0x180007fb5  mov     rcx, rbx
0x180007fb8  mov     rax, [rax+58h]
0x180007fbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fc1  mov     edi, eax
0x180007fc3  test    eax, eax
0x180007fc5  js      loc_1800084EE
0x180007fcb  movsxd  rdx, [rsp+460h+var_41C]
0x180007fd0  cmp     edx, 1
0x180007fd3  jnz     loc_180008361
0x180007fd9  mov     r14d, 9; jumptable 00000001800083F7 case 0
0x180007fdf  mov     [r15+18h], r14d; jumptable 00000001800083F7 cases 2,6
0x180007fe3  mov     eax, r13d
0x180007fe6  cmp     edx, 0Ch
0x180007fe9  setz    al
0x180007fec  mov     [r15+1Ch], eax
0x180007ff0  mov     rax, [rbx]
0x180007ff3  lea     r9, [r15+30h]
0x180007ff7  lea     r8, [r15+28h]
0x180007ffb  lea     rdx, [r15+20h]
0x180007fff  mov     rcx, rbx
0x180008002  mov     rax, [rax+0C8h]
0x180008009  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000800e  mov     edi, eax
0x180008010  test    eax, eax
0x180008012  js      loc_1800087F9
0x180008018  mov     r15, r13
0x18000801b  mov     r14, r13
0x18000801e  mov     r12, r13
0x180008021  mov     rax, [rbx]
0x180008024  lea     rdx, [rsp+460h+var_400]
0x180008029  mov     rcx, rbx
0x18000802c  mov     rax, [rax+60h]
0x180008030  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008035  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18000803c  mov     r13d, 7FFFFFFEh
0x180008042  test    eax, eax
0x180008044  js      loc_18000819F
0x18000804a  mov     rcx, [rsp+460h+var_400]
0x18000804f  mov     rax, [rcx]
0x180008052  lea     rdx, [rsp+460h+pv]
0x180008057  mov     rax, [rax+28h]
0x18000805b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008060  mov     edi, eax
0x180008062  test    eax, eax
0x180008064  js      loc_180008819
0x18000806a  mov     rcx, [rsp+460h+var_400]
0x18000806f  mov     rax, [rcx]
0x180008072  lea     rdx, [rsp+460h+var_408]
0x180008077  mov     rax, [rax+30h]
0x18000807b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008080  mov     edi, eax
0x180008082  test    eax, eax
0x180008084  js      loc_18000850E
0x18000808a  mov     rcx, [rsp+460h+pv]
0x18000808f  mov     rax, rsi
0x180008092  lea     rax, [rax+1]
0x180008096  cmp     [rcx+rax*2], r12w
0x18000809b  jnz     short loc_180008092
0x18000809d  lea     rdi, [rax+1]
0x1800080a1  lea     rdx, [rdi+rdi]; uBytes
0x1800080a5  mov     ecx, 40h ; '@'; uFlags
0x1800080aa  call    cs:__imp_LocalAlloc
0x1800080b1  nop     dword ptr [rax+rax+00h]
0x1800080b6  mov     r15, rax
0x1800080b9  test    rax, rax
0x1800080bc  jz      loc_18000883C
0x1800080c2  test    rdi, rdi
0x1800080c5  jz      short loc_180008111
0x1800080c7  cmp     rdi, 7FFFFFFFh
0x1800080ce  ja      loc_180008849
0x1800080d4  mov     rcx, r13
0x1800080d7  mov     rdx, [rsp+460h+pv]
0x1800080dc  mov     r8, rax
0x1800080df  test    rcx, rcx
0x1800080e2  jz      short loc_180008101
0x1800080e4  movzx   eax, word ptr [rdx]
0x1800080e7  test    ax, ax
0x1800080ea  jz      short loc_180008101
0x1800080ec  add     rdx, 2
0x1800080f0  mov     [r8], ax
0x1800080f4  add     r8, 2
0x1800080f8  dec     rcx
0x1800080fb  sub     rdi, 1
0x1800080ff  jnz     short loc_1800080DF
0x180008101  lea     rcx, [r8-2]
0x180008105  test    rdi, rdi
0x180008108  cmovnz  rcx, r8
0x18000810c  xor     eax, eax
0x18000810e  mov     [rcx], ax
0x180008111  mov     rcx, [rsp+460h+var_408]
0x180008116  mov     rax, rsi
0x180008119  nop     dword ptr [rax+00000000h]
0x180008120  lea     rax, [rax+1]
0x180008124  cmp     [rcx+rax*2], r12w
0x180008129  jnz     short loc_180008120
0x18000812b  lea     rdi, [rax+1]
0x18000812f  lea     rdx, [rdi+rdi]; uBytes
0x180008133  mov     ecx, 40h ; '@'; uFlags
0x180008138  call    cs:__imp_LocalAlloc
0x18000813f  nop     dword ptr [rax+rax+00h]
0x180008144  mov     r14, rax
0x180008147  test    rax, rax
0x18000814a  jz      loc_180008854
0x180008150  test    rdi, rdi
0x180008153  jz      short loc_18000819F
0x180008155  cmp     rdi, 7FFFFFFFh
0x18000815c  ja      loc_18000885E
0x180008162  mov     rcx, r13
0x180008165  mov     rdx, [rsp+460h+var_408]
0x18000816a  mov     r8, rax
0x18000816d  test    rcx, rcx
0x180008170  jz      short loc_18000818F
0x180008172  movzx   eax, word ptr [rdx]
0x180008175  test    ax, ax
0x180008178  jz      short loc_18000818F
0x18000817a  add     rdx, 2
0x18000817e  mov     [r8], ax
0x180008182  add     r8, 2
0x180008186  dec     rcx
0x180008189  sub     rdi, 1
0x18000818d  jnz     short loc_18000816D
0x18000818f  lea     rcx, [r8-2]
0x180008193  test    rdi, rdi
0x180008196  cmovnz  rcx, r8
0x18000819a  xor     eax, eax
0x18000819c  mov     [rcx], ax
0x18000819f  mov     rax, [rbx]
0x1800081a2  lea     rdx, [rsp+460h+var_3F8]
0x1800081a7  mov     rcx, rbx
0x1800081aa  mov     rax, [rax+68h]
0x1800081ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800081b3  test    eax, eax
0x1800081b5  js      loc_180008356
0x1800081bb  mov     rcx, [rsp+460h+var_3F8]
0x1800081c0  mov     rax, [rcx]
0x1800081c3  lea     rdx, [rbp+360h+var_90]
0x1800081ca  mov     rax, [rax+68h]
0x1800081ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800081d3  mov     edi, eax
0x1800081d5  test    eax, eax
0x1800081d7  js      loc_180008869
0x1800081dd  lea     rax, [rbp+360h+var_90]
0x1800081e4  inc     rsi
0x1800081e7  cmp     [rax+rsi*2], r12w
  ... truncated ...
```
