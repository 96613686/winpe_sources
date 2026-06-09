# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180002c14`
- end: `0x180002eaa`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800028dc`

## callees

- `0x180002c14`
- `0x180004774`
- `0x180006674`
- `0x180007f68`
- `0x18000815c`
- `0x18002737e`
- `0x1800273b0`
- `0x180027470`
- `0x180029010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180002cbf`
- `KERNEL32!GetCurrentThreadId` at `0x180002cbf`
- `KERNEL32!IsDebuggerPresent` at `0x180002dba`
- `KERNEL32!IsDebuggerPresent` at `0x180002dba`
- `KERNEL32!OutputDebugStringW` at `0x180002e44`
- `KERNEL32!OutputDebugStringW` at `0x180002e44`

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
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v16, v14);
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
0x180002c14  mov     [rsp-8+arg_10], rbx
0x180002c19  push    rbp
0x180002c1a  push    rsi
0x180002c1b  push    rdi
0x180002c1c  push    r14
0x180002c1e  push    r15
0x180002c20  lea     rbp, [rsp-13D0h]
0x180002c28  mov     eax, 14D0h
0x180002c2d  call    _alloca_probe
0x180002c32  sub     rsp, rax
0x180002c35  mov     rax, cs:__security_cookie
0x180002c3c  xor     rax, rsp
0x180002c3f  mov     [rbp+13F0h+var_30], rax
0x180002c46  mov     esi, edx
0x180002c48  mov     r14, rcx
0x180002c4b  mov     rdi, [rbp+13F0h+arg_28]
0x180002c52  xor     edx, edx; Val
0x180002c54  mov     r8d, 98h; Size
0x180002c5a  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180002c5f  call    memset_0
0x180002c64  nop
0x180002c65  xor     r15d, r15d
0x180002c68  mov     [rbp+13F0h+OutputString], r15w
0x180002c70  mov     [rbp+13F0h+var_1430], r15b
0x180002c74  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180002c7b  mov     ecx, [rdx]; this
0x180002c7d  mov     [rsp+14F0h+var_14C8], ecx
0x180002c81  mov     eax, [rdx+4]
0x180002c84  mov     [rsp+14F0h+var_14C4], eax
0x180002c88  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180002c8d  mov     ebx, eax
0x180002c8f  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180002c97  mov     ecx, r15d
0x180002c9a  lea     eax, [r15+8]
0x180002c9e  cmp     dword ptr [rdx+8], 1
0x180002ca2  cmovz   ecx, eax
0x180002ca5  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180002ca9  lea     ecx, [rax-7]
0x180002cac  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002cb4  inc     ecx
0x180002cb6  mov     [rsp+14F0h+var_14C0], ecx
0x180002cba  mov     [rsp+14F0h+var_14B8], r15
0x180002cbf  call    cs:__imp_GetCurrentThreadId
0x180002cc5  mov     [rsp+14F0h+var_14B0], eax
0x180002cc9  lea     rax, aWil; "wil"
0x180002cd0  mov     [rsp+14F0h+var_1498], rax
0x180002cd5  mov     [rsp+14F0h+var_1490], esi
0x180002cd9  mov     [rsp+14F0h+var_148C], ebx
0x180002cdd  mov     [rsp+14F0h+var_14A8], r15
0x180002ce2  mov     [rsp+14F0h+var_14A0], r15
0x180002ce7  mov     [rbp+13F0h+var_1448], rdi
0x180002ceb  mov     [rbp+13F0h+var_1440], r14
0x180002cef  mov     [rsp+14F0h+var_1488], r15
0x180002cf4  xorps   xmm0, xmm0
0x180002cf7  xor     eax, eax
0x180002cf9  movups  [rbp+13F0h+var_1468], xmm0
0x180002cfd  mov     [rbp+13F0h+var_1458], rax
0x180002d01  xorps   xmm1, xmm1
0x180002d04  movups  [rsp+14F0h+var_1480], xmm1
0x180002d09  mov     [rbp+13F0h+var_1470], rax
0x180002d0d  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002d14  test    rax, rax
0x180002d17  jz      short loc_180002D24
0x180002d19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d1e  mov     [rbp+13F0h+var_1450], rax
0x180002d22  jmp     short loc_180002D28
0x180002d24  mov     [rbp+13F0h+var_1450], r15
0x180002d28  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002d2f  test    rax, rax
0x180002d32  jz      short loc_180002D3E
0x180002d34  lea     rcx, [rsp+14F0h+var_14D0]
0x180002d39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d3e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002d45  test    rax, rax
0x180002d48  jz      short loc_180002D5E
0x180002d4a  mov     r8d, 400h
0x180002d50  lea     rdx, [rbp+13F0h+var_1430]
0x180002d54  lea     rcx, [rsp+14F0h+var_14D0]
0x180002d59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d5e  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002d65  test    rax, rax
0x180002d68  jz      short loc_180002D74
0x180002d6a  lea     rcx, [rsp+14F0h+var_14D0]
0x180002d6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d74  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002d7b  test    rax, rax
0x180002d7e  jz      short loc_180002D91
0x180002d80  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002d85  jnz     short loc_180002D91
0x180002d87  lea     rcx, [rsp+14F0h+var_14D0]
0x180002d8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d91  cmp     [rsp+14F0h+var_14C8], r15d
0x180002d96  jge     loc_180002EA4
0x180002d9c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180002da3  jnz     short loc_180002DC4
0x180002da5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002dac  test    rax, rax
0x180002daf  jz      short loc_180002DBA
0x180002db1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002db6  test    al, al
0x180002db8  jmp     short loc_180002DC2
0x180002dba  call    cs:__imp_IsDebuggerPresent
0x180002dc0  test    eax, eax
0x180002dc2  jz      short loc_180002DCB
0x180002dc4  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002dc9  jz      short loc_180002DF1
0x180002dcb  mov     rax, cs:g_pfnResultLoggingCallback
0x180002dd2  test    rax, rax
0x180002dd5  jz      short loc_180002E4A
0x180002dd7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180002dde  jnz     short loc_180002E4A
0x180002de0  xor     r8d, r8d
0x180002de3  xor     edx, edx
0x180002de5  lea     rcx, [rsp+14F0h+var_14D0]
0x180002dea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002def  jmp     short loc_180002E4A
0x180002df1  mov     ebx, 800h
0x180002df6  mov     rax, cs:g_pfnResultLoggingCallback
0x180002dfd  test    rax, rax
0x180002e00  jz      short loc_180002E1F
0x180002e02  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180002e09  jnz     short loc_180002E1F
0x180002e0b  mov     r8d, ebx
0x180002e0e  lea     rdx, [rbp+13F0h+OutputString]
0x180002e15  lea     rcx, [rsp+14F0h+var_14D0]
0x180002e1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e1f  cmp     [rbp+13F0h+OutputString], r15w
0x180002e27  jnz     short loc_180002E3D
0x180002e29  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180002e2e  mov     rdx, rbx; wchar_t *
0x180002e31  lea     rcx, [rbp+13F0h+OutputString]; this
0x180002e38  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180002e3d  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180002e44  call    cs:__imp_OutputDebugStringW
0x180002e4a  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180002e4f  jnz     short loc_180002E5A
0x180002e51  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180002e58  jz      short loc_180002E6C
0x180002e5a  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002e61  test    rax, rax
0x180002e64  jz      short loc_180002E6C
0x180002e66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e6b  nop
0x180002e6c  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180002e71  jnz     short loc_180002E99
0x180002e73  mov     rcx, [rbp+13F0h+var_30]
0x180002e7a  xor     rcx, rsp; StackCookie
0x180002e7d  call    __security_check_cookie
0x180002e82  mov     rbx, [rsp+14F0h+arg_10]
0x180002e8a  add     rsp, 14D0h
0x180002e91  pop     r15
0x180002e93  pop     r14
0x180002e95  pop     rdi
0x180002e96  pop     rsi
0x180002e97  pop     rbp
0x180002e98  retn
0x180002e99  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180002e9e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180002ea4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
