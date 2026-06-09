# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800e4be4`
- end: `0x1800e4e8a`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800e4798`

## callees

- `0x180019000`
- `0x180019fc4`
- `0x1800a9e20`
- `0x1800e4be4`
- `0x1800ea2e4`
- `0x1800ec33c`
- `0x1800ee258`
- `0x1800eeb1c`
- `0x180191010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800e4caa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800e4caa`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800e4d9f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800e4d9f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800e4e29`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800e4e29`

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
0x1800e4be4  push    rbp
0x1800e4be6  push    rbx
0x1800e4be7  push    rsi
0x1800e4be8  push    rdi
0x1800e4be9  push    r12
0x1800e4beb  push    r14
0x1800e4bed  push    r15
0x1800e4bef  lea     rbp, [rsp-13D0h]
0x1800e4bf7  mov     eax, 14D0h
0x1800e4bfc  call    _alloca_probe
0x1800e4c01  sub     rsp, rax
0x1800e4c04  mov     rax, cs:__security_cookie
0x1800e4c0b  xor     rax, rsp
0x1800e4c0e  mov     [rbp+1400h+var_40], rax
0x1800e4c15  mov     rsi, r8
0x1800e4c18  mov     edi, edx
0x1800e4c1a  mov     rbx, rcx
0x1800e4c1d  mov     r14, [rbp+1400h+arg_28]
0x1800e4c24  xor     edx, edx; Val
0x1800e4c26  mov     r8d, 98h; Size
0x1800e4c2c  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1800e4c31  call    memset_0
0x1800e4c36  nop
0x1800e4c37  xor     r12d, r12d
0x1800e4c3a  mov     [rbp+1400h+OutputString], r12w
0x1800e4c42  mov     [rbp+1400h+var_1440], r12b
0x1800e4c46  mov     rdx, [rbp+1400h+arg_30]; int
0x1800e4c4d  mov     ecx, [rdx]; this
0x1800e4c4f  mov     [rsp+1500h+var_14D8], ecx
0x1800e4c53  mov     eax, [rdx+4]
0x1800e4c56  mov     [rsp+1500h+var_14D4], eax
0x1800e4c5a  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800e4c5f  mov     r15d, eax
0x1800e4c62  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800e4c6a  mov     ecx, r12d
0x1800e4c6d  lea     eax, [r12+8]
0x1800e4c72  cmp     dword ptr [rdx+8], 1
0x1800e4c76  cmovz   ecx, eax
0x1800e4c79  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800e4c7d  lea     ecx, [rax-7]
0x1800e4c80  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800e4c88  inc     ecx
0x1800e4c8a  mov     [rsp+1500h+var_14D0], ecx
0x1800e4c8e  mov     rcx, [rbp+1400h+arg_38]
0x1800e4c95  test    rcx, rcx
0x1800e4c98  jz      short loc_1800E4CA5
0x1800e4c9a  cmp     [rcx], r12w
0x1800e4c9e  mov     [rsp+1500h+var_14C8], rcx
0x1800e4ca3  jnz     short loc_1800E4CAA
0x1800e4ca5  mov     [rsp+1500h+var_14C8], r12
0x1800e4caa  call    cs:__imp_GetCurrentThreadId
0x1800e4cb0  mov     [rsp+1500h+var_14C0], eax
0x1800e4cb4  mov     [rsp+1500h+var_14A8], rsi
0x1800e4cb9  mov     [rsp+1500h+var_14A0], edi
0x1800e4cbd  mov     [rsp+1500h+var_149C], r15d
0x1800e4cc2  mov     [rsp+1500h+var_14B8], r12
0x1800e4cc7  mov     [rsp+1500h+var_14B0], r12
0x1800e4ccc  mov     [rbp+1400h+var_1458], r14
0x1800e4cd0  mov     [rbp+1400h+var_1450], rbx
0x1800e4cd4  mov     [rsp+1500h+var_1498], r12
0x1800e4cd9  xorps   xmm0, xmm0
0x1800e4cdc  xor     eax, eax
0x1800e4cde  movups  [rbp+1400h+var_1478], xmm0
0x1800e4ce2  mov     [rbp+1400h+var_1468], rax
0x1800e4ce6  xorps   xmm1, xmm1
0x1800e4ce9  movups  [rsp+1500h+var_1490], xmm1
0x1800e4cee  mov     [rbp+1400h+var_1480], rax
0x1800e4cf2  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800e4cf9  test    rax, rax
0x1800e4cfc  jz      short loc_1800E4D09
0x1800e4cfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e4d03  mov     [rbp+1400h+var_1460], rax
0x1800e4d07  jmp     short loc_1800E4D0D
0x1800e4d09  mov     [rbp+1400h+var_1460], r12
0x1800e4d0d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800e4d14  test    rax, rax
0x1800e4d17  jz      short loc_1800E4D23
0x1800e4d19  lea     rcx, [rsp+1500h+var_14E0]
0x1800e4d1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e4d23  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800e4d2a  test    rax, rax
0x1800e4d2d  jz      short loc_1800E4D43
0x1800e4d2f  mov     r8d, 400h
0x1800e4d35  lea     rdx, [rbp+1400h+var_1440]
0x1800e4d39  lea     rcx, [rsp+1500h+var_14E0]
0x1800e4d3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e4d43  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800e4d4a  test    rax, rax
0x1800e4d4d  jz      short loc_1800E4D59
0x1800e4d4f  lea     rcx, [rsp+1500h+var_14E0]
0x1800e4d54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e4d59  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800e4d60  test    rax, rax
0x1800e4d63  jz      short loc_1800E4D76
0x1800e4d65  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800e4d6a  jnz     short loc_1800E4D76
0x1800e4d6c  lea     rcx, [rsp+1500h+var_14E0]
0x1800e4d71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e4d76  cmp     [rsp+1500h+var_14D8], r12d
0x1800e4d7b  jge     loc_1800E4E84
0x1800e4d81  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800e4d88  jnz     short loc_1800E4DA9
0x1800e4d8a  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800e4d91  test    rax, rax
0x1800e4d94  jz      short loc_1800E4D9F
0x1800e4d96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e4d9b  test    al, al
0x1800e4d9d  jmp     short loc_1800E4DA7
0x1800e4d9f  call    cs:__imp_IsDebuggerPresent
0x1800e4da5  test    eax, eax
0x1800e4da7  jz      short loc_1800E4DB0
0x1800e4da9  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800e4dae  jz      short loc_1800E4DD6
0x1800e4db0  mov     rax, cs:g_pfnResultLoggingCallback
0x1800e4db7  test    rax, rax
0x1800e4dba  jz      short loc_1800E4E2F
0x1800e4dbc  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800e4dc3  jnz     short loc_1800E4E2F
0x1800e4dc5  xor     r8d, r8d
0x1800e4dc8  xor     edx, edx
0x1800e4dca  lea     rcx, [rsp+1500h+var_14E0]
0x1800e4dcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e4dd4  jmp     short loc_1800E4E2F
0x1800e4dd6  mov     ebx, 800h
0x1800e4ddb  mov     rax, cs:g_pfnResultLoggingCallback
0x1800e4de2  test    rax, rax
0x1800e4de5  jz      short loc_1800E4E04
0x1800e4de7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800e4dee  jnz     short loc_1800E4E04
0x1800e4df0  mov     r8d, ebx
0x1800e4df3  lea     rdx, [rbp+1400h+OutputString]
0x1800e4dfa  lea     rcx, [rsp+1500h+var_14E0]
0x1800e4dff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e4e04  cmp     [rbp+1400h+OutputString], r12w
0x1800e4e0c  jnz     short loc_1800E4E22
0x1800e4e0e  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1800e4e13  mov     rdx, rbx; unsigned __int16 *
0x1800e4e16  lea     rcx, [rbp+1400h+OutputString]; this
0x1800e4e1d  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800e4e22  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1800e4e29  call    cs:__imp_OutputDebugStringW
0x1800e4e2f  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1800e4e34  jnz     short loc_1800E4E3F
0x1800e4e36  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800e4e3d  jz      short loc_1800E4E51
0x1800e4e3f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800e4e46  test    rax, rax
0x1800e4e49  jz      short loc_1800E4E51
0x1800e4e4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e4e50  nop
0x1800e4e51  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1800e4e56  jnz     short loc_1800E4E79
0x1800e4e58  mov     rcx, [rbp+1400h+var_40]
0x1800e4e5f  xor     rcx, rsp; StackCookie
0x1800e4e62  call    __security_check_cookie
0x1800e4e67  add     rsp, 14D0h
0x1800e4e6e  pop     r15
0x1800e4e70  pop     r14
0x1800e4e72  pop     r12
0x1800e4e74  pop     rdi
0x1800e4e75  pop     rsi
0x1800e4e76  pop     rbx
0x1800e4e77  pop     rbp
0x1800e4e78  retn
0x1800e4e79  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800e4e7e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800e4e84  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
