# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800efa68`
- end: `0x1800efd0a`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `674`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800c6d34`

## callees

- `0x1800d6354`
- `0x1800efa68`
- `0x1800f0894`
- `0x1800f16d0`
- `0x1800f2088`
- `0x1800f21e4`
- `0x1801178f0`
- `0x1801179b0`
- `0x18012a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800efb1f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800efb1f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800efca4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800efca4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800efc1a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800efc1a`

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
  __int64 v36; // [rsp+C0h] [rbp-40h]
  char v37[1024]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR OutputString[2048]; // [rsp+4D0h] [rbp+3D0h] BYREF

  v36 = -2;
  memset_0(&v16, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
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
    wil::details::g_pfnGetContextAndNotifyFailure(&v16, v37, 1024);
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
0x1800efa68  push    rbp
0x1800efa6a  push    rsi
0x1800efa6b  push    rdi
0x1800efa6c  push    r14
0x1800efa6e  push    r15
0x1800efa70  lea     rbp, [rsp-13E0h]
0x1800efa78  mov     eax, 14E0h
0x1800efa7d  call    _alloca_probe
0x1800efa82  sub     rsp, rax
0x1800efa85  mov     [rbp+1400h+var_1440], 0FFFFFFFFFFFFFFFEh
0x1800efa8d  mov     [rsp+1500h+arg_10], rbx
0x1800efa95  mov     rax, cs:__security_cookie
0x1800efa9c  xor     rax, rsp
0x1800efa9f  mov     [rbp+1400h+var_30], rax
0x1800efaa6  mov     esi, edx
0x1800efaa8  mov     r14, rcx
0x1800efaab  mov     rdi, [rbp+1400h+arg_28]
0x1800efab2  xor     edx, edx; Val
0x1800efab4  mov     r8d, 98h; Size
0x1800efaba  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1800efabf  call    memset_0
0x1800efac4  nop
0x1800efac5  xor     r15d, r15d
0x1800efac8  mov     [rbp+1400h+OutputString], r15w
0x1800efad0  mov     [rbp+1400h+var_1430], r15b
0x1800efad4  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x1800efadb  mov     ecx, [rdx]; this
0x1800efadd  mov     [rsp+1500h+var_14D8], ecx
0x1800efae1  mov     eax, [rdx+4]
0x1800efae4  mov     [rsp+1500h+var_14D4], eax
0x1800efae8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800efaed  mov     ebx, eax
0x1800efaef  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800efaf7  mov     ecx, r15d
0x1800efafa  lea     eax, [r15+8]
0x1800efafe  cmp     dword ptr [rdx+8], 1
0x1800efb02  cmovz   ecx, eax
0x1800efb05  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800efb09  lea     ecx, [rax-7]
0x1800efb0c  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800efb14  inc     ecx
0x1800efb16  mov     [rsp+1500h+var_14D0], ecx
0x1800efb1a  mov     [rsp+1500h+var_14C8], r15
0x1800efb1f  call    cs:__imp_GetCurrentThreadId
0x1800efb25  mov     [rsp+1500h+var_14C0], eax
0x1800efb29  lea     rax, aWil; "wil"
0x1800efb30  mov     [rsp+1500h+var_14A8], rax
0x1800efb35  mov     [rsp+1500h+var_14A0], esi
0x1800efb39  mov     [rsp+1500h+var_149C], ebx
0x1800efb3d  mov     [rsp+1500h+var_14B8], r15
0x1800efb42  mov     [rsp+1500h+var_14B0], r15
0x1800efb47  mov     [rbp+1400h+var_1458], rdi
0x1800efb4b  mov     [rbp+1400h+var_1450], r14
0x1800efb4f  mov     [rsp+1500h+var_1498], r15
0x1800efb54  xorps   xmm0, xmm0
0x1800efb57  xor     eax, eax
0x1800efb59  movups  [rbp+1400h+var_1478], xmm0
0x1800efb5d  mov     [rbp+1400h+var_1468], rax
0x1800efb61  xorps   xmm1, xmm1
0x1800efb64  movups  [rsp+1500h+var_1490], xmm1
0x1800efb69  mov     [rbp+1400h+var_1480], rax
0x1800efb6d  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800efb74  test    rax, rax
0x1800efb77  jz      short loc_1800EFB84
0x1800efb79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efb7e  mov     [rbp+1400h+var_1460], rax
0x1800efb82  jmp     short loc_1800EFB88
0x1800efb84  mov     [rbp+1400h+var_1460], r15
0x1800efb88  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800efb8f  test    rax, rax
0x1800efb92  jz      short loc_1800EFB9E
0x1800efb94  lea     rcx, [rsp+1500h+var_14E0]
0x1800efb99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efb9e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800efba5  test    rax, rax
0x1800efba8  jz      short loc_1800EFBBE
0x1800efbaa  mov     r8d, 400h
0x1800efbb0  lea     rdx, [rbp+1400h+var_1430]
0x1800efbb4  lea     rcx, [rsp+1500h+var_14E0]
0x1800efbb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efbbe  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800efbc5  test    rax, rax
0x1800efbc8  jz      short loc_1800EFBD4
0x1800efbca  lea     rcx, [rsp+1500h+var_14E0]
0x1800efbcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efbd4  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800efbdb  test    rax, rax
0x1800efbde  jz      short loc_1800EFBF1
0x1800efbe0  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800efbe5  jnz     short loc_1800EFBF1
0x1800efbe7  lea     rcx, [rsp+1500h+var_14E0]
0x1800efbec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efbf1  cmp     [rsp+1500h+var_14D8], r15d
0x1800efbf6  jge     loc_1800EFD04
0x1800efbfc  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x1800efc03  jnz     short loc_1800EFC24
0x1800efc05  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800efc0c  test    rax, rax
0x1800efc0f  jz      short loc_1800EFC1A
0x1800efc11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efc16  test    al, al
0x1800efc18  jmp     short loc_1800EFC22
0x1800efc1a  call    cs:__imp_IsDebuggerPresent
0x1800efc20  test    eax, eax
0x1800efc22  jz      short loc_1800EFC2B
0x1800efc24  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800efc29  jz      short loc_1800EFC51
0x1800efc2b  mov     rax, cs:g_pfnResultLoggingCallback
0x1800efc32  test    rax, rax
0x1800efc35  jz      short loc_1800EFCAA
0x1800efc37  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800efc3e  jnz     short loc_1800EFCAA
0x1800efc40  xor     r8d, r8d
0x1800efc43  xor     edx, edx
0x1800efc45  lea     rcx, [rsp+1500h+var_14E0]
0x1800efc4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efc4f  jmp     short loc_1800EFCAA
0x1800efc51  mov     ebx, 800h
0x1800efc56  mov     rax, cs:g_pfnResultLoggingCallback
0x1800efc5d  test    rax, rax
0x1800efc60  jz      short loc_1800EFC7F
0x1800efc62  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800efc69  jnz     short loc_1800EFC7F
0x1800efc6b  mov     r8d, ebx
0x1800efc6e  lea     rdx, [rbp+1400h+OutputString]
0x1800efc75  lea     rcx, [rsp+1500h+var_14E0]
0x1800efc7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efc7f  cmp     [rbp+1400h+OutputString], r15w
0x1800efc87  jnz     short loc_1800EFC9D
0x1800efc89  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1800efc8e  mov     rdx, rbx; wchar_t *
0x1800efc91  lea     rcx, [rbp+1400h+OutputString]; this
0x1800efc98  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1800efc9d  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1800efca4  call    cs:__imp_OutputDebugStringW
0x1800efcaa  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1800efcaf  jnz     short loc_1800EFCBA
0x1800efcb1  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x1800efcb8  jz      short loc_1800EFCCC
0x1800efcba  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800efcc1  test    rax, rax
0x1800efcc4  jz      short loc_1800EFCCC
0x1800efcc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efccb  nop
0x1800efccc  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1800efcd1  jnz     short loc_1800EFCF9
0x1800efcd3  mov     rcx, [rbp+1400h+var_30]
0x1800efcda  xor     rcx, rsp; StackCookie
0x1800efcdd  call    __security_check_cookie
0x1800efce2  mov     rbx, [rsp+1500h+arg_10]
0x1800efcea  add     rsp, 14E0h
0x1800efcf1  pop     r15
0x1800efcf3  pop     r14
0x1800efcf5  pop     rdi
0x1800efcf6  pop     rsi
0x1800efcf7  pop     rbp
0x1800efcf8  retn
0x1800efcf9  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800efcfe  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800efd04  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
