# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140006158`
- end: `0x140006464`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `780`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1400035b4`

## callees

- `0x140002fd0`
- `0x140005604`
- `0x140005e1c`
- `0x140006158`
- `0x140007248`
- `0x140007270`
- `0x1400073b8`
- `0x1400073d8`
- `0x140009e10`
- `0x140017010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000627b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000627b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400063a0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400063a0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140006418`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140006418`

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
0x140006158  mov     [rsp+arg_10], rbx
0x14000615d  mov     [rsp+arg_8], edx
0x140006161  mov     [rsp+arg_0], rcx
0x140006166  push    rbp
0x140006167  push    rsi
0x140006168  push    rdi
0x140006169  push    r12
0x14000616b  push    r13
0x14000616d  push    r14
0x14000616f  push    r15
0x140006171  sub     rsp, 40h
0x140006175  mov     r12, r9
0x140006178  mov     r13, r8
0x14000617b  mov     r10, rcx
0x14000617e  xor     eax, eax
0x140006180  mov     rsi, [rsp+78h+lpOutputString]
0x140006188  mov     [rsi], ax
0x14000618b  mov     rax, [rsp+78h+arg_60]
0x140006193  mov     byte ptr [rax], 0
0x140006196  mov     r14, [rsp+78h+arg_38]
0x14000619e  mov     edi, [r14]
0x1400061a1  mov     rbx, [rsp+78h+arg_78]
0x1400061a9  mov     [rbx+8], edi
0x1400061ac  mov     eax, [r14+4]
0x1400061b0  mov     [rbx+0Ch], eax
0x1400061b3  xor     ebp, ebp
0x1400061b5  mov     r15d, [rsp+78h+arg_30]
0x1400061bd  mov     ecx, r15d
0x1400061c0  test    r15d, r15d
0x1400061c3  jz      short loc_14000622B
0x1400061c5  sub     ecx, 1
0x1400061c8  jz      short loc_140006222
0x1400061ca  sub     ecx, 1
0x1400061cd  jz      short loc_1400061DD
0x1400061cf  cmp     ecx, 1
0x1400061d2  jnz     short loc_140006234
0x1400061d4  mov     ecx, edi; this
0x1400061d6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1400061db  jmp     short loc_140006232
0x1400061dd  test    edi, edi
0x1400061df  js      short loc_140006219
0x1400061e1  mov     edi, 8007029Ch
0x1400061e6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1400061ea  mov     rax, [rsp+78h+arg_28]
0x1400061f2  mov     [rsp+78h+var_50], rax; __int64
0x1400061f7  mov     rax, [rsp+78h+arg_20]
0x1400061ff  mov     [rsp+78h+var_58], rax; __int64
0x140006204  mov     rcx, r10; int
0x140006207  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x14000620c  mov     [rbx+8], edi
0x14000620f  mov     ecx, edi; this
0x140006211  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140006216  mov     [rbx+0Ch], eax
0x140006219  mov     ecx, edi; this
0x14000621b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140006220  jmp     short loc_140006232
0x140006222  mov     ecx, edi; this
0x140006224  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140006229  jmp     short loc_140006232
0x14000622b  mov     ecx, edi; this
0x14000622d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140006232  mov     ebp, eax
0x140006234  mov     [rbx], r15d
0x140006237  mov     eax, [rsp+78h+arg_70]
0x14000623e  mov     [rbx+4], eax
0x140006241  cmp     dword ptr [r14+8], 1
0x140006246  jnz     short loc_14000624E
0x140006248  or      eax, 8
0x14000624b  mov     [rbx+4], eax
0x14000624e  mov     eax, 1
0x140006253  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000625b  inc     eax
0x14000625d  mov     [rbx+10h], eax
0x140006260  mov     rax, [rsp+78h+arg_40]
0x140006268  xor     edi, edi
0x14000626a  test    rax, rax
0x14000626d  jz      short loc_140006274
0x14000626f  cmp     [rax], di
0x140006272  jnz     short loc_140006277
0x140006274  mov     rax, rdi
0x140006277  mov     [rbx+18h], rax
0x14000627b  call    cs:__imp_GetCurrentThreadId
0x140006282  nop     dword ptr [rax+rax+00h]
0x140006287  mov     [rbx+20h], eax
0x14000628a  mov     [rbx+38h], r13
0x14000628e  mov     eax, [rsp+78h+arg_8]
0x140006295  mov     [rbx+40h], eax
0x140006298  mov     [rbx+44h], ebp
0x14000629b  mov     rax, [rsp+78h+arg_20]
0x1400062a3  mov     [rbx+28h], rax
0x1400062a7  mov     [rbx+30h], r12
0x1400062ab  mov     rax, [rsp+78h+arg_28]
0x1400062b3  mov     [rbx+88h], rax
0x1400062ba  mov     rax, [rsp+78h+arg_0]
0x1400062c2  mov     [rbx+90h], rax
0x1400062c9  mov     [rbx+48h], rdi
0x1400062cd  xorps   xmm0, xmm0
0x1400062d0  xor     eax, eax
0x1400062d2  movups  xmmword ptr [rbx+68h], xmm0
0x1400062d6  mov     [rbx+78h], rax
0x1400062da  movups  xmmword ptr [rbx+50h], xmm0
0x1400062de  mov     [rbx+60h], rax
0x1400062e2  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1400062e9  test    rax, rax
0x1400062ec  jz      short loc_1400062F5
0x1400062ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400062f3  jmp     short loc_1400062F8
0x1400062f5  mov     rax, rdi
0x1400062f8  mov     [rbx+80h], rax
0x1400062ff  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140006306  test    rax, rax
0x140006309  jz      short loc_140006313
0x14000630b  mov     rcx, rbx
0x14000630e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006313  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000631a  test    rax, rax
0x14000631d  jz      short loc_140006335
0x14000631f  mov     r8d, 400h
0x140006325  mov     rdx, [rsp+78h+arg_60]
0x14000632d  mov     rcx, rbx
0x140006330  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006335  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000633c  test    rax, rax
0x14000633f  jz      short loc_140006349
0x140006341  mov     rcx, rbx
0x140006344  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006349  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140006350  test    rax, rax
0x140006353  jz      short loc_140006363
0x140006355  test    byte ptr [rbx+4], 2
0x140006359  jnz     short loc_140006363
0x14000635b  mov     rcx, rbx
0x14000635e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006363  cmp     [rbx+8], edi
0x140006366  jl      short loc_140006382
0x140006368  cmp     r15d, 3
0x14000636c  jnz     loc_14000645E
0x140006372  mov     ecx, 8000FFFFh; this
0x140006377  mov     [rbx+8], ecx
0x14000637a  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000637f  mov     [rbx+0Ch], eax
0x140006382  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x140006389  jnz     short loc_1400063B0
0x14000638b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140006392  test    rax, rax
0x140006395  jz      short loc_1400063A0
0x140006397  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000639c  test    al, al
0x14000639e  jmp     short loc_1400063AE
0x1400063a0  call    cs:__imp_IsDebuggerPresent
0x1400063a7  nop     dword ptr [rax+rax+00h]
0x1400063ac  test    eax, eax
0x1400063ae  jz      short loc_1400063B6
0x1400063b0  test    byte ptr [rbx+4], 2
0x1400063b4  jz      short loc_1400063DA
0x1400063b6  mov     rax, cs:g_pfnResultLoggingCallback
0x1400063bd  test    rax, rax
0x1400063c0  jz      short loc_140006424
0x1400063c2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1400063c9  jnz     short loc_140006424
0x1400063cb  xor     r8d, r8d
0x1400063ce  xor     edx, edx
0x1400063d0  mov     rcx, rbx
0x1400063d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400063d8  jmp     short loc_140006424
0x1400063da  mov     ebp, 800h
0x1400063df  mov     rax, cs:g_pfnResultLoggingCallback
0x1400063e6  test    rax, rax
0x1400063e9  jz      short loc_140006402
0x1400063eb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1400063f2  jnz     short loc_140006402
0x1400063f4  mov     r8d, ebp
0x1400063f7  mov     rdx, rsi
0x1400063fa  mov     rcx, rbx
0x1400063fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006402  cmp     [rsi], di
0x140006405  jnz     short loc_140006415
0x140006407  mov     r8, rbx; unsigned __int64
0x14000640a  mov     rdx, rbp; unsigned __int16 *
0x14000640d  mov     rcx, rsi; this
0x140006410  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140006415  mov     rcx, rsi; lpOutputString
0x140006418  call    cs:__imp_OutputDebugStringW
0x14000641f  nop     dword ptr [rax+rax+00h]
0x140006424  test    byte ptr [rbx+4], 4
0x140006428  jnz     short loc_140006433
0x14000642a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x140006431  jz      short loc_140006445
0x140006433  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14000643a  test    rax, rax
0x14000643d  jz      short loc_140006445
0x14000643f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006444  nop
0x140006445  mov     rbx, [rsp+78h+arg_10]
0x14000644d  add     rsp, 40h
0x140006451  pop     r15
0x140006453  pop     r14
0x140006455  pop     r13
0x140006457  pop     r12
0x140006459  pop     rdi
0x14000645a  pop     rsi
0x14000645b  pop     rbp
0x14000645c  retn
0x14000645e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
