# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180008a54`
- end: `0x180008ce8`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000853c`

## callees

- `0x180008a54`
- `0x1800098cc`
- `0x18000a5d8`
- `0x18000b128`
- `0x18000b204`
- `0x18000c392`
- `0x18000c3c0`
- `0x18000c450`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008bf9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008bf9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008c83`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008c83`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008afe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008afe`

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
0x180008a54  mov     [rsp-8+arg_10], rbx
0x180008a59  push    rbp
0x180008a5a  push    rsi
0x180008a5b  push    rdi
0x180008a5c  push    r14
0x180008a5e  push    r15
0x180008a60  lea     rbp, [rsp-13D0h]
0x180008a68  mov     eax, 14D0h
0x180008a6d  call    _alloca_probe
0x180008a72  sub     rsp, rax
0x180008a75  mov     rax, cs:__security_cookie
0x180008a7c  xor     rax, rsp
0x180008a7f  mov     [rbp+13F0h+var_30], rax
0x180008a86  mov     rdi, [rbp+13F0h+arg_28]
0x180008a8d  mov     esi, edx
0x180008a8f  mov     r14, rcx
0x180008a92  xor     edx, edx; Val
0x180008a94  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180008a99  mov     r8d, 98h; Size
0x180008a9f  call    memset_0
0x180008aa4  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180008aab  xor     r15d, r15d
0x180008aae  mov     [rbp+13F0h+OutputString], r15w
0x180008ab6  mov     [rbp+13F0h+var_1430], r15b
0x180008aba  mov     ecx, [rdx]; this
0x180008abc  mov     eax, [rdx+4]
0x180008abf  mov     [rsp+14F0h+var_14C8], ecx
0x180008ac3  mov     [rsp+14F0h+var_14C4], eax
0x180008ac7  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180008acc  cmp     dword ptr [rdx+8], 1
0x180008ad0  mov     ebx, eax
0x180008ad2  lea     eax, [r15+8]
0x180008ad6  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180008ade  mov     ecx, r15d
0x180008ae1  cmovz   ecx, eax
0x180008ae4  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180008ae8  lea     ecx, [rax-7]
0x180008aeb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180008af3  inc     ecx
0x180008af5  mov     [rsp+14F0h+var_14B8], r15
0x180008afa  mov     [rsp+14F0h+var_14C0], ecx
0x180008afe  call    cs:__imp_GetCurrentThreadId
0x180008b04  xorps   xmm0, xmm0
0x180008b07  mov     [rsp+14F0h+var_1490], esi
0x180008b0b  mov     [rsp+14F0h+var_14B0], eax
0x180008b0f  xorps   xmm1, xmm1
0x180008b12  lea     rax, aWil; "wil"
0x180008b19  mov     [rsp+14F0h+var_148C], ebx
0x180008b1d  mov     [rsp+14F0h+var_1498], rax
0x180008b22  xor     eax, eax
0x180008b24  mov     [rbp+13F0h+var_1458], rax
0x180008b28  mov     [rbp+13F0h+var_1470], rax
0x180008b2c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180008b33  mov     [rsp+14F0h+var_14A8], r15
0x180008b38  mov     [rsp+14F0h+var_14A0], r15
0x180008b3d  mov     [rbp+13F0h+var_1448], rdi
0x180008b41  mov     [rbp+13F0h+var_1440], r14
0x180008b45  mov     [rsp+14F0h+var_1488], r15
0x180008b4a  movups  [rbp+13F0h+var_1468], xmm0
0x180008b4e  movups  [rsp+14F0h+var_1480], xmm1
0x180008b53  test    rax, rax
0x180008b56  jz      short loc_180008B63
0x180008b58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b5d  mov     [rbp+13F0h+var_1450], rax
0x180008b61  jmp     short loc_180008B67
0x180008b63  mov     [rbp+13F0h+var_1450], r15
0x180008b67  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180008b6e  test    rax, rax
0x180008b71  jz      short loc_180008B7D
0x180008b73  lea     rcx, [rsp+14F0h+var_14D0]
0x180008b78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b7d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180008b84  test    rax, rax
0x180008b87  jz      short loc_180008B9D
0x180008b89  mov     r8d, 400h
0x180008b8f  lea     rdx, [rbp+13F0h+var_1430]
0x180008b93  lea     rcx, [rsp+14F0h+var_14D0]
0x180008b98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b9d  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008ba4  test    rax, rax
0x180008ba7  jz      short loc_180008BB3
0x180008ba9  lea     rcx, [rsp+14F0h+var_14D0]
0x180008bae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bb3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008bba  test    rax, rax
0x180008bbd  jz      short loc_180008BD0
0x180008bbf  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180008bc4  jnz     short loc_180008BD0
0x180008bc6  lea     rcx, [rsp+14F0h+var_14D0]
0x180008bcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bd0  cmp     [rsp+14F0h+var_14C8], r15d
0x180008bd5  jge     loc_180008CD7
0x180008bdb  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180008be2  jnz     short loc_180008C03
0x180008be4  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180008beb  test    rax, rax
0x180008bee  jz      short loc_180008BF9
0x180008bf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bf5  test    al, al
0x180008bf7  jmp     short loc_180008C01
0x180008bf9  call    cs:__imp_IsDebuggerPresent
0x180008bff  test    eax, eax
0x180008c01  jz      short loc_180008C0A
0x180008c03  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180008c08  jz      short loc_180008C30
0x180008c0a  mov     rax, cs:g_pfnResultLoggingCallback
0x180008c11  test    rax, rax
0x180008c14  jz      short loc_180008C89
0x180008c16  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180008c1d  jnz     short loc_180008C89
0x180008c1f  xor     r8d, r8d
0x180008c22  lea     rcx, [rsp+14F0h+var_14D0]
0x180008c27  xor     edx, edx
0x180008c29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c2e  jmp     short loc_180008C89
0x180008c30  mov     rax, cs:g_pfnResultLoggingCallback
0x180008c37  mov     ebx, 800h
0x180008c3c  test    rax, rax
0x180008c3f  jz      short loc_180008C5E
0x180008c41  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180008c48  jnz     short loc_180008C5E
0x180008c4a  mov     r8d, ebx
0x180008c4d  lea     rdx, [rbp+13F0h+OutputString]
0x180008c54  lea     rcx, [rsp+14F0h+var_14D0]
0x180008c59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c5e  cmp     [rbp+13F0h+OutputString], r15w
0x180008c66  jnz     short loc_180008C7C
0x180008c68  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180008c6d  mov     rdx, rbx; unsigned __int16 *
0x180008c70  lea     rcx, [rbp+13F0h+OutputString]; this
0x180008c77  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180008c7c  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180008c83  call    cs:__imp_OutputDebugStringW
0x180008c89  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180008c8e  jnz     short loc_180008C99
0x180008c90  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180008c97  jz      short loc_180008CAA
0x180008c99  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180008ca0  test    rax, rax
0x180008ca3  jz      short loc_180008CAA
0x180008ca5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008caa  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180008caf  jnz     short loc_180008CDD
0x180008cb1  mov     rcx, [rbp+13F0h+var_30]
0x180008cb8  xor     rcx, rsp; StackCookie
0x180008cbb  call    __security_check_cookie
0x180008cc0  mov     rbx, [rsp+14F0h+arg_10]
0x180008cc8  add     rsp, 14D0h
0x180008ccf  pop     r15
0x180008cd1  pop     r14
0x180008cd3  pop     rdi
0x180008cd4  pop     rsi
0x180008cd5  pop     rbp
0x180008cd6  retn
0x180008cd7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180008cdd  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180008ce2  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
