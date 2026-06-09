# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140003c6c`
- end: `0x140003ef9`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x14000392c`

## callees

- `0x140002de3`
- `0x140003c6c`
- `0x1400065b4`
- `0x140008f0c`
- `0x14000ad38`
- `0x14000b134`
- `0x140025d70`
- `0x140025e30`
- `0x140027010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140003d1a`
- `KERNEL32!GetCurrentThreadId` at `0x140003d1a`
- `KERNEL32!OutputDebugStringW` at `0x140003e98`
- `KERNEL32!OutputDebugStringW` at `0x140003e98`
- `KERNEL32!IsDebuggerPresent` at `0x140003e0e`
- `KERNEL32!IsDebuggerPresent` at `0x140003e0e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v10; // ebx
  int v11; // ecx
  __int64 v12; // rdx
  const struct wil::FailureInfo *v13; // rdx
  wil::details::in1diag3 *v14; // rcx
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
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v17, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
  v19 = *a7;
  v20 = a7[1];
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v19, (int)a7);
  v17 = 1;
  v11 = 0;
  if ( *(_DWORD *)(v12 + 8) == 1 )
    v11 = 8;
  v18 = v11;
  v21 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v26 = a3;
  v27 = a2;
  v28 = v10;
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
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v14);
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
      wil::GetFailureLogString(OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v17, v15);
    OutputDebugStringW(OutputString);
  }
  if ( ((v18 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v14);
  if ( (v18 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v17, v13);
}

```

## disassembly

```asm
0x140003c6c  push    rbp
0x140003c6e  push    rbx
0x140003c6f  push    rsi
0x140003c70  push    rdi
0x140003c71  push    r12
0x140003c73  push    r14
0x140003c75  push    r15
0x140003c77  lea     rbp, [rsp-13D0h]
0x140003c7f  mov     eax, 14D0h
0x140003c84  call    _alloca_probe
0x140003c89  sub     rsp, rax
0x140003c8c  mov     rax, cs:__security_cookie
0x140003c93  xor     rax, rsp
0x140003c96  mov     [rbp+1400h+var_40], rax
0x140003c9d  mov     r14, r8
0x140003ca0  mov     esi, edx
0x140003ca2  mov     r15, rcx
0x140003ca5  mov     rdi, [rbp+1400h+arg_28]
0x140003cac  xor     edx, edx; Val
0x140003cae  mov     r8d, 98h; Size
0x140003cb4  lea     rcx, [rsp+1500h+var_14E0]; void *
0x140003cb9  call    memset_0
0x140003cbe  nop
0x140003cbf  xor     r12d, r12d
0x140003cc2  mov     [rbp+1400h+OutputString], r12w
0x140003cca  mov     [rbp+1400h+var_1440], r12b
0x140003cce  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x140003cd5  mov     ecx, [rdx]; this
0x140003cd7  mov     [rsp+1500h+var_14D8], ecx
0x140003cdb  mov     eax, [rdx+4]
0x140003cde  mov     [rsp+1500h+var_14D4], eax
0x140003ce2  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140003ce7  mov     ebx, eax
0x140003ce9  mov     dword ptr [rsp+1500h+var_14E0], 1
0x140003cf1  mov     ecx, r12d
0x140003cf4  lea     eax, [r12+8]
0x140003cf9  cmp     dword ptr [rdx+8], 1
0x140003cfd  cmovz   ecx, eax
0x140003d00  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x140003d04  lea     ecx, [rax-7]
0x140003d07  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140003d0f  inc     ecx
0x140003d11  mov     [rsp+1500h+var_14D0], ecx
0x140003d15  mov     [rsp+1500h+var_14C8], r12
0x140003d1a  call    cs:__imp_GetCurrentThreadId
0x140003d20  mov     [rsp+1500h+var_14C0], eax
0x140003d24  mov     [rsp+1500h+var_14A8], r14
0x140003d29  mov     [rsp+1500h+var_14A0], esi
0x140003d2d  mov     [rsp+1500h+var_149C], ebx
0x140003d31  mov     [rsp+1500h+var_14B8], r12
0x140003d36  mov     [rsp+1500h+var_14B0], r12
0x140003d3b  mov     [rbp+1400h+var_1458], rdi
0x140003d3f  mov     [rbp+1400h+var_1450], r15
0x140003d43  mov     [rsp+1500h+var_1498], r12
0x140003d48  xorps   xmm0, xmm0
0x140003d4b  xor     eax, eax
0x140003d4d  movups  [rbp+1400h+var_1478], xmm0
0x140003d51  mov     [rbp+1400h+var_1468], rax
0x140003d55  xorps   xmm1, xmm1
0x140003d58  movups  [rsp+1500h+var_1490], xmm1
0x140003d5d  mov     [rbp+1400h+var_1480], rax
0x140003d61  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140003d68  test    rax, rax
0x140003d6b  jz      short loc_140003D78
0x140003d6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003d72  mov     [rbp+1400h+var_1460], rax
0x140003d76  jmp     short loc_140003D7C
0x140003d78  mov     [rbp+1400h+var_1460], r12
0x140003d7c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140003d83  test    rax, rax
0x140003d86  jz      short loc_140003D92
0x140003d88  lea     rcx, [rsp+1500h+var_14E0]
0x140003d8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003d92  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140003d99  test    rax, rax
0x140003d9c  jz      short loc_140003DB2
0x140003d9e  mov     r8d, 400h
0x140003da4  lea     rdx, [rbp+1400h+var_1440]
0x140003da8  lea     rcx, [rsp+1500h+var_14E0]
0x140003dad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003db2  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140003db9  test    rax, rax
0x140003dbc  jz      short loc_140003DC8
0x140003dbe  lea     rcx, [rsp+1500h+var_14E0]
0x140003dc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003dc8  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140003dcf  test    rax, rax
0x140003dd2  jz      short loc_140003DE5
0x140003dd4  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140003dd9  jnz     short loc_140003DE5
0x140003ddb  lea     rcx, [rsp+1500h+var_14E0]
0x140003de0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003de5  cmp     [rsp+1500h+var_14D8], r12d
0x140003dea  jge     loc_140003EF3
0x140003df0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x140003df7  jnz     short loc_140003E18
0x140003df9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140003e00  test    rax, rax
0x140003e03  jz      short loc_140003E0E
0x140003e05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003e0a  test    al, al
0x140003e0c  jmp     short loc_140003E16
0x140003e0e  call    cs:__imp_IsDebuggerPresent
0x140003e14  test    eax, eax
0x140003e16  jz      short loc_140003E1F
0x140003e18  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140003e1d  jz      short loc_140003E45
0x140003e1f  mov     rax, cs:g_pfnResultLoggingCallback
0x140003e26  test    rax, rax
0x140003e29  jz      short loc_140003E9E
0x140003e2b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140003e32  jnz     short loc_140003E9E
0x140003e34  xor     r8d, r8d
0x140003e37  xor     edx, edx
0x140003e39  lea     rcx, [rsp+1500h+var_14E0]
0x140003e3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003e43  jmp     short loc_140003E9E
0x140003e45  mov     ebx, 800h
0x140003e4a  mov     rax, cs:g_pfnResultLoggingCallback
0x140003e51  test    rax, rax
0x140003e54  jz      short loc_140003E73
0x140003e56  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140003e5d  jnz     short loc_140003E73
0x140003e5f  mov     r8d, ebx
0x140003e62  lea     rdx, [rbp+1400h+OutputString]
0x140003e69  lea     rcx, [rsp+1500h+var_14E0]
0x140003e6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003e73  cmp     [rbp+1400h+OutputString], r12w
0x140003e7b  jnz     short loc_140003E91
0x140003e7d  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x140003e82  mov     rdx, rbx; unsigned __int16 *
0x140003e85  lea     rcx, [rbp+1400h+OutputString]; pszDest
0x140003e8c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140003e91  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x140003e98  call    cs:__imp_OutputDebugStringW
0x140003e9e  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x140003ea3  jnz     short loc_140003EAE
0x140003ea5  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x140003eac  jz      short loc_140003EC0
0x140003eae  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140003eb5  test    rax, rax
0x140003eb8  jz      short loc_140003EC0
0x140003eba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003ebf  nop
0x140003ec0  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x140003ec5  jnz     short loc_140003EE8
0x140003ec7  mov     rcx, [rbp+1400h+var_40]
0x140003ece  xor     rcx, rsp; StackCookie
0x140003ed1  call    __security_check_cookie
0x140003ed6  add     rsp, 14D0h
0x140003edd  pop     r15
0x140003edf  pop     r14
0x140003ee1  pop     r12
0x140003ee3  pop     rdi
0x140003ee4  pop     rsi
0x140003ee5  pop     rbx
0x140003ee6  pop     rbp
0x140003ee7  retn
0x140003ee8  lea     rcx, [rsp+1500h+var_14E0]; this
0x140003eed  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x140003ef3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
