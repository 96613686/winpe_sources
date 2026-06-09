# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180011a04`
- end: `0x180011c98`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800116cc`

## callees

- `0x18000e2f0`
- `0x18000ec40`
- `0x180011a04`
- `0x180012f24`
- `0x18001441c`
- `0x180015548`
- `0x180015754`
- `0x180017490`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011aae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011aae`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180011ba9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180011ba9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180011c33`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180011c33`

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
0x180011a04  mov     [rsp-8+arg_10], rbx
0x180011a09  push    rbp
0x180011a0a  push    rsi
0x180011a0b  push    rdi
0x180011a0c  push    r14
0x180011a0e  push    r15
0x180011a10  lea     rbp, [rsp-13D0h]
0x180011a18  mov     eax, 14D0h
0x180011a1d  call    _alloca_probe
0x180011a22  sub     rsp, rax
0x180011a25  mov     rax, cs:__security_cookie
0x180011a2c  xor     rax, rsp
0x180011a2f  mov     [rbp+13F0h+var_30], rax
0x180011a36  mov     rdi, [rbp+13F0h+arg_28]
0x180011a3d  mov     esi, edx
0x180011a3f  mov     r14, rcx
0x180011a42  xor     edx, edx; Val
0x180011a44  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180011a49  mov     r8d, 98h; Size
0x180011a4f  call    memset_0
0x180011a54  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180011a5b  xor     r15d, r15d
0x180011a5e  mov     [rbp+13F0h+OutputString], r15w
0x180011a66  mov     [rbp+13F0h+var_1430], r15b
0x180011a6a  mov     ecx, [rdx]; this
0x180011a6c  mov     eax, [rdx+4]
0x180011a6f  mov     [rsp+14F0h+var_14C8], ecx
0x180011a73  mov     [rsp+14F0h+var_14C4], eax
0x180011a77  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180011a7c  cmp     dword ptr [rdx+8], 1
0x180011a80  mov     ebx, eax
0x180011a82  lea     eax, [r15+8]
0x180011a86  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180011a8e  mov     ecx, r15d
0x180011a91  cmovz   ecx, eax
0x180011a94  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180011a98  lea     ecx, [rax-7]
0x180011a9b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180011aa3  inc     ecx
0x180011aa5  mov     [rsp+14F0h+var_14B8], r15
0x180011aaa  mov     [rsp+14F0h+var_14C0], ecx
0x180011aae  call    cs:__imp_GetCurrentThreadId
0x180011ab4  xorps   xmm0, xmm0
0x180011ab7  mov     [rsp+14F0h+var_1490], esi
0x180011abb  mov     [rsp+14F0h+var_14B0], eax
0x180011abf  xorps   xmm1, xmm1
0x180011ac2  lea     rax, aWil; "wil"
0x180011ac9  mov     [rsp+14F0h+var_148C], ebx
0x180011acd  mov     [rsp+14F0h+var_1498], rax
0x180011ad2  xor     eax, eax
0x180011ad4  mov     [rbp+13F0h+var_1458], rax
0x180011ad8  mov     [rbp+13F0h+var_1470], rax
0x180011adc  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180011ae3  mov     [rsp+14F0h+var_14A8], r15
0x180011ae8  mov     [rsp+14F0h+var_14A0], r15
0x180011aed  mov     [rbp+13F0h+var_1448], rdi
0x180011af1  mov     [rbp+13F0h+var_1440], r14
0x180011af5  mov     [rsp+14F0h+var_1488], r15
0x180011afa  movups  [rbp+13F0h+var_1468], xmm0
0x180011afe  movups  [rsp+14F0h+var_1480], xmm1
0x180011b03  test    rax, rax
0x180011b06  jz      short loc_180011B13
0x180011b08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b0d  mov     [rbp+13F0h+var_1450], rax
0x180011b11  jmp     short loc_180011B17
0x180011b13  mov     [rbp+13F0h+var_1450], r15
0x180011b17  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180011b1e  test    rax, rax
0x180011b21  jz      short loc_180011B2D
0x180011b23  lea     rcx, [rsp+14F0h+var_14D0]
0x180011b28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b2d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180011b34  test    rax, rax
0x180011b37  jz      short loc_180011B4D
0x180011b39  mov     r8d, 400h
0x180011b3f  lea     rdx, [rbp+13F0h+var_1430]
0x180011b43  lea     rcx, [rsp+14F0h+var_14D0]
0x180011b48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b4d  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180011b54  test    rax, rax
0x180011b57  jz      short loc_180011B63
0x180011b59  lea     rcx, [rsp+14F0h+var_14D0]
0x180011b5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b63  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180011b6a  test    rax, rax
0x180011b6d  jz      short loc_180011B80
0x180011b6f  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180011b74  jnz     short loc_180011B80
0x180011b76  lea     rcx, [rsp+14F0h+var_14D0]
0x180011b7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b80  cmp     [rsp+14F0h+var_14C8], r15d
0x180011b85  jge     loc_180011C87
0x180011b8b  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180011b92  jnz     short loc_180011BB3
0x180011b94  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180011b9b  test    rax, rax
0x180011b9e  jz      short loc_180011BA9
0x180011ba0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ba5  test    al, al
0x180011ba7  jmp     short loc_180011BB1
0x180011ba9  call    cs:__imp_IsDebuggerPresent
0x180011baf  test    eax, eax
0x180011bb1  jz      short loc_180011BBA
0x180011bb3  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180011bb8  jz      short loc_180011BE0
0x180011bba  mov     rax, cs:g_pfnResultLoggingCallback
0x180011bc1  test    rax, rax
0x180011bc4  jz      short loc_180011C39
0x180011bc6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180011bcd  jnz     short loc_180011C39
0x180011bcf  xor     r8d, r8d
0x180011bd2  lea     rcx, [rsp+14F0h+var_14D0]
0x180011bd7  xor     edx, edx
0x180011bd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011bde  jmp     short loc_180011C39
0x180011be0  mov     rax, cs:g_pfnResultLoggingCallback
0x180011be7  mov     ebx, 800h
0x180011bec  test    rax, rax
0x180011bef  jz      short loc_180011C0E
0x180011bf1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180011bf8  jnz     short loc_180011C0E
0x180011bfa  mov     r8d, ebx
0x180011bfd  lea     rdx, [rbp+13F0h+OutputString]
0x180011c04  lea     rcx, [rsp+14F0h+var_14D0]
0x180011c09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c0e  cmp     [rbp+13F0h+OutputString], r15w
0x180011c16  jnz     short loc_180011C2C
0x180011c18  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180011c1d  mov     rdx, rbx; unsigned __int16 *
0x180011c20  lea     rcx, [rbp+13F0h+OutputString]; this
0x180011c27  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180011c2c  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180011c33  call    cs:__imp_OutputDebugStringW
0x180011c39  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180011c3e  jnz     short loc_180011C49
0x180011c40  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180011c47  jz      short loc_180011C5A
0x180011c49  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180011c50  test    rax, rax
0x180011c53  jz      short loc_180011C5A
0x180011c55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c5a  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180011c5f  jnz     short loc_180011C8D
0x180011c61  mov     rcx, [rbp+13F0h+var_30]
0x180011c68  xor     rcx, rsp; StackCookie
0x180011c6b  call    __security_check_cookie
0x180011c70  mov     rbx, [rsp+14F0h+arg_10]
0x180011c78  add     rsp, 14D0h
0x180011c7f  pop     r15
0x180011c81  pop     r14
0x180011c83  pop     rdi
0x180011c84  pop     rsi
0x180011c85  pop     rbp
0x180011c86  retn
0x180011c87  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180011c8d  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180011c92  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
