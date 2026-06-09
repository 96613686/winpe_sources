# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180009be0`
- end: `0x180009eb3`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `723`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180009670`

## callees

- `0x1800017b0`
- `0x180009be0`
- `0x18000eb60`
- `0x1800133e0`
- `0x1800186c0`
- `0x1800187e0`
- `0x180088690`
- `0x180088750`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009cac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009cac`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180009db3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180009db3`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009e45`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009e45`

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
        unsigned __int64 *a7)
{
  unsigned int v9; // ebx
  int v10; // ecx
  __int64 v11; // r8
  const struct wil::FailureInfo *v12; // rdx
  wil::details::in1diag3 *v13; // rcx
  const struct wil::FailureInfo *v14; // r9
  bool v15; // zf
  unsigned __int64 v16[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v17; // [rsp+30h] [rbp-D0h]
  __int128 v18; // [rsp+40h] [rbp-C0h]
  __int128 v19; // [rsp+50h] [rbp-B0h]
  __int128 v20; // [rsp+60h] [rbp-A0h]
  __int128 v21; // [rsp+70h] [rbp-90h]
  _OWORD v22[2]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v23; // [rsp+A0h] [rbp-60h]
  __int64 v24; // [rsp+B0h] [rbp-50h]
  _BYTE v25[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  *(_OWORD *)v16 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  memset(v22, 0, sizeof(v22));
  v23 = 0;
  v24 = 0;
  OutputString[0] = 0;
  v25[0] = 0;
  v16[1] = *a7;
  v9 = wil::details::RecordReturn((wil::details *)LODWORD(v16[1]), a2);
  LODWORD(v16[0]) = 1;
  v10 = 0;
  if ( *(_DWORD *)(v11 + 8) == 1 )
    v10 = 8;
  HIDWORD(v16[0]) = v10;
  LODWORD(v17) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  *((_QWORD *)&v17 + 1) = 0;
  LODWORD(v18) = GetCurrentThreadId();
  *((_QWORD *)&v19 + 1) = "wil";
  v20 = __PAIR64__(v9, a2);
  *((_QWORD *)&v18 + 1) = 0;
  *(_QWORD *)&v19 = 0;
  *((_QWORD *)&v23 + 1) = a6;
  v24 = a1;
  v21 = 0;
  memset(v22, 0, sizeof(v22));
  if ( wil::details::g_pfnGetModuleName )
    *(_QWORD *)&v23 = wil::details::g_pfnGetModuleName(v13);
  else
    *(_QWORD *)&v23 = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(v16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(v16, v25, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(v16);
  if ( wil::details::g_pfnOriginateCallback && (v16[0] & 0x200000000LL) == 0 )
    wil::details::g_pfnOriginateCallback(v16);
  if ( SLODWORD(v16[1]) >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v15 = !IsDebuggerPresent())
      : (v15 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v13) == 0),
        v15)
    || (v16[0] & 0x200000000LL) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(v16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(v16, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)v16, v14);
    OutputDebugStringW(OutputString);
  }
  if ( ((v16[0] & 0x400000000LL) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v13);
  if ( (v16[0] & 0x100000000LL) != 0 )
    wil::details::WilFailFast((wil::details *)v16, v12);
}

```

## disassembly

