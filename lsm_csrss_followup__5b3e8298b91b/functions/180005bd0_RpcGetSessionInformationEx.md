# RpcGetSessionInformationEx

- ea: `0x180005bd0`
- end: `0x1800067e0`
- name: `RpcGetSessionInformationEx`
- size: `3088`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180005480`

## callees

- `0x180005bd0`
- `0x1800074c0`
- `0x18000b190`
- `0x18000c700`
- `0x18001aa50`
- `0x1800271d0`
- `0x18004b460`
- `0x18004b86c`
- `0x18004bf44`
- `0x18005fcc4`
- `0x18009404c`
- `0x180097010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180006579`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180006579`
- `ntdll!NtQueryInformationProcess` at `0x18000655d`
- `ntdll!NtQueryInformationProcess` at `0x18000655d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006209`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000679a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006209`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000679a`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800061fb`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000678c`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800061fb`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000678c`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180005d16`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180005d16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800065a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800065a5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000631b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000631b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000629b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000629b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006118`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006128`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800063de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006118`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006128`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800063de`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180005c71`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180005c71`
- `RPCRT4!RpcImpersonateClient` at `0x180005dc0`
- `RPCRT4!RpcImpersonateClient` at `0x180005dc0`
- `RPCRT4!RpcRevertToSelf` at `0x180005dfc`
- `RPCRT4!RpcRevertToSelf` at `0x180005dfc`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180005cf5`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180005cf5`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180006535`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180006535`

## string_xrefs

- `0x180006214`: `GetCommonSessionInformation`
- `0x180006668`: `GetCommonSessionInformation`
- `0x1800063ec`: `AccessCheckEx failed: 0x%X`
- `0x180006414`: `Failed to allocate memory for ProtocolData failed: 0x%x in %s`
- `0x180006688`: `Cannot impersonate client: %d`
- `0x18000663c`: `CheckAccessToSession`
- `0x180006364`: `%s with Trace ID 0x%x Completed`
- `0x1800066ce`: `GetCommonSessionInformation failed: 0x%x in %s`
- `0x180006778`: `StringCchCopy failed: 0x%x in %s`
- `0x180006472`: `TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC`
- `0x1800063a5`: `RPC Caller: PID %d, SessID %d, Process Name: <%S>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RpcGetSessionInformationEx(__int64 a1, unsigned int a2, unsigned int a3, __int64 a4)
{
  __int64 v7; // rbx
  unsigned int v8; // esi
  RPC_STATUS v9; // eax
  int v10; // edi
  struct ISessionManagerInternal *v11; // rsi
  int v12; // eax
  unsigned int v13; // edi
  int v14; // eax
  __int64 v15; // rdi
  RPC_STATUS v16; // eax
  int v17; // eax
  int v18; // r14d
  RPC_STATUS v19; // eax
  int v20; // eax
  int v21; // eax
  __int64 v22; // rsi
  int v23; // eax
  __int64 v24; // rcx
  __int16 *v25; // rdx
  __int64 v26; // r9
  _WORD *v27; // r8
  __int16 v28; // ax
  _WORD *v29; // rcx
  int v30; // eax
  __int64 v31; // rcx
  __int16 *v32; // rdx
  __int64 v33; // r9
  _WORD *v34; // r8
  __int16 v35; // ax
  _WORD *v36; // rcx
  int v37; // eax
  __int16 *v38; // rcx
  __int64 v39; // rdx
  _WORD *v40; // r8
  __int16 v41; // ax
  _WORD *v42; // rcx
  HLOCAL v44; // rax
  HANDLE v45; // rax
  void *v46; // r14
  NTSTATUS InformationProcess; // eax
  wchar_t *v48; // rax
  wchar_t *v49; // rax
  CSessionManager *v50; // rax
  struct ISessionManagerInternal *v51; // rax
  int v52; // r9d
  SIZE_T uBytes; // [rsp+30h] [rbp-D0h] BYREF
  struct CTraceBase *v54; // [rsp+38h] [rbp-C8h] BYREF
  int v55; // [rsp+40h] [rbp-C0h] BYREF
  int v56; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v57; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v58; // [rsp+50h] [rbp-B0h] BYREF
  void *Src; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID v61; // [rsp+68h] [rbp-98h] BYREF
  __int64 v62; // [rsp+70h] [rbp-90h] BYREF
  _OWORD v63[4]; // [rsp+80h] [rbp-80h] BYREF
  _OWORD v64[2]; // [rsp+C0h] [rbp-40h] BYREF
  _OWORD v65[3]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v66; // [rsp+110h] [rbp+10h] BYREF
  __int128 v67; // [rsp+120h] [rbp+20h] BYREF
  __int128 v68; // [rsp+130h] [rbp+30h]
  HLOCAL hMem; // [rsp+140h] [rbp+40h]
  void **v70; // [rsp+150h] [rbp+50h] BYREF
  GUID pguid; // [rsp+158h] [rbp+58h] BYREF
  unsigned int v72[2]; // [rsp+168h] [rbp+68h] BYREF
  struct CTraceBase *v73; // [rsp+170h] [rbp+70h] BYREF
  int v74; // [rsp+178h] [rbp+78h]
  const char *v75; // [rsp+180h] [rbp+80h]
  unsigned int Pid[2]; // [rsp+188h] [rbp+88h] BYREF
  int v77; // [rsp+190h] [rbp+90h]
  unsigned __int16 v78[262]; // [rsp+194h] [rbp+94h] BYREF
  _BYTE ProcessInformation[8]; // [rsp+3A0h] [rbp+2A0h] BYREF
  wchar_t *Str; // [rsp+3A8h] [rbp+2A8h]
  _BYTE v81[80]; // [rsp+4B0h] [rbp+3B0h] BYREF

  memset_0(v63, 0, 0xC8u);
  v7 = 0;
  v56 = 0;
  v58 = 0;
  v61 = 0;
  pv = 0;
  v62 = 0;
  Src = 0;
  LODWORD(uBytes) = 0;
  v70 = &CTraceBase::`vftable';
  v72[1] = 1;
  v73 = 0;
  if ( CTraceBase::g_bEnabled )
  {
    if ( (g_DebugTraceComponent & 1) != 0 )
      _DbgPrintMessage(2, "Adding trace %p, %d, %s", &v70, 1, "RpcGetSessionInformationEx");
    v54 = 0;
    if ( (int)CTraceBase::GetThreadCurrentOperationTrace(&v54) >= 0 && v54 && (g_DebugTraceComponent & 1) != 0 )
      _DbgPrintMessage(
        2,
        "TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC",
        1);
    CTraceBase::ResetThreadCurrentOperationTrace(0, 0);
    if ( (int)CTraceBase::GetThreadCurrentOperationTrace(&v73) >= 0 && v73 )
    {
      (*(void (__fastcall **)(struct CTraceBase *, GUID *))(*(_QWORD *)v73 + 32LL))(v73, &pguid);
      v72[0] = (*(__int64 (__fastcall **)(struct CTraceBase *))(*(_QWORD *)v73 + 24LL))(v73);
      v74 = 1;
      goto LABEL_4;
    }
    CTraceBase::ResetThreadCurrentOperationTrace((struct CTraceBase *)&v70, "RpcGetSessionInformationEx");
    CTraceBase::GenerateTraceID(&pguid, v72);
  }
  else
  {
    CoCreateGuid(&pguid);
    v72[0] = _InterlockedIncrement((volatile signed __int32 *)&CTraceBase::g_NextShortActivityID);
  }
  v74 = 0;
