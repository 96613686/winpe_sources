# RpcGetTerminalName

- ea: `0x180015090`
- end: `0x18001573e`
- name: `RpcGetTerminalName`
- size: `1710`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800145c0`

## callees

- `0x1800074c0`
- `0x18000b190`
- `0x18000c700`
- `0x180015090`
- `0x18001aa50`
- `0x1800271d0`
- `0x18004b460`
- `0x18004bf44`
- `0x180097010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180015661`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180015661`
- `ntdll!NtQueryInformationProcess` at `0x180015645`
- `ntdll!NtQueryInformationProcess` at `0x180015645`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800153f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015732`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800153f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015732`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800153eb`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180015724`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800153eb`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180015724`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180015193`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180015193`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001568b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001568b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015368`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015368`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180015100`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180015100`
- `RPCRT4!RpcImpersonateClient` at `0x1800152b8`
- `RPCRT4!RpcImpersonateClient` at `0x1800152b8`
- `RPCRT4!RpcRevertToSelf` at `0x1800152ee`
- `RPCRT4!RpcRevertToSelf` at `0x1800152ee`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180015176`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180015176`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001561d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001561d`

## string_xrefs

- `0x180015512`: `AccessCheckEx failed: 0x%X`
- `0x1800156ac`: `Cannot impersonate client: %d`
- `0x1800151f4`: `CheckAccessToSession(WINSTATION_QUERY) failed: 0x%x in %s`
- `0x1800151cd`: `CheckAccessToSession`
- `0x18001549c`: `%s with Trace ID 0x%x Completed`
- `0x180015580`: `TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC`
- `0x1800154d6`: `RPC Caller: PID %d, SessID %d, Process Name: <%S>`

## pseudocode

```c
__int64 __fastcall RpcGetTerminalName(__int64 a1, _QWORD *a2)
{
  __int64 v4; // rbx
  unsigned int v5; // r14d
  RPC_STATUS v6; // eax
  int v7; // edi
  int v8; // edi
  _WORD *v9; // rcx
  RPC_STATUS v11; // eax
  int v12; // eax
  RPC_STATUS v13; // eax
  int v14; // eax
  int v15; // eax
  __int64 v16; // rax
  unsigned __int64 v17; // rsi
  _WORD *v18; // rax
  _WORD *v19; // r8
  __int64 v20; // rcx
  __int16 *v21; // rdx
  __int16 v22; // ax
  const char *v23; // r8
  HANDLE v24; // rax
  void *v25; // r15
  NTSTATUS InformationProcess; // eax
  wchar_t *v27; // rax
  wchar_t *v28; // rax
  __int64 v29; // [rsp+30h] [rbp-D0h] BYREF
  struct CTraceBase *v30; // [rsp+38h] [rbp-C8h] BYREF
  void **v31; // [rsp+40h] [rbp-C0h] BYREF
  GUID pguid; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v33[2]; // [rsp+58h] [rbp-A8h] BYREF
  struct CTraceBase *v34; // [rsp+60h] [rbp-A0h] BYREF
  int v35; // [rsp+68h] [rbp-98h]
  const char *v36; // [rsp+70h] [rbp-90h]
  unsigned int Pid[2]; // [rsp+78h] [rbp-88h] BYREF
  int v38; // [rsp+80h] [rbp-80h]
  unsigned __int16 v39[262]; // [rsp+84h] [rbp-7Ch] BYREF
  _BYTE ProcessInformation[8]; // [rsp+290h] [rbp+190h] BYREF
  wchar_t *Str; // [rsp+298h] [rbp+198h]
  _WORD v42[40]; // [rsp+3A0h] [rbp+2A0h] BYREF

  v4 = 0;
  v29 = 0;
  v31 = &CTraceBase::`vftable';
  v33[1] = 1;
  v34 = 0;
  if ( CTraceBase::g_bEnabled )
  {
    if ( (g_DebugTraceComponent & 1) != 0 )
      _DbgPrintMessage(2, "Adding trace %p, %d, %s", &v31, 1, "RpcGetTerminalName");
    v30 = 0;
    if ( (int)CTraceBase::GetThreadCurrentOperationTrace(&v30) >= 0 && v30 && (g_DebugTraceComponent & 1) != 0 )
      _DbgPrintMessage(
        2,
        "TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC",
        1);
    CTraceBase::ResetThreadCurrentOperationTrace(0, 0);
    if ( (int)CTraceBase::GetThreadCurrentOperationTrace(&v34) >= 0 && v34 )
    {
      (*(void (__fastcall **)(struct CTraceBase *, GUID *))(*(_QWORD *)v34 + 32LL))(v34, &pguid);
      v33[0] = (*(__int64 (__fastcall **)(struct CTraceBase *))(*(_QWORD *)v34 + 24LL))(v34);
      v35 = 1;
      goto LABEL_4;
    }
    CTraceBase::ResetThreadCurrentOperationTrace((struct CTraceBase *)&v31, "RpcGetTerminalName");
    CTraceBase::GenerateTraceID(&pguid, v33);
  }
  else
  {
    CoCreateGuid(&pguid);
    v33[0] = _InterlockedIncrement((volatile signed __int32 *)&CTraceBase::g_NextShortActivityID);
  }
  v35 = 0;
LABEL_4:
  v31 = &CRpcCallTrace::`vftable';
  v36 = "RpcGetTerminalName";
  *(_QWORD *)Pid = -1;
  v38 = 0;
  memset_0(v39, 0, 0x208u);
  if ( v38 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "TRACE RPC %s with Trace ID 0x%x", v36, v33[0]);
  v5 = 0;
  if ( (g_DebugTraceComponent & 1) != 0 )
    v5 = 260;
  *(_QWORD *)Pid = -1;
  v6 = I_RpcBindingInqLocalClientPID(0, &Pid[1]);
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  if ( v7 >= 0 )
  {
    ProcessIdToSessionId(Pid[1], Pid);
    if ( v5 )
    {
      v24 = OpenProcess(0x400u, 0, Pid[1]);
      v25 = v24;
      if ( v24 )
      {
        InformationProcess = NtQueryInformationProcess(v24, ProcessImageFileName, ProcessInformation, 0x110u, 0);
        v7 = InformationProcess | 0x10000000;
        if ( InformationProcess >= 0 )
        {
          v27 = wcsrchr(Str, 0x5Cu);
          if ( v27 )
            v28 = v27 + 1;
          else
            v28 = Str;
          StringCchCopyW(v39, v5, v28);
        }
        CloseHandle(v25);
      }
    }
  }
  if ( v38 )
  {
    if ( v7 < 0 )
    {
      if ( (g_DebugTraceComponent & 1) != 0 )
        _DbgPrintMessage(2, "RPC Caller: Unknown");
    }
    else if ( (g_DebugTraceComponent & 1) != 0 )
    {
      _DbgPrintMessage(2, "RPC Caller: PID %d, SessID %d, Process Name: <%S>", Pid[1], Pid[0], v39);
    }
  }
  if ( !a1 )
  {
    v23 = "hSession";
LABEL_50:
    _DbgPrintMessage(8, "Missing paramter %s in %s", v23, "RpcGetTerminalName");
    v8 = -2147024809;
    goto LABEL_21;
  }
  if ( !a2 )
  {
    v23 = "pszTerminalName";
    goto LABEL_50;
  }
  v4 = *(_QWORD *)(a1 + 1592);
  if ( !v4 )
  {
    _DbgPrintMessage(8, "Missing paramter %s in %s", "pSession", "CheckAccessToSession");
    v8 = -2147024809;
    goto LABEL_16;
  }
  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v4 + 8LL))(*(_QWORD *)(a1 + 1592));
  v11 = RpcImpersonateClient(0);
  if ( v11 )
  {
    _DbgPrintMessage(8, "Cannot impersonate client: %d", v11);
    v8 = -2147024891;
    goto LABEL_16;
  }
  v12 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v4 + 144LL))(v4, 1, 0);
  v8 = v12;
  if ( v12 < 0 )
  {
    _DbgPrintMessage(8, "AccessCheckEx failed: 0x%X", v12);
    v8 = -2147024891;
  }
  v13 = RpcRevertToSelf();
  if ( v13 )
  {
    _DbgPrintMessage(8, "RpcRevertToSelf failed: %d", v13);
    v8 = -2147024891;
    goto LABEL_16;
  }
  if ( v8 < 0 )
  {
LABEL_16:
    _DbgPrintMessage(
      8,
      "CheckAccessToSession(WINSTATION_QUERY) failed: 0x%x in %s",
      (unsigned int)v8,
      "RpcGetTerminalName");
    goto LABEL_21;
  }
  v14 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v4 + 104LL))(v4, &v29);
  if ( v14 < 0 )
  {
    _DbgPrintMessage(4, "RpcGetTerminalName, no terminal: 0x%x, returning success", v14);
    v42[0] = 0;
  }
  else
  {
    v15 = (*(__int64 (__fastcall **)(__int64, _WORD *))(*(_QWORD *)v29 + 104LL))(v29, v42);
    v8 = v15;
    if ( v15 < 0 )
    {
      _DbgPrintMessage(8, "Terminal->GetTerminalName failed: 0x%x in %s", (unsigned int)v15, "RpcGetTerminalName");
      goto LABEL_21;
    }
  }
  v16 = -1;
  do
    ++v16;
  while ( v42[v16] );
  v17 = v16 + 1;
  v18 = LocalAlloc(0x40u, 2 * (v16 + 1));
  v19 = v18;
  *a2 = v18;
  if ( v18 )
  {
    if ( v17 )
    {
      if ( v17 > 0x7FFFFFFF )
      {
        v8 = -2147024809;
        *v18 = 0;
      }
      else
      {
        v20 = 2147483646;
        v21 = v42;
        do
        {
          if ( !v20 )
            break;
          v22 = *v21;
          if ( !*v21 )
            break;
          ++v21;
          *v19++ = v22;
          --v20;
          --v17;
        }
        while ( v17 );
        v9 = v19 - 1;
        if ( v17 )
          v9 = v19;
        *v9 = 0;
        v8 = -2147024774;
        if ( v17 )
          v8 = 0;
      }
    }
    else
    {
      v8 = -2147024809;
    }
  }
  else
  {
    v8 = -2147024882;
  }
