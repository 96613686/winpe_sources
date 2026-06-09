# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18007742c`
- end: `0x18007769e`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `626`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800771f8`

## callees

- `0x18007742c`
- `0x180079424`
- `0x180079d70`
- `0x18007b550`
- `0x18007d05c`
- `0x180093bca`
- `0x180093c90`
- `0x180095010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800774cd`
- `KERNEL32!GetCurrentThreadId` at `0x1800774cd`
- `KERNEL32!IsDebuggerPresent` at `0x1800775d6`
- `KERNEL32!IsDebuggerPresent` at `0x1800775d6`
- `KERNEL32!OutputDebugStringW` at `0x180077666`
- `KERNEL32!OutputDebugStringW` at `0x180077666`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v10; // eax
  int v11; // edx
  int v12; // eax
  int v13; // edi
  int v14; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v16; // rdx
  __int64 v17; // rcx
  const struct wil::FailureInfo *v18; // r9
  bool v19; // zf
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD v26; // [rsp+40h] [rbp-C0h]
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

  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v10 = a7[1];
  v22 = *a7;
  v23 = v10;
  v12 = wil::details::RecordFailFast((wil::details *)(unsigned int)v22, v11);
  v19 = a7[2] == 1;
  v13 = v12;
  v20 = 3;
  v14 = 0;
  if ( v19 )
    v14 = 8;
  v21 = v14;
  v25 = 0;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v26 = CurrentThreadId;
  v30 = a2;
  v36 = 0;
  v34 = 0;
  v31 = v13;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v33 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v17);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
  {
    v22 = -2147418113;
    v23 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v16);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v19 = !IsDebuggerPresent())
      : (v19 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v17) == 0),
        v19)
    || (v21 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v20, v18);
    OutputDebugStringW(OutputString);
  }
  if ( (v21 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v17);
  }
  wil::details::WilFailFast((wil::details *)&v20, v16);
}

```

## disassembly

