# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180031988`
- end: `0x180031c1c`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180031650`

## callees

- `0x180031988`
- `0x180032fa4`
- `0x18003493c`
- `0x180035fe8`
- `0x1800361f8`
- `0x1800375ee`
- `0x180037620`
- `0x1800376e0`
- `0x180039010`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x180031bb7`
- `KERNEL32!OutputDebugStringW` at `0x180031bb7`
- `KERNEL32!IsDebuggerPresent` at `0x180031b2d`
- `KERNEL32!IsDebuggerPresent` at `0x180031b2d`
- `KERNEL32!GetCurrentThreadId` at `0x180031a32`
- `KERNEL32!GetCurrentThreadId` at `0x180031a32`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x180031988  mov     [rsp-8+arg_10], rbx
0x18003198d  push    rbp
0x18003198e  push    rsi
0x18003198f  push    rdi
0x180031990  push    r14
0x180031992  push    r15
0x180031994  lea     rbp, [rsp-13D0h]
0x18003199c  mov     eax, 14D0h
0x1800319a1  call    _alloca_probe
0x1800319a6  sub     rsp, rax
0x1800319a9  mov     rax, cs:__security_cookie
0x1800319b0  xor     rax, rsp
0x1800319b3  mov     [rbp+13F0h+var_30], rax
0x1800319ba  mov     rdi, [rbp+13F0h+arg_28]
0x1800319c1  mov     esi, edx
0x1800319c3  mov     r14, rcx
0x1800319c6  xor     edx, edx; Val
0x1800319c8  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800319cd  mov     r8d, 98h; Size
0x1800319d3  call    memset_0
0x1800319d8  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x1800319df  xor     r15d, r15d
0x1800319e2  mov     [rbp+13F0h+OutputString], r15w
0x1800319ea  mov     [rbp+13F0h+var_1430], r15b
0x1800319ee  mov     ecx, [rdx]; this
0x1800319f0  mov     eax, [rdx+4]
0x1800319f3  mov     [rsp+14F0h+var_14C8], ecx
0x1800319f7  mov     [rsp+14F0h+var_14C4], eax
0x1800319fb  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180031a00  cmp     dword ptr [rdx+8], 1
0x180031a04  mov     ebx, eax
0x180031a06  lea     eax, [r15+8]
0x180031a0a  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180031a12  mov     ecx, r15d
0x180031a15  cmovz   ecx, eax
0x180031a18  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180031a1c  lea     ecx, [rax-7]
0x180031a1f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180031a27  inc     ecx
0x180031a29  mov     [rsp+14F0h+var_14B8], r15
0x180031a2e  mov     [rsp+14F0h+var_14C0], ecx
0x180031a32  call    cs:__imp_GetCurrentThreadId
0x180031a38  xorps   xmm0, xmm0
0x180031a3b  mov     [rsp+14F0h+var_1490], esi
0x180031a3f  mov     [rsp+14F0h+var_14B0], eax
0x180031a43  xorps   xmm1, xmm1
0x180031a46  lea     rax, aWil; "wil"
0x180031a4d  mov     [rsp+14F0h+var_148C], ebx
0x180031a51  mov     [rsp+14F0h+var_1498], rax
0x180031a56  xor     eax, eax
0x180031a58  mov     [rbp+13F0h+var_1458], rax
0x180031a5c  mov     [rbp+13F0h+var_1470], rax
0x180031a60  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180031a67  mov     [rsp+14F0h+var_14A8], r15
0x180031a6c  mov     [rsp+14F0h+var_14A0], r15
0x180031a71  mov     [rbp+13F0h+var_1448], rdi
0x180031a75  mov     [rbp+13F0h+var_1440], r14
0x180031a79  mov     [rsp+14F0h+var_1488], r15
0x180031a7e  movups  [rbp+13F0h+var_1468], xmm0
0x180031a82  movups  [rsp+14F0h+var_1480], xmm1
0x180031a87  test    rax, rax
0x180031a8a  jz      short loc_180031A97
0x180031a8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031a91  mov     [rbp+13F0h+var_1450], rax
0x180031a95  jmp     short loc_180031A9B
0x180031a97  mov     [rbp+13F0h+var_1450], r15
0x180031a9b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180031aa2  test    rax, rax
0x180031aa5  jz      short loc_180031AB1
0x180031aa7  lea     rcx, [rsp+14F0h+var_14D0]
0x180031aac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031ab1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180031ab8  test    rax, rax
0x180031abb  jz      short loc_180031AD1
0x180031abd  mov     r8d, 400h
0x180031ac3  lea     rdx, [rbp+13F0h+var_1430]
0x180031ac7  lea     rcx, [rsp+14F0h+var_14D0]
0x180031acc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031ad1  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180031ad8  test    rax, rax
0x180031adb  jz      short loc_180031AE7
0x180031add  lea     rcx, [rsp+14F0h+var_14D0]
0x180031ae2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031ae7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180031aee  test    rax, rax
0x180031af1  jz      short loc_180031B04
0x180031af3  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180031af8  jnz     short loc_180031B04
0x180031afa  lea     rcx, [rsp+14F0h+var_14D0]
0x180031aff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031b04  cmp     [rsp+14F0h+var_14C8], r15d
0x180031b09  jge     loc_180031C0B
0x180031b0f  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180031b16  jnz     short loc_180031B37
0x180031b18  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180031b1f  test    rax, rax
0x180031b22  jz      short loc_180031B2D
0x180031b24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031b29  test    al, al
0x180031b2b  jmp     short loc_180031B35
0x180031b2d  call    cs:__imp_IsDebuggerPresent
0x180031b33  test    eax, eax
0x180031b35  jz      short loc_180031B3E
0x180031b37  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180031b3c  jz      short loc_180031B64
0x180031b3e  mov     rax, cs:g_pfnResultLoggingCallback
0x180031b45  test    rax, rax
0x180031b48  jz      short loc_180031BBD
0x180031b4a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180031b51  jnz     short loc_180031BBD
0x180031b53  xor     r8d, r8d
0x180031b56  lea     rcx, [rsp+14F0h+var_14D0]
0x180031b5b  xor     edx, edx
0x180031b5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031b62  jmp     short loc_180031BBD
0x180031b64  mov     rax, cs:g_pfnResultLoggingCallback
0x180031b6b  mov     ebx, 800h
0x180031b70  test    rax, rax
0x180031b73  jz      short loc_180031B92
0x180031b75  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180031b7c  jnz     short loc_180031B92
0x180031b7e  mov     r8d, ebx
0x180031b81  lea     rdx, [rbp+13F0h+OutputString]
0x180031b88  lea     rcx, [rsp+14F0h+var_14D0]
0x180031b8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031b92  cmp     [rbp+13F0h+OutputString], r15w
0x180031b9a  jnz     short loc_180031BB0
0x180031b9c  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180031ba1  mov     rdx, rbx; unsigned __int16 *
0x180031ba4  lea     rcx, [rbp+13F0h+OutputString]; this
0x180031bab  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180031bb0  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180031bb7  call    cs:__imp_OutputDebugStringW
0x180031bbd  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180031bc2  jnz     short loc_180031BCD
0x180031bc4  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180031bcb  jz      short loc_180031BDE
0x180031bcd  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180031bd4  test    rax, rax
0x180031bd7  jz      short loc_180031BDE
0x180031bd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031bde  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180031be3  jnz     short loc_180031C11
0x180031be5  mov     rcx, [rbp+13F0h+var_30]
0x180031bec  xor     rcx, rsp; StackCookie
0x180031bef  call    __security_check_cookie
0x180031bf4  mov     rbx, [rsp+14F0h+arg_10]
0x180031bfc  add     rsp, 14D0h
0x180031c03  pop     r15
0x180031c05  pop     r14
0x180031c07  pop     rdi
0x180031c08  pop     rsi
0x180031c09  pop     rbp
0x180031c0a  retn
0x180031c0b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180031c11  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180031c16  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
