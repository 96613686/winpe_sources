# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000e7d4`
- end: `0x18000ea68`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000a7b4`

## callees

- `0x18000e7d4`
- `0x18000f3e4`
- `0x18000ffd0`
- `0x1800107f8`
- `0x180010928`
- `0x18004c636`
- `0x18004c670`
- `0x18004c730`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e87e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e87e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000ea03`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000ea03`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000e979`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000e979`

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
0x18000e7d4  mov     [rsp-8+arg_10], rbx
0x18000e7d9  push    rbp
0x18000e7da  push    rsi
0x18000e7db  push    rdi
0x18000e7dc  push    r14
0x18000e7de  push    r15
0x18000e7e0  lea     rbp, [rsp-13D0h]
0x18000e7e8  mov     eax, 14D0h
0x18000e7ed  call    _alloca_probe
0x18000e7f2  sub     rsp, rax
0x18000e7f5  mov     rax, cs:__security_cookie
0x18000e7fc  xor     rax, rsp
0x18000e7ff  mov     [rbp+13F0h+var_30], rax
0x18000e806  mov     rdi, [rbp+13F0h+arg_28]
0x18000e80d  mov     esi, edx
0x18000e80f  mov     r14, rcx
0x18000e812  xor     edx, edx; Val
0x18000e814  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000e819  mov     r8d, 98h; Size
0x18000e81f  call    memset_0
0x18000e824  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18000e82b  xor     r15d, r15d
0x18000e82e  mov     [rbp+13F0h+OutputString], r15w
0x18000e836  mov     [rbp+13F0h+var_1430], r15b
0x18000e83a  mov     ecx, [rdx]; this
0x18000e83c  mov     eax, [rdx+4]
0x18000e83f  mov     [rsp+14F0h+var_14C8], ecx
0x18000e843  mov     [rsp+14F0h+var_14C4], eax
0x18000e847  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000e84c  cmp     dword ptr [rdx+8], 1
0x18000e850  mov     ebx, eax
0x18000e852  lea     eax, [r15+8]
0x18000e856  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x18000e85e  mov     ecx, r15d
0x18000e861  cmovz   ecx, eax
0x18000e864  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000e868  lea     ecx, [rax-7]
0x18000e86b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000e873  inc     ecx
0x18000e875  mov     [rsp+14F0h+var_14B8], r15
0x18000e87a  mov     [rsp+14F0h+var_14C0], ecx
0x18000e87e  call    cs:__imp_GetCurrentThreadId
0x18000e884  xorps   xmm0, xmm0
0x18000e887  mov     [rsp+14F0h+var_1490], esi
0x18000e88b  mov     [rsp+14F0h+var_14B0], eax
0x18000e88f  xorps   xmm1, xmm1
0x18000e892  lea     rax, aWil; "wil"
0x18000e899  mov     [rsp+14F0h+var_148C], ebx
0x18000e89d  mov     [rsp+14F0h+var_1498], rax
0x18000e8a2  xor     eax, eax
0x18000e8a4  mov     [rbp+13F0h+var_1458], rax
0x18000e8a8  mov     [rbp+13F0h+var_1470], rax
0x18000e8ac  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000e8b3  mov     [rsp+14F0h+var_14A8], r15
0x18000e8b8  mov     [rsp+14F0h+var_14A0], r15
0x18000e8bd  mov     [rbp+13F0h+var_1448], rdi
0x18000e8c1  mov     [rbp+13F0h+var_1440], r14
0x18000e8c5  mov     [rsp+14F0h+var_1488], r15
0x18000e8ca  movups  [rbp+13F0h+var_1468], xmm0
0x18000e8ce  movups  [rsp+14F0h+var_1480], xmm1
0x18000e8d3  test    rax, rax
0x18000e8d6  jz      short loc_18000E8E3
0x18000e8d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8dd  mov     [rbp+13F0h+var_1450], rax
0x18000e8e1  jmp     short loc_18000E8E7
0x18000e8e3  mov     [rbp+13F0h+var_1450], r15
0x18000e8e7  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000e8ee  test    rax, rax
0x18000e8f1  jz      short loc_18000E8FD
0x18000e8f3  lea     rcx, [rsp+14F0h+var_14D0]
0x18000e8f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8fd  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000e904  test    rax, rax
0x18000e907  jz      short loc_18000E91D
0x18000e909  mov     r8d, 400h
0x18000e90f  lea     rdx, [rbp+13F0h+var_1430]
0x18000e913  lea     rcx, [rsp+14F0h+var_14D0]
0x18000e918  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e91d  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000e924  test    rax, rax
0x18000e927  jz      short loc_18000E933
0x18000e929  lea     rcx, [rsp+14F0h+var_14D0]
0x18000e92e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e933  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000e93a  test    rax, rax
0x18000e93d  jz      short loc_18000E950
0x18000e93f  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000e944  jnz     short loc_18000E950
0x18000e946  lea     rcx, [rsp+14F0h+var_14D0]
0x18000e94b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e950  cmp     [rsp+14F0h+var_14C8], r15d
0x18000e955  jge     loc_18000EA57
0x18000e95b  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18000e962  jnz     short loc_18000E983
0x18000e964  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000e96b  test    rax, rax
0x18000e96e  jz      short loc_18000E979
0x18000e970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e975  test    al, al
0x18000e977  jmp     short loc_18000E981
0x18000e979  call    cs:__imp_IsDebuggerPresent
0x18000e97f  test    eax, eax
0x18000e981  jz      short loc_18000E98A
0x18000e983  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000e988  jz      short loc_18000E9B0
0x18000e98a  mov     rax, cs:g_pfnResultLoggingCallback
0x18000e991  test    rax, rax
0x18000e994  jz      short loc_18000EA09
0x18000e996  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000e99d  jnz     short loc_18000EA09
0x18000e99f  xor     r8d, r8d
0x18000e9a2  lea     rcx, [rsp+14F0h+var_14D0]
0x18000e9a7  xor     edx, edx
0x18000e9a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9ae  jmp     short loc_18000EA09
0x18000e9b0  mov     rax, cs:g_pfnResultLoggingCallback
0x18000e9b7  mov     ebx, 800h
0x18000e9bc  test    rax, rax
0x18000e9bf  jz      short loc_18000E9DE
0x18000e9c1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000e9c8  jnz     short loc_18000E9DE
0x18000e9ca  mov     r8d, ebx
0x18000e9cd  lea     rdx, [rbp+13F0h+OutputString]
0x18000e9d4  lea     rcx, [rsp+14F0h+var_14D0]
0x18000e9d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9de  cmp     [rbp+13F0h+OutputString], r15w
0x18000e9e6  jnz     short loc_18000E9FC
0x18000e9e8  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000e9ed  mov     rdx, rbx; unsigned __int16 *
0x18000e9f0  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000e9f7  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000e9fc  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000ea03  call    cs:__imp_OutputDebugStringW
0x18000ea09  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000ea0e  jnz     short loc_18000EA19
0x18000ea10  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18000ea17  jz      short loc_18000EA2A
0x18000ea19  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000ea20  test    rax, rax
0x18000ea23  jz      short loc_18000EA2A
0x18000ea25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea2a  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18000ea2f  jnz     short loc_18000EA5D
0x18000ea31  mov     rcx, [rbp+13F0h+var_30]
0x18000ea38  xor     rcx, rsp; StackCookie
0x18000ea3b  call    __security_check_cookie
0x18000ea40  mov     rbx, [rsp+14F0h+arg_10]
0x18000ea48  add     rsp, 14D0h
0x18000ea4f  pop     r15
0x18000ea51  pop     r14
0x18000ea53  pop     rdi
0x18000ea54  pop     rsi
0x18000ea55  pop     rbp
0x18000ea56  retn
0x18000ea57  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000ea5d  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000ea62  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
