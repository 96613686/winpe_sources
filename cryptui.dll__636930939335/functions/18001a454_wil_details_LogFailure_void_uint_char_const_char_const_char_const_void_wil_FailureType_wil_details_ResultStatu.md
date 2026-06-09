# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18001a454`
- end: `0x18001a74d`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180015d48`
- `0x180016094`

## callees

- `0x180015c88`
- `0x180019524`
- `0x18001a160`
- `0x18001a454`
- `0x18001b30c`
- `0x18001b330`
- `0x18001b4b4`
- `0x18001b4d0`
- `0x18001cd80`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a577`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a577`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001a708`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001a708`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001a696`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001a696`

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
      wil::details::g_pfnDebugBreak();
  }
}

```

## disassembly

```asm
0x18001a454  mov     [rsp+arg_10], rbx
0x18001a459  mov     [rsp+arg_8], edx
0x18001a45d  mov     [rsp+arg_0], rcx
0x18001a462  push    rbp
0x18001a463  push    rsi
0x18001a464  push    rdi
0x18001a465  push    r12
0x18001a467  push    r13
0x18001a469  push    r14
0x18001a46b  push    r15
0x18001a46d  sub     rsp, 40h
0x18001a471  mov     r12, r9
0x18001a474  mov     r13, r8
0x18001a477  mov     r10, rcx
0x18001a47a  xor     eax, eax
0x18001a47c  mov     rsi, [rsp+78h+lpOutputString]
0x18001a484  mov     [rsi], ax
0x18001a487  mov     rax, [rsp+78h+arg_60]
0x18001a48f  mov     byte ptr [rax], 0
0x18001a492  mov     r14, [rsp+78h+arg_38]
0x18001a49a  mov     edi, [r14]
0x18001a49d  mov     rbx, [rsp+78h+arg_78]
0x18001a4a5  mov     [rbx+8], edi
0x18001a4a8  mov     eax, [r14+4]
0x18001a4ac  mov     [rbx+0Ch], eax
0x18001a4af  xor     ebp, ebp
0x18001a4b1  mov     r15d, [rsp+78h+arg_30]
0x18001a4b9  mov     ecx, r15d
0x18001a4bc  test    r15d, r15d
0x18001a4bf  jz      short loc_18001A527
0x18001a4c1  sub     ecx, 1
0x18001a4c4  jz      short loc_18001A51E
0x18001a4c6  sub     ecx, 1
0x18001a4c9  jz      short loc_18001A4D9
0x18001a4cb  cmp     ecx, 1
0x18001a4ce  jnz     short loc_18001A530
0x18001a4d0  mov     ecx, edi; this
0x18001a4d2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18001a4d7  jmp     short loc_18001A52E
0x18001a4d9  test    edi, edi
0x18001a4db  js      short loc_18001A515
0x18001a4dd  mov     edi, 8007029Ch
0x18001a4e2  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18001a4e6  mov     rax, [rsp+78h+arg_28]
0x18001a4ee  mov     [rsp+78h+var_50], rax; __int64
0x18001a4f3  mov     rax, [rsp+78h+arg_20]
0x18001a4fb  mov     [rsp+78h+var_58], rax; __int64
0x18001a500  mov     rcx, r10; int
0x18001a503  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18001a508  mov     [rbx+8], edi
0x18001a50b  mov     ecx, edi; this
0x18001a50d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001a512  mov     [rbx+0Ch], eax
0x18001a515  mov     ecx, edi; this
0x18001a517  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18001a51c  jmp     short loc_18001A52E
0x18001a51e  mov     ecx, edi; this
0x18001a520  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18001a525  jmp     short loc_18001A52E
0x18001a527  mov     ecx, edi; this
0x18001a529  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18001a52e  mov     ebp, eax
0x18001a530  mov     [rbx], r15d
0x18001a533  mov     eax, [rsp+78h+arg_70]
0x18001a53a  mov     [rbx+4], eax
0x18001a53d  cmp     dword ptr [r14+8], 1
0x18001a542  jnz     short loc_18001A54A
0x18001a544  or      eax, 8
0x18001a547  mov     [rbx+4], eax
0x18001a54a  mov     eax, 1
0x18001a54f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18001a557  inc     eax
0x18001a559  mov     [rbx+10h], eax
0x18001a55c  mov     rax, [rsp+78h+arg_40]
0x18001a564  xor     edi, edi
0x18001a566  test    rax, rax
0x18001a569  jz      short loc_18001A570
0x18001a56b  cmp     [rax], di
0x18001a56e  jnz     short loc_18001A573
0x18001a570  mov     rax, rdi
0x18001a573  mov     [rbx+18h], rax
0x18001a577  call    cs:__imp_GetCurrentThreadId
0x18001a57d  mov     [rbx+20h], eax
0x18001a580  mov     [rbx+38h], r13
0x18001a584  mov     eax, [rsp+78h+arg_8]
0x18001a58b  mov     [rbx+40h], eax
0x18001a58e  mov     [rbx+44h], ebp
0x18001a591  mov     rax, [rsp+78h+arg_20]
0x18001a599  mov     [rbx+28h], rax
0x18001a59d  mov     [rbx+30h], r12
0x18001a5a1  mov     rax, [rsp+78h+arg_28]
0x18001a5a9  mov     [rbx+88h], rax
0x18001a5b0  mov     rax, [rsp+78h+arg_0]
0x18001a5b8  mov     [rbx+90h], rax
0x18001a5bf  mov     [rbx+48h], rdi
0x18001a5c3  xorps   xmm0, xmm0
0x18001a5c6  xor     eax, eax
0x18001a5c8  movups  xmmword ptr [rbx+68h], xmm0
0x18001a5cc  mov     [rbx+78h], rax
0x18001a5d0  movups  xmmword ptr [rbx+50h], xmm0
0x18001a5d4  mov     [rbx+60h], rax
0x18001a5d8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001a5df  test    rax, rax
0x18001a5e2  jz      short loc_18001A5EB
0x18001a5e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a5e9  jmp     short loc_18001A5EE
0x18001a5eb  mov     rax, rdi
0x18001a5ee  mov     [rbx+80h], rax
0x18001a5f5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18001a5fc  test    rax, rax
0x18001a5ff  jz      short loc_18001A609
0x18001a601  mov     rcx, rbx
0x18001a604  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a609  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001a610  test    rax, rax
0x18001a613  jz      short loc_18001A62B
0x18001a615  mov     r8d, 400h
0x18001a61b  mov     rdx, [rsp+78h+arg_60]
0x18001a623  mov     rcx, rbx
0x18001a626  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a62b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001a632  test    rax, rax
0x18001a635  jz      short loc_18001A63F
0x18001a637  mov     rcx, rbx
0x18001a63a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a63f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001a646  test    rax, rax
0x18001a649  jz      short loc_18001A659
0x18001a64b  test    byte ptr [rbx+4], 2
0x18001a64f  jnz     short loc_18001A659
0x18001a651  mov     rcx, rbx
0x18001a654  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a659  cmp     [rbx+8], edi
0x18001a65c  jl      short loc_18001A678
0x18001a65e  cmp     r15d, 3
0x18001a662  jnz     loc_18001A747
0x18001a668  mov     ecx, 8000FFFFh; this
0x18001a66d  mov     [rbx+8], ecx
0x18001a670  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001a675  mov     [rbx+0Ch], eax
0x18001a678  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18001a67f  jnz     short loc_18001A6A0
0x18001a681  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001a688  test    rax, rax
0x18001a68b  jz      short loc_18001A696
0x18001a68d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a692  test    al, al
0x18001a694  jmp     short loc_18001A69E
0x18001a696  call    cs:__imp_IsDebuggerPresent
0x18001a69c  test    eax, eax
0x18001a69e  jz      short loc_18001A6A6
0x18001a6a0  test    byte ptr [rbx+4], 2
0x18001a6a4  jz      short loc_18001A6CA
0x18001a6a6  mov     rax, cs:g_pfnResultLoggingCallback
0x18001a6ad  test    rax, rax
0x18001a6b0  jz      short loc_18001A70E
0x18001a6b2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001a6b9  jnz     short loc_18001A70E
0x18001a6bb  xor     r8d, r8d
0x18001a6be  xor     edx, edx
0x18001a6c0  mov     rcx, rbx
0x18001a6c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a6c8  jmp     short loc_18001A70E
0x18001a6ca  mov     ebp, 800h
0x18001a6cf  mov     rax, cs:g_pfnResultLoggingCallback
0x18001a6d6  test    rax, rax
0x18001a6d9  jz      short loc_18001A6F2
0x18001a6db  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001a6e2  jnz     short loc_18001A6F2
0x18001a6e4  mov     r8d, ebp
0x18001a6e7  mov     rdx, rsi
0x18001a6ea  mov     rcx, rbx
0x18001a6ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a6f2  cmp     [rsi], di
0x18001a6f5  jnz     short loc_18001A705
0x18001a6f7  mov     r8, rbx; unsigned __int64
0x18001a6fa  mov     rdx, rbp; unsigned __int16 *
0x18001a6fd  mov     rcx, rsi; this
0x18001a700  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18001a705  mov     rcx, rsi; lpOutputString
0x18001a708  call    cs:__imp_OutputDebugStringW
0x18001a70e  test    byte ptr [rbx+4], 4
0x18001a712  jnz     short loc_18001A71D
0x18001a714  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18001a71b  jz      short loc_18001A72F
0x18001a71d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001a724  test    rax, rax
0x18001a727  jz      short loc_18001A72F
0x18001a729  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a72e  nop
0x18001a72f  mov     rbx, [rsp+78h+arg_10]
0x18001a737  add     rsp, 40h
0x18001a73b  pop     r15
0x18001a73d  pop     r14
0x18001a73f  pop     r13
0x18001a741  pop     r12
0x18001a743  pop     rdi
0x18001a744  pop     rsi
0x18001a745  pop     rbp
0x18001a746  retn
0x18001a747  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
