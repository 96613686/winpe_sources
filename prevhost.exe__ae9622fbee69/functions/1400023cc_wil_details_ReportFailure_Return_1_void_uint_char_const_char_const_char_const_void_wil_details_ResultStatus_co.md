# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1400023cc`
- end: `0x140002660`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140001eb4`

## callees

- `0x140001470`
- `0x140001e52`
- `0x1400023cc`
- `0x1400036a4`
- `0x1400049e0`
- `0x140005570`
- `0x14000564c`
- `0x140005b00`
- `0x140006010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140002476`
- `KERNEL32!GetCurrentThreadId` at `0x140002476`
- `KERNEL32!OutputDebugStringW` at `0x1400025fb`
- `KERNEL32!OutputDebugStringW` at `0x1400025fb`
- `KERNEL32!IsDebuggerPresent` at `0x140002571`
- `KERNEL32!IsDebuggerPresent` at `0x140002571`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdx
  int v12; // ebx
  int v13; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v15; // rdx
  wil::details::in1diag3 *v16; // rcx
  const struct wil::FailureInfo *v17; // r9
  bool v18; // zf
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh]
  int v21; // [rsp+28h] [rbp-D8h]
  int v22; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v23; // [rsp+30h] [rbp-D0h]
  __int64 v24; // [rsp+38h] [rbp-C8h]
  DWORD v25; // [rsp+40h] [rbp-C0h]
  __int64 v26; // [rsp+48h] [rbp-B8h]
  __int64 v27; // [rsp+50h] [rbp-B0h]
  const char *v28; // [rsp+58h] [rbp-A8h]
  int v29; // [rsp+60h] [rbp-A0h]
  int v30; // [rsp+64h] [rbp-9Ch]
  __int64 v31; // [rsp+68h] [rbp-98h]
  __int128 v32; // [rsp+70h] [rbp-90h]
  __int64 v33; // [rsp+80h] [rbp-80h]
  __int128 v34; // [rsp+88h] [rbp-78h]
  __int64 v35; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v37; // [rsp+A8h] [rbp-58h]
  __int64 v38; // [rsp+B0h] [rbp-50h]
  char v39[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v19, 0, 0x98u);
  OutputString[0] = 0;
  v39[0] = 0;
  v9 = a7[1];
  v21 = *a7;
  v22 = v9;
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v21, (int)a7);
  v18 = *(_DWORD *)(v11 + 8) == 1;
  v12 = v10;
  v19 = 1;
  v13 = 0;
  if ( v18 )
    v13 = 8;
  v20 = v13;
  v24 = 0;
  v23 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a2;
  v25 = CurrentThreadId;
  v30 = v12;
  v28 = "wil";
  v35 = 0;
  v33 = 0;
  v26 = 0;
  v27 = 0;
  v37 = a6;
  v38 = a1;
  v31 = 0;
  v34 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v16);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v19);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v19, v39, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v19);
  if ( wil::details::g_pfnOriginateCallback && (v20 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v19);
  if ( v21 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v16);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v18 = !IsDebuggerPresent())
      : (v18 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v16) == 0),
        v18)
    || (v20 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v19, v17);
    OutputDebugStringW(OutputString);
  }
  if ( ((v20 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v16);
  if ( (v20 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v19, v15);
}

```

## disassembly

