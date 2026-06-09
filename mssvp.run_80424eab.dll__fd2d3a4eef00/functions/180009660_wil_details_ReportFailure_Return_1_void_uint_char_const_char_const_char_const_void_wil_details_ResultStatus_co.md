# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180009660`
- end: `0x180009906`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180005c44`

## callees

- `0x180006270`
- `0x180006dcc`
- `0x180007ec4`
- `0x180009660`
- `0x18000fb30`
- `0x180012880`
- `0x180012a68`
- `0x180038ab0`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009726`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009726`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000981b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000981b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800098a5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800098a5`

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
0x180009660  push    rbp
0x180009662  push    rbx
0x180009663  push    rsi
0x180009664  push    rdi
0x180009665  push    r12
0x180009667  push    r14
0x180009669  push    r15
0x18000966b  lea     rbp, [rsp-13D0h]
0x180009673  mov     eax, 14D0h
0x180009678  call    _alloca_probe
0x18000967d  sub     rsp, rax
0x180009680  mov     rax, cs:__security_cookie
0x180009687  xor     rax, rsp
0x18000968a  mov     [rbp+1400h+var_40], rax
0x180009691  mov     rsi, r8
0x180009694  mov     edi, edx
0x180009696  mov     rbx, rcx
0x180009699  mov     r14, [rbp+1400h+arg_28]
0x1800096a0  xor     edx, edx; Val
0x1800096a2  mov     r8d, 98h; Size
0x1800096a8  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1800096ad  call    memset_0
0x1800096b2  nop
0x1800096b3  xor     r12d, r12d
0x1800096b6  mov     [rbp+1400h+OutputString], r12w
0x1800096be  mov     [rbp+1400h+var_1440], r12b
0x1800096c2  mov     rdx, [rbp+1400h+arg_30]; int
0x1800096c9  mov     ecx, [rdx]; this
0x1800096cb  mov     [rsp+1500h+var_14D8], ecx
0x1800096cf  mov     eax, [rdx+4]
0x1800096d2  mov     [rsp+1500h+var_14D4], eax
0x1800096d6  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800096db  mov     r15d, eax
0x1800096de  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800096e6  mov     ecx, r12d
0x1800096e9  lea     eax, [r12+8]
0x1800096ee  cmp     dword ptr [rdx+8], 1
0x1800096f2  cmovz   ecx, eax
0x1800096f5  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800096f9  lea     ecx, [rax-7]
0x1800096fc  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180009704  inc     ecx
0x180009706  mov     [rsp+1500h+var_14D0], ecx
0x18000970a  mov     rcx, [rbp+1400h+arg_38]
0x180009711  test    rcx, rcx
0x180009714  jz      short loc_180009721
0x180009716  cmp     [rcx], r12w
0x18000971a  mov     [rsp+1500h+var_14C8], rcx
0x18000971f  jnz     short loc_180009726
0x180009721  mov     [rsp+1500h+var_14C8], r12
0x180009726  call    cs:__imp_GetCurrentThreadId
0x18000972c  mov     [rsp+1500h+var_14C0], eax
0x180009730  mov     [rsp+1500h+var_14A8], rsi
0x180009735  mov     [rsp+1500h+var_14A0], edi
0x180009739  mov     [rsp+1500h+var_149C], r15d
0x18000973e  mov     [rsp+1500h+var_14B8], r12
0x180009743  mov     [rsp+1500h+var_14B0], r12
0x180009748  mov     [rbp+1400h+var_1458], r14
0x18000974c  mov     [rbp+1400h+var_1450], rbx
0x180009750  mov     [rsp+1500h+var_1498], r12
0x180009755  xorps   xmm0, xmm0
0x180009758  xor     eax, eax
0x18000975a  movups  [rbp+1400h+var_1478], xmm0
0x18000975e  mov     [rbp+1400h+var_1468], rax
0x180009762  xorps   xmm1, xmm1
0x180009765  movups  [rsp+1500h+var_1490], xmm1
0x18000976a  mov     [rbp+1400h+var_1480], rax
0x18000976e  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180009775  test    rax, rax
0x180009778  jz      short loc_180009785
0x18000977a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000977f  mov     [rbp+1400h+var_1460], rax
0x180009783  jmp     short loc_180009789
0x180009785  mov     [rbp+1400h+var_1460], r12
0x180009789  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180009790  test    rax, rax
0x180009793  jz      short loc_18000979F
0x180009795  lea     rcx, [rsp+1500h+var_14E0]
0x18000979a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000979f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800097a6  test    rax, rax
0x1800097a9  jz      short loc_1800097BF
0x1800097ab  mov     r8d, 400h
0x1800097b1  lea     rdx, [rbp+1400h+var_1440]
0x1800097b5  lea     rcx, [rsp+1500h+var_14E0]
0x1800097ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097bf  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800097c6  test    rax, rax
0x1800097c9  jz      short loc_1800097D5
0x1800097cb  lea     rcx, [rsp+1500h+var_14E0]
0x1800097d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097d5  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800097dc  test    rax, rax
0x1800097df  jz      short loc_1800097F2
0x1800097e1  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800097e6  jnz     short loc_1800097F2
0x1800097e8  lea     rcx, [rsp+1500h+var_14E0]
0x1800097ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097f2  cmp     [rsp+1500h+var_14D8], r12d
0x1800097f7  jge     loc_180009900
0x1800097fd  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180009804  jnz     short loc_180009825
0x180009806  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000980d  test    rax, rax
0x180009810  jz      short loc_18000981B
0x180009812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009817  test    al, al
0x180009819  jmp     short loc_180009823
0x18000981b  call    cs:__imp_IsDebuggerPresent
0x180009821  test    eax, eax
0x180009823  jz      short loc_18000982C
0x180009825  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000982a  jz      short loc_180009852
0x18000982c  mov     rax, cs:g_pfnResultLoggingCallback
0x180009833  test    rax, rax
0x180009836  jz      short loc_1800098AB
0x180009838  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000983f  jnz     short loc_1800098AB
0x180009841  xor     r8d, r8d
0x180009844  xor     edx, edx
0x180009846  lea     rcx, [rsp+1500h+var_14E0]
0x18000984b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009850  jmp     short loc_1800098AB
0x180009852  mov     ebx, 800h
0x180009857  mov     rax, cs:g_pfnResultLoggingCallback
0x18000985e  test    rax, rax
0x180009861  jz      short loc_180009880
0x180009863  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000986a  jnz     short loc_180009880
0x18000986c  mov     r8d, ebx
0x18000986f  lea     rdx, [rbp+1400h+OutputString]
0x180009876  lea     rcx, [rsp+1500h+var_14E0]
0x18000987b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009880  cmp     [rbp+1400h+OutputString], r12w
0x180009888  jnz     short loc_18000989E
0x18000988a  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18000988f  mov     rdx, rbx; wchar_t *
0x180009892  lea     rcx, [rbp+1400h+OutputString]; this
0x180009899  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18000989e  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1800098a5  call    cs:__imp_OutputDebugStringW
0x1800098ab  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1800098b0  jnz     short loc_1800098BB
0x1800098b2  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800098b9  jz      short loc_1800098CD
0x1800098bb  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800098c2  test    rax, rax
0x1800098c5  jz      short loc_1800098CD
0x1800098c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098cc  nop
0x1800098cd  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1800098d2  jnz     short loc_1800098F5
0x1800098d4  mov     rcx, [rbp+1400h+var_40]
0x1800098db  xor     rcx, rsp; StackCookie
0x1800098de  call    __security_check_cookie
0x1800098e3  add     rsp, 14D0h
0x1800098ea  pop     r15
0x1800098ec  pop     r14
0x1800098ee  pop     r12
0x1800098f0  pop     rdi
0x1800098f1  pop     rsi
0x1800098f2  pop     rbx
0x1800098f3  pop     rbp
0x1800098f4  retn
0x1800098f5  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800098fa  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180009900  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
