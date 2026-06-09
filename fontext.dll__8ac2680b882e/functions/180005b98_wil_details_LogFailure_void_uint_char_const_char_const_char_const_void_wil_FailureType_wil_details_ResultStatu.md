# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180005b98`
- end: `0x180005e94`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `764`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1800044a0`
- `0x1800047e4`

## callees

- `0x1800043e0`
- `0x1800051b4`
- `0x1800059d4`
- `0x180005b98`
- `0x1800061c8`
- `0x1800061f0`
- `0x180006204`
- `0x180006220`
- `0x180006c14`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005cbf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005cbf`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005dde`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005dde`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005e50`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005e50`

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
0x180005b98  mov     [rsp+arg_10], rbx
0x180005b9d  mov     [rsp+arg_8], edx
0x180005ba1  mov     [rsp+arg_0], rcx
0x180005ba6  push    rbp
0x180005ba7  push    rsi
0x180005ba8  push    rdi
0x180005ba9  push    r12
0x180005bab  push    r13
0x180005bad  push    r14
0x180005baf  push    r15
0x180005bb1  sub     rsp, 40h
0x180005bb5  mov     r14, [rsp+78h+arg_38]
0x180005bbd  xor     eax, eax
0x180005bbf  mov     rbx, [rsp+78h+arg_78]
0x180005bc7  xor     ebp, ebp
0x180005bc9  mov     r15d, [rsp+78h+arg_30]
0x180005bd1  mov     r10, rcx
0x180005bd4  mov     rsi, [rsp+78h+lpOutputString]
0x180005bdc  mov     r12, r9
0x180005bdf  mov     r13, r8
0x180005be2  mov     ecx, r15d
0x180005be5  mov     [rsi], ax
0x180005be8  mov     rax, [rsp+78h+arg_60]
0x180005bf0  mov     byte ptr [rax], 0
0x180005bf3  mov     edi, [r14]
0x180005bf6  mov     [rbx+8], edi
0x180005bf9  mov     eax, [r14+4]
0x180005bfd  mov     [rbx+0Ch], eax
0x180005c00  test    r15d, r15d
0x180005c03  jz      short loc_180005C6F
0x180005c05  sub     ecx, 1
0x180005c08  jz      short loc_180005C66
0x180005c0a  sub     ecx, 1
0x180005c0d  jz      short loc_180005C1D
0x180005c0f  cmp     ecx, 1
0x180005c12  jnz     short loc_180005C78
0x180005c14  mov     ecx, edi; this
0x180005c16  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180005c1b  jmp     short loc_180005C76
0x180005c1d  test    edi, edi
0x180005c1f  js      short loc_180005C5D
0x180005c21  mov     rax, [rsp+78h+arg_28]
0x180005c29  mov     edi, 8007029Ch
0x180005c2e  mov     [rsp+78h+var_40], ebp
0x180005c32  mov     rcx, r10; int
0x180005c35  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180005c39  mov     [rsp+78h+var_50], rax; __int64
0x180005c3e  mov     rax, [rsp+78h+arg_20]
0x180005c46  mov     [rsp+78h+var_58], rax; __int64
0x180005c4b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180005c50  mov     ecx, edi; this
0x180005c52  mov     [rbx+8], edi
0x180005c55  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005c5a  mov     [rbx+0Ch], eax
0x180005c5d  mov     ecx, edi; this
0x180005c5f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180005c64  jmp     short loc_180005C76
0x180005c66  mov     ecx, edi; this
0x180005c68  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005c6d  jmp     short loc_180005C76
0x180005c6f  mov     ecx, edi; this
0x180005c71  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180005c76  mov     ebp, eax
0x180005c78  mov     eax, [rsp+78h+arg_70]
0x180005c7f  mov     [rbx+4], eax
0x180005c82  mov     [rbx], r15d
0x180005c85  cmp     dword ptr [r14+8], 1
0x180005c8a  jnz     short loc_180005C92
0x180005c8c  or      eax, 8
0x180005c8f  mov     [rbx+4], eax
0x180005c92  mov     eax, 1
0x180005c97  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005c9f  inc     eax
0x180005ca1  xor     edi, edi
0x180005ca3  mov     [rbx+10h], eax
0x180005ca6  mov     rax, [rsp+78h+arg_40]
0x180005cae  test    rax, rax
0x180005cb1  jz      short loc_180005CB8
0x180005cb3  cmp     [rax], di
0x180005cb6  jnz     short loc_180005CBB
0x180005cb8  mov     rax, rdi
0x180005cbb  mov     [rbx+18h], rax
0x180005cbf  call    cs:__imp_GetCurrentThreadId
0x180005cc5  mov     [rbx+38h], r13
0x180005cc9  xorps   xmm0, xmm0
0x180005ccc  mov     [rbx+20h], eax
0x180005ccf  mov     eax, [rsp+78h+arg_8]
0x180005cd6  mov     [rbx+40h], eax
0x180005cd9  mov     rax, [rsp+78h+arg_20]
0x180005ce1  mov     [rbx+28h], rax
0x180005ce5  mov     rax, [rsp+78h+arg_28]
0x180005ced  mov     [rbx+88h], rax
0x180005cf4  mov     rax, [rsp+78h+arg_0]
0x180005cfc  mov     [rbx+90h], rax
0x180005d03  xor     eax, eax
0x180005d05  mov     [rbx+44h], ebp
0x180005d08  mov     [rbx+30h], r12
0x180005d0c  mov     [rbx+48h], rdi
0x180005d10  movups  xmmword ptr [rbx+68h], xmm0
0x180005d14  mov     [rbx+78h], rax
0x180005d18  movups  xmmword ptr [rbx+50h], xmm0
0x180005d1c  mov     [rbx+60h], rax
0x180005d20  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005d27  test    rax, rax
0x180005d2a  jz      short loc_180005D33
0x180005d2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d31  jmp     short loc_180005D36
0x180005d33  mov     rax, rdi
0x180005d36  mov     [rbx+80h], rax
0x180005d3d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005d44  test    rax, rax
0x180005d47  jz      short loc_180005D51
0x180005d49  mov     rcx, rbx
0x180005d4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d51  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005d58  test    rax, rax
0x180005d5b  jz      short loc_180005D73
0x180005d5d  mov     rdx, [rsp+78h+arg_60]
0x180005d65  mov     r8d, 400h
0x180005d6b  mov     rcx, rbx
0x180005d6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d73  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005d7a  test    rax, rax
0x180005d7d  jz      short loc_180005D87
0x180005d7f  mov     rcx, rbx
0x180005d82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d87  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005d8e  test    rax, rax
0x180005d91  jz      short loc_180005DA1
0x180005d93  test    byte ptr [rbx+4], 2
0x180005d97  jnz     short loc_180005DA1
0x180005d99  mov     rcx, rbx
0x180005d9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005da1  cmp     [rbx+8], edi
0x180005da4  jl      short loc_180005DC0
0x180005da6  cmp     r15d, 3
0x180005daa  jnz     loc_180005E8E
0x180005db0  mov     ecx, 8000FFFFh; this
0x180005db5  mov     [rbx+8], ecx
0x180005db8  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005dbd  mov     [rbx+0Ch], eax
0x180005dc0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180005dc7  jnz     short loc_180005DE8
0x180005dc9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005dd0  test    rax, rax
0x180005dd3  jz      short loc_180005DDE
0x180005dd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005dda  test    al, al
0x180005ddc  jmp     short loc_180005DE6
0x180005dde  call    cs:__imp_IsDebuggerPresent
0x180005de4  test    eax, eax
0x180005de6  jz      short loc_180005DEE
0x180005de8  test    byte ptr [rbx+4], 2
0x180005dec  jz      short loc_180005E12
0x180005dee  mov     rax, cs:g_pfnResultLoggingCallback
0x180005df5  test    rax, rax
0x180005df8  jz      short loc_180005E56
0x180005dfa  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005e01  jnz     short loc_180005E56
0x180005e03  xor     r8d, r8d
0x180005e06  xor     edx, edx
0x180005e08  mov     rcx, rbx
0x180005e0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e10  jmp     short loc_180005E56
0x180005e12  mov     rax, cs:g_pfnResultLoggingCallback
0x180005e19  mov     ebp, 800h
0x180005e1e  test    rax, rax
0x180005e21  jz      short loc_180005E3A
0x180005e23  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005e2a  jnz     short loc_180005E3A
0x180005e2c  mov     r8d, ebp
0x180005e2f  mov     rdx, rsi
0x180005e32  mov     rcx, rbx
0x180005e35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e3a  cmp     [rsi], di
0x180005e3d  jnz     short loc_180005E4D
0x180005e3f  mov     r8, rbx; unsigned __int64
0x180005e42  mov     rdx, rbp; unsigned __int16 *
0x180005e45  mov     rcx, rsi; this
0x180005e48  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005e4d  mov     rcx, rsi; lpOutputString
0x180005e50  call    cs:__imp_OutputDebugStringW
0x180005e56  test    byte ptr [rbx+4], 4
0x180005e5a  jnz     short loc_180005E65
0x180005e5c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180005e63  jz      short loc_180005E76
0x180005e65  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005e6c  test    rax, rax
0x180005e6f  jz      short loc_180005E76
0x180005e71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e76  mov     rbx, [rsp+78h+arg_10]
0x180005e7e  add     rsp, 40h
0x180005e82  pop     r15
0x180005e84  pop     r14
0x180005e86  pop     r13
0x180005e88  pop     r12
0x180005e8a  pop     rdi
0x180005e8b  pop     rsi
0x180005e8c  pop     rbp
0x180005e8d  retn
0x180005e8e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
