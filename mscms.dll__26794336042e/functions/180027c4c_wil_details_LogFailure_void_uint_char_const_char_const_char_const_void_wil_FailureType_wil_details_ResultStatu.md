# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180027c4c`
- end: `0x180027f41`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x180027648`
- `0x180027800`
- `0x180027b50`
- `0x180056d80`

## callees

- `0x180023528`
- `0x180027748`
- `0x18002798c`
- `0x180027c4c`
- `0x180027f50`
- `0x180029fc8`
- `0x18003ab7c`
- `0x180042250`
- `0x180043dec`
- `0x180084010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027d6f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027d6f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180027f02`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180027f02`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180027e90`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180027e90`

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
0x180027c4c  mov     [rsp+arg_10], rbx
0x180027c51  mov     [rsp+arg_8], edx
0x180027c55  mov     [rsp+arg_0], rcx
0x180027c5a  push    rbp
0x180027c5b  push    rsi
0x180027c5c  push    rdi
0x180027c5d  push    r12
0x180027c5f  push    r13
0x180027c61  push    r14
0x180027c63  push    r15
0x180027c65  sub     rsp, 40h
0x180027c69  mov     r12, r9
0x180027c6c  mov     r13, r8
0x180027c6f  mov     r10, rcx
0x180027c72  xor     eax, eax
0x180027c74  mov     rsi, [rsp+78h+lpOutputString]
0x180027c7c  mov     [rsi], ax
0x180027c7f  mov     rax, [rsp+78h+arg_60]
0x180027c87  mov     byte ptr [rax], 0
0x180027c8a  mov     r14, [rsp+78h+arg_38]
0x180027c92  mov     edi, [r14]
0x180027c95  mov     rbx, [rsp+78h+arg_78]
0x180027c9d  mov     [rbx+8], edi
0x180027ca0  mov     eax, [r14+4]
0x180027ca4  mov     [rbx+0Ch], eax
0x180027ca7  xor     ebp, ebp
0x180027ca9  mov     r15d, [rsp+78h+arg_30]
0x180027cb1  mov     ecx, r15d
0x180027cb4  test    r15d, r15d
0x180027cb7  jz      short loc_180027D1F
0x180027cb9  sub     ecx, 1
0x180027cbc  jz      short loc_180027D16
0x180027cbe  sub     ecx, 1
0x180027cc1  jz      short loc_180027CD1
0x180027cc3  cmp     ecx, 1
0x180027cc6  jnz     short loc_180027D28
0x180027cc8  mov     ecx, edi; this
0x180027cca  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180027ccf  jmp     short loc_180027D26
0x180027cd1  test    edi, edi
0x180027cd3  js      short loc_180027D0D
0x180027cd5  mov     edi, 8007029Ch
0x180027cda  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180027cde  mov     rax, [rsp+78h+arg_28]
0x180027ce6  mov     [rsp+78h+var_50], rax; __int64
0x180027ceb  mov     rax, [rsp+78h+arg_20]
0x180027cf3  mov     [rsp+78h+var_58], rax; __int64
0x180027cf8  mov     rcx, r10; int
0x180027cfb  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180027d00  mov     [rbx+8], edi
0x180027d03  mov     ecx, edi; this
0x180027d05  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180027d0a  mov     [rbx+0Ch], eax
0x180027d0d  mov     ecx, edi; this
0x180027d0f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180027d14  jmp     short loc_180027D26
0x180027d16  mov     ecx, edi; this
0x180027d18  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180027d1d  jmp     short loc_180027D26
0x180027d1f  mov     ecx, edi; this
0x180027d21  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180027d26  mov     ebp, eax
0x180027d28  mov     [rbx], r15d
0x180027d2b  mov     eax, [rsp+78h+arg_70]
0x180027d32  mov     [rbx+4], eax
0x180027d35  cmp     dword ptr [r14+8], 1
0x180027d3a  jnz     short loc_180027D42
0x180027d3c  or      eax, 8
0x180027d3f  mov     [rbx+4], eax
0x180027d42  mov     eax, 1
0x180027d47  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180027d4f  inc     eax
0x180027d51  mov     [rbx+10h], eax
0x180027d54  mov     rax, [rsp+78h+arg_40]
0x180027d5c  xor     edi, edi
0x180027d5e  test    rax, rax
0x180027d61  jz      short loc_180027D68
0x180027d63  cmp     [rax], di
0x180027d66  jnz     short loc_180027D6B
0x180027d68  mov     rax, rdi
0x180027d6b  mov     [rbx+18h], rax
0x180027d6f  call    cs:__imp_GetCurrentThreadId
0x180027d75  mov     [rbx+20h], eax
0x180027d78  mov     [rbx+38h], r13
0x180027d7c  mov     eax, [rsp+78h+arg_8]
0x180027d83  mov     [rbx+40h], eax
0x180027d86  mov     [rbx+44h], ebp
0x180027d89  mov     rax, [rsp+78h+arg_20]
0x180027d91  mov     [rbx+28h], rax
0x180027d95  mov     [rbx+30h], r12
0x180027d99  mov     rax, [rsp+78h+arg_28]
0x180027da1  mov     [rbx+88h], rax
0x180027da8  mov     rax, [rsp+78h+arg_0]
0x180027db0  mov     [rbx+90h], rax
0x180027db7  mov     [rbx+48h], rdi
0x180027dbb  xorps   xmm0, xmm0
0x180027dbe  xor     eax, eax
0x180027dc0  movups  xmmword ptr [rbx+68h], xmm0
0x180027dc4  mov     [rbx+78h], rax
0x180027dc8  movups  xmmword ptr [rbx+50h], xmm0
0x180027dcc  mov     [rbx+60h], rax
0x180027dd0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180027dd7  test    rax, rax
0x180027dda  jz      short loc_180027DE3
0x180027ddc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027de1  jmp     short loc_180027DE6
0x180027de3  mov     rax, rdi
0x180027de6  mov     [rbx+80h], rax
0x180027ded  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180027df4  test    rax, rax
0x180027df7  jz      short loc_180027E01
0x180027df9  mov     rcx, rbx
0x180027dfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e01  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180027e08  test    rax, rax
0x180027e0b  jz      short loc_180027E23
0x180027e0d  mov     r8d, 400h
0x180027e13  mov     rdx, [rsp+78h+arg_60]
0x180027e1b  mov     rcx, rbx
0x180027e1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e23  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180027e2a  test    rax, rax
0x180027e2d  jz      short loc_180027E37
0x180027e2f  mov     rcx, rbx
0x180027e32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e37  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180027e3e  test    rax, rax
0x180027e41  jz      short loc_180027E51
0x180027e43  test    byte ptr [rbx+4], 2
0x180027e47  jnz     short loc_180027E51
0x180027e49  mov     rcx, rbx
0x180027e4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e51  cmp     [rbx+8], edi
0x180027e54  jl      short loc_180027E72
0x180027e56  cmp     r15d, 3
0x180027e5a  jz      short loc_180027E62
0x180027e5c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180027e62  mov     ecx, 8000FFFFh; this
0x180027e67  mov     [rbx+8], ecx
0x180027e6a  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180027e6f  mov     [rbx+0Ch], eax
0x180027e72  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180027e79  jnz     short loc_180027E9A
0x180027e7b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180027e82  test    rax, rax
0x180027e85  jz      short loc_180027E90
0x180027e87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e8c  test    al, al
0x180027e8e  jmp     short loc_180027E98
0x180027e90  call    cs:__imp_IsDebuggerPresent
0x180027e96  test    eax, eax
0x180027e98  jz      short loc_180027EA0
0x180027e9a  test    byte ptr [rbx+4], 2
0x180027e9e  jz      short loc_180027EC4
0x180027ea0  mov     rax, cs:g_pfnResultLoggingCallback
0x180027ea7  test    rax, rax
0x180027eaa  jz      short loc_180027F08
0x180027eac  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180027eb3  jnz     short loc_180027F08
0x180027eb5  xor     r8d, r8d
0x180027eb8  xor     edx, edx
0x180027eba  mov     rcx, rbx
0x180027ebd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ec2  jmp     short loc_180027F08
0x180027ec4  mov     ebp, 800h
0x180027ec9  mov     rax, cs:g_pfnResultLoggingCallback
0x180027ed0  test    rax, rax
0x180027ed3  jz      short loc_180027EEC
0x180027ed5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180027edc  jnz     short loc_180027EEC
0x180027ede  mov     r8d, ebp
0x180027ee1  mov     rdx, rsi
0x180027ee4  mov     rcx, rbx
0x180027ee7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027eec  cmp     [rsi], di
0x180027eef  jnz     short loc_180027EFF
0x180027ef1  mov     r8, rbx; unsigned __int64
0x180027ef4  mov     rdx, rbp; unsigned __int16 *
0x180027ef7  mov     rcx, rsi; this
0x180027efa  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180027eff  mov     rcx, rsi; lpOutputString
0x180027f02  call    cs:__imp_OutputDebugStringW
0x180027f08  test    byte ptr [rbx+4], 4
0x180027f0c  jnz     short loc_180027F17
0x180027f0e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180027f15  jz      short loc_180027F29
0x180027f17  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180027f1e  test    rax, rax
0x180027f21  jz      short loc_180027F29
0x180027f23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027f28  nop
0x180027f29  mov     rbx, [rsp+78h+arg_10]
0x180027f31  add     rsp, 40h
0x180027f35  pop     r15
0x180027f37  pop     r14
0x180027f39  pop     r13
0x180027f3b  pop     r12
0x180027f3d  pop     rdi
0x180027f3e  pop     rsi
0x180027f3f  pop     rbp
0x180027f40  retn
```
