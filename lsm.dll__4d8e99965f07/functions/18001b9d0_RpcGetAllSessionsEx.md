# RpcGetAllSessionsEx

- ea: `0x18001b9d0`
- end: `0x18001ce88`
- name: `RpcGetAllSessionsEx`
- size: `5304`
- prototype: `__int64 __fastcall(__int64, unsigned int, _QWORD *, unsigned int *)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800077a0`
- `0x180009580`
- `0x1800101b0`
- `0x180010260`
- `0x18001b9d0`
- `0x18001ce90`
- `0x180029158`
- `0x18004e850`
- `0x18004ec5c`
- `0x18004f354`
- `0x1800637cc`
- `0x180087cb0`
- `0x18009c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18001cb27`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18001cb27`
- `ntdll!NtQueryInformationProcess` at `0x18001cb05`
- `ntdll!NtQueryInformationProcess` at `0x18001cb05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c2ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c541`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ce3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c2ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c541`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ce3d`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001c52d`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001ce29`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001c52d`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001ce29`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001bb64`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001bb64`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001bb45`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001bb45`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18001bafd`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18001bafd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bb82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cb56`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bb82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cb56`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001bbcd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001bdd3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001bf23`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c0b7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c183`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c266`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c488`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c594`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c773`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001bbcd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001bdd3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001bf23`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c0b7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c183`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c266`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c488`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c594`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c773`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bfb0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bfcf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cdef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ce00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bfb0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bfcf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cdef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ce00`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001ba6a`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001ba6a`
- `RPCRT4!RpcImpersonateClient` at `0x18001bb90`
- `RPCRT4!RpcImpersonateClient` at `0x18001bb90`
- `RPCRT4!RpcRevertToSelf` at `0x18001c393`
- `RPCRT4!RpcRevertToSelf` at `0x18001c393`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18001badc`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18001badc`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001cad7`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001cad7`

## string_xrefs

- `0x18001cb81`: `RpcImpersonateClient failed: 0x%x in %s`
- `0x18001c901`: `%s with Trace ID 0x%x Completed`
- `0x18001cb9c`: `Impersonate.ImpersonateRpcClient failed: 0x%x in %s`
- `0x18001ca45`: `TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC`
- `0x18001c939`: `RPC Caller: PID %d, SessID %d, Process Name: <%S>`
- `0x18001cb77`: `CImpersonate::ImpersonateRpcClient`

## pseudocode

```c
__int64 __fastcall RpcGetAllSessionsEx(__int64 a1, unsigned int a2, _QWORD *a3, unsigned int *a4)
{
  struct ISessionManagerInternal *v6; // rbx
  char *v7; // r14
  unsigned int v8; // r13d
  unsigned int v9; // esi
  RPC_STATUS v10; // eax
  int v11; // edi
  unsigned int v12; // esi
  HANDLE CurrentThread; // rax
  RPC_STATUS v14; // eax
  signed int v15; // edi
  volatile unsigned int v16; // edi
  char *v17; // rax
  int v18; // eax
  int v19; // eax
  char v20; // r15
  char v21; // r12
  __int64 v22; // rcx
  int v23; // eax
  char *v24; // r15
  int v25; // eax
  __int64 v26; // rcx
  _WORD *v27; // rax
  SIZE_T v28; // rsi
  _WORD *v29; // r8
  unsigned __int64 v30; // rsi
  __int64 v31; // rcx
  __int16 *v32; // rdx
  __int16 v33; // ax
  _WORD *v34; // rcx
  int v35; // esi
  __int64 v36; // rcx
  __int16 *v37; // rsi
  __int64 v38; // rcx
  _WORD *v39; // rax
  __int64 v40; // r14
  SIZE_T v41; // r14
  _WORD *v42; // rdx
  unsigned __int64 v43; // r14
  __int64 v44; // rcx
  __int16 v45; // ax
  _WORD *v46; // rcx
  int v47; // esi
  __int64 v48; // rcx
  __int64 v49; // rcx
  int *v50; // rax
  SIZE_T v51; // rsi
  _WORD *v52; // rdx
  unsigned __int64 v53; // rsi
  __int64 v54; // rcx
  int *v55; // r8
  __int16 v56; // ax
  _WORD *v57; // rcx
  int v58; // esi
  __int64 v59; // rcx
  int *v60; // rax
  SIZE_T v61; // rsi
  _WORD *v62; // rdx
  unsigned __int64 v63; // rsi
  __int64 v64; // rcx
  int *v65; // r8
  __int16 v66; // ax
  _WORD *v67; // rcx
  int v68; // esi
  __int16 *v69; // r14
  __int64 v70; // rcx
  _WORD *v71; // rax
  __int64 v72; // rsi
  SIZE_T v73; // rsi
  _WORD *v74; // rdx
  unsigned __int64 v75; // rsi
  __int64 v76; // rcx
  __int16 v77; // ax
  _WORD *v78; // rcx
  int v79; // esi
  __int64 v81; // rcx
  int *v82; // rax
  SIZE_T v83; // rsi
  _WORD *v84; // r8
  unsigned __int64 v85; // rsi
  __int64 v86; // rcx
  int *v87; // rdx
  __int16 v88; // ax
  _WORD *v89; // rcx
  int v90; // esi
  __int64 v91; // rcx
  int *v92; // rax
  SIZE_T v93; // rsi
  _WORD *v94; // rdx
  unsigned __int64 v95; // rsi
  __int64 v96; // rcx
  int *v97; // r8
  __int16 v98; // ax
  _WORD *v99; // rcx
  int v100; // esi
  __int64 v101; // rcx
  int *v102; // rax
  SIZE_T v103; // rsi
  _WORD *v104; // rdx
  unsigned __int64 v105; // rsi
  __int64 v106; // rcx
  int *v107; // r8
  __int16 v108; // ax
  _WORD *v109; // rcx
  HANDLE v110; // rax
  void *v111; // r14
  NTSTATUS InformationProcess; // eax
  wchar_t *v113; // rax
  wchar_t *v114; // rax
  CSessionManager *v115; // rax
  struct ISessionManagerInternal *v116; // rax
  char v117; // [rsp+30h] [rbp-D0h]
  void *TokenHandle; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v119; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v120; // [rsp+48h] [rbp-B8h]
  struct CTraceBase *v121; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v122; // [rsp+58h] [rbp-A8h] BYREF
  int v123; // [rsp+60h] [rbp-A0h] BYREF
  int v124; // [rsp+64h] [rbp-9Ch] BYREF
  LPVOID pv; // [rsp+68h] [rbp-98h] BYREF
  LPVOID v126; // [rsp+70h] [rbp-90h] BYREF
  __int64 v127; // [rsp+78h] [rbp-88h] BYREF
  __int64 v128; // [rsp+80h] [rbp-80h] BYREF
  __int64 v129; // [rsp+88h] [rbp-78h] BYREF
  _QWORD *v130; // [rsp+90h] [rbp-70h]
  unsigned int *v131; // [rsp+98h] [rbp-68h]
  void **v132; // [rsp+A0h] [rbp-60h] BYREF
  GUID pguid; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v134[2]; // [rsp+B8h] [rbp-48h] BYREF
  struct CTraceBase *v135; // [rsp+C0h] [rbp-40h] BYREF
  int v136; // [rsp+C8h] [rbp-38h]
  const char *v137; // [rsp+D0h] [rbp-30h]
  unsigned int Pid[2]; // [rsp+D8h] [rbp-28h] BYREF
  int v139; // [rsp+E0h] [rbp-20h]
  unsigned __int16 v140[262]; // [rsp+E4h] [rbp-1Ch] BYREF
  char ProcessInformation[8]; // [rsp+2F0h] [rbp+1F0h] BYREF
  wchar_t *Str; // [rsp+2F8h] [rbp+1F8h]
  _WORD v143[40]; // [rsp+400h] [rbp+300h] BYREF

  v131 = a4;
  v130 = a3;
  v120 = a2;
  v119 = 0;
  v127 = 0;
  v6 = 0;
  v129 = 0;
  v128 = 0;
  v7 = 0;
  v8 = 0;
  v122 = 0;
  pv = 0;
  v126 = 0;
  v132 = &CTraceBase::`vftable';
  v134[1] = 1;
  v135 = 0;
  if ( CTraceBase::g_bEnabled )
  {
    if ( (g_DebugTraceComponent & 1) != 0 )
      _DbgPrintMessage(2, "Adding trace %p, %d, %s", &v132, 1, "RpcGetAllSessionsEx");
    v121 = 0;
    if ( (int)CTraceBase::GetThreadCurrentOperationTrace(&v121) >= 0 && v121 && (g_DebugTraceComponent & 1) != 0 )
      _DbgPrintMessage(
        2,
        "TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC",
        1);
    CTraceBase::ResetThreadCurrentOperationTrace(0, 0);
    if ( (int)CTraceBase::GetThreadCurrentOperationTrace(&v135) >= 0 && v135 )
    {
      (*(void (__fastcall **)(struct CTraceBase *, GUID *))(*(_QWORD *)v135 + 32LL))(v135, &pguid);
      v134[0] = (*(__int64 (__fastcall **)(struct CTraceBase *))(*(_QWORD *)v135 + 24LL))(v135);
      v136 = 1;
      goto LABEL_4;
    }
    CTraceBase::ResetThreadCurrentOperationTrace((struct CTraceBase *)&v132, "RpcGetAllSessionsEx");
    CTraceBase::GenerateTraceID(&pguid, v134);
  }
  else
  {
    CoCreateGuid(&pguid);
    v134[0] = _InterlockedIncrement((volatile signed __int32 *)&CTraceBase::g_NextShortActivityID);
  }
  v136 = 0;
LABEL_4:
  v132 = &CRpcCallTrace::`vftable';
  v137 = "RpcGetAllSessionsEx";
  *(_QWORD *)Pid = -1;
  v139 = 0;
  memset_0(v140, 0, 0x208u);
  if ( v139 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "TRACE RPC %s with Trace ID 0x%x", v137, v134[0]);
  v9 = 0;
  if ( (g_DebugTraceComponent & 1) != 0 )
    v9 = 260;
  *(_QWORD *)Pid = -1;
  v10 = I_RpcBindingInqLocalClientPID(0, &Pid[1]);
  v11 = v10;
  if ( v10 > 0 )
    v11 = (unsigned __int16)v10 | 0x80070000;
  if ( v11 >= 0 )
  {
    ProcessIdToSessionId(Pid[1], Pid);
    if ( v9 )
    {
      v110 = OpenProcess(0x400u, 0, Pid[1]);
      v111 = v110;
      if ( v110 )
      {
        InformationProcess = NtQueryInformationProcess(v110, ProcessImageFileName, ProcessInformation, 0x110u, 0);
        v11 = InformationProcess | 0x10000000;
        if ( InformationProcess >= 0 )
        {
          v113 = wcsrchr(Str, 0x5Cu);
          if ( v113 )
            v114 = v113 + 1;
          else
            v114 = Str;
          StringCchCopyW(v140, v9, v114);
        }
        CloseHandle(v111);
      }
      v7 = 0;
    }
  }
  if ( v139 )
  {
    if ( v11 < 0 )
    {
      if ( (g_DebugTraceComponent & 1) != 0 )
        _DbgPrintMessage(2, "RPC Caller: Unknown");
    }
    else if ( (g_DebugTraceComponent & 1) != 0 )
    {
      _DbgPrintMessage(2, "RPC Caller: PID %d, SessID %d, Process Name: <%S>", Pid[1], Pid[0], v140);
    }
  }
  if ( !a3 || !a4 )
  {
    v21 = 0;
    v15 = -2147024809;
    goto LABEL_219;
  }
  v12 = 0;
  *a3 = 0;
  *a4 = 0;
  if ( v120 > 1 )
    v120 = 1;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xEu, 1, &TokenHandle) )
    GetLastError();
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  v14 = RpcImpersonateClient(0);
  v15 = v14;
  if ( v14 > 0 )
    v15 = (unsigned __int16)v14 | 0x80070000;
  if ( v15 < 0 )
  {
    _DbgPrintMessage(8, "RpcImpersonateClient failed: 0x%x in %s", v15, "CImpersonate::ImpersonateRpcClient");
    _DbgPrintMessage(8, "Impersonate.ImpersonateRpcClient failed: 0x%x in %s", v15, "RpcGetAllSessionsEx");
    v21 = 0;
    goto LABEL_219;
  }
  v8 = CTSPerfProvider::TotalSessions;
  if ( !CTSPerfProvider::TotalSessions )
  {
    v15 = 0;
    v21 = 1;
    goto LABEL_153;
  }
  v16 = CTSPerfProvider::TotalSessions << 6;
  v17 = (char *)LocalAlloc(0x40u, (unsigned int)(CTSPerfProvider::TotalSessions << 6));
  v7 = v17;
  TokenHandle = v17;
  if ( !v17 )
  {
    v15 = -2147024882;
    v21 = 1;
    goto LABEL_219;
  }
  memset_0(v17, 0, v16);
  v8 = v16 >> 6;
  v123 = -2147467263;
  v6 = ISessionManagerInternal::pSMGlobalInstance;
  if ( ISessionManagerInternal::pSMGlobalInstance )
    goto LABEL_26;
  v6 = 0;
  v115 = (CSessionManager *)operator new(0x758u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v115 )
  {
    v116 = CSessionManager::CSessionManager(v115, &v123);
    ISessionManagerInternal::pSMGlobalInstance = v116;
    if ( v116 )
    {
      (*(void (__fastcall **)(struct ISessionManagerInternal *))(*(_QWORD *)v116 + 8LL))(v116);
      v6 = ISessionManagerInternal::pSMGlobalInstance;
LABEL_26:
      v123 = 0;
      (*(void (__fastcall **)(struct ISessionManagerInternal *))(*(_QWORD *)v6 + 8LL))(v6);
    }
  }
  else
  {
    ISessionManagerInternal::pSMGlobalInstance = 0;
  }
  v18 = (*(__int64 (__fastcall **)(struct ISessionManagerInternal *, __int64 *))(*(_QWORD *)v6 + 24LL))(v6, &v129);
  v15 = v18;
  if ( v18 < 0 )
  {
    _DbgPrintMessage(8, "GetSessionList failed: 0x%x in %s", v18, "RpcGetAllSessionsEx");
    v21 = 1;
    goto LABEL_219;
  }
  v19 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v129 + 32LL))(v129, &v128);
  v15 = v19;
  if ( v19 < 0 )
  {
    _DbgPrintMessage(8, "GetInstanceOfEnum failed: 0x%x in %s", v19, "RpcGetAllSessionsEx");
    v21 = 1;
    goto LABEL_219;
  }
  v20 = RDVIsInWellKnownGroup();
  v117 = v20;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v128 + 88LL))(v128);
  v21 = 1;
  while ( 1 )
  {
    LODWORD(v121) = v12;
    do
    {
      if ( v12 >= v8 )
        goto LABEL_152;
      v22 = v119;
      v119 = 0;
      if ( v22 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      v23 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v128 + 80LL))(v128, &v119);
      v15 = v23;
      if ( v23 == -2147024637 )
      {
LABEL_152:
        *v130 = v7;
        *v131 = v12;
        v7 = 0;
        v15 = 0;
        goto LABEL_153;
      }
      if ( v23 < 0 )
      {
        _DbgPrintMessage(8, "Enum failed: 0x%x in %s", v23, "RpcGetAllSessionsEx");
        goto LABEL_219;
      }
    }
    while ( !v20 && (*(int (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v119 + 136LL))(v119, 1, 0) < 0 );
    v24 = &v7[64 * (unsigned __int64)v12];
    *(_DWORD *)v24 = v120;
    (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v119 + 80LL))(v119, v24 + 8);
    *((_DWORD *)v24 + 4) = *((_DWORD *)v24 + 2);
    v124 = 0;
    (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v119 + 88LL))(v119, &v124);
    if ( v124 == 1 )
    {
LABEL_38:
      v25 = 9;
    }
    else if ( v124 == 12 )
    {
LABEL_151:
      v25 = 0;
    }
    else
    {
      switch ( v124 )
      {
        case 0:
          goto LABEL_38;
        case 2:
        case 6:
          v25 = 1;
          break;
        case 3:
        case 4:
        case 13:
          v25 = 4;
          break;
        case 5:
          goto LABEL_151;
        case 7:
          v25 = 3;
          break;
        case 8:
        case 9:
          v25 = 2;
          break;
        default:
          v25 = 8;
          break;
      }
    }
    *((_DWORD *)v24 + 3) = v25;
    v143[0] = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v119 + 104LL))(v119, &v127);
    if ( v127 )
    {
      if ( (*(int (__fastcall **)(__int64, _WORD *))(*(_QWORD *)v127 + 104LL))(v127, v143) >= 0 )
        break;
    }
