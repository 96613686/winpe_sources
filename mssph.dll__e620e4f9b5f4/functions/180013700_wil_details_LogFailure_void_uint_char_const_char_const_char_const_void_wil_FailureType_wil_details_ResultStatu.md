# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180013700`
- end: `0x1800139fd`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `765`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x18000cce0`
- `0x18001174c`
- `0x180011ab8`

## callees

- `0x18000c8c0`
- `0x180011684`
- `0x180012da4`
- `0x180013700`
- `0x1800140f0`
- `0x180014110`
- `0x1800141cc`
- `0x1800141e8`
- `0x18001566c`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013827`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013827`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180013946`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180013946`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800139b8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800139b8`

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
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v25);
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
0x180013700  mov     [rsp+arg_10], rbx
0x180013705  mov     [rsp+arg_8], edx
0x180013709  mov     [rsp+arg_0], rcx
0x18001370e  push    rbp
0x18001370f  push    rsi
0x180013710  push    rdi
0x180013711  push    r12
0x180013713  push    r13
0x180013715  push    r14
0x180013717  push    r15
0x180013719  sub     rsp, 40h
0x18001371d  mov     r12, r9
0x180013720  mov     r13, r8
0x180013723  mov     r10, rcx
0x180013726  xor     eax, eax
0x180013728  mov     rsi, [rsp+78h+lpOutputString]
0x180013730  mov     [rsi], ax
0x180013733  mov     rax, [rsp+78h+arg_60]
0x18001373b  mov     byte ptr [rax], 0
0x18001373e  mov     r14, [rsp+78h+arg_38]
0x180013746  mov     edi, [r14]
0x180013749  mov     rbx, [rsp+78h+arg_78]
0x180013751  mov     [rbx+8], edi
0x180013754  mov     eax, [r14+4]
0x180013758  mov     [rbx+0Ch], eax
0x18001375b  xor     ebp, ebp
0x18001375d  mov     r15d, [rsp+78h+arg_30]
0x180013765  mov     ecx, r15d
0x180013768  test    r15d, r15d
0x18001376b  jz      short loc_1800137D7
0x18001376d  sub     ecx, 1
0x180013770  jz      short loc_1800137CE
0x180013772  sub     ecx, 1
0x180013775  jz      short loc_180013785
0x180013777  cmp     ecx, 1
0x18001377a  jnz     short loc_1800137E0
0x18001377c  mov     ecx, edi; this
0x18001377e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180013783  jmp     short loc_1800137DE
0x180013785  test    edi, edi
0x180013787  js      short loc_1800137C5
0x180013789  mov     [rsp+78h+var_40], ebp
0x18001378d  mov     edi, 8007029Ch
0x180013792  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180013796  mov     rax, [rsp+78h+arg_28]
0x18001379e  mov     [rsp+78h+var_50], rax; __int64
0x1800137a3  mov     rax, [rsp+78h+arg_20]
0x1800137ab  mov     [rsp+78h+var_58], rax; __int64
0x1800137b0  mov     rcx, r10; int
0x1800137b3  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800137b8  mov     [rbx+8], edi
0x1800137bb  mov     ecx, edi; this
0x1800137bd  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800137c2  mov     [rbx+0Ch], eax
0x1800137c5  mov     ecx, edi; this
0x1800137c7  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800137cc  jmp     short loc_1800137DE
0x1800137ce  mov     ecx, edi; this
0x1800137d0  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800137d5  jmp     short loc_1800137DE
0x1800137d7  mov     ecx, edi; this
0x1800137d9  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800137de  mov     ebp, eax
0x1800137e0  mov     [rbx], r15d
0x1800137e3  mov     eax, [rsp+78h+arg_70]
0x1800137ea  mov     [rbx+4], eax
0x1800137ed  cmp     dword ptr [r14+8], 1
0x1800137f2  jnz     short loc_1800137FA
0x1800137f4  or      eax, 8
0x1800137f7  mov     [rbx+4], eax
0x1800137fa  mov     eax, 1
0x1800137ff  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180013807  inc     eax
0x180013809  mov     [rbx+10h], eax
0x18001380c  mov     rax, [rsp+78h+arg_40]
0x180013814  xor     edi, edi
0x180013816  test    rax, rax
0x180013819  jz      short loc_180013820
0x18001381b  cmp     [rax], di
0x18001381e  jnz     short loc_180013823
0x180013820  mov     rax, rdi
0x180013823  mov     [rbx+18h], rax
0x180013827  call    cs:__imp_GetCurrentThreadId
0x18001382d  mov     [rbx+20h], eax
0x180013830  mov     [rbx+38h], r13
0x180013834  mov     eax, [rsp+78h+arg_8]
0x18001383b  mov     [rbx+40h], eax
0x18001383e  mov     [rbx+44h], ebp
0x180013841  mov     rax, [rsp+78h+arg_20]
0x180013849  mov     [rbx+28h], rax
0x18001384d  mov     [rbx+30h], r12
0x180013851  mov     rax, [rsp+78h+arg_28]
0x180013859  mov     [rbx+88h], rax
0x180013860  mov     rax, [rsp+78h+arg_0]
0x180013868  mov     [rbx+90h], rax
0x18001386f  mov     [rbx+48h], rdi
0x180013873  xorps   xmm0, xmm0
0x180013876  xor     eax, eax
0x180013878  movups  xmmword ptr [rbx+68h], xmm0
0x18001387c  mov     [rbx+78h], rax
0x180013880  movups  xmmword ptr [rbx+50h], xmm0
0x180013884  mov     [rbx+60h], rax
0x180013888  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001388f  test    rax, rax
0x180013892  jz      short loc_18001389B
0x180013894  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013899  jmp     short loc_18001389E
0x18001389b  mov     rax, rdi
0x18001389e  mov     [rbx+80h], rax
0x1800138a5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800138ac  test    rax, rax
0x1800138af  jz      short loc_1800138B9
0x1800138b1  mov     rcx, rbx
0x1800138b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138b9  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800138c0  test    rax, rax
0x1800138c3  jz      short loc_1800138DB
0x1800138c5  mov     r8d, 400h
0x1800138cb  mov     rdx, [rsp+78h+arg_60]
0x1800138d3  mov     rcx, rbx
0x1800138d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138db  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800138e2  test    rax, rax
0x1800138e5  jz      short loc_1800138EF
0x1800138e7  mov     rcx, rbx
0x1800138ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138ef  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800138f6  test    rax, rax
0x1800138f9  jz      short loc_180013909
0x1800138fb  test    byte ptr [rbx+4], 2
0x1800138ff  jnz     short loc_180013909
0x180013901  mov     rcx, rbx
0x180013904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013909  cmp     [rbx+8], edi
0x18001390c  jl      short loc_180013928
0x18001390e  cmp     r15d, 3
0x180013912  jnz     loc_1800139F7
0x180013918  mov     ecx, 8000FFFFh; this
0x18001391d  mov     [rbx+8], ecx
0x180013920  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180013925  mov     [rbx+0Ch], eax
0x180013928  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18001392f  jnz     short loc_180013950
0x180013931  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180013938  test    rax, rax
0x18001393b  jz      short loc_180013946
0x18001393d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013942  test    al, al
0x180013944  jmp     short loc_18001394E
0x180013946  call    cs:__imp_IsDebuggerPresent
0x18001394c  test    eax, eax
0x18001394e  jz      short loc_180013956
0x180013950  test    byte ptr [rbx+4], 2
0x180013954  jz      short loc_18001397A
0x180013956  mov     rax, cs:g_pfnResultLoggingCallback
0x18001395d  test    rax, rax
0x180013960  jz      short loc_1800139BE
0x180013962  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180013969  jnz     short loc_1800139BE
0x18001396b  xor     r8d, r8d
0x18001396e  xor     edx, edx
0x180013970  mov     rcx, rbx
0x180013973  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013978  jmp     short loc_1800139BE
0x18001397a  mov     ebp, 800h
0x18001397f  mov     rax, cs:g_pfnResultLoggingCallback
0x180013986  test    rax, rax
0x180013989  jz      short loc_1800139A2
0x18001398b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180013992  jnz     short loc_1800139A2
0x180013994  mov     r8d, ebp
0x180013997  mov     rdx, rsi
0x18001399a  mov     rcx, rbx
0x18001399d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800139a2  cmp     [rsi], di
0x1800139a5  jnz     short loc_1800139B5
0x1800139a7  mov     r8, rbx; unsigned __int64
0x1800139aa  mov     rdx, rbp; wchar_t *
0x1800139ad  mov     rcx, rsi; this
0x1800139b0  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1800139b5  mov     rcx, rsi; lpOutputString
0x1800139b8  call    cs:__imp_OutputDebugStringW
0x1800139be  test    byte ptr [rbx+4], 4
0x1800139c2  jnz     short loc_1800139CD
0x1800139c4  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800139cb  jz      short loc_1800139DF
0x1800139cd  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800139d4  test    rax, rax
0x1800139d7  jz      short loc_1800139DF
0x1800139d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800139de  nop
0x1800139df  mov     rbx, [rsp+78h+arg_10]
0x1800139e7  add     rsp, 40h
0x1800139eb  pop     r15
0x1800139ed  pop     r14
0x1800139ef  pop     r13
0x1800139f1  pop     r12
0x1800139f3  pop     rdi
0x1800139f4  pop     rsi
0x1800139f5  pop     rbp
0x1800139f6  retn
0x1800139f7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
