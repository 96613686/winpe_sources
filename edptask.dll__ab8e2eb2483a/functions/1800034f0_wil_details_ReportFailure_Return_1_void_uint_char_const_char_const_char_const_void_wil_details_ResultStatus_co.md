# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800034f0`
- end: `0x18000377d`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180002fc8`

## callees

- `0x1800034f0`
- `0x180004664`
- `0x180005560`
- `0x180006490`
- `0x180006790`
- `0x1800133e2`
- `0x180013410`
- `0x1800134d0`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000359e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000359e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000371c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000371c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003692`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003692`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v10; // ebx
  int v11; // ecx
  __int64 v12; // rdx
  const struct wil::FailureInfo *v13; // rdx
  wil::details::in1diag3 *v14; // rcx
  const struct wil::FailureInfo *v15; // r9
  bool v16; // zf
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh]
  int v19; // [rsp+28h] [rbp-D8h]
  int v20; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v21; // [rsp+30h] [rbp-D0h]
  __int64 v22; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v24; // [rsp+48h] [rbp-B8h]
  __int64 v25; // [rsp+50h] [rbp-B0h]
  __int64 v26; // [rsp+58h] [rbp-A8h]
  int v27; // [rsp+60h] [rbp-A0h]
  int v28; // [rsp+64h] [rbp-9Ch]
  __int64 v29; // [rsp+68h] [rbp-98h]
  __int128 v30; // [rsp+70h] [rbp-90h]
  __int64 v31; // [rsp+80h] [rbp-80h]
  __int128 v32; // [rsp+88h] [rbp-78h]
  __int64 v33; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v35; // [rsp+A8h] [rbp-58h]
  __int64 v36; // [rsp+B0h] [rbp-50h]
  char v37[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v17, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
  v19 = *a7;
  v20 = a7[1];
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v19, (int)a7);
  v17 = 1;
  v11 = 0;
  if ( *(_DWORD *)(v12 + 8) == 1 )
    v11 = 8;
  v18 = v11;
  v21 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v26 = a3;
  v27 = a2;
  v28 = v10;
  v24 = 0;
  v25 = 0;
  v35 = a6;
  v36 = a1;
  v29 = 0;
  v32 = 0;
  v33 = 0;
  v30 = 0;
  v31 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v14);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v17);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v17, v37, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v17);
  if ( wil::details::g_pfnOriginateCallback && (v18 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v17);
  if ( v19 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v14);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v16 = !IsDebuggerPresent())
      : (v16 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v14) == 0),
        v16)
    || (v18 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v17, v15);
    OutputDebugStringW(OutputString);
  }
  if ( ((v18 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v14);
  if ( (v18 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v17, v13);
}

```

## disassembly

