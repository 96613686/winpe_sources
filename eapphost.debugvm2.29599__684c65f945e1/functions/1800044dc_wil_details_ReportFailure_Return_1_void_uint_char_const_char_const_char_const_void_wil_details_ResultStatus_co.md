# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800044dc`
- end: `0x180004772`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180004174`

## callees

- `0x180002a90`
- `0x18000343c`
- `0x1800044dc`
- `0x1800074e4`
- `0x180008890`
- `0x1800095f8`
- `0x180009728`
- `0x180033d00`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004587`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004587`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004682`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004682`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000470c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000470c`

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
0x1800044dc  mov     [rsp-8+arg_10], rbx
0x1800044e1  push    rbp
0x1800044e2  push    rsi
0x1800044e3  push    rdi
0x1800044e4  push    r14
0x1800044e6  push    r15
0x1800044e8  lea     rbp, [rsp-13D0h]
0x1800044f0  mov     eax, 14D0h
0x1800044f5  call    _alloca_probe
0x1800044fa  sub     rsp, rax
0x1800044fd  mov     rax, cs:__security_cookie
0x180004504  xor     rax, rsp
0x180004507  mov     [rbp+13F0h+var_30], rax
0x18000450e  mov     esi, edx
0x180004510  mov     r14, rcx
0x180004513  mov     rdi, [rbp+13F0h+arg_28]
0x18000451a  xor     edx, edx; Val
0x18000451c  mov     r8d, 98h; Size
0x180004522  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180004527  call    memset_0
0x18000452c  nop
0x18000452d  xor     r15d, r15d
0x180004530  mov     [rbp+13F0h+OutputString], r15w
0x180004538  mov     [rbp+13F0h+var_1430], r15b
0x18000453c  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180004543  mov     ecx, [rdx]; this
0x180004545  mov     [rsp+14F0h+var_14C8], ecx
0x180004549  mov     eax, [rdx+4]
0x18000454c  mov     [rsp+14F0h+var_14C4], eax
0x180004550  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004555  mov     ebx, eax
0x180004557  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x18000455f  mov     ecx, r15d
0x180004562  lea     eax, [r15+8]
0x180004566  cmp     dword ptr [rdx+8], 1
0x18000456a  cmovz   ecx, eax
0x18000456d  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180004571  lea     ecx, [rax-7]
0x180004574  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000457c  inc     ecx
0x18000457e  mov     [rsp+14F0h+var_14C0], ecx
0x180004582  mov     [rsp+14F0h+var_14B8], r15
0x180004587  call    cs:__imp_GetCurrentThreadId
0x18000458d  mov     [rsp+14F0h+var_14B0], eax
0x180004591  lea     rax, aWil; "wil"
0x180004598  mov     [rsp+14F0h+var_1498], rax
0x18000459d  mov     [rsp+14F0h+var_1490], esi
0x1800045a1  mov     [rsp+14F0h+var_148C], ebx
0x1800045a5  mov     [rsp+14F0h+var_14A8], r15
0x1800045aa  mov     [rsp+14F0h+var_14A0], r15
0x1800045af  mov     [rbp+13F0h+var_1448], rdi
0x1800045b3  mov     [rbp+13F0h+var_1440], r14
0x1800045b7  mov     [rsp+14F0h+var_1488], r15
0x1800045bc  xorps   xmm0, xmm0
0x1800045bf  xor     eax, eax
0x1800045c1  movups  [rbp+13F0h+var_1468], xmm0
0x1800045c5  mov     [rbp+13F0h+var_1458], rax
0x1800045c9  xorps   xmm1, xmm1
0x1800045cc  movups  [rsp+14F0h+var_1480], xmm1
0x1800045d1  mov     [rbp+13F0h+var_1470], rax
0x1800045d5  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800045dc  test    rax, rax
0x1800045df  jz      short loc_1800045EC
0x1800045e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045e6  mov     [rbp+13F0h+var_1450], rax
0x1800045ea  jmp     short loc_1800045F0
0x1800045ec  mov     [rbp+13F0h+var_1450], r15
0x1800045f0  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800045f7  test    rax, rax
0x1800045fa  jz      short loc_180004606
0x1800045fc  lea     rcx, [rsp+14F0h+var_14D0]
0x180004601  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004606  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000460d  test    rax, rax
0x180004610  jz      short loc_180004626
0x180004612  mov     r8d, 400h
0x180004618  lea     rdx, [rbp+13F0h+var_1430]
0x18000461c  lea     rcx, [rsp+14F0h+var_14D0]
0x180004621  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004626  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000462d  test    rax, rax
0x180004630  jz      short loc_18000463C
0x180004632  lea     rcx, [rsp+14F0h+var_14D0]
0x180004637  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000463c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004643  test    rax, rax
0x180004646  jz      short loc_180004659
0x180004648  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000464d  jnz     short loc_180004659
0x18000464f  lea     rcx, [rsp+14F0h+var_14D0]
0x180004654  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004659  cmp     [rsp+14F0h+var_14C8], r15d
0x18000465e  jge     loc_18000476C
0x180004664  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18000466b  jnz     short loc_18000468C
0x18000466d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004674  test    rax, rax
0x180004677  jz      short loc_180004682
0x180004679  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000467e  test    al, al
0x180004680  jmp     short loc_18000468A
0x180004682  call    cs:__imp_IsDebuggerPresent
0x180004688  test    eax, eax
0x18000468a  jz      short loc_180004693
0x18000468c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180004691  jz      short loc_1800046B9
0x180004693  mov     rax, cs:g_pfnResultLoggingCallback
0x18000469a  test    rax, rax
0x18000469d  jz      short loc_180004712
0x18000469f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800046a6  jnz     short loc_180004712
0x1800046a8  xor     r8d, r8d
0x1800046ab  xor     edx, edx
0x1800046ad  lea     rcx, [rsp+14F0h+var_14D0]
0x1800046b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046b7  jmp     short loc_180004712
0x1800046b9  mov     ebx, 800h
0x1800046be  mov     rax, cs:g_pfnResultLoggingCallback
0x1800046c5  test    rax, rax
0x1800046c8  jz      short loc_1800046E7
0x1800046ca  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800046d1  jnz     short loc_1800046E7
0x1800046d3  mov     r8d, ebx
0x1800046d6  lea     rdx, [rbp+13F0h+OutputString]
0x1800046dd  lea     rcx, [rsp+14F0h+var_14D0]
0x1800046e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046e7  cmp     [rbp+13F0h+OutputString], r15w
0x1800046ef  jnz     short loc_180004705
0x1800046f1  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800046f6  mov     rdx, rbx; wchar_t *
0x1800046f9  lea     rcx, [rbp+13F0h+OutputString]; this
0x180004700  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180004705  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000470c  call    cs:__imp_OutputDebugStringW
0x180004712  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180004717  jnz     short loc_180004722
0x180004719  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180004720  jz      short loc_180004734
0x180004722  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004729  test    rax, rax
0x18000472c  jz      short loc_180004734
0x18000472e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004733  nop
0x180004734  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180004739  jnz     short loc_180004761
0x18000473b  mov     rcx, [rbp+13F0h+var_30]
0x180004742  xor     rcx, rsp; StackCookie
0x180004745  call    __security_check_cookie
0x18000474a  mov     rbx, [rsp+14F0h+arg_10]
0x180004752  add     rsp, 14D0h
0x180004759  pop     r15
0x18000475b  pop     r14
0x18000475d  pop     rdi
0x18000475e  pop     rsi
0x18000475f  pop     rbp
0x180004760  retn
0x180004761  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180004766  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000476c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