LABEL_4:
  v70 = &CRpcCallTrace::`vftable';
  v75 = "RpcGetSessionInformationEx";
  *(_QWORD *)Pid = -1;
  v77 = 0;
  memset_0(v78, 0, 0x208u);
  if ( v77 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "TRACE RPC %s with Trace ID 0x%x", v75, v72[0]);
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
      v45 = OpenProcess(0x400u, 0, Pid[1]);
      v46 = v45;
      if ( v45 )
      {
        InformationProcess = NtQueryInformationProcess(v45, ProcessImageFileName, ProcessInformation, 0x110u, 0);
        v10 = InformationProcess | 0x10000000;
        if ( InformationProcess >= 0 )
        {
          v48 = wcsrchr(Str, 0x5Cu);
          if ( v48 )
            v49 = v48 + 1;
          else
            v49 = Str;
          StringCchCopyW(v78, v8, v49);
        }
        CloseHandle(v46);
      }
    }
  }
  if ( v77 )
  {
    if ( v10 < 0 )
    {
      if ( (g_DebugTraceComponent & 1) != 0 )
        _DbgPrintMessage(2, "RPC Caller: Unknown");
    }
    else if ( (g_DebugTraceComponent & 1) != 0 )
    {
      _DbgPrintMessage(2, "RPC Caller: PID %d, SessID %d, Process Name: <%S>", Pid[1], Pid[0], v78);
    }
  }
  if ( !a4 )
  {
    _DbgPrintMessage(8, "Missing paramter %s in %s", "LSMSesssionInfoExPtr", "RpcGetSessionInformationEx");
    v13 = -2147024809;
    goto LABEL_92;
  }
  v54 = 0;
  v57 = 0;
  v55 = -2147467263;
  v11 = ISessionManagerInternal::pSMGlobalInstance;
  if ( ISessionManagerInternal::pSMGlobalInstance )
    goto LABEL_14;
  v11 = 0;
  v50 = (CSessionManager *)operator new(0x758u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v50 )
  {
    v51 = CSessionManager::CSessionManager(v50, &v55);
    ISessionManagerInternal::pSMGlobalInstance = v51;
    if ( v51 )
    {
      (*(void (__fastcall **)(struct ISessionManagerInternal *))(*(_QWORD *)v51 + 8LL))(v51);
      v11 = ISessionManagerInternal::pSMGlobalInstance;
LABEL_14:
      v55 = 0;
      (*(void (__fastcall **)(struct ISessionManagerInternal *))(*(_QWORD *)v11 + 8LL))(v11);
    }
  }
  else
  {
    ISessionManagerInternal::pSMGlobalInstance = 0;
  }
  v12 = (*(__int64 (__fastcall **)(struct ISessionManagerInternal *, struct CTraceBase **))(*(_QWORD *)v11 + 24LL))(
          v11,
          &v54);
  v13 = v12;
  if ( v12 < 0 )
  {
    _DbgPrintMessage(8, "GetSessionList failed: 0x%x in %s", v12, "GetCommonSessionInformation");
  }
  else
  {
    v14 = (*(__int64 (__fastcall **)(struct CTraceBase *, _QWORD, __int64 *))(*(_QWORD *)v54 + 24LL))(v54, a2, &v57);
    v13 = v14;
    if ( v14 < 0 )
    {
      _DbgPrintMessage(4, "FindSessionById failed: 0x%x", v14);
    }
    else
    {
      v15 = v57;
      if ( v57 )
      {
        v16 = RpcImpersonateClient(0);
        if ( v16 )
        {
          _DbgPrintMessage(8, "Cannot impersonate client: %d", v16);
          v13 = -2147024891;
          v52 = -2147024891;
        }
        else
        {
          v17 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v15 + 144LL))(v15, 1, 0);
          v18 = v17;
          v13 = -2147024891;
          if ( v17 < 0 )
          {
            _DbgPrintMessage(8, "AccessCheckEx failed: 0x%X", v17);
            v18 = -2147024891;
          }
          v19 = RpcRevertToSelf();
          if ( v19 )
          {
            _DbgPrintMessage(8, "RpcRevertToSelf failed: %d", v19);
            v52 = -2147024891;
          }
          else
          {
            v13 = v18;
            if ( v18 >= 0 )
            {
              v7 = v57;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 8LL))(v57);
              goto LABEL_24;
            }
            v52 = v18;
          }
        }
      }
      else
      {
        _DbgPrintMessage(8, "Missing paramter %s in %s", "pSession", "CheckAccessToSession");
        v13 = -2147024809;
        v52 = -2147024809;
      }
      _DbgPrintMessage(
        8,
        "%s failed 0x%x: Caller does not have WINSTATION_QUERY right to session %d",
        "GetCommonSessionInformation",
        v52,
        a2);
    }
  }
LABEL_24:
  if ( v57 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
  if ( v54 )
    (*(void (__fastcall **)(struct CTraceBase *))(*(_QWORD *)v54 + 16LL))(v54);
  (*(void (__fastcall **)(struct ISessionManagerInternal *))(*(_QWORD *)v11 + 16LL))(v11);
  if ( (v13 & 0x80000000) != 0 )
  {
    _DbgPrintMessage(8, "GetCommonSessionInformation failed: 0x%x in %s", v13, "RpcGetSessionInformationEx");
    goto LABEL_92;
  }
  if ( a3 > 1 )
    a3 = 1;
  v20 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v7 + 88LL))(v7, &v56);
  v13 = v20;
  if ( v20 < 0 )
  {
    _DbgPrintMessage(8, "Session->getState failed: 0x%x in %s", (unsigned int)v20, "RpcGetSessionInformationEx");
    goto LABEL_92;
  }
  if ( v56 == 1 )
  {
LABEL_33:
    LODWORD(v63[0]) = 9;
LABEL_34:
    DWORD1(v63[0]) = -1;
  }
  else if ( v56 == 12 )
  {
    LODWORD(v63[0]) = 0;
  }
  else
  {
    switch ( v56 )
    {
      case 0:
        goto LABEL_33;
      case 2:
        LODWORD(v63[0]) = 1;
        break;
      case 3:
        LODWORD(v63[0]) = 4;
        goto LABEL_34;
      case 4:
        LODWORD(v63[0]) = 4;
        goto LABEL_121;
      case 5:
        LODWORD(v63[0]) = 0;
        goto LABEL_121;
      case 6:
        LODWORD(v63[0]) = 1;
        goto LABEL_121;
      case 7:
        LODWORD(v63[0]) = 3;
        goto LABEL_121;
      case 8:
      case 9:
        LODWORD(v63[0]) = 2;
        goto LABEL_34;
      case 10:
      case 11:
        LODWORD(v63[0]) = 8;
        goto LABEL_34;
      case 13:
        LODWORD(v63[0]) = 4;
        break;
      default:
        LODWORD(v63[0]) = 8;
        if ( v56 == 13 || v56 == 2 )
          break;
        if ( (unsigned int)(v56 - 4) > 3 )
          goto LABEL_34;
LABEL_121:
        DWORD1(v63[0]) |= 1u;
        break;
    }
  }
  v21 = (*(__int64 (__fastcall **)(__int64, char *, __int128 *, char *))(*(_QWORD *)v7 + 200LL))(
          v7,
          (char *)&v66 + 8,
          &v67,
          (char *)&v67 + 8);
  v13 = v21;
  if ( v21 < 0 )
  {
    _DbgPrintMessage(8, "Session->GetTimes failed: 0x%x in %s", (unsigned int)v21, "RpcGetSessionInformationEx");
    goto LABEL_92;
  }
  v22 = 2147483646;
  if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v7 + 96LL))(v7, &v58) >= 0 )
  {
    v23 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v58 + 40LL))(v58, &v61);
    v13 = v23;
    if ( v23 < 0 )
    {
      _DbgPrintMessage(8, "UserName->GetUserStr failed: 0x%x in %s", (unsigned int)v23, "RpcGetSessionInformationEx");
      goto LABEL_92;
    }
    v24 = 2147483646;
    v25 = (__int16 *)v61;
    v26 = 21;
    v27 = (_WORD *)v65 + 7;
    do
    {
      if ( !v24 )
        break;
      v28 = *v25;
      if ( !*v25 )
        break;
      ++v25;
      *v27++ = v28;
      --v24;
      --v26;
    }
    while ( v26 );
    v29 = v27 - 1;
    if ( v26 )
      v29 = v27;
    *v29 = 0;
    v30 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v58 + 48LL))(v58, &pv);
    v13 = v30;
    if ( v30 < 0 )
    {
      _DbgPrintMessage(8, "UserName->GetDomain failed: 0x%x in %s", (unsigned int)v30, "RpcGetSessionInformationEx");
      goto LABEL_92;
    }
    v31 = 2147483646;
    v32 = (__int16 *)pv;
    v33 = 18;
    v34 = (_WORD *)v64 + 5;
    do
    {
      if ( !v31 )
        break;
      v35 = *v32;
      if ( !*v32 )
        break;
      ++v32;
      *v34++ = v35;
      --v31;
      --v33;
    }
    while ( v33 );
    v36 = v34 - 1;
    if ( v33 )
      v36 = v34;
    *v36 = 0;
  }
  if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v7 + 104LL))(v7, &v62) < 0 )
  {
    v13 = 0;
  }
  else
  {
    v37 = (*(__int64 (__fastcall **)(__int64, _BYTE *, void **, SIZE_T *))(*(_QWORD *)v62 + 184LL))(
            v62,
            v81,
            &Src,
            &uBytes);
    v13 = v37;
    if ( v37 < 0 )
    {
      _DbgPrintMessage(
        8,
        "Terminal->GetTerminalInformation failed: 0x%x in %s",
        (unsigned int)v37,
        "RpcGetSessionInformationEx");
      goto LABEL_92;
    }
    if ( (_DWORD)uBytes )
    {
      v44 = LocalAlloc(0x40u, (unsigned int)uBytes);
      hMem = v44;
      if ( !v44 )
      {
        v13 = -2147024882;
        _DbgPrintMessage(
          8,
          "Failed to allocate memory for ProtocolData failed: 0x%x in %s",
          2147942414LL,
          "RpcGetSessionInformationEx");
        goto LABEL_92;
      }
      memcpy_0(v44, Src, (unsigned int)uBytes);
      DWORD2(v68) = uBytes;
    }
    v38 = (__int16 *)v81;
    v39 = 33;
    v40 = (_WORD *)v63 + 4;
    do
    {
      if ( !v22 )
        break;
      v41 = *v38;
      if ( !*v38 )
        break;
      ++v38;
      *v40++ = v41;
      --v22;
      --v39;
    }
    while ( v39 );
    v13 = -2147024774;
    if ( v39 )
      v13 = 0;
    v42 = v40 - 1;
    if ( v39 )
      v42 = v40;
    *v42 = 0;
    if ( !v39 )
    {
      _DbgPrintMessage(8, "StringCchCopy failed: 0x%x in %s", v13, "RpcGetSessionInformationEx");
      goto LABEL_92;
    }
  }
  *(_DWORD *)a4 = a3;
  if ( a3 == 1 )
  {
    *(_OWORD *)(a4 + 8) = v63[0];
    *(_OWORD *)(a4 + 24) = v63[1];
    *(_OWORD *)(a4 + 40) = v63[2];
    *(_OWORD *)(a4 + 56) = v63[3];
    *(_OWORD *)(a4 + 72) = v64[0];
    *(_OWORD *)(a4 + 88) = v64[1];
    *(_OWORD *)(a4 + 104) = v65[0];
    *(_OWORD *)(a4 + 120) = v65[1];
    *(_OWORD *)(a4 + 136) = v65[2];
    *(_OWORD *)(a4 + 152) = v66;
    *(_OWORD *)(a4 + 168) = v67;
    *(_OWORD *)(a4 + 184) = v68;
    *(_QWORD *)(a4 + 200) = hMem;
    hMem = 0;
    goto LABEL_66;
  }
LABEL_92:
  if ( hMem )
    LocalFree(hMem);
LABEL_66:
  if ( Src )
    CoTaskMemFree(Src);
  if ( pv )
    CoTaskMemFree(pv);
  if ( v61 )
    CoTaskMemFree(v61);
  v70 = &CRpcCallTrace::`vftable';
  if ( v77 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "%s with Trace ID 0x%x Completed", v75, v72[0]);
  v70 = &CTraceBase::`vftable';
  if ( CTraceBase::g_bEnabled && !v74 && CTraceBase::g_TLSIndex != -1 )
  {
    if ( TlsSetValue(CTraceBase::g_TLSIndex, 0) )
    {
      if ( TlsSetValue(CTraceBase::g_CreatorFunctionTLSIndex, 0) )
        goto LABEL_74;
    }
    else
    {
      GetLastError();
    }
    GetLastError();
  }
LABEL_74:
  v73 = 0;
  if ( v62 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
  if ( v58 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  return v13;
}

```

