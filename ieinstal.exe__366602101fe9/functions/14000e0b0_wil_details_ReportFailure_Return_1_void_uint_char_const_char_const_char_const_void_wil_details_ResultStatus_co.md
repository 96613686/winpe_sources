# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x14000e0b0`
- end: `0x14000e357`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `679`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x14000db80`

## callees

- `0x140001af3`
- `0x14000e0b0`
- `0x14000eb2c`
- `0x14000fbfc`
- `0x1400103d0`
- `0x1400104ac`
- `0x1400109c0`
- `0x140010a80`
- `0x140011010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14000e15a`
- `KERNEL32!GetCurrentThreadId` at `0x14000e15a`
- `KERNEL32!IsDebuggerPresent` at `0x14000e25b`
- `KERNEL32!IsDebuggerPresent` at `0x14000e25b`
- `KERNEL32!OutputDebugStringW` at `0x14000e2eb`
- `KERNEL32!OutputDebugStringW` at `0x14000e2eb`

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
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdx
  int v12; // ebx
  int v13; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v15; // rdx
  wil::details::in1diag3 *v16; // rcx
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
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v19, 0, 0x98u);
  OutputString[0] = 0;
  v39[0] = 0;
  v9 = a7[1];
  v21 = *a7;
  v22 = v9;
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v21, (int)a7);
  v18 = *(_DWORD *)(v11 + 8) == 1;
  v12 = v10;
  v19 = 1;
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
  v28 = "wil";
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
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v16);
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
  if ( ((v20 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v16);
  if ( (v20 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v19, v15);
}

```

## disassembly

