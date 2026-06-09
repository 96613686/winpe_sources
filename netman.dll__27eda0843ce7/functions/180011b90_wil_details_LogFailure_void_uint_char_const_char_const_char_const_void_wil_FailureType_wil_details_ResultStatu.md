# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180011b90`
- end: `0x180011e89`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180005fac`

## callees

- `0x1800032c4`
- `0x1800036ac`
- `0x180003a00`
- `0x1800059e8`
- `0x180011b90`
- `0x180013f04`
- `0x1800140a0`
- `0x1800140bc`
- `0x1800189ec`
- `0x180036010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x180011dd2`
- `KERNEL32!IsDebuggerPresent` at `0x180011dd2`
- `KERNEL32!OutputDebugStringW` at `0x180011e44`
- `KERNEL32!OutputDebugStringW` at `0x180011e44`
- `KERNEL32!GetCurrentThreadId` at `0x180011cb3`
- `KERNEL32!GetCurrentThreadId` at `0x180011cb3`

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
  unsigned int v18; // edi
  int v19; // ebp
  int v20; // eax
  int v21; // edx
  _WORD *v22; // rax
  int v23; // edx
  wil::details::in1diag3 *v24; // rcx
  const struct wil::FailureInfo *v25; // r9
  __int64 ModuleName; // rax
  bool v27; // zf
  wil::details *v28; // [rsp+30h] [rbp-48h]

  *(_WORD *)lpOutputString = 0;
  *a13 = 0;
  v18 = *a8;
  *(_DWORD *)(a16 + 8) = *a8;
  *(_DWORD *)(a16 + 12) = a8[1];
  v19 = 0;
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1:
        v20 = wil::details::RecordReturn((wil::details *)v18, a2);
        break;
      case 2:
        if ( (v18 & 0x80000000) == 0 )
        {
          v18 = -2147024228;
          LODWORD(v28) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v28);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v21);
        }
        v20 = wil::details::RecordLog((wil::details *)v18, a2);
        break;
      case 3:
        v20 = wil::details::RecordFailFast((wil::details *)v18, a2);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v20 = wil::details::RecordException((wil::details *)v18, a2);
  }
  v19 = v20;
LABEL_12:
  *(_DWORD *)a16 = a7;
  *(_DWORD *)(a16 + 4) = a15;
  if ( a8[2] == 1 )
    *(_DWORD *)(a16 + 4) = a15 | 8;
  *(_DWORD *)(a16 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = a9;
  if ( !a9 || !*a9 )
    v22 = 0;
  *(_QWORD *)(a16 + 24) = v22;
  *(_DWORD *)(a16 + 32) = GetCurrentThreadId();
  *(_QWORD *)(a16 + 56) = a3;
  *(_DWORD *)(a16 + 64) = a2;
  *(_DWORD *)(a16 + 68) = v19;
  *(_QWORD *)(a16 + 40) = a5;
  *(_QWORD *)(a16 + 48) = a4;
  *(_QWORD *)(a16 + 136) = a6;
  *(_QWORD *)(a16 + 144) = a1;
  *(_QWORD *)(a16 + 72) = 0;
  *(_OWORD *)(a16 + 104) = 0;
  *(_QWORD *)(a16 + 120) = 0;
  *(_OWORD *)(a16 + 80) = 0;
  *(_QWORD *)(a16 + 96) = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v24);
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v23);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v27 = !IsDebuggerPresent())
      : (v27 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v24) == 0),
        v27)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v25);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v24);
  }
}

```

## disassembly

