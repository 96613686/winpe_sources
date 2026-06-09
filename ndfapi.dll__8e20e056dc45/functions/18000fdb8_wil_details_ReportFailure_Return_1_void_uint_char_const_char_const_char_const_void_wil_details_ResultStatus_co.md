# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000fdb8`
- end: `0x18001004e`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000fd5c`

## callees

- `0x180002f94`
- `0x180009894`
- `0x180009c50`
- `0x180009efc`
- `0x18000fdb8`
- `0x18001f652`
- `0x18001f690`
- `0x18001f750`
- `0x180021010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000fe63`
- `KERNEL32!GetCurrentThreadId` at `0x18000fe63`
- `KERNEL32!OutputDebugStringW` at `0x18000ffe8`
- `KERNEL32!OutputDebugStringW` at `0x18000ffe8`
- `KERNEL32!IsDebuggerPresent` at `0x18000ff5e`
- `KERNEL32!IsDebuggerPresent` at `0x18000ff5e`

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
  v25 = "net\\diagnostics\\netdiagfx\\ndfapi\\diagnosemsgbox.cpp";
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
0x18000fdb8  mov     [rsp-8+arg_10], rbx
0x18000fdbd  push    rbp
0x18000fdbe  push    rsi
0x18000fdbf  push    rdi
0x18000fdc0  push    r14
0x18000fdc2  push    r15
0x18000fdc4  lea     rbp, [rsp-13D0h]
0x18000fdcc  mov     eax, 14D0h
0x18000fdd1  call    _alloca_probe
0x18000fdd6  sub     rsp, rax
0x18000fdd9  mov     rax, cs:__security_cookie
0x18000fde0  xor     rax, rsp
0x18000fde3  mov     [rbp+13F0h+var_30], rax
0x18000fdea  mov     esi, edx
0x18000fdec  mov     r14, rcx
0x18000fdef  mov     rdi, [rbp+13F0h+arg_28]
0x18000fdf6  xor     edx, edx; Val
0x18000fdf8  mov     r8d, 98h; Size
0x18000fdfe  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000fe03  call    memset_0
0x18000fe08  nop
0x18000fe09  xor     r15d, r15d
0x18000fe0c  mov     [rbp+13F0h+OutputString], r15w
0x18000fe14  mov     [rbp+13F0h+var_1430], r15b
0x18000fe18  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18000fe1f  mov     ecx, [rdx]; this
0x18000fe21  mov     [rsp+14F0h+var_14C8], ecx
0x18000fe25  mov     eax, [rdx+4]
0x18000fe28  mov     [rsp+14F0h+var_14C4], eax
0x18000fe2c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000fe31  mov     ebx, eax
0x18000fe33  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x18000fe3b  mov     ecx, r15d
0x18000fe3e  lea     eax, [r15+8]
0x18000fe42  cmp     dword ptr [rdx+8], 1
0x18000fe46  cmovz   ecx, eax
0x18000fe49  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000fe4d  lea     ecx, [rax-7]
0x18000fe50  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000fe58  inc     ecx
0x18000fe5a  mov     [rsp+14F0h+var_14C0], ecx
0x18000fe5e  mov     [rsp+14F0h+var_14B8], r15
0x18000fe63  call    cs:__imp_GetCurrentThreadId
0x18000fe69  mov     [rsp+14F0h+var_14B0], eax
0x18000fe6d  lea     rax, aNetDiagnostics_0; "net\\diagnostics\\netdiagfx\\ndfapi\\di"...
0x18000fe74  mov     [rsp+14F0h+var_1498], rax
0x18000fe79  mov     [rsp+14F0h+var_1490], esi
0x18000fe7d  mov     [rsp+14F0h+var_148C], ebx
0x18000fe81  mov     [rsp+14F0h+var_14A8], r15
0x18000fe86  mov     [rsp+14F0h+var_14A0], r15
0x18000fe8b  mov     [rbp+13F0h+var_1448], rdi
0x18000fe8f  mov     [rbp+13F0h+var_1440], r14
0x18000fe93  mov     [rsp+14F0h+var_1488], r15
0x18000fe98  xorps   xmm0, xmm0
0x18000fe9b  xor     eax, eax
0x18000fe9d  movups  [rbp+13F0h+var_1468], xmm0
0x18000fea1  mov     [rbp+13F0h+var_1458], rax
0x18000fea5  xorps   xmm1, xmm1
0x18000fea8  movups  [rsp+14F0h+var_1480], xmm1
0x18000fead  mov     [rbp+13F0h+var_1470], rax
0x18000feb1  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000feb8  test    rax, rax
0x18000febb  jz      short loc_18000FEC8
0x18000febd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fec2  mov     [rbp+13F0h+var_1450], rax
0x18000fec6  jmp     short loc_18000FECC
0x18000fec8  mov     [rbp+13F0h+var_1450], r15
0x18000fecc  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000fed3  test    rax, rax
0x18000fed6  jz      short loc_18000FEE2
0x18000fed8  lea     rcx, [rsp+14F0h+var_14D0]
0x18000fedd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fee2  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000fee9  test    rax, rax
0x18000feec  jz      short loc_18000FF02
0x18000feee  mov     r8d, 400h
0x18000fef4  lea     rdx, [rbp+13F0h+var_1430]
0x18000fef8  lea     rcx, [rsp+14F0h+var_14D0]
0x18000fefd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff02  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000ff09  test    rax, rax
0x18000ff0c  jz      short loc_18000FF18
0x18000ff0e  lea     rcx, [rsp+14F0h+var_14D0]
0x18000ff13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff18  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000ff1f  test    rax, rax
0x18000ff22  jz      short loc_18000FF35
0x18000ff24  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000ff29  jnz     short loc_18000FF35
0x18000ff2b  lea     rcx, [rsp+14F0h+var_14D0]
0x18000ff30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff35  cmp     [rsp+14F0h+var_14C8], r15d
0x18000ff3a  jge     loc_180010048
0x18000ff40  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18000ff47  jnz     short loc_18000FF68
0x18000ff49  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000ff50  test    rax, rax
0x18000ff53  jz      short loc_18000FF5E
0x18000ff55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff5a  test    al, al
0x18000ff5c  jmp     short loc_18000FF66
0x18000ff5e  call    cs:__imp_IsDebuggerPresent
0x18000ff64  test    eax, eax
0x18000ff66  jz      short loc_18000FF6F
0x18000ff68  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000ff6d  jz      short loc_18000FF95
0x18000ff6f  mov     rax, cs:g_pfnResultLoggingCallback
0x18000ff76  test    rax, rax
0x18000ff79  jz      short loc_18000FFEE
0x18000ff7b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000ff82  jnz     short loc_18000FFEE
0x18000ff84  xor     r8d, r8d
0x18000ff87  xor     edx, edx
0x18000ff89  lea     rcx, [rsp+14F0h+var_14D0]
0x18000ff8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff93  jmp     short loc_18000FFEE
0x18000ff95  mov     ebx, 800h
0x18000ff9a  mov     rax, cs:g_pfnResultLoggingCallback
0x18000ffa1  test    rax, rax
0x18000ffa4  jz      short loc_18000FFC3
0x18000ffa6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000ffad  jnz     short loc_18000FFC3
0x18000ffaf  mov     r8d, ebx
0x18000ffb2  lea     rdx, [rbp+13F0h+OutputString]
0x18000ffb9  lea     rcx, [rsp+14F0h+var_14D0]
0x18000ffbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffc3  cmp     [rbp+13F0h+OutputString], r15w
0x18000ffcb  jnz     short loc_18000FFE1
0x18000ffcd  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000ffd2  mov     rdx, rbx; unsigned __int16 *
0x18000ffd5  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000ffdc  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000ffe1  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000ffe8  call    cs:__imp_OutputDebugStringW
0x18000ffee  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000fff3  jnz     short loc_18000FFFE
0x18000fff5  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18000fffc  jz      short loc_180010010
0x18000fffe  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180010005  test    rax, rax
0x180010008  jz      short loc_180010010
0x18001000a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001000f  nop
0x180010010  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180010015  jnz     short loc_18001003D
0x180010017  mov     rcx, [rbp+13F0h+var_30]
0x18001001e  xor     rcx, rsp; StackCookie
0x180010021  call    __security_check_cookie
0x180010026  mov     rbx, [rsp+14F0h+arg_10]
0x18001002e  add     rsp, 14D0h
0x180010035  pop     r15
0x180010037  pop     r14
0x180010039  pop     rdi
0x18001003a  pop     rsi
0x18001003b  pop     rbp
0x18001003c  retn
0x18001003d  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180010042  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180010048  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
