# RpcCloseEnum

- ea: `0x180008970`
- end: `0x180008dd0`
- name: `RpcCloseEnum`
- size: `1120`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18005f460`

## callees

- `0x1800077a0`
- `0x180008970`
- `0x180009580`
- `0x1800101b0`
- `0x180010260`
- `0x180029158`
- `0x18004e850`
- `0x18004f354`
- `0x18009c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180008d4f`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180008d4f`
- `ntdll!NtQueryInformationProcess` at `0x180008d2d`
- `ntdll!NtQueryInformationProcess` at `0x180008d2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008dbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008dbe`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180008b0d`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180008daa`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180008b0d`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180008daa`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180008a71`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180008a71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008d7e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008d7e`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800089d6`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800089d6`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180008a4e`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180008a4e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180008cff`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180008cff`

## string_xrefs

- `0x180008ba9`: `%s with Trace ID 0x%x Completed`
- `0x180008c67`: `TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC`
- `0x180008be3`: `RPC Caller: PID %d, SessID %d, Process Name: <%S>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180008970  push    rbp
0x180008972  push    rbx
0x180008973  push    rsi
0x180008974  push    rdi
0x180008975  push    r12
0x180008977  push    r13
0x180008979  push    r14
0x18000897b  push    r15
0x18000897d  lea     rbp, [rsp-2B8h]
0x180008985  sub     rsp, 3B8h
0x18000898c  mov     rax, cs:__security_cookie
0x180008993  xor     rax, rsp
0x180008996  mov     [rbp+2F0h+var_50], rax
0x18000899d  mov     rdi, rcx
0x1800089a0  lea     r12, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x1800089a7  mov     [rsp+3F0h+var_3B0], r12
0x1800089ac  mov     ebx, 1
0x1800089b1  mov     [rsp+3F0h+var_394], ebx
0x1800089b5  xor     r15d, r15d
0x1800089b8  mov     [rsp+3F0h+var_390], r15
0x1800089bd  lea     r14, aRpccloseenum; "RpcCloseEnum"
0x1800089c4  cmp     cs:?g_bEnabled@CTraceBase@@0HA, r15d; int CTraceBase::g_bEnabled
0x1800089cb  jnz     loc_180008C1C
0x1800089d1  lea     rcx, [rsp+3F0h+pguid]; pguid
0x1800089d6  call    cs:__imp_CoCreateGuid
0x1800089dd  nop     dword ptr [rax+rax+00h]
0x1800089e2  lock xadd cs:?g_NextShortActivityID@CTraceBase@@0KA, ebx; ulong CTraceBase::g_NextShortActivityID
0x1800089ea  inc     ebx
0x1800089ec  mov     [rsp+3F0h+var_398], ebx
0x1800089f0  mov     [rsp+3F0h+var_388], r15d
0x1800089f5  lea     r13, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x1800089fc  mov     [rsp+3F0h+var_3B0], r13
0x180008a01  mov     [rsp+3F0h+var_380], r14
0x180008a06  mov     qword ptr [rsp+3F0h+Pid], 0FFFFFFFFFFFFFFFFh
0x180008a0f  mov     [rbp+2F0h+var_370], r15d
0x180008a13  xor     edx, edx; Val
0x180008a15  mov     r8d, 208h; Size
0x180008a1b  lea     rcx, [rbp+2F0h+var_36C]; void *
0x180008a1f  call    memset_0
0x180008a24  cmp     [rbp+2F0h+var_370], r15d
0x180008a28  jnz     loc_180008B65
0x180008a2e  mov     esi, r15d
0x180008a31  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x180008a38  jnz     loc_180008CE9
0x180008a3e  mov     qword ptr [rsp+3F0h+Pid], 0FFFFFFFFFFFFFFFFh
0x180008a47  lea     rdx, [rsp+3F0h+Pid+4]; Pid
0x180008a4c  xor     ecx, ecx; Binding
0x180008a4e  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x180008a55  nop     dword ptr [rax+rax+00h]
0x180008a5a  mov     ebx, eax
0x180008a5c  test    eax, eax
0x180008a5e  jg      loc_180008B57
0x180008a64  test    ebx, ebx
0x180008a66  js      short loc_180008A85
0x180008a68  lea     rdx, [rsp+3F0h+Pid]; pSessionId
0x180008a6d  mov     ecx, [rsp+3F0h+Pid+4]; dwProcessId
0x180008a71  call    cs:__imp_ProcessIdToSessionId
0x180008a78  nop     dword ptr [rax+rax+00h]
0x180008a7d  test    esi, esi
0x180008a7f  jnz     loc_180008CF3
0x180008a85  cmp     [rbp+2F0h+var_370], r15d
0x180008a89  jnz     loc_180008BBF
0x180008a8f  test    rdi, rdi
0x180008a92  jz      loc_180008B32
0x180008a98  mov     rcx, [rdi]
0x180008a9b  test    rcx, rcx
0x180008a9e  jz      loc_180008D96
0x180008aa4  mov     rax, [rcx]
0x180008aa7  mov     rax, [rax+10h]
0x180008aab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ab0  mov     [rdi], r15
0x180008ab3  mov     ebx, r15d
0x180008ab6  mov     [rsp+3F0h+var_3B0], r13
0x180008abb  cmp     [rbp+2F0h+var_370], 0
0x180008abf  jnz     loc_180008B92
0x180008ac5  mov     [rsp+3F0h+var_3B0], r12
0x180008aca  cmp     cs:?g_bEnabled@CTraceBase@@0HA, 0; int CTraceBase::g_bEnabled
0x180008ad1  jnz     short loc_180008AF9
0x180008ad3  mov     eax, ebx
0x180008ad5  mov     rcx, [rbp+2F0h+var_50]
0x180008adc  xor     rcx, rsp; StackCookie
0x180008adf  call    __security_check_cookie
0x180008ae4  add     rsp, 3B8h
0x180008aeb  pop     r15
0x180008aed  pop     r14
0x180008aef  pop     r13
0x180008af1  pop     r12
0x180008af3  pop     rdi
0x180008af4  pop     rsi
0x180008af5  pop     rbx
0x180008af6  pop     rbp
0x180008af7  retn
0x180008af9  cmp     [rsp+3F0h+var_388], 0
0x180008afe  jnz     short loc_180008AD3
0x180008b00  mov     ecx, cs:?g_TLSIndex@CTraceBase@@0KA; dwTlsIndex
0x180008b06  cmp     ecx, 0FFFFFFFFh
0x180008b09  jz      short loc_180008AD3
0x180008b0b  xor     edx, edx; lpTlsValue
0x180008b0d  call    cs:__imp_TlsSetValue
0x180008b14  nop     dword ptr [rax+rax+00h]
0x180008b19  test    eax, eax
0x180008b1b  jnz     loc_180008DA2
0x180008b21  call    cs:__imp_GetLastError
0x180008b28  nop     dword ptr [rax+rax+00h]
0x180008b2d  jmp     loc_180008DBE
0x180008b32  lea     r8, aPhenum_0; "phEnum"
0x180008b39  mov     r9, r14
0x180008b3c  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x180008b43  mov     ecx, 8; int
0x180008b48  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180008b4d  mov     ebx, 80070057h
0x180008b52  jmp     loc_180008AB6
0x180008b57  movzx   ebx, ax
0x180008b5a  or      ebx, 80070000h
0x180008b60  jmp     loc_180008A64
0x180008b65  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x180008b6c  jz      loc_180008A2E
0x180008b72  mov     r9d, [rsp+3F0h+var_398]
0x180008b77  mov     r8, [rsp+3F0h+var_380]
0x180008b7c  lea     rdx, aTraceRpcSWithT; "TRACE RPC %s with Trace ID 0x%x"
0x180008b83  mov     ecx, 2; int
0x180008b88  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180008b8d  jmp     loc_180008A2E
0x180008b92  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x180008b99  jz      loc_180008AC5
0x180008b9f  mov     r9d, [rsp+3F0h+var_398]
0x180008ba4  mov     r8, [rsp+3F0h+var_380]
0x180008ba9  lea     rdx, aSWithTraceId0x; "%s with Trace ID 0x%x Completed"
0x180008bb0  mov     ecx, 2; int
0x180008bb5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180008bba  jmp     loc_180008AC5
0x180008bbf  test    ebx, ebx
0x180008bc1  js      short loc_180008BF9
0x180008bc3  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x180008bca  jz      loc_180008A8F
0x180008bd0  lea     rax, [rbp+2F0h+var_36C]
0x180008bd4  mov     [rsp+3F0h+ReturnLength], rax
0x180008bd9  mov     r9d, [rsp+3F0h+Pid]
0x180008bde  mov     r8d, [rsp+3F0h+Pid+4]
0x180008be3  lea     rdx, aRpcCallerPidDS; "RPC Caller: PID %d, SessID %d, Process "...
0x180008bea  mov     ecx, 2; int
0x180008bef  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180008bf4  jmp     loc_180008A8F
0x180008bf9  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x180008c00  jz      loc_180008A8F
0x180008c06  lea     rdx, aRpcCallerUnkno; "RPC Caller: Unknown"
0x180008c0d  mov     ecx, 2; int
0x180008c12  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180008c17  jmp     loc_180008A8F
0x180008c1c  test    byte ptr cs:?g_DebugTraceComponent@@3KA, bl; ulong g_DebugTraceComponent
0x180008c22  jz      short loc_180008C42
0x180008c24  mov     [rsp+3F0h+ReturnLength], r14
0x180008c29  mov     r9d, ebx
0x180008c2c  lea     r8, [rsp+3F0h+var_3B0]
0x180008c31  lea     rdx, aAddingTracePDS; "Adding trace %p, %d, %s"
0x180008c38  mov     ecx, 2; int
0x180008c3d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180008c42  mov     [rsp+3F0h+var_3C0], r15
0x180008c47  lea     rcx, [rsp+3F0h+var_3C0]; struct CTraceBase **
0x180008c4c  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x180008c51  test    eax, eax
0x180008c53  js      short loc_180008C78
0x180008c55  cmp     [rsp+3F0h+var_3C0], r15
0x180008c5a  jz      short loc_180008C78
0x180008c5c  test    byte ptr cs:?g_DebugTraceComponent@@3KA, bl; ulong g_DebugTraceComponent
0x180008c62  jz      short loc_180008C78
0x180008c64  mov     r8d, ebx
0x180008c67  lea     rdx, aTracecomponent; "TraceComponent %d: Warning TLS should b"...
0x180008c6e  mov     ecx, 2; int
0x180008c73  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180008c78  xor     edx, edx; char *
0x180008c7a  xor     ecx, ecx; lpTlsValue
0x180008c7c  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x180008c81  lea     rcx, [rsp+3F0h+var_390]; struct CTraceBase **
0x180008c86  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x180008c8b  test    eax, eax
0x180008c8d  js      short loc_180008CC8
0x180008c8f  mov     rcx, [rsp+3F0h+var_390]
0x180008c94  test    rcx, rcx
0x180008c97  jz      short loc_180008CC8
0x180008c99  mov     rax, [rcx]
0x180008c9c  lea     rdx, [rsp+3F0h+pguid]
0x180008ca1  mov     rax, [rax+20h]
0x180008ca5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008caa  mov     rcx, [rsp+3F0h+var_390]
0x180008caf  mov     rax, [rcx]
0x180008cb2  mov     rax, [rax+18h]
0x180008cb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cbb  mov     [rsp+3F0h+var_398], eax
0x180008cbf  mov     [rsp+3F0h+var_388], ebx
0x180008cc3  jmp     loc_1800089F5
0x180008cc8  mov     rdx, r14; char *
0x180008ccb  lea     rcx, [rsp+3F0h+var_3B0]; lpTlsValue
0x180008cd0  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x180008cd5  lea     rdx, [rsp+3F0h+var_398]; unsigned int *
0x180008cda  lea     rcx, [rsp+3F0h+pguid]; struct _GUID *
0x180008cdf  call    ?GenerateTraceID@CTraceBase@@KAJPEAU_GUID@@PEAK@Z; CTraceBase::GenerateTraceID(_GUID *,ulong *)
0x180008ce4  jmp     loc_1800089F0
0x180008ce9  mov     esi, 104h
0x180008cee  jmp     loc_180008A3E
0x180008cf3  mov     r8d, [rsp+3F0h+Pid+4]; dwProcessId
0x180008cf8  xor     edx, edx; bInheritHandle
0x180008cfa  mov     ecx, 400h; dwDesiredAccess
0x180008cff  call    cs:__imp_OpenProcess
0x180008d06  nop     dword ptr [rax+rax+00h]
0x180008d0b  mov     r14, rax
0x180008d0e  test    rax, rax
0x180008d11  jz      short loc_180008D8A
0x180008d13  mov     [rsp+3F0h+ReturnLength], r15; ReturnLength
0x180008d18  mov     r9d, 110h; ProcessInformationLength
0x180008d1e  lea     r8, [rbp+2F0h+ProcessInformation]; ProcessInformation
0x180008d25  mov     edx, 1Bh; ProcessInformationClass
0x180008d2a  mov     rcx, rax; ProcessHandle
0x180008d2d  call    cs:__imp_NtQueryInformationProcess
0x180008d34  nop     dword ptr [rax+rax+00h]
0x180008d39  mov     ebx, eax
0x180008d3b  or      ebx, 10000000h
0x180008d41  jl      short loc_180008D7B
0x180008d43  mov     edx, 5Ch ; '\'; Ch
0x180008d48  mov     rcx, [rbp+2F0h+Str]; Str
0x180008d4f  call    cs:__imp_wcsrchr
0x180008d56  nop     dword ptr [rax+rax+00h]
0x180008d5b  test    rax, rax
0x180008d5e  jnz     short loc_180008D69
0x180008d60  mov     rax, [rbp+2F0h+Str]
0x180008d67  jmp     short loc_180008D6D
0x180008d69  add     rax, 2
0x180008d6d  mov     edx, esi; unsigned __int64
0x180008d6f  mov     r8, rax; unsigned __int16 *
0x180008d72  lea     rcx, [rbp+2F0h+var_36C]; unsigned __int16 *
0x180008d76  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180008d7b  mov     rcx, r14; hObject
0x180008d7e  call    cs:__imp_CloseHandle
0x180008d85  nop     dword ptr [rax+rax+00h]
0x180008d8a  lea     r14, aRpccloseenum; "RpcCloseEnum"
0x180008d91  jmp     loc_180008A85
0x180008d96  lea     r8, aPhenum; "*phEnum"
0x180008d9d  jmp     loc_180008B39
0x180008da2  xor     edx, edx; lpTlsValue
0x180008da4  mov     ecx, cs:?g_CreatorFunctionTLSIndex@CTraceBase@@0KA; dwTlsIndex
0x180008daa  call    cs:__imp_TlsSetValue
0x180008db1  nop     dword ptr [rax+rax+00h]
0x180008db6  test    eax, eax
0x180008db8  jnz     loc_180008AD3
0x180008dbe  call    cs:__imp_GetLastError
0x180008dc5  nop     dword ptr [rax+rax+00h]
0x180008dca  jmp     loc_180008AD3
```
