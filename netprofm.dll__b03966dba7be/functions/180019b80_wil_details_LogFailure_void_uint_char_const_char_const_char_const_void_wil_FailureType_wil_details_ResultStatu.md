# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180019b80`
- end: `0x180019e79`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180014674`
- `0x180014734`
- `0x180014aec`

## callees

- `0x180008bf8`
- `0x18000ad20`
- `0x1800145ac`
- `0x180018f70`
- `0x180019b80`
- `0x18001ae20`
- `0x18001ae40`
- `0x18001afd4`
- `0x18001d22c`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019ca3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019ca3`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180019e34`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180019e34`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180019dc2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180019dc2`

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
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v25);
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
0x180019b80  mov     [rsp+arg_10], rbx
0x180019b85  mov     [rsp+arg_8], edx
0x180019b89  mov     [rsp+arg_0], rcx
0x180019b8e  push    rbp
0x180019b8f  push    rsi
0x180019b90  push    rdi
0x180019b91  push    r12
0x180019b93  push    r13
0x180019b95  push    r14
0x180019b97  push    r15
0x180019b99  sub     rsp, 40h
0x180019b9d  mov     r12, r9
0x180019ba0  mov     r13, r8
0x180019ba3  mov     r10, rcx
0x180019ba6  xor     eax, eax
0x180019ba8  mov     rsi, [rsp+78h+lpOutputString]
0x180019bb0  mov     [rsi], ax
0x180019bb3  mov     rax, [rsp+78h+arg_60]
0x180019bbb  mov     byte ptr [rax], 0
0x180019bbe  mov     r14, [rsp+78h+arg_38]
0x180019bc6  mov     edi, [r14]
0x180019bc9  mov     rbx, [rsp+78h+arg_78]
0x180019bd1  mov     [rbx+8], edi
0x180019bd4  mov     eax, [r14+4]
0x180019bd8  mov     [rbx+0Ch], eax
0x180019bdb  xor     ebp, ebp
0x180019bdd  mov     r15d, [rsp+78h+arg_30]
0x180019be5  mov     ecx, r15d
0x180019be8  test    r15d, r15d
0x180019beb  jz      short loc_180019C53
0x180019bed  sub     ecx, 1
0x180019bf0  jz      short loc_180019C4A
0x180019bf2  sub     ecx, 1
0x180019bf5  jz      short loc_180019C05
0x180019bf7  cmp     ecx, 1
0x180019bfa  jnz     short loc_180019C5C
0x180019bfc  mov     ecx, edi; this
0x180019bfe  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180019c03  jmp     short loc_180019C5A
0x180019c05  test    edi, edi
0x180019c07  js      short loc_180019C41
0x180019c09  mov     edi, 8007029Ch
0x180019c0e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180019c12  mov     rax, [rsp+78h+arg_28]
0x180019c1a  mov     [rsp+78h+var_50], rax; __int64
0x180019c1f  mov     rax, [rsp+78h+arg_20]
0x180019c27  mov     [rsp+78h+var_58], rax; __int64
0x180019c2c  mov     rcx, r10; int
0x180019c2f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180019c34  mov     [rbx+8], edi
0x180019c37  mov     ecx, edi; this
0x180019c39  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180019c3e  mov     [rbx+0Ch], eax
0x180019c41  mov     ecx, edi; this
0x180019c43  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180019c48  jmp     short loc_180019C5A
0x180019c4a  mov     ecx, edi; this
0x180019c4c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180019c51  jmp     short loc_180019C5A
0x180019c53  mov     ecx, edi; this
0x180019c55  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180019c5a  mov     ebp, eax
0x180019c5c  mov     [rbx], r15d
0x180019c5f  mov     eax, [rsp+78h+arg_70]
0x180019c66  mov     [rbx+4], eax
0x180019c69  cmp     dword ptr [r14+8], 1
0x180019c6e  jnz     short loc_180019C76
0x180019c70  or      eax, 8
0x180019c73  mov     [rbx+4], eax
0x180019c76  mov     eax, 1
0x180019c7b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180019c83  inc     eax
0x180019c85  mov     [rbx+10h], eax
0x180019c88  mov     rax, [rsp+78h+arg_40]
0x180019c90  xor     edi, edi
0x180019c92  test    rax, rax
0x180019c95  jz      short loc_180019C9C
0x180019c97  cmp     [rax], di
0x180019c9a  jnz     short loc_180019C9F
0x180019c9c  mov     rax, rdi
0x180019c9f  mov     [rbx+18h], rax
0x180019ca3  call    cs:__imp_GetCurrentThreadId
0x180019ca9  mov     [rbx+20h], eax
0x180019cac  mov     [rbx+38h], r13
0x180019cb0  mov     eax, [rsp+78h+arg_8]
0x180019cb7  mov     [rbx+40h], eax
0x180019cba  mov     [rbx+44h], ebp
0x180019cbd  mov     rax, [rsp+78h+arg_20]
0x180019cc5  mov     [rbx+28h], rax
0x180019cc9  mov     [rbx+30h], r12
0x180019ccd  mov     rax, [rsp+78h+arg_28]
0x180019cd5  mov     [rbx+88h], rax
0x180019cdc  mov     rax, [rsp+78h+arg_0]
0x180019ce4  mov     [rbx+90h], rax
0x180019ceb  mov     [rbx+48h], rdi
0x180019cef  xorps   xmm0, xmm0
0x180019cf2  xor     eax, eax
0x180019cf4  movups  xmmword ptr [rbx+68h], xmm0
0x180019cf8  mov     [rbx+78h], rax
0x180019cfc  movups  xmmword ptr [rbx+50h], xmm0
0x180019d00  mov     [rbx+60h], rax
0x180019d04  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180019d0b  test    rax, rax
0x180019d0e  jz      short loc_180019D17
0x180019d10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d15  jmp     short loc_180019D1A
0x180019d17  mov     rax, rdi
0x180019d1a  mov     [rbx+80h], rax
0x180019d21  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180019d28  test    rax, rax
0x180019d2b  jz      short loc_180019D35
0x180019d2d  mov     rcx, rbx
0x180019d30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d35  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180019d3c  test    rax, rax
0x180019d3f  jz      short loc_180019D57
0x180019d41  mov     r8d, 400h
0x180019d47  mov     rdx, [rsp+78h+arg_60]
0x180019d4f  mov     rcx, rbx
0x180019d52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d57  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180019d5e  test    rax, rax
0x180019d61  jz      short loc_180019D6B
0x180019d63  mov     rcx, rbx
0x180019d66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d6b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180019d72  test    rax, rax
0x180019d75  jz      short loc_180019D85
0x180019d77  test    byte ptr [rbx+4], 2
0x180019d7b  jnz     short loc_180019D85
0x180019d7d  mov     rcx, rbx
0x180019d80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d85  cmp     [rbx+8], edi
0x180019d88  jl      short loc_180019DA4
0x180019d8a  cmp     r15d, 3
0x180019d8e  jnz     loc_180019E73
0x180019d94  mov     ecx, 8000FFFFh; this
0x180019d99  mov     [rbx+8], ecx
0x180019d9c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180019da1  mov     [rbx+0Ch], eax
0x180019da4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180019dab  jnz     short loc_180019DCC
0x180019dad  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180019db4  test    rax, rax
0x180019db7  jz      short loc_180019DC2
0x180019db9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019dbe  test    al, al
0x180019dc0  jmp     short loc_180019DCA
0x180019dc2  call    cs:__imp_IsDebuggerPresent
0x180019dc8  test    eax, eax
0x180019dca  jz      short loc_180019DD2
0x180019dcc  test    byte ptr [rbx+4], 2
0x180019dd0  jz      short loc_180019DF6
0x180019dd2  mov     rax, cs:g_pfnResultLoggingCallback
0x180019dd9  test    rax, rax
0x180019ddc  jz      short loc_180019E3A
0x180019dde  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180019de5  jnz     short loc_180019E3A
0x180019de7  xor     r8d, r8d
0x180019dea  xor     edx, edx
0x180019dec  mov     rcx, rbx
0x180019def  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019df4  jmp     short loc_180019E3A
0x180019df6  mov     ebp, 800h
0x180019dfb  mov     rax, cs:g_pfnResultLoggingCallback
0x180019e02  test    rax, rax
0x180019e05  jz      short loc_180019E1E
0x180019e07  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180019e0e  jnz     short loc_180019E1E
0x180019e10  mov     r8d, ebp
0x180019e13  mov     rdx, rsi
0x180019e16  mov     rcx, rbx
0x180019e19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e1e  cmp     [rsi], di
0x180019e21  jnz     short loc_180019E31
0x180019e23  mov     r8, rbx; unsigned __int64
0x180019e26  mov     rdx, rbp; wchar_t *
0x180019e29  mov     rcx, rsi; this
0x180019e2c  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180019e31  mov     rcx, rsi; lpOutputString
0x180019e34  call    cs:__imp_OutputDebugStringW
0x180019e3a  test    byte ptr [rbx+4], 4
0x180019e3e  jnz     short loc_180019E49
0x180019e40  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180019e47  jz      short loc_180019E5B
0x180019e49  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180019e50  test    rax, rax
0x180019e53  jz      short loc_180019E5B
0x180019e55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e5a  nop
0x180019e5b  mov     rbx, [rsp+78h+arg_10]
0x180019e63  add     rsp, 40h
0x180019e67  pop     r15
0x180019e69  pop     r14
0x180019e6b  pop     r13
0x180019e6d  pop     r12
0x180019e6f  pop     rdi
0x180019e70  pop     rsi
0x180019e71  pop     rbp
0x180019e72  retn
0x180019e73  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
