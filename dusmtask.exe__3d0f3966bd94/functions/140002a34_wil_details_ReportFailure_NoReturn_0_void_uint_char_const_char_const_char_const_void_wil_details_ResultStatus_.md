# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x140002a34`
- end: `0x140002ce0`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `684`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1400022f8`

## callees

- `0x140001f0e`
- `0x140002a34`
- `0x140004684`
- `0x14000561c`
- `0x1400068c4`
- `0x140006bf0`
- `0x140006ccc`
- `0x140007880`
- `0x140008010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002add`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002add`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140002bd8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140002bd8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140002c74`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140002c74`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int *a7)
{
  bool v10; // r12
  int v11; // ebx
  int v12; // ecx
  __int64 v13; // rdx
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  char v18; // bl
  const struct wil::FailureInfo *v19; // rdx
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
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
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v10 = g_pfnThrowPlatformException != 0;
  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v22 = *a7;
  v23 = a7[1];
  v11 = wil::details::RecordException((wil::details *)(unsigned int)v22, (int)a7);
  v20 = 0;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  v21 = v12;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v25 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v30 = a2;
  v31 = v11;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v36 = 0;
  v33 = 0;
  v34 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && !v10 && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v18 = 1, (v21 & 2) != 0) )
  {
    v18 = 0;
  }
  if ( v10 || v18 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v20, v16);
    if ( v18 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v20, 0, 0);
  }
  if ( ((v21 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v21 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v20, v14);
  if ( v10 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v20, OutputString);
  wil::ThrowResultException((wil *)&v20, v14);
  wil::details::WilFailFast((wil::details *)&v20, v19);
}

```

## disassembly

```asm
0x140002a34  mov     [rsp-8+arg_18], rbx
0x140002a39  push    rbp
0x140002a3a  push    rsi
0x140002a3b  push    rdi
0x140002a3c  push    r12
0x140002a3e  push    r13
0x140002a40  push    r14
0x140002a42  push    r15
0x140002a44  lea     rbp, [rsp-13C0h]
0x140002a4c  mov     eax, 14C0h
0x140002a51  call    _alloca_probe
0x140002a56  sub     rsp, rax
0x140002a59  mov     r14, r8
0x140002a5c  mov     esi, edx
0x140002a5e  mov     r15, rcx
0x140002a61  mov     rdi, [rbp+13F0h+arg_28]
0x140002a68  xor     r13d, r13d
0x140002a6b  cmp     cs:g_pfnThrowPlatformException, r13
0x140002a72  setnz   r12b
0x140002a76  xor     edx, edx; Val
0x140002a78  mov     r8d, 98h; Size
0x140002a7e  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x140002a83  call    memset_0
0x140002a88  nop
0x140002a89  mov     [rbp+13F0h+OutputString], r13w
0x140002a91  mov     [rbp+13F0h+var_1430], r13b
0x140002a95  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x140002a9c  mov     ecx, [rdx]; this
0x140002a9e  mov     [rsp+14F0h+var_14C8], ecx
0x140002aa2  mov     eax, [rdx+4]
0x140002aa5  mov     [rsp+14F0h+var_14C4], eax
0x140002aa9  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140002aae  mov     ebx, eax
0x140002ab0  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x140002ab5  mov     ecx, r13d
0x140002ab8  lea     eax, [r13+8]
0x140002abc  cmp     dword ptr [rdx+8], 1
0x140002ac0  cmovz   ecx, eax
0x140002ac3  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x140002ac7  lea     ecx, [rax-7]
0x140002aca  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140002ad2  inc     ecx
0x140002ad4  mov     [rsp+14F0h+var_14C0], ecx
0x140002ad8  mov     [rsp+14F0h+var_14B8], r13
0x140002add  call    cs:__imp_GetCurrentThreadId
0x140002ae3  mov     [rsp+14F0h+var_14B0], eax
0x140002ae7  mov     [rsp+14F0h+var_1498], r14
0x140002aec  mov     [rsp+14F0h+var_1490], esi
0x140002af0  mov     [rsp+14F0h+var_148C], ebx
0x140002af4  mov     [rsp+14F0h+var_14A8], r13
0x140002af9  mov     [rsp+14F0h+var_14A0], r13
0x140002afe  mov     [rbp+13F0h+var_1448], rdi
0x140002b02  mov     [rbp+13F0h+var_1440], r15
0x140002b06  mov     [rsp+14F0h+var_1488], r13
0x140002b0b  xorps   xmm0, xmm0
0x140002b0e  xor     eax, eax
0x140002b10  movups  [rbp+13F0h+var_1468], xmm0
0x140002b14  mov     [rbp+13F0h+var_1458], rax
0x140002b18  xorps   xmm1, xmm1
0x140002b1b  movups  [rsp+14F0h+var_1480], xmm1
0x140002b20  mov     [rbp+13F0h+var_1470], rax
0x140002b24  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140002b2b  test    rax, rax
0x140002b2e  jz      short loc_140002B3B
0x140002b30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002b35  mov     [rbp+13F0h+var_1450], rax
0x140002b39  jmp     short loc_140002B3F
0x140002b3b  mov     [rbp+13F0h+var_1450], r13
0x140002b3f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140002b46  test    rax, rax
0x140002b49  jz      short loc_140002B55
0x140002b4b  lea     rcx, [rsp+14F0h+var_14D0]
0x140002b50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002b55  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140002b5c  test    rax, rax
0x140002b5f  jz      short loc_140002B75
0x140002b61  mov     r8d, 400h
0x140002b67  lea     rdx, [rbp+13F0h+var_1430]
0x140002b6b  lea     rcx, [rsp+14F0h+var_14D0]
0x140002b70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002b75  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002b7c  test    rax, rax
0x140002b7f  jz      short loc_140002B8B
0x140002b81  lea     rcx, [rsp+14F0h+var_14D0]
0x140002b86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002b8b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002b92  test    rax, rax
0x140002b95  jz      short loc_140002BAD
0x140002b97  test    r12b, r12b
0x140002b9a  jnz     short loc_140002BAD
0x140002b9c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140002ba1  jnz     short loc_140002BAD
0x140002ba3  lea     rcx, [rsp+14F0h+var_14D0]
0x140002ba8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002bad  cmp     [rsp+14F0h+var_14C8], r13d
0x140002bb2  jl      short loc_140002BBA
0x140002bb4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140002bba  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x140002bc1  jnz     short loc_140002BE2
0x140002bc3  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140002bca  test    rax, rax
0x140002bcd  jz      short loc_140002BD8
0x140002bcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002bd4  test    al, al
0x140002bd6  jmp     short loc_140002BE0
0x140002bd8  call    cs:__imp_IsDebuggerPresent
0x140002bde  test    eax, eax
0x140002be0  jz      short loc_140002BEB
0x140002be2  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140002be7  mov     bl, 1
0x140002be9  jz      short loc_140002BEE
0x140002beb  mov     bl, r13b
0x140002bee  test    r12b, r12b
0x140002bf1  jnz     short loc_140002C1D
0x140002bf3  test    bl, bl
0x140002bf5  jnz     short loc_140002C1D
0x140002bf7  mov     rax, cs:g_pfnResultLoggingCallback
0x140002bfe  test    rax, rax
0x140002c01  jz      short loc_140002C7A
0x140002c03  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140002c0a  jnz     short loc_140002C7A
0x140002c0c  xor     r8d, r8d
0x140002c0f  xor     edx, edx
0x140002c11  lea     rcx, [rsp+14F0h+var_14D0]
0x140002c16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002c1b  jmp     short loc_140002C7A
0x140002c1d  mov     edi, 800h
0x140002c22  mov     rax, cs:g_pfnResultLoggingCallback
0x140002c29  test    rax, rax
0x140002c2c  jz      short loc_140002C4B
0x140002c2e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140002c35  jnz     short loc_140002C4B
0x140002c37  mov     r8d, edi
0x140002c3a  lea     rdx, [rbp+13F0h+OutputString]
0x140002c41  lea     rcx, [rsp+14F0h+var_14D0]
0x140002c46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002c4b  cmp     [rbp+13F0h+OutputString], r13w
0x140002c53  jnz     short loc_140002C69
0x140002c55  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x140002c5a  mov     rdx, rdi; wchar_t *
0x140002c5d  lea     rcx, [rbp+13F0h+OutputString]; this
0x140002c64  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x140002c69  test    bl, bl
0x140002c6b  jz      short loc_140002C7A
0x140002c6d  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x140002c74  call    cs:__imp_OutputDebugStringW
0x140002c7a  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x140002c7f  jnz     short loc_140002C8A
0x140002c81  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x140002c88  jz      short loc_140002C9C
0x140002c8a  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140002c91  test    rax, rax
0x140002c94  jz      short loc_140002C9C
0x140002c96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002c9b  nop
0x140002c9c  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x140002ca1  jz      short loc_140002CAE
0x140002ca3  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140002ca8  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x140002cae  test    r12b, r12b
0x140002cb1  jz      short loc_140002CCB
0x140002cb3  lea     rdx, [rbp+13F0h+OutputString]
0x140002cba  lea     rcx, [rsp+14F0h+var_14D0]
0x140002cbf  mov     rax, cs:g_pfnThrowPlatformException
0x140002cc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002ccb  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140002cd0  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x140002cd5  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140002cda  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
