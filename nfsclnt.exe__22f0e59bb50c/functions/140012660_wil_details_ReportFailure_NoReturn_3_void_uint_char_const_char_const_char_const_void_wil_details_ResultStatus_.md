# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x140012660`
- end: `0x1400128c0`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `608`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140012404`

## callees

- `0x140012660`
- `0x140014574`
- `0x140014d0c`
- `0x1400158e0`
- `0x140017510`
- `0x14001830e`
- `0x1400183e0`
- `0x140019010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x140012804`
- `KERNEL32!IsDebuggerPresent` at `0x140012804`
- `KERNEL32!OutputDebugStringW` at `0x14001288e`
- `KERNEL32!OutputDebugStringW` at `0x14001288e`
- `KERNEL32!GetCurrentThreadId` at `0x140012701`
- `KERNEL32!GetCurrentThreadId` at `0x140012701`

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
0x140012660  mov     [rsp-8+arg_18], rbx
0x140012665  push    rbp
0x140012666  push    rsi
0x140012667  push    rdi
0x140012668  push    r12
0x14001266a  push    r13
0x14001266c  push    r14
0x14001266e  push    r15
0x140012670  lea     rbp, [rsp-13C0h]
0x140012678  mov     eax, 14C0h
0x14001267d  call    _alloca_probe
0x140012682  sub     rsp, rax
0x140012685  mov     rsi, [rbp+13F0h+arg_28]
0x14001268c  mov     r15, r8
0x14001268f  mov     r14d, edx
0x140012692  mov     r12, rcx
0x140012695  xor     edx, edx; Val
0x140012697  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x14001269c  mov     r8d, 98h; Size
0x1400126a2  call    memset_0
0x1400126a7  mov     rbx, [rbp+13F0h+arg_30]
0x1400126ae  xor     r13d, r13d
0x1400126b1  mov     [rbp+13F0h+OutputString], r13w
0x1400126b9  mov     [rbp+13F0h+var_1430], r13b
0x1400126bd  mov     ecx, [rbx]; this
0x1400126bf  mov     eax, [rbx+4]
0x1400126c2  mov     [rsp+14F0h+var_14C8], ecx
0x1400126c6  mov     [rsp+14F0h+var_14C4], eax
0x1400126ca  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1400126cf  cmp     dword ptr [rbx+8], 1
0x1400126d3  mov     edi, eax
0x1400126d5  lea     eax, [r13+8]
0x1400126d9  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x1400126e1  mov     ecx, r13d
0x1400126e4  cmovz   ecx, eax
0x1400126e7  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1400126eb  lea     ecx, [rax-7]
0x1400126ee  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400126f6  inc     ecx
0x1400126f8  mov     [rsp+14F0h+var_14B8], r13
0x1400126fd  mov     [rsp+14F0h+var_14C0], ecx
0x140012701  call    cs:__imp_GetCurrentThreadId
0x140012707  xorps   xmm0, xmm0
0x14001270a  mov     [rsp+14F0h+var_1498], r15
0x14001270f  mov     [rsp+14F0h+var_14B0], eax
0x140012713  xorps   xmm1, xmm1
0x140012716  xor     eax, eax
0x140012718  mov     [rsp+14F0h+var_1490], r14d
0x14001271d  mov     [rbp+13F0h+var_1458], rax
0x140012721  mov     [rbp+13F0h+var_1470], rax
0x140012725  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14001272c  mov     [rsp+14F0h+var_148C], edi
0x140012730  mov     [rsp+14F0h+var_14A8], r13
0x140012735  mov     [rsp+14F0h+var_14A0], r13
0x14001273a  mov     [rbp+13F0h+var_1448], rsi
0x14001273e  mov     [rbp+13F0h+var_1440], r12
0x140012742  mov     [rsp+14F0h+var_1488], r13
0x140012747  movups  [rbp+13F0h+var_1468], xmm0
0x14001274b  movups  [rsp+14F0h+var_1480], xmm1
0x140012750  test    rax, rax
0x140012753  jz      short loc_140012760
0x140012755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001275a  mov     [rbp+13F0h+var_1450], rax
0x14001275e  jmp     short loc_140012764
0x140012760  mov     [rbp+13F0h+var_1450], r13
0x140012764  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14001276b  test    rax, rax
0x14001276e  jz      short loc_14001277A
0x140012770  lea     rcx, [rsp+14F0h+var_14D0]
0x140012775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001277a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140012781  test    rax, rax
0x140012784  jz      short loc_14001279A
0x140012786  mov     r8d, 400h
0x14001278c  lea     rdx, [rbp+13F0h+var_1430]
0x140012790  lea     rcx, [rsp+14F0h+var_14D0]
0x140012795  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001279a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400127a1  test    rax, rax
0x1400127a4  jz      short loc_1400127B0
0x1400127a6  lea     rcx, [rsp+14F0h+var_14D0]
0x1400127ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400127b0  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400127b7  test    rax, rax
0x1400127ba  jz      short loc_1400127CD
0x1400127bc  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1400127c1  jnz     short loc_1400127CD
0x1400127c3  lea     rcx, [rsp+14F0h+var_14D0]
0x1400127c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400127cd  cmp     [rsp+14F0h+var_14C8], r13d
0x1400127d2  jl      short loc_1400127E6
0x1400127d4  mov     ecx, 8000FFFFh; this
0x1400127d9  mov     [rsp+14F0h+var_14C8], ecx
0x1400127dd  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400127e2  mov     [rsp+14F0h+var_14C4], eax
0x1400127e6  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x1400127ed  jnz     short loc_14001280E
0x1400127ef  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400127f6  test    rax, rax
0x1400127f9  jz      short loc_140012804
0x1400127fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012800  test    al, al
0x140012802  jmp     short loc_14001280C
0x140012804  call    cs:__imp_IsDebuggerPresent
0x14001280a  test    eax, eax
0x14001280c  jz      short loc_140012815
0x14001280e  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140012813  jz      short loc_14001283B
0x140012815  mov     rax, cs:g_pfnResultLoggingCallback
0x14001281c  test    rax, rax
0x14001281f  jz      short loc_140012894
0x140012821  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140012828  jnz     short loc_140012894
0x14001282a  xor     r8d, r8d
0x14001282d  lea     rcx, [rsp+14F0h+var_14D0]
0x140012832  xor     edx, edx
0x140012834  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012839  jmp     short loc_140012894
0x14001283b  mov     rax, cs:g_pfnResultLoggingCallback
0x140012842  mov     ebx, 800h
0x140012847  test    rax, rax
0x14001284a  jz      short loc_140012869
0x14001284c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140012853  jnz     short loc_140012869
0x140012855  mov     r8d, ebx
0x140012858  lea     rdx, [rbp+13F0h+OutputString]
0x14001285f  lea     rcx, [rsp+14F0h+var_14D0]
0x140012864  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012869  cmp     [rbp+13F0h+OutputString], r13w
0x140012871  jnz     short loc_140012887
0x140012873  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x140012878  mov     rdx, rbx; unsigned __int16 *
0x14001287b  lea     rcx, [rbp+13F0h+OutputString]; this
0x140012882  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140012887  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x14001288e  call    cs:__imp_OutputDebugStringW
0x140012894  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x140012899  jnz     short loc_1400128A4
0x14001289b  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1400128a2  jz      short loc_1400128B5
0x1400128a4  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400128ab  test    rax, rax
0x1400128ae  jz      short loc_1400128B5
0x1400128b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400128b5  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1400128ba  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
