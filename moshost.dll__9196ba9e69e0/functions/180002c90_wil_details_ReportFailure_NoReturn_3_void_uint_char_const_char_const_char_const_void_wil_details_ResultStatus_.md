# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180002c90`
- end: `0x180002ef2`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `610`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180002a34`

## callees

- `0x180002722`
- `0x180002c90`
- `0x180004034`
- `0x1800047d0`
- `0x180004f30`
- `0x180005fb0`
- `0x18000c6c0`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002d32`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002d32`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002e35`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002e35`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002ebf`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002ebf`

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
0x180002c90  mov     [rsp-8+arg_18], rbx
0x180002c95  push    rbp
0x180002c96  push    rsi
0x180002c97  push    rdi
0x180002c98  push    r12
0x180002c9a  push    r13
0x180002c9c  push    r14
0x180002c9e  push    r15
0x180002ca0  lea     rbp, [rsp-13C0h]
0x180002ca8  mov     eax, 14C0h
0x180002cad  call    _alloca_probe
0x180002cb2  sub     rsp, rax
0x180002cb5  mov     r15, r8
0x180002cb8  mov     r14d, edx
0x180002cbb  mov     r12, rcx
0x180002cbe  mov     rsi, [rbp+13F0h+arg_28]
0x180002cc5  xor     edx, edx; Val
0x180002cc7  mov     r8d, 98h; Size
0x180002ccd  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180002cd2  call    memset_0
0x180002cd7  nop
0x180002cd8  xor     r13d, r13d
0x180002cdb  mov     [rbp+13F0h+OutputString], r13w
0x180002ce3  mov     [rbp+13F0h+var_1430], r13b
0x180002ce7  mov     rbx, [rbp+13F0h+arg_30]
0x180002cee  mov     ecx, [rbx]; this
0x180002cf0  mov     [rsp+14F0h+var_14C8], ecx
0x180002cf4  mov     eax, [rbx+4]
0x180002cf7  mov     [rsp+14F0h+var_14C4], eax
0x180002cfb  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180002d00  mov     edi, eax
0x180002d02  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180002d0a  mov     ecx, r13d
0x180002d0d  lea     eax, [r13+8]
0x180002d11  cmp     dword ptr [rbx+8], 1
0x180002d15  cmovz   ecx, eax
0x180002d18  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180002d1c  lea     ecx, [rax-7]
0x180002d1f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002d27  inc     ecx
0x180002d29  mov     [rsp+14F0h+var_14C0], ecx
0x180002d2d  mov     [rsp+14F0h+var_14B8], r13
0x180002d32  call    cs:__imp_GetCurrentThreadId
0x180002d38  mov     [rsp+14F0h+var_14B0], eax
0x180002d3c  mov     [rsp+14F0h+var_1498], r15
0x180002d41  mov     [rsp+14F0h+var_1490], r14d
0x180002d46  mov     [rsp+14F0h+var_148C], edi
0x180002d4a  mov     [rsp+14F0h+var_14A8], r13
0x180002d4f  mov     [rsp+14F0h+var_14A0], r13
0x180002d54  mov     [rbp+13F0h+var_1448], rsi
0x180002d58  mov     [rbp+13F0h+var_1440], r12
0x180002d5c  mov     [rsp+14F0h+var_1488], r13
0x180002d61  xorps   xmm0, xmm0
0x180002d64  xor     eax, eax
0x180002d66  movups  [rbp+13F0h+var_1468], xmm0
0x180002d6a  mov     [rbp+13F0h+var_1458], rax
0x180002d6e  xorps   xmm1, xmm1
0x180002d71  movups  [rsp+14F0h+var_1480], xmm1
0x180002d76  mov     [rbp+13F0h+var_1470], rax
0x180002d7a  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002d81  test    rax, rax
0x180002d84  jz      short loc_180002D91
0x180002d86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d8b  mov     [rbp+13F0h+var_1450], rax
0x180002d8f  jmp     short loc_180002D95
0x180002d91  mov     [rbp+13F0h+var_1450], r13
0x180002d95  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002d9c  test    rax, rax
0x180002d9f  jz      short loc_180002DAB
0x180002da1  lea     rcx, [rsp+14F0h+var_14D0]
0x180002da6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dab  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002db2  test    rax, rax
0x180002db5  jz      short loc_180002DCB
0x180002db7  mov     r8d, 400h
0x180002dbd  lea     rdx, [rbp+13F0h+var_1430]
0x180002dc1  lea     rcx, [rsp+14F0h+var_14D0]
0x180002dc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dcb  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002dd2  test    rax, rax
0x180002dd5  jz      short loc_180002DE1
0x180002dd7  lea     rcx, [rsp+14F0h+var_14D0]
0x180002ddc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002de1  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002de8  test    rax, rax
0x180002deb  jz      short loc_180002DFE
0x180002ded  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002df2  jnz     short loc_180002DFE
0x180002df4  lea     rcx, [rsp+14F0h+var_14D0]
0x180002df9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dfe  cmp     [rsp+14F0h+var_14C8], r13d
0x180002e03  jl      short loc_180002E17
0x180002e05  mov     ecx, 8000FFFFh; this
0x180002e0a  mov     [rsp+14F0h+var_14C8], ecx
0x180002e0e  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180002e13  mov     [rsp+14F0h+var_14C4], eax
0x180002e17  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180002e1e  jnz     short loc_180002E3F
0x180002e20  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002e27  test    rax, rax
0x180002e2a  jz      short loc_180002E35
0x180002e2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e31  test    al, al
0x180002e33  jmp     short loc_180002E3D
0x180002e35  call    cs:__imp_IsDebuggerPresent
0x180002e3b  test    eax, eax
0x180002e3d  jz      short loc_180002E46
0x180002e3f  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002e44  jz      short loc_180002E6C
0x180002e46  mov     rax, cs:g_pfnResultLoggingCallback
0x180002e4d  test    rax, rax
0x180002e50  jz      short loc_180002EC5
0x180002e52  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180002e59  jnz     short loc_180002EC5
0x180002e5b  xor     r8d, r8d
0x180002e5e  xor     edx, edx
0x180002e60  lea     rcx, [rsp+14F0h+var_14D0]
0x180002e65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e6a  jmp     short loc_180002EC5
0x180002e6c  mov     ebx, 800h
0x180002e71  mov     rax, cs:g_pfnResultLoggingCallback
0x180002e78  test    rax, rax
0x180002e7b  jz      short loc_180002E9A
0x180002e7d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180002e84  jnz     short loc_180002E9A
0x180002e86  mov     r8d, ebx
0x180002e89  lea     rdx, [rbp+13F0h+OutputString]
0x180002e90  lea     rcx, [rsp+14F0h+var_14D0]
0x180002e95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e9a  cmp     [rbp+13F0h+OutputString], r13w
0x180002ea2  jnz     short loc_180002EB8
0x180002ea4  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180002ea9  mov     rdx, rbx; unsigned __int16 *
0x180002eac  lea     rcx, [rbp+13F0h+OutputString]; this
0x180002eb3  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002eb8  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180002ebf  call    cs:__imp_OutputDebugStringW
0x180002ec5  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180002eca  jnz     short loc_180002ED5
0x180002ecc  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180002ed3  jz      short loc_180002EE7
0x180002ed5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002edc  test    rax, rax
0x180002edf  jz      short loc_180002EE7
0x180002ee1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ee6  nop
0x180002ee7  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180002eec  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
