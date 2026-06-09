# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180025dd0`
- end: `0x180026064`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18001a8fc`

## callees

- `0x18001b7e0`
- `0x18001c10c`
- `0x180025dd0`
- `0x180027194`
- `0x18002888c`
- `0x180029a78`
- `0x180029c84`
- `0x18002e110`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180025e7a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180025e7a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180025f75`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180025f75`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180025fff`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180025fff`

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
0x180025dd0  mov     [rsp-8+arg_10], rbx
0x180025dd5  push    rbp
0x180025dd6  push    rsi
0x180025dd7  push    rdi
0x180025dd8  push    r14
0x180025dda  push    r15
0x180025ddc  lea     rbp, [rsp-13D0h]
0x180025de4  mov     eax, 14D0h
0x180025de9  call    _alloca_probe
0x180025dee  sub     rsp, rax
0x180025df1  mov     rax, cs:__security_cookie
0x180025df8  xor     rax, rsp
0x180025dfb  mov     [rbp+13F0h+var_30], rax
0x180025e02  mov     rdi, [rbp+13F0h+arg_28]
0x180025e09  mov     esi, edx
0x180025e0b  mov     r14, rcx
0x180025e0e  xor     edx, edx; Val
0x180025e10  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180025e15  mov     r8d, 98h; Size
0x180025e1b  call    memset_0
0x180025e20  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180025e27  xor     r15d, r15d
0x180025e2a  mov     [rbp+13F0h+OutputString], r15w
0x180025e32  mov     [rbp+13F0h+var_1430], r15b
0x180025e36  mov     ecx, [rdx]; this
0x180025e38  mov     eax, [rdx+4]
0x180025e3b  mov     [rsp+14F0h+var_14C8], ecx
0x180025e3f  mov     [rsp+14F0h+var_14C4], eax
0x180025e43  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180025e48  cmp     dword ptr [rdx+8], 1
0x180025e4c  mov     ebx, eax
0x180025e4e  lea     eax, [r15+8]
0x180025e52  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180025e5a  mov     ecx, r15d
0x180025e5d  cmovz   ecx, eax
0x180025e60  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180025e64  lea     ecx, [rax-7]
0x180025e67  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180025e6f  inc     ecx
0x180025e71  mov     [rsp+14F0h+var_14B8], r15
0x180025e76  mov     [rsp+14F0h+var_14C0], ecx
0x180025e7a  call    cs:__imp_GetCurrentThreadId
0x180025e80  xorps   xmm0, xmm0
0x180025e83  mov     [rsp+14F0h+var_1490], esi
0x180025e87  mov     [rsp+14F0h+var_14B0], eax
0x180025e8b  xorps   xmm1, xmm1
0x180025e8e  lea     rax, aWil; "wil"
0x180025e95  mov     [rsp+14F0h+var_148C], ebx
0x180025e99  mov     [rsp+14F0h+var_1498], rax
0x180025e9e  xor     eax, eax
0x180025ea0  mov     [rbp+13F0h+var_1458], rax
0x180025ea4  mov     [rbp+13F0h+var_1470], rax
0x180025ea8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180025eaf  mov     [rsp+14F0h+var_14A8], r15
0x180025eb4  mov     [rsp+14F0h+var_14A0], r15
0x180025eb9  mov     [rbp+13F0h+var_1448], rdi
0x180025ebd  mov     [rbp+13F0h+var_1440], r14
0x180025ec1  mov     [rsp+14F0h+var_1488], r15
0x180025ec6  movups  [rbp+13F0h+var_1468], xmm0
0x180025eca  movups  [rsp+14F0h+var_1480], xmm1
0x180025ecf  test    rax, rax
0x180025ed2  jz      short loc_180025EDF
0x180025ed4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ed9  mov     [rbp+13F0h+var_1450], rax
0x180025edd  jmp     short loc_180025EE3
0x180025edf  mov     [rbp+13F0h+var_1450], r15
0x180025ee3  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180025eea  test    rax, rax
0x180025eed  jz      short loc_180025EF9
0x180025eef  lea     rcx, [rsp+14F0h+var_14D0]
0x180025ef4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ef9  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180025f00  test    rax, rax
0x180025f03  jz      short loc_180025F19
0x180025f05  mov     r8d, 400h
0x180025f0b  lea     rdx, [rbp+13F0h+var_1430]
0x180025f0f  lea     rcx, [rsp+14F0h+var_14D0]
0x180025f14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025f19  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180025f20  test    rax, rax
0x180025f23  jz      short loc_180025F2F
0x180025f25  lea     rcx, [rsp+14F0h+var_14D0]
0x180025f2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025f2f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180025f36  test    rax, rax
0x180025f39  jz      short loc_180025F4C
0x180025f3b  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180025f40  jnz     short loc_180025F4C
0x180025f42  lea     rcx, [rsp+14F0h+var_14D0]
0x180025f47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025f4c  cmp     [rsp+14F0h+var_14C8], r15d
0x180025f51  jge     loc_180026053
0x180025f57  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180025f5e  jnz     short loc_180025F7F
0x180025f60  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180025f67  test    rax, rax
0x180025f6a  jz      short loc_180025F75
0x180025f6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025f71  test    al, al
0x180025f73  jmp     short loc_180025F7D
0x180025f75  call    cs:__imp_IsDebuggerPresent
0x180025f7b  test    eax, eax
0x180025f7d  jz      short loc_180025F86
0x180025f7f  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180025f84  jz      short loc_180025FAC
0x180025f86  mov     rax, cs:g_pfnResultLoggingCallback
0x180025f8d  test    rax, rax
0x180025f90  jz      short loc_180026005
0x180025f92  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180025f99  jnz     short loc_180026005
0x180025f9b  xor     r8d, r8d
0x180025f9e  lea     rcx, [rsp+14F0h+var_14D0]
0x180025fa3  xor     edx, edx
0x180025fa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025faa  jmp     short loc_180026005
0x180025fac  mov     rax, cs:g_pfnResultLoggingCallback
0x180025fb3  mov     ebx, 800h
0x180025fb8  test    rax, rax
0x180025fbb  jz      short loc_180025FDA
0x180025fbd  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180025fc4  jnz     short loc_180025FDA
0x180025fc6  mov     r8d, ebx
0x180025fc9  lea     rdx, [rbp+13F0h+OutputString]
0x180025fd0  lea     rcx, [rsp+14F0h+var_14D0]
0x180025fd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025fda  cmp     [rbp+13F0h+OutputString], r15w
0x180025fe2  jnz     short loc_180025FF8
0x180025fe4  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180025fe9  mov     rdx, rbx; unsigned __int16 *
0x180025fec  lea     rcx, [rbp+13F0h+OutputString]; this
0x180025ff3  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180025ff8  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180025fff  call    cs:__imp_OutputDebugStringW
0x180026005  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18002600a  jnz     short loc_180026015
0x18002600c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180026013  jz      short loc_180026026
0x180026015  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18002601c  test    rax, rax
0x18002601f  jz      short loc_180026026
0x180026021  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026026  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18002602b  jnz     short loc_180026059
0x18002602d  mov     rcx, [rbp+13F0h+var_30]
0x180026034  xor     rcx, rsp; StackCookie
0x180026037  call    __security_check_cookie
0x18002603c  mov     rbx, [rsp+14F0h+arg_10]
0x180026044  add     rsp, 14D0h
0x18002604b  pop     r15
0x18002604d  pop     r14
0x18002604f  pop     rdi
0x180026050  pop     rsi
0x180026051  pop     rbp
0x180026052  retn
0x180026053  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180026059  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18002605e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
