# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180015ac0`
- end: `0x180015db9`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180013dc8`
- `0x180014118`

## callees

- `0x180013d10`
- `0x180015064`
- `0x18001583c`
- `0x180015ac0`
- `0x1800166f4`
- `0x180016710`
- `0x180016724`
- `0x180016740`
- `0x180017be4`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015be3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015be3`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180015d74`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180015d74`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180015d02`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180015d02`

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
0x180015ac0  mov     [rsp+arg_10], rbx
0x180015ac5  mov     [rsp+arg_8], edx
0x180015ac9  mov     [rsp+arg_0], rcx
0x180015ace  push    rbp
0x180015acf  push    rsi
0x180015ad0  push    rdi
0x180015ad1  push    r12
0x180015ad3  push    r13
0x180015ad5  push    r14
0x180015ad7  push    r15
0x180015ad9  sub     rsp, 40h
0x180015add  mov     r12, r9
0x180015ae0  mov     r13, r8
0x180015ae3  mov     r10, rcx
0x180015ae6  xor     eax, eax
0x180015ae8  mov     rsi, [rsp+78h+lpOutputString]
0x180015af0  mov     [rsi], ax
0x180015af3  mov     rax, [rsp+78h+arg_60]
0x180015afb  mov     byte ptr [rax], 0
0x180015afe  mov     r14, [rsp+78h+arg_38]
0x180015b06  mov     edi, [r14]
0x180015b09  mov     rbx, [rsp+78h+arg_78]
0x180015b11  mov     [rbx+8], edi
0x180015b14  mov     eax, [r14+4]
0x180015b18  mov     [rbx+0Ch], eax
0x180015b1b  xor     ebp, ebp
0x180015b1d  mov     r15d, [rsp+78h+arg_30]
0x180015b25  mov     ecx, r15d
0x180015b28  test    r15d, r15d
0x180015b2b  jz      short loc_180015B93
0x180015b2d  sub     ecx, 1
0x180015b30  jz      short loc_180015B8A
0x180015b32  sub     ecx, 1
0x180015b35  jz      short loc_180015B45
0x180015b37  cmp     ecx, 1
0x180015b3a  jnz     short loc_180015B9C
0x180015b3c  mov     ecx, edi; this
0x180015b3e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180015b43  jmp     short loc_180015B9A
0x180015b45  test    edi, edi
0x180015b47  js      short loc_180015B81
0x180015b49  mov     edi, 8007029Ch
0x180015b4e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180015b52  mov     rax, [rsp+78h+arg_28]
0x180015b5a  mov     [rsp+78h+var_50], rax; __int64
0x180015b5f  mov     rax, [rsp+78h+arg_20]
0x180015b67  mov     [rsp+78h+var_58], rax; __int64
0x180015b6c  mov     rcx, r10; int
0x180015b6f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180015b74  mov     [rbx+8], edi
0x180015b77  mov     ecx, edi; this
0x180015b79  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180015b7e  mov     [rbx+0Ch], eax
0x180015b81  mov     ecx, edi; this
0x180015b83  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180015b88  jmp     short loc_180015B9A
0x180015b8a  mov     ecx, edi; this
0x180015b8c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180015b91  jmp     short loc_180015B9A
0x180015b93  mov     ecx, edi; this
0x180015b95  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180015b9a  mov     ebp, eax
0x180015b9c  mov     [rbx], r15d
0x180015b9f  mov     eax, [rsp+78h+arg_70]
0x180015ba6  mov     [rbx+4], eax
0x180015ba9  cmp     dword ptr [r14+8], 1
0x180015bae  jnz     short loc_180015BB6
0x180015bb0  or      eax, 8
0x180015bb3  mov     [rbx+4], eax
0x180015bb6  mov     eax, 1
0x180015bbb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180015bc3  inc     eax
0x180015bc5  mov     [rbx+10h], eax
0x180015bc8  mov     rax, [rsp+78h+arg_40]
0x180015bd0  xor     edi, edi
0x180015bd2  test    rax, rax
0x180015bd5  jz      short loc_180015BDC
0x180015bd7  cmp     [rax], di
0x180015bda  jnz     short loc_180015BDF
0x180015bdc  mov     rax, rdi
0x180015bdf  mov     [rbx+18h], rax
0x180015be3  call    cs:__imp_GetCurrentThreadId
0x180015be9  mov     [rbx+20h], eax
0x180015bec  mov     [rbx+38h], r13
0x180015bf0  mov     eax, [rsp+78h+arg_8]
0x180015bf7  mov     [rbx+40h], eax
0x180015bfa  mov     [rbx+44h], ebp
0x180015bfd  mov     rax, [rsp+78h+arg_20]
0x180015c05  mov     [rbx+28h], rax
0x180015c09  mov     [rbx+30h], r12
0x180015c0d  mov     rax, [rsp+78h+arg_28]
0x180015c15  mov     [rbx+88h], rax
0x180015c1c  mov     rax, [rsp+78h+arg_0]
0x180015c24  mov     [rbx+90h], rax
0x180015c2b  mov     [rbx+48h], rdi
0x180015c2f  xorps   xmm0, xmm0
0x180015c32  xor     eax, eax
0x180015c34  movups  xmmword ptr [rbx+68h], xmm0
0x180015c38  mov     [rbx+78h], rax
0x180015c3c  movups  xmmword ptr [rbx+50h], xmm0
0x180015c40  mov     [rbx+60h], rax
0x180015c44  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180015c4b  test    rax, rax
0x180015c4e  jz      short loc_180015C57
0x180015c50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c55  jmp     short loc_180015C5A
0x180015c57  mov     rax, rdi
0x180015c5a  mov     [rbx+80h], rax
0x180015c61  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180015c68  test    rax, rax
0x180015c6b  jz      short loc_180015C75
0x180015c6d  mov     rcx, rbx
0x180015c70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c75  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180015c7c  test    rax, rax
0x180015c7f  jz      short loc_180015C97
0x180015c81  mov     r8d, 400h
0x180015c87  mov     rdx, [rsp+78h+arg_60]
0x180015c8f  mov     rcx, rbx
0x180015c92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c97  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180015c9e  test    rax, rax
0x180015ca1  jz      short loc_180015CAB
0x180015ca3  mov     rcx, rbx
0x180015ca6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015cab  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180015cb2  test    rax, rax
0x180015cb5  jz      short loc_180015CC5
0x180015cb7  test    byte ptr [rbx+4], 2
0x180015cbb  jnz     short loc_180015CC5
0x180015cbd  mov     rcx, rbx
0x180015cc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015cc5  cmp     [rbx+8], edi
0x180015cc8  jl      short loc_180015CE4
0x180015cca  cmp     r15d, 3
0x180015cce  jnz     loc_180015DB3
0x180015cd4  mov     ecx, 8000FFFFh; this
0x180015cd9  mov     [rbx+8], ecx
0x180015cdc  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180015ce1  mov     [rbx+0Ch], eax
0x180015ce4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180015ceb  jnz     short loc_180015D0C
0x180015ced  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180015cf4  test    rax, rax
0x180015cf7  jz      short loc_180015D02
0x180015cf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015cfe  test    al, al
0x180015d00  jmp     short loc_180015D0A
0x180015d02  call    cs:__imp_IsDebuggerPresent
0x180015d08  test    eax, eax
0x180015d0a  jz      short loc_180015D12
0x180015d0c  test    byte ptr [rbx+4], 2
0x180015d10  jz      short loc_180015D36
0x180015d12  mov     rax, cs:g_pfnResultLoggingCallback
0x180015d19  test    rax, rax
0x180015d1c  jz      short loc_180015D7A
0x180015d1e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180015d25  jnz     short loc_180015D7A
0x180015d27  xor     r8d, r8d
0x180015d2a  xor     edx, edx
0x180015d2c  mov     rcx, rbx
0x180015d2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d34  jmp     short loc_180015D7A
0x180015d36  mov     ebp, 800h
0x180015d3b  mov     rax, cs:g_pfnResultLoggingCallback
0x180015d42  test    rax, rax
0x180015d45  jz      short loc_180015D5E
0x180015d47  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180015d4e  jnz     short loc_180015D5E
0x180015d50  mov     r8d, ebp
0x180015d53  mov     rdx, rsi
0x180015d56  mov     rcx, rbx
0x180015d59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d5e  cmp     [rsi], di
0x180015d61  jnz     short loc_180015D71
0x180015d63  mov     r8, rbx; unsigned __int64
0x180015d66  mov     rdx, rbp; unsigned __int16 *
0x180015d69  mov     rcx, rsi; this
0x180015d6c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180015d71  mov     rcx, rsi; lpOutputString
0x180015d74  call    cs:__imp_OutputDebugStringW
0x180015d7a  test    byte ptr [rbx+4], 4
0x180015d7e  jnz     short loc_180015D89
0x180015d80  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180015d87  jz      short loc_180015D9B
0x180015d89  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180015d90  test    rax, rax
0x180015d93  jz      short loc_180015D9B
0x180015d95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d9a  nop
0x180015d9b  mov     rbx, [rsp+78h+arg_10]
0x180015da3  add     rsp, 40h
0x180015da7  pop     r15
0x180015da9  pop     r14
0x180015dab  pop     r13
0x180015dad  pop     r12
0x180015daf  pop     rdi
0x180015db0  pop     rsi
0x180015db1  pop     rbp
0x180015db2  retn
0x180015db3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
