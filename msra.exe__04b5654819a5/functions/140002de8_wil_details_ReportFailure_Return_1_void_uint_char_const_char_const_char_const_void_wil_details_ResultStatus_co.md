# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140002de8`
- end: `0x140003091`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `681`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1400028ac`

## callees

- `0x140002463`
- `0x140002de8`
- `0x140004f04`
- `0x1400068b8`
- `0x140008d5c`
- `0x140009030`
- `0x14004ad80`
- `0x14004ae40`
- `0x14004d010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x140002f94`
- `KERNEL32!IsDebuggerPresent` at `0x140002f94`
- `KERNEL32!OutputDebugStringW` at `0x140003024`
- `KERNEL32!OutputDebugStringW` at `0x140003024`
- `KERNEL32!GetCurrentThreadId` at `0x140002e93`
- `KERNEL32!GetCurrentThreadId` at `0x140002e93`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v9; // ebx
  int v10; // ecx
  __int64 v11; // rdx
  const struct wil::FailureInfo *v12; // rdx
  wil::details::in1diag3 *v13; // rcx
  const struct wil::FailureInfo *v14; // r9
  bool v15; // zf
  int v16; // [rsp+20h] [rbp-E0h] BYREF
  int v17; // [rsp+24h] [rbp-DCh]
  int v18; // [rsp+28h] [rbp-D8h]
  int v19; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v20; // [rsp+30h] [rbp-D0h]
  __int64 v21; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v23; // [rsp+48h] [rbp-B8h]
  __int64 v24; // [rsp+50h] [rbp-B0h]
  const char *v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+60h] [rbp-A0h]
  int v27; // [rsp+64h] [rbp-9Ch]
  __int64 v28; // [rsp+68h] [rbp-98h]
  __int128 v29; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+80h] [rbp-80h]
  __int128 v31; // [rsp+88h] [rbp-78h]
  __int64 v32; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v34; // [rsp+A8h] [rbp-58h]
  __int64 v35; // [rsp+B0h] [rbp-50h]
  char v36[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v16, 0, 0x98u);
  OutputString[0] = 0;
  v36[0] = 0;
  v18 = *a7;
  v19 = a7[1];
  v9 = wil::details::RecordReturn((wil::details *)(unsigned int)v18, (int)a7);
  v16 = 1;
  v10 = 0;
  if ( *(_DWORD *)(v11 + 8) == 1 )
    v10 = 8;
  v17 = v10;
  v20 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v25 = "wil";
  v26 = a2;
  v27 = v9;
  v23 = 0;
  v24 = 0;
  v34 = a6;
  v35 = a1;
  v28 = 0;
  v31 = 0;
  v32 = 0;
  v29 = 0;
  v30 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v13);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v16, v36, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v16);
  if ( wil::details::g_pfnOriginateCallback && (v17 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v16);
  if ( v18 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v15 = !IsDebuggerPresent())
      : (v15 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v13) == 0),
        v15)
    || (v17 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v16, v14);
    OutputDebugStringW(OutputString);
  }
  if ( ((v17 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v13);
  if ( (v17 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v16, v12);
}

```

## disassembly