```asm
0x180009be0  mov     [rsp-8+arg_10], rbx
0x180009be5  push    rbp
0x180009be6  push    rsi
0x180009be7  push    rdi
0x180009be8  push    r14
0x180009bea  push    r15
0x180009bec  lea     rbp, [rsp-13D0h]
0x180009bf4  mov     eax, 14D0h
0x180009bf9  call    _alloca_probe
0x180009bfe  sub     rsp, rax
0x180009c01  mov     rax, cs:__security_cookie
0x180009c08  xor     rax, rsp
0x180009c0b  mov     [rbp+13F0h+var_30], rax
0x180009c12  mov     esi, edx
0x180009c14  mov     r14, rcx
0x180009c17  mov     rdi, [rbp+13F0h+arg_28]
0x180009c1e  xorps   xmm0, xmm0
0x180009c21  xor     eax, eax
0x180009c23  movups  xmmword ptr [rsp+14F0h+var_14D0], xmm0
0x180009c28  movups  [rsp+14F0h+var_14C0], xmm0
0x180009c2d  movups  [rsp+14F0h+var_14B0], xmm0
0x180009c32  movups  [rsp+14F0h+var_14A0], xmm0
0x180009c37  movups  [rsp+14F0h+var_1490], xmm0
0x180009c3c  movups  [rsp+14F0h+var_1480], xmm0
0x180009c41  movups  [rbp+13F0h+var_1470], xmm0
0x180009c45  movups  [rbp+13F0h+var_1460], xmm0
0x180009c49  movups  [rbp+13F0h+var_1450], xmm0
0x180009c4d  mov     [rbp+13F0h+var_1440], rax
0x180009c51  xor     r15d, r15d
0x180009c54  mov     [rbp+13F0h+OutputString], r15w
0x180009c5c  mov     [rbp+13F0h+var_1430], r15b
0x180009c60  mov     r8, [rbp+13F0h+arg_30]
0x180009c67  mov     ecx, [r8]; this
0x180009c6a  mov     dword ptr [rsp+14F0h+var_14D0+8], ecx
0x180009c6e  mov     eax, [r8+4]
0x180009c72  mov     dword ptr [rsp+14F0h+var_14D0+0Ch], eax
0x180009c76  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180009c7b  mov     ebx, eax
0x180009c7d  mov     edx, 1
0x180009c82  mov     dword ptr [rsp+14F0h+var_14D0], edx
0x180009c86  mov     ecx, r15d
0x180009c89  mov     eax, 8
0x180009c8e  cmp     [r8+8], edx
0x180009c92  cmovz   ecx, eax
0x180009c95  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180009c99  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, edx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180009ca1  inc     edx
0x180009ca3  mov     dword ptr [rsp+14F0h+var_14C0], edx
0x180009ca7  mov     qword ptr [rsp+14F0h+var_14C0+8], r15
0x180009cac  call    cs:__imp_GetCurrentThreadId
0x180009cb3  nop     dword ptr [rax+rax+00h]
0x180009cb8  mov     dword ptr [rsp+14F0h+var_14B0], eax
0x180009cbc  lea     rax, aWil; "wil"
0x180009cc3  mov     qword ptr [rsp+14F0h+var_14A0+8], rax
0x180009cc8  mov     dword ptr [rsp+14F0h+var_1490], esi
0x180009ccc  mov     dword ptr [rsp+14F0h+var_1490+4], ebx
0x180009cd0  mov     qword ptr [rsp+14F0h+var_14B0+8], r15
0x180009cd5  mov     qword ptr [rsp+14F0h+var_14A0], r15
0x180009cda  mov     qword ptr [rbp+13F0h+var_1450+8], rdi
0x180009cde  mov     [rbp+13F0h+var_1440], r14
0x180009ce2  mov     qword ptr [rsp+14F0h+var_1490+8], r15
0x180009ce7  xorps   xmm0, xmm0
0x180009cea  xor     eax, eax
0x180009cec  movups  [rbp+13F0h+var_1470+8], xmm0
0x180009cf0  mov     qword ptr [rbp+13F0h+var_1460+8], rax
0x180009cf4  xorps   xmm1, xmm1
0x180009cf7  movups  [rsp+14F0h+var_1480], xmm1
0x180009cfc  mov     qword ptr [rbp+13F0h+var_1470], rax
0x180009d00  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180009d07  test    rax, rax
0x180009d0a  jz      short loc_180009D18
0x180009d0c  call    cs:__guard_dispatch_icall_fptr
0x180009d12  mov     qword ptr [rbp+13F0h+var_1450], rax
0x180009d16  jmp     short loc_180009D1C
0x180009d18  mov     qword ptr [rbp+13F0h+var_1450], r15
0x180009d1c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180009d23  test    rax, rax
0x180009d26  jz      short loc_180009D33
0x180009d28  lea     rcx, [rsp+14F0h+var_14D0]
0x180009d2d  call    cs:__guard_dispatch_icall_fptr
0x180009d33  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180009d3a  test    rax, rax
0x180009d3d  jz      short loc_180009D54
0x180009d3f  mov     r8d, 400h
0x180009d45  lea     rdx, [rbp+13F0h+var_1430]
0x180009d49  lea     rcx, [rsp+14F0h+var_14D0]
0x180009d4e  call    cs:__guard_dispatch_icall_fptr
0x180009d54  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180009d5b  test    rax, rax
0x180009d5e  jz      short loc_180009D6B
0x180009d60  lea     rcx, [rsp+14F0h+var_14D0]
0x180009d65  call    cs:__guard_dispatch_icall_fptr
0x180009d6b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180009d72  test    rax, rax
0x180009d75  jz      short loc_180009D89
0x180009d77  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180009d7c  jnz     short loc_180009D89
0x180009d7e  lea     rcx, [rsp+14F0h+var_14D0]
0x180009d83  call    cs:__guard_dispatch_icall_fptr
0x180009d89  cmp     dword ptr [rsp+14F0h+var_14D0+8], r15d
0x180009d8e  jge     loc_180009EAD
0x180009d94  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180009d9b  jnz     short loc_180009DC3
0x180009d9d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180009da4  test    rax, rax
0x180009da7  jz      short loc_180009DB3
0x180009da9  call    cs:__guard_dispatch_icall_fptr
0x180009daf  test    al, al
0x180009db1  jmp     short loc_180009DC1
0x180009db3  call    cs:__imp_IsDebuggerPresent
0x180009dba  nop     dword ptr [rax+rax+00h]
0x180009dbf  test    eax, eax
0x180009dc1  jz      short loc_180009DCA
0x180009dc3  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180009dc8  jz      short loc_180009DF1
0x180009dca  mov     rax, cs:g_pfnResultLoggingCallback
0x180009dd1  test    rax, rax
0x180009dd4  jz      short loc_180009E51
0x180009dd6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180009ddd  jnz     short loc_180009E51
0x180009ddf  xor     r8d, r8d
0x180009de2  xor     edx, edx
0x180009de4  lea     rcx, [rsp+14F0h+var_14D0]
0x180009de9  call    cs:__guard_dispatch_icall_fptr
0x180009def  jmp     short loc_180009E51
0x180009df1  mov     rax, cs:g_pfnResultLoggingCallback
0x180009df8  test    rax, rax
0x180009dfb  jz      short loc_180009E1E
0x180009dfd  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180009e04  jnz     short loc_180009E1E
0x180009e06  mov     r8d, 800h
0x180009e0c  lea     rdx, [rbp+13F0h+OutputString]
0x180009e13  lea     rcx, [rsp+14F0h+var_14D0]
0x180009e18  call    cs:__guard_dispatch_icall_fptr
0x180009e1e  cmp     [rbp+13F0h+OutputString], r15w
0x180009e26  jnz     short loc_180009E3E
0x180009e28  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180009e2d  mov     edx, 800h; unsigned __int16 *
0x180009e32  lea     rcx, [rbp+13F0h+OutputString]; this
0x180009e39  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180009e3e  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180009e45  call    cs:__imp_OutputDebugStringW
0x180009e4c  nop     dword ptr [rax+rax+00h]
0x180009e51  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180009e56  jnz     short loc_180009E61
0x180009e58  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180009e5f  jz      short loc_180009E74
0x180009e61  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180009e68  test    rax, rax
0x180009e6b  jz      short loc_180009E74
0x180009e6d  call    cs:__guard_dispatch_icall_fptr
0x180009e73  nop
0x180009e74  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180009e79  jnz     short loc_180009EA2
0x180009e7b  mov     rcx, [rbp+13F0h+var_30]
0x180009e82  xor     rcx, rsp; StackCookie
0x180009e85  call    __security_check_cookie
0x180009e8a  mov     rbx, [rsp+14F0h+arg_10]
0x180009e92  add     rsp, 14D0h
0x180009e99  pop     r15
0x180009e9b  pop     r14
0x180009e9d  pop     rdi
0x180009e9e  pop     rsi
0x180009e9f  pop     rbp
0x180009ea0  retn
0x180009ea2  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180009ea7  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180009ead  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
