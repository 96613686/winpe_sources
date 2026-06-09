# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18001eb50`
- end: `0x18001ee0e`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `702`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18001e93c`

## callees

- `0x180018944`
- `0x180019b44`
- `0x18001b07c`
- `0x18001b4f0`
- `0x18001b82c`
- `0x18001eb50`
- `0x1800227f2`
- `0x1800228f0`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ebf9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ebf9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001ecfa`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001ecfa`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001ed9c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001ed9c`

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
      g_pfnResultLoggingCallback(&v20, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v20, v16);
    if ( v18 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v20, 0, 0);
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
0x18001eb50  mov     [rsp-8+arg_18], rbx
0x18001eb55  push    rbp
0x18001eb56  push    rsi
0x18001eb57  push    rdi
0x18001eb58  push    r12
0x18001eb5a  push    r13
0x18001eb5c  push    r14
0x18001eb5e  push    r15
0x18001eb60  lea     rbp, [rsp-13C0h]
0x18001eb68  mov     eax, 14C0h
0x18001eb6d  call    _alloca_probe
0x18001eb72  sub     rsp, rax
0x18001eb75  mov     r14, r8
0x18001eb78  mov     esi, edx
0x18001eb7a  mov     r15, rcx
0x18001eb7d  mov     rdi, [rbp+13F0h+arg_28]
0x18001eb84  xor     r13d, r13d
0x18001eb87  cmp     cs:g_pfnThrowPlatformException, r13
0x18001eb8e  setnz   r12b
0x18001eb92  xor     edx, edx; Val
0x18001eb94  mov     r8d, 98h; Size
0x18001eb9a  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18001eb9f  call    memset_0
0x18001eba4  nop
0x18001eba5  mov     [rbp+13F0h+OutputString], r13w
0x18001ebad  mov     [rbp+13F0h+var_1430], r13b
0x18001ebb1  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18001ebb8  mov     ecx, [rdx]; this
0x18001ebba  mov     [rsp+14F0h+var_14C8], ecx
0x18001ebbe  mov     eax, [rdx+4]
0x18001ebc1  mov     [rsp+14F0h+var_14C4], eax
0x18001ebc5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18001ebca  mov     ebx, eax
0x18001ebcc  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x18001ebd1  mov     ecx, r13d
0x18001ebd4  lea     eax, [r13+8]
0x18001ebd8  cmp     dword ptr [rdx+8], 1
0x18001ebdc  cmovz   ecx, eax
0x18001ebdf  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18001ebe3  lea     ecx, [rax-7]
0x18001ebe6  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18001ebee  inc     ecx
0x18001ebf0  mov     [rsp+14F0h+var_14C0], ecx
0x18001ebf4  mov     [rsp+14F0h+var_14B8], r13
0x18001ebf9  call    cs:__imp_GetCurrentThreadId
0x18001ec00  nop     dword ptr [rax+rax+00h]
0x18001ec05  mov     [rsp+14F0h+var_14B0], eax
0x18001ec09  mov     [rsp+14F0h+var_1498], r14
0x18001ec0e  mov     [rsp+14F0h+var_1490], esi
0x18001ec12  mov     [rsp+14F0h+var_148C], ebx
0x18001ec16  mov     [rsp+14F0h+var_14A8], r13
0x18001ec1b  mov     [rsp+14F0h+var_14A0], r13
0x18001ec20  mov     [rbp+13F0h+var_1448], rdi
0x18001ec24  mov     [rbp+13F0h+var_1440], r15
0x18001ec28  mov     [rsp+14F0h+var_1488], r13
0x18001ec2d  xorps   xmm0, xmm0
0x18001ec30  xor     eax, eax
0x18001ec32  movups  [rbp+13F0h+var_1468], xmm0
0x18001ec36  mov     [rbp+13F0h+var_1458], rax
0x18001ec3a  xorps   xmm1, xmm1
0x18001ec3d  movups  [rsp+14F0h+var_1480], xmm1
0x18001ec42  mov     [rbp+13F0h+var_1470], rax
0x18001ec46  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001ec4d  test    rax, rax
0x18001ec50  jz      short loc_18001EC5D
0x18001ec52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec57  mov     [rbp+13F0h+var_1450], rax
0x18001ec5b  jmp     short loc_18001EC61
0x18001ec5d  mov     [rbp+13F0h+var_1450], r13
0x18001ec61  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18001ec68  test    rax, rax
0x18001ec6b  jz      short loc_18001EC77
0x18001ec6d  lea     rcx, [rsp+14F0h+var_14D0]
0x18001ec72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec77  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001ec7e  test    rax, rax
0x18001ec81  jz      short loc_18001EC97
0x18001ec83  mov     r8d, 400h
0x18001ec89  lea     rdx, [rbp+13F0h+var_1430]
0x18001ec8d  lea     rcx, [rsp+14F0h+var_14D0]
0x18001ec92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec97  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001ec9e  test    rax, rax
0x18001eca1  jz      short loc_18001ECAD
0x18001eca3  lea     rcx, [rsp+14F0h+var_14D0]
0x18001eca8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ecad  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001ecb4  test    rax, rax
0x18001ecb7  jz      short loc_18001ECCF
0x18001ecb9  test    r12b, r12b
0x18001ecbc  jnz     short loc_18001ECCF
0x18001ecbe  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18001ecc3  jnz     short loc_18001ECCF
0x18001ecc5  lea     rcx, [rsp+14F0h+var_14D0]
0x18001ecca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eccf  cmp     [rsp+14F0h+var_14C8], r13d
0x18001ecd4  jl      short loc_18001ECDC
0x18001ecd6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18001ecdc  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18001ece3  jnz     short loc_18001ED0A
0x18001ece5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001ecec  test    rax, rax
0x18001ecef  jz      short loc_18001ECFA
0x18001ecf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ecf6  test    al, al
0x18001ecf8  jmp     short loc_18001ED08
0x18001ecfa  call    cs:__imp_IsDebuggerPresent
0x18001ed01  nop     dword ptr [rax+rax+00h]
0x18001ed06  test    eax, eax
0x18001ed08  jz      short loc_18001ED13
0x18001ed0a  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18001ed0f  mov     bl, 1
0x18001ed11  jz      short loc_18001ED16
0x18001ed13  mov     bl, r13b
0x18001ed16  test    r12b, r12b
0x18001ed19  jnz     short loc_18001ED45
0x18001ed1b  test    bl, bl
0x18001ed1d  jnz     short loc_18001ED45
0x18001ed1f  mov     rax, cs:g_pfnResultLoggingCallback
0x18001ed26  test    rax, rax
0x18001ed29  jz      short loc_18001EDA8
0x18001ed2b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18001ed32  jnz     short loc_18001EDA8
0x18001ed34  xor     r8d, r8d
0x18001ed37  xor     edx, edx
0x18001ed39  lea     rcx, [rsp+14F0h+var_14D0]
0x18001ed3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed43  jmp     short loc_18001EDA8
0x18001ed45  mov     edi, 800h
0x18001ed4a  mov     rax, cs:g_pfnResultLoggingCallback
0x18001ed51  test    rax, rax
0x18001ed54  jz      short loc_18001ED73
0x18001ed56  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18001ed5d  jnz     short loc_18001ED73
0x18001ed5f  mov     r8d, edi
0x18001ed62  lea     rdx, [rbp+13F0h+OutputString]
0x18001ed69  lea     rcx, [rsp+14F0h+var_14D0]
0x18001ed6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed73  cmp     [rbp+13F0h+OutputString], r13w
0x18001ed7b  jnz     short loc_18001ED91
0x18001ed7d  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18001ed82  mov     rdx, rdi; unsigned __int16 *
0x18001ed85  lea     rcx, [rbp+13F0h+OutputString]; this
0x18001ed8c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18001ed91  test    bl, bl
0x18001ed93  jz      short loc_18001EDA8
0x18001ed95  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18001ed9c  call    cs:__imp_OutputDebugStringW
0x18001eda3  nop     dword ptr [rax+rax+00h]
0x18001eda8  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18001edad  jnz     short loc_18001EDB8
0x18001edaf  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18001edb6  jz      short loc_18001EDCA
0x18001edb8  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001edbf  test    rax, rax
0x18001edc2  jz      short loc_18001EDCA
0x18001edc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001edc9  nop
0x18001edca  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18001edcf  jz      short loc_18001EDDC
0x18001edd1  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18001edd6  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18001eddc  test    r12b, r12b
0x18001eddf  jz      short loc_18001EDF9
0x18001ede1  lea     rdx, [rbp+13F0h+OutputString]
0x18001ede8  lea     rcx, [rsp+14F0h+var_14D0]
0x18001eded  mov     rax, cs:g_pfnThrowPlatformException
0x18001edf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001edf9  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18001edfe  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x18001ee03  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18001ee08  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
