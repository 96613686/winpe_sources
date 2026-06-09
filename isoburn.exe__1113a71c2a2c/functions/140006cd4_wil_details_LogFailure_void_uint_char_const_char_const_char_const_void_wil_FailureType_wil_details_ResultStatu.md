# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140006cd4`
- end: `0x140006fcc`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140003560`

## callees

- `0x140002f9c`
- `0x140005024`
- `0x140006078`
- `0x140006cd4`
- `0x140007720`
- `0x140007740`
- `0x140007754`
- `0x140007770`
- `0x140009a1c`
- `0x140010010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x140006f16`
- `KERNEL32!IsDebuggerPresent` at `0x140006f16`
- `KERNEL32!OutputDebugStringW` at `0x140006f88`
- `KERNEL32!OutputDebugStringW` at `0x140006f88`
- `KERNEL32!GetCurrentThreadId` at `0x140006df7`
- `KERNEL32!GetCurrentThreadId` at `0x140006df7`

## pseudocode

```c
void __fastcall wil::details::LogFailure(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int a7,
        unsigned int *a8,
        _WORD *a9,
        __int64 a10,
        wil *lpOutputString,
        __int64 a12,
        _BYTE *a13,
        __int64 a14,
        int a15,
        unsigned __int64 a16)
{
  int v16; // ebp
  unsigned int v19; // edi
  int v20; // eax
  int v21; // edx
  _WORD *v22; // rax
  DWORD CurrentThreadId; // eax
  int v24; // edx
  wil::details::in1diag3 *v25; // rcx
  const struct wil::FailureInfo *v26; // r9
  __int64 ModuleName; // rax
  bool v28; // zf
  wil::details *v29; // [rsp+30h] [rbp-48h]

  v16 = 0;
  *(_WORD *)lpOutputString = 0;
  *a13 = 0;
  v19 = *a8;
  *(_DWORD *)(a16 + 8) = *a8;
  *(_DWORD *)(a16 + 12) = a8[1];
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1:
        v20 = wil::details::RecordReturn((wil::details *)v19, a2);
        break;
      case 2:
        if ( (v19 & 0x80000000) == 0 )
        {
          v19 = -2147024228;
          LODWORD(v29) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v29);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v21);
        }
        v20 = wil::details::RecordLog((wil::details *)v19, a2);
        break;
      case 3:
        v20 = wil::details::RecordFailFast((wil::details *)v19, a2);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v20 = wil::details::RecordException((wil::details *)v19, a2);
  }
  v16 = v20;
LABEL_12:
  *(_DWORD *)(a16 + 4) = a15;
  *(_DWORD *)a16 = a7;
  if ( a8[2] == 1 )
    *(_DWORD *)(a16 + 4) = a15 | 8;
  *(_DWORD *)(a16 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = a9;
  if ( !a9 || !*a9 )
    v22 = 0;
  *(_QWORD *)(a16 + 24) = v22;
  CurrentThreadId = GetCurrentThreadId();
  *(_QWORD *)(a16 + 56) = a3;
  *(_DWORD *)(a16 + 32) = CurrentThreadId;
  *(_DWORD *)(a16 + 64) = a2;
  *(_QWORD *)(a16 + 40) = a5;
  *(_QWORD *)(a16 + 136) = a6;
  *(_QWORD *)(a16 + 144) = a1;
  *(_DWORD *)(a16 + 68) = v16;
  *(_QWORD *)(a16 + 48) = a4;
  *(_QWORD *)(a16 + 72) = 0;
  *(_OWORD *)(a16 + 104) = 0;
  *(_QWORD *)(a16 + 120) = 0;
  *(_OWORD *)(a16 + 80) = 0;
  *(_QWORD *)(a16 + 96) = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v25);
  else
    ModuleName = 0;
  *(_QWORD *)(a16 + 128) = ModuleName;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(a16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(a16, a13, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(a16);
  if ( wil::details::g_pfnOriginateCallback && (*(_BYTE *)(a16 + 4) & 2) == 0 )
    wil::details::g_pfnOriginateCallback(a16);
  if ( *(int *)(a16 + 8) >= 0 )
  {
    if ( a7 != 3 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v25);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v24);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v28 = !IsDebuggerPresent())
      : (v28 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v25) == 0),
        v28)
    || (*(_BYTE *)(a16 + 4) & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v26);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v25);
  }
}

