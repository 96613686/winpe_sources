# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180002dcc`
- end: `0x180003073`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `679`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180002894`

## callees

- `0x180002dcc`
- `0x180004934`
- `0x180005ee8`
- `0x180007c2c`
- `0x180007e00`
- `0x180014dce`
- `0x180014e00`
- `0x180014ec0`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002f77`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002f77`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003007`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003007`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002e76`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002e76`

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
0x180002dcc  mov     [rsp-8+arg_10], rbx
0x180002dd1  push    rbp
0x180002dd2  push    rsi
0x180002dd3  push    rdi
0x180002dd4  push    r14
0x180002dd6  push    r15
0x180002dd8  lea     rbp, [rsp-13D0h]
0x180002de0  mov     eax, 14D0h
0x180002de5  call    _alloca_probe
0x180002dea  sub     rsp, rax
0x180002ded  mov     rax, cs:__security_cookie
0x180002df4  xor     rax, rsp
0x180002df7  mov     [rbp+13F0h+var_30], rax
0x180002dfe  mov     rdi, [rbp+13F0h+arg_28]
0x180002e05  mov     esi, edx
0x180002e07  mov     r14, rcx
0x180002e0a  xor     edx, edx; Val
0x180002e0c  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180002e11  mov     r8d, 98h; Size
0x180002e17  call    memset_0
0x180002e1c  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180002e23  xor     r15d, r15d
0x180002e26  mov     [rbp+13F0h+OutputString], r15w
0x180002e2e  mov     [rbp+13F0h+var_1430], r15b
0x180002e32  mov     ecx, [rdx]; this
0x180002e34  mov     eax, [rdx+4]
0x180002e37  mov     [rsp+14F0h+var_14C8], ecx
0x180002e3b  mov     [rsp+14F0h+var_14C4], eax
0x180002e3f  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180002e44  cmp     dword ptr [rdx+8], 1
0x180002e48  mov     ebx, eax
0x180002e4a  lea     eax, [r15+8]
0x180002e4e  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180002e56  mov     ecx, r15d
0x180002e59  cmovz   ecx, eax
0x180002e5c  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180002e60  lea     ecx, [rax-7]
0x180002e63  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002e6b  inc     ecx
0x180002e6d  mov     [rsp+14F0h+var_14B8], r15
0x180002e72  mov     [rsp+14F0h+var_14C0], ecx
0x180002e76  call    cs:__imp_GetCurrentThreadId
0x180002e7d  nop     dword ptr [rax+rax+00h]
0x180002e82  xorps   xmm0, xmm0
0x180002e85  mov     [rsp+14F0h+var_1490], esi
0x180002e89  mov     [rsp+14F0h+var_14B0], eax
0x180002e8d  xorps   xmm1, xmm1
0x180002e90  lea     rax, aWil; "wil"
0x180002e97  mov     [rsp+14F0h+var_148C], ebx
0x180002e9b  mov     [rsp+14F0h+var_1498], rax
0x180002ea0  xor     eax, eax
0x180002ea2  mov     [rbp+13F0h+var_1458], rax
0x180002ea6  mov     [rbp+13F0h+var_1470], rax
0x180002eaa  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002eb1  mov     [rsp+14F0h+var_14A8], r15
0x180002eb6  mov     [rsp+14F0h+var_14A0], r15
0x180002ebb  mov     [rbp+13F0h+var_1448], rdi
0x180002ebf  mov     [rbp+13F0h+var_1440], r14
0x180002ec3  mov     [rsp+14F0h+var_1488], r15
0x180002ec8  movups  [rbp+13F0h+var_1468], xmm0
0x180002ecc  movups  [rsp+14F0h+var_1480], xmm1
0x180002ed1  test    rax, rax
0x180002ed4  jz      short loc_180002EE1
0x180002ed6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002edb  mov     [rbp+13F0h+var_1450], rax
0x180002edf  jmp     short loc_180002EE5
0x180002ee1  mov     [rbp+13F0h+var_1450], r15
0x180002ee5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002eec  test    rax, rax
0x180002eef  jz      short loc_180002EFB
0x180002ef1  lea     rcx, [rsp+14F0h+var_14D0]
0x180002ef6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002efb  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002f02  test    rax, rax
0x180002f05  jz      short loc_180002F1B
0x180002f07  mov     r8d, 400h
0x180002f0d  lea     rdx, [rbp+13F0h+var_1430]
0x180002f11  lea     rcx, [rsp+14F0h+var_14D0]
0x180002f16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f1b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002f22  test    rax, rax
0x180002f25  jz      short loc_180002F31
0x180002f27  lea     rcx, [rsp+14F0h+var_14D0]
0x180002f2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f31  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002f38  test    rax, rax
0x180002f3b  jz      short loc_180002F4E
0x180002f3d  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002f42  jnz     short loc_180002F4E
0x180002f44  lea     rcx, [rsp+14F0h+var_14D0]
0x180002f49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f4e  cmp     [rsp+14F0h+var_14C8], r15d
0x180002f53  jge     loc_180003062
0x180002f59  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180002f60  jnz     short loc_180002F87
0x180002f62  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002f69  test    rax, rax
0x180002f6c  jz      short loc_180002F77
0x180002f6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f73  test    al, al
0x180002f75  jmp     short loc_180002F85
0x180002f77  call    cs:__imp_IsDebuggerPresent
0x180002f7e  nop     dword ptr [rax+rax+00h]
0x180002f83  test    eax, eax
0x180002f85  jz      short loc_180002F8E
0x180002f87  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002f8c  jz      short loc_180002FB4
0x180002f8e  mov     rax, cs:g_pfnResultLoggingCallback
0x180002f95  test    rax, rax
0x180002f98  jz      short loc_180003013
0x180002f9a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180002fa1  jnz     short loc_180003013
0x180002fa3  xor     r8d, r8d
0x180002fa6  lea     rcx, [rsp+14F0h+var_14D0]
0x180002fab  xor     edx, edx
0x180002fad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fb2  jmp     short loc_180003013
0x180002fb4  mov     rax, cs:g_pfnResultLoggingCallback
0x180002fbb  mov     ebx, 800h
0x180002fc0  test    rax, rax
0x180002fc3  jz      short loc_180002FE2
0x180002fc5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180002fcc  jnz     short loc_180002FE2
0x180002fce  mov     r8d, ebx
0x180002fd1  lea     rdx, [rbp+13F0h+OutputString]
0x180002fd8  lea     rcx, [rsp+14F0h+var_14D0]
0x180002fdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fe2  cmp     [rbp+13F0h+OutputString], r15w
0x180002fea  jnz     short loc_180003000
0x180002fec  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180002ff1  mov     rdx, rbx; unsigned __int16 *
0x180002ff4  lea     rcx, [rbp+13F0h+OutputString]; this
0x180002ffb  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003000  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180003007  call    cs:__imp_OutputDebugStringW
0x18000300e  nop     dword ptr [rax+rax+00h]
0x180003013  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180003018  jnz     short loc_180003023
0x18000301a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180003021  jz      short loc_180003034
0x180003023  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000302a  test    rax, rax
0x18000302d  jz      short loc_180003034
0x18000302f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003034  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180003039  jnz     short loc_180003068
0x18000303b  mov     rcx, [rbp+13F0h+var_30]
0x180003042  xor     rcx, rsp; StackCookie
0x180003045  call    __security_check_cookie
0x18000304a  mov     rbx, [rsp+14F0h+arg_10]
0x180003052  add     rsp, 14D0h
0x180003059  pop     r15
0x18000305b  pop     r14
0x18000305d  pop     rdi
0x18000305e  pop     rsi
0x18000305f  pop     rbp
0x180003060  retn
0x180003062  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003068  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000306d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
