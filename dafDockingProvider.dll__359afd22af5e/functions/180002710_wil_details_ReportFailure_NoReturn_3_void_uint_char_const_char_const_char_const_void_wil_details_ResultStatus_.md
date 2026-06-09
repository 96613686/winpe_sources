# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180002710`
- end: `0x180002972`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `610`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800024b4`

## callees

- `0x180002710`
- `0x1800048b4`
- `0x180005050`
- `0x180005c30`
- `0x180007d20`
- `0x18001ca3e`
- `0x18001cb00`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800027b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800027b2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800028b5`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800028b5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000293f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000293f`

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
  int v10; // edx
  int v11; // edi
  int v12; // ecx
  const struct wil::FailureInfo *v13; // rdx
  __int64 v14; // rcx
  const struct wil::FailureInfo *v15; // r9
  bool v16; // zf
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh]
  int v19; // [rsp+28h] [rbp-D8h]
  int v20; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v21; // [rsp+30h] [rbp-D0h]
  __int64 v22; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v24; // [rsp+48h] [rbp-B8h]
  __int64 v25; // [rsp+50h] [rbp-B0h]
  __int64 v26; // [rsp+58h] [rbp-A8h]
  int v27; // [rsp+60h] [rbp-A0h]
  int v28; // [rsp+64h] [rbp-9Ch]
  __int64 v29; // [rsp+68h] [rbp-98h]
  __int128 v30; // [rsp+70h] [rbp-90h]
  __int64 v31; // [rsp+80h] [rbp-80h]
  __int128 v32; // [rsp+88h] [rbp-78h]
  __int64 v33; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v35; // [rsp+A8h] [rbp-58h]
  __int64 v36; // [rsp+B0h] [rbp-50h]
  char v37[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v17, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
  v19 = *a7;
  v20 = a7[1];
  v11 = wil::details::RecordFailFast((wil::details *)(unsigned int)v19, v10);
  v17 = 3;
  v12 = 0;
  if ( a7[2] == 1 )
    v12 = 8;
  v18 = v12;
  v21 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v26 = a3;
  v27 = a2;
  v28 = v11;
  v24 = 0;
  v25 = 0;
  v35 = a6;
  v36 = a1;
  v29 = 0;
  v32 = 0;
  v33 = 0;
  v30 = 0;
  v31 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v14);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v17);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v17, v37, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v17);
  if ( wil::details::g_pfnOriginateCallback && (v18 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v17);
  if ( v19 >= 0 )
  {
    v19 = -2147418113;
    v20 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v13);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v16 = !IsDebuggerPresent())
      : (v16 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v14) == 0),
        v16)
    || (v18 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v17, v15);
    OutputDebugStringW(OutputString);
  }
  if ( (v18 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v14);
  }
  wil::details::WilFailFast((wil::details *)&v17, v13);
}

```

## disassembly

