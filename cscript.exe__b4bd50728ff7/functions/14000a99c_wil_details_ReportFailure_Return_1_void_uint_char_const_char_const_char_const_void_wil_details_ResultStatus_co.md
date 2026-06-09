# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x14000a99c`
- end: `0x14000ac30`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x14000a4a4`

## callees

- `0x14000a99c`
- `0x14000b49c`
- `0x14000c1a0`
- `0x14000c8b4`
- `0x14000c9c4`
- `0x14001619a`
- `0x1400161d0`
- `0x140016200`
- `0x140017010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14000aa46`
- `KERNEL32!GetCurrentThreadId` at `0x14000aa46`
- `KERNEL32!OutputDebugStringW` at `0x14000abcb`
- `KERNEL32!OutputDebugStringW` at `0x14000abcb`
- `KERNEL32!IsDebuggerPresent` at `0x14000ab41`
- `KERNEL32!IsDebuggerPresent` at `0x14000ab41`

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
0x14000a99c  mov     [rsp-8+arg_10], rbx
0x14000a9a1  push    rbp
0x14000a9a2  push    rsi
0x14000a9a3  push    rdi
0x14000a9a4  push    r14
0x14000a9a6  push    r15
0x14000a9a8  lea     rbp, [rsp-13D0h]
0x14000a9b0  mov     eax, 14D0h
0x14000a9b5  call    _alloca_probe
0x14000a9ba  sub     rsp, rax
0x14000a9bd  mov     rax, cs:__security_cookie
0x14000a9c4  xor     rax, rsp
0x14000a9c7  mov     [rbp+13F0h+var_30], rax
0x14000a9ce  mov     rdi, [rbp+13F0h+arg_28]
0x14000a9d5  mov     esi, edx
0x14000a9d7  mov     r14, rcx
0x14000a9da  xor     edx, edx; Val
0x14000a9dc  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x14000a9e1  mov     r8d, 98h; Size
0x14000a9e7  call    memset_0
0x14000a9ec  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x14000a9f3  xor     r15d, r15d
0x14000a9f6  mov     [rbp+13F0h+OutputString], r15w
0x14000a9fe  mov     [rbp+13F0h+var_1430], r15b
0x14000aa02  mov     ecx, [rdx]; this
0x14000aa04  mov     eax, [rdx+4]
0x14000aa07  mov     [rsp+14F0h+var_14C8], ecx
0x14000aa0b  mov     [rsp+14F0h+var_14C4], eax
0x14000aa0f  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x14000aa14  cmp     dword ptr [rdx+8], 1
0x14000aa18  mov     ebx, eax
0x14000aa1a  lea     eax, [r15+8]
0x14000aa1e  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x14000aa26  mov     ecx, r15d
0x14000aa29  cmovz   ecx, eax
0x14000aa2c  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x14000aa30  lea     ecx, [rax-7]
0x14000aa33  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000aa3b  inc     ecx
0x14000aa3d  mov     [rsp+14F0h+var_14B8], r15
0x14000aa42  mov     [rsp+14F0h+var_14C0], ecx
0x14000aa46  call    cs:__imp_GetCurrentThreadId
0x14000aa4c  xorps   xmm0, xmm0
0x14000aa4f  mov     [rsp+14F0h+var_1490], esi
0x14000aa53  mov     [rsp+14F0h+var_14B0], eax
0x14000aa57  xorps   xmm1, xmm1
0x14000aa5a  lea     rax, aWil; "wil"
0x14000aa61  mov     [rsp+14F0h+var_148C], ebx
0x14000aa65  mov     [rsp+14F0h+var_1498], rax
0x14000aa6a  xor     eax, eax
0x14000aa6c  mov     [rbp+13F0h+var_1458], rax
0x14000aa70  mov     [rbp+13F0h+var_1470], rax
0x14000aa74  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000aa7b  mov     [rsp+14F0h+var_14A8], r15
0x14000aa80  mov     [rsp+14F0h+var_14A0], r15
0x14000aa85  mov     [rbp+13F0h+var_1448], rdi
0x14000aa89  mov     [rbp+13F0h+var_1440], r14
0x14000aa8d  mov     [rsp+14F0h+var_1488], r15
0x14000aa92  movups  [rbp+13F0h+var_1468], xmm0
0x14000aa96  movups  [rsp+14F0h+var_1480], xmm1
0x14000aa9b  test    rax, rax
0x14000aa9e  jz      short loc_14000AAAB
0x14000aaa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aaa5  mov     [rbp+13F0h+var_1450], rax
0x14000aaa9  jmp     short loc_14000AAAF
0x14000aaab  mov     [rbp+13F0h+var_1450], r15
0x14000aaaf  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14000aab6  test    rax, rax
0x14000aab9  jz      short loc_14000AAC5
0x14000aabb  lea     rcx, [rsp+14F0h+var_14D0]
0x14000aac0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aac5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000aacc  test    rax, rax
0x14000aacf  jz      short loc_14000AAE5
0x14000aad1  mov     r8d, 400h
0x14000aad7  lea     rdx, [rbp+13F0h+var_1430]
0x14000aadb  lea     rcx, [rsp+14F0h+var_14D0]
0x14000aae0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aae5  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000aaec  test    rax, rax
0x14000aaef  jz      short loc_14000AAFB
0x14000aaf1  lea     rcx, [rsp+14F0h+var_14D0]
0x14000aaf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aafb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000ab02  test    rax, rax
0x14000ab05  jz      short loc_14000AB18
0x14000ab07  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x14000ab0c  jnz     short loc_14000AB18
0x14000ab0e  lea     rcx, [rsp+14F0h+var_14D0]
0x14000ab13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ab18  cmp     [rsp+14F0h+var_14C8], r15d
0x14000ab1d  jge     loc_14000AC1F
0x14000ab23  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x14000ab2a  jnz     short loc_14000AB4B
0x14000ab2c  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14000ab33  test    rax, rax
0x14000ab36  jz      short loc_14000AB41
0x14000ab38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ab3d  test    al, al
0x14000ab3f  jmp     short loc_14000AB49
0x14000ab41  call    cs:__imp_IsDebuggerPresent
0x14000ab47  test    eax, eax
0x14000ab49  jz      short loc_14000AB52
0x14000ab4b  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x14000ab50  jz      short loc_14000AB78
0x14000ab52  mov     rax, cs:g_pfnResultLoggingCallback
0x14000ab59  test    rax, rax
0x14000ab5c  jz      short loc_14000ABD1
0x14000ab5e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14000ab65  jnz     short loc_14000ABD1
0x14000ab67  xor     r8d, r8d
0x14000ab6a  lea     rcx, [rsp+14F0h+var_14D0]
0x14000ab6f  xor     edx, edx
0x14000ab71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ab76  jmp     short loc_14000ABD1
0x14000ab78  mov     rax, cs:g_pfnResultLoggingCallback
0x14000ab7f  mov     ebx, 800h
0x14000ab84  test    rax, rax
0x14000ab87  jz      short loc_14000ABA6
0x14000ab89  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14000ab90  jnz     short loc_14000ABA6
0x14000ab92  mov     r8d, ebx
0x14000ab95  lea     rdx, [rbp+13F0h+OutputString]
0x14000ab9c  lea     rcx, [rsp+14F0h+var_14D0]
0x14000aba1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aba6  cmp     [rbp+13F0h+OutputString], r15w
0x14000abae  jnz     short loc_14000ABC4
0x14000abb0  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x14000abb5  mov     rdx, rbx; unsigned __int16 *
0x14000abb8  lea     rcx, [rbp+13F0h+OutputString]; this
0x14000abbf  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14000abc4  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x14000abcb  call    cs:__imp_OutputDebugStringW
0x14000abd1  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x14000abd6  jnz     short loc_14000ABE1
0x14000abd8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x14000abdf  jz      short loc_14000ABF2
0x14000abe1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14000abe8  test    rax, rax
0x14000abeb  jz      short loc_14000ABF2
0x14000abed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000abf2  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x14000abf7  jnz     short loc_14000AC25
0x14000abf9  mov     rcx, [rbp+13F0h+var_30]
0x14000ac00  xor     rcx, rsp; StackCookie
0x14000ac03  call    __security_check_cookie
0x14000ac08  mov     rbx, [rsp+14F0h+arg_10]
0x14000ac10  add     rsp, 14D0h
0x14000ac17  pop     r15
0x14000ac19  pop     r14
0x14000ac1b  pop     rdi
0x14000ac1c  pop     rsi
0x14000ac1d  pop     rbp
0x14000ac1e  retn
0x14000ac1f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14000ac25  lea     rcx, [rsp+14F0h+var_14D0]; this
0x14000ac2a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
