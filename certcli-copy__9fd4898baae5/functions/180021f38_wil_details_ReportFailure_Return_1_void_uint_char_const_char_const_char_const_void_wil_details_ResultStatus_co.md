# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180021f38`
- end: `0x1800221cc`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180021a40`

## callees

- `0x18001b934`
- `0x180021f38`
- `0x180024ac0`
- `0x180025cf4`
- `0x180025eb0`
- `0x1800396f2`
- `0x180039740`
- `0x180039800`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021fe2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021fe2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180022167`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180022167`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800220dd`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800220dd`

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
0x180021f38  mov     [rsp-8+arg_10], rbx
0x180021f3d  push    rbp
0x180021f3e  push    rsi
0x180021f3f  push    rdi
0x180021f40  push    r14
0x180021f42  push    r15
0x180021f44  lea     rbp, [rsp-13D0h]
0x180021f4c  mov     eax, 14D0h
0x180021f51  call    _alloca_probe
0x180021f56  sub     rsp, rax
0x180021f59  mov     rax, cs:__security_cookie
0x180021f60  xor     rax, rsp
0x180021f63  mov     [rbp+13F0h+var_30], rax
0x180021f6a  mov     rdi, [rbp+13F0h+arg_28]
0x180021f71  mov     esi, edx
0x180021f73  mov     r14, rcx
0x180021f76  xor     edx, edx; Val
0x180021f78  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180021f7d  mov     r8d, 98h; Size
0x180021f83  call    memset_0
0x180021f88  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180021f8f  xor     r15d, r15d
0x180021f92  mov     [rbp+13F0h+OutputString], r15w
0x180021f9a  mov     [rbp+13F0h+var_1430], r15b
0x180021f9e  mov     ecx, [rdx]; this
0x180021fa0  mov     eax, [rdx+4]
0x180021fa3  mov     [rsp+14F0h+var_14C8], ecx
0x180021fa7  mov     [rsp+14F0h+var_14C4], eax
0x180021fab  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180021fb0  cmp     dword ptr [rdx+8], 1
0x180021fb4  mov     ebx, eax
0x180021fb6  lea     eax, [r15+8]
0x180021fba  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180021fc2  mov     ecx, r15d
0x180021fc5  cmovz   ecx, eax
0x180021fc8  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180021fcc  lea     ecx, [rax-7]
0x180021fcf  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180021fd7  inc     ecx
0x180021fd9  mov     [rsp+14F0h+var_14B8], r15
0x180021fde  mov     [rsp+14F0h+var_14C0], ecx
0x180021fe2  call    cs:__imp_GetCurrentThreadId
0x180021fe8  xorps   xmm0, xmm0
0x180021feb  mov     [rsp+14F0h+var_1490], esi
0x180021fef  mov     [rsp+14F0h+var_14B0], eax
0x180021ff3  xorps   xmm1, xmm1
0x180021ff6  lea     rax, aWil; "wil"
0x180021ffd  mov     [rsp+14F0h+var_148C], ebx
0x180022001  mov     [rsp+14F0h+var_1498], rax
0x180022006  xor     eax, eax
0x180022008  mov     [rbp+13F0h+var_1458], rax
0x18002200c  mov     [rbp+13F0h+var_1470], rax
0x180022010  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180022017  mov     [rsp+14F0h+var_14A8], r15
0x18002201c  mov     [rsp+14F0h+var_14A0], r15
0x180022021  mov     [rbp+13F0h+var_1448], rdi
0x180022025  mov     [rbp+13F0h+var_1440], r14
0x180022029  mov     [rsp+14F0h+var_1488], r15
0x18002202e  movups  [rbp+13F0h+var_1468], xmm0
0x180022032  movups  [rsp+14F0h+var_1480], xmm1
0x180022037  test    rax, rax
0x18002203a  jz      short loc_180022047
0x18002203c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022041  mov     [rbp+13F0h+var_1450], rax
0x180022045  jmp     short loc_18002204B
0x180022047  mov     [rbp+13F0h+var_1450], r15
0x18002204b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180022052  test    rax, rax
0x180022055  jz      short loc_180022061
0x180022057  lea     rcx, [rsp+14F0h+var_14D0]
0x18002205c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022061  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180022068  test    rax, rax
0x18002206b  jz      short loc_180022081
0x18002206d  mov     r8d, 400h
0x180022073  lea     rdx, [rbp+13F0h+var_1430]
0x180022077  lea     rcx, [rsp+14F0h+var_14D0]
0x18002207c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022081  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180022088  test    rax, rax
0x18002208b  jz      short loc_180022097
0x18002208d  lea     rcx, [rsp+14F0h+var_14D0]
0x180022092  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022097  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002209e  test    rax, rax
0x1800220a1  jz      short loc_1800220B4
0x1800220a3  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800220a8  jnz     short loc_1800220B4
0x1800220aa  lea     rcx, [rsp+14F0h+var_14D0]
0x1800220af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220b4  cmp     [rsp+14F0h+var_14C8], r15d
0x1800220b9  jge     loc_1800221BB
0x1800220bf  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x1800220c6  jnz     short loc_1800220E7
0x1800220c8  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800220cf  test    rax, rax
0x1800220d2  jz      short loc_1800220DD
0x1800220d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220d9  test    al, al
0x1800220db  jmp     short loc_1800220E5
0x1800220dd  call    cs:__imp_IsDebuggerPresent
0x1800220e3  test    eax, eax
0x1800220e5  jz      short loc_1800220EE
0x1800220e7  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800220ec  jz      short loc_180022114
0x1800220ee  mov     rax, cs:g_pfnResultLoggingCallback
0x1800220f5  test    rax, rax
0x1800220f8  jz      short loc_18002216D
0x1800220fa  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180022101  jnz     short loc_18002216D
0x180022103  xor     r8d, r8d
0x180022106  lea     rcx, [rsp+14F0h+var_14D0]
0x18002210b  xor     edx, edx
0x18002210d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022112  jmp     short loc_18002216D
0x180022114  mov     rax, cs:g_pfnResultLoggingCallback
0x18002211b  mov     ebx, 800h
0x180022120  test    rax, rax
0x180022123  jz      short loc_180022142
0x180022125  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18002212c  jnz     short loc_180022142
0x18002212e  mov     r8d, ebx
0x180022131  lea     rdx, [rbp+13F0h+OutputString]
0x180022138  lea     rcx, [rsp+14F0h+var_14D0]
0x18002213d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022142  cmp     [rbp+13F0h+OutputString], r15w
0x18002214a  jnz     short loc_180022160
0x18002214c  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180022151  mov     rdx, rbx; unsigned __int16 *
0x180022154  lea     rcx, [rbp+13F0h+OutputString]; this
0x18002215b  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180022160  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180022167  call    cs:__imp_OutputDebugStringW
0x18002216d  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180022172  jnz     short loc_18002217D
0x180022174  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18002217b  jz      short loc_18002218E
0x18002217d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180022184  test    rax, rax
0x180022187  jz      short loc_18002218E
0x180022189  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002218e  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180022193  jnz     short loc_1800221C1
0x180022195  mov     rcx, [rbp+13F0h+var_30]
0x18002219c  xor     rcx, rsp; StackCookie
0x18002219f  call    __security_check_cookie
0x1800221a4  mov     rbx, [rsp+14F0h+arg_10]
0x1800221ac  add     rsp, 14D0h
0x1800221b3  pop     r15
0x1800221b5  pop     r14
0x1800221b7  pop     rdi
0x1800221b8  pop     rsi
0x1800221b9  pop     rbp
0x1800221ba  retn
0x1800221bb  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800221c1  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800221c6  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
