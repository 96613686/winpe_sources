# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18006c7d4`
- end: `0x18006cac9`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x18006c6d8`
- `0x18008122c`
- `0x1800812ec`
- `0x18009ff8c`

## callees

- `0x18006c7d4`
- `0x18006f144`
- `0x180081174`
- `0x180082294`
- `0x1800831a0`
- `0x1800831c0`
- `0x18008327c`
- `0x180083298`
- `0x18008447c`
- `0x1800a5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006c8f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006c8f7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18006ca18`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18006ca18`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18006ca8a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18006ca8a`

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
0x18006c7d4  mov     [rsp+arg_10], rbx
0x18006c7d9  mov     [rsp+arg_8], edx
0x18006c7dd  mov     [rsp+arg_0], rcx
0x18006c7e2  push    rbp
0x18006c7e3  push    rsi
0x18006c7e4  push    rdi
0x18006c7e5  push    r12
0x18006c7e7  push    r13
0x18006c7e9  push    r14
0x18006c7eb  push    r15
0x18006c7ed  sub     rsp, 40h
0x18006c7f1  mov     r12, r9
0x18006c7f4  mov     r13, r8
0x18006c7f7  mov     r10, rcx
0x18006c7fa  xor     eax, eax
0x18006c7fc  mov     rsi, [rsp+78h+lpOutputString]
0x18006c804  mov     [rsi], ax
0x18006c807  mov     rax, [rsp+78h+arg_60]
0x18006c80f  mov     byte ptr [rax], 0
0x18006c812  mov     r14, [rsp+78h+arg_38]
0x18006c81a  mov     edi, [r14]
0x18006c81d  mov     rbx, [rsp+78h+arg_78]
0x18006c825  mov     [rbx+8], edi
0x18006c828  mov     eax, [r14+4]
0x18006c82c  mov     [rbx+0Ch], eax
0x18006c82f  xor     ebp, ebp
0x18006c831  mov     r15d, [rsp+78h+arg_30]
0x18006c839  mov     ecx, r15d
0x18006c83c  test    r15d, r15d
0x18006c83f  jz      short loc_18006C8A7
0x18006c841  sub     ecx, 1
0x18006c844  jz      short loc_18006C89E
0x18006c846  sub     ecx, 1
0x18006c849  jz      short loc_18006C859
0x18006c84b  cmp     ecx, 1
0x18006c84e  jnz     short loc_18006C8B0
0x18006c850  mov     ecx, edi; this
0x18006c852  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18006c857  jmp     short loc_18006C8AE
0x18006c859  test    edi, edi
0x18006c85b  js      short loc_18006C895
0x18006c85d  mov     edi, 8007029Ch
0x18006c862  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18006c866  mov     rax, [rsp+78h+arg_28]
0x18006c86e  mov     [rsp+78h+var_50], rax; __int64
0x18006c873  mov     rax, [rsp+78h+arg_20]
0x18006c87b  mov     [rsp+78h+var_58], rax; __int64
0x18006c880  mov     rcx, r10; int
0x18006c883  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18006c888  mov     [rbx+8], edi
0x18006c88b  mov     ecx, edi; this
0x18006c88d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18006c892  mov     [rbx+0Ch], eax
0x18006c895  mov     ecx, edi; this
0x18006c897  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18006c89c  jmp     short loc_18006C8AE
0x18006c89e  mov     ecx, edi; this
0x18006c8a0  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18006c8a5  jmp     short loc_18006C8AE
0x18006c8a7  mov     ecx, edi; this
0x18006c8a9  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18006c8ae  mov     ebp, eax
0x18006c8b0  mov     [rbx], r15d
0x18006c8b3  mov     eax, [rsp+78h+arg_70]
0x18006c8ba  mov     [rbx+4], eax
0x18006c8bd  cmp     dword ptr [r14+8], 1
0x18006c8c2  jnz     short loc_18006C8CA
0x18006c8c4  or      eax, 8
0x18006c8c7  mov     [rbx+4], eax
0x18006c8ca  mov     eax, 1
0x18006c8cf  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18006c8d7  inc     eax
0x18006c8d9  mov     [rbx+10h], eax
0x18006c8dc  mov     rax, [rsp+78h+arg_40]
0x18006c8e4  xor     edi, edi
0x18006c8e6  test    rax, rax
0x18006c8e9  jz      short loc_18006C8F0
0x18006c8eb  cmp     [rax], di
0x18006c8ee  jnz     short loc_18006C8F3
0x18006c8f0  mov     rax, rdi
0x18006c8f3  mov     [rbx+18h], rax
0x18006c8f7  call    cs:__imp_GetCurrentThreadId
0x18006c8fd  mov     [rbx+20h], eax
0x18006c900  mov     [rbx+38h], r13
0x18006c904  mov     eax, [rsp+78h+arg_8]
0x18006c90b  mov     [rbx+40h], eax
0x18006c90e  mov     [rbx+44h], ebp
0x18006c911  mov     rax, [rsp+78h+arg_20]
0x18006c919  mov     [rbx+28h], rax
0x18006c91d  mov     [rbx+30h], r12
0x18006c921  mov     rax, [rsp+78h+arg_28]
0x18006c929  mov     [rbx+88h], rax
0x18006c930  mov     rax, [rsp+78h+arg_0]
0x18006c938  mov     [rbx+90h], rax
0x18006c93f  mov     [rbx+48h], rdi
0x18006c943  xorps   xmm0, xmm0
0x18006c946  xor     eax, eax
0x18006c948  movups  xmmword ptr [rbx+68h], xmm0
0x18006c94c  mov     [rbx+78h], rax
0x18006c950  movups  xmmword ptr [rbx+50h], xmm0
0x18006c954  mov     [rbx+60h], rax
0x18006c958  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18006c95f  test    rax, rax
0x18006c962  jz      short loc_18006C96B
0x18006c964  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c969  jmp     short loc_18006C96E
0x18006c96b  mov     rax, rdi
0x18006c96e  mov     [rbx+80h], rax
0x18006c975  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18006c97c  test    rax, rax
0x18006c97f  jz      short loc_18006C989
0x18006c981  mov     rcx, rbx
0x18006c984  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c989  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18006c990  test    rax, rax
0x18006c993  jz      short loc_18006C9AB
0x18006c995  mov     r8d, 400h
0x18006c99b  mov     rdx, [rsp+78h+arg_60]
0x18006c9a3  mov     rcx, rbx
0x18006c9a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c9ab  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18006c9b2  test    rax, rax
0x18006c9b5  jz      short loc_18006C9BF
0x18006c9b7  mov     rcx, rbx
0x18006c9ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c9bf  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18006c9c6  test    rax, rax
0x18006c9c9  jz      short loc_18006C9D9
0x18006c9cb  test    byte ptr [rbx+4], 2
0x18006c9cf  jnz     short loc_18006C9D9
0x18006c9d1  mov     rcx, rbx
0x18006c9d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c9d9  cmp     [rbx+8], edi
0x18006c9dc  jl      short loc_18006C9FA
0x18006c9de  cmp     r15d, 3
0x18006c9e2  jz      short loc_18006C9EA
0x18006c9e4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18006c9ea  mov     ecx, 8000FFFFh; this
0x18006c9ef  mov     [rbx+8], ecx
0x18006c9f2  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18006c9f7  mov     [rbx+0Ch], eax
0x18006c9fa  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18006ca01  jnz     short loc_18006CA22
0x18006ca03  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18006ca0a  test    rax, rax
0x18006ca0d  jz      short loc_18006CA18
0x18006ca0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ca14  test    al, al
0x18006ca16  jmp     short loc_18006CA20
0x18006ca18  call    cs:__imp_IsDebuggerPresent
0x18006ca1e  test    eax, eax
0x18006ca20  jz      short loc_18006CA28
0x18006ca22  test    byte ptr [rbx+4], 2
0x18006ca26  jz      short loc_18006CA4C
0x18006ca28  mov     rax, cs:g_pfnResultLoggingCallback
0x18006ca2f  test    rax, rax
0x18006ca32  jz      short loc_18006CA90
0x18006ca34  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18006ca3b  jnz     short loc_18006CA90
0x18006ca3d  xor     r8d, r8d
0x18006ca40  xor     edx, edx
0x18006ca42  mov     rcx, rbx
0x18006ca45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ca4a  jmp     short loc_18006CA90
0x18006ca4c  mov     ebp, 800h
0x18006ca51  mov     rax, cs:g_pfnResultLoggingCallback
0x18006ca58  test    rax, rax
0x18006ca5b  jz      short loc_18006CA74
0x18006ca5d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18006ca64  jnz     short loc_18006CA74
0x18006ca66  mov     r8d, ebp
0x18006ca69  mov     rdx, rsi
0x18006ca6c  mov     rcx, rbx
0x18006ca6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ca74  cmp     [rsi], di
0x18006ca77  jnz     short loc_18006CA87
0x18006ca79  mov     r8, rbx; unsigned __int64
0x18006ca7c  mov     rdx, rbp; unsigned __int16 *
0x18006ca7f  mov     rcx, rsi; this
0x18006ca82  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18006ca87  mov     rcx, rsi; lpOutputString
0x18006ca8a  call    cs:__imp_OutputDebugStringW
0x18006ca90  test    byte ptr [rbx+4], 4
0x18006ca94  jnz     short loc_18006CA9F
0x18006ca96  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18006ca9d  jz      short loc_18006CAB1
0x18006ca9f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18006caa6  test    rax, rax
0x18006caa9  jz      short loc_18006CAB1
0x18006caab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cab0  nop
0x18006cab1  mov     rbx, [rsp+78h+arg_10]
0x18006cab9  add     rsp, 40h
0x18006cabd  pop     r15
0x18006cabf  pop     r14
0x18006cac1  pop     r13
0x18006cac3  pop     r12
0x18006cac5  pop     rdi
0x18006cac6  pop     rsi
0x18006cac7  pop     rbp
0x18006cac8  retn
```
