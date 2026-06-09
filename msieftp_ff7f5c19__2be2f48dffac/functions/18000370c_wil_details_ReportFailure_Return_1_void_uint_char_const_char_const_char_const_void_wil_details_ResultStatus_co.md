# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000370c`
- end: `0x1800039a0`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800031ec`

## callees

- `0x180002240`
- `0x180002b60`
- `0x18000370c`
- `0x1800061e4`
- `0x180007e44`
- `0x18000a1f0`
- `0x18000a3bc`
- `0x1800271f0`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800037b6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800037b6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000393b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000393b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800038b1`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800038b1`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdx
  int v12; // ebx
  int v13; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v15; // rdx
  wil::details::in1diag3 *v16; // rcx
  const struct wil::FailureInfo *v17; // r9
  bool v18; // zf
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh]
  int v21; // [rsp+28h] [rbp-D8h]
  int v22; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v23; // [rsp+30h] [rbp-D0h]
  __int64 v24; // [rsp+38h] [rbp-C8h]
  DWORD v25; // [rsp+40h] [rbp-C0h]
  __int64 v26; // [rsp+48h] [rbp-B8h]
  __int64 v27; // [rsp+50h] [rbp-B0h]
  const char *v28; // [rsp+58h] [rbp-A8h]
  int v29; // [rsp+60h] [rbp-A0h]
  int v30; // [rsp+64h] [rbp-9Ch]
  __int64 v31; // [rsp+68h] [rbp-98h]
  __int128 v32; // [rsp+70h] [rbp-90h]
  __int64 v33; // [rsp+80h] [rbp-80h]
  __int128 v34; // [rsp+88h] [rbp-78h]
  __int64 v35; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v37; // [rsp+A8h] [rbp-58h]
  __int64 v38; // [rsp+B0h] [rbp-50h]
  char v39[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v19, 0, 0x98u);
  OutputString[0] = 0;
  v39[0] = 0;
  v9 = a7[1];
  v21 = *a7;
  v22 = v9;
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v21, (int)a7);
  v18 = *(_DWORD *)(v11 + 8) == 1;
  v12 = v10;
  v19 = 1;
  v13 = 0;
  if ( v18 )
    v13 = 8;
  v20 = v13;
  v24 = 0;
  v23 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a2;
  v25 = CurrentThreadId;
  v30 = v12;
  v28 = "wil";
  v35 = 0;
  v33 = 0;
  v26 = 0;
  v27 = 0;
  v37 = a6;
  v38 = a1;
  v31 = 0;
  v34 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v16);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v19);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v19, v39, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v19);
  if ( wil::details::g_pfnOriginateCallback && (v20 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v19);
  if ( v21 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v16);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v18 = !IsDebuggerPresent())
      : (v18 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v16) == 0),
        v18)
    || (v20 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v19, v17);
    OutputDebugStringW(OutputString);
  }
  if ( ((v20 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v16);
  if ( (v20 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v19, v15);
}

```

## disassembly

