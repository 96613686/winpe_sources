# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180004314`
- end: `0x18000460d`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180002b28`

## callees

- `0x180002564`
- `0x1800039b4`
- `0x180004150`
- `0x180004314`
- `0x18000484c`
- `0x180004870`
- `0x180004884`
- `0x1800048a0`
- `0x1800058ec`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004437`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004437`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004556`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004556`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800045c8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800045c8`

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
0x180004314  mov     [rsp+arg_10], rbx
0x180004319  mov     [rsp+arg_8], edx
0x18000431d  mov     [rsp+arg_0], rcx
0x180004322  push    rbp
0x180004323  push    rsi
0x180004324  push    rdi
0x180004325  push    r12
0x180004327  push    r13
0x180004329  push    r14
0x18000432b  push    r15
0x18000432d  sub     rsp, 40h
0x180004331  mov     r12, r9
0x180004334  mov     r13, r8
0x180004337  mov     r10, rcx
0x18000433a  xor     eax, eax
0x18000433c  mov     rsi, [rsp+78h+lpOutputString]
0x180004344  mov     [rsi], ax
0x180004347  mov     rax, [rsp+78h+arg_60]
0x18000434f  mov     byte ptr [rax], 0
0x180004352  mov     r14, [rsp+78h+arg_38]
0x18000435a  mov     edi, [r14]
0x18000435d  mov     rbx, [rsp+78h+arg_78]
0x180004365  mov     [rbx+8], edi
0x180004368  mov     eax, [r14+4]
0x18000436c  mov     [rbx+0Ch], eax
0x18000436f  xor     ebp, ebp
0x180004371  mov     r15d, [rsp+78h+arg_30]
0x180004379  mov     ecx, r15d
0x18000437c  test    r15d, r15d
0x18000437f  jz      short loc_1800043E7
0x180004381  sub     ecx, 1
0x180004384  jz      short loc_1800043DE
0x180004386  sub     ecx, 1
0x180004389  jz      short loc_180004399
0x18000438b  cmp     ecx, 1
0x18000438e  jnz     short loc_1800043F0
0x180004390  mov     ecx, edi; this
0x180004392  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180004397  jmp     short loc_1800043EE
0x180004399  test    edi, edi
0x18000439b  js      short loc_1800043D5
0x18000439d  mov     edi, 8007029Ch
0x1800043a2  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800043a6  mov     rax, [rsp+78h+arg_28]
0x1800043ae  mov     [rsp+78h+var_50], rax; __int64
0x1800043b3  mov     rax, [rsp+78h+arg_20]
0x1800043bb  mov     [rsp+78h+var_58], rax; __int64
0x1800043c0  mov     rcx, r10; int
0x1800043c3  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800043c8  mov     [rbx+8], edi
0x1800043cb  mov     ecx, edi; this
0x1800043cd  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800043d2  mov     [rbx+0Ch], eax
0x1800043d5  mov     ecx, edi; this
0x1800043d7  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800043dc  jmp     short loc_1800043EE
0x1800043de  mov     ecx, edi; this
0x1800043e0  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800043e5  jmp     short loc_1800043EE
0x1800043e7  mov     ecx, edi; this
0x1800043e9  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800043ee  mov     ebp, eax
0x1800043f0  mov     [rbx], r15d
0x1800043f3  mov     eax, [rsp+78h+arg_70]
0x1800043fa  mov     [rbx+4], eax
0x1800043fd  cmp     dword ptr [r14+8], 1
0x180004402  jnz     short loc_18000440A
0x180004404  or      eax, 8
0x180004407  mov     [rbx+4], eax
0x18000440a  mov     eax, 1
0x18000440f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004417  inc     eax
0x180004419  mov     [rbx+10h], eax
0x18000441c  mov     rax, [rsp+78h+arg_40]
0x180004424  xor     edi, edi
0x180004426  test    rax, rax
0x180004429  jz      short loc_180004430
0x18000442b  cmp     [rax], di
0x18000442e  jnz     short loc_180004433
0x180004430  mov     rax, rdi
0x180004433  mov     [rbx+18h], rax
0x180004437  call    cs:__imp_GetCurrentThreadId
0x18000443d  mov     [rbx+20h], eax
0x180004440  mov     [rbx+38h], r13
0x180004444  mov     eax, [rsp+78h+arg_8]
0x18000444b  mov     [rbx+40h], eax
0x18000444e  mov     [rbx+44h], ebp
0x180004451  mov     rax, [rsp+78h+arg_20]
0x180004459  mov     [rbx+28h], rax
0x18000445d  mov     [rbx+30h], r12
0x180004461  mov     rax, [rsp+78h+arg_28]
0x180004469  mov     [rbx+88h], rax
0x180004470  mov     rax, [rsp+78h+arg_0]
0x180004478  mov     [rbx+90h], rax
0x18000447f  mov     [rbx+48h], rdi
0x180004483  xorps   xmm0, xmm0
0x180004486  xor     eax, eax
0x180004488  movups  xmmword ptr [rbx+68h], xmm0
0x18000448c  mov     [rbx+78h], rax
0x180004490  movups  xmmword ptr [rbx+50h], xmm0
0x180004494  mov     [rbx+60h], rax
0x180004498  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000449f  test    rax, rax
0x1800044a2  jz      short loc_1800044AB
0x1800044a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044a9  jmp     short loc_1800044AE
0x1800044ab  mov     rax, rdi
0x1800044ae  mov     [rbx+80h], rax
0x1800044b5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800044bc  test    rax, rax
0x1800044bf  jz      short loc_1800044C9
0x1800044c1  mov     rcx, rbx
0x1800044c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044c9  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800044d0  test    rax, rax
0x1800044d3  jz      short loc_1800044EB
0x1800044d5  mov     r8d, 400h
0x1800044db  mov     rdx, [rsp+78h+arg_60]
0x1800044e3  mov     rcx, rbx
0x1800044e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044eb  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800044f2  test    rax, rax
0x1800044f5  jz      short loc_1800044FF
0x1800044f7  mov     rcx, rbx
0x1800044fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044ff  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004506  test    rax, rax
0x180004509  jz      short loc_180004519
0x18000450b  test    byte ptr [rbx+4], 2
0x18000450f  jnz     short loc_180004519
0x180004511  mov     rcx, rbx
0x180004514  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004519  cmp     [rbx+8], edi
0x18000451c  jl      short loc_180004538
0x18000451e  cmp     r15d, 3
0x180004522  jnz     loc_180004607
0x180004528  mov     ecx, 8000FFFFh; this
0x18000452d  mov     [rbx+8], ecx
0x180004530  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004535  mov     [rbx+0Ch], eax
0x180004538  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000453f  jnz     short loc_180004560
0x180004541  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004548  test    rax, rax
0x18000454b  jz      short loc_180004556
0x18000454d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004552  test    al, al
0x180004554  jmp     short loc_18000455E
0x180004556  call    cs:__imp_IsDebuggerPresent
0x18000455c  test    eax, eax
0x18000455e  jz      short loc_180004566
0x180004560  test    byte ptr [rbx+4], 2
0x180004564  jz      short loc_18000458A
0x180004566  mov     rax, cs:g_pfnResultLoggingCallback
0x18000456d  test    rax, rax
0x180004570  jz      short loc_1800045CE
0x180004572  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180004579  jnz     short loc_1800045CE
0x18000457b  xor     r8d, r8d
0x18000457e  xor     edx, edx
0x180004580  mov     rcx, rbx
0x180004583  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004588  jmp     short loc_1800045CE
0x18000458a  mov     ebp, 800h
0x18000458f  mov     rax, cs:g_pfnResultLoggingCallback
0x180004596  test    rax, rax
0x180004599  jz      short loc_1800045B2
0x18000459b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800045a2  jnz     short loc_1800045B2
0x1800045a4  mov     r8d, ebp
0x1800045a7  mov     rdx, rsi
0x1800045aa  mov     rcx, rbx
0x1800045ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045b2  cmp     [rsi], di
0x1800045b5  jnz     short loc_1800045C5
0x1800045b7  mov     r8, rbx; unsigned __int64
0x1800045ba  mov     rdx, rbp; unsigned __int16 *
0x1800045bd  mov     rcx, rsi; this
0x1800045c0  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800045c5  mov     rcx, rsi; lpOutputString
0x1800045c8  call    cs:__imp_OutputDebugStringW
0x1800045ce  test    byte ptr [rbx+4], 4
0x1800045d2  jnz     short loc_1800045DD
0x1800045d4  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800045db  jz      short loc_1800045EF
0x1800045dd  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800045e4  test    rax, rax
0x1800045e7  jz      short loc_1800045EF
0x1800045e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045ee  nop
0x1800045ef  mov     rbx, [rsp+78h+arg_10]
0x1800045f7  add     rsp, 40h
0x1800045fb  pop     r15
0x1800045fd  pop     r14
0x1800045ff  pop     r13
0x180004601  pop     r12
0x180004603  pop     rdi
0x180004604  pop     rsi
0x180004605  pop     rbp
0x180004606  retn
0x180004607  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
