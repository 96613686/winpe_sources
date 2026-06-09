# RpcGetSessionInformationEx

- ea: `0x180005cf0`
- end: `0x180006970`
- name: `RpcGetSessionInformationEx`
- size: `3200`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180005500`

## callees

- `0x180005cf0`
- `0x1800077a0`
- `0x180009580`
- `0x1800101b0`
- `0x180010260`
- `0x180029158`
- `0x18004e850`
- `0x18004ec5c`
- `0x18004f354`
- `0x1800637cc`
- `0x18009959c`
- `0x18009c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800066f2`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800066f2`
- `ntdll!NtQueryInformationProcess` at `0x1800066d0`
- `ntdll!NtQueryInformationProcess` at `0x1800066d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000635a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006925`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000635a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006925`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180006346`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180006911`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180006346`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180006911`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180005e42`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180005e42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006724`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006724`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000647c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000647c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800063f6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800063f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006256`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000626c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006545`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006256`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000626c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006545`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180005d91`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180005d91`
- `RPCRT4!RpcImpersonateClient` at `0x180005ef2`
- `RPCRT4!RpcImpersonateClient` at `0x180005ef2`
- `RPCRT4!RpcRevertToSelf` at `0x180005f34`
- `RPCRT4!RpcRevertToSelf` at `0x180005f34`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180005e1b`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180005e1b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800066a2`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800066a2`

## string_xrefs

- `0x18000636b`: `GetCommonSessionInformation`
- `0x1800067ed`: `GetCommonSessionInformation`
- `0x180006559`: `AccessCheckEx failed: 0x%X`
- `0x180006581`: `Failed to allocate memory for ProtocolData failed: 0x%x in %s`
- `0x1800067c1`: `CheckAccessToSession`
- `0x18000680d`: `Cannot impersonate client: %d`
- `0x1800064cb`: `%s with Trace ID 0x%x Completed`
- `0x180006853`: `GetCommonSessionInformation failed: 0x%x in %s`
- `0x1800068fd`: `StringCchCopy failed: 0x%x in %s`
- `0x1800065df`: `TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC`
- `0x18000650c`: `RPC Caller: PID %d, SessID %d, Process Name: <%S>`

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
0x180005cf0  mov     [rsp-8+arg_0], rbx
0x180005cf5  push    rbp
0x180005cf6  push    rsi
0x180005cf7  push    rdi
0x180005cf8  push    r12
0x180005cfa  push    r13
0x180005cfc  push    r14
0x180005cfe  push    r15
0x180005d00  lea     rbp, [rsp-410h]
0x180005d08  sub     rsp, 510h
0x180005d0f  mov     rax, cs:__security_cookie
0x180005d16  xor     rax, rsp
0x180005d19  mov     [rbp+440h+var_40], rax
0x180005d20  mov     r15, r9
0x180005d23  mov     r13d, r8d
0x180005d26  mov     r12d, edx
0x180005d29  xor     edx, edx; Val
0x180005d2b  mov     r8d, 0C8h; Size
0x180005d31  lea     rcx, [rbp+440h+var_4C0]; void *
0x180005d35  call    memset_0
0x180005d3a  xor     r14d, r14d
0x180005d3d  mov     ebx, r14d
0x180005d40  mov     [rsp+540h+var_4FC], r14d
0x180005d45  mov     [rsp+540h+var_4F0], r14
0x180005d4a  mov     [rsp+540h+var_4D8], r14
0x180005d4f  mov     [rsp+540h+pv], r14
0x180005d54  mov     [rsp+540h+var_4D0], r14
0x180005d59  mov     [rsp+540h+Src], r14
0x180005d5e  mov     dword ptr [rsp+540h+uBytes], r14d
0x180005d63  lea     rax, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x180005d6a  mov     [rbp+440h+var_3F0], rax
0x180005d6e  mov     [rbp+440h+var_3D4], 1
0x180005d75  mov     [rbp+440h+var_3D0], r14
0x180005d79  lea     rdi, aRpcgetsessioni_1; "RpcGetSessionInformationEx"
0x180005d80  cmp     cs:?g_bEnabled@CTraceBase@@0HA, r14d; int CTraceBase::g_bEnabled
0x180005d87  jnz     loc_18000658D
0x180005d8d  lea     rcx, [rbp+440h+pguid]; pguid
0x180005d91  call    cs:__imp_CoCreateGuid
0x180005d98  nop     dword ptr [rax+rax+00h]
0x180005d9d  mov     eax, 1
0x180005da2  lock xadd cs:?g_NextShortActivityID@CTraceBase@@0KA, eax; ulong CTraceBase::g_NextShortActivityID
0x180005daa  inc     eax
0x180005dac  mov     [rbp+440h+var_3D8], eax
0x180005daf  mov     [rbp+440h+var_3C8], r14d
0x180005db3  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x180005dba  mov     [rbp+440h+var_3F0], rax
0x180005dbe  mov     [rbp+440h+var_3C0], rdi
0x180005dc5  mov     qword ptr [rbp+440h+Pid], 0FFFFFFFFFFFFFFFFh
0x180005dd0  mov     [rbp+440h+var_3B0], r14d
0x180005dd7  xor     edx, edx; Val
0x180005dd9  mov     r8d, 208h; Size
0x180005ddf  lea     rcx, [rbp+440h+var_3AC]; void *
0x180005de6  call    memset_0
0x180005deb  cmp     [rbp+440h+var_3B0], ebx
0x180005df1  jnz     loc_180006446
0x180005df7  mov     esi, r14d
0x180005dfa  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x180005e01  jnz     loc_18000668A
0x180005e07  mov     qword ptr [rbp+440h+Pid], 0FFFFFFFFFFFFFFFFh
0x180005e12  lea     rdx, [rbp+440h+Pid+4]; Pid
0x180005e19  xor     ecx, ecx; Binding
0x180005e1b  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x180005e22  nop     dword ptr [rax+rax+00h]
0x180005e27  mov     edi, eax
0x180005e29  test    eax, eax
0x180005e2b  jg      loc_18000638B
0x180005e31  test    edi, edi
0x180005e33  js      short loc_180005E56
0x180005e35  lea     rdx, [rbp+440h+Pid]; pSessionId
0x180005e3c  mov     ecx, [rbp+440h+Pid+4]; dwProcessId
0x180005e42  call    cs:__imp_ProcessIdToSessionId
0x180005e49  nop     dword ptr [rax+rax+00h]
0x180005e4e  test    esi, esi
0x180005e50  jnz     loc_180006694
0x180005e56  cmp     [rbp+440h+var_3B0], ebx
0x180005e5c  jnz     loc_1800064E1
0x180005e62  test    r15, r15
0x180005e65  jz      loc_180006738
0x180005e6b  mov     [rsp+540h+var_508], r14
0x180005e70  mov     [rsp+540h+var_4F8], r14
0x180005e75  mov     [rsp+540h+var_500], 80004001h
0x180005e7d  mov     rsi, cs:?pSMGlobalInstance@ISessionManagerInternal@@0PEAV1@EA; ISessionManagerInternal * ISessionManagerInternal::pSMGlobalInstance
0x180005e84  test    rsi, rsi
0x180005e87  jz      loc_180006761
0x180005e8d  mov     [rsp+540h+var_500], r14d
0x180005e92  mov     rax, [rsi]
0x180005e95  mov     rcx, rsi
0x180005e98  mov     rax, [rax+8]
0x180005e9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ea1  mov     rax, [rsi]
0x180005ea4  lea     rdx, [rsp+540h+var_508]
0x180005ea9  mov     rcx, rsi
0x180005eac  mov     rax, [rax+18h]
0x180005eb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005eb5  mov     edi, eax
0x180005eb7  test    eax, eax
0x180005eb9  js      loc_18000636B
0x180005ebf  mov     rcx, [rsp+540h+var_508]
0x180005ec4  mov     rax, [rcx]
0x180005ec7  lea     r8, [rsp+540h+var_4F8]
0x180005ecc  mov     edx, r12d
0x180005ecf  mov     rax, [rax+18h]
0x180005ed3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ed8  mov     edi, eax
0x180005eda  test    eax, eax
0x180005edc  js      loc_18000642D
0x180005ee2  mov     rdi, [rsp+540h+var_4F8]
0x180005ee7  test    rdi, rdi
0x180005eea  jz      loc_1800067C1
0x180005ef0  xor     ecx, ecx; BindingHandle
0x180005ef2  call    cs:__imp_RpcImpersonateClient
0x180005ef9  nop     dword ptr [rax+rax+00h]
0x180005efe  test    eax, eax
0x180005f00  jnz     loc_18000680A
0x180005f06  mov     rax, [rdi]
0x180005f09  mov     r9d, 1
0x180005f0f  xor     r8d, r8d
0x180005f12  mov     edx, r9d
0x180005f15  mov     rcx, rdi
0x180005f18  mov     rax, [rax+90h]
0x180005f1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f24  mov     r14d, eax
0x180005f27  mov     edi, 80070005h
0x180005f2c  test    eax, eax
0x180005f2e  js      loc_180006556
0x180005f34  call    cs:__imp_RpcRevertToSelf
0x180005f3b  nop     dword ptr [rax+rax+00h]
0x180005f40  test    eax, eax
0x180005f42  jnz     loc_180006828
0x180005f48  mov     edi, r14d
0x180005f4b  test    r14d, r14d
0x180005f4e  js      loc_180006841
0x180005f54  mov     rbx, [rsp+540h+var_4F8]
0x180005f59  mov     rax, [rbx]
0x180005f5c  mov     rcx, rbx
0x180005f5f  mov     rax, [rax+8]
0x180005f63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f68  xor     r14d, r14d
0x180005f6b  mov     rcx, [rsp+540h+var_4F8]
0x180005f70  test    rcx, rcx
0x180005f73  jz      short loc_180005F82
0x180005f75  mov     rax, [rcx]
0x180005f78  mov     rax, [rax+10h]
0x180005f7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f81  nop
0x180005f82  mov     rcx, [rsp+540h+var_508]
0x180005f87  test    rcx, rcx
0x180005f8a  jz      short loc_180005F99
0x180005f8c  mov     rax, [rcx]
0x180005f8f  mov     rax, [rax+10h]
0x180005f93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f98  nop
0x180005f99  mov     rax, [rsi]
0x180005f9c  mov     rcx, rsi
0x180005f9f  mov     rax, [rax+10h]
0x180005fa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fa8  nop
0x180005fa9  test    edi, edi
0x180005fab  js      loc_180006849
0x180005fb1  cmp     r13d, 1
0x180005fb5  ja      loc_18000685F
0x180005fbb  mov     rax, [rbx]
0x180005fbe  lea     rdx, [rsp+540h+var_4FC]
0x180005fc3  mov     rcx, rbx
0x180005fc6  mov     rax, [rax+58h]
0x180005fca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fcf  mov     edi, eax
0x180005fd1  test    eax, eax
0x180005fd3  js      loc_18000686A
0x180005fd9  movsxd  rdx, [rsp+540h+var_4FC]
0x180005fde  cmp     edx, 1
0x180005fe1  jnz     loc_18000631D
0x180005fe7  mov     dword ptr [rbp+440h+var_4C0], 9; jumptable 00000001800063B4 case 0
0x180005fee  mov     dword ptr [rbp+440h+var_4C0+4], 0FFFFFFFFh
0x180005ff5  mov     rax, [rbx]
0x180005ff8  lea     r9, [rbp+440h+var_420+8]
0x180005ffc  lea     r8, [rbp+440h+var_420]
0x180006000  lea     rdx, [rbp+440h+var_428]
0x180006004  mov     rcx, rbx
0x180006007  mov     rax, [rax+0C8h]
0x18000600e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006013  mov     edi, eax
0x180006015  test    eax, eax
0x180006017  js      loc_1800063CE
0x18000601d  mov     rax, [rbx]
0x180006020  lea     rdx, [rsp+540h+var_4F0]
0x180006025  mov     rcx, rbx
0x180006028  mov     rax, [rax+60h]
0x18000602c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006031  mov     esi, 7FFFFFFEh
0x180006036  test    eax, eax
0x180006038  js      loc_180006103
0x18000603e  mov     rcx, [rsp+540h+var_4F0]
0x180006043  mov     rax, [rcx]
0x180006046  lea     rdx, [rsp+540h+var_4D8]
0x18000604b  mov     rax, [rax+28h]
0x18000604f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006054  mov     edi, eax
0x180006056  test    eax, eax
0x180006058  js      loc_18000641A
0x18000605e  mov     ecx, esi
0x180006060  mov     rdx, [rsp+540h+var_4D8]
0x180006065  mov     r9d, 15h
0x18000606b  lea     r8, [rbp+440h+var_452]
0x18000606f  test    rcx, rcx
0x180006072  jz      short loc_180006091
0x180006074  movzx   eax, word ptr [rdx]
0x180006077  test    ax, ax
0x18000607a  jz      short loc_180006091
0x18000607c  add     rdx, 2
0x180006080  mov     [r8], ax
0x180006084  add     r8, 2
0x180006088  dec     rcx
0x18000608b  sub     r9, 1
0x18000608f  jnz     short loc_18000606F
0x180006091  lea     rcx, [r8-2]
0x180006095  test    r9, r9
0x180006098  cmovnz  rcx, r8
0x18000609c  mov     [rcx], r14w
0x1800060a0  mov     rcx, [rsp+540h+var_4F0]
0x1800060a5  mov     rax, [rcx]
0x1800060a8  lea     rdx, [rsp+540h+pv]
0x1800060ad  mov     rax, [rax+30h]
0x1800060b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060b6  mov     edi, eax
0x1800060b8  test    eax, eax
0x1800060ba  js      loc_1800068DD
0x1800060c0  mov     rcx, rsi
0x1800060c3  mov     rdx, [rsp+540h+pv]
0x1800060c8  mov     r9d, 12h
0x1800060ce  lea     r8, [rbp+440h+var_476]
0x1800060d2  test    rcx, rcx
0x1800060d5  jz      short loc_1800060F4
0x1800060d7  movzx   eax, word ptr [rdx]
0x1800060da  test    ax, ax
0x1800060dd  jz      short loc_1800060F4
0x1800060df  add     rdx, 2
0x1800060e3  mov     [r8], ax
0x1800060e7  add     r8, 2
0x1800060eb  dec     rcx
0x1800060ee  sub     r9, 1
0x1800060f2  jnz     short loc_1800060D2
0x1800060f4  lea     rcx, [r8-2]
0x1800060f8  test    r9, r9
0x1800060fb  cmovnz  rcx, r8
0x1800060ff  mov     [rcx], r14w
0x180006103  mov     rax, [rbx]
0x180006106  lea     rdx, [rsp+540h+var_4D0]
0x18000610b  mov     rcx, rbx
0x18000610e  mov     rax, [rax+68h]
0x180006112  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006117  test    eax, eax
0x180006119  js      loc_1800063C6
0x18000611f  mov     rcx, [rsp+540h+var_4D0]
0x180006124  mov     rax, [rcx]
0x180006127  lea     r9, [rsp+540h+uBytes]
0x18000612c  lea     r8, [rsp+540h+Src]
0x180006131  lea     rdx, [rbp+440h+var_90]
0x180006138  mov     rax, [rax+0B8h]
0x18000613f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006144  mov     edi, eax
0x180006146  test    eax, eax
0x180006148  js      loc_180006407
0x18000614e  mov     eax, dword ptr [rsp+540h+uBytes]
0x180006152  test    eax, eax
0x180006154  jnz     loc_180006474
0x18000615a  lea     rcx, [rbp+440h+var_90]
0x180006161  mov     edx, 21h ; '!'
0x180006166  lea     r8, [rbp+440h+var_4C0+8]
0x18000616a  test    rsi, rsi
0x18000616d  jz      short loc_18000618C
0x18000616f  movzx   eax, word ptr [rcx]
0x180006172  test    ax, ax
0x180006175  jz      short loc_18000618C
0x180006177  add     rcx, 2
0x18000617b  mov     [r8], ax
0x18000617f  add     r8, 2
0x180006183  dec     rsi
0x180006186  sub     rdx, 1
0x18000618a  jnz     short loc_18000616A
0x18000618c  mov     edi, 8007007Ah
0x180006191  test    rdx, rdx
0x180006194  cmovnz  edi, r14d
0x180006198  lea     rcx, [r8-2]
0x18000619c  cmovnz  rcx, r8
0x1800061a0  mov     [rcx], r14w
0x1800061a4  jz      loc_1800068F3
0x1800061aa  mov     [r15], r13d
0x1800061ad  cmp     r13d, 1
0x1800061b1  jnz     loc_1800063E9
0x1800061b7  movaps  xmm0, [rbp+440h+var_4C0]
0x1800061bb  movups  xmmword ptr [r15+8], xmm0
0x1800061c0  movaps  xmm1, [rbp+440h+var_4B0]
0x1800061c4  movups  xmmword ptr [r15+18h], xmm1
0x1800061c9  movaps  xmm0, [rbp+440h+var_4A0]
0x1800061cd  movups  xmmword ptr [r15+28h], xmm0
0x1800061d2  movaps  xmm1, [rbp+440h+var_490]
0x1800061d6  movups  xmmword ptr [r15+38h], xmm1
0x1800061db  movaps  xmm0, xmmword ptr [rbp-40h]
0x1800061df  movups  xmmword ptr [r15+48h], xmm0
  ... truncated ...
```
