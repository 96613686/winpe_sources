# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800079d0`
- end: `0x180007c30`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `608`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180007774`

## callees

- `0x1800079d0`
- `0x1800098e4`
- `0x18000a07c`
- `0x18000ac50`
- `0x18000c880`
- `0x18000d89e`
- `0x18000d960`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007a71`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007a71`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007bfe`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007bfe`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007b74`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007b74`

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
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v20, v18);
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
0x1800079d0  mov     [rsp-8+arg_18], rbx
0x1800079d5  push    rbp
0x1800079d6  push    rsi
0x1800079d7  push    rdi
0x1800079d8  push    r12
0x1800079da  push    r13
0x1800079dc  push    r14
0x1800079de  push    r15
0x1800079e0  lea     rbp, [rsp-13C0h]
0x1800079e8  mov     eax, 14C0h
0x1800079ed  call    _alloca_probe
0x1800079f2  sub     rsp, rax
0x1800079f5  mov     rsi, [rbp+13F0h+arg_28]
0x1800079fc  mov     r15, r8
0x1800079ff  mov     r14d, edx
0x180007a02  mov     r12, rcx
0x180007a05  xor     edx, edx; Val
0x180007a07  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180007a0c  mov     r8d, 98h; Size
0x180007a12  call    memset_0
0x180007a17  mov     rbx, [rbp+13F0h+arg_30]
0x180007a1e  xor     r13d, r13d
0x180007a21  mov     [rbp+13F0h+OutputString], r13w
0x180007a29  mov     [rbp+13F0h+var_1430], r13b
0x180007a2d  mov     ecx, [rbx]; this
0x180007a2f  mov     eax, [rbx+4]
0x180007a32  mov     [rsp+14F0h+var_14C8], ecx
0x180007a36  mov     [rsp+14F0h+var_14C4], eax
0x180007a3a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180007a3f  cmp     dword ptr [rbx+8], 1
0x180007a43  mov     edi, eax
0x180007a45  lea     eax, [r13+8]
0x180007a49  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180007a51  mov     ecx, r13d
0x180007a54  cmovz   ecx, eax
0x180007a57  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180007a5b  lea     ecx, [rax-7]
0x180007a5e  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180007a66  inc     ecx
0x180007a68  mov     [rsp+14F0h+var_14B8], r13
0x180007a6d  mov     [rsp+14F0h+var_14C0], ecx
0x180007a71  call    cs:__imp_GetCurrentThreadId
0x180007a77  xorps   xmm0, xmm0
0x180007a7a  mov     [rsp+14F0h+var_1498], r15
0x180007a7f  mov     [rsp+14F0h+var_14B0], eax
0x180007a83  xorps   xmm1, xmm1
0x180007a86  xor     eax, eax
0x180007a88  mov     [rsp+14F0h+var_1490], r14d
0x180007a8d  mov     [rbp+13F0h+var_1458], rax
0x180007a91  mov     [rbp+13F0h+var_1470], rax
0x180007a95  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180007a9c  mov     [rsp+14F0h+var_148C], edi
0x180007aa0  mov     [rsp+14F0h+var_14A8], r13
0x180007aa5  mov     [rsp+14F0h+var_14A0], r13
0x180007aaa  mov     [rbp+13F0h+var_1448], rsi
0x180007aae  mov     [rbp+13F0h+var_1440], r12
0x180007ab2  mov     [rsp+14F0h+var_1488], r13
0x180007ab7  movups  [rbp+13F0h+var_1468], xmm0
0x180007abb  movups  [rsp+14F0h+var_1480], xmm1
0x180007ac0  test    rax, rax
0x180007ac3  jz      short loc_180007AD0
0x180007ac5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007aca  mov     [rbp+13F0h+var_1450], rax
0x180007ace  jmp     short loc_180007AD4
0x180007ad0  mov     [rbp+13F0h+var_1450], r13
0x180007ad4  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180007adb  test    rax, rax
0x180007ade  jz      short loc_180007AEA
0x180007ae0  lea     rcx, [rsp+14F0h+var_14D0]
0x180007ae5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007aea  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180007af1  test    rax, rax
0x180007af4  jz      short loc_180007B0A
0x180007af6  mov     r8d, 400h
0x180007afc  lea     rdx, [rbp+13F0h+var_1430]
0x180007b00  lea     rcx, [rsp+14F0h+var_14D0]
0x180007b05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b0a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007b11  test    rax, rax
0x180007b14  jz      short loc_180007B20
0x180007b16  lea     rcx, [rsp+14F0h+var_14D0]
0x180007b1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b20  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007b27  test    rax, rax
0x180007b2a  jz      short loc_180007B3D
0x180007b2c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180007b31  jnz     short loc_180007B3D
0x180007b33  lea     rcx, [rsp+14F0h+var_14D0]
0x180007b38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b3d  cmp     [rsp+14F0h+var_14C8], r13d
0x180007b42  jl      short loc_180007B56
0x180007b44  mov     ecx, 8000FFFFh; this
0x180007b49  mov     [rsp+14F0h+var_14C8], ecx
0x180007b4d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007b52  mov     [rsp+14F0h+var_14C4], eax
0x180007b56  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180007b5d  jnz     short loc_180007B7E
0x180007b5f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180007b66  test    rax, rax
0x180007b69  jz      short loc_180007B74
0x180007b6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b70  test    al, al
0x180007b72  jmp     short loc_180007B7C
0x180007b74  call    cs:__imp_IsDebuggerPresent
0x180007b7a  test    eax, eax
0x180007b7c  jz      short loc_180007B85
0x180007b7e  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180007b83  jz      short loc_180007BAB
0x180007b85  mov     rax, cs:g_pfnResultLoggingCallback
0x180007b8c  test    rax, rax
0x180007b8f  jz      short loc_180007C04
0x180007b91  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180007b98  jnz     short loc_180007C04
0x180007b9a  xor     r8d, r8d
0x180007b9d  lea     rcx, [rsp+14F0h+var_14D0]
0x180007ba2  xor     edx, edx
0x180007ba4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ba9  jmp     short loc_180007C04
0x180007bab  mov     rax, cs:g_pfnResultLoggingCallback
0x180007bb2  mov     ebx, 800h
0x180007bb7  test    rax, rax
0x180007bba  jz      short loc_180007BD9
0x180007bbc  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180007bc3  jnz     short loc_180007BD9
0x180007bc5  mov     r8d, ebx
0x180007bc8  lea     rdx, [rbp+13F0h+OutputString]
0x180007bcf  lea     rcx, [rsp+14F0h+var_14D0]
0x180007bd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bd9  cmp     [rbp+13F0h+OutputString], r13w
0x180007be1  jnz     short loc_180007BF7
0x180007be3  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180007be8  mov     rdx, rbx; unsigned __int16 *
0x180007beb  lea     rcx, [rbp+13F0h+OutputString]; this
0x180007bf2  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180007bf7  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180007bfe  call    cs:__imp_OutputDebugStringW
0x180007c04  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180007c09  jnz     short loc_180007C14
0x180007c0b  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180007c12  jz      short loc_180007C25
0x180007c14  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180007c1b  test    rax, rax
0x180007c1e  jz      short loc_180007C25
0x180007c20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c25  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180007c2a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
