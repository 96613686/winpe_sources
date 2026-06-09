# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800458d4`
- end: `0x180045bcc`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180043b90`
- `0x180043ed4`

## callees

- `0x18003a480`
- `0x180043acc`
- `0x180044ee4`
- `0x1800458d4`
- `0x180046324`
- `0x180046340`
- `0x180046490`
- `0x1800464ac`
- `0x180047974`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180045b16`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180045b16`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180045b88`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180045b88`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800459f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800459f7`

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
0x1800458d4  mov     [rsp+arg_10], rbx
0x1800458d9  mov     [rsp+arg_8], edx
0x1800458dd  mov     [rsp+arg_0], rcx
0x1800458e2  push    rbp
0x1800458e3  push    rsi
0x1800458e4  push    rdi
0x1800458e5  push    r12
0x1800458e7  push    r13
0x1800458e9  push    r14
0x1800458eb  push    r15
0x1800458ed  sub     rsp, 40h
0x1800458f1  mov     r14, [rsp+78h+arg_38]
0x1800458f9  xor     eax, eax
0x1800458fb  mov     rbx, [rsp+78h+arg_78]
0x180045903  xor     ebp, ebp
0x180045905  mov     r15d, [rsp+78h+arg_30]
0x18004590d  mov     r10, rcx
0x180045910  mov     rsi, [rsp+78h+lpOutputString]
0x180045918  mov     r12, r9
0x18004591b  mov     r13, r8
0x18004591e  mov     ecx, r15d
0x180045921  mov     [rsi], ax
0x180045924  mov     rax, [rsp+78h+arg_60]
0x18004592c  mov     byte ptr [rax], 0
0x18004592f  mov     edi, [r14]
0x180045932  mov     [rbx+8], edi
0x180045935  mov     eax, [r14+4]
0x180045939  mov     [rbx+0Ch], eax
0x18004593c  test    r15d, r15d
0x18004593f  jz      short loc_1800459A7
0x180045941  sub     ecx, 1
0x180045944  jz      short loc_18004599E
0x180045946  sub     ecx, 1
0x180045949  jz      short loc_180045959
0x18004594b  cmp     ecx, 1
0x18004594e  jnz     short loc_1800459B0
0x180045950  mov     ecx, edi; this
0x180045952  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180045957  jmp     short loc_1800459AE
0x180045959  test    edi, edi
0x18004595b  js      short loc_180045995
0x18004595d  mov     rax, [rsp+78h+arg_28]
0x180045965  mov     edi, 8007029Ch
0x18004596a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18004596e  mov     rcx, r10; int
0x180045971  mov     [rsp+78h+var_50], rax; __int64
0x180045976  mov     rax, [rsp+78h+arg_20]
0x18004597e  mov     [rsp+78h+var_58], rax; __int64
0x180045983  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180045988  mov     ecx, edi; this
0x18004598a  mov     [rbx+8], edi
0x18004598d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180045992  mov     [rbx+0Ch], eax
0x180045995  mov     ecx, edi; this
0x180045997  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18004599c  jmp     short loc_1800459AE
0x18004599e  mov     ecx, edi; this
0x1800459a0  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800459a5  jmp     short loc_1800459AE
0x1800459a7  mov     ecx, edi; this
0x1800459a9  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800459ae  mov     ebp, eax
0x1800459b0  mov     eax, [rsp+78h+arg_70]
0x1800459b7  mov     [rbx+4], eax
0x1800459ba  mov     [rbx], r15d
0x1800459bd  cmp     dword ptr [r14+8], 1
0x1800459c2  jnz     short loc_1800459CA
0x1800459c4  or      eax, 8
0x1800459c7  mov     [rbx+4], eax
0x1800459ca  mov     eax, 1
0x1800459cf  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800459d7  inc     eax
0x1800459d9  xor     edi, edi
0x1800459db  mov     [rbx+10h], eax
0x1800459de  mov     rax, [rsp+78h+arg_40]
0x1800459e6  test    rax, rax
0x1800459e9  jz      short loc_1800459F0
0x1800459eb  cmp     [rax], di
0x1800459ee  jnz     short loc_1800459F3
0x1800459f0  mov     rax, rdi
0x1800459f3  mov     [rbx+18h], rax
0x1800459f7  call    cs:__imp_GetCurrentThreadId
0x1800459fd  mov     [rbx+38h], r13
0x180045a01  xorps   xmm0, xmm0
0x180045a04  mov     [rbx+20h], eax
0x180045a07  mov     eax, [rsp+78h+arg_8]
0x180045a0e  mov     [rbx+40h], eax
0x180045a11  mov     rax, [rsp+78h+arg_20]
0x180045a19  mov     [rbx+28h], rax
0x180045a1d  mov     rax, [rsp+78h+arg_28]
0x180045a25  mov     [rbx+88h], rax
0x180045a2c  mov     rax, [rsp+78h+arg_0]
0x180045a34  mov     [rbx+90h], rax
0x180045a3b  xor     eax, eax
0x180045a3d  mov     [rbx+44h], ebp
0x180045a40  mov     [rbx+30h], r12
0x180045a44  mov     [rbx+48h], rdi
0x180045a48  movups  xmmword ptr [rbx+68h], xmm0
0x180045a4c  mov     [rbx+78h], rax
0x180045a50  movups  xmmword ptr [rbx+50h], xmm0
0x180045a54  mov     [rbx+60h], rax
0x180045a58  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180045a5f  test    rax, rax
0x180045a62  jz      short loc_180045A6B
0x180045a64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045a69  jmp     short loc_180045A6E
0x180045a6b  mov     rax, rdi
0x180045a6e  mov     [rbx+80h], rax
0x180045a75  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180045a7c  test    rax, rax
0x180045a7f  jz      short loc_180045A89
0x180045a81  mov     rcx, rbx
0x180045a84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045a89  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180045a90  test    rax, rax
0x180045a93  jz      short loc_180045AAB
0x180045a95  mov     rdx, [rsp+78h+arg_60]
0x180045a9d  mov     r8d, 400h
0x180045aa3  mov     rcx, rbx
0x180045aa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045aab  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180045ab2  test    rax, rax
0x180045ab5  jz      short loc_180045ABF
0x180045ab7  mov     rcx, rbx
0x180045aba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045abf  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180045ac6  test    rax, rax
0x180045ac9  jz      short loc_180045AD9
0x180045acb  test    byte ptr [rbx+4], 2
0x180045acf  jnz     short loc_180045AD9
0x180045ad1  mov     rcx, rbx
0x180045ad4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045ad9  cmp     [rbx+8], edi
0x180045adc  jl      short loc_180045AF8
0x180045ade  cmp     r15d, 3
0x180045ae2  jnz     loc_180045BC6
0x180045ae8  mov     ecx, 8000FFFFh; this
0x180045aed  mov     [rbx+8], ecx
0x180045af0  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180045af5  mov     [rbx+0Ch], eax
0x180045af8  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180045aff  jnz     short loc_180045B20
0x180045b01  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180045b08  test    rax, rax
0x180045b0b  jz      short loc_180045B16
0x180045b0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045b12  test    al, al
0x180045b14  jmp     short loc_180045B1E
0x180045b16  call    cs:__imp_IsDebuggerPresent
0x180045b1c  test    eax, eax
0x180045b1e  jz      short loc_180045B26
0x180045b20  test    byte ptr [rbx+4], 2
0x180045b24  jz      short loc_180045B4A
0x180045b26  mov     rax, cs:g_pfnResultLoggingCallback
0x180045b2d  test    rax, rax
0x180045b30  jz      short loc_180045B8E
0x180045b32  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180045b39  jnz     short loc_180045B8E
0x180045b3b  xor     r8d, r8d
0x180045b3e  xor     edx, edx
0x180045b40  mov     rcx, rbx
0x180045b43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045b48  jmp     short loc_180045B8E
0x180045b4a  mov     rax, cs:g_pfnResultLoggingCallback
0x180045b51  mov     ebp, 800h
0x180045b56  test    rax, rax
0x180045b59  jz      short loc_180045B72
0x180045b5b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180045b62  jnz     short loc_180045B72
0x180045b64  mov     r8d, ebp
0x180045b67  mov     rdx, rsi
0x180045b6a  mov     rcx, rbx
0x180045b6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045b72  cmp     [rsi], di
0x180045b75  jnz     short loc_180045B85
0x180045b77  mov     r8, rbx; unsigned __int64
0x180045b7a  mov     rdx, rbp; unsigned __int16 *
0x180045b7d  mov     rcx, rsi; this
0x180045b80  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180045b85  mov     rcx, rsi; lpOutputString
0x180045b88  call    cs:__imp_OutputDebugStringW
0x180045b8e  test    byte ptr [rbx+4], 4
0x180045b92  jnz     short loc_180045B9D
0x180045b94  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180045b9b  jz      short loc_180045BAE
0x180045b9d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180045ba4  test    rax, rax
0x180045ba7  jz      short loc_180045BAE
0x180045ba9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045bae  mov     rbx, [rsp+78h+arg_10]
0x180045bb6  add     rsp, 40h
0x180045bba  pop     r15
0x180045bbc  pop     r14
0x180045bbe  pop     r13
0x180045bc0  pop     r12
0x180045bc2  pop     rdi
0x180045bc3  pop     rsi
0x180045bc4  pop     rbp
0x180045bc5  retn
0x180045bc6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