```asm
0x180011b90  mov     [rsp+arg_10], rbx
0x180011b95  mov     [rsp+arg_8], edx
0x180011b99  mov     [rsp+arg_0], rcx
0x180011b9e  push    rbp
0x180011b9f  push    rsi
0x180011ba0  push    rdi
0x180011ba1  push    r12
0x180011ba3  push    r13
0x180011ba5  push    r14
0x180011ba7  push    r15
0x180011ba9  sub     rsp, 40h
0x180011bad  mov     r12, r9
0x180011bb0  mov     r13, r8
0x180011bb3  mov     r10, rcx
0x180011bb6  xor     eax, eax
0x180011bb8  mov     rsi, [rsp+78h+lpOutputString]
0x180011bc0  mov     [rsi], ax
0x180011bc3  mov     rax, [rsp+78h+arg_60]
0x180011bcb  mov     byte ptr [rax], 0
0x180011bce  mov     r14, [rsp+78h+arg_38]
0x180011bd6  mov     edi, [r14]
0x180011bd9  mov     rbx, [rsp+78h+arg_78]
0x180011be1  mov     [rbx+8], edi
0x180011be4  mov     eax, [r14+4]
0x180011be8  mov     [rbx+0Ch], eax
0x180011beb  xor     ebp, ebp
0x180011bed  mov     r15d, [rsp+78h+arg_30]
0x180011bf5  mov     ecx, r15d
0x180011bf8  test    r15d, r15d
0x180011bfb  jz      short loc_180011C63
0x180011bfd  sub     ecx, 1
0x180011c00  jz      short loc_180011C5A
0x180011c02  sub     ecx, 1
0x180011c05  jz      short loc_180011C15
0x180011c07  cmp     ecx, 1
0x180011c0a  jnz     short loc_180011C6C
0x180011c0c  mov     ecx, edi; this
0x180011c0e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180011c13  jmp     short loc_180011C6A
0x180011c15  test    edi, edi
0x180011c17  js      short loc_180011C51
0x180011c19  mov     edi, 8007029Ch
0x180011c1e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180011c22  mov     rax, [rsp+78h+arg_28]
0x180011c2a  mov     [rsp+78h+var_50], rax; __int64
0x180011c2f  mov     rax, [rsp+78h+arg_20]
0x180011c37  mov     [rsp+78h+var_58], rax; __int64
0x180011c3c  mov     rcx, r10; int
0x180011c3f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180011c44  mov     [rbx+8], edi
0x180011c47  mov     ecx, edi; this
0x180011c49  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180011c4e  mov     [rbx+0Ch], eax
0x180011c51  mov     ecx, edi; this
0x180011c53  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180011c58  jmp     short loc_180011C6A
0x180011c5a  mov     ecx, edi; this
0x180011c5c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180011c61  jmp     short loc_180011C6A
0x180011c63  mov     ecx, edi; this
0x180011c65  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180011c6a  mov     ebp, eax
0x180011c6c  mov     [rbx], r15d
0x180011c6f  mov     eax, [rsp+78h+arg_70]
0x180011c76  mov     [rbx+4], eax
0x180011c79  cmp     dword ptr [r14+8], 1
0x180011c7e  jnz     short loc_180011C86
0x180011c80  or      eax, 8
0x180011c83  mov     [rbx+4], eax
0x180011c86  mov     eax, 1
0x180011c8b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180011c93  inc     eax
0x180011c95  mov     [rbx+10h], eax
0x180011c98  mov     rax, [rsp+78h+arg_40]
0x180011ca0  xor     edi, edi
0x180011ca2  test    rax, rax
0x180011ca5  jz      short loc_180011CAC
0x180011ca7  cmp     [rax], di
0x180011caa  jnz     short loc_180011CAF
0x180011cac  mov     rax, rdi
0x180011caf  mov     [rbx+18h], rax
0x180011cb3  call    cs:__imp_GetCurrentThreadId
0x180011cb9  mov     [rbx+20h], eax
0x180011cbc  mov     [rbx+38h], r13
0x180011cc0  mov     eax, [rsp+78h+arg_8]
0x180011cc7  mov     [rbx+40h], eax
0x180011cca  mov     [rbx+44h], ebp
0x180011ccd  mov     rax, [rsp+78h+arg_20]
0x180011cd5  mov     [rbx+28h], rax
0x180011cd9  mov     [rbx+30h], r12
0x180011cdd  mov     rax, [rsp+78h+arg_28]
0x180011ce5  mov     [rbx+88h], rax
0x180011cec  mov     rax, [rsp+78h+arg_0]
0x180011cf4  mov     [rbx+90h], rax
0x180011cfb  mov     [rbx+48h], rdi
0x180011cff  xorps   xmm0, xmm0
0x180011d02  xor     eax, eax
0x180011d04  movups  xmmword ptr [rbx+68h], xmm0
0x180011d08  mov     [rbx+78h], rax
0x180011d0c  movups  xmmword ptr [rbx+50h], xmm0
0x180011d10  mov     [rbx+60h], rax
0x180011d14  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180011d1b  test    rax, rax
0x180011d1e  jz      short loc_180011D27
0x180011d20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d25  jmp     short loc_180011D2A
0x180011d27  mov     rax, rdi
0x180011d2a  mov     [rbx+80h], rax
0x180011d31  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180011d38  test    rax, rax
0x180011d3b  jz      short loc_180011D45
0x180011d3d  mov     rcx, rbx
0x180011d40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d45  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180011d4c  test    rax, rax
0x180011d4f  jz      short loc_180011D67
0x180011d51  mov     r8d, 400h
0x180011d57  mov     rdx, [rsp+78h+arg_60]
0x180011d5f  mov     rcx, rbx
0x180011d62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d67  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180011d6e  test    rax, rax
0x180011d71  jz      short loc_180011D7B
0x180011d73  mov     rcx, rbx
0x180011d76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d7b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180011d82  test    rax, rax
0x180011d85  jz      short loc_180011D95
0x180011d87  test    byte ptr [rbx+4], 2
0x180011d8b  jnz     short loc_180011D95
0x180011d8d  mov     rcx, rbx
0x180011d90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d95  cmp     [rbx+8], edi
0x180011d98  jl      short loc_180011DB4
0x180011d9a  cmp     r15d, 3
0x180011d9e  jnz     loc_180011E83
0x180011da4  mov     ecx, 8000FFFFh; this
0x180011da9  mov     [rbx+8], ecx
0x180011dac  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180011db1  mov     [rbx+0Ch], eax
0x180011db4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180011dbb  jnz     short loc_180011DDC
0x180011dbd  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180011dc4  test    rax, rax
0x180011dc7  jz      short loc_180011DD2
0x180011dc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011dce  test    al, al
0x180011dd0  jmp     short loc_180011DDA
0x180011dd2  call    cs:__imp_IsDebuggerPresent
0x180011dd8  test    eax, eax
0x180011dda  jz      short loc_180011DE2
0x180011ddc  test    byte ptr [rbx+4], 2
0x180011de0  jz      short loc_180011E06
0x180011de2  mov     rax, cs:g_pfnResultLoggingCallback
0x180011de9  test    rax, rax
0x180011dec  jz      short loc_180011E4A
0x180011dee  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180011df5  jnz     short loc_180011E4A
0x180011df7  xor     r8d, r8d
0x180011dfa  xor     edx, edx
0x180011dfc  mov     rcx, rbx
0x180011dff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e04  jmp     short loc_180011E4A
0x180011e06  mov     ebp, 800h
0x180011e0b  mov     rax, cs:g_pfnResultLoggingCallback
0x180011e12  test    rax, rax
0x180011e15  jz      short loc_180011E2E
0x180011e17  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180011e1e  jnz     short loc_180011E2E
0x180011e20  mov     r8d, ebp
0x180011e23  mov     rdx, rsi
0x180011e26  mov     rcx, rbx
0x180011e29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e2e  cmp     [rsi], di
0x180011e31  jnz     short loc_180011E41
0x180011e33  mov     r8, rbx; unsigned __int64
0x180011e36  mov     rdx, rbp; unsigned __int16 *
0x180011e39  mov     rcx, rsi; this
0x180011e3c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180011e41  mov     rcx, rsi; lpOutputString
0x180011e44  call    cs:__imp_OutputDebugStringW
0x180011e4a  test    byte ptr [rbx+4], 4
0x180011e4e  jnz     short loc_180011E59
0x180011e50  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180011e57  jz      short loc_180011E6B
0x180011e59  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180011e60  test    rax, rax
0x180011e63  jz      short loc_180011E6B
0x180011e65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e6a  nop
0x180011e6b  mov     rbx, [rsp+78h+arg_10]
0x180011e73  add     rsp, 40h
0x180011e77  pop     r15
0x180011e79  pop     r14
0x180011e7b  pop     r13
0x180011e7d  pop     r12
0x180011e7f  pop     rdi
0x180011e80  pop     rsi
0x180011e81  pop     rbp
0x180011e82  retn
0x180011e83  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
