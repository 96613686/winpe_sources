# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180014840`
- end: `0x180014ae6`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180014238`

## callees

- `0x1800120d0`
- `0x180012f40`
- `0x180014840`
- `0x180018f70`
- `0x18001afd4`
- `0x18001d048`
- `0x18001d22c`
- `0x18003f700`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014906`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014906`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180014a85`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180014a85`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800149fb`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800149fb`

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
0x180014840  push    rbp
0x180014842  push    rbx
0x180014843  push    rsi
0x180014844  push    rdi
0x180014845  push    r12
0x180014847  push    r14
0x180014849  push    r15
0x18001484b  lea     rbp, [rsp-13D0h]
0x180014853  mov     eax, 14D0h
0x180014858  call    _alloca_probe
0x18001485d  sub     rsp, rax
0x180014860  mov     rax, cs:__security_cookie
0x180014867  xor     rax, rsp
0x18001486a  mov     [rbp+1400h+var_40], rax
0x180014871  mov     rsi, r8
0x180014874  mov     edi, edx
0x180014876  mov     rbx, rcx
0x180014879  mov     r14, [rbp+1400h+arg_28]
0x180014880  xor     edx, edx; Val
0x180014882  mov     r8d, 98h; Size
0x180014888  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18001488d  call    memset_0
0x180014892  nop
0x180014893  xor     r12d, r12d
0x180014896  mov     [rbp+1400h+OutputString], r12w
0x18001489e  mov     [rbp+1400h+var_1440], r12b
0x1800148a2  mov     rdx, [rbp+1400h+arg_30]; int
0x1800148a9  mov     ecx, [rdx]; this
0x1800148ab  mov     [rsp+1500h+var_14D8], ecx
0x1800148af  mov     eax, [rdx+4]
0x1800148b2  mov     [rsp+1500h+var_14D4], eax
0x1800148b6  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800148bb  mov     r15d, eax
0x1800148be  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800148c6  mov     ecx, r12d
0x1800148c9  lea     eax, [r12+8]
0x1800148ce  cmp     dword ptr [rdx+8], 1
0x1800148d2  cmovz   ecx, eax
0x1800148d5  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800148d9  lea     ecx, [rax-7]
0x1800148dc  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800148e4  inc     ecx
0x1800148e6  mov     [rsp+1500h+var_14D0], ecx
0x1800148ea  mov     rcx, [rbp+1400h+arg_38]
0x1800148f1  test    rcx, rcx
0x1800148f4  jz      short loc_180014901
0x1800148f6  cmp     [rcx], r12w
0x1800148fa  mov     [rsp+1500h+var_14C8], rcx
0x1800148ff  jnz     short loc_180014906
0x180014901  mov     [rsp+1500h+var_14C8], r12
0x180014906  call    cs:__imp_GetCurrentThreadId
0x18001490c  mov     [rsp+1500h+var_14C0], eax
0x180014910  mov     [rsp+1500h+var_14A8], rsi
0x180014915  mov     [rsp+1500h+var_14A0], edi
0x180014919  mov     [rsp+1500h+var_149C], r15d
0x18001491e  mov     [rsp+1500h+var_14B8], r12
0x180014923  mov     [rsp+1500h+var_14B0], r12
0x180014928  mov     [rbp+1400h+var_1458], r14
0x18001492c  mov     [rbp+1400h+var_1450], rbx
0x180014930  mov     [rsp+1500h+var_1498], r12
0x180014935  xorps   xmm0, xmm0
0x180014938  xor     eax, eax
0x18001493a  movups  [rbp+1400h+var_1478], xmm0
0x18001493e  mov     [rbp+1400h+var_1468], rax
0x180014942  xorps   xmm1, xmm1
0x180014945  movups  [rsp+1500h+var_1490], xmm1
0x18001494a  mov     [rbp+1400h+var_1480], rax
0x18001494e  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180014955  test    rax, rax
0x180014958  jz      short loc_180014965
0x18001495a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001495f  mov     [rbp+1400h+var_1460], rax
0x180014963  jmp     short loc_180014969
0x180014965  mov     [rbp+1400h+var_1460], r12
0x180014969  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180014970  test    rax, rax
0x180014973  jz      short loc_18001497F
0x180014975  lea     rcx, [rsp+1500h+var_14E0]
0x18001497a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001497f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180014986  test    rax, rax
0x180014989  jz      short loc_18001499F
0x18001498b  mov     r8d, 400h
0x180014991  lea     rdx, [rbp+1400h+var_1440]
0x180014995  lea     rcx, [rsp+1500h+var_14E0]
0x18001499a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001499f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800149a6  test    rax, rax
0x1800149a9  jz      short loc_1800149B5
0x1800149ab  lea     rcx, [rsp+1500h+var_14E0]
0x1800149b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800149b5  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800149bc  test    rax, rax
0x1800149bf  jz      short loc_1800149D2
0x1800149c1  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800149c6  jnz     short loc_1800149D2
0x1800149c8  lea     rcx, [rsp+1500h+var_14E0]
0x1800149cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800149d2  cmp     [rsp+1500h+var_14D8], r12d
0x1800149d7  jge     loc_180014AE0
0x1800149dd  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800149e4  jnz     short loc_180014A05
0x1800149e6  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800149ed  test    rax, rax
0x1800149f0  jz      short loc_1800149FB
0x1800149f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800149f7  test    al, al
0x1800149f9  jmp     short loc_180014A03
0x1800149fb  call    cs:__imp_IsDebuggerPresent
0x180014a01  test    eax, eax
0x180014a03  jz      short loc_180014A0C
0x180014a05  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180014a0a  jz      short loc_180014A32
0x180014a0c  mov     rax, cs:g_pfnResultLoggingCallback
0x180014a13  test    rax, rax
0x180014a16  jz      short loc_180014A8B
0x180014a18  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180014a1f  jnz     short loc_180014A8B
0x180014a21  xor     r8d, r8d
0x180014a24  xor     edx, edx
0x180014a26  lea     rcx, [rsp+1500h+var_14E0]
0x180014a2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a30  jmp     short loc_180014A8B
0x180014a32  mov     ebx, 800h
0x180014a37  mov     rax, cs:g_pfnResultLoggingCallback
0x180014a3e  test    rax, rax
0x180014a41  jz      short loc_180014A60
0x180014a43  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180014a4a  jnz     short loc_180014A60
0x180014a4c  mov     r8d, ebx
0x180014a4f  lea     rdx, [rbp+1400h+OutputString]
0x180014a56  lea     rcx, [rsp+1500h+var_14E0]
0x180014a5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a60  cmp     [rbp+1400h+OutputString], r12w
0x180014a68  jnz     short loc_180014A7E
0x180014a6a  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180014a6f  mov     rdx, rbx; wchar_t *
0x180014a72  lea     rcx, [rbp+1400h+OutputString]; this
0x180014a79  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180014a7e  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180014a85  call    cs:__imp_OutputDebugStringW
0x180014a8b  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180014a90  jnz     short loc_180014A9B
0x180014a92  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180014a99  jz      short loc_180014AAD
0x180014a9b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180014aa2  test    rax, rax
0x180014aa5  jz      short loc_180014AAD
0x180014aa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014aac  nop
0x180014aad  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180014ab2  jnz     short loc_180014AD5
0x180014ab4  mov     rcx, [rbp+1400h+var_40]
0x180014abb  xor     rcx, rsp; StackCookie
0x180014abe  call    __security_check_cookie
0x180014ac3  add     rsp, 14D0h
0x180014aca  pop     r15
0x180014acc  pop     r14
0x180014ace  pop     r12
0x180014ad0  pop     rdi
0x180014ad1  pop     rsi
0x180014ad2  pop     rbx
0x180014ad3  pop     rbp
0x180014ad4  retn
0x180014ad5  lea     rcx, [rsp+1500h+var_14E0]; this
0x180014ada  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180014ae0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
