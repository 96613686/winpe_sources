# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000b484`
- end: `0x18000b77d`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180007a94`
- `0x180007de8`

## callees

- `0x180007940`
- `0x18000a3b8`
- `0x18000ae80`
- `0x18000b484`
- `0x18000c4d8`
- `0x18000c500`
- `0x18000c514`
- `0x18000c530`
- `0x18000eb94`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b5a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b5a7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000b738`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000b738`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000b6c6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000b6c6`

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
0x18000b484  mov     [rsp+arg_10], rbx
0x18000b489  mov     [rsp+arg_8], edx
0x18000b48d  mov     [rsp+arg_0], rcx
0x18000b492  push    rbp
0x18000b493  push    rsi
0x18000b494  push    rdi
0x18000b495  push    r12
0x18000b497  push    r13
0x18000b499  push    r14
0x18000b49b  push    r15
0x18000b49d  sub     rsp, 40h
0x18000b4a1  mov     r12, r9
0x18000b4a4  mov     r13, r8
0x18000b4a7  mov     r10, rcx
0x18000b4aa  xor     eax, eax
0x18000b4ac  mov     rsi, [rsp+78h+lpOutputString]
0x18000b4b4  mov     [rsi], ax
0x18000b4b7  mov     rax, [rsp+78h+arg_60]
0x18000b4bf  mov     byte ptr [rax], 0
0x18000b4c2  mov     r14, [rsp+78h+arg_38]
0x18000b4ca  mov     edi, [r14]
0x18000b4cd  mov     rbx, [rsp+78h+arg_78]
0x18000b4d5  mov     [rbx+8], edi
0x18000b4d8  mov     eax, [r14+4]
0x18000b4dc  mov     [rbx+0Ch], eax
0x18000b4df  xor     ebp, ebp
0x18000b4e1  mov     r15d, [rsp+78h+arg_30]
0x18000b4e9  mov     ecx, r15d
0x18000b4ec  test    r15d, r15d
0x18000b4ef  jz      short loc_18000B557
0x18000b4f1  sub     ecx, 1
0x18000b4f4  jz      short loc_18000B54E
0x18000b4f6  sub     ecx, 1
0x18000b4f9  jz      short loc_18000B509
0x18000b4fb  cmp     ecx, 1
0x18000b4fe  jnz     short loc_18000B560
0x18000b500  mov     ecx, edi; this
0x18000b502  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000b507  jmp     short loc_18000B55E
0x18000b509  test    edi, edi
0x18000b50b  js      short loc_18000B545
0x18000b50d  mov     edi, 8007029Ch
0x18000b512  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000b516  mov     rax, [rsp+78h+arg_28]
0x18000b51e  mov     [rsp+78h+var_50], rax; __int64
0x18000b523  mov     rax, [rsp+78h+arg_20]
0x18000b52b  mov     [rsp+78h+var_58], rax; __int64
0x18000b530  mov     rcx, r10; int
0x18000b533  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000b538  mov     [rbx+8], edi
0x18000b53b  mov     ecx, edi; this
0x18000b53d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000b542  mov     [rbx+0Ch], eax
0x18000b545  mov     ecx, edi; this
0x18000b547  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000b54c  jmp     short loc_18000B55E
0x18000b54e  mov     ecx, edi; this
0x18000b550  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000b555  jmp     short loc_18000B55E
0x18000b557  mov     ecx, edi; this
0x18000b559  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000b55e  mov     ebp, eax
0x18000b560  mov     [rbx], r15d
0x18000b563  mov     eax, [rsp+78h+arg_70]
0x18000b56a  mov     [rbx+4], eax
0x18000b56d  cmp     dword ptr [r14+8], 1
0x18000b572  jnz     short loc_18000B57A
0x18000b574  or      eax, 8
0x18000b577  mov     [rbx+4], eax
0x18000b57a  mov     eax, 1
0x18000b57f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000b587  inc     eax
0x18000b589  mov     [rbx+10h], eax
0x18000b58c  mov     rax, [rsp+78h+arg_40]
0x18000b594  xor     edi, edi
0x18000b596  test    rax, rax
0x18000b599  jz      short loc_18000B5A0
0x18000b59b  cmp     [rax], di
0x18000b59e  jnz     short loc_18000B5A3
0x18000b5a0  mov     rax, rdi
0x18000b5a3  mov     [rbx+18h], rax
0x18000b5a7  call    cs:__imp_GetCurrentThreadId
0x18000b5ad  mov     [rbx+20h], eax
0x18000b5b0  mov     [rbx+38h], r13
0x18000b5b4  mov     eax, [rsp+78h+arg_8]
0x18000b5bb  mov     [rbx+40h], eax
0x18000b5be  mov     [rbx+44h], ebp
0x18000b5c1  mov     rax, [rsp+78h+arg_20]
0x18000b5c9  mov     [rbx+28h], rax
0x18000b5cd  mov     [rbx+30h], r12
0x18000b5d1  mov     rax, [rsp+78h+arg_28]
0x18000b5d9  mov     [rbx+88h], rax
0x18000b5e0  mov     rax, [rsp+78h+arg_0]
0x18000b5e8  mov     [rbx+90h], rax
0x18000b5ef  mov     [rbx+48h], rdi
0x18000b5f3  xorps   xmm0, xmm0
0x18000b5f6  xor     eax, eax
0x18000b5f8  movups  xmmword ptr [rbx+68h], xmm0
0x18000b5fc  mov     [rbx+78h], rax
0x18000b600  movups  xmmword ptr [rbx+50h], xmm0
0x18000b604  mov     [rbx+60h], rax
0x18000b608  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000b60f  test    rax, rax
0x18000b612  jz      short loc_18000B61B
0x18000b614  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b619  jmp     short loc_18000B61E
0x18000b61b  mov     rax, rdi
0x18000b61e  mov     [rbx+80h], rax
0x18000b625  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000b62c  test    rax, rax
0x18000b62f  jz      short loc_18000B639
0x18000b631  mov     rcx, rbx
0x18000b634  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b639  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000b640  test    rax, rax
0x18000b643  jz      short loc_18000B65B
0x18000b645  mov     r8d, 400h
0x18000b64b  mov     rdx, [rsp+78h+arg_60]
0x18000b653  mov     rcx, rbx
0x18000b656  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b65b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000b662  test    rax, rax
0x18000b665  jz      short loc_18000B66F
0x18000b667  mov     rcx, rbx
0x18000b66a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b66f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000b676  test    rax, rax
0x18000b679  jz      short loc_18000B689
0x18000b67b  test    byte ptr [rbx+4], 2
0x18000b67f  jnz     short loc_18000B689
0x18000b681  mov     rcx, rbx
0x18000b684  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b689  cmp     [rbx+8], edi
0x18000b68c  jl      short loc_18000B6A8
0x18000b68e  cmp     r15d, 3
0x18000b692  jnz     loc_18000B777
0x18000b698  mov     ecx, 8000FFFFh; this
0x18000b69d  mov     [rbx+8], ecx
0x18000b6a0  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000b6a5  mov     [rbx+0Ch], eax
0x18000b6a8  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000b6af  jnz     short loc_18000B6D0
0x18000b6b1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000b6b8  test    rax, rax
0x18000b6bb  jz      short loc_18000B6C6
0x18000b6bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6c2  test    al, al
0x18000b6c4  jmp     short loc_18000B6CE
0x18000b6c6  call    cs:__imp_IsDebuggerPresent
0x18000b6cc  test    eax, eax
0x18000b6ce  jz      short loc_18000B6D6
0x18000b6d0  test    byte ptr [rbx+4], 2
0x18000b6d4  jz      short loc_18000B6FA
0x18000b6d6  mov     rax, cs:g_pfnResultLoggingCallback
0x18000b6dd  test    rax, rax
0x18000b6e0  jz      short loc_18000B73E
0x18000b6e2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000b6e9  jnz     short loc_18000B73E
0x18000b6eb  xor     r8d, r8d
0x18000b6ee  xor     edx, edx
0x18000b6f0  mov     rcx, rbx
0x18000b6f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6f8  jmp     short loc_18000B73E
0x18000b6fa  mov     ebp, 800h
0x18000b6ff  mov     rax, cs:g_pfnResultLoggingCallback
0x18000b706  test    rax, rax
0x18000b709  jz      short loc_18000B722
0x18000b70b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000b712  jnz     short loc_18000B722
0x18000b714  mov     r8d, ebp
0x18000b717  mov     rdx, rsi
0x18000b71a  mov     rcx, rbx
0x18000b71d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b722  cmp     [rsi], di
0x18000b725  jnz     short loc_18000B735
0x18000b727  mov     r8, rbx; unsigned __int64
0x18000b72a  mov     rdx, rbp; unsigned __int16 *
0x18000b72d  mov     rcx, rsi; this
0x18000b730  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000b735  mov     rcx, rsi; lpOutputString
0x18000b738  call    cs:__imp_OutputDebugStringW
0x18000b73e  test    byte ptr [rbx+4], 4
0x18000b742  jnz     short loc_18000B74D
0x18000b744  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000b74b  jz      short loc_18000B75F
0x18000b74d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000b754  test    rax, rax
0x18000b757  jz      short loc_18000B75F
0x18000b759  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b75e  nop
0x18000b75f  mov     rbx, [rsp+78h+arg_10]
0x18000b767  add     rsp, 40h
0x18000b76b  pop     r15
0x18000b76d  pop     r14
0x18000b76f  pop     r13
0x18000b771  pop     r12
0x18000b773  pop     rdi
0x18000b774  pop     rsi
0x18000b775  pop     rbp
0x18000b776  retn
0x18000b777  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
