# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180005f74`
- end: `0x18000621b`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `679`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180004d7c`

## callees

- `0x180005f74`
- `0x180006cd4`
- `0x180007b84`
- `0x1800082b0`
- `0x1800083d8`
- `0x180009e16`
- `0x180009e40`
- `0x180009ed0`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000601e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000601e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800061af`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800061af`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000611f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000611f`

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
0x180005f74  mov     [rsp-8+arg_10], rbx
0x180005f79  push    rbp
0x180005f7a  push    rsi
0x180005f7b  push    rdi
0x180005f7c  push    r14
0x180005f7e  push    r15
0x180005f80  lea     rbp, [rsp-13D0h]
0x180005f88  mov     eax, 14D0h
0x180005f8d  call    _alloca_probe
0x180005f92  sub     rsp, rax
0x180005f95  mov     rax, cs:__security_cookie
0x180005f9c  xor     rax, rsp
0x180005f9f  mov     [rbp+13F0h+var_30], rax
0x180005fa6  mov     rdi, [rbp+13F0h+arg_28]
0x180005fad  mov     esi, edx
0x180005faf  mov     r14, rcx
0x180005fb2  xor     edx, edx; Val
0x180005fb4  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180005fb9  mov     r8d, 98h; Size
0x180005fbf  call    memset_0
0x180005fc4  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180005fcb  xor     r15d, r15d
0x180005fce  mov     [rbp+13F0h+OutputString], r15w
0x180005fd6  mov     [rbp+13F0h+var_1430], r15b
0x180005fda  mov     ecx, [rdx]; this
0x180005fdc  mov     eax, [rdx+4]
0x180005fdf  mov     [rsp+14F0h+var_14C8], ecx
0x180005fe3  mov     [rsp+14F0h+var_14C4], eax
0x180005fe7  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005fec  cmp     dword ptr [rdx+8], 1
0x180005ff0  mov     ebx, eax
0x180005ff2  lea     eax, [r15+8]
0x180005ff6  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180005ffe  mov     ecx, r15d
0x180006001  cmovz   ecx, eax
0x180006004  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180006008  lea     ecx, [rax-7]
0x18000600b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180006013  inc     ecx
0x180006015  mov     [rsp+14F0h+var_14B8], r15
0x18000601a  mov     [rsp+14F0h+var_14C0], ecx
0x18000601e  call    cs:__imp_GetCurrentThreadId
0x180006025  nop     dword ptr [rax+rax+00h]
0x18000602a  xorps   xmm0, xmm0
0x18000602d  mov     [rsp+14F0h+var_1490], esi
0x180006031  mov     [rsp+14F0h+var_14B0], eax
0x180006035  xorps   xmm1, xmm1
0x180006038  lea     rax, aWil; "wil"
0x18000603f  mov     [rsp+14F0h+var_148C], ebx
0x180006043  mov     [rsp+14F0h+var_1498], rax
0x180006048  xor     eax, eax
0x18000604a  mov     [rbp+13F0h+var_1458], rax
0x18000604e  mov     [rbp+13F0h+var_1470], rax
0x180006052  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180006059  mov     [rsp+14F0h+var_14A8], r15
0x18000605e  mov     [rsp+14F0h+var_14A0], r15
0x180006063  mov     [rbp+13F0h+var_1448], rdi
0x180006067  mov     [rbp+13F0h+var_1440], r14
0x18000606b  mov     [rsp+14F0h+var_1488], r15
0x180006070  movups  [rbp+13F0h+var_1468], xmm0
0x180006074  movups  [rsp+14F0h+var_1480], xmm1
0x180006079  test    rax, rax
0x18000607c  jz      short loc_180006089
0x18000607e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006083  mov     [rbp+13F0h+var_1450], rax
0x180006087  jmp     short loc_18000608D
0x180006089  mov     [rbp+13F0h+var_1450], r15
0x18000608d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006094  test    rax, rax
0x180006097  jz      short loc_1800060A3
0x180006099  lea     rcx, [rsp+14F0h+var_14D0]
0x18000609e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060a3  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800060aa  test    rax, rax
0x1800060ad  jz      short loc_1800060C3
0x1800060af  mov     r8d, 400h
0x1800060b5  lea     rdx, [rbp+13F0h+var_1430]
0x1800060b9  lea     rcx, [rsp+14F0h+var_14D0]
0x1800060be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060c3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800060ca  test    rax, rax
0x1800060cd  jz      short loc_1800060D9
0x1800060cf  lea     rcx, [rsp+14F0h+var_14D0]
0x1800060d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060d9  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800060e0  test    rax, rax
0x1800060e3  jz      short loc_1800060F6
0x1800060e5  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800060ea  jnz     short loc_1800060F6
0x1800060ec  lea     rcx, [rsp+14F0h+var_14D0]
0x1800060f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060f6  cmp     [rsp+14F0h+var_14C8], r15d
0x1800060fb  jge     loc_18000620A
0x180006101  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180006108  jnz     short loc_18000612F
0x18000610a  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180006111  test    rax, rax
0x180006114  jz      short loc_18000611F
0x180006116  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000611b  test    al, al
0x18000611d  jmp     short loc_18000612D
0x18000611f  call    cs:__imp_IsDebuggerPresent
0x180006126  nop     dword ptr [rax+rax+00h]
0x18000612b  test    eax, eax
0x18000612d  jz      short loc_180006136
0x18000612f  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180006134  jz      short loc_18000615C
0x180006136  mov     rax, cs:g_pfnResultLoggingCallback
0x18000613d  test    rax, rax
0x180006140  jz      short loc_1800061BB
0x180006142  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180006149  jnz     short loc_1800061BB
0x18000614b  xor     r8d, r8d
0x18000614e  lea     rcx, [rsp+14F0h+var_14D0]
0x180006153  xor     edx, edx
0x180006155  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000615a  jmp     short loc_1800061BB
0x18000615c  mov     rax, cs:g_pfnResultLoggingCallback
0x180006163  mov     ebx, 800h
0x180006168  test    rax, rax
0x18000616b  jz      short loc_18000618A
0x18000616d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180006174  jnz     short loc_18000618A
0x180006176  mov     r8d, ebx
0x180006179  lea     rdx, [rbp+13F0h+OutputString]
0x180006180  lea     rcx, [rsp+14F0h+var_14D0]
0x180006185  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000618a  cmp     [rbp+13F0h+OutputString], r15w
0x180006192  jnz     short loc_1800061A8
0x180006194  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180006199  mov     rdx, rbx; unsigned __int16 *
0x18000619c  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800061a3  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800061a8  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800061af  call    cs:__imp_OutputDebugStringW
0x1800061b6  nop     dword ptr [rax+rax+00h]
0x1800061bb  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800061c0  jnz     short loc_1800061CB
0x1800061c2  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x1800061c9  jz      short loc_1800061DC
0x1800061cb  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800061d2  test    rax, rax
0x1800061d5  jz      short loc_1800061DC
0x1800061d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061dc  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x1800061e1  jnz     short loc_180006210
0x1800061e3  mov     rcx, [rbp+13F0h+var_30]
0x1800061ea  xor     rcx, rsp; StackCookie
0x1800061ed  call    __security_check_cookie
0x1800061f2  mov     rbx, [rsp+14F0h+arg_10]
0x1800061fa  add     rsp, 14D0h
0x180006201  pop     r15
0x180006203  pop     r14
0x180006205  pop     rdi
0x180006206  pop     rsi
0x180006207  pop     rbp
0x180006208  retn
0x18000620a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180006210  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180006215  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
