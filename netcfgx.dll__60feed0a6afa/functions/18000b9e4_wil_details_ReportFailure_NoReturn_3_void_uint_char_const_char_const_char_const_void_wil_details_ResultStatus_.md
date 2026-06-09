# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18000b9e4`
- end: `0x18000bc4d`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `617`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18000b798`

## callees

- `0x180002a40`
- `0x18000b9e4`
- `0x18000d1f4`
- `0x18000ddd0`
- `0x18000ea50`
- `0x180010210`
- `0x180012350`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ba86`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ba86`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000bc1a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000bc1a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000bb90`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000bb90`

## string_xrefs

- `0x18000ba90`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v9; // edx
  int v10; // edi
  int v11; // ecx
  const struct wil::FailureInfo *v12; // rdx
  __int64 v13; // rcx
  const struct wil::FailureInfo *v14; // r9
  bool v15; // zf
  int v16; // [rsp+20h] [rbp-E0h] BYREF
  int v17; // [rsp+24h] [rbp-DCh]
  int v18; // [rsp+28h] [rbp-D8h]
  int v19; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v20; // [rsp+30h] [rbp-D0h]
  __int64 v21; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v23; // [rsp+48h] [rbp-B8h]
  __int64 v24; // [rsp+50h] [rbp-B0h]
  const char *v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+60h] [rbp-A0h]
  int v27; // [rsp+64h] [rbp-9Ch]
  __int64 v28; // [rsp+68h] [rbp-98h]
  __int128 v29; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+80h] [rbp-80h]
  __int128 v31; // [rsp+88h] [rbp-78h]
  __int64 v32; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v34; // [rsp+A8h] [rbp-58h]
  __int64 v35; // [rsp+B0h] [rbp-50h]
  char v36[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2064]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v16, 0, 0x98u);
  OutputString[0] = 0;
  v36[0] = 0;
  v18 = *a7;
  v19 = a7[1];
  v10 = wil::details::RecordFailFast((wil::details *)(unsigned int)v18, v9);
  v16 = 3;
  v11 = 0;
  if ( a7[2] == 1 )
    v11 = 8;
  v17 = v11;
  v20 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v25 = "onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h";
  v26 = a2;
  v27 = v10;
  v23 = 0;
  v24 = 0;
  v34 = a6;
  v35 = a1;
  v28 = 0;
  v31 = 0;
  v32 = 0;
  v29 = 0;
  v30 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v13);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v16, v36, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v16);
  if ( wil::details::g_pfnOriginateCallback && (v17 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v16);
  if ( v18 >= 0 )
  {
    v18 = -2147418113;
    v19 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v12);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v15 = !IsDebuggerPresent())
      : (v15 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v13) == 0),
        v15)
    || (v17 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v16, v14);
    OutputDebugStringW(OutputString);
  }
  if ( (v17 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v13);
  }
  wil::details::WilFailFast((wil::details *)&v16, v12);
}

```

## disassembly

