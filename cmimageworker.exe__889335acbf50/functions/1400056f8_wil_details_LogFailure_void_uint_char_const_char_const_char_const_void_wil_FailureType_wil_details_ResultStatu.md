# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1400056f8`
- end: `0x140005a04`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `780`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x14000369c`

## callees

- `0x140003080`
- `0x140004b34`
- `0x1400052b8`
- `0x1400056f8`
- `0x1400069a0`
- `0x1400069c0`
- `0x1400069d4`
- `0x1400069f4`
- `0x140008f64`
- `0x140034010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000581b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000581b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400059b8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400059b8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140005940`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140005940`

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
0x1400056f8  mov     [rsp+arg_10], rbx
0x1400056fd  mov     [rsp+arg_8], edx
0x140005701  mov     [rsp+arg_0], rcx
0x140005706  push    rbp
0x140005707  push    rsi
0x140005708  push    rdi
0x140005709  push    r12
0x14000570b  push    r13
0x14000570d  push    r14
0x14000570f  push    r15
0x140005711  sub     rsp, 40h
0x140005715  mov     r12, r9
0x140005718  mov     r13, r8
0x14000571b  mov     r10, rcx
0x14000571e  xor     eax, eax
0x140005720  mov     rsi, [rsp+78h+lpOutputString]
0x140005728  mov     [rsi], ax
0x14000572b  mov     rax, [rsp+78h+arg_60]
0x140005733  mov     byte ptr [rax], 0
0x140005736  mov     r14, [rsp+78h+arg_38]
0x14000573e  mov     edi, [r14]
0x140005741  mov     rbx, [rsp+78h+arg_78]
0x140005749  mov     [rbx+8], edi
0x14000574c  mov     eax, [r14+4]
0x140005750  mov     [rbx+0Ch], eax
0x140005753  xor     ebp, ebp
0x140005755  mov     r15d, [rsp+78h+arg_30]
0x14000575d  mov     ecx, r15d
0x140005760  test    r15d, r15d
0x140005763  jz      short loc_1400057CB
0x140005765  sub     ecx, 1
0x140005768  jz      short loc_1400057C2
0x14000576a  sub     ecx, 1
0x14000576d  jz      short loc_14000577D
0x14000576f  cmp     ecx, 1
0x140005772  jnz     short loc_1400057D4
0x140005774  mov     ecx, edi; this
0x140005776  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x14000577b  jmp     short loc_1400057D2
0x14000577d  test    edi, edi
0x14000577f  js      short loc_1400057B9
0x140005781  mov     edi, 8007029Ch
0x140005786  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x14000578a  mov     rax, [rsp+78h+arg_28]
0x140005792  mov     [rsp+78h+var_50], rax; __int64
0x140005797  mov     rax, [rsp+78h+arg_20]
0x14000579f  mov     [rsp+78h+var_58], rax; __int64
0x1400057a4  mov     rcx, r10; int
0x1400057a7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1400057ac  mov     [rbx+8], edi
0x1400057af  mov     ecx, edi; this
0x1400057b1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400057b6  mov     [rbx+0Ch], eax
0x1400057b9  mov     ecx, edi; this
0x1400057bb  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1400057c0  jmp     short loc_1400057D2
0x1400057c2  mov     ecx, edi; this
0x1400057c4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1400057c9  jmp     short loc_1400057D2
0x1400057cb  mov     ecx, edi; this
0x1400057cd  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1400057d2  mov     ebp, eax
0x1400057d4  mov     [rbx], r15d
0x1400057d7  mov     eax, [rsp+78h+arg_70]
0x1400057de  mov     [rbx+4], eax
0x1400057e1  cmp     dword ptr [r14+8], 1
0x1400057e6  jnz     short loc_1400057EE
0x1400057e8  or      eax, 8
0x1400057eb  mov     [rbx+4], eax
0x1400057ee  mov     eax, 1
0x1400057f3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400057fb  inc     eax
0x1400057fd  mov     [rbx+10h], eax
0x140005800  mov     rax, [rsp+78h+arg_40]
0x140005808  xor     edi, edi
0x14000580a  test    rax, rax
0x14000580d  jz      short loc_140005814
0x14000580f  cmp     [rax], di
0x140005812  jnz     short loc_140005817
0x140005814  mov     rax, rdi
0x140005817  mov     [rbx+18h], rax
0x14000581b  call    cs:__imp_GetCurrentThreadId
0x140005822  nop     dword ptr [rax+rax+00h]
0x140005827  mov     [rbx+20h], eax
0x14000582a  mov     [rbx+38h], r13
0x14000582e  mov     eax, [rsp+78h+arg_8]
0x140005835  mov     [rbx+40h], eax
0x140005838  mov     [rbx+44h], ebp
0x14000583b  mov     rax, [rsp+78h+arg_20]
0x140005843  mov     [rbx+28h], rax
0x140005847  mov     [rbx+30h], r12
0x14000584b  mov     rax, [rsp+78h+arg_28]
0x140005853  mov     [rbx+88h], rax
0x14000585a  mov     rax, [rsp+78h+arg_0]
0x140005862  mov     [rbx+90h], rax
0x140005869  mov     [rbx+48h], rdi
0x14000586d  xorps   xmm0, xmm0
0x140005870  xor     eax, eax
0x140005872  movups  xmmword ptr [rbx+68h], xmm0
0x140005876  mov     [rbx+78h], rax
0x14000587a  movups  xmmword ptr [rbx+50h], xmm0
0x14000587e  mov     [rbx+60h], rax
0x140005882  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140005889  test    rax, rax
0x14000588c  jz      short loc_140005895
0x14000588e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005893  jmp     short loc_140005898
0x140005895  mov     rax, rdi
0x140005898  mov     [rbx+80h], rax
0x14000589f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400058a6  test    rax, rax
0x1400058a9  jz      short loc_1400058B3
0x1400058ab  mov     rcx, rbx
0x1400058ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400058b3  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400058ba  test    rax, rax
0x1400058bd  jz      short loc_1400058D5
0x1400058bf  mov     r8d, 400h
0x1400058c5  mov     rdx, [rsp+78h+arg_60]
0x1400058cd  mov     rcx, rbx
0x1400058d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400058d5  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400058dc  test    rax, rax
0x1400058df  jz      short loc_1400058E9
0x1400058e1  mov     rcx, rbx
0x1400058e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400058e9  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400058f0  test    rax, rax
0x1400058f3  jz      short loc_140005903
0x1400058f5  test    byte ptr [rbx+4], 2
0x1400058f9  jnz     short loc_140005903
0x1400058fb  mov     rcx, rbx
0x1400058fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005903  cmp     [rbx+8], edi
0x140005906  jl      short loc_140005922
0x140005908  cmp     r15d, 3
0x14000590c  jnz     loc_1400059FE
0x140005912  mov     ecx, 8000FFFFh; this
0x140005917  mov     [rbx+8], ecx
0x14000591a  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000591f  mov     [rbx+0Ch], eax
0x140005922  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x140005929  jnz     short loc_140005950
0x14000592b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140005932  test    rax, rax
0x140005935  jz      short loc_140005940
0x140005937  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000593c  test    al, al
0x14000593e  jmp     short loc_14000594E
0x140005940  call    cs:__imp_IsDebuggerPresent
0x140005947  nop     dword ptr [rax+rax+00h]
0x14000594c  test    eax, eax
0x14000594e  jz      short loc_140005956
0x140005950  test    byte ptr [rbx+4], 2
0x140005954  jz      short loc_14000597A
0x140005956  mov     rax, cs:g_pfnResultLoggingCallback
0x14000595d  test    rax, rax
0x140005960  jz      short loc_1400059C4
0x140005962  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140005969  jnz     short loc_1400059C4
0x14000596b  xor     r8d, r8d
0x14000596e  xor     edx, edx
0x140005970  mov     rcx, rbx
0x140005973  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005978  jmp     short loc_1400059C4
0x14000597a  mov     ebp, 800h
0x14000597f  mov     rax, cs:g_pfnResultLoggingCallback
0x140005986  test    rax, rax
0x140005989  jz      short loc_1400059A2
0x14000598b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140005992  jnz     short loc_1400059A2
0x140005994  mov     r8d, ebp
0x140005997  mov     rdx, rsi
0x14000599a  mov     rcx, rbx
0x14000599d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400059a2  cmp     [rsi], di
0x1400059a5  jnz     short loc_1400059B5
0x1400059a7  mov     r8, rbx; unsigned __int64
0x1400059aa  mov     rdx, rbp; unsigned __int16 *
0x1400059ad  mov     rcx, rsi; this
0x1400059b0  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1400059b5  mov     rcx, rsi; lpOutputString
0x1400059b8  call    cs:__imp_OutputDebugStringW
0x1400059bf  nop     dword ptr [rax+rax+00h]
0x1400059c4  test    byte ptr [rbx+4], 4
0x1400059c8  jnz     short loc_1400059D3
0x1400059ca  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1400059d1  jz      short loc_1400059E5
0x1400059d3  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400059da  test    rax, rax
0x1400059dd  jz      short loc_1400059E5
0x1400059df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400059e4  nop
0x1400059e5  mov     rbx, [rsp+78h+arg_10]
0x1400059ed  add     rsp, 40h
0x1400059f1  pop     r15
0x1400059f3  pop     r14
0x1400059f5  pop     r13
0x1400059f7  pop     r12
0x1400059f9  pop     rdi
0x1400059fa  pop     rsi
0x1400059fb  pop     rbp
0x1400059fc  retn
0x1400059fe  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
