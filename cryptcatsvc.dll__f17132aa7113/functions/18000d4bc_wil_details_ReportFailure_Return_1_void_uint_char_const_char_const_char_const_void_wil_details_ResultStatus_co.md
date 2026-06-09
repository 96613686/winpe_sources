# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000d4bc`
- end: `0x18000d75e`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `674`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000b33c`

## callees

- `0x18000be40`
- `0x18000c7e8`
- `0x18000d4bc`
- `0x18000ebd4`
- `0x180010398`
- `0x180011c28`
- `0x180011e40`
- `0x180021550`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d574`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d574`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000d66e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000d66e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000d6f8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000d6f8`

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
  int v16; // [rsp+30h] [rbp-D0h] BYREF
  int v17; // [rsp+34h] [rbp-CCh]
  int v18; // [rsp+38h] [rbp-C8h]
  int v19; // [rsp+3Ch] [rbp-C4h]
  signed __int32 v20; // [rsp+40h] [rbp-C0h]
  __int64 v21; // [rsp+48h] [rbp-B8h]
  DWORD CurrentThreadId; // [rsp+50h] [rbp-B0h]
  __int64 v23; // [rsp+58h] [rbp-A8h]
  __int64 v24; // [rsp+60h] [rbp-A0h]
  const char *v25; // [rsp+68h] [rbp-98h]
  int v26; // [rsp+70h] [rbp-90h]
  int v27; // [rsp+74h] [rbp-8Ch]
  __int64 v28; // [rsp+78h] [rbp-88h]
  __int128 v29; // [rsp+80h] [rbp-80h]
  __int64 v30; // [rsp+90h] [rbp-70h]
  __int128 v31; // [rsp+98h] [rbp-68h]
  __int64 v32; // [rsp+A8h] [rbp-58h]
  __int64 ModuleName; // [rsp+B0h] [rbp-50h]
  __int64 v34; // [rsp+B8h] [rbp-48h]
  __int64 v35; // [rsp+C0h] [rbp-40h]
  char v36[1024]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR OutputString[2048]; // [rsp+4D0h] [rbp+3D0h] BYREF

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
0x18000d4bc  push    rbp
0x18000d4be  push    rsi
0x18000d4bf  push    rdi
0x18000d4c0  push    r14
0x18000d4c2  push    r15
0x18000d4c4  lea     rbp, [rsp-13E0h]
0x18000d4cc  mov     eax, 14E0h
0x18000d4d1  call    _alloca_probe
0x18000d4d6  sub     rsp, rax
0x18000d4d9  mov     [rsp+1500h+var_14E0], 0FFFFFFFFFFFFFFFEh
0x18000d4e2  mov     [rsp+1500h+arg_10], rbx
0x18000d4ea  mov     rax, cs:__security_cookie
0x18000d4f1  xor     rax, rsp
0x18000d4f4  mov     [rbp+1400h+var_30], rax
0x18000d4fb  mov     esi, edx
0x18000d4fd  mov     r14, rcx
0x18000d500  mov     rdi, [rbp+1400h+arg_28]
0x18000d507  xor     edx, edx; Val
0x18000d509  mov     r8d, 98h; Size
0x18000d50f  lea     rcx, [rsp+1500h+var_14D0]; void *
0x18000d514  call    memset_0
0x18000d519  nop
0x18000d51a  xor     r15d, r15d
0x18000d51d  mov     [rbp+1400h+OutputString], r15w
0x18000d525  mov     [rbp+1400h+var_1430], r15b
0x18000d529  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x18000d530  mov     ecx, [rdx]; this
0x18000d532  mov     [rsp+1500h+var_14C8], ecx
0x18000d536  mov     eax, [rdx+4]
0x18000d539  mov     [rsp+1500h+var_14C4], eax
0x18000d53d  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000d542  mov     ebx, eax
0x18000d544  mov     dword ptr [rsp+1500h+var_14D0], 1
0x18000d54c  mov     ecx, r15d
0x18000d54f  lea     eax, [r15+8]
0x18000d553  cmp     dword ptr [rdx+8], 1
0x18000d557  cmovz   ecx, eax
0x18000d55a  mov     dword ptr [rsp+1500h+var_14D0+4], ecx
0x18000d55e  lea     ecx, [rax-7]
0x18000d561  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000d569  inc     ecx
0x18000d56b  mov     [rsp+1500h+var_14C0], ecx
0x18000d56f  mov     [rsp+1500h+var_14B8], r15
0x18000d574  call    cs:__imp_GetCurrentThreadId
0x18000d57a  mov     [rsp+1500h+var_14B0], eax
0x18000d57e  lea     rax, aWil; "wil"
0x18000d585  mov     [rsp+1500h+var_1498], rax
0x18000d58a  mov     [rsp+1500h+var_1490], esi
0x18000d58e  mov     [rsp+1500h+var_148C], ebx
0x18000d592  mov     [rsp+1500h+var_14A8], r15
0x18000d597  mov     [rsp+1500h+var_14A0], r15
0x18000d59c  mov     [rbp+1400h+var_1448], rdi
0x18000d5a0  mov     [rbp+1400h+var_1440], r14
0x18000d5a4  mov     [rsp+1500h+var_1488], r15
0x18000d5a9  xorps   xmm0, xmm0
0x18000d5ac  xor     eax, eax
0x18000d5ae  movups  [rbp+1400h+var_1468], xmm0
0x18000d5b2  mov     [rbp+1400h+var_1458], rax
0x18000d5b6  xorps   xmm1, xmm1
0x18000d5b9  movups  [rbp+1400h+var_1480], xmm1
0x18000d5bd  mov     [rbp+1400h+var_1470], rax
0x18000d5c1  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000d5c8  test    rax, rax
0x18000d5cb  jz      short loc_18000D5D8
0x18000d5cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5d2  mov     [rbp+1400h+var_1450], rax
0x18000d5d6  jmp     short loc_18000D5DC
0x18000d5d8  mov     [rbp+1400h+var_1450], r15
0x18000d5dc  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000d5e3  test    rax, rax
0x18000d5e6  jz      short loc_18000D5F2
0x18000d5e8  lea     rcx, [rsp+1500h+var_14D0]
0x18000d5ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5f2  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000d5f9  test    rax, rax
0x18000d5fc  jz      short loc_18000D612
0x18000d5fe  mov     r8d, 400h
0x18000d604  lea     rdx, [rbp+1400h+var_1430]
0x18000d608  lea     rcx, [rsp+1500h+var_14D0]
0x18000d60d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d612  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000d619  test    rax, rax
0x18000d61c  jz      short loc_18000D628
0x18000d61e  lea     rcx, [rsp+1500h+var_14D0]
0x18000d623  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d628  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000d62f  test    rax, rax
0x18000d632  jz      short loc_18000D645
0x18000d634  test    byte ptr [rsp+1500h+var_14D0+4], 2
0x18000d639  jnz     short loc_18000D645
0x18000d63b  lea     rcx, [rsp+1500h+var_14D0]
0x18000d640  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d645  cmp     [rsp+1500h+var_14C8], r15d
0x18000d64a  jge     loc_18000D758
0x18000d650  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18000d657  jnz     short loc_18000D678
0x18000d659  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000d660  test    rax, rax
0x18000d663  jz      short loc_18000D66E
0x18000d665  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d66a  test    al, al
0x18000d66c  jmp     short loc_18000D676
0x18000d66e  call    cs:__imp_IsDebuggerPresent
0x18000d674  test    eax, eax
0x18000d676  jz      short loc_18000D67F
0x18000d678  test    byte ptr [rsp+1500h+var_14D0+4], 2
0x18000d67d  jz      short loc_18000D6A5
0x18000d67f  mov     rax, cs:g_pfnResultLoggingCallback
0x18000d686  test    rax, rax
0x18000d689  jz      short loc_18000D6FE
0x18000d68b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000d692  jnz     short loc_18000D6FE
0x18000d694  xor     r8d, r8d
0x18000d697  xor     edx, edx
0x18000d699  lea     rcx, [rsp+1500h+var_14D0]
0x18000d69e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6a3  jmp     short loc_18000D6FE
0x18000d6a5  mov     ebx, 800h
0x18000d6aa  mov     rax, cs:g_pfnResultLoggingCallback
0x18000d6b1  test    rax, rax
0x18000d6b4  jz      short loc_18000D6D3
0x18000d6b6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000d6bd  jnz     short loc_18000D6D3
0x18000d6bf  mov     r8d, ebx
0x18000d6c2  lea     rdx, [rbp+1400h+OutputString]
0x18000d6c9  lea     rcx, [rsp+1500h+var_14D0]
0x18000d6ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6d3  cmp     [rbp+1400h+OutputString], r15w
0x18000d6db  jnz     short loc_18000D6F1
0x18000d6dd  lea     r8, [rsp+1500h+var_14D0]; unsigned __int64
0x18000d6e2  mov     rdx, rbx; unsigned __int16 *
0x18000d6e5  lea     rcx, [rbp+1400h+OutputString]; this
0x18000d6ec  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000d6f1  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18000d6f8  call    cs:__imp_OutputDebugStringW
0x18000d6fe  test    byte ptr [rsp+1500h+var_14D0+4], 4
0x18000d703  jnz     short loc_18000D70E
0x18000d705  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18000d70c  jz      short loc_18000D720
0x18000d70e  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000d715  test    rax, rax
0x18000d718  jz      short loc_18000D720
0x18000d71a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d71f  nop
0x18000d720  test    byte ptr [rsp+1500h+var_14D0+4], 1
0x18000d725  jnz     short loc_18000D74D
0x18000d727  mov     rcx, [rbp+1400h+var_30]
0x18000d72e  xor     rcx, rsp; StackCookie
0x18000d731  call    __security_check_cookie
0x18000d736  mov     rbx, [rsp+1500h+arg_10]
0x18000d73e  add     rsp, 14E0h
0x18000d745  pop     r15
0x18000d747  pop     r14
0x18000d749  pop     rdi
0x18000d74a  pop     rsi
0x18000d74b  pop     rbp
0x18000d74c  retn
0x18000d74d  lea     rcx, [rsp+1500h+var_14D0]; this
0x18000d752  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000d758  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
