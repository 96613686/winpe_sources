# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180007e24`
- end: `0x1800080b8`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180007dc8`

## callees

- `0x180007e24`
- `0x180008174`
- `0x180008824`
- `0x1800089e8`
- `0x180008c94`
- `0x18000a7ce`
- `0x18000a800`
- `0x18000a890`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008053`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008053`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007fc9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007fc9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007ece`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007ece`

## string_xrefs

- `0x180007ee2`: `onecore\ds\security\cryptoapi\crypttpmeksvc\tpmeksvc.cpp`

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
  v28 = "onecore\\ds\\security\\cryptoapi\\crypttpmeksvc\\tpmeksvc.cpp";
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
0x180007e24  mov     [rsp-8+arg_10], rbx
0x180007e29  push    rbp
0x180007e2a  push    rsi
0x180007e2b  push    rdi
0x180007e2c  push    r14
0x180007e2e  push    r15
0x180007e30  lea     rbp, [rsp-13D0h]
0x180007e38  mov     eax, 14D0h
0x180007e3d  call    _alloca_probe
0x180007e42  sub     rsp, rax
0x180007e45  mov     rax, cs:__security_cookie
0x180007e4c  xor     rax, rsp
0x180007e4f  mov     [rbp+13F0h+var_30], rax
0x180007e56  mov     rdi, [rbp+13F0h+arg_28]
0x180007e5d  mov     esi, edx
0x180007e5f  mov     r14, rcx
0x180007e62  xor     edx, edx; Val
0x180007e64  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180007e69  mov     r8d, 98h; Size
0x180007e6f  call    memset_0
0x180007e74  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180007e7b  xor     r15d, r15d
0x180007e7e  mov     [rbp+13F0h+OutputString], r15w
0x180007e86  mov     [rbp+13F0h+var_1430], r15b
0x180007e8a  mov     ecx, [rdx]; this
0x180007e8c  mov     eax, [rdx+4]
0x180007e8f  mov     [rsp+14F0h+var_14C8], ecx
0x180007e93  mov     [rsp+14F0h+var_14C4], eax
0x180007e97  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180007e9c  cmp     dword ptr [rdx+8], 1
0x180007ea0  mov     ebx, eax
0x180007ea2  lea     eax, [r15+8]
0x180007ea6  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180007eae  mov     ecx, r15d
0x180007eb1  cmovz   ecx, eax
0x180007eb4  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180007eb8  lea     ecx, [rax-7]
0x180007ebb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180007ec3  inc     ecx
0x180007ec5  mov     [rsp+14F0h+var_14B8], r15
0x180007eca  mov     [rsp+14F0h+var_14C0], ecx
0x180007ece  call    cs:__imp_GetCurrentThreadId
0x180007ed4  xorps   xmm0, xmm0
0x180007ed7  mov     [rsp+14F0h+var_1490], esi
0x180007edb  mov     [rsp+14F0h+var_14B0], eax
0x180007edf  xorps   xmm1, xmm1
0x180007ee2  lea     rax, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\crypt"...
0x180007ee9  mov     [rsp+14F0h+var_148C], ebx
0x180007eed  mov     [rsp+14F0h+var_1498], rax
0x180007ef2  xor     eax, eax
0x180007ef4  mov     [rbp+13F0h+var_1458], rax
0x180007ef8  mov     [rbp+13F0h+var_1470], rax
0x180007efc  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180007f03  mov     [rsp+14F0h+var_14A8], r15
0x180007f08  mov     [rsp+14F0h+var_14A0], r15
0x180007f0d  mov     [rbp+13F0h+var_1448], rdi
0x180007f11  mov     [rbp+13F0h+var_1440], r14
0x180007f15  mov     [rsp+14F0h+var_1488], r15
0x180007f1a  movups  [rbp+13F0h+var_1468], xmm0
0x180007f1e  movups  [rsp+14F0h+var_1480], xmm1
0x180007f23  test    rax, rax
0x180007f26  jz      short loc_180007F33
0x180007f28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f2d  mov     [rbp+13F0h+var_1450], rax
0x180007f31  jmp     short loc_180007F37
0x180007f33  mov     [rbp+13F0h+var_1450], r15
0x180007f37  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180007f3e  test    rax, rax
0x180007f41  jz      short loc_180007F4D
0x180007f43  lea     rcx, [rsp+14F0h+var_14D0]
0x180007f48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f4d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180007f54  test    rax, rax
0x180007f57  jz      short loc_180007F6D
0x180007f59  mov     r8d, 400h
0x180007f5f  lea     rdx, [rbp+13F0h+var_1430]
0x180007f63  lea     rcx, [rsp+14F0h+var_14D0]
0x180007f68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f6d  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007f74  test    rax, rax
0x180007f77  jz      short loc_180007F83
0x180007f79  lea     rcx, [rsp+14F0h+var_14D0]
0x180007f7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f83  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007f8a  test    rax, rax
0x180007f8d  jz      short loc_180007FA0
0x180007f8f  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180007f94  jnz     short loc_180007FA0
0x180007f96  lea     rcx, [rsp+14F0h+var_14D0]
0x180007f9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fa0  cmp     [rsp+14F0h+var_14C8], r15d
0x180007fa5  jge     loc_1800080A7
0x180007fab  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180007fb2  jnz     short loc_180007FD3
0x180007fb4  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180007fbb  test    rax, rax
0x180007fbe  jz      short loc_180007FC9
0x180007fc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fc5  test    al, al
0x180007fc7  jmp     short loc_180007FD1
0x180007fc9  call    cs:__imp_IsDebuggerPresent
0x180007fcf  test    eax, eax
0x180007fd1  jz      short loc_180007FDA
0x180007fd3  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180007fd8  jz      short loc_180008000
0x180007fda  mov     rax, cs:g_pfnResultLoggingCallback
0x180007fe1  test    rax, rax
0x180007fe4  jz      short loc_180008059
0x180007fe6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180007fed  jnz     short loc_180008059
0x180007fef  xor     r8d, r8d
0x180007ff2  lea     rcx, [rsp+14F0h+var_14D0]
0x180007ff7  xor     edx, edx
0x180007ff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ffe  jmp     short loc_180008059
0x180008000  mov     rax, cs:g_pfnResultLoggingCallback
0x180008007  mov     ebx, 800h
0x18000800c  test    rax, rax
0x18000800f  jz      short loc_18000802E
0x180008011  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180008018  jnz     short loc_18000802E
0x18000801a  mov     r8d, ebx
0x18000801d  lea     rdx, [rbp+13F0h+OutputString]
0x180008024  lea     rcx, [rsp+14F0h+var_14D0]
0x180008029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000802e  cmp     [rbp+13F0h+OutputString], r15w
0x180008036  jnz     short loc_18000804C
0x180008038  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000803d  mov     rdx, rbx; unsigned __int16 *
0x180008040  lea     rcx, [rbp+13F0h+OutputString]; this
0x180008047  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000804c  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180008053  call    cs:__imp_OutputDebugStringW
0x180008059  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000805e  jnz     short loc_180008069
0x180008060  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180008067  jz      short loc_18000807A
0x180008069  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180008070  test    rax, rax
0x180008073  jz      short loc_18000807A
0x180008075  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000807a  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18000807f  jnz     short loc_1800080AD
0x180008081  mov     rcx, [rbp+13F0h+var_30]
0x180008088  xor     rcx, rsp; StackCookie
0x18000808b  call    __security_check_cookie
0x180008090  mov     rbx, [rsp+14F0h+arg_10]
0x180008098  add     rsp, 14D0h
0x18000809f  pop     r15
0x1800080a1  pop     r14
0x1800080a3  pop     rdi
0x1800080a4  pop     rsi
0x1800080a5  pop     rbp
0x1800080a6  retn
0x1800080a7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800080ad  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800080b2  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
