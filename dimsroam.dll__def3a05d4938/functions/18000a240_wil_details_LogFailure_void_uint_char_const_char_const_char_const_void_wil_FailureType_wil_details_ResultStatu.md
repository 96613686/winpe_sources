# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000a240`
- end: `0x18000a538`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180007ed4`

## callees

- `0x180007910`
- `0x1800098e4`
- `0x18000a07c`
- `0x18000a240`
- `0x18000ac28`
- `0x18000ac50`
- `0x18000ad78`
- `0x18000ad94`
- `0x18000ca3c`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a363`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a363`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000a4f4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000a4f4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000a482`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000a482`

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
  _WORD *v21; // rax
  DWORD CurrentThreadId; // eax
  wil::details::in1diag3 *v23; // rcx
  const struct wil::FailureInfo *v24; // r9
  __int64 ModuleName; // rax
  bool v26; // zf
  wil::details *v27; // [rsp+30h] [rbp-48h]

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
          LODWORD(v27) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v27);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL);
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
  v21 = a9;
  if ( !a9 || !*a9 )
    v21 = 0;
  *(_QWORD *)(a16 + 24) = v21;
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
    ModuleName = wil::details::g_pfnGetModuleName(v23);
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v23);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v26 = !IsDebuggerPresent())
      : (v26 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v23) == 0),
        v26)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v24);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v23);
  }
}

```

## disassembly

