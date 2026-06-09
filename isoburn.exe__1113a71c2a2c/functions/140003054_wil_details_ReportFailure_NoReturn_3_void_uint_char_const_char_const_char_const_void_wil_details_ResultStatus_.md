# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x140003054`
- end: `0x1400032bb`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `615`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140002e08`

## callees

- `0x140002bc6`
- `0x140003054`
- `0x140005024`
- `0x140006078`
- `0x140007740`
- `0x1400096d0`
- `0x14000f6e0`
- `0x140010010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x1400031ff`
- `KERNEL32!IsDebuggerPresent` at `0x1400031ff`
- `KERNEL32!OutputDebugStringW` at `0x140003289`
- `KERNEL32!OutputDebugStringW` at `0x140003289`
- `KERNEL32!GetCurrentThreadId` at `0x1400030f5`
- `KERNEL32!GetCurrentThreadId` at `0x1400030f5`

## string_xrefs

- `0x14000310a`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x140003054  mov     [rsp-8+arg_10], rbx
0x140003059  mov     [rsp-8+arg_18], rsi
0x14000305e  push    rbp
0x14000305f  push    rdi
0x140003060  push    r12
0x140003062  push    r14
0x140003064  push    r15
0x140003066  lea     rbp, [rsp-13C0h]
0x14000306e  mov     eax, 14C0h
0x140003073  call    _alloca_probe
0x140003078  sub     rsp, rax
0x14000307b  mov     rsi, [rbp+13E0h+arg_28]
0x140003082  mov     r14d, edx
0x140003085  mov     r15, rcx
0x140003088  xor     edx, edx; Val
0x14000308a  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x14000308f  mov     r8d, 98h; Size
0x140003095  call    memset_0
0x14000309a  mov     rbx, [rbp+13E0h+arg_30]
0x1400030a1  xor     r12d, r12d
0x1400030a4  mov     [rbp+13E0h+OutputString], r12w
0x1400030ac  mov     [rbp+13E0h+var_1420], r12b
0x1400030b0  mov     ecx, [rbx]; this
0x1400030b2  mov     eax, [rbx+4]
0x1400030b5  mov     [rsp+14E0h+var_14B8], ecx
0x1400030b9  mov     [rsp+14E0h+var_14B4], eax
0x1400030bd  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1400030c2  cmp     dword ptr [rbx+8], 1
0x1400030c6  mov     edi, eax
0x1400030c8  lea     eax, [r12+8]
0x1400030cd  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x1400030d5  mov     ecx, r12d
0x1400030d8  cmovz   ecx, eax
0x1400030db  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x1400030df  lea     ecx, [rax-7]
0x1400030e2  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400030ea  inc     ecx
0x1400030ec  mov     [rsp+14E0h+var_14A8], r12
0x1400030f1  mov     [rsp+14E0h+var_14B0], ecx
0x1400030f5  call    cs:__imp_GetCurrentThreadId
0x1400030fb  xorps   xmm0, xmm0
0x1400030fe  mov     [rsp+14E0h+var_1480], r14d
0x140003103  mov     [rsp+14E0h+var_14A0], eax
0x140003107  xorps   xmm1, xmm1
0x14000310a  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140003111  mov     [rsp+14E0h+var_147C], edi
0x140003115  mov     [rsp+14E0h+var_1488], rax
0x14000311a  xor     eax, eax
0x14000311c  mov     [rbp+13E0h+var_1448], rax
0x140003120  mov     [rbp+13E0h+var_1460], rax
0x140003124  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000312b  mov     [rsp+14E0h+var_1498], r12
0x140003130  mov     [rsp+14E0h+var_1490], r12
0x140003135  mov     [rbp+13E0h+var_1438], rsi
0x140003139  mov     [rbp+13E0h+var_1430], r15
0x14000313d  mov     [rsp+14E0h+var_1478], r12
0x140003142  movups  [rbp+13E0h+var_1458], xmm0
0x140003146  movups  [rsp+14E0h+var_1470], xmm1
0x14000314b  test    rax, rax
0x14000314e  jz      short loc_14000315B
0x140003150  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003155  mov     [rbp+13E0h+var_1440], rax
0x140003159  jmp     short loc_14000315F
0x14000315b  mov     [rbp+13E0h+var_1440], r12
0x14000315f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140003166  test    rax, rax
0x140003169  jz      short loc_140003175
0x14000316b  lea     rcx, [rsp+14E0h+var_14C0]
0x140003170  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003175  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000317c  test    rax, rax
0x14000317f  jz      short loc_140003195
0x140003181  mov     r8d, 400h
0x140003187  lea     rdx, [rbp+13E0h+var_1420]
0x14000318b  lea     rcx, [rsp+14E0h+var_14C0]
0x140003190  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003195  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000319c  test    rax, rax
0x14000319f  jz      short loc_1400031AB
0x1400031a1  lea     rcx, [rsp+14E0h+var_14C0]
0x1400031a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400031ab  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400031b2  test    rax, rax
0x1400031b5  jz      short loc_1400031C8
0x1400031b7  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x1400031bc  jnz     short loc_1400031C8
0x1400031be  lea     rcx, [rsp+14E0h+var_14C0]
0x1400031c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400031c8  cmp     [rsp+14E0h+var_14B8], r12d
0x1400031cd  jl      short loc_1400031E1
0x1400031cf  mov     ecx, 8000FFFFh; this
0x1400031d4  mov     [rsp+14E0h+var_14B8], ecx
0x1400031d8  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400031dd  mov     [rsp+14E0h+var_14B4], eax
0x1400031e1  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1400031e8  jnz     short loc_140003209
0x1400031ea  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400031f1  test    rax, rax
0x1400031f4  jz      short loc_1400031FF
0x1400031f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400031fb  test    al, al
0x1400031fd  jmp     short loc_140003207
0x1400031ff  call    cs:__imp_IsDebuggerPresent
0x140003205  test    eax, eax
0x140003207  jz      short loc_140003210
0x140003209  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x14000320e  jz      short loc_140003236
0x140003210  mov     rax, cs:g_pfnResultLoggingCallback
0x140003217  test    rax, rax
0x14000321a  jz      short loc_14000328F
0x14000321c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140003223  jnz     short loc_14000328F
0x140003225  xor     r8d, r8d
0x140003228  lea     rcx, [rsp+14E0h+var_14C0]
0x14000322d  xor     edx, edx
0x14000322f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003234  jmp     short loc_14000328F
0x140003236  mov     rax, cs:g_pfnResultLoggingCallback
0x14000323d  mov     ebx, 800h
0x140003242  test    rax, rax
0x140003245  jz      short loc_140003264
0x140003247  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x14000324e  jnz     short loc_140003264
0x140003250  mov     r8d, ebx
0x140003253  lea     rdx, [rbp+13E0h+OutputString]
0x14000325a  lea     rcx, [rsp+14E0h+var_14C0]
0x14000325f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003264  cmp     [rbp+13E0h+OutputString], r12w
0x14000326c  jnz     short loc_140003282
0x14000326e  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x140003273  mov     rdx, rbx; unsigned __int16 *
0x140003276  lea     rcx, [rbp+13E0h+OutputString]; this
0x14000327d  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140003282  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x140003289  call    cs:__imp_OutputDebugStringW
0x14000328f  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x140003294  jnz     short loc_14000329F
0x140003296  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x14000329d  jz      short loc_1400032B0
0x14000329f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400032a6  test    rax, rax
0x1400032a9  jz      short loc_1400032B0
0x1400032ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400032b0  lea     rcx, [rsp+14E0h+var_14C0]; this
0x1400032b5  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
