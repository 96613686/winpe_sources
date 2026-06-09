# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180004a1c`
- end: `0x180004cc2`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180004520`

## callees

- `0x180002b60`
- `0x1800036e4`
- `0x180004a1c`
- `0x180005e04`
- `0x180007100`
- `0x1800082b8`
- `0x1800083e8`
- `0x18006ab40`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004ae2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004ae2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004bd7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004bd7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004c61`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004c61`

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
        int *a7,
        _WORD *a8)
{
  int v11; // r15d
  int v12; // ecx
  __int64 v13; // rdx
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh]
  int v20; // [rsp+28h] [rbp-D8h]
  int v21; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v22; // [rsp+30h] [rbp-D0h]
  _WORD *v23; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+48h] [rbp-B8h]
  __int64 v26; // [rsp+50h] [rbp-B0h]
  __int64 v27; // [rsp+58h] [rbp-A8h]
  int v28; // [rsp+60h] [rbp-A0h]
  int v29; // [rsp+64h] [rbp-9Ch]
  __int64 v30; // [rsp+68h] [rbp-98h]
  __int128 v31; // [rsp+70h] [rbp-90h]
  __int64 v32; // [rsp+80h] [rbp-80h]
  __int128 v33; // [rsp+88h] [rbp-78h]
  __int64 v34; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v36; // [rsp+A8h] [rbp-58h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  char v38[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v11 = wil::details::RecordReturn((wil::details *)(unsigned int)v20, (int)a7);
  v18 = 1;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  v19 = v12;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v11;
  v25 = 0;
  v26 = 0;
  v36 = a6;
  v37 = a1;
  v30 = 0;
  v33 = 0;
  v34 = 0;
  v31 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v18);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v18, v38, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v18);
  if ( wil::details::g_pfnOriginateCallback && (v19 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v18);
  if ( v20 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v19 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v18, v16);
    OutputDebugStringW(OutputString);
  }
  if ( ((v19 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v19 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x180004a1c  push    rbp
0x180004a1e  push    rbx
0x180004a1f  push    rsi
0x180004a20  push    rdi
0x180004a21  push    r12
0x180004a23  push    r14
0x180004a25  push    r15
0x180004a27  lea     rbp, [rsp-13D0h]
0x180004a2f  mov     eax, 14D0h
0x180004a34  call    _alloca_probe
0x180004a39  sub     rsp, rax
0x180004a3c  mov     rax, cs:__security_cookie
0x180004a43  xor     rax, rsp
0x180004a46  mov     [rbp+1400h+var_40], rax
0x180004a4d  mov     rsi, r8
0x180004a50  mov     edi, edx
0x180004a52  mov     rbx, rcx
0x180004a55  mov     r14, [rbp+1400h+arg_28]
0x180004a5c  xor     edx, edx; Val
0x180004a5e  mov     r8d, 98h; Size
0x180004a64  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180004a69  call    memset_0
0x180004a6e  nop
0x180004a6f  xor     r12d, r12d
0x180004a72  mov     [rbp+1400h+OutputString], r12w
0x180004a7a  mov     [rbp+1400h+var_1440], r12b
0x180004a7e  mov     rdx, [rbp+1400h+arg_30]; int
0x180004a85  mov     ecx, [rdx]; this
0x180004a87  mov     [rsp+1500h+var_14D8], ecx
0x180004a8b  mov     eax, [rdx+4]
0x180004a8e  mov     [rsp+1500h+var_14D4], eax
0x180004a92  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004a97  mov     r15d, eax
0x180004a9a  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180004aa2  mov     ecx, r12d
0x180004aa5  lea     eax, [r12+8]
0x180004aaa  cmp     dword ptr [rdx+8], 1
0x180004aae  cmovz   ecx, eax
0x180004ab1  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180004ab5  lea     ecx, [rax-7]
0x180004ab8  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004ac0  inc     ecx
0x180004ac2  mov     [rsp+1500h+var_14D0], ecx
0x180004ac6  mov     rcx, [rbp+1400h+arg_38]
0x180004acd  test    rcx, rcx
0x180004ad0  jz      short loc_180004ADD
0x180004ad2  cmp     [rcx], r12w
0x180004ad6  mov     [rsp+1500h+var_14C8], rcx
0x180004adb  jnz     short loc_180004AE2
0x180004add  mov     [rsp+1500h+var_14C8], r12
0x180004ae2  call    cs:__imp_GetCurrentThreadId
0x180004ae8  mov     [rsp+1500h+var_14C0], eax
0x180004aec  mov     [rsp+1500h+var_14A8], rsi
0x180004af1  mov     [rsp+1500h+var_14A0], edi
0x180004af5  mov     [rsp+1500h+var_149C], r15d
0x180004afa  mov     [rsp+1500h+var_14B8], r12
0x180004aff  mov     [rsp+1500h+var_14B0], r12
0x180004b04  mov     [rbp+1400h+var_1458], r14
0x180004b08  mov     [rbp+1400h+var_1450], rbx
0x180004b0c  mov     [rsp+1500h+var_1498], r12
0x180004b11  xorps   xmm0, xmm0
0x180004b14  xor     eax, eax
0x180004b16  movups  [rbp+1400h+var_1478], xmm0
0x180004b1a  mov     [rbp+1400h+var_1468], rax
0x180004b1e  xorps   xmm1, xmm1
0x180004b21  movups  [rsp+1500h+var_1490], xmm1
0x180004b26  mov     [rbp+1400h+var_1480], rax
0x180004b2a  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004b31  test    rax, rax
0x180004b34  jz      short loc_180004B41
0x180004b36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b3b  mov     [rbp+1400h+var_1460], rax
0x180004b3f  jmp     short loc_180004B45
0x180004b41  mov     [rbp+1400h+var_1460], r12
0x180004b45  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004b4c  test    rax, rax
0x180004b4f  jz      short loc_180004B5B
0x180004b51  lea     rcx, [rsp+1500h+var_14E0]
0x180004b56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b5b  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004b62  test    rax, rax
0x180004b65  jz      short loc_180004B7B
0x180004b67  mov     r8d, 400h
0x180004b6d  lea     rdx, [rbp+1400h+var_1440]
0x180004b71  lea     rcx, [rsp+1500h+var_14E0]
0x180004b76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b7b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004b82  test    rax, rax
0x180004b85  jz      short loc_180004B91
0x180004b87  lea     rcx, [rsp+1500h+var_14E0]
0x180004b8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b91  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004b98  test    rax, rax
0x180004b9b  jz      short loc_180004BAE
0x180004b9d  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180004ba2  jnz     short loc_180004BAE
0x180004ba4  lea     rcx, [rsp+1500h+var_14E0]
0x180004ba9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bae  cmp     [rsp+1500h+var_14D8], r12d
0x180004bb3  jge     loc_180004CBC
0x180004bb9  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180004bc0  jnz     short loc_180004BE1
0x180004bc2  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004bc9  test    rax, rax
0x180004bcc  jz      short loc_180004BD7
0x180004bce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bd3  test    al, al
0x180004bd5  jmp     short loc_180004BDF
0x180004bd7  call    cs:__imp_IsDebuggerPresent
0x180004bdd  test    eax, eax
0x180004bdf  jz      short loc_180004BE8
0x180004be1  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180004be6  jz      short loc_180004C0E
0x180004be8  mov     rax, cs:g_pfnResultLoggingCallback
0x180004bef  test    rax, rax
0x180004bf2  jz      short loc_180004C67
0x180004bf4  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180004bfb  jnz     short loc_180004C67
0x180004bfd  xor     r8d, r8d
0x180004c00  xor     edx, edx
0x180004c02  lea     rcx, [rsp+1500h+var_14E0]
0x180004c07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c0c  jmp     short loc_180004C67
0x180004c0e  mov     ebx, 800h
0x180004c13  mov     rax, cs:g_pfnResultLoggingCallback
0x180004c1a  test    rax, rax
0x180004c1d  jz      short loc_180004C3C
0x180004c1f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180004c26  jnz     short loc_180004C3C
0x180004c28  mov     r8d, ebx
0x180004c2b  lea     rdx, [rbp+1400h+OutputString]
0x180004c32  lea     rcx, [rsp+1500h+var_14E0]
0x180004c37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c3c  cmp     [rbp+1400h+OutputString], r12w
0x180004c44  jnz     short loc_180004C5A
0x180004c46  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180004c4b  mov     rdx, rbx; unsigned __int16 *
0x180004c4e  lea     rcx, [rbp+1400h+OutputString]; this
0x180004c55  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004c5a  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180004c61  call    cs:__imp_OutputDebugStringW
0x180004c67  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180004c6c  jnz     short loc_180004C77
0x180004c6e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180004c75  jz      short loc_180004C89
0x180004c77  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004c7e  test    rax, rax
0x180004c81  jz      short loc_180004C89
0x180004c83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c88  nop
0x180004c89  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180004c8e  jnz     short loc_180004CB1
0x180004c90  mov     rcx, [rbp+1400h+var_40]
0x180004c97  xor     rcx, rsp; StackCookie
0x180004c9a  call    __security_check_cookie
0x180004c9f  add     rsp, 14D0h
0x180004ca6  pop     r15
0x180004ca8  pop     r14
0x180004caa  pop     r12
0x180004cac  pop     rdi
0x180004cad  pop     rsi
0x180004cae  pop     rbx
0x180004caf  pop     rbp
0x180004cb0  retn
0x180004cb1  lea     rcx, [rsp+1500h+var_14E0]; this
0x180004cb6  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180004cbc  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
