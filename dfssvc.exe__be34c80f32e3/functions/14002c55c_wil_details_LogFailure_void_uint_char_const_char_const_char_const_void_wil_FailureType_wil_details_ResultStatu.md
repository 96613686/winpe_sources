# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)

- ea: `0x14002c55c`
- end: `0x14002c85f`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7PEAUFailureInfo@2@@Z`
- size: `771`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x140026b64`
- `0x140026c10`
- `0x140026d04`

## callees

- `0x140026ab8`
- `0x14002ade4`
- `0x14002b63c`
- `0x14002c55c`
- `0x14002d8e8`
- `0x14002d910`
- `0x14002dadc`
- `0x14002dafc`
- `0x140031c08`
- `0x14005e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002c67b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002c67b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14002c81a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14002c81a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14002c7a1`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14002c7a1`

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
        WCHAR *lpOutputString,
        __int64 a12,
        _BYTE *a13,
        __int64 a14,
        unsigned __int64 a15)
{
  int v17; // esi
  unsigned int v18; // edi
  int v19; // eax
  int v20; // edx
  _WORD *v21; // rax
  DWORD CurrentThreadId; // eax
  int v23; // edx
  wil::details::in1diag3 *v24; // rcx
  const struct wil::FailureInfo *v25; // r9
  __int64 ModuleName; // rax
  bool v27; // zf
  wil::details *v28; // [rsp+30h] [rbp-48h]

  v17 = 0;
  *lpOutputString = 0;
  *a13 = 0;
  v18 = *a8;
  *(_DWORD *)(a15 + 8) = *a8;
  *(_DWORD *)(a15 + 12) = a8[1];
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1:
        v19 = wil::details::RecordReturn((wil::details *)v18, a2);
        break;
      case 2:
        if ( (v18 & 0x80000000) == 0 )
        {
          v18 = -2147024228;
          LODWORD(v28) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v28);
          *(_DWORD *)(a15 + 8) = -2147024228;
          *(_DWORD *)(a15 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v20);
        }
        v19 = wil::details::RecordLog((wil::details *)v18, a2);
        break;
      case 3:
        v19 = wil::details::RecordFailFast((wil::details *)v18, a2);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v19 = wil::details::RecordException((wil::details *)v18, a2);
  }
  v17 = v19;
LABEL_12:
  *(_DWORD *)a15 = a7;
  *(_DWORD *)(a15 + 4) = 0;
  if ( a8[2] == 1 )
    *(_DWORD *)(a15 + 4) = 8;
  *(_DWORD *)(a15 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = a9;
  if ( !a9 || !*a9 )
    v21 = 0;
  *(_QWORD *)(a15 + 24) = v21;
  CurrentThreadId = GetCurrentThreadId();
  *(_QWORD *)(a15 + 56) = a3;
  *(_DWORD *)(a15 + 32) = CurrentThreadId;
  *(_DWORD *)(a15 + 64) = a2;
  *(_QWORD *)(a15 + 40) = a5;
  *(_QWORD *)(a15 + 136) = a6;
  *(_QWORD *)(a15 + 144) = a1;
  *(_DWORD *)(a15 + 68) = v17;
  *(_QWORD *)(a15 + 48) = a4;
  *(_QWORD *)(a15 + 72) = 0;
  *(_OWORD *)(a15 + 104) = 0;
  *(_QWORD *)(a15 + 120) = 0;
  *(_OWORD *)(a15 + 80) = 0;
  *(_QWORD *)(a15 + 96) = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName();
  else
    ModuleName = 0;
  *(_QWORD *)(a15 + 128) = ModuleName;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(a15);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(a15, a13, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(a15);
  if ( wil::details::g_pfnOriginateCallback && (*(_BYTE *)(a15 + 4) & 2) == 0 )
    wil::details::g_pfnOriginateCallback(a15);
  if ( *(int *)(a15 + 8) >= 0 )
  {
    if ( a7 != 3 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
    *(_DWORD *)(a15 + 8) = -2147418113;
    *(_DWORD *)(a15 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v23);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v27 = !IsDebuggerPresent())
      : (v27 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v27)
    || (*(_BYTE *)(a15 + 4) & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a15, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a15, lpOutputString, 2048);
    if ( !*lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a15, v25);
    OutputDebugStringW(lpOutputString);
  }
  if ( (*(_BYTE *)(a15 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak();
  }
}

```

## disassembly

