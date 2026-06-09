# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180007b54`
- end: `0x180007ddf`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `651`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000775c`

## callees

- `0x180006330`
- `0x180006e9c`
- `0x180007b54`
- `0x18000a3b8`
- `0x18000c530`
- `0x18000e9d8`
- `0x18000eb94`
- `0x18001e940`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007c01`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007c01`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007d7f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007d7f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007cf5`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007cf5`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v10; // eax
  int v11; // eax
  __int64 v12; // rdx
  int v13; // ebx
  int v14; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v16; // rdx
  wil::details::in1diag3 *v17; // rcx
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
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v10 = a7[1];
  v22 = *a7;
  v23 = v10;
  v11 = wil::details::RecordReturn((wil::details *)(unsigned int)v22, (int)a7);
  v19 = *(_DWORD *)(v12 + 8) == 1;
  v13 = v11;
  v20 = 1;
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
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v17);
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
  if ( ((v21 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v17);
  if ( (v21 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v20, v16);
}

```

## disassembly

```asm
0x180007b54  push    rbp
0x180007b56  push    rbx
0x180007b57  push    rsi
0x180007b58  push    rdi
0x180007b59  push    r12
0x180007b5b  push    r14
0x180007b5d  push    r15
0x180007b5f  lea     rbp, [rsp-13D0h]
0x180007b67  mov     eax, 14D0h
0x180007b6c  call    _alloca_probe
0x180007b71  sub     rsp, rax
0x180007b74  mov     rax, cs:__security_cookie
0x180007b7b  xor     rax, rsp
0x180007b7e  mov     [rbp+1400h+var_40], rax
0x180007b85  mov     rdi, [rbp+1400h+arg_28]
0x180007b8c  mov     r14, r8
0x180007b8f  mov     esi, edx
0x180007b91  mov     r15, rcx
0x180007b94  xor     edx, edx; Val
0x180007b96  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180007b9b  mov     r8d, 98h; Size
0x180007ba1  call    memset_0
0x180007ba6  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180007bad  xor     r12d, r12d
0x180007bb0  mov     [rbp+1400h+OutputString], r12w
0x180007bb8  mov     [rbp+1400h+var_1440], r12b
0x180007bbc  mov     ecx, [rdx]; this
0x180007bbe  mov     eax, [rdx+4]
0x180007bc1  mov     [rsp+1500h+var_14D8], ecx
0x180007bc5  mov     [rsp+1500h+var_14D4], eax
0x180007bc9  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180007bce  cmp     dword ptr [rdx+8], 1
0x180007bd2  mov     ebx, eax
0x180007bd4  lea     eax, [r12+8]
0x180007bd9  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180007be1  mov     ecx, r12d
0x180007be4  cmovz   ecx, eax
0x180007be7  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180007beb  lea     ecx, [rax-7]
0x180007bee  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180007bf6  inc     ecx
0x180007bf8  mov     [rsp+1500h+var_14C8], r12
0x180007bfd  mov     [rsp+1500h+var_14D0], ecx
0x180007c01  call    cs:__imp_GetCurrentThreadId
0x180007c07  xorps   xmm0, xmm0
0x180007c0a  mov     [rsp+1500h+var_14A8], r14
0x180007c0f  mov     [rsp+1500h+var_14C0], eax
0x180007c13  xorps   xmm1, xmm1
0x180007c16  xor     eax, eax
0x180007c18  mov     [rsp+1500h+var_14A0], esi
0x180007c1c  mov     [rbp+1400h+var_1468], rax
0x180007c20  mov     [rbp+1400h+var_1480], rax
0x180007c24  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180007c2b  mov     [rsp+1500h+var_149C], ebx
0x180007c2f  mov     [rsp+1500h+var_14B8], r12
0x180007c34  mov     [rsp+1500h+var_14B0], r12
0x180007c39  mov     [rbp+1400h+var_1458], rdi
0x180007c3d  mov     [rbp+1400h+var_1450], r15
0x180007c41  mov     [rsp+1500h+var_1498], r12
0x180007c46  movups  [rbp+1400h+var_1478], xmm0
0x180007c4a  movups  [rsp+1500h+var_1490], xmm1
0x180007c4f  test    rax, rax
0x180007c52  jz      short loc_180007C5F
0x180007c54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c59  mov     [rbp+1400h+var_1460], rax
0x180007c5d  jmp     short loc_180007C63
0x180007c5f  mov     [rbp+1400h+var_1460], r12
0x180007c63  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180007c6a  test    rax, rax
0x180007c6d  jz      short loc_180007C79
0x180007c6f  lea     rcx, [rsp+1500h+var_14E0]
0x180007c74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c79  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180007c80  test    rax, rax
0x180007c83  jz      short loc_180007C99
0x180007c85  mov     r8d, 400h
0x180007c8b  lea     rdx, [rbp+1400h+var_1440]
0x180007c8f  lea     rcx, [rsp+1500h+var_14E0]
0x180007c94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c99  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007ca0  test    rax, rax
0x180007ca3  jz      short loc_180007CAF
0x180007ca5  lea     rcx, [rsp+1500h+var_14E0]
0x180007caa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007caf  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007cb6  test    rax, rax
0x180007cb9  jz      short loc_180007CCC
0x180007cbb  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180007cc0  jnz     short loc_180007CCC
0x180007cc2  lea     rcx, [rsp+1500h+var_14E0]
0x180007cc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ccc  cmp     [rsp+1500h+var_14D8], r12d
0x180007cd1  jge     loc_180007DCE
0x180007cd7  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180007cde  jnz     short loc_180007CFF
0x180007ce0  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180007ce7  test    rax, rax
0x180007cea  jz      short loc_180007CF5
0x180007cec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cf1  test    al, al
0x180007cf3  jmp     short loc_180007CFD
0x180007cf5  call    cs:__imp_IsDebuggerPresent
0x180007cfb  test    eax, eax
0x180007cfd  jz      short loc_180007D06
0x180007cff  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180007d04  jz      short loc_180007D2C
0x180007d06  mov     rax, cs:g_pfnResultLoggingCallback
0x180007d0d  test    rax, rax
0x180007d10  jz      short loc_180007D85
0x180007d12  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180007d19  jnz     short loc_180007D85
0x180007d1b  xor     r8d, r8d
0x180007d1e  lea     rcx, [rsp+1500h+var_14E0]
0x180007d23  xor     edx, edx
0x180007d25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d2a  jmp     short loc_180007D85
0x180007d2c  mov     rax, cs:g_pfnResultLoggingCallback
0x180007d33  mov     ebx, 800h
0x180007d38  test    rax, rax
0x180007d3b  jz      short loc_180007D5A
0x180007d3d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180007d44  jnz     short loc_180007D5A
0x180007d46  mov     r8d, ebx
0x180007d49  lea     rdx, [rbp+1400h+OutputString]
0x180007d50  lea     rcx, [rsp+1500h+var_14E0]
0x180007d55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d5a  cmp     [rbp+1400h+OutputString], r12w
0x180007d62  jnz     short loc_180007D78
0x180007d64  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180007d69  mov     rdx, rbx; unsigned __int16 *
0x180007d6c  lea     rcx, [rbp+1400h+OutputString]; this
0x180007d73  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180007d78  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180007d7f  call    cs:__imp_OutputDebugStringW
0x180007d85  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180007d8a  jnz     short loc_180007D95
0x180007d8c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180007d93  jz      short loc_180007DA6
0x180007d95  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180007d9c  test    rax, rax
0x180007d9f  jz      short loc_180007DA6
0x180007da1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007da6  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180007dab  jnz     short loc_180007DD4
0x180007dad  mov     rcx, [rbp+1400h+var_40]
0x180007db4  xor     rcx, rsp; StackCookie
0x180007db7  call    __security_check_cookie
0x180007dbc  add     rsp, 14D0h
0x180007dc3  pop     r15
0x180007dc5  pop     r14
0x180007dc7  pop     r12
0x180007dc9  pop     rdi
0x180007dca  pop     rsi
0x180007dcb  pop     rbx
0x180007dcc  pop     rbp
0x180007dcd  retn
0x180007dce  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180007dd4  lea     rcx, [rsp+1500h+var_14E0]; this
0x180007dd9  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