```asm
0x18000370c  mov     [rsp-8+arg_10], rbx
0x180003711  push    rbp
0x180003712  push    rsi
0x180003713  push    rdi
0x180003714  push    r14
0x180003716  push    r15
0x180003718  lea     rbp, [rsp-13D0h]
0x180003720  mov     eax, 14D0h
0x180003725  call    _alloca_probe
0x18000372a  sub     rsp, rax
0x18000372d  mov     rax, cs:__security_cookie
0x180003734  xor     rax, rsp
0x180003737  mov     [rbp+13F0h+var_30], rax
0x18000373e  mov     rdi, [rbp+13F0h+arg_28]
0x180003745  mov     esi, edx
0x180003747  mov     r14, rcx
0x18000374a  xor     edx, edx; Val
0x18000374c  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180003751  mov     r8d, 98h; Size
0x180003757  call    memset_0
0x18000375c  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180003763  xor     r15d, r15d
0x180003766  mov     [rbp+13F0h+OutputString], r15w
0x18000376e  mov     [rbp+13F0h+var_1430], r15b
0x180003772  mov     ecx, [rdx]; this
0x180003774  mov     eax, [rdx+4]
0x180003777  mov     [rsp+14F0h+var_14C8], ecx
0x18000377b  mov     [rsp+14F0h+var_14C4], eax
0x18000377f  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180003784  cmp     dword ptr [rdx+8], 1
0x180003788  mov     ebx, eax
0x18000378a  lea     eax, [r15+8]
0x18000378e  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180003796  mov     ecx, r15d
0x180003799  cmovz   ecx, eax
0x18000379c  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800037a0  lea     ecx, [rax-7]
0x1800037a3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800037ab  inc     ecx
0x1800037ad  mov     [rsp+14F0h+var_14B8], r15
0x1800037b2  mov     [rsp+14F0h+var_14C0], ecx
0x1800037b6  call    cs:__imp_GetCurrentThreadId
0x1800037bc  xorps   xmm0, xmm0
0x1800037bf  mov     [rsp+14F0h+var_1490], esi
0x1800037c3  mov     [rsp+14F0h+var_14B0], eax
0x1800037c7  xorps   xmm1, xmm1
0x1800037ca  lea     rax, aWil; "wil"
0x1800037d1  mov     [rsp+14F0h+var_148C], ebx
0x1800037d5  mov     [rsp+14F0h+var_1498], rax
0x1800037da  xor     eax, eax
0x1800037dc  mov     [rbp+13F0h+var_1458], rax
0x1800037e0  mov     [rbp+13F0h+var_1470], rax
0x1800037e4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800037eb  mov     [rsp+14F0h+var_14A8], r15
0x1800037f0  mov     [rsp+14F0h+var_14A0], r15
0x1800037f5  mov     [rbp+13F0h+var_1448], rdi
0x1800037f9  mov     [rbp+13F0h+var_1440], r14
0x1800037fd  mov     [rsp+14F0h+var_1488], r15
0x180003802  movups  [rbp+13F0h+var_1468], xmm0
0x180003806  movups  [rsp+14F0h+var_1480], xmm1
0x18000380b  test    rax, rax
0x18000380e  jz      short loc_18000381B
0x180003810  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003815  mov     [rbp+13F0h+var_1450], rax
0x180003819  jmp     short loc_18000381F
0x18000381b  mov     [rbp+13F0h+var_1450], r15
0x18000381f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003826  test    rax, rax
0x180003829  jz      short loc_180003835
0x18000382b  lea     rcx, [rsp+14F0h+var_14D0]
0x180003830  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003835  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000383c  test    rax, rax
0x18000383f  jz      short loc_180003855
0x180003841  mov     r8d, 400h
0x180003847  lea     rdx, [rbp+13F0h+var_1430]
0x18000384b  lea     rcx, [rsp+14F0h+var_14D0]
0x180003850  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003855  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000385c  test    rax, rax
0x18000385f  jz      short loc_18000386B
0x180003861  lea     rcx, [rsp+14F0h+var_14D0]
0x180003866  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000386b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003872  test    rax, rax
0x180003875  jz      short loc_180003888
0x180003877  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000387c  jnz     short loc_180003888
0x18000387e  lea     rcx, [rsp+14F0h+var_14D0]
0x180003883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003888  cmp     [rsp+14F0h+var_14C8], r15d
0x18000388d  jge     loc_18000398F
0x180003893  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18000389a  jnz     short loc_1800038BB
0x18000389c  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800038a3  test    rax, rax
0x1800038a6  jz      short loc_1800038B1
0x1800038a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038ad  test    al, al
0x1800038af  jmp     short loc_1800038B9
0x1800038b1  call    cs:__imp_IsDebuggerPresent
0x1800038b7  test    eax, eax
0x1800038b9  jz      short loc_1800038C2
0x1800038bb  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800038c0  jz      short loc_1800038E8
0x1800038c2  mov     rax, cs:g_pfnResultLoggingCallback
0x1800038c9  test    rax, rax
0x1800038cc  jz      short loc_180003941
0x1800038ce  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800038d5  jnz     short loc_180003941
0x1800038d7  xor     r8d, r8d
0x1800038da  lea     rcx, [rsp+14F0h+var_14D0]
0x1800038df  xor     edx, edx
0x1800038e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038e6  jmp     short loc_180003941
0x1800038e8  mov     rax, cs:g_pfnResultLoggingCallback
0x1800038ef  mov     ebx, 800h
0x1800038f4  test    rax, rax
0x1800038f7  jz      short loc_180003916
0x1800038f9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180003900  jnz     short loc_180003916
0x180003902  mov     r8d, ebx
0x180003905  lea     rdx, [rbp+13F0h+OutputString]
0x18000390c  lea     rcx, [rsp+14F0h+var_14D0]
0x180003911  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003916  cmp     [rbp+13F0h+OutputString], r15w
0x18000391e  jnz     short loc_180003934
0x180003920  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180003925  mov     rdx, rbx; unsigned __int16 *
0x180003928  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000392f  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003934  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000393b  call    cs:__imp_OutputDebugStringW
0x180003941  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180003946  jnz     short loc_180003951
0x180003948  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18000394f  jz      short loc_180003962
0x180003951  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003958  test    rax, rax
0x18000395b  jz      short loc_180003962
0x18000395d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003962  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180003967  jnz     short loc_180003995
0x180003969  mov     rcx, [rbp+13F0h+var_30]
0x180003970  xor     rcx, rsp; StackCookie
0x180003973  call    __security_check_cookie
0x180003978  mov     rbx, [rsp+14F0h+arg_10]
0x180003980  add     rsp, 14D0h
0x180003987  pop     r15
0x180003989  pop     r14
0x18000398b  pop     rdi
0x18000398c  pop     rsi
0x18000398d  pop     rbp
0x18000398e  retn
0x18000398f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003995  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000399a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
