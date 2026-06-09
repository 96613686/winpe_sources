# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180005a58`
- end: `0x180005cca`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `626`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180005810`

## callees

- `0x180005665`
- `0x180005a58`
- `0x180009574`
- `0x18000a33c`
- `0x18000bc90`
- `0x18000e57c`
- `0x1800a1070`
- `0x1800a5010`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x180005c92`
- `KERNEL32!OutputDebugStringW` at `0x180005c92`
- `KERNEL32!IsDebuggerPresent` at `0x180005c02`
- `KERNEL32!IsDebuggerPresent` at `0x180005c02`
- `KERNEL32!GetCurrentThreadId` at `0x180005af9`
- `KERNEL32!GetCurrentThreadId` at `0x180005af9`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v10; // eax
  int v11; // edx
  int v12; // eax
  int v13; // edi
  int v14; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v16; // rdx
  __int64 v17; // rcx
  const struct wil::FailureInfo *v18; // r9
  bool v19; // zf
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD v26; // [rsp+40h] [rbp-C0h]
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

  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v10 = a7[1];
  v22 = *a7;
  v23 = v10;
  v12 = wil::details::RecordFailFast((wil::details *)(unsigned int)v22, v11);
  v19 = a7[2] == 1;
  v13 = v12;
  v20 = 3;
  v14 = 0;
  if ( v19 )
    v14 = 8;
  v21 = v14;
  v25 = 0;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v26 = CurrentThreadId;
  v30 = a2;
  v36 = 0;
  v34 = 0;
  v31 = v13;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v33 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v17);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
  {
    v22 = -2147418113;
    v23 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v16);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v19 = !IsDebuggerPresent())
      : (v19 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v17) == 0),
        v19)
    || (v21 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v20, v18);
    OutputDebugStringW(OutputString);
  }
  if ( (v21 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v17);
  }
  wil::details::WilFailFast((wil::details *)&v20, v16);
}

