# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180003a3c`
- end: `0x180003ce2`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180003014`

## callees

- `0x180001600`
- `0x180002062`
- `0x180003a3c`
- `0x180004e44`
- `0x1800066c0`
- `0x1800077d0`
- `0x1800078ac`
- `0x18000ce90`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003b02`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003b02`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003c81`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003c81`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003bf7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003bf7`

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
      g_pfnResultLoggingCallback(&v18, 0, 0, v16);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048, v16);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v18, v16);
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
0x180003a3c  push    rbp
0x180003a3e  push    rbx
0x180003a3f  push    rsi
0x180003a40  push    rdi
0x180003a41  push    r12
0x180003a43  push    r14
0x180003a45  push    r15
0x180003a47  lea     rbp, [rsp-13D0h]
0x180003a4f  mov     eax, 14D0h
0x180003a54  call    _alloca_probe
0x180003a59  sub     rsp, rax
0x180003a5c  mov     rax, cs:__security_cookie
0x180003a63  xor     rax, rsp
0x180003a66  mov     [rbp+1400h+var_40], rax
0x180003a6d  mov     rsi, r8
0x180003a70  mov     edi, edx
0x180003a72  mov     rbx, rcx
0x180003a75  mov     r14, [rbp+1400h+arg_28]
0x180003a7c  xor     edx, edx; Val
0x180003a7e  mov     r8d, 98h; Size
0x180003a84  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180003a89  call    memset_0
0x180003a8e  nop
0x180003a8f  xor     r12d, r12d
0x180003a92  mov     [rbp+1400h+OutputString], r12w
0x180003a9a  mov     [rbp+1400h+var_1440], r12b
0x180003a9e  mov     rdx, [rbp+1400h+arg_30]; int
0x180003aa5  mov     ecx, [rdx]; this
0x180003aa7  mov     [rsp+1500h+var_14D8], ecx
0x180003aab  mov     eax, [rdx+4]
0x180003aae  mov     [rsp+1500h+var_14D4], eax
0x180003ab2  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180003ab7  mov     r15d, eax
0x180003aba  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180003ac2  mov     ecx, r12d
0x180003ac5  lea     eax, [r12+8]
0x180003aca  cmp     dword ptr [rdx+8], 1
0x180003ace  cmovz   ecx, eax
0x180003ad1  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180003ad5  lea     ecx, [rax-7]
0x180003ad8  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003ae0  inc     ecx
0x180003ae2  mov     [rsp+1500h+var_14D0], ecx
0x180003ae6  mov     rcx, [rbp+1400h+arg_38]
0x180003aed  test    rcx, rcx
0x180003af0  jz      short loc_180003AFD
0x180003af2  cmp     [rcx], r12w
0x180003af6  mov     [rsp+1500h+var_14C8], rcx
0x180003afb  jnz     short loc_180003B02
0x180003afd  mov     [rsp+1500h+var_14C8], r12
0x180003b02  call    cs:__imp_GetCurrentThreadId
0x180003b08  mov     [rsp+1500h+var_14C0], eax
0x180003b0c  mov     [rsp+1500h+var_14A8], rsi
0x180003b11  mov     [rsp+1500h+var_14A0], edi
0x180003b15  mov     [rsp+1500h+var_149C], r15d
0x180003b1a  mov     [rsp+1500h+var_14B8], r12
0x180003b1f  mov     [rsp+1500h+var_14B0], r12
0x180003b24  mov     [rbp+1400h+var_1458], r14
0x180003b28  mov     [rbp+1400h+var_1450], rbx
0x180003b2c  mov     [rsp+1500h+var_1498], r12
0x180003b31  xorps   xmm0, xmm0
0x180003b34  xor     eax, eax
0x180003b36  movups  [rbp+1400h+var_1478], xmm0
0x180003b3a  mov     [rbp+1400h+var_1468], rax
0x180003b3e  xorps   xmm1, xmm1
0x180003b41  movups  [rsp+1500h+var_1490], xmm1
0x180003b46  mov     [rbp+1400h+var_1480], rax
0x180003b4a  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003b51  test    rax, rax
0x180003b54  jz      short loc_180003B61
0x180003b56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b5b  mov     [rbp+1400h+var_1460], rax
0x180003b5f  jmp     short loc_180003B65
0x180003b61  mov     [rbp+1400h+var_1460], r12
0x180003b65  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003b6c  test    rax, rax
0x180003b6f  jz      short loc_180003B7B
0x180003b71  lea     rcx, [rsp+1500h+var_14E0]
0x180003b76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b7b  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003b82  test    rax, rax
0x180003b85  jz      short loc_180003B9B
0x180003b87  mov     r8d, 400h
0x180003b8d  lea     rdx, [rbp+1400h+var_1440]
0x180003b91  lea     rcx, [rsp+1500h+var_14E0]
0x180003b96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b9b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003ba2  test    rax, rax
0x180003ba5  jz      short loc_180003BB1
0x180003ba7  lea     rcx, [rsp+1500h+var_14E0]
0x180003bac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bb1  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003bb8  test    rax, rax
0x180003bbb  jz      short loc_180003BCE
0x180003bbd  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003bc2  jnz     short loc_180003BCE
0x180003bc4  lea     rcx, [rsp+1500h+var_14E0]
0x180003bc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bce  cmp     [rsp+1500h+var_14D8], r12d
0x180003bd3  jge     loc_180003CDC
0x180003bd9  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180003be0  jnz     short loc_180003C01
0x180003be2  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003be9  test    rax, rax
0x180003bec  jz      short loc_180003BF7
0x180003bee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bf3  test    al, al
0x180003bf5  jmp     short loc_180003BFF
0x180003bf7  call    cs:__imp_IsDebuggerPresent
0x180003bfd  test    eax, eax
0x180003bff  jz      short loc_180003C08
0x180003c01  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003c06  jz      short loc_180003C2E
0x180003c08  mov     rax, cs:g_pfnResultLoggingCallback
0x180003c0f  test    rax, rax
0x180003c12  jz      short loc_180003C87
0x180003c14  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003c1b  jnz     short loc_180003C87
0x180003c1d  xor     r8d, r8d
0x180003c20  xor     edx, edx
0x180003c22  lea     rcx, [rsp+1500h+var_14E0]
0x180003c27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c2c  jmp     short loc_180003C87
0x180003c2e  mov     ebx, 800h
0x180003c33  mov     rax, cs:g_pfnResultLoggingCallback
0x180003c3a  test    rax, rax
0x180003c3d  jz      short loc_180003C5C
0x180003c3f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003c46  jnz     short loc_180003C5C
0x180003c48  mov     r8d, ebx
0x180003c4b  lea     rdx, [rbp+1400h+OutputString]
0x180003c52  lea     rcx, [rsp+1500h+var_14E0]
0x180003c57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c5c  cmp     [rbp+1400h+OutputString], r12w
0x180003c64  jnz     short loc_180003C7A
0x180003c66  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180003c6b  mov     rdx, rbx; unsigned __int16 *
0x180003c6e  lea     rcx, [rbp+1400h+OutputString]; this
0x180003c75  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003c7a  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180003c81  call    cs:__imp_OutputDebugStringW
0x180003c87  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180003c8c  jnz     short loc_180003C97
0x180003c8e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180003c95  jz      short loc_180003CA9
0x180003c97  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003c9e  test    rax, rax
0x180003ca1  jz      short loc_180003CA9
0x180003ca3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ca8  nop
0x180003ca9  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180003cae  jnz     short loc_180003CD1
0x180003cb0  mov     rcx, [rbp+1400h+var_40]
0x180003cb7  xor     rcx, rsp; StackCookie
0x180003cba  call    __security_check_cookie
0x180003cbf  add     rsp, 14D0h
0x180003cc6  pop     r15
0x180003cc8  pop     r14
0x180003cca  pop     r12
0x180003ccc  pop     rdi
0x180003ccd  pop     rsi
0x180003cce  pop     rbx
0x180003ccf  pop     rbp
0x180003cd0  retn
0x180003cd1  lea     rcx, [rsp+1500h+var_14E0]; this
0x180003cd6  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180003cdc  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
