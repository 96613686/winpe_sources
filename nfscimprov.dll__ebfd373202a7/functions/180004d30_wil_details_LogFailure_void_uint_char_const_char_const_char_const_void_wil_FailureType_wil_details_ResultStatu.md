# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180004d30`
- end: `0x180005029`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180002ba0`

## callees

- `0x1800025dc`
- `0x1800041c4`
- `0x180004a30`
- `0x180004d30`
- `0x18000595c`
- `0x180005980`
- `0x180005b04`
- `0x180005b20`
- `0x18000766c`
- `0x180037010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180004e53`
- `KERNEL32!GetCurrentThreadId` at `0x180004e53`
- `KERNEL32!OutputDebugStringW` at `0x180004fe4`
- `KERNEL32!OutputDebugStringW` at `0x180004fe4`
- `KERNEL32!IsDebuggerPresent` at `0x180004f72`
- `KERNEL32!IsDebuggerPresent` at `0x180004f72`

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
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v25);
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
0x180004d30  mov     [rsp+arg_10], rbx
0x180004d35  mov     [rsp+arg_8], edx
0x180004d39  mov     [rsp+arg_0], rcx
0x180004d3e  push    rbp
0x180004d3f  push    rsi
0x180004d40  push    rdi
0x180004d41  push    r12
0x180004d43  push    r13
0x180004d45  push    r14
0x180004d47  push    r15
0x180004d49  sub     rsp, 40h
0x180004d4d  mov     r12, r9
0x180004d50  mov     r13, r8
0x180004d53  mov     r10, rcx
0x180004d56  xor     eax, eax
0x180004d58  mov     rsi, [rsp+78h+lpOutputString]
0x180004d60  mov     [rsi], ax
0x180004d63  mov     rax, [rsp+78h+arg_60]
0x180004d6b  mov     byte ptr [rax], 0
0x180004d6e  mov     r14, [rsp+78h+arg_38]
0x180004d76  mov     edi, [r14]
0x180004d79  mov     rbx, [rsp+78h+arg_78]
0x180004d81  mov     [rbx+8], edi
0x180004d84  mov     eax, [r14+4]
0x180004d88  mov     [rbx+0Ch], eax
0x180004d8b  xor     ebp, ebp
0x180004d8d  mov     r15d, [rsp+78h+arg_30]
0x180004d95  mov     ecx, r15d
0x180004d98  test    r15d, r15d
0x180004d9b  jz      short loc_180004E03
0x180004d9d  sub     ecx, 1
0x180004da0  jz      short loc_180004DFA
0x180004da2  sub     ecx, 1
0x180004da5  jz      short loc_180004DB5
0x180004da7  cmp     ecx, 1
0x180004daa  jnz     short loc_180004E0C
0x180004dac  mov     ecx, edi; this
0x180004dae  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180004db3  jmp     short loc_180004E0A
0x180004db5  test    edi, edi
0x180004db7  js      short loc_180004DF1
0x180004db9  mov     edi, 8007029Ch
0x180004dbe  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180004dc2  mov     rax, [rsp+78h+arg_28]
0x180004dca  mov     [rsp+78h+var_50], rax; __int64
0x180004dcf  mov     rax, [rsp+78h+arg_20]
0x180004dd7  mov     [rsp+78h+var_58], rax; __int64
0x180004ddc  mov     rcx, r10; int
0x180004ddf  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180004de4  mov     [rbx+8], edi
0x180004de7  mov     ecx, edi; this
0x180004de9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004dee  mov     [rbx+0Ch], eax
0x180004df1  mov     ecx, edi; this
0x180004df3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180004df8  jmp     short loc_180004E0A
0x180004dfa  mov     ecx, edi; this
0x180004dfc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004e01  jmp     short loc_180004E0A
0x180004e03  mov     ecx, edi; this
0x180004e05  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180004e0a  mov     ebp, eax
0x180004e0c  mov     [rbx], r15d
0x180004e0f  mov     eax, [rsp+78h+arg_70]
0x180004e16  mov     [rbx+4], eax
0x180004e19  cmp     dword ptr [r14+8], 1
0x180004e1e  jnz     short loc_180004E26
0x180004e20  or      eax, 8
0x180004e23  mov     [rbx+4], eax
0x180004e26  mov     eax, 1
0x180004e2b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004e33  inc     eax
0x180004e35  mov     [rbx+10h], eax
0x180004e38  mov     rax, [rsp+78h+arg_40]
0x180004e40  xor     edi, edi
0x180004e42  test    rax, rax
0x180004e45  jz      short loc_180004E4C
0x180004e47  cmp     [rax], di
0x180004e4a  jnz     short loc_180004E4F
0x180004e4c  mov     rax, rdi
0x180004e4f  mov     [rbx+18h], rax
0x180004e53  call    cs:__imp_GetCurrentThreadId
0x180004e59  mov     [rbx+20h], eax
0x180004e5c  mov     [rbx+38h], r13
0x180004e60  mov     eax, [rsp+78h+arg_8]
0x180004e67  mov     [rbx+40h], eax
0x180004e6a  mov     [rbx+44h], ebp
0x180004e6d  mov     rax, [rsp+78h+arg_20]
0x180004e75  mov     [rbx+28h], rax
0x180004e79  mov     [rbx+30h], r12
0x180004e7d  mov     rax, [rsp+78h+arg_28]
0x180004e85  mov     [rbx+88h], rax
0x180004e8c  mov     rax, [rsp+78h+arg_0]
0x180004e94  mov     [rbx+90h], rax
0x180004e9b  mov     [rbx+48h], rdi
0x180004e9f  xorps   xmm0, xmm0
0x180004ea2  xor     eax, eax
0x180004ea4  movups  xmmword ptr [rbx+68h], xmm0
0x180004ea8  mov     [rbx+78h], rax
0x180004eac  movups  xmmword ptr [rbx+50h], xmm0
0x180004eb0  mov     [rbx+60h], rax
0x180004eb4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004ebb  test    rax, rax
0x180004ebe  jz      short loc_180004EC7
0x180004ec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ec5  jmp     short loc_180004ECA
0x180004ec7  mov     rax, rdi
0x180004eca  mov     [rbx+80h], rax
0x180004ed1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004ed8  test    rax, rax
0x180004edb  jz      short loc_180004EE5
0x180004edd  mov     rcx, rbx
0x180004ee0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ee5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004eec  test    rax, rax
0x180004eef  jz      short loc_180004F07
0x180004ef1  mov     r8d, 400h
0x180004ef7  mov     rdx, [rsp+78h+arg_60]
0x180004eff  mov     rcx, rbx
0x180004f02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f07  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004f0e  test    rax, rax
0x180004f11  jz      short loc_180004F1B
0x180004f13  mov     rcx, rbx
0x180004f16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f1b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004f22  test    rax, rax
0x180004f25  jz      short loc_180004F35
0x180004f27  test    byte ptr [rbx+4], 2
0x180004f2b  jnz     short loc_180004F35
0x180004f2d  mov     rcx, rbx
0x180004f30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f35  cmp     [rbx+8], edi
0x180004f38  jl      short loc_180004F54
0x180004f3a  cmp     r15d, 3
0x180004f3e  jnz     loc_180005023
0x180004f44  mov     ecx, 8000FFFFh; this
0x180004f49  mov     [rbx+8], ecx
0x180004f4c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004f51  mov     [rbx+0Ch], eax
0x180004f54  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180004f5b  jnz     short loc_180004F7C
0x180004f5d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004f64  test    rax, rax
0x180004f67  jz      short loc_180004F72
0x180004f69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f6e  test    al, al
0x180004f70  jmp     short loc_180004F7A
0x180004f72  call    cs:__imp_IsDebuggerPresent
0x180004f78  test    eax, eax
0x180004f7a  jz      short loc_180004F82
0x180004f7c  test    byte ptr [rbx+4], 2
0x180004f80  jz      short loc_180004FA6
0x180004f82  mov     rax, cs:g_pfnResultLoggingCallback
0x180004f89  test    rax, rax
0x180004f8c  jz      short loc_180004FEA
0x180004f8e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180004f95  jnz     short loc_180004FEA
0x180004f97  xor     r8d, r8d
0x180004f9a  xor     edx, edx
0x180004f9c  mov     rcx, rbx
0x180004f9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fa4  jmp     short loc_180004FEA
0x180004fa6  mov     ebp, 800h
0x180004fab  mov     rax, cs:g_pfnResultLoggingCallback
0x180004fb2  test    rax, rax
0x180004fb5  jz      short loc_180004FCE
0x180004fb7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180004fbe  jnz     short loc_180004FCE
0x180004fc0  mov     r8d, ebp
0x180004fc3  mov     rdx, rsi
0x180004fc6  mov     rcx, rbx
0x180004fc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fce  cmp     [rsi], di
0x180004fd1  jnz     short loc_180004FE1
0x180004fd3  mov     r8, rbx; unsigned __int64
0x180004fd6  mov     rdx, rbp; unsigned __int16 *
0x180004fd9  mov     rcx, rsi; this
0x180004fdc  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004fe1  mov     rcx, rsi; lpOutputString
0x180004fe4  call    cs:__imp_OutputDebugStringW
0x180004fea  test    byte ptr [rbx+4], 4
0x180004fee  jnz     short loc_180004FF9
0x180004ff0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180004ff7  jz      short loc_18000500B
0x180004ff9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005000  test    rax, rax
0x180005003  jz      short loc_18000500B
0x180005005  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000500a  nop
0x18000500b  mov     rbx, [rsp+78h+arg_10]
0x180005013  add     rsp, 40h
0x180005017  pop     r15
0x180005019  pop     r14
0x18000501b  pop     r13
0x18000501d  pop     r12
0x18000501f  pop     rdi
0x180005020  pop     rsi
0x180005021  pop     rbp
0x180005022  retn
0x180005023  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
