# wil::details::ReportFailure_Return<2>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140002bb8`
- end: `0x140002eb0`
- name: `??$ReportFailure_Return@$01@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `760`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int *, _WORD *, int, int)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x1400023a4`

## callees

- `0x140001570`
- `0x1400020d0`
- `0x1400025c0`
- `0x140002bb8`
- `0x140004c14`
- `0x1400053bc`
- `0x140005e0c`
- `0x1400081e0`
- `0x1400083ac`
- `0x14001a7d0`
- `0x14001c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002cd1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002cd1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140002e4d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140002e4d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140002dc4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140002dc4`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<2>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int *a7,
        _WORD *a8,
        int a9,
        int a10)
{
  int v14; // edx
  int v15; // ebx
  int v16; // edx
  int v17; // ebx
  const struct wil::FailureInfo *v18; // rdx
  wil::details::in1diag3 *v19; // rcx
  const struct wil::FailureInfo *v20; // r9
  bool v21; // zf
  wil::details *v22; // [rsp+30h] [rbp-D0h]
  int v23; // [rsp+50h] [rbp-B0h] BYREF
  int v24; // [rsp+54h] [rbp-ACh]
  int v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+5Ch] [rbp-A4h]
  signed __int32 v27; // [rsp+60h] [rbp-A0h]
  _WORD *v28; // [rsp+68h] [rbp-98h]
  DWORD CurrentThreadId; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+78h] [rbp-88h]
  __int64 v31; // [rsp+80h] [rbp-80h]
  __int64 v32; // [rsp+88h] [rbp-78h]
  int v33; // [rsp+90h] [rbp-70h]
  int v34; // [rsp+94h] [rbp-6Ch]
  __int64 v35; // [rsp+98h] [rbp-68h]
  __int128 v36; // [rsp+A0h] [rbp-60h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  __int128 v38; // [rsp+B8h] [rbp-48h]
  __int64 v39; // [rsp+C8h] [rbp-38h]
  __int64 ModuleName; // [rsp+D0h] [rbp-30h]
  __int64 v41; // [rsp+D8h] [rbp-28h]
  __int64 v42; // [rsp+E0h] [rbp-20h]
  char v43[1024]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR OutputString[2048]; // [rsp+4F0h] [rbp+3F0h] BYREF

  memset_0(&v23, 0, 0x98u);
  OutputString[0] = 0;
  v43[0] = 0;
  v15 = *a7;
  v25 = v15;
  v26 = a7[1];
  if ( v15 >= 0 )
  {
    v15 = -2147024228;
    LODWORD(v22) = -2147024228;
    wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v22);
    v25 = -2147024228;
    v26 = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v16);
  }
  v17 = wil::details::RecordLog((wil::details *)(unsigned int)v15, v14);
  v23 = 2;
  v24 = a10;
  if ( a7[2] == 1 )
    v24 = a10 | 8;
  v27 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v21 = *a8 == 0, v28 = a8, v21) )
    v28 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v32 = a3;
  v33 = a2;
  v34 = v17;
  v30 = a5;
  v31 = a4;
  v41 = a6;
  v42 = a1;
  v35 = 0;
  v38 = 0;
  v39 = 0;
  v36 = 0;
  v37 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v19);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v23);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v23, v43, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v23);
  if ( wil::details::g_pfnOriginateCallback && (v24 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v23);
  if ( v25 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v19);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v21 = !IsDebuggerPresent())
      : (v21 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v19) == 0),
        v21)
    || (v24 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v23, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v23, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v23, v20);
    OutputDebugStringW(OutputString);
  }
  if ( ((v24 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v19);
  if ( (v24 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v23, v18);
}

```

## disassembly

```asm
0x140002bb8  push    rbp
0x140002bba  push    rbx
0x140002bbb  push    rsi
0x140002bbc  push    rdi
0x140002bbd  push    r12
0x140002bbf  push    r13
0x140002bc1  push    r14
0x140002bc3  push    r15
0x140002bc5  lea     rbp, [rsp-1408h]
0x140002bcd  mov     eax, 1508h
0x140002bd2  call    _alloca_probe
0x140002bd7  sub     rsp, rax
0x140002bda  mov     rax, cs:__security_cookie
0x140002be1  xor     rax, rsp
0x140002be4  mov     [rbp+1440h+var_50], rax
0x140002beb  mov     r12, r9
0x140002bee  mov     r15, r8
0x140002bf1  mov     r14d, edx
0x140002bf4  mov     rsi, rcx
0x140002bf7  mov     r13, [rbp+1440h+arg_20]
0x140002bfe  mov     rax, [rbp+1440h+arg_28]
0x140002c05  mov     [rsp+1540h+var_1500], rax
0x140002c0a  xor     edx, edx; Val
0x140002c0c  mov     r8d, 98h; Size
0x140002c12  lea     rcx, [rsp+1540h+var_14F0]; void *
0x140002c17  call    memset_0
0x140002c1c  nop
0x140002c1d  xor     eax, eax
0x140002c1f  mov     [rbp+1440h+OutputString], ax
0x140002c26  mov     [rbp+1440h+var_1450], al
0x140002c29  mov     rdi, [rbp+1440h+arg_30]
0x140002c30  mov     ebx, [rdi]
0x140002c32  mov     [rsp+1540h+var_14E8], ebx
0x140002c36  mov     eax, [rdi+4]
0x140002c39  mov     [rsp+1540h+var_14E4], eax
0x140002c3d  test    ebx, ebx
0x140002c3f  js      short loc_140002C79
0x140002c41  mov     ebx, 8007029Ch
0x140002c46  mov     dword ptr [rsp+1540h+var_1510], ebx; wil::details *
0x140002c4a  mov     rax, [rsp+1540h+var_1500]
0x140002c4f  mov     [rsp+1540h+var_1518], rax; __int64
0x140002c54  mov     [rsp+1540h+var_1520], r13; __int64
0x140002c59  mov     r9, r12; int
0x140002c5c  mov     r8, r15; int
0x140002c5f  mov     edx, r14d; int
0x140002c62  mov     rcx, rsi; int
0x140002c65  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140002c6a  mov     [rsp+1540h+var_14E8], ebx
0x140002c6e  mov     ecx, ebx; this
0x140002c70  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140002c75  mov     [rsp+1540h+var_14E4], eax
0x140002c79  mov     ecx, ebx; this
0x140002c7b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140002c80  mov     ebx, eax
0x140002c82  mov     dword ptr [rsp+1540h+var_14F0], 2
0x140002c8a  mov     ecx, [rbp+1440h+arg_48]
0x140002c90  mov     dword ptr [rsp+1540h+var_14F0+4], ecx
0x140002c94  cmp     dword ptr [rdi+8], 1
0x140002c98  jnz     short loc_140002CA1
0x140002c9a  or      ecx, 8
0x140002c9d  mov     dword ptr [rsp+1540h+var_14F0+4], ecx
0x140002ca1  mov     ecx, 1
0x140002ca6  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140002cae  inc     ecx
0x140002cb0  mov     [rsp+1540h+var_14E0], ecx
0x140002cb4  mov     rax, [rbp+1440h+arg_38]
0x140002cbb  xor     edi, edi
0x140002cbd  test    rax, rax
0x140002cc0  jz      short loc_140002CCC
0x140002cc2  cmp     [rax], di
0x140002cc5  mov     [rsp+1540h+var_14D8], rax
0x140002cca  jnz     short loc_140002CD1
0x140002ccc  mov     [rsp+1540h+var_14D8], rdi
0x140002cd1  call    cs:__imp_GetCurrentThreadId
0x140002cd7  mov     [rsp+1540h+var_14D0], eax
0x140002cdb  mov     [rbp+1440h+var_14B8], r15
0x140002cdf  mov     [rbp+1440h+var_14B0], r14d
0x140002ce3  mov     [rbp+1440h+var_14AC], ebx
0x140002ce6  mov     [rsp+1540h+var_14C8], r13
0x140002ceb  mov     [rbp+1440h+var_14C0], r12
0x140002cef  mov     rax, [rsp+1540h+var_1500]
0x140002cf4  mov     [rbp+1440h+var_1468], rax
0x140002cf8  mov     [rbp+1440h+var_1460], rsi
0x140002cfc  mov     [rbp+1440h+var_14A8], rdi
0x140002d00  xorps   xmm0, xmm0
0x140002d03  xor     eax, eax
0x140002d05  movups  [rbp+1440h+var_1488], xmm0
0x140002d09  mov     [rbp+1440h+var_1478], rax
0x140002d0d  xorps   xmm1, xmm1
0x140002d10  movups  [rbp+1440h+var_14A0], xmm1
0x140002d14  mov     [rbp+1440h+var_1490], rax
0x140002d18  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140002d1f  test    rax, rax
0x140002d22  jz      short loc_140002D2F
0x140002d24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002d29  mov     [rbp+1440h+var_1470], rax
0x140002d2d  jmp     short loc_140002D33
0x140002d2f  mov     [rbp+1440h+var_1470], rdi
0x140002d33  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140002d3a  test    rax, rax
0x140002d3d  jz      short loc_140002D49
0x140002d3f  lea     rcx, [rsp+1540h+var_14F0]
0x140002d44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002d49  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140002d50  test    rax, rax
0x140002d53  jz      short loc_140002D69
0x140002d55  mov     r8d, 400h
0x140002d5b  lea     rdx, [rbp+1440h+var_1450]
0x140002d5f  lea     rcx, [rsp+1540h+var_14F0]
0x140002d64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002d69  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002d70  test    rax, rax
0x140002d73  jz      short loc_140002D7F
0x140002d75  lea     rcx, [rsp+1540h+var_14F0]
0x140002d7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002d7f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002d86  test    rax, rax
0x140002d89  jz      short loc_140002D9C
0x140002d8b  test    byte ptr [rsp+1540h+var_14F0+4], 2
0x140002d90  jnz     short loc_140002D9C
0x140002d92  lea     rcx, [rsp+1540h+var_14F0]
0x140002d97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002d9c  cmp     [rsp+1540h+var_14E8], edi
0x140002da0  jge     loc_140002EAA
0x140002da6  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x140002dad  jnz     short loc_140002DCE
0x140002daf  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140002db6  test    rax, rax
0x140002db9  jz      short loc_140002DC4
0x140002dbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002dc0  test    al, al
0x140002dc2  jmp     short loc_140002DCC
0x140002dc4  call    cs:__imp_IsDebuggerPresent
0x140002dca  test    eax, eax
0x140002dcc  jz      short loc_140002DD5
0x140002dce  test    byte ptr [rsp+1540h+var_14F0+4], 2
0x140002dd3  jz      short loc_140002DFB
0x140002dd5  mov     rax, cs:g_pfnResultLoggingCallback
0x140002ddc  test    rax, rax
0x140002ddf  jz      short loc_140002E53
0x140002de1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140002de8  jnz     short loc_140002E53
0x140002dea  xor     r8d, r8d
0x140002ded  xor     edx, edx
0x140002def  lea     rcx, [rsp+1540h+var_14F0]
0x140002df4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002df9  jmp     short loc_140002E53
0x140002dfb  mov     ebx, 800h
0x140002e00  mov     rax, cs:g_pfnResultLoggingCallback
0x140002e07  test    rax, rax
0x140002e0a  jz      short loc_140002E29
0x140002e0c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140002e13  jnz     short loc_140002E29
0x140002e15  mov     r8d, ebx
0x140002e18  lea     rdx, [rbp+1440h+OutputString]
0x140002e1f  lea     rcx, [rsp+1540h+var_14F0]
0x140002e24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002e29  cmp     [rbp+1440h+OutputString], di
0x140002e30  jnz     short loc_140002E46
0x140002e32  lea     r8, [rsp+1540h+var_14F0]; unsigned __int64
0x140002e37  mov     rdx, rbx; unsigned __int16 *
0x140002e3a  lea     rcx, [rbp+1440h+OutputString]; this
0x140002e41  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140002e46  lea     rcx, [rbp+1440h+OutputString]; lpOutputString
0x140002e4d  call    cs:__imp_OutputDebugStringW
0x140002e53  test    byte ptr [rsp+1540h+var_14F0+4], 4
0x140002e58  jnz     short loc_140002E63
0x140002e5a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x140002e61  jz      short loc_140002E75
0x140002e63  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140002e6a  test    rax, rax
0x140002e6d  jz      short loc_140002E75
0x140002e6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002e74  nop
0x140002e75  test    byte ptr [rsp+1540h+var_14F0+4], 1
0x140002e7a  jnz     short loc_140002E9F
0x140002e7c  mov     rcx, [rbp+1440h+var_50]
0x140002e83  xor     rcx, rsp; StackCookie
0x140002e86  call    __security_check_cookie
0x140002e8b  add     rsp, 1508h
0x140002e92  pop     r15
0x140002e94  pop     r14
0x140002e96  pop     r13
0x140002e98  pop     r12
0x140002e9a  pop     rdi
0x140002e9b  pop     rsi
0x140002e9c  pop     rbx
0x140002e9d  pop     rbp
0x140002e9e  retn
0x140002e9f  lea     rcx, [rsp+1540h+var_14F0]; this
0x140002ea4  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x140002eaa  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
