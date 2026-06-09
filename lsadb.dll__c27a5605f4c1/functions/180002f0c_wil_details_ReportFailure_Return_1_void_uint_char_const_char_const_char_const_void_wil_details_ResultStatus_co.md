# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180002f0c`
- end: `0x1800031a0`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800029ec`

## callees

- `0x180001670`
- `0x180001fb8`
- `0x180002f0c`
- `0x180004e14`
- `0x180006d44`
- `0x180008ab0`
- `0x180008c7c`
- `0x18003acd0`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002fb6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002fb6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800030b1`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800030b1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000313b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000313b`

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
0x180002f0c  mov     [rsp-8+arg_10], rbx
0x180002f11  push    rbp
0x180002f12  push    rsi
0x180002f13  push    rdi
0x180002f14  push    r14
0x180002f16  push    r15
0x180002f18  lea     rbp, [rsp-13D0h]
0x180002f20  mov     eax, 14D0h
0x180002f25  call    _alloca_probe
0x180002f2a  sub     rsp, rax
0x180002f2d  mov     rax, cs:__security_cookie
0x180002f34  xor     rax, rsp
0x180002f37  mov     [rbp+13F0h+var_30], rax
0x180002f3e  mov     rdi, [rbp+13F0h+arg_28]
0x180002f45  mov     esi, edx
0x180002f47  mov     r14, rcx
0x180002f4a  xor     edx, edx; Val
0x180002f4c  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180002f51  mov     r8d, 98h; Size
0x180002f57  call    memset_0
0x180002f5c  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180002f63  xor     r15d, r15d
0x180002f66  mov     [rbp+13F0h+OutputString], r15w
0x180002f6e  mov     [rbp+13F0h+var_1430], r15b
0x180002f72  mov     ecx, [rdx]; this
0x180002f74  mov     eax, [rdx+4]
0x180002f77  mov     [rsp+14F0h+var_14C8], ecx
0x180002f7b  mov     [rsp+14F0h+var_14C4], eax
0x180002f7f  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180002f84  cmp     dword ptr [rdx+8], 1
0x180002f88  mov     ebx, eax
0x180002f8a  lea     eax, [r15+8]
0x180002f8e  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180002f96  mov     ecx, r15d
0x180002f99  cmovz   ecx, eax
0x180002f9c  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180002fa0  lea     ecx, [rax-7]
0x180002fa3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002fab  inc     ecx
0x180002fad  mov     [rsp+14F0h+var_14B8], r15
0x180002fb2  mov     [rsp+14F0h+var_14C0], ecx
0x180002fb6  call    cs:__imp_GetCurrentThreadId
0x180002fbc  xorps   xmm0, xmm0
0x180002fbf  mov     [rsp+14F0h+var_1490], esi
0x180002fc3  mov     [rsp+14F0h+var_14B0], eax
0x180002fc7  xorps   xmm1, xmm1
0x180002fca  lea     rax, aWil; "wil"
0x180002fd1  mov     [rsp+14F0h+var_148C], ebx
0x180002fd5  mov     [rsp+14F0h+var_1498], rax
0x180002fda  xor     eax, eax
0x180002fdc  mov     [rbp+13F0h+var_1458], rax
0x180002fe0  mov     [rbp+13F0h+var_1470], rax
0x180002fe4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002feb  mov     [rsp+14F0h+var_14A8], r15
0x180002ff0  mov     [rsp+14F0h+var_14A0], r15
0x180002ff5  mov     [rbp+13F0h+var_1448], rdi
0x180002ff9  mov     [rbp+13F0h+var_1440], r14
0x180002ffd  mov     [rsp+14F0h+var_1488], r15
0x180003002  movups  [rbp+13F0h+var_1468], xmm0
0x180003006  movups  [rsp+14F0h+var_1480], xmm1
0x18000300b  test    rax, rax
0x18000300e  jz      short loc_18000301B
0x180003010  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003015  mov     [rbp+13F0h+var_1450], rax
0x180003019  jmp     short loc_18000301F
0x18000301b  mov     [rbp+13F0h+var_1450], r15
0x18000301f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003026  test    rax, rax
0x180003029  jz      short loc_180003035
0x18000302b  lea     rcx, [rsp+14F0h+var_14D0]
0x180003030  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003035  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000303c  test    rax, rax
0x18000303f  jz      short loc_180003055
0x180003041  mov     r8d, 400h
0x180003047  lea     rdx, [rbp+13F0h+var_1430]
0x18000304b  lea     rcx, [rsp+14F0h+var_14D0]
0x180003050  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003055  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000305c  test    rax, rax
0x18000305f  jz      short loc_18000306B
0x180003061  lea     rcx, [rsp+14F0h+var_14D0]
0x180003066  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000306b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003072  test    rax, rax
0x180003075  jz      short loc_180003088
0x180003077  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000307c  jnz     short loc_180003088
0x18000307e  lea     rcx, [rsp+14F0h+var_14D0]
0x180003083  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003088  cmp     [rsp+14F0h+var_14C8], r15d
0x18000308d  jge     loc_18000318F
0x180003093  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18000309a  jnz     short loc_1800030BB
0x18000309c  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800030a3  test    rax, rax
0x1800030a6  jz      short loc_1800030B1
0x1800030a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030ad  test    al, al
0x1800030af  jmp     short loc_1800030B9
0x1800030b1  call    cs:__imp_IsDebuggerPresent
0x1800030b7  test    eax, eax
0x1800030b9  jz      short loc_1800030C2
0x1800030bb  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800030c0  jz      short loc_1800030E8
0x1800030c2  mov     rax, cs:g_pfnResultLoggingCallback
0x1800030c9  test    rax, rax
0x1800030cc  jz      short loc_180003141
0x1800030ce  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800030d5  jnz     short loc_180003141
0x1800030d7  xor     r8d, r8d
0x1800030da  lea     rcx, [rsp+14F0h+var_14D0]
0x1800030df  xor     edx, edx
0x1800030e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030e6  jmp     short loc_180003141
0x1800030e8  mov     rax, cs:g_pfnResultLoggingCallback
0x1800030ef  mov     ebx, 800h
0x1800030f4  test    rax, rax
0x1800030f7  jz      short loc_180003116
0x1800030f9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180003100  jnz     short loc_180003116
0x180003102  mov     r8d, ebx
0x180003105  lea     rdx, [rbp+13F0h+OutputString]
0x18000310c  lea     rcx, [rsp+14F0h+var_14D0]
0x180003111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003116  cmp     [rbp+13F0h+OutputString], r15w
0x18000311e  jnz     short loc_180003134
0x180003120  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180003125  mov     rdx, rbx; unsigned __int16 *
0x180003128  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000312f  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003134  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000313b  call    cs:__imp_OutputDebugStringW
0x180003141  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180003146  jnz     short loc_180003151
0x180003148  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18000314f  jz      short loc_180003162
0x180003151  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003158  test    rax, rax
0x18000315b  jz      short loc_180003162
0x18000315d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003162  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180003167  jnz     short loc_180003195
0x180003169  mov     rcx, [rbp+13F0h+var_30]
0x180003170  xor     rcx, rsp; StackCookie
0x180003173  call    __security_check_cookie
0x180003178  mov     rbx, [rsp+14F0h+arg_10]
0x180003180  add     rsp, 14D0h
0x180003187  pop     r15
0x180003189  pop     r14
0x18000318b  pop     rdi
0x18000318c  pop     rsi
0x18000318d  pop     rbp
0x18000318e  retn
0x18000318f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003195  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000319a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
