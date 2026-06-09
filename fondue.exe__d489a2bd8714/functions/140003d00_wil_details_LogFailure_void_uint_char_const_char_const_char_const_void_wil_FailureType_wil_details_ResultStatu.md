# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140003d00`
- end: `0x140003ff8`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140002840`

## callees

- `0x14000227c`
- `0x1400033a4`
- `0x140003b3c`
- `0x140003d00`
- `0x14000423c`
- `0x140004260`
- `0x140004274`
- `0x140004290`
- `0x140004bfc`
- `0x140005010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140003e23`
- `KERNEL32!GetCurrentThreadId` at `0x140003e23`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140003f42`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140003f42`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140003fb4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140003fb4`

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
0x140003d00  mov     [rsp+arg_10], rbx
0x140003d05  mov     [rsp+arg_8], edx
0x140003d09  mov     [rsp+arg_0], rcx
0x140003d0e  push    rbp
0x140003d0f  push    rsi
0x140003d10  push    rdi
0x140003d11  push    r12
0x140003d13  push    r13
0x140003d15  push    r14
0x140003d17  push    r15
0x140003d19  sub     rsp, 40h
0x140003d1d  mov     r14, [rsp+78h+arg_38]
0x140003d25  xor     eax, eax
0x140003d27  mov     rbx, [rsp+78h+arg_78]
0x140003d2f  xor     ebp, ebp
0x140003d31  mov     r15d, [rsp+78h+arg_30]
0x140003d39  mov     r10, rcx
0x140003d3c  mov     rsi, [rsp+78h+lpOutputString]
0x140003d44  mov     r12, r9
0x140003d47  mov     r13, r8
0x140003d4a  mov     ecx, r15d
0x140003d4d  mov     [rsi], ax
0x140003d50  mov     rax, [rsp+78h+arg_60]
0x140003d58  mov     byte ptr [rax], 0
0x140003d5b  mov     edi, [r14]
0x140003d5e  mov     [rbx+8], edi
0x140003d61  mov     eax, [r14+4]
0x140003d65  mov     [rbx+0Ch], eax
0x140003d68  test    r15d, r15d
0x140003d6b  jz      short loc_140003DD3
0x140003d6d  sub     ecx, 1
0x140003d70  jz      short loc_140003DCA
0x140003d72  sub     ecx, 1
0x140003d75  jz      short loc_140003D85
0x140003d77  cmp     ecx, 1
0x140003d7a  jnz     short loc_140003DDC
0x140003d7c  mov     ecx, edi; this
0x140003d7e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140003d83  jmp     short loc_140003DDA
0x140003d85  test    edi, edi
0x140003d87  js      short loc_140003DC1
0x140003d89  mov     rax, [rsp+78h+arg_28]
0x140003d91  mov     edi, 8007029Ch
0x140003d96  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x140003d9a  mov     rcx, r10; int
0x140003d9d  mov     [rsp+78h+var_50], rax; __int64
0x140003da2  mov     rax, [rsp+78h+arg_20]
0x140003daa  mov     [rsp+78h+var_58], rax; __int64
0x140003daf  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140003db4  mov     ecx, edi; this
0x140003db6  mov     [rbx+8], edi
0x140003db9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140003dbe  mov     [rbx+0Ch], eax
0x140003dc1  mov     ecx, edi; this
0x140003dc3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140003dc8  jmp     short loc_140003DDA
0x140003dca  mov     ecx, edi; this
0x140003dcc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140003dd1  jmp     short loc_140003DDA
0x140003dd3  mov     ecx, edi; this
0x140003dd5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140003dda  mov     ebp, eax
0x140003ddc  mov     eax, [rsp+78h+arg_70]
0x140003de3  mov     [rbx+4], eax
0x140003de6  mov     [rbx], r15d
0x140003de9  cmp     dword ptr [r14+8], 1
0x140003dee  jnz     short loc_140003DF6
0x140003df0  or      eax, 8
0x140003df3  mov     [rbx+4], eax
0x140003df6  mov     eax, 1
0x140003dfb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140003e03  inc     eax
0x140003e05  xor     edi, edi
0x140003e07  mov     [rbx+10h], eax
0x140003e0a  mov     rax, [rsp+78h+arg_40]
0x140003e12  test    rax, rax
0x140003e15  jz      short loc_140003E1C
0x140003e17  cmp     [rax], di
0x140003e1a  jnz     short loc_140003E1F
0x140003e1c  mov     rax, rdi
0x140003e1f  mov     [rbx+18h], rax
0x140003e23  call    cs:__imp_GetCurrentThreadId
0x140003e29  mov     [rbx+38h], r13
0x140003e2d  xorps   xmm0, xmm0
0x140003e30  mov     [rbx+20h], eax
0x140003e33  mov     eax, [rsp+78h+arg_8]
0x140003e3a  mov     [rbx+40h], eax
0x140003e3d  mov     rax, [rsp+78h+arg_20]
0x140003e45  mov     [rbx+28h], rax
0x140003e49  mov     rax, [rsp+78h+arg_28]
0x140003e51  mov     [rbx+88h], rax
0x140003e58  mov     rax, [rsp+78h+arg_0]
0x140003e60  mov     [rbx+90h], rax
0x140003e67  xor     eax, eax
0x140003e69  mov     [rbx+44h], ebp
0x140003e6c  mov     [rbx+30h], r12
0x140003e70  mov     [rbx+48h], rdi
0x140003e74  movups  xmmword ptr [rbx+68h], xmm0
0x140003e78  mov     [rbx+78h], rax
0x140003e7c  movups  xmmword ptr [rbx+50h], xmm0
0x140003e80  mov     [rbx+60h], rax
0x140003e84  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140003e8b  test    rax, rax
0x140003e8e  jz      short loc_140003E97
0x140003e90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003e95  jmp     short loc_140003E9A
0x140003e97  mov     rax, rdi
0x140003e9a  mov     [rbx+80h], rax
0x140003ea1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140003ea8  test    rax, rax
0x140003eab  jz      short loc_140003EB5
0x140003ead  mov     rcx, rbx
0x140003eb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003eb5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140003ebc  test    rax, rax
0x140003ebf  jz      short loc_140003ED7
0x140003ec1  mov     rdx, [rsp+78h+arg_60]
0x140003ec9  mov     r8d, 400h
0x140003ecf  mov     rcx, rbx
0x140003ed2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003ed7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140003ede  test    rax, rax
0x140003ee1  jz      short loc_140003EEB
0x140003ee3  mov     rcx, rbx
0x140003ee6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003eeb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140003ef2  test    rax, rax
0x140003ef5  jz      short loc_140003F05
0x140003ef7  test    byte ptr [rbx+4], 2
0x140003efb  jnz     short loc_140003F05
0x140003efd  mov     rcx, rbx
0x140003f00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003f05  cmp     [rbx+8], edi
0x140003f08  jl      short loc_140003F24
0x140003f0a  cmp     r15d, 3
0x140003f0e  jnz     loc_140003FF2
0x140003f14  mov     ecx, 8000FFFFh; this
0x140003f19  mov     [rbx+8], ecx
0x140003f1c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140003f21  mov     [rbx+0Ch], eax
0x140003f24  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x140003f2b  jnz     short loc_140003F4C
0x140003f2d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140003f34  test    rax, rax
0x140003f37  jz      short loc_140003F42
0x140003f39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003f3e  test    al, al
0x140003f40  jmp     short loc_140003F4A
0x140003f42  call    cs:__imp_IsDebuggerPresent
0x140003f48  test    eax, eax
0x140003f4a  jz      short loc_140003F52
0x140003f4c  test    byte ptr [rbx+4], 2
0x140003f50  jz      short loc_140003F76
0x140003f52  mov     rax, cs:g_pfnResultLoggingCallback
0x140003f59  test    rax, rax
0x140003f5c  jz      short loc_140003FBA
0x140003f5e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140003f65  jnz     short loc_140003FBA
0x140003f67  xor     r8d, r8d
0x140003f6a  xor     edx, edx
0x140003f6c  mov     rcx, rbx
0x140003f6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003f74  jmp     short loc_140003FBA
0x140003f76  mov     rax, cs:g_pfnResultLoggingCallback
0x140003f7d  mov     ebp, 800h
0x140003f82  test    rax, rax
0x140003f85  jz      short loc_140003F9E
0x140003f87  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140003f8e  jnz     short loc_140003F9E
0x140003f90  mov     r8d, ebp
0x140003f93  mov     rdx, rsi
0x140003f96  mov     rcx, rbx
0x140003f99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003f9e  cmp     [rsi], di
0x140003fa1  jnz     short loc_140003FB1
0x140003fa3  mov     r8, rbx; unsigned __int64
0x140003fa6  mov     rdx, rbp; unsigned __int16 *
0x140003fa9  mov     rcx, rsi; this
0x140003fac  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140003fb1  mov     rcx, rsi; lpOutputString
0x140003fb4  call    cs:__imp_OutputDebugStringW
0x140003fba  test    byte ptr [rbx+4], 4
0x140003fbe  jnz     short loc_140003FC9
0x140003fc0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x140003fc7  jz      short loc_140003FDA
0x140003fc9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140003fd0  test    rax, rax
0x140003fd3  jz      short loc_140003FDA
0x140003fd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003fda  mov     rbx, [rsp+78h+arg_10]
0x140003fe2  add     rsp, 40h
0x140003fe6  pop     r15
0x140003fe8  pop     r14
0x140003fea  pop     r13
0x140003fec  pop     r12
0x140003fee  pop     rdi
0x140003fef  pop     rsi
0x140003ff0  pop     rbp
0x140003ff1  retn
0x140003ff2  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
