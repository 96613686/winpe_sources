# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800061c8`
- end: `0x1800064c0`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180004048`
- `0x180004394`

## callees

- `0x18000255c`
- `0x180003f88`
- `0x180005814`
- `0x1800061c8`
- `0x180006f7c`
- `0x180006fa0`
- `0x180007124`
- `0x180007140`
- `0x180008a98`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800062eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800062eb`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000640a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000640a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000647c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000647c`

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
0x1800061c8  mov     [rsp+arg_10], rbx
0x1800061cd  mov     [rsp+arg_8], edx
0x1800061d1  mov     [rsp+arg_0], rcx
0x1800061d6  push    rbp
0x1800061d7  push    rsi
0x1800061d8  push    rdi
0x1800061d9  push    r12
0x1800061db  push    r13
0x1800061dd  push    r14
0x1800061df  push    r15
0x1800061e1  sub     rsp, 40h
0x1800061e5  mov     r14, [rsp+78h+arg_38]
0x1800061ed  xor     eax, eax
0x1800061ef  mov     rbx, [rsp+78h+arg_78]
0x1800061f7  xor     ebp, ebp
0x1800061f9  mov     r15d, [rsp+78h+arg_30]
0x180006201  mov     r10, rcx
0x180006204  mov     rsi, [rsp+78h+lpOutputString]
0x18000620c  mov     r12, r9
0x18000620f  mov     r13, r8
0x180006212  mov     ecx, r15d
0x180006215  mov     [rsi], ax
0x180006218  mov     rax, [rsp+78h+arg_60]
0x180006220  mov     byte ptr [rax], 0
0x180006223  mov     edi, [r14]
0x180006226  mov     [rbx+8], edi
0x180006229  mov     eax, [r14+4]
0x18000622d  mov     [rbx+0Ch], eax
0x180006230  test    r15d, r15d
0x180006233  jz      short loc_18000629B
0x180006235  sub     ecx, 1
0x180006238  jz      short loc_180006292
0x18000623a  sub     ecx, 1
0x18000623d  jz      short loc_18000624D
0x18000623f  cmp     ecx, 1
0x180006242  jnz     short loc_1800062A4
0x180006244  mov     ecx, edi; this
0x180006246  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000624b  jmp     short loc_1800062A2
0x18000624d  test    edi, edi
0x18000624f  js      short loc_180006289
0x180006251  mov     rax, [rsp+78h+arg_28]
0x180006259  mov     edi, 8007029Ch
0x18000625e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180006262  mov     rcx, r10; int
0x180006265  mov     [rsp+78h+var_50], rax; __int64
0x18000626a  mov     rax, [rsp+78h+arg_20]
0x180006272  mov     [rsp+78h+var_58], rax; __int64
0x180006277  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000627c  mov     ecx, edi; this
0x18000627e  mov     [rbx+8], edi
0x180006281  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006286  mov     [rbx+0Ch], eax
0x180006289  mov     ecx, edi; this
0x18000628b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180006290  jmp     short loc_1800062A2
0x180006292  mov     ecx, edi; this
0x180006294  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180006299  jmp     short loc_1800062A2
0x18000629b  mov     ecx, edi; this
0x18000629d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800062a2  mov     ebp, eax
0x1800062a4  mov     eax, [rsp+78h+arg_70]
0x1800062ab  mov     [rbx+4], eax
0x1800062ae  mov     [rbx], r15d
0x1800062b1  cmp     dword ptr [r14+8], 1
0x1800062b6  jnz     short loc_1800062BE
0x1800062b8  or      eax, 8
0x1800062bb  mov     [rbx+4], eax
0x1800062be  mov     eax, 1
0x1800062c3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800062cb  inc     eax
0x1800062cd  xor     edi, edi
0x1800062cf  mov     [rbx+10h], eax
0x1800062d2  mov     rax, [rsp+78h+arg_40]
0x1800062da  test    rax, rax
0x1800062dd  jz      short loc_1800062E4
0x1800062df  cmp     [rax], di
0x1800062e2  jnz     short loc_1800062E7
0x1800062e4  mov     rax, rdi
0x1800062e7  mov     [rbx+18h], rax
0x1800062eb  call    cs:__imp_GetCurrentThreadId
0x1800062f1  mov     [rbx+38h], r13
0x1800062f5  xorps   xmm0, xmm0
0x1800062f8  mov     [rbx+20h], eax
0x1800062fb  mov     eax, [rsp+78h+arg_8]
0x180006302  mov     [rbx+40h], eax
0x180006305  mov     rax, [rsp+78h+arg_20]
0x18000630d  mov     [rbx+28h], rax
0x180006311  mov     rax, [rsp+78h+arg_28]
0x180006319  mov     [rbx+88h], rax
0x180006320  mov     rax, [rsp+78h+arg_0]
0x180006328  mov     [rbx+90h], rax
0x18000632f  xor     eax, eax
0x180006331  mov     [rbx+44h], ebp
0x180006334  mov     [rbx+30h], r12
0x180006338  mov     [rbx+48h], rdi
0x18000633c  movups  xmmword ptr [rbx+68h], xmm0
0x180006340  mov     [rbx+78h], rax
0x180006344  movups  xmmword ptr [rbx+50h], xmm0
0x180006348  mov     [rbx+60h], rax
0x18000634c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180006353  test    rax, rax
0x180006356  jz      short loc_18000635F
0x180006358  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000635d  jmp     short loc_180006362
0x18000635f  mov     rax, rdi
0x180006362  mov     [rbx+80h], rax
0x180006369  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006370  test    rax, rax
0x180006373  jz      short loc_18000637D
0x180006375  mov     rcx, rbx
0x180006378  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000637d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006384  test    rax, rax
0x180006387  jz      short loc_18000639F
0x180006389  mov     rdx, [rsp+78h+arg_60]
0x180006391  mov     r8d, 400h
0x180006397  mov     rcx, rbx
0x18000639a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000639f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800063a6  test    rax, rax
0x1800063a9  jz      short loc_1800063B3
0x1800063ab  mov     rcx, rbx
0x1800063ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063b3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800063ba  test    rax, rax
0x1800063bd  jz      short loc_1800063CD
0x1800063bf  test    byte ptr [rbx+4], 2
0x1800063c3  jnz     short loc_1800063CD
0x1800063c5  mov     rcx, rbx
0x1800063c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063cd  cmp     [rbx+8], edi
0x1800063d0  jl      short loc_1800063EC
0x1800063d2  cmp     r15d, 3
0x1800063d6  jnz     loc_1800064BA
0x1800063dc  mov     ecx, 8000FFFFh; this
0x1800063e1  mov     [rbx+8], ecx
0x1800063e4  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800063e9  mov     [rbx+0Ch], eax
0x1800063ec  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800063f3  jnz     short loc_180006414
0x1800063f5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800063fc  test    rax, rax
0x1800063ff  jz      short loc_18000640A
0x180006401  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006406  test    al, al
0x180006408  jmp     short loc_180006412
0x18000640a  call    cs:__imp_IsDebuggerPresent
0x180006410  test    eax, eax
0x180006412  jz      short loc_18000641A
0x180006414  test    byte ptr [rbx+4], 2
0x180006418  jz      short loc_18000643E
0x18000641a  mov     rax, cs:g_pfnResultLoggingCallback
0x180006421  test    rax, rax
0x180006424  jz      short loc_180006482
0x180006426  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000642d  jnz     short loc_180006482
0x18000642f  xor     r8d, r8d
0x180006432  xor     edx, edx
0x180006434  mov     rcx, rbx
0x180006437  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000643c  jmp     short loc_180006482
0x18000643e  mov     rax, cs:g_pfnResultLoggingCallback
0x180006445  mov     ebp, 800h
0x18000644a  test    rax, rax
0x18000644d  jz      short loc_180006466
0x18000644f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006456  jnz     short loc_180006466
0x180006458  mov     r8d, ebp
0x18000645b  mov     rdx, rsi
0x18000645e  mov     rcx, rbx
0x180006461  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006466  cmp     [rsi], di
0x180006469  jnz     short loc_180006479
0x18000646b  mov     r8, rbx; unsigned __int64
0x18000646e  mov     rdx, rbp; unsigned __int16 *
0x180006471  mov     rcx, rsi; this
0x180006474  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180006479  mov     rcx, rsi; lpOutputString
0x18000647c  call    cs:__imp_OutputDebugStringW
0x180006482  test    byte ptr [rbx+4], 4
0x180006486  jnz     short loc_180006491
0x180006488  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000648f  jz      short loc_1800064A2
0x180006491  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006498  test    rax, rax
0x18000649b  jz      short loc_1800064A2
0x18000649d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064a2  mov     rbx, [rsp+78h+arg_10]
0x1800064aa  add     rsp, 40h
0x1800064ae  pop     r15
0x1800064b0  pop     r14
0x1800064b2  pop     r13
0x1800064b4  pop     r12
0x1800064b6  pop     rdi
0x1800064b7  pop     rsi
0x1800064b8  pop     rbp
0x1800064b9  retn
0x1800064ba  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
