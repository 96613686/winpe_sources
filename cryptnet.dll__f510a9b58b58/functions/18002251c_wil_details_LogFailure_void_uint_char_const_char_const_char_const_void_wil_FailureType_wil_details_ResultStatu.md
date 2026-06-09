# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18002251c`
- end: `0x180022814`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1800206e4`
- `0x180020a30`

## callees

- `0x180020624`
- `0x1800219f4`
- `0x180022220`
- `0x18002251c`
- `0x180022f18`
- `0x180022f40`
- `0x180023090`
- `0x1800230ac`
- `0x1800242a8`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002263f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002263f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800227d0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800227d0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002275e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002275e`

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
0x18002251c  mov     [rsp+arg_10], rbx
0x180022521  mov     [rsp+arg_8], edx
0x180022525  mov     [rsp+arg_0], rcx
0x18002252a  push    rbp
0x18002252b  push    rsi
0x18002252c  push    rdi
0x18002252d  push    r12
0x18002252f  push    r13
0x180022531  push    r14
0x180022533  push    r15
0x180022535  sub     rsp, 40h
0x180022539  mov     r14, [rsp+78h+arg_38]
0x180022541  xor     eax, eax
0x180022543  mov     rbx, [rsp+78h+arg_78]
0x18002254b  xor     ebp, ebp
0x18002254d  mov     r15d, [rsp+78h+arg_30]
0x180022555  mov     r10, rcx
0x180022558  mov     rsi, [rsp+78h+lpOutputString]
0x180022560  mov     r12, r9
0x180022563  mov     r13, r8
0x180022566  mov     ecx, r15d
0x180022569  mov     [rsi], ax
0x18002256c  mov     rax, [rsp+78h+arg_60]
0x180022574  mov     byte ptr [rax], 0
0x180022577  mov     edi, [r14]
0x18002257a  mov     [rbx+8], edi
0x18002257d  mov     eax, [r14+4]
0x180022581  mov     [rbx+0Ch], eax
0x180022584  test    r15d, r15d
0x180022587  jz      short loc_1800225EF
0x180022589  sub     ecx, 1
0x18002258c  jz      short loc_1800225E6
0x18002258e  sub     ecx, 1
0x180022591  jz      short loc_1800225A1
0x180022593  cmp     ecx, 1
0x180022596  jnz     short loc_1800225F8
0x180022598  mov     ecx, edi; this
0x18002259a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18002259f  jmp     short loc_1800225F6
0x1800225a1  test    edi, edi
0x1800225a3  js      short loc_1800225DD
0x1800225a5  mov     rax, [rsp+78h+arg_28]
0x1800225ad  mov     edi, 8007029Ch
0x1800225b2  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800225b6  mov     rcx, r10; int
0x1800225b9  mov     [rsp+78h+var_50], rax; __int64
0x1800225be  mov     rax, [rsp+78h+arg_20]
0x1800225c6  mov     [rsp+78h+var_58], rax; __int64
0x1800225cb  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800225d0  mov     ecx, edi; this
0x1800225d2  mov     [rbx+8], edi
0x1800225d5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800225da  mov     [rbx+0Ch], eax
0x1800225dd  mov     ecx, edi; this
0x1800225df  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800225e4  jmp     short loc_1800225F6
0x1800225e6  mov     ecx, edi; this
0x1800225e8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800225ed  jmp     short loc_1800225F6
0x1800225ef  mov     ecx, edi; this
0x1800225f1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800225f6  mov     ebp, eax
0x1800225f8  mov     eax, [rsp+78h+arg_70]
0x1800225ff  mov     [rbx+4], eax
0x180022602  mov     [rbx], r15d
0x180022605  cmp     dword ptr [r14+8], 1
0x18002260a  jnz     short loc_180022612
0x18002260c  or      eax, 8
0x18002260f  mov     [rbx+4], eax
0x180022612  mov     eax, 1
0x180022617  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18002261f  inc     eax
0x180022621  xor     edi, edi
0x180022623  mov     [rbx+10h], eax
0x180022626  mov     rax, [rsp+78h+arg_40]
0x18002262e  test    rax, rax
0x180022631  jz      short loc_180022638
0x180022633  cmp     [rax], di
0x180022636  jnz     short loc_18002263B
0x180022638  mov     rax, rdi
0x18002263b  mov     [rbx+18h], rax
0x18002263f  call    cs:__imp_GetCurrentThreadId
0x180022645  mov     [rbx+38h], r13
0x180022649  xorps   xmm0, xmm0
0x18002264c  mov     [rbx+20h], eax
0x18002264f  mov     eax, [rsp+78h+arg_8]
0x180022656  mov     [rbx+40h], eax
0x180022659  mov     rax, [rsp+78h+arg_20]
0x180022661  mov     [rbx+28h], rax
0x180022665  mov     rax, [rsp+78h+arg_28]
0x18002266d  mov     [rbx+88h], rax
0x180022674  mov     rax, [rsp+78h+arg_0]
0x18002267c  mov     [rbx+90h], rax
0x180022683  xor     eax, eax
0x180022685  mov     [rbx+44h], ebp
0x180022688  mov     [rbx+30h], r12
0x18002268c  mov     [rbx+48h], rdi
0x180022690  movups  xmmword ptr [rbx+68h], xmm0
0x180022694  mov     [rbx+78h], rax
0x180022698  movups  xmmword ptr [rbx+50h], xmm0
0x18002269c  mov     [rbx+60h], rax
0x1800226a0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800226a7  test    rax, rax
0x1800226aa  jz      short loc_1800226B3
0x1800226ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800226b1  jmp     short loc_1800226B6
0x1800226b3  mov     rax, rdi
0x1800226b6  mov     [rbx+80h], rax
0x1800226bd  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800226c4  test    rax, rax
0x1800226c7  jz      short loc_1800226D1
0x1800226c9  mov     rcx, rbx
0x1800226cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800226d1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800226d8  test    rax, rax
0x1800226db  jz      short loc_1800226F3
0x1800226dd  mov     rdx, [rsp+78h+arg_60]
0x1800226e5  mov     r8d, 400h
0x1800226eb  mov     rcx, rbx
0x1800226ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800226f3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800226fa  test    rax, rax
0x1800226fd  jz      short loc_180022707
0x1800226ff  mov     rcx, rbx
0x180022702  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022707  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002270e  test    rax, rax
0x180022711  jz      short loc_180022721
0x180022713  test    byte ptr [rbx+4], 2
0x180022717  jnz     short loc_180022721
0x180022719  mov     rcx, rbx
0x18002271c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022721  cmp     [rbx+8], edi
0x180022724  jl      short loc_180022740
0x180022726  cmp     r15d, 3
0x18002272a  jnz     loc_18002280E
0x180022730  mov     ecx, 8000FFFFh; this
0x180022735  mov     [rbx+8], ecx
0x180022738  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18002273d  mov     [rbx+0Ch], eax
0x180022740  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180022747  jnz     short loc_180022768
0x180022749  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180022750  test    rax, rax
0x180022753  jz      short loc_18002275E
0x180022755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002275a  test    al, al
0x18002275c  jmp     short loc_180022766
0x18002275e  call    cs:__imp_IsDebuggerPresent
0x180022764  test    eax, eax
0x180022766  jz      short loc_18002276E
0x180022768  test    byte ptr [rbx+4], 2
0x18002276c  jz      short loc_180022792
0x18002276e  mov     rax, cs:g_pfnResultLoggingCallback
0x180022775  test    rax, rax
0x180022778  jz      short loc_1800227D6
0x18002277a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180022781  jnz     short loc_1800227D6
0x180022783  xor     r8d, r8d
0x180022786  xor     edx, edx
0x180022788  mov     rcx, rbx
0x18002278b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022790  jmp     short loc_1800227D6
0x180022792  mov     rax, cs:g_pfnResultLoggingCallback
0x180022799  mov     ebp, 800h
0x18002279e  test    rax, rax
0x1800227a1  jz      short loc_1800227BA
0x1800227a3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800227aa  jnz     short loc_1800227BA
0x1800227ac  mov     r8d, ebp
0x1800227af  mov     rdx, rsi
0x1800227b2  mov     rcx, rbx
0x1800227b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800227ba  cmp     [rsi], di
0x1800227bd  jnz     short loc_1800227CD
0x1800227bf  mov     r8, rbx; unsigned __int64
0x1800227c2  mov     rdx, rbp; unsigned __int16 *
0x1800227c5  mov     rcx, rsi; this
0x1800227c8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800227cd  mov     rcx, rsi; lpOutputString
0x1800227d0  call    cs:__imp_OutputDebugStringW
0x1800227d6  test    byte ptr [rbx+4], 4
0x1800227da  jnz     short loc_1800227E5
0x1800227dc  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800227e3  jz      short loc_1800227F6
0x1800227e5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800227ec  test    rax, rax
0x1800227ef  jz      short loc_1800227F6
0x1800227f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800227f6  mov     rbx, [rsp+78h+arg_10]
0x1800227fe  add     rsp, 40h
0x180022802  pop     r15
0x180022804  pop     r14
0x180022806  pop     r13
0x180022808  pop     r12
0x18002280a  pop     rdi
0x18002280b  pop     rsi
0x18002280c  pop     rbp
0x18002280d  retn
0x18002280e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
