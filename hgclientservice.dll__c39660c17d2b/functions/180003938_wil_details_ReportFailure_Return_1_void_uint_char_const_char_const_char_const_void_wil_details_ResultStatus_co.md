# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180003938`
- end: `0x180003bde`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180003264`

## callees

- `0x180001770`
- `0x1800021f0`
- `0x180003938`
- `0x180005054`
- `0x180006080`
- `0x180007260`
- `0x18000733c`
- `0x1800151e0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800039fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800039fe`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003af3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003af3`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003b7d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003b7d`

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
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v18, v16);
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
0x180003938  push    rbp
0x18000393a  push    rbx
0x18000393b  push    rsi
0x18000393c  push    rdi
0x18000393d  push    r12
0x18000393f  push    r14
0x180003941  push    r15
0x180003943  lea     rbp, [rsp-13D0h]
0x18000394b  mov     eax, 14D0h
0x180003950  call    _alloca_probe
0x180003955  sub     rsp, rax
0x180003958  mov     rax, cs:__security_cookie
0x18000395f  xor     rax, rsp
0x180003962  mov     [rbp+1400h+var_40], rax
0x180003969  mov     rsi, r8
0x18000396c  mov     edi, edx
0x18000396e  mov     rbx, rcx
0x180003971  mov     r14, [rbp+1400h+arg_28]
0x180003978  xor     edx, edx; Val
0x18000397a  mov     r8d, 98h; Size
0x180003980  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180003985  call    memset_0
0x18000398a  nop
0x18000398b  xor     r12d, r12d
0x18000398e  mov     [rbp+1400h+OutputString], r12w
0x180003996  mov     [rbp+1400h+var_1440], r12b
0x18000399a  mov     rdx, [rbp+1400h+arg_30]; int
0x1800039a1  mov     ecx, [rdx]; this
0x1800039a3  mov     [rsp+1500h+var_14D8], ecx
0x1800039a7  mov     eax, [rdx+4]
0x1800039aa  mov     [rsp+1500h+var_14D4], eax
0x1800039ae  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800039b3  mov     r15d, eax
0x1800039b6  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800039be  mov     ecx, r12d
0x1800039c1  lea     eax, [r12+8]
0x1800039c6  cmp     dword ptr [rdx+8], 1
0x1800039ca  cmovz   ecx, eax
0x1800039cd  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800039d1  lea     ecx, [rax-7]
0x1800039d4  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800039dc  inc     ecx
0x1800039de  mov     [rsp+1500h+var_14D0], ecx
0x1800039e2  mov     rcx, [rbp+1400h+arg_38]
0x1800039e9  test    rcx, rcx
0x1800039ec  jz      short loc_1800039F9
0x1800039ee  cmp     [rcx], r12w
0x1800039f2  mov     [rsp+1500h+var_14C8], rcx
0x1800039f7  jnz     short loc_1800039FE
0x1800039f9  mov     [rsp+1500h+var_14C8], r12
0x1800039fe  call    cs:__imp_GetCurrentThreadId
0x180003a04  mov     [rsp+1500h+var_14C0], eax
0x180003a08  mov     [rsp+1500h+var_14A8], rsi
0x180003a0d  mov     [rsp+1500h+var_14A0], edi
0x180003a11  mov     [rsp+1500h+var_149C], r15d
0x180003a16  mov     [rsp+1500h+var_14B8], r12
0x180003a1b  mov     [rsp+1500h+var_14B0], r12
0x180003a20  mov     [rbp+1400h+var_1458], r14
0x180003a24  mov     [rbp+1400h+var_1450], rbx
0x180003a28  mov     [rsp+1500h+var_1498], r12
0x180003a2d  xorps   xmm0, xmm0
0x180003a30  xor     eax, eax
0x180003a32  movups  [rbp+1400h+var_1478], xmm0
0x180003a36  mov     [rbp+1400h+var_1468], rax
0x180003a3a  xorps   xmm1, xmm1
0x180003a3d  movups  [rsp+1500h+var_1490], xmm1
0x180003a42  mov     [rbp+1400h+var_1480], rax
0x180003a46  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003a4d  test    rax, rax
0x180003a50  jz      short loc_180003A5D
0x180003a52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a57  mov     [rbp+1400h+var_1460], rax
0x180003a5b  jmp     short loc_180003A61
0x180003a5d  mov     [rbp+1400h+var_1460], r12
0x180003a61  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003a68  test    rax, rax
0x180003a6b  jz      short loc_180003A77
0x180003a6d  lea     rcx, [rsp+1500h+var_14E0]
0x180003a72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a77  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003a7e  test    rax, rax
0x180003a81  jz      short loc_180003A97
0x180003a83  mov     r8d, 400h
0x180003a89  lea     rdx, [rbp+1400h+var_1440]
0x180003a8d  lea     rcx, [rsp+1500h+var_14E0]
0x180003a92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a97  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003a9e  test    rax, rax
0x180003aa1  jz      short loc_180003AAD
0x180003aa3  lea     rcx, [rsp+1500h+var_14E0]
0x180003aa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003aad  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003ab4  test    rax, rax
0x180003ab7  jz      short loc_180003ACA
0x180003ab9  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003abe  jnz     short loc_180003ACA
0x180003ac0  lea     rcx, [rsp+1500h+var_14E0]
0x180003ac5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003aca  cmp     [rsp+1500h+var_14D8], r12d
0x180003acf  jge     loc_180003BD8
0x180003ad5  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180003adc  jnz     short loc_180003AFD
0x180003ade  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003ae5  test    rax, rax
0x180003ae8  jz      short loc_180003AF3
0x180003aea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003aef  test    al, al
0x180003af1  jmp     short loc_180003AFB
0x180003af3  call    cs:__imp_IsDebuggerPresent
0x180003af9  test    eax, eax
0x180003afb  jz      short loc_180003B04
0x180003afd  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003b02  jz      short loc_180003B2A
0x180003b04  mov     rax, cs:g_pfnResultLoggingCallback
0x180003b0b  test    rax, rax
0x180003b0e  jz      short loc_180003B83
0x180003b10  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003b17  jnz     short loc_180003B83
0x180003b19  xor     r8d, r8d
0x180003b1c  xor     edx, edx
0x180003b1e  lea     rcx, [rsp+1500h+var_14E0]
0x180003b23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b28  jmp     short loc_180003B83
0x180003b2a  mov     ebx, 800h
0x180003b2f  mov     rax, cs:g_pfnResultLoggingCallback
0x180003b36  test    rax, rax
0x180003b39  jz      short loc_180003B58
0x180003b3b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003b42  jnz     short loc_180003B58
0x180003b44  mov     r8d, ebx
0x180003b47  lea     rdx, [rbp+1400h+OutputString]
0x180003b4e  lea     rcx, [rsp+1500h+var_14E0]
0x180003b53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b58  cmp     [rbp+1400h+OutputString], r12w
0x180003b60  jnz     short loc_180003B76
0x180003b62  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180003b67  mov     rdx, rbx; wchar_t *
0x180003b6a  lea     rcx, [rbp+1400h+OutputString]; this
0x180003b71  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180003b76  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180003b7d  call    cs:__imp_OutputDebugStringW
0x180003b83  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180003b88  jnz     short loc_180003B93
0x180003b8a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180003b91  jz      short loc_180003BA5
0x180003b93  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003b9a  test    rax, rax
0x180003b9d  jz      short loc_180003BA5
0x180003b9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ba4  nop
0x180003ba5  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180003baa  jnz     short loc_180003BCD
0x180003bac  mov     rcx, [rbp+1400h+var_40]
0x180003bb3  xor     rcx, rsp; StackCookie
0x180003bb6  call    __security_check_cookie
0x180003bbb  add     rsp, 14D0h
0x180003bc2  pop     r15
0x180003bc4  pop     r14
0x180003bc6  pop     r12
0x180003bc8  pop     rdi
0x180003bc9  pop     rsi
0x180003bca  pop     rbx
0x180003bcb  pop     rbp
0x180003bcc  retn
0x180003bcd  lea     rcx, [rsp+1500h+var_14E0]; this
0x180003bd2  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180003bd8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
