# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x18000d408`
- end: `0x18000d719`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `785`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000d324`

## callees

- `0x18000ae24`
- `0x18000cac4`
- `0x18000cba4`
- `0x18000d408`
- `0x180011b94`
- `0x180011bac`
- `0x180011bd0`
- `0x18032f050`
- `0x180375c40`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x18000d5f2`
- `KERNEL32!IsDebuggerPresent` at `0x18000d5f2`
- `KERNEL32!OutputDebugStringW` at `0x18000d6a0`
- `KERNEL32!OutputDebugStringW` at `0x18000d6a0`
- `KERNEL32!GetCurrentThreadId` at `0x18000d4e8`
- `KERNEL32!GetCurrentThreadId` at `0x18000d4e8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int *a7,
        _WORD *a8,
        char a9)
{
  bool v13; // di
  int v14; // esi
  int v15; // ecx
  bool v16; // zf
  const struct wil::FailureInfo *v17; // rdx
  unsigned __int64 IsDebuggerPresent; // rcx
  const struct wil::FailureInfo *v19; // r9
  char v20; // bl
  const struct wil::FailureInfo *v21; // rdx
  int v22; // [rsp+40h] [rbp-C0h] BYREF
  int v23; // [rsp+44h] [rbp-BCh]
  int v24; // [rsp+48h] [rbp-B8h]
  int v25; // [rsp+4Ch] [rbp-B4h]
  signed __int32 v26; // [rsp+50h] [rbp-B0h]
  _WORD *v27; // [rsp+58h] [rbp-A8h]
  DWORD CurrentThreadId; // [rsp+60h] [rbp-A0h]
  __int64 v29; // [rsp+68h] [rbp-98h]
  __int64 v30; // [rsp+70h] [rbp-90h]
  __int64 v31; // [rsp+78h] [rbp-88h]
  int v32; // [rsp+80h] [rbp-80h]
  int v33; // [rsp+84h] [rbp-7Ch]
  __int64 v34; // [rsp+88h] [rbp-78h]
  __int128 v35; // [rsp+90h] [rbp-70h]
  __int64 v36; // [rsp+A0h] [rbp-60h]
  __int128 v37; // [rsp+A8h] [rbp-58h]
  __int64 v38; // [rsp+B8h] [rbp-48h]
  __int64 ModuleName; // [rsp+C0h] [rbp-40h]
  __int64 v40; // [rsp+C8h] [rbp-38h]
  __int64 v41; // [rsp+D0h] [rbp-30h]
  char v42[1024]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR OutputString[2080]; // [rsp+4E0h] [rbp+3E0h] BYREF

  v13 = (a9 & 2) == 0 && g_pfnThrowPlatformException && (wil::g_fResultThrowPlatformException || (a9 & 1) != 0);
  OutputString[0] = 0;
  v42[0] = 0;
  v24 = *a7;
  v25 = a7[1];
  v14 = wil::details::RecordException((wil::details *)(unsigned int)v24, a2);
  v22 = 0;
  v15 = 0;
  if ( a7[2] == 1 )
    v15 = 8;
  v23 = v15;
  v26 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v16 = *a8 == 0, v27 = a8, v16) )
    v27 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v31 = a3;
  v32 = a2;
  v33 = v14;
  v29 = a5;
  v30 = a4;
  v40 = a6;
  v41 = a1;
  v34 = 0;
  v37 = 0;
  v38 = 0;
  v35 = 0;
  v36 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName();
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v22);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v22, v42, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v22);
  if ( wil::details::g_pfnOriginateCallback && !v13 && (v23 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v22);
  if ( v24 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected((wil::details::in1diag3 *)IsDebuggerPresent);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (IsDebuggerPresent = ::IsDebuggerPresent())
      : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent()),
        !(_DWORD)IsDebuggerPresent)
    || !wil::g_fResultOutputDebugString
    || (v20 = 1, (v23 & 2) != 0) )
  {
    v20 = 0;
  }
  if ( v13 || v20 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v22, OutputString, 2048, v19);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (__int64)&v22, v19);
    if ( v20 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v22, 0, 0, v19);
  }
  if ( ((v23 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak();
  if ( (v23 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v22, v17);
  if ( v13 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v22, OutputString);
  if ( (a9 & 2) != 0 )
    wil::RethrowCaughtException((wil *)IsDebuggerPresent);
  wil::ThrowResultException((wil *)&v22, v17);
  wil::details::WilFailFast((wil::details *)&v22, v21);
}

```

