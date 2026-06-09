# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180004d34`
- end: `0x18000502c`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180003138`
- `0x180003488`

## callees

- `0x180003080`
- `0x180004284`
- `0x180004aa0`
- `0x180004d34`
- `0x1800055cc`
- `0x1800055f0`
- `0x180005604`
- `0x180005620`
- `0x180007074`
- `0x18001c010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x180004f76`
- `KERNEL32!IsDebuggerPresent` at `0x180004f76`
- `KERNEL32!GetCurrentThreadId` at `0x180004e57`
- `KERNEL32!GetCurrentThreadId` at `0x180004e57`
- `KERNEL32!OutputDebugStringW` at `0x180004fe8`
- `KERNEL32!OutputDebugStringW` at `0x180004fe8`

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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v25);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v24);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v28 = !IsDebuggerPresent())
      : (v28 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
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
      wil::details::g_pfnDebugBreak();
  }
}

```

## disassembly

```asm
0x180004d34  mov     [rsp+arg_10], rbx
0x180004d39  mov     [rsp+arg_8], edx
0x180004d3d  mov     [rsp+arg_0], rcx
0x180004d42  push    rbp
0x180004d43  push    rsi
0x180004d44  push    rdi
0x180004d45  push    r12
0x180004d47  push    r13
0x180004d49  push    r14
0x180004d4b  push    r15
0x180004d4d  sub     rsp, 40h
0x180004d51  mov     r14, [rsp+78h+arg_38]
0x180004d59  xor     eax, eax
0x180004d5b  mov     rbx, [rsp+78h+arg_78]
0x180004d63  xor     ebp, ebp
0x180004d65  mov     r15d, [rsp+78h+arg_30]
0x180004d6d  mov     r10, rcx
0x180004d70  mov     rsi, [rsp+78h+lpOutputString]
0x180004d78  mov     r12, r9
0x180004d7b  mov     r13, r8
0x180004d7e  mov     ecx, r15d
0x180004d81  mov     [rsi], ax
0x180004d84  mov     rax, [rsp+78h+arg_60]
0x180004d8c  mov     byte ptr [rax], 0
0x180004d8f  mov     edi, [r14]
0x180004d92  mov     [rbx+8], edi
0x180004d95  mov     eax, [r14+4]
0x180004d99  mov     [rbx+0Ch], eax
0x180004d9c  test    r15d, r15d
0x180004d9f  jz      short loc_180004E07
0x180004da1  sub     ecx, 1
0x180004da4  jz      short loc_180004DFE
0x180004da6  sub     ecx, 1
0x180004da9  jz      short loc_180004DB9
0x180004dab  cmp     ecx, 1
0x180004dae  jnz     short loc_180004E10
0x180004db0  mov     ecx, edi; this
0x180004db2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180004db7  jmp     short loc_180004E0E
0x180004db9  test    edi, edi
0x180004dbb  js      short loc_180004DF5
0x180004dbd  mov     rax, [rsp+78h+arg_28]
0x180004dc5  mov     edi, 8007029Ch
0x180004dca  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180004dce  mov     rcx, r10; int
0x180004dd1  mov     [rsp+78h+var_50], rax; __int64
0x180004dd6  mov     rax, [rsp+78h+arg_20]
0x180004dde  mov     [rsp+78h+var_58], rax; __int64
0x180004de3  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180004de8  mov     ecx, edi; this
0x180004dea  mov     [rbx+8], edi
0x180004ded  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004df2  mov     [rbx+0Ch], eax
0x180004df5  mov     ecx, edi; this
0x180004df7  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180004dfc  jmp     short loc_180004E0E
0x180004dfe  mov     ecx, edi; this
0x180004e00  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004e05  jmp     short loc_180004E0E
0x180004e07  mov     ecx, edi; this
0x180004e09  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180004e0e  mov     ebp, eax
0x180004e10  mov     eax, [rsp+78h+arg_70]
0x180004e17  mov     [rbx+4], eax
0x180004e1a  mov     [rbx], r15d
0x180004e1d  cmp     dword ptr [r14+8], 1
0x180004e22  jnz     short loc_180004E2A
0x180004e24  or      eax, 8
0x180004e27  mov     [rbx+4], eax
0x180004e2a  mov     eax, 1
0x180004e2f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004e37  inc     eax
0x180004e39  xor     edi, edi
0x180004e3b  mov     [rbx+10h], eax
0x180004e3e  mov     rax, [rsp+78h+arg_40]
0x180004e46  test    rax, rax
0x180004e49  jz      short loc_180004E50
0x180004e4b  cmp     [rax], di
0x180004e4e  jnz     short loc_180004E53
0x180004e50  mov     rax, rdi
0x180004e53  mov     [rbx+18h], rax
0x180004e57  call    cs:__imp_GetCurrentThreadId
0x180004e5d  mov     [rbx+38h], r13
0x180004e61  xorps   xmm0, xmm0
0x180004e64  mov     [rbx+20h], eax
0x180004e67  mov     eax, [rsp+78h+arg_8]
0x180004e6e  mov     [rbx+40h], eax
0x180004e71  mov     rax, [rsp+78h+arg_20]
0x180004e79  mov     [rbx+28h], rax
0x180004e7d  mov     rax, [rsp+78h+arg_28]
0x180004e85  mov     [rbx+88h], rax
0x180004e8c  mov     rax, [rsp+78h+arg_0]
0x180004e94  mov     [rbx+90h], rax
0x180004e9b  xor     eax, eax
0x180004e9d  mov     [rbx+44h], ebp
0x180004ea0  mov     [rbx+30h], r12
0x180004ea4  mov     [rbx+48h], rdi
0x180004ea8  movups  xmmword ptr [rbx+68h], xmm0
0x180004eac  mov     [rbx+78h], rax
0x180004eb0  movups  xmmword ptr [rbx+50h], xmm0
0x180004eb4  mov     [rbx+60h], rax
0x180004eb8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004ebf  test    rax, rax
0x180004ec2  jz      short loc_180004ECB
0x180004ec4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ec9  jmp     short loc_180004ECE
0x180004ecb  mov     rax, rdi
0x180004ece  mov     [rbx+80h], rax
0x180004ed5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004edc  test    rax, rax
0x180004edf  jz      short loc_180004EE9
0x180004ee1  mov     rcx, rbx
0x180004ee4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ee9  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004ef0  test    rax, rax
0x180004ef3  jz      short loc_180004F0B
0x180004ef5  mov     rdx, [rsp+78h+arg_60]
0x180004efd  mov     r8d, 400h
0x180004f03  mov     rcx, rbx
0x180004f06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f0b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004f12  test    rax, rax
0x180004f15  jz      short loc_180004F1F
0x180004f17  mov     rcx, rbx
0x180004f1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f1f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004f26  test    rax, rax
0x180004f29  jz      short loc_180004F39
0x180004f2b  test    byte ptr [rbx+4], 2
0x180004f2f  jnz     short loc_180004F39
0x180004f31  mov     rcx, rbx
0x180004f34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f39  cmp     [rbx+8], edi
0x180004f3c  jl      short loc_180004F58
0x180004f3e  cmp     r15d, 3
0x180004f42  jnz     loc_180005026
0x180004f48  mov     ecx, 8000FFFFh; this
0x180004f4d  mov     [rbx+8], ecx
0x180004f50  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004f55  mov     [rbx+0Ch], eax
0x180004f58  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180004f5f  jnz     short loc_180004F80
0x180004f61  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004f68  test    rax, rax
0x180004f6b  jz      short loc_180004F76
0x180004f6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f72  test    al, al
0x180004f74  jmp     short loc_180004F7E
0x180004f76  call    cs:__imp_IsDebuggerPresent
0x180004f7c  test    eax, eax
0x180004f7e  jz      short loc_180004F86
0x180004f80  test    byte ptr [rbx+4], 2
0x180004f84  jz      short loc_180004FAA
0x180004f86  mov     rax, cs:g_pfnResultLoggingCallback
0x180004f8d  test    rax, rax
0x180004f90  jz      short loc_180004FEE
0x180004f92  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180004f99  jnz     short loc_180004FEE
0x180004f9b  xor     r8d, r8d
0x180004f9e  xor     edx, edx
0x180004fa0  mov     rcx, rbx
0x180004fa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fa8  jmp     short loc_180004FEE
0x180004faa  mov     rax, cs:g_pfnResultLoggingCallback
0x180004fb1  mov     ebp, 800h
0x180004fb6  test    rax, rax
0x180004fb9  jz      short loc_180004FD2
0x180004fbb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180004fc2  jnz     short loc_180004FD2
0x180004fc4  mov     r8d, ebp
0x180004fc7  mov     rdx, rsi
0x180004fca  mov     rcx, rbx
0x180004fcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fd2  cmp     [rsi], di
0x180004fd5  jnz     short loc_180004FE5
0x180004fd7  mov     r8, rbx; unsigned __int64
0x180004fda  mov     rdx, rbp; unsigned __int16 *
0x180004fdd  mov     rcx, rsi; this
0x180004fe0  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004fe5  mov     rcx, rsi; lpOutputString
0x180004fe8  call    cs:__imp_OutputDebugStringW
0x180004fee  test    byte ptr [rbx+4], 4
0x180004ff2  jnz     short loc_180004FFD
0x180004ff4  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180004ffb  jz      short loc_18000500E
0x180004ffd  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005004  test    rax, rax
0x180005007  jz      short loc_18000500E
0x180005009  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000500e  mov     rbx, [rsp+78h+arg_10]
0x180005016  add     rsp, 40h
0x18000501a  pop     r15
0x18000501c  pop     r14
0x18000501e  pop     r13
0x180005020  pop     r12
0x180005022  pop     rdi
0x180005023  pop     rsi
0x180005024  pop     rbp
0x180005025  retn
0x180005026  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