```asm
0x140002de8  mov     [rsp-8+arg_10], rbx
0x140002ded  push    rbp
0x140002dee  push    rsi
0x140002def  push    rdi
0x140002df0  push    r14
0x140002df2  push    r15
0x140002df4  lea     rbp, [rsp-13D0h]
0x140002dfc  mov     eax, 14D0h
0x140002e01  call    _alloca_probe
0x140002e06  sub     rsp, rax
0x140002e09  mov     rax, cs:__security_cookie
0x140002e10  xor     rax, rsp
0x140002e13  mov     [rbp+13F0h+var_30], rax
0x140002e1a  mov     esi, edx
0x140002e1c  mov     r14, rcx
0x140002e1f  mov     rdi, [rbp+13F0h+arg_28]
0x140002e26  xor     edx, edx; Val
0x140002e28  mov     r8d, 98h; Size
0x140002e2e  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x140002e33  call    memset_0
0x140002e38  nop
0x140002e39  xor     r15d, r15d
0x140002e3c  mov     [rbp+13F0h+OutputString], r15w
0x140002e44  mov     [rbp+13F0h+var_1430], r15b
0x140002e48  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x140002e4f  mov     ecx, [rdx]; this
0x140002e51  mov     [rsp+14F0h+var_14C8], ecx
0x140002e55  mov     eax, [rdx+4]
0x140002e58  mov     [rsp+14F0h+var_14C4], eax
0x140002e5c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140002e61  mov     ebx, eax
0x140002e63  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x140002e6b  mov     ecx, r15d
0x140002e6e  lea     eax, [r15+8]
0x140002e72  cmp     dword ptr [rdx+8], 1
0x140002e76  cmovz   ecx, eax
0x140002e79  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x140002e7d  lea     ecx, [rax-7]
0x140002e80  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140002e88  inc     ecx
0x140002e8a  mov     [rsp+14F0h+var_14C0], ecx
0x140002e8e  mov     [rsp+14F0h+var_14B8], r15
0x140002e93  call    cs:__imp_GetCurrentThreadId
0x140002e9a  nop     dword ptr [rax+rax+00h]
0x140002e9f  mov     [rsp+14F0h+var_14B0], eax
0x140002ea3  lea     rax, aWil; "wil"
0x140002eaa  mov     [rsp+14F0h+var_1498], rax
0x140002eaf  mov     [rsp+14F0h+var_1490], esi
0x140002eb3  mov     [rsp+14F0h+var_148C], ebx
0x140002eb7  mov     [rsp+14F0h+var_14A8], r15
0x140002ebc  mov     [rsp+14F0h+var_14A0], r15
0x140002ec1  mov     [rbp+13F0h+var_1448], rdi
0x140002ec5  mov     [rbp+13F0h+var_1440], r14
0x140002ec9  mov     [rsp+14F0h+var_1488], r15
0x140002ece  xorps   xmm0, xmm0
0x140002ed1  xor     eax, eax
0x140002ed3  movups  [rbp+13F0h+var_1468], xmm0
0x140002ed7  mov     [rbp+13F0h+var_1458], rax
0x140002edb  xorps   xmm1, xmm1
0x140002ede  movups  [rsp+14F0h+var_1480], xmm1
0x140002ee3  mov     [rbp+13F0h+var_1470], rax
0x140002ee7  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140002eee  test    rax, rax
0x140002ef1  jz      short loc_140002EFE
0x140002ef3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002ef8  mov     [rbp+13F0h+var_1450], rax
0x140002efc  jmp     short loc_140002F02
0x140002efe  mov     [rbp+13F0h+var_1450], r15
0x140002f02  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140002f09  test    rax, rax
0x140002f0c  jz      short loc_140002F18
0x140002f0e  lea     rcx, [rsp+14F0h+var_14D0]
0x140002f13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002f18  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140002f1f  test    rax, rax
0x140002f22  jz      short loc_140002F38
0x140002f24  mov     r8d, 400h
0x140002f2a  lea     rdx, [rbp+13F0h+var_1430]
0x140002f2e  lea     rcx, [rsp+14F0h+var_14D0]
0x140002f33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002f38  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002f3f  test    rax, rax
0x140002f42  jz      short loc_140002F4E
0x140002f44  lea     rcx, [rsp+14F0h+var_14D0]
0x140002f49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002f4e  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002f55  test    rax, rax
0x140002f58  jz      short loc_140002F6B
0x140002f5a  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140002f5f  jnz     short loc_140002F6B
0x140002f61  lea     rcx, [rsp+14F0h+var_14D0]
0x140002f66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002f6b  cmp     [rsp+14F0h+var_14C8], r15d
0x140002f70  jge     loc_14000308B
0x140002f76  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x140002f7d  jnz     short loc_140002FA4
0x140002f7f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140002f86  test    rax, rax
0x140002f89  jz      short loc_140002F94
0x140002f8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002f90  test    al, al
0x140002f92  jmp     short loc_140002FA2
0x140002f94  call    cs:__imp_IsDebuggerPresent
0x140002f9b  nop     dword ptr [rax+rax+00h]
0x140002fa0  test    eax, eax
0x140002fa2  jz      short loc_140002FAB
0x140002fa4  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140002fa9  jz      short loc_140002FD1
0x140002fab  mov     rax, cs:g_pfnResultLoggingCallback
0x140002fb2  test    rax, rax
0x140002fb5  jz      short loc_140003030
0x140002fb7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140002fbe  jnz     short loc_140003030
0x140002fc0  xor     r8d, r8d
0x140002fc3  xor     edx, edx
0x140002fc5  lea     rcx, [rsp+14F0h+var_14D0]
0x140002fca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002fcf  jmp     short loc_140003030
0x140002fd1  mov     ebx, 800h
0x140002fd6  mov     rax, cs:g_pfnResultLoggingCallback
0x140002fdd  test    rax, rax
0x140002fe0  jz      short loc_140002FFF
0x140002fe2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140002fe9  jnz     short loc_140002FFF
0x140002feb  mov     r8d, ebx
0x140002fee  lea     rdx, [rbp+13F0h+OutputString]
0x140002ff5  lea     rcx, [rsp+14F0h+var_14D0]
0x140002ffa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002fff  cmp     [rbp+13F0h+OutputString], r15w
0x140003007  jnz     short loc_14000301D
0x140003009  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x14000300e  mov     rdx, rbx; unsigned __int16 *
0x140003011  lea     rcx, [rbp+13F0h+OutputString]; this
0x140003018  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14000301d  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x140003024  call    cs:__imp_OutputDebugStringW
0x14000302b  nop     dword ptr [rax+rax+00h]
0x140003030  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x140003035  jnz     short loc_140003040
0x140003037  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x14000303e  jz      short loc_140003052
0x140003040  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140003047  test    rax, rax
0x14000304a  jz      short loc_140003052
0x14000304c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003051  nop
0x140003052  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x140003057  jnz     short loc_140003080
0x140003059  mov     rcx, [rbp+13F0h+var_30]
0x140003060  xor     rcx, rsp; StackCookie
0x140003063  call    __security_check_cookie
0x140003068  mov     rbx, [rsp+14F0h+arg_10]
0x140003070  add     rsp, 14D0h
0x140003077  pop     r15
0x140003079  pop     r14
0x14000307b  pop     rdi
0x14000307c  pop     rsi
0x14000307d  pop     rbp
0x14000307e  retn
0x140003080  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140003085  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x14000308b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
