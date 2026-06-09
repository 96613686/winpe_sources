# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800042e4`
- end: `0x18000458a`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180003d74`

## callees

- `0x180002490`
- `0x180002ef8`
- `0x1800042e4`
- `0x180005534`
- `0x180006510`
- `0x180007610`
- `0x180007798`
- `0x18002df90`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800043aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800043aa`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004529`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004529`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000449f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000449f`

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
      g_pfnResultLoggingCallback(&v18, 0, 0, v16);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048, v16);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v18, v16);
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
0x1800042e4  push    rbp
0x1800042e6  push    rbx
0x1800042e7  push    rsi
0x1800042e8  push    rdi
0x1800042e9  push    r12
0x1800042eb  push    r14
0x1800042ed  push    r15
0x1800042ef  lea     rbp, [rsp-13D0h]
0x1800042f7  mov     eax, 14D0h
0x1800042fc  call    _alloca_probe
0x180004301  sub     rsp, rax
0x180004304  mov     rax, cs:__security_cookie
0x18000430b  xor     rax, rsp
0x18000430e  mov     [rbp+1400h+var_40], rax
0x180004315  mov     rsi, r8
0x180004318  mov     edi, edx
0x18000431a  mov     rbx, rcx
0x18000431d  mov     r14, [rbp+1400h+arg_28]
0x180004324  xor     edx, edx; Val
0x180004326  mov     r8d, 98h; Size
0x18000432c  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180004331  call    memset_0
0x180004336  nop
0x180004337  xor     r12d, r12d
0x18000433a  mov     [rbp+1400h+OutputString], r12w
0x180004342  mov     [rbp+1400h+var_1440], r12b
0x180004346  mov     rdx, [rbp+1400h+arg_30]; int
0x18000434d  mov     ecx, [rdx]; this
0x18000434f  mov     [rsp+1500h+var_14D8], ecx
0x180004353  mov     eax, [rdx+4]
0x180004356  mov     [rsp+1500h+var_14D4], eax
0x18000435a  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000435f  mov     r15d, eax
0x180004362  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18000436a  mov     ecx, r12d
0x18000436d  lea     eax, [r12+8]
0x180004372  cmp     dword ptr [rdx+8], 1
0x180004376  cmovz   ecx, eax
0x180004379  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18000437d  lea     ecx, [rax-7]
0x180004380  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004388  inc     ecx
0x18000438a  mov     [rsp+1500h+var_14D0], ecx
0x18000438e  mov     rcx, [rbp+1400h+arg_38]
0x180004395  test    rcx, rcx
0x180004398  jz      short loc_1800043A5
0x18000439a  cmp     [rcx], r12w
0x18000439e  mov     [rsp+1500h+var_14C8], rcx
0x1800043a3  jnz     short loc_1800043AA
0x1800043a5  mov     [rsp+1500h+var_14C8], r12
0x1800043aa  call    cs:__imp_GetCurrentThreadId
0x1800043b0  mov     [rsp+1500h+var_14C0], eax
0x1800043b4  mov     [rsp+1500h+var_14A8], rsi
0x1800043b9  mov     [rsp+1500h+var_14A0], edi
0x1800043bd  mov     [rsp+1500h+var_149C], r15d
0x1800043c2  mov     [rsp+1500h+var_14B8], r12
0x1800043c7  mov     [rsp+1500h+var_14B0], r12
0x1800043cc  mov     [rbp+1400h+var_1458], r14
0x1800043d0  mov     [rbp+1400h+var_1450], rbx
0x1800043d4  mov     [rsp+1500h+var_1498], r12
0x1800043d9  xorps   xmm0, xmm0
0x1800043dc  xor     eax, eax
0x1800043de  movups  [rbp+1400h+var_1478], xmm0
0x1800043e2  mov     [rbp+1400h+var_1468], rax
0x1800043e6  xorps   xmm1, xmm1
0x1800043e9  movups  [rsp+1500h+var_1490], xmm1
0x1800043ee  mov     [rbp+1400h+var_1480], rax
0x1800043f2  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800043f9  test    rax, rax
0x1800043fc  jz      short loc_180004409
0x1800043fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004403  mov     [rbp+1400h+var_1460], rax
0x180004407  jmp     short loc_18000440D
0x180004409  mov     [rbp+1400h+var_1460], r12
0x18000440d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004414  test    rax, rax
0x180004417  jz      short loc_180004423
0x180004419  lea     rcx, [rsp+1500h+var_14E0]
0x18000441e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004423  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000442a  test    rax, rax
0x18000442d  jz      short loc_180004443
0x18000442f  mov     r8d, 400h
0x180004435  lea     rdx, [rbp+1400h+var_1440]
0x180004439  lea     rcx, [rsp+1500h+var_14E0]
0x18000443e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004443  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000444a  test    rax, rax
0x18000444d  jz      short loc_180004459
0x18000444f  lea     rcx, [rsp+1500h+var_14E0]
0x180004454  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004459  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004460  test    rax, rax
0x180004463  jz      short loc_180004476
0x180004465  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000446a  jnz     short loc_180004476
0x18000446c  lea     rcx, [rsp+1500h+var_14E0]
0x180004471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004476  cmp     [rsp+1500h+var_14D8], r12d
0x18000447b  jge     loc_180004584
0x180004481  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180004488  jnz     short loc_1800044A9
0x18000448a  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004491  test    rax, rax
0x180004494  jz      short loc_18000449F
0x180004496  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000449b  test    al, al
0x18000449d  jmp     short loc_1800044A7
0x18000449f  call    cs:__imp_IsDebuggerPresent
0x1800044a5  test    eax, eax
0x1800044a7  jz      short loc_1800044B0
0x1800044a9  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800044ae  jz      short loc_1800044D6
0x1800044b0  mov     rax, cs:g_pfnResultLoggingCallback
0x1800044b7  test    rax, rax
0x1800044ba  jz      short loc_18000452F
0x1800044bc  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800044c3  jnz     short loc_18000452F
0x1800044c5  xor     r8d, r8d
0x1800044c8  xor     edx, edx
0x1800044ca  lea     rcx, [rsp+1500h+var_14E0]
0x1800044cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044d4  jmp     short loc_18000452F
0x1800044d6  mov     ebx, 800h
0x1800044db  mov     rax, cs:g_pfnResultLoggingCallback
0x1800044e2  test    rax, rax
0x1800044e5  jz      short loc_180004504
0x1800044e7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800044ee  jnz     short loc_180004504
0x1800044f0  mov     r8d, ebx
0x1800044f3  lea     rdx, [rbp+1400h+OutputString]
0x1800044fa  lea     rcx, [rsp+1500h+var_14E0]
0x1800044ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004504  cmp     [rbp+1400h+OutputString], r12w
0x18000450c  jnz     short loc_180004522
0x18000450e  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180004513  mov     rdx, rbx; unsigned __int16 *
0x180004516  lea     rcx, [rbp+1400h+OutputString]; this
0x18000451d  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004522  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180004529  call    cs:__imp_OutputDebugStringW
0x18000452f  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180004534  jnz     short loc_18000453F
0x180004536  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18000453d  jz      short loc_180004551
0x18000453f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004546  test    rax, rax
0x180004549  jz      short loc_180004551
0x18000454b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004550  nop
0x180004551  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180004556  jnz     short loc_180004579
0x180004558  mov     rcx, [rbp+1400h+var_40]
0x18000455f  xor     rcx, rsp; StackCookie
0x180004562  call    __security_check_cookie
0x180004567  add     rsp, 14D0h
0x18000456e  pop     r15
0x180004570  pop     r14
0x180004572  pop     r12
0x180004574  pop     rdi
0x180004575  pop     rsi
0x180004576  pop     rbx
0x180004577  pop     rbp
0x180004578  retn
0x180004579  lea     rcx, [rsp+1500h+var_14E0]; this
0x18000457e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180004584  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
