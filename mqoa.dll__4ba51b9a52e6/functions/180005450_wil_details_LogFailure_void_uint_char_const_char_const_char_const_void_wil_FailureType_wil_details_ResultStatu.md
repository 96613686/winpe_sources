# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180005450`
- end: `0x180005749`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180002b64`
- `0x180002eb0`

## callees

- `0x180002aa4`
- `0x180004774`
- `0x1800050f0`
- `0x180005450`
- `0x1800064ac`
- `0x1800064d0`
- `0x180006658`
- `0x180006674`
- `0x18000815c`
- `0x180029010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180005573`
- `KERNEL32!GetCurrentThreadId` at `0x180005573`
- `KERNEL32!IsDebuggerPresent` at `0x180005692`
- `KERNEL32!IsDebuggerPresent` at `0x180005692`
- `KERNEL32!OutputDebugStringW` at `0x180005704`
- `KERNEL32!OutputDebugStringW` at `0x180005704`

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
0x180005450  mov     [rsp+arg_10], rbx
0x180005455  mov     [rsp+arg_8], edx
0x180005459  mov     [rsp+arg_0], rcx
0x18000545e  push    rbp
0x18000545f  push    rsi
0x180005460  push    rdi
0x180005461  push    r12
0x180005463  push    r13
0x180005465  push    r14
0x180005467  push    r15
0x180005469  sub     rsp, 40h
0x18000546d  mov     r12, r9
0x180005470  mov     r13, r8
0x180005473  mov     r10, rcx
0x180005476  xor     eax, eax
0x180005478  mov     rsi, [rsp+78h+lpOutputString]
0x180005480  mov     [rsi], ax
0x180005483  mov     rax, [rsp+78h+arg_60]
0x18000548b  mov     byte ptr [rax], 0
0x18000548e  mov     r14, [rsp+78h+arg_38]
0x180005496  mov     edi, [r14]
0x180005499  mov     rbx, [rsp+78h+arg_78]
0x1800054a1  mov     [rbx+8], edi
0x1800054a4  mov     eax, [r14+4]
0x1800054a8  mov     [rbx+0Ch], eax
0x1800054ab  xor     ebp, ebp
0x1800054ad  mov     r15d, [rsp+78h+arg_30]
0x1800054b5  mov     ecx, r15d
0x1800054b8  test    r15d, r15d
0x1800054bb  jz      short loc_180005523
0x1800054bd  sub     ecx, 1
0x1800054c0  jz      short loc_18000551A
0x1800054c2  sub     ecx, 1
0x1800054c5  jz      short loc_1800054D5
0x1800054c7  cmp     ecx, 1
0x1800054ca  jnz     short loc_18000552C
0x1800054cc  mov     ecx, edi; this
0x1800054ce  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800054d3  jmp     short loc_18000552A
0x1800054d5  test    edi, edi
0x1800054d7  js      short loc_180005511
0x1800054d9  mov     edi, 8007029Ch
0x1800054de  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800054e2  mov     rax, [rsp+78h+arg_28]
0x1800054ea  mov     [rsp+78h+var_50], rax; __int64
0x1800054ef  mov     rax, [rsp+78h+arg_20]
0x1800054f7  mov     [rsp+78h+var_58], rax; __int64
0x1800054fc  mov     rcx, r10; int
0x1800054ff  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180005504  mov     [rbx+8], edi
0x180005507  mov     ecx, edi; this
0x180005509  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000550e  mov     [rbx+0Ch], eax
0x180005511  mov     ecx, edi; this
0x180005513  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180005518  jmp     short loc_18000552A
0x18000551a  mov     ecx, edi; this
0x18000551c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005521  jmp     short loc_18000552A
0x180005523  mov     ecx, edi; this
0x180005525  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000552a  mov     ebp, eax
0x18000552c  mov     [rbx], r15d
0x18000552f  mov     eax, [rsp+78h+arg_70]
0x180005536  mov     [rbx+4], eax
0x180005539  cmp     dword ptr [r14+8], 1
0x18000553e  jnz     short loc_180005546
0x180005540  or      eax, 8
0x180005543  mov     [rbx+4], eax
0x180005546  mov     eax, 1
0x18000554b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005553  inc     eax
0x180005555  mov     [rbx+10h], eax
0x180005558  mov     rax, [rsp+78h+arg_40]
0x180005560  xor     edi, edi
0x180005562  test    rax, rax
0x180005565  jz      short loc_18000556C
0x180005567  cmp     [rax], di
0x18000556a  jnz     short loc_18000556F
0x18000556c  mov     rax, rdi
0x18000556f  mov     [rbx+18h], rax
0x180005573  call    cs:__imp_GetCurrentThreadId
0x180005579  mov     [rbx+20h], eax
0x18000557c  mov     [rbx+38h], r13
0x180005580  mov     eax, [rsp+78h+arg_8]
0x180005587  mov     [rbx+40h], eax
0x18000558a  mov     [rbx+44h], ebp
0x18000558d  mov     rax, [rsp+78h+arg_20]
0x180005595  mov     [rbx+28h], rax
0x180005599  mov     [rbx+30h], r12
0x18000559d  mov     rax, [rsp+78h+arg_28]
0x1800055a5  mov     [rbx+88h], rax
0x1800055ac  mov     rax, [rsp+78h+arg_0]
0x1800055b4  mov     [rbx+90h], rax
0x1800055bb  mov     [rbx+48h], rdi
0x1800055bf  xorps   xmm0, xmm0
0x1800055c2  xor     eax, eax
0x1800055c4  movups  xmmword ptr [rbx+68h], xmm0
0x1800055c8  mov     [rbx+78h], rax
0x1800055cc  movups  xmmword ptr [rbx+50h], xmm0
0x1800055d0  mov     [rbx+60h], rax
0x1800055d4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800055db  test    rax, rax
0x1800055de  jz      short loc_1800055E7
0x1800055e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055e5  jmp     short loc_1800055EA
0x1800055e7  mov     rax, rdi
0x1800055ea  mov     [rbx+80h], rax
0x1800055f1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800055f8  test    rax, rax
0x1800055fb  jz      short loc_180005605
0x1800055fd  mov     rcx, rbx
0x180005600  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005605  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000560c  test    rax, rax
0x18000560f  jz      short loc_180005627
0x180005611  mov     r8d, 400h
0x180005617  mov     rdx, [rsp+78h+arg_60]
0x18000561f  mov     rcx, rbx
0x180005622  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005627  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000562e  test    rax, rax
0x180005631  jz      short loc_18000563B
0x180005633  mov     rcx, rbx
0x180005636  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000563b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005642  test    rax, rax
0x180005645  jz      short loc_180005655
0x180005647  test    byte ptr [rbx+4], 2
0x18000564b  jnz     short loc_180005655
0x18000564d  mov     rcx, rbx
0x180005650  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005655  cmp     [rbx+8], edi
0x180005658  jl      short loc_180005674
0x18000565a  cmp     r15d, 3
0x18000565e  jnz     loc_180005743
0x180005664  mov     ecx, 8000FFFFh; this
0x180005669  mov     [rbx+8], ecx
0x18000566c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005671  mov     [rbx+0Ch], eax
0x180005674  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000567b  jnz     short loc_18000569C
0x18000567d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005684  test    rax, rax
0x180005687  jz      short loc_180005692
0x180005689  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000568e  test    al, al
0x180005690  jmp     short loc_18000569A
0x180005692  call    cs:__imp_IsDebuggerPresent
0x180005698  test    eax, eax
0x18000569a  jz      short loc_1800056A2
0x18000569c  test    byte ptr [rbx+4], 2
0x1800056a0  jz      short loc_1800056C6
0x1800056a2  mov     rax, cs:g_pfnResultLoggingCallback
0x1800056a9  test    rax, rax
0x1800056ac  jz      short loc_18000570A
0x1800056ae  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800056b5  jnz     short loc_18000570A
0x1800056b7  xor     r8d, r8d
0x1800056ba  xor     edx, edx
0x1800056bc  mov     rcx, rbx
0x1800056bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056c4  jmp     short loc_18000570A
0x1800056c6  mov     ebp, 800h
0x1800056cb  mov     rax, cs:g_pfnResultLoggingCallback
0x1800056d2  test    rax, rax
0x1800056d5  jz      short loc_1800056EE
0x1800056d7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800056de  jnz     short loc_1800056EE
0x1800056e0  mov     r8d, ebp
0x1800056e3  mov     rdx, rsi
0x1800056e6  mov     rcx, rbx
0x1800056e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056ee  cmp     [rsi], di
0x1800056f1  jnz     short loc_180005701
0x1800056f3  mov     r8, rbx; unsigned __int64
0x1800056f6  mov     rdx, rbp; wchar_t *
0x1800056f9  mov     rcx, rsi; this
0x1800056fc  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180005701  mov     rcx, rsi; lpOutputString
0x180005704  call    cs:__imp_OutputDebugStringW
0x18000570a  test    byte ptr [rbx+4], 4
0x18000570e  jnz     short loc_180005719
0x180005710  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180005717  jz      short loc_18000572B
0x180005719  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005720  test    rax, rax
0x180005723  jz      short loc_18000572B
0x180005725  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000572a  nop
0x18000572b  mov     rbx, [rsp+78h+arg_10]
0x180005733  add     rsp, 40h
0x180005737  pop     r15
0x180005739  pop     r14
0x18000573b  pop     r13
0x18000573d  pop     r12
0x18000573f  pop     rdi
0x180005740  pop     rsi
0x180005741  pop     rbp
0x180005742  retn
0x180005743  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
