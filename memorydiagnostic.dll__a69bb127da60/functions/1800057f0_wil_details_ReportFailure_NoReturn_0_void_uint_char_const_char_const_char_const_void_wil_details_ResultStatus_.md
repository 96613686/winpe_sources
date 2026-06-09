# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800057f0`
- end: `0x180005a9c`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `684`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180004d84`

## callees

- `0x180003940`
- `0x1800057f0`
- `0x18000cd54`
- `0x18000f25c`
- `0x180013948`
- `0x180014e80`
- `0x1800155f4`
- `0x180020830`
- `0x180023010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x180005994`
- `KERNEL32!IsDebuggerPresent` at `0x180005994`
- `KERNEL32!OutputDebugStringW` at `0x180005a30`
- `KERNEL32!OutputDebugStringW` at `0x180005a30`
- `KERNEL32!GetCurrentThreadId` at `0x180005899`
- `KERNEL32!GetCurrentThreadId` at `0x180005899`

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
0x1800057f0  mov     [rsp-8+arg_18], rbx
0x1800057f5  push    rbp
0x1800057f6  push    rsi
0x1800057f7  push    rdi
0x1800057f8  push    r12
0x1800057fa  push    r13
0x1800057fc  push    r14
0x1800057fe  push    r15
0x180005800  lea     rbp, [rsp-13C0h]
0x180005808  mov     eax, 14C0h
0x18000580d  call    _alloca_probe
0x180005812  sub     rsp, rax
0x180005815  mov     r14, r8
0x180005818  mov     esi, edx
0x18000581a  mov     r15, rcx
0x18000581d  mov     rdi, [rbp+13F0h+arg_28]
0x180005824  xor     r13d, r13d
0x180005827  cmp     cs:g_pfnThrowPlatformException, r13
0x18000582e  setnz   r12b
0x180005832  xor     edx, edx; Val
0x180005834  mov     r8d, 98h; Size
0x18000583a  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000583f  call    memset_0
0x180005844  nop
0x180005845  mov     [rbp+13F0h+OutputString], r13w
0x18000584d  mov     [rbp+13F0h+var_1430], r13b
0x180005851  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180005858  mov     ecx, [rdx]; this
0x18000585a  mov     [rsp+14F0h+var_14C8], ecx
0x18000585e  mov     eax, [rdx+4]
0x180005861  mov     [rsp+14F0h+var_14C4], eax
0x180005865  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000586a  mov     ebx, eax
0x18000586c  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x180005871  mov     ecx, r13d
0x180005874  lea     eax, [r13+8]
0x180005878  cmp     dword ptr [rdx+8], 1
0x18000587c  cmovz   ecx, eax
0x18000587f  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180005883  lea     ecx, [rax-7]
0x180005886  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000588e  inc     ecx
0x180005890  mov     [rsp+14F0h+var_14C0], ecx
0x180005894  mov     [rsp+14F0h+var_14B8], r13
0x180005899  call    cs:__imp_GetCurrentThreadId
0x18000589f  mov     [rsp+14F0h+var_14B0], eax
0x1800058a3  mov     [rsp+14F0h+var_1498], r14
0x1800058a8  mov     [rsp+14F0h+var_1490], esi
0x1800058ac  mov     [rsp+14F0h+var_148C], ebx
0x1800058b0  mov     [rsp+14F0h+var_14A8], r13
0x1800058b5  mov     [rsp+14F0h+var_14A0], r13
0x1800058ba  mov     [rbp+13F0h+var_1448], rdi
0x1800058be  mov     [rbp+13F0h+var_1440], r15
0x1800058c2  mov     [rsp+14F0h+var_1488], r13
0x1800058c7  xorps   xmm0, xmm0
0x1800058ca  xor     eax, eax
0x1800058cc  movups  [rbp+13F0h+var_1468], xmm0
0x1800058d0  mov     [rbp+13F0h+var_1458], rax
0x1800058d4  xorps   xmm1, xmm1
0x1800058d7  movups  [rsp+14F0h+var_1480], xmm1
0x1800058dc  mov     [rbp+13F0h+var_1470], rax
0x1800058e0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800058e7  test    rax, rax
0x1800058ea  jz      short loc_1800058F7
0x1800058ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058f1  mov     [rbp+13F0h+var_1450], rax
0x1800058f5  jmp     short loc_1800058FB
0x1800058f7  mov     [rbp+13F0h+var_1450], r13
0x1800058fb  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005902  test    rax, rax
0x180005905  jz      short loc_180005911
0x180005907  lea     rcx, [rsp+14F0h+var_14D0]
0x18000590c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005911  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005918  test    rax, rax
0x18000591b  jz      short loc_180005931
0x18000591d  mov     r8d, 400h
0x180005923  lea     rdx, [rbp+13F0h+var_1430]
0x180005927  lea     rcx, [rsp+14F0h+var_14D0]
0x18000592c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005931  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005938  test    rax, rax
0x18000593b  jz      short loc_180005947
0x18000593d  lea     rcx, [rsp+14F0h+var_14D0]
0x180005942  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005947  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000594e  test    rax, rax
0x180005951  jz      short loc_180005969
0x180005953  test    r12b, r12b
0x180005956  jnz     short loc_180005969
0x180005958  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000595d  jnz     short loc_180005969
0x18000595f  lea     rcx, [rsp+14F0h+var_14D0]
0x180005964  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005969  cmp     [rsp+14F0h+var_14C8], r13d
0x18000596e  jl      short loc_180005976
0x180005970  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180005976  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000597d  jnz     short loc_18000599E
0x18000597f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005986  test    rax, rax
0x180005989  jz      short loc_180005994
0x18000598b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005990  test    al, al
0x180005992  jmp     short loc_18000599C
0x180005994  call    cs:__imp_IsDebuggerPresent
0x18000599a  test    eax, eax
0x18000599c  jz      short loc_1800059A7
0x18000599e  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800059a3  mov     bl, 1
0x1800059a5  jz      short loc_1800059AA
0x1800059a7  mov     bl, r13b
0x1800059aa  test    r12b, r12b
0x1800059ad  jnz     short loc_1800059D9
0x1800059af  test    bl, bl
0x1800059b1  jnz     short loc_1800059D9
0x1800059b3  mov     rax, cs:g_pfnResultLoggingCallback
0x1800059ba  test    rax, rax
0x1800059bd  jz      short loc_180005A36
0x1800059bf  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800059c6  jnz     short loc_180005A36
0x1800059c8  xor     r8d, r8d
0x1800059cb  xor     edx, edx
0x1800059cd  lea     rcx, [rsp+14F0h+var_14D0]
0x1800059d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059d7  jmp     short loc_180005A36
0x1800059d9  mov     edi, 800h
0x1800059de  mov     rax, cs:g_pfnResultLoggingCallback
0x1800059e5  test    rax, rax
0x1800059e8  jz      short loc_180005A07
0x1800059ea  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800059f1  jnz     short loc_180005A07
0x1800059f3  mov     r8d, edi
0x1800059f6  lea     rdx, [rbp+13F0h+OutputString]
0x1800059fd  lea     rcx, [rsp+14F0h+var_14D0]
0x180005a02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a07  cmp     [rbp+13F0h+OutputString], r13w
0x180005a0f  jnz     short loc_180005A25
0x180005a11  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180005a16  mov     rdx, rdi; unsigned __int16 *
0x180005a19  lea     rcx, [rbp+13F0h+OutputString]; this
0x180005a20  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005a25  test    bl, bl
0x180005a27  jz      short loc_180005A36
0x180005a29  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180005a30  call    cs:__imp_OutputDebugStringW
0x180005a36  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180005a3b  jnz     short loc_180005A46
0x180005a3d  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180005a44  jz      short loc_180005A58
0x180005a46  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005a4d  test    rax, rax
0x180005a50  jz      short loc_180005A58
0x180005a52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a57  nop
0x180005a58  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180005a5d  jz      short loc_180005A6A
0x180005a5f  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180005a64  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180005a6a  test    r12b, r12b
0x180005a6d  jz      short loc_180005A87
0x180005a6f  lea     rdx, [rbp+13F0h+OutputString]
0x180005a76  lea     rcx, [rsp+14F0h+var_14D0]
0x180005a7b  mov     rax, cs:g_pfnThrowPlatformException
0x180005a82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a87  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180005a8c  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x180005a91  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180005a96  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
