# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800079f8`
- end: `0x180007c8e`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800074d8`

## callees

- `0x1800079f8`
- `0x1800099e4`
- `0x18000aea8`
- `0x18000cd20`
- `0x18000cedc`
- `0x180015cbe`
- `0x180015cf0`
- `0x180015db0`
- `0x180017010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180007aa3`
- `KERNEL32!GetCurrentThreadId` at `0x180007aa3`
- `KERNEL32!OutputDebugStringW` at `0x180007c28`
- `KERNEL32!OutputDebugStringW` at `0x180007c28`
- `KERNEL32!IsDebuggerPresent` at `0x180007b9e`
- `KERNEL32!IsDebuggerPresent` at `0x180007b9e`

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
0x1800079f8  mov     [rsp-8+arg_10], rbx
0x1800079fd  push    rbp
0x1800079fe  push    rsi
0x1800079ff  push    rdi
0x180007a00  push    r14
0x180007a02  push    r15
0x180007a04  lea     rbp, [rsp-13D0h]
0x180007a0c  mov     eax, 14D0h
0x180007a11  call    _alloca_probe
0x180007a16  sub     rsp, rax
0x180007a19  mov     rax, cs:__security_cookie
0x180007a20  xor     rax, rsp
0x180007a23  mov     [rbp+13F0h+var_30], rax
0x180007a2a  mov     esi, edx
0x180007a2c  mov     r14, rcx
0x180007a2f  mov     rdi, [rbp+13F0h+arg_28]
0x180007a36  xor     edx, edx; Val
0x180007a38  mov     r8d, 98h; Size
0x180007a3e  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180007a43  call    memset_0
0x180007a48  nop
0x180007a49  xor     r15d, r15d
0x180007a4c  mov     [rbp+13F0h+OutputString], r15w
0x180007a54  mov     [rbp+13F0h+var_1430], r15b
0x180007a58  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180007a5f  mov     ecx, [rdx]; this
0x180007a61  mov     [rsp+14F0h+var_14C8], ecx
0x180007a65  mov     eax, [rdx+4]
0x180007a68  mov     [rsp+14F0h+var_14C4], eax
0x180007a6c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180007a71  mov     ebx, eax
0x180007a73  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180007a7b  mov     ecx, r15d
0x180007a7e  lea     eax, [r15+8]
0x180007a82  cmp     dword ptr [rdx+8], 1
0x180007a86  cmovz   ecx, eax
0x180007a89  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180007a8d  lea     ecx, [rax-7]
0x180007a90  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180007a98  inc     ecx
0x180007a9a  mov     [rsp+14F0h+var_14C0], ecx
0x180007a9e  mov     [rsp+14F0h+var_14B8], r15
0x180007aa3  call    cs:__imp_GetCurrentThreadId
0x180007aa9  mov     [rsp+14F0h+var_14B0], eax
0x180007aad  lea     rax, aWil; "wil"
0x180007ab4  mov     [rsp+14F0h+var_1498], rax
0x180007ab9  mov     [rsp+14F0h+var_1490], esi
0x180007abd  mov     [rsp+14F0h+var_148C], ebx
0x180007ac1  mov     [rsp+14F0h+var_14A8], r15
0x180007ac6  mov     [rsp+14F0h+var_14A0], r15
0x180007acb  mov     [rbp+13F0h+var_1448], rdi
0x180007acf  mov     [rbp+13F0h+var_1440], r14
0x180007ad3  mov     [rsp+14F0h+var_1488], r15
0x180007ad8  xorps   xmm0, xmm0
0x180007adb  xor     eax, eax
0x180007add  movups  [rbp+13F0h+var_1468], xmm0
0x180007ae1  mov     [rbp+13F0h+var_1458], rax
0x180007ae5  xorps   xmm1, xmm1
0x180007ae8  movups  [rsp+14F0h+var_1480], xmm1
0x180007aed  mov     [rbp+13F0h+var_1470], rax
0x180007af1  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180007af8  test    rax, rax
0x180007afb  jz      short loc_180007B08
0x180007afd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b02  mov     [rbp+13F0h+var_1450], rax
0x180007b06  jmp     short loc_180007B0C
0x180007b08  mov     [rbp+13F0h+var_1450], r15
0x180007b0c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180007b13  test    rax, rax
0x180007b16  jz      short loc_180007B22
0x180007b18  lea     rcx, [rsp+14F0h+var_14D0]
0x180007b1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b22  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180007b29  test    rax, rax
0x180007b2c  jz      short loc_180007B42
0x180007b2e  mov     r8d, 400h
0x180007b34  lea     rdx, [rbp+13F0h+var_1430]
0x180007b38  lea     rcx, [rsp+14F0h+var_14D0]
0x180007b3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b42  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007b49  test    rax, rax
0x180007b4c  jz      short loc_180007B58
0x180007b4e  lea     rcx, [rsp+14F0h+var_14D0]
0x180007b53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b58  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007b5f  test    rax, rax
0x180007b62  jz      short loc_180007B75
0x180007b64  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180007b69  jnz     short loc_180007B75
0x180007b6b  lea     rcx, [rsp+14F0h+var_14D0]
0x180007b70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b75  cmp     [rsp+14F0h+var_14C8], r15d
0x180007b7a  jge     loc_180007C88
0x180007b80  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180007b87  jnz     short loc_180007BA8
0x180007b89  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180007b90  test    rax, rax
0x180007b93  jz      short loc_180007B9E
0x180007b95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b9a  test    al, al
0x180007b9c  jmp     short loc_180007BA6
0x180007b9e  call    cs:__imp_IsDebuggerPresent
0x180007ba4  test    eax, eax
0x180007ba6  jz      short loc_180007BAF
0x180007ba8  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180007bad  jz      short loc_180007BD5
0x180007baf  mov     rax, cs:g_pfnResultLoggingCallback
0x180007bb6  test    rax, rax
0x180007bb9  jz      short loc_180007C2E
0x180007bbb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180007bc2  jnz     short loc_180007C2E
0x180007bc4  xor     r8d, r8d
0x180007bc7  xor     edx, edx
0x180007bc9  lea     rcx, [rsp+14F0h+var_14D0]
0x180007bce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bd3  jmp     short loc_180007C2E
0x180007bd5  mov     ebx, 800h
0x180007bda  mov     rax, cs:g_pfnResultLoggingCallback
0x180007be1  test    rax, rax
0x180007be4  jz      short loc_180007C03
0x180007be6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180007bed  jnz     short loc_180007C03
0x180007bef  mov     r8d, ebx
0x180007bf2  lea     rdx, [rbp+13F0h+OutputString]
0x180007bf9  lea     rcx, [rsp+14F0h+var_14D0]
0x180007bfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c03  cmp     [rbp+13F0h+OutputString], r15w
0x180007c0b  jnz     short loc_180007C21
0x180007c0d  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180007c12  mov     rdx, rbx; unsigned __int16 *
0x180007c15  lea     rcx, [rbp+13F0h+OutputString]; this
0x180007c1c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180007c21  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180007c28  call    cs:__imp_OutputDebugStringW
0x180007c2e  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180007c33  jnz     short loc_180007C3E
0x180007c35  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180007c3c  jz      short loc_180007C50
0x180007c3e  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180007c45  test    rax, rax
0x180007c48  jz      short loc_180007C50
0x180007c4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c4f  nop
0x180007c50  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180007c55  jnz     short loc_180007C7D
0x180007c57  mov     rcx, [rbp+13F0h+var_30]
0x180007c5e  xor     rcx, rsp; StackCookie
0x180007c61  call    __security_check_cookie
0x180007c66  mov     rbx, [rsp+14F0h+arg_10]
0x180007c6e  add     rsp, 14D0h
0x180007c75  pop     r15
0x180007c77  pop     r14
0x180007c79  pop     rdi
0x180007c7a  pop     rsi
0x180007c7b  pop     rbp
0x180007c7c  retn
0x180007c7d  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180007c82  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180007c88  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
