# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000bad4`
- end: `0x18000bdcd`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x18000a16c`
- `0x18000a4d8`
- `0x18000d85c`

## callees

- `0x18000a0a0`
- `0x18000b114`
- `0x18000b910`
- `0x18000bad4`
- `0x18000c1f8`
- `0x18000c220`
- `0x18000c234`
- `0x18000c250`
- `0x18000cfd8`
- `0x18004b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bbf7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bbf7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000bd16`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000bd16`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000bd88`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000bd88`

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
0x18000bad4  mov     [rsp+arg_10], rbx
0x18000bad9  mov     [rsp+arg_8], edx
0x18000badd  mov     [rsp+arg_0], rcx
0x18000bae2  push    rbp
0x18000bae3  push    rsi
0x18000bae4  push    rdi
0x18000bae5  push    r12
0x18000bae7  push    r13
0x18000bae9  push    r14
0x18000baeb  push    r15
0x18000baed  sub     rsp, 40h
0x18000baf1  mov     r12, r9
0x18000baf4  mov     r13, r8
0x18000baf7  mov     r10, rcx
0x18000bafa  xor     eax, eax
0x18000bafc  mov     rsi, [rsp+78h+lpOutputString]
0x18000bb04  mov     [rsi], ax
0x18000bb07  mov     rax, [rsp+78h+arg_60]
0x18000bb0f  mov     byte ptr [rax], 0
0x18000bb12  mov     r14, [rsp+78h+arg_38]
0x18000bb1a  mov     edi, [r14]
0x18000bb1d  mov     rbx, [rsp+78h+arg_78]
0x18000bb25  mov     [rbx+8], edi
0x18000bb28  mov     eax, [r14+4]
0x18000bb2c  mov     [rbx+0Ch], eax
0x18000bb2f  xor     ebp, ebp
0x18000bb31  mov     r15d, [rsp+78h+arg_30]
0x18000bb39  mov     ecx, r15d
0x18000bb3c  test    r15d, r15d
0x18000bb3f  jz      short loc_18000BBA7
0x18000bb41  sub     ecx, 1
0x18000bb44  jz      short loc_18000BB9E
0x18000bb46  sub     ecx, 1
0x18000bb49  jz      short loc_18000BB59
0x18000bb4b  cmp     ecx, 1
0x18000bb4e  jnz     short loc_18000BBB0
0x18000bb50  mov     ecx, edi; this
0x18000bb52  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000bb57  jmp     short loc_18000BBAE
0x18000bb59  test    edi, edi
0x18000bb5b  js      short loc_18000BB95
0x18000bb5d  mov     edi, 8007029Ch
0x18000bb62  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000bb66  mov     rax, [rsp+78h+arg_28]
0x18000bb6e  mov     [rsp+78h+var_50], rax; __int64
0x18000bb73  mov     rax, [rsp+78h+arg_20]
0x18000bb7b  mov     [rsp+78h+var_58], rax; __int64
0x18000bb80  mov     rcx, r10; int
0x18000bb83  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000bb88  mov     [rbx+8], edi
0x18000bb8b  mov     ecx, edi; this
0x18000bb8d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000bb92  mov     [rbx+0Ch], eax
0x18000bb95  mov     ecx, edi; this
0x18000bb97  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000bb9c  jmp     short loc_18000BBAE
0x18000bb9e  mov     ecx, edi; this
0x18000bba0  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000bba5  jmp     short loc_18000BBAE
0x18000bba7  mov     ecx, edi; this
0x18000bba9  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000bbae  mov     ebp, eax
0x18000bbb0  mov     [rbx], r15d
0x18000bbb3  mov     eax, [rsp+78h+arg_70]
0x18000bbba  mov     [rbx+4], eax
0x18000bbbd  cmp     dword ptr [r14+8], 1
0x18000bbc2  jnz     short loc_18000BBCA
0x18000bbc4  or      eax, 8
0x18000bbc7  mov     [rbx+4], eax
0x18000bbca  mov     eax, 1
0x18000bbcf  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000bbd7  inc     eax
0x18000bbd9  mov     [rbx+10h], eax
0x18000bbdc  mov     rax, [rsp+78h+arg_40]
0x18000bbe4  xor     edi, edi
0x18000bbe6  test    rax, rax
0x18000bbe9  jz      short loc_18000BBF0
0x18000bbeb  cmp     [rax], di
0x18000bbee  jnz     short loc_18000BBF3
0x18000bbf0  mov     rax, rdi
0x18000bbf3  mov     [rbx+18h], rax
0x18000bbf7  call    cs:__imp_GetCurrentThreadId
0x18000bbfd  mov     [rbx+20h], eax
0x18000bc00  mov     [rbx+38h], r13
0x18000bc04  mov     eax, [rsp+78h+arg_8]
0x18000bc0b  mov     [rbx+40h], eax
0x18000bc0e  mov     [rbx+44h], ebp
0x18000bc11  mov     rax, [rsp+78h+arg_20]
0x18000bc19  mov     [rbx+28h], rax
0x18000bc1d  mov     [rbx+30h], r12
0x18000bc21  mov     rax, [rsp+78h+arg_28]
0x18000bc29  mov     [rbx+88h], rax
0x18000bc30  mov     rax, [rsp+78h+arg_0]
0x18000bc38  mov     [rbx+90h], rax
0x18000bc3f  mov     [rbx+48h], rdi
0x18000bc43  xorps   xmm0, xmm0
0x18000bc46  xor     eax, eax
0x18000bc48  movups  xmmword ptr [rbx+68h], xmm0
0x18000bc4c  mov     [rbx+78h], rax
0x18000bc50  movups  xmmword ptr [rbx+50h], xmm0
0x18000bc54  mov     [rbx+60h], rax
0x18000bc58  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000bc5f  test    rax, rax
0x18000bc62  jz      short loc_18000BC6B
0x18000bc64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc69  jmp     short loc_18000BC6E
0x18000bc6b  mov     rax, rdi
0x18000bc6e  mov     [rbx+80h], rax
0x18000bc75  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000bc7c  test    rax, rax
0x18000bc7f  jz      short loc_18000BC89
0x18000bc81  mov     rcx, rbx
0x18000bc84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc89  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000bc90  test    rax, rax
0x18000bc93  jz      short loc_18000BCAB
0x18000bc95  mov     r8d, 400h
0x18000bc9b  mov     rdx, [rsp+78h+arg_60]
0x18000bca3  mov     rcx, rbx
0x18000bca6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcab  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000bcb2  test    rax, rax
0x18000bcb5  jz      short loc_18000BCBF
0x18000bcb7  mov     rcx, rbx
0x18000bcba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcbf  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000bcc6  test    rax, rax
0x18000bcc9  jz      short loc_18000BCD9
0x18000bccb  test    byte ptr [rbx+4], 2
0x18000bccf  jnz     short loc_18000BCD9
0x18000bcd1  mov     rcx, rbx
0x18000bcd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcd9  cmp     [rbx+8], edi
0x18000bcdc  jl      short loc_18000BCF8
0x18000bcde  cmp     r15d, 3
0x18000bce2  jnz     loc_18000BDC7
0x18000bce8  mov     ecx, 8000FFFFh; this
0x18000bced  mov     [rbx+8], ecx
0x18000bcf0  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000bcf5  mov     [rbx+0Ch], eax
0x18000bcf8  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000bcff  jnz     short loc_18000BD20
0x18000bd01  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000bd08  test    rax, rax
0x18000bd0b  jz      short loc_18000BD16
0x18000bd0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd12  test    al, al
0x18000bd14  jmp     short loc_18000BD1E
0x18000bd16  call    cs:__imp_IsDebuggerPresent
0x18000bd1c  test    eax, eax
0x18000bd1e  jz      short loc_18000BD26
0x18000bd20  test    byte ptr [rbx+4], 2
0x18000bd24  jz      short loc_18000BD4A
0x18000bd26  mov     rax, cs:g_pfnResultLoggingCallback
0x18000bd2d  test    rax, rax
0x18000bd30  jz      short loc_18000BD8E
0x18000bd32  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000bd39  jnz     short loc_18000BD8E
0x18000bd3b  xor     r8d, r8d
0x18000bd3e  xor     edx, edx
0x18000bd40  mov     rcx, rbx
0x18000bd43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd48  jmp     short loc_18000BD8E
0x18000bd4a  mov     ebp, 800h
0x18000bd4f  mov     rax, cs:g_pfnResultLoggingCallback
0x18000bd56  test    rax, rax
0x18000bd59  jz      short loc_18000BD72
0x18000bd5b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000bd62  jnz     short loc_18000BD72
0x18000bd64  mov     r8d, ebp
0x18000bd67  mov     rdx, rsi
0x18000bd6a  mov     rcx, rbx
0x18000bd6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd72  cmp     [rsi], di
0x18000bd75  jnz     short loc_18000BD85
0x18000bd77  mov     r8, rbx; unsigned __int64
0x18000bd7a  mov     rdx, rbp; wchar_t *
0x18000bd7d  mov     rcx, rsi; this
0x18000bd80  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18000bd85  mov     rcx, rsi; lpOutputString
0x18000bd88  call    cs:__imp_OutputDebugStringW
0x18000bd8e  test    byte ptr [rbx+4], 4
0x18000bd92  jnz     short loc_18000BD9D
0x18000bd94  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000bd9b  jz      short loc_18000BDAF
0x18000bd9d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000bda4  test    rax, rax
0x18000bda7  jz      short loc_18000BDAF
0x18000bda9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bdae  nop
0x18000bdaf  mov     rbx, [rsp+78h+arg_10]
0x18000bdb7  add     rsp, 40h
0x18000bdbb  pop     r15
0x18000bdbd  pop     r14
0x18000bdbf  pop     r13
0x18000bdc1  pop     r12
0x18000bdc3  pop     rdi
0x18000bdc4  pop     rsi
0x18000bdc5  pop     rbp
0x18000bdc6  retn
0x18000bdc7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
