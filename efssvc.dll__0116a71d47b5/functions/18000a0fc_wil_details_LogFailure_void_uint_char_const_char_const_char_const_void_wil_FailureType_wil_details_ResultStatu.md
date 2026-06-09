# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000a0fc`
- end: `0x18000a3f4`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180008cf0`

## callees

- `0x180002b20`
- `0x18000872c`
- `0x1800098cc`
- `0x180009f38`
- `0x18000a0fc`
- `0x18000a5a0`
- `0x18000a5bc`
- `0x18000a5d8`
- `0x18000b204`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000a33e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000a33e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000a3b0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000a3b0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a21f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a21f`

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
0x18000a0fc  mov     [rsp+arg_10], rbx
0x18000a101  mov     [rsp+arg_8], edx
0x18000a105  mov     [rsp+arg_0], rcx
0x18000a10a  push    rbp
0x18000a10b  push    rsi
0x18000a10c  push    rdi
0x18000a10d  push    r12
0x18000a10f  push    r13
0x18000a111  push    r14
0x18000a113  push    r15
0x18000a115  sub     rsp, 40h
0x18000a119  mov     r14, [rsp+78h+arg_38]
0x18000a121  xor     eax, eax
0x18000a123  mov     rbx, [rsp+78h+arg_78]
0x18000a12b  xor     ebp, ebp
0x18000a12d  mov     r15d, [rsp+78h+arg_30]
0x18000a135  mov     r10, rcx
0x18000a138  mov     rsi, [rsp+78h+lpOutputString]
0x18000a140  mov     r12, r9
0x18000a143  mov     r13, r8
0x18000a146  mov     ecx, r15d
0x18000a149  mov     [rsi], ax
0x18000a14c  mov     rax, [rsp+78h+arg_60]
0x18000a154  mov     byte ptr [rax], 0
0x18000a157  mov     edi, [r14]
0x18000a15a  mov     [rbx+8], edi
0x18000a15d  mov     eax, [r14+4]
0x18000a161  mov     [rbx+0Ch], eax
0x18000a164  test    r15d, r15d
0x18000a167  jz      short loc_18000A1CF
0x18000a169  sub     ecx, 1
0x18000a16c  jz      short loc_18000A1C6
0x18000a16e  sub     ecx, 1
0x18000a171  jz      short loc_18000A181
0x18000a173  cmp     ecx, 1
0x18000a176  jnz     short loc_18000A1D8
0x18000a178  mov     ecx, edi; this
0x18000a17a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000a17f  jmp     short loc_18000A1D6
0x18000a181  test    edi, edi
0x18000a183  js      short loc_18000A1BD
0x18000a185  mov     rax, [rsp+78h+arg_28]
0x18000a18d  mov     edi, 8007029Ch
0x18000a192  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000a196  mov     rcx, r10; int
0x18000a199  mov     [rsp+78h+var_50], rax; __int64
0x18000a19e  mov     rax, [rsp+78h+arg_20]
0x18000a1a6  mov     [rsp+78h+var_58], rax; __int64
0x18000a1ab  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000a1b0  mov     ecx, edi; this
0x18000a1b2  mov     [rbx+8], edi
0x18000a1b5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000a1ba  mov     [rbx+0Ch], eax
0x18000a1bd  mov     ecx, edi; this
0x18000a1bf  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000a1c4  jmp     short loc_18000A1D6
0x18000a1c6  mov     ecx, edi; this
0x18000a1c8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000a1cd  jmp     short loc_18000A1D6
0x18000a1cf  mov     ecx, edi; this
0x18000a1d1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000a1d6  mov     ebp, eax
0x18000a1d8  mov     eax, [rsp+78h+arg_70]
0x18000a1df  mov     [rbx+4], eax
0x18000a1e2  mov     [rbx], r15d
0x18000a1e5  cmp     dword ptr [r14+8], 1
0x18000a1ea  jnz     short loc_18000A1F2
0x18000a1ec  or      eax, 8
0x18000a1ef  mov     [rbx+4], eax
0x18000a1f2  mov     eax, 1
0x18000a1f7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000a1ff  inc     eax
0x18000a201  xor     edi, edi
0x18000a203  mov     [rbx+10h], eax
0x18000a206  mov     rax, [rsp+78h+arg_40]
0x18000a20e  test    rax, rax
0x18000a211  jz      short loc_18000A218
0x18000a213  cmp     [rax], di
0x18000a216  jnz     short loc_18000A21B
0x18000a218  mov     rax, rdi
0x18000a21b  mov     [rbx+18h], rax
0x18000a21f  call    cs:__imp_GetCurrentThreadId
0x18000a225  mov     [rbx+38h], r13
0x18000a229  xorps   xmm0, xmm0
0x18000a22c  mov     [rbx+20h], eax
0x18000a22f  mov     eax, [rsp+78h+arg_8]
0x18000a236  mov     [rbx+40h], eax
0x18000a239  mov     rax, [rsp+78h+arg_20]
0x18000a241  mov     [rbx+28h], rax
0x18000a245  mov     rax, [rsp+78h+arg_28]
0x18000a24d  mov     [rbx+88h], rax
0x18000a254  mov     rax, [rsp+78h+arg_0]
0x18000a25c  mov     [rbx+90h], rax
0x18000a263  xor     eax, eax
0x18000a265  mov     [rbx+44h], ebp
0x18000a268  mov     [rbx+30h], r12
0x18000a26c  mov     [rbx+48h], rdi
0x18000a270  movups  xmmword ptr [rbx+68h], xmm0
0x18000a274  mov     [rbx+78h], rax
0x18000a278  movups  xmmword ptr [rbx+50h], xmm0
0x18000a27c  mov     [rbx+60h], rax
0x18000a280  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000a287  test    rax, rax
0x18000a28a  jz      short loc_18000A293
0x18000a28c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a291  jmp     short loc_18000A296
0x18000a293  mov     rax, rdi
0x18000a296  mov     [rbx+80h], rax
0x18000a29d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000a2a4  test    rax, rax
0x18000a2a7  jz      short loc_18000A2B1
0x18000a2a9  mov     rcx, rbx
0x18000a2ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2b1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000a2b8  test    rax, rax
0x18000a2bb  jz      short loc_18000A2D3
0x18000a2bd  mov     rdx, [rsp+78h+arg_60]
0x18000a2c5  mov     r8d, 400h
0x18000a2cb  mov     rcx, rbx
0x18000a2ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2d3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a2da  test    rax, rax
0x18000a2dd  jz      short loc_18000A2E7
0x18000a2df  mov     rcx, rbx
0x18000a2e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2e7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a2ee  test    rax, rax
0x18000a2f1  jz      short loc_18000A301
0x18000a2f3  test    byte ptr [rbx+4], 2
0x18000a2f7  jnz     short loc_18000A301
0x18000a2f9  mov     rcx, rbx
0x18000a2fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a301  cmp     [rbx+8], edi
0x18000a304  jl      short loc_18000A320
0x18000a306  cmp     r15d, 3
0x18000a30a  jnz     loc_18000A3EE
0x18000a310  mov     ecx, 8000FFFFh; this
0x18000a315  mov     [rbx+8], ecx
0x18000a318  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000a31d  mov     [rbx+0Ch], eax
0x18000a320  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000a327  jnz     short loc_18000A348
0x18000a329  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000a330  test    rax, rax
0x18000a333  jz      short loc_18000A33E
0x18000a335  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a33a  test    al, al
0x18000a33c  jmp     short loc_18000A346
0x18000a33e  call    cs:__imp_IsDebuggerPresent
0x18000a344  test    eax, eax
0x18000a346  jz      short loc_18000A34E
0x18000a348  test    byte ptr [rbx+4], 2
0x18000a34c  jz      short loc_18000A372
0x18000a34e  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a355  test    rax, rax
0x18000a358  jz      short loc_18000A3B6
0x18000a35a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000a361  jnz     short loc_18000A3B6
0x18000a363  xor     r8d, r8d
0x18000a366  xor     edx, edx
0x18000a368  mov     rcx, rbx
0x18000a36b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a370  jmp     short loc_18000A3B6
0x18000a372  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a379  mov     ebp, 800h
0x18000a37e  test    rax, rax
0x18000a381  jz      short loc_18000A39A
0x18000a383  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000a38a  jnz     short loc_18000A39A
0x18000a38c  mov     r8d, ebp
0x18000a38f  mov     rdx, rsi
0x18000a392  mov     rcx, rbx
0x18000a395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a39a  cmp     [rsi], di
0x18000a39d  jnz     short loc_18000A3AD
0x18000a39f  mov     r8, rbx; unsigned __int64
0x18000a3a2  mov     rdx, rbp; unsigned __int16 *
0x18000a3a5  mov     rcx, rsi; this
0x18000a3a8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000a3ad  mov     rcx, rsi; lpOutputString
0x18000a3b0  call    cs:__imp_OutputDebugStringW
0x18000a3b6  test    byte ptr [rbx+4], 4
0x18000a3ba  jnz     short loc_18000A3C5
0x18000a3bc  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000a3c3  jz      short loc_18000A3D6
0x18000a3c5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000a3cc  test    rax, rax
0x18000a3cf  jz      short loc_18000A3D6
0x18000a3d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3d6  mov     rbx, [rsp+78h+arg_10]
0x18000a3de  add     rsp, 40h
0x18000a3e2  pop     r15
0x18000a3e4  pop     r14
0x18000a3e6  pop     r13
0x18000a3e8  pop     r12
0x18000a3ea  pop     rdi
0x18000a3eb  pop     rsi
0x18000a3ec  pop     rbp
0x18000a3ed  retn
0x18000a3ee  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