```asm
0x180002710  mov     [rsp-8+arg_18], rbx
0x180002715  push    rbp
0x180002716  push    rsi
0x180002717  push    rdi
0x180002718  push    r12
0x18000271a  push    r13
0x18000271c  push    r14
0x18000271e  push    r15
0x180002720  lea     rbp, [rsp-13C0h]
0x180002728  mov     eax, 14C0h
0x18000272d  call    _alloca_probe
0x180002732  sub     rsp, rax
0x180002735  mov     r15, r8
0x180002738  mov     r14d, edx
0x18000273b  mov     r12, rcx
0x18000273e  mov     rsi, [rbp+13F0h+arg_28]
0x180002745  xor     edx, edx; Val
0x180002747  mov     r8d, 98h; Size
0x18000274d  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180002752  call    memset_0
0x180002757  nop
0x180002758  xor     r13d, r13d
0x18000275b  mov     [rbp+13F0h+OutputString], r13w
0x180002763  mov     [rbp+13F0h+var_1430], r13b
0x180002767  mov     rbx, [rbp+13F0h+arg_30]
0x18000276e  mov     ecx, [rbx]; this
0x180002770  mov     [rsp+14F0h+var_14C8], ecx
0x180002774  mov     eax, [rbx+4]
0x180002777  mov     [rsp+14F0h+var_14C4], eax
0x18000277b  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180002780  mov     edi, eax
0x180002782  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x18000278a  mov     ecx, r13d
0x18000278d  lea     eax, [r13+8]
0x180002791  cmp     dword ptr [rbx+8], 1
0x180002795  cmovz   ecx, eax
0x180002798  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000279c  lea     ecx, [rax-7]
0x18000279f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800027a7  inc     ecx
0x1800027a9  mov     [rsp+14F0h+var_14C0], ecx
0x1800027ad  mov     [rsp+14F0h+var_14B8], r13
0x1800027b2  call    cs:__imp_GetCurrentThreadId
0x1800027b8  mov     [rsp+14F0h+var_14B0], eax
0x1800027bc  mov     [rsp+14F0h+var_1498], r15
0x1800027c1  mov     [rsp+14F0h+var_1490], r14d
0x1800027c6  mov     [rsp+14F0h+var_148C], edi
0x1800027ca  mov     [rsp+14F0h+var_14A8], r13
0x1800027cf  mov     [rsp+14F0h+var_14A0], r13
0x1800027d4  mov     [rbp+13F0h+var_1448], rsi
0x1800027d8  mov     [rbp+13F0h+var_1440], r12
0x1800027dc  mov     [rsp+14F0h+var_1488], r13
0x1800027e1  xorps   xmm0, xmm0
0x1800027e4  xor     eax, eax
0x1800027e6  movups  [rbp+13F0h+var_1468], xmm0
0x1800027ea  mov     [rbp+13F0h+var_1458], rax
0x1800027ee  xorps   xmm1, xmm1
0x1800027f1  movups  [rsp+14F0h+var_1480], xmm1
0x1800027f6  mov     [rbp+13F0h+var_1470], rax
0x1800027fa  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002801  test    rax, rax
0x180002804  jz      short loc_180002811
0x180002806  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000280b  mov     [rbp+13F0h+var_1450], rax
0x18000280f  jmp     short loc_180002815
0x180002811  mov     [rbp+13F0h+var_1450], r13
0x180002815  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000281c  test    rax, rax
0x18000281f  jz      short loc_18000282B
0x180002821  lea     rcx, [rsp+14F0h+var_14D0]
0x180002826  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000282b  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002832  test    rax, rax
0x180002835  jz      short loc_18000284B
0x180002837  mov     r8d, 400h
0x18000283d  lea     rdx, [rbp+13F0h+var_1430]
0x180002841  lea     rcx, [rsp+14F0h+var_14D0]
0x180002846  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000284b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002852  test    rax, rax
0x180002855  jz      short loc_180002861
0x180002857  lea     rcx, [rsp+14F0h+var_14D0]
0x18000285c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002861  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002868  test    rax, rax
0x18000286b  jz      short loc_18000287E
0x18000286d  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002872  jnz     short loc_18000287E
0x180002874  lea     rcx, [rsp+14F0h+var_14D0]
0x180002879  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000287e  cmp     [rsp+14F0h+var_14C8], r13d
0x180002883  jl      short loc_180002897
0x180002885  mov     ecx, 8000FFFFh; this
0x18000288a  mov     [rsp+14F0h+var_14C8], ecx
0x18000288e  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180002893  mov     [rsp+14F0h+var_14C4], eax
0x180002897  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000289e  jnz     short loc_1800028BF
0x1800028a0  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800028a7  test    rax, rax
0x1800028aa  jz      short loc_1800028B5
0x1800028ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028b1  test    al, al
0x1800028b3  jmp     short loc_1800028BD
0x1800028b5  call    cs:__imp_IsDebuggerPresent
0x1800028bb  test    eax, eax
0x1800028bd  jz      short loc_1800028C6
0x1800028bf  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800028c4  jz      short loc_1800028EC
0x1800028c6  mov     rax, cs:g_pfnResultLoggingCallback
0x1800028cd  test    rax, rax
0x1800028d0  jz      short loc_180002945
0x1800028d2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800028d9  jnz     short loc_180002945
0x1800028db  xor     r8d, r8d
0x1800028de  xor     edx, edx
0x1800028e0  lea     rcx, [rsp+14F0h+var_14D0]
0x1800028e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028ea  jmp     short loc_180002945
0x1800028ec  mov     ebx, 800h
0x1800028f1  mov     rax, cs:g_pfnResultLoggingCallback
0x1800028f8  test    rax, rax
0x1800028fb  jz      short loc_18000291A
0x1800028fd  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180002904  jnz     short loc_18000291A
0x180002906  mov     r8d, ebx
0x180002909  lea     rdx, [rbp+13F0h+OutputString]
0x180002910  lea     rcx, [rsp+14F0h+var_14D0]
0x180002915  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000291a  cmp     [rbp+13F0h+OutputString], r13w
0x180002922  jnz     short loc_180002938
0x180002924  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180002929  mov     rdx, rbx; unsigned __int16 *
0x18000292c  lea     rcx, [rbp+13F0h+OutputString]; this
0x180002933  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002938  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000293f  call    cs:__imp_OutputDebugStringW
0x180002945  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000294a  jnz     short loc_180002955
0x18000294c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180002953  jz      short loc_180002967
0x180002955  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000295c  test    rax, rax
0x18000295f  jz      short loc_180002967
0x180002961  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002966  nop
0x180002967  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000296c  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
