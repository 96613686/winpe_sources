# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140004158`
- end: `0x1400043fe`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140003684`

## callees

- `0x140002600`
- `0x140003168`
- `0x140004158`
- `0x1400070c4`
- `0x1400089b8`
- `0x14000ace0`
- `0x14000af58`
- `0x1400130e0`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000421e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000421e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140004313`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140004313`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000439d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000439d`

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
0x140004158  push    rbp
0x14000415a  push    rbx
0x14000415b  push    rsi
0x14000415c  push    rdi
0x14000415d  push    r12
0x14000415f  push    r14
0x140004161  push    r15
0x140004163  lea     rbp, [rsp-13D0h]
0x14000416b  mov     eax, 14D0h
0x140004170  call    _alloca_probe
0x140004175  sub     rsp, rax
0x140004178  mov     rax, cs:__security_cookie
0x14000417f  xor     rax, rsp
0x140004182  mov     [rbp+1400h+var_40], rax
0x140004189  mov     rsi, r8
0x14000418c  mov     edi, edx
0x14000418e  mov     rbx, rcx
0x140004191  mov     r14, [rbp+1400h+arg_28]
0x140004198  xor     edx, edx; Val
0x14000419a  mov     r8d, 98h; Size
0x1400041a0  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1400041a5  call    memset_0
0x1400041aa  nop
0x1400041ab  xor     r12d, r12d
0x1400041ae  mov     [rbp+1400h+OutputString], r12w
0x1400041b6  mov     [rbp+1400h+var_1440], r12b
0x1400041ba  mov     rdx, [rbp+1400h+arg_30]; int
0x1400041c1  mov     ecx, [rdx]; this
0x1400041c3  mov     [rsp+1500h+var_14D8], ecx
0x1400041c7  mov     eax, [rdx+4]
0x1400041ca  mov     [rsp+1500h+var_14D4], eax
0x1400041ce  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1400041d3  mov     r15d, eax
0x1400041d6  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1400041de  mov     ecx, r12d
0x1400041e1  lea     eax, [r12+8]
0x1400041e6  cmp     dword ptr [rdx+8], 1
0x1400041ea  cmovz   ecx, eax
0x1400041ed  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1400041f1  lea     ecx, [rax-7]
0x1400041f4  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400041fc  inc     ecx
0x1400041fe  mov     [rsp+1500h+var_14D0], ecx
0x140004202  mov     rcx, [rbp+1400h+arg_38]
0x140004209  test    rcx, rcx
0x14000420c  jz      short loc_140004219
0x14000420e  cmp     [rcx], r12w
0x140004212  mov     [rsp+1500h+var_14C8], rcx
0x140004217  jnz     short loc_14000421E
0x140004219  mov     [rsp+1500h+var_14C8], r12
0x14000421e  call    cs:__imp_GetCurrentThreadId
0x140004224  mov     [rsp+1500h+var_14C0], eax
0x140004228  mov     [rsp+1500h+var_14A8], rsi
0x14000422d  mov     [rsp+1500h+var_14A0], edi
0x140004231  mov     [rsp+1500h+var_149C], r15d
0x140004236  mov     [rsp+1500h+var_14B8], r12
0x14000423b  mov     [rsp+1500h+var_14B0], r12
0x140004240  mov     [rbp+1400h+var_1458], r14
0x140004244  mov     [rbp+1400h+var_1450], rbx
0x140004248  mov     [rsp+1500h+var_1498], r12
0x14000424d  xorps   xmm0, xmm0
0x140004250  xor     eax, eax
0x140004252  movups  [rbp+1400h+var_1478], xmm0
0x140004256  mov     [rbp+1400h+var_1468], rax
0x14000425a  xorps   xmm1, xmm1
0x14000425d  movups  [rsp+1500h+var_1490], xmm1
0x140004262  mov     [rbp+1400h+var_1480], rax
0x140004266  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000426d  test    rax, rax
0x140004270  jz      short loc_14000427D
0x140004272  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004277  mov     [rbp+1400h+var_1460], rax
0x14000427b  jmp     short loc_140004281
0x14000427d  mov     [rbp+1400h+var_1460], r12
0x140004281  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140004288  test    rax, rax
0x14000428b  jz      short loc_140004297
0x14000428d  lea     rcx, [rsp+1500h+var_14E0]
0x140004292  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004297  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000429e  test    rax, rax
0x1400042a1  jz      short loc_1400042B7
0x1400042a3  mov     r8d, 400h
0x1400042a9  lea     rdx, [rbp+1400h+var_1440]
0x1400042ad  lea     rcx, [rsp+1500h+var_14E0]
0x1400042b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400042b7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400042be  test    rax, rax
0x1400042c1  jz      short loc_1400042CD
0x1400042c3  lea     rcx, [rsp+1500h+var_14E0]
0x1400042c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400042cd  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400042d4  test    rax, rax
0x1400042d7  jz      short loc_1400042EA
0x1400042d9  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1400042de  jnz     short loc_1400042EA
0x1400042e0  lea     rcx, [rsp+1500h+var_14E0]
0x1400042e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400042ea  cmp     [rsp+1500h+var_14D8], r12d
0x1400042ef  jge     loc_1400043F8
0x1400042f5  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1400042fc  jnz     short loc_14000431D
0x1400042fe  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140004305  test    rax, rax
0x140004308  jz      short loc_140004313
0x14000430a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000430f  test    al, al
0x140004311  jmp     short loc_14000431B
0x140004313  call    cs:__imp_IsDebuggerPresent
0x140004319  test    eax, eax
0x14000431b  jz      short loc_140004324
0x14000431d  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140004322  jz      short loc_14000434A
0x140004324  mov     rax, cs:g_pfnResultLoggingCallback
0x14000432b  test    rax, rax
0x14000432e  jz      short loc_1400043A3
0x140004330  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140004337  jnz     short loc_1400043A3
0x140004339  xor     r8d, r8d
0x14000433c  xor     edx, edx
0x14000433e  lea     rcx, [rsp+1500h+var_14E0]
0x140004343  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004348  jmp     short loc_1400043A3
0x14000434a  mov     ebx, 800h
0x14000434f  mov     rax, cs:g_pfnResultLoggingCallback
0x140004356  test    rax, rax
0x140004359  jz      short loc_140004378
0x14000435b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140004362  jnz     short loc_140004378
0x140004364  mov     r8d, ebx
0x140004367  lea     rdx, [rbp+1400h+OutputString]
0x14000436e  lea     rcx, [rsp+1500h+var_14E0]
0x140004373  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004378  cmp     [rbp+1400h+OutputString], r12w
0x140004380  jnz     short loc_140004396
0x140004382  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x140004387  mov     rdx, rbx; unsigned __int16 *
0x14000438a  lea     rcx, [rbp+1400h+OutputString]; this
0x140004391  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140004396  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x14000439d  call    cs:__imp_OutputDebugStringW
0x1400043a3  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1400043a8  jnz     short loc_1400043B3
0x1400043aa  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1400043b1  jz      short loc_1400043C5
0x1400043b3  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400043ba  test    rax, rax
0x1400043bd  jz      short loc_1400043C5
0x1400043bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400043c4  nop
0x1400043c5  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1400043ca  jnz     short loc_1400043ED
0x1400043cc  mov     rcx, [rbp+1400h+var_40]
0x1400043d3  xor     rcx, rsp; StackCookie
0x1400043d6  call    __security_check_cookie
0x1400043db  add     rsp, 14D0h
0x1400043e2  pop     r15
0x1400043e4  pop     r14
0x1400043e6  pop     r12
0x1400043e8  pop     rdi
0x1400043e9  pop     rsi
0x1400043ea  pop     rbx
0x1400043eb  pop     rbp
0x1400043ec  retn
0x1400043ed  lea     rcx, [rsp+1500h+var_14E0]; this
0x1400043f2  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1400043f8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
