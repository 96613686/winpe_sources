# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800abd34`
- end: `0x1800ac02c`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800a9400`

## callees

- `0x1800a8e3c`
- `0x1800ab0e4`
- `0x1800ab950`
- `0x1800abd34`
- `0x1800acbf4`
- `0x1800acc10`
- `0x1800acd94`
- `0x1800acdb0`
- `0x1800ae7ec`
- `0x1800e0010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800abe57`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800abe57`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800abf76`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800abf76`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800abfe8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800abfe8`

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
0x1800abd34  mov     [rsp+arg_10], rbx
0x1800abd39  mov     [rsp+arg_8], edx
0x1800abd3d  mov     [rsp+arg_0], rcx
0x1800abd42  push    rbp
0x1800abd43  push    rsi
0x1800abd44  push    rdi
0x1800abd45  push    r12
0x1800abd47  push    r13
0x1800abd49  push    r14
0x1800abd4b  push    r15
0x1800abd4d  sub     rsp, 40h
0x1800abd51  mov     r14, [rsp+78h+arg_38]
0x1800abd59  xor     eax, eax
0x1800abd5b  mov     rbx, [rsp+78h+arg_78]
0x1800abd63  xor     ebp, ebp
0x1800abd65  mov     r15d, [rsp+78h+arg_30]
0x1800abd6d  mov     r10, rcx
0x1800abd70  mov     rsi, [rsp+78h+lpOutputString]
0x1800abd78  mov     r12, r9
0x1800abd7b  mov     r13, r8
0x1800abd7e  mov     ecx, r15d
0x1800abd81  mov     [rsi], ax
0x1800abd84  mov     rax, [rsp+78h+arg_60]
0x1800abd8c  mov     byte ptr [rax], 0
0x1800abd8f  mov     edi, [r14]
0x1800abd92  mov     [rbx+8], edi
0x1800abd95  mov     eax, [r14+4]
0x1800abd99  mov     [rbx+0Ch], eax
0x1800abd9c  test    r15d, r15d
0x1800abd9f  jz      short loc_1800ABE07
0x1800abda1  sub     ecx, 1
0x1800abda4  jz      short loc_1800ABDFE
0x1800abda6  sub     ecx, 1
0x1800abda9  jz      short loc_1800ABDB9
0x1800abdab  cmp     ecx, 1
0x1800abdae  jnz     short loc_1800ABE10
0x1800abdb0  mov     ecx, edi; this
0x1800abdb2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800abdb7  jmp     short loc_1800ABE0E
0x1800abdb9  test    edi, edi
0x1800abdbb  js      short loc_1800ABDF5
0x1800abdbd  mov     rax, [rsp+78h+arg_28]
0x1800abdc5  mov     edi, 8007029Ch
0x1800abdca  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800abdce  mov     rcx, r10; int
0x1800abdd1  mov     [rsp+78h+var_50], rax; __int64
0x1800abdd6  mov     rax, [rsp+78h+arg_20]
0x1800abdde  mov     [rsp+78h+var_58], rax; __int64
0x1800abde3  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800abde8  mov     ecx, edi; this
0x1800abdea  mov     [rbx+8], edi
0x1800abded  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800abdf2  mov     [rbx+0Ch], eax
0x1800abdf5  mov     ecx, edi; this
0x1800abdf7  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800abdfc  jmp     short loc_1800ABE0E
0x1800abdfe  mov     ecx, edi; this
0x1800abe00  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800abe05  jmp     short loc_1800ABE0E
0x1800abe07  mov     ecx, edi; this
0x1800abe09  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800abe0e  mov     ebp, eax
0x1800abe10  mov     eax, [rsp+78h+arg_70]
0x1800abe17  mov     [rbx+4], eax
0x1800abe1a  mov     [rbx], r15d
0x1800abe1d  cmp     dword ptr [r14+8], 1
0x1800abe22  jnz     short loc_1800ABE2A
0x1800abe24  or      eax, 8
0x1800abe27  mov     [rbx+4], eax
0x1800abe2a  mov     eax, 1
0x1800abe2f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800abe37  inc     eax
0x1800abe39  xor     edi, edi
0x1800abe3b  mov     [rbx+10h], eax
0x1800abe3e  mov     rax, [rsp+78h+arg_40]
0x1800abe46  test    rax, rax
0x1800abe49  jz      short loc_1800ABE50
0x1800abe4b  cmp     [rax], di
0x1800abe4e  jnz     short loc_1800ABE53
0x1800abe50  mov     rax, rdi
0x1800abe53  mov     [rbx+18h], rax
0x1800abe57  call    cs:__imp_GetCurrentThreadId
0x1800abe5d  mov     [rbx+38h], r13
0x1800abe61  xorps   xmm0, xmm0
0x1800abe64  mov     [rbx+20h], eax
0x1800abe67  mov     eax, [rsp+78h+arg_8]
0x1800abe6e  mov     [rbx+40h], eax
0x1800abe71  mov     rax, [rsp+78h+arg_20]
0x1800abe79  mov     [rbx+28h], rax
0x1800abe7d  mov     rax, [rsp+78h+arg_28]
0x1800abe85  mov     [rbx+88h], rax
0x1800abe8c  mov     rax, [rsp+78h+arg_0]
0x1800abe94  mov     [rbx+90h], rax
0x1800abe9b  xor     eax, eax
0x1800abe9d  mov     [rbx+44h], ebp
0x1800abea0  mov     [rbx+30h], r12
0x1800abea4  mov     [rbx+48h], rdi
0x1800abea8  movups  xmmword ptr [rbx+68h], xmm0
0x1800abeac  mov     [rbx+78h], rax
0x1800abeb0  movups  xmmword ptr [rbx+50h], xmm0
0x1800abeb4  mov     [rbx+60h], rax
0x1800abeb8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800abebf  test    rax, rax
0x1800abec2  jz      short loc_1800ABECB
0x1800abec4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abec9  jmp     short loc_1800ABECE
0x1800abecb  mov     rax, rdi
0x1800abece  mov     [rbx+80h], rax
0x1800abed5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800abedc  test    rax, rax
0x1800abedf  jz      short loc_1800ABEE9
0x1800abee1  mov     rcx, rbx
0x1800abee4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abee9  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800abef0  test    rax, rax
0x1800abef3  jz      short loc_1800ABF0B
0x1800abef5  mov     rdx, [rsp+78h+arg_60]
0x1800abefd  mov     r8d, 400h
0x1800abf03  mov     rcx, rbx
0x1800abf06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abf0b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800abf12  test    rax, rax
0x1800abf15  jz      short loc_1800ABF1F
0x1800abf17  mov     rcx, rbx
0x1800abf1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abf1f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800abf26  test    rax, rax
0x1800abf29  jz      short loc_1800ABF39
0x1800abf2b  test    byte ptr [rbx+4], 2
0x1800abf2f  jnz     short loc_1800ABF39
0x1800abf31  mov     rcx, rbx
0x1800abf34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abf39  cmp     [rbx+8], edi
0x1800abf3c  jl      short loc_1800ABF58
0x1800abf3e  cmp     r15d, 3
0x1800abf42  jnz     loc_1800AC026
0x1800abf48  mov     ecx, 8000FFFFh; this
0x1800abf4d  mov     [rbx+8], ecx
0x1800abf50  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800abf55  mov     [rbx+0Ch], eax
0x1800abf58  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800abf5f  jnz     short loc_1800ABF80
0x1800abf61  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800abf68  test    rax, rax
0x1800abf6b  jz      short loc_1800ABF76
0x1800abf6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abf72  test    al, al
0x1800abf74  jmp     short loc_1800ABF7E
0x1800abf76  call    cs:__imp_IsDebuggerPresent
0x1800abf7c  test    eax, eax
0x1800abf7e  jz      short loc_1800ABF86
0x1800abf80  test    byte ptr [rbx+4], 2
0x1800abf84  jz      short loc_1800ABFAA
0x1800abf86  mov     rax, cs:g_pfnResultLoggingCallback
0x1800abf8d  test    rax, rax
0x1800abf90  jz      short loc_1800ABFEE
0x1800abf92  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800abf99  jnz     short loc_1800ABFEE
0x1800abf9b  xor     r8d, r8d
0x1800abf9e  xor     edx, edx
0x1800abfa0  mov     rcx, rbx
0x1800abfa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abfa8  jmp     short loc_1800ABFEE
0x1800abfaa  mov     rax, cs:g_pfnResultLoggingCallback
0x1800abfb1  mov     ebp, 800h
0x1800abfb6  test    rax, rax
0x1800abfb9  jz      short loc_1800ABFD2
0x1800abfbb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800abfc2  jnz     short loc_1800ABFD2
0x1800abfc4  mov     r8d, ebp
0x1800abfc7  mov     rdx, rsi
0x1800abfca  mov     rcx, rbx
0x1800abfcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abfd2  cmp     [rsi], di
0x1800abfd5  jnz     short loc_1800ABFE5
0x1800abfd7  mov     r8, rbx; unsigned __int64
0x1800abfda  mov     rdx, rbp; unsigned __int16 *
0x1800abfdd  mov     rcx, rsi; this
0x1800abfe0  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800abfe5  mov     rcx, rsi; lpOutputString
0x1800abfe8  call    cs:__imp_OutputDebugStringW
0x1800abfee  test    byte ptr [rbx+4], 4
0x1800abff2  jnz     short loc_1800ABFFD
0x1800abff4  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800abffb  jz      short loc_1800AC00E
0x1800abffd  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800ac004  test    rax, rax
0x1800ac007  jz      short loc_1800AC00E
0x1800ac009  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac00e  mov     rbx, [rsp+78h+arg_10]
0x1800ac016  add     rsp, 40h
0x1800ac01a  pop     r15
0x1800ac01c  pop     r14
0x1800ac01e  pop     r13
0x1800ac020  pop     r12
0x1800ac022  pop     rdi
0x1800ac023  pop     rsi
0x1800ac024  pop     rbp
0x1800ac025  retn
0x1800ac026  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
