# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800055bc`
- end: `0x1800058b5`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180003c68`
- `0x180003fbc`
- `0x180009d0c`

## callees

- `0x180003ba0`
- `0x180004ba4`
- `0x1800053cc`
- `0x1800055bc`
- `0x180005c94`
- `0x180005cb0`
- `0x180005cc4`
- `0x180005ce0`
- `0x180006ae4`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800056df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800056df`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800057fe`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800057fe`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005870`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005870`

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
    ModuleName = wil::details::g_pfnGetModuleName(v24);
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
      : (v27 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v24) == 0),
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
      wil::details::g_pfnDebugBreak(v24);
  }
}

```

## disassembly

```asm
0x1800055bc  mov     [rsp+arg_10], rbx
0x1800055c1  mov     [rsp+arg_8], edx
0x1800055c5  mov     [rsp+arg_0], rcx
0x1800055ca  push    rbp
0x1800055cb  push    rsi
0x1800055cc  push    rdi
0x1800055cd  push    r12
0x1800055cf  push    r13
0x1800055d1  push    r14
0x1800055d3  push    r15
0x1800055d5  sub     rsp, 40h
0x1800055d9  mov     r12, r9
0x1800055dc  mov     r13, r8
0x1800055df  mov     r10, rcx
0x1800055e2  xor     eax, eax
0x1800055e4  mov     rsi, [rsp+78h+lpOutputString]
0x1800055ec  mov     [rsi], ax
0x1800055ef  mov     rax, [rsp+78h+arg_60]
0x1800055f7  mov     byte ptr [rax], 0
0x1800055fa  mov     r14, [rsp+78h+arg_38]
0x180005602  mov     edi, [r14]
0x180005605  mov     rbx, [rsp+78h+arg_78]
0x18000560d  mov     [rbx+8], edi
0x180005610  mov     eax, [r14+4]
0x180005614  mov     [rbx+0Ch], eax
0x180005617  xor     ebp, ebp
0x180005619  mov     r15d, [rsp+78h+arg_30]
0x180005621  mov     ecx, r15d
0x180005624  test    r15d, r15d
0x180005627  jz      short loc_18000568F
0x180005629  sub     ecx, 1
0x18000562c  jz      short loc_180005686
0x18000562e  sub     ecx, 1
0x180005631  jz      short loc_180005641
0x180005633  cmp     ecx, 1
0x180005636  jnz     short loc_180005698
0x180005638  mov     ecx, edi; this
0x18000563a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000563f  jmp     short loc_180005696
0x180005641  test    edi, edi
0x180005643  js      short loc_18000567D
0x180005645  mov     edi, 8007029Ch
0x18000564a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000564e  mov     rax, [rsp+78h+arg_28]
0x180005656  mov     [rsp+78h+var_50], rax; __int64
0x18000565b  mov     rax, [rsp+78h+arg_20]
0x180005663  mov     [rsp+78h+var_58], rax; __int64
0x180005668  mov     rcx, r10; int
0x18000566b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180005670  mov     [rbx+8], edi
0x180005673  mov     ecx, edi; this
0x180005675  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000567a  mov     [rbx+0Ch], eax
0x18000567d  mov     ecx, edi; this
0x18000567f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180005684  jmp     short loc_180005696
0x180005686  mov     ecx, edi; this
0x180005688  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000568d  jmp     short loc_180005696
0x18000568f  mov     ecx, edi; this
0x180005691  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180005696  mov     ebp, eax
0x180005698  mov     [rbx], r15d
0x18000569b  mov     eax, [rsp+78h+arg_70]
0x1800056a2  mov     [rbx+4], eax
0x1800056a5  cmp     dword ptr [r14+8], 1
0x1800056aa  jnz     short loc_1800056B2
0x1800056ac  or      eax, 8
0x1800056af  mov     [rbx+4], eax
0x1800056b2  mov     eax, 1
0x1800056b7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800056bf  inc     eax
0x1800056c1  mov     [rbx+10h], eax
0x1800056c4  mov     rax, [rsp+78h+arg_40]
0x1800056cc  xor     edi, edi
0x1800056ce  test    rax, rax
0x1800056d1  jz      short loc_1800056D8
0x1800056d3  cmp     [rax], di
0x1800056d6  jnz     short loc_1800056DB
0x1800056d8  mov     rax, rdi
0x1800056db  mov     [rbx+18h], rax
0x1800056df  call    cs:__imp_GetCurrentThreadId
0x1800056e5  mov     [rbx+20h], eax
0x1800056e8  mov     [rbx+38h], r13
0x1800056ec  mov     eax, [rsp+78h+arg_8]
0x1800056f3  mov     [rbx+40h], eax
0x1800056f6  mov     [rbx+44h], ebp
0x1800056f9  mov     rax, [rsp+78h+arg_20]
0x180005701  mov     [rbx+28h], rax
0x180005705  mov     [rbx+30h], r12
0x180005709  mov     rax, [rsp+78h+arg_28]
0x180005711  mov     [rbx+88h], rax
0x180005718  mov     rax, [rsp+78h+arg_0]
0x180005720  mov     [rbx+90h], rax
0x180005727  mov     [rbx+48h], rdi
0x18000572b  xorps   xmm0, xmm0
0x18000572e  xor     eax, eax
0x180005730  movups  xmmword ptr [rbx+68h], xmm0
0x180005734  mov     [rbx+78h], rax
0x180005738  movups  xmmword ptr [rbx+50h], xmm0
0x18000573c  mov     [rbx+60h], rax
0x180005740  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005747  test    rax, rax
0x18000574a  jz      short loc_180005753
0x18000574c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005751  jmp     short loc_180005756
0x180005753  mov     rax, rdi
0x180005756  mov     [rbx+80h], rax
0x18000575d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005764  test    rax, rax
0x180005767  jz      short loc_180005771
0x180005769  mov     rcx, rbx
0x18000576c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005771  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005778  test    rax, rax
0x18000577b  jz      short loc_180005793
0x18000577d  mov     r8d, 400h
0x180005783  mov     rdx, [rsp+78h+arg_60]
0x18000578b  mov     rcx, rbx
0x18000578e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005793  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000579a  test    rax, rax
0x18000579d  jz      short loc_1800057A7
0x18000579f  mov     rcx, rbx
0x1800057a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057a7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800057ae  test    rax, rax
0x1800057b1  jz      short loc_1800057C1
0x1800057b3  test    byte ptr [rbx+4], 2
0x1800057b7  jnz     short loc_1800057C1
0x1800057b9  mov     rcx, rbx
0x1800057bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057c1  cmp     [rbx+8], edi
0x1800057c4  jl      short loc_1800057E0
0x1800057c6  cmp     r15d, 3
0x1800057ca  jnz     loc_1800058AF
0x1800057d0  mov     ecx, 8000FFFFh; this
0x1800057d5  mov     [rbx+8], ecx
0x1800057d8  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800057dd  mov     [rbx+0Ch], eax
0x1800057e0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800057e7  jnz     short loc_180005808
0x1800057e9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800057f0  test    rax, rax
0x1800057f3  jz      short loc_1800057FE
0x1800057f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057fa  test    al, al
0x1800057fc  jmp     short loc_180005806
0x1800057fe  call    cs:__imp_IsDebuggerPresent
0x180005804  test    eax, eax
0x180005806  jz      short loc_18000580E
0x180005808  test    byte ptr [rbx+4], 2
0x18000580c  jz      short loc_180005832
0x18000580e  mov     rax, cs:g_pfnResultLoggingCallback
0x180005815  test    rax, rax
0x180005818  jz      short loc_180005876
0x18000581a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005821  jnz     short loc_180005876
0x180005823  xor     r8d, r8d
0x180005826  xor     edx, edx
0x180005828  mov     rcx, rbx
0x18000582b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005830  jmp     short loc_180005876
0x180005832  mov     ebp, 800h
0x180005837  mov     rax, cs:g_pfnResultLoggingCallback
0x18000583e  test    rax, rax
0x180005841  jz      short loc_18000585A
0x180005843  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000584a  jnz     short loc_18000585A
0x18000584c  mov     r8d, ebp
0x18000584f  mov     rdx, rsi
0x180005852  mov     rcx, rbx
0x180005855  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000585a  cmp     [rsi], di
0x18000585d  jnz     short loc_18000586D
0x18000585f  mov     r8, rbx; unsigned __int64
0x180005862  mov     rdx, rbp; unsigned __int16 *
0x180005865  mov     rcx, rsi; this
0x180005868  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000586d  mov     rcx, rsi; lpOutputString
0x180005870  call    cs:__imp_OutputDebugStringW
0x180005876  test    byte ptr [rbx+4], 4
0x18000587a  jnz     short loc_180005885
0x18000587c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180005883  jz      short loc_180005897
0x180005885  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000588c  test    rax, rax
0x18000588f  jz      short loc_180005897
0x180005891  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005896  nop
0x180005897  mov     rbx, [rsp+78h+arg_10]
0x18000589f  add     rsp, 40h
0x1800058a3  pop     r15
0x1800058a5  pop     r14
0x1800058a7  pop     r13
0x1800058a9  pop     r12
0x1800058ab  pop     rdi
0x1800058ac  pop     rsi
0x1800058ad  pop     rbp
0x1800058ae  retn
0x1800058af  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
