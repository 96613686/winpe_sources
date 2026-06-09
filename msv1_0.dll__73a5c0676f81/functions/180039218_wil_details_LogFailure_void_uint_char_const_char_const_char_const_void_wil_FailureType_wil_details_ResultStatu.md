# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180039218`
- end: `0x18003950d`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x1800371a0`
- `0x180037250`
- `0x180037344`

## callees

- `0x1800370f4`
- `0x180038634`
- `0x180038e3c`
- `0x180039218`
- `0x180039dbc`
- `0x180039de0`
- `0x180039e9c`
- `0x180039eb8`
- `0x18003b768`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003933b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003933b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18003945c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18003945c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800394ce`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800394ce`

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
0x180039218  mov     [rsp+arg_10], rbx
0x18003921d  mov     [rsp+arg_8], edx
0x180039221  mov     [rsp+arg_0], rcx
0x180039226  push    rbp
0x180039227  push    rsi
0x180039228  push    rdi
0x180039229  push    r12
0x18003922b  push    r13
0x18003922d  push    r14
0x18003922f  push    r15
0x180039231  sub     rsp, 40h
0x180039235  mov     r12, r9
0x180039238  mov     r13, r8
0x18003923b  mov     r10, rcx
0x18003923e  xor     eax, eax
0x180039240  mov     rsi, [rsp+78h+lpOutputString]
0x180039248  mov     [rsi], ax
0x18003924b  mov     rax, [rsp+78h+arg_60]
0x180039253  mov     byte ptr [rax], 0
0x180039256  mov     r14, [rsp+78h+arg_38]
0x18003925e  mov     edi, [r14]
0x180039261  mov     rbx, [rsp+78h+arg_78]
0x180039269  mov     [rbx+8], edi
0x18003926c  mov     eax, [r14+4]
0x180039270  mov     [rbx+0Ch], eax
0x180039273  xor     ebp, ebp
0x180039275  mov     r15d, [rsp+78h+arg_30]
0x18003927d  mov     ecx, r15d
0x180039280  test    r15d, r15d
0x180039283  jz      short loc_1800392EB
0x180039285  sub     ecx, 1
0x180039288  jz      short loc_1800392E2
0x18003928a  sub     ecx, 1
0x18003928d  jz      short loc_18003929D
0x18003928f  cmp     ecx, 1
0x180039292  jnz     short loc_1800392F4
0x180039294  mov     ecx, edi; this
0x180039296  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18003929b  jmp     short loc_1800392F2
0x18003929d  test    edi, edi
0x18003929f  js      short loc_1800392D9
0x1800392a1  mov     edi, 8007029Ch
0x1800392a6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800392aa  mov     rax, [rsp+78h+arg_28]
0x1800392b2  mov     [rsp+78h+var_50], rax; __int64
0x1800392b7  mov     rax, [rsp+78h+arg_20]
0x1800392bf  mov     [rsp+78h+var_58], rax; __int64
0x1800392c4  mov     rcx, r10; int
0x1800392c7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800392cc  mov     [rbx+8], edi
0x1800392cf  mov     ecx, edi; this
0x1800392d1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800392d6  mov     [rbx+0Ch], eax
0x1800392d9  mov     ecx, edi; this
0x1800392db  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800392e0  jmp     short loc_1800392F2
0x1800392e2  mov     ecx, edi; this
0x1800392e4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800392e9  jmp     short loc_1800392F2
0x1800392eb  mov     ecx, edi; this
0x1800392ed  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800392f2  mov     ebp, eax
0x1800392f4  mov     [rbx], r15d
0x1800392f7  mov     eax, [rsp+78h+arg_70]
0x1800392fe  mov     [rbx+4], eax
0x180039301  cmp     dword ptr [r14+8], 1
0x180039306  jnz     short loc_18003930E
0x180039308  or      eax, 8
0x18003930b  mov     [rbx+4], eax
0x18003930e  mov     eax, 1
0x180039313  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18003931b  inc     eax
0x18003931d  mov     [rbx+10h], eax
0x180039320  mov     rax, [rsp+78h+arg_40]
0x180039328  xor     edi, edi
0x18003932a  test    rax, rax
0x18003932d  jz      short loc_180039334
0x18003932f  cmp     [rax], di
0x180039332  jnz     short loc_180039337
0x180039334  mov     rax, rdi
0x180039337  mov     [rbx+18h], rax
0x18003933b  call    cs:__imp_GetCurrentThreadId
0x180039341  mov     [rbx+20h], eax
0x180039344  mov     [rbx+38h], r13
0x180039348  mov     eax, [rsp+78h+arg_8]
0x18003934f  mov     [rbx+40h], eax
0x180039352  mov     [rbx+44h], ebp
0x180039355  mov     rax, [rsp+78h+arg_20]
0x18003935d  mov     [rbx+28h], rax
0x180039361  mov     [rbx+30h], r12
0x180039365  mov     rax, [rsp+78h+arg_28]
0x18003936d  mov     [rbx+88h], rax
0x180039374  mov     rax, [rsp+78h+arg_0]
0x18003937c  mov     [rbx+90h], rax
0x180039383  mov     [rbx+48h], rdi
0x180039387  xorps   xmm0, xmm0
0x18003938a  xor     eax, eax
0x18003938c  movups  xmmword ptr [rbx+68h], xmm0
0x180039390  mov     [rbx+78h], rax
0x180039394  movups  xmmword ptr [rbx+50h], xmm0
0x180039398  mov     [rbx+60h], rax
0x18003939c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800393a3  test    rax, rax
0x1800393a6  jz      short loc_1800393AF
0x1800393a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800393ad  jmp     short loc_1800393B2
0x1800393af  mov     rax, rdi
0x1800393b2  mov     [rbx+80h], rax
0x1800393b9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800393c0  test    rax, rax
0x1800393c3  jz      short loc_1800393CD
0x1800393c5  mov     rcx, rbx
0x1800393c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800393cd  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800393d4  test    rax, rax
0x1800393d7  jz      short loc_1800393EF
0x1800393d9  mov     r8d, 400h
0x1800393df  mov     rdx, [rsp+78h+arg_60]
0x1800393e7  mov     rcx, rbx
0x1800393ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800393ef  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800393f6  test    rax, rax
0x1800393f9  jz      short loc_180039403
0x1800393fb  mov     rcx, rbx
0x1800393fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039403  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18003940a  test    rax, rax
0x18003940d  jz      short loc_18003941D
0x18003940f  test    byte ptr [rbx+4], 2
0x180039413  jnz     short loc_18003941D
0x180039415  mov     rcx, rbx
0x180039418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003941d  cmp     [rbx+8], edi
0x180039420  jl      short loc_18003943E
0x180039422  cmp     r15d, 3
0x180039426  jz      short loc_18003942E
0x180039428  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18003942e  mov     ecx, 8000FFFFh; this
0x180039433  mov     [rbx+8], ecx
0x180039436  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18003943b  mov     [rbx+0Ch], eax
0x18003943e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180039445  jnz     short loc_180039466
0x180039447  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18003944e  test    rax, rax
0x180039451  jz      short loc_18003945C
0x180039453  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039458  test    al, al
0x18003945a  jmp     short loc_180039464
0x18003945c  call    cs:__imp_IsDebuggerPresent
0x180039462  test    eax, eax
0x180039464  jz      short loc_18003946C
0x180039466  test    byte ptr [rbx+4], 2
0x18003946a  jz      short loc_180039490
0x18003946c  mov     rax, cs:g_pfnResultLoggingCallback
0x180039473  test    rax, rax
0x180039476  jz      short loc_1800394D4
0x180039478  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18003947f  jnz     short loc_1800394D4
0x180039481  xor     r8d, r8d
0x180039484  xor     edx, edx
0x180039486  mov     rcx, rbx
0x180039489  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003948e  jmp     short loc_1800394D4
0x180039490  mov     ebp, 800h
0x180039495  mov     rax, cs:g_pfnResultLoggingCallback
0x18003949c  test    rax, rax
0x18003949f  jz      short loc_1800394B8
0x1800394a1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800394a8  jnz     short loc_1800394B8
0x1800394aa  mov     r8d, ebp
0x1800394ad  mov     rdx, rsi
0x1800394b0  mov     rcx, rbx
0x1800394b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800394b8  cmp     [rsi], di
0x1800394bb  jnz     short loc_1800394CB
0x1800394bd  mov     r8, rbx; unsigned __int64
0x1800394c0  mov     rdx, rbp; unsigned __int16 *
0x1800394c3  mov     rcx, rsi; this
0x1800394c6  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800394cb  mov     rcx, rsi; lpOutputString
0x1800394ce  call    cs:__imp_OutputDebugStringW
0x1800394d4  test    byte ptr [rbx+4], 4
0x1800394d8  jnz     short loc_1800394E3
0x1800394da  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800394e1  jz      short loc_1800394F5
0x1800394e3  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800394ea  test    rax, rax
0x1800394ed  jz      short loc_1800394F5
0x1800394ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800394f4  nop
0x1800394f5  mov     rbx, [rsp+78h+arg_10]
0x1800394fd  add     rsp, 40h
0x180039501  pop     r15
0x180039503  pop     r14
0x180039505  pop     r13
0x180039507  pop     r12
0x180039509  pop     rdi
0x18003950a  pop     rsi
0x18003950b  pop     rbp
0x18003950c  retn
```
