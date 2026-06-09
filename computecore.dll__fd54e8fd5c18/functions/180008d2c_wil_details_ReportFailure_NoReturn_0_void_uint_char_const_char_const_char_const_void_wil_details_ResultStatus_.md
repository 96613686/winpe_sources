# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180008d2c`
- end: `0x180008ff1`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `709`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800087b4`

## callees

- `0x180007438`
- `0x180008d2c`
- `0x18000c36c`
- `0x18000de00`
- `0x180010128`
- `0x180011320`
- `0x1800115b4`
- `0x180099a90`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008ded`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008ded`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008f85`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008f85`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008ee9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008ee9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  bool v11; // di
  int v12; // r12d
  int v13; // ecx
  __int64 v14; // rdx
  const struct wil::FailureInfo *v15; // rdx
  wil::details::in1diag3 *v16; // rcx
  const struct wil::FailureInfo *v17; // r9
  bool v18; // zf
  char v19; // bl
  const struct wil::FailureInfo *v20; // rdx
  int v21; // [rsp+20h] [rbp-E0h] BYREF
  int v22; // [rsp+24h] [rbp-DCh]
  int v23; // [rsp+28h] [rbp-D8h]
  int v24; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v25; // [rsp+30h] [rbp-D0h]
  _WORD *v26; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v28; // [rsp+48h] [rbp-B8h]
  __int64 v29; // [rsp+50h] [rbp-B0h]
  __int64 v30; // [rsp+58h] [rbp-A8h]
  int v31; // [rsp+60h] [rbp-A0h]
  int v32; // [rsp+64h] [rbp-9Ch]
  __int64 v33; // [rsp+68h] [rbp-98h]
  __int128 v34; // [rsp+70h] [rbp-90h]
  __int64 v35; // [rsp+80h] [rbp-80h]
  __int128 v36; // [rsp+88h] [rbp-78h]
  __int64 v37; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v39; // [rsp+A8h] [rbp-58h]
  __int64 v40; // [rsp+B0h] [rbp-50h]
  char v41[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v11 = g_pfnThrowPlatformException != 0;
  memset_0(&v21, 0, 0x98u);
  OutputString[0] = 0;
  v41[0] = 0;
  v23 = *a7;
  v24 = a7[1];
  v12 = wil::details::RecordException((wil::details *)(unsigned int)v23, (int)a7);
  v21 = 0;
  v13 = 0;
  if ( *(_DWORD *)(v14 + 8) == 1 )
    v13 = 8;
  v22 = v13;
  v25 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v18 = *a8 == 0, v26 = a8, v18) )
    v26 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v30 = a3;
  v31 = a2;
  v32 = v12;
  v28 = 0;
  v29 = 0;
  v39 = a6;
  v40 = a1;
  v33 = 0;
  v36 = 0;
  v37 = 0;
  v34 = 0;
  v35 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v16);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v21);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v21, v41, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v21);
  if ( wil::details::g_pfnOriginateCallback && !v11 && (v22 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v21);
  if ( v23 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v16);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v18 = !IsDebuggerPresent())
      : (v18 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v16) == 0),
        v18)
    || (v19 = 1, (v22 & 2) != 0) )
  {
    v19 = 0;
  }
  if ( v11 || v19 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v21, OutputString, 2048, v17);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v21, v17);
    if ( v19 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v21, 0, 0, v17);
  }
  if ( ((v22 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v16);
  if ( (v22 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v21, v15);
  if ( v11 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v21, OutputString);
  wil::ThrowResultException((wil *)&v21, v15);
  wil::details::WilFailFast((wil::details *)&v21, v20);
}

```

## disassembly