```

## disassembly

```asm
0x180005a58  mov     [rsp-8+arg_18], rbx
0x180005a5d  push    rbp
0x180005a5e  push    rsi
0x180005a5f  push    rdi
0x180005a60  push    r12
0x180005a62  push    r13
0x180005a64  push    r14
0x180005a66  push    r15
0x180005a68  lea     rbp, [rsp-13C0h]
0x180005a70  mov     eax, 14C0h
0x180005a75  call    _alloca_probe
0x180005a7a  sub     rsp, rax
0x180005a7d  mov     rsi, [rbp+13F0h+arg_28]
0x180005a84  mov     r15, r8
0x180005a87  mov     r14d, edx
0x180005a8a  mov     r12, rcx
0x180005a8d  xor     edx, edx; Val
0x180005a8f  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180005a94  mov     r8d, 98h; Size
0x180005a9a  call    memset_0
0x180005a9f  mov     rbx, [rbp+13F0h+arg_30]
0x180005aa6  xor     r13d, r13d
0x180005aa9  mov     [rbp+13F0h+OutputString], r13w
0x180005ab1  mov     [rbp+13F0h+var_1430], r13b
0x180005ab5  mov     ecx, [rbx]; this
0x180005ab7  mov     eax, [rbx+4]
0x180005aba  mov     [rsp+14F0h+var_14C8], ecx
0x180005abe  mov     [rsp+14F0h+var_14C4], eax
0x180005ac2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180005ac7  cmp     dword ptr [rbx+8], 1
0x180005acb  mov     edi, eax
0x180005acd  lea     eax, [r13+8]
0x180005ad1  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180005ad9  mov     ecx, r13d
0x180005adc  cmovz   ecx, eax
0x180005adf  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180005ae3  lea     ecx, [rax-7]
0x180005ae6  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)'::`2'::s_failureId
0x180005aee  inc     ecx
0x180005af0  mov     [rsp+14F0h+var_14B8], r13
0x180005af5  mov     [rsp+14F0h+var_14C0], ecx
0x180005af9  call    cs:__imp_GetCurrentThreadId
0x180005b00  nop     dword ptr [rax+rax+00h]
0x180005b05  xorps   xmm0, xmm0
0x180005b08  mov     [rsp+14F0h+var_1498], r15
0x180005b0d  mov     [rsp+14F0h+var_14B0], eax
0x180005b11  xorps   xmm1, xmm1
0x180005b14  xor     eax, eax
0x180005b16  mov     [rsp+14F0h+var_1490], r14d
0x180005b1b  mov     [rbp+13F0h+var_1458], rax
0x180005b1f  mov     [rbp+13F0h+var_1470], rax
0x180005b23  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005b2a  mov     [rsp+14F0h+var_148C], edi
0x180005b2e  mov     [rsp+14F0h+var_14A8], r13
0x180005b33  mov     [rsp+14F0h+var_14A0], r13
0x180005b38  mov     [rbp+13F0h+var_1448], rsi
0x180005b3c  mov     [rbp+13F0h+var_1440], r12
0x180005b40  mov     [rsp+14F0h+var_1488], r13
0x180005b45  movups  [rbp+13F0h+var_1468], xmm0
0x180005b49  movups  [rsp+14F0h+var_1480], xmm1
0x180005b4e  test    rax, rax
0x180005b51  jz      short loc_180005B5E
0x180005b53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b58  mov     [rbp+13F0h+var_1450], rax
0x180005b5c  jmp     short loc_180005B62
0x180005b5e  mov     [rbp+13F0h+var_1450], r13
0x180005b62  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005b69  test    rax, rax
0x180005b6c  jz      short loc_180005B78
0x180005b6e  lea     rcx, [rsp+14F0h+var_14D0]
0x180005b73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b78  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005b7f  test    rax, rax
0x180005b82  jz      short loc_180005B98
0x180005b84  mov     r8d, 400h
0x180005b8a  lea     rdx, [rbp+13F0h+var_1430]
0x180005b8e  lea     rcx, [rsp+14F0h+var_14D0]
0x180005b93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b98  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005b9f  test    rax, rax
0x180005ba2  jz      short loc_180005BAE
0x180005ba4  lea     rcx, [rsp+14F0h+var_14D0]
0x180005ba9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bae  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005bb5  test    rax, rax
0x180005bb8  jz      short loc_180005BCB
0x180005bba  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180005bbf  jnz     short loc_180005BCB
0x180005bc1  lea     rcx, [rsp+14F0h+var_14D0]
0x180005bc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bcb  cmp     [rsp+14F0h+var_14C8], r13d
0x180005bd0  jl      short loc_180005BE4
0x180005bd2  mov     ecx, 8000FFFFh; this
0x180005bd7  mov     [rsp+14F0h+var_14C8], ecx
0x180005bdb  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005be0  mov     [rsp+14F0h+var_14C4], eax
0x180005be4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180005beb  jnz     short loc_180005C12
0x180005bed  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005bf4  test    rax, rax
0x180005bf7  jz      short loc_180005C02
0x180005bf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bfe  test    al, al
0x180005c00  jmp     short loc_180005C10
0x180005c02  call    cs:__imp_IsDebuggerPresent
0x180005c09  nop     dword ptr [rax+rax+00h]
0x180005c0e  test    eax, eax
0x180005c10  jz      short loc_180005C19
0x180005c12  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180005c17  jz      short loc_180005C3F
0x180005c19  mov     rax, cs:g_pfnResultLoggingCallback
0x180005c20  test    rax, rax
0x180005c23  jz      short loc_180005C9E
0x180005c25  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180005c2c  jnz     short loc_180005C9E
0x180005c2e  xor     r8d, r8d
0x180005c31  lea     rcx, [rsp+14F0h+var_14D0]
0x180005c36  xor     edx, edx
0x180005c38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c3d  jmp     short loc_180005C9E
0x180005c3f  mov     rax, cs:g_pfnResultLoggingCallback
0x180005c46  mov     ebx, 800h
0x180005c4b  test    rax, rax
0x180005c4e  jz      short loc_180005C6D
0x180005c50  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180005c57  jnz     short loc_180005C6D
0x180005c59  mov     r8d, ebx
0x180005c5c  lea     rdx, [rbp+13F0h+OutputString]
0x180005c63  lea     rcx, [rsp+14F0h+var_14D0]
0x180005c68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c6d  cmp     [rbp+13F0h+OutputString], r13w
0x180005c75  jnz     short loc_180005C8B
0x180005c77  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180005c7c  mov     rdx, rbx; unsigned __int16 *
0x180005c7f  lea     rcx, [rbp+13F0h+OutputString]; this
0x180005c86  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005c8b  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180005c92  call    cs:__imp_OutputDebugStringW
0x180005c99  nop     dword ptr [rax+rax+00h]
0x180005c9e  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180005ca3  jnz     short loc_180005CAE
0x180005ca5  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180005cac  jz      short loc_180005CBF
0x180005cae  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005cb5  test    rax, rax
0x180005cb8  jz      short loc_180005CBF
0x180005cba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cbf  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180005cc4  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
