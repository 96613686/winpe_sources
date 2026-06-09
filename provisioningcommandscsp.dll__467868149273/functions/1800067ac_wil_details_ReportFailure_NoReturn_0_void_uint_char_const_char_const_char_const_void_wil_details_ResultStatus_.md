# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800067ac`
- end: `0x180006a6a`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `702`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800065e0`

## callees

- `0x180003814`
- `0x180004aa0`
- `0x180005780`
- `0x180005b0c`
- `0x180005ce8`
- `0x1800067ac`
- `0x18000cc8e`
- `0x18000cd80`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006855`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006855`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800069f8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800069f8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006956`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006956`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  bool v10; // r12
  int v11; // ebx
  int v12; // ecx
  __int64 v13; // rdx
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  char v18; // bl
  const struct wil::FailureInfo *v19; // rdx
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v27; // [rsp+48h] [rbp-B8h]
  __int64 v28; // [rsp+50h] [rbp-B0h]
  __int64 v29; // [rsp+58h] [rbp-A8h]
  int v30; // [rsp+60h] [rbp-A0h]
  int v31; // [rsp+64h] [rbp-9Ch]
  __int64 v32; // [rsp+68h] [rbp-98h]
  __int128 v33; // [rsp+70h] [rbp-90h]
  __int64 v34; // [rsp+80h] [rbp-80h]
  __int128 v35; // [rsp+88h] [rbp-78h]
  __int64 v36; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v38; // [rsp+A8h] [rbp-58h]
  __int64 v39; // [rsp+B0h] [rbp-50h]
  char v40[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v10 = g_pfnThrowPlatformException != 0;
  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v22 = *a7;
  v23 = a7[1];
  v11 = wil::details::RecordException((wil::details *)(unsigned int)v22, (int)a7);
  v20 = 0;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  v21 = v12;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v25 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v30 = a2;
  v31 = v11;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v36 = 0;
  v33 = 0;
  v34 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && !v10 && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v18 = 1, (v21 & 2) != 0) )
  {
    v18 = 0;
  }
  if ( v10 || v18 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048, v16);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v20, v16);
    if ( v18 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v20, 0, 0, v16);
  }
  if ( ((v21 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v21 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v20, v14);
  if ( v10 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v20, OutputString);
  wil::ThrowResultException((wil *)&v20, v14);
  wil::details::WilFailFast((wil::details *)&v20, v19);
}

```

## disassembly

