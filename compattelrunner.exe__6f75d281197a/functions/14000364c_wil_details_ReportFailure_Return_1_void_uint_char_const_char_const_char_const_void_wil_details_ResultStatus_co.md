# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x14000364c`
- end: `0x1400038e2`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x14000312c`

## callees

- `0x140001ba0`
- `0x1400026c0`
- `0x14000364c`
- `0x140005e84`
- `0x140007868`
- `0x140009f50`
- `0x14000a11c`
- `0x1400a7290`
- `0x1400a8010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400036f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400036f7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400037f2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400037f2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000387c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000387c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v9; // ebx
  int v10; // ecx
  __int64 v11; // rdx
  const struct wil::FailureInfo *v12; // rdx
  wil::details::in1diag3 *v13; // rcx
  const struct wil::FailureInfo *v14; // r9
  bool v15; // zf
  int v16; // [rsp+20h] [rbp-E0h] BYREF
  int v17; // [rsp+24h] [rbp-DCh]
  int v18; // [rsp+28h] [rbp-D8h]
  int v19; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v20; // [rsp+30h] [rbp-D0h]
  __int64 v21; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v23; // [rsp+48h] [rbp-B8h]
  __int64 v24; // [rsp+50h] [rbp-B0h]
  const char *v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+60h] [rbp-A0h]
  int v27; // [rsp+64h] [rbp-9Ch]
  __int64 v28; // [rsp+68h] [rbp-98h]
  __int128 v29; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+80h] [rbp-80h]
  __int128 v31; // [rsp+88h] [rbp-78h]
  __int64 v32; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v34; // [rsp+A8h] [rbp-58h]
  __int64 v35; // [rsp+B0h] [rbp-50h]
  char v36[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v16, 0, 0x98u);
  OutputString[0] = 0;
  v36[0] = 0;
  v18 = *a7;
  v19 = a7[1];
  v9 = wil::details::RecordReturn((wil::details *)(unsigned int)v18, (int)a7);
  v16 = 1;
  v10 = 0;
  if ( *(_DWORD *)(v11 + 8) == 1 )
    v10 = 8;
  v17 = v10;
  v20 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v25 = "wil";
  v26 = a2;
  v27 = v9;
  v23 = 0;
  v24 = 0;
  v34 = a6;
  v35 = a1;
  v28 = 0;
  v31 = 0;
  v32 = 0;
  v29 = 0;
  v30 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v13);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v16, v36, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v16);
  if ( wil::details::g_pfnOriginateCallback && (v17 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v16);
  if ( v18 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v15 = !IsDebuggerPresent())
      : (v15 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v13) == 0),
        v15)
    || (v17 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v16, v14);
    OutputDebugStringW(OutputString);
  }
  if ( ((v17 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v13);
  if ( (v17 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v16, v12);
}

```

## disassembly

```asm
0x14000364c  mov     [rsp-8+arg_10], rbx
0x140003651  push    rbp
0x140003652  push    rsi
0x140003653  push    rdi
0x140003654  push    r14
0x140003656  push    r15
0x140003658  lea     rbp, [rsp-13D0h]
0x140003660  mov     eax, 14D0h
0x140003665  call    _alloca_probe
0x14000366a  sub     rsp, rax
0x14000366d  mov     rax, cs:__security_cookie
0x140003674  xor     rax, rsp
0x140003677  mov     [rbp+13F0h+var_30], rax
0x14000367e  mov     esi, edx
0x140003680  mov     r14, rcx
0x140003683  mov     rdi, [rbp+13F0h+arg_28]
0x14000368a  xor     edx, edx; Val
0x14000368c  mov     r8d, 98h; Size
0x140003692  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x140003697  call    memset_0
0x14000369c  nop
0x14000369d  xor     r15d, r15d
0x1400036a0  mov     [rbp+13F0h+OutputString], r15w
0x1400036a8  mov     [rbp+13F0h+var_1430], r15b
0x1400036ac  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x1400036b3  mov     ecx, [rdx]; this
0x1400036b5  mov     [rsp+14F0h+var_14C8], ecx
0x1400036b9  mov     eax, [rdx+4]
0x1400036bc  mov     [rsp+14F0h+var_14C4], eax
0x1400036c0  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1400036c5  mov     ebx, eax
0x1400036c7  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x1400036cf  mov     ecx, r15d
0x1400036d2  lea     eax, [r15+8]
0x1400036d6  cmp     dword ptr [rdx+8], 1
0x1400036da  cmovz   ecx, eax
0x1400036dd  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1400036e1  lea     ecx, [rax-7]
0x1400036e4  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400036ec  inc     ecx
0x1400036ee  mov     [rsp+14F0h+var_14C0], ecx
0x1400036f2  mov     [rsp+14F0h+var_14B8], r15
0x1400036f7  call    cs:__imp_GetCurrentThreadId
0x1400036fd  mov     [rsp+14F0h+var_14B0], eax
0x140003701  lea     rax, aWil; "wil"
0x140003708  mov     [rsp+14F0h+var_1498], rax
0x14000370d  mov     [rsp+14F0h+var_1490], esi
0x140003711  mov     [rsp+14F0h+var_148C], ebx
0x140003715  mov     [rsp+14F0h+var_14A8], r15
0x14000371a  mov     [rsp+14F0h+var_14A0], r15
0x14000371f  mov     [rbp+13F0h+var_1448], rdi
0x140003723  mov     [rbp+13F0h+var_1440], r14
0x140003727  mov     [rsp+14F0h+var_1488], r15
0x14000372c  xorps   xmm0, xmm0
0x14000372f  xor     eax, eax
0x140003731  movups  [rbp+13F0h+var_1468], xmm0
0x140003735  mov     [rbp+13F0h+var_1458], rax
0x140003739  xorps   xmm1, xmm1
0x14000373c  movups  [rsp+14F0h+var_1480], xmm1
0x140003741  mov     [rbp+13F0h+var_1470], rax
0x140003745  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000374c  test    rax, rax
0x14000374f  jz      short loc_14000375C
0x140003751  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003756  mov     [rbp+13F0h+var_1450], rax
0x14000375a  jmp     short loc_140003760
0x14000375c  mov     [rbp+13F0h+var_1450], r15
0x140003760  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140003767  test    rax, rax
0x14000376a  jz      short loc_140003776
0x14000376c  lea     rcx, [rsp+14F0h+var_14D0]
0x140003771  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003776  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000377d  test    rax, rax
0x140003780  jz      short loc_140003796
0x140003782  mov     r8d, 400h
0x140003788  lea     rdx, [rbp+13F0h+var_1430]
0x14000378c  lea     rcx, [rsp+14F0h+var_14D0]
0x140003791  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003796  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000379d  test    rax, rax
0x1400037a0  jz      short loc_1400037AC
0x1400037a2  lea     rcx, [rsp+14F0h+var_14D0]
0x1400037a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400037ac  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400037b3  test    rax, rax
0x1400037b6  jz      short loc_1400037C9
0x1400037b8  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1400037bd  jnz     short loc_1400037C9
0x1400037bf  lea     rcx, [rsp+14F0h+var_14D0]
0x1400037c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400037c9  cmp     [rsp+14F0h+var_14C8], r15d
0x1400037ce  jge     loc_1400038DC
0x1400037d4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x1400037db  jnz     short loc_1400037FC
0x1400037dd  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400037e4  test    rax, rax
0x1400037e7  jz      short loc_1400037F2
0x1400037e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400037ee  test    al, al
0x1400037f0  jmp     short loc_1400037FA
0x1400037f2  call    cs:__imp_IsDebuggerPresent
0x1400037f8  test    eax, eax
0x1400037fa  jz      short loc_140003803
0x1400037fc  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140003801  jz      short loc_140003829
0x140003803  mov     rax, cs:g_pfnResultLoggingCallback
0x14000380a  test    rax, rax
0x14000380d  jz      short loc_140003882
0x14000380f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140003816  jnz     short loc_140003882
0x140003818  xor     r8d, r8d
0x14000381b  xor     edx, edx
0x14000381d  lea     rcx, [rsp+14F0h+var_14D0]
0x140003822  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003827  jmp     short loc_140003882
0x140003829  mov     ebx, 800h
0x14000382e  mov     rax, cs:g_pfnResultLoggingCallback
0x140003835  test    rax, rax
0x140003838  jz      short loc_140003857
0x14000383a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140003841  jnz     short loc_140003857
0x140003843  mov     r8d, ebx
0x140003846  lea     rdx, [rbp+13F0h+OutputString]
0x14000384d  lea     rcx, [rsp+14F0h+var_14D0]
0x140003852  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003857  cmp     [rbp+13F0h+OutputString], r15w
0x14000385f  jnz     short loc_140003875
0x140003861  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x140003866  mov     rdx, rbx; unsigned __int16 *
0x140003869  lea     rcx, [rbp+13F0h+OutputString]; this
0x140003870  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140003875  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x14000387c  call    cs:__imp_OutputDebugStringW
0x140003882  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x140003887  jnz     short loc_140003892
0x140003889  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x140003890  jz      short loc_1400038A4
0x140003892  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140003899  test    rax, rax
0x14000389c  jz      short loc_1400038A4
0x14000389e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400038a3  nop
0x1400038a4  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x1400038a9  jnz     short loc_1400038D1
0x1400038ab  mov     rcx, [rbp+13F0h+var_30]
0x1400038b2  xor     rcx, rsp; StackCookie
0x1400038b5  call    __security_check_cookie
0x1400038ba  mov     rbx, [rsp+14F0h+arg_10]
0x1400038c2  add     rsp, 14D0h
0x1400038c9  pop     r15
0x1400038cb  pop     r14
0x1400038cd  pop     rdi
0x1400038ce  pop     rsi
0x1400038cf  pop     rbp
0x1400038d0  retn
0x1400038d1  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1400038d6  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1400038dc  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
