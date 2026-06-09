# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18000f210`
- end: `0x18000f4bc`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `684`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000f044`

## callees

- `0x180005ed4`
- `0x180007114`
- `0x1800080ec`
- `0x180008440`
- `0x18000872c`
- `0x18000f210`
- `0x18003b96a`
- `0x18003ba60`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f2b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f2b9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000f450`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000f450`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000f3b4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000f3b4`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  bool v10; // r12
  int v11; // ebx
  int v12; // ecx
  __int64 v13; // rdx
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  char v18; // bl
  const struct wil::FailureInfo *v19; // rdx
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v27; // [rsp+48h] [rbp-B8h]
  __int64 v28; // [rsp+50h] [rbp-B0h]
  __int64 v29; // [rsp+58h] [rbp-A8h]
  int v30; // [rsp+60h] [rbp-A0h]
  int v31; // [rsp+64h] [rbp-9Ch]
  __int64 v32; // [rsp+68h] [rbp-98h]
  __int128 v33; // [rsp+70h] [rbp-90h]
  __int64 v34; // [rsp+80h] [rbp-80h]
  __int128 v35; // [rsp+88h] [rbp-78h]
  __int64 v36; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v38; // [rsp+A8h] [rbp-58h]
  __int64 v39; // [rsp+B0h] [rbp-50h]
  char v40[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v10 = g_pfnThrowPlatformException != 0;
  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v22 = *a7;
  v23 = a7[1];
  v11 = wil::details::RecordException((wil::details *)(unsigned int)v22, (int)a7);
  v20 = 0;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  v21 = v12;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v25 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v30 = a2;
  v31 = v11;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v36 = 0;
  v33 = 0;
  v34 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && !v10 && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v18 = 1, (v21 & 2) != 0) )
  {
    v18 = 0;
  }
  if ( v10 || v18 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v20, v16);
    if ( v18 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v20, 0, 0);
  }
  if ( ((v21 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v21 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v20, v14);
  if ( v10 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v20, OutputString);
  wil::ThrowResultException((wil *)&v20, v14);
  wil::details::WilFailFast((wil::details *)&v20, v19);
}

```

## disassembly

```asm
0x18000f210  mov     [rsp-8+arg_18], rbx
0x18000f215  push    rbp
0x18000f216  push    rsi
0x18000f217  push    rdi
0x18000f218  push    r12
0x18000f21a  push    r13
0x18000f21c  push    r14
0x18000f21e  push    r15
0x18000f220  lea     rbp, [rsp-13C0h]
0x18000f228  mov     eax, 14C0h
0x18000f22d  call    _alloca_probe
0x18000f232  sub     rsp, rax
0x18000f235  mov     r14, r8
0x18000f238  mov     esi, edx
0x18000f23a  mov     r15, rcx
0x18000f23d  mov     rdi, [rbp+13F0h+arg_28]
0x18000f244  xor     r13d, r13d
0x18000f247  cmp     cs:g_pfnThrowPlatformException, r13
0x18000f24e  setnz   r12b
0x18000f252  xor     edx, edx; Val
0x18000f254  mov     r8d, 98h; Size
0x18000f25a  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000f25f  call    memset_0
0x18000f264  nop
0x18000f265  mov     [rbp+13F0h+OutputString], r13w
0x18000f26d  mov     [rbp+13F0h+var_1430], r13b
0x18000f271  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18000f278  mov     ecx, [rdx]; this
0x18000f27a  mov     [rsp+14F0h+var_14C8], ecx
0x18000f27e  mov     eax, [rdx+4]
0x18000f281  mov     [rsp+14F0h+var_14C4], eax
0x18000f285  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000f28a  mov     ebx, eax
0x18000f28c  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x18000f291  mov     ecx, r13d
0x18000f294  lea     eax, [r13+8]
0x18000f298  cmp     dword ptr [rdx+8], 1
0x18000f29c  cmovz   ecx, eax
0x18000f29f  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000f2a3  lea     ecx, [rax-7]
0x18000f2a6  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000f2ae  inc     ecx
0x18000f2b0  mov     [rsp+14F0h+var_14C0], ecx
0x18000f2b4  mov     [rsp+14F0h+var_14B8], r13
0x18000f2b9  call    cs:__imp_GetCurrentThreadId
0x18000f2bf  mov     [rsp+14F0h+var_14B0], eax
0x18000f2c3  mov     [rsp+14F0h+var_1498], r14
0x18000f2c8  mov     [rsp+14F0h+var_1490], esi
0x18000f2cc  mov     [rsp+14F0h+var_148C], ebx
0x18000f2d0  mov     [rsp+14F0h+var_14A8], r13
0x18000f2d5  mov     [rsp+14F0h+var_14A0], r13
0x18000f2da  mov     [rbp+13F0h+var_1448], rdi
0x18000f2de  mov     [rbp+13F0h+var_1440], r15
0x18000f2e2  mov     [rsp+14F0h+var_1488], r13
0x18000f2e7  xorps   xmm0, xmm0
0x18000f2ea  xor     eax, eax
0x18000f2ec  movups  [rbp+13F0h+var_1468], xmm0
0x18000f2f0  mov     [rbp+13F0h+var_1458], rax
0x18000f2f4  xorps   xmm1, xmm1
0x18000f2f7  movups  [rsp+14F0h+var_1480], xmm1
0x18000f2fc  mov     [rbp+13F0h+var_1470], rax
0x18000f300  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000f307  test    rax, rax
0x18000f30a  jz      short loc_18000F317
0x18000f30c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f311  mov     [rbp+13F0h+var_1450], rax
0x18000f315  jmp     short loc_18000F31B
0x18000f317  mov     [rbp+13F0h+var_1450], r13
0x18000f31b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000f322  test    rax, rax
0x18000f325  jz      short loc_18000F331
0x18000f327  lea     rcx, [rsp+14F0h+var_14D0]
0x18000f32c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f331  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000f338  test    rax, rax
0x18000f33b  jz      short loc_18000F351
0x18000f33d  mov     r8d, 400h
0x18000f343  lea     rdx, [rbp+13F0h+var_1430]
0x18000f347  lea     rcx, [rsp+14F0h+var_14D0]
0x18000f34c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f351  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000f358  test    rax, rax
0x18000f35b  jz      short loc_18000F367
0x18000f35d  lea     rcx, [rsp+14F0h+var_14D0]
0x18000f362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f367  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000f36e  test    rax, rax
0x18000f371  jz      short loc_18000F389
0x18000f373  test    r12b, r12b
0x18000f376  jnz     short loc_18000F389
0x18000f378  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000f37d  jnz     short loc_18000F389
0x18000f37f  lea     rcx, [rsp+14F0h+var_14D0]
0x18000f384  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f389  cmp     [rsp+14F0h+var_14C8], r13d
0x18000f38e  jl      short loc_18000F396
0x18000f390  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000f396  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000f39d  jnz     short loc_18000F3BE
0x18000f39f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000f3a6  test    rax, rax
0x18000f3a9  jz      short loc_18000F3B4
0x18000f3ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3b0  test    al, al
0x18000f3b2  jmp     short loc_18000F3BC
0x18000f3b4  call    cs:__imp_IsDebuggerPresent
0x18000f3ba  test    eax, eax
0x18000f3bc  jz      short loc_18000F3C7
0x18000f3be  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000f3c3  mov     bl, 1
0x18000f3c5  jz      short loc_18000F3CA
0x18000f3c7  mov     bl, r13b
0x18000f3ca  test    r12b, r12b
0x18000f3cd  jnz     short loc_18000F3F9
0x18000f3cf  test    bl, bl
0x18000f3d1  jnz     short loc_18000F3F9
0x18000f3d3  mov     rax, cs:g_pfnResultLoggingCallback
0x18000f3da  test    rax, rax
0x18000f3dd  jz      short loc_18000F456
0x18000f3df  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000f3e6  jnz     short loc_18000F456
0x18000f3e8  xor     r8d, r8d
0x18000f3eb  xor     edx, edx
0x18000f3ed  lea     rcx, [rsp+14F0h+var_14D0]
0x18000f3f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3f7  jmp     short loc_18000F456
0x18000f3f9  mov     edi, 800h
0x18000f3fe  mov     rax, cs:g_pfnResultLoggingCallback
0x18000f405  test    rax, rax
0x18000f408  jz      short loc_18000F427
0x18000f40a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000f411  jnz     short loc_18000F427
0x18000f413  mov     r8d, edi
0x18000f416  lea     rdx, [rbp+13F0h+OutputString]
0x18000f41d  lea     rcx, [rsp+14F0h+var_14D0]
0x18000f422  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f427  cmp     [rbp+13F0h+OutputString], r13w
0x18000f42f  jnz     short loc_18000F445
0x18000f431  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000f436  mov     rdx, rdi; unsigned __int16 *
0x18000f439  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000f440  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000f445  test    bl, bl
0x18000f447  jz      short loc_18000F456
0x18000f449  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000f450  call    cs:__imp_OutputDebugStringW
0x18000f456  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000f45b  jnz     short loc_18000F466
0x18000f45d  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18000f464  jz      short loc_18000F478
0x18000f466  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000f46d  test    rax, rax
0x18000f470  jz      short loc_18000F478
0x18000f472  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f477  nop
0x18000f478  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18000f47d  jz      short loc_18000F48A
0x18000f47f  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000f484  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000f48a  test    r12b, r12b
0x18000f48d  jz      short loc_18000F4A7
0x18000f48f  lea     rdx, [rbp+13F0h+OutputString]
0x18000f496  lea     rcx, [rsp+14F0h+var_14D0]
0x18000f49b  mov     rax, cs:g_pfnThrowPlatformException
0x18000f4a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4a7  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000f4ac  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x18000f4b1  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000f4b6  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