```

## disassembly

```asm
0x140006cd4  mov     [rsp+arg_10], rbx
0x140006cd9  mov     [rsp+arg_8], edx
0x140006cdd  mov     [rsp+arg_0], rcx
0x140006ce2  push    rbp
0x140006ce3  push    rsi
0x140006ce4  push    rdi
0x140006ce5  push    r12
0x140006ce7  push    r13
0x140006ce9  push    r14
0x140006ceb  push    r15
0x140006ced  sub     rsp, 40h
0x140006cf1  mov     r14, [rsp+78h+arg_38]
0x140006cf9  xor     eax, eax
0x140006cfb  mov     rbx, [rsp+78h+arg_78]
0x140006d03  xor     ebp, ebp
0x140006d05  mov     r15d, [rsp+78h+arg_30]
0x140006d0d  mov     r10, rcx
0x140006d10  mov     rsi, [rsp+78h+lpOutputString]
0x140006d18  mov     r12, r9
0x140006d1b  mov     r13, r8
0x140006d1e  mov     ecx, r15d
0x140006d21  mov     [rsi], ax
0x140006d24  mov     rax, [rsp+78h+arg_60]
0x140006d2c  mov     byte ptr [rax], 0
0x140006d2f  mov     edi, [r14]
0x140006d32  mov     [rbx+8], edi
0x140006d35  mov     eax, [r14+4]
0x140006d39  mov     [rbx+0Ch], eax
0x140006d3c  test    r15d, r15d
0x140006d3f  jz      short loc_140006DA7
0x140006d41  sub     ecx, 1
0x140006d44  jz      short loc_140006D9E
0x140006d46  sub     ecx, 1
0x140006d49  jz      short loc_140006D59
0x140006d4b  cmp     ecx, 1
0x140006d4e  jnz     short loc_140006DB0
0x140006d50  mov     ecx, edi; this
0x140006d52  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140006d57  jmp     short loc_140006DAE
0x140006d59  test    edi, edi
0x140006d5b  js      short loc_140006D95
0x140006d5d  mov     rax, [rsp+78h+arg_28]
0x140006d65  mov     edi, 8007029Ch
0x140006d6a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x140006d6e  mov     rcx, r10; int
0x140006d71  mov     [rsp+78h+var_50], rax; __int64
0x140006d76  mov     rax, [rsp+78h+arg_20]
0x140006d7e  mov     [rsp+78h+var_58], rax; __int64
0x140006d83  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140006d88  mov     ecx, edi; this
0x140006d8a  mov     [rbx+8], edi
0x140006d8d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140006d92  mov     [rbx+0Ch], eax
0x140006d95  mov     ecx, edi; this
0x140006d97  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140006d9c  jmp     short loc_140006DAE
0x140006d9e  mov     ecx, edi; this
0x140006da0  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140006da5  jmp     short loc_140006DAE
0x140006da7  mov     ecx, edi; this
0x140006da9  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140006dae  mov     ebp, eax
0x140006db0  mov     eax, [rsp+78h+arg_70]
0x140006db7  mov     [rbx+4], eax
0x140006dba  mov     [rbx], r15d
0x140006dbd  cmp     dword ptr [r14+8], 1
0x140006dc2  jnz     short loc_140006DCA
0x140006dc4  or      eax, 8
0x140006dc7  mov     [rbx+4], eax
0x140006dca  mov     eax, 1
0x140006dcf  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140006dd7  inc     eax
0x140006dd9  xor     edi, edi
0x140006ddb  mov     [rbx+10h], eax
0x140006dde  mov     rax, [rsp+78h+arg_40]
0x140006de6  test    rax, rax
0x140006de9  jz      short loc_140006DF0
0x140006deb  cmp     [rax], di
0x140006dee  jnz     short loc_140006DF3
0x140006df0  mov     rax, rdi
0x140006df3  mov     [rbx+18h], rax
0x140006df7  call    cs:__imp_GetCurrentThreadId
0x140006dfd  mov     [rbx+38h], r13
0x140006e01  xorps   xmm0, xmm0
0x140006e04  mov     [rbx+20h], eax
0x140006e07  mov     eax, [rsp+78h+arg_8]
0x140006e0e  mov     [rbx+40h], eax
0x140006e11  mov     rax, [rsp+78h+arg_20]
0x140006e19  mov     [rbx+28h], rax
0x140006e1d  mov     rax, [rsp+78h+arg_28]
0x140006e25  mov     [rbx+88h], rax
0x140006e2c  mov     rax, [rsp+78h+arg_0]
0x140006e34  mov     [rbx+90h], rax
0x140006e3b  xor     eax, eax
0x140006e3d  mov     [rbx+44h], ebp
0x140006e40  mov     [rbx+30h], r12
0x140006e44  mov     [rbx+48h], rdi
0x140006e48  movups  xmmword ptr [rbx+68h], xmm0
0x140006e4c  mov     [rbx+78h], rax
0x140006e50  movups  xmmword ptr [rbx+50h], xmm0
0x140006e54  mov     [rbx+60h], rax
0x140006e58  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140006e5f  test    rax, rax
0x140006e62  jz      short loc_140006E6B
0x140006e64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006e69  jmp     short loc_140006E6E
0x140006e6b  mov     rax, rdi
0x140006e6e  mov     [rbx+80h], rax
0x140006e75  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140006e7c  test    rax, rax
0x140006e7f  jz      short loc_140006E89
0x140006e81  mov     rcx, rbx
0x140006e84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006e89  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140006e90  test    rax, rax
0x140006e93  jz      short loc_140006EAB
0x140006e95  mov     rdx, [rsp+78h+arg_60]
0x140006e9d  mov     r8d, 400h
0x140006ea3  mov     rcx, rbx
0x140006ea6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006eab  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140006eb2  test    rax, rax
0x140006eb5  jz      short loc_140006EBF
0x140006eb7  mov     rcx, rbx
0x140006eba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006ebf  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140006ec6  test    rax, rax
0x140006ec9  jz      short loc_140006ED9
0x140006ecb  test    byte ptr [rbx+4], 2
0x140006ecf  jnz     short loc_140006ED9
0x140006ed1  mov     rcx, rbx
0x140006ed4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006ed9  cmp     [rbx+8], edi
0x140006edc  jl      short loc_140006EF8
0x140006ede  cmp     r15d, 3
0x140006ee2  jnz     loc_140006FC6
0x140006ee8  mov     ecx, 8000FFFFh; this
0x140006eed  mov     [rbx+8], ecx
0x140006ef0  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140006ef5  mov     [rbx+0Ch], eax
0x140006ef8  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x140006eff  jnz     short loc_140006F20
0x140006f01  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140006f08  test    rax, rax
0x140006f0b  jz      short loc_140006F16
0x140006f0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006f12  test    al, al
0x140006f14  jmp     short loc_140006F1E
0x140006f16  call    cs:__imp_IsDebuggerPresent
0x140006f1c  test    eax, eax
0x140006f1e  jz      short loc_140006F26
0x140006f20  test    byte ptr [rbx+4], 2
0x140006f24  jz      short loc_140006F4A
0x140006f26  mov     rax, cs:g_pfnResultLoggingCallback
0x140006f2d  test    rax, rax
0x140006f30  jz      short loc_140006F8E
0x140006f32  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140006f39  jnz     short loc_140006F8E
0x140006f3b  xor     r8d, r8d
0x140006f3e  xor     edx, edx
0x140006f40  mov     rcx, rbx
0x140006f43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006f48  jmp     short loc_140006F8E
0x140006f4a  mov     rax, cs:g_pfnResultLoggingCallback
0x140006f51  mov     ebp, 800h
0x140006f56  test    rax, rax
0x140006f59  jz      short loc_140006F72
0x140006f5b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140006f62  jnz     short loc_140006F72
0x140006f64  mov     r8d, ebp
0x140006f67  mov     rdx, rsi
0x140006f6a  mov     rcx, rbx
0x140006f6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006f72  cmp     [rsi], di
0x140006f75  jnz     short loc_140006F85
0x140006f77  mov     r8, rbx; unsigned __int64
0x140006f7a  mov     rdx, rbp; unsigned __int16 *
0x140006f7d  mov     rcx, rsi; this
0x140006f80  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140006f85  mov     rcx, rsi; lpOutputString
0x140006f88  call    cs:__imp_OutputDebugStringW
0x140006f8e  test    byte ptr [rbx+4], 4
0x140006f92  jnz     short loc_140006F9D
0x140006f94  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x140006f9b  jz      short loc_140006FAE
0x140006f9d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140006fa4  test    rax, rax
0x140006fa7  jz      short loc_140006FAE
0x140006fa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006fae  mov     rbx, [rsp+78h+arg_10]
0x140006fb6  add     rsp, 40h
0x140006fba  pop     r15
0x140006fbc  pop     r14
0x140006fbe  pop     r13
0x140006fc0  pop     r12
0x140006fc2  pop     rdi
0x140006fc3  pop     rsi
0x140006fc4  pop     rbp
0x140006fc5  retn
0x140006fc6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
