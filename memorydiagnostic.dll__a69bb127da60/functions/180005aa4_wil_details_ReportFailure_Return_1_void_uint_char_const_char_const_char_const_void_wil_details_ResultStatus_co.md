# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180005aa4`
- end: `0x180005d4a`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180004cec`

## callees

- `0x180002e50`
- `0x180003940`
- `0x180005aa4`
- `0x18000cd54`
- `0x18000f3c8`
- `0x180014e80`
- `0x1800155f4`
- `0x180020830`
- `0x180023010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x180005c5f`
- `KERNEL32!IsDebuggerPresent` at `0x180005c5f`
- `KERNEL32!OutputDebugStringW` at `0x180005ce9`
- `KERNEL32!OutputDebugStringW` at `0x180005ce9`
- `KERNEL32!GetCurrentThreadId` at `0x180005b6a`
- `KERNEL32!GetCurrentThreadId` at `0x180005b6a`

## pseudocode

```c
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
0x180005aa4  push    rbp
0x180005aa6  push    rbx
0x180005aa7  push    rsi
0x180005aa8  push    rdi
0x180005aa9  push    r12
0x180005aab  push    r14
0x180005aad  push    r15
0x180005aaf  lea     rbp, [rsp-13D0h]
0x180005ab7  mov     eax, 14D0h
0x180005abc  call    _alloca_probe
0x180005ac1  sub     rsp, rax
0x180005ac4  mov     rax, cs:__security_cookie
0x180005acb  xor     rax, rsp
0x180005ace  mov     [rbp+1400h+var_40], rax
0x180005ad5  mov     rsi, r8
0x180005ad8  mov     edi, edx
0x180005ada  mov     rbx, rcx
0x180005add  mov     r14, [rbp+1400h+arg_28]
0x180005ae4  xor     edx, edx; Val
0x180005ae6  mov     r8d, 98h; Size
0x180005aec  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180005af1  call    memset_0
0x180005af6  nop
0x180005af7  xor     r12d, r12d
0x180005afa  mov     [rbp+1400h+OutputString], r12w
0x180005b02  mov     [rbp+1400h+var_1440], r12b
0x180005b06  mov     rdx, [rbp+1400h+arg_30]; int
0x180005b0d  mov     ecx, [rdx]; this
0x180005b0f  mov     [rsp+1500h+var_14D8], ecx
0x180005b13  mov     eax, [rdx+4]
0x180005b16  mov     [rsp+1500h+var_14D4], eax
0x180005b1a  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005b1f  mov     r15d, eax
0x180005b22  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180005b2a  mov     ecx, r12d
0x180005b2d  lea     eax, [r12+8]
0x180005b32  cmp     dword ptr [rdx+8], 1
0x180005b36  cmovz   ecx, eax
0x180005b39  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180005b3d  lea     ecx, [rax-7]
0x180005b40  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005b48  inc     ecx
0x180005b4a  mov     [rsp+1500h+var_14D0], ecx
0x180005b4e  mov     rcx, [rbp+1400h+arg_38]
0x180005b55  test    rcx, rcx
0x180005b58  jz      short loc_180005B65
0x180005b5a  cmp     [rcx], r12w
0x180005b5e  mov     [rsp+1500h+var_14C8], rcx
0x180005b63  jnz     short loc_180005B6A
0x180005b65  mov     [rsp+1500h+var_14C8], r12
0x180005b6a  call    cs:__imp_GetCurrentThreadId
0x180005b70  mov     [rsp+1500h+var_14C0], eax
0x180005b74  mov     [rsp+1500h+var_14A8], rsi
0x180005b79  mov     [rsp+1500h+var_14A0], edi
0x180005b7d  mov     [rsp+1500h+var_149C], r15d
0x180005b82  mov     [rsp+1500h+var_14B8], r12
0x180005b87  mov     [rsp+1500h+var_14B0], r12
0x180005b8c  mov     [rbp+1400h+var_1458], r14
0x180005b90  mov     [rbp+1400h+var_1450], rbx
0x180005b94  mov     [rsp+1500h+var_1498], r12
0x180005b99  xorps   xmm0, xmm0
0x180005b9c  xor     eax, eax
0x180005b9e  movups  [rbp+1400h+var_1478], xmm0
0x180005ba2  mov     [rbp+1400h+var_1468], rax
0x180005ba6  xorps   xmm1, xmm1
0x180005ba9  movups  [rsp+1500h+var_1490], xmm1
0x180005bae  mov     [rbp+1400h+var_1480], rax
0x180005bb2  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005bb9  test    rax, rax
0x180005bbc  jz      short loc_180005BC9
0x180005bbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bc3  mov     [rbp+1400h+var_1460], rax
0x180005bc7  jmp     short loc_180005BCD
0x180005bc9  mov     [rbp+1400h+var_1460], r12
0x180005bcd  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005bd4  test    rax, rax
0x180005bd7  jz      short loc_180005BE3
0x180005bd9  lea     rcx, [rsp+1500h+var_14E0]
0x180005bde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005be3  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005bea  test    rax, rax
0x180005bed  jz      short loc_180005C03
0x180005bef  mov     r8d, 400h
0x180005bf5  lea     rdx, [rbp+1400h+var_1440]
0x180005bf9  lea     rcx, [rsp+1500h+var_14E0]
0x180005bfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c03  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005c0a  test    rax, rax
0x180005c0d  jz      short loc_180005C19
0x180005c0f  lea     rcx, [rsp+1500h+var_14E0]
0x180005c14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c19  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005c20  test    rax, rax
0x180005c23  jz      short loc_180005C36
0x180005c25  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180005c2a  jnz     short loc_180005C36
0x180005c2c  lea     rcx, [rsp+1500h+var_14E0]
0x180005c31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c36  cmp     [rsp+1500h+var_14D8], r12d
0x180005c3b  jge     loc_180005D44
0x180005c41  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180005c48  jnz     short loc_180005C69
0x180005c4a  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005c51  test    rax, rax
0x180005c54  jz      short loc_180005C5F
0x180005c56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c5b  test    al, al
0x180005c5d  jmp     short loc_180005C67
0x180005c5f  call    cs:__imp_IsDebuggerPresent
0x180005c65  test    eax, eax
0x180005c67  jz      short loc_180005C70
0x180005c69  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180005c6e  jz      short loc_180005C96
0x180005c70  mov     rax, cs:g_pfnResultLoggingCallback
0x180005c77  test    rax, rax
0x180005c7a  jz      short loc_180005CEF
0x180005c7c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180005c83  jnz     short loc_180005CEF
0x180005c85  xor     r8d, r8d
0x180005c88  xor     edx, edx
0x180005c8a  lea     rcx, [rsp+1500h+var_14E0]
0x180005c8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c94  jmp     short loc_180005CEF
0x180005c96  mov     ebx, 800h
0x180005c9b  mov     rax, cs:g_pfnResultLoggingCallback
0x180005ca2  test    rax, rax
0x180005ca5  jz      short loc_180005CC4
0x180005ca7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180005cae  jnz     short loc_180005CC4
0x180005cb0  mov     r8d, ebx
0x180005cb3  lea     rdx, [rbp+1400h+OutputString]
0x180005cba  lea     rcx, [rsp+1500h+var_14E0]
0x180005cbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cc4  cmp     [rbp+1400h+OutputString], r12w
0x180005ccc  jnz     short loc_180005CE2
0x180005cce  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180005cd3  mov     rdx, rbx; unsigned __int16 *
0x180005cd6  lea     rcx, [rbp+1400h+OutputString]; this
0x180005cdd  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005ce2  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180005ce9  call    cs:__imp_OutputDebugStringW
0x180005cef  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180005cf4  jnz     short loc_180005CFF
0x180005cf6  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180005cfd  jz      short loc_180005D11
0x180005cff  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005d06  test    rax, rax
0x180005d09  jz      short loc_180005D11
0x180005d0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d10  nop
0x180005d11  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180005d16  jnz     short loc_180005D39
0x180005d18  mov     rcx, [rbp+1400h+var_40]
0x180005d1f  xor     rcx, rsp; StackCookie
0x180005d22  call    __security_check_cookie
0x180005d27  add     rsp, 14D0h
0x180005d2e  pop     r15
0x180005d30  pop     r14
0x180005d32  pop     r12
0x180005d34  pop     rdi
0x180005d35  pop     rsi
0x180005d36  pop     rbx
0x180005d37  pop     rbp
0x180005d38  retn
0x180005d39  lea     rcx, [rsp+1500h+var_14E0]; this
0x180005d3e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180005d44  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
