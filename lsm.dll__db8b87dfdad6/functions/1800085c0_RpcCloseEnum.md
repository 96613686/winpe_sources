# RpcCloseEnum

- ea: `0x1800085c0`
- end: `0x1800089dd`
- name: `RpcCloseEnum`
- size: `1053`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18005ba20`

## callees

- `0x1800074c0`
- `0x1800085c0`
- `0x18000b190`
- `0x18000c700`
- `0x18001aa50`
- `0x1800271d0`
- `0x18004b460`
- `0x18004bf44`
- `0x180097010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180008974`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180008974`
- `ntdll!NtQueryInformationProcess` at `0x180008958`
- `ntdll!NtQueryInformationProcess` at `0x180008958`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008758`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800089d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008758`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800089d1`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000874a`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800089c3`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000874a`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800089c3`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800086b5`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800086b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000899d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000899d`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180008626`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180008626`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180008698`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180008698`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180008930`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180008930`

## string_xrefs

- `0x1800087da`: `%s with Trace ID 0x%x Completed`
- `0x180008898`: `TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC`
- `0x180008814`: `RPC Caller: PID %d, SessID %d, Process Name: <%S>`

## pseudocode

```c
__int64 __fastcall RpcCloseEnum(_QWORD *a1)
{
  unsigned int v2; // esi
  RPC_STATUS v3; // eax
  int v4; // ebx
  unsigned int v5; // ebx
  const char *v7; // r8
  HANDLE v8; // rax
  void *v9; // r14
  NTSTATUS InformationProcess; // eax
  wchar_t *v11; // rax
  wchar_t *v12; // rax
  struct CTraceBase *v13; // [rsp+30h] [rbp-D0h] BYREF
  void **v14; // [rsp+40h] [rbp-C0h] BYREF
  GUID pguid; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v16[2]; // [rsp+58h] [rbp-A8h] BYREF
  struct CTraceBase *v17; // [rsp+60h] [rbp-A0h] BYREF
  int v18; // [rsp+68h] [rbp-98h]
  const char *v19; // [rsp+70h] [rbp-90h]
  unsigned int Pid[2]; // [rsp+78h] [rbp-88h] BYREF
  int v21; // [rsp+80h] [rbp-80h]
  unsigned __int16 v22[262]; // [rsp+84h] [rbp-7Ch] BYREF
  _BYTE ProcessInformation[8]; // [rsp+290h] [rbp+190h] BYREF
  wchar_t *Str; // [rsp+298h] [rbp+198h]

  v14 = &CTraceBase::`vftable';
  v16[1] = 1;
  v17 = 0;
  if ( CTraceBase::g_bEnabled )
  {
    if ( (g_DebugTraceComponent & 1) != 0 )
      _DbgPrintMessage(2, "Adding trace %p, %d, %s", &v14, 1, "RpcCloseEnum");
    v13 = 0;
    if ( (int)CTraceBase::GetThreadCurrentOperationTrace(&v13) >= 0 && v13 && (g_DebugTraceComponent & 1) != 0 )
      _DbgPrintMessage(
        2,
        "TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC",
        1);
    CTraceBase::ResetThreadCurrentOperationTrace(0, 0);
    if ( (int)CTraceBase::GetThreadCurrentOperationTrace(&v17) >= 0 && v17 )
    {
      (*(void (__fastcall **)(struct CTraceBase *, GUID *))(*(_QWORD *)v17 + 32LL))(v17, &pguid);
      v16[0] = (*(__int64 (__fastcall **)(struct CTraceBase *))(*(_QWORD *)v17 + 24LL))(v17);
      v18 = 1;
      goto LABEL_4;
    }
    CTraceBase::ResetThreadCurrentOperationTrace((struct CTraceBase *)&v14, "RpcCloseEnum");
    CTraceBase::GenerateTraceID(&pguid, v16);
  }
  else
  {
    CoCreateGuid(&pguid);
    v16[0] = _InterlockedIncrement((volatile signed __int32 *)&CTraceBase::g_NextShortActivityID);
  }
  v18 = 0;
LABEL_4:
  v14 = &CRpcCallTrace::`vftable';
  v19 = "RpcCloseEnum";
  *(_QWORD *)Pid = -1;
  v21 = 0;
  memset_0(v22, 0, 0x208u);
  if ( v21 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "TRACE RPC %s with Trace ID 0x%x", v19, v16[0]);
  v2 = 0;
  if ( (g_DebugTraceComponent & 1) != 0 )
    v2 = 260;
  *(_QWORD *)Pid = -1;
  v3 = I_RpcBindingInqLocalClientPID(0, &Pid[1]);
  v4 = v3;
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x80070000;
  if ( v4 >= 0 )
  {
    ProcessIdToSessionId(Pid[1], Pid);
    if ( v2 )
    {
      v8 = OpenProcess(0x400u, 0, Pid[1]);
      v9 = v8;
      if ( v8 )
      {
        InformationProcess = NtQueryInformationProcess(v8, ProcessImageFileName, ProcessInformation, 0x110u, 0);
        v4 = InformationProcess | 0x10000000;
        if ( InformationProcess >= 0 )
        {
          v11 = wcsrchr(Str, 0x5Cu);
          if ( v11 )
            v12 = v11 + 1;
          else
            v12 = Str;
          StringCchCopyW(v22, v2, v12);
        }
        CloseHandle(v9);
      }
    }
  }
  if ( v21 )
  {
    if ( v4 < 0 )
    {
      if ( (g_DebugTraceComponent & 1) != 0 )
        _DbgPrintMessage(2, "RPC Caller: Unknown");
    }
    else if ( (g_DebugTraceComponent & 1) != 0 )
    {
      _DbgPrintMessage(2, "RPC Caller: PID %d, SessID %d, Process Name: <%S>", Pid[1], Pid[0], v22);
    }
  }
  if ( !a1 )
  {
    v7 = "phEnum";
LABEL_23:
    _DbgPrintMessage(8, "Missing paramter %s in %s", v7, "RpcCloseEnum");
    v5 = -2147024809;
    goto LABEL_15;
  }
  if ( !*a1 )
  {
    v7 = "*phEnum";
    goto LABEL_23;
  }
  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 16LL))(*a1);
  *a1 = 0;
  v5 = 0;
