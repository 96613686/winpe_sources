# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x14000215c`
- end: `0x1400023c3`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `615`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140001f10`

## callees

- `0x140001e52`
- `0x14000215c`
- `0x1400036a4`
- `0x140003e3c`
- `0x1400049b0`
- `0x140005570`
- `0x140005b00`
- `0x140006010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400021fd`
- `KERNEL32!GetCurrentThreadId` at `0x1400021fd`
- `KERNEL32!OutputDebugStringW` at `0x140002391`
- `KERNEL32!OutputDebugStringW` at `0x140002391`
- `KERNEL32!IsDebuggerPresent` at `0x140002307`
- `KERNEL32!IsDebuggerPresent` at `0x140002307`

## string_xrefs

- `0x140002212`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  int v9; // eax
  int v10; // edx
  int v11; // eax
  int v12; // edi
  int v13; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v15; // rdx
  __int64 v16; // rcx
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
  WCHAR OutputString[2064]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v19, 0, 0x98u);
  OutputString[0] = 0;
  v39[0] = 0;
  v9 = a7[1];
  v21 = *a7;
  v22 = v9;
  v11 = wil::details::RecordFailFast((wil::details *)(unsigned int)v21, v10);
  v18 = a7[2] == 1;
  v12 = v11;
  v19 = 3;
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
  v28 = "onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h";
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
  {
    v21 = -2147418113;
    v22 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v15);
  }
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
  if ( (v20 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v16);
  }
  wil::details::WilFailFast((wil::details *)&v19, v15);
}

```

## disassembly