```asm
0x1800034f0  push    rbp
0x1800034f2  push    rbx
0x1800034f3  push    rsi
0x1800034f4  push    rdi
0x1800034f5  push    r12
0x1800034f7  push    r14
0x1800034f9  push    r15
0x1800034fb  lea     rbp, [rsp-13D0h]
0x180003503  mov     eax, 14D0h
0x180003508  call    _alloca_probe
0x18000350d  sub     rsp, rax
0x180003510  mov     rax, cs:__security_cookie
0x180003517  xor     rax, rsp
0x18000351a  mov     [rbp+1400h+var_40], rax
0x180003521  mov     r14, r8
0x180003524  mov     esi, edx
0x180003526  mov     r15, rcx
0x180003529  mov     rdi, [rbp+1400h+arg_28]
0x180003530  xor     edx, edx; Val
0x180003532  mov     r8d, 98h; Size
0x180003538  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18000353d  call    memset_0
0x180003542  nop
0x180003543  xor     r12d, r12d
0x180003546  mov     [rbp+1400h+OutputString], r12w
0x18000354e  mov     [rbp+1400h+var_1440], r12b
0x180003552  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180003559  mov     ecx, [rdx]; this
0x18000355b  mov     [rsp+1500h+var_14D8], ecx
0x18000355f  mov     eax, [rdx+4]
0x180003562  mov     [rsp+1500h+var_14D4], eax
0x180003566  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000356b  mov     ebx, eax
0x18000356d  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180003575  mov     ecx, r12d
0x180003578  lea     eax, [r12+8]
0x18000357d  cmp     dword ptr [rdx+8], 1
0x180003581  cmovz   ecx, eax
0x180003584  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180003588  lea     ecx, [rax-7]
0x18000358b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003593  inc     ecx
0x180003595  mov     [rsp+1500h+var_14D0], ecx
0x180003599  mov     [rsp+1500h+var_14C8], r12
0x18000359e  call    cs:__imp_GetCurrentThreadId
0x1800035a4  mov     [rsp+1500h+var_14C0], eax
0x1800035a8  mov     [rsp+1500h+var_14A8], r14
0x1800035ad  mov     [rsp+1500h+var_14A0], esi
0x1800035b1  mov     [rsp+1500h+var_149C], ebx
0x1800035b5  mov     [rsp+1500h+var_14B8], r12
0x1800035ba  mov     [rsp+1500h+var_14B0], r12
0x1800035bf  mov     [rbp+1400h+var_1458], rdi
0x1800035c3  mov     [rbp+1400h+var_1450], r15
0x1800035c7  mov     [rsp+1500h+var_1498], r12
0x1800035cc  xorps   xmm0, xmm0
0x1800035cf  xor     eax, eax
0x1800035d1  movups  [rbp+1400h+var_1478], xmm0
0x1800035d5  mov     [rbp+1400h+var_1468], rax
0x1800035d9  xorps   xmm1, xmm1
0x1800035dc  movups  [rsp+1500h+var_1490], xmm1
0x1800035e1  mov     [rbp+1400h+var_1480], rax
0x1800035e5  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800035ec  test    rax, rax
0x1800035ef  jz      short loc_1800035FC
0x1800035f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035f6  mov     [rbp+1400h+var_1460], rax
0x1800035fa  jmp     short loc_180003600
0x1800035fc  mov     [rbp+1400h+var_1460], r12
0x180003600  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003607  test    rax, rax
0x18000360a  jz      short loc_180003616
0x18000360c  lea     rcx, [rsp+1500h+var_14E0]
0x180003611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003616  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000361d  test    rax, rax
0x180003620  jz      short loc_180003636
0x180003622  mov     r8d, 400h
0x180003628  lea     rdx, [rbp+1400h+var_1440]
0x18000362c  lea     rcx, [rsp+1500h+var_14E0]
0x180003631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003636  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000363d  test    rax, rax
0x180003640  jz      short loc_18000364C
0x180003642  lea     rcx, [rsp+1500h+var_14E0]
0x180003647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000364c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003653  test    rax, rax
0x180003656  jz      short loc_180003669
0x180003658  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000365d  jnz     short loc_180003669
0x18000365f  lea     rcx, [rsp+1500h+var_14E0]
0x180003664  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003669  cmp     [rsp+1500h+var_14D8], r12d
0x18000366e  jge     loc_180003777
0x180003674  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18000367b  jnz     short loc_18000369C
0x18000367d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003684  test    rax, rax
0x180003687  jz      short loc_180003692
0x180003689  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000368e  test    al, al
0x180003690  jmp     short loc_18000369A
0x180003692  call    cs:__imp_IsDebuggerPresent
0x180003698  test    eax, eax
0x18000369a  jz      short loc_1800036A3
0x18000369c  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800036a1  jz      short loc_1800036C9
0x1800036a3  mov     rax, cs:g_pfnResultLoggingCallback
0x1800036aa  test    rax, rax
0x1800036ad  jz      short loc_180003722
0x1800036af  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800036b6  jnz     short loc_180003722
0x1800036b8  xor     r8d, r8d
0x1800036bb  xor     edx, edx
0x1800036bd  lea     rcx, [rsp+1500h+var_14E0]
0x1800036c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036c7  jmp     short loc_180003722
0x1800036c9  mov     ebx, 800h
0x1800036ce  mov     rax, cs:g_pfnResultLoggingCallback
0x1800036d5  test    rax, rax
0x1800036d8  jz      short loc_1800036F7
0x1800036da  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800036e1  jnz     short loc_1800036F7
0x1800036e3  mov     r8d, ebx
0x1800036e6  lea     rdx, [rbp+1400h+OutputString]
0x1800036ed  lea     rcx, [rsp+1500h+var_14E0]
0x1800036f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036f7  cmp     [rbp+1400h+OutputString], r12w
0x1800036ff  jnz     short loc_180003715
0x180003701  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180003706  mov     rdx, rbx; unsigned __int16 *
0x180003709  lea     rcx, [rbp+1400h+OutputString]; this
0x180003710  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003715  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18000371c  call    cs:__imp_OutputDebugStringW
0x180003722  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180003727  jnz     short loc_180003732
0x180003729  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180003730  jz      short loc_180003744
0x180003732  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003739  test    rax, rax
0x18000373c  jz      short loc_180003744
0x18000373e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003743  nop
0x180003744  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180003749  jnz     short loc_18000376C
0x18000374b  mov     rcx, [rbp+1400h+var_40]
0x180003752  xor     rcx, rsp; StackCookie
0x180003755  call    __security_check_cookie
0x18000375a  add     rsp, 14D0h
0x180003761  pop     r15
0x180003763  pop     r14
0x180003765  pop     r12
0x180003767  pop     rdi
0x180003768  pop     rsi
0x180003769  pop     rbx
0x18000376a  pop     rbp
0x18000376b  retn
0x18000376c  lea     rcx, [rsp+1500h+var_14E0]; this
0x180003771  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180003777  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
