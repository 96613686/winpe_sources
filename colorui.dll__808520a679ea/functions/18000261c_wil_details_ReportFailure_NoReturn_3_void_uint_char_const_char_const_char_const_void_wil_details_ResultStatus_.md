# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18000261c`
- end: `0x18000287c`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `608`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800023b8`

## callees

- `0x18000261c`
- `0x180005c74`
- `0x1800064a0`
- `0x180007d80`
- `0x18000b220`
- `0x1800184ce`
- `0x180018590`
- `0x180019010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800026bd`
- `KERNEL32!GetCurrentThreadId` at `0x1800026bd`
- `KERNEL32!OutputDebugStringW` at `0x18000284a`
- `KERNEL32!OutputDebugStringW` at `0x18000284a`
- `KERNEL32!IsDebuggerPresent` at `0x1800027c0`
- `KERNEL32!IsDebuggerPresent` at `0x1800027c0`

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
0x18000261c  mov     [rsp-8+arg_18], rbx
0x180002621  push    rbp
0x180002622  push    rsi
0x180002623  push    rdi
0x180002624  push    r12
0x180002626  push    r13
0x180002628  push    r14
0x18000262a  push    r15
0x18000262c  lea     rbp, [rsp-13C0h]
0x180002634  mov     eax, 14C0h
0x180002639  call    _alloca_probe
0x18000263e  sub     rsp, rax
0x180002641  mov     rsi, [rbp+13F0h+arg_28]
0x180002648  mov     r15, r8
0x18000264b  mov     r14d, edx
0x18000264e  mov     r12, rcx
0x180002651  xor     edx, edx; Val
0x180002653  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180002658  mov     r8d, 98h; Size
0x18000265e  call    memset_0
0x180002663  mov     rbx, [rbp+13F0h+arg_30]
0x18000266a  xor     r13d, r13d
0x18000266d  mov     [rbp+13F0h+OutputString], r13w
0x180002675  mov     [rbp+13F0h+var_1430], r13b
0x180002679  mov     ecx, [rbx]; this
0x18000267b  mov     eax, [rbx+4]
0x18000267e  mov     [rsp+14F0h+var_14C8], ecx
0x180002682  mov     [rsp+14F0h+var_14C4], eax
0x180002686  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000268b  cmp     dword ptr [rbx+8], 1
0x18000268f  mov     edi, eax
0x180002691  lea     eax, [r13+8]
0x180002695  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x18000269d  mov     ecx, r13d
0x1800026a0  cmovz   ecx, eax
0x1800026a3  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800026a7  lea     ecx, [rax-7]
0x1800026aa  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800026b2  inc     ecx
0x1800026b4  mov     [rsp+14F0h+var_14B8], r13
0x1800026b9  mov     [rsp+14F0h+var_14C0], ecx
0x1800026bd  call    cs:__imp_GetCurrentThreadId
0x1800026c3  xorps   xmm0, xmm0
0x1800026c6  mov     [rsp+14F0h+var_1498], r15
0x1800026cb  mov     [rsp+14F0h+var_14B0], eax
0x1800026cf  xorps   xmm1, xmm1
0x1800026d2  xor     eax, eax
0x1800026d4  mov     [rsp+14F0h+var_1490], r14d
0x1800026d9  mov     [rbp+13F0h+var_1458], rax
0x1800026dd  mov     [rbp+13F0h+var_1470], rax
0x1800026e1  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800026e8  mov     [rsp+14F0h+var_148C], edi
0x1800026ec  mov     [rsp+14F0h+var_14A8], r13
0x1800026f1  mov     [rsp+14F0h+var_14A0], r13
0x1800026f6  mov     [rbp+13F0h+var_1448], rsi
0x1800026fa  mov     [rbp+13F0h+var_1440], r12
0x1800026fe  mov     [rsp+14F0h+var_1488], r13
0x180002703  movups  [rbp+13F0h+var_1468], xmm0
0x180002707  movups  [rsp+14F0h+var_1480], xmm1
0x18000270c  test    rax, rax
0x18000270f  jz      short loc_18000271C
0x180002711  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002716  mov     [rbp+13F0h+var_1450], rax
0x18000271a  jmp     short loc_180002720
0x18000271c  mov     [rbp+13F0h+var_1450], r13
0x180002720  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002727  test    rax, rax
0x18000272a  jz      short loc_180002736
0x18000272c  lea     rcx, [rsp+14F0h+var_14D0]
0x180002731  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002736  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000273d  test    rax, rax
0x180002740  jz      short loc_180002756
0x180002742  mov     r8d, 400h
0x180002748  lea     rdx, [rbp+13F0h+var_1430]
0x18000274c  lea     rcx, [rsp+14F0h+var_14D0]
0x180002751  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002756  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000275d  test    rax, rax
0x180002760  jz      short loc_18000276C
0x180002762  lea     rcx, [rsp+14F0h+var_14D0]
0x180002767  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000276c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002773  test    rax, rax
0x180002776  jz      short loc_180002789
0x180002778  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000277d  jnz     short loc_180002789
0x18000277f  lea     rcx, [rsp+14F0h+var_14D0]
0x180002784  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002789  cmp     [rsp+14F0h+var_14C8], r13d
0x18000278e  jl      short loc_1800027A2
0x180002790  mov     ecx, 8000FFFFh; this
0x180002795  mov     [rsp+14F0h+var_14C8], ecx
0x180002799  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000279e  mov     [rsp+14F0h+var_14C4], eax
0x1800027a2  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x1800027a9  jnz     short loc_1800027CA
0x1800027ab  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800027b2  test    rax, rax
0x1800027b5  jz      short loc_1800027C0
0x1800027b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027bc  test    al, al
0x1800027be  jmp     short loc_1800027C8
0x1800027c0  call    cs:__imp_IsDebuggerPresent
0x1800027c6  test    eax, eax
0x1800027c8  jz      short loc_1800027D1
0x1800027ca  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800027cf  jz      short loc_1800027F7
0x1800027d1  mov     rax, cs:g_pfnResultLoggingCallback
0x1800027d8  test    rax, rax
0x1800027db  jz      short loc_180002850
0x1800027dd  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800027e4  jnz     short loc_180002850
0x1800027e6  xor     r8d, r8d
0x1800027e9  lea     rcx, [rsp+14F0h+var_14D0]
0x1800027ee  xor     edx, edx
0x1800027f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027f5  jmp     short loc_180002850
0x1800027f7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800027fe  mov     ebx, 800h
0x180002803  test    rax, rax
0x180002806  jz      short loc_180002825
0x180002808  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000280f  jnz     short loc_180002825
0x180002811  mov     r8d, ebx
0x180002814  lea     rdx, [rbp+13F0h+OutputString]
0x18000281b  lea     rcx, [rsp+14F0h+var_14D0]
0x180002820  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002825  cmp     [rbp+13F0h+OutputString], r13w
0x18000282d  jnz     short loc_180002843
0x18000282f  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180002834  mov     rdx, rbx; unsigned __int16 *
0x180002837  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000283e  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002843  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000284a  call    cs:__imp_OutputDebugStringW
0x180002850  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180002855  jnz     short loc_180002860
0x180002857  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18000285e  jz      short loc_180002871
0x180002860  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002867  test    rax, rax
0x18000286a  jz      short loc_180002871
0x18000286c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002871  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180002876  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
