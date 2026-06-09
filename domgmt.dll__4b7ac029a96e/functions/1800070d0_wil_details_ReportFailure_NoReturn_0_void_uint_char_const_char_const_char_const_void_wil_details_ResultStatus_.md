# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800070d0`
- end: `0x180007395`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `709`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, __int64, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180006eb0`

## callees

- `0x18000296c`
- `0x1800046f4`
- `0x1800055e4`
- `0x18000637c`
- `0x1800066d0`
- `0x1800067ac`
- `0x1800070d0`
- `0x18000d560`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007191`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007191`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007329`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007329`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000728d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000728d`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
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
      g_pfnResultLoggingCallback(&v21, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v21, v17);
    if ( v19 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v21, 0, 0);
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
0x1800070d0  mov     [rsp-8+arg_18], rbx
0x1800070d5  push    rbp
0x1800070d6  push    rsi
0x1800070d7  push    rdi
0x1800070d8  push    r12
0x1800070da  push    r13
0x1800070dc  push    r14
0x1800070de  push    r15
0x1800070e0  lea     rbp, [rsp-13C0h]
0x1800070e8  mov     eax, 14C0h
0x1800070ed  call    _alloca_probe
0x1800070f2  sub     rsp, rax
0x1800070f5  mov     r14, r8
0x1800070f8  mov     esi, edx
0x1800070fa  mov     rbx, rcx
0x1800070fd  mov     r15, [rbp+13F0h+arg_28]
0x180007104  xor     r13d, r13d
0x180007107  cmp     cs:g_pfnThrowPlatformException, r13
0x18000710e  setnz   dil
0x180007112  xor     edx, edx; Val
0x180007114  mov     r8d, 98h; Size
0x18000711a  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000711f  call    memset_0
0x180007124  nop
0x180007125  mov     [rbp+13F0h+OutputString], r13w
0x18000712d  mov     [rbp+13F0h+var_1430], r13b
0x180007131  mov     rdx, [rbp+13F0h+arg_30]; int
0x180007138  mov     ecx, [rdx]; this
0x18000713a  mov     [rsp+14F0h+var_14C8], ecx
0x18000713e  mov     eax, [rdx+4]
0x180007141  mov     [rsp+14F0h+var_14C4], eax
0x180007145  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000714a  mov     r12d, eax
0x18000714d  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x180007152  mov     ecx, r13d
0x180007155  lea     eax, [r13+8]
0x180007159  cmp     dword ptr [rdx+8], 1
0x18000715d  cmovz   ecx, eax
0x180007160  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180007164  lea     ecx, [rax-7]
0x180007167  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000716f  inc     ecx
0x180007171  mov     [rsp+14F0h+var_14C0], ecx
0x180007175  mov     rcx, [rbp+13F0h+arg_38]
0x18000717c  test    rcx, rcx
0x18000717f  jz      short loc_18000718C
0x180007181  cmp     [rcx], r13w
0x180007185  mov     [rsp+14F0h+var_14B8], rcx
0x18000718a  jnz     short loc_180007191
0x18000718c  mov     [rsp+14F0h+var_14B8], r13
0x180007191  call    cs:__imp_GetCurrentThreadId
0x180007197  mov     [rsp+14F0h+var_14B0], eax
0x18000719b  mov     [rsp+14F0h+var_1498], r14
0x1800071a0  mov     [rsp+14F0h+var_1490], esi
0x1800071a4  mov     [rsp+14F0h+var_148C], r12d
0x1800071a9  mov     [rsp+14F0h+var_14A8], r13
0x1800071ae  mov     [rsp+14F0h+var_14A0], r13
0x1800071b3  mov     [rbp+13F0h+var_1448], r15
0x1800071b7  mov     [rbp+13F0h+var_1440], rbx
0x1800071bb  mov     [rsp+14F0h+var_1488], r13
0x1800071c0  xorps   xmm0, xmm0
0x1800071c3  xor     eax, eax
0x1800071c5  movups  [rbp+13F0h+var_1468], xmm0
0x1800071c9  mov     [rbp+13F0h+var_1458], rax
0x1800071cd  xorps   xmm1, xmm1
0x1800071d0  movups  [rsp+14F0h+var_1480], xmm1
0x1800071d5  mov     [rbp+13F0h+var_1470], rax
0x1800071d9  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800071e0  test    rax, rax
0x1800071e3  jz      short loc_1800071F0
0x1800071e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071ea  mov     [rbp+13F0h+var_1450], rax
0x1800071ee  jmp     short loc_1800071F4
0x1800071f0  mov     [rbp+13F0h+var_1450], r13
0x1800071f4  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800071fb  test    rax, rax
0x1800071fe  jz      short loc_18000720A
0x180007200  lea     rcx, [rsp+14F0h+var_14D0]
0x180007205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000720a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180007211  test    rax, rax
0x180007214  jz      short loc_18000722A
0x180007216  mov     r8d, 400h
0x18000721c  lea     rdx, [rbp+13F0h+var_1430]
0x180007220  lea     rcx, [rsp+14F0h+var_14D0]
0x180007225  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000722a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007231  test    rax, rax
0x180007234  jz      short loc_180007240
0x180007236  lea     rcx, [rsp+14F0h+var_14D0]
0x18000723b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007240  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007247  test    rax, rax
0x18000724a  jz      short loc_180007262
0x18000724c  test    dil, dil
0x18000724f  jnz     short loc_180007262
0x180007251  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180007256  jnz     short loc_180007262
0x180007258  lea     rcx, [rsp+14F0h+var_14D0]
0x18000725d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007262  cmp     [rsp+14F0h+var_14C8], r13d
0x180007267  jl      short loc_18000726F
0x180007269  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000726f  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180007276  jnz     short loc_180007297
0x180007278  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000727f  test    rax, rax
0x180007282  jz      short loc_18000728D
0x180007284  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007289  test    al, al
0x18000728b  jmp     short loc_180007295
0x18000728d  call    cs:__imp_IsDebuggerPresent
0x180007293  test    eax, eax
0x180007295  jz      short loc_1800072A0
0x180007297  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000729c  mov     bl, 1
0x18000729e  jz      short loc_1800072A3
0x1800072a0  mov     bl, r13b
0x1800072a3  test    dil, dil
0x1800072a6  jnz     short loc_1800072D2
0x1800072a8  test    bl, bl
0x1800072aa  jnz     short loc_1800072D2
0x1800072ac  mov     rax, cs:g_pfnResultLoggingCallback
0x1800072b3  test    rax, rax
0x1800072b6  jz      short loc_18000732F
0x1800072b8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800072bf  jnz     short loc_18000732F
0x1800072c1  xor     r8d, r8d
0x1800072c4  xor     edx, edx
0x1800072c6  lea     rcx, [rsp+14F0h+var_14D0]
0x1800072cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072d0  jmp     short loc_18000732F
0x1800072d2  mov     esi, 800h
0x1800072d7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800072de  test    rax, rax
0x1800072e1  jz      short loc_180007300
0x1800072e3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800072ea  jnz     short loc_180007300
0x1800072ec  mov     r8d, esi
0x1800072ef  lea     rdx, [rbp+13F0h+OutputString]
0x1800072f6  lea     rcx, [rsp+14F0h+var_14D0]
0x1800072fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007300  cmp     [rbp+13F0h+OutputString], r13w
0x180007308  jnz     short loc_18000731E
0x18000730a  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000730f  mov     rdx, rsi; unsigned __int16 *
0x180007312  lea     rcx, [rbp+13F0h+OutputString]; this
0x180007319  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000731e  test    bl, bl
0x180007320  jz      short loc_18000732F
0x180007322  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180007329  call    cs:__imp_OutputDebugStringW
0x18000732f  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180007334  jnz     short loc_18000733F
0x180007336  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18000733d  jz      short loc_180007351
0x18000733f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180007346  test    rax, rax
0x180007349  jz      short loc_180007351
0x18000734b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007350  nop
0x180007351  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180007356  jz      short loc_180007363
0x180007358  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000735d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180007363  test    dil, dil
0x180007366  jz      short loc_180007380
0x180007368  lea     rdx, [rbp+13F0h+OutputString]
0x18000736f  lea     rcx, [rsp+14F0h+var_14D0]
0x180007374  mov     rax, cs:g_pfnThrowPlatformException
0x18000737b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007380  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180007385  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x18000738a  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000738f  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
