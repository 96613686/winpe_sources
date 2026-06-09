# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x140005e30`
- end: `0x1400060bb`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `651`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140005b98`

## callees

- `0x140003eb4`
- `0x140005e30`
- `0x14000866c`
- `0x140008e7c`
- `0x140009f00`
- `0x14000cbdc`
- `0x140065e80`
- `0x140069010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005ee9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005ee9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140005ff2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140005ff2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140006082`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140006082`

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
        int *a7,
        _WORD *a8)
{
  int v11; // edx
  int v12; // r12d
  int v13; // ecx
  const struct wil::FailureInfo *v14; // rdx
  __int64 v15; // rcx
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
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v12 = wil::details::RecordFailFast((wil::details *)(unsigned int)v20, v11);
  v18 = 3;
  v13 = 0;
  if ( a7[2] == 1 )
    v13 = 8;
  v19 = v13;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v12;
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
  {
    v20 = -2147418113;
    v21 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v14);
  }
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
  if ( (v19 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v15);
  }
  wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x140005e30  mov     [rsp-8+arg_18], rbx
0x140005e35  push    rbp
0x140005e36  push    rsi
0x140005e37  push    rdi
0x140005e38  push    r12
0x140005e3a  push    r13
0x140005e3c  push    r14
0x140005e3e  push    r15
0x140005e40  lea     rbp, [rsp-13C0h]
0x140005e48  mov     eax, 14C0h
0x140005e4d  call    _alloca_probe
0x140005e52  sub     rsp, rax
0x140005e55  mov     r14, r8
0x140005e58  mov     esi, edx
0x140005e5a  mov     rdi, rcx
0x140005e5d  mov     r15, [rbp+13F0h+arg_28]
0x140005e64  xor     edx, edx; Val
0x140005e66  mov     r8d, 98h; Size
0x140005e6c  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x140005e71  call    memset_0
0x140005e76  nop
0x140005e77  xor     r13d, r13d
0x140005e7a  mov     [rbp+13F0h+OutputString], r13w
0x140005e82  mov     [rbp+13F0h+var_1430], r13b
0x140005e86  mov     rbx, [rbp+13F0h+arg_30]
0x140005e8d  mov     ecx, [rbx]; this
0x140005e8f  mov     [rsp+14F0h+var_14C8], ecx
0x140005e93  mov     eax, [rbx+4]
0x140005e96  mov     [rsp+14F0h+var_14C4], eax
0x140005e9a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140005e9f  mov     r12d, eax
0x140005ea2  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x140005eaa  mov     ecx, r13d
0x140005ead  lea     eax, [r13+8]
0x140005eb1  cmp     dword ptr [rbx+8], 1
0x140005eb5  cmovz   ecx, eax
0x140005eb8  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x140005ebc  lea     ecx, [rax-7]
0x140005ebf  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140005ec7  inc     ecx
0x140005ec9  mov     [rsp+14F0h+var_14C0], ecx
0x140005ecd  mov     rcx, [rbp+13F0h+arg_38]
0x140005ed4  test    rcx, rcx
0x140005ed7  jz      short loc_140005EE4
0x140005ed9  cmp     [rcx], r13w
0x140005edd  mov     [rsp+14F0h+var_14B8], rcx
0x140005ee2  jnz     short loc_140005EE9
0x140005ee4  mov     [rsp+14F0h+var_14B8], r13
0x140005ee9  call    cs:__imp_GetCurrentThreadId
0x140005ef0  nop     dword ptr [rax+rax+00h]
0x140005ef5  mov     [rsp+14F0h+var_14B0], eax
0x140005ef9  mov     [rsp+14F0h+var_1498], r14
0x140005efe  mov     [rsp+14F0h+var_1490], esi
0x140005f02  mov     [rsp+14F0h+var_148C], r12d
0x140005f07  mov     [rsp+14F0h+var_14A8], r13
0x140005f0c  mov     [rsp+14F0h+var_14A0], r13
0x140005f11  mov     [rbp+13F0h+var_1448], r15
0x140005f15  mov     [rbp+13F0h+var_1440], rdi
0x140005f19  mov     [rsp+14F0h+var_1488], r13
0x140005f1e  xorps   xmm0, xmm0
0x140005f21  xor     eax, eax
0x140005f23  movups  [rbp+13F0h+var_1468], xmm0
0x140005f27  mov     [rbp+13F0h+var_1458], rax
0x140005f2b  xorps   xmm1, xmm1
0x140005f2e  movups  [rsp+14F0h+var_1480], xmm1
0x140005f33  mov     [rbp+13F0h+var_1470], rax
0x140005f37  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140005f3e  test    rax, rax
0x140005f41  jz      short loc_140005F4E
0x140005f43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005f48  mov     [rbp+13F0h+var_1450], rax
0x140005f4c  jmp     short loc_140005F52
0x140005f4e  mov     [rbp+13F0h+var_1450], r13
0x140005f52  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140005f59  test    rax, rax
0x140005f5c  jz      short loc_140005F68
0x140005f5e  lea     rcx, [rsp+14F0h+var_14D0]
0x140005f63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005f68  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140005f6f  test    rax, rax
0x140005f72  jz      short loc_140005F88
0x140005f74  mov     r8d, 400h
0x140005f7a  lea     rdx, [rbp+13F0h+var_1430]
0x140005f7e  lea     rcx, [rsp+14F0h+var_14D0]
0x140005f83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005f88  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140005f8f  test    rax, rax
0x140005f92  jz      short loc_140005F9E
0x140005f94  lea     rcx, [rsp+14F0h+var_14D0]
0x140005f99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005f9e  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140005fa5  test    rax, rax
0x140005fa8  jz      short loc_140005FBB
0x140005faa  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140005faf  jnz     short loc_140005FBB
0x140005fb1  lea     rcx, [rsp+14F0h+var_14D0]
0x140005fb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005fbb  cmp     [rsp+14F0h+var_14C8], r13d
0x140005fc0  jl      short loc_140005FD4
0x140005fc2  mov     ecx, 8000FFFFh; this
0x140005fc7  mov     [rsp+14F0h+var_14C8], ecx
0x140005fcb  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140005fd0  mov     [rsp+14F0h+var_14C4], eax
0x140005fd4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x140005fdb  jnz     short loc_140006002
0x140005fdd  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140005fe4  test    rax, rax
0x140005fe7  jz      short loc_140005FF2
0x140005fe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005fee  test    al, al
0x140005ff0  jmp     short loc_140006000
0x140005ff2  call    cs:__imp_IsDebuggerPresent
0x140005ff9  nop     dword ptr [rax+rax+00h]
0x140005ffe  test    eax, eax
0x140006000  jz      short loc_140006009
0x140006002  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140006007  jz      short loc_14000602F
0x140006009  mov     rax, cs:g_pfnResultLoggingCallback
0x140006010  test    rax, rax
0x140006013  jz      short loc_14000608E
0x140006015  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x14000601c  jnz     short loc_14000608E
0x14000601e  xor     r8d, r8d
0x140006021  xor     edx, edx
0x140006023  lea     rcx, [rsp+14F0h+var_14D0]
0x140006028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000602d  jmp     short loc_14000608E
0x14000602f  mov     ebx, 800h
0x140006034  mov     rax, cs:g_pfnResultLoggingCallback
0x14000603b  test    rax, rax
0x14000603e  jz      short loc_14000605D
0x140006040  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140006047  jnz     short loc_14000605D
0x140006049  mov     r8d, ebx
0x14000604c  lea     rdx, [rbp+13F0h+OutputString]
0x140006053  lea     rcx, [rsp+14F0h+var_14D0]
0x140006058  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000605d  cmp     [rbp+13F0h+OutputString], r13w
0x140006065  jnz     short loc_14000607B
0x140006067  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x14000606c  mov     rdx, rbx; unsigned __int16 *
0x14000606f  lea     rcx, [rbp+13F0h+OutputString]; this
0x140006076  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14000607b  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x140006082  call    cs:__imp_OutputDebugStringW
0x140006089  nop     dword ptr [rax+rax+00h]
0x14000608e  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x140006093  jnz     short loc_14000609E
0x140006095  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x14000609c  jz      short loc_1400060B0
0x14000609e  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400060a5  test    rax, rax
0x1400060a8  jz      short loc_1400060B0
0x1400060aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400060af  nop
0x1400060b0  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1400060b5  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
