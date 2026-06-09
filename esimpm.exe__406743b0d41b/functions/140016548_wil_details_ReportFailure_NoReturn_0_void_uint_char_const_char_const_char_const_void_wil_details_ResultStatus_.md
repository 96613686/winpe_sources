# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x140016548`
- end: `0x1400167f4`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `684`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1400164c0`

## callees

- `0x140003b28`
- `0x14000fdf4`
- `0x1400114f0`
- `0x14001347c`
- `0x140013bb0`
- `0x140013d7c`
- `0x140016548`
- `0x14003bcc0`
- `0x14003e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400165f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400165f1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140016788`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140016788`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400166ec`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400166ec`

## pseudocode

```c
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
0x140016548  mov     [rsp-8+arg_18], rbx
0x14001654d  push    rbp
0x14001654e  push    rsi
0x14001654f  push    rdi
0x140016550  push    r12
0x140016552  push    r13
0x140016554  push    r14
0x140016556  push    r15
0x140016558  lea     rbp, [rsp-13C0h]
0x140016560  mov     eax, 14C0h
0x140016565  call    _alloca_probe
0x14001656a  sub     rsp, rax
0x14001656d  mov     r14, r8
0x140016570  mov     esi, edx
0x140016572  mov     r15, rcx
0x140016575  mov     rdi, [rbp+13F0h+arg_28]
0x14001657c  xor     r13d, r13d
0x14001657f  cmp     cs:g_pfnThrowPlatformException, r13
0x140016586  setnz   r12b
0x14001658a  xor     edx, edx; Val
0x14001658c  mov     r8d, 98h; Size
0x140016592  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x140016597  call    memset_0
0x14001659c  nop
0x14001659d  mov     [rbp+13F0h+OutputString], r13w
0x1400165a5  mov     [rbp+13F0h+var_1430], r13b
0x1400165a9  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x1400165b0  mov     ecx, [rdx]; this
0x1400165b2  mov     [rsp+14F0h+var_14C8], ecx
0x1400165b6  mov     eax, [rdx+4]
0x1400165b9  mov     [rsp+14F0h+var_14C4], eax
0x1400165bd  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1400165c2  mov     ebx, eax
0x1400165c4  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x1400165c9  mov     ecx, r13d
0x1400165cc  lea     eax, [r13+8]
0x1400165d0  cmp     dword ptr [rdx+8], 1
0x1400165d4  cmovz   ecx, eax
0x1400165d7  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1400165db  lea     ecx, [rax-7]
0x1400165de  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400165e6  inc     ecx
0x1400165e8  mov     [rsp+14F0h+var_14C0], ecx
0x1400165ec  mov     [rsp+14F0h+var_14B8], r13
0x1400165f1  call    cs:__imp_GetCurrentThreadId
0x1400165f7  mov     [rsp+14F0h+var_14B0], eax
0x1400165fb  mov     [rsp+14F0h+var_1498], r14
0x140016600  mov     [rsp+14F0h+var_1490], esi
0x140016604  mov     [rsp+14F0h+var_148C], ebx
0x140016608  mov     [rsp+14F0h+var_14A8], r13
0x14001660d  mov     [rsp+14F0h+var_14A0], r13
0x140016612  mov     [rbp+13F0h+var_1448], rdi
0x140016616  mov     [rbp+13F0h+var_1440], r15
0x14001661a  mov     [rsp+14F0h+var_1488], r13
0x14001661f  xorps   xmm0, xmm0
0x140016622  xor     eax, eax
0x140016624  movups  [rbp+13F0h+var_1468], xmm0
0x140016628  mov     [rbp+13F0h+var_1458], rax
0x14001662c  xorps   xmm1, xmm1
0x14001662f  movups  [rsp+14F0h+var_1480], xmm1
0x140016634  mov     [rbp+13F0h+var_1470], rax
0x140016638  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14001663f  test    rax, rax
0x140016642  jz      short loc_14001664F
0x140016644  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016649  mov     [rbp+13F0h+var_1450], rax
0x14001664d  jmp     short loc_140016653
0x14001664f  mov     [rbp+13F0h+var_1450], r13
0x140016653  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14001665a  test    rax, rax
0x14001665d  jz      short loc_140016669
0x14001665f  lea     rcx, [rsp+14F0h+var_14D0]
0x140016664  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016669  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140016670  test    rax, rax
0x140016673  jz      short loc_140016689
0x140016675  mov     r8d, 400h
0x14001667b  lea     rdx, [rbp+13F0h+var_1430]
0x14001667f  lea     rcx, [rsp+14F0h+var_14D0]
0x140016684  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016689  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140016690  test    rax, rax
0x140016693  jz      short loc_14001669F
0x140016695  lea     rcx, [rsp+14F0h+var_14D0]
0x14001669a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001669f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400166a6  test    rax, rax
0x1400166a9  jz      short loc_1400166C1
0x1400166ab  test    r12b, r12b
0x1400166ae  jnz     short loc_1400166C1
0x1400166b0  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1400166b5  jnz     short loc_1400166C1
0x1400166b7  lea     rcx, [rsp+14F0h+var_14D0]
0x1400166bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400166c1  cmp     [rsp+14F0h+var_14C8], r13d
0x1400166c6  jl      short loc_1400166CE
0x1400166c8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1400166ce  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x1400166d5  jnz     short loc_1400166F6
0x1400166d7  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400166de  test    rax, rax
0x1400166e1  jz      short loc_1400166EC
0x1400166e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400166e8  test    al, al
0x1400166ea  jmp     short loc_1400166F4
0x1400166ec  call    cs:__imp_IsDebuggerPresent
0x1400166f2  test    eax, eax
0x1400166f4  jz      short loc_1400166FF
0x1400166f6  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1400166fb  mov     bl, 1
0x1400166fd  jz      short loc_140016702
0x1400166ff  mov     bl, r13b
0x140016702  test    r12b, r12b
0x140016705  jnz     short loc_140016731
0x140016707  test    bl, bl
0x140016709  jnz     short loc_140016731
0x14001670b  mov     rax, cs:g_pfnResultLoggingCallback
0x140016712  test    rax, rax
0x140016715  jz      short loc_14001678E
0x140016717  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x14001671e  jnz     short loc_14001678E
0x140016720  xor     r8d, r8d
0x140016723  xor     edx, edx
0x140016725  lea     rcx, [rsp+14F0h+var_14D0]
0x14001672a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001672f  jmp     short loc_14001678E
0x140016731  mov     edi, 800h
0x140016736  mov     rax, cs:g_pfnResultLoggingCallback
0x14001673d  test    rax, rax
0x140016740  jz      short loc_14001675F
0x140016742  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140016749  jnz     short loc_14001675F
0x14001674b  mov     r8d, edi
0x14001674e  lea     rdx, [rbp+13F0h+OutputString]
0x140016755  lea     rcx, [rsp+14F0h+var_14D0]
0x14001675a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001675f  cmp     [rbp+13F0h+OutputString], r13w
0x140016767  jnz     short loc_14001677D
0x140016769  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x14001676e  mov     rdx, rdi; unsigned __int16 *
0x140016771  lea     rcx, [rbp+13F0h+OutputString]; this
0x140016778  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14001677d  test    bl, bl
0x14001677f  jz      short loc_14001678E
0x140016781  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x140016788  call    cs:__imp_OutputDebugStringW
0x14001678e  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x140016793  jnz     short loc_14001679E
0x140016795  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x14001679c  jz      short loc_1400167B0
0x14001679e  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400167a5  test    rax, rax
0x1400167a8  jz      short loc_1400167B0
0x1400167aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400167af  nop
0x1400167b0  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x1400167b5  jz      short loc_1400167C2
0x1400167b7  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1400167bc  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1400167c2  test    r12b, r12b
0x1400167c5  jz      short loc_1400167DF
0x1400167c7  lea     rdx, [rbp+13F0h+OutputString]
0x1400167ce  lea     rcx, [rsp+14F0h+var_14D0]
0x1400167d3  mov     rax, cs:g_pfnThrowPlatformException
0x1400167da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400167df  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1400167e4  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x1400167e9  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1400167ee  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
