# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180003568`
- end: `0x18000380e`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180002ffc`

## callees

- `0x180001ba0`
- `0x18000296c`
- `0x180003568`
- `0x1800046f4`
- `0x180005630`
- `0x1800066d0`
- `0x1800067ac`
- `0x18000d560`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000362e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000362e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800037ad`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800037ad`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003723`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003723`

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
0x180003568  push    rbp
0x18000356a  push    rbx
0x18000356b  push    rsi
0x18000356c  push    rdi
0x18000356d  push    r12
0x18000356f  push    r14
0x180003571  push    r15
0x180003573  lea     rbp, [rsp-13D0h]
0x18000357b  mov     eax, 14D0h
0x180003580  call    _alloca_probe
0x180003585  sub     rsp, rax
0x180003588  mov     rax, cs:__security_cookie
0x18000358f  xor     rax, rsp
0x180003592  mov     [rbp+1400h+var_40], rax
0x180003599  mov     rsi, r8
0x18000359c  mov     edi, edx
0x18000359e  mov     rbx, rcx
0x1800035a1  mov     r14, [rbp+1400h+arg_28]
0x1800035a8  xor     edx, edx; Val
0x1800035aa  mov     r8d, 98h; Size
0x1800035b0  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1800035b5  call    memset_0
0x1800035ba  nop
0x1800035bb  xor     r12d, r12d
0x1800035be  mov     [rbp+1400h+OutputString], r12w
0x1800035c6  mov     [rbp+1400h+var_1440], r12b
0x1800035ca  mov     rdx, [rbp+1400h+arg_30]; int
0x1800035d1  mov     ecx, [rdx]; this
0x1800035d3  mov     [rsp+1500h+var_14D8], ecx
0x1800035d7  mov     eax, [rdx+4]
0x1800035da  mov     [rsp+1500h+var_14D4], eax
0x1800035de  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800035e3  mov     r15d, eax
0x1800035e6  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800035ee  mov     ecx, r12d
0x1800035f1  lea     eax, [r12+8]
0x1800035f6  cmp     dword ptr [rdx+8], 1
0x1800035fa  cmovz   ecx, eax
0x1800035fd  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180003601  lea     ecx, [rax-7]
0x180003604  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000360c  inc     ecx
0x18000360e  mov     [rsp+1500h+var_14D0], ecx
0x180003612  mov     rcx, [rbp+1400h+arg_38]
0x180003619  test    rcx, rcx
0x18000361c  jz      short loc_180003629
0x18000361e  cmp     [rcx], r12w
0x180003622  mov     [rsp+1500h+var_14C8], rcx
0x180003627  jnz     short loc_18000362E
0x180003629  mov     [rsp+1500h+var_14C8], r12
0x18000362e  call    cs:__imp_GetCurrentThreadId
0x180003634  mov     [rsp+1500h+var_14C0], eax
0x180003638  mov     [rsp+1500h+var_14A8], rsi
0x18000363d  mov     [rsp+1500h+var_14A0], edi
0x180003641  mov     [rsp+1500h+var_149C], r15d
0x180003646  mov     [rsp+1500h+var_14B8], r12
0x18000364b  mov     [rsp+1500h+var_14B0], r12
0x180003650  mov     [rbp+1400h+var_1458], r14
0x180003654  mov     [rbp+1400h+var_1450], rbx
0x180003658  mov     [rsp+1500h+var_1498], r12
0x18000365d  xorps   xmm0, xmm0
0x180003660  xor     eax, eax
0x180003662  movups  [rbp+1400h+var_1478], xmm0
0x180003666  mov     [rbp+1400h+var_1468], rax
0x18000366a  xorps   xmm1, xmm1
0x18000366d  movups  [rsp+1500h+var_1490], xmm1
0x180003672  mov     [rbp+1400h+var_1480], rax
0x180003676  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000367d  test    rax, rax
0x180003680  jz      short loc_18000368D
0x180003682  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003687  mov     [rbp+1400h+var_1460], rax
0x18000368b  jmp     short loc_180003691
0x18000368d  mov     [rbp+1400h+var_1460], r12
0x180003691  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003698  test    rax, rax
0x18000369b  jz      short loc_1800036A7
0x18000369d  lea     rcx, [rsp+1500h+var_14E0]
0x1800036a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036a7  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800036ae  test    rax, rax
0x1800036b1  jz      short loc_1800036C7
0x1800036b3  mov     r8d, 400h
0x1800036b9  lea     rdx, [rbp+1400h+var_1440]
0x1800036bd  lea     rcx, [rsp+1500h+var_14E0]
0x1800036c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036c7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800036ce  test    rax, rax
0x1800036d1  jz      short loc_1800036DD
0x1800036d3  lea     rcx, [rsp+1500h+var_14E0]
0x1800036d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036dd  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800036e4  test    rax, rax
0x1800036e7  jz      short loc_1800036FA
0x1800036e9  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800036ee  jnz     short loc_1800036FA
0x1800036f0  lea     rcx, [rsp+1500h+var_14E0]
0x1800036f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036fa  cmp     [rsp+1500h+var_14D8], r12d
0x1800036ff  jge     loc_180003808
0x180003705  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18000370c  jnz     short loc_18000372D
0x18000370e  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003715  test    rax, rax
0x180003718  jz      short loc_180003723
0x18000371a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000371f  test    al, al
0x180003721  jmp     short loc_18000372B
0x180003723  call    cs:__imp_IsDebuggerPresent
0x180003729  test    eax, eax
0x18000372b  jz      short loc_180003734
0x18000372d  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003732  jz      short loc_18000375A
0x180003734  mov     rax, cs:g_pfnResultLoggingCallback
0x18000373b  test    rax, rax
0x18000373e  jz      short loc_1800037B3
0x180003740  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003747  jnz     short loc_1800037B3
0x180003749  xor     r8d, r8d
0x18000374c  xor     edx, edx
0x18000374e  lea     rcx, [rsp+1500h+var_14E0]
0x180003753  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003758  jmp     short loc_1800037B3
0x18000375a  mov     ebx, 800h
0x18000375f  mov     rax, cs:g_pfnResultLoggingCallback
0x180003766  test    rax, rax
0x180003769  jz      short loc_180003788
0x18000376b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003772  jnz     short loc_180003788
0x180003774  mov     r8d, ebx
0x180003777  lea     rdx, [rbp+1400h+OutputString]
0x18000377e  lea     rcx, [rsp+1500h+var_14E0]
0x180003783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003788  cmp     [rbp+1400h+OutputString], r12w
0x180003790  jnz     short loc_1800037A6
0x180003792  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180003797  mov     rdx, rbx; unsigned __int16 *
0x18000379a  lea     rcx, [rbp+1400h+OutputString]; this
0x1800037a1  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800037a6  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1800037ad  call    cs:__imp_OutputDebugStringW
0x1800037b3  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1800037b8  jnz     short loc_1800037C3
0x1800037ba  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800037c1  jz      short loc_1800037D5
0x1800037c3  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800037ca  test    rax, rax
0x1800037cd  jz      short loc_1800037D5
0x1800037cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037d4  nop
0x1800037d5  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1800037da  jnz     short loc_1800037FD
0x1800037dc  mov     rcx, [rbp+1400h+var_40]
0x1800037e3  xor     rcx, rsp; StackCookie
0x1800037e6  call    __security_check_cookie
0x1800037eb  add     rsp, 14D0h
0x1800037f2  pop     r15
0x1800037f4  pop     r14
0x1800037f6  pop     r12
0x1800037f8  pop     rdi
0x1800037f9  pop     rsi
0x1800037fa  pop     rbx
0x1800037fb  pop     rbp
0x1800037fc  retn
0x1800037fd  lea     rcx, [rsp+1500h+var_14E0]; this
0x180003802  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180003808  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
