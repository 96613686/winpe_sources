# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180005d20`
- end: `0x180006028`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `776`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x180003f1c`
- `0x180003fdc`
- `0x1800040dc`
- `0x180007fe4`

## callees

- `0x180003e5c`
- `0x180005284`
- `0x180005a80`
- `0x180005d20`
- `0x1800063e0`
- `0x180006400`
- `0x180006414`
- `0x180006434`
- `0x180007498`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005e43`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005e43`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005fe2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005fe2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005f6a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005f6a`

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
0x180005d20  mov     [rsp+arg_10], rbx
0x180005d25  mov     [rsp+arg_8], edx
0x180005d29  mov     [rsp+arg_0], rcx
0x180005d2e  push    rbp
0x180005d2f  push    rsi
0x180005d30  push    rdi
0x180005d31  push    r12
0x180005d33  push    r13
0x180005d35  push    r14
0x180005d37  push    r15
0x180005d39  sub     rsp, 40h
0x180005d3d  mov     r12, r9
0x180005d40  mov     r13, r8
0x180005d43  mov     r10, rcx
0x180005d46  xor     eax, eax
0x180005d48  mov     rsi, [rsp+78h+lpOutputString]
0x180005d50  mov     [rsi], ax
0x180005d53  mov     rax, [rsp+78h+arg_60]
0x180005d5b  mov     byte ptr [rax], 0
0x180005d5e  mov     r14, [rsp+78h+arg_38]
0x180005d66  mov     edi, [r14]
0x180005d69  mov     rbx, [rsp+78h+arg_78]
0x180005d71  mov     [rbx+8], edi
0x180005d74  mov     eax, [r14+4]
0x180005d78  mov     [rbx+0Ch], eax
0x180005d7b  xor     ebp, ebp
0x180005d7d  mov     r15d, [rsp+78h+arg_30]
0x180005d85  mov     ecx, r15d
0x180005d88  test    r15d, r15d
0x180005d8b  jz      short loc_180005DF3
0x180005d8d  sub     ecx, 1
0x180005d90  jz      short loc_180005DEA
0x180005d92  sub     ecx, 1
0x180005d95  jz      short loc_180005DA5
0x180005d97  cmp     ecx, 1
0x180005d9a  jnz     short loc_180005DFC
0x180005d9c  mov     ecx, edi; this
0x180005d9e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180005da3  jmp     short loc_180005DFA
0x180005da5  test    edi, edi
0x180005da7  js      short loc_180005DE1
0x180005da9  mov     edi, 8007029Ch
0x180005dae  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180005db2  mov     rax, [rsp+78h+arg_28]
0x180005dba  mov     [rsp+78h+var_50], rax; __int64
0x180005dbf  mov     rax, [rsp+78h+arg_20]
0x180005dc7  mov     [rsp+78h+var_58], rax; __int64
0x180005dcc  mov     rcx, r10; int
0x180005dcf  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180005dd4  mov     [rbx+8], edi
0x180005dd7  mov     ecx, edi; this
0x180005dd9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005dde  mov     [rbx+0Ch], eax
0x180005de1  mov     ecx, edi; this
0x180005de3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180005de8  jmp     short loc_180005DFA
0x180005dea  mov     ecx, edi; this
0x180005dec  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005df1  jmp     short loc_180005DFA
0x180005df3  mov     ecx, edi; this
0x180005df5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180005dfa  mov     ebp, eax
0x180005dfc  mov     [rbx], r15d
0x180005dff  mov     eax, [rsp+78h+arg_70]
0x180005e06  mov     [rbx+4], eax
0x180005e09  cmp     dword ptr [r14+8], 1
0x180005e0e  jnz     short loc_180005E16
0x180005e10  or      eax, 8
0x180005e13  mov     [rbx+4], eax
0x180005e16  mov     eax, 1
0x180005e1b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005e23  inc     eax
0x180005e25  mov     [rbx+10h], eax
0x180005e28  mov     rax, [rsp+78h+arg_40]
0x180005e30  xor     edi, edi
0x180005e32  test    rax, rax
0x180005e35  jz      short loc_180005E3C
0x180005e37  cmp     [rax], di
0x180005e3a  jnz     short loc_180005E3F
0x180005e3c  mov     rax, rdi
0x180005e3f  mov     [rbx+18h], rax
0x180005e43  call    cs:__imp_GetCurrentThreadId
0x180005e4a  nop     dword ptr [rax+rax+00h]
0x180005e4f  mov     [rbx+20h], eax
0x180005e52  mov     [rbx+38h], r13
0x180005e56  mov     eax, [rsp+78h+arg_8]
0x180005e5d  mov     [rbx+40h], eax
0x180005e60  mov     [rbx+44h], ebp
0x180005e63  mov     rax, [rsp+78h+arg_20]
0x180005e6b  mov     [rbx+28h], rax
0x180005e6f  mov     [rbx+30h], r12
0x180005e73  mov     rax, [rsp+78h+arg_28]
0x180005e7b  mov     [rbx+88h], rax
0x180005e82  mov     rax, [rsp+78h+arg_0]
0x180005e8a  mov     [rbx+90h], rax
0x180005e91  mov     [rbx+48h], rdi
0x180005e95  xorps   xmm0, xmm0
0x180005e98  xor     eax, eax
0x180005e9a  movups  xmmword ptr [rbx+68h], xmm0
0x180005e9e  mov     [rbx+78h], rax
0x180005ea2  movups  xmmword ptr [rbx+50h], xmm0
0x180005ea6  mov     [rbx+60h], rax
0x180005eaa  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005eb1  test    rax, rax
0x180005eb4  jz      short loc_180005EBD
0x180005eb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ebb  jmp     short loc_180005EC0
0x180005ebd  mov     rax, rdi
0x180005ec0  mov     [rbx+80h], rax
0x180005ec7  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005ece  test    rax, rax
0x180005ed1  jz      short loc_180005EDB
0x180005ed3  mov     rcx, rbx
0x180005ed6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005edb  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005ee2  test    rax, rax
0x180005ee5  jz      short loc_180005EFD
0x180005ee7  mov     r8d, 400h
0x180005eed  mov     rdx, [rsp+78h+arg_60]
0x180005ef5  mov     rcx, rbx
0x180005ef8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005efd  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005f04  test    rax, rax
0x180005f07  jz      short loc_180005F11
0x180005f09  mov     rcx, rbx
0x180005f0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f11  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005f18  test    rax, rax
0x180005f1b  jz      short loc_180005F2B
0x180005f1d  test    byte ptr [rbx+4], 2
0x180005f21  jnz     short loc_180005F2B
0x180005f23  mov     rcx, rbx
0x180005f26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f2b  cmp     [rbx+8], edi
0x180005f2e  jl      short loc_180005F4C
0x180005f30  cmp     r15d, 3
0x180005f34  jz      short loc_180005F3C
0x180005f36  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180005f3c  mov     ecx, 8000FFFFh; this
0x180005f41  mov     [rbx+8], ecx
0x180005f44  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005f49  mov     [rbx+0Ch], eax
0x180005f4c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180005f53  jnz     short loc_180005F7A
0x180005f55  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005f5c  test    rax, rax
0x180005f5f  jz      short loc_180005F6A
0x180005f61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f66  test    al, al
0x180005f68  jmp     short loc_180005F78
0x180005f6a  call    cs:__imp_IsDebuggerPresent
0x180005f71  nop     dword ptr [rax+rax+00h]
0x180005f76  test    eax, eax
0x180005f78  jz      short loc_180005F80
0x180005f7a  test    byte ptr [rbx+4], 2
0x180005f7e  jz      short loc_180005FA4
0x180005f80  mov     rax, cs:g_pfnResultLoggingCallback
0x180005f87  test    rax, rax
0x180005f8a  jz      short loc_180005FEE
0x180005f8c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005f93  jnz     short loc_180005FEE
0x180005f95  xor     r8d, r8d
0x180005f98  xor     edx, edx
0x180005f9a  mov     rcx, rbx
0x180005f9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fa2  jmp     short loc_180005FEE
0x180005fa4  mov     ebp, 800h
0x180005fa9  mov     rax, cs:g_pfnResultLoggingCallback
0x180005fb0  test    rax, rax
0x180005fb3  jz      short loc_180005FCC
0x180005fb5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005fbc  jnz     short loc_180005FCC
0x180005fbe  mov     r8d, ebp
0x180005fc1  mov     rdx, rsi
0x180005fc4  mov     rcx, rbx
0x180005fc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fcc  cmp     [rsi], di
0x180005fcf  jnz     short loc_180005FDF
0x180005fd1  mov     r8, rbx; unsigned __int64
0x180005fd4  mov     rdx, rbp; unsigned __int16 *
0x180005fd7  mov     rcx, rsi; this
0x180005fda  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005fdf  mov     rcx, rsi; lpOutputString
0x180005fe2  call    cs:__imp_OutputDebugStringW
0x180005fe9  nop     dword ptr [rax+rax+00h]
0x180005fee  test    byte ptr [rbx+4], 4
0x180005ff2  jnz     short loc_180005FFD
0x180005ff4  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180005ffb  jz      short loc_18000600F
0x180005ffd  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006004  test    rax, rax
0x180006007  jz      short loc_18000600F
0x180006009  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000600e  nop
0x18000600f  mov     rbx, [rsp+78h+arg_10]
0x180006017  add     rsp, 40h
0x18000601b  pop     r15
0x18000601d  pop     r14
0x18000601f  pop     r13
0x180006021  pop     r12
0x180006023  pop     rdi
0x180006024  pop     rsi
0x180006025  pop     rbp
0x180006026  retn
```
