# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180005400`
- end: `0x1800056a6`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000508c`

## callees

- `0x180003220`
- `0x180004100`
- `0x180005400`
- `0x180006ef4`
- `0x180008ca0`
- `0x18000a798`
- `0x18000aa30`
- `0x1800aef90`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800054c6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800054c6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800055bb`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800055bb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005645`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005645`

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
0x180005400  push    rbp
0x180005402  push    rbx
0x180005403  push    rsi
0x180005404  push    rdi
0x180005405  push    r12
0x180005407  push    r14
0x180005409  push    r15
0x18000540b  lea     rbp, [rsp-13D0h]
0x180005413  mov     eax, 14D0h
0x180005418  call    _alloca_probe
0x18000541d  sub     rsp, rax
0x180005420  mov     rax, cs:__security_cookie
0x180005427  xor     rax, rsp
0x18000542a  mov     [rbp+1400h+var_40], rax
0x180005431  mov     rsi, r8
0x180005434  mov     edi, edx
0x180005436  mov     rbx, rcx
0x180005439  mov     r14, [rbp+1400h+arg_28]
0x180005440  xor     edx, edx; Val
0x180005442  mov     r8d, 98h; Size
0x180005448  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18000544d  call    memset_0
0x180005452  nop
0x180005453  xor     r12d, r12d
0x180005456  mov     [rbp+1400h+OutputString], r12w
0x18000545e  mov     [rbp+1400h+var_1440], r12b
0x180005462  mov     rdx, [rbp+1400h+arg_30]; int
0x180005469  mov     ecx, [rdx]; this
0x18000546b  mov     [rsp+1500h+var_14D8], ecx
0x18000546f  mov     eax, [rdx+4]
0x180005472  mov     [rsp+1500h+var_14D4], eax
0x180005476  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000547b  mov     r15d, eax
0x18000547e  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180005486  mov     ecx, r12d
0x180005489  lea     eax, [r12+8]
0x18000548e  cmp     dword ptr [rdx+8], 1
0x180005492  cmovz   ecx, eax
0x180005495  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180005499  lea     ecx, [rax-7]
0x18000549c  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800054a4  inc     ecx
0x1800054a6  mov     [rsp+1500h+var_14D0], ecx
0x1800054aa  mov     rcx, [rbp+1400h+arg_38]
0x1800054b1  test    rcx, rcx
0x1800054b4  jz      short loc_1800054C1
0x1800054b6  cmp     [rcx], r12w
0x1800054ba  mov     [rsp+1500h+var_14C8], rcx
0x1800054bf  jnz     short loc_1800054C6
0x1800054c1  mov     [rsp+1500h+var_14C8], r12
0x1800054c6  call    cs:__imp_GetCurrentThreadId
0x1800054cc  mov     [rsp+1500h+var_14C0], eax
0x1800054d0  mov     [rsp+1500h+var_14A8], rsi
0x1800054d5  mov     [rsp+1500h+var_14A0], edi
0x1800054d9  mov     [rsp+1500h+var_149C], r15d
0x1800054de  mov     [rsp+1500h+var_14B8], r12
0x1800054e3  mov     [rsp+1500h+var_14B0], r12
0x1800054e8  mov     [rbp+1400h+var_1458], r14
0x1800054ec  mov     [rbp+1400h+var_1450], rbx
0x1800054f0  mov     [rsp+1500h+var_1498], r12
0x1800054f5  xorps   xmm0, xmm0
0x1800054f8  xor     eax, eax
0x1800054fa  movups  [rbp+1400h+var_1478], xmm0
0x1800054fe  mov     [rbp+1400h+var_1468], rax
0x180005502  xorps   xmm1, xmm1
0x180005505  movups  [rsp+1500h+var_1490], xmm1
0x18000550a  mov     [rbp+1400h+var_1480], rax
0x18000550e  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005515  test    rax, rax
0x180005518  jz      short loc_180005525
0x18000551a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000551f  mov     [rbp+1400h+var_1460], rax
0x180005523  jmp     short loc_180005529
0x180005525  mov     [rbp+1400h+var_1460], r12
0x180005529  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005530  test    rax, rax
0x180005533  jz      short loc_18000553F
0x180005535  lea     rcx, [rsp+1500h+var_14E0]
0x18000553a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000553f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005546  test    rax, rax
0x180005549  jz      short loc_18000555F
0x18000554b  mov     r8d, 400h
0x180005551  lea     rdx, [rbp+1400h+var_1440]
0x180005555  lea     rcx, [rsp+1500h+var_14E0]
0x18000555a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000555f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005566  test    rax, rax
0x180005569  jz      short loc_180005575
0x18000556b  lea     rcx, [rsp+1500h+var_14E0]
0x180005570  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005575  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000557c  test    rax, rax
0x18000557f  jz      short loc_180005592
0x180005581  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180005586  jnz     short loc_180005592
0x180005588  lea     rcx, [rsp+1500h+var_14E0]
0x18000558d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005592  cmp     [rsp+1500h+var_14D8], r12d
0x180005597  jge     loc_1800056A0
0x18000559d  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800055a4  jnz     short loc_1800055C5
0x1800055a6  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800055ad  test    rax, rax
0x1800055b0  jz      short loc_1800055BB
0x1800055b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055b7  test    al, al
0x1800055b9  jmp     short loc_1800055C3
0x1800055bb  call    cs:__imp_IsDebuggerPresent
0x1800055c1  test    eax, eax
0x1800055c3  jz      short loc_1800055CC
0x1800055c5  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800055ca  jz      short loc_1800055F2
0x1800055cc  mov     rax, cs:g_pfnResultLoggingCallback
0x1800055d3  test    rax, rax
0x1800055d6  jz      short loc_18000564B
0x1800055d8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800055df  jnz     short loc_18000564B
0x1800055e1  xor     r8d, r8d
0x1800055e4  xor     edx, edx
0x1800055e6  lea     rcx, [rsp+1500h+var_14E0]
0x1800055eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055f0  jmp     short loc_18000564B
0x1800055f2  mov     ebx, 800h
0x1800055f7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800055fe  test    rax, rax
0x180005601  jz      short loc_180005620
0x180005603  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000560a  jnz     short loc_180005620
0x18000560c  mov     r8d, ebx
0x18000560f  lea     rdx, [rbp+1400h+OutputString]
0x180005616  lea     rcx, [rsp+1500h+var_14E0]
0x18000561b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005620  cmp     [rbp+1400h+OutputString], r12w
0x180005628  jnz     short loc_18000563E
0x18000562a  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18000562f  mov     rdx, rbx; unsigned __int16 *
0x180005632  lea     rcx, [rbp+1400h+OutputString]; this
0x180005639  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000563e  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180005645  call    cs:__imp_OutputDebugStringW
0x18000564b  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180005650  jnz     short loc_18000565B
0x180005652  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180005659  jz      short loc_18000566D
0x18000565b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005662  test    rax, rax
0x180005665  jz      short loc_18000566D
0x180005667  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000566c  nop
0x18000566d  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180005672  jnz     short loc_180005695
0x180005674  mov     rcx, [rbp+1400h+var_40]
0x18000567b  xor     rcx, rsp; StackCookie
0x18000567e  call    __security_check_cookie
0x180005683  add     rsp, 14D0h
0x18000568a  pop     r15
0x18000568c  pop     r14
0x18000568e  pop     r12
0x180005690  pop     rdi
0x180005691  pop     rsi
0x180005692  pop     rbx
0x180005693  pop     rbp
0x180005694  retn
0x180005695  lea     rcx, [rsp+1500h+var_14E0]; this
0x18000569a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800056a0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
