# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180003720`
- end: `0x180003a18`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18000225c`

## callees

- `0x180001c98`
- `0x180002dc4`
- `0x18000355c`
- `0x180003720`
- `0x180003c5c`
- `0x180003c80`
- `0x180003c94`
- `0x180003cb0`
- `0x18000468c`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003843`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003843`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800039d4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800039d4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003962`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003962`

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
0x180003720  mov     [rsp+arg_10], rbx
0x180003725  mov     [rsp+arg_8], edx
0x180003729  mov     [rsp+arg_0], rcx
0x18000372e  push    rbp
0x18000372f  push    rsi
0x180003730  push    rdi
0x180003731  push    r12
0x180003733  push    r13
0x180003735  push    r14
0x180003737  push    r15
0x180003739  sub     rsp, 40h
0x18000373d  mov     r14, [rsp+78h+arg_38]
0x180003745  xor     eax, eax
0x180003747  mov     rbx, [rsp+78h+arg_78]
0x18000374f  xor     ebp, ebp
0x180003751  mov     r15d, [rsp+78h+arg_30]
0x180003759  mov     r10, rcx
0x18000375c  mov     rsi, [rsp+78h+lpOutputString]
0x180003764  mov     r12, r9
0x180003767  mov     r13, r8
0x18000376a  mov     ecx, r15d
0x18000376d  mov     [rsi], ax
0x180003770  mov     rax, [rsp+78h+arg_60]
0x180003778  mov     byte ptr [rax], 0
0x18000377b  mov     edi, [r14]
0x18000377e  mov     [rbx+8], edi
0x180003781  mov     eax, [r14+4]
0x180003785  mov     [rbx+0Ch], eax
0x180003788  test    r15d, r15d
0x18000378b  jz      short loc_1800037F3
0x18000378d  sub     ecx, 1
0x180003790  jz      short loc_1800037EA
0x180003792  sub     ecx, 1
0x180003795  jz      short loc_1800037A5
0x180003797  cmp     ecx, 1
0x18000379a  jnz     short loc_1800037FC
0x18000379c  mov     ecx, edi; this
0x18000379e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800037a3  jmp     short loc_1800037FA
0x1800037a5  test    edi, edi
0x1800037a7  js      short loc_1800037E1
0x1800037a9  mov     rax, [rsp+78h+arg_28]
0x1800037b1  mov     edi, 8007029Ch
0x1800037b6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800037ba  mov     rcx, r10; int
0x1800037bd  mov     [rsp+78h+var_50], rax; __int64
0x1800037c2  mov     rax, [rsp+78h+arg_20]
0x1800037ca  mov     [rsp+78h+var_58], rax; __int64
0x1800037cf  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800037d4  mov     ecx, edi; this
0x1800037d6  mov     [rbx+8], edi
0x1800037d9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800037de  mov     [rbx+0Ch], eax
0x1800037e1  mov     ecx, edi; this
0x1800037e3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800037e8  jmp     short loc_1800037FA
0x1800037ea  mov     ecx, edi; this
0x1800037ec  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800037f1  jmp     short loc_1800037FA
0x1800037f3  mov     ecx, edi; this
0x1800037f5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800037fa  mov     ebp, eax
0x1800037fc  mov     eax, [rsp+78h+arg_70]
0x180003803  mov     [rbx+4], eax
0x180003806  mov     [rbx], r15d
0x180003809  cmp     dword ptr [r14+8], 1
0x18000380e  jnz     short loc_180003816
0x180003810  or      eax, 8
0x180003813  mov     [rbx+4], eax
0x180003816  mov     eax, 1
0x18000381b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003823  inc     eax
0x180003825  xor     edi, edi
0x180003827  mov     [rbx+10h], eax
0x18000382a  mov     rax, [rsp+78h+arg_40]
0x180003832  test    rax, rax
0x180003835  jz      short loc_18000383C
0x180003837  cmp     [rax], di
0x18000383a  jnz     short loc_18000383F
0x18000383c  mov     rax, rdi
0x18000383f  mov     [rbx+18h], rax
0x180003843  call    cs:__imp_GetCurrentThreadId
0x180003849  mov     [rbx+38h], r13
0x18000384d  xorps   xmm0, xmm0
0x180003850  mov     [rbx+20h], eax
0x180003853  mov     eax, [rsp+78h+arg_8]
0x18000385a  mov     [rbx+40h], eax
0x18000385d  mov     rax, [rsp+78h+arg_20]
0x180003865  mov     [rbx+28h], rax
0x180003869  mov     rax, [rsp+78h+arg_28]
0x180003871  mov     [rbx+88h], rax
0x180003878  mov     rax, [rsp+78h+arg_0]
0x180003880  mov     [rbx+90h], rax
0x180003887  xor     eax, eax
0x180003889  mov     [rbx+44h], ebp
0x18000388c  mov     [rbx+30h], r12
0x180003890  mov     [rbx+48h], rdi
0x180003894  movups  xmmword ptr [rbx+68h], xmm0
0x180003898  mov     [rbx+78h], rax
0x18000389c  movups  xmmword ptr [rbx+50h], xmm0
0x1800038a0  mov     [rbx+60h], rax
0x1800038a4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800038ab  test    rax, rax
0x1800038ae  jz      short loc_1800038B7
0x1800038b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038b5  jmp     short loc_1800038BA
0x1800038b7  mov     rax, rdi
0x1800038ba  mov     [rbx+80h], rax
0x1800038c1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800038c8  test    rax, rax
0x1800038cb  jz      short loc_1800038D5
0x1800038cd  mov     rcx, rbx
0x1800038d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038d5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800038dc  test    rax, rax
0x1800038df  jz      short loc_1800038F7
0x1800038e1  mov     rdx, [rsp+78h+arg_60]
0x1800038e9  mov     r8d, 400h
0x1800038ef  mov     rcx, rbx
0x1800038f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038f7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800038fe  test    rax, rax
0x180003901  jz      short loc_18000390B
0x180003903  mov     rcx, rbx
0x180003906  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000390b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003912  test    rax, rax
0x180003915  jz      short loc_180003925
0x180003917  test    byte ptr [rbx+4], 2
0x18000391b  jnz     short loc_180003925
0x18000391d  mov     rcx, rbx
0x180003920  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003925  cmp     [rbx+8], edi
0x180003928  jl      short loc_180003944
0x18000392a  cmp     r15d, 3
0x18000392e  jnz     loc_180003A12
0x180003934  mov     ecx, 8000FFFFh; this
0x180003939  mov     [rbx+8], ecx
0x18000393c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180003941  mov     [rbx+0Ch], eax
0x180003944  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000394b  jnz     short loc_18000396C
0x18000394d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003954  test    rax, rax
0x180003957  jz      short loc_180003962
0x180003959  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000395e  test    al, al
0x180003960  jmp     short loc_18000396A
0x180003962  call    cs:__imp_IsDebuggerPresent
0x180003968  test    eax, eax
0x18000396a  jz      short loc_180003972
0x18000396c  test    byte ptr [rbx+4], 2
0x180003970  jz      short loc_180003996
0x180003972  mov     rax, cs:g_pfnResultLoggingCallback
0x180003979  test    rax, rax
0x18000397c  jz      short loc_1800039DA
0x18000397e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180003985  jnz     short loc_1800039DA
0x180003987  xor     r8d, r8d
0x18000398a  xor     edx, edx
0x18000398c  mov     rcx, rbx
0x18000398f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003994  jmp     short loc_1800039DA
0x180003996  mov     rax, cs:g_pfnResultLoggingCallback
0x18000399d  mov     ebp, 800h
0x1800039a2  test    rax, rax
0x1800039a5  jz      short loc_1800039BE
0x1800039a7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800039ae  jnz     short loc_1800039BE
0x1800039b0  mov     r8d, ebp
0x1800039b3  mov     rdx, rsi
0x1800039b6  mov     rcx, rbx
0x1800039b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039be  cmp     [rsi], di
0x1800039c1  jnz     short loc_1800039D1
0x1800039c3  mov     r8, rbx; unsigned __int64
0x1800039c6  mov     rdx, rbp; unsigned __int16 *
0x1800039c9  mov     rcx, rsi; this
0x1800039cc  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800039d1  mov     rcx, rsi; lpOutputString
0x1800039d4  call    cs:__imp_OutputDebugStringW
0x1800039da  test    byte ptr [rbx+4], 4
0x1800039de  jnz     short loc_1800039E9
0x1800039e0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800039e7  jz      short loc_1800039FA
0x1800039e9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800039f0  test    rax, rax
0x1800039f3  jz      short loc_1800039FA
0x1800039f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039fa  mov     rbx, [rsp+78h+arg_10]
0x180003a02  add     rsp, 40h
0x180003a06  pop     r15
0x180003a08  pop     r14
0x180003a0a  pop     r13
0x180003a0c  pop     r12
0x180003a0e  pop     rdi
0x180003a0f  pop     rsi
0x180003a10  pop     rbp
0x180003a11  retn
0x180003a12  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
