# RpcGetSessionInformation

- ea: `0x180007a00`
- end: `0x1800085b8`
- name: `RpcGetSessionInformation`
- size: `3000`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800074c0`
- `0x180007a00`
- `0x18000b190`
- `0x18000c700`
- `0x18001aa50`
- `0x1800271d0`
- `0x18004b460`
- `0x18004b86c`
- `0x18004bf44`
- `0x18005fcc4`
- `0x180097010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800082e0`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800082e0`
- `ntdll!NtQueryInformationProcess` at `0x1800082c4`
- `ntdll!NtQueryInformationProcess` at `0x1800082c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008033`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008571`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008033`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008571`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180008025`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180008563`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180008025`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180008563`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180007b16`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180007b16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008309`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008309`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007d6c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007ded`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007ea9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007d6c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007ded`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007ea9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008503`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008511`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008523`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008503`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008511`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008523`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007f39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007f49`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007f39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007f49`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180007a8d`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180007a8d`
- `RPCRT4!RpcImpersonateClient` at `0x180007bbd`
- `RPCRT4!RpcImpersonateClient` at `0x180007bbd`
- `RPCRT4!RpcRevertToSelf` at `0x180007bf6`
- `RPCRT4!RpcRevertToSelf` at `0x180007bf6`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180007afb`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180007afb`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000829c`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000829c`

## string_xrefs

