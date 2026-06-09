# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180143488`
- end: `0x180143793`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `779`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18014100c`
- `0x180141360`

## callees

- `0x180138de4`
- `0x180140f4c`
- `0x180142a04`
- `0x180143488`
- `0x180144260`
- `0x180144280`
- `0x18014441c`
- `0x18014443c`
- `0x180145d40`
- `0x18027f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801435ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801435ab`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180143748`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180143748`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1801436d0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1801436d0`

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
        WCHAR *lpOutputString,
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
  *lpOutputString = 0;
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
    if ( !*lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v26);
    OutputDebugStringW(lpOutputString);
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
0x180143488  mov     [rsp+arg_10], rbx
0x18014348d  mov     [rsp+arg_8], edx
0x180143491  mov     [rsp+arg_0], rcx
0x180143496  push    rbp
0x180143497  push    rsi
0x180143498  push    rdi
0x180143499  push    r12
0x18014349b  push    r13
0x18014349d  push    r14
0x18014349f  push    r15
0x1801434a1  sub     rsp, 40h
0x1801434a5  mov     r14, [rsp+78h+arg_38]
0x1801434ad  xor     eax, eax
0x1801434af  mov     rbx, [rsp+78h+arg_78]
0x1801434b7  xor     ebp, ebp
0x1801434b9  mov     r15d, [rsp+78h+arg_30]
0x1801434c1  mov     r10, rcx
0x1801434c4  mov     rsi, [rsp+78h+lpOutputString]
0x1801434cc  mov     r12, r9
0x1801434cf  mov     r13, r8
0x1801434d2  mov     ecx, r15d
0x1801434d5  mov     [rsi], ax
0x1801434d8  mov     rax, [rsp+78h+arg_60]
0x1801434e0  mov     byte ptr [rax], 0
0x1801434e3  mov     edi, [r14]
0x1801434e6  mov     [rbx+8], edi
0x1801434e9  mov     eax, [r14+4]
0x1801434ed  mov     [rbx+0Ch], eax
0x1801434f0  test    r15d, r15d
0x1801434f3  jz      short loc_18014355B
0x1801434f5  sub     ecx, 1
0x1801434f8  jz      short loc_180143552
0x1801434fa  sub     ecx, 1
0x1801434fd  jz      short loc_18014350D
0x1801434ff  cmp     ecx, 1
0x180143502  jnz     short loc_180143564
0x180143504  mov     ecx, edi; this
0x180143506  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18014350b  jmp     short loc_180143562
0x18014350d  test    edi, edi
0x18014350f  js      short loc_180143549
0x180143511  mov     rax, [rsp+78h+arg_28]
0x180143519  mov     edi, 8007029Ch
0x18014351e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180143522  mov     rcx, r10; int
0x180143525  mov     [rsp+78h+var_50], rax; __int64
0x18014352a  mov     rax, [rsp+78h+arg_20]
0x180143532  mov     [rsp+78h+var_58], rax; __int64
0x180143537  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18014353c  mov     ecx, edi; this
0x18014353e  mov     [rbx+8], edi
0x180143541  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180143546  mov     [rbx+0Ch], eax
0x180143549  mov     ecx, edi; this
0x18014354b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180143550  jmp     short loc_180143562
0x180143552  mov     ecx, edi; this
0x180143554  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180143559  jmp     short loc_180143562
0x18014355b  mov     ecx, edi; this
0x18014355d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180143562  mov     ebp, eax
0x180143564  mov     eax, [rsp+78h+arg_70]
0x18014356b  mov     [rbx+4], eax
0x18014356e  mov     [rbx], r15d
0x180143571  cmp     dword ptr [r14+8], 1
0x180143576  jnz     short loc_18014357E
0x180143578  or      eax, 8
0x18014357b  mov     [rbx+4], eax
0x18014357e  mov     eax, 1
0x180143583  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18014358b  inc     eax
0x18014358d  xor     edi, edi
0x18014358f  mov     [rbx+10h], eax
0x180143592  mov     rax, [rsp+78h+arg_40]
0x18014359a  test    rax, rax
0x18014359d  jz      short loc_1801435A4
0x18014359f  cmp     [rax], di
0x1801435a2  jnz     short loc_1801435A7
0x1801435a4  mov     rax, rdi
0x1801435a7  mov     [rbx+18h], rax
0x1801435ab  call    cs:__imp_GetCurrentThreadId
0x1801435b2  nop     dword ptr [rax+rax+00h]
0x1801435b7  mov     [rbx+38h], r13
0x1801435bb  xorps   xmm0, xmm0
0x1801435be  mov     [rbx+20h], eax
0x1801435c1  mov     eax, [rsp+78h+arg_8]
0x1801435c8  mov     [rbx+40h], eax
0x1801435cb  mov     rax, [rsp+78h+arg_20]
0x1801435d3  mov     [rbx+28h], rax
0x1801435d7  mov     rax, [rsp+78h+arg_28]
0x1801435df  mov     [rbx+88h], rax
0x1801435e6  mov     rax, [rsp+78h+arg_0]
0x1801435ee  mov     [rbx+90h], rax
0x1801435f5  xor     eax, eax
0x1801435f7  mov     [rbx+44h], ebp
0x1801435fa  mov     [rbx+30h], r12
0x1801435fe  mov     [rbx+48h], rdi
0x180143602  movups  xmmword ptr [rbx+68h], xmm0
0x180143606  mov     [rbx+78h], rax
0x18014360a  movups  xmmword ptr [rbx+50h], xmm0
0x18014360e  mov     [rbx+60h], rax
0x180143612  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180143619  test    rax, rax
0x18014361c  jz      short loc_180143625
0x18014361e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180143623  jmp     short loc_180143628
0x180143625  mov     rax, rdi
0x180143628  mov     [rbx+80h], rax
0x18014362f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180143636  test    rax, rax
0x180143639  jz      short loc_180143643
0x18014363b  mov     rcx, rbx
0x18014363e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180143643  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18014364a  test    rax, rax
0x18014364d  jz      short loc_180143665
0x18014364f  mov     rdx, [rsp+78h+arg_60]
0x180143657  mov     r8d, 400h
0x18014365d  mov     rcx, rbx
0x180143660  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180143665  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18014366c  test    rax, rax
0x18014366f  jz      short loc_180143679
0x180143671  mov     rcx, rbx
0x180143674  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180143679  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180143680  test    rax, rax
0x180143683  jz      short loc_180143693
0x180143685  test    byte ptr [rbx+4], 2
0x180143689  jnz     short loc_180143693
0x18014368b  mov     rcx, rbx
0x18014368e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180143693  cmp     [rbx+8], edi
0x180143696  jl      short loc_1801436B2
0x180143698  cmp     r15d, 3
0x18014369c  jnz     loc_18014378D
0x1801436a2  mov     ecx, 8000FFFFh; this
0x1801436a7  mov     [rbx+8], ecx
0x1801436aa  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1801436af  mov     [rbx+0Ch], eax
0x1801436b2  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1801436b9  jnz     short loc_1801436E0
0x1801436bb  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1801436c2  test    rax, rax
0x1801436c5  jz      short loc_1801436D0
0x1801436c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801436cc  test    al, al
0x1801436ce  jmp     short loc_1801436DE
0x1801436d0  call    cs:__imp_IsDebuggerPresent
0x1801436d7  nop     dword ptr [rax+rax+00h]
0x1801436dc  test    eax, eax
0x1801436de  jz      short loc_1801436E6
0x1801436e0  test    byte ptr [rbx+4], 2
0x1801436e4  jz      short loc_18014370A
0x1801436e6  mov     rax, cs:g_pfnResultLoggingCallback
0x1801436ed  test    rax, rax
0x1801436f0  jz      short loc_180143754
0x1801436f2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1801436f9  jnz     short loc_180143754
0x1801436fb  xor     r8d, r8d
0x1801436fe  xor     edx, edx
0x180143700  mov     rcx, rbx
0x180143703  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180143708  jmp     short loc_180143754
0x18014370a  mov     rax, cs:g_pfnResultLoggingCallback
0x180143711  mov     ebp, 800h
0x180143716  test    rax, rax
0x180143719  jz      short loc_180143732
0x18014371b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180143722  jnz     short loc_180143732
0x180143724  mov     r8d, ebp
0x180143727  mov     rdx, rsi
0x18014372a  mov     rcx, rbx
0x18014372d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180143732  cmp     [rsi], di
0x180143735  jnz     short loc_180143745
0x180143737  mov     r8, rbx; unsigned __int64
0x18014373a  mov     rdx, rbp; unsigned __int16 *
0x18014373d  mov     rcx, rsi; pszDest
0x180143740  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180143745  mov     rcx, rsi; lpOutputString
0x180143748  call    cs:__imp_OutputDebugStringW
0x18014374f  nop     dword ptr [rax+rax+00h]
0x180143754  test    byte ptr [rbx+4], 4
0x180143758  jnz     short loc_180143763
0x18014375a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180143761  jz      short loc_180143774
0x180143763  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18014376a  test    rax, rax
0x18014376d  jz      short loc_180143774
0x18014376f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180143774  mov     rbx, [rsp+78h+arg_10]
0x18014377c  add     rsp, 40h
0x180143780  pop     r15
0x180143782  pop     r14
0x180143784  pop     r13
0x180143786  pop     r12
0x180143788  pop     rdi
0x180143789  pop     rsi
0x18014378a  pop     rbp
0x18014378b  retn
0x18014378d  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
