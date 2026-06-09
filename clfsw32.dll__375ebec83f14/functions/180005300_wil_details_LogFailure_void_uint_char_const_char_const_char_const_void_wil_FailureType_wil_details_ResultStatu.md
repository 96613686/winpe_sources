# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180005300`
- end: `0x18000560b`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `779`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18000307c`

## callees

- `0x180002a94`
- `0x180004934`
- `0x18000513c`
- `0x180005300`
- `0x180005d54`
- `0x180005d80`
- `0x180005ec8`
- `0x180005ee8`
- `0x180007e00`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005548`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005548`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800055c0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800055c0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005423`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005423`

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
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v26);
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
0x180005300  mov     [rsp+arg_10], rbx
0x180005305  mov     [rsp+arg_8], edx
0x180005309  mov     [rsp+arg_0], rcx
0x18000530e  push    rbp
0x18000530f  push    rsi
0x180005310  push    rdi
0x180005311  push    r12
0x180005313  push    r13
0x180005315  push    r14
0x180005317  push    r15
0x180005319  sub     rsp, 40h
0x18000531d  mov     r14, [rsp+78h+arg_38]
0x180005325  xor     eax, eax
0x180005327  mov     rbx, [rsp+78h+arg_78]
0x18000532f  xor     ebp, ebp
0x180005331  mov     r15d, [rsp+78h+arg_30]
0x180005339  mov     r10, rcx
0x18000533c  mov     rsi, [rsp+78h+lpOutputString]
0x180005344  mov     r12, r9
0x180005347  mov     r13, r8
0x18000534a  mov     ecx, r15d
0x18000534d  mov     [rsi], ax
0x180005350  mov     rax, [rsp+78h+arg_60]
0x180005358  mov     byte ptr [rax], 0
0x18000535b  mov     edi, [r14]
0x18000535e  mov     [rbx+8], edi
0x180005361  mov     eax, [r14+4]
0x180005365  mov     [rbx+0Ch], eax
0x180005368  test    r15d, r15d
0x18000536b  jz      short loc_1800053D3
0x18000536d  sub     ecx, 1
0x180005370  jz      short loc_1800053CA
0x180005372  sub     ecx, 1
0x180005375  jz      short loc_180005385
0x180005377  cmp     ecx, 1
0x18000537a  jnz     short loc_1800053DC
0x18000537c  mov     ecx, edi; this
0x18000537e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180005383  jmp     short loc_1800053DA
0x180005385  test    edi, edi
0x180005387  js      short loc_1800053C1
0x180005389  mov     rax, [rsp+78h+arg_28]
0x180005391  mov     edi, 8007029Ch
0x180005396  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000539a  mov     rcx, r10; int
0x18000539d  mov     [rsp+78h+var_50], rax; __int64
0x1800053a2  mov     rax, [rsp+78h+arg_20]
0x1800053aa  mov     [rsp+78h+var_58], rax; __int64
0x1800053af  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800053b4  mov     ecx, edi; this
0x1800053b6  mov     [rbx+8], edi
0x1800053b9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800053be  mov     [rbx+0Ch], eax
0x1800053c1  mov     ecx, edi; this
0x1800053c3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800053c8  jmp     short loc_1800053DA
0x1800053ca  mov     ecx, edi; this
0x1800053cc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800053d1  jmp     short loc_1800053DA
0x1800053d3  mov     ecx, edi; this
0x1800053d5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800053da  mov     ebp, eax
0x1800053dc  mov     eax, [rsp+78h+arg_70]
0x1800053e3  mov     [rbx+4], eax
0x1800053e6  mov     [rbx], r15d
0x1800053e9  cmp     dword ptr [r14+8], 1
0x1800053ee  jnz     short loc_1800053F6
0x1800053f0  or      eax, 8
0x1800053f3  mov     [rbx+4], eax
0x1800053f6  mov     eax, 1
0x1800053fb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005403  inc     eax
0x180005405  xor     edi, edi
0x180005407  mov     [rbx+10h], eax
0x18000540a  mov     rax, [rsp+78h+arg_40]
0x180005412  test    rax, rax
0x180005415  jz      short loc_18000541C
0x180005417  cmp     [rax], di
0x18000541a  jnz     short loc_18000541F
0x18000541c  mov     rax, rdi
0x18000541f  mov     [rbx+18h], rax
0x180005423  call    cs:__imp_GetCurrentThreadId
0x18000542a  nop     dword ptr [rax+rax+00h]
0x18000542f  mov     [rbx+38h], r13
0x180005433  xorps   xmm0, xmm0
0x180005436  mov     [rbx+20h], eax
0x180005439  mov     eax, [rsp+78h+arg_8]
0x180005440  mov     [rbx+40h], eax
0x180005443  mov     rax, [rsp+78h+arg_20]
0x18000544b  mov     [rbx+28h], rax
0x18000544f  mov     rax, [rsp+78h+arg_28]
0x180005457  mov     [rbx+88h], rax
0x18000545e  mov     rax, [rsp+78h+arg_0]
0x180005466  mov     [rbx+90h], rax
0x18000546d  xor     eax, eax
0x18000546f  mov     [rbx+44h], ebp
0x180005472  mov     [rbx+30h], r12
0x180005476  mov     [rbx+48h], rdi
0x18000547a  movups  xmmword ptr [rbx+68h], xmm0
0x18000547e  mov     [rbx+78h], rax
0x180005482  movups  xmmword ptr [rbx+50h], xmm0
0x180005486  mov     [rbx+60h], rax
0x18000548a  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005491  test    rax, rax
0x180005494  jz      short loc_18000549D
0x180005496  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000549b  jmp     short loc_1800054A0
0x18000549d  mov     rax, rdi
0x1800054a0  mov     [rbx+80h], rax
0x1800054a7  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800054ae  test    rax, rax
0x1800054b1  jz      short loc_1800054BB
0x1800054b3  mov     rcx, rbx
0x1800054b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054bb  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800054c2  test    rax, rax
0x1800054c5  jz      short loc_1800054DD
0x1800054c7  mov     rdx, [rsp+78h+arg_60]
0x1800054cf  mov     r8d, 400h
0x1800054d5  mov     rcx, rbx
0x1800054d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054dd  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800054e4  test    rax, rax
0x1800054e7  jz      short loc_1800054F1
0x1800054e9  mov     rcx, rbx
0x1800054ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054f1  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800054f8  test    rax, rax
0x1800054fb  jz      short loc_18000550B
0x1800054fd  test    byte ptr [rbx+4], 2
0x180005501  jnz     short loc_18000550B
0x180005503  mov     rcx, rbx
0x180005506  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000550b  cmp     [rbx+8], edi
0x18000550e  jl      short loc_18000552A
0x180005510  cmp     r15d, 3
0x180005514  jnz     loc_180005605
0x18000551a  mov     ecx, 8000FFFFh; this
0x18000551f  mov     [rbx+8], ecx
0x180005522  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005527  mov     [rbx+0Ch], eax
0x18000552a  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180005531  jnz     short loc_180005558
0x180005533  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000553a  test    rax, rax
0x18000553d  jz      short loc_180005548
0x18000553f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005544  test    al, al
0x180005546  jmp     short loc_180005556
0x180005548  call    cs:__imp_IsDebuggerPresent
0x18000554f  nop     dword ptr [rax+rax+00h]
0x180005554  test    eax, eax
0x180005556  jz      short loc_18000555E
0x180005558  test    byte ptr [rbx+4], 2
0x18000555c  jz      short loc_180005582
0x18000555e  mov     rax, cs:g_pfnResultLoggingCallback
0x180005565  test    rax, rax
0x180005568  jz      short loc_1800055CC
0x18000556a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005571  jnz     short loc_1800055CC
0x180005573  xor     r8d, r8d
0x180005576  xor     edx, edx
0x180005578  mov     rcx, rbx
0x18000557b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005580  jmp     short loc_1800055CC
0x180005582  mov     rax, cs:g_pfnResultLoggingCallback
0x180005589  mov     ebp, 800h
0x18000558e  test    rax, rax
0x180005591  jz      short loc_1800055AA
0x180005593  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000559a  jnz     short loc_1800055AA
0x18000559c  mov     r8d, ebp
0x18000559f  mov     rdx, rsi
0x1800055a2  mov     rcx, rbx
0x1800055a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055aa  cmp     [rsi], di
0x1800055ad  jnz     short loc_1800055BD
0x1800055af  mov     r8, rbx; unsigned __int64
0x1800055b2  mov     rdx, rbp; unsigned __int16 *
0x1800055b5  mov     rcx, rsi; this
0x1800055b8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800055bd  mov     rcx, rsi; lpOutputString
0x1800055c0  call    cs:__imp_OutputDebugStringW
0x1800055c7  nop     dword ptr [rax+rax+00h]
0x1800055cc  test    byte ptr [rbx+4], 4
0x1800055d0  jnz     short loc_1800055DB
0x1800055d2  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800055d9  jz      short loc_1800055EC
0x1800055db  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800055e2  test    rax, rax
0x1800055e5  jz      short loc_1800055EC
0x1800055e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055ec  mov     rbx, [rsp+78h+arg_10]
0x1800055f4  add     rsp, 40h
0x1800055f8  pop     r15
0x1800055fa  pop     r14
0x1800055fc  pop     r13
0x1800055fe  pop     r12
0x180005600  pop     rdi
0x180005601  pop     rsi
0x180005602  pop     rbp
0x180005603  retn
0x180005605  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
