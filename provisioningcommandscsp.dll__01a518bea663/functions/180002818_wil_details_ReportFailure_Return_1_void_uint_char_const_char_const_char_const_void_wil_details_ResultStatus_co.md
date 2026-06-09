# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180002818`
- end: `0x180002abe`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800022ac`

## callees

- `0x180002818`
- `0x180003a74`
- `0x180004a40`
- `0x180005930`
- `0x180005b00`
- `0x18000c5ce`
- `0x18000c600`
- `0x18000c6c0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800028de`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800028de`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002a5d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002a5d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800029d3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800029d3`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v11; // r15d
  int v12; // ecx
  __int64 v13; // rdx
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
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
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v11 = wil::details::RecordReturn((wil::details *)(unsigned int)v20, (int)a7);
  v18 = 1;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  v19 = v12;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v11;
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
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
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
  if ( ((v19 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v19 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x180002818  push    rbp
0x18000281a  push    rbx
0x18000281b  push    rsi
0x18000281c  push    rdi
0x18000281d  push    r12
0x18000281f  push    r14
0x180002821  push    r15
0x180002823  lea     rbp, [rsp-13D0h]
0x18000282b  mov     eax, 14D0h
0x180002830  call    _alloca_probe
0x180002835  sub     rsp, rax
0x180002838  mov     rax, cs:__security_cookie
0x18000283f  xor     rax, rsp
0x180002842  mov     [rbp+1400h+var_40], rax
0x180002849  mov     rsi, r8
0x18000284c  mov     edi, edx
0x18000284e  mov     rbx, rcx
0x180002851  mov     r14, [rbp+1400h+arg_28]
0x180002858  xor     edx, edx; Val
0x18000285a  mov     r8d, 98h; Size
0x180002860  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180002865  call    memset_0
0x18000286a  nop
0x18000286b  xor     r12d, r12d
0x18000286e  mov     [rbp+1400h+OutputString], r12w
0x180002876  mov     [rbp+1400h+var_1440], r12b
0x18000287a  mov     rdx, [rbp+1400h+arg_30]; int
0x180002881  mov     ecx, [rdx]; this
0x180002883  mov     [rsp+1500h+var_14D8], ecx
0x180002887  mov     eax, [rdx+4]
0x18000288a  mov     [rsp+1500h+var_14D4], eax
0x18000288e  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180002893  mov     r15d, eax
0x180002896  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18000289e  mov     ecx, r12d
0x1800028a1  lea     eax, [r12+8]
0x1800028a6  cmp     dword ptr [rdx+8], 1
0x1800028aa  cmovz   ecx, eax
0x1800028ad  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800028b1  lea     ecx, [rax-7]
0x1800028b4  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800028bc  inc     ecx
0x1800028be  mov     [rsp+1500h+var_14D0], ecx
0x1800028c2  mov     rcx, [rbp+1400h+arg_38]
0x1800028c9  test    rcx, rcx
0x1800028cc  jz      short loc_1800028D9
0x1800028ce  cmp     [rcx], r12w
0x1800028d2  mov     [rsp+1500h+var_14C8], rcx
0x1800028d7  jnz     short loc_1800028DE
0x1800028d9  mov     [rsp+1500h+var_14C8], r12
0x1800028de  call    cs:__imp_GetCurrentThreadId
0x1800028e4  mov     [rsp+1500h+var_14C0], eax
0x1800028e8  mov     [rsp+1500h+var_14A8], rsi
0x1800028ed  mov     [rsp+1500h+var_14A0], edi
0x1800028f1  mov     [rsp+1500h+var_149C], r15d
0x1800028f6  mov     [rsp+1500h+var_14B8], r12
0x1800028fb  mov     [rsp+1500h+var_14B0], r12
0x180002900  mov     [rbp+1400h+var_1458], r14
0x180002904  mov     [rbp+1400h+var_1450], rbx
0x180002908  mov     [rsp+1500h+var_1498], r12
0x18000290d  xorps   xmm0, xmm0
0x180002910  xor     eax, eax
0x180002912  movups  [rbp+1400h+var_1478], xmm0
0x180002916  mov     [rbp+1400h+var_1468], rax
0x18000291a  xorps   xmm1, xmm1
0x18000291d  movups  [rsp+1500h+var_1490], xmm1
0x180002922  mov     [rbp+1400h+var_1480], rax
0x180002926  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000292d  test    rax, rax
0x180002930  jz      short loc_18000293D
0x180002932  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002937  mov     [rbp+1400h+var_1460], rax
0x18000293b  jmp     short loc_180002941
0x18000293d  mov     [rbp+1400h+var_1460], r12
0x180002941  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002948  test    rax, rax
0x18000294b  jz      short loc_180002957
0x18000294d  lea     rcx, [rsp+1500h+var_14E0]
0x180002952  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002957  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000295e  test    rax, rax
0x180002961  jz      short loc_180002977
0x180002963  mov     r8d, 400h
0x180002969  lea     rdx, [rbp+1400h+var_1440]
0x18000296d  lea     rcx, [rsp+1500h+var_14E0]
0x180002972  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002977  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000297e  test    rax, rax
0x180002981  jz      short loc_18000298D
0x180002983  lea     rcx, [rsp+1500h+var_14E0]
0x180002988  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000298d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002994  test    rax, rax
0x180002997  jz      short loc_1800029AA
0x180002999  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000299e  jnz     short loc_1800029AA
0x1800029a0  lea     rcx, [rsp+1500h+var_14E0]
0x1800029a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029aa  cmp     [rsp+1500h+var_14D8], r12d
0x1800029af  jge     loc_180002AB8
0x1800029b5  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800029bc  jnz     short loc_1800029DD
0x1800029be  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800029c5  test    rax, rax
0x1800029c8  jz      short loc_1800029D3
0x1800029ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029cf  test    al, al
0x1800029d1  jmp     short loc_1800029DB
0x1800029d3  call    cs:__imp_IsDebuggerPresent
0x1800029d9  test    eax, eax
0x1800029db  jz      short loc_1800029E4
0x1800029dd  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800029e2  jz      short loc_180002A0A
0x1800029e4  mov     rax, cs:g_pfnResultLoggingCallback
0x1800029eb  test    rax, rax
0x1800029ee  jz      short loc_180002A63
0x1800029f0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800029f7  jnz     short loc_180002A63
0x1800029f9  xor     r8d, r8d
0x1800029fc  xor     edx, edx
0x1800029fe  lea     rcx, [rsp+1500h+var_14E0]
0x180002a03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a08  jmp     short loc_180002A63
0x180002a0a  mov     ebx, 800h
0x180002a0f  mov     rax, cs:g_pfnResultLoggingCallback
0x180002a16  test    rax, rax
0x180002a19  jz      short loc_180002A38
0x180002a1b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180002a22  jnz     short loc_180002A38
0x180002a24  mov     r8d, ebx
0x180002a27  lea     rdx, [rbp+1400h+OutputString]
0x180002a2e  lea     rcx, [rsp+1500h+var_14E0]
0x180002a33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a38  cmp     [rbp+1400h+OutputString], r12w
0x180002a40  jnz     short loc_180002A56
0x180002a42  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180002a47  mov     rdx, rbx; unsigned __int16 *
0x180002a4a  lea     rcx, [rbp+1400h+OutputString]; this
0x180002a51  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002a56  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180002a5d  call    cs:__imp_OutputDebugStringW
0x180002a63  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180002a68  jnz     short loc_180002A73
0x180002a6a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180002a71  jz      short loc_180002A85
0x180002a73  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002a7a  test    rax, rax
0x180002a7d  jz      short loc_180002A85
0x180002a7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a84  nop
0x180002a85  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180002a8a  jnz     short loc_180002AAD
0x180002a8c  mov     rcx, [rbp+1400h+var_40]
0x180002a93  xor     rcx, rsp; StackCookie
0x180002a96  call    __security_check_cookie
0x180002a9b  add     rsp, 14D0h
0x180002aa2  pop     r15
0x180002aa4  pop     r14
0x180002aa6  pop     r12
0x180002aa8  pop     rdi
0x180002aa9  pop     rsi
0x180002aaa  pop     rbx
0x180002aab  pop     rbp
0x180002aac  retn
0x180002aad  lea     rcx, [rsp+1500h+var_14E0]; this
0x180002ab2  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180002ab8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