## disassembly

```asm
0x18000d408  push    rbp
0x18000d40a  push    rbx
0x18000d40b  push    rsi
0x18000d40c  push    rdi
0x18000d40d  push    r12
0x18000d40f  push    r13
0x18000d411  push    r14
0x18000d413  push    r15
0x18000d415  lea     rbp, [rsp-13E8h]
0x18000d41d  mov     eax, 14E8h
0x18000d422  call    _alloca_probe
0x18000d427  sub     rsp, rax
0x18000d42a  mov     r13, r9
0x18000d42d  mov     r12, r8
0x18000d430  mov     r15d, edx
0x18000d433  mov     r14, rcx
0x18000d436  mov     rax, [rbp+1420h+arg_20]
0x18000d43d  mov     [rsp+1520h+var_14F8], rax
0x18000d442  mov     rax, [rbp+1420h+arg_28]
0x18000d449  mov     [rsp+1520h+var_14F0], rax
0x18000d44e  mov     eax, [rbp+1420h+arg_40]
0x18000d454  xor     ecx, ecx
0x18000d456  and     eax, 2
0x18000d459  mov     [rsp+1520h+var_1500], eax
0x18000d45d  jnz     short loc_18000D47E
0x18000d45f  cmp     cs:g_pfnThrowPlatformException, rcx
0x18000d466  jz      short loc_18000D47E
0x18000d468  cmp     cs:?g_fResultThrowPlatformException@wil@@3_NA, cl; bool wil::g_fResultThrowPlatformException
0x18000d46e  jnz     short loc_18000D479
0x18000d470  test    byte ptr [rbp+1420h+arg_40], 1
0x18000d477  jz      short loc_18000D47E
0x18000d479  mov     dil, 1
0x18000d47c  jmp     short loc_18000D481
0x18000d47e  mov     dil, cl
0x18000d481  mov     [rbp+1420h+OutputString], cx
0x18000d488  mov     [rbp+1420h+var_1440], cl
0x18000d48b  mov     rbx, [rbp+1420h+arg_30]
0x18000d492  mov     ecx, [rbx]; this
0x18000d494  mov     [rsp+1520h+var_14D8], ecx
0x18000d498  mov     eax, [rbx+4]
0x18000d49b  mov     [rsp+1520h+var_14D4], eax
0x18000d49f  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000d4a4  mov     esi, eax
0x18000d4a6  xor     edx, edx
0x18000d4a8  mov     dword ptr [rsp+1520h+var_14E0], edx
0x18000d4ac  mov     ecx, edx
0x18000d4ae  lea     eax, [rdx+8]
0x18000d4b1  cmp     dword ptr [rbx+8], 1
0x18000d4b5  cmovz   ecx, eax
0x18000d4b8  mov     dword ptr [rsp+1520h+var_14E0+4], ecx
0x18000d4bc  lea     ecx, [rdx+1]
0x18000d4bf  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000d4c7  inc     ecx
0x18000d4c9  mov     [rsp+1520h+var_14D0], ecx
0x18000d4cd  mov     rcx, [rbp+1420h+arg_38]
0x18000d4d4  test    rcx, rcx
0x18000d4d7  jz      short loc_18000D4E3
0x18000d4d9  cmp     [rcx], dx
0x18000d4dc  mov     [rsp+1520h+var_14C8], rcx
0x18000d4e1  jnz     short loc_18000D4E8
0x18000d4e3  mov     [rsp+1520h+var_14C8], rdx
0x18000d4e8  call    cs:__imp_GetCurrentThreadId
0x18000d4ee  mov     [rsp+1520h+var_14C0], eax
0x18000d4f2  mov     [rsp+1520h+var_14A8], r12
0x18000d4f7  mov     [rbp+1420h+var_14A0], r15d
0x18000d4fb  mov     [rbp+1420h+var_149C], esi
0x18000d4fe  mov     rax, [rsp+1520h+var_14F8]
0x18000d503  mov     [rsp+1520h+var_14B8], rax
0x18000d508  mov     [rsp+1520h+var_14B0], r13
0x18000d50d  mov     rax, [rsp+1520h+var_14F0]
0x18000d512  mov     [rbp+1420h+var_1458], rax
0x18000d516  mov     [rbp+1420h+var_1450], r14
0x18000d51a  xor     esi, esi
0x18000d51c  mov     [rbp+1420h+var_1498], rsi
0x18000d520  xorps   xmm0, xmm0
0x18000d523  xor     eax, eax
0x18000d525  movups  [rbp+1420h+var_1478], xmm0
0x18000d529  mov     [rbp+1420h+var_1468], rax
0x18000d52d  xorps   xmm1, xmm1
0x18000d530  movups  [rbp+1420h+var_1490], xmm1
0x18000d534  mov     [rbp+1420h+var_1480], rax
0x18000d538  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000d53f  test    rax, rax
0x18000d542  jz      short loc_18000D550
0x18000d544  call    cs:__guard_dispatch_icall_fptr
0x18000d54a  mov     [rbp+1420h+var_1460], rax
0x18000d54e  jmp     short loc_18000D554
0x18000d550  mov     [rbp+1420h+var_1460], rsi
0x18000d554  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000d55b  test    rax, rax
0x18000d55e  jz      short loc_18000D56B
0x18000d560  lea     rcx, [rsp+1520h+var_14E0]
0x18000d565  call    cs:__guard_dispatch_icall_fptr
0x18000d56b  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000d572  test    rax, rax
0x18000d575  jz      short loc_18000D58C
0x18000d577  mov     r8d, 400h
0x18000d57d  lea     rdx, [rbp+1420h+var_1440]
0x18000d581  lea     rcx, [rsp+1520h+var_14E0]
0x18000d586  call    cs:__guard_dispatch_icall_fptr
0x18000d58c  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000d593  test    rax, rax
0x18000d596  jz      short loc_18000D5A3
0x18000d598  lea     rcx, [rsp+1520h+var_14E0]
0x18000d59d  call    cs:__guard_dispatch_icall_fptr
0x18000d5a3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000d5aa  test    rax, rax
0x18000d5ad  jz      short loc_18000D5C6
0x18000d5af  test    dil, dil
0x18000d5b2  jnz     short loc_18000D5C6
0x18000d5b4  test    byte ptr [rsp+1520h+var_14E0+4], 2
0x18000d5b9  jnz     short loc_18000D5C6
0x18000d5bb  lea     rcx, [rsp+1520h+var_14E0]
0x18000d5c0  call    cs:__guard_dispatch_icall_fptr
0x18000d5c6  cmp     [rsp+1520h+var_14D8], esi
0x18000d5ca  jl      short loc_18000D5D2
0x18000d5cc  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000d5d2  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, sil; bool wil::g_fIsDebuggerPresent
0x18000d5d9  jnz     short loc_18000D603
0x18000d5db  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000d5e2  test    rax, rax
0x18000d5e5  jz      short loc_18000D5F2
0x18000d5e7  call    cs:__guard_dispatch_icall_fptr
0x18000d5ed  movzx   ecx, al
0x18000d5f0  jmp     short loc_18000D5FF
0x18000d5f2  call    cs:__imp_IsDebuggerPresent
0x18000d5f8  mov     ecx, esi
0x18000d5fa  test    eax, eax
0x18000d5fc  setnz   cl
0x18000d5ff  test    ecx, ecx
0x18000d601  jz      short loc_18000D615
0x18000d603  cmp     cs:?g_fResultOutputDebugString@wil@@3_NA, sil; bool wil::g_fResultOutputDebugString
0x18000d60a  jz      short loc_18000D615
0x18000d60c  test    byte ptr [rsp+1520h+var_14E0+4], 2
0x18000d611  mov     bl, 1
0x18000d613  jz      short loc_18000D618
0x18000d615  mov     bl, sil
0x18000d618  test    dil, dil
0x18000d61b  jnz     short loc_18000D648
0x18000d61d  test    bl, bl
0x18000d61f  jnz     short loc_18000D648
0x18000d621  mov     rax, cs:g_pfnResultLoggingCallback
0x18000d628  test    rax, rax
0x18000d62b  jz      short loc_18000D6A6
0x18000d62d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, sil; bool wil::details::g_resultMessageCallbackSet
0x18000d634  jnz     short loc_18000D6A6
0x18000d636  xor     r8d, r8d
0x18000d639  xor     edx, edx
0x18000d63b  lea     rcx, [rsp+1520h+var_14E0]
0x18000d640  call    cs:__guard_dispatch_icall_fptr
0x18000d646  jmp     short loc_18000D6A6
0x18000d648  mov     r14d, 800h
0x18000d64e  mov     rax, cs:g_pfnResultLoggingCallback
0x18000d655  test    rax, rax
0x18000d658  jz      short loc_18000D678
0x18000d65a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, sil; bool wil::details::g_resultMessageCallbackSet
0x18000d661  jnz     short loc_18000D678
0x18000d663  mov     r8d, r14d
0x18000d666  lea     rdx, [rbp+1420h+OutputString]
0x18000d66d  lea     rcx, [rsp+1520h+var_14E0]
0x18000d672  call    cs:__guard_dispatch_icall_fptr
0x18000d678  cmp     [rbp+1420h+OutputString], si
0x18000d67f  jnz     short loc_18000D695
0x18000d681  lea     r8, [rsp+1520h+var_14E0]; unsigned __int64
0x18000d686  mov     rdx, r14; wchar_t *
0x18000d689  lea     rcx, [rbp+1420h+OutputString]; this
0x18000d690  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18000d695  test    bl, bl
0x18000d697  jz      short loc_18000D6A6
0x18000d699  lea     rcx, [rbp+1420h+OutputString]; lpOutputString
0x18000d6a0  call    cs:__imp_OutputDebugStringW
0x18000d6a6  test    byte ptr [rsp+1520h+var_14E0+4], 4
0x18000d6ab  jnz     short loc_18000D6B6
0x18000d6ad  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, sil; bool wil::g_fBreakOnFailure
0x18000d6b4  jz      short loc_18000D6C9
0x18000d6b6  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000d6bd  test    rax, rax
0x18000d6c0  jz      short loc_18000D6C9
0x18000d6c2  call    cs:__guard_dispatch_icall_fptr
0x18000d6c8  nop
0x18000d6c9  test    byte ptr [rsp+1520h+var_14E0+4], 1
0x18000d6ce  jz      short loc_18000D6DB
0x18000d6d0  lea     rcx, [rsp+1520h+var_14E0]; this
0x18000d6d5  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000d6db  test    dil, dil
0x18000d6de  jz      short loc_18000D6F9
0x18000d6e0  lea     rdx, [rbp+1420h+OutputString]
0x18000d6e7  lea     rcx, [rsp+1520h+var_14E0]
0x18000d6ec  mov     rax, cs:g_pfnThrowPlatformException
0x18000d6f3  call    cs:__guard_dispatch_icall_fptr
0x18000d6f9  cmp     [rsp+1520h+var_1500], esi
0x18000d6fd  jz      short loc_18000D704
0x18000d6ff  call    ?RethrowCaughtException@wil@@YAXXZ; wil::RethrowCaughtException(void)
0x18000d704  lea     rcx, [rsp+1520h+var_14E0]; this
0x18000d709  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x18000d70e  lea     rcx, [rsp+1520h+var_14E0]; this
0x18000d713  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
