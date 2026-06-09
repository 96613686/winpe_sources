# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180005cd0`
- end: `0x180005f77`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `679`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800057c0`

## callees

- `0x180005665`
- `0x180005cd0`
- `0x180009574`
- `0x18000bcc4`
- `0x18000e57c`
- `0x18000e748`
- `0x1800a0fb0`
- `0x1800a1070`
- `0x1800a5010`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x180005f0b`
- `KERNEL32!OutputDebugStringW` at `0x180005f0b`
- `KERNEL32!IsDebuggerPresent` at `0x180005e7b`
- `KERNEL32!IsDebuggerPresent` at `0x180005e7b`
- `KERNEL32!GetCurrentThreadId` at `0x180005d7a`
- `KERNEL32!GetCurrentThreadId` at `0x180005d7a`

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
0x180005cd0  mov     [rsp-8+arg_10], rbx
0x180005cd5  push    rbp
0x180005cd6  push    rsi
0x180005cd7  push    rdi
0x180005cd8  push    r14
0x180005cda  push    r15
0x180005cdc  lea     rbp, [rsp-13D0h]
0x180005ce4  mov     eax, 14D0h
0x180005ce9  call    _alloca_probe
0x180005cee  sub     rsp, rax
0x180005cf1  mov     rax, cs:__security_cookie
0x180005cf8  xor     rax, rsp
0x180005cfb  mov     [rbp+13F0h+var_30], rax
0x180005d02  mov     rdi, [rbp+13F0h+arg_28]
0x180005d09  mov     esi, edx
0x180005d0b  mov     r14, rcx
0x180005d0e  xor     edx, edx; Val
0x180005d10  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180005d15  mov     r8d, 98h; Size
0x180005d1b  call    memset_0
0x180005d20  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180005d27  xor     r15d, r15d
0x180005d2a  mov     [rbp+13F0h+OutputString], r15w
0x180005d32  mov     [rbp+13F0h+var_1430], r15b
0x180005d36  mov     ecx, [rdx]; this
0x180005d38  mov     eax, [rdx+4]
0x180005d3b  mov     [rsp+14F0h+var_14C8], ecx
0x180005d3f  mov     [rsp+14F0h+var_14C4], eax
0x180005d43  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005d48  cmp     dword ptr [rdx+8], 1
0x180005d4c  mov     ebx, eax
0x180005d4e  lea     eax, [r15+8]
0x180005d52  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180005d5a  mov     ecx, r15d
0x180005d5d  cmovz   ecx, eax
0x180005d60  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180005d64  lea     ecx, [rax-7]
0x180005d67  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)'::`2'::s_failureId
0x180005d6f  inc     ecx
0x180005d71  mov     [rsp+14F0h+var_14B8], r15
0x180005d76  mov     [rsp+14F0h+var_14C0], ecx
0x180005d7a  call    cs:__imp_GetCurrentThreadId
0x180005d81  nop     dword ptr [rax+rax+00h]
0x180005d86  xorps   xmm0, xmm0
0x180005d89  mov     [rsp+14F0h+var_1490], esi
0x180005d8d  mov     [rsp+14F0h+var_14B0], eax
0x180005d91  xorps   xmm1, xmm1
0x180005d94  lea     rax, aWil; "wil"
0x180005d9b  mov     [rsp+14F0h+var_148C], ebx
0x180005d9f  mov     [rsp+14F0h+var_1498], rax
0x180005da4  xor     eax, eax
0x180005da6  mov     [rbp+13F0h+var_1458], rax
0x180005daa  mov     [rbp+13F0h+var_1470], rax
0x180005dae  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005db5  mov     [rsp+14F0h+var_14A8], r15
0x180005dba  mov     [rsp+14F0h+var_14A0], r15
0x180005dbf  mov     [rbp+13F0h+var_1448], rdi
0x180005dc3  mov     [rbp+13F0h+var_1440], r14
0x180005dc7  mov     [rsp+14F0h+var_1488], r15
0x180005dcc  movups  [rbp+13F0h+var_1468], xmm0
0x180005dd0  movups  [rsp+14F0h+var_1480], xmm1
0x180005dd5  test    rax, rax
0x180005dd8  jz      short loc_180005DE5
0x180005dda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ddf  mov     [rbp+13F0h+var_1450], rax
0x180005de3  jmp     short loc_180005DE9
0x180005de5  mov     [rbp+13F0h+var_1450], r15
0x180005de9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005df0  test    rax, rax
0x180005df3  jz      short loc_180005DFF
0x180005df5  lea     rcx, [rsp+14F0h+var_14D0]
0x180005dfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005dff  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005e06  test    rax, rax
0x180005e09  jz      short loc_180005E1F
0x180005e0b  mov     r8d, 400h
0x180005e11  lea     rdx, [rbp+13F0h+var_1430]
0x180005e15  lea     rcx, [rsp+14F0h+var_14D0]
0x180005e1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e1f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005e26  test    rax, rax
0x180005e29  jz      short loc_180005E35
0x180005e2b  lea     rcx, [rsp+14F0h+var_14D0]
0x180005e30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e35  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005e3c  test    rax, rax
0x180005e3f  jz      short loc_180005E52
0x180005e41  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180005e46  jnz     short loc_180005E52
0x180005e48  lea     rcx, [rsp+14F0h+var_14D0]
0x180005e4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e52  cmp     [rsp+14F0h+var_14C8], r15d
0x180005e57  jge     loc_180005F66
0x180005e5d  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180005e64  jnz     short loc_180005E8B
0x180005e66  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005e6d  test    rax, rax
0x180005e70  jz      short loc_180005E7B
0x180005e72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e77  test    al, al
0x180005e79  jmp     short loc_180005E89
0x180005e7b  call    cs:__imp_IsDebuggerPresent
0x180005e82  nop     dword ptr [rax+rax+00h]
0x180005e87  test    eax, eax
0x180005e89  jz      short loc_180005E92
0x180005e8b  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180005e90  jz      short loc_180005EB8
0x180005e92  mov     rax, cs:g_pfnResultLoggingCallback
0x180005e99  test    rax, rax
0x180005e9c  jz      short loc_180005F17
0x180005e9e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180005ea5  jnz     short loc_180005F17
0x180005ea7  xor     r8d, r8d
0x180005eaa  lea     rcx, [rsp+14F0h+var_14D0]
0x180005eaf  xor     edx, edx
0x180005eb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005eb6  jmp     short loc_180005F17
0x180005eb8  mov     rax, cs:g_pfnResultLoggingCallback
0x180005ebf  mov     ebx, 800h
0x180005ec4  test    rax, rax
0x180005ec7  jz      short loc_180005EE6
0x180005ec9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180005ed0  jnz     short loc_180005EE6
0x180005ed2  mov     r8d, ebx
0x180005ed5  lea     rdx, [rbp+13F0h+OutputString]
0x180005edc  lea     rcx, [rsp+14F0h+var_14D0]
0x180005ee1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ee6  cmp     [rbp+13F0h+OutputString], r15w
0x180005eee  jnz     short loc_180005F04
0x180005ef0  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180005ef5  mov     rdx, rbx; unsigned __int16 *
0x180005ef8  lea     rcx, [rbp+13F0h+OutputString]; this
0x180005eff  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005f04  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180005f0b  call    cs:__imp_OutputDebugStringW
0x180005f12  nop     dword ptr [rax+rax+00h]
0x180005f17  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180005f1c  jnz     short loc_180005F27
0x180005f1e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180005f25  jz      short loc_180005F38
0x180005f27  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005f2e  test    rax, rax
0x180005f31  jz      short loc_180005F38
0x180005f33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f38  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180005f3d  jnz     short loc_180005F6C
0x180005f3f  mov     rcx, [rbp+13F0h+var_30]
0x180005f46  xor     rcx, rsp; StackCookie
0x180005f49  call    __security_check_cookie
0x180005f4e  mov     rbx, [rsp+14F0h+arg_10]
0x180005f56  add     rsp, 14D0h
0x180005f5d  pop     r15
0x180005f5f  pop     r14
0x180005f61  pop     rdi
0x180005f62  pop     rsi
0x180005f63  pop     rbp
0x180005f64  retn
0x180005f66  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180005f6c  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180005f71  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