```asm
0x14002c55c  mov     [rsp+arg_10], rbx
0x14002c561  mov     [rsp+arg_8], edx
0x14002c565  mov     [rsp+arg_0], rcx
0x14002c56a  push    rbp
0x14002c56b  push    rsi
0x14002c56c  push    rdi
0x14002c56d  push    r12
0x14002c56f  push    r13
0x14002c571  push    r14
0x14002c573  push    r15
0x14002c575  sub     rsp, 40h
0x14002c579  mov     rax, [rsp+78h+arg_60]
0x14002c581  mov     r13, r8
0x14002c584  mov     r15, [rsp+78h+arg_38]
0x14002c58c  xor     r8d, r8d
0x14002c58f  mov     rbx, [rsp+78h+arg_70]
0x14002c597  mov     r10, rcx
0x14002c59a  mov     ebp, [rsp+78h+arg_30]
0x14002c5a1  mov     r12, r9
0x14002c5a4  mov     r14, [rsp+78h+lpOutputString]
0x14002c5ac  mov     esi, r8d
0x14002c5af  mov     ecx, ebp
0x14002c5b1  mov     [r14], r8w
0x14002c5b5  mov     [rax], r8b
0x14002c5b8  mov     edi, [r15]
0x14002c5bb  mov     [rbx+8], edi
0x14002c5be  mov     eax, [r15+4]
0x14002c5c2  mov     [rbx+0Ch], eax
0x14002c5c5  test    ebp, ebp
0x14002c5c7  jz      short loc_14002C632
0x14002c5c9  sub     ecx, 1
0x14002c5cc  jz      short loc_14002C629
0x14002c5ce  sub     ecx, 1
0x14002c5d1  jz      short loc_14002C5E1
0x14002c5d3  cmp     ecx, 1
0x14002c5d6  jnz     short loc_14002C63B
0x14002c5d8  mov     ecx, edi; this
0x14002c5da  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x14002c5df  jmp     short loc_14002C639
0x14002c5e1  test    edi, edi
0x14002c5e3  js      short loc_14002C620
0x14002c5e5  mov     rax, [rsp+78h+arg_28]
0x14002c5ed  mov     edi, 8007029Ch
0x14002c5f2  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x14002c5f6  mov     r8, r13; int
0x14002c5f9  mov     [rsp+78h+var_50], rax; __int64
0x14002c5fe  mov     rcx, r10; int
0x14002c601  mov     rax, [rsp+78h+arg_20]
0x14002c609  mov     [rsp+78h+var_58], rax; __int64
0x14002c60e  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110J@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long)
0x14002c613  mov     ecx, edi; this
0x14002c615  mov     [rbx+8], edi
0x14002c618  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14002c61d  mov     [rbx+0Ch], eax
0x14002c620  mov     ecx, edi; this
0x14002c622  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x14002c627  jmp     short loc_14002C639
0x14002c629  mov     ecx, edi; this
0x14002c62b  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x14002c630  jmp     short loc_14002C639
0x14002c632  mov     ecx, edi; this
0x14002c634  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x14002c639  mov     esi, eax
0x14002c63b  xor     edi, edi
0x14002c63d  mov     [rbx], ebp
0x14002c63f  mov     [rbx+4], edi
0x14002c642  cmp     dword ptr [r15+8], 1
0x14002c647  jnz     short loc_14002C650
0x14002c649  mov     dword ptr [rbx+4], 8
0x14002c650  mov     eax, 1
0x14002c655  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)'::`2'::s_failureId
0x14002c65d  inc     eax
0x14002c65f  mov     [rbx+10h], eax
0x14002c662  mov     rax, [rsp+78h+arg_40]
0x14002c66a  test    rax, rax
0x14002c66d  jz      short loc_14002C674
0x14002c66f  cmp     [rax], di
0x14002c672  jnz     short loc_14002C677
0x14002c674  mov     rax, rdi
0x14002c677  mov     [rbx+18h], rax
0x14002c67b  call    cs:__imp_GetCurrentThreadId
0x14002c682  nop     dword ptr [rax+rax+00h]
0x14002c687  mov     [rbx+38h], r13
0x14002c68b  xorps   xmm0, xmm0
0x14002c68e  mov     [rbx+20h], eax
0x14002c691  mov     eax, [rsp+78h+arg_8]
0x14002c698  mov     [rbx+40h], eax
0x14002c69b  mov     rax, [rsp+78h+arg_20]
0x14002c6a3  mov     [rbx+28h], rax
0x14002c6a7  mov     rax, [rsp+78h+arg_28]
0x14002c6af  mov     [rbx+88h], rax
0x14002c6b6  mov     rax, [rsp+78h+arg_0]
0x14002c6be  mov     [rbx+90h], rax
0x14002c6c5  xor     eax, eax
0x14002c6c7  mov     [rbx+44h], esi
0x14002c6ca  mov     [rbx+30h], r12
0x14002c6ce  mov     [rbx+48h], rdi
0x14002c6d2  movups  xmmword ptr [rbx+68h], xmm0
0x14002c6d6  mov     [rbx+78h], rax
0x14002c6da  movups  xmmword ptr [rbx+50h], xmm0
0x14002c6de  mov     [rbx+60h], rax
0x14002c6e2  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14002c6e9  test    rax, rax
0x14002c6ec  jz      short loc_14002C6F5
0x14002c6ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c6f3  jmp     short loc_14002C6F8
0x14002c6f5  mov     rax, rdi
0x14002c6f8  mov     [rbx+80h], rax
0x14002c6ff  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14002c706  test    rax, rax
0x14002c709  jz      short loc_14002C713
0x14002c70b  mov     rcx, rbx
0x14002c70e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c713  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14002c71a  test    rax, rax
0x14002c71d  jz      short loc_14002C735
0x14002c71f  mov     rdx, [rsp+78h+arg_60]
0x14002c727  mov     r8d, 400h
0x14002c72d  mov     rcx, rbx
0x14002c730  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c735  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14002c73c  test    rax, rax
0x14002c73f  jz      short loc_14002C749
0x14002c741  mov     rcx, rbx
0x14002c744  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c749  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14002c750  test    rax, rax
0x14002c753  jz      short loc_14002C763
0x14002c755  test    byte ptr [rbx+4], 2
0x14002c759  jnz     short loc_14002C763
0x14002c75b  mov     rcx, rbx
0x14002c75e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c763  cmp     [rbx+8], edi
0x14002c766  jl      short loc_14002C783
0x14002c768  cmp     ebp, 3
0x14002c76b  jz      short loc_14002C773
0x14002c76d  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14002c773  mov     ecx, 8000FFFFh; this
0x14002c778  mov     [rbx+8], ecx
0x14002c77b  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14002c780  mov     [rbx+0Ch], eax
0x14002c783  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x14002c78a  jnz     short loc_14002C7B1
0x14002c78c  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14002c793  test    rax, rax
0x14002c796  jz      short loc_14002C7A1
0x14002c798  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c79d  test    al, al
0x14002c79f  jmp     short loc_14002C7AF
0x14002c7a1  call    cs:__imp_IsDebuggerPresent
0x14002c7a8  nop     dword ptr [rax+rax+00h]
0x14002c7ad  test    eax, eax
0x14002c7af  jz      short loc_14002C7B7
0x14002c7b1  test    byte ptr [rbx+4], 2
0x14002c7b5  jz      short loc_14002C7DB
0x14002c7b7  mov     rax, cs:g_pfnResultLoggingCallback
0x14002c7be  test    rax, rax
0x14002c7c1  jz      short loc_14002C826
0x14002c7c3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14002c7ca  jnz     short loc_14002C826
0x14002c7cc  xor     r8d, r8d
0x14002c7cf  xor     edx, edx
0x14002c7d1  mov     rcx, rbx
0x14002c7d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c7d9  jmp     short loc_14002C826
0x14002c7db  mov     rax, cs:g_pfnResultLoggingCallback
0x14002c7e2  mov     esi, 800h
0x14002c7e7  test    rax, rax
0x14002c7ea  jz      short loc_14002C803
0x14002c7ec  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14002c7f3  jnz     short loc_14002C803
0x14002c7f5  mov     r8d, esi
0x14002c7f8  mov     rdx, r14
0x14002c7fb  mov     rcx, rbx
0x14002c7fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c803  cmp     [r14], di
0x14002c807  jnz     short loc_14002C817
0x14002c809  mov     r8, rbx; unsigned __int64
0x14002c80c  mov     rdx, rsi; unsigned __int16 *
0x14002c80f  mov     rcx, r14; pszDest
0x14002c812  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14002c817  mov     rcx, r14; lpOutputString
0x14002c81a  call    cs:__imp_OutputDebugStringW
0x14002c821  nop     dword ptr [rax+rax+00h]
0x14002c826  test    byte ptr [rbx+4], 4
0x14002c82a  jnz     short loc_14002C835
0x14002c82c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x14002c833  jz      short loc_14002C846
0x14002c835  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14002c83c  test    rax, rax
0x14002c83f  jz      short loc_14002C846
0x14002c841  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c846  mov     rbx, [rsp+78h+arg_10]
0x14002c84e  add     rsp, 40h
0x14002c852  pop     r15
0x14002c854  pop     r14
0x14002c856  pop     r13
0x14002c858  pop     r12
0x14002c85a  pop     rdi
0x14002c85b  pop     rsi
0x14002c85c  pop     rbp
0x14002c85d  retn
```
