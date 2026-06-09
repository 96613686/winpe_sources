# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180003638`
- end: `0x1800038cc`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180003118`

## callees

- `0x180003638`
- `0x1800052e4`
- `0x180006794`
- `0x180008280`
- `0x18000843c`
- `0x18000bbc2`
- `0x18000bbf0`
- `0x18000bc80`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800036e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800036e2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003867`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003867`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800037dd`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800037dd`

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
0x180003638  mov     [rsp-8+arg_10], rbx
0x18000363d  push    rbp
0x18000363e  push    rsi
0x18000363f  push    rdi
0x180003640  push    r14
0x180003642  push    r15
0x180003644  lea     rbp, [rsp-13D0h]
0x18000364c  mov     eax, 14D0h
0x180003651  call    _alloca_probe
0x180003656  sub     rsp, rax
0x180003659  mov     rax, cs:__security_cookie
0x180003660  xor     rax, rsp
0x180003663  mov     [rbp+13F0h+var_30], rax
0x18000366a  mov     rdi, [rbp+13F0h+arg_28]
0x180003671  mov     esi, edx
0x180003673  mov     r14, rcx
0x180003676  xor     edx, edx; Val
0x180003678  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000367d  mov     r8d, 98h; Size
0x180003683  call    memset_0
0x180003688  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18000368f  xor     r15d, r15d
0x180003692  mov     [rbp+13F0h+OutputString], r15w
0x18000369a  mov     [rbp+13F0h+var_1430], r15b
0x18000369e  mov     ecx, [rdx]; this
0x1800036a0  mov     eax, [rdx+4]
0x1800036a3  mov     [rsp+14F0h+var_14C8], ecx
0x1800036a7  mov     [rsp+14F0h+var_14C4], eax
0x1800036ab  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800036b0  cmp     dword ptr [rdx+8], 1
0x1800036b4  mov     ebx, eax
0x1800036b6  lea     eax, [r15+8]
0x1800036ba  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x1800036c2  mov     ecx, r15d
0x1800036c5  cmovz   ecx, eax
0x1800036c8  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800036cc  lea     ecx, [rax-7]
0x1800036cf  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800036d7  inc     ecx
0x1800036d9  mov     [rsp+14F0h+var_14B8], r15
0x1800036de  mov     [rsp+14F0h+var_14C0], ecx
0x1800036e2  call    cs:__imp_GetCurrentThreadId
0x1800036e8  xorps   xmm0, xmm0
0x1800036eb  mov     [rsp+14F0h+var_1490], esi
0x1800036ef  mov     [rsp+14F0h+var_14B0], eax
0x1800036f3  xorps   xmm1, xmm1
0x1800036f6  lea     rax, aWil; "wil"
0x1800036fd  mov     [rsp+14F0h+var_148C], ebx
0x180003701  mov     [rsp+14F0h+var_1498], rax
0x180003706  xor     eax, eax
0x180003708  mov     [rbp+13F0h+var_1458], rax
0x18000370c  mov     [rbp+13F0h+var_1470], rax
0x180003710  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003717  mov     [rsp+14F0h+var_14A8], r15
0x18000371c  mov     [rsp+14F0h+var_14A0], r15
0x180003721  mov     [rbp+13F0h+var_1448], rdi
0x180003725  mov     [rbp+13F0h+var_1440], r14
0x180003729  mov     [rsp+14F0h+var_1488], r15
0x18000372e  movups  [rbp+13F0h+var_1468], xmm0
0x180003732  movups  [rsp+14F0h+var_1480], xmm1
0x180003737  test    rax, rax
0x18000373a  jz      short loc_180003747
0x18000373c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003741  mov     [rbp+13F0h+var_1450], rax
0x180003745  jmp     short loc_18000374B
0x180003747  mov     [rbp+13F0h+var_1450], r15
0x18000374b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003752  test    rax, rax
0x180003755  jz      short loc_180003761
0x180003757  lea     rcx, [rsp+14F0h+var_14D0]
0x18000375c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003761  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003768  test    rax, rax
0x18000376b  jz      short loc_180003781
0x18000376d  mov     r8d, 400h
0x180003773  lea     rdx, [rbp+13F0h+var_1430]
0x180003777  lea     rcx, [rsp+14F0h+var_14D0]
0x18000377c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003781  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003788  test    rax, rax
0x18000378b  jz      short loc_180003797
0x18000378d  lea     rcx, [rsp+14F0h+var_14D0]
0x180003792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003797  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000379e  test    rax, rax
0x1800037a1  jz      short loc_1800037B4
0x1800037a3  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800037a8  jnz     short loc_1800037B4
0x1800037aa  lea     rcx, [rsp+14F0h+var_14D0]
0x1800037af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037b4  cmp     [rsp+14F0h+var_14C8], r15d
0x1800037b9  jge     loc_1800038BB
0x1800037bf  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x1800037c6  jnz     short loc_1800037E7
0x1800037c8  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800037cf  test    rax, rax
0x1800037d2  jz      short loc_1800037DD
0x1800037d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037d9  test    al, al
0x1800037db  jmp     short loc_1800037E5
0x1800037dd  call    cs:__imp_IsDebuggerPresent
0x1800037e3  test    eax, eax
0x1800037e5  jz      short loc_1800037EE
0x1800037e7  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800037ec  jz      short loc_180003814
0x1800037ee  mov     rax, cs:g_pfnResultLoggingCallback
0x1800037f5  test    rax, rax
0x1800037f8  jz      short loc_18000386D
0x1800037fa  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180003801  jnz     short loc_18000386D
0x180003803  xor     r8d, r8d
0x180003806  lea     rcx, [rsp+14F0h+var_14D0]
0x18000380b  xor     edx, edx
0x18000380d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003812  jmp     short loc_18000386D
0x180003814  mov     rax, cs:g_pfnResultLoggingCallback
0x18000381b  mov     ebx, 800h
0x180003820  test    rax, rax
0x180003823  jz      short loc_180003842
0x180003825  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000382c  jnz     short loc_180003842
0x18000382e  mov     r8d, ebx
0x180003831  lea     rdx, [rbp+13F0h+OutputString]
0x180003838  lea     rcx, [rsp+14F0h+var_14D0]
0x18000383d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003842  cmp     [rbp+13F0h+OutputString], r15w
0x18000384a  jnz     short loc_180003860
0x18000384c  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180003851  mov     rdx, rbx; unsigned __int16 *
0x180003854  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000385b  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003860  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180003867  call    cs:__imp_OutputDebugStringW
0x18000386d  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180003872  jnz     short loc_18000387D
0x180003874  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18000387b  jz      short loc_18000388E
0x18000387d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003884  test    rax, rax
0x180003887  jz      short loc_18000388E
0x180003889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000388e  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180003893  jnz     short loc_1800038C1
0x180003895  mov     rcx, [rbp+13F0h+var_30]
0x18000389c  xor     rcx, rsp; StackCookie
0x18000389f  call    __security_check_cookie
0x1800038a4  mov     rbx, [rsp+14F0h+arg_10]
0x1800038ac  add     rsp, 14D0h
0x1800038b3  pop     r15
0x1800038b5  pop     r14
0x1800038b7  pop     rdi
0x1800038b8  pop     rsi
0x1800038b9  pop     rbp
0x1800038ba  retn
0x1800038bb  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800038c1  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800038c6  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
