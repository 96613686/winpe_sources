# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180007180`
- end: `0x180007475`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x1800052c0`
- `0x180005370`
- `0x180005464`

## callees

- `0x180005214`
- `0x180006684`
- `0x180006e8c`
- `0x180007180`
- `0x1800081ec`
- `0x180008210`
- `0x1800082cc`
- `0x1800082e8`
- `0x18000995c`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800072a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800072a3`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007436`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007436`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800073c4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800073c4`

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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v25 = !IsDebuggerPresent())
      : (v25 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v25)
    || (*(_BYTE *)(a16 + 4) & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, 0, 0, v23);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048, v23);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v23);
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
0x180007180  mov     [rsp+arg_10], rbx
0x180007185  mov     [rsp+arg_8], edx
0x180007189  mov     [rsp+arg_0], rcx
0x18000718e  push    rbp
0x18000718f  push    rsi
0x180007190  push    rdi
0x180007191  push    r12
0x180007193  push    r13
0x180007195  push    r14
0x180007197  push    r15
0x180007199  sub     rsp, 40h
0x18000719d  mov     r12, r9
0x1800071a0  mov     r13, r8
0x1800071a3  mov     r10, rcx
0x1800071a6  xor     eax, eax
0x1800071a8  mov     rsi, [rsp+78h+lpOutputString]
0x1800071b0  mov     [rsi], ax
0x1800071b3  mov     rax, [rsp+78h+arg_60]
0x1800071bb  mov     byte ptr [rax], 0
0x1800071be  mov     r14, [rsp+78h+arg_38]
0x1800071c6  mov     edi, [r14]
0x1800071c9  mov     rbx, [rsp+78h+arg_78]
0x1800071d1  mov     [rbx+8], edi
0x1800071d4  mov     eax, [r14+4]
0x1800071d8  mov     [rbx+0Ch], eax
0x1800071db  xor     ebp, ebp
0x1800071dd  mov     r15d, [rsp+78h+arg_30]
0x1800071e5  mov     ecx, r15d
0x1800071e8  test    r15d, r15d
0x1800071eb  jz      short loc_180007253
0x1800071ed  sub     ecx, 1
0x1800071f0  jz      short loc_18000724A
0x1800071f2  sub     ecx, 1
0x1800071f5  jz      short loc_180007205
0x1800071f7  cmp     ecx, 1
0x1800071fa  jnz     short loc_18000725C
0x1800071fc  mov     ecx, edi; this
0x1800071fe  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180007203  jmp     short loc_18000725A
0x180007205  test    edi, edi
0x180007207  js      short loc_180007241
0x180007209  mov     edi, 8007029Ch
0x18000720e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180007212  mov     rax, [rsp+78h+arg_28]
0x18000721a  mov     [rsp+78h+var_50], rax; __int64
0x18000721f  mov     rax, [rsp+78h+arg_20]
0x180007227  mov     [rsp+78h+var_58], rax; __int64
0x18000722c  mov     rcx, r10; int
0x18000722f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180007234  mov     [rbx+8], edi
0x180007237  mov     ecx, edi; this
0x180007239  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000723e  mov     [rbx+0Ch], eax
0x180007241  mov     ecx, edi; this
0x180007243  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180007248  jmp     short loc_18000725A
0x18000724a  mov     ecx, edi; this
0x18000724c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180007251  jmp     short loc_18000725A
0x180007253  mov     ecx, edi; this
0x180007255  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000725a  mov     ebp, eax
0x18000725c  mov     [rbx], r15d
0x18000725f  mov     eax, [rsp+78h+arg_70]
0x180007266  mov     [rbx+4], eax
0x180007269  cmp     dword ptr [r14+8], 1
0x18000726e  jnz     short loc_180007276
0x180007270  or      eax, 8
0x180007273  mov     [rbx+4], eax
0x180007276  mov     eax, 1
0x18000727b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180007283  inc     eax
0x180007285  mov     [rbx+10h], eax
0x180007288  mov     rax, [rsp+78h+arg_40]
0x180007290  xor     edi, edi
0x180007292  test    rax, rax
0x180007295  jz      short loc_18000729C
0x180007297  cmp     [rax], di
0x18000729a  jnz     short loc_18000729F
0x18000729c  mov     rax, rdi
0x18000729f  mov     [rbx+18h], rax
0x1800072a3  call    cs:__imp_GetCurrentThreadId
0x1800072a9  mov     [rbx+20h], eax
0x1800072ac  mov     [rbx+38h], r13
0x1800072b0  mov     eax, [rsp+78h+arg_8]
0x1800072b7  mov     [rbx+40h], eax
0x1800072ba  mov     [rbx+44h], ebp
0x1800072bd  mov     rax, [rsp+78h+arg_20]
0x1800072c5  mov     [rbx+28h], rax
0x1800072c9  mov     [rbx+30h], r12
0x1800072cd  mov     rax, [rsp+78h+arg_28]
0x1800072d5  mov     [rbx+88h], rax
0x1800072dc  mov     rax, [rsp+78h+arg_0]
0x1800072e4  mov     [rbx+90h], rax
0x1800072eb  mov     [rbx+48h], rdi
0x1800072ef  xorps   xmm0, xmm0
0x1800072f2  xor     eax, eax
0x1800072f4  movups  xmmword ptr [rbx+68h], xmm0
0x1800072f8  mov     [rbx+78h], rax
0x1800072fc  movups  xmmword ptr [rbx+50h], xmm0
0x180007300  mov     [rbx+60h], rax
0x180007304  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000730b  test    rax, rax
0x18000730e  jz      short loc_180007317
0x180007310  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007315  jmp     short loc_18000731A
0x180007317  mov     rax, rdi
0x18000731a  mov     [rbx+80h], rax
0x180007321  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180007328  test    rax, rax
0x18000732b  jz      short loc_180007335
0x18000732d  mov     rcx, rbx
0x180007330  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007335  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000733c  test    rax, rax
0x18000733f  jz      short loc_180007357
0x180007341  mov     r8d, 400h
0x180007347  mov     rdx, [rsp+78h+arg_60]
0x18000734f  mov     rcx, rbx
0x180007352  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007357  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000735e  test    rax, rax
0x180007361  jz      short loc_18000736B
0x180007363  mov     rcx, rbx
0x180007366  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000736b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007372  test    rax, rax
0x180007375  jz      short loc_180007385
0x180007377  test    byte ptr [rbx+4], 2
0x18000737b  jnz     short loc_180007385
0x18000737d  mov     rcx, rbx
0x180007380  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007385  cmp     [rbx+8], edi
0x180007388  jl      short loc_1800073A6
0x18000738a  cmp     r15d, 3
0x18000738e  jz      short loc_180007396
0x180007390  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180007396  mov     ecx, 8000FFFFh; this
0x18000739b  mov     [rbx+8], ecx
0x18000739e  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800073a3  mov     [rbx+0Ch], eax
0x1800073a6  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800073ad  jnz     short loc_1800073CE
0x1800073af  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800073b6  test    rax, rax
0x1800073b9  jz      short loc_1800073C4
0x1800073bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073c0  test    al, al
0x1800073c2  jmp     short loc_1800073CC
0x1800073c4  call    cs:__imp_IsDebuggerPresent
0x1800073ca  test    eax, eax
0x1800073cc  jz      short loc_1800073D4
0x1800073ce  test    byte ptr [rbx+4], 2
0x1800073d2  jz      short loc_1800073F8
0x1800073d4  mov     rax, cs:g_pfnResultLoggingCallback
0x1800073db  test    rax, rax
0x1800073de  jz      short loc_18000743C
0x1800073e0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800073e7  jnz     short loc_18000743C
0x1800073e9  xor     r8d, r8d
0x1800073ec  xor     edx, edx
0x1800073ee  mov     rcx, rbx
0x1800073f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073f6  jmp     short loc_18000743C
0x1800073f8  mov     ebp, 800h
0x1800073fd  mov     rax, cs:g_pfnResultLoggingCallback
0x180007404  test    rax, rax
0x180007407  jz      short loc_180007420
0x180007409  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180007410  jnz     short loc_180007420
0x180007412  mov     r8d, ebp
0x180007415  mov     rdx, rsi
0x180007418  mov     rcx, rbx
0x18000741b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007420  cmp     [rsi], di
0x180007423  jnz     short loc_180007433
0x180007425  mov     r8, rbx; unsigned __int64
0x180007428  mov     rdx, rbp; unsigned __int16 *
0x18000742b  mov     rcx, rsi; this
0x18000742e  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180007433  mov     rcx, rsi; lpOutputString
0x180007436  call    cs:__imp_OutputDebugStringW
0x18000743c  test    byte ptr [rbx+4], 4
0x180007440  jnz     short loc_18000744B
0x180007442  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180007449  jz      short loc_18000745D
0x18000744b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180007452  test    rax, rax
0x180007455  jz      short loc_18000745D
0x180007457  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000745c  nop
0x18000745d  mov     rbx, [rsp+78h+arg_10]
0x180007465  add     rsp, 40h
0x180007469  pop     r15
0x18000746b  pop     r14
0x18000746d  pop     r13
0x18000746f  pop     r12
0x180007471  pop     rdi
0x180007472  pop     rsi
0x180007473  pop     rbp
0x180007474  retn
```
