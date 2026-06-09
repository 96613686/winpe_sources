# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800078c4`
- end: `0x180007bbd`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180003af8`

## callees

- `0x180003534`
- `0x1800067f4`
- `0x180007234`
- `0x1800078c4`
- `0x1800086e8`
- `0x180008710`
- `0x18000883c`
- `0x180008858`
- `0x18000c57c`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800079e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800079e7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007b06`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007b06`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007b78`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007b78`

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
0x1800078c4  mov     [rsp+arg_10], rbx
0x1800078c9  mov     [rsp+arg_8], edx
0x1800078cd  mov     [rsp+arg_0], rcx
0x1800078d2  push    rbp
0x1800078d3  push    rsi
0x1800078d4  push    rdi
0x1800078d5  push    r12
0x1800078d7  push    r13
0x1800078d9  push    r14
0x1800078db  push    r15
0x1800078dd  sub     rsp, 40h
0x1800078e1  mov     r12, r9
0x1800078e4  mov     r13, r8
0x1800078e7  mov     r10, rcx
0x1800078ea  xor     eax, eax
0x1800078ec  mov     rsi, [rsp+78h+lpOutputString]
0x1800078f4  mov     [rsi], ax
0x1800078f7  mov     rax, [rsp+78h+arg_60]
0x1800078ff  mov     byte ptr [rax], 0
0x180007902  mov     r14, [rsp+78h+arg_38]
0x18000790a  mov     edi, [r14]
0x18000790d  mov     rbx, [rsp+78h+arg_78]
0x180007915  mov     [rbx+8], edi
0x180007918  mov     eax, [r14+4]
0x18000791c  mov     [rbx+0Ch], eax
0x18000791f  xor     ebp, ebp
0x180007921  mov     r15d, [rsp+78h+arg_30]
0x180007929  mov     ecx, r15d
0x18000792c  test    r15d, r15d
0x18000792f  jz      short loc_180007997
0x180007931  sub     ecx, 1
0x180007934  jz      short loc_18000798E
0x180007936  sub     ecx, 1
0x180007939  jz      short loc_180007949
0x18000793b  cmp     ecx, 1
0x18000793e  jnz     short loc_1800079A0
0x180007940  mov     ecx, edi; this
0x180007942  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180007947  jmp     short loc_18000799E
0x180007949  test    edi, edi
0x18000794b  js      short loc_180007985
0x18000794d  mov     edi, 8007029Ch
0x180007952  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180007956  mov     rax, [rsp+78h+arg_28]
0x18000795e  mov     [rsp+78h+var_50], rax; __int64
0x180007963  mov     rax, [rsp+78h+arg_20]
0x18000796b  mov     [rsp+78h+var_58], rax; __int64
0x180007970  mov     rcx, r10; int
0x180007973  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180007978  mov     [rbx+8], edi
0x18000797b  mov     ecx, edi; this
0x18000797d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007982  mov     [rbx+0Ch], eax
0x180007985  mov     ecx, edi; this
0x180007987  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000798c  jmp     short loc_18000799E
0x18000798e  mov     ecx, edi; this
0x180007990  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180007995  jmp     short loc_18000799E
0x180007997  mov     ecx, edi; this
0x180007999  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000799e  mov     ebp, eax
0x1800079a0  mov     [rbx], r15d
0x1800079a3  mov     eax, [rsp+78h+arg_70]
0x1800079aa  mov     [rbx+4], eax
0x1800079ad  cmp     dword ptr [r14+8], 1
0x1800079b2  jnz     short loc_1800079BA
0x1800079b4  or      eax, 8
0x1800079b7  mov     [rbx+4], eax
0x1800079ba  mov     eax, 1
0x1800079bf  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800079c7  inc     eax
0x1800079c9  mov     [rbx+10h], eax
0x1800079cc  mov     rax, [rsp+78h+arg_40]
0x1800079d4  xor     edi, edi
0x1800079d6  test    rax, rax
0x1800079d9  jz      short loc_1800079E0
0x1800079db  cmp     [rax], di
0x1800079de  jnz     short loc_1800079E3
0x1800079e0  mov     rax, rdi
0x1800079e3  mov     [rbx+18h], rax
0x1800079e7  call    cs:__imp_GetCurrentThreadId
0x1800079ed  mov     [rbx+20h], eax
0x1800079f0  mov     [rbx+38h], r13
0x1800079f4  mov     eax, [rsp+78h+arg_8]
0x1800079fb  mov     [rbx+40h], eax
0x1800079fe  mov     [rbx+44h], ebp
0x180007a01  mov     rax, [rsp+78h+arg_20]
0x180007a09  mov     [rbx+28h], rax
0x180007a0d  mov     [rbx+30h], r12
0x180007a11  mov     rax, [rsp+78h+arg_28]
0x180007a19  mov     [rbx+88h], rax
0x180007a20  mov     rax, [rsp+78h+arg_0]
0x180007a28  mov     [rbx+90h], rax
0x180007a2f  mov     [rbx+48h], rdi
0x180007a33  xorps   xmm0, xmm0
0x180007a36  xor     eax, eax
0x180007a38  movups  xmmword ptr [rbx+68h], xmm0
0x180007a3c  mov     [rbx+78h], rax
0x180007a40  movups  xmmword ptr [rbx+50h], xmm0
0x180007a44  mov     [rbx+60h], rax
0x180007a48  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180007a4f  test    rax, rax
0x180007a52  jz      short loc_180007A5B
0x180007a54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a59  jmp     short loc_180007A5E
0x180007a5b  mov     rax, rdi
0x180007a5e  mov     [rbx+80h], rax
0x180007a65  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180007a6c  test    rax, rax
0x180007a6f  jz      short loc_180007A79
0x180007a71  mov     rcx, rbx
0x180007a74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a79  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180007a80  test    rax, rax
0x180007a83  jz      short loc_180007A9B
0x180007a85  mov     r8d, 400h
0x180007a8b  mov     rdx, [rsp+78h+arg_60]
0x180007a93  mov     rcx, rbx
0x180007a96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a9b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007aa2  test    rax, rax
0x180007aa5  jz      short loc_180007AAF
0x180007aa7  mov     rcx, rbx
0x180007aaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007aaf  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007ab6  test    rax, rax
0x180007ab9  jz      short loc_180007AC9
0x180007abb  test    byte ptr [rbx+4], 2
0x180007abf  jnz     short loc_180007AC9
0x180007ac1  mov     rcx, rbx
0x180007ac4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ac9  cmp     [rbx+8], edi
0x180007acc  jl      short loc_180007AE8
0x180007ace  cmp     r15d, 3
0x180007ad2  jnz     loc_180007BB7
0x180007ad8  mov     ecx, 8000FFFFh; this
0x180007add  mov     [rbx+8], ecx
0x180007ae0  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007ae5  mov     [rbx+0Ch], eax
0x180007ae8  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180007aef  jnz     short loc_180007B10
0x180007af1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180007af8  test    rax, rax
0x180007afb  jz      short loc_180007B06
0x180007afd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b02  test    al, al
0x180007b04  jmp     short loc_180007B0E
0x180007b06  call    cs:__imp_IsDebuggerPresent
0x180007b0c  test    eax, eax
0x180007b0e  jz      short loc_180007B16
0x180007b10  test    byte ptr [rbx+4], 2
0x180007b14  jz      short loc_180007B3A
0x180007b16  mov     rax, cs:g_pfnResultLoggingCallback
0x180007b1d  test    rax, rax
0x180007b20  jz      short loc_180007B7E
0x180007b22  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180007b29  jnz     short loc_180007B7E
0x180007b2b  xor     r8d, r8d
0x180007b2e  xor     edx, edx
0x180007b30  mov     rcx, rbx
0x180007b33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b38  jmp     short loc_180007B7E
0x180007b3a  mov     ebp, 800h
0x180007b3f  mov     rax, cs:g_pfnResultLoggingCallback
0x180007b46  test    rax, rax
0x180007b49  jz      short loc_180007B62
0x180007b4b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180007b52  jnz     short loc_180007B62
0x180007b54  mov     r8d, ebp
0x180007b57  mov     rdx, rsi
0x180007b5a  mov     rcx, rbx
0x180007b5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b62  cmp     [rsi], di
0x180007b65  jnz     short loc_180007B75
0x180007b67  mov     r8, rbx; unsigned __int64
0x180007b6a  mov     rdx, rbp; unsigned __int16 *
0x180007b6d  mov     rcx, rsi; this
0x180007b70  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180007b75  mov     rcx, rsi; lpOutputString
0x180007b78  call    cs:__imp_OutputDebugStringW
0x180007b7e  test    byte ptr [rbx+4], 4
0x180007b82  jnz     short loc_180007B8D
0x180007b84  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180007b8b  jz      short loc_180007B9F
0x180007b8d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180007b94  test    rax, rax
0x180007b97  jz      short loc_180007B9F
0x180007b99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b9e  nop
0x180007b9f  mov     rbx, [rsp+78h+arg_10]
0x180007ba7  add     rsp, 40h
0x180007bab  pop     r15
0x180007bad  pop     r14
0x180007baf  pop     r13
0x180007bb1  pop     r12
0x180007bb3  pop     rdi
0x180007bb4  pop     rsi
0x180007bb5  pop     rbp
0x180007bb6  retn
0x180007bb7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
