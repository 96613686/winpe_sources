# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18000be28`
- end: `0x18000c0d4`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `684`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000bb5c`

## callees

- `0x180002efc`
- `0x180006fe4`
- `0x1800083f0`
- `0x18000a430`
- `0x18000ab80`
- `0x18000ad4c`
- `0x18000be28`
- `0x1800588d0`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bed1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bed1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000c068`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000c068`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000bfcc`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000bfcc`

## pseudocode

```c
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
0x18000be28  mov     [rsp-8+arg_18], rbx
0x18000be2d  push    rbp
0x18000be2e  push    rsi
0x18000be2f  push    rdi
0x18000be30  push    r12
0x18000be32  push    r13
0x18000be34  push    r14
0x18000be36  push    r15
0x18000be38  lea     rbp, [rsp-13C0h]
0x18000be40  mov     eax, 14C0h
0x18000be45  call    _alloca_probe
0x18000be4a  sub     rsp, rax
0x18000be4d  mov     r14, r8
0x18000be50  mov     esi, edx
0x18000be52  mov     r15, rcx
0x18000be55  mov     rdi, [rbp+13F0h+arg_28]
0x18000be5c  xor     r13d, r13d
0x18000be5f  cmp     cs:g_pfnThrowPlatformException, r13
0x18000be66  setnz   r12b
0x18000be6a  xor     edx, edx; Val
0x18000be6c  mov     r8d, 98h; Size
0x18000be72  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000be77  call    memset_0
0x18000be7c  nop
0x18000be7d  mov     [rbp+13F0h+OutputString], r13w
0x18000be85  mov     [rbp+13F0h+var_1430], r13b
0x18000be89  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18000be90  mov     ecx, [rdx]; this
0x18000be92  mov     [rsp+14F0h+var_14C8], ecx
0x18000be96  mov     eax, [rdx+4]
0x18000be99  mov     [rsp+14F0h+var_14C4], eax
0x18000be9d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000bea2  mov     ebx, eax
0x18000bea4  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x18000bea9  mov     ecx, r13d
0x18000beac  lea     eax, [r13+8]
0x18000beb0  cmp     dword ptr [rdx+8], 1
0x18000beb4  cmovz   ecx, eax
0x18000beb7  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000bebb  lea     ecx, [rax-7]
0x18000bebe  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000bec6  inc     ecx
0x18000bec8  mov     [rsp+14F0h+var_14C0], ecx
0x18000becc  mov     [rsp+14F0h+var_14B8], r13
0x18000bed1  call    cs:__imp_GetCurrentThreadId
0x18000bed7  mov     [rsp+14F0h+var_14B0], eax
0x18000bedb  mov     [rsp+14F0h+var_1498], r14
0x18000bee0  mov     [rsp+14F0h+var_1490], esi
0x18000bee4  mov     [rsp+14F0h+var_148C], ebx
0x18000bee8  mov     [rsp+14F0h+var_14A8], r13
0x18000beed  mov     [rsp+14F0h+var_14A0], r13
0x18000bef2  mov     [rbp+13F0h+var_1448], rdi
0x18000bef6  mov     [rbp+13F0h+var_1440], r15
0x18000befa  mov     [rsp+14F0h+var_1488], r13
0x18000beff  xorps   xmm0, xmm0
0x18000bf02  xor     eax, eax
0x18000bf04  movups  [rbp+13F0h+var_1468], xmm0
0x18000bf08  mov     [rbp+13F0h+var_1458], rax
0x18000bf0c  xorps   xmm1, xmm1
0x18000bf0f  movups  [rsp+14F0h+var_1480], xmm1
0x18000bf14  mov     [rbp+13F0h+var_1470], rax
0x18000bf18  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000bf1f  test    rax, rax
0x18000bf22  jz      short loc_18000BF2F
0x18000bf24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf29  mov     [rbp+13F0h+var_1450], rax
0x18000bf2d  jmp     short loc_18000BF33
0x18000bf2f  mov     [rbp+13F0h+var_1450], r13
0x18000bf33  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000bf3a  test    rax, rax
0x18000bf3d  jz      short loc_18000BF49
0x18000bf3f  lea     rcx, [rsp+14F0h+var_14D0]
0x18000bf44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf49  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000bf50  test    rax, rax
0x18000bf53  jz      short loc_18000BF69
0x18000bf55  mov     r8d, 400h
0x18000bf5b  lea     rdx, [rbp+13F0h+var_1430]
0x18000bf5f  lea     rcx, [rsp+14F0h+var_14D0]
0x18000bf64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf69  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000bf70  test    rax, rax
0x18000bf73  jz      short loc_18000BF7F
0x18000bf75  lea     rcx, [rsp+14F0h+var_14D0]
0x18000bf7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf7f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000bf86  test    rax, rax
0x18000bf89  jz      short loc_18000BFA1
0x18000bf8b  test    r12b, r12b
0x18000bf8e  jnz     short loc_18000BFA1
0x18000bf90  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000bf95  jnz     short loc_18000BFA1
0x18000bf97  lea     rcx, [rsp+14F0h+var_14D0]
0x18000bf9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfa1  cmp     [rsp+14F0h+var_14C8], r13d
0x18000bfa6  jl      short loc_18000BFAE
0x18000bfa8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000bfae  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000bfb5  jnz     short loc_18000BFD6
0x18000bfb7  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000bfbe  test    rax, rax
0x18000bfc1  jz      short loc_18000BFCC
0x18000bfc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfc8  test    al, al
0x18000bfca  jmp     short loc_18000BFD4
0x18000bfcc  call    cs:__imp_IsDebuggerPresent
0x18000bfd2  test    eax, eax
0x18000bfd4  jz      short loc_18000BFDF
0x18000bfd6  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000bfdb  mov     bl, 1
0x18000bfdd  jz      short loc_18000BFE2
0x18000bfdf  mov     bl, r13b
0x18000bfe2  test    r12b, r12b
0x18000bfe5  jnz     short loc_18000C011
0x18000bfe7  test    bl, bl
0x18000bfe9  jnz     short loc_18000C011
0x18000bfeb  mov     rax, cs:g_pfnResultLoggingCallback
0x18000bff2  test    rax, rax
0x18000bff5  jz      short loc_18000C06E
0x18000bff7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000bffe  jnz     short loc_18000C06E
0x18000c000  xor     r8d, r8d
0x18000c003  xor     edx, edx
0x18000c005  lea     rcx, [rsp+14F0h+var_14D0]
0x18000c00a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c00f  jmp     short loc_18000C06E
0x18000c011  mov     edi, 800h
0x18000c016  mov     rax, cs:g_pfnResultLoggingCallback
0x18000c01d  test    rax, rax
0x18000c020  jz      short loc_18000C03F
0x18000c022  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000c029  jnz     short loc_18000C03F
0x18000c02b  mov     r8d, edi
0x18000c02e  lea     rdx, [rbp+13F0h+OutputString]
0x18000c035  lea     rcx, [rsp+14F0h+var_14D0]
0x18000c03a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c03f  cmp     [rbp+13F0h+OutputString], r13w
0x18000c047  jnz     short loc_18000C05D
0x18000c049  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000c04e  mov     rdx, rdi; unsigned __int16 *
0x18000c051  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000c058  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000c05d  test    bl, bl
0x18000c05f  jz      short loc_18000C06E
0x18000c061  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000c068  call    cs:__imp_OutputDebugStringW
0x18000c06e  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000c073  jnz     short loc_18000C07E
0x18000c075  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18000c07c  jz      short loc_18000C090
0x18000c07e  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000c085  test    rax, rax
0x18000c088  jz      short loc_18000C090
0x18000c08a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c08f  nop
0x18000c090  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18000c095  jz      short loc_18000C0A2
0x18000c097  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000c09c  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000c0a2  test    r12b, r12b
0x18000c0a5  jz      short loc_18000C0BF
0x18000c0a7  lea     rdx, [rbp+13F0h+OutputString]
0x18000c0ae  lea     rcx, [rsp+14F0h+var_14D0]
0x18000c0b3  mov     rax, cs:g_pfnThrowPlatformException
0x18000c0ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0bf  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000c0c4  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x18000c0c9  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000c0ce  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
