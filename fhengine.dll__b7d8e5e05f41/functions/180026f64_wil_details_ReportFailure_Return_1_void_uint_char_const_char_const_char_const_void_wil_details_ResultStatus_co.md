# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180026f64`
- end: `0x1800271fa`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180026a6c`

## callees

- `0x180026f64`
- `0x18002a094`
- `0x18002bff0`
- `0x18002e070`
- `0x18002e22c`
- `0x180031642`
- `0x180031680`
- `0x180031740`
- `0x180034010`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x180027194`
- `KERNEL32!OutputDebugStringW` at `0x180027194`
- `KERNEL32!IsDebuggerPresent` at `0x18002710a`
- `KERNEL32!IsDebuggerPresent` at `0x18002710a`
- `KERNEL32!GetCurrentThreadId` at `0x18002700f`
- `KERNEL32!GetCurrentThreadId` at `0x18002700f`

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
  int v9; // ebx
  int v10; // ecx
  __int64 v11; // rdx
  const struct wil::FailureInfo *v12; // rdx
  wil::details::in1diag3 *v13; // rcx
  const struct wil::FailureInfo *v14; // r9
  bool v15; // zf
  int v16; // [rsp+20h] [rbp-E0h] BYREF
  int v17; // [rsp+24h] [rbp-DCh]
  int v18; // [rsp+28h] [rbp-D8h]
  int v19; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v20; // [rsp+30h] [rbp-D0h]
  __int64 v21; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v23; // [rsp+48h] [rbp-B8h]
  __int64 v24; // [rsp+50h] [rbp-B0h]
  const char *v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+60h] [rbp-A0h]
  int v27; // [rsp+64h] [rbp-9Ch]
  __int64 v28; // [rsp+68h] [rbp-98h]
  __int128 v29; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+80h] [rbp-80h]
  __int128 v31; // [rsp+88h] [rbp-78h]
  __int64 v32; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v34; // [rsp+A8h] [rbp-58h]
  __int64 v35; // [rsp+B0h] [rbp-50h]
  char v36[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v16, 0, 0x98u);
  OutputString[0] = 0;
  v36[0] = 0;
  v18 = *a7;
  v19 = a7[1];
  v9 = wil::details::RecordReturn((wil::details *)(unsigned int)v18, (int)a7);
  v16 = 1;
  v10 = 0;
  if ( *(_DWORD *)(v11 + 8) == 1 )
    v10 = 8;
  v17 = v10;
  v20 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v25 = "wil";
  v26 = a2;
  v27 = v9;
  v23 = 0;
  v24 = 0;
  v34 = a6;
  v35 = a1;
  v28 = 0;
  v31 = 0;
  v32 = 0;
  v29 = 0;
  v30 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v13);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v16, v36, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v16);
  if ( wil::details::g_pfnOriginateCallback && (v17 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v16);
  if ( v18 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v15 = !IsDebuggerPresent())
      : (v15 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v13) == 0),
        v15)
    || (v17 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v16, v14);
    OutputDebugStringW(OutputString);
  }
  if ( ((v17 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v13);
  if ( (v17 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v16, v12);
}

```

## disassembly

```asm
0x180026f64  mov     [rsp-8+arg_10], rbx
0x180026f69  push    rbp
0x180026f6a  push    rsi
0x180026f6b  push    rdi
0x180026f6c  push    r14
0x180026f6e  push    r15
0x180026f70  lea     rbp, [rsp-13D0h]
0x180026f78  mov     eax, 14D0h
0x180026f7d  call    _alloca_probe
0x180026f82  sub     rsp, rax
0x180026f85  mov     rax, cs:__security_cookie
0x180026f8c  xor     rax, rsp
0x180026f8f  mov     [rbp+13F0h+var_30], rax
0x180026f96  mov     esi, edx
0x180026f98  mov     r14, rcx
0x180026f9b  mov     rdi, [rbp+13F0h+arg_28]
0x180026fa2  xor     edx, edx; Val
0x180026fa4  mov     r8d, 98h; Size
0x180026faa  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180026faf  call    memset_0
0x180026fb4  nop
0x180026fb5  xor     r15d, r15d
0x180026fb8  mov     [rbp+13F0h+OutputString], r15w
0x180026fc0  mov     [rbp+13F0h+var_1430], r15b
0x180026fc4  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180026fcb  mov     ecx, [rdx]; this
0x180026fcd  mov     [rsp+14F0h+var_14C8], ecx
0x180026fd1  mov     eax, [rdx+4]
0x180026fd4  mov     [rsp+14F0h+var_14C4], eax
0x180026fd8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180026fdd  mov     ebx, eax
0x180026fdf  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180026fe7  mov     ecx, r15d
0x180026fea  lea     eax, [r15+8]
0x180026fee  cmp     dword ptr [rdx+8], 1
0x180026ff2  cmovz   ecx, eax
0x180026ff5  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180026ff9  lea     ecx, [rax-7]
0x180026ffc  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180027004  inc     ecx
0x180027006  mov     [rsp+14F0h+var_14C0], ecx
0x18002700a  mov     [rsp+14F0h+var_14B8], r15
0x18002700f  call    cs:__imp_GetCurrentThreadId
0x180027015  mov     [rsp+14F0h+var_14B0], eax
0x180027019  lea     rax, aWil; "wil"
0x180027020  mov     [rsp+14F0h+var_1498], rax
0x180027025  mov     [rsp+14F0h+var_1490], esi
0x180027029  mov     [rsp+14F0h+var_148C], ebx
0x18002702d  mov     [rsp+14F0h+var_14A8], r15
0x180027032  mov     [rsp+14F0h+var_14A0], r15
0x180027037  mov     [rbp+13F0h+var_1448], rdi
0x18002703b  mov     [rbp+13F0h+var_1440], r14
0x18002703f  mov     [rsp+14F0h+var_1488], r15
0x180027044  xorps   xmm0, xmm0
0x180027047  xor     eax, eax
0x180027049  movups  [rbp+13F0h+var_1468], xmm0
0x18002704d  mov     [rbp+13F0h+var_1458], rax
0x180027051  xorps   xmm1, xmm1
0x180027054  movups  [rsp+14F0h+var_1480], xmm1
0x180027059  mov     [rbp+13F0h+var_1470], rax
0x18002705d  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180027064  test    rax, rax
0x180027067  jz      short loc_180027074
0x180027069  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002706e  mov     [rbp+13F0h+var_1450], rax
0x180027072  jmp     short loc_180027078
0x180027074  mov     [rbp+13F0h+var_1450], r15
0x180027078  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18002707f  test    rax, rax
0x180027082  jz      short loc_18002708E
0x180027084  lea     rcx, [rsp+14F0h+var_14D0]
0x180027089  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002708e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180027095  test    rax, rax
0x180027098  jz      short loc_1800270AE
0x18002709a  mov     r8d, 400h
0x1800270a0  lea     rdx, [rbp+13F0h+var_1430]
0x1800270a4  lea     rcx, [rsp+14F0h+var_14D0]
0x1800270a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800270ae  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800270b5  test    rax, rax
0x1800270b8  jz      short loc_1800270C4
0x1800270ba  lea     rcx, [rsp+14F0h+var_14D0]
0x1800270bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800270c4  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800270cb  test    rax, rax
0x1800270ce  jz      short loc_1800270E1
0x1800270d0  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800270d5  jnz     short loc_1800270E1
0x1800270d7  lea     rcx, [rsp+14F0h+var_14D0]
0x1800270dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800270e1  cmp     [rsp+14F0h+var_14C8], r15d
0x1800270e6  jge     loc_1800271F4
0x1800270ec  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x1800270f3  jnz     short loc_180027114
0x1800270f5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800270fc  test    rax, rax
0x1800270ff  jz      short loc_18002710A
0x180027101  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027106  test    al, al
0x180027108  jmp     short loc_180027112
0x18002710a  call    cs:__imp_IsDebuggerPresent
0x180027110  test    eax, eax
0x180027112  jz      short loc_18002711B
0x180027114  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180027119  jz      short loc_180027141
0x18002711b  mov     rax, cs:g_pfnResultLoggingCallback
0x180027122  test    rax, rax
0x180027125  jz      short loc_18002719A
0x180027127  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18002712e  jnz     short loc_18002719A
0x180027130  xor     r8d, r8d
0x180027133  xor     edx, edx
0x180027135  lea     rcx, [rsp+14F0h+var_14D0]
0x18002713a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002713f  jmp     short loc_18002719A
0x180027141  mov     ebx, 800h
0x180027146  mov     rax, cs:g_pfnResultLoggingCallback
0x18002714d  test    rax, rax
0x180027150  jz      short loc_18002716F
0x180027152  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180027159  jnz     short loc_18002716F
0x18002715b  mov     r8d, ebx
0x18002715e  lea     rdx, [rbp+13F0h+OutputString]
0x180027165  lea     rcx, [rsp+14F0h+var_14D0]
0x18002716a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002716f  cmp     [rbp+13F0h+OutputString], r15w
0x180027177  jnz     short loc_18002718D
0x180027179  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18002717e  mov     rdx, rbx; unsigned __int16 *
0x180027181  lea     rcx, [rbp+13F0h+OutputString]; this
0x180027188  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18002718d  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180027194  call    cs:__imp_OutputDebugStringW
0x18002719a  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18002719f  jnz     short loc_1800271AA
0x1800271a1  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x1800271a8  jz      short loc_1800271BC
0x1800271aa  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800271b1  test    rax, rax
0x1800271b4  jz      short loc_1800271BC
0x1800271b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800271bb  nop
0x1800271bc  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x1800271c1  jnz     short loc_1800271E9
0x1800271c3  mov     rcx, [rbp+13F0h+var_30]
0x1800271ca  xor     rcx, rsp; StackCookie
0x1800271cd  call    __security_check_cookie
0x1800271d2  mov     rbx, [rsp+14F0h+arg_10]
0x1800271da  add     rsp, 14D0h
0x1800271e1  pop     r15
0x1800271e3  pop     r14
0x1800271e5  pop     rdi
0x1800271e6  pop     rsi
0x1800271e7  pop     rbp
0x1800271e8  retn
0x1800271e9  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800271ee  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800271f4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