```asm
0x14000215c  mov     [rsp-8+arg_10], rbx
0x140002161  mov     [rsp-8+arg_18], rsi
0x140002166  push    rbp
0x140002167  push    rdi
0x140002168  push    r12
0x14000216a  push    r14
0x14000216c  push    r15
0x14000216e  lea     rbp, [rsp-13C0h]
0x140002176  mov     eax, 14C0h
0x14000217b  call    _alloca_probe
0x140002180  sub     rsp, rax
0x140002183  mov     rsi, [rbp+13E0h+arg_28]
0x14000218a  mov     r14d, edx
0x14000218d  mov     r15, rcx
0x140002190  xor     edx, edx; Val
0x140002192  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x140002197  mov     r8d, 98h; Size
0x14000219d  call    memset_0
0x1400021a2  mov     rbx, [rbp+13E0h+arg_30]
0x1400021a9  xor     r12d, r12d
0x1400021ac  mov     [rbp+13E0h+OutputString], r12w
0x1400021b4  mov     [rbp+13E0h+var_1420], r12b
0x1400021b8  mov     ecx, [rbx]; this
0x1400021ba  mov     eax, [rbx+4]
0x1400021bd  mov     [rsp+14E0h+var_14B8], ecx
0x1400021c1  mov     [rsp+14E0h+var_14B4], eax
0x1400021c5  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1400021ca  cmp     dword ptr [rbx+8], 1
0x1400021ce  mov     edi, eax
0x1400021d0  lea     eax, [r12+8]
0x1400021d5  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x1400021dd  mov     ecx, r12d
0x1400021e0  cmovz   ecx, eax
0x1400021e3  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x1400021e7  lea     ecx, [rax-7]
0x1400021ea  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400021f2  inc     ecx
0x1400021f4  mov     [rsp+14E0h+var_14A8], r12
0x1400021f9  mov     [rsp+14E0h+var_14B0], ecx
0x1400021fd  call    cs:__imp_GetCurrentThreadId
0x140002203  xorps   xmm0, xmm0
0x140002206  mov     [rsp+14E0h+var_1480], r14d
0x14000220b  mov     [rsp+14E0h+var_14A0], eax
0x14000220f  xorps   xmm1, xmm1
0x140002212  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140002219  mov     [rsp+14E0h+var_147C], edi
0x14000221d  mov     [rsp+14E0h+var_1488], rax
0x140002222  xor     eax, eax
0x140002224  mov     [rbp+13E0h+var_1448], rax
0x140002228  mov     [rbp+13E0h+var_1460], rax
0x14000222c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140002233  mov     [rsp+14E0h+var_1498], r12
0x140002238  mov     [rsp+14E0h+var_1490], r12
0x14000223d  mov     [rbp+13E0h+var_1438], rsi
0x140002241  mov     [rbp+13E0h+var_1430], r15
0x140002245  mov     [rsp+14E0h+var_1478], r12
0x14000224a  movups  [rbp+13E0h+var_1458], xmm0
0x14000224e  movups  [rsp+14E0h+var_1470], xmm1
0x140002253  test    rax, rax
0x140002256  jz      short loc_140002263
0x140002258  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000225d  mov     [rbp+13E0h+var_1440], rax
0x140002261  jmp     short loc_140002267
0x140002263  mov     [rbp+13E0h+var_1440], r12
0x140002267  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14000226e  test    rax, rax
0x140002271  jz      short loc_14000227D
0x140002273  lea     rcx, [rsp+14E0h+var_14C0]
0x140002278  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000227d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140002284  test    rax, rax
0x140002287  jz      short loc_14000229D
0x140002289  mov     r8d, 400h
0x14000228f  lea     rdx, [rbp+13E0h+var_1420]
0x140002293  lea     rcx, [rsp+14E0h+var_14C0]
0x140002298  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000229d  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400022a4  test    rax, rax
0x1400022a7  jz      short loc_1400022B3
0x1400022a9  lea     rcx, [rsp+14E0h+var_14C0]
0x1400022ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400022b3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400022ba  test    rax, rax
0x1400022bd  jz      short loc_1400022D0
0x1400022bf  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x1400022c4  jnz     short loc_1400022D0
0x1400022c6  lea     rcx, [rsp+14E0h+var_14C0]
0x1400022cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400022d0  cmp     [rsp+14E0h+var_14B8], r12d
0x1400022d5  jl      short loc_1400022E9
0x1400022d7  mov     ecx, 8000FFFFh; this
0x1400022dc  mov     [rsp+14E0h+var_14B8], ecx
0x1400022e0  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400022e5  mov     [rsp+14E0h+var_14B4], eax
0x1400022e9  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1400022f0  jnz     short loc_140002311
0x1400022f2  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400022f9  test    rax, rax
0x1400022fc  jz      short loc_140002307
0x1400022fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002303  test    al, al
0x140002305  jmp     short loc_14000230F
0x140002307  call    cs:__imp_IsDebuggerPresent
0x14000230d  test    eax, eax
0x14000230f  jz      short loc_140002318
0x140002311  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x140002316  jz      short loc_14000233E
0x140002318  mov     rax, cs:g_pfnResultLoggingCallback
0x14000231f  test    rax, rax
0x140002322  jz      short loc_140002397
0x140002324  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x14000232b  jnz     short loc_140002397
0x14000232d  xor     r8d, r8d
0x140002330  lea     rcx, [rsp+14E0h+var_14C0]
0x140002335  xor     edx, edx
0x140002337  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000233c  jmp     short loc_140002397
0x14000233e  mov     rax, cs:g_pfnResultLoggingCallback
0x140002345  mov     ebx, 800h
0x14000234a  test    rax, rax
0x14000234d  jz      short loc_14000236C
0x14000234f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140002356  jnz     short loc_14000236C
0x140002358  mov     r8d, ebx
0x14000235b  lea     rdx, [rbp+13E0h+OutputString]
0x140002362  lea     rcx, [rsp+14E0h+var_14C0]
0x140002367  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000236c  cmp     [rbp+13E0h+OutputString], r12w
0x140002374  jnz     short loc_14000238A
0x140002376  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x14000237b  mov     rdx, rbx; unsigned __int16 *
0x14000237e  lea     rcx, [rbp+13E0h+OutputString]; this
0x140002385  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14000238a  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x140002391  call    cs:__imp_OutputDebugStringW
0x140002397  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x14000239c  jnz     short loc_1400023A7
0x14000239e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1400023a5  jz      short loc_1400023B8
0x1400023a7  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400023ae  test    rax, rax
0x1400023b1  jz      short loc_1400023B8
0x1400023b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400023b8  lea     rcx, [rsp+14E0h+var_14C0]; this
0x1400023bd  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
