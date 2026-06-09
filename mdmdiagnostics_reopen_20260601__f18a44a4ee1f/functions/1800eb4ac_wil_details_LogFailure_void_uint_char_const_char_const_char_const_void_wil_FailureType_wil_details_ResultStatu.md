# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800eb4ac`
- end: `0x1800eb7b8`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `780`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x1800e4cac`
- `0x1800e502c`
- `0x1800f7dc8`

## callees

- `0x1800e4ac8`
- `0x1800ea714`
- `0x1800eafe8`
- `0x1800eb4ac`
- `0x1800ec6dc`
- `0x1800ec700`
- `0x1800ec864`
- `0x1800ec884`
- `0x1800ef1b8`
- `0x180193010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800eb5cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800eb5cf`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800eb6f4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800eb6f4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800eb76c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800eb76c`

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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v25);
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
0x1800eb4ac  mov     [rsp+arg_10], rbx
0x1800eb4b1  mov     [rsp+arg_8], edx
0x1800eb4b5  mov     [rsp+arg_0], rcx
0x1800eb4ba  push    rbp
0x1800eb4bb  push    rsi
0x1800eb4bc  push    rdi
0x1800eb4bd  push    r12
0x1800eb4bf  push    r13
0x1800eb4c1  push    r14
0x1800eb4c3  push    r15
0x1800eb4c5  sub     rsp, 40h
0x1800eb4c9  mov     r12, r9
0x1800eb4cc  mov     r13, r8
0x1800eb4cf  mov     r10, rcx
0x1800eb4d2  xor     eax, eax
0x1800eb4d4  mov     rsi, [rsp+78h+lpOutputString]
0x1800eb4dc  mov     [rsi], ax
0x1800eb4df  mov     rax, [rsp+78h+arg_60]
0x1800eb4e7  mov     byte ptr [rax], 0
0x1800eb4ea  mov     r14, [rsp+78h+arg_38]
0x1800eb4f2  mov     edi, [r14]
0x1800eb4f5  mov     rbx, [rsp+78h+arg_78]
0x1800eb4fd  mov     [rbx+8], edi
0x1800eb500  mov     eax, [r14+4]
0x1800eb504  mov     [rbx+0Ch], eax
0x1800eb507  xor     ebp, ebp
0x1800eb509  mov     r15d, [rsp+78h+arg_30]
0x1800eb511  mov     ecx, r15d
0x1800eb514  test    r15d, r15d
0x1800eb517  jz      short loc_1800EB57F
0x1800eb519  sub     ecx, 1
0x1800eb51c  jz      short loc_1800EB576
0x1800eb51e  sub     ecx, 1
0x1800eb521  jz      short loc_1800EB531
0x1800eb523  cmp     ecx, 1
0x1800eb526  jnz     short loc_1800EB588
0x1800eb528  mov     ecx, edi; this
0x1800eb52a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800eb52f  jmp     short loc_1800EB586
0x1800eb531  test    edi, edi
0x1800eb533  js      short loc_1800EB56D
0x1800eb535  mov     edi, 8007029Ch
0x1800eb53a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800eb53e  mov     rax, [rsp+78h+arg_28]
0x1800eb546  mov     [rsp+78h+var_50], rax; __int64
0x1800eb54b  mov     rax, [rsp+78h+arg_20]
0x1800eb553  mov     [rsp+78h+var_58], rax; __int64
0x1800eb558  mov     rcx, r10; int
0x1800eb55b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800eb560  mov     [rbx+8], edi
0x1800eb563  mov     ecx, edi; this
0x1800eb565  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800eb56a  mov     [rbx+0Ch], eax
0x1800eb56d  mov     ecx, edi; this
0x1800eb56f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800eb574  jmp     short loc_1800EB586
0x1800eb576  mov     ecx, edi; this
0x1800eb578  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800eb57d  jmp     short loc_1800EB586
0x1800eb57f  mov     ecx, edi; this
0x1800eb581  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800eb586  mov     ebp, eax
0x1800eb588  mov     [rbx], r15d
0x1800eb58b  mov     eax, [rsp+78h+arg_70]
0x1800eb592  mov     [rbx+4], eax
0x1800eb595  cmp     dword ptr [r14+8], 1
0x1800eb59a  jnz     short loc_1800EB5A2
0x1800eb59c  or      eax, 8
0x1800eb59f  mov     [rbx+4], eax
0x1800eb5a2  mov     eax, 1
0x1800eb5a7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800eb5af  inc     eax
0x1800eb5b1  mov     [rbx+10h], eax
0x1800eb5b4  mov     rax, [rsp+78h+arg_40]
0x1800eb5bc  xor     edi, edi
0x1800eb5be  test    rax, rax
0x1800eb5c1  jz      short loc_1800EB5C8
0x1800eb5c3  cmp     [rax], di
0x1800eb5c6  jnz     short loc_1800EB5CB
0x1800eb5c8  mov     rax, rdi
0x1800eb5cb  mov     [rbx+18h], rax
0x1800eb5cf  call    cs:__imp_GetCurrentThreadId
0x1800eb5d6  nop     dword ptr [rax+rax+00h]
0x1800eb5db  mov     [rbx+20h], eax
0x1800eb5de  mov     [rbx+38h], r13
0x1800eb5e2  mov     eax, [rsp+78h+arg_8]
0x1800eb5e9  mov     [rbx+40h], eax
0x1800eb5ec  mov     [rbx+44h], ebp
0x1800eb5ef  mov     rax, [rsp+78h+arg_20]
0x1800eb5f7  mov     [rbx+28h], rax
0x1800eb5fb  mov     [rbx+30h], r12
0x1800eb5ff  mov     rax, [rsp+78h+arg_28]
0x1800eb607  mov     [rbx+88h], rax
0x1800eb60e  mov     rax, [rsp+78h+arg_0]
0x1800eb616  mov     [rbx+90h], rax
0x1800eb61d  mov     [rbx+48h], rdi
0x1800eb621  xorps   xmm0, xmm0
0x1800eb624  xor     eax, eax
0x1800eb626  movups  xmmword ptr [rbx+68h], xmm0
0x1800eb62a  mov     [rbx+78h], rax
0x1800eb62e  movups  xmmword ptr [rbx+50h], xmm0
0x1800eb632  mov     [rbx+60h], rax
0x1800eb636  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800eb63d  test    rax, rax
0x1800eb640  jz      short loc_1800EB649
0x1800eb642  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb647  jmp     short loc_1800EB64C
0x1800eb649  mov     rax, rdi
0x1800eb64c  mov     [rbx+80h], rax
0x1800eb653  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800eb65a  test    rax, rax
0x1800eb65d  jz      short loc_1800EB667
0x1800eb65f  mov     rcx, rbx
0x1800eb662  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb667  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800eb66e  test    rax, rax
0x1800eb671  jz      short loc_1800EB689
0x1800eb673  mov     r8d, 400h
0x1800eb679  mov     rdx, [rsp+78h+arg_60]
0x1800eb681  mov     rcx, rbx
0x1800eb684  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb689  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800eb690  test    rax, rax
0x1800eb693  jz      short loc_1800EB69D
0x1800eb695  mov     rcx, rbx
0x1800eb698  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb69d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800eb6a4  test    rax, rax
0x1800eb6a7  jz      short loc_1800EB6B7
0x1800eb6a9  test    byte ptr [rbx+4], 2
0x1800eb6ad  jnz     short loc_1800EB6B7
0x1800eb6af  mov     rcx, rbx
0x1800eb6b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb6b7  cmp     [rbx+8], edi
0x1800eb6ba  jl      short loc_1800EB6D6
0x1800eb6bc  cmp     r15d, 3
0x1800eb6c0  jnz     loc_1800EB7B2
0x1800eb6c6  mov     ecx, 8000FFFFh; this
0x1800eb6cb  mov     [rbx+8], ecx
0x1800eb6ce  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800eb6d3  mov     [rbx+0Ch], eax
0x1800eb6d6  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800eb6dd  jnz     short loc_1800EB704
0x1800eb6df  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800eb6e6  test    rax, rax
0x1800eb6e9  jz      short loc_1800EB6F4
0x1800eb6eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb6f0  test    al, al
0x1800eb6f2  jmp     short loc_1800EB702
0x1800eb6f4  call    cs:__imp_IsDebuggerPresent
0x1800eb6fb  nop     dword ptr [rax+rax+00h]
0x1800eb700  test    eax, eax
0x1800eb702  jz      short loc_1800EB70A
0x1800eb704  test    byte ptr [rbx+4], 2
0x1800eb708  jz      short loc_1800EB72E
0x1800eb70a  mov     rax, cs:g_pfnResultLoggingCallback
0x1800eb711  test    rax, rax
0x1800eb714  jz      short loc_1800EB778
0x1800eb716  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800eb71d  jnz     short loc_1800EB778
0x1800eb71f  xor     r8d, r8d
0x1800eb722  xor     edx, edx
0x1800eb724  mov     rcx, rbx
0x1800eb727  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb72c  jmp     short loc_1800EB778
0x1800eb72e  mov     ebp, 800h
0x1800eb733  mov     rax, cs:g_pfnResultLoggingCallback
0x1800eb73a  test    rax, rax
0x1800eb73d  jz      short loc_1800EB756
0x1800eb73f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800eb746  jnz     short loc_1800EB756
0x1800eb748  mov     r8d, ebp
0x1800eb74b  mov     rdx, rsi
0x1800eb74e  mov     rcx, rbx
0x1800eb751  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb756  cmp     [rsi], di
0x1800eb759  jnz     short loc_1800EB769
0x1800eb75b  mov     r8, rbx; unsigned __int64
0x1800eb75e  mov     rdx, rbp; unsigned __int16 *
0x1800eb761  mov     rcx, rsi; this
0x1800eb764  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800eb769  mov     rcx, rsi; lpOutputString
0x1800eb76c  call    cs:__imp_OutputDebugStringW
0x1800eb773  nop     dword ptr [rax+rax+00h]
0x1800eb778  test    byte ptr [rbx+4], 4
0x1800eb77c  jnz     short loc_1800EB787
0x1800eb77e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800eb785  jz      short loc_1800EB799
0x1800eb787  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800eb78e  test    rax, rax
0x1800eb791  jz      short loc_1800EB799
0x1800eb793  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb798  nop
0x1800eb799  mov     rbx, [rsp+78h+arg_10]
0x1800eb7a1  add     rsp, 40h
0x1800eb7a5  pop     r15
0x1800eb7a7  pop     r14
0x1800eb7a9  pop     r13
0x1800eb7ab  pop     r12
0x1800eb7ad  pop     rdi
0x1800eb7ae  pop     rsi
0x1800eb7af  pop     rbp
0x1800eb7b0  retn
0x1800eb7b2  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
