# CRpcCallTrace::CRpcCallTrace(int,char const *)

- ea: `0x18000e8b0`
- end: `0x18000ec0a`
- name: `??0CRpcCallTrace@@QEAA@HPEBD@Z`
- size: `858`
- prototype: `CRpcCallTrace *__fastcall(CRpcCallTrace *__hidden this, int, const char *)`
- caller_count: `46`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000cc20`
- `0x18000cfb0`
- `0x18000d510`
- `0x18000db70`
- `0x18000dea0`
- `0x18000df50`
- `0x18000e210`
- `0x18000e5f0`
- `0x18000fa20`
- `0x18000ffb0`
- `0x180020b00`
- `0x180022290`
- `0x1800327e0`
- `0x180032be0`
- `0x1800330c0`
- `0x18005aef0`
- `0x18005b240`
- `0x18005b3d0`
- `0x18005b560`
- `0x18005b910`
- `0x18005b9e0`
- `0x18005bab0`
- `0x18005e678`
- `0x18005ea70`
- `0x18005f480`
- `0x18005f690`
- `0x18005fa60`
- `0x18005fb70`
- `0x18005fd30`
- `0x18005fea0`
- `0x18005ff90`
- `0x180060080`
- `0x180060190`
- `0x180060530`
- `0x180060a60`
- `0x180061450`
- `0x180061650`
- `0x180061860`
- `0x1800619a0`
- `0x180061af0`
- `0x180062030`
- `0x180062120`
- `0x180062300`
- `0x1800625d0`
- `0x1800627a0`
- `0x180062a60`

## callees

- `0x1800077a0`
- `0x180009580`
- `0x18000e8b0`
- `0x1800101b0`
- `0x180010260`
- `0x180029158`
- `0x18004e850`
- `0x18004f354`
- `0x18009c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000ebc4`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000ebc4`
- `ntdll!NtQueryInformationProcess` at `0x18000eba4`
- `ntdll!NtQueryInformationProcess` at `0x18000eba4`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000e9a1`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000e9a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ebf1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ebf1`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000e90d`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000e90d`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000e984`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000e984`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000eb78`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000eb78`

## string_xrefs

