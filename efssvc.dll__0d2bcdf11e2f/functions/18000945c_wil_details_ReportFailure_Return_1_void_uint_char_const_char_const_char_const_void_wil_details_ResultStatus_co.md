# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000945c`
- end: `0x180009703`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `679`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180008f2c`

## callees

- `0x18000945c`
- `0x18000a03c`
- `0x18000b02c`
- `0x18000bc80`
- `0x18000bd5c`
- `0x18000d192`
- `0x18000d1c0`
- `0x18000d250`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180009607`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180009607`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009697`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009697`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009506`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009506`

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
0x18000945c  mov     [rsp-8+arg_10], rbx
0x180009461  push    rbp
0x180009462  push    rsi
0x180009463  push    rdi
0x180009464  push    r14
0x180009466  push    r15
0x180009468  lea     rbp, [rsp-13D0h]
0x180009470  mov     eax, 14D0h
0x180009475  call    _alloca_probe
0x18000947a  sub     rsp, rax
0x18000947d  mov     rax, cs:__security_cookie
0x180009484  xor     rax, rsp
0x180009487  mov     [rbp+13F0h+var_30], rax
0x18000948e  mov     rdi, [rbp+13F0h+arg_28]
0x180009495  mov     esi, edx
0x180009497  mov     r14, rcx
0x18000949a  xor     edx, edx; Val
0x18000949c  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800094a1  mov     r8d, 98h; Size
0x1800094a7  call    memset_0
0x1800094ac  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x1800094b3  xor     r15d, r15d
0x1800094b6  mov     [rbp+13F0h+OutputString], r15w
0x1800094be  mov     [rbp+13F0h+var_1430], r15b
0x1800094c2  mov     ecx, [rdx]; this
0x1800094c4  mov     eax, [rdx+4]
0x1800094c7  mov     [rsp+14F0h+var_14C8], ecx
0x1800094cb  mov     [rsp+14F0h+var_14C4], eax
0x1800094cf  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800094d4  cmp     dword ptr [rdx+8], 1
0x1800094d8  mov     ebx, eax
0x1800094da  lea     eax, [r15+8]
0x1800094de  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x1800094e6  mov     ecx, r15d
0x1800094e9  cmovz   ecx, eax
0x1800094ec  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800094f0  lea     ecx, [rax-7]
0x1800094f3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800094fb  inc     ecx
0x1800094fd  mov     [rsp+14F0h+var_14B8], r15
0x180009502  mov     [rsp+14F0h+var_14C0], ecx
0x180009506  call    cs:__imp_GetCurrentThreadId
0x18000950d  nop     dword ptr [rax+rax+00h]
0x180009512  xorps   xmm0, xmm0
0x180009515  mov     [rsp+14F0h+var_1490], esi
0x180009519  mov     [rsp+14F0h+var_14B0], eax
0x18000951d  xorps   xmm1, xmm1
0x180009520  lea     rax, aWil; "wil"
0x180009527  mov     [rsp+14F0h+var_148C], ebx
0x18000952b  mov     [rsp+14F0h+var_1498], rax
0x180009530  xor     eax, eax
0x180009532  mov     [rbp+13F0h+var_1458], rax
0x180009536  mov     [rbp+13F0h+var_1470], rax
0x18000953a  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180009541  mov     [rsp+14F0h+var_14A8], r15
0x180009546  mov     [rsp+14F0h+var_14A0], r15
0x18000954b  mov     [rbp+13F0h+var_1448], rdi
0x18000954f  mov     [rbp+13F0h+var_1440], r14
0x180009553  mov     [rsp+14F0h+var_1488], r15
0x180009558  movups  [rbp+13F0h+var_1468], xmm0
0x18000955c  movups  [rsp+14F0h+var_1480], xmm1
0x180009561  test    rax, rax
0x180009564  jz      short loc_180009571
0x180009566  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000956b  mov     [rbp+13F0h+var_1450], rax
0x18000956f  jmp     short loc_180009575
0x180009571  mov     [rbp+13F0h+var_1450], r15
0x180009575  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000957c  test    rax, rax
0x18000957f  jz      short loc_18000958B
0x180009581  lea     rcx, [rsp+14F0h+var_14D0]
0x180009586  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000958b  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180009592  test    rax, rax
0x180009595  jz      short loc_1800095AB
0x180009597  mov     r8d, 400h
0x18000959d  lea     rdx, [rbp+13F0h+var_1430]
0x1800095a1  lea     rcx, [rsp+14F0h+var_14D0]
0x1800095a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095ab  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800095b2  test    rax, rax
0x1800095b5  jz      short loc_1800095C1
0x1800095b7  lea     rcx, [rsp+14F0h+var_14D0]
0x1800095bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095c1  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800095c8  test    rax, rax
0x1800095cb  jz      short loc_1800095DE
0x1800095cd  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800095d2  jnz     short loc_1800095DE
0x1800095d4  lea     rcx, [rsp+14F0h+var_14D0]
0x1800095d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095de  cmp     [rsp+14F0h+var_14C8], r15d
0x1800095e3  jge     loc_1800096F2
0x1800095e9  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x1800095f0  jnz     short loc_180009617
0x1800095f2  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800095f9  test    rax, rax
0x1800095fc  jz      short loc_180009607
0x1800095fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009603  test    al, al
0x180009605  jmp     short loc_180009615
0x180009607  call    cs:__imp_IsDebuggerPresent
0x18000960e  nop     dword ptr [rax+rax+00h]
0x180009613  test    eax, eax
0x180009615  jz      short loc_18000961E
0x180009617  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000961c  jz      short loc_180009644
0x18000961e  mov     rax, cs:g_pfnResultLoggingCallback
0x180009625  test    rax, rax
0x180009628  jz      short loc_1800096A3
0x18000962a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180009631  jnz     short loc_1800096A3
0x180009633  xor     r8d, r8d
0x180009636  lea     rcx, [rsp+14F0h+var_14D0]
0x18000963b  xor     edx, edx
0x18000963d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009642  jmp     short loc_1800096A3
0x180009644  mov     rax, cs:g_pfnResultLoggingCallback
0x18000964b  mov     ebx, 800h
0x180009650  test    rax, rax
0x180009653  jz      short loc_180009672
0x180009655  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000965c  jnz     short loc_180009672
0x18000965e  mov     r8d, ebx
0x180009661  lea     rdx, [rbp+13F0h+OutputString]
0x180009668  lea     rcx, [rsp+14F0h+var_14D0]
0x18000966d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009672  cmp     [rbp+13F0h+OutputString], r15w
0x18000967a  jnz     short loc_180009690
0x18000967c  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180009681  mov     rdx, rbx; unsigned __int16 *
0x180009684  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000968b  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180009690  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180009697  call    cs:__imp_OutputDebugStringW
0x18000969e  nop     dword ptr [rax+rax+00h]
0x1800096a3  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800096a8  jnz     short loc_1800096B3
0x1800096aa  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x1800096b1  jz      short loc_1800096C4
0x1800096b3  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800096ba  test    rax, rax
0x1800096bd  jz      short loc_1800096C4
0x1800096bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096c4  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x1800096c9  jnz     short loc_1800096F8
0x1800096cb  mov     rcx, [rbp+13F0h+var_30]
0x1800096d2  xor     rcx, rsp; StackCookie
0x1800096d5  call    __security_check_cookie
0x1800096da  mov     rbx, [rsp+14F0h+arg_10]
0x1800096e2  add     rsp, 14D0h
0x1800096e9  pop     r15
0x1800096eb  pop     r14
0x1800096ed  pop     rdi
0x1800096ee  pop     rsi
0x1800096ef  pop     rbp
0x1800096f0  retn
0x1800096f2  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800096f8  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800096fd  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