LABEL_57:
    v36 = v122;
    v122 = 0;
    if ( v36 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v119 + 96LL))(v119, &v122) >= 0 )
    {
      if ( (*(int (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v122 + 40LL))(v122, &pv) >= 0 )
      {
        v69 = (__int16 *)pv;
        if ( !pv )
        {
          v15 = -2147024809;
LABEL_243:
          v79 = v15;
          _DbgPrintMessage(8, "StringCbLength failed: 0x%x in %s", v15, "CRpcUtils::MIDL_str_dup");
LABEL_244:
          _DbgPrintMessage(8, "CRpcUtils::MIDL_str_dup(UserName) failed: 0x%x in %s", v79, "RpcGetAllSessionsEx");
          v7 = (char *)TokenHandle;
          goto LABEL_219;
        }
        v70 = 257;
        v71 = pv;
        do
        {
          if ( !*v71 )
            break;
          ++v71;
          --v70;
        }
        while ( v70 );
        v15 = -2147024809;
        if ( v70 )
        {
          v15 = 0;
          v72 = 2 * (257 - v70);
        }
        else
        {
          v72 = 0;
        }
        if ( !v70 )
          goto LABEL_243;
        v73 = v72 + 2;
        v74 = LocalAlloc(0x40u, v73);
        *((_QWORD *)v24 + 5) = v74;
        if ( !v74 )
        {
          v15 = -2147024882;
          v79 = -2147024882;
          goto LABEL_244;
        }
        v75 = v73 >> 1;
        if ( v75 )
        {
          if ( v75 > 0x7FFFFFFF )
          {
            v15 = -2147024809;
            *v74 = 0;
          }
          else
          {
            v76 = 2147483646;
            do
            {
              if ( !v76 )
                break;
              v77 = *v69;
              if ( !*v69 )
                break;
              ++v69;
              *v74++ = v77;
              --v76;
              --v75;
            }
            while ( v75 );
            v78 = v74 - 1;
            if ( v75 )
              v78 = v74;
            *v78 = 0;
            v15 = -2147024774;
            if ( v75 )
              v15 = 0;
          }
        }
        else
        {
          v15 = -2147024809;
        }
        v79 = v15;
        if ( v15 < 0 )
          goto LABEL_244;
      }
      if ( (*(int (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v122 + 48LL))(v122, &v126) >= 0 )
      {
        v37 = (__int16 *)v126;
        if ( !v126 )
        {
          v15 = -2147024809;
LABEL_217:
          v47 = v15;
          _DbgPrintMessage(8, "StringCbLength failed: 0x%x in %s", v15, "CRpcUtils::MIDL_str_dup");
LABEL_218:
          _DbgPrintMessage(8, "CRpcUtils::MIDL_str_dup(DomainName) failed: 0x%x in %s", v47, "RpcGetAllSessionsEx");
          v7 = (char *)TokenHandle;
          goto LABEL_219;
        }
        v38 = 256;
        v39 = v126;
        do
        {
          if ( !*v39 )
            break;
          ++v39;
          --v38;
        }
        while ( v38 );
        v15 = -2147024809;
        if ( v38 )
        {
          v15 = 0;
          v40 = 2 * (256 - v38);
        }
        else
        {
          v40 = 0;
        }
        if ( !v38 )
          goto LABEL_217;
        v41 = v40 + 2;
        v42 = LocalAlloc(0x40u, v41);
        *((_QWORD *)v24 + 6) = v42;
        if ( !v42 )
        {
          v15 = -2147024882;
          v47 = -2147024882;
          goto LABEL_218;
        }
        v43 = v41 >> 1;
        if ( v43 )
        {
          if ( v43 > 0x7FFFFFFF )
          {
            v15 = -2147024809;
            *v42 = 0;
          }
          else
          {
            v44 = 2147483646;
            do
            {
              if ( !v44 )
                break;
              v45 = *v37;
              if ( !*v37 )
                break;
              ++v37;
              *v42++ = v45;
              --v44;
              --v43;
            }
            while ( v43 );
            v46 = v42 - 1;
            if ( v43 )
              v46 = v42;
            *v46 = 0;
            v15 = -2147024774;
            if ( v43 )
              v15 = 0;
          }
        }
        else
        {
          v15 = -2147024809;
        }
        v47 = v15;
        if ( v15 < 0 )
          goto LABEL_218;
      }
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      if ( v126 )
      {
        CoTaskMemFree(v126);
        v126 = 0;
      }
      v7 = (char *)TokenHandle;
    }
    if ( !*((_QWORD *)v24 + 3) )
    {
      v101 = 33;
      v102 = &dword_1800A8ADC;
      do
      {
        if ( !*(_WORD *)v102 )
          break;
        v102 = (int *)((char *)v102 + 2);
        --v101;
      }
      while ( v101 );
      v15 = -2147024809;
      if ( !v101 )
        goto LABEL_220;
      v103 = 2 * (34 - v101);
      v104 = LocalAlloc(0x40u, v103);
      *((_QWORD *)v24 + 3) = v104;
      if ( !v104 )
        goto LABEL_307;
      v105 = v103 >> 1;
      if ( v105 )
      {
        if ( v105 > 0x7FFFFFFF )
        {
          v15 = -2147024809;
          *v104 = 0;
        }
        else
        {
          v106 = 2147483646;
          v107 = &dword_1800A8ADC;
          do
          {
            if ( !v106 )
              break;
            v108 = *(_WORD *)v107;
            if ( !*(_WORD *)v107 )
              break;
            v107 = (int *)((char *)v107 + 2);
            *v104++ = v108;
            --v106;
            --v105;
          }
          while ( v105 );
          v109 = v104 - 1;
          if ( v105 )
            v109 = v104;
          *v109 = 0;
          v15 = -2147024774;
          if ( v105 )
            v15 = 0;
        }
      }
      else
      {
        v15 = -2147024809;
      }
      v35 = v15;
      if ( v15 < 0 )
        goto LABEL_221;
    }
    if ( !*((_QWORD *)v24 + 4) )
    {
      v59 = 256;
      v60 = &dword_1800A8ADC;
      do
      {
        if ( !*(_WORD *)v60 )
          break;
        v60 = (int *)((char *)v60 + 2);
        --v59;
      }
      while ( v59 );
      v15 = -2147024809;
      if ( !v59 )
      {
        v68 = -2147024809;
        _DbgPrintMessage(8, "StringCbLength failed: 0x%x in %s", -2147024809, "CRpcUtils::MIDL_str_dup");
LABEL_256:
        _DbgPrintMessage(8, "CRpcUtils::MIDL_str_dup(.pszHostName) failed: 0x%x in %s", v68, "RpcGetAllSessionsEx");
        goto LABEL_219;
      }
      v61 = 2 * (257 - v59);
      v62 = LocalAlloc(0x40u, v61);
      *((_QWORD *)v24 + 4) = v62;
      if ( !v62 )
      {
        v15 = -2147024882;
        v68 = -2147024882;
        goto LABEL_256;
      }
      v63 = v61 >> 1;
      if ( v63 )
      {
        if ( v63 > 0x7FFFFFFF )
        {
          v15 = -2147024809;
          *v62 = 0;
        }
        else
        {
          v64 = 2147483646;
          v65 = &dword_1800A8ADC;
          do
          {
            if ( !v64 )
              break;
            v66 = *(_WORD *)v65;
            if ( !*(_WORD *)v65 )
              break;
            v65 = (int *)((char *)v65 + 2);
            *v62++ = v66;
            --v64;
            --v63;
          }
          while ( v63 );
          v67 = v62 - 1;
          if ( v63 )
            v67 = v62;
          *v67 = 0;
          v15 = -2147024774;
          if ( v63 )
            v15 = 0;
        }
      }
      else
      {
        v15 = -2147024809;
      }
      v68 = v15;
      if ( v15 < 0 )
        goto LABEL_256;
    }
    if ( !*((_QWORD *)v24 + 5) )
    {
      v91 = 257;
      v92 = &dword_1800A8ADC;
      do
      {
        if ( !*(_WORD *)v92 )
          break;
        v92 = (int *)((char *)v92 + 2);
        --v91;
      }
      while ( v91 );
      v15 = -2147024809;
      if ( !v91 )
      {
        v100 = -2147024809;
        _DbgPrintMessage(8, "StringCbLength failed: 0x%x in %s", -2147024809, "CRpcUtils::MIDL_str_dup");
LABEL_261:
        _DbgPrintMessage(8, "CRpcUtils::MIDL_str_dup(pszUserName) failed: 0x%x in %s", v100, "RpcGetAllSessionsEx");
        goto LABEL_219;
      }
      v93 = 2 * (258 - v91);
      v94 = LocalAlloc(0x40u, v93);
      *((_QWORD *)v24 + 5) = v94;
      if ( !v94 )
      {
        v15 = -2147024882;
        v100 = -2147024882;
        goto LABEL_261;
      }
      v95 = v93 >> 1;
      if ( v95 )
      {
        if ( v95 > 0x7FFFFFFF )
        {
          v15 = -2147024809;
          *v94 = 0;
        }
        else
        {
          v96 = 2147483646;
          v97 = &dword_1800A8ADC;
          do
          {
            if ( !v96 )
              break;
            v98 = *(_WORD *)v97;
            if ( !*(_WORD *)v97 )
              break;
            v97 = (int *)((char *)v97 + 2);
            *v94++ = v98;
            --v96;
            --v95;
          }
          while ( v95 );
          v99 = v94 - 1;
          if ( v95 )
            v99 = v94;
          *v99 = 0;
          v15 = -2147024774;
          if ( v95 )
            v15 = 0;
        }
      }
      else
      {
        v15 = -2147024809;
      }
      v100 = v15;
      if ( v15 < 0 )
        goto LABEL_261;
    }
    if ( !*((_QWORD *)v24 + 6) )
    {
      v81 = 256;
      v82 = &dword_1800A8ADC;
      do
      {
        if ( !*(_WORD *)v82 )
          break;
        v82 = (int *)((char *)v82 + 2);
        --v81;
      }
      while ( v81 );
      v15 = -2147024809;
      if ( !v81 )
      {
        v90 = -2147024809;
        _DbgPrintMessage(8, "StringCbLength failed: 0x%x in %s", -2147024809, "CRpcUtils::MIDL_str_dup");
LABEL_246:
        _DbgPrintMessage(8, "CRpcUtils::MIDL_str_dup(pszDomainName) failed: 0x%x in %s", v90, "RpcGetAllSessionsEx");
        goto LABEL_219;
      }
      v83 = 2 * (257 - v81);
      v84 = LocalAlloc(0x40u, v83);
      *((_QWORD *)v24 + 6) = v84;
      if ( !v84 )
      {
        v15 = -2147024882;
        v90 = -2147024882;
        goto LABEL_246;
      }
      v85 = v83 >> 1;
      if ( v85 )
      {
        if ( v85 > 0x7FFFFFFF )
        {
          v15 = -2147024809;
          *v84 = 0;
        }
        else
        {
          v86 = 2147483646;
          v87 = &dword_1800A8ADC;
          do
          {
            if ( !v86 )
              break;
            v88 = *(_WORD *)v87;
            if ( !*(_WORD *)v87 )
              break;
            v87 = (int *)((char *)v87 + 2);
            *v84++ = v88;
            --v86;
            --v85;
          }
          while ( v85 );
          v89 = v84 - 1;
          if ( v85 )
            v89 = v84;
          *v89 = 0;
          v15 = -2147024774;
          if ( v85 )
            v15 = 0;
        }
      }
      else
      {
        v15 = -2147024809;
      }
      v90 = v15;
      if ( v15 < 0 )
        goto LABEL_246;
    }
    if ( !*((_QWORD *)v24 + 7) )
    {
      v49 = 256;
      v50 = &dword_1800A8ADC;
      do
      {
        if ( !*(_WORD *)v50 )
          break;
        v50 = (int *)((char *)v50 + 2);
        --v49;
      }
      while ( v49 );
      v15 = -2147024809;
      if ( !v49 )
      {
        v58 = -2147024809;
        _DbgPrintMessage(8, "StringCbLength failed: 0x%x in %s", -2147024809, "CRpcUtils::MIDL_str_dup");
LABEL_242:
        _DbgPrintMessage(8, "CRpcUtils::MIDL_str_dup(pszFarmName) failed: 0x%x in %s", v58, "RpcGetAllSessionsEx");
        goto LABEL_219;
      }
      v51 = 2 * (257 - v49);
      v52 = LocalAlloc(0x40u, v51);
      *((_QWORD *)v24 + 7) = v52;
      if ( !v52 )
      {
        v15 = -2147024882;
        v58 = -2147024882;
        goto LABEL_242;
      }
      v53 = v51 >> 1;
      if ( v53 )
      {
        if ( v53 > 0x7FFFFFFF )
        {
          v15 = -2147024809;
          *v52 = 0;
        }
        else
        {
          v54 = 2147483646;
          v55 = &dword_1800A8ADC;
          do
          {
            if ( !v54 )
              break;
            v56 = *(_WORD *)v55;
            if ( !*(_WORD *)v55 )
              break;
            v55 = (int *)((char *)v55 + 2);
            *v52++ = v56;
            --v54;
            --v53;
          }
          while ( v53 );
          v57 = v52 - 1;
          if ( v53 )
            v57 = v52;
          *v57 = 0;
          v15 = -2147024774;
          if ( v53 )
            v15 = 0;
        }
      }
      else
      {
        v15 = -2147024809;
      }
      v58 = v15;
      if ( v15 < 0 )
        goto LABEL_242;
    }
    v48 = v127;
    v127 = 0;
    if ( v48 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
    v12 = (_DWORD)v121 + 1;
    v20 = v117;
  }
  v26 = 33;
  v27 = v143;
  do
  {
    if ( !*v27 )
      break;
    ++v27;
    --v26;
  }
  while ( v26 );
  v15 = -2147024809;
  if ( !v26 )
  {
LABEL_220:
    v35 = -2147024809;
    _DbgPrintMessage(8, "StringCbLength failed: 0x%x in %s", -2147024809, "CRpcUtils::MIDL_str_dup");
    goto LABEL_221;
  }
  v28 = 2 * (34 - v26);
  v29 = LocalAlloc(0x40u, v28);
  *((_QWORD *)v24 + 3) = v29;
  if ( !v29 )
  {
LABEL_307:
    v15 = -2147024882;
    v35 = -2147024882;
    goto LABEL_221;
  }
  v30 = v28 >> 1;
  if ( v30 )
  {
    if ( v30 > 0x7FFFFFFF )
    {
      v15 = -2147024809;
      *v29 = 0;
    }
    else
    {
      v31 = 2147483646;
      v32 = v143;
      do
      {
        if ( !v31 )
          break;
        v33 = *v32;
        if ( !*v32 )
          break;
        ++v32;
        *v29++ = v33;
        --v31;
        --v30;
      }
      while ( v30 );
      v34 = v29 - 1;
      if ( v30 )
        v34 = v29;
      *v34 = 0;
      v15 = -2147024774;
      if ( v30 )
        v15 = 0;
    }
  }
  else
  {
    v15 = -2147024809;
  }
  v35 = v15;
  if ( v15 >= 0 )
    goto LABEL_57;
LABEL_221:
  _DbgPrintMessage(8, "CRpcUtils::MIDL_str_dup(SessionName) failed: 0x%x in %s", v35, "RpcGetAllSessionsEx");
LABEL_219:
  _DbgPrintMessage(8, "RpcGetAllSessionsEx FAILED with error 0x%x", v15);
LABEL_153:
  if ( pv )
    CoTaskMemFree(pv);
  if ( v126 )
    CoTaskMemFree(v126);
  if ( v7 )
    MIDL_free_EXECENVDATAEX(v7, v8);
  v132 = &CRpcCallTrace::`vftable';
  if ( v139 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "%s with Trace ID 0x%x Completed", v137, v134[0]);
  v132 = &CTraceBase::`vftable';
  if ( CTraceBase::g_bEnabled && !v136 && CTraceBase::g_TLSIndex != -1 )
  {
    if ( TlsSetValue(CTraceBase::g_TLSIndex, 0) )
    {
      if ( TlsSetValue(CTraceBase::g_CreatorFunctionTLSIndex, 0) )
        goto LABEL_161;
    }
    else
    {
      GetLastError();
    }
    GetLastError();
  }
LABEL_161:
  v135 = 0;
  if ( v122 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v122 + 16LL))(v122);
  if ( v21 )
    RpcRevertToSelf();
  if ( v128 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v128 + 16LL))(v128);
  if ( v129 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v129 + 16LL))(v129);
  if ( v6 )
    (*(void (__fastcall **)(struct ISessionManagerInternal *))(*(_QWORD *)v6 + 16LL))(v6);
  if ( v127 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v127 + 16LL))(v127);
  if ( v119 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v119 + 16LL))(v119);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18001b9d0  mov     [rsp-8+arg_0], rbx
