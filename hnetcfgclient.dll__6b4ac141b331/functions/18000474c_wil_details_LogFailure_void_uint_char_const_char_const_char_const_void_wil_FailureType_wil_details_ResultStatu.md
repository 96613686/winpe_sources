# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000474c`
- end: `0x180004a45`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180002e9c`
- `0x1800031e8`
- `0x18002523c`

## callees

- `0x180002ddc`
- `0x180003db4`
- `0x180004588`
- `0x18000474c`
- `0x180004e14`
- `0x180004e30`
- `0x180004e44`
- `0x180004e60`
- `0x180005ca0`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000486f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000486f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004a00`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004a00`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000498e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000498e`

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
0x18000474c  mov     [rsp+arg_10], rbx
0x180004751  mov     [rsp+arg_8], edx
0x180004755  mov     [rsp+arg_0], rcx
0x18000475a  push    rbp
0x18000475b  push    rsi
0x18000475c  push    rdi
0x18000475d  push    r12
0x18000475f  push    r13
0x180004761  push    r14
0x180004763  push    r15
0x180004765  sub     rsp, 40h
0x180004769  mov     r12, r9
0x18000476c  mov     r13, r8
0x18000476f  mov     r10, rcx
0x180004772  xor     eax, eax
0x180004774  mov     rsi, [rsp+78h+lpOutputString]
0x18000477c  mov     [rsi], ax
0x18000477f  mov     rax, [rsp+78h+arg_60]
0x180004787  mov     byte ptr [rax], 0
0x18000478a  mov     r14, [rsp+78h+arg_38]
0x180004792  mov     edi, [r14]
0x180004795  mov     rbx, [rsp+78h+arg_78]
0x18000479d  mov     [rbx+8], edi
0x1800047a0  mov     eax, [r14+4]
0x1800047a4  mov     [rbx+0Ch], eax
0x1800047a7  xor     ebp, ebp
0x1800047a9  mov     r15d, [rsp+78h+arg_30]
0x1800047b1  mov     ecx, r15d
0x1800047b4  test    r15d, r15d
0x1800047b7  jz      short loc_18000481F
0x1800047b9  sub     ecx, 1
0x1800047bc  jz      short loc_180004816
0x1800047be  sub     ecx, 1
0x1800047c1  jz      short loc_1800047D1
0x1800047c3  cmp     ecx, 1
0x1800047c6  jnz     short loc_180004828
0x1800047c8  mov     ecx, edi; this
0x1800047ca  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800047cf  jmp     short loc_180004826
0x1800047d1  test    edi, edi
0x1800047d3  js      short loc_18000480D
0x1800047d5  mov     edi, 8007029Ch
0x1800047da  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800047de  mov     rax, [rsp+78h+arg_28]
0x1800047e6  mov     [rsp+78h+var_50], rax; __int64
0x1800047eb  mov     rax, [rsp+78h+arg_20]
0x1800047f3  mov     [rsp+78h+var_58], rax; __int64
0x1800047f8  mov     rcx, r10; int
0x1800047fb  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180004800  mov     [rbx+8], edi
0x180004803  mov     ecx, edi; this
0x180004805  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000480a  mov     [rbx+0Ch], eax
0x18000480d  mov     ecx, edi; this
0x18000480f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180004814  jmp     short loc_180004826
0x180004816  mov     ecx, edi; this
0x180004818  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000481d  jmp     short loc_180004826
0x18000481f  mov     ecx, edi; this
0x180004821  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180004826  mov     ebp, eax
0x180004828  mov     [rbx], r15d
0x18000482b  mov     eax, [rsp+78h+arg_70]
0x180004832  mov     [rbx+4], eax
0x180004835  cmp     dword ptr [r14+8], 1
0x18000483a  jnz     short loc_180004842
0x18000483c  or      eax, 8
0x18000483f  mov     [rbx+4], eax
0x180004842  mov     eax, 1
0x180004847  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000484f  inc     eax
0x180004851  mov     [rbx+10h], eax
0x180004854  mov     rax, [rsp+78h+arg_40]
0x18000485c  xor     edi, edi
0x18000485e  test    rax, rax
0x180004861  jz      short loc_180004868
0x180004863  cmp     [rax], di
0x180004866  jnz     short loc_18000486B
0x180004868  mov     rax, rdi
0x18000486b  mov     [rbx+18h], rax
0x18000486f  call    cs:__imp_GetCurrentThreadId
0x180004875  mov     [rbx+20h], eax
0x180004878  mov     [rbx+38h], r13
0x18000487c  mov     eax, [rsp+78h+arg_8]
0x180004883  mov     [rbx+40h], eax
0x180004886  mov     [rbx+44h], ebp
0x180004889  mov     rax, [rsp+78h+arg_20]
0x180004891  mov     [rbx+28h], rax
0x180004895  mov     [rbx+30h], r12
0x180004899  mov     rax, [rsp+78h+arg_28]
0x1800048a1  mov     [rbx+88h], rax
0x1800048a8  mov     rax, [rsp+78h+arg_0]
0x1800048b0  mov     [rbx+90h], rax
0x1800048b7  mov     [rbx+48h], rdi
0x1800048bb  xorps   xmm0, xmm0
0x1800048be  xor     eax, eax
0x1800048c0  movups  xmmword ptr [rbx+68h], xmm0
0x1800048c4  mov     [rbx+78h], rax
0x1800048c8  movups  xmmword ptr [rbx+50h], xmm0
0x1800048cc  mov     [rbx+60h], rax
0x1800048d0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800048d7  test    rax, rax
0x1800048da  jz      short loc_1800048E3
0x1800048dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048e1  jmp     short loc_1800048E6
0x1800048e3  mov     rax, rdi
0x1800048e6  mov     [rbx+80h], rax
0x1800048ed  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800048f4  test    rax, rax
0x1800048f7  jz      short loc_180004901
0x1800048f9  mov     rcx, rbx
0x1800048fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004901  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004908  test    rax, rax
0x18000490b  jz      short loc_180004923
0x18000490d  mov     r8d, 400h
0x180004913  mov     rdx, [rsp+78h+arg_60]
0x18000491b  mov     rcx, rbx
0x18000491e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004923  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000492a  test    rax, rax
0x18000492d  jz      short loc_180004937
0x18000492f  mov     rcx, rbx
0x180004932  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004937  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000493e  test    rax, rax
0x180004941  jz      short loc_180004951
0x180004943  test    byte ptr [rbx+4], 2
0x180004947  jnz     short loc_180004951
0x180004949  mov     rcx, rbx
0x18000494c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004951  cmp     [rbx+8], edi
0x180004954  jl      short loc_180004970
0x180004956  cmp     r15d, 3
0x18000495a  jnz     loc_180004A3F
0x180004960  mov     ecx, 8000FFFFh; this
0x180004965  mov     [rbx+8], ecx
0x180004968  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000496d  mov     [rbx+0Ch], eax
0x180004970  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180004977  jnz     short loc_180004998
0x180004979  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004980  test    rax, rax
0x180004983  jz      short loc_18000498E
0x180004985  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000498a  test    al, al
0x18000498c  jmp     short loc_180004996
0x18000498e  call    cs:__imp_IsDebuggerPresent
0x180004994  test    eax, eax
0x180004996  jz      short loc_18000499E
0x180004998  test    byte ptr [rbx+4], 2
0x18000499c  jz      short loc_1800049C2
0x18000499e  mov     rax, cs:g_pfnResultLoggingCallback
0x1800049a5  test    rax, rax
0x1800049a8  jz      short loc_180004A06
0x1800049aa  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800049b1  jnz     short loc_180004A06
0x1800049b3  xor     r8d, r8d
0x1800049b6  xor     edx, edx
0x1800049b8  mov     rcx, rbx
0x1800049bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049c0  jmp     short loc_180004A06
0x1800049c2  mov     ebp, 800h
0x1800049c7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800049ce  test    rax, rax
0x1800049d1  jz      short loc_1800049EA
0x1800049d3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800049da  jnz     short loc_1800049EA
0x1800049dc  mov     r8d, ebp
0x1800049df  mov     rdx, rsi
0x1800049e2  mov     rcx, rbx
0x1800049e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049ea  cmp     [rsi], di
0x1800049ed  jnz     short loc_1800049FD
0x1800049ef  mov     r8, rbx; unsigned __int64
0x1800049f2  mov     rdx, rbp; unsigned __int16 *
0x1800049f5  mov     rcx, rsi; this
0x1800049f8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800049fd  mov     rcx, rsi; lpOutputString
0x180004a00  call    cs:__imp_OutputDebugStringW
0x180004a06  test    byte ptr [rbx+4], 4
0x180004a0a  jnz     short loc_180004A15
0x180004a0c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180004a13  jz      short loc_180004A27
0x180004a15  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004a1c  test    rax, rax
0x180004a1f  jz      short loc_180004A27
0x180004a21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a26  nop
0x180004a27  mov     rbx, [rsp+78h+arg_10]
0x180004a2f  add     rsp, 40h
0x180004a33  pop     r15
0x180004a35  pop     r14
0x180004a37  pop     r13
0x180004a39  pop     r12
0x180004a3b  pop     rdi
0x180004a3c  pop     rsi
0x180004a3d  pop     rbp
0x180004a3e  retn
0x180004a3f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
