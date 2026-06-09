# CRpcCallTrace::CRpcCallTrace(int,char const *)

- ea: `0x180014c00`
- end: `0x180014f2f`
- name: `??0CRpcCallTrace@@QEAA@HPEBD@Z`
- size: `815`
- prototype: `CRpcCallTrace *__fastcall(CRpcCallTrace *__hidden this, int, const char *)`
- caller_count: `46`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000e690`
- `0x180014250`
- `0x180014300`
- `0x1800145c0`
- `0x180014950`
- `0x180015750`
- `0x180016340`
- `0x180016960`
- `0x180016a90`
- `0x18001fef0`
- `0x180029930`
- `0x18002e110`
- `0x180030790`
- `0x180030b90`
- `0x180031050`
- `0x1800575f0`
- `0x180057920`
- `0x180057ab0`
- `0x180057c40`
- `0x180057ff0`
- `0x1800580c0`
- `0x180058180`
- `0x18005ac9c`
- `0x18005b080`
- `0x18005ba40`
- `0x18005bc50`
- `0x18005c020`
- `0x18005c120`
- `0x18005c2e0`
- `0x18005c480`
- `0x18005c570`
- `0x18005c660`
- `0x18005c770`
- `0x18005caf0`
- `0x18005d000`
- `0x18005d9c0`
- `0x18005dbb0`
- `0x18005ddc0`
- `0x18005df00`
- `0x18005e050`
- `0x18005e560`
- `0x18005e640`
- `0x18005e810`
- `0x18005eae0`
- `0x18005ecb0`
- `0x18005ef70`

## callees

- `0x1800074c0`
- `0x18000b190`
- `0x18000c700`
- `0x180014c00`
- `0x18001aa50`
- `0x1800271d0`
- `0x18004b460`
- `0x18004bf44`
- `0x180097010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180014ef5`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180014ef5`
- `ntdll!NtQueryInformationProcess` at `0x180014edb`
- `ntdll!NtQueryInformationProcess` at `0x180014edb`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180014ce5`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180014ce5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014f1c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014f1c`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180014c5d`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180014c5d`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180014cce`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180014cce`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180014eb5`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180014eb5`

## string_xrefs

- `0x180014e0f`: `TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC`
- `0x180014d71`: `RPC Caller: PID %d, SessID %d, Process Name: <%S>`

## pseudocode

```c
CRpcCallTrace *__fastcall CRpcCallTrace::CRpcCallTrace(CRpcCallTrace *this, int a2, const char *a3)
{
  _DWORD *v6; // r14
  unsigned int v7; // r14d
  RPC_STATUS v8; // eax
  int v9; // ebp
  const char *v11; // rax
  __int64 v12; // rcx
  HANDLE v13; // rax
  void *v14; // r12
  NTSTATUS InformationProcess; // eax
  wchar_t *v16; // rax
  wchar_t *v17; // rax
  struct CTraceBase *v18; // [rsp+30h] [rbp-168h] BYREF
  _BYTE ProcessInformation[8]; // [rsp+40h] [rbp-158h] BYREF
  wchar_t *Str; // [rsp+48h] [rbp-150h]

  *(_QWORD *)this = &CTraceBase::`vftable';
  *((_QWORD *)this + 4) = 0;
  *((_DWORD *)this + 7) = 1;
  if ( CTraceBase::g_bEnabled )
  {
    if ( (g_DebugTraceComponent & 1) != 0 )
    {
      v11 = a3;
      if ( !a3 )
        v11 = "null";
      _DbgPrintMessage(2, "Adding trace %p, %d, %s", this, 1, v11);
    }
    v18 = 0;
    if ( (int)CTraceBase::GetThreadCurrentOperationTrace(&v18) >= 0 && v18 && (g_DebugTraceComponent & 1) != 0 )
      _DbgPrintMessage(
        2,
        "TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC",
        1);
    CTraceBase::ResetThreadCurrentOperationTrace(0, 0);
    if ( (int)CTraceBase::GetThreadCurrentOperationTrace((struct CTraceBase **)this + 4) >= 0 )
    {
      v12 = *((_QWORD *)this + 4);
      if ( v12 )
      {
        (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v12 + 32LL))(v12, (char *)this + 8);
        v6 = (_DWORD *)((char *)this + 24);
        *((_DWORD *)this + 6) = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 24LL))(*((_QWORD *)this + 4));
        *((_DWORD *)this + 10) = 1;
        goto LABEL_4;
      }
    }
    CTraceBase::ResetThreadCurrentOperationTrace(this, a3);
    v6 = (_DWORD *)((char *)this + 24);
    CTraceBase::GenerateTraceID((struct _GUID *)((char *)this + 8), (unsigned int *)this + 6);
  }
  else
  {
    CoCreateGuid((GUID *)((char *)this + 8));
    v6 = (_DWORD *)((char *)this + 24);
    *((_DWORD *)this + 6) = _InterlockedIncrement((volatile signed __int32 *)&CTraceBase::g_NextShortActivityID);
  }
  *((_DWORD *)this + 10) = 0;
