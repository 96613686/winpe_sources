# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180002844`
- end: `0x180002afd`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `697`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800022bc`

## callees

- `0x180002844`
- `0x180003814`
- `0x180004af4`
- `0x180005b0c`
- `0x180005ce8`
- `0x18000cc8e`
- `0x18000ccc0`
- `0x18000cd80`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000290a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000290a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002a95`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002a95`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002a05`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002a05`

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
      g_pfnResultLoggingCallback(&v18, 0, 0, v16);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048, v16);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v18, v16);
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
0x180002844  push    rbp
0x180002846  push    rbx
0x180002847  push    rsi
0x180002848  push    rdi
0x180002849  push    r12
0x18000284b  push    r14
0x18000284d  push    r15
0x18000284f  lea     rbp, [rsp-13D0h]
0x180002857  mov     eax, 14D0h
0x18000285c  call    _alloca_probe
0x180002861  sub     rsp, rax
0x180002864  mov     rax, cs:__security_cookie
0x18000286b  xor     rax, rsp
0x18000286e  mov     [rbp+1400h+var_40], rax
0x180002875  mov     rsi, r8
0x180002878  mov     edi, edx
0x18000287a  mov     rbx, rcx
0x18000287d  mov     r14, [rbp+1400h+arg_28]
0x180002884  xor     edx, edx; Val
0x180002886  mov     r8d, 98h; Size
0x18000288c  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180002891  call    memset_0
0x180002896  nop
0x180002897  xor     r12d, r12d
0x18000289a  mov     [rbp+1400h+OutputString], r12w
0x1800028a2  mov     [rbp+1400h+var_1440], r12b
0x1800028a6  mov     rdx, [rbp+1400h+arg_30]; int
0x1800028ad  mov     ecx, [rdx]; this
0x1800028af  mov     [rsp+1500h+var_14D8], ecx
0x1800028b3  mov     eax, [rdx+4]
0x1800028b6  mov     [rsp+1500h+var_14D4], eax
0x1800028ba  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800028bf  mov     r15d, eax
0x1800028c2  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800028ca  mov     ecx, r12d
0x1800028cd  lea     eax, [r12+8]
0x1800028d2  cmp     dword ptr [rdx+8], 1
0x1800028d6  cmovz   ecx, eax
0x1800028d9  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800028dd  lea     ecx, [rax-7]
0x1800028e0  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800028e8  inc     ecx
0x1800028ea  mov     [rsp+1500h+var_14D0], ecx
0x1800028ee  mov     rcx, [rbp+1400h+arg_38]
0x1800028f5  test    rcx, rcx
0x1800028f8  jz      short loc_180002905
0x1800028fa  cmp     [rcx], r12w
0x1800028fe  mov     [rsp+1500h+var_14C8], rcx
0x180002903  jnz     short loc_18000290A
0x180002905  mov     [rsp+1500h+var_14C8], r12
0x18000290a  call    cs:__imp_GetCurrentThreadId
0x180002911  nop     dword ptr [rax+rax+00h]
0x180002916  mov     [rsp+1500h+var_14C0], eax
0x18000291a  mov     [rsp+1500h+var_14A8], rsi
0x18000291f  mov     [rsp+1500h+var_14A0], edi
0x180002923  mov     [rsp+1500h+var_149C], r15d
0x180002928  mov     [rsp+1500h+var_14B8], r12
0x18000292d  mov     [rsp+1500h+var_14B0], r12
0x180002932  mov     [rbp+1400h+var_1458], r14
0x180002936  mov     [rbp+1400h+var_1450], rbx
0x18000293a  mov     [rsp+1500h+var_1498], r12
0x18000293f  xorps   xmm0, xmm0
0x180002942  xor     eax, eax
0x180002944  movups  [rbp+1400h+var_1478], xmm0
0x180002948  mov     [rbp+1400h+var_1468], rax
0x18000294c  xorps   xmm1, xmm1
0x18000294f  movups  [rsp+1500h+var_1490], xmm1
0x180002954  mov     [rbp+1400h+var_1480], rax
0x180002958  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000295f  test    rax, rax
0x180002962  jz      short loc_18000296F
0x180002964  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002969  mov     [rbp+1400h+var_1460], rax
0x18000296d  jmp     short loc_180002973
0x18000296f  mov     [rbp+1400h+var_1460], r12
0x180002973  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000297a  test    rax, rax
0x18000297d  jz      short loc_180002989
0x18000297f  lea     rcx, [rsp+1500h+var_14E0]
0x180002984  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002989  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002990  test    rax, rax
0x180002993  jz      short loc_1800029A9
0x180002995  mov     r8d, 400h
0x18000299b  lea     rdx, [rbp+1400h+var_1440]
0x18000299f  lea     rcx, [rsp+1500h+var_14E0]
0x1800029a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029a9  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800029b0  test    rax, rax
0x1800029b3  jz      short loc_1800029BF
0x1800029b5  lea     rcx, [rsp+1500h+var_14E0]
0x1800029ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029bf  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800029c6  test    rax, rax
0x1800029c9  jz      short loc_1800029DC
0x1800029cb  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800029d0  jnz     short loc_1800029DC
0x1800029d2  lea     rcx, [rsp+1500h+var_14E0]
0x1800029d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029dc  cmp     [rsp+1500h+var_14D8], r12d
0x1800029e1  jge     loc_180002AF7
0x1800029e7  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800029ee  jnz     short loc_180002A15
0x1800029f0  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800029f7  test    rax, rax
0x1800029fa  jz      short loc_180002A05
0x1800029fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a01  test    al, al
0x180002a03  jmp     short loc_180002A13
0x180002a05  call    cs:__imp_IsDebuggerPresent
0x180002a0c  nop     dword ptr [rax+rax+00h]
0x180002a11  test    eax, eax
0x180002a13  jz      short loc_180002A1C
0x180002a15  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180002a1a  jz      short loc_180002A42
0x180002a1c  mov     rax, cs:g_pfnResultLoggingCallback
0x180002a23  test    rax, rax
0x180002a26  jz      short loc_180002AA1
0x180002a28  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180002a2f  jnz     short loc_180002AA1
0x180002a31  xor     r8d, r8d
0x180002a34  xor     edx, edx
0x180002a36  lea     rcx, [rsp+1500h+var_14E0]
0x180002a3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a40  jmp     short loc_180002AA1
0x180002a42  mov     ebx, 800h
0x180002a47  mov     rax, cs:g_pfnResultLoggingCallback
0x180002a4e  test    rax, rax
0x180002a51  jz      short loc_180002A70
0x180002a53  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180002a5a  jnz     short loc_180002A70
0x180002a5c  mov     r8d, ebx
0x180002a5f  lea     rdx, [rbp+1400h+OutputString]
0x180002a66  lea     rcx, [rsp+1500h+var_14E0]
0x180002a6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a70  cmp     [rbp+1400h+OutputString], r12w
0x180002a78  jnz     short loc_180002A8E
0x180002a7a  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180002a7f  mov     rdx, rbx; unsigned __int16 *
0x180002a82  lea     rcx, [rbp+1400h+OutputString]; this
0x180002a89  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002a8e  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180002a95  call    cs:__imp_OutputDebugStringW
0x180002a9c  nop     dword ptr [rax+rax+00h]
0x180002aa1  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180002aa6  jnz     short loc_180002AB1
0x180002aa8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180002aaf  jz      short loc_180002AC3
0x180002ab1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002ab8  test    rax, rax
0x180002abb  jz      short loc_180002AC3
0x180002abd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ac2  nop
0x180002ac3  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180002ac8  jnz     short loc_180002AEC
0x180002aca  mov     rcx, [rbp+1400h+var_40]
0x180002ad1  xor     rcx, rsp; StackCookie
0x180002ad4  call    __security_check_cookie
0x180002ad9  add     rsp, 14D0h
0x180002ae0  pop     r15
0x180002ae2  pop     r14
0x180002ae4  pop     r12
0x180002ae6  pop     rdi
0x180002ae7  pop     rsi
0x180002ae8  pop     rbx
0x180002ae9  pop     rbp
0x180002aea  retn
0x180002aec  lea     rcx, [rsp+1500h+var_14E0]; this
0x180002af1  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180002af7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