```asm
0x1400023cc  mov     [rsp-8+arg_10], rbx
0x1400023d1  push    rbp
0x1400023d2  push    rsi
0x1400023d3  push    rdi
0x1400023d4  push    r14
0x1400023d6  push    r15
0x1400023d8  lea     rbp, [rsp-13D0h]
0x1400023e0  mov     eax, 14D0h
0x1400023e5  call    _alloca_probe
0x1400023ea  sub     rsp, rax
0x1400023ed  mov     rax, cs:__security_cookie
0x1400023f4  xor     rax, rsp
0x1400023f7  mov     [rbp+13F0h+var_30], rax
0x1400023fe  mov     rdi, [rbp+13F0h+arg_28]
0x140002405  mov     esi, edx
0x140002407  mov     r14, rcx
0x14000240a  xor     edx, edx; Val
0x14000240c  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x140002411  mov     r8d, 98h; Size
0x140002417  call    memset_0
0x14000241c  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x140002423  xor     r15d, r15d
0x140002426  mov     [rbp+13F0h+OutputString], r15w
0x14000242e  mov     [rbp+13F0h+var_1430], r15b
0x140002432  mov     ecx, [rdx]; this
0x140002434  mov     eax, [rdx+4]
0x140002437  mov     [rsp+14F0h+var_14C8], ecx
0x14000243b  mov     [rsp+14F0h+var_14C4], eax
0x14000243f  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140002444  cmp     dword ptr [rdx+8], 1
0x140002448  mov     ebx, eax
0x14000244a  lea     eax, [r15+8]
0x14000244e  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x140002456  mov     ecx, r15d
0x140002459  cmovz   ecx, eax
0x14000245c  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x140002460  lea     ecx, [rax-7]
0x140002463  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000246b  inc     ecx
0x14000246d  mov     [rsp+14F0h+var_14B8], r15
0x140002472  mov     [rsp+14F0h+var_14C0], ecx
0x140002476  call    cs:__imp_GetCurrentThreadId
0x14000247c  xorps   xmm0, xmm0
0x14000247f  mov     [rsp+14F0h+var_1490], esi
0x140002483  mov     [rsp+14F0h+var_14B0], eax
0x140002487  xorps   xmm1, xmm1
0x14000248a  lea     rax, aWil; "wil"
0x140002491  mov     [rsp+14F0h+var_148C], ebx
0x140002495  mov     [rsp+14F0h+var_1498], rax
0x14000249a  xor     eax, eax
0x14000249c  mov     [rbp+13F0h+var_1458], rax
0x1400024a0  mov     [rbp+13F0h+var_1470], rax
0x1400024a4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1400024ab  mov     [rsp+14F0h+var_14A8], r15
0x1400024b0  mov     [rsp+14F0h+var_14A0], r15
0x1400024b5  mov     [rbp+13F0h+var_1448], rdi
0x1400024b9  mov     [rbp+13F0h+var_1440], r14
0x1400024bd  mov     [rsp+14F0h+var_1488], r15
0x1400024c2  movups  [rbp+13F0h+var_1468], xmm0
0x1400024c6  movups  [rsp+14F0h+var_1480], xmm1
0x1400024cb  test    rax, rax
0x1400024ce  jz      short loc_1400024DB
0x1400024d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400024d5  mov     [rbp+13F0h+var_1450], rax
0x1400024d9  jmp     short loc_1400024DF
0x1400024db  mov     [rbp+13F0h+var_1450], r15
0x1400024df  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400024e6  test    rax, rax
0x1400024e9  jz      short loc_1400024F5
0x1400024eb  lea     rcx, [rsp+14F0h+var_14D0]
0x1400024f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400024f5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400024fc  test    rax, rax
0x1400024ff  jz      short loc_140002515
0x140002501  mov     r8d, 400h
0x140002507  lea     rdx, [rbp+13F0h+var_1430]
0x14000250b  lea     rcx, [rsp+14F0h+var_14D0]
0x140002510  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002515  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000251c  test    rax, rax
0x14000251f  jz      short loc_14000252B
0x140002521  lea     rcx, [rsp+14F0h+var_14D0]
0x140002526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000252b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002532  test    rax, rax
0x140002535  jz      short loc_140002548
0x140002537  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x14000253c  jnz     short loc_140002548
0x14000253e  lea     rcx, [rsp+14F0h+var_14D0]
0x140002543  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002548  cmp     [rsp+14F0h+var_14C8], r15d
0x14000254d  jge     loc_14000264F
0x140002553  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x14000255a  jnz     short loc_14000257B
0x14000255c  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140002563  test    rax, rax
0x140002566  jz      short loc_140002571
0x140002568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000256d  test    al, al
0x14000256f  jmp     short loc_140002579
0x140002571  call    cs:__imp_IsDebuggerPresent
0x140002577  test    eax, eax
0x140002579  jz      short loc_140002582
0x14000257b  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140002580  jz      short loc_1400025A8
0x140002582  mov     rax, cs:g_pfnResultLoggingCallback
0x140002589  test    rax, rax
0x14000258c  jz      short loc_140002601
0x14000258e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140002595  jnz     short loc_140002601
0x140002597  xor     r8d, r8d
0x14000259a  lea     rcx, [rsp+14F0h+var_14D0]
0x14000259f  xor     edx, edx
0x1400025a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400025a6  jmp     short loc_140002601
0x1400025a8  mov     rax, cs:g_pfnResultLoggingCallback
0x1400025af  mov     ebx, 800h
0x1400025b4  test    rax, rax
0x1400025b7  jz      short loc_1400025D6
0x1400025b9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1400025c0  jnz     short loc_1400025D6
0x1400025c2  mov     r8d, ebx
0x1400025c5  lea     rdx, [rbp+13F0h+OutputString]
0x1400025cc  lea     rcx, [rsp+14F0h+var_14D0]
0x1400025d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400025d6  cmp     [rbp+13F0h+OutputString], r15w
0x1400025de  jnz     short loc_1400025F4
0x1400025e0  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1400025e5  mov     rdx, rbx; unsigned __int16 *
0x1400025e8  lea     rcx, [rbp+13F0h+OutputString]; this
0x1400025ef  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1400025f4  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1400025fb  call    cs:__imp_OutputDebugStringW
0x140002601  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x140002606  jnz     short loc_140002611
0x140002608  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x14000260f  jz      short loc_140002622
0x140002611  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140002618  test    rax, rax
0x14000261b  jz      short loc_140002622
0x14000261d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002622  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x140002627  jnz     short loc_140002655
0x140002629  mov     rcx, [rbp+13F0h+var_30]
0x140002630  xor     rcx, rsp; StackCookie
0x140002633  call    __security_check_cookie
0x140002638  mov     rbx, [rsp+14F0h+arg_10]
0x140002640  add     rsp, 14D0h
0x140002647  pop     r15
0x140002649  pop     r14
0x14000264b  pop     rdi
0x14000264c  pop     rsi
0x14000264d  pop     rbp
0x14000264e  retn
0x14000264f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140002655  lea     rcx, [rsp+14F0h+var_14D0]; this
0x14000265a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