```asm
0x18000b9e4  mov     [rsp-8+arg_10], rbx
0x18000b9e9  mov     [rsp-8+arg_18], rsi
0x18000b9ee  push    rbp
0x18000b9ef  push    rdi
0x18000b9f0  push    r12
0x18000b9f2  push    r14
0x18000b9f4  push    r15
0x18000b9f6  lea     rbp, [rsp-13C0h]
0x18000b9fe  mov     eax, 14C0h
0x18000ba03  call    _alloca_probe
0x18000ba08  sub     rsp, rax
0x18000ba0b  mov     r14d, edx
0x18000ba0e  mov     r15, rcx
0x18000ba11  mov     rsi, [rbp+13E0h+arg_28]
0x18000ba18  xor     edx, edx; Val
0x18000ba1a  mov     r8d, 98h; Size
0x18000ba20  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x18000ba25  call    memset_0
0x18000ba2a  nop
0x18000ba2b  xor     r12d, r12d
0x18000ba2e  mov     [rbp+13E0h+OutputString], r12w
0x18000ba36  mov     [rbp+13E0h+var_1420], r12b
0x18000ba3a  mov     rbx, [rbp+13E0h+arg_30]
0x18000ba41  mov     ecx, [rbx]; this
0x18000ba43  mov     [rsp+14E0h+var_14B8], ecx
0x18000ba47  mov     eax, [rbx+4]
0x18000ba4a  mov     [rsp+14E0h+var_14B4], eax
0x18000ba4e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000ba53  mov     edi, eax
0x18000ba55  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x18000ba5d  mov     ecx, r12d
0x18000ba60  lea     eax, [r12+8]
0x18000ba65  cmp     dword ptr [rbx+8], 1
0x18000ba69  cmovz   ecx, eax
0x18000ba6c  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x18000ba70  lea     ecx, [rax-7]
0x18000ba73  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000ba7b  inc     ecx
0x18000ba7d  mov     [rsp+14E0h+var_14B0], ecx
0x18000ba81  mov     [rsp+14E0h+var_14A8], r12
0x18000ba86  call    cs:__imp_GetCurrentThreadId
0x18000ba8c  mov     [rsp+14E0h+var_14A0], eax
0x18000ba90  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000ba97  mov     [rsp+14E0h+var_1488], rax
0x18000ba9c  mov     [rsp+14E0h+var_1480], r14d
0x18000baa1  mov     [rsp+14E0h+var_147C], edi
0x18000baa5  mov     [rsp+14E0h+var_1498], r12
0x18000baaa  mov     [rsp+14E0h+var_1490], r12
0x18000baaf  mov     [rbp+13E0h+var_1438], rsi
0x18000bab3  mov     [rbp+13E0h+var_1430], r15
0x18000bab7  mov     [rsp+14E0h+var_1478], r12
0x18000babc  xorps   xmm0, xmm0
0x18000babf  xor     eax, eax
0x18000bac1  movups  [rbp+13E0h+var_1458], xmm0
0x18000bac5  mov     [rbp+13E0h+var_1448], rax
0x18000bac9  xorps   xmm1, xmm1
0x18000bacc  movups  [rsp+14E0h+var_1470], xmm1
0x18000bad1  mov     [rbp+13E0h+var_1460], rax
0x18000bad5  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000badc  test    rax, rax
0x18000badf  jz      short loc_18000BAEC
0x18000bae1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bae6  mov     [rbp+13E0h+var_1440], rax
0x18000baea  jmp     short loc_18000BAF0
0x18000baec  mov     [rbp+13E0h+var_1440], r12
0x18000baf0  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000baf7  test    rax, rax
0x18000bafa  jz      short loc_18000BB06
0x18000bafc  lea     rcx, [rsp+14E0h+var_14C0]
0x18000bb01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb06  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000bb0d  test    rax, rax
0x18000bb10  jz      short loc_18000BB26
0x18000bb12  mov     r8d, 400h
0x18000bb18  lea     rdx, [rbp+13E0h+var_1420]
0x18000bb1c  lea     rcx, [rsp+14E0h+var_14C0]
0x18000bb21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb26  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000bb2d  test    rax, rax
0x18000bb30  jz      short loc_18000BB3C
0x18000bb32  lea     rcx, [rsp+14E0h+var_14C0]
0x18000bb37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb3c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000bb43  test    rax, rax
0x18000bb46  jz      short loc_18000BB59
0x18000bb48  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x18000bb4d  jnz     short loc_18000BB59
0x18000bb4f  lea     rcx, [rsp+14E0h+var_14C0]
0x18000bb54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb59  cmp     [rsp+14E0h+var_14B8], r12d
0x18000bb5e  jl      short loc_18000BB72
0x18000bb60  mov     ecx, 8000FFFFh; this
0x18000bb65  mov     [rsp+14E0h+var_14B8], ecx
0x18000bb69  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000bb6e  mov     [rsp+14E0h+var_14B4], eax
0x18000bb72  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18000bb79  jnz     short loc_18000BB9A
0x18000bb7b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000bb82  test    rax, rax
0x18000bb85  jz      short loc_18000BB90
0x18000bb87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb8c  test    al, al
0x18000bb8e  jmp     short loc_18000BB98
0x18000bb90  call    cs:__imp_IsDebuggerPresent
0x18000bb96  test    eax, eax
0x18000bb98  jz      short loc_18000BBA1
0x18000bb9a  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x18000bb9f  jz      short loc_18000BBC7
0x18000bba1  mov     rax, cs:g_pfnResultLoggingCallback
0x18000bba8  test    rax, rax
0x18000bbab  jz      short loc_18000BC20
0x18000bbad  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000bbb4  jnz     short loc_18000BC20
0x18000bbb6  xor     r8d, r8d
0x18000bbb9  xor     edx, edx
0x18000bbbb  lea     rcx, [rsp+14E0h+var_14C0]
0x18000bbc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bbc5  jmp     short loc_18000BC20
0x18000bbc7  mov     ebx, 800h
0x18000bbcc  mov     rax, cs:g_pfnResultLoggingCallback
0x18000bbd3  test    rax, rax
0x18000bbd6  jz      short loc_18000BBF5
0x18000bbd8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000bbdf  jnz     short loc_18000BBF5
0x18000bbe1  mov     r8d, ebx
0x18000bbe4  lea     rdx, [rbp+13E0h+OutputString]
0x18000bbeb  lea     rcx, [rsp+14E0h+var_14C0]
0x18000bbf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bbf5  cmp     [rbp+13E0h+OutputString], r12w
0x18000bbfd  jnz     short loc_18000BC13
0x18000bbff  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x18000bc04  mov     rdx, rbx; unsigned __int16 *
0x18000bc07  lea     rcx, [rbp+13E0h+OutputString]; this
0x18000bc0e  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000bc13  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x18000bc1a  call    cs:__imp_OutputDebugStringW
0x18000bc20  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x18000bc25  jnz     short loc_18000BC30
0x18000bc27  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18000bc2e  jz      short loc_18000BC42
0x18000bc30  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000bc37  test    rax, rax
0x18000bc3a  jz      short loc_18000BC42
0x18000bc3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc41  nop
0x18000bc42  lea     rcx, [rsp+14E0h+var_14C0]; this
0x18000bc47  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
