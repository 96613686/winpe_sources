# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1802663c8`
- end: `0x1802666c0`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1802645e0`
- `0x18026492c`

## callees

- `0x18023cd80`
- `0x180264520`
- `0x1802659e4`
- `0x1802663c8`
- `0x180266e88`
- `0x180266eb0`
- `0x180267000`
- `0x18026701c`
- `0x1802683c4`
- `0x180307010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1802664eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1802664eb`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18026660a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18026660a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18026667c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18026667c`

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
  int v21; // edx
  _WORD *v22; // rax
  DWORD CurrentThreadId; // eax
  int v24; // edx
  wil::details::in1diag3 *v25; // rcx
  const struct wil::FailureInfo *v26; // r9
  __int64 ModuleName; // rax
  bool v28; // zf
  wil::details *v29; // [rsp+30h] [rbp-48h]

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
          LODWORD(v29) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v29);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v21);
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
  v22 = a9;
  if ( !a9 || !*a9 )
    v22 = 0;
  *(_QWORD *)(a16 + 24) = v22;
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v25);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v24);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v28 = !IsDebuggerPresent())
      : (v28 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v28)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v26);
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
0x1802663c8  mov     [rsp+arg_10], rbx
0x1802663cd  mov     [rsp+arg_8], edx
0x1802663d1  mov     [rsp+arg_0], rcx
0x1802663d6  push    rbp
0x1802663d7  push    rsi
0x1802663d8  push    rdi
0x1802663d9  push    r12
0x1802663db  push    r13
0x1802663dd  push    r14
0x1802663df  push    r15
0x1802663e1  sub     rsp, 40h
0x1802663e5  mov     r14, [rsp+78h+arg_38]
0x1802663ed  xor     eax, eax
0x1802663ef  mov     rbx, [rsp+78h+arg_78]
0x1802663f7  xor     ebp, ebp
0x1802663f9  mov     r15d, [rsp+78h+arg_30]
0x180266401  mov     r10, rcx
0x180266404  mov     rsi, [rsp+78h+lpOutputString]
0x18026640c  mov     r12, r9
0x18026640f  mov     r13, r8
0x180266412  mov     ecx, r15d
0x180266415  mov     [rsi], ax
0x180266418  mov     rax, [rsp+78h+arg_60]
0x180266420  mov     byte ptr [rax], 0
0x180266423  mov     edi, [r14]
0x180266426  mov     [rbx+8], edi
0x180266429  mov     eax, [r14+4]
0x18026642d  mov     [rbx+0Ch], eax
0x180266430  test    r15d, r15d
0x180266433  jz      short loc_18026649B
0x180266435  sub     ecx, 1
0x180266438  jz      short loc_180266492
0x18026643a  sub     ecx, 1
0x18026643d  jz      short loc_18026644D
0x18026643f  cmp     ecx, 1
0x180266442  jnz     short loc_1802664A4
0x180266444  mov     ecx, edi; this
0x180266446  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18026644b  jmp     short loc_1802664A2
0x18026644d  test    edi, edi
0x18026644f  js      short loc_180266489
0x180266451  mov     rax, [rsp+78h+arg_28]
0x180266459  mov     edi, 8007029Ch
0x18026645e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180266462  mov     rcx, r10; int
0x180266465  mov     [rsp+78h+var_50], rax; __int64
0x18026646a  mov     rax, [rsp+78h+arg_20]
0x180266472  mov     [rsp+78h+var_58], rax; __int64
0x180266477  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18026647c  mov     ecx, edi; this
0x18026647e  mov     [rbx+8], edi
0x180266481  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180266486  mov     [rbx+0Ch], eax
0x180266489  mov     ecx, edi; this
0x18026648b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180266490  jmp     short loc_1802664A2
0x180266492  mov     ecx, edi; this
0x180266494  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180266499  jmp     short loc_1802664A2
0x18026649b  mov     ecx, edi; this
0x18026649d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1802664a2  mov     ebp, eax
0x1802664a4  mov     eax, [rsp+78h+arg_70]
0x1802664ab  mov     [rbx+4], eax
0x1802664ae  mov     [rbx], r15d
0x1802664b1  cmp     dword ptr [r14+8], 1
0x1802664b6  jnz     short loc_1802664BE
0x1802664b8  or      eax, 8
0x1802664bb  mov     [rbx+4], eax
0x1802664be  mov     eax, 1
0x1802664c3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1802664cb  inc     eax
0x1802664cd  xor     edi, edi
0x1802664cf  mov     [rbx+10h], eax
0x1802664d2  mov     rax, [rsp+78h+arg_40]
0x1802664da  test    rax, rax
0x1802664dd  jz      short loc_1802664E4
0x1802664df  cmp     [rax], di
0x1802664e2  jnz     short loc_1802664E7
0x1802664e4  mov     rax, rdi
0x1802664e7  mov     [rbx+18h], rax
0x1802664eb  call    cs:__imp_GetCurrentThreadId
0x1802664f1  mov     [rbx+38h], r13
0x1802664f5  xorps   xmm0, xmm0
0x1802664f8  mov     [rbx+20h], eax
0x1802664fb  mov     eax, [rsp+78h+arg_8]
0x180266502  mov     [rbx+40h], eax
0x180266505  mov     rax, [rsp+78h+arg_20]
0x18026650d  mov     [rbx+28h], rax
0x180266511  mov     rax, [rsp+78h+arg_28]
0x180266519  mov     [rbx+88h], rax
0x180266520  mov     rax, [rsp+78h+arg_0]
0x180266528  mov     [rbx+90h], rax
0x18026652f  xor     eax, eax
0x180266531  mov     [rbx+44h], ebp
0x180266534  mov     [rbx+30h], r12
0x180266538  mov     [rbx+48h], rdi
0x18026653c  movups  xmmword ptr [rbx+68h], xmm0
0x180266540  mov     [rbx+78h], rax
0x180266544  movups  xmmword ptr [rbx+50h], xmm0
0x180266548  mov     [rbx+60h], rax
0x18026654c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180266553  test    rax, rax
0x180266556  jz      short loc_18026655F
0x180266558  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026655d  jmp     short loc_180266562
0x18026655f  mov     rax, rdi
0x180266562  mov     [rbx+80h], rax
0x180266569  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180266570  test    rax, rax
0x180266573  jz      short loc_18026657D
0x180266575  mov     rcx, rbx
0x180266578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026657d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180266584  test    rax, rax
0x180266587  jz      short loc_18026659F
0x180266589  mov     rdx, [rsp+78h+arg_60]
0x180266591  mov     r8d, 400h
0x180266597  mov     rcx, rbx
0x18026659a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026659f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1802665a6  test    rax, rax
0x1802665a9  jz      short loc_1802665B3
0x1802665ab  mov     rcx, rbx
0x1802665ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802665b3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1802665ba  test    rax, rax
0x1802665bd  jz      short loc_1802665CD
0x1802665bf  test    byte ptr [rbx+4], 2
0x1802665c3  jnz     short loc_1802665CD
0x1802665c5  mov     rcx, rbx
0x1802665c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802665cd  cmp     [rbx+8], edi
0x1802665d0  jl      short loc_1802665EC
0x1802665d2  cmp     r15d, 3
0x1802665d6  jnz     loc_1802666BA
0x1802665dc  mov     ecx, 8000FFFFh; this
0x1802665e1  mov     [rbx+8], ecx
0x1802665e4  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1802665e9  mov     [rbx+0Ch], eax
0x1802665ec  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1802665f3  jnz     short loc_180266614
0x1802665f5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1802665fc  test    rax, rax
0x1802665ff  jz      short loc_18026660A
0x180266601  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180266606  test    al, al
0x180266608  jmp     short loc_180266612
0x18026660a  call    cs:__imp_IsDebuggerPresent
0x180266610  test    eax, eax
0x180266612  jz      short loc_18026661A
0x180266614  test    byte ptr [rbx+4], 2
0x180266618  jz      short loc_18026663E
0x18026661a  mov     rax, cs:g_pfnResultLoggingCallback
0x180266621  test    rax, rax
0x180266624  jz      short loc_180266682
0x180266626  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18026662d  jnz     short loc_180266682
0x18026662f  xor     r8d, r8d
0x180266632  xor     edx, edx
0x180266634  mov     rcx, rbx
0x180266637  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026663c  jmp     short loc_180266682
0x18026663e  mov     rax, cs:g_pfnResultLoggingCallback
0x180266645  mov     ebp, 800h
0x18026664a  test    rax, rax
0x18026664d  jz      short loc_180266666
0x18026664f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180266656  jnz     short loc_180266666
0x180266658  mov     r8d, ebp
0x18026665b  mov     rdx, rsi
0x18026665e  mov     rcx, rbx
0x180266661  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180266666  cmp     [rsi], di
0x180266669  jnz     short loc_180266679
0x18026666b  mov     r8, rbx; unsigned __int64
0x18026666e  mov     rdx, rbp; unsigned __int16 *
0x180266671  mov     rcx, rsi; this
0x180266674  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180266679  mov     rcx, rsi; lpOutputString
0x18026667c  call    cs:__imp_OutputDebugStringW
0x180266682  test    byte ptr [rbx+4], 4
0x180266686  jnz     short loc_180266691
0x180266688  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18026668f  jz      short loc_1802666A2
0x180266691  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180266698  test    rax, rax
0x18026669b  jz      short loc_1802666A2
0x18026669d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802666a2  mov     rbx, [rsp+78h+arg_10]
0x1802666aa  add     rsp, 40h
0x1802666ae  pop     r15
0x1802666b0  pop     r14
0x1802666b2  pop     r13
0x1802666b4  pop     r12
0x1802666b6  pop     rdi
0x1802666b7  pop     rsi
0x1802666b8  pop     rbp
0x1802666b9  retn
0x1802666ba  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
