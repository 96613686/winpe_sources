# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180006168`
- end: `0x18000645d`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x18000458c`
- `0x18000464c`
- `0x180004748`
- `0x180009920`

## callees

- `0x1800044d4`
- `0x180005864`
- `0x180005fa4`
- `0x180006168`
- `0x180006744`
- `0x180006760`
- `0x180006774`
- `0x180006790`
- `0x180007558`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000628b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000628b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000641e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000641e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800063ac`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800063ac`

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
0x180006168  mov     [rsp+arg_10], rbx
0x18000616d  mov     [rsp+arg_8], edx
0x180006171  mov     [rsp+arg_0], rcx
0x180006176  push    rbp
0x180006177  push    rsi
0x180006178  push    rdi
0x180006179  push    r12
0x18000617b  push    r13
0x18000617d  push    r14
0x18000617f  push    r15
0x180006181  sub     rsp, 40h
0x180006185  mov     r12, r9
0x180006188  mov     r13, r8
0x18000618b  mov     r10, rcx
0x18000618e  xor     eax, eax
0x180006190  mov     rsi, [rsp+78h+lpOutputString]
0x180006198  mov     [rsi], ax
0x18000619b  mov     rax, [rsp+78h+arg_60]
0x1800061a3  mov     byte ptr [rax], 0
0x1800061a6  mov     r14, [rsp+78h+arg_38]
0x1800061ae  mov     edi, [r14]
0x1800061b1  mov     rbx, [rsp+78h+arg_78]
0x1800061b9  mov     [rbx+8], edi
0x1800061bc  mov     eax, [r14+4]
0x1800061c0  mov     [rbx+0Ch], eax
0x1800061c3  xor     ebp, ebp
0x1800061c5  mov     r15d, [rsp+78h+arg_30]
0x1800061cd  mov     ecx, r15d
0x1800061d0  test    r15d, r15d
0x1800061d3  jz      short loc_18000623B
0x1800061d5  sub     ecx, 1
0x1800061d8  jz      short loc_180006232
0x1800061da  sub     ecx, 1
0x1800061dd  jz      short loc_1800061ED
0x1800061df  cmp     ecx, 1
0x1800061e2  jnz     short loc_180006244
0x1800061e4  mov     ecx, edi; this
0x1800061e6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800061eb  jmp     short loc_180006242
0x1800061ed  test    edi, edi
0x1800061ef  js      short loc_180006229
0x1800061f1  mov     edi, 8007029Ch
0x1800061f6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800061fa  mov     rax, [rsp+78h+arg_28]
0x180006202  mov     [rsp+78h+var_50], rax; __int64
0x180006207  mov     rax, [rsp+78h+arg_20]
0x18000620f  mov     [rsp+78h+var_58], rax; __int64
0x180006214  mov     rcx, r10; int
0x180006217  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000621c  mov     [rbx+8], edi
0x18000621f  mov     ecx, edi; this
0x180006221  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006226  mov     [rbx+0Ch], eax
0x180006229  mov     ecx, edi; this
0x18000622b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180006230  jmp     short loc_180006242
0x180006232  mov     ecx, edi; this
0x180006234  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180006239  jmp     short loc_180006242
0x18000623b  mov     ecx, edi; this
0x18000623d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180006242  mov     ebp, eax
0x180006244  mov     [rbx], r15d
0x180006247  mov     eax, [rsp+78h+arg_70]
0x18000624e  mov     [rbx+4], eax
0x180006251  cmp     dword ptr [r14+8], 1
0x180006256  jnz     short loc_18000625E
0x180006258  or      eax, 8
0x18000625b  mov     [rbx+4], eax
0x18000625e  mov     eax, 1
0x180006263  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000626b  inc     eax
0x18000626d  mov     [rbx+10h], eax
0x180006270  mov     rax, [rsp+78h+arg_40]
0x180006278  xor     edi, edi
0x18000627a  test    rax, rax
0x18000627d  jz      short loc_180006284
0x18000627f  cmp     [rax], di
0x180006282  jnz     short loc_180006287
0x180006284  mov     rax, rdi
0x180006287  mov     [rbx+18h], rax
0x18000628b  call    cs:__imp_GetCurrentThreadId
0x180006291  mov     [rbx+20h], eax
0x180006294  mov     [rbx+38h], r13
0x180006298  mov     eax, [rsp+78h+arg_8]
0x18000629f  mov     [rbx+40h], eax
0x1800062a2  mov     [rbx+44h], ebp
0x1800062a5  mov     rax, [rsp+78h+arg_20]
0x1800062ad  mov     [rbx+28h], rax
0x1800062b1  mov     [rbx+30h], r12
0x1800062b5  mov     rax, [rsp+78h+arg_28]
0x1800062bd  mov     [rbx+88h], rax
0x1800062c4  mov     rax, [rsp+78h+arg_0]
0x1800062cc  mov     [rbx+90h], rax
0x1800062d3  mov     [rbx+48h], rdi
0x1800062d7  xorps   xmm0, xmm0
0x1800062da  xor     eax, eax
0x1800062dc  movups  xmmword ptr [rbx+68h], xmm0
0x1800062e0  mov     [rbx+78h], rax
0x1800062e4  movups  xmmword ptr [rbx+50h], xmm0
0x1800062e8  mov     [rbx+60h], rax
0x1800062ec  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800062f3  test    rax, rax
0x1800062f6  jz      short loc_1800062FF
0x1800062f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062fd  jmp     short loc_180006302
0x1800062ff  mov     rax, rdi
0x180006302  mov     [rbx+80h], rax
0x180006309  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006310  test    rax, rax
0x180006313  jz      short loc_18000631D
0x180006315  mov     rcx, rbx
0x180006318  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000631d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006324  test    rax, rax
0x180006327  jz      short loc_18000633F
0x180006329  mov     r8d, 400h
0x18000632f  mov     rdx, [rsp+78h+arg_60]
0x180006337  mov     rcx, rbx
0x18000633a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000633f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006346  test    rax, rax
0x180006349  jz      short loc_180006353
0x18000634b  mov     rcx, rbx
0x18000634e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006353  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000635a  test    rax, rax
0x18000635d  jz      short loc_18000636D
0x18000635f  test    byte ptr [rbx+4], 2
0x180006363  jnz     short loc_18000636D
0x180006365  mov     rcx, rbx
0x180006368  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000636d  cmp     [rbx+8], edi
0x180006370  jl      short loc_18000638E
0x180006372  cmp     r15d, 3
0x180006376  jz      short loc_18000637E
0x180006378  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000637e  mov     ecx, 8000FFFFh; this
0x180006383  mov     [rbx+8], ecx
0x180006386  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000638b  mov     [rbx+0Ch], eax
0x18000638e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180006395  jnz     short loc_1800063B6
0x180006397  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000639e  test    rax, rax
0x1800063a1  jz      short loc_1800063AC
0x1800063a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063a8  test    al, al
0x1800063aa  jmp     short loc_1800063B4
0x1800063ac  call    cs:__imp_IsDebuggerPresent
0x1800063b2  test    eax, eax
0x1800063b4  jz      short loc_1800063BC
0x1800063b6  test    byte ptr [rbx+4], 2
0x1800063ba  jz      short loc_1800063E0
0x1800063bc  mov     rax, cs:g_pfnResultLoggingCallback
0x1800063c3  test    rax, rax
0x1800063c6  jz      short loc_180006424
0x1800063c8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800063cf  jnz     short loc_180006424
0x1800063d1  xor     r8d, r8d
0x1800063d4  xor     edx, edx
0x1800063d6  mov     rcx, rbx
0x1800063d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063de  jmp     short loc_180006424
0x1800063e0  mov     ebp, 800h
0x1800063e5  mov     rax, cs:g_pfnResultLoggingCallback
0x1800063ec  test    rax, rax
0x1800063ef  jz      short loc_180006408
0x1800063f1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800063f8  jnz     short loc_180006408
0x1800063fa  mov     r8d, ebp
0x1800063fd  mov     rdx, rsi
0x180006400  mov     rcx, rbx
0x180006403  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006408  cmp     [rsi], di
0x18000640b  jnz     short loc_18000641B
0x18000640d  mov     r8, rbx; unsigned __int64
0x180006410  mov     rdx, rbp; unsigned __int16 *
0x180006413  mov     rcx, rsi; this
0x180006416  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000641b  mov     rcx, rsi; lpOutputString
0x18000641e  call    cs:__imp_OutputDebugStringW
0x180006424  test    byte ptr [rbx+4], 4
0x180006428  jnz     short loc_180006433
0x18000642a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180006431  jz      short loc_180006445
0x180006433  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000643a  test    rax, rax
0x18000643d  jz      short loc_180006445
0x18000643f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006444  nop
0x180006445  mov     rbx, [rsp+78h+arg_10]
0x18000644d  add     rsp, 40h
0x180006451  pop     r15
0x180006453  pop     r14
0x180006455  pop     r13
0x180006457  pop     r12
0x180006459  pop     rdi
0x18000645a  pop     rsi
0x18000645b  pop     rbp
0x18000645c  retn
```