LABEL_4:
  *((_DWORD *)this + 16) = a2;
  *(_QWORD *)this = &CRpcCallTrace::`vftable';
  *((_QWORD *)this + 6) = a3;
  *((_QWORD *)this + 7) = -1;
  memset_0((char *)this + 68, 0, 0x208u);
  if ( *((_DWORD *)this + 16) && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "TRACE RPC %s with Trace ID 0x%x", *((const char **)this + 6), *v6);
  v7 = 0;
  if ( (g_DebugTraceComponent & 1) != 0 )
    v7 = 260;
  *((_QWORD *)this + 7) = -1;
  v8 = I_RpcBindingInqLocalClientPID(0, (unsigned int *)this + 15);
  v9 = v8;
  if ( v8 > 0 )
    v9 = (unsigned __int16)v8 | 0x80070000;
  if ( v9 >= 0 )
  {
    ProcessIdToSessionId(*((_DWORD *)this + 15), (DWORD *)this + 14);
    if ( v7 )
    {
      if ( this != (CRpcCallTrace *)-68LL )
      {
        v13 = OpenProcess(0x400u, 0, *((_DWORD *)this + 15));
        v14 = v13;
        if ( v13 )
        {
          InformationProcess = NtQueryInformationProcess(v13, ProcessImageFileName, ProcessInformation, 0x110u, 0);
          v9 = InformationProcess | 0x10000000;
          if ( InformationProcess >= 0 )
          {
            v16 = wcsrchr(Str, 0x5Cu);
            if ( v16 )
              v17 = v16 + 1;
            else
              v17 = Str;
            StringCchCopyW((unsigned __int16 *)this + 34, v7, v17);
          }
          CloseHandle(v14);
        }
      }
    }
  }
  if ( *((_DWORD *)this + 16) )
  {
    if ( v9 < 0 )
    {
      if ( (g_DebugTraceComponent & 1) != 0 )
        _DbgPrintMessage(2, "RPC Caller: Unknown");
    }
    else if ( (g_DebugTraceComponent & 1) != 0 )
    {
      _DbgPrintMessage(
        2,
        "RPC Caller: PID %d, SessID %d, Process Name: <%S>",
        *((_DWORD *)this + 15),
        *((_DWORD *)this + 14),
        (const wchar_t *)this + 34);
    }
  }
  return this;
}

```

## disassembly

