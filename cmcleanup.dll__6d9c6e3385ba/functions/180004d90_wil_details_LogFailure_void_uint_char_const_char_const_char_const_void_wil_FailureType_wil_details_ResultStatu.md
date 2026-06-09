# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180004d90`
- end: `0x180005089`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800029e4`

## callees

- `0x180002428`
- `0x180004314`
- `0x180004b64`
- `0x180004d90`
- `0x180005534`
- `0x180005550`
- `0x180005564`
- `0x180005580`
- `0x1800078b4`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004eb3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004eb3`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005044`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005044`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004fd2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004fd2`

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
  _WORD *v21; // rax
  wil::details::in1diag3 *v22; // rcx
  const struct wil::FailureInfo *v23; // r9
  __int64 ModuleName; // rax
  bool v25; // zf
  wil::details *v26; // [rsp+30h] [rbp-48h]

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
          LODWORD(v26) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v26);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL);
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
  v21 = a9;
  if ( !a9 || !*a9 )
    v21 = 0;
  *(_QWORD *)(a16 + 24) = v21;
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
    ModuleName = wil::details::g_pfnGetModuleName(v22);
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v25 = !IsDebuggerPresent())
      : (v25 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v22) == 0),
        v25)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v23);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v22);
  }
}

```

## disassembly

