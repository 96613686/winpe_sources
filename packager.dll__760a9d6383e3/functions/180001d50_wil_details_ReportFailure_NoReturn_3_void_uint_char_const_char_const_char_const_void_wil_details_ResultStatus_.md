# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180001d50`
- end: `0x180001fb7`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `615`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180001b04`

## callees

- `0x180001d50`
- `0x180002dc4`
- `0x18000355c`
- `0x180003c80`
- `0x1800045b0`
- `0x18000cbbe`
- `0x18000cc80`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001df1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001df1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180001f85`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180001f85`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180001efb`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180001efb`

## string_xrefs

- `0x180001e06`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
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
0x180001d50  mov     [rsp-8+arg_10], rbx
0x180001d55  mov     [rsp-8+arg_18], rsi
0x180001d5a  push    rbp
0x180001d5b  push    rdi
0x180001d5c  push    r12
0x180001d5e  push    r14
0x180001d60  push    r15
0x180001d62  lea     rbp, [rsp-13C0h]
0x180001d6a  mov     eax, 14C0h
0x180001d6f  call    _alloca_probe
0x180001d74  sub     rsp, rax
0x180001d77  mov     rsi, [rbp+13E0h+arg_28]
0x180001d7e  mov     r14d, edx
0x180001d81  mov     r15, rcx
0x180001d84  xor     edx, edx; Val
0x180001d86  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x180001d8b  mov     r8d, 98h; Size
0x180001d91  call    memset_0
0x180001d96  mov     rbx, [rbp+13E0h+arg_30]
0x180001d9d  xor     r12d, r12d
0x180001da0  mov     [rbp+13E0h+OutputString], r12w
0x180001da8  mov     [rbp+13E0h+var_1420], r12b
0x180001dac  mov     ecx, [rbx]; this
0x180001dae  mov     eax, [rbx+4]
0x180001db1  mov     [rsp+14E0h+var_14B8], ecx
0x180001db5  mov     [rsp+14E0h+var_14B4], eax
0x180001db9  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180001dbe  cmp     dword ptr [rbx+8], 1
0x180001dc2  mov     edi, eax
0x180001dc4  lea     eax, [r12+8]
0x180001dc9  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x180001dd1  mov     ecx, r12d
0x180001dd4  cmovz   ecx, eax
0x180001dd7  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x180001ddb  lea     ecx, [rax-7]
0x180001dde  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180001de6  inc     ecx
0x180001de8  mov     [rsp+14E0h+var_14A8], r12
0x180001ded  mov     [rsp+14E0h+var_14B0], ecx
0x180001df1  call    cs:__imp_GetCurrentThreadId
0x180001df7  xorps   xmm0, xmm0
0x180001dfa  mov     [rsp+14E0h+var_1480], r14d
0x180001dff  mov     [rsp+14E0h+var_14A0], eax
0x180001e03  xorps   xmm1, xmm1
0x180001e06  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180001e0d  mov     [rsp+14E0h+var_147C], edi
0x180001e11  mov     [rsp+14E0h+var_1488], rax
0x180001e16  xor     eax, eax
0x180001e18  mov     [rbp+13E0h+var_1448], rax
0x180001e1c  mov     [rbp+13E0h+var_1460], rax
0x180001e20  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180001e27  mov     [rsp+14E0h+var_1498], r12
0x180001e2c  mov     [rsp+14E0h+var_1490], r12
0x180001e31  mov     [rbp+13E0h+var_1438], rsi
0x180001e35  mov     [rbp+13E0h+var_1430], r15
0x180001e39  mov     [rsp+14E0h+var_1478], r12
0x180001e3e  movups  [rbp+13E0h+var_1458], xmm0
0x180001e42  movups  [rsp+14E0h+var_1470], xmm1
0x180001e47  test    rax, rax
0x180001e4a  jz      short loc_180001E57
0x180001e4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e51  mov     [rbp+13E0h+var_1440], rax
0x180001e55  jmp     short loc_180001E5B
0x180001e57  mov     [rbp+13E0h+var_1440], r12
0x180001e5b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180001e62  test    rax, rax
0x180001e65  jz      short loc_180001E71
0x180001e67  lea     rcx, [rsp+14E0h+var_14C0]
0x180001e6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e71  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180001e78  test    rax, rax
0x180001e7b  jz      short loc_180001E91
0x180001e7d  mov     r8d, 400h
0x180001e83  lea     rdx, [rbp+13E0h+var_1420]
0x180001e87  lea     rcx, [rsp+14E0h+var_14C0]
0x180001e8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e91  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180001e98  test    rax, rax
0x180001e9b  jz      short loc_180001EA7
0x180001e9d  lea     rcx, [rsp+14E0h+var_14C0]
0x180001ea2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ea7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180001eae  test    rax, rax
0x180001eb1  jz      short loc_180001EC4
0x180001eb3  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180001eb8  jnz     short loc_180001EC4
0x180001eba  lea     rcx, [rsp+14E0h+var_14C0]
0x180001ebf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ec4  cmp     [rsp+14E0h+var_14B8], r12d
0x180001ec9  jl      short loc_180001EDD
0x180001ecb  mov     ecx, 8000FFFFh; this
0x180001ed0  mov     [rsp+14E0h+var_14B8], ecx
0x180001ed4  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180001ed9  mov     [rsp+14E0h+var_14B4], eax
0x180001edd  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180001ee4  jnz     short loc_180001F05
0x180001ee6  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180001eed  test    rax, rax
0x180001ef0  jz      short loc_180001EFB
0x180001ef2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ef7  test    al, al
0x180001ef9  jmp     short loc_180001F03
0x180001efb  call    cs:__imp_IsDebuggerPresent
0x180001f01  test    eax, eax
0x180001f03  jz      short loc_180001F0C
0x180001f05  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180001f0a  jz      short loc_180001F32
0x180001f0c  mov     rax, cs:g_pfnResultLoggingCallback
0x180001f13  test    rax, rax
0x180001f16  jz      short loc_180001F8B
0x180001f18  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180001f1f  jnz     short loc_180001F8B
0x180001f21  xor     r8d, r8d
0x180001f24  lea     rcx, [rsp+14E0h+var_14C0]
0x180001f29  xor     edx, edx
0x180001f2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f30  jmp     short loc_180001F8B
0x180001f32  mov     rax, cs:g_pfnResultLoggingCallback
0x180001f39  mov     ebx, 800h
0x180001f3e  test    rax, rax
0x180001f41  jz      short loc_180001F60
0x180001f43  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180001f4a  jnz     short loc_180001F60
0x180001f4c  mov     r8d, ebx
0x180001f4f  lea     rdx, [rbp+13E0h+OutputString]
0x180001f56  lea     rcx, [rsp+14E0h+var_14C0]
0x180001f5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f60  cmp     [rbp+13E0h+OutputString], r12w
0x180001f68  jnz     short loc_180001F7E
0x180001f6a  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x180001f6f  mov     rdx, rbx; unsigned __int16 *
0x180001f72  lea     rcx, [rbp+13E0h+OutputString]; this
0x180001f79  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180001f7e  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x180001f85  call    cs:__imp_OutputDebugStringW
0x180001f8b  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x180001f90  jnz     short loc_180001F9B
0x180001f92  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180001f99  jz      short loc_180001FAC
0x180001f9b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180001fa2  test    rax, rax
0x180001fa5  jz      short loc_180001FAC
0x180001fa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fac  lea     rcx, [rsp+14E0h+var_14C0]; this
0x180001fb1  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