```asm
0x1800067ac  mov     [rsp-8+arg_18], rbx
0x1800067b1  push    rbp
0x1800067b2  push    rsi
0x1800067b3  push    rdi
0x1800067b4  push    r12
0x1800067b6  push    r13
0x1800067b8  push    r14
0x1800067ba  push    r15
0x1800067bc  lea     rbp, [rsp-13C0h]
0x1800067c4  mov     eax, 14C0h
0x1800067c9  call    _alloca_probe
0x1800067ce  sub     rsp, rax
0x1800067d1  mov     r14, r8
0x1800067d4  mov     esi, edx
0x1800067d6  mov     r15, rcx
0x1800067d9  mov     rdi, [rbp+13F0h+arg_28]
0x1800067e0  xor     r13d, r13d
0x1800067e3  cmp     cs:g_pfnThrowPlatformException, r13
0x1800067ea  setnz   r12b
0x1800067ee  xor     edx, edx; Val
0x1800067f0  mov     r8d, 98h; Size
0x1800067f6  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800067fb  call    memset_0
0x180006800  nop
0x180006801  mov     [rbp+13F0h+OutputString], r13w
0x180006809  mov     [rbp+13F0h+var_1430], r13b
0x18000680d  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180006814  mov     ecx, [rdx]; this
0x180006816  mov     [rsp+14F0h+var_14C8], ecx
0x18000681a  mov     eax, [rdx+4]
0x18000681d  mov     [rsp+14F0h+var_14C4], eax
0x180006821  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180006826  mov     ebx, eax
0x180006828  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x18000682d  mov     ecx, r13d
0x180006830  lea     eax, [r13+8]
0x180006834  cmp     dword ptr [rdx+8], 1
0x180006838  cmovz   ecx, eax
0x18000683b  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000683f  lea     ecx, [rax-7]
0x180006842  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000684a  inc     ecx
0x18000684c  mov     [rsp+14F0h+var_14C0], ecx
0x180006850  mov     [rsp+14F0h+var_14B8], r13
0x180006855  call    cs:__imp_GetCurrentThreadId
0x18000685c  nop     dword ptr [rax+rax+00h]
0x180006861  mov     [rsp+14F0h+var_14B0], eax
0x180006865  mov     [rsp+14F0h+var_1498], r14
0x18000686a  mov     [rsp+14F0h+var_1490], esi
0x18000686e  mov     [rsp+14F0h+var_148C], ebx
0x180006872  mov     [rsp+14F0h+var_14A8], r13
0x180006877  mov     [rsp+14F0h+var_14A0], r13
0x18000687c  mov     [rbp+13F0h+var_1448], rdi
0x180006880  mov     [rbp+13F0h+var_1440], r15
0x180006884  mov     [rsp+14F0h+var_1488], r13
0x180006889  xorps   xmm0, xmm0
0x18000688c  xor     eax, eax
0x18000688e  movups  [rbp+13F0h+var_1468], xmm0
0x180006892  mov     [rbp+13F0h+var_1458], rax
0x180006896  xorps   xmm1, xmm1
0x180006899  movups  [rsp+14F0h+var_1480], xmm1
0x18000689e  mov     [rbp+13F0h+var_1470], rax
0x1800068a2  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800068a9  test    rax, rax
0x1800068ac  jz      short loc_1800068B9
0x1800068ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068b3  mov     [rbp+13F0h+var_1450], rax
0x1800068b7  jmp     short loc_1800068BD
0x1800068b9  mov     [rbp+13F0h+var_1450], r13
0x1800068bd  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800068c4  test    rax, rax
0x1800068c7  jz      short loc_1800068D3
0x1800068c9  lea     rcx, [rsp+14F0h+var_14D0]
0x1800068ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068d3  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800068da  test    rax, rax
0x1800068dd  jz      short loc_1800068F3
0x1800068df  mov     r8d, 400h
0x1800068e5  lea     rdx, [rbp+13F0h+var_1430]
0x1800068e9  lea     rcx, [rsp+14F0h+var_14D0]
0x1800068ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068f3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800068fa  test    rax, rax
0x1800068fd  jz      short loc_180006909
0x1800068ff  lea     rcx, [rsp+14F0h+var_14D0]
0x180006904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006909  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006910  test    rax, rax
0x180006913  jz      short loc_18000692B
0x180006915  test    r12b, r12b
0x180006918  jnz     short loc_18000692B
0x18000691a  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000691f  jnz     short loc_18000692B
0x180006921  lea     rcx, [rsp+14F0h+var_14D0]
0x180006926  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000692b  cmp     [rsp+14F0h+var_14C8], r13d
0x180006930  jl      short loc_180006938
0x180006932  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180006938  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000693f  jnz     short loc_180006966
0x180006941  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180006948  test    rax, rax
0x18000694b  jz      short loc_180006956
0x18000694d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006952  test    al, al
0x180006954  jmp     short loc_180006964
0x180006956  call    cs:__imp_IsDebuggerPresent
0x18000695d  nop     dword ptr [rax+rax+00h]
0x180006962  test    eax, eax
0x180006964  jz      short loc_18000696F
0x180006966  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000696b  mov     bl, 1
0x18000696d  jz      short loc_180006972
0x18000696f  mov     bl, r13b
0x180006972  test    r12b, r12b
0x180006975  jnz     short loc_1800069A1
0x180006977  test    bl, bl
0x180006979  jnz     short loc_1800069A1
0x18000697b  mov     rax, cs:g_pfnResultLoggingCallback
0x180006982  test    rax, rax
0x180006985  jz      short loc_180006A04
0x180006987  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000698e  jnz     short loc_180006A04
0x180006990  xor     r8d, r8d
0x180006993  xor     edx, edx
0x180006995  lea     rcx, [rsp+14F0h+var_14D0]
0x18000699a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000699f  jmp     short loc_180006A04
0x1800069a1  mov     edi, 800h
0x1800069a6  mov     rax, cs:g_pfnResultLoggingCallback
0x1800069ad  test    rax, rax
0x1800069b0  jz      short loc_1800069CF
0x1800069b2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800069b9  jnz     short loc_1800069CF
0x1800069bb  mov     r8d, edi
0x1800069be  lea     rdx, [rbp+13F0h+OutputString]
0x1800069c5  lea     rcx, [rsp+14F0h+var_14D0]
0x1800069ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069cf  cmp     [rbp+13F0h+OutputString], r13w
0x1800069d7  jnz     short loc_1800069ED
0x1800069d9  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800069de  mov     rdx, rdi; unsigned __int16 *
0x1800069e1  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800069e8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800069ed  test    bl, bl
0x1800069ef  jz      short loc_180006A04
0x1800069f1  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800069f8  call    cs:__imp_OutputDebugStringW
0x1800069ff  nop     dword ptr [rax+rax+00h]
0x180006a04  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180006a09  jnz     short loc_180006A14
0x180006a0b  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180006a12  jz      short loc_180006A26
0x180006a14  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006a1b  test    rax, rax
0x180006a1e  jz      short loc_180006A26
0x180006a20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a25  nop
0x180006a26  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180006a2b  jz      short loc_180006A38
0x180006a2d  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180006a32  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180006a38  test    r12b, r12b
0x180006a3b  jz      short loc_180006A55
0x180006a3d  lea     rdx, [rbp+13F0h+OutputString]
0x180006a44  lea     rcx, [rsp+14F0h+var_14D0]
0x180006a49  mov     rax, cs:g_pfnThrowPlatformException
0x180006a50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a55  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180006a5a  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x180006a5f  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180006a64  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