0x18001b9d5  push    rbp
0x18001b9d6  push    rsi
0x18001b9d7  push    rdi
0x18001b9d8  push    r12
0x18001b9da  push    r13
0x18001b9dc  push    r14
0x18001b9de  push    r15
0x18001b9e0  lea     rbp, [rsp-360h]
0x18001b9e8  sub     rsp, 460h
0x18001b9ef  mov     rax, cs:__security_cookie
0x18001b9f6  xor     rax, rsp
0x18001b9f9  mov     [rbp+390h+var_40], rax
0x18001ba00  mov     r12, r9
0x18001ba03  mov     [rbp+390h+var_3F8], r9
0x18001ba07  mov     r15, r8
0x18001ba0a  mov     [rbp+390h+var_400], r8
0x18001ba0e  mov     [rsp+490h+var_448], edx
0x18001ba12  xor     edi, edi
0x18001ba14  mov     [rsp+490h+var_450], rdi
0x18001ba19  mov     [rsp+490h+var_418], rdi
0x18001ba1e  mov     ebx, edi
0x18001ba20  mov     [rbp+390h+var_408], rdi
0x18001ba24  mov     [rbp+390h+var_410], rdi
0x18001ba28  mov     r14d, edi
0x18001ba2b  mov     r13d, edi
0x18001ba2e  mov     [rsp+490h+var_438], rdi
0x18001ba33  mov     [rsp+490h+pv], rdi
0x18001ba38  mov     [rsp+490h+var_420], rdi
0x18001ba3d  lea     rax, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x18001ba44  mov     [rbp+390h+var_3F0], rax
0x18001ba48  mov     [rbp+390h+var_3D4], 1
0x18001ba4f  mov     [rbp+390h+var_3D0], rdi
0x18001ba53  lea     rsi, aRpcgetallsessi_0; "RpcGetAllSessionsEx"
0x18001ba5a  cmp     cs:?g_bEnabled@CTraceBase@@0HA, edi; int CTraceBase::g_bEnabled
0x18001ba60  jnz     loc_18001C9F3
0x18001ba66  lea     rcx, [rbp+390h+pguid]; pguid
0x18001ba6a  call    cs:__imp_CoCreateGuid
0x18001ba71  nop     dword ptr [rax+rax+00h]
0x18001ba76  mov     eax, 1
0x18001ba7b  lock xadd cs:?g_NextShortActivityID@CTraceBase@@0KA, eax; ulong CTraceBase::g_NextShortActivityID
0x18001ba83  inc     eax
0x18001ba85  mov     [rbp+390h+var_3D8], eax
0x18001ba88  mov     [rbp+390h+var_3C8], edi
0x18001ba8b  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x18001ba92  mov     [rbp+390h+var_3F0], rax
0x18001ba96  mov     [rbp+390h+var_3C0], rsi
0x18001ba9a  mov     qword ptr [rbp+390h+Pid], 0FFFFFFFFFFFFFFFFh
0x18001baa2  mov     [rbp+390h+var_3B0], edi
0x18001baa5  xor     edx, edx; Val
0x18001baa7  mov     r8d, 208h; Size
0x18001baad  lea     rcx, [rbp+390h+var_3AC]; void *
0x18001bab1  call    memset_0
0x18001bab6  cmp     [rbp+390h+var_3B0], ebx
0x18001bab9  jnz     loc_18001C8B9
0x18001babf  mov     esi, edi
0x18001bac1  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18001bac8  jnz     loc_18001CAC2
0x18001bace  mov     qword ptr [rbp+390h+Pid], 0FFFFFFFFFFFFFFFFh
0x18001bad6  lea     rdx, [rbp+390h+Pid+4]; Pid
0x18001bada  xor     ecx, ecx; Binding
0x18001badc  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18001bae3  nop     dword ptr [rax+rax+00h]
0x18001bae8  mov     edi, eax
0x18001baea  test    eax, eax
0x18001baec  jg      loc_18001C648
0x18001baf2  test    edi, edi
0x18001baf4  js      short loc_18001BB11
0x18001baf6  lea     rdx, [rbp+390h+Pid]; pSessionId
0x18001bafa  mov     ecx, [rbp+390h+Pid+4]; dwProcessId
0x18001bafd  call    cs:__imp_ProcessIdToSessionId
0x18001bb04  nop     dword ptr [rax+rax+00h]
0x18001bb09  test    esi, esi
0x18001bb0b  jnz     loc_18001CACC
0x18001bb11  cmp     [rbp+390h+var_3B0], ebx
0x18001bb14  jnz     loc_18001C917
0x18001bb1a  test    r15, r15
0x18001bb1d  jz      loc_18001C6F6
0x18001bb23  test    r12, r12
0x18001bb26  jz      loc_18001C6F6
0x18001bb2c  xor     esi, esi
0x18001bb2e  mov     [r15], rsi
0x18001bb31  mov     [r12], esi
0x18001bb35  cmp     [rsp+490h+var_448], 1
0x18001bb3a  ja      loc_18001CB6A
0x18001bb40  mov     [rsp+490h+TokenHandle], rsi
0x18001bb45  call    cs:__imp_GetCurrentThread
0x18001bb4c  nop     dword ptr [rax+rax+00h]
0x18001bb51  mov     rcx, rax; ThreadHandle
0x18001bb54  lea     r9, [rsp+490h+TokenHandle]; TokenHandle
0x18001bb59  mov     edx, 0Eh; DesiredAccess
0x18001bb5e  mov     r8d, 1; OpenAsSelf
0x18001bb64  call    cs:__imp_OpenThreadToken
0x18001bb6b  nop     dword ptr [rax+rax+00h]
0x18001bb70  test    eax, eax
0x18001bb72  jz      loc_18001C2EC
0x18001bb78  mov     rcx, [rsp+490h+TokenHandle]; hObject
0x18001bb7d  test    rcx, rcx
0x18001bb80  jz      short loc_18001BB8E
0x18001bb82  call    cs:__imp_CloseHandle
0x18001bb89  nop     dword ptr [rax+rax+00h]
0x18001bb8e  xor     ecx, ecx; BindingHandle
0x18001bb90  call    cs:__imp_RpcImpersonateClient
0x18001bb97  nop     dword ptr [rax+rax+00h]
0x18001bb9c  mov     edi, eax
0x18001bb9e  test    eax, eax
0x18001bba0  jg      loc_18001C656
0x18001bba6  test    edi, edi
0x18001bba8  js      loc_18001CB77
0x18001bbae  mov     r13d, cs:?TotalSessions@CTSPerfProvider@@0JC; long volatile CTSPerfProvider::TotalSessions
0x18001bbb5  test    r13d, r13d
0x18001bbb8  jz      loc_18001C43C
0x18001bbbe  mov     eax, r13d
0x18001bbc1  shl     eax, 6
0x18001bbc4  mov     edi, eax
0x18001bbc6  mov     edx, eax; uBytes
0x18001bbc8  mov     ecx, 40h ; '@'; uFlags
0x18001bbcd  call    cs:__imp_LocalAlloc
0x18001bbd4  nop     dword ptr [rax+rax+00h]
0x18001bbd9  mov     r14, rax
0x18001bbdc  mov     [rsp+490h+TokenHandle], rax
0x18001bbe1  test    rax, rax
0x18001bbe4  jz      loc_18001CBB5
0x18001bbea  mov     r8d, edi; Size
0x18001bbed  xor     edx, edx; Val
0x18001bbef  mov     rcx, rax; void *
0x18001bbf2  call    memset_0
0x18001bbf7  mov     r13d, edi
0x18001bbfa  shr     r13d, 6
0x18001bbfe  mov     [rsp+490h+var_430], 80004001h
0x18001bc06  mov     rbx, cs:?pSMGlobalInstance@ISessionManagerInternal@@0PEAV1@EA; ISessionManagerInternal * ISessionManagerInternal::pSMGlobalInstance
0x18001bc0d  test    rbx, rbx
0x18001bc10  jz      loc_18001CBC2
0x18001bc16  mov     [rsp+490h+var_430], esi
0x18001bc1a  mov     rax, [rbx]
0x18001bc1d  mov     rcx, rbx
0x18001bc20  mov     rax, [rax+8]
0x18001bc24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc29  mov     rax, [rbx]
0x18001bc2c  lea     rdx, [rbp+390h+var_408]
0x18001bc30  mov     rcx, rbx
0x18001bc33  mov     rax, [rax+18h]
0x18001bc37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc3c  mov     edi, eax
0x18001bc3e  test    eax, eax
0x18001bc40  js      loc_18001CC22
0x18001bc46  mov     rcx, [rbp+390h+var_408]
0x18001bc4a  mov     rax, [rcx]
0x18001bc4d  lea     rdx, [rbp+390h+var_410]
0x18001bc51  mov     rax, [rax+20h]
0x18001bc55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc5a  mov     edi, eax
0x18001bc5c  test    eax, eax
0x18001bc5e  js      loc_18001C700
0x18001bc64  call    RDVIsInWellKnownGroup
0x18001bc69  movzx   r15d, al
0x18001bc6d  mov     [rsp+490h+var_460], al
0x18001bc71  mov     rdx, [rbp+390h+var_410]
0x18001bc75  mov     rcx, [rdx]
0x18001bc78  mov     rax, [rcx+58h]
0x18001bc7c  mov     rcx, rdx
0x18001bc7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc84  mov     r12b, 1
0x18001bc87  mov     dword ptr [rsp+490h+var_440], esi
0x18001bc8b  cmp     esi, r13d
0x18001bc8e  jnb     loc_18001C30D
0x18001bc94  mov     rcx, [rsp+490h+var_450]
0x18001bc99  mov     [rsp+490h+var_450], 0
0x18001bca2  test    rcx, rcx
0x18001bca5  jz      short loc_18001BCB3
0x18001bca7  mov     rax, [rcx]
0x18001bcaa  mov     rax, [rax+10h]
0x18001bcae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bcb3  mov     rcx, [rbp+390h+var_410]
0x18001bcb7  mov     rax, [rcx]
0x18001bcba  lea     rdx, [rsp+490h+var_450]
0x18001bcbf  mov     rax, [rax+50h]
0x18001bcc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bcc8  mov     edi, eax
0x18001bcca  cmp     eax, 80070103h
0x18001bccf  jz      loc_18001C30D
0x18001bcd5  test    eax, eax
0x18001bcd7  js      loc_18001CDCF
0x18001bcdd  test    r15b, r15b
0x18001bce0  jz      loc_18001C04C
0x18001bce6  mov     r15d, esi
0x18001bce9  shl     r15, 6
0x18001bced  add     r15, r14
0x18001bcf0  mov     eax, [rsp+490h+var_448]
0x18001bcf4  mov     [r15], eax
0x18001bcf7  mov     rcx, [rsp+490h+var_450]
0x18001bcfc  mov     rax, [rcx]
0x18001bcff  lea     rdx, [r15+8]
0x18001bd03  mov     rax, [rax+50h]
0x18001bd07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bd0c  mov     eax, [r15+8]
0x18001bd10  mov     [r15+10h], eax
0x18001bd14  mov     [rsp+490h+var_42C], 0
0x18001bd1c  mov     rcx, [rsp+490h+var_450]
0x18001bd21  mov     rax, [rcx]
0x18001bd24  lea     rdx, [rsp+490h+var_42C]
0x18001bd29  mov     rax, [rax+58h]
0x18001bd2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bd32  movsxd  rax, [rsp+490h+var_42C]
0x18001bd37  cmp     eax, 1
0x18001bd3a  jnz     loc_18001C2FD
0x18001bd40  mov     eax, 9; jumptable 000000018001C638 case 0
0x18001bd45  mov     [r15+0Ch], eax
0x18001bd49  xor     eax, eax
0x18001bd4b  mov     [rbp+390h+var_90], ax
0x18001bd52  mov     rcx, [rsp+490h+var_450]
0x18001bd57  mov     rax, [rcx]
0x18001bd5a  lea     rdx, [rsp+490h+var_418]
0x18001bd5f  mov     rax, [rax+68h]
0x18001bd63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bd68  mov     rcx, [rsp+490h+var_418]
0x18001bd6d  test    rcx, rcx
0x18001bd70  jz      loc_18001BE58
0x18001bd76  mov     rax, [rcx]
0x18001bd79  lea     rdx, [rbp+390h+var_90]
0x18001bd80  mov     rax, [rax+68h]
0x18001bd84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bd89  test    eax, eax
0x18001bd8b  js      loc_18001BE58
0x18001bd91  mov     ecx, 21h ; '!'
0x18001bd96  lea     rax, [rbp+390h+var_90]
0x18001bd9d  cmp     word ptr [rax], 0
0x18001bda1  jz      short loc_18001BDAD
0x18001bda3  add     rax, 2
0x18001bda7  sub     rcx, 1
0x18001bdab  jnz     short loc_18001BD9D
0x18001bdad  mov     edi, 80070057h
0x18001bdb2  xor     eax, eax
0x18001bdb4  test    rcx, rcx
0x18001bdb7  cmovnz  edi, eax
0x18001bdba  jz      loc_18001C6BC
0x18001bdc0  mov     esi, 22h ; '"'
0x18001bdc5  sub     rsi, rcx
0x18001bdc8  add     rsi, rsi
0x18001bdcb  mov     rdx, rsi; uBytes
0x18001bdce  mov     ecx, 40h ; '@'; uFlags
0x18001bdd3  call    cs:__imp_LocalAlloc
0x18001bdda  nop     dword ptr [rax+rax+00h]
0x18001bddf  mov     r8, rax
0x18001bde2  mov     [r15+18h], rax
0x18001bde6  test    rax, rax
0x18001bde9  jz      loc_18001CD67
0x18001bdef  shr     rsi, 1
0x18001bdf2  jz      loc_18001CC74
0x18001bdf8  cmp     rsi, 7FFFFFFFh
0x18001bdff  ja      loc_18001CC6D
0x18001be05  mov     ecx, 7FFFFFFEh
0x18001be0a  lea     rdx, [rbp+390h+var_90]
0x18001be11  test    rcx, rcx
0x18001be14  jz      short loc_18001BE33
0x18001be16  movzx   eax, word ptr [rdx]
0x18001be19  test    ax, ax
0x18001be1c  jz      short loc_18001BE33
0x18001be1e  add     rdx, 2
0x18001be22  mov     [r8], ax
0x18001be26  add     r8, 2
0x18001be2a  dec     rcx
0x18001be2d  sub     rsi, 1
0x18001be31  jnz     short loc_18001BE11
0x18001be33  lea     rcx, [r8-2]
0x18001be37  test    rsi, rsi
0x18001be3a  cmovnz  rcx, r8
0x18001be3e  xor     eax, eax
0x18001be40  mov     [rcx], ax
0x18001be43  mov     edi, 8007007Ah
0x18001be48  test    rsi, rsi
0x18001be4b  cmovnz  edi, eax
0x18001be4e  mov     esi, edi
0x18001be50  test    edi, edi
0x18001be52  js      loc_18001C6D9
0x18001be58  mov     rcx, [rsp+490h+var_438]
0x18001be5d  mov     [rsp+490h+var_438], 0
0x18001be66  test    rcx, rcx
0x18001be69  jnz     loc_18001C720
0x18001be6f  mov     rcx, [rsp+490h+var_450]
0x18001be74  mov     rax, [rcx]
0x18001be77  lea     rdx, [rsp+490h+var_438]
0x18001be7c  mov     rax, [rax+60h]
0x18001be80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be85  test    eax, eax
0x18001be87  js      loc_18001BFE9
0x18001be8d  mov     rcx, [rsp+490h+var_438]
0x18001be92  mov     rax, [rcx]
0x18001be95  lea     rdx, [rsp+490h+pv]
0x18001be9a  mov     rax, [rax+28h]
0x18001be9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bea3  test    eax, eax
0x18001bea5  jns     loc_18001C20D
0x18001beab  mov     rcx, [rsp+490h+var_438]
0x18001beb0  mov     rax, [rcx]
0x18001beb3  lea     rdx, [rsp+490h+var_420]
0x18001beb8  mov     rax, [rax+30h]
0x18001bebc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bec1  test    eax, eax
0x18001bec3  js      loc_18001BFA6
  ... truncated ...
```
