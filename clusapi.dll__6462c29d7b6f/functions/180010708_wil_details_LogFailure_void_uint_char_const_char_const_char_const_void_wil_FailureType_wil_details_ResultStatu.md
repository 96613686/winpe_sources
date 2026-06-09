# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180010708`
- end: `0x180010a01`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18000e208`
- `0x18000e554`

## callees

- `0x18000e148`
- `0x18000fba4`
- `0x180010410`
- `0x180010708`
- `0x180011398`
- `0x1800113c0`
- `0x180011510`
- `0x18001152c`
- `0x180012e14`
- `0x1800b5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001082b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001082b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001094a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001094a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800109bc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800109bc`

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
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v25);
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
0x180010708  mov     [rsp+arg_10], rbx
0x18001070d  mov     [rsp+arg_8], edx
0x180010711  mov     [rsp+arg_0], rcx
0x180010716  push    rbp
0x180010717  push    rsi
0x180010718  push    rdi
0x180010719  push    r12
0x18001071b  push    r13
0x18001071d  push    r14
0x18001071f  push    r15
0x180010721  sub     rsp, 40h
0x180010725  mov     r12, r9
0x180010728  mov     r13, r8
0x18001072b  mov     r10, rcx
0x18001072e  xor     eax, eax
0x180010730  mov     rsi, [rsp+78h+lpOutputString]
0x180010738  mov     [rsi], ax
0x18001073b  mov     rax, [rsp+78h+arg_60]
0x180010743  mov     byte ptr [rax], 0
0x180010746  mov     r14, [rsp+78h+arg_38]
0x18001074e  mov     edi, [r14]
0x180010751  mov     rbx, [rsp+78h+arg_78]
0x180010759  mov     [rbx+8], edi
0x18001075c  mov     eax, [r14+4]
0x180010760  mov     [rbx+0Ch], eax
0x180010763  xor     ebp, ebp
0x180010765  mov     r15d, [rsp+78h+arg_30]
0x18001076d  mov     ecx, r15d
0x180010770  test    r15d, r15d
0x180010773  jz      short loc_1800107DB
0x180010775  sub     ecx, 1
0x180010778  jz      short loc_1800107D2
0x18001077a  sub     ecx, 1
0x18001077d  jz      short loc_18001078D
0x18001077f  cmp     ecx, 1
0x180010782  jnz     short loc_1800107E4
0x180010784  mov     ecx, edi; this
0x180010786  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18001078b  jmp     short loc_1800107E2
0x18001078d  test    edi, edi
0x18001078f  js      short loc_1800107C9
0x180010791  mov     edi, 8007029Ch
0x180010796  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18001079a  mov     rax, [rsp+78h+arg_28]
0x1800107a2  mov     [rsp+78h+var_50], rax; __int64
0x1800107a7  mov     rax, [rsp+78h+arg_20]
0x1800107af  mov     [rsp+78h+var_58], rax; __int64
0x1800107b4  mov     rcx, r10; int
0x1800107b7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800107bc  mov     [rbx+8], edi
0x1800107bf  mov     ecx, edi; this
0x1800107c1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800107c6  mov     [rbx+0Ch], eax
0x1800107c9  mov     ecx, edi; this
0x1800107cb  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800107d0  jmp     short loc_1800107E2
0x1800107d2  mov     ecx, edi; this
0x1800107d4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800107d9  jmp     short loc_1800107E2
0x1800107db  mov     ecx, edi; this
0x1800107dd  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800107e2  mov     ebp, eax
0x1800107e4  mov     [rbx], r15d
0x1800107e7  mov     eax, [rsp+78h+arg_70]
0x1800107ee  mov     [rbx+4], eax
0x1800107f1  cmp     dword ptr [r14+8], 1
0x1800107f6  jnz     short loc_1800107FE
0x1800107f8  or      eax, 8
0x1800107fb  mov     [rbx+4], eax
0x1800107fe  mov     eax, 1
0x180010803  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18001080b  inc     eax
0x18001080d  mov     [rbx+10h], eax
0x180010810  mov     rax, [rsp+78h+arg_40]
0x180010818  xor     edi, edi
0x18001081a  test    rax, rax
0x18001081d  jz      short loc_180010824
0x18001081f  cmp     [rax], di
0x180010822  jnz     short loc_180010827
0x180010824  mov     rax, rdi
0x180010827  mov     [rbx+18h], rax
0x18001082b  call    cs:__imp_GetCurrentThreadId
0x180010831  mov     [rbx+20h], eax
0x180010834  mov     [rbx+38h], r13
0x180010838  mov     eax, [rsp+78h+arg_8]
0x18001083f  mov     [rbx+40h], eax
0x180010842  mov     [rbx+44h], ebp
0x180010845  mov     rax, [rsp+78h+arg_20]
0x18001084d  mov     [rbx+28h], rax
0x180010851  mov     [rbx+30h], r12
0x180010855  mov     rax, [rsp+78h+arg_28]
0x18001085d  mov     [rbx+88h], rax
0x180010864  mov     rax, [rsp+78h+arg_0]
0x18001086c  mov     [rbx+90h], rax
0x180010873  mov     [rbx+48h], rdi
0x180010877  xorps   xmm0, xmm0
0x18001087a  xor     eax, eax
0x18001087c  movups  xmmword ptr [rbx+68h], xmm0
0x180010880  mov     [rbx+78h], rax
0x180010884  movups  xmmword ptr [rbx+50h], xmm0
0x180010888  mov     [rbx+60h], rax
0x18001088c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180010893  test    rax, rax
0x180010896  jz      short loc_18001089F
0x180010898  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001089d  jmp     short loc_1800108A2
0x18001089f  mov     rax, rdi
0x1800108a2  mov     [rbx+80h], rax
0x1800108a9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800108b0  test    rax, rax
0x1800108b3  jz      short loc_1800108BD
0x1800108b5  mov     rcx, rbx
0x1800108b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108bd  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800108c4  test    rax, rax
0x1800108c7  jz      short loc_1800108DF
0x1800108c9  mov     r8d, 400h
0x1800108cf  mov     rdx, [rsp+78h+arg_60]
0x1800108d7  mov     rcx, rbx
0x1800108da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108df  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800108e6  test    rax, rax
0x1800108e9  jz      short loc_1800108F3
0x1800108eb  mov     rcx, rbx
0x1800108ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108f3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800108fa  test    rax, rax
0x1800108fd  jz      short loc_18001090D
0x1800108ff  test    byte ptr [rbx+4], 2
0x180010903  jnz     short loc_18001090D
0x180010905  mov     rcx, rbx
0x180010908  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001090d  cmp     [rbx+8], edi
0x180010910  jl      short loc_18001092C
0x180010912  cmp     r15d, 3
0x180010916  jnz     loc_1800109FB
0x18001091c  mov     ecx, 8000FFFFh; this
0x180010921  mov     [rbx+8], ecx
0x180010924  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180010929  mov     [rbx+0Ch], eax
0x18001092c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180010933  jnz     short loc_180010954
0x180010935  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001093c  test    rax, rax
0x18001093f  jz      short loc_18001094A
0x180010941  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010946  test    al, al
0x180010948  jmp     short loc_180010952
0x18001094a  call    cs:__imp_IsDebuggerPresent
0x180010950  test    eax, eax
0x180010952  jz      short loc_18001095A
0x180010954  test    byte ptr [rbx+4], 2
0x180010958  jz      short loc_18001097E
0x18001095a  mov     rax, cs:g_pfnResultLoggingCallback
0x180010961  test    rax, rax
0x180010964  jz      short loc_1800109C2
0x180010966  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001096d  jnz     short loc_1800109C2
0x18001096f  xor     r8d, r8d
0x180010972  xor     edx, edx
0x180010974  mov     rcx, rbx
0x180010977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001097c  jmp     short loc_1800109C2
0x18001097e  mov     ebp, 800h
0x180010983  mov     rax, cs:g_pfnResultLoggingCallback
0x18001098a  test    rax, rax
0x18001098d  jz      short loc_1800109A6
0x18001098f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180010996  jnz     short loc_1800109A6
0x180010998  mov     r8d, ebp
0x18001099b  mov     rdx, rsi
0x18001099e  mov     rcx, rbx
0x1800109a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109a6  cmp     [rsi], di
0x1800109a9  jnz     short loc_1800109B9
0x1800109ab  mov     r8, rbx; unsigned __int64
0x1800109ae  mov     rdx, rbp; wchar_t *
0x1800109b1  mov     rcx, rsi; this
0x1800109b4  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1800109b9  mov     rcx, rsi; lpOutputString
0x1800109bc  call    cs:__imp_OutputDebugStringW
0x1800109c2  test    byte ptr [rbx+4], 4
0x1800109c6  jnz     short loc_1800109D1
0x1800109c8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800109cf  jz      short loc_1800109E3
0x1800109d1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800109d8  test    rax, rax
0x1800109db  jz      short loc_1800109E3
0x1800109dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109e2  nop
0x1800109e3  mov     rbx, [rsp+78h+arg_10]
0x1800109eb  add     rsp, 40h
0x1800109ef  pop     r15
0x1800109f1  pop     r14
0x1800109f3  pop     r13
0x1800109f5  pop     r12
0x1800109f7  pop     rdi
0x1800109f8  pop     rsi
0x1800109f9  pop     rbp
0x1800109fa  retn
0x1800109fb  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
