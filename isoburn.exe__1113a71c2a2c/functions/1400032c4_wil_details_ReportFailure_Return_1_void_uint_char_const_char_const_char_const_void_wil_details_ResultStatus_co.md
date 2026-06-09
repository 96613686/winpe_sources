# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1400032c4`
- end: `0x140003558`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140002dac`

## callees

- `0x140001fa0`
- `0x140002bc6`
- `0x1400032c4`
- `0x140005024`
- `0x140007770`
- `0x1400096d0`
- `0x140009a1c`
- `0x14000f6e0`
- `0x140010010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x140003469`
- `KERNEL32!IsDebuggerPresent` at `0x140003469`
- `KERNEL32!OutputDebugStringW` at `0x1400034f3`
- `KERNEL32!OutputDebugStringW` at `0x1400034f3`
- `KERNEL32!GetCurrentThreadId` at `0x14000336e`
- `KERNEL32!GetCurrentThreadId` at `0x14000336e`

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
0x1400032c4  mov     [rsp-8+arg_10], rbx
0x1400032c9  push    rbp
0x1400032ca  push    rsi
0x1400032cb  push    rdi
0x1400032cc  push    r14
0x1400032ce  push    r15
0x1400032d0  lea     rbp, [rsp-13D0h]
0x1400032d8  mov     eax, 14D0h
0x1400032dd  call    _alloca_probe
0x1400032e2  sub     rsp, rax
0x1400032e5  mov     rax, cs:__security_cookie
0x1400032ec  xor     rax, rsp
0x1400032ef  mov     [rbp+13F0h+var_30], rax
0x1400032f6  mov     rdi, [rbp+13F0h+arg_28]
0x1400032fd  mov     esi, edx
0x1400032ff  mov     r14, rcx
0x140003302  xor     edx, edx; Val
0x140003304  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x140003309  mov     r8d, 98h; Size
0x14000330f  call    memset_0
0x140003314  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x14000331b  xor     r15d, r15d
0x14000331e  mov     [rbp+13F0h+OutputString], r15w
0x140003326  mov     [rbp+13F0h+var_1430], r15b
0x14000332a  mov     ecx, [rdx]; this
0x14000332c  mov     eax, [rdx+4]
0x14000332f  mov     [rsp+14F0h+var_14C8], ecx
0x140003333  mov     [rsp+14F0h+var_14C4], eax
0x140003337  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x14000333c  cmp     dword ptr [rdx+8], 1
0x140003340  mov     ebx, eax
0x140003342  lea     eax, [r15+8]
0x140003346  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x14000334e  mov     ecx, r15d
0x140003351  cmovz   ecx, eax
0x140003354  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x140003358  lea     ecx, [rax-7]
0x14000335b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140003363  inc     ecx
0x140003365  mov     [rsp+14F0h+var_14B8], r15
0x14000336a  mov     [rsp+14F0h+var_14C0], ecx
0x14000336e  call    cs:__imp_GetCurrentThreadId
0x140003374  xorps   xmm0, xmm0
0x140003377  mov     [rsp+14F0h+var_1490], esi
0x14000337b  mov     [rsp+14F0h+var_14B0], eax
0x14000337f  xorps   xmm1, xmm1
0x140003382  lea     rax, aWil; "wil"
0x140003389  mov     [rsp+14F0h+var_148C], ebx
0x14000338d  mov     [rsp+14F0h+var_1498], rax
0x140003392  xor     eax, eax
0x140003394  mov     [rbp+13F0h+var_1458], rax
0x140003398  mov     [rbp+13F0h+var_1470], rax
0x14000339c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1400033a3  mov     [rsp+14F0h+var_14A8], r15
0x1400033a8  mov     [rsp+14F0h+var_14A0], r15
0x1400033ad  mov     [rbp+13F0h+var_1448], rdi
0x1400033b1  mov     [rbp+13F0h+var_1440], r14
0x1400033b5  mov     [rsp+14F0h+var_1488], r15
0x1400033ba  movups  [rbp+13F0h+var_1468], xmm0
0x1400033be  movups  [rsp+14F0h+var_1480], xmm1
0x1400033c3  test    rax, rax
0x1400033c6  jz      short loc_1400033D3
0x1400033c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400033cd  mov     [rbp+13F0h+var_1450], rax
0x1400033d1  jmp     short loc_1400033D7
0x1400033d3  mov     [rbp+13F0h+var_1450], r15
0x1400033d7  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400033de  test    rax, rax
0x1400033e1  jz      short loc_1400033ED
0x1400033e3  lea     rcx, [rsp+14F0h+var_14D0]
0x1400033e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400033ed  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400033f4  test    rax, rax
0x1400033f7  jz      short loc_14000340D
0x1400033f9  mov     r8d, 400h
0x1400033ff  lea     rdx, [rbp+13F0h+var_1430]
0x140003403  lea     rcx, [rsp+14F0h+var_14D0]
0x140003408  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000340d  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140003414  test    rax, rax
0x140003417  jz      short loc_140003423
0x140003419  lea     rcx, [rsp+14F0h+var_14D0]
0x14000341e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003423  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000342a  test    rax, rax
0x14000342d  jz      short loc_140003440
0x14000342f  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140003434  jnz     short loc_140003440
0x140003436  lea     rcx, [rsp+14F0h+var_14D0]
0x14000343b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003440  cmp     [rsp+14F0h+var_14C8], r15d
0x140003445  jge     loc_140003547
0x14000344b  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x140003452  jnz     short loc_140003473
0x140003454  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14000345b  test    rax, rax
0x14000345e  jz      short loc_140003469
0x140003460  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003465  test    al, al
0x140003467  jmp     short loc_140003471
0x140003469  call    cs:__imp_IsDebuggerPresent
0x14000346f  test    eax, eax
0x140003471  jz      short loc_14000347A
0x140003473  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140003478  jz      short loc_1400034A0
0x14000347a  mov     rax, cs:g_pfnResultLoggingCallback
0x140003481  test    rax, rax
0x140003484  jz      short loc_1400034F9
0x140003486  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14000348d  jnz     short loc_1400034F9
0x14000348f  xor     r8d, r8d
0x140003492  lea     rcx, [rsp+14F0h+var_14D0]
0x140003497  xor     edx, edx
0x140003499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000349e  jmp     short loc_1400034F9
0x1400034a0  mov     rax, cs:g_pfnResultLoggingCallback
0x1400034a7  mov     ebx, 800h
0x1400034ac  test    rax, rax
0x1400034af  jz      short loc_1400034CE
0x1400034b1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1400034b8  jnz     short loc_1400034CE
0x1400034ba  mov     r8d, ebx
0x1400034bd  lea     rdx, [rbp+13F0h+OutputString]
0x1400034c4  lea     rcx, [rsp+14F0h+var_14D0]
0x1400034c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400034ce  cmp     [rbp+13F0h+OutputString], r15w
0x1400034d6  jnz     short loc_1400034EC
0x1400034d8  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1400034dd  mov     rdx, rbx; unsigned __int16 *
0x1400034e0  lea     rcx, [rbp+13F0h+OutputString]; this
0x1400034e7  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1400034ec  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1400034f3  call    cs:__imp_OutputDebugStringW
0x1400034f9  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1400034fe  jnz     short loc_140003509
0x140003500  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x140003507  jz      short loc_14000351A
0x140003509  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140003510  test    rax, rax
0x140003513  jz      short loc_14000351A
0x140003515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000351a  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x14000351f  jnz     short loc_14000354D
0x140003521  mov     rcx, [rbp+13F0h+var_30]
0x140003528  xor     rcx, rsp; StackCookie
0x14000352b  call    __security_check_cookie
0x140003530  mov     rbx, [rsp+14F0h+arg_10]
0x140003538  add     rsp, 14D0h
0x14000353f  pop     r15
0x140003541  pop     r14
0x140003543  pop     rdi
0x140003544  pop     rsi
0x140003545  pop     rbp
0x140003546  retn
0x140003547  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14000354d  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140003552  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