```asm
0x180014c00  mov     r11, rsp
0x180014c03  push    rbx
0x180014c04  push    rbp
0x180014c05  push    rsi
0x180014c06  push    rdi
0x180014c07  push    r15
0x180014c09  sub     rsp, 170h
0x180014c10  mov     rax, cs:__security_cookie
0x180014c17  xor     rax, rsp
0x180014c1a  mov     [rsp+198h+var_48], rax
0x180014c22  mov     [r11-30h], r13
0x180014c26  lea     rax, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x180014c2d  xor     r13d, r13d
0x180014c30  mov     [rcx], rax
0x180014c33  mov     edi, 1
0x180014c38  mov     [rcx+20h], r13
0x180014c3c  mov     [rcx+1Ch], edi
0x180014c3f  mov     rbp, r8
0x180014c42  cmp     cs:?g_bEnabled@CTraceBase@@0HA, r13d; int CTraceBase::g_bEnabled
0x180014c49  mov     r15d, edx
0x180014c4c  mov     [r11-38h], r14
0x180014c50  mov     rbx, rcx
0x180014c53  jnz     loc_180014DB3
0x180014c59  add     rcx, 8; pguid
0x180014c5d  call    cs:__imp_CoCreateGuid
0x180014c63  lea     r14, [rbx+18h]
0x180014c67  lock xadd cs:?g_NextShortActivityID@CTraceBase@@0KA, edi; ulong CTraceBase::g_NextShortActivityID
0x180014c6f  inc     edi
0x180014c71  mov     [r14], edi
0x180014c74  mov     [rbx+28h], r13d
0x180014c78  mov     [rbx+40h], r15d
0x180014c7c  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x180014c83  lea     r15, [rbx+44h]
0x180014c87  mov     [rbx], rax
0x180014c8a  mov     rcx, r15; void *
0x180014c8d  mov     [rbx+30h], rbp
0x180014c91  xor     edx, edx; Val
0x180014c93  mov     qword ptr [rbx+38h], 0FFFFFFFFFFFFFFFFh
0x180014c9b  mov     r8d, 208h; Size
0x180014ca1  call    memset_0
0x180014ca6  cmp     [rbx+40h], r13d
0x180014caa  jnz     loc_180014D36
0x180014cb0  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x180014cb7  mov     r14d, r13d
0x180014cba  jnz     loc_180014E8E
0x180014cc0  lea     rdx, [rbx+3Ch]; Pid
0x180014cc4  mov     qword ptr [rbx+38h], 0FFFFFFFFFFFFFFFFh
0x180014ccc  xor     ecx, ecx; Binding
0x180014cce  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x180014cd4  mov     ebp, eax
0x180014cd6  test    eax, eax
0x180014cd8  jg      short loc_180014D2B
0x180014cda  test    ebp, ebp
0x180014cdc  js      short loc_180014CF4
0x180014cde  mov     ecx, [rbx+3Ch]; dwProcessId
0x180014ce1  lea     rdx, [rbx+38h]; pSessionId
0x180014ce5  call    cs:__imp_ProcessIdToSessionId
0x180014ceb  test    r14d, r14d
0x180014cee  jnz     loc_180014E99
0x180014cf4  cmp     dword ptr [rbx+40h], 0
0x180014cf8  mov     r14, [rsp+198h+var_38]
0x180014d00  mov     r13, [rsp+198h+var_30]
0x180014d08  jnz     short loc_180014D60
0x180014d0a  mov     rax, rbx
0x180014d0d  mov     rcx, [rsp+198h+var_48]
0x180014d15  xor     rcx, rsp; StackCookie
0x180014d18  call    __security_check_cookie
0x180014d1d  add     rsp, 170h
0x180014d24  pop     r15
0x180014d26  pop     rdi
0x180014d27  pop     rsi
0x180014d28  pop     rbp
0x180014d29  pop     rbx
0x180014d2a  retn
0x180014d2b  movzx   ebp, ax
0x180014d2e  or      ebp, 80070000h
0x180014d34  jmp     short loc_180014CDA
0x180014d36  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x180014d3d  jz      loc_180014CB0
0x180014d43  mov     r9d, [r14]
0x180014d46  lea     rdx, aTraceRpcSWithT; "TRACE RPC %s with Trace ID 0x%x"
0x180014d4d  mov     r8, [rbx+30h]
0x180014d51  mov     ecx, 2; int
0x180014d56  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180014d5b  jmp     loc_180014CB0
0x180014d60  test    ebp, ebp
0x180014d62  js      short loc_180014D90
0x180014d64  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x180014d6b  jz      short loc_180014D0A
0x180014d6d  mov     r9d, [rbx+38h]
0x180014d71  lea     rdx, aRpcCallerPidDS; "RPC Caller: PID %d, SessID %d, Process "...
0x180014d78  mov     r8d, [rbx+3Ch]
0x180014d7c  mov     ecx, 2; int
0x180014d81  mov     [rsp+198h+ReturnLength], r15
0x180014d86  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180014d8b  jmp     loc_180014D0A
0x180014d90  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x180014d97  jz      loc_180014D0A
0x180014d9d  lea     rdx, aRpcCallerUnkno; "RPC Caller: Unknown"
0x180014da4  mov     ecx, 2; int
0x180014da9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180014dae  jmp     loc_180014D0A
0x180014db3  test    byte ptr cs:?g_DebugTraceComponent@@3KA, dil; ulong g_DebugTraceComponent
0x180014dba  jz      short loc_180014DE9
0x180014dbc  lea     rcx, aNull; "null"
0x180014dc3  test    rbp, rbp
0x180014dc6  mov     rax, rbp
0x180014dc9  lea     rdx, aAddingTracePDS; "Adding trace %p, %d, %s"
0x180014dd0  cmovz   rax, rcx
0x180014dd4  mov     r9d, edi
0x180014dd7  mov     ecx, 2; int
0x180014ddc  mov     [rsp+198h+ReturnLength], rax
0x180014de1  mov     r8, rbx
0x180014de4  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180014de9  lea     rcx, [rsp+198h+var_168]; struct CTraceBase **
0x180014dee  mov     [rsp+198h+var_168], r13
0x180014df3  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x180014df8  test    eax, eax
0x180014dfa  js      short loc_180014E20
0x180014dfc  cmp     [rsp+198h+var_168], r13
0x180014e01  jz      short loc_180014E20
0x180014e03  test    byte ptr cs:?g_DebugTraceComponent@@3KA, dil; ulong g_DebugTraceComponent
0x180014e0a  jz      short loc_180014E20
0x180014e0c  mov     r8d, edi
0x180014e0f  lea     rdx, aTracecomponent; "TraceComponent %d: Warning TLS should b"...
0x180014e16  mov     ecx, 2; int
0x180014e1b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180014e20  xor     edx, edx; char *
0x180014e22  xor     ecx, ecx; lpTlsValue
0x180014e24  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x180014e29  lea     rcx, [rbx+20h]; struct CTraceBase **
0x180014e2d  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x180014e32  test    eax, eax
0x180014e34  js      short loc_180014E6E
0x180014e36  mov     rcx, [rbx+20h]
0x180014e3a  test    rcx, rcx
0x180014e3d  jz      short loc_180014E6E
0x180014e3f  mov     rax, [rcx]
0x180014e42  lea     rdx, [rbx+8]
0x180014e46  mov     rax, [rax+20h]
0x180014e4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e4f  mov     rcx, [rbx+20h]
0x180014e53  lea     r14, [rbx+18h]
0x180014e57  mov     rax, [rcx]
0x180014e5a  mov     rax, [rax+18h]
0x180014e5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e63  mov     [r14], eax
0x180014e66  mov     [rbx+28h], edi
0x180014e69  jmp     loc_180014C78
0x180014e6e  mov     rdx, rbp; char *
0x180014e71  mov     rcx, rbx; lpTlsValue
0x180014e74  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x180014e79  lea     r14, [rbx+18h]
0x180014e7d  mov     rdx, r14; unsigned int *
0x180014e80  lea     rcx, [rbx+8]; struct _GUID *
0x180014e84  call    ?GenerateTraceID@CTraceBase@@KAJPEAU_GUID@@PEAK@Z; CTraceBase::GenerateTraceID(_GUID *,ulong *)
0x180014e89  jmp     loc_180014C74
0x180014e8e  mov     r14d, 104h
0x180014e94  jmp     loc_180014CC0
0x180014e99  test    r15, r15
0x180014e9c  jz      loc_180014CF4
0x180014ea2  mov     r8d, [rbx+3Ch]; dwProcessId
0x180014ea6  xor     edx, edx; bInheritHandle
0x180014ea8  mov     ecx, 400h; dwDesiredAccess
0x180014ead  mov     [rsp+198h+arg_8], r12
0x180014eb5  call    cs:__imp_OpenProcess
0x180014ebb  mov     r12, rax
0x180014ebe  test    rax, rax
0x180014ec1  jz      short loc_180014F22
0x180014ec3  mov     r9d, 110h; ProcessInformationLength
0x180014ec9  mov     [rsp+198h+ReturnLength], r13; ReturnLength
0x180014ece  lea     r8, [rsp+198h+ProcessInformation]; ProcessInformation
0x180014ed3  mov     edx, 1Bh; ProcessInformationClass
0x180014ed8  mov     rcx, rax; ProcessHandle
0x180014edb  call    cs:__imp_NtQueryInformationProcess
0x180014ee1  mov     ebp, eax
0x180014ee3  or      ebp, 10000000h
0x180014ee9  jl      short loc_180014F19
0x180014eeb  mov     rcx, [rsp+198h+Str]; Str
0x180014ef0  mov     edx, 5Ch ; '\'; Ch
0x180014ef5  call    cs:__imp_wcsrchr
0x180014efb  test    rax, rax
0x180014efe  jnz     short loc_180014F07
0x180014f00  mov     rax, [rsp+198h+Str]
0x180014f05  jmp     short loc_180014F0B
0x180014f07  add     rax, 2
0x180014f0b  mov     edx, r14d; unsigned __int64
0x180014f0e  mov     r8, rax; unsigned __int16 *
0x180014f11  mov     rcx, r15; unsigned __int16 *
0x180014f14  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180014f19  mov     rcx, r12; hObject
0x180014f1c  call    cs:__imp_CloseHandle
0x180014f22  mov     r12, [rsp+198h+arg_8]
0x180014f2a  jmp     loc_180014CF4
```
