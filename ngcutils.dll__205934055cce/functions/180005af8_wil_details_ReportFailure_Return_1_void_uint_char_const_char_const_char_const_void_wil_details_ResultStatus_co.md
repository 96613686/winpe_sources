# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180005af8`
- end: `0x180005d9e`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180005584`

## callees

- `0x180003080`
- `0x180003bc8`
- `0x180005af8`
- `0x180008064`
- `0x180009668`
- `0x18000bc50`
- `0x18000be1c`
- `0x180057f50`
- `0x180061010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005bbe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005bbe`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005cb3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005cb3`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005d3d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005d3d`

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
0x180005af8  push    rbp
0x180005afa  push    rbx
0x180005afb  push    rsi
0x180005afc  push    rdi
0x180005afd  push    r12
0x180005aff  push    r14
0x180005b01  push    r15
0x180005b03  lea     rbp, [rsp-13D0h]
0x180005b0b  mov     eax, 14D0h
0x180005b10  call    _alloca_probe
0x180005b15  sub     rsp, rax
0x180005b18  mov     rax, cs:__security_cookie
0x180005b1f  xor     rax, rsp
0x180005b22  mov     [rbp+1400h+var_40], rax
0x180005b29  mov     rsi, r8
0x180005b2c  mov     edi, edx
0x180005b2e  mov     rbx, rcx
0x180005b31  mov     r14, [rbp+1400h+arg_28]
0x180005b38  xor     edx, edx; Val
0x180005b3a  mov     r8d, 98h; Size
0x180005b40  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180005b45  call    memset_0
0x180005b4a  nop
0x180005b4b  xor     r12d, r12d
0x180005b4e  mov     [rbp+1400h+OutputString], r12w
0x180005b56  mov     [rbp+1400h+var_1440], r12b
0x180005b5a  mov     rdx, [rbp+1400h+arg_30]; int
0x180005b61  mov     ecx, [rdx]; this
0x180005b63  mov     [rsp+1500h+var_14D8], ecx
0x180005b67  mov     eax, [rdx+4]
0x180005b6a  mov     [rsp+1500h+var_14D4], eax
0x180005b6e  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005b73  mov     r15d, eax
0x180005b76  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180005b7e  mov     ecx, r12d
0x180005b81  lea     eax, [r12+8]
0x180005b86  cmp     dword ptr [rdx+8], 1
0x180005b8a  cmovz   ecx, eax
0x180005b8d  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180005b91  lea     ecx, [rax-7]
0x180005b94  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005b9c  inc     ecx
0x180005b9e  mov     [rsp+1500h+var_14D0], ecx
0x180005ba2  mov     rcx, [rbp+1400h+arg_38]
0x180005ba9  test    rcx, rcx
0x180005bac  jz      short loc_180005BB9
0x180005bae  cmp     [rcx], r12w
0x180005bb2  mov     [rsp+1500h+var_14C8], rcx
0x180005bb7  jnz     short loc_180005BBE
0x180005bb9  mov     [rsp+1500h+var_14C8], r12
0x180005bbe  call    cs:__imp_GetCurrentThreadId
0x180005bc4  mov     [rsp+1500h+var_14C0], eax
0x180005bc8  mov     [rsp+1500h+var_14A8], rsi
0x180005bcd  mov     [rsp+1500h+var_14A0], edi
0x180005bd1  mov     [rsp+1500h+var_149C], r15d
0x180005bd6  mov     [rsp+1500h+var_14B8], r12
0x180005bdb  mov     [rsp+1500h+var_14B0], r12
0x180005be0  mov     [rbp+1400h+var_1458], r14
0x180005be4  mov     [rbp+1400h+var_1450], rbx
0x180005be8  mov     [rsp+1500h+var_1498], r12
0x180005bed  xorps   xmm0, xmm0
0x180005bf0  xor     eax, eax
0x180005bf2  movups  [rbp+1400h+var_1478], xmm0
0x180005bf6  mov     [rbp+1400h+var_1468], rax
0x180005bfa  xorps   xmm1, xmm1
0x180005bfd  movups  [rsp+1500h+var_1490], xmm1
0x180005c02  mov     [rbp+1400h+var_1480], rax
0x180005c06  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005c0d  test    rax, rax
0x180005c10  jz      short loc_180005C1D
0x180005c12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c17  mov     [rbp+1400h+var_1460], rax
0x180005c1b  jmp     short loc_180005C21
0x180005c1d  mov     [rbp+1400h+var_1460], r12
0x180005c21  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005c28  test    rax, rax
0x180005c2b  jz      short loc_180005C37
0x180005c2d  lea     rcx, [rsp+1500h+var_14E0]
0x180005c32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c37  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005c3e  test    rax, rax
0x180005c41  jz      short loc_180005C57
0x180005c43  mov     r8d, 400h
0x180005c49  lea     rdx, [rbp+1400h+var_1440]
0x180005c4d  lea     rcx, [rsp+1500h+var_14E0]
0x180005c52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c57  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005c5e  test    rax, rax
0x180005c61  jz      short loc_180005C6D
0x180005c63  lea     rcx, [rsp+1500h+var_14E0]
0x180005c68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c6d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005c74  test    rax, rax
0x180005c77  jz      short loc_180005C8A
0x180005c79  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180005c7e  jnz     short loc_180005C8A
0x180005c80  lea     rcx, [rsp+1500h+var_14E0]
0x180005c85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c8a  cmp     [rsp+1500h+var_14D8], r12d
0x180005c8f  jge     loc_180005D98
0x180005c95  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180005c9c  jnz     short loc_180005CBD
0x180005c9e  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005ca5  test    rax, rax
0x180005ca8  jz      short loc_180005CB3
0x180005caa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005caf  test    al, al
0x180005cb1  jmp     short loc_180005CBB
0x180005cb3  call    cs:__imp_IsDebuggerPresent
0x180005cb9  test    eax, eax
0x180005cbb  jz      short loc_180005CC4
0x180005cbd  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180005cc2  jz      short loc_180005CEA
0x180005cc4  mov     rax, cs:g_pfnResultLoggingCallback
0x180005ccb  test    rax, rax
0x180005cce  jz      short loc_180005D43
0x180005cd0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180005cd7  jnz     short loc_180005D43
0x180005cd9  xor     r8d, r8d
0x180005cdc  xor     edx, edx
0x180005cde  lea     rcx, [rsp+1500h+var_14E0]
0x180005ce3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ce8  jmp     short loc_180005D43
0x180005cea  mov     ebx, 800h
0x180005cef  mov     rax, cs:g_pfnResultLoggingCallback
0x180005cf6  test    rax, rax
0x180005cf9  jz      short loc_180005D18
0x180005cfb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180005d02  jnz     short loc_180005D18
0x180005d04  mov     r8d, ebx
0x180005d07  lea     rdx, [rbp+1400h+OutputString]
0x180005d0e  lea     rcx, [rsp+1500h+var_14E0]
0x180005d13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d18  cmp     [rbp+1400h+OutputString], r12w
0x180005d20  jnz     short loc_180005D36
0x180005d22  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180005d27  mov     rdx, rbx; unsigned __int16 *
0x180005d2a  lea     rcx, [rbp+1400h+OutputString]; this
0x180005d31  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005d36  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180005d3d  call    cs:__imp_OutputDebugStringW
0x180005d43  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180005d48  jnz     short loc_180005D53
0x180005d4a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180005d51  jz      short loc_180005D65
0x180005d53  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005d5a  test    rax, rax
0x180005d5d  jz      short loc_180005D65
0x180005d5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d64  nop
0x180005d65  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180005d6a  jnz     short loc_180005D8D
0x180005d6c  mov     rcx, [rbp+1400h+var_40]
0x180005d73  xor     rcx, rsp; StackCookie
0x180005d76  call    __security_check_cookie
0x180005d7b  add     rsp, 14D0h
0x180005d82  pop     r15
0x180005d84  pop     r14
0x180005d86  pop     r12
0x180005d88  pop     rdi
0x180005d89  pop     rsi
0x180005d8a  pop     rbx
0x180005d8b  pop     rbp
0x180005d8c  retn
0x180005d8d  lea     rcx, [rsp+1500h+var_14E0]; this
0x180005d92  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180005d98  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
