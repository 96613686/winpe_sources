# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180018950`
- end: `0x180018be4`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180018618`

## callees

- `0x180018950`
- `0x18001a714`
- `0x18001c1fc`
- `0x18001d7c8`
- `0x18001d9d8`
- `0x18002c01e`
- `0x18002c050`
- `0x18002c0e0`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800189fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800189fa`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180018af5`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180018af5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180018b7f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180018b7f`

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
0x180018950  mov     [rsp-8+arg_10], rbx
0x180018955  push    rbp
0x180018956  push    rsi
0x180018957  push    rdi
0x180018958  push    r14
0x18001895a  push    r15
0x18001895c  lea     rbp, [rsp-13D0h]
0x180018964  mov     eax, 14D0h
0x180018969  call    _alloca_probe
0x18001896e  sub     rsp, rax
0x180018971  mov     rax, cs:__security_cookie
0x180018978  xor     rax, rsp
0x18001897b  mov     [rbp+13F0h+var_30], rax
0x180018982  mov     rdi, [rbp+13F0h+arg_28]
0x180018989  mov     esi, edx
0x18001898b  mov     r14, rcx
0x18001898e  xor     edx, edx; Val
0x180018990  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180018995  mov     r8d, 98h; Size
0x18001899b  call    memset_0
0x1800189a0  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x1800189a7  xor     r15d, r15d
0x1800189aa  mov     [rbp+13F0h+OutputString], r15w
0x1800189b2  mov     [rbp+13F0h+var_1430], r15b
0x1800189b6  mov     ecx, [rdx]; this
0x1800189b8  mov     eax, [rdx+4]
0x1800189bb  mov     [rsp+14F0h+var_14C8], ecx
0x1800189bf  mov     [rsp+14F0h+var_14C4], eax
0x1800189c3  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800189c8  cmp     dword ptr [rdx+8], 1
0x1800189cc  mov     ebx, eax
0x1800189ce  lea     eax, [r15+8]
0x1800189d2  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x1800189da  mov     ecx, r15d
0x1800189dd  cmovz   ecx, eax
0x1800189e0  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800189e4  lea     ecx, [rax-7]
0x1800189e7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800189ef  inc     ecx
0x1800189f1  mov     [rsp+14F0h+var_14B8], r15
0x1800189f6  mov     [rsp+14F0h+var_14C0], ecx
0x1800189fa  call    cs:__imp_GetCurrentThreadId
0x180018a00  xorps   xmm0, xmm0
0x180018a03  mov     [rsp+14F0h+var_1490], esi
0x180018a07  mov     [rsp+14F0h+var_14B0], eax
0x180018a0b  xorps   xmm1, xmm1
0x180018a0e  lea     rax, aWil; "wil"
0x180018a15  mov     [rsp+14F0h+var_148C], ebx
0x180018a19  mov     [rsp+14F0h+var_1498], rax
0x180018a1e  xor     eax, eax
0x180018a20  mov     [rbp+13F0h+var_1458], rax
0x180018a24  mov     [rbp+13F0h+var_1470], rax
0x180018a28  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180018a2f  mov     [rsp+14F0h+var_14A8], r15
0x180018a34  mov     [rsp+14F0h+var_14A0], r15
0x180018a39  mov     [rbp+13F0h+var_1448], rdi
0x180018a3d  mov     [rbp+13F0h+var_1440], r14
0x180018a41  mov     [rsp+14F0h+var_1488], r15
0x180018a46  movups  [rbp+13F0h+var_1468], xmm0
0x180018a4a  movups  [rsp+14F0h+var_1480], xmm1
0x180018a4f  test    rax, rax
0x180018a52  jz      short loc_180018A5F
0x180018a54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a59  mov     [rbp+13F0h+var_1450], rax
0x180018a5d  jmp     short loc_180018A63
0x180018a5f  mov     [rbp+13F0h+var_1450], r15
0x180018a63  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180018a6a  test    rax, rax
0x180018a6d  jz      short loc_180018A79
0x180018a6f  lea     rcx, [rsp+14F0h+var_14D0]
0x180018a74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a79  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180018a80  test    rax, rax
0x180018a83  jz      short loc_180018A99
0x180018a85  mov     r8d, 400h
0x180018a8b  lea     rdx, [rbp+13F0h+var_1430]
0x180018a8f  lea     rcx, [rsp+14F0h+var_14D0]
0x180018a94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a99  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180018aa0  test    rax, rax
0x180018aa3  jz      short loc_180018AAF
0x180018aa5  lea     rcx, [rsp+14F0h+var_14D0]
0x180018aaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018aaf  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180018ab6  test    rax, rax
0x180018ab9  jz      short loc_180018ACC
0x180018abb  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180018ac0  jnz     short loc_180018ACC
0x180018ac2  lea     rcx, [rsp+14F0h+var_14D0]
0x180018ac7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018acc  cmp     [rsp+14F0h+var_14C8], r15d
0x180018ad1  jge     loc_180018BD3
0x180018ad7  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180018ade  jnz     short loc_180018AFF
0x180018ae0  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180018ae7  test    rax, rax
0x180018aea  jz      short loc_180018AF5
0x180018aec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018af1  test    al, al
0x180018af3  jmp     short loc_180018AFD
0x180018af5  call    cs:__imp_IsDebuggerPresent
0x180018afb  test    eax, eax
0x180018afd  jz      short loc_180018B06
0x180018aff  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180018b04  jz      short loc_180018B2C
0x180018b06  mov     rax, cs:g_pfnResultLoggingCallback
0x180018b0d  test    rax, rax
0x180018b10  jz      short loc_180018B85
0x180018b12  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180018b19  jnz     short loc_180018B85
0x180018b1b  xor     r8d, r8d
0x180018b1e  lea     rcx, [rsp+14F0h+var_14D0]
0x180018b23  xor     edx, edx
0x180018b25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018b2a  jmp     short loc_180018B85
0x180018b2c  mov     rax, cs:g_pfnResultLoggingCallback
0x180018b33  mov     ebx, 800h
0x180018b38  test    rax, rax
0x180018b3b  jz      short loc_180018B5A
0x180018b3d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180018b44  jnz     short loc_180018B5A
0x180018b46  mov     r8d, ebx
0x180018b49  lea     rdx, [rbp+13F0h+OutputString]
0x180018b50  lea     rcx, [rsp+14F0h+var_14D0]
0x180018b55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018b5a  cmp     [rbp+13F0h+OutputString], r15w
0x180018b62  jnz     short loc_180018B78
0x180018b64  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180018b69  mov     rdx, rbx; unsigned __int16 *
0x180018b6c  lea     rcx, [rbp+13F0h+OutputString]; this
0x180018b73  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180018b78  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180018b7f  call    cs:__imp_OutputDebugStringW
0x180018b85  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180018b8a  jnz     short loc_180018B95
0x180018b8c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180018b93  jz      short loc_180018BA6
0x180018b95  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180018b9c  test    rax, rax
0x180018b9f  jz      short loc_180018BA6
0x180018ba1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ba6  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180018bab  jnz     short loc_180018BD9
0x180018bad  mov     rcx, [rbp+13F0h+var_30]
0x180018bb4  xor     rcx, rsp; StackCookie
0x180018bb7  call    __security_check_cookie
0x180018bbc  mov     rbx, [rsp+14F0h+arg_10]
0x180018bc4  add     rsp, 14D0h
0x180018bcb  pop     r15
0x180018bcd  pop     r14
0x180018bcf  pop     rdi
0x180018bd0  pop     rsi
0x180018bd1  pop     rbp
0x180018bd2  retn
0x180018bd3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180018bd9  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180018bde  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
