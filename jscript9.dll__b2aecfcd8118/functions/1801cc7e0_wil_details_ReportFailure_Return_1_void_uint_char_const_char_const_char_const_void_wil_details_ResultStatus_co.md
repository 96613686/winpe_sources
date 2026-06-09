# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1801cc7e0`
- end: `0x1801ccafe`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `798`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1801cc390`

## callees

- `0x1801cc7e0`
- `0x1801ce414`
- `0x1801d09d8`
- `0x1801d253c`
- `0x1801d2804`
- `0x1803481f0`
- `0x180348220`
- `0x180364010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x1801cc9fb`
- `KERNEL32!IsDebuggerPresent` at `0x1801cc9fb`
- `KERNEL32!GetCurrentThreadId` at `0x1801cc8fe`
- `KERNEL32!GetCurrentThreadId` at `0x1801cc8fe`
- `KERNEL32!OutputDebugStringW` at `0x1801cca6e`
- `KERNEL32!OutputDebugStringW` at `0x1801cca6e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        _WORD *a8,
        int a9,
        int a10)
{
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  unsigned int v18; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v19[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v20; // [rsp+40h] [rbp-C0h]
  __int128 v21; // [rsp+50h] [rbp-B0h]
  __int128 v22; // [rsp+60h] [rbp-A0h]
  __int128 v23; // [rsp+70h] [rbp-90h]
  __int128 v24; // [rsp+80h] [rbp-80h]
  _OWORD v25[2]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v26; // [rsp+B0h] [rbp-50h]
  __int64 v27; // [rsp+C0h] [rbp-40h]
  __int64 v28; // [rsp+D0h] [rbp-30h]
  _BYTE v29[1024]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR OutputString[2048]; // [rsp+4E0h] [rbp+3E0h] BYREF

  v28 = -2;
  *(_OWORD *)v19 = 0;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  memset(v25, 0, sizeof(v25));
  v26 = 0;
  v27 = 0;
  OutputString[0] = 0;
  v29[0] = 0;
  v19[1] = *(_QWORD *)a7;
  v18 = wil::details::RecordReturn((wil::details *)LODWORD(v19[1]), a2);
  LODWORD(v19[0]) = 1;
  HIDWORD(v19[0]) = a10;
  if ( *(_DWORD *)(a7 + 8) == 1 )
    HIDWORD(v19[0]) = a10 | 8;
  LODWORD(v20) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( a8 && *a8 )
    *((_QWORD *)&v20 + 1) = a8;
  else
    *((_QWORD *)&v20 + 1) = 0;
  LODWORD(v21) = GetCurrentThreadId();
  *((_QWORD *)&v22 + 1) = a3;
  v23 = __PAIR64__(v18, a2);
  *((_QWORD *)&v21 + 1) = a5;
  *(_QWORD *)&v22 = a4;
  *((_QWORD *)&v26 + 1) = a6;
  v27 = a1;
  v24 = 0;
  memset(v25, 0, sizeof(v25));
  if ( wil::details::g_pfnGetModuleName )
    *(_QWORD *)&v26 = wil::details::g_pfnGetModuleName();
  else
    *(_QWORD *)&v26 = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(v19);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(v19, v29, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(v19);
  if ( wil::details::g_pfnOriginateCallback && (v19[0] & 0x200000000LL) == 0 )
    wil::details::g_pfnOriginateCallback(v19);
  if ( SLODWORD(v19[1]) >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v17)
    || !wil::g_fResultOutputDebugString
    || (v19[0] & 0x200000000LL) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(v19, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(v19, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)v19, v16);
    OutputDebugStringW(OutputString);
  }
  if ( ((v19[0] & 0x400000000LL) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak();
  if ( (v19[0] & 0x100000000LL) != 0 )
    wil::details::WilFailFast((wil::details *)v19, v14);
}

```

## disassembly

```asm
0x1801cc7e0  mov     [rsp-8+arg_18], r9
0x1801cc7e5  mov     [rsp-8+arg_10], r8
0x1801cc7ea  mov     [rsp-8+arg_8], edx
0x1801cc7ee  mov     [rsp-8+arg_0], rcx
0x1801cc7f3  push    rbp
0x1801cc7f4  push    rbx
0x1801cc7f5  push    rsi
0x1801cc7f6  push    rdi
0x1801cc7f7  push    r12
0x1801cc7f9  push    r13
0x1801cc7fb  push    r14
0x1801cc7fd  push    r15
0x1801cc7ff  lea     rbp, [rsp-13F8h]
0x1801cc807  mov     eax, 14F8h
0x1801cc80c  call    _alloca_probe
0x1801cc811  sub     rsp, rax
0x1801cc814  mov     [rbp+1430h+var_1460], 0FFFFFFFFFFFFFFFEh
0x1801cc81c  mov     rax, cs:__security_cookie
0x1801cc823  xor     rax, rsp
0x1801cc826  mov     [rbp+1430h+var_50], rax
0x1801cc82d  mov     rdi, [rbp+1430h+arg_0]
0x1801cc834  mov     esi, [rbp+1430h+arg_8]
0x1801cc83a  mov     r14, [rbp+1430h+arg_10]
0x1801cc841  mov     r15, [rbp+1430h+arg_18]
0x1801cc848  mov     r12, [rbp+1430h+arg_20]
0x1801cc84f  mov     r13, [rbp+1430h+arg_28]
0x1801cc856  xorps   xmm0, xmm0
0x1801cc859  xor     eax, eax
0x1801cc85b  movups  xmmword ptr [rsp+1530h+var_1500], xmm0
0x1801cc860  movups  [rsp+1530h+var_14F0], xmm0
0x1801cc865  movups  [rsp+1530h+var_14E0], xmm0
0x1801cc86a  movups  [rsp+1530h+var_14D0], xmm0
0x1801cc86f  movups  [rsp+1530h+var_14C0], xmm0
0x1801cc874  movups  [rbp+1430h+var_14B0], xmm0
0x1801cc878  movups  [rbp+1430h+var_14A0], xmm0
0x1801cc87c  movups  [rbp+1430h+var_1490], xmm0
0x1801cc880  movups  [rbp+1430h+var_1480], xmm0
0x1801cc884  mov     [rbp+1430h+var_1470], rax
0x1801cc888  mov     [rbp+1430h+OutputString], ax
0x1801cc88f  mov     [rbp+1430h+var_1450], al
0x1801cc892  mov     rbx, [rbp+1430h+arg_30]
0x1801cc899  mov     ecx, [rbx]; this
0x1801cc89b  mov     dword ptr [rsp+1530h+var_1500+8], ecx
0x1801cc89f  mov     eax, [rbx+4]
0x1801cc8a2  mov     dword ptr [rsp+1530h+var_1500+0Ch], eax
0x1801cc8a6  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1801cc8ab  mov     [rsp+1530h+var_1510], eax
0x1801cc8af  mov     ecx, 1
0x1801cc8b4  mov     dword ptr [rsp+1530h+var_1500], ecx
0x1801cc8b8  mov     edx, [rbp+1430h+arg_48]
0x1801cc8be  mov     dword ptr [rsp+1530h+var_1500+4], edx
0x1801cc8c2  cmp     [rbx+8], ecx
0x1801cc8c5  jnz     short loc_1801CC8CE
0x1801cc8c7  or      edx, 8
0x1801cc8ca  mov     dword ptr [rsp+1530h+var_1500+4], edx
0x1801cc8ce  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1801cc8d6  inc     ecx
0x1801cc8d8  mov     dword ptr [rsp+1530h+var_14F0], ecx
0x1801cc8dc  mov     rax, [rbp+1430h+arg_38]
0x1801cc8e3  test    rax, rax
0x1801cc8e6  jz      short loc_1801CC8F7
0x1801cc8e8  cmp     word ptr [rax], 0
0x1801cc8ec  jz      short loc_1801CC8F7
0x1801cc8ee  mov     qword ptr [rsp+1530h+var_14F0+8], rax
0x1801cc8f3  xor     ebx, ebx
0x1801cc8f5  jmp     short loc_1801CC8FE
0x1801cc8f7  xor     ebx, ebx
0x1801cc8f9  mov     qword ptr [rsp+1530h+var_14F0+8], rbx
0x1801cc8fe  call    cs:__imp_GetCurrentThreadId
0x1801cc905  nop     dword ptr [rax+rax+00h]
0x1801cc90a  mov     dword ptr [rsp+1530h+var_14E0], eax
0x1801cc90e  mov     qword ptr [rsp+1530h+var_14D0+8], r14
0x1801cc913  mov     dword ptr [rsp+1530h+var_14C0], esi
0x1801cc917  mov     eax, [rsp+1530h+var_1510]
0x1801cc91b  mov     dword ptr [rsp+1530h+var_14C0+4], eax
0x1801cc91f  mov     qword ptr [rsp+1530h+var_14E0+8], r12
0x1801cc924  mov     qword ptr [rsp+1530h+var_14D0], r15
0x1801cc929  mov     qword ptr [rbp+1430h+var_1480+8], r13
0x1801cc92d  mov     [rbp+1430h+var_1470], rdi
0x1801cc931  mov     qword ptr [rsp+1530h+var_14C0+8], rbx
0x1801cc936  xorps   xmm0, xmm0
0x1801cc939  xor     eax, eax
0x1801cc93b  movups  [rbp+1430h+var_14A0+8], xmm0
0x1801cc93f  mov     qword ptr [rbp+1430h+var_1490+8], rax
0x1801cc943  xorps   xmm1, xmm1
0x1801cc946  movups  [rbp+1430h+var_14B0], xmm1
0x1801cc94a  mov     qword ptr [rbp+1430h+var_14A0], rax
0x1801cc94e  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1801cc955  test    rax, rax
0x1801cc958  jz      short loc_1801CC965
0x1801cc95a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801cc95f  mov     qword ptr [rbp+1430h+var_1480], rax
0x1801cc963  jmp     short loc_1801CC969
0x1801cc965  mov     qword ptr [rbp+1430h+var_1480], rbx
0x1801cc969  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1801cc970  test    rax, rax
0x1801cc973  jz      short loc_1801CC97F
0x1801cc975  lea     rcx, [rsp+1530h+var_1500]
0x1801cc97a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801cc97f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1801cc986  test    rax, rax
0x1801cc989  jz      short loc_1801CC99F
0x1801cc98b  mov     r8d, 400h
0x1801cc991  lea     rdx, [rbp+1430h+var_1450]
0x1801cc995  lea     rcx, [rsp+1530h+var_1500]
0x1801cc99a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801cc99f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1801cc9a6  test    rax, rax
0x1801cc9a9  jz      short loc_1801CC9B5
0x1801cc9ab  lea     rcx, [rsp+1530h+var_1500]
0x1801cc9b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801cc9b5  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1801cc9bc  test    rax, rax
0x1801cc9bf  jz      short loc_1801CC9D2
0x1801cc9c1  test    byte ptr [rsp+1530h+var_1500+4], 2
0x1801cc9c6  jnz     short loc_1801CC9D2
0x1801cc9c8  lea     rcx, [rsp+1530h+var_1500]
0x1801cc9cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801cc9d2  cmp     dword ptr [rsp+1530h+var_1500+8], 0
0x1801cc9d7  jge     loc_1801CCAF8
0x1801cc9dd  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, 0; bool wil::g_fIsDebuggerPresent
0x1801cc9e4  jnz     short loc_1801CCA0B
0x1801cc9e6  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1801cc9ed  test    rax, rax
0x1801cc9f0  jz      short loc_1801CC9FB
0x1801cc9f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801cc9f7  test    al, al
0x1801cc9f9  jmp     short loc_1801CCA09
0x1801cc9fb  call    cs:__imp_IsDebuggerPresent
0x1801cca02  nop     dword ptr [rax+rax+00h]
0x1801cca07  test    eax, eax
0x1801cca09  jz      short loc_1801CCA7C
0x1801cca0b  cmp     cs:?g_fResultOutputDebugString@wil@@3_NA, 0; bool wil::g_fResultOutputDebugString
0x1801cca12  jz      short loc_1801CCA7C
0x1801cca14  test    byte ptr [rsp+1530h+var_1500+4], 2
0x1801cca19  jnz     short loc_1801CCA7C
0x1801cca1b  mov     rax, cs:g_pfnResultLoggingCallback
0x1801cca22  test    rax, rax
0x1801cca25  jz      short loc_1801CCA47
0x1801cca27  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x1801cca2e  jnz     short loc_1801CCA47
0x1801cca30  mov     r8d, 800h
0x1801cca36  lea     rdx, [rbp+1430h+OutputString]
0x1801cca3d  lea     rcx, [rsp+1530h+var_1500]
0x1801cca42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801cca47  cmp     [rbp+1430h+OutputString], 0
0x1801cca4f  jnz     short loc_1801CCA67
0x1801cca51  lea     r8, [rsp+1530h+var_1500]; unsigned __int64
0x1801cca56  mov     edx, 800h; unsigned __int16 *
0x1801cca5b  lea     rcx, [rbp+1430h+OutputString]; this
0x1801cca62  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1801cca67  lea     rcx, [rbp+1430h+OutputString]; lpOutputString
0x1801cca6e  call    cs:__imp_OutputDebugStringW
0x1801cca75  nop     dword ptr [rax+rax+00h]
0x1801cca7a  jmp     short loc_1801CCAA0
0x1801cca7c  mov     rax, cs:g_pfnResultLoggingCallback
0x1801cca83  test    rax, rax
0x1801cca86  jz      short loc_1801CCAA0
0x1801cca88  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x1801cca8f  jnz     short loc_1801CCAA0
0x1801cca91  xor     r8d, r8d
0x1801cca94  xor     edx, edx
0x1801cca96  lea     rcx, [rsp+1530h+var_1500]
0x1801cca9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ccaa0  test    byte ptr [rsp+1530h+var_1500+4], 4
0x1801ccaa5  jnz     short loc_1801CCAB0
0x1801ccaa7  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, 0; bool wil::g_fBreakOnFailure
0x1801ccaae  jz      short loc_1801CCAC2
0x1801ccab0  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1801ccab7  test    rax, rax
0x1801ccaba  jz      short loc_1801CCAC2
0x1801ccabc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ccac1  nop
0x1801ccac2  test    byte ptr [rsp+1530h+var_1500+4], 1
0x1801ccac7  jnz     short loc_1801CCAED
0x1801ccac9  mov     rcx, [rbp+1430h+var_50]
0x1801ccad0  xor     rcx, rsp; StackCookie
0x1801ccad3  call    __security_check_cookie
0x1801ccad8  add     rsp, 14F8h
0x1801ccadf  pop     r15
0x1801ccae1  pop     r14
0x1801ccae3  pop     r13
0x1801ccae5  pop     r12
0x1801ccae7  pop     rdi
0x1801ccae8  pop     rsi
0x1801ccae9  pop     rbx
0x1801ccaea  pop     rbp
0x1801ccaeb  retn
0x1801ccaed  lea     rcx, [rsp+1530h+var_1500]; this
0x1801ccaf2  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1801ccaf8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
