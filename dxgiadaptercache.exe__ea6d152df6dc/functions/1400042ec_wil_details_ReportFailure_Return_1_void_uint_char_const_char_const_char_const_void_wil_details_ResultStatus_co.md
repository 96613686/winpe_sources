# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1400042ec`
- end: `0x140004592`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1400036b8`

## callees

- `0x1400022a0`
- `0x140002d4c`
- `0x1400042ec`
- `0x140009350`
- `0x14000b438`
- `0x14000fa00`
- `0x1400100dc`
- `0x1400113b0`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400043b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400043b2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140004531`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140004531`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400044a7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400044a7`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v11; // r15d
  int v12; // ecx
  __int64 v13; // rdx
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh]
  int v20; // [rsp+28h] [rbp-D8h]
  int v21; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v22; // [rsp+30h] [rbp-D0h]
  _WORD *v23; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+48h] [rbp-B8h]
  __int64 v26; // [rsp+50h] [rbp-B0h]
  __int64 v27; // [rsp+58h] [rbp-A8h]
  int v28; // [rsp+60h] [rbp-A0h]
  int v29; // [rsp+64h] [rbp-9Ch]
  __int64 v30; // [rsp+68h] [rbp-98h]
  __int128 v31; // [rsp+70h] [rbp-90h]
  __int64 v32; // [rsp+80h] [rbp-80h]
  __int128 v33; // [rsp+88h] [rbp-78h]
  __int64 v34; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v36; // [rsp+A8h] [rbp-58h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  char v38[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v11 = wil::details::RecordReturn((wil::details *)(unsigned int)v20, (int)a7);
  v18 = 1;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  v19 = v12;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v11;
  v25 = 0;
  v26 = 0;
  v36 = a6;
  v37 = a1;
  v30 = 0;
  v33 = 0;
  v34 = 0;
  v31 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v18);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v18, v38, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v18);
  if ( wil::details::g_pfnOriginateCallback && (v19 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v18);
  if ( v20 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v19 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v18, v16);
    OutputDebugStringW(OutputString);
  }
  if ( ((v19 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v19 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x1400042ec  push    rbp
0x1400042ee  push    rbx
0x1400042ef  push    rsi
0x1400042f0  push    rdi
0x1400042f1  push    r12
0x1400042f3  push    r14
0x1400042f5  push    r15
0x1400042f7  lea     rbp, [rsp-13D0h]
0x1400042ff  mov     eax, 14D0h
0x140004304  call    _alloca_probe
0x140004309  sub     rsp, rax
0x14000430c  mov     rax, cs:__security_cookie
0x140004313  xor     rax, rsp
0x140004316  mov     [rbp+1400h+var_40], rax
0x14000431d  mov     rsi, r8
0x140004320  mov     edi, edx
0x140004322  mov     rbx, rcx
0x140004325  mov     r14, [rbp+1400h+arg_28]
0x14000432c  xor     edx, edx; Val
0x14000432e  mov     r8d, 98h; Size
0x140004334  lea     rcx, [rsp+1500h+var_14E0]; void *
0x140004339  call    memset_0
0x14000433e  nop
0x14000433f  xor     r12d, r12d
0x140004342  mov     [rbp+1400h+OutputString], r12w
0x14000434a  mov     [rbp+1400h+var_1440], r12b
0x14000434e  mov     rdx, [rbp+1400h+arg_30]; int
0x140004355  mov     ecx, [rdx]; this
0x140004357  mov     [rsp+1500h+var_14D8], ecx
0x14000435b  mov     eax, [rdx+4]
0x14000435e  mov     [rsp+1500h+var_14D4], eax
0x140004362  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140004367  mov     r15d, eax
0x14000436a  mov     dword ptr [rsp+1500h+var_14E0], 1
0x140004372  mov     ecx, r12d
0x140004375  lea     eax, [r12+8]
0x14000437a  cmp     dword ptr [rdx+8], 1
0x14000437e  cmovz   ecx, eax
0x140004381  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x140004385  lea     ecx, [rax-7]
0x140004388  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140004390  inc     ecx
0x140004392  mov     [rsp+1500h+var_14D0], ecx
0x140004396  mov     rcx, [rbp+1400h+arg_38]
0x14000439d  test    rcx, rcx
0x1400043a0  jz      short loc_1400043AD
0x1400043a2  cmp     [rcx], r12w
0x1400043a6  mov     [rsp+1500h+var_14C8], rcx
0x1400043ab  jnz     short loc_1400043B2
0x1400043ad  mov     [rsp+1500h+var_14C8], r12
0x1400043b2  call    cs:__imp_GetCurrentThreadId
0x1400043b8  mov     [rsp+1500h+var_14C0], eax
0x1400043bc  mov     [rsp+1500h+var_14A8], rsi
0x1400043c1  mov     [rsp+1500h+var_14A0], edi
0x1400043c5  mov     [rsp+1500h+var_149C], r15d
0x1400043ca  mov     [rsp+1500h+var_14B8], r12
0x1400043cf  mov     [rsp+1500h+var_14B0], r12
0x1400043d4  mov     [rbp+1400h+var_1458], r14
0x1400043d8  mov     [rbp+1400h+var_1450], rbx
0x1400043dc  mov     [rsp+1500h+var_1498], r12
0x1400043e1  xorps   xmm0, xmm0
0x1400043e4  xor     eax, eax
0x1400043e6  movups  [rbp+1400h+var_1478], xmm0
0x1400043ea  mov     [rbp+1400h+var_1468], rax
0x1400043ee  xorps   xmm1, xmm1
0x1400043f1  movups  [rsp+1500h+var_1490], xmm1
0x1400043f6  mov     [rbp+1400h+var_1480], rax
0x1400043fa  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140004401  test    rax, rax
0x140004404  jz      short loc_140004411
0x140004406  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000440b  mov     [rbp+1400h+var_1460], rax
0x14000440f  jmp     short loc_140004415
0x140004411  mov     [rbp+1400h+var_1460], r12
0x140004415  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14000441c  test    rax, rax
0x14000441f  jz      short loc_14000442B
0x140004421  lea     rcx, [rsp+1500h+var_14E0]
0x140004426  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000442b  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140004432  test    rax, rax
0x140004435  jz      short loc_14000444B
0x140004437  mov     r8d, 400h
0x14000443d  lea     rdx, [rbp+1400h+var_1440]
0x140004441  lea     rcx, [rsp+1500h+var_14E0]
0x140004446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000444b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140004452  test    rax, rax
0x140004455  jz      short loc_140004461
0x140004457  lea     rcx, [rsp+1500h+var_14E0]
0x14000445c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004461  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140004468  test    rax, rax
0x14000446b  jz      short loc_14000447E
0x14000446d  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140004472  jnz     short loc_14000447E
0x140004474  lea     rcx, [rsp+1500h+var_14E0]
0x140004479  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000447e  cmp     [rsp+1500h+var_14D8], r12d
0x140004483  jge     loc_14000458C
0x140004489  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x140004490  jnz     short loc_1400044B1
0x140004492  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140004499  test    rax, rax
0x14000449c  jz      short loc_1400044A7
0x14000449e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400044a3  test    al, al
0x1400044a5  jmp     short loc_1400044AF
0x1400044a7  call    cs:__imp_IsDebuggerPresent
0x1400044ad  test    eax, eax
0x1400044af  jz      short loc_1400044B8
0x1400044b1  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1400044b6  jz      short loc_1400044DE
0x1400044b8  mov     rax, cs:g_pfnResultLoggingCallback
0x1400044bf  test    rax, rax
0x1400044c2  jz      short loc_140004537
0x1400044c4  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1400044cb  jnz     short loc_140004537
0x1400044cd  xor     r8d, r8d
0x1400044d0  xor     edx, edx
0x1400044d2  lea     rcx, [rsp+1500h+var_14E0]
0x1400044d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400044dc  jmp     short loc_140004537
0x1400044de  mov     ebx, 800h
0x1400044e3  mov     rax, cs:g_pfnResultLoggingCallback
0x1400044ea  test    rax, rax
0x1400044ed  jz      short loc_14000450C
0x1400044ef  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1400044f6  jnz     short loc_14000450C
0x1400044f8  mov     r8d, ebx
0x1400044fb  lea     rdx, [rbp+1400h+OutputString]
0x140004502  lea     rcx, [rsp+1500h+var_14E0]
0x140004507  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000450c  cmp     [rbp+1400h+OutputString], r12w
0x140004514  jnz     short loc_14000452A
0x140004516  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x14000451b  mov     rdx, rbx; unsigned __int16 *
0x14000451e  lea     rcx, [rbp+1400h+OutputString]; this
0x140004525  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14000452a  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x140004531  call    cs:__imp_OutputDebugStringW
0x140004537  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x14000453c  jnz     short loc_140004547
0x14000453e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x140004545  jz      short loc_140004559
0x140004547  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14000454e  test    rax, rax
0x140004551  jz      short loc_140004559
0x140004553  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004558  nop
0x140004559  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x14000455e  jnz     short loc_140004581
0x140004560  mov     rcx, [rbp+1400h+var_40]
0x140004567  xor     rcx, rsp; StackCookie
0x14000456a  call    __security_check_cookie
0x14000456f  add     rsp, 14D0h
0x140004576  pop     r15
0x140004578  pop     r14
0x14000457a  pop     r12
0x14000457c  pop     rdi
0x14000457d  pop     rsi
0x14000457e  pop     rbx
0x14000457f  pop     rbp
0x140004580  retn
0x140004581  lea     rcx, [rsp+1500h+var_14E0]; this
0x140004586  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x14000458c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