```asm
0x18000a240  mov     [rsp+arg_10], rbx
0x18000a245  mov     [rsp+arg_8], edx
0x18000a249  mov     [rsp+arg_0], rcx
0x18000a24e  push    rbp
0x18000a24f  push    rsi
0x18000a250  push    rdi
0x18000a251  push    r12
0x18000a253  push    r13
0x18000a255  push    r14
0x18000a257  push    r15
0x18000a259  sub     rsp, 40h
0x18000a25d  mov     r14, [rsp+78h+arg_38]
0x18000a265  xor     eax, eax
0x18000a267  mov     rbx, [rsp+78h+arg_78]
0x18000a26f  xor     ebp, ebp
0x18000a271  mov     r15d, [rsp+78h+arg_30]
0x18000a279  mov     r10, rcx
0x18000a27c  mov     rsi, [rsp+78h+lpOutputString]
0x18000a284  mov     r12, r9
0x18000a287  mov     r13, r8
0x18000a28a  mov     ecx, r15d
0x18000a28d  mov     [rsi], ax
0x18000a290  mov     rax, [rsp+78h+arg_60]
0x18000a298  mov     byte ptr [rax], 0
0x18000a29b  mov     edi, [r14]
0x18000a29e  mov     [rbx+8], edi
0x18000a2a1  mov     eax, [r14+4]
0x18000a2a5  mov     [rbx+0Ch], eax
0x18000a2a8  test    r15d, r15d
0x18000a2ab  jz      short loc_18000A313
0x18000a2ad  sub     ecx, 1
0x18000a2b0  jz      short loc_18000A30A
0x18000a2b2  sub     ecx, 1
0x18000a2b5  jz      short loc_18000A2C5
0x18000a2b7  cmp     ecx, 1
0x18000a2ba  jnz     short loc_18000A31C
0x18000a2bc  mov     ecx, edi; this
0x18000a2be  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000a2c3  jmp     short loc_18000A31A
0x18000a2c5  test    edi, edi
0x18000a2c7  js      short loc_18000A301
0x18000a2c9  mov     rax, [rsp+78h+arg_28]
0x18000a2d1  mov     edi, 8007029Ch
0x18000a2d6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000a2da  mov     rcx, r10; int
0x18000a2dd  mov     [rsp+78h+var_50], rax; __int64
0x18000a2e2  mov     rax, [rsp+78h+arg_20]
0x18000a2ea  mov     [rsp+78h+var_58], rax; __int64
0x18000a2ef  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000a2f4  mov     ecx, edi; this
0x18000a2f6  mov     [rbx+8], edi
0x18000a2f9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000a2fe  mov     [rbx+0Ch], eax
0x18000a301  mov     ecx, edi; this
0x18000a303  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000a308  jmp     short loc_18000A31A
0x18000a30a  mov     ecx, edi; this
0x18000a30c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000a311  jmp     short loc_18000A31A
0x18000a313  mov     ecx, edi; this
0x18000a315  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000a31a  mov     ebp, eax
0x18000a31c  mov     eax, [rsp+78h+arg_70]
0x18000a323  mov     [rbx+4], eax
0x18000a326  mov     [rbx], r15d
0x18000a329  cmp     dword ptr [r14+8], 1
0x18000a32e  jnz     short loc_18000A336
0x18000a330  or      eax, 8
0x18000a333  mov     [rbx+4], eax
0x18000a336  mov     eax, 1
0x18000a33b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000a343  inc     eax
0x18000a345  xor     edi, edi
0x18000a347  mov     [rbx+10h], eax
0x18000a34a  mov     rax, [rsp+78h+arg_40]
0x18000a352  test    rax, rax
0x18000a355  jz      short loc_18000A35C
0x18000a357  cmp     [rax], di
0x18000a35a  jnz     short loc_18000A35F
0x18000a35c  mov     rax, rdi
0x18000a35f  mov     [rbx+18h], rax
0x18000a363  call    cs:__imp_GetCurrentThreadId
0x18000a369  mov     [rbx+38h], r13
0x18000a36d  xorps   xmm0, xmm0
0x18000a370  mov     [rbx+20h], eax
0x18000a373  mov     eax, [rsp+78h+arg_8]
0x18000a37a  mov     [rbx+40h], eax
0x18000a37d  mov     rax, [rsp+78h+arg_20]
0x18000a385  mov     [rbx+28h], rax
0x18000a389  mov     rax, [rsp+78h+arg_28]
0x18000a391  mov     [rbx+88h], rax
0x18000a398  mov     rax, [rsp+78h+arg_0]
0x18000a3a0  mov     [rbx+90h], rax
0x18000a3a7  xor     eax, eax
0x18000a3a9  mov     [rbx+44h], ebp
0x18000a3ac  mov     [rbx+30h], r12
0x18000a3b0  mov     [rbx+48h], rdi
0x18000a3b4  movups  xmmword ptr [rbx+68h], xmm0
0x18000a3b8  mov     [rbx+78h], rax
0x18000a3bc  movups  xmmword ptr [rbx+50h], xmm0
0x18000a3c0  mov     [rbx+60h], rax
0x18000a3c4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000a3cb  test    rax, rax
0x18000a3ce  jz      short loc_18000A3D7
0x18000a3d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3d5  jmp     short loc_18000A3DA
0x18000a3d7  mov     rax, rdi
0x18000a3da  mov     [rbx+80h], rax
0x18000a3e1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000a3e8  test    rax, rax
0x18000a3eb  jz      short loc_18000A3F5
0x18000a3ed  mov     rcx, rbx
0x18000a3f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3f5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000a3fc  test    rax, rax
0x18000a3ff  jz      short loc_18000A417
0x18000a401  mov     rdx, [rsp+78h+arg_60]
0x18000a409  mov     r8d, 400h
0x18000a40f  mov     rcx, rbx
0x18000a412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a417  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a41e  test    rax, rax
0x18000a421  jz      short loc_18000A42B
0x18000a423  mov     rcx, rbx
0x18000a426  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a42b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a432  test    rax, rax
0x18000a435  jz      short loc_18000A445
0x18000a437  test    byte ptr [rbx+4], 2
0x18000a43b  jnz     short loc_18000A445
0x18000a43d  mov     rcx, rbx
0x18000a440  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a445  cmp     [rbx+8], edi
0x18000a448  jl      short loc_18000A464
0x18000a44a  cmp     r15d, 3
0x18000a44e  jnz     loc_18000A532
0x18000a454  mov     ecx, 8000FFFFh; this
0x18000a459  mov     [rbx+8], ecx
0x18000a45c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000a461  mov     [rbx+0Ch], eax
0x18000a464  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000a46b  jnz     short loc_18000A48C
0x18000a46d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000a474  test    rax, rax
0x18000a477  jz      short loc_18000A482
0x18000a479  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a47e  test    al, al
0x18000a480  jmp     short loc_18000A48A
0x18000a482  call    cs:__imp_IsDebuggerPresent
0x18000a488  test    eax, eax
0x18000a48a  jz      short loc_18000A492
0x18000a48c  test    byte ptr [rbx+4], 2
0x18000a490  jz      short loc_18000A4B6
0x18000a492  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a499  test    rax, rax
0x18000a49c  jz      short loc_18000A4FA
0x18000a49e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000a4a5  jnz     short loc_18000A4FA
0x18000a4a7  xor     r8d, r8d
0x18000a4aa  xor     edx, edx
0x18000a4ac  mov     rcx, rbx
0x18000a4af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4b4  jmp     short loc_18000A4FA
0x18000a4b6  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a4bd  mov     ebp, 800h
0x18000a4c2  test    rax, rax
0x18000a4c5  jz      short loc_18000A4DE
0x18000a4c7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000a4ce  jnz     short loc_18000A4DE
0x18000a4d0  mov     r8d, ebp
0x18000a4d3  mov     rdx, rsi
0x18000a4d6  mov     rcx, rbx
0x18000a4d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4de  cmp     [rsi], di
0x18000a4e1  jnz     short loc_18000A4F1
0x18000a4e3  mov     r8, rbx; unsigned __int64
0x18000a4e6  mov     rdx, rbp; unsigned __int16 *
0x18000a4e9  mov     rcx, rsi; this
0x18000a4ec  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000a4f1  mov     rcx, rsi; lpOutputString
0x18000a4f4  call    cs:__imp_OutputDebugStringW
0x18000a4fa  test    byte ptr [rbx+4], 4
0x18000a4fe  jnz     short loc_18000A509
0x18000a500  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000a507  jz      short loc_18000A51A
0x18000a509  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000a510  test    rax, rax
0x18000a513  jz      short loc_18000A51A
0x18000a515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a51a  mov     rbx, [rsp+78h+arg_10]
0x18000a522  add     rsp, 40h
0x18000a526  pop     r15
0x18000a528  pop     r14
0x18000a52a  pop     r13
0x18000a52c  pop     r12
0x18000a52e  pop     rdi
0x18000a52f  pop     rsi
0x18000a530  pop     rbp
0x18000a531  retn
0x18000a532  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
