# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180002c88`
- end: `0x180002eef`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `615`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180002a3c`

## callees

- `0x180001962`
- `0x180002c88`
- `0x180003d14`
- `0x1800044ac`
- `0x180004bf0`
- `0x180005620`
- `0x18000b390`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002d29`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002d29`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002ebd`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002ebd`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002e33`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002e33`

## string_xrefs

- `0x180002d3e`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180002c88  mov     [rsp-8+arg_10], rbx
0x180002c8d  mov     [rsp-8+arg_18], rsi
0x180002c92  push    rbp
0x180002c93  push    rdi
0x180002c94  push    r12
0x180002c96  push    r14
0x180002c98  push    r15
0x180002c9a  lea     rbp, [rsp-13C0h]
0x180002ca2  mov     eax, 14C0h
0x180002ca7  call    _alloca_probe
0x180002cac  sub     rsp, rax
0x180002caf  mov     rsi, [rbp+13E0h+arg_28]
0x180002cb6  mov     r14d, edx
0x180002cb9  mov     r15, rcx
0x180002cbc  xor     edx, edx; Val
0x180002cbe  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x180002cc3  mov     r8d, 98h; Size
0x180002cc9  call    memset_0
0x180002cce  mov     rbx, [rbp+13E0h+arg_30]
0x180002cd5  xor     r12d, r12d
0x180002cd8  mov     [rbp+13E0h+OutputString], r12w
0x180002ce0  mov     [rbp+13E0h+var_1420], r12b
0x180002ce4  mov     ecx, [rbx]; this
0x180002ce6  mov     eax, [rbx+4]
0x180002ce9  mov     [rsp+14E0h+var_14B8], ecx
0x180002ced  mov     [rsp+14E0h+var_14B4], eax
0x180002cf1  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180002cf6  cmp     dword ptr [rbx+8], 1
0x180002cfa  mov     edi, eax
0x180002cfc  lea     eax, [r12+8]
0x180002d01  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x180002d09  mov     ecx, r12d
0x180002d0c  cmovz   ecx, eax
0x180002d0f  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x180002d13  lea     ecx, [rax-7]
0x180002d16  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002d1e  inc     ecx
0x180002d20  mov     [rsp+14E0h+var_14A8], r12
0x180002d25  mov     [rsp+14E0h+var_14B0], ecx
0x180002d29  call    cs:__imp_GetCurrentThreadId
0x180002d2f  xorps   xmm0, xmm0
0x180002d32  mov     [rsp+14E0h+var_1480], r14d
0x180002d37  mov     [rsp+14E0h+var_14A0], eax
0x180002d3b  xorps   xmm1, xmm1
0x180002d3e  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180002d45  mov     [rsp+14E0h+var_147C], edi
0x180002d49  mov     [rsp+14E0h+var_1488], rax
0x180002d4e  xor     eax, eax
0x180002d50  mov     [rbp+13E0h+var_1448], rax
0x180002d54  mov     [rbp+13E0h+var_1460], rax
0x180002d58  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002d5f  mov     [rsp+14E0h+var_1498], r12
0x180002d64  mov     [rsp+14E0h+var_1490], r12
0x180002d69  mov     [rbp+13E0h+var_1438], rsi
0x180002d6d  mov     [rbp+13E0h+var_1430], r15
0x180002d71  mov     [rsp+14E0h+var_1478], r12
0x180002d76  movups  [rbp+13E0h+var_1458], xmm0
0x180002d7a  movups  [rsp+14E0h+var_1470], xmm1
0x180002d7f  test    rax, rax
0x180002d82  jz      short loc_180002D8F
0x180002d84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d89  mov     [rbp+13E0h+var_1440], rax
0x180002d8d  jmp     short loc_180002D93
0x180002d8f  mov     [rbp+13E0h+var_1440], r12
0x180002d93  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002d9a  test    rax, rax
0x180002d9d  jz      short loc_180002DA9
0x180002d9f  lea     rcx, [rsp+14E0h+var_14C0]
0x180002da4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002da9  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002db0  test    rax, rax
0x180002db3  jz      short loc_180002DC9
0x180002db5  mov     r8d, 400h
0x180002dbb  lea     rdx, [rbp+13E0h+var_1420]
0x180002dbf  lea     rcx, [rsp+14E0h+var_14C0]
0x180002dc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dc9  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002dd0  test    rax, rax
0x180002dd3  jz      short loc_180002DDF
0x180002dd5  lea     rcx, [rsp+14E0h+var_14C0]
0x180002dda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ddf  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002de6  test    rax, rax
0x180002de9  jz      short loc_180002DFC
0x180002deb  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180002df0  jnz     short loc_180002DFC
0x180002df2  lea     rcx, [rsp+14E0h+var_14C0]
0x180002df7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dfc  cmp     [rsp+14E0h+var_14B8], r12d
0x180002e01  jl      short loc_180002E15
0x180002e03  mov     ecx, 8000FFFFh; this
0x180002e08  mov     [rsp+14E0h+var_14B8], ecx
0x180002e0c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180002e11  mov     [rsp+14E0h+var_14B4], eax
0x180002e15  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180002e1c  jnz     short loc_180002E3D
0x180002e1e  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002e25  test    rax, rax
0x180002e28  jz      short loc_180002E33
0x180002e2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e2f  test    al, al
0x180002e31  jmp     short loc_180002E3B
0x180002e33  call    cs:__imp_IsDebuggerPresent
0x180002e39  test    eax, eax
0x180002e3b  jz      short loc_180002E44
0x180002e3d  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180002e42  jz      short loc_180002E6A
0x180002e44  mov     rax, cs:g_pfnResultLoggingCallback
0x180002e4b  test    rax, rax
0x180002e4e  jz      short loc_180002EC3
0x180002e50  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180002e57  jnz     short loc_180002EC3
0x180002e59  xor     r8d, r8d
0x180002e5c  lea     rcx, [rsp+14E0h+var_14C0]
0x180002e61  xor     edx, edx
0x180002e63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e68  jmp     short loc_180002EC3
0x180002e6a  mov     rax, cs:g_pfnResultLoggingCallback
0x180002e71  mov     ebx, 800h
0x180002e76  test    rax, rax
0x180002e79  jz      short loc_180002E98
0x180002e7b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180002e82  jnz     short loc_180002E98
0x180002e84  mov     r8d, ebx
0x180002e87  lea     rdx, [rbp+13E0h+OutputString]
0x180002e8e  lea     rcx, [rsp+14E0h+var_14C0]
0x180002e93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e98  cmp     [rbp+13E0h+OutputString], r12w
0x180002ea0  jnz     short loc_180002EB6
0x180002ea2  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x180002ea7  mov     rdx, rbx; unsigned __int16 *
0x180002eaa  lea     rcx, [rbp+13E0h+OutputString]; this
0x180002eb1  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002eb6  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x180002ebd  call    cs:__imp_OutputDebugStringW
0x180002ec3  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x180002ec8  jnz     short loc_180002ED3
0x180002eca  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180002ed1  jz      short loc_180002EE4
0x180002ed3  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002eda  test    rax, rax
0x180002edd  jz      short loc_180002EE4
0x180002edf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ee4  lea     rcx, [rsp+14E0h+var_14C0]; this
0x180002ee9  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
