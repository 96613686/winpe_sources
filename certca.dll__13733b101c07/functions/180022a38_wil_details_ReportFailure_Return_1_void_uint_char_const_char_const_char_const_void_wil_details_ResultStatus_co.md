# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180022a38`
- end: `0x180022ccc`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180022540`

## callees

- `0x18001c7f4`
- `0x180022a38`
- `0x180025544`
- `0x180026774`
- `0x180026930`
- `0x180038262`
- `0x1800382c0`
- `0x180038380`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022ae2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022ae2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180022bdd`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180022bdd`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180022c67`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180022c67`

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
0x180022a38  mov     [rsp-8+arg_10], rbx
0x180022a3d  push    rbp
0x180022a3e  push    rsi
0x180022a3f  push    rdi
0x180022a40  push    r14
0x180022a42  push    r15
0x180022a44  lea     rbp, [rsp-13D0h]
0x180022a4c  mov     eax, 14D0h
0x180022a51  call    _alloca_probe
0x180022a56  sub     rsp, rax
0x180022a59  mov     rax, cs:__security_cookie
0x180022a60  xor     rax, rsp
0x180022a63  mov     [rbp+13F0h+var_30], rax
0x180022a6a  mov     rdi, [rbp+13F0h+arg_28]
0x180022a71  mov     esi, edx
0x180022a73  mov     r14, rcx
0x180022a76  xor     edx, edx; Val
0x180022a78  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180022a7d  mov     r8d, 98h; Size
0x180022a83  call    memset_0
0x180022a88  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180022a8f  xor     r15d, r15d
0x180022a92  mov     [rbp+13F0h+OutputString], r15w
0x180022a9a  mov     [rbp+13F0h+var_1430], r15b
0x180022a9e  mov     ecx, [rdx]; this
0x180022aa0  mov     eax, [rdx+4]
0x180022aa3  mov     [rsp+14F0h+var_14C8], ecx
0x180022aa7  mov     [rsp+14F0h+var_14C4], eax
0x180022aab  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180022ab0  cmp     dword ptr [rdx+8], 1
0x180022ab4  mov     ebx, eax
0x180022ab6  lea     eax, [r15+8]
0x180022aba  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180022ac2  mov     ecx, r15d
0x180022ac5  cmovz   ecx, eax
0x180022ac8  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180022acc  lea     ecx, [rax-7]
0x180022acf  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180022ad7  inc     ecx
0x180022ad9  mov     [rsp+14F0h+var_14B8], r15
0x180022ade  mov     [rsp+14F0h+var_14C0], ecx
0x180022ae2  call    cs:__imp_GetCurrentThreadId
0x180022ae8  xorps   xmm0, xmm0
0x180022aeb  mov     [rsp+14F0h+var_1490], esi
0x180022aef  mov     [rsp+14F0h+var_14B0], eax
0x180022af3  xorps   xmm1, xmm1
0x180022af6  lea     rax, aWil; "wil"
0x180022afd  mov     [rsp+14F0h+var_148C], ebx
0x180022b01  mov     [rsp+14F0h+var_1498], rax
0x180022b06  xor     eax, eax
0x180022b08  mov     [rbp+13F0h+var_1458], rax
0x180022b0c  mov     [rbp+13F0h+var_1470], rax
0x180022b10  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180022b17  mov     [rsp+14F0h+var_14A8], r15
0x180022b1c  mov     [rsp+14F0h+var_14A0], r15
0x180022b21  mov     [rbp+13F0h+var_1448], rdi
0x180022b25  mov     [rbp+13F0h+var_1440], r14
0x180022b29  mov     [rsp+14F0h+var_1488], r15
0x180022b2e  movups  [rbp+13F0h+var_1468], xmm0
0x180022b32  movups  [rsp+14F0h+var_1480], xmm1
0x180022b37  test    rax, rax
0x180022b3a  jz      short loc_180022B47
0x180022b3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022b41  mov     [rbp+13F0h+var_1450], rax
0x180022b45  jmp     short loc_180022B4B
0x180022b47  mov     [rbp+13F0h+var_1450], r15
0x180022b4b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180022b52  test    rax, rax
0x180022b55  jz      short loc_180022B61
0x180022b57  lea     rcx, [rsp+14F0h+var_14D0]
0x180022b5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022b61  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180022b68  test    rax, rax
0x180022b6b  jz      short loc_180022B81
0x180022b6d  mov     r8d, 400h
0x180022b73  lea     rdx, [rbp+13F0h+var_1430]
0x180022b77  lea     rcx, [rsp+14F0h+var_14D0]
0x180022b7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022b81  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180022b88  test    rax, rax
0x180022b8b  jz      short loc_180022B97
0x180022b8d  lea     rcx, [rsp+14F0h+var_14D0]
0x180022b92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022b97  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180022b9e  test    rax, rax
0x180022ba1  jz      short loc_180022BB4
0x180022ba3  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180022ba8  jnz     short loc_180022BB4
0x180022baa  lea     rcx, [rsp+14F0h+var_14D0]
0x180022baf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022bb4  cmp     [rsp+14F0h+var_14C8], r15d
0x180022bb9  jge     loc_180022CBB
0x180022bbf  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180022bc6  jnz     short loc_180022BE7
0x180022bc8  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180022bcf  test    rax, rax
0x180022bd2  jz      short loc_180022BDD
0x180022bd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022bd9  test    al, al
0x180022bdb  jmp     short loc_180022BE5
0x180022bdd  call    cs:__imp_IsDebuggerPresent
0x180022be3  test    eax, eax
0x180022be5  jz      short loc_180022BEE
0x180022be7  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180022bec  jz      short loc_180022C14
0x180022bee  mov     rax, cs:g_pfnResultLoggingCallback
0x180022bf5  test    rax, rax
0x180022bf8  jz      short loc_180022C6D
0x180022bfa  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180022c01  jnz     short loc_180022C6D
0x180022c03  xor     r8d, r8d
0x180022c06  lea     rcx, [rsp+14F0h+var_14D0]
0x180022c0b  xor     edx, edx
0x180022c0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022c12  jmp     short loc_180022C6D
0x180022c14  mov     rax, cs:g_pfnResultLoggingCallback
0x180022c1b  mov     ebx, 800h
0x180022c20  test    rax, rax
0x180022c23  jz      short loc_180022C42
0x180022c25  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180022c2c  jnz     short loc_180022C42
0x180022c2e  mov     r8d, ebx
0x180022c31  lea     rdx, [rbp+13F0h+OutputString]
0x180022c38  lea     rcx, [rsp+14F0h+var_14D0]
0x180022c3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022c42  cmp     [rbp+13F0h+OutputString], r15w
0x180022c4a  jnz     short loc_180022C60
0x180022c4c  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180022c51  mov     rdx, rbx; unsigned __int16 *
0x180022c54  lea     rcx, [rbp+13F0h+OutputString]; this
0x180022c5b  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180022c60  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180022c67  call    cs:__imp_OutputDebugStringW
0x180022c6d  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180022c72  jnz     short loc_180022C7D
0x180022c74  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180022c7b  jz      short loc_180022C8E
0x180022c7d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180022c84  test    rax, rax
0x180022c87  jz      short loc_180022C8E
0x180022c89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022c8e  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180022c93  jnz     short loc_180022CC1
0x180022c95  mov     rcx, [rbp+13F0h+var_30]
0x180022c9c  xor     rcx, rsp; StackCookie
0x180022c9f  call    __security_check_cookie
0x180022ca4  mov     rbx, [rsp+14F0h+arg_10]
0x180022cac  add     rsp, 14D0h
0x180022cb3  pop     r15
0x180022cb5  pop     r14
0x180022cb7  pop     rdi
0x180022cb8  pop     rsi
0x180022cb9  pop     rbp
0x180022cba  retn
0x180022cbb  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180022cc1  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180022cc6  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
