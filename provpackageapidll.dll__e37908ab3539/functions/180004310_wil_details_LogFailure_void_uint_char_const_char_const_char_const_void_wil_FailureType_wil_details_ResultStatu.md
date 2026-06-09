# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180004310`
- end: `0x180004609`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180002ad0`

## callees

- `0x180002514`
- `0x1800039a4`
- `0x18000414c`
- `0x180004310`
- `0x18000484c`
- `0x180004870`
- `0x180004884`
- `0x1800048a0`
- `0x18000593c`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004433`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004433`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004552`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004552`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800045c4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800045c4`

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
    ModuleName = wil::details::g_pfnGetModuleName(v22);
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
      : (v25 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v22) == 0),
        v25)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v23);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v22);
  }
}

```

## disassembly

```asm
0x180004310  mov     [rsp+arg_10], rbx
0x180004315  mov     [rsp+arg_8], edx
0x180004319  mov     [rsp+arg_0], rcx
0x18000431e  push    rbp
0x18000431f  push    rsi
0x180004320  push    rdi
0x180004321  push    r12
0x180004323  push    r13
0x180004325  push    r14
0x180004327  push    r15
0x180004329  sub     rsp, 40h
0x18000432d  mov     r12, r9
0x180004330  mov     r13, r8
0x180004333  mov     r10, rcx
0x180004336  xor     eax, eax
0x180004338  mov     rsi, [rsp+78h+lpOutputString]
0x180004340  mov     [rsi], ax
0x180004343  mov     rax, [rsp+78h+arg_60]
0x18000434b  mov     byte ptr [rax], 0
0x18000434e  mov     r14, [rsp+78h+arg_38]
0x180004356  mov     edi, [r14]
0x180004359  mov     rbx, [rsp+78h+arg_78]
0x180004361  mov     [rbx+8], edi
0x180004364  mov     eax, [r14+4]
0x180004368  mov     [rbx+0Ch], eax
0x18000436b  xor     ebp, ebp
0x18000436d  mov     r15d, [rsp+78h+arg_30]
0x180004375  mov     ecx, r15d
0x180004378  test    r15d, r15d
0x18000437b  jz      short loc_1800043E3
0x18000437d  sub     ecx, 1
0x180004380  jz      short loc_1800043DA
0x180004382  sub     ecx, 1
0x180004385  jz      short loc_180004395
0x180004387  cmp     ecx, 1
0x18000438a  jnz     short loc_1800043EC
0x18000438c  mov     ecx, edi; this
0x18000438e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180004393  jmp     short loc_1800043EA
0x180004395  test    edi, edi
0x180004397  js      short loc_1800043D1
0x180004399  mov     edi, 8007029Ch
0x18000439e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800043a2  mov     rax, [rsp+78h+arg_28]
0x1800043aa  mov     [rsp+78h+var_50], rax; __int64
0x1800043af  mov     rax, [rsp+78h+arg_20]
0x1800043b7  mov     [rsp+78h+var_58], rax; __int64
0x1800043bc  mov     rcx, r10; int
0x1800043bf  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800043c4  mov     [rbx+8], edi
0x1800043c7  mov     ecx, edi; this
0x1800043c9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800043ce  mov     [rbx+0Ch], eax
0x1800043d1  mov     ecx, edi; this
0x1800043d3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800043d8  jmp     short loc_1800043EA
0x1800043da  mov     ecx, edi; this
0x1800043dc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800043e1  jmp     short loc_1800043EA
0x1800043e3  mov     ecx, edi; this
0x1800043e5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800043ea  mov     ebp, eax
0x1800043ec  mov     [rbx], r15d
0x1800043ef  mov     eax, [rsp+78h+arg_70]
0x1800043f6  mov     [rbx+4], eax
0x1800043f9  cmp     dword ptr [r14+8], 1
0x1800043fe  jnz     short loc_180004406
0x180004400  or      eax, 8
0x180004403  mov     [rbx+4], eax
0x180004406  mov     eax, 1
0x18000440b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004413  inc     eax
0x180004415  mov     [rbx+10h], eax
0x180004418  mov     rax, [rsp+78h+arg_40]
0x180004420  xor     edi, edi
0x180004422  test    rax, rax
0x180004425  jz      short loc_18000442C
0x180004427  cmp     [rax], di
0x18000442a  jnz     short loc_18000442F
0x18000442c  mov     rax, rdi
0x18000442f  mov     [rbx+18h], rax
0x180004433  call    cs:__imp_GetCurrentThreadId
0x180004439  mov     [rbx+20h], eax
0x18000443c  mov     [rbx+38h], r13
0x180004440  mov     eax, [rsp+78h+arg_8]
0x180004447  mov     [rbx+40h], eax
0x18000444a  mov     [rbx+44h], ebp
0x18000444d  mov     rax, [rsp+78h+arg_20]
0x180004455  mov     [rbx+28h], rax
0x180004459  mov     [rbx+30h], r12
0x18000445d  mov     rax, [rsp+78h+arg_28]
0x180004465  mov     [rbx+88h], rax
0x18000446c  mov     rax, [rsp+78h+arg_0]
0x180004474  mov     [rbx+90h], rax
0x18000447b  mov     [rbx+48h], rdi
0x18000447f  xorps   xmm0, xmm0
0x180004482  xor     eax, eax
0x180004484  movups  xmmword ptr [rbx+68h], xmm0
0x180004488  mov     [rbx+78h], rax
0x18000448c  movups  xmmword ptr [rbx+50h], xmm0
0x180004490  mov     [rbx+60h], rax
0x180004494  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000449b  test    rax, rax
0x18000449e  jz      short loc_1800044A7
0x1800044a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044a5  jmp     short loc_1800044AA
0x1800044a7  mov     rax, rdi
0x1800044aa  mov     [rbx+80h], rax
0x1800044b1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800044b8  test    rax, rax
0x1800044bb  jz      short loc_1800044C5
0x1800044bd  mov     rcx, rbx
0x1800044c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044c5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800044cc  test    rax, rax
0x1800044cf  jz      short loc_1800044E7
0x1800044d1  mov     r8d, 400h
0x1800044d7  mov     rdx, [rsp+78h+arg_60]
0x1800044df  mov     rcx, rbx
0x1800044e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044e7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800044ee  test    rax, rax
0x1800044f1  jz      short loc_1800044FB
0x1800044f3  mov     rcx, rbx
0x1800044f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044fb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004502  test    rax, rax
0x180004505  jz      short loc_180004515
0x180004507  test    byte ptr [rbx+4], 2
0x18000450b  jnz     short loc_180004515
0x18000450d  mov     rcx, rbx
0x180004510  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004515  cmp     [rbx+8], edi
0x180004518  jl      short loc_180004534
0x18000451a  cmp     r15d, 3
0x18000451e  jnz     loc_180004603
0x180004524  mov     ecx, 8000FFFFh; this
0x180004529  mov     [rbx+8], ecx
0x18000452c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004531  mov     [rbx+0Ch], eax
0x180004534  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000453b  jnz     short loc_18000455C
0x18000453d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004544  test    rax, rax
0x180004547  jz      short loc_180004552
0x180004549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000454e  test    al, al
0x180004550  jmp     short loc_18000455A
0x180004552  call    cs:__imp_IsDebuggerPresent
0x180004558  test    eax, eax
0x18000455a  jz      short loc_180004562
0x18000455c  test    byte ptr [rbx+4], 2
0x180004560  jz      short loc_180004586
0x180004562  mov     rax, cs:g_pfnResultLoggingCallback
0x180004569  test    rax, rax
0x18000456c  jz      short loc_1800045CA
0x18000456e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180004575  jnz     short loc_1800045CA
0x180004577  xor     r8d, r8d
0x18000457a  xor     edx, edx
0x18000457c  mov     rcx, rbx
0x18000457f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004584  jmp     short loc_1800045CA
0x180004586  mov     ebp, 800h
0x18000458b  mov     rax, cs:g_pfnResultLoggingCallback
0x180004592  test    rax, rax
0x180004595  jz      short loc_1800045AE
0x180004597  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000459e  jnz     short loc_1800045AE
0x1800045a0  mov     r8d, ebp
0x1800045a3  mov     rdx, rsi
0x1800045a6  mov     rcx, rbx
0x1800045a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045ae  cmp     [rsi], di
0x1800045b1  jnz     short loc_1800045C1
0x1800045b3  mov     r8, rbx; unsigned __int64
0x1800045b6  mov     rdx, rbp; unsigned __int16 *
0x1800045b9  mov     rcx, rsi; this
0x1800045bc  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800045c1  mov     rcx, rsi; lpOutputString
0x1800045c4  call    cs:__imp_OutputDebugStringW
0x1800045ca  test    byte ptr [rbx+4], 4
0x1800045ce  jnz     short loc_1800045D9
0x1800045d0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800045d7  jz      short loc_1800045EB
0x1800045d9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800045e0  test    rax, rax
0x1800045e3  jz      short loc_1800045EB
0x1800045e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045ea  nop
0x1800045eb  mov     rbx, [rsp+78h+arg_10]
0x1800045f3  add     rsp, 40h
0x1800045f7  pop     r15
0x1800045f9  pop     r14
0x1800045fb  pop     r13
0x1800045fd  pop     r12
0x1800045ff  pop     rdi
0x180004600  pop     rsi
0x180004601  pop     rbp
0x180004602  retn
0x180004603  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