```asm
0x180008d2c  mov     [rsp-8+arg_18], rbx
0x180008d31  push    rbp
0x180008d32  push    rsi
0x180008d33  push    rdi
0x180008d34  push    r12
0x180008d36  push    r13
0x180008d38  push    r14
0x180008d3a  push    r15
0x180008d3c  lea     rbp, [rsp-13C0h]
0x180008d44  mov     eax, 14C0h
0x180008d49  call    _alloca_probe
0x180008d4e  sub     rsp, rax
0x180008d51  mov     r14, r8
0x180008d54  mov     esi, edx
0x180008d56  mov     rbx, rcx
0x180008d59  mov     r15, [rbp+13F0h+arg_28]
0x180008d60  xor     r13d, r13d
0x180008d63  cmp     cs:g_pfnThrowPlatformException, r13
0x180008d6a  setnz   dil
0x180008d6e  xor     edx, edx; Val
0x180008d70  mov     r8d, 98h; Size
0x180008d76  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180008d7b  call    memset_0
0x180008d80  nop
0x180008d81  mov     [rbp+13F0h+OutputString], r13w
0x180008d89  mov     [rbp+13F0h+var_1430], r13b
0x180008d8d  mov     rdx, [rbp+13F0h+arg_30]; int
0x180008d94  mov     ecx, [rdx]; this
0x180008d96  mov     [rsp+14F0h+var_14C8], ecx
0x180008d9a  mov     eax, [rdx+4]
0x180008d9d  mov     [rsp+14F0h+var_14C4], eax
0x180008da1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180008da6  mov     r12d, eax
0x180008da9  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x180008dae  mov     ecx, r13d
0x180008db1  lea     eax, [r13+8]
0x180008db5  cmp     dword ptr [rdx+8], 1
0x180008db9  cmovz   ecx, eax
0x180008dbc  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180008dc0  lea     ecx, [rax-7]
0x180008dc3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180008dcb  inc     ecx
0x180008dcd  mov     [rsp+14F0h+var_14C0], ecx
0x180008dd1  mov     rcx, [rbp+13F0h+arg_38]
0x180008dd8  test    rcx, rcx
0x180008ddb  jz      short loc_180008DE8
0x180008ddd  cmp     [rcx], r13w
0x180008de1  mov     [rsp+14F0h+var_14B8], rcx
0x180008de6  jnz     short loc_180008DED
0x180008de8  mov     [rsp+14F0h+var_14B8], r13
0x180008ded  call    cs:__imp_GetCurrentThreadId
0x180008df3  mov     [rsp+14F0h+var_14B0], eax
0x180008df7  mov     [rsp+14F0h+var_1498], r14
0x180008dfc  mov     [rsp+14F0h+var_1490], esi
0x180008e00  mov     [rsp+14F0h+var_148C], r12d
0x180008e05  mov     [rsp+14F0h+var_14A8], r13
0x180008e0a  mov     [rsp+14F0h+var_14A0], r13
0x180008e0f  mov     [rbp+13F0h+var_1448], r15
0x180008e13  mov     [rbp+13F0h+var_1440], rbx
0x180008e17  mov     [rsp+14F0h+var_1488], r13
0x180008e1c  xorps   xmm0, xmm0
0x180008e1f  xor     eax, eax
0x180008e21  movups  [rbp+13F0h+var_1468], xmm0
0x180008e25  mov     [rbp+13F0h+var_1458], rax
0x180008e29  xorps   xmm1, xmm1
0x180008e2c  movups  [rsp+14F0h+var_1480], xmm1
0x180008e31  mov     [rbp+13F0h+var_1470], rax
0x180008e35  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180008e3c  test    rax, rax
0x180008e3f  jz      short loc_180008E4C
0x180008e41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e46  mov     [rbp+13F0h+var_1450], rax
0x180008e4a  jmp     short loc_180008E50
0x180008e4c  mov     [rbp+13F0h+var_1450], r13
0x180008e50  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180008e57  test    rax, rax
0x180008e5a  jz      short loc_180008E66
0x180008e5c  lea     rcx, [rsp+14F0h+var_14D0]
0x180008e61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e66  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180008e6d  test    rax, rax
0x180008e70  jz      short loc_180008E86
0x180008e72  mov     r8d, 400h
0x180008e78  lea     rdx, [rbp+13F0h+var_1430]
0x180008e7c  lea     rcx, [rsp+14F0h+var_14D0]
0x180008e81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e86  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008e8d  test    rax, rax
0x180008e90  jz      short loc_180008E9C
0x180008e92  lea     rcx, [rsp+14F0h+var_14D0]
0x180008e97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e9c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008ea3  test    rax, rax
0x180008ea6  jz      short loc_180008EBE
0x180008ea8  test    dil, dil
0x180008eab  jnz     short loc_180008EBE
0x180008ead  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180008eb2  jnz     short loc_180008EBE
0x180008eb4  lea     rcx, [rsp+14F0h+var_14D0]
0x180008eb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ebe  cmp     [rsp+14F0h+var_14C8], r13d
0x180008ec3  jl      short loc_180008ECB
0x180008ec5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180008ecb  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180008ed2  jnz     short loc_180008EF3
0x180008ed4  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180008edb  test    rax, rax
0x180008ede  jz      short loc_180008EE9
0x180008ee0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ee5  test    al, al
0x180008ee7  jmp     short loc_180008EF1
0x180008ee9  call    cs:__imp_IsDebuggerPresent
0x180008eef  test    eax, eax
0x180008ef1  jz      short loc_180008EFC
0x180008ef3  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180008ef8  mov     bl, 1
0x180008efa  jz      short loc_180008EFF
0x180008efc  mov     bl, r13b
0x180008eff  test    dil, dil
0x180008f02  jnz     short loc_180008F2E
0x180008f04  test    bl, bl
0x180008f06  jnz     short loc_180008F2E
0x180008f08  mov     rax, cs:g_pfnResultLoggingCallback
0x180008f0f  test    rax, rax
0x180008f12  jz      short loc_180008F8B
0x180008f14  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180008f1b  jnz     short loc_180008F8B
0x180008f1d  xor     r8d, r8d
0x180008f20  xor     edx, edx
0x180008f22  lea     rcx, [rsp+14F0h+var_14D0]
0x180008f27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f2c  jmp     short loc_180008F8B
0x180008f2e  mov     esi, 800h
0x180008f33  mov     rax, cs:g_pfnResultLoggingCallback
0x180008f3a  test    rax, rax
0x180008f3d  jz      short loc_180008F5C
0x180008f3f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180008f46  jnz     short loc_180008F5C
0x180008f48  mov     r8d, esi
0x180008f4b  lea     rdx, [rbp+13F0h+OutputString]
0x180008f52  lea     rcx, [rsp+14F0h+var_14D0]
0x180008f57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f5c  cmp     [rbp+13F0h+OutputString], r13w
0x180008f64  jnz     short loc_180008F7A
0x180008f66  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180008f6b  mov     rdx, rsi; unsigned __int16 *
0x180008f6e  lea     rcx, [rbp+13F0h+OutputString]; this
0x180008f75  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180008f7a  test    bl, bl
0x180008f7c  jz      short loc_180008F8B
0x180008f7e  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180008f85  call    cs:__imp_OutputDebugStringW
0x180008f8b  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180008f90  jnz     short loc_180008F9B
0x180008f92  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180008f99  jz      short loc_180008FAD
0x180008f9b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180008fa2  test    rax, rax
0x180008fa5  jz      short loc_180008FAD
0x180008fa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fac  nop
0x180008fad  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180008fb2  jz      short loc_180008FBF
0x180008fb4  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180008fb9  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180008fbf  test    dil, dil
0x180008fc2  jz      short loc_180008FDC
0x180008fc4  lea     rdx, [rbp+13F0h+OutputString]
0x180008fcb  lea     rcx, [rsp+14F0h+var_14D0]
0x180008fd0  mov     rax, cs:g_pfnThrowPlatformException
0x180008fd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fdc  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180008fe1  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x180008fe6  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180008feb  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
