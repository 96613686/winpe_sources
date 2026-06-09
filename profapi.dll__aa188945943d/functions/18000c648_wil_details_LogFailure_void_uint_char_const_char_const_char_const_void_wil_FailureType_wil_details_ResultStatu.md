# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000c648`
- end: `0x18000c93d`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x18000c3c0`
- `0x18000c54c`
- `0x180010964`

## callees

- `0x1800035e0`
- `0x18000b9a8`
- `0x18000be7c`
- `0x18000c308`
- `0x18000c648`
- `0x18000c950`
- `0x18001102c`
- `0x18001141c`
- `0x1800119fc`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c76b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c76b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000c88c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000c88c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000c8fe`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000c8fe`

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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v25 = !IsDebuggerPresent())
      : (v25 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v25)
    || (*(_BYTE *)(a16 + 4) & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, 0, 0, v23);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048, v23);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v23);
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
0x18000c648  mov     [rsp+arg_10], rbx
0x18000c64d  mov     [rsp+arg_8], edx
0x18000c651  mov     [rsp+arg_0], rcx
0x18000c656  push    rbp
0x18000c657  push    rsi
0x18000c658  push    rdi
0x18000c659  push    r12
0x18000c65b  push    r13
0x18000c65d  push    r14
0x18000c65f  push    r15
0x18000c661  sub     rsp, 40h
0x18000c665  mov     r12, r9
0x18000c668  mov     r13, r8
0x18000c66b  mov     r10, rcx
0x18000c66e  xor     eax, eax
0x18000c670  mov     rsi, [rsp+78h+lpOutputString]
0x18000c678  mov     [rsi], ax
0x18000c67b  mov     rax, [rsp+78h+arg_60]
0x18000c683  mov     byte ptr [rax], 0
0x18000c686  mov     r14, [rsp+78h+arg_38]
0x18000c68e  mov     edi, [r14]
0x18000c691  mov     rbx, [rsp+78h+arg_78]
0x18000c699  mov     [rbx+8], edi
0x18000c69c  mov     eax, [r14+4]
0x18000c6a0  mov     [rbx+0Ch], eax
0x18000c6a3  xor     ebp, ebp
0x18000c6a5  mov     r15d, [rsp+78h+arg_30]
0x18000c6ad  mov     ecx, r15d
0x18000c6b0  test    r15d, r15d
0x18000c6b3  jz      short loc_18000C71B
0x18000c6b5  sub     ecx, 1
0x18000c6b8  jz      short loc_18000C712
0x18000c6ba  sub     ecx, 1
0x18000c6bd  jz      short loc_18000C6CD
0x18000c6bf  cmp     ecx, 1
0x18000c6c2  jnz     short loc_18000C724
0x18000c6c4  mov     ecx, edi; this
0x18000c6c6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000c6cb  jmp     short loc_18000C722
0x18000c6cd  test    edi, edi
0x18000c6cf  js      short loc_18000C709
0x18000c6d1  mov     edi, 8007029Ch
0x18000c6d6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000c6da  mov     rax, [rsp+78h+arg_28]
0x18000c6e2  mov     [rsp+78h+var_50], rax; __int64
0x18000c6e7  mov     rax, [rsp+78h+arg_20]
0x18000c6ef  mov     [rsp+78h+var_58], rax; __int64
0x18000c6f4  mov     rcx, r10; int
0x18000c6f7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000c6fc  mov     [rbx+8], edi
0x18000c6ff  mov     ecx, edi; this
0x18000c701  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000c706  mov     [rbx+0Ch], eax
0x18000c709  mov     ecx, edi; this
0x18000c70b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000c710  jmp     short loc_18000C722
0x18000c712  mov     ecx, edi; this
0x18000c714  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000c719  jmp     short loc_18000C722
0x18000c71b  mov     ecx, edi; this
0x18000c71d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000c722  mov     ebp, eax
0x18000c724  mov     [rbx], r15d
0x18000c727  mov     eax, [rsp+78h+arg_70]
0x18000c72e  mov     [rbx+4], eax
0x18000c731  cmp     dword ptr [r14+8], 1
0x18000c736  jnz     short loc_18000C73E
0x18000c738  or      eax, 8
0x18000c73b  mov     [rbx+4], eax
0x18000c73e  mov     eax, 1
0x18000c743  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000c74b  inc     eax
0x18000c74d  mov     [rbx+10h], eax
0x18000c750  mov     rax, [rsp+78h+arg_40]
0x18000c758  xor     edi, edi
0x18000c75a  test    rax, rax
0x18000c75d  jz      short loc_18000C764
0x18000c75f  cmp     [rax], di
0x18000c762  jnz     short loc_18000C767
0x18000c764  mov     rax, rdi
0x18000c767  mov     [rbx+18h], rax
0x18000c76b  call    cs:__imp_GetCurrentThreadId
0x18000c771  mov     [rbx+20h], eax
0x18000c774  mov     [rbx+38h], r13
0x18000c778  mov     eax, [rsp+78h+arg_8]
0x18000c77f  mov     [rbx+40h], eax
0x18000c782  mov     [rbx+44h], ebp
0x18000c785  mov     rax, [rsp+78h+arg_20]
0x18000c78d  mov     [rbx+28h], rax
0x18000c791  mov     [rbx+30h], r12
0x18000c795  mov     rax, [rsp+78h+arg_28]
0x18000c79d  mov     [rbx+88h], rax
0x18000c7a4  mov     rax, [rsp+78h+arg_0]
0x18000c7ac  mov     [rbx+90h], rax
0x18000c7b3  mov     [rbx+48h], rdi
0x18000c7b7  xorps   xmm0, xmm0
0x18000c7ba  xor     eax, eax
0x18000c7bc  movups  xmmword ptr [rbx+68h], xmm0
0x18000c7c0  mov     [rbx+78h], rax
0x18000c7c4  movups  xmmword ptr [rbx+50h], xmm0
0x18000c7c8  mov     [rbx+60h], rax
0x18000c7cc  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000c7d3  test    rax, rax
0x18000c7d6  jz      short loc_18000C7DF
0x18000c7d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7dd  jmp     short loc_18000C7E2
0x18000c7df  mov     rax, rdi
0x18000c7e2  mov     [rbx+80h], rax
0x18000c7e9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000c7f0  test    rax, rax
0x18000c7f3  jz      short loc_18000C7FD
0x18000c7f5  mov     rcx, rbx
0x18000c7f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7fd  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000c804  test    rax, rax
0x18000c807  jz      short loc_18000C81F
0x18000c809  mov     r8d, 400h
0x18000c80f  mov     rdx, [rsp+78h+arg_60]
0x18000c817  mov     rcx, rbx
0x18000c81a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c81f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000c826  test    rax, rax
0x18000c829  jz      short loc_18000C833
0x18000c82b  mov     rcx, rbx
0x18000c82e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c833  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000c83a  test    rax, rax
0x18000c83d  jz      short loc_18000C84D
0x18000c83f  test    byte ptr [rbx+4], 2
0x18000c843  jnz     short loc_18000C84D
0x18000c845  mov     rcx, rbx
0x18000c848  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c84d  cmp     [rbx+8], edi
0x18000c850  jl      short loc_18000C86E
0x18000c852  cmp     r15d, 3
0x18000c856  jz      short loc_18000C85E
0x18000c858  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000c85e  mov     ecx, 8000FFFFh; this
0x18000c863  mov     [rbx+8], ecx
0x18000c866  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000c86b  mov     [rbx+0Ch], eax
0x18000c86e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000c875  jnz     short loc_18000C896
0x18000c877  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000c87e  test    rax, rax
0x18000c881  jz      short loc_18000C88C
0x18000c883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c888  test    al, al
0x18000c88a  jmp     short loc_18000C894
0x18000c88c  call    cs:__imp_IsDebuggerPresent
0x18000c892  test    eax, eax
0x18000c894  jz      short loc_18000C89C
0x18000c896  test    byte ptr [rbx+4], 2
0x18000c89a  jz      short loc_18000C8C0
0x18000c89c  mov     rax, cs:g_pfnResultLoggingCallback
0x18000c8a3  test    rax, rax
0x18000c8a6  jz      short loc_18000C904
0x18000c8a8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000c8af  jnz     short loc_18000C904
0x18000c8b1  xor     r8d, r8d
0x18000c8b4  xor     edx, edx
0x18000c8b6  mov     rcx, rbx
0x18000c8b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c8be  jmp     short loc_18000C904
0x18000c8c0  mov     ebp, 800h
0x18000c8c5  mov     rax, cs:g_pfnResultLoggingCallback
0x18000c8cc  test    rax, rax
0x18000c8cf  jz      short loc_18000C8E8
0x18000c8d1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000c8d8  jnz     short loc_18000C8E8
0x18000c8da  mov     r8d, ebp
0x18000c8dd  mov     rdx, rsi
0x18000c8e0  mov     rcx, rbx
0x18000c8e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c8e8  cmp     [rsi], di
0x18000c8eb  jnz     short loc_18000C8FB
0x18000c8ed  mov     r8, rbx; unsigned __int64
0x18000c8f0  mov     rdx, rbp; unsigned __int16 *
0x18000c8f3  mov     rcx, rsi; this
0x18000c8f6  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000c8fb  mov     rcx, rsi; lpOutputString
0x18000c8fe  call    cs:__imp_OutputDebugStringW
0x18000c904  test    byte ptr [rbx+4], 4
0x18000c908  jnz     short loc_18000C913
0x18000c90a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000c911  jz      short loc_18000C925
0x18000c913  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000c91a  test    rax, rax
0x18000c91d  jz      short loc_18000C925
0x18000c91f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c924  nop
0x18000c925  mov     rbx, [rsp+78h+arg_10]
0x18000c92d  add     rsp, 40h
0x18000c931  pop     r15
0x18000c933  pop     r14
0x18000c935  pop     r13
0x18000c937  pop     r12
0x18000c939  pop     rdi
0x18000c93a  pop     rsi
0x18000c93b  pop     rbp
0x18000c93c  retn
```