## disassembly

```asm
0x180005bd0  mov     [rsp-8+arg_0], rbx
0x180005bd5  push    rbp
0x180005bd6  push    rsi
0x180005bd7  push    rdi
0x180005bd8  push    r12
0x180005bda  push    r13
0x180005bdc  push    r14
0x180005bde  push    r15
0x180005be0  lea     rbp, [rsp-410h]
0x180005be8  sub     rsp, 510h
0x180005bef  mov     rax, cs:__security_cookie
0x180005bf6  xor     rax, rsp
0x180005bf9  mov     [rbp+440h+var_40], rax
0x180005c00  mov     r15, r9
0x180005c03  mov     r13d, r8d
0x180005c06  mov     r12d, edx
0x180005c09  xor     edx, edx; Val
0x180005c0b  mov     r8d, 0C8h; Size
0x180005c11  lea     rcx, [rbp+440h+var_4C0]; void *
0x180005c15  call    memset_0
0x180005c1a  xor     r14d, r14d
0x180005c1d  mov     ebx, r14d
0x180005c20  mov     [rsp+540h+var_4FC], r14d
0x180005c25  mov     [rsp+540h+var_4F0], r14
0x180005c2a  mov     [rsp+540h+var_4D8], r14
0x180005c2f  mov     [rsp+540h+pv], r14
0x180005c34  mov     [rsp+540h+var_4D0], r14
0x180005c39  mov     [rsp+540h+Src], r14
0x180005c3e  mov     dword ptr [rsp+540h+uBytes], r14d
0x180005c43  lea     rax, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x180005c4a  mov     [rbp+440h+var_3F0], rax
0x180005c4e  mov     [rbp+440h+var_3D4], 1
0x180005c55  mov     [rbp+440h+var_3D0], r14
0x180005c59  lea     rdi, aRpcgetsessioni_1; "RpcGetSessionInformationEx"
0x180005c60  cmp     cs:?g_bEnabled@CTraceBase@@0HA, r14d; int CTraceBase::g_bEnabled
0x180005c67  jnz     loc_180006420
0x180005c6d  lea     rcx, [rbp+440h+pguid]; pguid
0x180005c71  call    cs:__imp_CoCreateGuid
0x180005c77  mov     eax, 1
0x180005c7c  lock xadd cs:?g_NextShortActivityID@CTraceBase@@0KA, eax; ulong CTraceBase::g_NextShortActivityID
0x180005c84  inc     eax
0x180005c86  mov     [rbp+440h+var_3D8], eax
0x180005c89  mov     [rbp+440h+var_3C8], r14d
0x180005c8d  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x180005c94  mov     [rbp+440h+var_3F0], rax
0x180005c98  mov     [rbp+440h+var_3C0], rdi
0x180005c9f  mov     qword ptr [rbp+440h+Pid], 0FFFFFFFFFFFFFFFFh
0x180005caa  mov     [rbp+440h+var_3B0], r14d
0x180005cb1  xor     edx, edx; Val
0x180005cb3  mov     r8d, 208h; Size
0x180005cb9  lea     rcx, [rbp+440h+var_3AC]; void *
0x180005cc0  call    memset_0
0x180005cc5  cmp     [rbp+440h+var_3B0], ebx
0x180005ccb  jnz     loc_1800062E5
0x180005cd1  mov     esi, r14d
0x180005cd4  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x180005cdb  jnz     loc_18000651D
0x180005ce1  mov     qword ptr [rbp+440h+Pid], 0FFFFFFFFFFFFFFFFh
0x180005cec  lea     rdx, [rbp+440h+Pid+4]; Pid
0x180005cf3  xor     ecx, ecx; Binding
0x180005cf5  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x180005cfb  mov     edi, eax
0x180005cfd  test    eax, eax
0x180005cff  jg      loc_180006234
0x180005d05  test    edi, edi
0x180005d07  js      short loc_180005D24
0x180005d09  lea     rdx, [rbp+440h+Pid]; pSessionId
0x180005d10  mov     ecx, [rbp+440h+Pid+4]; dwProcessId
0x180005d16  call    cs:__imp_ProcessIdToSessionId
0x180005d1c  test    esi, esi
0x180005d1e  jnz     loc_180006527
0x180005d24  cmp     [rbp+440h+var_3B0], ebx
0x180005d2a  jnz     loc_18000637A
0x180005d30  test    r15, r15
0x180005d33  jz      loc_1800065B3
0x180005d39  mov     [rsp+540h+var_508], r14
0x180005d3e  mov     [rsp+540h+var_4F8], r14
0x180005d43  mov     [rsp+540h+var_500], 80004001h
0x180005d4b  mov     rsi, cs:?pSMGlobalInstance@ISessionManagerInternal@@0PEAV1@EA; ISessionManagerInternal * ISessionManagerInternal::pSMGlobalInstance
0x180005d52  test    rsi, rsi
0x180005d55  jz      loc_1800065DC
0x180005d5b  mov     [rsp+540h+var_500], r14d
0x180005d60  mov     rax, [rsi]
0x180005d63  mov     rcx, rsi
0x180005d66  mov     rax, [rax+8]
0x180005d6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d6f  mov     rax, [rsi]
0x180005d72  lea     rdx, [rsp+540h+var_508]
0x180005d77  mov     rcx, rsi
0x180005d7a  mov     rax, [rax+18h]
0x180005d7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d83  mov     edi, eax
0x180005d85  test    eax, eax
0x180005d87  js      loc_180006214
0x180005d8d  mov     rcx, [rsp+540h+var_508]
0x180005d92  mov     rax, [rcx]
0x180005d95  lea     r8, [rsp+540h+var_4F8]
0x180005d9a  mov     edx, r12d
0x180005d9d  mov     rax, [rax+18h]
0x180005da1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005da6  mov     edi, eax
0x180005da8  test    eax, eax
0x180005daa  js      loc_1800062CC
0x180005db0  mov     rdi, [rsp+540h+var_4F8]
0x180005db5  test    rdi, rdi
0x180005db8  jz      loc_18000663C
0x180005dbe  xor     ecx, ecx; BindingHandle
0x180005dc0  call    cs:__imp_RpcImpersonateClient
0x180005dc6  test    eax, eax
0x180005dc8  jnz     loc_180006685
0x180005dce  mov     rax, [rdi]
0x180005dd1  mov     r9d, 1
0x180005dd7  xor     r8d, r8d
0x180005dda  mov     edx, r9d
0x180005ddd  mov     rcx, rdi
0x180005de0  mov     rax, [rax+90h]
0x180005de7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005dec  mov     r14d, eax
0x180005def  mov     edi, 80070005h
0x180005df4  test    eax, eax
0x180005df6  js      loc_1800063E9
0x180005dfc  call    cs:__imp_RpcRevertToSelf
0x180005e02  test    eax, eax
0x180005e04  jnz     loc_1800066A3
0x180005e0a  mov     edi, r14d
0x180005e0d  test    r14d, r14d
0x180005e10  js      loc_1800066BC
0x180005e16  mov     rbx, [rsp+540h+var_4F8]
0x180005e1b  mov     rax, [rbx]
0x180005e1e  mov     rcx, rbx
0x180005e21  mov     rax, [rax+8]
0x180005e25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e2a  xor     r14d, r14d
0x180005e2d  mov     rcx, [rsp+540h+var_4F8]
0x180005e32  test    rcx, rcx
0x180005e35  jz      short loc_180005E44
0x180005e37  mov     rax, [rcx]
0x180005e3a  mov     rax, [rax+10h]
0x180005e3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e43  nop
0x180005e44  mov     rcx, [rsp+540h+var_508]
0x180005e49  test    rcx, rcx
0x180005e4c  jz      short loc_180005E5B
0x180005e4e  mov     rax, [rcx]
0x180005e51  mov     rax, [rax+10h]
0x180005e55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e5a  nop
0x180005e5b  mov     rax, [rsi]
0x180005e5e  mov     rcx, rsi
0x180005e61  mov     rax, [rax+10h]
0x180005e65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e6a  nop
0x180005e6b  test    edi, edi
0x180005e6d  js      loc_1800066C4
0x180005e73  cmp     r13d, 1
0x180005e77  ja      loc_1800066DA
0x180005e7d  mov     rax, [rbx]
0x180005e80  lea     rdx, [rsp+540h+var_4FC]
0x180005e85  mov     rcx, rbx
0x180005e88  mov     rax, [rax+58h]
0x180005e8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e91  mov     edi, eax
0x180005e93  test    eax, eax
0x180005e95  js      loc_1800066E5
0x180005e9b  movsxd  rdx, [rsp+540h+var_4FC]
0x180005ea0  cmp     edx, 1
0x180005ea3  jnz     loc_1800061D2
0x180005ea9  mov     dword ptr [rbp+440h+var_4C0], 9; jumptable 000000018000625D case 0
0x180005eb0  mov     dword ptr [rbp+440h+var_4C0+4], 0FFFFFFFFh
0x180005eb7  mov     rax, [rbx]
0x180005eba  lea     r9, [rbp+440h+var_420+8]
0x180005ebe  lea     r8, [rbp+440h+var_420]
0x180005ec2  lea     rdx, [rbp+440h+var_428]
0x180005ec6  mov     rcx, rbx
0x180005ec9  mov     rax, [rax+0C8h]
0x180005ed0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ed5  mov     edi, eax
0x180005ed7  test    eax, eax
0x180005ed9  js      loc_180006273
0x180005edf  mov     rax, [rbx]
0x180005ee2  lea     rdx, [rsp+540h+var_4F0]
0x180005ee7  mov     rcx, rbx
0x180005eea  mov     rax, [rax+60h]
0x180005eee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ef3  mov     esi, 7FFFFFFEh
0x180005ef8  test    eax, eax
0x180005efa  js      loc_180005FC5
0x180005f00  mov     rcx, [rsp+540h+var_4F0]
0x180005f05  mov     rax, [rcx]
0x180005f08  lea     rdx, [rsp+540h+var_4D8]
0x180005f0d  mov     rax, [rax+28h]
0x180005f11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f16  mov     edi, eax
0x180005f18  test    eax, eax
0x180005f1a  js      loc_1800062B9
0x180005f20  mov     ecx, esi
0x180005f22  mov     rdx, [rsp+540h+var_4D8]
0x180005f27  mov     r9d, 15h
0x180005f2d  lea     r8, [rbp+440h+var_452]
0x180005f31  test    rcx, rcx
0x180005f34  jz      short loc_180005F53
0x180005f36  movzx   eax, word ptr [rdx]
0x180005f39  test    ax, ax
0x180005f3c  jz      short loc_180005F53
0x180005f3e  add     rdx, 2
0x180005f42  mov     [r8], ax
0x180005f46  add     r8, 2
0x180005f4a  dec     rcx
0x180005f4d  sub     r9, 1
0x180005f51  jnz     short loc_180005F31
0x180005f53  lea     rcx, [r8-2]
0x180005f57  test    r9, r9
0x180005f5a  cmovnz  rcx, r8
0x180005f5e  mov     [rcx], r14w
0x180005f62  mov     rcx, [rsp+540h+var_4F0]
0x180005f67  mov     rax, [rcx]
0x180005f6a  lea     rdx, [rsp+540h+pv]
0x180005f6f  mov     rax, [rax+30h]
0x180005f73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f78  mov     edi, eax
0x180005f7a  test    eax, eax
0x180005f7c  js      loc_180006758
0x180005f82  mov     rcx, rsi
0x180005f85  mov     rdx, [rsp+540h+pv]
0x180005f8a  mov     r9d, 12h
0x180005f90  lea     r8, [rbp+440h+var_476]
0x180005f94  test    rcx, rcx
0x180005f97  jz      short loc_180005FB6
0x180005f99  movzx   eax, word ptr [rdx]
0x180005f9c  test    ax, ax
0x180005f9f  jz      short loc_180005FB6
0x180005fa1  add     rdx, 2
0x180005fa5  mov     [r8], ax
0x180005fa9  add     r8, 2
0x180005fad  dec     rcx
0x180005fb0  sub     r9, 1
0x180005fb4  jnz     short loc_180005F94
0x180005fb6  lea     rcx, [r8-2]
0x180005fba  test    r9, r9
0x180005fbd  cmovnz  rcx, r8
0x180005fc1  mov     [rcx], r14w
0x180005fc5  mov     rax, [rbx]
0x180005fc8  lea     rdx, [rsp+540h+var_4D0]
0x180005fcd  mov     rcx, rbx
0x180005fd0  mov     rax, [rax+68h]
0x180005fd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fd9  test    eax, eax
0x180005fdb  js      loc_18000626B
0x180005fe1  mov     rcx, [rsp+540h+var_4D0]
0x180005fe6  mov     rax, [rcx]
0x180005fe9  lea     r9, [rsp+540h+uBytes]
0x180005fee  lea     r8, [rsp+540h+Src]
0x180005ff3  lea     rdx, [rbp+440h+var_90]
0x180005ffa  mov     rax, [rax+0B8h]
0x180006001  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006006  mov     edi, eax
0x180006008  test    eax, eax
0x18000600a  js      loc_1800062A6
0x180006010  mov     eax, dword ptr [rsp+540h+uBytes]
0x180006014  test    eax, eax
0x180006016  jnz     loc_180006313
0x18000601c  lea     rcx, [rbp+440h+var_90]
0x180006023  mov     edx, 21h ; '!'
0x180006028  lea     r8, [rbp+440h+var_4C0+8]
0x18000602c  test    rsi, rsi
0x18000602f  jz      short loc_18000604E
0x180006031  movzx   eax, word ptr [rcx]
0x180006034  test    ax, ax
0x180006037  jz      short loc_18000604E
0x180006039  add     rcx, 2
0x18000603d  mov     [r8], ax
0x180006041  add     r8, 2
0x180006045  dec     rsi
0x180006048  sub     rdx, 1
0x18000604c  jnz     short loc_18000602C
0x18000604e  mov     edi, 8007007Ah
0x180006053  test    rdx, rdx
0x180006056  cmovnz  edi, r14d
0x18000605a  lea     rcx, [r8-2]
0x18000605e  cmovnz  rcx, r8
0x180006062  mov     [rcx], r14w
0x180006066  jz      loc_18000676E
0x18000606c  mov     [r15], r13d
0x18000606f  cmp     r13d, 1
0x180006073  jnz     loc_18000628E
0x180006079  movaps  xmm0, [rbp+440h+var_4C0]
0x18000607d  movups  xmmword ptr [r15+8], xmm0
0x180006082  movaps  xmm1, [rbp+440h+var_4B0]
0x180006086  movups  xmmword ptr [r15+18h], xmm1
0x18000608b  movaps  xmm0, [rbp+440h+var_4A0]
0x18000608f  movups  xmmword ptr [r15+28h], xmm0
0x180006094  movaps  xmm1, [rbp+440h+var_490]
0x180006098  movups  xmmword ptr [r15+38h], xmm1
0x18000609d  movaps  xmm0, xmmword ptr [rbp-40h]
0x1800060a1  movups  xmmword ptr [r15+48h], xmm0
0x1800060a6  movaps  xmm1, [rbp+440h+var_470]
0x1800060aa  movups  xmmword ptr [r15+58h], xmm1
0x1800060af  movaps  xmm0, xmmword ptr [rbp-20h]
0x1800060b3  movups  xmmword ptr [r15+68h], xmm0
0x1800060b8  movaps  xmm1, [rbp+440h+var_450]
  ... truncated ...
```
