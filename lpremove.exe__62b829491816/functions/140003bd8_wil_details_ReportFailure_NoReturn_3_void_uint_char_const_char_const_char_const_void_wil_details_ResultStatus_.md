# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x140003bd8`
- end: `0x140003e51`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, __int64, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1400036a0`

## callees

- `0x140002c2c`
- `0x140003bd8`
- `0x1400073e4`
- `0x140007cd4`
- `0x1400095c0`
- `0x14000cad0`
- `0x14000fe00`
- `0x140011010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140003c91`
- `KERNEL32!GetCurrentThreadId` at `0x140003c91`
- `KERNEL32!IsDebuggerPresent` at `0x140003d94`
- `KERNEL32!IsDebuggerPresent` at `0x140003d94`
- `KERNEL32!OutputDebugStringW` at `0x140003e1e`
- `KERNEL32!OutputDebugStringW` at `0x140003e1e`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v11; // edx
  int v12; // r12d
  int v13; // ecx
  const struct wil::FailureInfo *v14; // rdx
  __int64 v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh]
  int v20; // [rsp+28h] [rbp-D8h]
  int v21; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v22; // [rsp+30h] [rbp-D0h]
  _WORD *v23; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+48h] [rbp-B8h]
  __int64 v26; // [rsp+50h] [rbp-B0h]
  __int64 v27; // [rsp+58h] [rbp-A8h]
  int v28; // [rsp+60h] [rbp-A0h]
  int v29; // [rsp+64h] [rbp-9Ch]
  __int64 v30; // [rsp+68h] [rbp-98h]
  __int128 v31; // [rsp+70h] [rbp-90h]
  __int64 v32; // [rsp+80h] [rbp-80h]
  __int128 v33; // [rsp+88h] [rbp-78h]
  __int64 v34; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v36; // [rsp+A8h] [rbp-58h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  char v38[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v12 = wil::details::RecordFailFast((wil::details *)(unsigned int)v20, v11);
  v18 = 3;
  v13 = 0;
  if ( a7[2] == 1 )
    v13 = 8;
  v19 = v13;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v12;
  v25 = 0;
  v26 = 0;
  v36 = a6;
  v37 = a1;
  v30 = 0;
  v33 = 0;
  v34 = 0;
  v31 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v18);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v18, v38, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v18);
  if ( wil::details::g_pfnOriginateCallback && (v19 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v18);
  if ( v20 >= 0 )
  {
    v20 = -2147418113;
    v21 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v14);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v19 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v18, v16);
    OutputDebugStringW(OutputString);
  }
  if ( (v19 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v15);
  }
  wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x140003bd8  mov     [rsp-8+arg_18], rbx
0x140003bdd  push    rbp
0x140003bde  push    rsi
0x140003bdf  push    rdi
0x140003be0  push    r12
0x140003be2  push    r13
0x140003be4  push    r14
0x140003be6  push    r15
0x140003be8  lea     rbp, [rsp-13C0h]
0x140003bf0  mov     eax, 14C0h
0x140003bf5  call    _alloca_probe
0x140003bfa  sub     rsp, rax
0x140003bfd  mov     r14, r8
0x140003c00  mov     esi, edx
0x140003c02  mov     rdi, rcx
0x140003c05  mov     r15, [rbp+13F0h+arg_28]
0x140003c0c  xor     edx, edx; Val
0x140003c0e  mov     r8d, 98h; Size
0x140003c14  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x140003c19  call    memset_0
0x140003c1e  nop
0x140003c1f  xor     r13d, r13d
0x140003c22  mov     [rbp+13F0h+OutputString], r13w
0x140003c2a  mov     [rbp+13F0h+var_1430], r13b
0x140003c2e  mov     rbx, [rbp+13F0h+arg_30]
0x140003c35  mov     ecx, [rbx]; this
0x140003c37  mov     [rsp+14F0h+var_14C8], ecx
0x140003c3b  mov     eax, [rbx+4]
0x140003c3e  mov     [rsp+14F0h+var_14C4], eax
0x140003c42  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140003c47  mov     r12d, eax
0x140003c4a  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x140003c52  mov     ecx, r13d
0x140003c55  lea     eax, [r13+8]
0x140003c59  cmp     dword ptr [rbx+8], 1
0x140003c5d  cmovz   ecx, eax
0x140003c60  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x140003c64  lea     ecx, [rax-7]
0x140003c67  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140003c6f  inc     ecx
0x140003c71  mov     [rsp+14F0h+var_14C0], ecx
0x140003c75  mov     rcx, [rbp+13F0h+arg_38]
0x140003c7c  test    rcx, rcx
0x140003c7f  jz      short loc_140003C8C
0x140003c81  cmp     [rcx], r13w
0x140003c85  mov     [rsp+14F0h+var_14B8], rcx
0x140003c8a  jnz     short loc_140003C91
0x140003c8c  mov     [rsp+14F0h+var_14B8], r13
0x140003c91  call    cs:__imp_GetCurrentThreadId
0x140003c97  mov     [rsp+14F0h+var_14B0], eax
0x140003c9b  mov     [rsp+14F0h+var_1498], r14
0x140003ca0  mov     [rsp+14F0h+var_1490], esi
0x140003ca4  mov     [rsp+14F0h+var_148C], r12d
0x140003ca9  mov     [rsp+14F0h+var_14A8], r13
0x140003cae  mov     [rsp+14F0h+var_14A0], r13
0x140003cb3  mov     [rbp+13F0h+var_1448], r15
0x140003cb7  mov     [rbp+13F0h+var_1440], rdi
0x140003cbb  mov     [rsp+14F0h+var_1488], r13
0x140003cc0  xorps   xmm0, xmm0
0x140003cc3  xor     eax, eax
0x140003cc5  movups  [rbp+13F0h+var_1468], xmm0
0x140003cc9  mov     [rbp+13F0h+var_1458], rax
0x140003ccd  xorps   xmm1, xmm1
0x140003cd0  movups  [rsp+14F0h+var_1480], xmm1
0x140003cd5  mov     [rbp+13F0h+var_1470], rax
0x140003cd9  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140003ce0  test    rax, rax
0x140003ce3  jz      short loc_140003CF0
0x140003ce5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003cea  mov     [rbp+13F0h+var_1450], rax
0x140003cee  jmp     short loc_140003CF4
0x140003cf0  mov     [rbp+13F0h+var_1450], r13
0x140003cf4  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140003cfb  test    rax, rax
0x140003cfe  jz      short loc_140003D0A
0x140003d00  lea     rcx, [rsp+14F0h+var_14D0]
0x140003d05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003d0a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140003d11  test    rax, rax
0x140003d14  jz      short loc_140003D2A
0x140003d16  mov     r8d, 400h
0x140003d1c  lea     rdx, [rbp+13F0h+var_1430]
0x140003d20  lea     rcx, [rsp+14F0h+var_14D0]
0x140003d25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003d2a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140003d31  test    rax, rax
0x140003d34  jz      short loc_140003D40
0x140003d36  lea     rcx, [rsp+14F0h+var_14D0]
0x140003d3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003d40  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140003d47  test    rax, rax
0x140003d4a  jz      short loc_140003D5D
0x140003d4c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140003d51  jnz     short loc_140003D5D
0x140003d53  lea     rcx, [rsp+14F0h+var_14D0]
0x140003d58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003d5d  cmp     [rsp+14F0h+var_14C8], r13d
0x140003d62  jl      short loc_140003D76
0x140003d64  mov     ecx, 8000FFFFh; this
0x140003d69  mov     [rsp+14F0h+var_14C8], ecx
0x140003d6d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140003d72  mov     [rsp+14F0h+var_14C4], eax
0x140003d76  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x140003d7d  jnz     short loc_140003D9E
0x140003d7f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140003d86  test    rax, rax
0x140003d89  jz      short loc_140003D94
0x140003d8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003d90  test    al, al
0x140003d92  jmp     short loc_140003D9C
0x140003d94  call    cs:__imp_IsDebuggerPresent
0x140003d9a  test    eax, eax
0x140003d9c  jz      short loc_140003DA5
0x140003d9e  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140003da3  jz      short loc_140003DCB
0x140003da5  mov     rax, cs:g_pfnResultLoggingCallback
0x140003dac  test    rax, rax
0x140003daf  jz      short loc_140003E24
0x140003db1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140003db8  jnz     short loc_140003E24
0x140003dba  xor     r8d, r8d
0x140003dbd  xor     edx, edx
0x140003dbf  lea     rcx, [rsp+14F0h+var_14D0]
0x140003dc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003dc9  jmp     short loc_140003E24
0x140003dcb  mov     ebx, 800h
0x140003dd0  mov     rax, cs:g_pfnResultLoggingCallback
0x140003dd7  test    rax, rax
0x140003dda  jz      short loc_140003DF9
0x140003ddc  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140003de3  jnz     short loc_140003DF9
0x140003de5  mov     r8d, ebx
0x140003de8  lea     rdx, [rbp+13F0h+OutputString]
0x140003def  lea     rcx, [rsp+14F0h+var_14D0]
0x140003df4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003df9  cmp     [rbp+13F0h+OutputString], r13w
0x140003e01  jnz     short loc_140003E17
0x140003e03  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x140003e08  mov     rdx, rbx; unsigned __int16 *
0x140003e0b  lea     rcx, [rbp+13F0h+OutputString]; this
0x140003e12  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140003e17  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x140003e1e  call    cs:__imp_OutputDebugStringW
0x140003e24  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x140003e29  jnz     short loc_140003E34
0x140003e2b  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x140003e32  jz      short loc_140003E46
0x140003e34  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140003e3b  test    rax, rax
0x140003e3e  jz      short loc_140003E46
0x140003e40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003e45  nop
0x140003e46  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140003e4b  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
