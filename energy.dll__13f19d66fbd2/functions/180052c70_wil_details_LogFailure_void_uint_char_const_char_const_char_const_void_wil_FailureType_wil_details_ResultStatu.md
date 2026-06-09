# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180052c70`
- end: `0x180052f65`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180050664`
- `0x180050714`
- `0x180050808`

## callees

- `0x18004aa10`
- `0x1800505b8`
- `0x180051fb4`
- `0x180052c70`
- `0x180053c14`
- `0x180053c30`
- `0x180053cec`
- `0x180053d08`
- `0x1800554e0`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180052d93`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180052d93`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180052eb4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180052eb4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180052f26`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180052f26`

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
        WCHAR *lpOutputString,
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

  *lpOutputString = 0;
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
    ModuleName = wil::details::g_pfnGetModuleName();
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
      : (v27 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
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
    if ( !*lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v25);
    OutputDebugStringW(lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak();
  }
}

```

## disassembly

```asm
0x180052c70  mov     [rsp+arg_10], rbx
0x180052c75  mov     [rsp+arg_8], edx
0x180052c79  mov     [rsp+arg_0], rcx
0x180052c7e  push    rbp
0x180052c7f  push    rsi
0x180052c80  push    rdi
0x180052c81  push    r12
0x180052c83  push    r13
0x180052c85  push    r14
0x180052c87  push    r15
0x180052c89  sub     rsp, 40h
0x180052c8d  mov     r12, r9
0x180052c90  mov     r13, r8
0x180052c93  mov     r10, rcx
0x180052c96  xor     eax, eax
0x180052c98  mov     rsi, [rsp+78h+lpOutputString]
0x180052ca0  mov     [rsi], ax
0x180052ca3  mov     rax, [rsp+78h+arg_60]
0x180052cab  mov     byte ptr [rax], 0
0x180052cae  mov     r14, [rsp+78h+arg_38]
0x180052cb6  mov     edi, [r14]
0x180052cb9  mov     rbx, [rsp+78h+arg_78]
0x180052cc1  mov     [rbx+8], edi
0x180052cc4  mov     eax, [r14+4]
0x180052cc8  mov     [rbx+0Ch], eax
0x180052ccb  xor     ebp, ebp
0x180052ccd  mov     r15d, [rsp+78h+arg_30]
0x180052cd5  mov     ecx, r15d
0x180052cd8  test    r15d, r15d
0x180052cdb  jz      short loc_180052D43
0x180052cdd  sub     ecx, 1
0x180052ce0  jz      short loc_180052D3A
0x180052ce2  sub     ecx, 1
0x180052ce5  jz      short loc_180052CF5
0x180052ce7  cmp     ecx, 1
0x180052cea  jnz     short loc_180052D4C
0x180052cec  mov     ecx, edi; this
0x180052cee  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180052cf3  jmp     short loc_180052D4A
0x180052cf5  test    edi, edi
0x180052cf7  js      short loc_180052D31
0x180052cf9  mov     edi, 8007029Ch
0x180052cfe  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180052d02  mov     rax, [rsp+78h+arg_28]
0x180052d0a  mov     [rsp+78h+var_50], rax; __int64
0x180052d0f  mov     rax, [rsp+78h+arg_20]
0x180052d17  mov     [rsp+78h+var_58], rax; __int64
0x180052d1c  mov     rcx, r10; int
0x180052d1f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180052d24  mov     [rbx+8], edi
0x180052d27  mov     ecx, edi; this
0x180052d29  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180052d2e  mov     [rbx+0Ch], eax
0x180052d31  mov     ecx, edi; this
0x180052d33  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180052d38  jmp     short loc_180052D4A
0x180052d3a  mov     ecx, edi; this
0x180052d3c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180052d41  jmp     short loc_180052D4A
0x180052d43  mov     ecx, edi; this
0x180052d45  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180052d4a  mov     ebp, eax
0x180052d4c  mov     [rbx], r15d
0x180052d4f  mov     eax, [rsp+78h+arg_70]
0x180052d56  mov     [rbx+4], eax
0x180052d59  cmp     dword ptr [r14+8], 1
0x180052d5e  jnz     short loc_180052D66
0x180052d60  or      eax, 8
0x180052d63  mov     [rbx+4], eax
0x180052d66  mov     eax, 1
0x180052d6b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180052d73  inc     eax
0x180052d75  mov     [rbx+10h], eax
0x180052d78  mov     rax, [rsp+78h+arg_40]
0x180052d80  xor     edi, edi
0x180052d82  test    rax, rax
0x180052d85  jz      short loc_180052D8C
0x180052d87  cmp     [rax], di
0x180052d8a  jnz     short loc_180052D8F
0x180052d8c  mov     rax, rdi
0x180052d8f  mov     [rbx+18h], rax
0x180052d93  call    cs:__imp_GetCurrentThreadId
0x180052d99  mov     [rbx+20h], eax
0x180052d9c  mov     [rbx+38h], r13
0x180052da0  mov     eax, [rsp+78h+arg_8]
0x180052da7  mov     [rbx+40h], eax
0x180052daa  mov     [rbx+44h], ebp
0x180052dad  mov     rax, [rsp+78h+arg_20]
0x180052db5  mov     [rbx+28h], rax
0x180052db9  mov     [rbx+30h], r12
0x180052dbd  mov     rax, [rsp+78h+arg_28]
0x180052dc5  mov     [rbx+88h], rax
0x180052dcc  mov     rax, [rsp+78h+arg_0]
0x180052dd4  mov     [rbx+90h], rax
0x180052ddb  mov     [rbx+48h], rdi
0x180052ddf  xorps   xmm0, xmm0
0x180052de2  xor     eax, eax
0x180052de4  movups  xmmword ptr [rbx+68h], xmm0
0x180052de8  mov     [rbx+78h], rax
0x180052dec  movups  xmmword ptr [rbx+50h], xmm0
0x180052df0  mov     [rbx+60h], rax
0x180052df4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180052dfb  test    rax, rax
0x180052dfe  jz      short loc_180052E07
0x180052e00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052e05  jmp     short loc_180052E0A
0x180052e07  mov     rax, rdi
0x180052e0a  mov     [rbx+80h], rax
0x180052e11  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180052e18  test    rax, rax
0x180052e1b  jz      short loc_180052E25
0x180052e1d  mov     rcx, rbx
0x180052e20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052e25  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180052e2c  test    rax, rax
0x180052e2f  jz      short loc_180052E47
0x180052e31  mov     r8d, 400h
0x180052e37  mov     rdx, [rsp+78h+arg_60]
0x180052e3f  mov     rcx, rbx
0x180052e42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052e47  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180052e4e  test    rax, rax
0x180052e51  jz      short loc_180052E5B
0x180052e53  mov     rcx, rbx
0x180052e56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052e5b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180052e62  test    rax, rax
0x180052e65  jz      short loc_180052E75
0x180052e67  test    byte ptr [rbx+4], 2
0x180052e6b  jnz     short loc_180052E75
0x180052e6d  mov     rcx, rbx
0x180052e70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052e75  cmp     [rbx+8], edi
0x180052e78  jl      short loc_180052E96
0x180052e7a  cmp     r15d, 3
0x180052e7e  jz      short loc_180052E86
0x180052e80  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180052e86  mov     ecx, 8000FFFFh; this
0x180052e8b  mov     [rbx+8], ecx
0x180052e8e  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180052e93  mov     [rbx+0Ch], eax
0x180052e96  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180052e9d  jnz     short loc_180052EBE
0x180052e9f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180052ea6  test    rax, rax
0x180052ea9  jz      short loc_180052EB4
0x180052eab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052eb0  test    al, al
0x180052eb2  jmp     short loc_180052EBC
0x180052eb4  call    cs:__imp_IsDebuggerPresent
0x180052eba  test    eax, eax
0x180052ebc  jz      short loc_180052EC4
0x180052ebe  test    byte ptr [rbx+4], 2
0x180052ec2  jz      short loc_180052EE8
0x180052ec4  mov     rax, cs:g_pfnResultLoggingCallback
0x180052ecb  test    rax, rax
0x180052ece  jz      short loc_180052F2C
0x180052ed0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180052ed7  jnz     short loc_180052F2C
0x180052ed9  xor     r8d, r8d
0x180052edc  xor     edx, edx
0x180052ede  mov     rcx, rbx
0x180052ee1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052ee6  jmp     short loc_180052F2C
0x180052ee8  mov     ebp, 800h
0x180052eed  mov     rax, cs:g_pfnResultLoggingCallback
0x180052ef4  test    rax, rax
0x180052ef7  jz      short loc_180052F10
0x180052ef9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180052f00  jnz     short loc_180052F10
0x180052f02  mov     r8d, ebp
0x180052f05  mov     rdx, rsi
0x180052f08  mov     rcx, rbx
0x180052f0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052f10  cmp     [rsi], di
0x180052f13  jnz     short loc_180052F23
0x180052f15  mov     r8, rbx; unsigned __int64
0x180052f18  mov     rdx, rbp; unsigned __int16 *
0x180052f1b  mov     rcx, rsi; pszDest
0x180052f1e  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180052f23  mov     rcx, rsi; lpOutputString
0x180052f26  call    cs:__imp_OutputDebugStringW
0x180052f2c  test    byte ptr [rbx+4], 4
0x180052f30  jnz     short loc_180052F3B
0x180052f32  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180052f39  jz      short loc_180052F4D
0x180052f3b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180052f42  test    rax, rax
0x180052f45  jz      short loc_180052F4D
0x180052f47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052f4c  nop
0x180052f4d  mov     rbx, [rsp+78h+arg_10]
0x180052f55  add     rsp, 40h
0x180052f59  pop     r15
0x180052f5b  pop     r14
0x180052f5d  pop     r13
0x180052f5f  pop     r12
0x180052f61  pop     rdi
0x180052f62  pop     rsi
0x180052f63  pop     rbp
0x180052f64  retn
```