```asm
0x180004d90  mov     [rsp+arg_10], rbx
0x180004d95  mov     [rsp+arg_8], edx
0x180004d99  mov     [rsp+arg_0], rcx
0x180004d9e  push    rbp
0x180004d9f  push    rsi
0x180004da0  push    rdi
0x180004da1  push    r12
0x180004da3  push    r13
0x180004da5  push    r14
0x180004da7  push    r15
0x180004da9  sub     rsp, 40h
0x180004dad  mov     r12, r9
0x180004db0  mov     r13, r8
0x180004db3  mov     r10, rcx
0x180004db6  xor     eax, eax
0x180004db8  mov     rsi, [rsp+78h+lpOutputString]
0x180004dc0  mov     [rsi], ax
0x180004dc3  mov     rax, [rsp+78h+arg_60]
0x180004dcb  mov     byte ptr [rax], 0
0x180004dce  mov     r14, [rsp+78h+arg_38]
0x180004dd6  mov     edi, [r14]
0x180004dd9  mov     rbx, [rsp+78h+arg_78]
0x180004de1  mov     [rbx+8], edi
0x180004de4  mov     eax, [r14+4]
0x180004de8  mov     [rbx+0Ch], eax
0x180004deb  xor     ebp, ebp
0x180004ded  mov     r15d, [rsp+78h+arg_30]
0x180004df5  mov     ecx, r15d
0x180004df8  test    r15d, r15d
0x180004dfb  jz      short loc_180004E63
0x180004dfd  sub     ecx, 1
0x180004e00  jz      short loc_180004E5A
0x180004e02  sub     ecx, 1
0x180004e05  jz      short loc_180004E15
0x180004e07  cmp     ecx, 1
0x180004e0a  jnz     short loc_180004E6C
0x180004e0c  mov     ecx, edi; this
0x180004e0e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180004e13  jmp     short loc_180004E6A
0x180004e15  test    edi, edi
0x180004e17  js      short loc_180004E51
0x180004e19  mov     edi, 8007029Ch
0x180004e1e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180004e22  mov     rax, [rsp+78h+arg_28]
0x180004e2a  mov     [rsp+78h+var_50], rax; __int64
0x180004e2f  mov     rax, [rsp+78h+arg_20]
0x180004e37  mov     [rsp+78h+var_58], rax; __int64
0x180004e3c  mov     rcx, r10; int
0x180004e3f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180004e44  mov     [rbx+8], edi
0x180004e47  mov     ecx, edi; this
0x180004e49  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004e4e  mov     [rbx+0Ch], eax
0x180004e51  mov     ecx, edi; this
0x180004e53  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180004e58  jmp     short loc_180004E6A
0x180004e5a  mov     ecx, edi; this
0x180004e5c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004e61  jmp     short loc_180004E6A
0x180004e63  mov     ecx, edi; this
0x180004e65  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180004e6a  mov     ebp, eax
0x180004e6c  mov     [rbx], r15d
0x180004e6f  mov     eax, [rsp+78h+arg_70]
0x180004e76  mov     [rbx+4], eax
0x180004e79  cmp     dword ptr [r14+8], 1
0x180004e7e  jnz     short loc_180004E86
0x180004e80  or      eax, 8
0x180004e83  mov     [rbx+4], eax
0x180004e86  mov     eax, 1
0x180004e8b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004e93  inc     eax
0x180004e95  mov     [rbx+10h], eax
0x180004e98  mov     rax, [rsp+78h+arg_40]
0x180004ea0  xor     edi, edi
0x180004ea2  test    rax, rax
0x180004ea5  jz      short loc_180004EAC
0x180004ea7  cmp     [rax], di
0x180004eaa  jnz     short loc_180004EAF
0x180004eac  mov     rax, rdi
0x180004eaf  mov     [rbx+18h], rax
0x180004eb3  call    cs:__imp_GetCurrentThreadId
0x180004eb9  mov     [rbx+20h], eax
0x180004ebc  mov     [rbx+38h], r13
0x180004ec0  mov     eax, [rsp+78h+arg_8]
0x180004ec7  mov     [rbx+40h], eax
0x180004eca  mov     [rbx+44h], ebp
0x180004ecd  mov     rax, [rsp+78h+arg_20]
0x180004ed5  mov     [rbx+28h], rax
0x180004ed9  mov     [rbx+30h], r12
0x180004edd  mov     rax, [rsp+78h+arg_28]
0x180004ee5  mov     [rbx+88h], rax
0x180004eec  mov     rax, [rsp+78h+arg_0]
0x180004ef4  mov     [rbx+90h], rax
0x180004efb  mov     [rbx+48h], rdi
0x180004eff  xorps   xmm0, xmm0
0x180004f02  xor     eax, eax
0x180004f04  movups  xmmword ptr [rbx+68h], xmm0
0x180004f08  mov     [rbx+78h], rax
0x180004f0c  movups  xmmword ptr [rbx+50h], xmm0
0x180004f10  mov     [rbx+60h], rax
0x180004f14  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004f1b  test    rax, rax
0x180004f1e  jz      short loc_180004F27
0x180004f20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f25  jmp     short loc_180004F2A
0x180004f27  mov     rax, rdi
0x180004f2a  mov     [rbx+80h], rax
0x180004f31  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004f38  test    rax, rax
0x180004f3b  jz      short loc_180004F45
0x180004f3d  mov     rcx, rbx
0x180004f40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f45  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004f4c  test    rax, rax
0x180004f4f  jz      short loc_180004F67
0x180004f51  mov     r8d, 400h
0x180004f57  mov     rdx, [rsp+78h+arg_60]
0x180004f5f  mov     rcx, rbx
0x180004f62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f67  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004f6e  test    rax, rax
0x180004f71  jz      short loc_180004F7B
0x180004f73  mov     rcx, rbx
0x180004f76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f7b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004f82  test    rax, rax
0x180004f85  jz      short loc_180004F95
0x180004f87  test    byte ptr [rbx+4], 2
0x180004f8b  jnz     short loc_180004F95
0x180004f8d  mov     rcx, rbx
0x180004f90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f95  cmp     [rbx+8], edi
0x180004f98  jl      short loc_180004FB4
0x180004f9a  cmp     r15d, 3
0x180004f9e  jnz     loc_180005083
0x180004fa4  mov     ecx, 8000FFFFh; this
0x180004fa9  mov     [rbx+8], ecx
0x180004fac  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004fb1  mov     [rbx+0Ch], eax
0x180004fb4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180004fbb  jnz     short loc_180004FDC
0x180004fbd  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004fc4  test    rax, rax
0x180004fc7  jz      short loc_180004FD2
0x180004fc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fce  test    al, al
0x180004fd0  jmp     short loc_180004FDA
0x180004fd2  call    cs:__imp_IsDebuggerPresent
0x180004fd8  test    eax, eax
0x180004fda  jz      short loc_180004FE2
0x180004fdc  test    byte ptr [rbx+4], 2
0x180004fe0  jz      short loc_180005006
0x180004fe2  mov     rax, cs:g_pfnResultLoggingCallback
0x180004fe9  test    rax, rax
0x180004fec  jz      short loc_18000504A
0x180004fee  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180004ff5  jnz     short loc_18000504A
0x180004ff7  xor     r8d, r8d
0x180004ffa  xor     edx, edx
0x180004ffc  mov     rcx, rbx
0x180004fff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005004  jmp     short loc_18000504A
0x180005006  mov     ebp, 800h
0x18000500b  mov     rax, cs:g_pfnResultLoggingCallback
0x180005012  test    rax, rax
0x180005015  jz      short loc_18000502E
0x180005017  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000501e  jnz     short loc_18000502E
0x180005020  mov     r8d, ebp
0x180005023  mov     rdx, rsi
0x180005026  mov     rcx, rbx
0x180005029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000502e  cmp     [rsi], di
0x180005031  jnz     short loc_180005041
0x180005033  mov     r8, rbx; unsigned __int64
0x180005036  mov     rdx, rbp; unsigned __int16 *
0x180005039  mov     rcx, rsi; this
0x18000503c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005041  mov     rcx, rsi; lpOutputString
0x180005044  call    cs:__imp_OutputDebugStringW
0x18000504a  test    byte ptr [rbx+4], 4
0x18000504e  jnz     short loc_180005059
0x180005050  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180005057  jz      short loc_18000506B
0x180005059  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005060  test    rax, rax
0x180005063  jz      short loc_18000506B
0x180005065  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000506a  nop
0x18000506b  mov     rbx, [rsp+78h+arg_10]
0x180005073  add     rsp, 40h
0x180005077  pop     r15
0x180005079  pop     r14
0x18000507b  pop     r13
0x18000507d  pop     r12
0x18000507f  pop     rdi
0x180005080  pop     rsi
0x180005081  pop     rbp
0x180005082  retn
0x180005083  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