- `0x18000803e`: `GetCommonSessionInformation`
- `0x1800083ce`: `GetCommonSessionInformation`
- `0x180008161`: `AccessCheckEx failed: 0x%X`
- `0x1800083ee`: `Cannot impersonate client: %d`
- `0x1800083a2`: `CheckAccessToSession`
- `0x1800080ed`: `%s with Trace ID 0x%x Completed`
- `0x180008436`: `GetCommonSessionInformation failed: 0x%x in %s`
- `0x18000820a`: `TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC`
- `0x180008125`: `RPC Caller: PID %d, SessID %d, Process Name: <%S>`

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
0x180007a00  mov     [rsp-8+arg_0], rbx
0x180007a05  push    rbp
0x180007a06  push    rsi
0x180007a07  push    rdi
0x180007a08  push    r12
0x180007a0a  push    r13
0x180007a0c  push    r14
0x180007a0e  push    r15
0x180007a10  lea     rbp, [rsp-330h]
0x180007a18  sub     rsp, 430h
0x180007a1f  mov     rax, cs:__security_cookie
0x180007a26  xor     rax, rsp
0x180007a29  mov     [rbp+360h+var_40], rax
0x180007a30  mov     r15, r8
0x180007a33  mov     [rsp+460h+var_430], r8
0x180007a38  mov     r12d, edx
0x180007a3b  xor     r13d, r13d
0x180007a3e  mov     [rsp+460h+pv], r13
0x180007a43  mov     [rsp+460h+var_408], r13
0x180007a48  mov     [rsp+460h+var_400], r13
0x180007a4d  mov     [rsp+460h+var_3F8], r13
0x180007a52  mov     [rsp+460h+var_41C], r13d
0x180007a57  mov     ebx, r13d
0x180007a5a  lea     rax, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x180007a61  mov     [rsp+460h+var_3F0], rax
0x180007a66  mov     r14d, 1
0x180007a6c  mov     [rbp+360h+var_3D4], r14d
0x180007a70  mov     [rbp+360h+var_3D0], r13
0x180007a74  lea     rdi, aRpcgetsessioni; "RpcGetSessionInformation"
0x180007a7b  cmp     cs:?g_bEnabled@CTraceBase@@0HA, r13d; int CTraceBase::g_bEnabled
0x180007a82  jnz     loc_1800081BD
0x180007a88  lea     rcx, [rsp+460h+pguid]; pguid
0x180007a8d  call    cs:__imp_CoCreateGuid
0x180007a93  mov     eax, r14d
0x180007a96  lock xadd cs:?g_NextShortActivityID@CTraceBase@@0KA, eax; ulong CTraceBase::g_NextShortActivityID
0x180007a9e  inc     eax
0x180007aa0  mov     [rbp+360h+var_3D8], eax
0x180007aa3  mov     [rbp+360h+var_3C8], r13d
0x180007aa7  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x180007aae  mov     [rsp+460h+var_3F0], rax
0x180007ab3  mov     [rbp+360h+var_3C0], rdi
0x180007ab7  mov     qword ptr [rbp+360h+Pid], 0FFFFFFFFFFFFFFFFh
0x180007abf  mov     [rbp+360h+var_3B0], r13d
0x180007ac3  xor     edx, edx; Val
0x180007ac5  mov     r8d, 208h; Size
0x180007acb  lea     rcx, [rbp+360h+var_3AC]; void *
0x180007acf  call    memset_0
0x180007ad4  cmp     [rbp+360h+var_3B0], ebx
0x180007ad7  jnz     loc_1800080AD
0x180007add  mov     esi, r13d
0x180007ae0  test    byte ptr cs:?g_DebugTraceComponent@@3KA, r14b; ulong g_DebugTraceComponent
0x180007ae7  jnz     loc_180008287
0x180007aed  mov     qword ptr [rbp+360h+Pid], 0FFFFFFFFFFFFFFFFh
0x180007af5  lea     rdx, [rbp+360h+Pid+4]; Pid
0x180007af9  xor     ecx, ecx; Binding
0x180007afb  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x180007b01  mov     edi, eax
0x180007b03  test    eax, eax
0x180007b05  jg      loc_18000805E
0x180007b0b  test    edi, edi
0x180007b0d  js      short loc_180007B24
0x180007b0f  lea     rdx, [rbp+360h+Pid]; pSessionId
0x180007b13  mov     ecx, [rbp+360h+Pid+4]; dwProcessId
0x180007b16  call    cs:__imp_ProcessIdToSessionId
0x180007b1c  test    esi, esi
0x180007b1e  jnz     loc_180008291
0x180007b24  cmp     [rbp+360h+var_3B0], ebx
0x180007b27  jnz     loc_180008103
0x180007b2d  test    r15, r15
0x180007b30  jz      loc_180008319
0x180007b36  mov     [rsp+460h+var_428], r13
0x180007b3b  mov     [rsp+460h+var_418], r13
0x180007b40  mov     [rsp+460h+var_420], 80004001h
0x180007b48  mov     rsi, cs:?pSMGlobalInstance@ISessionManagerInternal@@0PEAV1@EA; ISessionManagerInternal * ISessionManagerInternal::pSMGlobalInstance
0x180007b4f  test    rsi, rsi
0x180007b52  jz      loc_180008342
0x180007b58  mov     [rsp+460h+var_420], r13d
0x180007b5d  mov     rax, [rsi]
0x180007b60  mov     rcx, rsi
0x180007b63  mov     rax, [rax+8]
0x180007b67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b6c  mov     rax, [rsi]
0x180007b6f  lea     rdx, [rsp+460h+var_428]
0x180007b74  mov     rcx, rsi
0x180007b77  mov     rax, [rax+18h]
0x180007b7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b80  mov     edi, eax
0x180007b82  test    eax, eax
0x180007b84  js      loc_18000803E
0x180007b8a  mov     rcx, [rsp+460h+var_428]
0x180007b8f  mov     rax, [rcx]
0x180007b92  lea     r8, [rsp+460h+var_418]
0x180007b97  mov     edx, r12d
0x180007b9a  mov     rax, [rax+18h]
0x180007b9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ba3  mov     edi, eax
0x180007ba5  test    eax, eax
0x180007ba7  js      loc_180008094
0x180007bad  mov     rdi, [rsp+460h+var_418]
0x180007bb2  test    rdi, rdi
0x180007bb5  jz      loc_1800083A2
0x180007bbb  xor     ecx, ecx; BindingHandle
0x180007bbd  call    cs:__imp_RpcImpersonateClient
0x180007bc3  test    eax, eax
0x180007bc5  jnz     loc_1800083EB
0x180007bcb  mov     rax, [rdi]
0x180007bce  mov     r9d, r14d
0x180007bd1  xor     r8d, r8d
0x180007bd4  mov     edx, r14d
0x180007bd7  mov     rcx, rdi
0x180007bda  mov     rax, [rax+90h]
0x180007be1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007be6  mov     r15d, eax
0x180007be9  mov     edi, 80070005h
0x180007bee  test    eax, eax
0x180007bf0  js      loc_18000815E
0x180007bf6  call    cs:__imp_RpcRevertToSelf
0x180007bfc  test    eax, eax
0x180007bfe  jnz     loc_180008409
0x180007c04  mov     edi, r15d
0x180007c07  test    r15d, r15d
0x180007c0a  js      loc_180008422
0x180007c10  mov     rbx, [rsp+460h+var_418]
0x180007c15  mov     rax, [rbx]
0x180007c18  mov     rcx, rbx
0x180007c1b  mov     rax, [rax+8]
0x180007c1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c24  mov     r15, [rsp+460h+var_430]
0x180007c29  mov     rcx, [rsp+460h+var_418]
0x180007c2e  test    rcx, rcx
0x180007c31  jz      short loc_180007C40
0x180007c33  mov     rax, [rcx]
0x180007c36  mov     rax, [rax+10h]
0x180007c3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c3f  nop
0x180007c40  mov     rcx, [rsp+460h+var_428]
0x180007c45  test    rcx, rcx
0x180007c48  jz      short loc_180007C57
0x180007c4a  mov     rax, [rcx]
0x180007c4d  mov     rax, [rax+10h]
0x180007c51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c56  nop
0x180007c57  mov     rax, [rsi]
0x180007c5a  mov     rcx, rsi
0x180007c5d  mov     rax, [rax+10h]
0x180007c61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c66  nop
0x180007c67  test    edi, edi
0x180007c69  js      loc_18000842C
0x180007c6f  mov     rax, [rbx]
0x180007c72  lea     rdx, [rsp+460h+var_41C]
0x180007c77  mov     rcx, rbx
0x180007c7a  mov     rax, [rax+58h]
0x180007c7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c83  mov     edi, eax
0x180007c85  test    eax, eax
0x180007c87  js      loc_18000817A
0x180007c8d  movsxd  rdx, [rsp+460h+var_41C]
0x180007c92  cmp     edx, 1
0x180007c95  jnz     loc_180007FFD
0x180007c9b  mov     r14d, 9; jumptable 0000000180008087 case 0
0x180007ca1  mov     [r15+18h], r14d; jumptable 0000000180008087 cases 2,6
0x180007ca5  mov     eax, r13d
0x180007ca8  cmp     edx, 0Ch
0x180007cab  setz    al
0x180007cae  mov     [r15+1Ch], eax
0x180007cb2  mov     rax, [rbx]
0x180007cb5  lea     r9, [r15+30h]
0x180007cb9  lea     r8, [r15+28h]
0x180007cbd  lea     rdx, [r15+20h]
0x180007cc1  mov     rcx, rbx
0x180007cc4  mov     rax, [rax+0C8h]
0x180007ccb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cd0  mov     edi, eax
0x180007cd2  test    eax, eax
0x180007cd4  js      loc_18000846D
0x180007cda  mov     r15, r13
0x180007cdd  mov     r14, r13
0x180007ce0  mov     r12, r13
0x180007ce3  mov     rax, [rbx]
0x180007ce6  lea     rdx, [rsp+460h+var_400]
0x180007ceb  mov     rcx, rbx
0x180007cee  mov     rax, [rax+60h]
0x180007cf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cf7  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180007cfe  mov     r13d, 7FFFFFFEh
0x180007d04  test    eax, eax
0x180007d06  js      loc_180007E4E
0x180007d0c  mov     rcx, [rsp+460h+var_400]
0x180007d11  mov     rax, [rcx]
0x180007d14  lea     rdx, [rsp+460h+pv]
0x180007d19  mov     rax, [rax+28h]
0x180007d1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d22  mov     edi, eax
0x180007d24  test    eax, eax
0x180007d26  js      loc_18000848D
0x180007d2c  mov     rcx, [rsp+460h+var_400]
0x180007d31  mov     rax, [rcx]
0x180007d34  lea     rdx, [rsp+460h+var_408]
0x180007d39  mov     rax, [rax+30h]
0x180007d3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d42  mov     edi, eax
0x180007d44  test    eax, eax
0x180007d46  js      loc_18000819A
0x180007d4c  mov     rcx, [rsp+460h+pv]
0x180007d51  mov     rax, rsi
0x180007d54  lea     rax, [rax+1]
0x180007d58  cmp     [rcx+rax*2], r12w
0x180007d5d  jnz     short loc_180007D54
0x180007d5f  lea     rdi, [rax+1]
0x180007d63  lea     rdx, [rdi+rdi]; uBytes
0x180007d67  mov     ecx, 40h ; '@'; uFlags
0x180007d6c  call    cs:__imp_LocalAlloc
0x180007d72  mov     r15, rax
0x180007d75  test    rax, rax
0x180007d78  jz      loc_1800084B0
0x180007d7e  test    rdi, rdi
0x180007d81  jz      short loc_180007DCD
0x180007d83  cmp     rdi, 7FFFFFFFh
0x180007d8a  ja      loc_1800084BD
0x180007d90  mov     rcx, r13
0x180007d93  mov     rdx, [rsp+460h+pv]
0x180007d98  mov     r8, rax
0x180007d9b  test    rcx, rcx
0x180007d9e  jz      short loc_180007DBD
0x180007da0  movzx   eax, word ptr [rdx]
0x180007da3  test    ax, ax
0x180007da6  jz      short loc_180007DBD
0x180007da8  add     rdx, 2
0x180007dac  mov     [r8], ax
0x180007db0  add     r8, 2
0x180007db4  dec     rcx
0x180007db7  sub     rdi, 1
0x180007dbb  jnz     short loc_180007D9B
0x180007dbd  lea     rcx, [r8-2]
0x180007dc1  test    rdi, rdi
0x180007dc4  cmovnz  rcx, r8
0x180007dc8  xor     eax, eax
0x180007dca  mov     [rcx], ax
0x180007dcd  mov     rcx, [rsp+460h+var_408]
0x180007dd2  mov     rax, rsi
0x180007dd5  lea     rax, [rax+1]
0x180007dd9  cmp     [rcx+rax*2], r12w
0x180007dde  jnz     short loc_180007DD5
0x180007de0  lea     rdi, [rax+1]
0x180007de4  lea     rdx, [rdi+rdi]; uBytes
0x180007de8  mov     ecx, 40h ; '@'; uFlags
0x180007ded  call    cs:__imp_LocalAlloc
0x180007df3  mov     r14, rax
0x180007df6  test    rax, rax
0x180007df9  jz      loc_1800084C8
0x180007dff  test    rdi, rdi
0x180007e02  jz      short loc_180007E4E
0x180007e04  cmp     rdi, 7FFFFFFFh
0x180007e0b  ja      loc_1800084D2
0x180007e11  mov     rcx, r13
0x180007e14  mov     rdx, [rsp+460h+var_408]
0x180007e19  mov     r8, rax
0x180007e1c  test    rcx, rcx
0x180007e1f  jz      short loc_180007E3E
0x180007e21  movzx   eax, word ptr [rdx]
0x180007e24  test    ax, ax
0x180007e27  jz      short loc_180007E3E
0x180007e29  add     rdx, 2
0x180007e2d  mov     [r8], ax
0x180007e31  add     r8, 2
0x180007e35  dec     rcx
0x180007e38  sub     rdi, 1
0x180007e3c  jnz     short loc_180007E1C
0x180007e3e  lea     rcx, [r8-2]
0x180007e42  test    rdi, rdi
0x180007e45  cmovnz  rcx, r8
0x180007e49  xor     eax, eax
0x180007e4b  mov     [rcx], ax
0x180007e4e  mov     rax, [rbx]
0x180007e51  lea     rdx, [rsp+460h+var_3F8]
0x180007e56  mov     rcx, rbx
0x180007e59  mov     rax, [rax+68h]
0x180007e5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e62  test    eax, eax
0x180007e64  js      loc_180007FF2
0x180007e6a  mov     rcx, [rsp+460h+var_3F8]
0x180007e6f  mov     rax, [rcx]
0x180007e72  lea     rdx, [rbp+360h+var_90]
0x180007e79  mov     rax, [rax+68h]
0x180007e7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e82  mov     edi, eax
0x180007e84  test    eax, eax
0x180007e86  js      loc_1800084DD
0x180007e8c  lea     rax, [rbp+360h+var_90]
0x180007e93  inc     rsi
0x180007e96  cmp     [rax+rsi*2], r12w
0x180007e9b  jnz     short loc_180007E93
0x180007e9d  inc     rsi
0x180007ea0  lea     rdx, [rsi+rsi]; uBytes
0x180007ea4  mov     ecx, 40h ; '@'; uFlags
0x180007ea9  call    cs:__imp_LocalAlloc
0x180007eaf  mov     r12, rax
0x180007eb2  test    rax, rax
0x180007eb5  jz      loc_18000852E
  ... truncated ...
```
