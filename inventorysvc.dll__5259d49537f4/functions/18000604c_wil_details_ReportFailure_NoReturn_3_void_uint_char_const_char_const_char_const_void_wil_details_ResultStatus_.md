# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18000604c`
- end: `0x1800062ae`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `610`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180005d4c`

## callees

- `0x1800038b8`
- `0x18000604c`
- `0x18000b994`
- `0x18000c13c`
- `0x18000da10`
- `0x180010630`
- `0x1800ce770`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800060ee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800060ee`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800061f1`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800061f1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000627b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000627b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v10; // edx
  int v11; // edi
  int v12; // ecx
  const struct wil::FailureInfo *v13; // rdx
  __int64 v14; // rcx
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
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v17, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
  v19 = *a7;
  v20 = a7[1];
  v11 = wil::details::RecordFailFast((wil::details *)(unsigned int)v19, v10);
  v17 = 3;
  v12 = 0;
  if ( a7[2] == 1 )
    v12 = 8;
  v18 = v12;
  v21 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v26 = a3;
  v27 = a2;
  v28 = v11;
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
  {
    v19 = -2147418113;
    v20 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v13);
  }
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
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v17, v15);
    OutputDebugStringW(OutputString);
  }
  if ( (v18 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v14);
  }
  wil::details::WilFailFast((wil::details *)&v17, v13);
}

```

## disassembly

