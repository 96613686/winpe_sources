# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180002ca4`
- end: `0x180002f04`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `608`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180002a48`

## callees

- `0x180001fb8`
- `0x180002ca4`
- `0x180004e14`
- `0x1800055ac`
- `0x180006c00`
- `0x180008ab0`
- `0x18003acd0`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002d45`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002d45`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002e48`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002e48`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002ed2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002ed2`

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
0x180002ca4  mov     [rsp-8+arg_18], rbx
0x180002ca9  push    rbp
0x180002caa  push    rsi
0x180002cab  push    rdi
0x180002cac  push    r12
0x180002cae  push    r13
0x180002cb0  push    r14
0x180002cb2  push    r15
0x180002cb4  lea     rbp, [rsp-13C0h]
0x180002cbc  mov     eax, 14C0h
0x180002cc1  call    _alloca_probe
0x180002cc6  sub     rsp, rax
0x180002cc9  mov     rsi, [rbp+13F0h+arg_28]
0x180002cd0  mov     r15, r8
0x180002cd3  mov     r14d, edx
0x180002cd6  mov     r12, rcx
0x180002cd9  xor     edx, edx; Val
0x180002cdb  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180002ce0  mov     r8d, 98h; Size
0x180002ce6  call    memset_0
0x180002ceb  mov     rbx, [rbp+13F0h+arg_30]
0x180002cf2  xor     r13d, r13d
0x180002cf5  mov     [rbp+13F0h+OutputString], r13w
0x180002cfd  mov     [rbp+13F0h+var_1430], r13b
0x180002d01  mov     ecx, [rbx]; this
0x180002d03  mov     eax, [rbx+4]
0x180002d06  mov     [rsp+14F0h+var_14C8], ecx
0x180002d0a  mov     [rsp+14F0h+var_14C4], eax
0x180002d0e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180002d13  cmp     dword ptr [rbx+8], 1
0x180002d17  mov     edi, eax
0x180002d19  lea     eax, [r13+8]
0x180002d1d  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180002d25  mov     ecx, r13d
0x180002d28  cmovz   ecx, eax
0x180002d2b  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180002d2f  lea     ecx, [rax-7]
0x180002d32  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002d3a  inc     ecx
0x180002d3c  mov     [rsp+14F0h+var_14B8], r13
0x180002d41  mov     [rsp+14F0h+var_14C0], ecx
0x180002d45  call    cs:__imp_GetCurrentThreadId
0x180002d4b  xorps   xmm0, xmm0
0x180002d4e  mov     [rsp+14F0h+var_1498], r15
0x180002d53  mov     [rsp+14F0h+var_14B0], eax
0x180002d57  xorps   xmm1, xmm1
0x180002d5a  xor     eax, eax
0x180002d5c  mov     [rsp+14F0h+var_1490], r14d
0x180002d61  mov     [rbp+13F0h+var_1458], rax
0x180002d65  mov     [rbp+13F0h+var_1470], rax
0x180002d69  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002d70  mov     [rsp+14F0h+var_148C], edi
0x180002d74  mov     [rsp+14F0h+var_14A8], r13
0x180002d79  mov     [rsp+14F0h+var_14A0], r13
0x180002d7e  mov     [rbp+13F0h+var_1448], rsi
0x180002d82  mov     [rbp+13F0h+var_1440], r12
0x180002d86  mov     [rsp+14F0h+var_1488], r13
0x180002d8b  movups  [rbp+13F0h+var_1468], xmm0
0x180002d8f  movups  [rsp+14F0h+var_1480], xmm1
0x180002d94  test    rax, rax
0x180002d97  jz      short loc_180002DA4
0x180002d99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d9e  mov     [rbp+13F0h+var_1450], rax
0x180002da2  jmp     short loc_180002DA8
0x180002da4  mov     [rbp+13F0h+var_1450], r13
0x180002da8  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002daf  test    rax, rax
0x180002db2  jz      short loc_180002DBE
0x180002db4  lea     rcx, [rsp+14F0h+var_14D0]
0x180002db9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dbe  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002dc5  test    rax, rax
0x180002dc8  jz      short loc_180002DDE
0x180002dca  mov     r8d, 400h
0x180002dd0  lea     rdx, [rbp+13F0h+var_1430]
0x180002dd4  lea     rcx, [rsp+14F0h+var_14D0]
0x180002dd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dde  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002de5  test    rax, rax
0x180002de8  jz      short loc_180002DF4
0x180002dea  lea     rcx, [rsp+14F0h+var_14D0]
0x180002def  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002df4  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002dfb  test    rax, rax
0x180002dfe  jz      short loc_180002E11
0x180002e00  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002e05  jnz     short loc_180002E11
0x180002e07  lea     rcx, [rsp+14F0h+var_14D0]
0x180002e0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e11  cmp     [rsp+14F0h+var_14C8], r13d
0x180002e16  jl      short loc_180002E2A
0x180002e18  mov     ecx, 8000FFFFh; this
0x180002e1d  mov     [rsp+14F0h+var_14C8], ecx
0x180002e21  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180002e26  mov     [rsp+14F0h+var_14C4], eax
0x180002e2a  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180002e31  jnz     short loc_180002E52
0x180002e33  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002e3a  test    rax, rax
0x180002e3d  jz      short loc_180002E48
0x180002e3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e44  test    al, al
0x180002e46  jmp     short loc_180002E50
0x180002e48  call    cs:__imp_IsDebuggerPresent
0x180002e4e  test    eax, eax
0x180002e50  jz      short loc_180002E59
0x180002e52  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002e57  jz      short loc_180002E7F
0x180002e59  mov     rax, cs:g_pfnResultLoggingCallback
0x180002e60  test    rax, rax
0x180002e63  jz      short loc_180002ED8
0x180002e65  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180002e6c  jnz     short loc_180002ED8
0x180002e6e  xor     r8d, r8d
0x180002e71  lea     rcx, [rsp+14F0h+var_14D0]
0x180002e76  xor     edx, edx
0x180002e78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e7d  jmp     short loc_180002ED8
0x180002e7f  mov     rax, cs:g_pfnResultLoggingCallback
0x180002e86  mov     ebx, 800h
0x180002e8b  test    rax, rax
0x180002e8e  jz      short loc_180002EAD
0x180002e90  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180002e97  jnz     short loc_180002EAD
0x180002e99  mov     r8d, ebx
0x180002e9c  lea     rdx, [rbp+13F0h+OutputString]
0x180002ea3  lea     rcx, [rsp+14F0h+var_14D0]
0x180002ea8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ead  cmp     [rbp+13F0h+OutputString], r13w
0x180002eb5  jnz     short loc_180002ECB
0x180002eb7  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180002ebc  mov     rdx, rbx; unsigned __int16 *
0x180002ebf  lea     rcx, [rbp+13F0h+OutputString]; this
0x180002ec6  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002ecb  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180002ed2  call    cs:__imp_OutputDebugStringW
0x180002ed8  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180002edd  jnz     short loc_180002EE8
0x180002edf  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180002ee6  jz      short loc_180002EF9
0x180002ee8  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002eef  test    rax, rax
0x180002ef2  jz      short loc_180002EF9
0x180002ef4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ef9  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180002efe  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