```asm
0x14000e0b0  mov     [rsp-8+arg_10], rbx
0x14000e0b5  push    rbp
0x14000e0b6  push    rsi
0x14000e0b7  push    rdi
0x14000e0b8  push    r14
0x14000e0ba  push    r15
0x14000e0bc  lea     rbp, [rsp-13D0h]
0x14000e0c4  mov     eax, 14D0h
0x14000e0c9  call    _alloca_probe
0x14000e0ce  sub     rsp, rax
0x14000e0d1  mov     rax, cs:__security_cookie
0x14000e0d8  xor     rax, rsp
0x14000e0db  mov     [rbp+13F0h+var_30], rax
0x14000e0e2  mov     rdi, [rbp+13F0h+arg_28]
0x14000e0e9  mov     esi, edx
0x14000e0eb  mov     r14, rcx
0x14000e0ee  xor     edx, edx; Val
0x14000e0f0  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x14000e0f5  mov     r8d, 98h; Size
0x14000e0fb  call    memset_0
0x14000e100  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x14000e107  xor     r15d, r15d
0x14000e10a  mov     [rbp+13F0h+OutputString], r15w
0x14000e112  mov     [rbp+13F0h+var_1430], r15b
0x14000e116  mov     ecx, [rdx]; this
0x14000e118  mov     eax, [rdx+4]
0x14000e11b  mov     [rsp+14F0h+var_14C8], ecx
0x14000e11f  mov     [rsp+14F0h+var_14C4], eax
0x14000e123  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x14000e128  cmp     dword ptr [rdx+8], 1
0x14000e12c  mov     ebx, eax
0x14000e12e  lea     eax, [r15+8]
0x14000e132  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x14000e13a  mov     ecx, r15d
0x14000e13d  cmovz   ecx, eax
0x14000e140  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x14000e144  lea     ecx, [rax-7]
0x14000e147  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000e14f  inc     ecx
0x14000e151  mov     [rsp+14F0h+var_14B8], r15
0x14000e156  mov     [rsp+14F0h+var_14C0], ecx
0x14000e15a  call    cs:__imp_GetCurrentThreadId
0x14000e161  nop     dword ptr [rax+rax+00h]
0x14000e166  xorps   xmm0, xmm0
0x14000e169  mov     [rsp+14F0h+var_1490], esi
0x14000e16d  mov     [rsp+14F0h+var_14B0], eax
0x14000e171  xorps   xmm1, xmm1
0x14000e174  lea     rax, aWil; "wil"
0x14000e17b  mov     [rsp+14F0h+var_148C], ebx
0x14000e17f  mov     [rsp+14F0h+var_1498], rax
0x14000e184  xor     eax, eax
0x14000e186  mov     [rbp+13F0h+var_1458], rax
0x14000e18a  mov     [rbp+13F0h+var_1470], rax
0x14000e18e  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000e195  mov     [rsp+14F0h+var_14A8], r15
0x14000e19a  mov     [rsp+14F0h+var_14A0], r15
0x14000e19f  mov     [rbp+13F0h+var_1448], rdi
0x14000e1a3  mov     [rbp+13F0h+var_1440], r14
0x14000e1a7  mov     [rsp+14F0h+var_1488], r15
0x14000e1ac  movups  [rbp+13F0h+var_1468], xmm0
0x14000e1b0  movups  [rsp+14F0h+var_1480], xmm1
0x14000e1b5  test    rax, rax
0x14000e1b8  jz      short loc_14000E1C5
0x14000e1ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e1bf  mov     [rbp+13F0h+var_1450], rax
0x14000e1c3  jmp     short loc_14000E1C9
0x14000e1c5  mov     [rbp+13F0h+var_1450], r15
0x14000e1c9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14000e1d0  test    rax, rax
0x14000e1d3  jz      short loc_14000E1DF
0x14000e1d5  lea     rcx, [rsp+14F0h+var_14D0]
0x14000e1da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e1df  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000e1e6  test    rax, rax
0x14000e1e9  jz      short loc_14000E1FF
0x14000e1eb  mov     r8d, 400h
0x14000e1f1  lea     rdx, [rbp+13F0h+var_1430]
0x14000e1f5  lea     rcx, [rsp+14F0h+var_14D0]
0x14000e1fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e1ff  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000e206  test    rax, rax
0x14000e209  jz      short loc_14000E215
0x14000e20b  lea     rcx, [rsp+14F0h+var_14D0]
0x14000e210  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e215  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000e21c  test    rax, rax
0x14000e21f  jz      short loc_14000E232
0x14000e221  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x14000e226  jnz     short loc_14000E232
0x14000e228  lea     rcx, [rsp+14F0h+var_14D0]
0x14000e22d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e232  cmp     [rsp+14F0h+var_14C8], r15d
0x14000e237  jge     loc_14000E346
0x14000e23d  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x14000e244  jnz     short loc_14000E26B
0x14000e246  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14000e24d  test    rax, rax
0x14000e250  jz      short loc_14000E25B
0x14000e252  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e257  test    al, al
0x14000e259  jmp     short loc_14000E269
0x14000e25b  call    cs:__imp_IsDebuggerPresent
0x14000e262  nop     dword ptr [rax+rax+00h]
0x14000e267  test    eax, eax
0x14000e269  jz      short loc_14000E272
0x14000e26b  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x14000e270  jz      short loc_14000E298
0x14000e272  mov     rax, cs:g_pfnResultLoggingCallback
0x14000e279  test    rax, rax
0x14000e27c  jz      short loc_14000E2F7
0x14000e27e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14000e285  jnz     short loc_14000E2F7
0x14000e287  xor     r8d, r8d
0x14000e28a  lea     rcx, [rsp+14F0h+var_14D0]
0x14000e28f  xor     edx, edx
0x14000e291  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e296  jmp     short loc_14000E2F7
0x14000e298  mov     rax, cs:g_pfnResultLoggingCallback
0x14000e29f  mov     ebx, 800h
0x14000e2a4  test    rax, rax
0x14000e2a7  jz      short loc_14000E2C6
0x14000e2a9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14000e2b0  jnz     short loc_14000E2C6
0x14000e2b2  mov     r8d, ebx
0x14000e2b5  lea     rdx, [rbp+13F0h+OutputString]
0x14000e2bc  lea     rcx, [rsp+14F0h+var_14D0]
0x14000e2c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e2c6  cmp     [rbp+13F0h+OutputString], r15w
0x14000e2ce  jnz     short loc_14000E2E4
0x14000e2d0  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x14000e2d5  mov     rdx, rbx; unsigned __int16 *
0x14000e2d8  lea     rcx, [rbp+13F0h+OutputString]; this
0x14000e2df  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14000e2e4  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x14000e2eb  call    cs:__imp_OutputDebugStringW
0x14000e2f2  nop     dword ptr [rax+rax+00h]
0x14000e2f7  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x14000e2fc  jnz     short loc_14000E307
0x14000e2fe  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x14000e305  jz      short loc_14000E318
0x14000e307  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14000e30e  test    rax, rax
0x14000e311  jz      short loc_14000E318
0x14000e313  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e318  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x14000e31d  jnz     short loc_14000E34C
0x14000e31f  mov     rcx, [rbp+13F0h+var_30]
0x14000e326  xor     rcx, rsp; StackCookie
0x14000e329  call    __security_check_cookie
0x14000e32e  mov     rbx, [rsp+14F0h+arg_10]
0x14000e336  add     rsp, 14D0h
0x14000e33d  pop     r15
0x14000e33f  pop     r14
0x14000e341  pop     rdi
0x14000e342  pop     rsi
0x14000e343  pop     rbp
0x14000e344  retn
0x14000e346  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14000e34c  lea     rcx, [rsp+14F0h+var_14D0]; this
0x14000e351  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