```asm
0x18007742c  mov     [rsp-8+arg_18], rbx
0x180077431  push    rbp
0x180077432  push    rsi
0x180077433  push    rdi
0x180077434  push    r12
0x180077436  push    r13
0x180077438  push    r14
0x18007743a  push    r15
0x18007743c  lea     rbp, [rsp-13C0h]
0x180077444  mov     eax, 14C0h
0x180077449  call    _alloca_probe
0x18007744e  sub     rsp, rax
0x180077451  mov     rsi, [rbp+13F0h+arg_28]
0x180077458  mov     r15, r8
0x18007745b  mov     r14d, edx
0x18007745e  mov     r12, rcx
0x180077461  xor     edx, edx; Val
0x180077463  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180077468  mov     r8d, 98h; Size
0x18007746e  call    memset_0
0x180077473  mov     rbx, [rbp+13F0h+arg_30]
0x18007747a  xor     r13d, r13d
0x18007747d  mov     [rbp+13F0h+OutputString], r13w
0x180077485  mov     [rbp+13F0h+var_1430], r13b
0x180077489  mov     ecx, [rbx]; this
0x18007748b  mov     eax, [rbx+4]
0x18007748e  mov     [rsp+14F0h+var_14C8], ecx
0x180077492  mov     [rsp+14F0h+var_14C4], eax
0x180077496  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18007749b  cmp     dword ptr [rbx+8], 1
0x18007749f  mov     edi, eax
0x1800774a1  lea     eax, [r13+8]
0x1800774a5  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x1800774ad  mov     ecx, r13d
0x1800774b0  cmovz   ecx, eax
0x1800774b3  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800774b7  lea     ecx, [rax-7]
0x1800774ba  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800774c2  inc     ecx
0x1800774c4  mov     [rsp+14F0h+var_14B8], r13
0x1800774c9  mov     [rsp+14F0h+var_14C0], ecx
0x1800774cd  call    cs:__imp_GetCurrentThreadId
0x1800774d4  nop     dword ptr [rax+rax+00h]
0x1800774d9  xorps   xmm0, xmm0
0x1800774dc  mov     [rsp+14F0h+var_1498], r15
0x1800774e1  mov     [rsp+14F0h+var_14B0], eax
0x1800774e5  xorps   xmm1, xmm1
0x1800774e8  xor     eax, eax
0x1800774ea  mov     [rsp+14F0h+var_1490], r14d
0x1800774ef  mov     [rbp+13F0h+var_1458], rax
0x1800774f3  mov     [rbp+13F0h+var_1470], rax
0x1800774f7  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800774fe  mov     [rsp+14F0h+var_148C], edi
0x180077502  mov     [rsp+14F0h+var_14A8], r13
0x180077507  mov     [rsp+14F0h+var_14A0], r13
0x18007750c  mov     [rbp+13F0h+var_1448], rsi
0x180077510  mov     [rbp+13F0h+var_1440], r12
0x180077514  mov     [rsp+14F0h+var_1488], r13
0x180077519  movups  [rbp+13F0h+var_1468], xmm0
0x18007751d  movups  [rsp+14F0h+var_1480], xmm1
0x180077522  test    rax, rax
0x180077525  jz      short loc_180077532
0x180077527  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007752c  mov     [rbp+13F0h+var_1450], rax
0x180077530  jmp     short loc_180077536
0x180077532  mov     [rbp+13F0h+var_1450], r13
0x180077536  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18007753d  test    rax, rax
0x180077540  jz      short loc_18007754C
0x180077542  lea     rcx, [rsp+14F0h+var_14D0]
0x180077547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007754c  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180077553  test    rax, rax
0x180077556  jz      short loc_18007756C
0x180077558  mov     r8d, 400h
0x18007755e  lea     rdx, [rbp+13F0h+var_1430]
0x180077562  lea     rcx, [rsp+14F0h+var_14D0]
0x180077567  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007756c  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180077573  test    rax, rax
0x180077576  jz      short loc_180077582
0x180077578  lea     rcx, [rsp+14F0h+var_14D0]
0x18007757d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077582  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180077589  test    rax, rax
0x18007758c  jz      short loc_18007759F
0x18007758e  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180077593  jnz     short loc_18007759F
0x180077595  lea     rcx, [rsp+14F0h+var_14D0]
0x18007759a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007759f  cmp     [rsp+14F0h+var_14C8], r13d
0x1800775a4  jl      short loc_1800775B8
0x1800775a6  mov     ecx, 8000FFFFh; this
0x1800775ab  mov     [rsp+14F0h+var_14C8], ecx
0x1800775af  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800775b4  mov     [rsp+14F0h+var_14C4], eax
0x1800775b8  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x1800775bf  jnz     short loc_1800775E6
0x1800775c1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800775c8  test    rax, rax
0x1800775cb  jz      short loc_1800775D6
0x1800775cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800775d2  test    al, al
0x1800775d4  jmp     short loc_1800775E4
0x1800775d6  call    cs:__imp_IsDebuggerPresent
0x1800775dd  nop     dword ptr [rax+rax+00h]
0x1800775e2  test    eax, eax
0x1800775e4  jz      short loc_1800775ED
0x1800775e6  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800775eb  jz      short loc_180077613
0x1800775ed  mov     rax, cs:g_pfnResultLoggingCallback
0x1800775f4  test    rax, rax
0x1800775f7  jz      short loc_180077672
0x1800775f9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180077600  jnz     short loc_180077672
0x180077602  xor     r8d, r8d
0x180077605  lea     rcx, [rsp+14F0h+var_14D0]
0x18007760a  xor     edx, edx
0x18007760c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077611  jmp     short loc_180077672
0x180077613  mov     rax, cs:g_pfnResultLoggingCallback
0x18007761a  mov     ebx, 800h
0x18007761f  test    rax, rax
0x180077622  jz      short loc_180077641
0x180077624  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18007762b  jnz     short loc_180077641
0x18007762d  mov     r8d, ebx
0x180077630  lea     rdx, [rbp+13F0h+OutputString]
0x180077637  lea     rcx, [rsp+14F0h+var_14D0]
0x18007763c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077641  cmp     [rbp+13F0h+OutputString], r13w
0x180077649  jnz     short loc_18007765F
0x18007764b  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180077650  mov     rdx, rbx; unsigned __int16 *
0x180077653  lea     rcx, [rbp+13F0h+OutputString]; this
0x18007765a  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18007765f  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180077666  call    cs:__imp_OutputDebugStringW
0x18007766d  nop     dword ptr [rax+rax+00h]
0x180077672  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180077677  jnz     short loc_180077682
0x180077679  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180077680  jz      short loc_180077693
0x180077682  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180077689  test    rax, rax
0x18007768c  jz      short loc_180077693
0x18007768e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077693  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180077698  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
