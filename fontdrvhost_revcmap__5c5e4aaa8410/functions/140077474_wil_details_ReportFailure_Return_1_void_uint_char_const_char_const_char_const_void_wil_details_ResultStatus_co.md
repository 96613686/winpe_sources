# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140077474`
- end: `0x14007770a`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x14007713c`

## callees

- `0x140075de0`
- `0x14007680c`
- `0x140077474`
- `0x140078a54`
- `0x14007a11c`
- `0x14007b548`
- `0x14007b754`
- `0x140096170`
- `0x140098010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x14007761a`
- `KERNEL32!IsDebuggerPresent` at `0x14007761a`
- `KERNEL32!OutputDebugStringW` at `0x1400776a4`
- `KERNEL32!OutputDebugStringW` at `0x1400776a4`
- `KERNEL32!GetCurrentThreadId` at `0x14007751f`
- `KERNEL32!GetCurrentThreadId` at `0x14007751f`

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
0x140077474  mov     [rsp-8+arg_10], rbx
0x140077479  push    rbp
0x14007747a  push    rsi
0x14007747b  push    rdi
0x14007747c  push    r14
0x14007747e  push    r15
0x140077480  lea     rbp, [rsp-13D0h]
0x140077488  mov     eax, 14D0h
0x14007748d  call    _alloca_probe
0x140077492  sub     rsp, rax
0x140077495  mov     rax, cs:__security_cookie
0x14007749c  xor     rax, rsp
0x14007749f  mov     [rbp+13F0h+var_30], rax
0x1400774a6  mov     esi, edx
0x1400774a8  mov     r14, rcx
0x1400774ab  mov     rdi, [rbp+13F0h+arg_28]
0x1400774b2  xor     edx, edx; Val
0x1400774b4  mov     r8d, 98h; Size
0x1400774ba  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1400774bf  call    memset_0
0x1400774c4  nop
0x1400774c5  xor     r15d, r15d
0x1400774c8  mov     [rbp+13F0h+OutputString], r15w
0x1400774d0  mov     [rbp+13F0h+var_1430], r15b
0x1400774d4  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x1400774db  mov     ecx, [rdx]; this
0x1400774dd  mov     [rsp+14F0h+var_14C8], ecx
0x1400774e1  mov     eax, [rdx+4]
0x1400774e4  mov     [rsp+14F0h+var_14C4], eax
0x1400774e8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1400774ed  mov     ebx, eax
0x1400774ef  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x1400774f7  mov     ecx, r15d
0x1400774fa  lea     eax, [r15+8]
0x1400774fe  cmp     dword ptr [rdx+8], 1
0x140077502  cmovz   ecx, eax
0x140077505  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x140077509  lea     ecx, [rax-7]
0x14007750c  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140077514  inc     ecx
0x140077516  mov     [rsp+14F0h+var_14C0], ecx
0x14007751a  mov     [rsp+14F0h+var_14B8], r15
0x14007751f  call    cs:__imp_GetCurrentThreadId
0x140077525  mov     [rsp+14F0h+var_14B0], eax
0x140077529  lea     rax, aWil; "wil"
0x140077530  mov     [rsp+14F0h+var_1498], rax
0x140077535  mov     [rsp+14F0h+var_1490], esi
0x140077539  mov     [rsp+14F0h+var_148C], ebx
0x14007753d  mov     [rsp+14F0h+var_14A8], r15
0x140077542  mov     [rsp+14F0h+var_14A0], r15
0x140077547  mov     [rbp+13F0h+var_1448], rdi
0x14007754b  mov     [rbp+13F0h+var_1440], r14
0x14007754f  mov     [rsp+14F0h+var_1488], r15
0x140077554  xorps   xmm0, xmm0
0x140077557  xor     eax, eax
0x140077559  movups  [rbp+13F0h+var_1468], xmm0
0x14007755d  mov     [rbp+13F0h+var_1458], rax
0x140077561  xorps   xmm1, xmm1
0x140077564  movups  [rsp+14F0h+var_1480], xmm1
0x140077569  mov     [rbp+13F0h+var_1470], rax
0x14007756d  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140077574  test    rax, rax
0x140077577  jz      short loc_140077584
0x140077579  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007757e  mov     [rbp+13F0h+var_1450], rax
0x140077582  jmp     short loc_140077588
0x140077584  mov     [rbp+13F0h+var_1450], r15
0x140077588  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14007758f  test    rax, rax
0x140077592  jz      short loc_14007759E
0x140077594  lea     rcx, [rsp+14F0h+var_14D0]
0x140077599  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007759e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400775a5  test    rax, rax
0x1400775a8  jz      short loc_1400775BE
0x1400775aa  mov     r8d, 400h
0x1400775b0  lea     rdx, [rbp+13F0h+var_1430]
0x1400775b4  lea     rcx, [rsp+14F0h+var_14D0]
0x1400775b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400775be  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400775c5  test    rax, rax
0x1400775c8  jz      short loc_1400775D4
0x1400775ca  lea     rcx, [rsp+14F0h+var_14D0]
0x1400775cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400775d4  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400775db  test    rax, rax
0x1400775de  jz      short loc_1400775F1
0x1400775e0  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1400775e5  jnz     short loc_1400775F1
0x1400775e7  lea     rcx, [rsp+14F0h+var_14D0]
0x1400775ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400775f1  cmp     [rsp+14F0h+var_14C8], r15d
0x1400775f6  jge     loc_140077704
0x1400775fc  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x140077603  jnz     short loc_140077624
0x140077605  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14007760c  test    rax, rax
0x14007760f  jz      short loc_14007761A
0x140077611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140077616  test    al, al
0x140077618  jmp     short loc_140077622
0x14007761a  call    cs:__imp_IsDebuggerPresent
0x140077620  test    eax, eax
0x140077622  jz      short loc_14007762B
0x140077624  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140077629  jz      short loc_140077651
0x14007762b  mov     rax, cs:g_pfnResultLoggingCallback
0x140077632  test    rax, rax
0x140077635  jz      short loc_1400776AA
0x140077637  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14007763e  jnz     short loc_1400776AA
0x140077640  xor     r8d, r8d
0x140077643  xor     edx, edx
0x140077645  lea     rcx, [rsp+14F0h+var_14D0]
0x14007764a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007764f  jmp     short loc_1400776AA
0x140077651  mov     ebx, 800h
0x140077656  mov     rax, cs:g_pfnResultLoggingCallback
0x14007765d  test    rax, rax
0x140077660  jz      short loc_14007767F
0x140077662  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140077669  jnz     short loc_14007767F
0x14007766b  mov     r8d, ebx
0x14007766e  lea     rdx, [rbp+13F0h+OutputString]
0x140077675  lea     rcx, [rsp+14F0h+var_14D0]
0x14007767a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007767f  cmp     [rbp+13F0h+OutputString], r15w
0x140077687  jnz     short loc_14007769D
0x140077689  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x14007768e  mov     rdx, rbx; unsigned __int16 *
0x140077691  lea     rcx, [rbp+13F0h+OutputString]; this
0x140077698  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14007769d  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1400776a4  call    cs:__imp_OutputDebugStringW
0x1400776aa  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1400776af  jnz     short loc_1400776BA
0x1400776b1  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x1400776b8  jz      short loc_1400776CC
0x1400776ba  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400776c1  test    rax, rax
0x1400776c4  jz      short loc_1400776CC
0x1400776c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400776cb  nop
0x1400776cc  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x1400776d1  jnz     short loc_1400776F9
0x1400776d3  mov     rcx, [rbp+13F0h+var_30]
0x1400776da  xor     rcx, rsp; StackCookie
0x1400776dd  call    __security_check_cookie
0x1400776e2  mov     rbx, [rsp+14F0h+arg_10]
0x1400776ea  add     rsp, 14D0h
0x1400776f1  pop     r15
0x1400776f3  pop     r14
0x1400776f5  pop     rdi
0x1400776f6  pop     rsi
0x1400776f7  pop     rbp
0x1400776f8  retn
0x1400776f9  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1400776fe  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x140077704  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
