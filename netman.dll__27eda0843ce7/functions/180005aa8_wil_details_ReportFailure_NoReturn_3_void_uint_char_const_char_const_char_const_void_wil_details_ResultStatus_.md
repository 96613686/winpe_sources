# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180005aa8`
- end: `0x180005d0a`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `610`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180005874`

## callees

- `0x180002320`
- `0x1800032c4`
- `0x1800036ac`
- `0x180003a00`
- `0x180005aa8`
- `0x18001871c`
- `0x180034d90`
- `0x180036010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x180005c4d`
- `KERNEL32!IsDebuggerPresent` at `0x180005c4d`
- `KERNEL32!OutputDebugStringW` at `0x180005cd7`
- `KERNEL32!OutputDebugStringW` at `0x180005cd7`
- `KERNEL32!GetCurrentThreadId` at `0x180005b4a`
- `KERNEL32!GetCurrentThreadId` at `0x180005b4a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x180005aa8  mov     [rsp-8+arg_18], rbx
0x180005aad  push    rbp
0x180005aae  push    rsi
0x180005aaf  push    rdi
0x180005ab0  push    r12
0x180005ab2  push    r13
0x180005ab4  push    r14
0x180005ab6  push    r15
0x180005ab8  lea     rbp, [rsp-13C0h]
0x180005ac0  mov     eax, 14C0h
0x180005ac5  call    _alloca_probe
0x180005aca  sub     rsp, rax
0x180005acd  mov     r15, r8
0x180005ad0  mov     r14d, edx
0x180005ad3  mov     r12, rcx
0x180005ad6  mov     rsi, [rbp+13F0h+arg_28]
0x180005add  xor     edx, edx; Val
0x180005adf  mov     r8d, 98h; Size
0x180005ae5  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180005aea  call    memset_0
0x180005aef  nop
0x180005af0  xor     r13d, r13d
0x180005af3  mov     [rbp+13F0h+OutputString], r13w
0x180005afb  mov     [rbp+13F0h+var_1430], r13b
0x180005aff  mov     rbx, [rbp+13F0h+arg_30]
0x180005b06  mov     ecx, [rbx]; this
0x180005b08  mov     [rsp+14F0h+var_14C8], ecx
0x180005b0c  mov     eax, [rbx+4]
0x180005b0f  mov     [rsp+14F0h+var_14C4], eax
0x180005b13  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180005b18  mov     edi, eax
0x180005b1a  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180005b22  mov     ecx, r13d
0x180005b25  lea     eax, [r13+8]
0x180005b29  cmp     dword ptr [rbx+8], 1
0x180005b2d  cmovz   ecx, eax
0x180005b30  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180005b34  lea     ecx, [rax-7]
0x180005b37  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005b3f  inc     ecx
0x180005b41  mov     [rsp+14F0h+var_14C0], ecx
0x180005b45  mov     [rsp+14F0h+var_14B8], r13
0x180005b4a  call    cs:__imp_GetCurrentThreadId
0x180005b50  mov     [rsp+14F0h+var_14B0], eax
0x180005b54  mov     [rsp+14F0h+var_1498], r15
0x180005b59  mov     [rsp+14F0h+var_1490], r14d
0x180005b5e  mov     [rsp+14F0h+var_148C], edi
0x180005b62  mov     [rsp+14F0h+var_14A8], r13
0x180005b67  mov     [rsp+14F0h+var_14A0], r13
0x180005b6c  mov     [rbp+13F0h+var_1448], rsi
0x180005b70  mov     [rbp+13F0h+var_1440], r12
0x180005b74  mov     [rsp+14F0h+var_1488], r13
0x180005b79  xorps   xmm0, xmm0
0x180005b7c  xor     eax, eax
0x180005b7e  movups  [rbp+13F0h+var_1468], xmm0
0x180005b82  mov     [rbp+13F0h+var_1458], rax
0x180005b86  xorps   xmm1, xmm1
0x180005b89  movups  [rsp+14F0h+var_1480], xmm1
0x180005b8e  mov     [rbp+13F0h+var_1470], rax
0x180005b92  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005b99  test    rax, rax
0x180005b9c  jz      short loc_180005BA9
0x180005b9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ba3  mov     [rbp+13F0h+var_1450], rax
0x180005ba7  jmp     short loc_180005BAD
0x180005ba9  mov     [rbp+13F0h+var_1450], r13
0x180005bad  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005bb4  test    rax, rax
0x180005bb7  jz      short loc_180005BC3
0x180005bb9  lea     rcx, [rsp+14F0h+var_14D0]
0x180005bbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bc3  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005bca  test    rax, rax
0x180005bcd  jz      short loc_180005BE3
0x180005bcf  mov     r8d, 400h
0x180005bd5  lea     rdx, [rbp+13F0h+var_1430]
0x180005bd9  lea     rcx, [rsp+14F0h+var_14D0]
0x180005bde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005be3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005bea  test    rax, rax
0x180005bed  jz      short loc_180005BF9
0x180005bef  lea     rcx, [rsp+14F0h+var_14D0]
0x180005bf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bf9  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005c00  test    rax, rax
0x180005c03  jz      short loc_180005C16
0x180005c05  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180005c0a  jnz     short loc_180005C16
0x180005c0c  lea     rcx, [rsp+14F0h+var_14D0]
0x180005c11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c16  cmp     [rsp+14F0h+var_14C8], r13d
0x180005c1b  jl      short loc_180005C2F
0x180005c1d  mov     ecx, 8000FFFFh; this
0x180005c22  mov     [rsp+14F0h+var_14C8], ecx
0x180005c26  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005c2b  mov     [rsp+14F0h+var_14C4], eax
0x180005c2f  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180005c36  jnz     short loc_180005C57
0x180005c38  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005c3f  test    rax, rax
0x180005c42  jz      short loc_180005C4D
0x180005c44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c49  test    al, al
0x180005c4b  jmp     short loc_180005C55
0x180005c4d  call    cs:__imp_IsDebuggerPresent
0x180005c53  test    eax, eax
0x180005c55  jz      short loc_180005C5E
0x180005c57  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180005c5c  jz      short loc_180005C84
0x180005c5e  mov     rax, cs:g_pfnResultLoggingCallback
0x180005c65  test    rax, rax
0x180005c68  jz      short loc_180005CDD
0x180005c6a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180005c71  jnz     short loc_180005CDD
0x180005c73  xor     r8d, r8d
0x180005c76  xor     edx, edx
0x180005c78  lea     rcx, [rsp+14F0h+var_14D0]
0x180005c7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c82  jmp     short loc_180005CDD
0x180005c84  mov     ebx, 800h
0x180005c89  mov     rax, cs:g_pfnResultLoggingCallback
0x180005c90  test    rax, rax
0x180005c93  jz      short loc_180005CB2
0x180005c95  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180005c9c  jnz     short loc_180005CB2
0x180005c9e  mov     r8d, ebx
0x180005ca1  lea     rdx, [rbp+13F0h+OutputString]
0x180005ca8  lea     rcx, [rsp+14F0h+var_14D0]
0x180005cad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cb2  cmp     [rbp+13F0h+OutputString], r13w
0x180005cba  jnz     short loc_180005CD0
0x180005cbc  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180005cc1  mov     rdx, rbx; unsigned __int16 *
0x180005cc4  lea     rcx, [rbp+13F0h+OutputString]; this
0x180005ccb  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005cd0  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180005cd7  call    cs:__imp_OutputDebugStringW
0x180005cdd  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180005ce2  jnz     short loc_180005CED
0x180005ce4  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180005ceb  jz      short loc_180005CFF
0x180005ced  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005cf4  test    rax, rax
0x180005cf7  jz      short loc_180005CFF
0x180005cf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cfe  nop
0x180005cff  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180005d04  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
