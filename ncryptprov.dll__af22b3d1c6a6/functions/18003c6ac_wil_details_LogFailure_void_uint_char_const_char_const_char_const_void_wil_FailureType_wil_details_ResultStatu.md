# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18003c6ac`
- end: `0x18003c9b4`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `776`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180039f38`
- `0x180039fe8`
- `0x18003a0e0`

## callees

- `0x180037430`
- `0x180039e8c`
- `0x18003ba14`
- `0x18003c6ac`
- `0x18003d214`
- `0x18003d240`
- `0x18003d304`
- `0x18003d324`
- `0x18003ed18`
- `0x180063010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003c7cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003c7cf`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18003c8f6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18003c8f6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18003c96e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18003c96e`

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
      g_pfnResultLoggingCallback(a16, 0, 0, v25);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048, v25);
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
0x18003c6ac  mov     [rsp+arg_10], rbx
0x18003c6b1  mov     [rsp+arg_8], edx
0x18003c6b5  mov     [rsp+arg_0], rcx
0x18003c6ba  push    rbp
0x18003c6bb  push    rsi
0x18003c6bc  push    rdi
0x18003c6bd  push    r12
0x18003c6bf  push    r13
0x18003c6c1  push    r14
0x18003c6c3  push    r15
0x18003c6c5  sub     rsp, 40h
0x18003c6c9  mov     r12, r9
0x18003c6cc  mov     r13, r8
0x18003c6cf  mov     r10, rcx
0x18003c6d2  xor     eax, eax
0x18003c6d4  mov     rsi, [rsp+78h+lpOutputString]
0x18003c6dc  mov     [rsi], ax
0x18003c6df  mov     rax, [rsp+78h+arg_60]
0x18003c6e7  mov     byte ptr [rax], 0
0x18003c6ea  mov     r14, [rsp+78h+arg_38]
0x18003c6f2  mov     edi, [r14]
0x18003c6f5  mov     rbx, [rsp+78h+arg_78]
0x18003c6fd  mov     [rbx+8], edi
0x18003c700  mov     eax, [r14+4]
0x18003c704  mov     [rbx+0Ch], eax
0x18003c707  xor     ebp, ebp
0x18003c709  mov     r15d, [rsp+78h+arg_30]
0x18003c711  mov     ecx, r15d
0x18003c714  test    r15d, r15d
0x18003c717  jz      short loc_18003C77F
0x18003c719  sub     ecx, 1
0x18003c71c  jz      short loc_18003C776
0x18003c71e  sub     ecx, 1
0x18003c721  jz      short loc_18003C731
0x18003c723  cmp     ecx, 1
0x18003c726  jnz     short loc_18003C788
0x18003c728  mov     ecx, edi; this
0x18003c72a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18003c72f  jmp     short loc_18003C786
0x18003c731  test    edi, edi
0x18003c733  js      short loc_18003C76D
0x18003c735  mov     edi, 8007029Ch
0x18003c73a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18003c73e  mov     rax, [rsp+78h+arg_28]
0x18003c746  mov     [rsp+78h+var_50], rax; __int64
0x18003c74b  mov     rax, [rsp+78h+arg_20]
0x18003c753  mov     [rsp+78h+var_58], rax; __int64
0x18003c758  mov     rcx, r10; int
0x18003c75b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18003c760  mov     [rbx+8], edi
0x18003c763  mov     ecx, edi; this
0x18003c765  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18003c76a  mov     [rbx+0Ch], eax
0x18003c76d  mov     ecx, edi; this
0x18003c76f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18003c774  jmp     short loc_18003C786
0x18003c776  mov     ecx, edi; this
0x18003c778  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18003c77d  jmp     short loc_18003C786
0x18003c77f  mov     ecx, edi; this
0x18003c781  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18003c786  mov     ebp, eax
0x18003c788  mov     [rbx], r15d
0x18003c78b  mov     eax, [rsp+78h+arg_70]
0x18003c792  mov     [rbx+4], eax
0x18003c795  cmp     dword ptr [r14+8], 1
0x18003c79a  jnz     short loc_18003C7A2
0x18003c79c  or      eax, 8
0x18003c79f  mov     [rbx+4], eax
0x18003c7a2  mov     eax, 1
0x18003c7a7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18003c7af  inc     eax
0x18003c7b1  mov     [rbx+10h], eax
0x18003c7b4  mov     rax, [rsp+78h+arg_40]
0x18003c7bc  xor     edi, edi
0x18003c7be  test    rax, rax
0x18003c7c1  jz      short loc_18003C7C8
0x18003c7c3  cmp     [rax], di
0x18003c7c6  jnz     short loc_18003C7CB
0x18003c7c8  mov     rax, rdi
0x18003c7cb  mov     [rbx+18h], rax
0x18003c7cf  call    cs:__imp_GetCurrentThreadId
0x18003c7d6  nop     dword ptr [rax+rax+00h]
0x18003c7db  mov     [rbx+20h], eax
0x18003c7de  mov     [rbx+38h], r13
0x18003c7e2  mov     eax, [rsp+78h+arg_8]
0x18003c7e9  mov     [rbx+40h], eax
0x18003c7ec  mov     [rbx+44h], ebp
0x18003c7ef  mov     rax, [rsp+78h+arg_20]
0x18003c7f7  mov     [rbx+28h], rax
0x18003c7fb  mov     [rbx+30h], r12
0x18003c7ff  mov     rax, [rsp+78h+arg_28]
0x18003c807  mov     [rbx+88h], rax
0x18003c80e  mov     rax, [rsp+78h+arg_0]
0x18003c816  mov     [rbx+90h], rax
0x18003c81d  mov     [rbx+48h], rdi
0x18003c821  xorps   xmm0, xmm0
0x18003c824  xor     eax, eax
0x18003c826  movups  xmmword ptr [rbx+68h], xmm0
0x18003c82a  mov     [rbx+78h], rax
0x18003c82e  movups  xmmword ptr [rbx+50h], xmm0
0x18003c832  mov     [rbx+60h], rax
0x18003c836  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18003c83d  test    rax, rax
0x18003c840  jz      short loc_18003C849
0x18003c842  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c847  jmp     short loc_18003C84C
0x18003c849  mov     rax, rdi
0x18003c84c  mov     [rbx+80h], rax
0x18003c853  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18003c85a  test    rax, rax
0x18003c85d  jz      short loc_18003C867
0x18003c85f  mov     rcx, rbx
0x18003c862  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c867  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18003c86e  test    rax, rax
0x18003c871  jz      short loc_18003C889
0x18003c873  mov     r8d, 400h
0x18003c879  mov     rdx, [rsp+78h+arg_60]
0x18003c881  mov     rcx, rbx
0x18003c884  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c889  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18003c890  test    rax, rax
0x18003c893  jz      short loc_18003C89D
0x18003c895  mov     rcx, rbx
0x18003c898  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c89d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18003c8a4  test    rax, rax
0x18003c8a7  jz      short loc_18003C8B7
0x18003c8a9  test    byte ptr [rbx+4], 2
0x18003c8ad  jnz     short loc_18003C8B7
0x18003c8af  mov     rcx, rbx
0x18003c8b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c8b7  cmp     [rbx+8], edi
0x18003c8ba  jl      short loc_18003C8D8
0x18003c8bc  cmp     r15d, 3
0x18003c8c0  jz      short loc_18003C8C8
0x18003c8c2  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18003c8c8  mov     ecx, 8000FFFFh; this
0x18003c8cd  mov     [rbx+8], ecx
0x18003c8d0  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18003c8d5  mov     [rbx+0Ch], eax
0x18003c8d8  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18003c8df  jnz     short loc_18003C906
0x18003c8e1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18003c8e8  test    rax, rax
0x18003c8eb  jz      short loc_18003C8F6
0x18003c8ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c8f2  test    al, al
0x18003c8f4  jmp     short loc_18003C904
0x18003c8f6  call    cs:__imp_IsDebuggerPresent
0x18003c8fd  nop     dword ptr [rax+rax+00h]
0x18003c902  test    eax, eax
0x18003c904  jz      short loc_18003C90C
0x18003c906  test    byte ptr [rbx+4], 2
0x18003c90a  jz      short loc_18003C930
0x18003c90c  mov     rax, cs:g_pfnResultLoggingCallback
0x18003c913  test    rax, rax
0x18003c916  jz      short loc_18003C97A
0x18003c918  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18003c91f  jnz     short loc_18003C97A
0x18003c921  xor     r8d, r8d
0x18003c924  xor     edx, edx
0x18003c926  mov     rcx, rbx
0x18003c929  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c92e  jmp     short loc_18003C97A
0x18003c930  mov     ebp, 800h
0x18003c935  mov     rax, cs:g_pfnResultLoggingCallback
0x18003c93c  test    rax, rax
0x18003c93f  jz      short loc_18003C958
0x18003c941  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18003c948  jnz     short loc_18003C958
0x18003c94a  mov     r8d, ebp
0x18003c94d  mov     rdx, rsi
0x18003c950  mov     rcx, rbx
0x18003c953  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c958  cmp     [rsi], di
0x18003c95b  jnz     short loc_18003C96B
0x18003c95d  mov     r8, rbx; unsigned __int64
0x18003c960  mov     rdx, rbp; unsigned __int16 *
0x18003c963  mov     rcx, rsi; this
0x18003c966  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18003c96b  mov     rcx, rsi; lpOutputString
0x18003c96e  call    cs:__imp_OutputDebugStringW
0x18003c975  nop     dword ptr [rax+rax+00h]
0x18003c97a  test    byte ptr [rbx+4], 4
0x18003c97e  jnz     short loc_18003C989
0x18003c980  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18003c987  jz      short loc_18003C99B
0x18003c989  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18003c990  test    rax, rax
0x18003c993  jz      short loc_18003C99B
0x18003c995  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c99a  nop
0x18003c99b  mov     rbx, [rsp+78h+arg_10]
0x18003c9a3  add     rsp, 40h
0x18003c9a7  pop     r15
0x18003c9a9  pop     r14
0x18003c9ab  pop     r13
0x18003c9ad  pop     r12
0x18003c9af  pop     rdi
0x18003c9b0  pop     rsi
0x18003c9b1  pop     rbp
0x18003c9b2  retn
```