LABEL_21:
  v31 = &CRpcCallTrace::`vftable';
  if ( v38 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "%s with Trace ID 0x%x Completed", v36, v33[0]);
  v31 = &CTraceBase::`vftable';
  if ( CTraceBase::g_bEnabled && !v35 && CTraceBase::g_TLSIndex != -1 )
  {
    if ( TlsSetValue(CTraceBase::g_TLSIndex, 0) )
    {
      if ( TlsSetValue(CTraceBase::g_CreatorFunctionTLSIndex, 0) )
        goto LABEL_23;
    }
    else
    {
      GetLastError();
    }
    GetLastError();
  }
LABEL_23:
  v34 = 0;
  if ( v29 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180015090  push    rbp
0x180015092  push    rbx
0x180015093  push    rsi
0x180015094  push    rdi
0x180015095  push    r12
0x180015097  push    r13
0x180015099  push    r14
0x18001509b  push    r15
0x18001509d  lea     rbp, [rsp-308h]
0x1800150a5  sub     rsp, 408h
0x1800150ac  mov     rax, cs:__security_cookie
0x1800150b3  xor     rax, rsp
0x1800150b6  mov     [rbp+340h+var_50], rax
0x1800150bd  mov     r12, rdx
0x1800150c0  mov     rsi, rcx
0x1800150c3  xor     r13d, r13d
0x1800150c6  mov     ebx, r13d
0x1800150c9  mov     [rsp+440h+var_410], r13
0x1800150ce  lea     rax, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x1800150d5  mov     [rsp+440h+var_400], rax
0x1800150da  mov     [rsp+440h+var_3E4], 1
0x1800150e2  mov     [rsp+440h+var_3E0], r13
0x1800150e7  lea     r15, aRpcgetterminal_0; "RpcGetTerminalName"
0x1800150ee  cmp     cs:?g_bEnabled@CTraceBase@@0HA, r13d; int CTraceBase::g_bEnabled
0x1800150f5  jnz     loc_18001552D
0x1800150fb  lea     rcx, [rsp+440h+pguid]; pguid
0x180015100  call    cs:__imp_CoCreateGuid
0x180015106  mov     eax, 1
0x18001510b  lock xadd cs:?g_NextShortActivityID@CTraceBase@@0KA, eax; ulong CTraceBase::g_NextShortActivityID
0x180015113  inc     eax
0x180015115  mov     [rsp+440h+var_3E8], eax
0x180015119  mov     [rsp+440h+var_3D8], r13d
0x18001511e  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x180015125  mov     [rsp+440h+var_400], rax
0x18001512a  mov     [rsp+440h+var_3D0], r15
0x18001512f  mov     qword ptr [rsp+440h+Pid], 0FFFFFFFFFFFFFFFFh
0x180015138  mov     [rbp+340h+var_3C0], r13d
0x18001513c  xor     edx, edx; Val
0x18001513e  mov     r8d, 208h; Size
0x180015144  lea     rcx, [rbp+340h+var_3BC]; void *
0x180015148  call    memset_0
0x18001514d  cmp     [rbp+340h+var_3C0], ebx
0x180015150  jnz     loc_180015458
0x180015156  mov     r14d, r13d
0x180015159  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x180015160  jnz     loc_180015606
0x180015166  mov     qword ptr [rsp+440h+Pid], 0FFFFFFFFFFFFFFFFh
0x18001516f  lea     rdx, [rsp+440h+Pid+4]; Pid
0x180015174  xor     ecx, ecx; Binding
0x180015176  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18001517c  mov     edi, eax
0x18001517e  test    eax, eax
0x180015180  jg      loc_180015404
0x180015186  test    edi, edi
0x180015188  js      short loc_1800151A2
0x18001518a  lea     rdx, [rsp+440h+Pid]; pSessionId
0x18001518f  mov     ecx, [rsp+440h+Pid+4]; dwProcessId
0x180015193  call    cs:__imp_ProcessIdToSessionId
0x180015199  test    r14d, r14d
0x18001519c  jnz     loc_180015611
0x1800151a2  cmp     [rbp+340h+var_3C0], ebx
0x1800151a5  jnz     loc_1800154B2
0x1800151ab  test    rsi, rsi
0x1800151ae  jz      loc_180015412
0x1800151b4  test    r12, r12
0x1800151b7  jz      loc_18001569D
0x1800151bd  mov     rbx, [rsi+638h]
0x1800151c4  test    rbx, rbx
0x1800151c7  jnz     loc_1800152A7
0x1800151cd  lea     r9, aCheckaccesstos_3; "CheckAccessToSession"
0x1800151d4  lea     r8, aPsession; "pSession"
0x1800151db  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x1800151e2  mov     ecx, 8; int
0x1800151e7  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800151ec  mov     edi, 80070057h
0x1800151f1  mov     r8d, edi
0x1800151f4  lea     rdx, aCheckaccesstos_5; "CheckAccessToSession(WINSTATION_QUERY) "...
0x1800151fb  mov     r9, r15
0x1800151fe  mov     ecx, 8; int
0x180015203  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180015208  jmp     short loc_180015222
0x18001520a  lea     rcx, [r8-2]
0x18001520e  test    rsi, rsi
0x180015211  cmovnz  rcx, r8
0x180015215  mov     [rcx], r13w
0x180015219  mov     edi, 8007007Ah
0x18001521e  cmovnz  edi, r13d
0x180015222  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x180015229  mov     [rsp+440h+var_400], rax
0x18001522e  cmp     [rbp+340h+var_3C0], 0
0x180015232  jnz     loc_180015485
0x180015238  lea     rax, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x18001523f  mov     [rsp+440h+var_400], rax
0x180015244  cmp     cs:?g_bEnabled@CTraceBase@@0HA, 0; int CTraceBase::g_bEnabled
0x18001524b  jnz     loc_1800153CF
0x180015251  mov     [rsp+440h+var_3E0], r13
0x180015256  mov     rcx, [rsp+440h+var_410]
0x18001525b  test    rcx, rcx
0x18001525e  jz      short loc_18001526D
0x180015260  mov     rax, [rcx]
0x180015263  mov     rax, [rax+10h]
0x180015267  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001526c  nop
0x18001526d  test    rbx, rbx
0x180015270  jz      short loc_180015282
0x180015272  mov     rax, [rbx]
0x180015275  mov     rcx, rbx
0x180015278  mov     rax, [rax+10h]
0x18001527c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015281  nop
0x180015282  mov     eax, edi
0x180015284  mov     rcx, [rbp+340h+var_50]
0x18001528b  xor     rcx, rsp; StackCookie
0x18001528e  call    __security_check_cookie
0x180015293  add     rsp, 408h
0x18001529a  pop     r15
0x18001529c  pop     r14
0x18001529e  pop     r13
0x1800152a0  pop     r12
0x1800152a2  pop     rdi
0x1800152a3  pop     rsi
0x1800152a4  pop     rbx
0x1800152a5  pop     rbp
0x1800152a6  retn
0x1800152a7  mov     rax, [rbx]
0x1800152aa  mov     rcx, rbx
0x1800152ad  mov     rax, [rax+8]
0x1800152b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800152b6  xor     ecx, ecx; BindingHandle
0x1800152b8  call    cs:__imp_RpcImpersonateClient
0x1800152be  test    eax, eax
0x1800152c0  jnz     loc_1800156A9
0x1800152c6  mov     rax, [rbx]
0x1800152c9  mov     r9d, 1
0x1800152cf  xor     r8d, r8d
0x1800152d2  mov     edx, r9d
0x1800152d5  mov     rcx, rbx
0x1800152d8  mov     rax, [rax+90h]
0x1800152df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800152e4  mov     edi, eax
0x1800152e6  test    eax, eax
0x1800152e8  js      loc_18001550F
0x1800152ee  call    cs:__imp_RpcRevertToSelf
0x1800152f4  test    eax, eax
0x1800152f6  jnz     loc_1800156C7
0x1800152fc  test    edi, edi
0x1800152fe  js      loc_1800151F1
0x180015304  mov     rax, [rbx]
0x180015307  lea     rdx, [rsp+440h+var_410]
0x18001530c  mov     rcx, rbx
0x18001530f  mov     rax, [rax+68h]
0x180015313  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015318  test    eax, eax
0x18001531a  js      loc_180015437
0x180015320  mov     rcx, [rsp+440h+var_410]
0x180015325  mov     rax, [rcx]
0x180015328  lea     rdx, [rbp+340h+var_A0]
0x18001532f  mov     rax, [rax+68h]
0x180015333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015338  mov     edi, eax
0x18001533a  test    eax, eax
0x18001533c  js      loc_1800156E5
0x180015342  lea     rcx, [rbp+340h+var_A0]
0x180015349  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180015350  lea     rax, [rax+1]
0x180015354  cmp     [rcx+rax*2], r13w
0x180015359  jnz     short loc_180015350
0x18001535b  lea     rsi, [rax+1]
0x18001535f  lea     rdx, [rsi+rsi]; uBytes
0x180015363  mov     ecx, 40h ; '@'; uFlags
0x180015368  call    cs:__imp_LocalAlloc
0x18001536e  mov     r8, rax
0x180015371  mov     [r12], rax
0x180015375  test    rax, rax
0x180015378  jz      loc_1800156F4
0x18001537e  test    rsi, rsi
0x180015381  jz      loc_180015705
0x180015387  cmp     rsi, 7FFFFFFFh
0x18001538e  ja      loc_1800156FE
0x180015394  mov     ecx, 7FFFFFFEh
0x180015399  lea     rdx, [rbp+340h+var_A0]
0x1800153a0  test    rcx, rcx
0x1800153a3  jz      loc_18001520A
0x1800153a9  movzx   eax, word ptr [rdx]
0x1800153ac  test    ax, ax
0x1800153af  jz      loc_18001520A
0x1800153b5  add     rdx, 2
0x1800153b9  mov     [r8], ax
0x1800153bd  add     r8, 2
0x1800153c1  dec     rcx
0x1800153c4  sub     rsi, 1
0x1800153c8  jnz     short loc_1800153A0
0x1800153ca  jmp     loc_18001520A
0x1800153cf  cmp     [rsp+440h+var_3D8], 0
0x1800153d4  jnz     loc_180015251
0x1800153da  mov     ecx, cs:?g_TLSIndex@CTraceBase@@0KA; dwTlsIndex
0x1800153e0  cmp     ecx, 0FFFFFFFFh
0x1800153e3  jz      loc_180015251
0x1800153e9  xor     edx, edx; lpTlsValue
0x1800153eb  call    cs:__imp_TlsSetValue
0x1800153f1  test    eax, eax
0x1800153f3  jnz     loc_18001571C
0x1800153f9  call    cs:__imp_GetLastError
0x1800153ff  jmp     loc_180015732
0x180015404  movzx   edi, ax
0x180015407  or      edi, 80070000h
0x18001540d  jmp     loc_180015186
0x180015412  lea     r8, aHsession; "hSession"
0x180015419  mov     r9, r15
0x18001541c  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x180015423  mov     ecx, 8; int
0x180015428  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001542d  mov     edi, 80070057h
0x180015432  jmp     loc_180015222
0x180015437  mov     r8d, eax
0x18001543a  lea     rdx, aRpcgetterminal_1; "RpcGetTerminalName, no terminal: 0x%x, "...
0x180015441  mov     ecx, 4; int
0x180015446  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001544b  mov     [rbp+340h+var_A0], r13w
0x180015453  jmp     loc_180015342
0x180015458  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18001545f  jz      loc_180015156
0x180015465  mov     r9d, [rsp+440h+var_3E8]
0x18001546a  mov     r8, [rsp+440h+var_3D0]
0x18001546f  lea     rdx, aTraceRpcSWithT; "TRACE RPC %s with Trace ID 0x%x"
0x180015476  mov     ecx, 2; int
0x18001547b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180015480  jmp     loc_180015156
0x180015485  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18001548c  jz      loc_180015238
0x180015492  mov     r9d, [rsp+440h+var_3E8]
0x180015497  mov     r8, [rsp+440h+var_3D0]
0x18001549c  lea     rdx, aSWithTraceId0x; "%s with Trace ID 0x%x Completed"
0x1800154a3  mov     ecx, 2; int
0x1800154a8  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800154ad  jmp     loc_180015238
0x1800154b2  test    edi, edi
0x1800154b4  js      short loc_1800154EC
0x1800154b6  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x1800154bd  jz      loc_1800151AB
0x1800154c3  lea     rax, [rbp+340h+var_3BC]
0x1800154c7  mov     [rsp+440h+ReturnLength], rax
0x1800154cc  mov     r9d, [rsp+440h+Pid]
0x1800154d1  mov     r8d, [rsp+440h+Pid+4]
0x1800154d6  lea     rdx, aRpcCallerPidDS; "RPC Caller: PID %d, SessID %d, Process "...
0x1800154dd  mov     ecx, 2; int
0x1800154e2  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800154e7  jmp     loc_1800151AB
0x1800154ec  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x1800154f3  jz      loc_1800151AB
0x1800154f9  lea     rdx, aRpcCallerUnkno; "RPC Caller: Unknown"
0x180015500  mov     ecx, 2; int
0x180015505  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001550a  jmp     loc_1800151AB
0x18001550f  mov     r8d, eax
0x180015512  lea     rdx, aAccesscheckexF; "AccessCheckEx failed: 0x%X"
0x180015519  mov     ecx, 8; int
0x18001551e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180015523  mov     edi, 80070005h
0x180015528  jmp     loc_1800152EE
0x18001552d  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x180015534  jz      short loc_180015557
0x180015536  mov     [rsp+440h+ReturnLength], r15
0x18001553b  mov     r9d, 1
0x180015541  lea     r8, [rsp+440h+var_400]
0x180015546  lea     rdx, aAddingTracePDS; "Adding trace %p, %d, %s"
0x18001554d  mov     ecx, 2; int
0x180015552  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180015557  mov     [rsp+440h+var_408], r13
0x18001555c  lea     rcx, [rsp+440h+var_408]; struct CTraceBase **
0x180015561  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x180015566  test    eax, eax
0x180015568  js      short loc_180015591
0x18001556a  cmp     [rsp+440h+var_408], rbx
0x18001556f  jz      short loc_180015591
0x180015571  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x180015578  jz      short loc_180015591
0x18001557a  mov     r8d, 1
0x180015580  lea     rdx, aTracecomponent; "TraceComponent %d: Warning TLS should b"...
0x180015587  mov     ecx, 2; int
0x18001558c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180015591  xor     edx, edx; char *
0x180015593  xor     ecx, ecx; lpTlsValue
0x180015595  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x18001559a  lea     rcx, [rsp+440h+var_3E0]; struct CTraceBase **
0x18001559f  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x1800155a4  test    eax, eax
0x1800155a6  js      short loc_1800155E5
0x1800155a8  mov     rcx, [rsp+440h+var_3E0]
0x1800155ad  test    rcx, rcx
0x1800155b0  jz      short loc_1800155E5
0x1800155b2  mov     rax, [rcx]
0x1800155b5  lea     rdx, [rsp+440h+pguid]
0x1800155ba  mov     rax, [rax+20h]
0x1800155be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155c3  mov     rcx, [rsp+440h+var_3E0]
0x1800155c8  mov     rax, [rcx]
0x1800155cb  mov     rax, [rax+18h]
0x1800155cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155d4  mov     [rsp+440h+var_3E8], eax
  ... truncated ...
```
