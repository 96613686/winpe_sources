# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180002c38`
- end: `0x180002ecc`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180002718`

## callees

- `0x180002c38`
- `0x180003af4`
- `0x1800049e0`
- `0x180005260`
- `0x18000533c`
- `0x180012dce`
- `0x180012e00`
- `0x180012e90`
- `0x180014010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180002ce2`
- `KERNEL32!GetCurrentThreadId` at `0x180002ce2`
- `KERNEL32!OutputDebugStringW` at `0x180002e67`
- `KERNEL32!OutputDebugStringW` at `0x180002e67`
- `KERNEL32!IsDebuggerPresent` at `0x180002ddd`
- `KERNEL32!IsDebuggerPresent` at `0x180002ddd`

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
0x180002c38  mov     [rsp-8+arg_10], rbx
0x180002c3d  push    rbp
0x180002c3e  push    rsi
0x180002c3f  push    rdi
0x180002c40  push    r14
0x180002c42  push    r15
0x180002c44  lea     rbp, [rsp-13D0h]
0x180002c4c  mov     eax, 14D0h
0x180002c51  call    _alloca_probe
0x180002c56  sub     rsp, rax
0x180002c59  mov     rax, cs:__security_cookie
0x180002c60  xor     rax, rsp
0x180002c63  mov     [rbp+13F0h+var_30], rax
0x180002c6a  mov     rdi, [rbp+13F0h+arg_28]
0x180002c71  mov     esi, edx
0x180002c73  mov     r14, rcx
0x180002c76  xor     edx, edx; Val
0x180002c78  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180002c7d  mov     r8d, 98h; Size
0x180002c83  call    memset_0
0x180002c88  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180002c8f  xor     r15d, r15d
0x180002c92  mov     [rbp+13F0h+OutputString], r15w
0x180002c9a  mov     [rbp+13F0h+var_1430], r15b
0x180002c9e  mov     ecx, [rdx]; this
0x180002ca0  mov     eax, [rdx+4]
0x180002ca3  mov     [rsp+14F0h+var_14C8], ecx
0x180002ca7  mov     [rsp+14F0h+var_14C4], eax
0x180002cab  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180002cb0  cmp     dword ptr [rdx+8], 1
0x180002cb4  mov     ebx, eax
0x180002cb6  lea     eax, [r15+8]
0x180002cba  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180002cc2  mov     ecx, r15d
0x180002cc5  cmovz   ecx, eax
0x180002cc8  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180002ccc  lea     ecx, [rax-7]
0x180002ccf  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002cd7  inc     ecx
0x180002cd9  mov     [rsp+14F0h+var_14B8], r15
0x180002cde  mov     [rsp+14F0h+var_14C0], ecx
0x180002ce2  call    cs:__imp_GetCurrentThreadId
0x180002ce8  xorps   xmm0, xmm0
0x180002ceb  mov     [rsp+14F0h+var_1490], esi
0x180002cef  mov     [rsp+14F0h+var_14B0], eax
0x180002cf3  xorps   xmm1, xmm1
0x180002cf6  lea     rax, aWil; "wil"
0x180002cfd  mov     [rsp+14F0h+var_148C], ebx
0x180002d01  mov     [rsp+14F0h+var_1498], rax
0x180002d06  xor     eax, eax
0x180002d08  mov     [rbp+13F0h+var_1458], rax
0x180002d0c  mov     [rbp+13F0h+var_1470], rax
0x180002d10  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002d17  mov     [rsp+14F0h+var_14A8], r15
0x180002d1c  mov     [rsp+14F0h+var_14A0], r15
0x180002d21  mov     [rbp+13F0h+var_1448], rdi
0x180002d25  mov     [rbp+13F0h+var_1440], r14
0x180002d29  mov     [rsp+14F0h+var_1488], r15
0x180002d2e  movups  [rbp+13F0h+var_1468], xmm0
0x180002d32  movups  [rsp+14F0h+var_1480], xmm1
0x180002d37  test    rax, rax
0x180002d3a  jz      short loc_180002D47
0x180002d3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d41  mov     [rbp+13F0h+var_1450], rax
0x180002d45  jmp     short loc_180002D4B
0x180002d47  mov     [rbp+13F0h+var_1450], r15
0x180002d4b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002d52  test    rax, rax
0x180002d55  jz      short loc_180002D61
0x180002d57  lea     rcx, [rsp+14F0h+var_14D0]
0x180002d5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d61  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002d68  test    rax, rax
0x180002d6b  jz      short loc_180002D81
0x180002d6d  mov     r8d, 400h
0x180002d73  lea     rdx, [rbp+13F0h+var_1430]
0x180002d77  lea     rcx, [rsp+14F0h+var_14D0]
0x180002d7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d81  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002d88  test    rax, rax
0x180002d8b  jz      short loc_180002D97
0x180002d8d  lea     rcx, [rsp+14F0h+var_14D0]
0x180002d92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d97  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002d9e  test    rax, rax
0x180002da1  jz      short loc_180002DB4
0x180002da3  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002da8  jnz     short loc_180002DB4
0x180002daa  lea     rcx, [rsp+14F0h+var_14D0]
0x180002daf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002db4  cmp     [rsp+14F0h+var_14C8], r15d
0x180002db9  jge     loc_180002EBB
0x180002dbf  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180002dc6  jnz     short loc_180002DE7
0x180002dc8  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002dcf  test    rax, rax
0x180002dd2  jz      short loc_180002DDD
0x180002dd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dd9  test    al, al
0x180002ddb  jmp     short loc_180002DE5
0x180002ddd  call    cs:__imp_IsDebuggerPresent
0x180002de3  test    eax, eax
0x180002de5  jz      short loc_180002DEE
0x180002de7  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002dec  jz      short loc_180002E14
0x180002dee  mov     rax, cs:g_pfnResultLoggingCallback
0x180002df5  test    rax, rax
0x180002df8  jz      short loc_180002E6D
0x180002dfa  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180002e01  jnz     short loc_180002E6D
0x180002e03  xor     r8d, r8d
0x180002e06  lea     rcx, [rsp+14F0h+var_14D0]
0x180002e0b  xor     edx, edx
0x180002e0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e12  jmp     short loc_180002E6D
0x180002e14  mov     rax, cs:g_pfnResultLoggingCallback
0x180002e1b  mov     ebx, 800h
0x180002e20  test    rax, rax
0x180002e23  jz      short loc_180002E42
0x180002e25  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180002e2c  jnz     short loc_180002E42
0x180002e2e  mov     r8d, ebx
0x180002e31  lea     rdx, [rbp+13F0h+OutputString]
0x180002e38  lea     rcx, [rsp+14F0h+var_14D0]
0x180002e3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e42  cmp     [rbp+13F0h+OutputString], r15w
0x180002e4a  jnz     short loc_180002E60
0x180002e4c  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180002e51  mov     rdx, rbx; unsigned __int16 *
0x180002e54  lea     rcx, [rbp+13F0h+OutputString]; this
0x180002e5b  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002e60  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180002e67  call    cs:__imp_OutputDebugStringW
0x180002e6d  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180002e72  jnz     short loc_180002E7D
0x180002e74  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180002e7b  jz      short loc_180002E8E
0x180002e7d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002e84  test    rax, rax
0x180002e87  jz      short loc_180002E8E
0x180002e89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e8e  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180002e93  jnz     short loc_180002EC1
0x180002e95  mov     rcx, [rbp+13F0h+var_30]
0x180002e9c  xor     rcx, rsp; StackCookie
0x180002e9f  call    __security_check_cookie
0x180002ea4  mov     rbx, [rsp+14F0h+arg_10]
0x180002eac  add     rsp, 14D0h
0x180002eb3  pop     r15
0x180002eb5  pop     r14
0x180002eb7  pop     rdi
0x180002eb8  pop     rsi
0x180002eb9  pop     rbp
0x180002eba  retn
0x180002ebb  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180002ec1  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180002ec6  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