```asm
0x18000604c  mov     [rsp-8+arg_18], rbx
0x180006051  push    rbp
0x180006052  push    rsi
0x180006053  push    rdi
0x180006054  push    r12
0x180006056  push    r13
0x180006058  push    r14
0x18000605a  push    r15
0x18000605c  lea     rbp, [rsp-13C0h]
0x180006064  mov     eax, 14C0h
0x180006069  call    _alloca_probe
0x18000606e  sub     rsp, rax
0x180006071  mov     r15, r8
0x180006074  mov     r14d, edx
0x180006077  mov     r12, rcx
0x18000607a  mov     rsi, [rbp+13F0h+arg_28]
0x180006081  xor     edx, edx; Val
0x180006083  mov     r8d, 98h; Size
0x180006089  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000608e  call    memset_0
0x180006093  nop
0x180006094  xor     r13d, r13d
0x180006097  mov     [rbp+13F0h+OutputString], r13w
0x18000609f  mov     [rbp+13F0h+var_1430], r13b
0x1800060a3  mov     rbx, [rbp+13F0h+arg_30]
0x1800060aa  mov     ecx, [rbx]; this
0x1800060ac  mov     [rsp+14F0h+var_14C8], ecx
0x1800060b0  mov     eax, [rbx+4]
0x1800060b3  mov     [rsp+14F0h+var_14C4], eax
0x1800060b7  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800060bc  mov     edi, eax
0x1800060be  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x1800060c6  mov     ecx, r13d
0x1800060c9  lea     eax, [r13+8]
0x1800060cd  cmp     dword ptr [rbx+8], 1
0x1800060d1  cmovz   ecx, eax
0x1800060d4  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800060d8  lea     ecx, [rax-7]
0x1800060db  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800060e3  inc     ecx
0x1800060e5  mov     [rsp+14F0h+var_14C0], ecx
0x1800060e9  mov     [rsp+14F0h+var_14B8], r13
0x1800060ee  call    cs:__imp_GetCurrentThreadId
0x1800060f4  mov     [rsp+14F0h+var_14B0], eax
0x1800060f8  mov     [rsp+14F0h+var_1498], r15
0x1800060fd  mov     [rsp+14F0h+var_1490], r14d
0x180006102  mov     [rsp+14F0h+var_148C], edi
0x180006106  mov     [rsp+14F0h+var_14A8], r13
0x18000610b  mov     [rsp+14F0h+var_14A0], r13
0x180006110  mov     [rbp+13F0h+var_1448], rsi
0x180006114  mov     [rbp+13F0h+var_1440], r12
0x180006118  mov     [rsp+14F0h+var_1488], r13
0x18000611d  xorps   xmm0, xmm0
0x180006120  xor     eax, eax
0x180006122  movups  [rbp+13F0h+var_1468], xmm0
0x180006126  mov     [rbp+13F0h+var_1458], rax
0x18000612a  xorps   xmm1, xmm1
0x18000612d  movups  [rsp+14F0h+var_1480], xmm1
0x180006132  mov     [rbp+13F0h+var_1470], rax
0x180006136  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000613d  test    rax, rax
0x180006140  jz      short loc_18000614D
0x180006142  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006147  mov     [rbp+13F0h+var_1450], rax
0x18000614b  jmp     short loc_180006151
0x18000614d  mov     [rbp+13F0h+var_1450], r13
0x180006151  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006158  test    rax, rax
0x18000615b  jz      short loc_180006167
0x18000615d  lea     rcx, [rsp+14F0h+var_14D0]
0x180006162  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006167  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000616e  test    rax, rax
0x180006171  jz      short loc_180006187
0x180006173  mov     r8d, 400h
0x180006179  lea     rdx, [rbp+13F0h+var_1430]
0x18000617d  lea     rcx, [rsp+14F0h+var_14D0]
0x180006182  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006187  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000618e  test    rax, rax
0x180006191  jz      short loc_18000619D
0x180006193  lea     rcx, [rsp+14F0h+var_14D0]
0x180006198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000619d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800061a4  test    rax, rax
0x1800061a7  jz      short loc_1800061BA
0x1800061a9  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800061ae  jnz     short loc_1800061BA
0x1800061b0  lea     rcx, [rsp+14F0h+var_14D0]
0x1800061b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061ba  cmp     [rsp+14F0h+var_14C8], r13d
0x1800061bf  jl      short loc_1800061D3
0x1800061c1  mov     ecx, 8000FFFFh; this
0x1800061c6  mov     [rsp+14F0h+var_14C8], ecx
0x1800061ca  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800061cf  mov     [rsp+14F0h+var_14C4], eax
0x1800061d3  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x1800061da  jnz     short loc_1800061FB
0x1800061dc  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800061e3  test    rax, rax
0x1800061e6  jz      short loc_1800061F1
0x1800061e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061ed  test    al, al
0x1800061ef  jmp     short loc_1800061F9
0x1800061f1  call    cs:__imp_IsDebuggerPresent
0x1800061f7  test    eax, eax
0x1800061f9  jz      short loc_180006202
0x1800061fb  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180006200  jz      short loc_180006228
0x180006202  mov     rax, cs:g_pfnResultLoggingCallback
0x180006209  test    rax, rax
0x18000620c  jz      short loc_180006281
0x18000620e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180006215  jnz     short loc_180006281
0x180006217  xor     r8d, r8d
0x18000621a  xor     edx, edx
0x18000621c  lea     rcx, [rsp+14F0h+var_14D0]
0x180006221  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006226  jmp     short loc_180006281
0x180006228  mov     ebx, 800h
0x18000622d  mov     rax, cs:g_pfnResultLoggingCallback
0x180006234  test    rax, rax
0x180006237  jz      short loc_180006256
0x180006239  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180006240  jnz     short loc_180006256
0x180006242  mov     r8d, ebx
0x180006245  lea     rdx, [rbp+13F0h+OutputString]
0x18000624c  lea     rcx, [rsp+14F0h+var_14D0]
0x180006251  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006256  cmp     [rbp+13F0h+OutputString], r13w
0x18000625e  jnz     short loc_180006274
0x180006260  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180006265  mov     rdx, rbx; unsigned __int16 *
0x180006268  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000626f  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180006274  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000627b  call    cs:__imp_OutputDebugStringW
0x180006281  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180006286  jnz     short loc_180006291
0x180006288  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18000628f  jz      short loc_1800062A3
0x180006291  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006298  test    rax, rax
0x18000629b  jz      short loc_1800062A3
0x18000629d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062a2  nop
0x1800062a3  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800062a8  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
