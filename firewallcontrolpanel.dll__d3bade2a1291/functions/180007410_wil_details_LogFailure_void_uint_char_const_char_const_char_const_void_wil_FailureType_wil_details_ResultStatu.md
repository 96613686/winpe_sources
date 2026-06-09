# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180007410`
- end: `0x18000770c`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `764`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180005b64`
- `0x180005ee0`

## callees

- `0x180005ab0`
- `0x180006a24`
- `0x180007240`
- `0x180007410`
- `0x180007a1c`
- `0x180007a40`
- `0x180007a54`
- `0x180007a70`
- `0x18000875c`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007531`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007531`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007654`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007654`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800076c7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800076c7`

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
  __int64 (__fastcall *ModuleName)(_QWORD); // rax
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
  ModuleName = wil::details::g_pfnGetModuleName;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = (__int64 (__fastcall *)(_QWORD))wil::details::g_pfnGetModuleName(v24);
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
0x180007410  mov     [rsp+arg_10], rbx
0x180007415  mov     [rsp+arg_8], edx
0x180007419  mov     [rsp+arg_0], rcx
0x18000741e  push    rbp
0x18000741f  push    rsi
0x180007420  push    rdi
0x180007421  push    r12
0x180007423  push    r13
0x180007425  push    r14
0x180007427  push    r15
0x180007429  sub     rsp, 40h
0x18000742d  mov     r12, r9
0x180007430  mov     r13, r8
0x180007433  mov     r10, rcx
0x180007436  xor     eax, eax
0x180007438  mov     rsi, [rsp+78h+lpOutputString]
0x180007440  mov     [rsi], ax
0x180007443  mov     rax, [rsp+78h+arg_60]
0x18000744b  mov     byte ptr [rax], 0
0x18000744e  mov     r14, [rsp+78h+arg_38]
0x180007456  mov     edi, [r14]
0x180007459  mov     rbx, [rsp+78h+arg_78]
0x180007461  mov     [rbx+8], edi
0x180007464  mov     eax, [r14+4]
0x180007468  mov     [rbx+0Ch], eax
0x18000746b  xor     ebp, ebp
0x18000746d  mov     r15d, [rsp+78h+arg_30]
0x180007475  mov     ecx, r15d
0x180007478  test    r15d, r15d
0x18000747b  jz      short loc_1800074E3
0x18000747d  sub     ecx, 1
0x180007480  jz      short loc_1800074DA
0x180007482  sub     ecx, 1
0x180007485  jz      short loc_180007495
0x180007487  cmp     ecx, 1
0x18000748a  jnz     short loc_1800074EC
0x18000748c  mov     ecx, edi; this
0x18000748e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180007493  jmp     short loc_1800074EA
0x180007495  test    edi, edi
0x180007497  js      short loc_1800074D1
0x180007499  mov     edi, 8007029Ch
0x18000749e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800074a2  mov     rax, [rsp+78h+arg_28]
0x1800074aa  mov     [rsp+78h+var_50], rax; __int64
0x1800074af  mov     rax, [rsp+78h+arg_20]
0x1800074b7  mov     [rsp+78h+var_58], rax; __int64
0x1800074bc  mov     rcx, r10; int
0x1800074bf  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800074c4  mov     [rbx+8], edi
0x1800074c7  mov     ecx, edi; this
0x1800074c9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800074ce  mov     [rbx+0Ch], eax
0x1800074d1  mov     ecx, edi; this
0x1800074d3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800074d8  jmp     short loc_1800074EA
0x1800074da  mov     ecx, edi; this
0x1800074dc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800074e1  jmp     short loc_1800074EA
0x1800074e3  mov     ecx, edi; this
0x1800074e5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800074ea  mov     ebp, eax
0x1800074ec  mov     [rbx], r15d
0x1800074ef  mov     eax, [rsp+78h+arg_70]
0x1800074f6  mov     [rbx+4], eax
0x1800074f9  cmp     dword ptr [r14+8], 1
0x1800074fe  jnz     short loc_180007506
0x180007500  or      eax, 8
0x180007503  mov     [rbx+4], eax
0x180007506  mov     eax, 1
0x18000750b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180007513  inc     eax
0x180007515  mov     [rbx+10h], eax
0x180007518  mov     rax, [rsp+78h+arg_40]
0x180007520  test    rax, rax
0x180007523  jz      short loc_18000752B
0x180007525  cmp     word ptr [rax], 0
0x180007529  jnz     short loc_18000752D
0x18000752b  xor     eax, eax
0x18000752d  mov     [rbx+18h], rax
0x180007531  call    cs:__imp_GetCurrentThreadId
0x180007537  mov     [rbx+20h], eax
0x18000753a  mov     [rbx+38h], r13
0x18000753e  mov     eax, [rsp+78h+arg_8]
0x180007545  mov     [rbx+40h], eax
0x180007548  mov     [rbx+44h], ebp
0x18000754b  mov     rax, [rsp+78h+arg_20]
0x180007553  mov     [rbx+28h], rax
0x180007557  mov     [rbx+30h], r12
0x18000755b  mov     rax, [rsp+78h+arg_28]
0x180007563  mov     [rbx+88h], rax
0x18000756a  mov     rax, [rsp+78h+arg_0]
0x180007572  mov     [rbx+90h], rax
0x180007579  mov     qword ptr [rbx+48h], 0
0x180007581  xorps   xmm0, xmm0
0x180007584  xor     eax, eax
0x180007586  movups  xmmword ptr [rbx+68h], xmm0
0x18000758a  mov     [rbx+78h], rax
0x18000758e  movups  xmmword ptr [rbx+50h], xmm0
0x180007592  mov     [rbx+60h], rax
0x180007596  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000759d  test    rax, rax
0x1800075a0  jz      short loc_1800075A7
0x1800075a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075a7  mov     [rbx+80h], rax
0x1800075ae  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800075b5  test    rax, rax
0x1800075b8  jz      short loc_1800075C2
0x1800075ba  mov     rcx, rbx
0x1800075bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075c2  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800075c9  test    rax, rax
0x1800075cc  jz      short loc_1800075E4
0x1800075ce  mov     r8d, 400h
0x1800075d4  mov     rdx, [rsp+78h+arg_60]
0x1800075dc  mov     rcx, rbx
0x1800075df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075e4  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800075eb  test    rax, rax
0x1800075ee  jz      short loc_1800075F8
0x1800075f0  mov     rcx, rbx
0x1800075f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075f8  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800075ff  test    rax, rax
0x180007602  jz      short loc_180007612
0x180007604  test    byte ptr [rbx+4], 2
0x180007608  jnz     short loc_180007612
0x18000760a  mov     rcx, rbx
0x18000760d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007612  cmp     dword ptr [rbx+8], 0
0x180007616  jl      short loc_180007636
0x180007618  cmp     r15d, 3
0x18000761c  jnz     loc_180007706
0x180007622  mov     dword ptr [rbx+8], 8000FFFFh
0x180007629  mov     ecx, 8000FFFFh; this
0x18000762e  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007633  mov     [rbx+0Ch], eax
0x180007636  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, 0; bool wil::g_fIsDebuggerPresent
0x18000763d  jnz     short loc_18000765E
0x18000763f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180007646  test    rax, rax
0x180007649  jz      short loc_180007654
0x18000764b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007650  test    al, al
0x180007652  jmp     short loc_18000765C
0x180007654  call    cs:__imp_IsDebuggerPresent
0x18000765a  test    eax, eax
0x18000765c  jz      short loc_180007664
0x18000765e  test    byte ptr [rbx+4], 2
0x180007662  jz      short loc_180007688
0x180007664  mov     rax, cs:g_pfnResultLoggingCallback
0x18000766b  test    rax, rax
0x18000766e  jz      short loc_1800076CD
0x180007670  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x180007677  jnz     short loc_1800076CD
0x180007679  xor     r8d, r8d
0x18000767c  xor     edx, edx
0x18000767e  mov     rcx, rbx
0x180007681  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007686  jmp     short loc_1800076CD
0x180007688  mov     rax, cs:g_pfnResultLoggingCallback
0x18000768f  test    rax, rax
0x180007692  jz      short loc_1800076AE
0x180007694  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x18000769b  jnz     short loc_1800076AE
0x18000769d  mov     r8d, 800h
0x1800076a3  mov     rdx, rsi
0x1800076a6  mov     rcx, rbx
0x1800076a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076ae  cmp     word ptr [rsi], 0
0x1800076b2  jnz     short loc_1800076C4
0x1800076b4  mov     r8, rbx; unsigned __int64
0x1800076b7  mov     edx, 800h; unsigned __int16 *
0x1800076bc  mov     rcx, rsi; this
0x1800076bf  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800076c4  mov     rcx, rsi; lpOutputString
0x1800076c7  call    cs:__imp_OutputDebugStringW
0x1800076cd  test    byte ptr [rbx+4], 4
0x1800076d1  jnz     short loc_1800076DC
0x1800076d3  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, 0; bool wil::g_fBreakOnFailure
0x1800076da  jz      short loc_1800076EE
0x1800076dc  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800076e3  test    rax, rax
0x1800076e6  jz      short loc_1800076EE
0x1800076e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076ed  nop
0x1800076ee  mov     rbx, [rsp+78h+arg_10]
0x1800076f6  add     rsp, 40h
0x1800076fa  pop     r15
0x1800076fc  pop     r14
0x1800076fe  pop     r13
0x180007700  pop     r12
0x180007702  pop     rdi
0x180007703  pop     rsi
0x180007704  pop     rbp
0x180007705  retn
0x180007706  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
