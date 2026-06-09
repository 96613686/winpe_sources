# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000bc54`
- end: `0x18000beea`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000b73c`

## callees

- `0x180001f90`
- `0x180002a40`
- `0x18000bc54`
- `0x18000d1f4`
- `0x18000ea80`
- `0x180010210`
- `0x180010398`
- `0x180012350`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bcff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bcff`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000be84`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000be84`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000bdfa`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000bdfa`

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
0x18000bc54  mov     [rsp-8+arg_10], rbx
0x18000bc59  push    rbp
0x18000bc5a  push    rsi
0x18000bc5b  push    rdi
0x18000bc5c  push    r14
0x18000bc5e  push    r15
0x18000bc60  lea     rbp, [rsp-13D0h]
0x18000bc68  mov     eax, 14D0h
0x18000bc6d  call    _alloca_probe
0x18000bc72  sub     rsp, rax
0x18000bc75  mov     rax, cs:__security_cookie
0x18000bc7c  xor     rax, rsp
0x18000bc7f  mov     [rbp+13F0h+var_30], rax
0x18000bc86  mov     esi, edx
0x18000bc88  mov     r14, rcx
0x18000bc8b  mov     rdi, [rbp+13F0h+arg_28]
0x18000bc92  xor     edx, edx; Val
0x18000bc94  mov     r8d, 98h; Size
0x18000bc9a  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000bc9f  call    memset_0
0x18000bca4  nop
0x18000bca5  xor     r15d, r15d
0x18000bca8  mov     [rbp+13F0h+OutputString], r15w
0x18000bcb0  mov     [rbp+13F0h+var_1430], r15b
0x18000bcb4  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18000bcbb  mov     ecx, [rdx]; this
0x18000bcbd  mov     [rsp+14F0h+var_14C8], ecx
0x18000bcc1  mov     eax, [rdx+4]
0x18000bcc4  mov     [rsp+14F0h+var_14C4], eax
0x18000bcc8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000bccd  mov     ebx, eax
0x18000bccf  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x18000bcd7  mov     ecx, r15d
0x18000bcda  lea     eax, [r15+8]
0x18000bcde  cmp     dword ptr [rdx+8], 1
0x18000bce2  cmovz   ecx, eax
0x18000bce5  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000bce9  lea     ecx, [rax-7]
0x18000bcec  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000bcf4  inc     ecx
0x18000bcf6  mov     [rsp+14F0h+var_14C0], ecx
0x18000bcfa  mov     [rsp+14F0h+var_14B8], r15
0x18000bcff  call    cs:__imp_GetCurrentThreadId
0x18000bd05  mov     [rsp+14F0h+var_14B0], eax
0x18000bd09  lea     rax, aWil; "wil"
0x18000bd10  mov     [rsp+14F0h+var_1498], rax
0x18000bd15  mov     [rsp+14F0h+var_1490], esi
0x18000bd19  mov     [rsp+14F0h+var_148C], ebx
0x18000bd1d  mov     [rsp+14F0h+var_14A8], r15
0x18000bd22  mov     [rsp+14F0h+var_14A0], r15
0x18000bd27  mov     [rbp+13F0h+var_1448], rdi
0x18000bd2b  mov     [rbp+13F0h+var_1440], r14
0x18000bd2f  mov     [rsp+14F0h+var_1488], r15
0x18000bd34  xorps   xmm0, xmm0
0x18000bd37  xor     eax, eax
0x18000bd39  movups  [rbp+13F0h+var_1468], xmm0
0x18000bd3d  mov     [rbp+13F0h+var_1458], rax
0x18000bd41  xorps   xmm1, xmm1
0x18000bd44  movups  [rsp+14F0h+var_1480], xmm1
0x18000bd49  mov     [rbp+13F0h+var_1470], rax
0x18000bd4d  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000bd54  test    rax, rax
0x18000bd57  jz      short loc_18000BD64
0x18000bd59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd5e  mov     [rbp+13F0h+var_1450], rax
0x18000bd62  jmp     short loc_18000BD68
0x18000bd64  mov     [rbp+13F0h+var_1450], r15
0x18000bd68  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000bd6f  test    rax, rax
0x18000bd72  jz      short loc_18000BD7E
0x18000bd74  lea     rcx, [rsp+14F0h+var_14D0]
0x18000bd79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd7e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000bd85  test    rax, rax
0x18000bd88  jz      short loc_18000BD9E
0x18000bd8a  mov     r8d, 400h
0x18000bd90  lea     rdx, [rbp+13F0h+var_1430]
0x18000bd94  lea     rcx, [rsp+14F0h+var_14D0]
0x18000bd99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd9e  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000bda5  test    rax, rax
0x18000bda8  jz      short loc_18000BDB4
0x18000bdaa  lea     rcx, [rsp+14F0h+var_14D0]
0x18000bdaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bdb4  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000bdbb  test    rax, rax
0x18000bdbe  jz      short loc_18000BDD1
0x18000bdc0  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000bdc5  jnz     short loc_18000BDD1
0x18000bdc7  lea     rcx, [rsp+14F0h+var_14D0]
0x18000bdcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bdd1  cmp     [rsp+14F0h+var_14C8], r15d
0x18000bdd6  jge     loc_18000BEE4
0x18000bddc  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18000bde3  jnz     short loc_18000BE04
0x18000bde5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000bdec  test    rax, rax
0x18000bdef  jz      short loc_18000BDFA
0x18000bdf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bdf6  test    al, al
0x18000bdf8  jmp     short loc_18000BE02
0x18000bdfa  call    cs:__imp_IsDebuggerPresent
0x18000be00  test    eax, eax
0x18000be02  jz      short loc_18000BE0B
0x18000be04  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000be09  jz      short loc_18000BE31
0x18000be0b  mov     rax, cs:g_pfnResultLoggingCallback
0x18000be12  test    rax, rax
0x18000be15  jz      short loc_18000BE8A
0x18000be17  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000be1e  jnz     short loc_18000BE8A
0x18000be20  xor     r8d, r8d
0x18000be23  xor     edx, edx
0x18000be25  lea     rcx, [rsp+14F0h+var_14D0]
0x18000be2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be2f  jmp     short loc_18000BE8A
0x18000be31  mov     ebx, 800h
0x18000be36  mov     rax, cs:g_pfnResultLoggingCallback
0x18000be3d  test    rax, rax
0x18000be40  jz      short loc_18000BE5F
0x18000be42  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000be49  jnz     short loc_18000BE5F
0x18000be4b  mov     r8d, ebx
0x18000be4e  lea     rdx, [rbp+13F0h+OutputString]
0x18000be55  lea     rcx, [rsp+14F0h+var_14D0]
0x18000be5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be5f  cmp     [rbp+13F0h+OutputString], r15w
0x18000be67  jnz     short loc_18000BE7D
0x18000be69  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000be6e  mov     rdx, rbx; unsigned __int16 *
0x18000be71  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000be78  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000be7d  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000be84  call    cs:__imp_OutputDebugStringW
0x18000be8a  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000be8f  jnz     short loc_18000BE9A
0x18000be91  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18000be98  jz      short loc_18000BEAC
0x18000be9a  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000bea1  test    rax, rax
0x18000bea4  jz      short loc_18000BEAC
0x18000bea6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000beab  nop
0x18000beac  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18000beb1  jnz     short loc_18000BED9
0x18000beb3  mov     rcx, [rbp+13F0h+var_30]
0x18000beba  xor     rcx, rsp; StackCookie
0x18000bebd  call    __security_check_cookie
0x18000bec2  mov     rbx, [rsp+14F0h+arg_10]
0x18000beca  add     rsp, 14D0h
0x18000bed1  pop     r15
0x18000bed3  pop     r14
0x18000bed5  pop     rdi
0x18000bed6  pop     rsi
0x18000bed7  pop     rbp
0x18000bed8  retn
0x18000bed9  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000bede  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000bee4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
