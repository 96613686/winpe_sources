# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180005ecc`
- end: `0x180006185`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `697`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800051b4`

## callees

- `0x180002690`
- `0x1800032b8`
- `0x180005ecc`
- `0x18000b004`
- `0x18000dcc4`
- `0x180012f2c`
- `0x180013490`
- `0x180042f60`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005f92`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005f92`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000611d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000611d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000608d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000608d`

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
0x180005ecc  push    rbp
0x180005ece  push    rbx
0x180005ecf  push    rsi
0x180005ed0  push    rdi
0x180005ed1  push    r12
0x180005ed3  push    r14
0x180005ed5  push    r15
0x180005ed7  lea     rbp, [rsp-13D0h]
0x180005edf  mov     eax, 14D0h
0x180005ee4  call    _alloca_probe
0x180005ee9  sub     rsp, rax
0x180005eec  mov     rax, cs:__security_cookie
0x180005ef3  xor     rax, rsp
0x180005ef6  mov     [rbp+1400h+var_40], rax
0x180005efd  mov     rsi, r8
0x180005f00  mov     edi, edx
0x180005f02  mov     rbx, rcx
0x180005f05  mov     r14, [rbp+1400h+arg_28]
0x180005f0c  xor     edx, edx; Val
0x180005f0e  mov     r8d, 98h; Size
0x180005f14  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180005f19  call    memset_0
0x180005f1e  nop
0x180005f1f  xor     r12d, r12d
0x180005f22  mov     [rbp+1400h+OutputString], r12w
0x180005f2a  mov     [rbp+1400h+var_1440], r12b
0x180005f2e  mov     rdx, [rbp+1400h+arg_30]; int
0x180005f35  mov     ecx, [rdx]; this
0x180005f37  mov     [rsp+1500h+var_14D8], ecx
0x180005f3b  mov     eax, [rdx+4]
0x180005f3e  mov     [rsp+1500h+var_14D4], eax
0x180005f42  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005f47  mov     r15d, eax
0x180005f4a  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180005f52  mov     ecx, r12d
0x180005f55  lea     eax, [r12+8]
0x180005f5a  cmp     dword ptr [rdx+8], 1
0x180005f5e  cmovz   ecx, eax
0x180005f61  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180005f65  lea     ecx, [rax-7]
0x180005f68  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005f70  inc     ecx
0x180005f72  mov     [rsp+1500h+var_14D0], ecx
0x180005f76  mov     rcx, [rbp+1400h+arg_38]
0x180005f7d  test    rcx, rcx
0x180005f80  jz      short loc_180005F8D
0x180005f82  cmp     [rcx], r12w
0x180005f86  mov     [rsp+1500h+var_14C8], rcx
0x180005f8b  jnz     short loc_180005F92
0x180005f8d  mov     [rsp+1500h+var_14C8], r12
0x180005f92  call    cs:__imp_GetCurrentThreadId
0x180005f99  nop     dword ptr [rax+rax+00h]
0x180005f9e  mov     [rsp+1500h+var_14C0], eax
0x180005fa2  mov     [rsp+1500h+var_14A8], rsi
0x180005fa7  mov     [rsp+1500h+var_14A0], edi
0x180005fab  mov     [rsp+1500h+var_149C], r15d
0x180005fb0  mov     [rsp+1500h+var_14B8], r12
0x180005fb5  mov     [rsp+1500h+var_14B0], r12
0x180005fba  mov     [rbp+1400h+var_1458], r14
0x180005fbe  mov     [rbp+1400h+var_1450], rbx
0x180005fc2  mov     [rsp+1500h+var_1498], r12
0x180005fc7  xorps   xmm0, xmm0
0x180005fca  xor     eax, eax
0x180005fcc  movups  [rbp+1400h+var_1478], xmm0
0x180005fd0  mov     [rbp+1400h+var_1468], rax
0x180005fd4  xorps   xmm1, xmm1
0x180005fd7  movups  [rsp+1500h+var_1490], xmm1
0x180005fdc  mov     [rbp+1400h+var_1480], rax
0x180005fe0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005fe7  test    rax, rax
0x180005fea  jz      short loc_180005FF7
0x180005fec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ff1  mov     [rbp+1400h+var_1460], rax
0x180005ff5  jmp     short loc_180005FFB
0x180005ff7  mov     [rbp+1400h+var_1460], r12
0x180005ffb  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006002  test    rax, rax
0x180006005  jz      short loc_180006011
0x180006007  lea     rcx, [rsp+1500h+var_14E0]
0x18000600c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006011  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006018  test    rax, rax
0x18000601b  jz      short loc_180006031
0x18000601d  mov     r8d, 400h
0x180006023  lea     rdx, [rbp+1400h+var_1440]
0x180006027  lea     rcx, [rsp+1500h+var_14E0]
0x18000602c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006031  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006038  test    rax, rax
0x18000603b  jz      short loc_180006047
0x18000603d  lea     rcx, [rsp+1500h+var_14E0]
0x180006042  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006047  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000604e  test    rax, rax
0x180006051  jz      short loc_180006064
0x180006053  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180006058  jnz     short loc_180006064
0x18000605a  lea     rcx, [rsp+1500h+var_14E0]
0x18000605f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006064  cmp     [rsp+1500h+var_14D8], r12d
0x180006069  jge     loc_18000617F
0x18000606f  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180006076  jnz     short loc_18000609D
0x180006078  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000607f  test    rax, rax
0x180006082  jz      short loc_18000608D
0x180006084  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006089  test    al, al
0x18000608b  jmp     short loc_18000609B
0x18000608d  call    cs:__imp_IsDebuggerPresent
0x180006094  nop     dword ptr [rax+rax+00h]
0x180006099  test    eax, eax
0x18000609b  jz      short loc_1800060A4
0x18000609d  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800060a2  jz      short loc_1800060CA
0x1800060a4  mov     rax, cs:g_pfnResultLoggingCallback
0x1800060ab  test    rax, rax
0x1800060ae  jz      short loc_180006129
0x1800060b0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800060b7  jnz     short loc_180006129
0x1800060b9  xor     r8d, r8d
0x1800060bc  xor     edx, edx
0x1800060be  lea     rcx, [rsp+1500h+var_14E0]
0x1800060c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060c8  jmp     short loc_180006129
0x1800060ca  mov     ebx, 800h
0x1800060cf  mov     rax, cs:g_pfnResultLoggingCallback
0x1800060d6  test    rax, rax
0x1800060d9  jz      short loc_1800060F8
0x1800060db  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800060e2  jnz     short loc_1800060F8
0x1800060e4  mov     r8d, ebx
0x1800060e7  lea     rdx, [rbp+1400h+OutputString]
0x1800060ee  lea     rcx, [rsp+1500h+var_14E0]
0x1800060f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060f8  cmp     [rbp+1400h+OutputString], r12w
0x180006100  jnz     short loc_180006116
0x180006102  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180006107  mov     rdx, rbx; unsigned __int16 *
0x18000610a  lea     rcx, [rbp+1400h+OutputString]; this
0x180006111  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180006116  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18000611d  call    cs:__imp_OutputDebugStringW
0x180006124  nop     dword ptr [rax+rax+00h]
0x180006129  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18000612e  jnz     short loc_180006139
0x180006130  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180006137  jz      short loc_18000614B
0x180006139  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006140  test    rax, rax
0x180006143  jz      short loc_18000614B
0x180006145  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000614a  nop
0x18000614b  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180006150  jnz     short loc_180006174
0x180006152  mov     rcx, [rbp+1400h+var_40]
0x180006159  xor     rcx, rsp; StackCookie
0x18000615c  call    __security_check_cookie
0x180006161  add     rsp, 14D0h
0x180006168  pop     r15
0x18000616a  pop     r14
0x18000616c  pop     r12
0x18000616e  pop     rdi
0x18000616f  pop     rsi
0x180006170  pop     rbx
0x180006171  pop     rbp
0x180006172  retn
0x180006174  lea     rcx, [rsp+1500h+var_14E0]; this
0x180006179  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000617f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
