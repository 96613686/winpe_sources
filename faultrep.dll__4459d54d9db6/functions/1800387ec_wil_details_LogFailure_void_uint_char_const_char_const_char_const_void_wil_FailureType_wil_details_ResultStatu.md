# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800387ec`
- end: `0x180038a00`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `532`
- prototype: `void __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, unsigned int *, __int64, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180037fd8`

## callees

- `0x18000e2f0`
- `0x18000e5f8`
- `0x180038330`
- `0x1800387ec`
- `0x18004b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003885f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003885f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800389c7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800389c7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180038959`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180038959`

## pseudocode

```c
void __fastcall wil::details::LogFailure(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        unsigned int *a8,
        __int64 a9,
        __int64 a10,
        wil *lpOutputString,
        __int64 a12,
        _BYTE *a13,
        __int64 a14,
        __int64 a15,
        unsigned __int64 a16)
{
  wil::details *v17; // rcx
  int v18; // r14d
  __int64 v19; // rdx
  signed __int32 v20; // ecx
  DWORD CurrentThreadId; // eax
  unsigned __int16 *v22; // rdx
  wil::details::in1diag3 *v23; // rcx
  const struct wil::FailureInfo *v24; // r9
  __int64 ModuleName; // rax
  bool v26; // zf

  *(_WORD *)lpOutputString = 0;
  *a13 = 0;
  v17 = (wil::details *)*a8;
  *(_DWORD *)(a16 + 8) = (_DWORD)v17;
  *(_DWORD *)(a16 + 12) = a8[1];
  v18 = wil::details::RecordReturn(v17, (int)a8);
  *(_QWORD *)a16 = 1;
  if ( *(_DWORD *)(v19 + 8) == 1 )
    *(_DWORD *)(a16 + 4) = 8;
  v20 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  *(_QWORD *)(a16 + 24) = 0;
  *(_DWORD *)(a16 + 16) = v20;
  CurrentThreadId = GetCurrentThreadId();
  *(_DWORD *)(a16 + 64) = 172;
  *(_DWORD *)(a16 + 32) = CurrentThreadId;
  *(_QWORD *)(a16 + 56) = "onecore\\shell\\lib\\calleridentity\\calleridentity.cpp";
  *(_QWORD *)(a16 + 136) = a6;
  *(_DWORD *)(a16 + 68) = v18;
  *(_QWORD *)(a16 + 40) = 0;
  *(_QWORD *)(a16 + 48) = 0;
  *(_QWORD *)(a16 + 144) = a1;
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
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v23);
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
      wil::GetFailureLogString(lpOutputString, v22, a16, v24);
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
0x1800387ec  push    rbx
0x1800387ee  push    rbp
0x1800387ef  push    rsi
0x1800387f0  push    rdi
0x1800387f1  push    r14
0x1800387f3  push    r15
0x1800387f5  sub     rsp, 28h
0x1800387f9  mov     rdx, [rsp+58h+arg_38]; int
0x180038801  xor     r15d, r15d
0x180038804  mov     rbx, [rsp+58h+arg_78]
0x18003880c  mov     rbp, rcx
0x18003880f  mov     rdi, [rsp+58h+lpOutputString]
0x180038817  mov     rsi, [rsp+58h+arg_60]
0x18003881f  mov     [rdi], r15w
0x180038823  mov     [rsi], r15b
0x180038826  mov     ecx, [rdx]; this
0x180038828  mov     [rbx+8], ecx
0x18003882b  mov     eax, [rdx+4]
0x18003882e  mov     [rbx+0Ch], eax
0x180038831  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180038836  mov     r14d, eax
0x180038839  lea     eax, [r15+1]
0x18003883d  mov     [rbx], rax
0x180038840  cmp     [rdx+8], eax
0x180038843  jnz     short loc_18003884C
0x180038845  mov     dword ptr [rbx+4], 8
0x18003884c  mov     ecx, eax
0x18003884e  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180038856  add     ecx, eax
0x180038858  mov     [rbx+18h], r15
0x18003885c  mov     [rbx+10h], ecx
0x18003885f  call    cs:__imp_GetCurrentThreadId
0x180038865  mov     dword ptr [rbx+40h], 0ACh
0x18003886c  xorps   xmm0, xmm0
0x18003886f  mov     [rbx+20h], eax
0x180038872  lea     rax, aOnecoreShellLi; "onecore\\shell\\lib\\calleridentity\\ca"...
0x180038879  mov     [rbx+38h], rax
0x18003887d  mov     rax, [rsp+58h+arg_28]
0x180038885  mov     [rbx+88h], rax
0x18003888c  xor     eax, eax
0x18003888e  mov     [rbx+44h], r14d
0x180038892  mov     [rbx+28h], r15
0x180038896  mov     [rbx+30h], r15
0x18003889a  mov     [rbx+90h], rbp
0x1800388a1  mov     [rbx+48h], r15
0x1800388a5  movups  xmmword ptr [rbx+68h], xmm0
0x1800388a9  mov     [rbx+78h], rax
0x1800388ad  movups  xmmword ptr [rbx+50h], xmm0
0x1800388b1  mov     [rbx+60h], rax
0x1800388b5  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800388bc  test    rax, rax
0x1800388bf  jz      short loc_1800388C8
0x1800388c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800388c6  jmp     short loc_1800388CB
0x1800388c8  mov     rax, r15
0x1800388cb  mov     [rbx+80h], rax
0x1800388d2  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800388d9  test    rax, rax
0x1800388dc  jz      short loc_1800388E6
0x1800388de  mov     rcx, rbx
0x1800388e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800388e6  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800388ed  test    rax, rax
0x1800388f0  jz      short loc_180038903
0x1800388f2  mov     r8d, 400h
0x1800388f8  mov     rdx, rsi
0x1800388fb  mov     rcx, rbx
0x1800388fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038903  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18003890a  test    rax, rax
0x18003890d  jz      short loc_180038917
0x18003890f  mov     rcx, rbx
0x180038912  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038917  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18003891e  test    rax, rax
0x180038921  jz      short loc_180038931
0x180038923  test    byte ptr [rbx+4], 2
0x180038927  jnz     short loc_180038931
0x180038929  mov     rcx, rbx
0x18003892c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038931  cmp     [rbx+8], r15d
0x180038935  jge     loc_1800389FA
0x18003893b  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180038942  jnz     short loc_180038963
0x180038944  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18003894b  test    rax, rax
0x18003894e  jz      short loc_180038959
0x180038950  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038955  test    al, al
0x180038957  jmp     short loc_180038961
0x180038959  call    cs:__imp_IsDebuggerPresent
0x18003895f  test    eax, eax
0x180038961  jz      short loc_180038969
0x180038963  test    byte ptr [rbx+4], 2
0x180038967  jz      short loc_18003898D
0x180038969  mov     rax, cs:g_pfnResultLoggingCallback
0x180038970  test    rax, rax
0x180038973  jz      short loc_1800389CD
0x180038975  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18003897c  jnz     short loc_1800389CD
0x18003897e  xor     r8d, r8d
0x180038981  xor     edx, edx
0x180038983  mov     rcx, rbx
0x180038986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003898b  jmp     short loc_1800389CD
0x18003898d  mov     rax, cs:g_pfnResultLoggingCallback
0x180038994  test    rax, rax
0x180038997  jz      short loc_1800389B3
0x180038999  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800389a0  jnz     short loc_1800389B3
0x1800389a2  mov     r8d, 800h
0x1800389a8  mov     rdx, rdi
0x1800389ab  mov     rcx, rbx
0x1800389ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800389b3  cmp     [rdi], r15w
0x1800389b7  jnz     short loc_1800389C4
0x1800389b9  mov     r8, rbx; unsigned __int64
0x1800389bc  mov     rcx, rdi; this
0x1800389bf  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800389c4  mov     rcx, rdi; lpOutputString
0x1800389c7  call    cs:__imp_OutputDebugStringW
0x1800389cd  test    byte ptr [rbx+4], 4
0x1800389d1  jnz     short loc_1800389DC
0x1800389d3  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x1800389da  jz      short loc_1800389ED
0x1800389dc  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800389e3  test    rax, rax
0x1800389e6  jz      short loc_1800389ED
0x1800389e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800389ed  add     rsp, 28h
0x1800389f1  pop     r15
0x1800389f3  pop     r14
0x1800389f5  pop     rdi
0x1800389f6  pop     rsi
0x1800389f7  pop     rbp
0x1800389f8  pop     rbx
0x1800389f9  retn
0x1800389fa  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
