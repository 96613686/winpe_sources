# RpcGetTerminalName

- ea: `0x18000ec10`
- end: `0x18000f257`
- name: `RpcGetTerminalName`
- size: `1607`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000e210`

## callees

- `0x1800077a0`
- `0x180009580`
- `0x18000ec10`
- `0x18000f260`
- `0x1800101b0`
- `0x180010260`
- `0x180029158`
- `0x18004e850`
- `0x18004f354`
- `0x18009c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000f190`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000f190`
- `ntdll!NtQueryInformationProcess` at `0x18000f16e`
- `ntdll!NtQueryInformationProcess` at `0x18000f16e`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000ed1f`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000ed1f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f1c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f1c0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000eee8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000eee8`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000ec80`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000ec80`
- `RPCRT4!RpcImpersonateClient` at `0x18000ee22`
- `RPCRT4!RpcImpersonateClient` at `0x18000ee22`
- `RPCRT4!RpcRevertToSelf` at `0x18000ee5e`
- `RPCRT4!RpcRevertToSelf` at `0x18000ee5e`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000ecfc`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000ecfc`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000f140`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000f140`

## string_xrefs

- `0x18000f035`: `AccessCheckEx failed: 0x%X`
- `0x18000ed86`: `CheckAccessToSession(WINSTATION_QUERY) failed: 0x%x in %s`
- `0x18000ed5f`: `CheckAccessToSession`
- `0x18000f1e7`: `Cannot impersonate client: %d`
- `0x18000f0a3`: `TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC`
- `0x18000eff9`: `RPC Caller: PID %d, SessID %d, Process Name: <%S>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  void *v25; // r12
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
LABEL_44:
    _DbgPrintMessage(8, "Missing paramter %s in %s", v23, "RpcGetTerminalName");
    v8 = -2147024809;
    goto LABEL_21;
  }
  if ( !a2 )
  {
    v23 = "pszTerminalName";
    goto LABEL_44;
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
  CRpcCallTrace::~CRpcCallTrace((CRpcCallTrace *)&v31);
  if ( v29 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000ec10  push    rbp
0x18000ec12  push    rbx
0x18000ec13  push    rsi
0x18000ec14  push    rdi
0x18000ec15  push    r12
0x18000ec17  push    r13
0x18000ec19  push    r14
0x18000ec1b  push    r15
0x18000ec1d  lea     rbp, [rsp-308h]
0x18000ec25  sub     rsp, 408h
0x18000ec2c  mov     rax, cs:__security_cookie
0x18000ec33  xor     rax, rsp
0x18000ec36  mov     [rbp+340h+var_50], rax
0x18000ec3d  mov     r15, rdx
0x18000ec40  mov     rsi, rcx
0x18000ec43  xor     r13d, r13d
0x18000ec46  mov     ebx, r13d
0x18000ec49  mov     [rsp+440h+var_410], r13
0x18000ec4e  lea     rax, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x18000ec55  mov     [rsp+440h+var_400], rax
0x18000ec5a  mov     [rsp+440h+var_3E4], 1
0x18000ec62  mov     [rsp+440h+var_3E0], r13
0x18000ec67  lea     r12, aRpcgetterminal_0; "RpcGetTerminalName"
0x18000ec6e  cmp     cs:?g_bEnabled@CTraceBase@@0HA, r13d; int CTraceBase::g_bEnabled
0x18000ec75  jnz     loc_18000F050
0x18000ec7b  lea     rcx, [rsp+440h+pguid]; pguid
0x18000ec80  call    cs:__imp_CoCreateGuid
0x18000ec87  nop     dword ptr [rax+rax+00h]
0x18000ec8c  mov     eax, 1
0x18000ec91  lock xadd cs:?g_NextShortActivityID@CTraceBase@@0KA, eax; ulong CTraceBase::g_NextShortActivityID
0x18000ec99  inc     eax
0x18000ec9b  mov     [rsp+440h+var_3E8], eax
0x18000ec9f  mov     [rsp+440h+var_3D8], r13d
0x18000eca4  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x18000ecab  mov     [rsp+440h+var_400], rax
0x18000ecb0  mov     [rsp+440h+var_3D0], r12
0x18000ecb5  mov     qword ptr [rsp+440h+Pid], 0FFFFFFFFFFFFFFFFh
0x18000ecbe  mov     [rbp+340h+var_3C0], r13d
0x18000ecc2  xor     edx, edx; Val
0x18000ecc4  mov     r8d, 208h; Size
0x18000ecca  lea     rcx, [rbp+340h+var_3BC]; void *
0x18000ecce  call    memset_0
0x18000ecd3  cmp     [rbp+340h+var_3C0], ebx
0x18000ecd6  jnz     loc_18000EFA8
0x18000ecdc  mov     r14d, r13d
0x18000ecdf  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000ece6  jnz     loc_18000F129
0x18000ecec  mov     qword ptr [rsp+440h+Pid], 0FFFFFFFFFFFFFFFFh
0x18000ecf5  lea     rdx, [rsp+440h+Pid+4]; Pid
0x18000ecfa  xor     ecx, ecx; Binding
0x18000ecfc  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18000ed03  nop     dword ptr [rax+rax+00h]
0x18000ed08  mov     edi, eax
0x18000ed0a  test    eax, eax
0x18000ed0c  jg      loc_18000EF54
0x18000ed12  test    edi, edi
0x18000ed14  js      short loc_18000ED34
0x18000ed16  lea     rdx, [rsp+440h+Pid]; pSessionId
0x18000ed1b  mov     ecx, [rsp+440h+Pid+4]; dwProcessId
0x18000ed1f  call    cs:__imp_ProcessIdToSessionId
0x18000ed26  nop     dword ptr [rax+rax+00h]
0x18000ed2b  test    r14d, r14d
0x18000ed2e  jnz     loc_18000F134
0x18000ed34  cmp     [rbp+340h+var_3C0], ebx
0x18000ed37  jnz     loc_18000EFD5
0x18000ed3d  test    rsi, rsi
0x18000ed40  jz      loc_18000EF62
0x18000ed46  test    r15, r15
0x18000ed49  jz      loc_18000F1D8
0x18000ed4f  mov     rbx, [rsi+638h]
0x18000ed56  test    rbx, rbx
0x18000ed59  jnz     loc_18000EE11
0x18000ed5f  lea     r9, aCheckaccesstos_3; "CheckAccessToSession"
0x18000ed66  lea     r8, aPsession; "pSession"
0x18000ed6d  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x18000ed74  mov     ecx, 8; int
0x18000ed79  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000ed7e  mov     edi, 80070057h
0x18000ed83  mov     r8d, edi
0x18000ed86  lea     rdx, aCheckaccesstos_5; "CheckAccessToSession(WINSTATION_QUERY) "...
0x18000ed8d  mov     r9, r12
0x18000ed90  mov     ecx, 8; int
0x18000ed95  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000ed9a  jmp     short loc_18000EDB4
0x18000ed9c  lea     rcx, [r8-2]
0x18000eda0  test    rsi, rsi
0x18000eda3  cmovnz  rcx, r8
0x18000eda7  mov     [rcx], r13w
0x18000edab  mov     edi, 8007007Ah
0x18000edb0  cmovnz  edi, r13d
0x18000edb4  lea     rcx, [rsp+440h+var_400]; this
0x18000edb9  call    ??1CRpcCallTrace@@UEAA@XZ; CRpcCallTrace::~CRpcCallTrace(void)
0x18000edbe  nop
0x18000edbf  mov     rcx, [rsp+440h+var_410]
0x18000edc4  test    rcx, rcx
0x18000edc7  jz      short loc_18000EDD6
0x18000edc9  mov     rax, [rcx]
0x18000edcc  mov     rax, [rax+10h]
0x18000edd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000edd5  nop
0x18000edd6  test    rbx, rbx
0x18000edd9  jz      short loc_18000EDEB
0x18000eddb  mov     rax, [rbx]
0x18000edde  mov     rcx, rbx
0x18000ede1  mov     rax, [rax+10h]
0x18000ede5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000edea  nop
0x18000edeb  mov     eax, edi
0x18000eded  mov     rcx, [rbp+340h+var_50]
0x18000edf4  xor     rcx, rsp; StackCookie
0x18000edf7  call    __security_check_cookie
0x18000edfc  add     rsp, 408h
0x18000ee03  pop     r15
0x18000ee05  pop     r14
0x18000ee07  pop     r13
0x18000ee09  pop     r12
0x18000ee0b  pop     rdi
0x18000ee0c  pop     rsi
0x18000ee0d  pop     rbx
0x18000ee0e  pop     rbp
0x18000ee0f  retn
0x18000ee11  mov     rax, [rbx]
0x18000ee14  mov     rcx, rbx
0x18000ee17  mov     rax, [rax+8]
0x18000ee1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee20  xor     ecx, ecx; BindingHandle
0x18000ee22  call    cs:__imp_RpcImpersonateClient
0x18000ee29  nop     dword ptr [rax+rax+00h]
0x18000ee2e  test    eax, eax
0x18000ee30  jnz     loc_18000F1E4
0x18000ee36  mov     rax, [rbx]
0x18000ee39  mov     r9d, 1
0x18000ee3f  xor     r8d, r8d
0x18000ee42  mov     edx, r9d
0x18000ee45  mov     rcx, rbx
0x18000ee48  mov     rax, [rax+90h]
0x18000ee4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee54  mov     edi, eax
0x18000ee56  test    eax, eax
0x18000ee58  js      loc_18000F032
0x18000ee5e  call    cs:__imp_RpcRevertToSelf
0x18000ee65  nop     dword ptr [rax+rax+00h]
0x18000ee6a  test    eax, eax
0x18000ee6c  jnz     loc_18000F202
0x18000ee72  test    edi, edi
0x18000ee74  js      loc_18000ED83
0x18000ee7a  mov     rax, [rbx]
0x18000ee7d  lea     rdx, [rsp+440h+var_410]
0x18000ee82  mov     rcx, rbx
0x18000ee85  mov     rax, [rax+68h]
0x18000ee89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee8e  test    eax, eax
0x18000ee90  js      loc_18000EF87
0x18000ee96  mov     rcx, [rsp+440h+var_410]
0x18000ee9b  mov     rax, [rcx]
0x18000ee9e  lea     rdx, [rbp+340h+var_A0]
0x18000eea5  mov     rax, [rax+68h]
0x18000eea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eeae  mov     edi, eax
0x18000eeb0  test    eax, eax
0x18000eeb2  js      loc_18000F220
0x18000eeb8  lea     rcx, [rbp+340h+var_A0]
0x18000eebf  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000eec6  nop     word ptr [rax+rax+00000000h]
0x18000eed0  lea     rax, [rax+1]
0x18000eed4  cmp     [rcx+rax*2], r13w
0x18000eed9  jnz     short loc_18000EED0
0x18000eedb  lea     rsi, [rax+1]
0x18000eedf  lea     rdx, [rsi+rsi]; uBytes
0x18000eee3  mov     ecx, 40h ; '@'; uFlags
0x18000eee8  call    cs:__imp_LocalAlloc
0x18000eeef  nop     dword ptr [rax+rax+00h]
0x18000eef4  mov     r8, rax
0x18000eef7  mov     [r15], rax
0x18000eefa  test    rax, rax
0x18000eefd  jz      loc_18000F22F
0x18000ef03  test    rsi, rsi
0x18000ef06  jz      loc_18000F240
0x18000ef0c  cmp     rsi, 7FFFFFFFh
0x18000ef13  ja      loc_18000F239
0x18000ef19  mov     ecx, 7FFFFFFEh
0x18000ef1e  lea     rdx, [rbp+340h+var_A0]
0x18000ef25  test    rcx, rcx
0x18000ef28  jz      loc_18000ED9C
0x18000ef2e  movzx   eax, word ptr [rdx]
0x18000ef31  test    ax, ax
0x18000ef34  jz      loc_18000ED9C
0x18000ef3a  add     rdx, 2
0x18000ef3e  mov     [r8], ax
0x18000ef42  add     r8, 2
0x18000ef46  dec     rcx
0x18000ef49  sub     rsi, 1
0x18000ef4d  jnz     short loc_18000EF25
0x18000ef4f  jmp     loc_18000ED9C
0x18000ef54  movzx   edi, ax
0x18000ef57  or      edi, 80070000h
0x18000ef5d  jmp     loc_18000ED12
0x18000ef62  lea     r8, aHsession; "hSession"
0x18000ef69  mov     r9, r12
0x18000ef6c  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x18000ef73  mov     ecx, 8; int
0x18000ef78  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000ef7d  mov     edi, 80070057h
0x18000ef82  jmp     loc_18000EDB4
0x18000ef87  mov     r8d, eax
0x18000ef8a  lea     rdx, aRpcgetterminal_1; "RpcGetTerminalName, no terminal: 0x%x, "...
0x18000ef91  mov     ecx, 4; int
0x18000ef96  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000ef9b  mov     [rbp+340h+var_A0], r13w
0x18000efa3  jmp     loc_18000EEB8
0x18000efa8  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000efaf  jz      loc_18000ECDC
0x18000efb5  mov     r9d, [rsp+440h+var_3E8]
0x18000efba  mov     r8, [rsp+440h+var_3D0]
0x18000efbf  lea     rdx, aTraceRpcSWithT; "TRACE RPC %s with Trace ID 0x%x"
0x18000efc6  mov     ecx, 2; int
0x18000efcb  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000efd0  jmp     loc_18000ECDC
0x18000efd5  test    edi, edi
0x18000efd7  js      short loc_18000F00F
0x18000efd9  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000efe0  jz      loc_18000ED3D
0x18000efe6  lea     rax, [rbp+340h+var_3BC]
0x18000efea  mov     [rsp+440h+ReturnLength], rax
0x18000efef  mov     r9d, [rsp+440h+Pid]
0x18000eff4  mov     r8d, [rsp+440h+Pid+4]
0x18000eff9  lea     rdx, aRpcCallerPidDS; "RPC Caller: PID %d, SessID %d, Process "...
0x18000f000  mov     ecx, 2; int
0x18000f005  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000f00a  jmp     loc_18000ED3D
0x18000f00f  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000f016  jz      loc_18000ED3D
0x18000f01c  lea     rdx, aRpcCallerUnkno; "RPC Caller: Unknown"
0x18000f023  mov     ecx, 2; int
0x18000f028  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000f02d  jmp     loc_18000ED3D
0x18000f032  mov     r8d, eax
0x18000f035  lea     rdx, aAccesscheckexF; "AccessCheckEx failed: 0x%X"
0x18000f03c  mov     ecx, 8; int
0x18000f041  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000f046  mov     edi, 80070005h
0x18000f04b  jmp     loc_18000EE5E
0x18000f050  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000f057  jz      short loc_18000F07A
0x18000f059  mov     [rsp+440h+ReturnLength], r12
0x18000f05e  mov     r9d, 1
0x18000f064  lea     r8, [rsp+440h+var_400]
0x18000f069  lea     rdx, aAddingTracePDS; "Adding trace %p, %d, %s"
0x18000f070  mov     ecx, 2; int
0x18000f075  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000f07a  mov     [rsp+440h+var_408], r13
0x18000f07f  lea     rcx, [rsp+440h+var_408]; struct CTraceBase **
0x18000f084  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x18000f089  test    eax, eax
0x18000f08b  js      short loc_18000F0B4
0x18000f08d  cmp     [rsp+440h+var_408], rbx
0x18000f092  jz      short loc_18000F0B4
0x18000f094  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000f09b  jz      short loc_18000F0B4
0x18000f09d  mov     r8d, 1
0x18000f0a3  lea     rdx, aTracecomponent; "TraceComponent %d: Warning TLS should b"...
0x18000f0aa  mov     ecx, 2; int
0x18000f0af  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000f0b4  xor     edx, edx; char *
0x18000f0b6  xor     ecx, ecx; lpTlsValue
0x18000f0b8  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x18000f0bd  lea     rcx, [rsp+440h+var_3E0]; struct CTraceBase **
0x18000f0c2  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x18000f0c7  test    eax, eax
0x18000f0c9  js      short loc_18000F108
0x18000f0cb  mov     rcx, [rsp+440h+var_3E0]
0x18000f0d0  test    rcx, rcx
0x18000f0d3  jz      short loc_18000F108
0x18000f0d5  mov     rax, [rcx]
0x18000f0d8  lea     rdx, [rsp+440h+pguid]
0x18000f0dd  mov     rax, [rax+20h]
0x18000f0e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0e6  mov     rcx, [rsp+440h+var_3E0]
0x18000f0eb  mov     rax, [rcx]
0x18000f0ee  mov     rax, [rax+18h]
0x18000f0f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0f7  mov     [rsp+440h+var_3E8], eax
0x18000f0fb  mov     [rsp+440h+var_3D8], 1
0x18000f103  jmp     loc_18000ECA4
0x18000f108  mov     rdx, r12; char *
0x18000f10b  lea     rcx, [rsp+440h+var_400]; lpTlsValue
0x18000f110  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x18000f115  lea     rdx, [rsp+440h+var_3E8]; unsigned int *
0x18000f11a  lea     rcx, [rsp+440h+pguid]; struct _GUID *
0x18000f11f  call    ?GenerateTraceID@CTraceBase@@KAJPEAU_GUID@@PEAK@Z; CTraceBase::GenerateTraceID(_GUID *,ulong *)
0x18000f124  jmp     loc_18000EC9F
0x18000f129  mov     r14d, 104h
0x18000f12f  jmp     loc_18000ECEC
0x18000f134  mov     r8d, [rsp+440h+Pid+4]; dwProcessId
0x18000f139  xor     edx, edx; bInheritHandle
0x18000f13b  mov     ecx, 400h; dwDesiredAccess
0x18000f140  call    cs:__imp_OpenProcess
0x18000f147  nop     dword ptr [rax+rax+00h]
0x18000f14c  mov     r12, rax
0x18000f14f  test    rax, rax
  ... truncated ...
```