- `0x18000ead2`: `TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC`
- `0x18000ea34`: `RPC Caller: PID %d, SessID %d, Process Name: <%S>`

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
0x18000e8b0  mov     r11, rsp
0x18000e8b3  push    rbx
0x18000e8b4  push    rbp
0x18000e8b5  push    rsi
0x18000e8b6  push    rdi
0x18000e8b7  push    r15
0x18000e8b9  sub     rsp, 170h
0x18000e8c0  mov     rax, cs:__security_cookie
0x18000e8c7  xor     rax, rsp
0x18000e8ca  mov     [rsp+198h+var_48], rax
0x18000e8d2  mov     [r11-30h], r13
0x18000e8d6  lea     rax, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x18000e8dd  xor     r13d, r13d
0x18000e8e0  mov     [rcx], rax
0x18000e8e3  mov     edi, 1
0x18000e8e8  mov     [rcx+20h], r13
0x18000e8ec  mov     [rcx+1Ch], edi
0x18000e8ef  mov     rbp, r8
0x18000e8f2  cmp     cs:?g_bEnabled@CTraceBase@@0HA, r13d; int CTraceBase::g_bEnabled
0x18000e8f9  mov     r15d, edx
0x18000e8fc  mov     [r11-38h], r14
0x18000e900  mov     rbx, rcx
0x18000e903  jnz     loc_18000EA76
0x18000e909  add     rcx, 8; pguid
0x18000e90d  call    cs:__imp_CoCreateGuid
0x18000e914  nop     dword ptr [rax+rax+00h]
0x18000e919  lea     r14, [rbx+18h]
0x18000e91d  lock xadd cs:?g_NextShortActivityID@CTraceBase@@0KA, edi; ulong CTraceBase::g_NextShortActivityID
0x18000e925  inc     edi
0x18000e927  mov     [r14], edi
0x18000e92a  mov     [rbx+28h], r13d
0x18000e92e  mov     [rbx+40h], r15d
0x18000e932  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x18000e939  lea     r15, [rbx+44h]
0x18000e93d  mov     [rbx], rax
0x18000e940  mov     rcx, r15; void *
0x18000e943  mov     [rbx+30h], rbp
0x18000e947  xor     edx, edx; Val
0x18000e949  mov     qword ptr [rbx+38h], 0FFFFFFFFFFFFFFFFh
0x18000e951  mov     r8d, 208h; Size
0x18000e957  call    memset_0
0x18000e95c  cmp     [rbx+40h], r13d
0x18000e960  jnz     loc_18000E9F9
0x18000e966  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000e96d  mov     r14d, r13d
0x18000e970  jnz     loc_18000EB51
0x18000e976  lea     rdx, [rbx+3Ch]; Pid
0x18000e97a  mov     qword ptr [rbx+38h], 0FFFFFFFFFFFFFFFFh
0x18000e982  xor     ecx, ecx; Binding
0x18000e984  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18000e98b  nop     dword ptr [rax+rax+00h]
0x18000e990  mov     ebp, eax
0x18000e992  test    eax, eax
0x18000e994  jg      short loc_18000E9EE
0x18000e996  test    ebp, ebp
0x18000e998  js      short loc_18000E9B6
0x18000e99a  mov     ecx, [rbx+3Ch]; dwProcessId
0x18000e99d  lea     rdx, [rbx+38h]; pSessionId
0x18000e9a1  call    cs:__imp_ProcessIdToSessionId
0x18000e9a8  nop     dword ptr [rax+rax+00h]
0x18000e9ad  test    r14d, r14d
0x18000e9b0  jnz     loc_18000EB5C
0x18000e9b6  cmp     dword ptr [rbx+40h], 0
0x18000e9ba  mov     r14, [rsp+198h+var_38]
0x18000e9c2  mov     r13, [rsp+198h+var_30]
0x18000e9ca  jnz     short loc_18000EA23
0x18000e9cc  mov     rax, rbx
0x18000e9cf  mov     rcx, [rsp+198h+var_48]
0x18000e9d7  xor     rcx, rsp; StackCookie
0x18000e9da  call    __security_check_cookie
0x18000e9df  add     rsp, 170h
0x18000e9e6  pop     r15
0x18000e9e8  pop     rdi
0x18000e9e9  pop     rsi
0x18000e9ea  pop     rbp
0x18000e9eb  pop     rbx
0x18000e9ec  retn
0x18000e9ee  movzx   ebp, ax
0x18000e9f1  or      ebp, 80070000h
0x18000e9f7  jmp     short loc_18000E996
0x18000e9f9  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000ea00  jz      loc_18000E966
0x18000ea06  mov     r9d, [r14]
0x18000ea09  lea     rdx, aTraceRpcSWithT; "TRACE RPC %s with Trace ID 0x%x"
0x18000ea10  mov     r8, [rbx+30h]
0x18000ea14  mov     ecx, 2; int
0x18000ea19  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000ea1e  jmp     loc_18000E966
0x18000ea23  test    ebp, ebp
0x18000ea25  js      short loc_18000EA53
0x18000ea27  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000ea2e  jz      short loc_18000E9CC
0x18000ea30  mov     r9d, [rbx+38h]
0x18000ea34  lea     rdx, aRpcCallerPidDS; "RPC Caller: PID %d, SessID %d, Process "...
0x18000ea3b  mov     r8d, [rbx+3Ch]
0x18000ea3f  mov     ecx, 2; int
0x18000ea44  mov     [rsp+198h+ReturnLength], r15
0x18000ea49  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000ea4e  jmp     loc_18000E9CC
0x18000ea53  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000ea5a  jz      loc_18000E9CC
0x18000ea60  lea     rdx, aRpcCallerUnkno; "RPC Caller: Unknown"
0x18000ea67  mov     ecx, 2; int
0x18000ea6c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000ea71  jmp     loc_18000E9CC
0x18000ea76  test    byte ptr cs:?g_DebugTraceComponent@@3KA, dil; ulong g_DebugTraceComponent
0x18000ea7d  jz      short loc_18000EAAC
0x18000ea7f  lea     rcx, aNull; "null"
0x18000ea86  test    rbp, rbp
0x18000ea89  mov     rax, rbp
0x18000ea8c  lea     rdx, aAddingTracePDS; "Adding trace %p, %d, %s"
0x18000ea93  cmovz   rax, rcx
0x18000ea97  mov     r9d, edi
0x18000ea9a  mov     ecx, 2; int
0x18000ea9f  mov     [rsp+198h+ReturnLength], rax
0x18000eaa4  mov     r8, rbx
0x18000eaa7  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000eaac  lea     rcx, [rsp+198h+var_168]; struct CTraceBase **
0x18000eab1  mov     [rsp+198h+var_168], r13
0x18000eab6  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x18000eabb  test    eax, eax
0x18000eabd  js      short loc_18000EAE3
0x18000eabf  cmp     [rsp+198h+var_168], r13
0x18000eac4  jz      short loc_18000EAE3
0x18000eac6  test    byte ptr cs:?g_DebugTraceComponent@@3KA, dil; ulong g_DebugTraceComponent
0x18000eacd  jz      short loc_18000EAE3
0x18000eacf  mov     r8d, edi
0x18000ead2  lea     rdx, aTracecomponent; "TraceComponent %d: Warning TLS should b"...
0x18000ead9  mov     ecx, 2; int
0x18000eade  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000eae3  xor     edx, edx; char *
0x18000eae5  xor     ecx, ecx; lpTlsValue
0x18000eae7  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x18000eaec  lea     rcx, [rbx+20h]; struct CTraceBase **
0x18000eaf0  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x18000eaf5  test    eax, eax
0x18000eaf7  js      short loc_18000EB31
0x18000eaf9  mov     rcx, [rbx+20h]
0x18000eafd  test    rcx, rcx
0x18000eb00  jz      short loc_18000EB31
0x18000eb02  mov     rax, [rcx]
0x18000eb05  lea     rdx, [rbx+8]
0x18000eb09  mov     rax, [rax+20h]
0x18000eb0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb12  mov     rcx, [rbx+20h]
0x18000eb16  lea     r14, [rbx+18h]
0x18000eb1a  mov     rax, [rcx]
0x18000eb1d  mov     rax, [rax+18h]
0x18000eb21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb26  mov     [r14], eax
0x18000eb29  mov     [rbx+28h], edi
0x18000eb2c  jmp     loc_18000E92E
0x18000eb31  mov     rdx, rbp; char *
0x18000eb34  mov     rcx, rbx; lpTlsValue
0x18000eb37  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x18000eb3c  lea     r14, [rbx+18h]
0x18000eb40  mov     rdx, r14; unsigned int *
0x18000eb43  lea     rcx, [rbx+8]; struct _GUID *
0x18000eb47  call    ?GenerateTraceID@CTraceBase@@KAJPEAU_GUID@@PEAK@Z; CTraceBase::GenerateTraceID(_GUID *,ulong *)
0x18000eb4c  jmp     loc_18000E92A
0x18000eb51  mov     r14d, 104h
0x18000eb57  jmp     loc_18000E976
0x18000eb5c  test    r15, r15
0x18000eb5f  jz      loc_18000E9B6
0x18000eb65  mov     r8d, [rbx+3Ch]; dwProcessId
0x18000eb69  xor     edx, edx; bInheritHandle
0x18000eb6b  mov     ecx, 400h; dwDesiredAccess
0x18000eb70  mov     [rsp+198h+arg_8], r12
0x18000eb78  call    cs:__imp_OpenProcess
0x18000eb7f  nop     dword ptr [rax+rax+00h]
0x18000eb84  mov     r12, rax
0x18000eb87  test    rax, rax
0x18000eb8a  jz      short loc_18000EBFD
0x18000eb8c  mov     r9d, 110h; ProcessInformationLength
0x18000eb92  mov     [rsp+198h+ReturnLength], r13; ReturnLength
0x18000eb97  lea     r8, [rsp+198h+ProcessInformation]; ProcessInformation
0x18000eb9c  mov     edx, 1Bh; ProcessInformationClass
0x18000eba1  mov     rcx, rax; ProcessHandle
0x18000eba4  call    cs:__imp_NtQueryInformationProcess
0x18000ebab  nop     dword ptr [rax+rax+00h]
0x18000ebb0  mov     ebp, eax
0x18000ebb2  or      ebp, 10000000h
0x18000ebb8  jl      short loc_18000EBEE
0x18000ebba  mov     rcx, [rsp+198h+Str]; Str
0x18000ebbf  mov     edx, 5Ch ; '\'; Ch
0x18000ebc4  call    cs:__imp_wcsrchr
0x18000ebcb  nop     dword ptr [rax+rax+00h]
0x18000ebd0  test    rax, rax
0x18000ebd3  jnz     short loc_18000EBDC
0x18000ebd5  mov     rax, [rsp+198h+Str]
0x18000ebda  jmp     short loc_18000EBE0
0x18000ebdc  add     rax, 2
0x18000ebe0  mov     edx, r14d; unsigned __int64
0x18000ebe3  mov     r8, rax; unsigned __int16 *
0x18000ebe6  mov     rcx, r15; unsigned __int16 *
0x18000ebe9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000ebee  mov     rcx, r12; hObject
0x18000ebf1  call    cs:__imp_CloseHandle
0x18000ebf8  nop     dword ptr [rax+rax+00h]
0x18000ebfd  mov     r12, [rsp+198h+arg_8]
0x18000ec05  jmp     loc_18000E9B6
```
