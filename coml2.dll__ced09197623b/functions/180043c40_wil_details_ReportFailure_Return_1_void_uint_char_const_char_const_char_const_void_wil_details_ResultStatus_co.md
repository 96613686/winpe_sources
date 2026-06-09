# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180043c40`
- end: `0x180043ecb`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `651`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800439c8`

## callees

- `0x180042800`
- `0x180043100`
- `0x180043c40`
- `0x180044ee4`
- `0x1800464ac`
- `0x180047768`
- `0x180047974`
- `0x1800613b0`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180043de1`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180043de1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180043e6b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180043e6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180043ced`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180043ced`

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
0x180043c40  push    rbp
0x180043c42  push    rbx
0x180043c43  push    rsi
0x180043c44  push    rdi
0x180043c45  push    r12
0x180043c47  push    r14
0x180043c49  push    r15
0x180043c4b  lea     rbp, [rsp-13D0h]
0x180043c53  mov     eax, 14D0h
0x180043c58  call    _alloca_probe
0x180043c5d  sub     rsp, rax
0x180043c60  mov     rax, cs:__security_cookie
0x180043c67  xor     rax, rsp
0x180043c6a  mov     [rbp+1400h+var_40], rax
0x180043c71  mov     rdi, [rbp+1400h+arg_28]
0x180043c78  mov     r14, r8
0x180043c7b  mov     esi, edx
0x180043c7d  mov     r15, rcx
0x180043c80  xor     edx, edx; Val
0x180043c82  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180043c87  mov     r8d, 98h; Size
0x180043c8d  call    memset_0
0x180043c92  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180043c99  xor     r12d, r12d
0x180043c9c  mov     [rbp+1400h+OutputString], r12w
0x180043ca4  mov     [rbp+1400h+var_1440], r12b
0x180043ca8  mov     ecx, [rdx]; this
0x180043caa  mov     eax, [rdx+4]
0x180043cad  mov     [rsp+1500h+var_14D8], ecx
0x180043cb1  mov     [rsp+1500h+var_14D4], eax
0x180043cb5  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180043cba  cmp     dword ptr [rdx+8], 1
0x180043cbe  mov     ebx, eax
0x180043cc0  lea     eax, [r12+8]
0x180043cc5  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180043ccd  mov     ecx, r12d
0x180043cd0  cmovz   ecx, eax
0x180043cd3  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180043cd7  lea     ecx, [rax-7]
0x180043cda  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180043ce2  inc     ecx
0x180043ce4  mov     [rsp+1500h+var_14C8], r12
0x180043ce9  mov     [rsp+1500h+var_14D0], ecx
0x180043ced  call    cs:__imp_GetCurrentThreadId
0x180043cf3  xorps   xmm0, xmm0
0x180043cf6  mov     [rsp+1500h+var_14A8], r14
0x180043cfb  mov     [rsp+1500h+var_14C0], eax
0x180043cff  xorps   xmm1, xmm1
0x180043d02  xor     eax, eax
0x180043d04  mov     [rsp+1500h+var_14A0], esi
0x180043d08  mov     [rbp+1400h+var_1468], rax
0x180043d0c  mov     [rbp+1400h+var_1480], rax
0x180043d10  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180043d17  mov     [rsp+1500h+var_149C], ebx
0x180043d1b  mov     [rsp+1500h+var_14B8], r12
0x180043d20  mov     [rsp+1500h+var_14B0], r12
0x180043d25  mov     [rbp+1400h+var_1458], rdi
0x180043d29  mov     [rbp+1400h+var_1450], r15
0x180043d2d  mov     [rsp+1500h+var_1498], r12
0x180043d32  movups  [rbp+1400h+var_1478], xmm0
0x180043d36  movups  [rsp+1500h+var_1490], xmm1
0x180043d3b  test    rax, rax
0x180043d3e  jz      short loc_180043D4B
0x180043d40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043d45  mov     [rbp+1400h+var_1460], rax
0x180043d49  jmp     short loc_180043D4F
0x180043d4b  mov     [rbp+1400h+var_1460], r12
0x180043d4f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180043d56  test    rax, rax
0x180043d59  jz      short loc_180043D65
0x180043d5b  lea     rcx, [rsp+1500h+var_14E0]
0x180043d60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043d65  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180043d6c  test    rax, rax
0x180043d6f  jz      short loc_180043D85
0x180043d71  mov     r8d, 400h
0x180043d77  lea     rdx, [rbp+1400h+var_1440]
0x180043d7b  lea     rcx, [rsp+1500h+var_14E0]
0x180043d80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043d85  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180043d8c  test    rax, rax
0x180043d8f  jz      short loc_180043D9B
0x180043d91  lea     rcx, [rsp+1500h+var_14E0]
0x180043d96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043d9b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180043da2  test    rax, rax
0x180043da5  jz      short loc_180043DB8
0x180043da7  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180043dac  jnz     short loc_180043DB8
0x180043dae  lea     rcx, [rsp+1500h+var_14E0]
0x180043db3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043db8  cmp     [rsp+1500h+var_14D8], r12d
0x180043dbd  jge     loc_180043EBA
0x180043dc3  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180043dca  jnz     short loc_180043DEB
0x180043dcc  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180043dd3  test    rax, rax
0x180043dd6  jz      short loc_180043DE1
0x180043dd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043ddd  test    al, al
0x180043ddf  jmp     short loc_180043DE9
0x180043de1  call    cs:__imp_IsDebuggerPresent
0x180043de7  test    eax, eax
0x180043de9  jz      short loc_180043DF2
0x180043deb  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180043df0  jz      short loc_180043E18
0x180043df2  mov     rax, cs:g_pfnResultLoggingCallback
0x180043df9  test    rax, rax
0x180043dfc  jz      short loc_180043E71
0x180043dfe  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180043e05  jnz     short loc_180043E71
0x180043e07  xor     r8d, r8d
0x180043e0a  lea     rcx, [rsp+1500h+var_14E0]
0x180043e0f  xor     edx, edx
0x180043e11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043e16  jmp     short loc_180043E71
0x180043e18  mov     rax, cs:g_pfnResultLoggingCallback
0x180043e1f  mov     ebx, 800h
0x180043e24  test    rax, rax
0x180043e27  jz      short loc_180043E46
0x180043e29  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180043e30  jnz     short loc_180043E46
0x180043e32  mov     r8d, ebx
0x180043e35  lea     rdx, [rbp+1400h+OutputString]
0x180043e3c  lea     rcx, [rsp+1500h+var_14E0]
0x180043e41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043e46  cmp     [rbp+1400h+OutputString], r12w
0x180043e4e  jnz     short loc_180043E64
0x180043e50  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180043e55  mov     rdx, rbx; unsigned __int16 *
0x180043e58  lea     rcx, [rbp+1400h+OutputString]; this
0x180043e5f  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180043e64  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180043e6b  call    cs:__imp_OutputDebugStringW
0x180043e71  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180043e76  jnz     short loc_180043E81
0x180043e78  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180043e7f  jz      short loc_180043E92
0x180043e81  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180043e88  test    rax, rax
0x180043e8b  jz      short loc_180043E92
0x180043e8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043e92  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180043e97  jnz     short loc_180043EC0
0x180043e99  mov     rcx, [rbp+1400h+var_40]
0x180043ea0  xor     rcx, rsp; StackCookie
0x180043ea3  call    __security_check_cookie
0x180043ea8  add     rsp, 14D0h
0x180043eaf  pop     r15
0x180043eb1  pop     r14
0x180043eb3  pop     r12
0x180043eb5  pop     rdi
0x180043eb6  pop     rsi
0x180043eb7  pop     rbx
0x180043eb8  pop     rbp
0x180043eb9  retn
0x180043eba  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180043ec0  lea     rcx, [rsp+1500h+var_14E0]; this
0x180043ec5  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
