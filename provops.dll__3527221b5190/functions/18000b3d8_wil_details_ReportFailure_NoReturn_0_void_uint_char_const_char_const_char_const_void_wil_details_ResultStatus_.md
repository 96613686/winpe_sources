# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18000b3d8`
- end: `0x18000b684`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `684`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000b034`

## callees

- `0x180005fa4`
- `0x180007050`
- `0x180008048`
- `0x1800083c0`
- `0x18000863c`
- `0x18000b3d8`
- `0x180033e9a`
- `0x180033f90`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b481`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b481`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000b618`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000b618`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000b57c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000b57c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
0x18000b3d8  mov     [rsp-8+arg_18], rbx
0x18000b3dd  push    rbp
0x18000b3de  push    rsi
0x18000b3df  push    rdi
0x18000b3e0  push    r12
0x18000b3e2  push    r13
0x18000b3e4  push    r14
0x18000b3e6  push    r15
0x18000b3e8  lea     rbp, [rsp-13C0h]
0x18000b3f0  mov     eax, 14C0h
0x18000b3f5  call    _alloca_probe
0x18000b3fa  sub     rsp, rax
0x18000b3fd  mov     r14, r8
0x18000b400  mov     esi, edx
0x18000b402  mov     r15, rcx
0x18000b405  mov     rdi, [rbp+13F0h+arg_28]
0x18000b40c  xor     r13d, r13d
0x18000b40f  cmp     cs:g_pfnThrowPlatformException, r13
0x18000b416  setnz   r12b
0x18000b41a  xor     edx, edx; Val
0x18000b41c  mov     r8d, 98h; Size
0x18000b422  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000b427  call    memset_0
0x18000b42c  nop
0x18000b42d  mov     [rbp+13F0h+OutputString], r13w
0x18000b435  mov     [rbp+13F0h+var_1430], r13b
0x18000b439  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18000b440  mov     ecx, [rdx]; this
0x18000b442  mov     [rsp+14F0h+var_14C8], ecx
0x18000b446  mov     eax, [rdx+4]
0x18000b449  mov     [rsp+14F0h+var_14C4], eax
0x18000b44d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000b452  mov     ebx, eax
0x18000b454  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x18000b459  mov     ecx, r13d
0x18000b45c  lea     eax, [r13+8]
0x18000b460  cmp     dword ptr [rdx+8], 1
0x18000b464  cmovz   ecx, eax
0x18000b467  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000b46b  lea     ecx, [rax-7]
0x18000b46e  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000b476  inc     ecx
0x18000b478  mov     [rsp+14F0h+var_14C0], ecx
0x18000b47c  mov     [rsp+14F0h+var_14B8], r13
0x18000b481  call    cs:__imp_GetCurrentThreadId
0x18000b487  mov     [rsp+14F0h+var_14B0], eax
0x18000b48b  mov     [rsp+14F0h+var_1498], r14
0x18000b490  mov     [rsp+14F0h+var_1490], esi
0x18000b494  mov     [rsp+14F0h+var_148C], ebx
0x18000b498  mov     [rsp+14F0h+var_14A8], r13
0x18000b49d  mov     [rsp+14F0h+var_14A0], r13
0x18000b4a2  mov     [rbp+13F0h+var_1448], rdi
0x18000b4a6  mov     [rbp+13F0h+var_1440], r15
0x18000b4aa  mov     [rsp+14F0h+var_1488], r13
0x18000b4af  xorps   xmm0, xmm0
0x18000b4b2  xor     eax, eax
0x18000b4b4  movups  [rbp+13F0h+var_1468], xmm0
0x18000b4b8  mov     [rbp+13F0h+var_1458], rax
0x18000b4bc  xorps   xmm1, xmm1
0x18000b4bf  movups  [rsp+14F0h+var_1480], xmm1
0x18000b4c4  mov     [rbp+13F0h+var_1470], rax
0x18000b4c8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000b4cf  test    rax, rax
0x18000b4d2  jz      short loc_18000B4DF
0x18000b4d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4d9  mov     [rbp+13F0h+var_1450], rax
0x18000b4dd  jmp     short loc_18000B4E3
0x18000b4df  mov     [rbp+13F0h+var_1450], r13
0x18000b4e3  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000b4ea  test    rax, rax
0x18000b4ed  jz      short loc_18000B4F9
0x18000b4ef  lea     rcx, [rsp+14F0h+var_14D0]
0x18000b4f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4f9  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000b500  test    rax, rax
0x18000b503  jz      short loc_18000B519
0x18000b505  mov     r8d, 400h
0x18000b50b  lea     rdx, [rbp+13F0h+var_1430]
0x18000b50f  lea     rcx, [rsp+14F0h+var_14D0]
0x18000b514  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b519  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000b520  test    rax, rax
0x18000b523  jz      short loc_18000B52F
0x18000b525  lea     rcx, [rsp+14F0h+var_14D0]
0x18000b52a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b52f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000b536  test    rax, rax
0x18000b539  jz      short loc_18000B551
0x18000b53b  test    r12b, r12b
0x18000b53e  jnz     short loc_18000B551
0x18000b540  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000b545  jnz     short loc_18000B551
0x18000b547  lea     rcx, [rsp+14F0h+var_14D0]
0x18000b54c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b551  cmp     [rsp+14F0h+var_14C8], r13d
0x18000b556  jl      short loc_18000B55E
0x18000b558  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000b55e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000b565  jnz     short loc_18000B586
0x18000b567  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000b56e  test    rax, rax
0x18000b571  jz      short loc_18000B57C
0x18000b573  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b578  test    al, al
0x18000b57a  jmp     short loc_18000B584
0x18000b57c  call    cs:__imp_IsDebuggerPresent
0x18000b582  test    eax, eax
0x18000b584  jz      short loc_18000B58F
0x18000b586  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000b58b  mov     bl, 1
0x18000b58d  jz      short loc_18000B592
0x18000b58f  mov     bl, r13b
0x18000b592  test    r12b, r12b
0x18000b595  jnz     short loc_18000B5C1
0x18000b597  test    bl, bl
0x18000b599  jnz     short loc_18000B5C1
0x18000b59b  mov     rax, cs:g_pfnResultLoggingCallback
0x18000b5a2  test    rax, rax
0x18000b5a5  jz      short loc_18000B61E
0x18000b5a7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000b5ae  jnz     short loc_18000B61E
0x18000b5b0  xor     r8d, r8d
0x18000b5b3  xor     edx, edx
0x18000b5b5  lea     rcx, [rsp+14F0h+var_14D0]
0x18000b5ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5bf  jmp     short loc_18000B61E
0x18000b5c1  mov     edi, 800h
0x18000b5c6  mov     rax, cs:g_pfnResultLoggingCallback
0x18000b5cd  test    rax, rax
0x18000b5d0  jz      short loc_18000B5EF
0x18000b5d2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000b5d9  jnz     short loc_18000B5EF
0x18000b5db  mov     r8d, edi
0x18000b5de  lea     rdx, [rbp+13F0h+OutputString]
0x18000b5e5  lea     rcx, [rsp+14F0h+var_14D0]
0x18000b5ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5ef  cmp     [rbp+13F0h+OutputString], r13w
0x18000b5f7  jnz     short loc_18000B60D
0x18000b5f9  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000b5fe  mov     rdx, rdi; unsigned __int16 *
0x18000b601  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000b608  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000b60d  test    bl, bl
0x18000b60f  jz      short loc_18000B61E
0x18000b611  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000b618  call    cs:__imp_OutputDebugStringW
0x18000b61e  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000b623  jnz     short loc_18000B62E
0x18000b625  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18000b62c  jz      short loc_18000B640
0x18000b62e  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000b635  test    rax, rax
0x18000b638  jz      short loc_18000B640
0x18000b63a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b63f  nop
0x18000b640  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18000b645  jz      short loc_18000B652
0x18000b647  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000b64c  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000b652  test    r12b, r12b
0x18000b655  jz      short loc_18000B66F
0x18000b657  lea     rdx, [rbp+13F0h+OutputString]
0x18000b65e  lea     rcx, [rsp+14F0h+var_14D0]
0x18000b663  mov     rax, cs:g_pfnThrowPlatformException
0x18000b66a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b66f  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000b674  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x18000b679  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000b67e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