LABEL_15:
  v14 = &CRpcCallTrace::`vftable';
  if ( v21 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "%s with Trace ID 0x%x Completed", v19, v16[0]);
  v14 = &CTraceBase::`vftable';
  if ( CTraceBase::g_bEnabled && !v18 && CTraceBase::g_TLSIndex != -1 )
  {
    if ( !TlsSetValue(CTraceBase::g_TLSIndex, 0) )
    {
      GetLastError();
LABEL_53:
      GetLastError();
      return v5;
    }
    if ( !TlsSetValue(CTraceBase::g_CreatorFunctionTLSIndex, 0) )
      goto LABEL_53;
  }
  return v5;
}

```

## disassembly

```asm
0x1800085c0  push    rbp
0x1800085c2  push    rbx
0x1800085c3  push    rsi
0x1800085c4  push    rdi
0x1800085c5  push    r12
0x1800085c7  push    r13
0x1800085c9  push    r14
0x1800085cb  push    r15
0x1800085cd  lea     rbp, [rsp-2B8h]
0x1800085d5  sub     rsp, 3B8h
0x1800085dc  mov     rax, cs:__security_cookie
0x1800085e3  xor     rax, rsp
0x1800085e6  mov     [rbp+2F0h+var_50], rax
0x1800085ed  mov     rdi, rcx
0x1800085f0  lea     r12, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x1800085f7  mov     [rsp+3F0h+var_3B0], r12
0x1800085fc  mov     ebx, 1
0x180008601  mov     [rsp+3F0h+var_394], ebx
0x180008605  xor     r15d, r15d
0x180008608  mov     [rsp+3F0h+var_390], r15
0x18000860d  lea     r14, aRpccloseenum; "RpcCloseEnum"
0x180008614  cmp     cs:?g_bEnabled@CTraceBase@@0HA, r15d; int CTraceBase::g_bEnabled
0x18000861b  jnz     loc_18000884D
0x180008621  lea     rcx, [rsp+3F0h+pguid]; pguid
0x180008626  call    cs:__imp_CoCreateGuid
0x18000862c  lock xadd cs:?g_NextShortActivityID@CTraceBase@@0KA, ebx; ulong CTraceBase::g_NextShortActivityID
0x180008634  inc     ebx
0x180008636  mov     [rsp+3F0h+var_398], ebx
0x18000863a  mov     [rsp+3F0h+var_388], r15d
0x18000863f  lea     r13, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x180008646  mov     [rsp+3F0h+var_3B0], r13
0x18000864b  mov     [rsp+3F0h+var_380], r14
0x180008650  mov     qword ptr [rsp+3F0h+Pid], 0FFFFFFFFFFFFFFFFh
0x180008659  mov     [rbp+2F0h+var_370], r15d
0x18000865d  xor     edx, edx; Val
0x18000865f  mov     r8d, 208h; Size
0x180008665  lea     rcx, [rbp+2F0h+var_36C]; void *
0x180008669  call    memset_0
0x18000866e  cmp     [rbp+2F0h+var_370], r15d
0x180008672  jnz     loc_180008796
0x180008678  mov     esi, r15d
0x18000867b  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x180008682  jnz     loc_18000891A
0x180008688  mov     qword ptr [rsp+3F0h+Pid], 0FFFFFFFFFFFFFFFFh
0x180008691  lea     rdx, [rsp+3F0h+Pid+4]; Pid
0x180008696  xor     ecx, ecx; Binding
0x180008698  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18000869e  mov     ebx, eax
0x1800086a0  test    eax, eax
0x1800086a2  jg      loc_180008788
0x1800086a8  test    ebx, ebx
0x1800086aa  js      short loc_1800086C3
0x1800086ac  lea     rdx, [rsp+3F0h+Pid]; pSessionId
0x1800086b1  mov     ecx, [rsp+3F0h+Pid+4]; dwProcessId
0x1800086b5  call    cs:__imp_ProcessIdToSessionId
0x1800086bb  test    esi, esi
0x1800086bd  jnz     loc_180008924
0x1800086c3  cmp     [rbp+2F0h+var_370], r15d
0x1800086c7  jnz     loc_1800087F0
0x1800086cd  test    rdi, rdi
0x1800086d0  jz      loc_180008763
0x1800086d6  mov     rcx, [rdi]
0x1800086d9  test    rcx, rcx
0x1800086dc  jz      loc_1800089AF
0x1800086e2  mov     rax, [rcx]
0x1800086e5  mov     rax, [rax+10h]
0x1800086e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086ee  mov     [rdi], r15
0x1800086f1  mov     ebx, r15d
0x1800086f4  mov     [rsp+3F0h+var_3B0], r13
0x1800086f9  cmp     [rbp+2F0h+var_370], 0
0x1800086fd  jnz     loc_1800087C3
0x180008703  mov     [rsp+3F0h+var_3B0], r12
0x180008708  cmp     cs:?g_bEnabled@CTraceBase@@0HA, 0; int CTraceBase::g_bEnabled
0x18000870f  jnz     short loc_180008736
0x180008711  mov     eax, ebx
0x180008713  mov     rcx, [rbp+2F0h+var_50]
0x18000871a  xor     rcx, rsp; StackCookie
0x18000871d  call    __security_check_cookie
0x180008722  add     rsp, 3B8h
0x180008729  pop     r15
0x18000872b  pop     r14
0x18000872d  pop     r13
0x18000872f  pop     r12
0x180008731  pop     rdi
0x180008732  pop     rsi
0x180008733  pop     rbx
0x180008734  pop     rbp
0x180008735  retn
0x180008736  cmp     [rsp+3F0h+var_388], 0
0x18000873b  jnz     short loc_180008711
0x18000873d  mov     ecx, cs:?g_TLSIndex@CTraceBase@@0KA; dwTlsIndex
0x180008743  cmp     ecx, 0FFFFFFFFh
0x180008746  jz      short loc_180008711
0x180008748  xor     edx, edx; lpTlsValue
0x18000874a  call    cs:__imp_TlsSetValue
0x180008750  test    eax, eax
0x180008752  jnz     loc_1800089BB
0x180008758  call    cs:__imp_GetLastError
0x18000875e  jmp     loc_1800089D1
0x180008763  lea     r8, aPhenum_0; "phEnum"
0x18000876a  mov     r9, r14
0x18000876d  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x180008774  mov     ecx, 8; int
0x180008779  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000877e  mov     ebx, 80070057h
0x180008783  jmp     loc_1800086F4
0x180008788  movzx   ebx, ax
0x18000878b  or      ebx, 80070000h
0x180008791  jmp     loc_1800086A8
0x180008796  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000879d  jz      loc_180008678
0x1800087a3  mov     r9d, [rsp+3F0h+var_398]
0x1800087a8  mov     r8, [rsp+3F0h+var_380]
0x1800087ad  lea     rdx, aTraceRpcSWithT; "TRACE RPC %s with Trace ID 0x%x"
0x1800087b4  mov     ecx, 2; int
0x1800087b9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800087be  jmp     loc_180008678
0x1800087c3  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x1800087ca  jz      loc_180008703
0x1800087d0  mov     r9d, [rsp+3F0h+var_398]
0x1800087d5  mov     r8, [rsp+3F0h+var_380]
0x1800087da  lea     rdx, aSWithTraceId0x; "%s with Trace ID 0x%x Completed"
0x1800087e1  mov     ecx, 2; int
0x1800087e6  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800087eb  jmp     loc_180008703
0x1800087f0  test    ebx, ebx
0x1800087f2  js      short loc_18000882A
0x1800087f4  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x1800087fb  jz      loc_1800086CD
0x180008801  lea     rax, [rbp+2F0h+var_36C]
0x180008805  mov     [rsp+3F0h+ReturnLength], rax
0x18000880a  mov     r9d, [rsp+3F0h+Pid]
0x18000880f  mov     r8d, [rsp+3F0h+Pid+4]
0x180008814  lea     rdx, aRpcCallerPidDS; "RPC Caller: PID %d, SessID %d, Process "...
0x18000881b  mov     ecx, 2; int
0x180008820  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180008825  jmp     loc_1800086CD
0x18000882a  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x180008831  jz      loc_1800086CD
0x180008837  lea     rdx, aRpcCallerUnkno; "RPC Caller: Unknown"
0x18000883e  mov     ecx, 2; int
0x180008843  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180008848  jmp     loc_1800086CD
0x18000884d  test    byte ptr cs:?g_DebugTraceComponent@@3KA, bl; ulong g_DebugTraceComponent
0x180008853  jz      short loc_180008873
0x180008855  mov     [rsp+3F0h+ReturnLength], r14
0x18000885a  mov     r9d, ebx
0x18000885d  lea     r8, [rsp+3F0h+var_3B0]
0x180008862  lea     rdx, aAddingTracePDS; "Adding trace %p, %d, %s"
0x180008869  mov     ecx, 2; int
0x18000886e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180008873  mov     [rsp+3F0h+var_3C0], r15
0x180008878  lea     rcx, [rsp+3F0h+var_3C0]; struct CTraceBase **
0x18000887d  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x180008882  test    eax, eax
0x180008884  js      short loc_1800088A9
0x180008886  cmp     [rsp+3F0h+var_3C0], r15
0x18000888b  jz      short loc_1800088A9
0x18000888d  test    byte ptr cs:?g_DebugTraceComponent@@3KA, bl; ulong g_DebugTraceComponent
0x180008893  jz      short loc_1800088A9
0x180008895  mov     r8d, ebx
0x180008898  lea     rdx, aTracecomponent; "TraceComponent %d: Warning TLS should b"...
0x18000889f  mov     ecx, 2; int
0x1800088a4  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800088a9  xor     edx, edx; char *
0x1800088ab  xor     ecx, ecx; lpTlsValue
0x1800088ad  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x1800088b2  lea     rcx, [rsp+3F0h+var_390]; struct CTraceBase **
0x1800088b7  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x1800088bc  test    eax, eax
0x1800088be  js      short loc_1800088F9
0x1800088c0  mov     rcx, [rsp+3F0h+var_390]
0x1800088c5  test    rcx, rcx
0x1800088c8  jz      short loc_1800088F9
0x1800088ca  mov     rax, [rcx]
0x1800088cd  lea     rdx, [rsp+3F0h+pguid]
0x1800088d2  mov     rax, [rax+20h]
0x1800088d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088db  mov     rcx, [rsp+3F0h+var_390]
0x1800088e0  mov     rax, [rcx]
0x1800088e3  mov     rax, [rax+18h]
0x1800088e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088ec  mov     [rsp+3F0h+var_398], eax
0x1800088f0  mov     [rsp+3F0h+var_388], ebx
0x1800088f4  jmp     loc_18000863F
0x1800088f9  mov     rdx, r14; char *
0x1800088fc  lea     rcx, [rsp+3F0h+var_3B0]; lpTlsValue
0x180008901  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x180008906  lea     rdx, [rsp+3F0h+var_398]; unsigned int *
0x18000890b  lea     rcx, [rsp+3F0h+pguid]; struct _GUID *
0x180008910  call    ?GenerateTraceID@CTraceBase@@KAJPEAU_GUID@@PEAK@Z; CTraceBase::GenerateTraceID(_GUID *,ulong *)
0x180008915  jmp     loc_18000863A
0x18000891a  mov     esi, 104h
0x18000891f  jmp     loc_180008688
0x180008924  mov     r8d, [rsp+3F0h+Pid+4]; dwProcessId
0x180008929  xor     edx, edx; bInheritHandle
0x18000892b  mov     ecx, 400h; dwDesiredAccess
0x180008930  call    cs:__imp_OpenProcess
0x180008936  mov     r14, rax
0x180008939  test    rax, rax
0x18000893c  jz      short loc_1800089A3
0x18000893e  mov     [rsp+3F0h+ReturnLength], r15; ReturnLength
0x180008943  mov     r9d, 110h; ProcessInformationLength
0x180008949  lea     r8, [rbp+2F0h+ProcessInformation]; ProcessInformation
0x180008950  mov     edx, 1Bh; ProcessInformationClass
0x180008955  mov     rcx, rax; ProcessHandle
0x180008958  call    cs:__imp_NtQueryInformationProcess
0x18000895e  mov     ebx, eax
0x180008960  or      ebx, 10000000h
0x180008966  jl      short loc_18000899A
0x180008968  mov     edx, 5Ch ; '\'; Ch
0x18000896d  mov     rcx, [rbp+2F0h+Str]; Str
0x180008974  call    cs:__imp_wcsrchr
0x18000897a  test    rax, rax
0x18000897d  jnz     short loc_180008988
0x18000897f  mov     rax, [rbp+2F0h+Str]
0x180008986  jmp     short loc_18000898C
0x180008988  add     rax, 2
0x18000898c  mov     edx, esi; unsigned __int64
0x18000898e  mov     r8, rax; unsigned __int16 *
0x180008991  lea     rcx, [rbp+2F0h+var_36C]; unsigned __int16 *
0x180008995  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000899a  mov     rcx, r14; hObject
0x18000899d  call    cs:__imp_CloseHandle
0x1800089a3  lea     r14, aRpccloseenum; "RpcCloseEnum"
0x1800089aa  jmp     loc_1800086C3
0x1800089af  lea     r8, aPhenum; "*phEnum"
0x1800089b6  jmp     loc_18000876A
0x1800089bb  xor     edx, edx; lpTlsValue
0x1800089bd  mov     ecx, cs:?g_CreatorFunctionTLSIndex@CTraceBase@@0KA; dwTlsIndex
0x1800089c3  call    cs:__imp_TlsSetValue
0x1800089c9  test    eax, eax
0x1800089cb  jnz     loc_180008711
0x1800089d1  call    cs:__imp_GetLastError
0x1800089d7  jmp     loc_180008711
```
