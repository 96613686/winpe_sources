# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180002904`
- end: `0x180002b9a`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000240c`

## callees

- `0x180002904`
- `0x1800041c4`
- `0x180005b20`
- `0x1800073d0`
- `0x18000766c`
- `0x180035b02`
- `0x180035b40`
- `0x180035c00`
- `0x180037010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800029af`
- `KERNEL32!GetCurrentThreadId` at `0x1800029af`
- `KERNEL32!OutputDebugStringW` at `0x180002b34`
- `KERNEL32!OutputDebugStringW` at `0x180002b34`
- `KERNEL32!IsDebuggerPresent` at `0x180002aaa`
- `KERNEL32!IsDebuggerPresent` at `0x180002aaa`

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
0x180002904  mov     [rsp-8+arg_10], rbx
0x180002909  push    rbp
0x18000290a  push    rsi
0x18000290b  push    rdi
0x18000290c  push    r14
0x18000290e  push    r15
0x180002910  lea     rbp, [rsp-13D0h]
0x180002918  mov     eax, 14D0h
0x18000291d  call    _alloca_probe
0x180002922  sub     rsp, rax
0x180002925  mov     rax, cs:__security_cookie
0x18000292c  xor     rax, rsp
0x18000292f  mov     [rbp+13F0h+var_30], rax
0x180002936  mov     esi, edx
0x180002938  mov     r14, rcx
0x18000293b  mov     rdi, [rbp+13F0h+arg_28]
0x180002942  xor     edx, edx; Val
0x180002944  mov     r8d, 98h; Size
0x18000294a  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000294f  call    memset_0
0x180002954  nop
0x180002955  xor     r15d, r15d
0x180002958  mov     [rbp+13F0h+OutputString], r15w
0x180002960  mov     [rbp+13F0h+var_1430], r15b
0x180002964  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18000296b  mov     ecx, [rdx]; this
0x18000296d  mov     [rsp+14F0h+var_14C8], ecx
0x180002971  mov     eax, [rdx+4]
0x180002974  mov     [rsp+14F0h+var_14C4], eax
0x180002978  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000297d  mov     ebx, eax
0x18000297f  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180002987  mov     ecx, r15d
0x18000298a  lea     eax, [r15+8]
0x18000298e  cmp     dword ptr [rdx+8], 1
0x180002992  cmovz   ecx, eax
0x180002995  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180002999  lea     ecx, [rax-7]
0x18000299c  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800029a4  inc     ecx
0x1800029a6  mov     [rsp+14F0h+var_14C0], ecx
0x1800029aa  mov     [rsp+14F0h+var_14B8], r15
0x1800029af  call    cs:__imp_GetCurrentThreadId
0x1800029b5  mov     [rsp+14F0h+var_14B0], eax
0x1800029b9  lea     rax, aWil; "wil"
0x1800029c0  mov     [rsp+14F0h+var_1498], rax
0x1800029c5  mov     [rsp+14F0h+var_1490], esi
0x1800029c9  mov     [rsp+14F0h+var_148C], ebx
0x1800029cd  mov     [rsp+14F0h+var_14A8], r15
0x1800029d2  mov     [rsp+14F0h+var_14A0], r15
0x1800029d7  mov     [rbp+13F0h+var_1448], rdi
0x1800029db  mov     [rbp+13F0h+var_1440], r14
0x1800029df  mov     [rsp+14F0h+var_1488], r15
0x1800029e4  xorps   xmm0, xmm0
0x1800029e7  xor     eax, eax
0x1800029e9  movups  [rbp+13F0h+var_1468], xmm0
0x1800029ed  mov     [rbp+13F0h+var_1458], rax
0x1800029f1  xorps   xmm1, xmm1
0x1800029f4  movups  [rsp+14F0h+var_1480], xmm1
0x1800029f9  mov     [rbp+13F0h+var_1470], rax
0x1800029fd  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002a04  test    rax, rax
0x180002a07  jz      short loc_180002A14
0x180002a09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a0e  mov     [rbp+13F0h+var_1450], rax
0x180002a12  jmp     short loc_180002A18
0x180002a14  mov     [rbp+13F0h+var_1450], r15
0x180002a18  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002a1f  test    rax, rax
0x180002a22  jz      short loc_180002A2E
0x180002a24  lea     rcx, [rsp+14F0h+var_14D0]
0x180002a29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a2e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002a35  test    rax, rax
0x180002a38  jz      short loc_180002A4E
0x180002a3a  mov     r8d, 400h
0x180002a40  lea     rdx, [rbp+13F0h+var_1430]
0x180002a44  lea     rcx, [rsp+14F0h+var_14D0]
0x180002a49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a4e  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002a55  test    rax, rax
0x180002a58  jz      short loc_180002A64
0x180002a5a  lea     rcx, [rsp+14F0h+var_14D0]
0x180002a5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a64  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002a6b  test    rax, rax
0x180002a6e  jz      short loc_180002A81
0x180002a70  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002a75  jnz     short loc_180002A81
0x180002a77  lea     rcx, [rsp+14F0h+var_14D0]
0x180002a7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a81  cmp     [rsp+14F0h+var_14C8], r15d
0x180002a86  jge     loc_180002B94
0x180002a8c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180002a93  jnz     short loc_180002AB4
0x180002a95  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002a9c  test    rax, rax
0x180002a9f  jz      short loc_180002AAA
0x180002aa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002aa6  test    al, al
0x180002aa8  jmp     short loc_180002AB2
0x180002aaa  call    cs:__imp_IsDebuggerPresent
0x180002ab0  test    eax, eax
0x180002ab2  jz      short loc_180002ABB
0x180002ab4  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002ab9  jz      short loc_180002AE1
0x180002abb  mov     rax, cs:g_pfnResultLoggingCallback
0x180002ac2  test    rax, rax
0x180002ac5  jz      short loc_180002B3A
0x180002ac7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180002ace  jnz     short loc_180002B3A
0x180002ad0  xor     r8d, r8d
0x180002ad3  xor     edx, edx
0x180002ad5  lea     rcx, [rsp+14F0h+var_14D0]
0x180002ada  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002adf  jmp     short loc_180002B3A
0x180002ae1  mov     ebx, 800h
0x180002ae6  mov     rax, cs:g_pfnResultLoggingCallback
0x180002aed  test    rax, rax
0x180002af0  jz      short loc_180002B0F
0x180002af2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180002af9  jnz     short loc_180002B0F
0x180002afb  mov     r8d, ebx
0x180002afe  lea     rdx, [rbp+13F0h+OutputString]
0x180002b05  lea     rcx, [rsp+14F0h+var_14D0]
0x180002b0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b0f  cmp     [rbp+13F0h+OutputString], r15w
0x180002b17  jnz     short loc_180002B2D
0x180002b19  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180002b1e  mov     rdx, rbx; unsigned __int16 *
0x180002b21  lea     rcx, [rbp+13F0h+OutputString]; this
0x180002b28  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002b2d  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180002b34  call    cs:__imp_OutputDebugStringW
0x180002b3a  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180002b3f  jnz     short loc_180002B4A
0x180002b41  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180002b48  jz      short loc_180002B5C
0x180002b4a  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002b51  test    rax, rax
0x180002b54  jz      short loc_180002B5C
0x180002b56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b5b  nop
0x180002b5c  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180002b61  jnz     short loc_180002B89
0x180002b63  mov     rcx, [rbp+13F0h+var_30]
0x180002b6a  xor     rcx, rsp; StackCookie
0x180002b6d  call    __security_check_cookie
0x180002b72  mov     rbx, [rsp+14F0h+arg_10]
0x180002b7a  add     rsp, 14D0h
0x180002b81  pop     r15
0x180002b83  pop     r14
0x180002b85  pop     rdi
0x180002b86  pop     rsi
0x180002b87  pop     rbp
0x180002b88  retn
0x180002b89  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180002b8e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180002b94  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
