# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18007f64c`
- end: `0x18007f945`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18007a3a8`
- `0x18007a6ec`

## callees

- `0x18005477c`
- `0x18007a2e8`
- `0x18007eac4`
- `0x18007f64c`
- `0x180080b48`
- `0x180080b70`
- `0x180080ce4`
- `0x180080d00`
- `0x1800827d8`
- `0x1800d6010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18007f88e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18007f88e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18007f900`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18007f900`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007f76f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007f76f`

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

  *lpOutputString = 0;
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
    if ( !*lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v25);
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
0x18007f64c  mov     [rsp+arg_10], rbx
0x18007f651  mov     [rsp+arg_8], edx
0x18007f655  mov     [rsp+arg_0], rcx
0x18007f65a  push    rbp
0x18007f65b  push    rsi
0x18007f65c  push    rdi
0x18007f65d  push    r12
0x18007f65f  push    r13
0x18007f661  push    r14
0x18007f663  push    r15
0x18007f665  sub     rsp, 40h
0x18007f669  mov     r12, r9
0x18007f66c  mov     r13, r8
0x18007f66f  mov     r10, rcx
0x18007f672  xor     eax, eax
0x18007f674  mov     rsi, [rsp+78h+lpOutputString]
0x18007f67c  mov     [rsi], ax
0x18007f67f  mov     rax, [rsp+78h+arg_60]
0x18007f687  mov     byte ptr [rax], 0
0x18007f68a  mov     r14, [rsp+78h+arg_38]
0x18007f692  mov     edi, [r14]
0x18007f695  mov     rbx, [rsp+78h+arg_78]
0x18007f69d  mov     [rbx+8], edi
0x18007f6a0  mov     eax, [r14+4]
0x18007f6a4  mov     [rbx+0Ch], eax
0x18007f6a7  xor     ebp, ebp
0x18007f6a9  mov     r15d, [rsp+78h+arg_30]
0x18007f6b1  mov     ecx, r15d
0x18007f6b4  test    r15d, r15d
0x18007f6b7  jz      short loc_18007F71F
0x18007f6b9  sub     ecx, 1
0x18007f6bc  jz      short loc_18007F716
0x18007f6be  sub     ecx, 1
0x18007f6c1  jz      short loc_18007F6D1
0x18007f6c3  cmp     ecx, 1
0x18007f6c6  jnz     short loc_18007F728
0x18007f6c8  mov     ecx, edi; this
0x18007f6ca  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18007f6cf  jmp     short loc_18007F726
0x18007f6d1  test    edi, edi
0x18007f6d3  js      short loc_18007F70D
0x18007f6d5  mov     edi, 8007029Ch
0x18007f6da  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18007f6de  mov     rax, [rsp+78h+arg_28]
0x18007f6e6  mov     [rsp+78h+var_50], rax; __int64
0x18007f6eb  mov     rax, [rsp+78h+arg_20]
0x18007f6f3  mov     [rsp+78h+var_58], rax; __int64
0x18007f6f8  mov     rcx, r10; int
0x18007f6fb  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18007f700  mov     [rbx+8], edi
0x18007f703  mov     ecx, edi; this
0x18007f705  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18007f70a  mov     [rbx+0Ch], eax
0x18007f70d  mov     ecx, edi; this
0x18007f70f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18007f714  jmp     short loc_18007F726
0x18007f716  mov     ecx, edi; this
0x18007f718  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18007f71d  jmp     short loc_18007F726
0x18007f71f  mov     ecx, edi; this
0x18007f721  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18007f726  mov     ebp, eax
0x18007f728  mov     [rbx], r15d
0x18007f72b  mov     eax, [rsp+78h+arg_70]
0x18007f732  mov     [rbx+4], eax
0x18007f735  cmp     dword ptr [r14+8], 1
0x18007f73a  jnz     short loc_18007F742
0x18007f73c  or      eax, 8
0x18007f73f  mov     [rbx+4], eax
0x18007f742  mov     eax, 1
0x18007f747  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18007f74f  inc     eax
0x18007f751  mov     [rbx+10h], eax
0x18007f754  mov     rax, [rsp+78h+arg_40]
0x18007f75c  xor     edi, edi
0x18007f75e  test    rax, rax
0x18007f761  jz      short loc_18007F768
0x18007f763  cmp     [rax], di
0x18007f766  jnz     short loc_18007F76B
0x18007f768  mov     rax, rdi
0x18007f76b  mov     [rbx+18h], rax
0x18007f76f  call    cs:__imp_GetCurrentThreadId
0x18007f775  mov     [rbx+20h], eax
0x18007f778  mov     [rbx+38h], r13
0x18007f77c  mov     eax, [rsp+78h+arg_8]
0x18007f783  mov     [rbx+40h], eax
0x18007f786  mov     [rbx+44h], ebp
0x18007f789  mov     rax, [rsp+78h+arg_20]
0x18007f791  mov     [rbx+28h], rax
0x18007f795  mov     [rbx+30h], r12
0x18007f799  mov     rax, [rsp+78h+arg_28]
0x18007f7a1  mov     [rbx+88h], rax
0x18007f7a8  mov     rax, [rsp+78h+arg_0]
0x18007f7b0  mov     [rbx+90h], rax
0x18007f7b7  mov     [rbx+48h], rdi
0x18007f7bb  xorps   xmm0, xmm0
0x18007f7be  xor     eax, eax
0x18007f7c0  movups  xmmword ptr [rbx+68h], xmm0
0x18007f7c4  mov     [rbx+78h], rax
0x18007f7c8  movups  xmmword ptr [rbx+50h], xmm0
0x18007f7cc  mov     [rbx+60h], rax
0x18007f7d0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18007f7d7  test    rax, rax
0x18007f7da  jz      short loc_18007F7E3
0x18007f7dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f7e1  jmp     short loc_18007F7E6
0x18007f7e3  mov     rax, rdi
0x18007f7e6  mov     [rbx+80h], rax
0x18007f7ed  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18007f7f4  test    rax, rax
0x18007f7f7  jz      short loc_18007F801
0x18007f7f9  mov     rcx, rbx
0x18007f7fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f801  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18007f808  test    rax, rax
0x18007f80b  jz      short loc_18007F823
0x18007f80d  mov     r8d, 400h
0x18007f813  mov     rdx, [rsp+78h+arg_60]
0x18007f81b  mov     rcx, rbx
0x18007f81e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f823  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18007f82a  test    rax, rax
0x18007f82d  jz      short loc_18007F837
0x18007f82f  mov     rcx, rbx
0x18007f832  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f837  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18007f83e  test    rax, rax
0x18007f841  jz      short loc_18007F851
0x18007f843  test    byte ptr [rbx+4], 2
0x18007f847  jnz     short loc_18007F851
0x18007f849  mov     rcx, rbx
0x18007f84c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f851  cmp     [rbx+8], edi
0x18007f854  jl      short loc_18007F870
0x18007f856  cmp     r15d, 3
0x18007f85a  jnz     loc_18007F93F
0x18007f860  mov     ecx, 8000FFFFh; this
0x18007f865  mov     [rbx+8], ecx
0x18007f868  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18007f86d  mov     [rbx+0Ch], eax
0x18007f870  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18007f877  jnz     short loc_18007F898
0x18007f879  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18007f880  test    rax, rax
0x18007f883  jz      short loc_18007F88E
0x18007f885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f88a  test    al, al
0x18007f88c  jmp     short loc_18007F896
0x18007f88e  call    cs:__imp_IsDebuggerPresent
0x18007f894  test    eax, eax
0x18007f896  jz      short loc_18007F89E
0x18007f898  test    byte ptr [rbx+4], 2
0x18007f89c  jz      short loc_18007F8C2
0x18007f89e  mov     rax, cs:g_pfnResultLoggingCallback
0x18007f8a5  test    rax, rax
0x18007f8a8  jz      short loc_18007F906
0x18007f8aa  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18007f8b1  jnz     short loc_18007F906
0x18007f8b3  xor     r8d, r8d
0x18007f8b6  xor     edx, edx
0x18007f8b8  mov     rcx, rbx
0x18007f8bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f8c0  jmp     short loc_18007F906
0x18007f8c2  mov     ebp, 800h
0x18007f8c7  mov     rax, cs:g_pfnResultLoggingCallback
0x18007f8ce  test    rax, rax
0x18007f8d1  jz      short loc_18007F8EA
0x18007f8d3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18007f8da  jnz     short loc_18007F8EA
0x18007f8dc  mov     r8d, ebp
0x18007f8df  mov     rdx, rsi
0x18007f8e2  mov     rcx, rbx
0x18007f8e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f8ea  cmp     [rsi], di
0x18007f8ed  jnz     short loc_18007F8FD
0x18007f8ef  mov     r8, rbx; unsigned __int64
0x18007f8f2  mov     rdx, rbp; unsigned __int16 *
0x18007f8f5  mov     rcx, rsi; pszDest
0x18007f8f8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18007f8fd  mov     rcx, rsi; lpOutputString
0x18007f900  call    cs:__imp_OutputDebugStringW
0x18007f906  test    byte ptr [rbx+4], 4
0x18007f90a  jnz     short loc_18007F915
0x18007f90c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18007f913  jz      short loc_18007F927
0x18007f915  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18007f91c  test    rax, rax
0x18007f91f  jz      short loc_18007F927
0x18007f921  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f926  nop
0x18007f927  mov     rbx, [rsp+78h+arg_10]
0x18007f92f  add     rsp, 40h
0x18007f933  pop     r15
0x18007f935  pop     r14
0x18007f937  pop     r13
0x18007f939  pop     r12
0x18007f93b  pop     rdi
0x18007f93c  pop     rsi
0x18007f93d  pop     rbp
0x18007f93e  retn
0x18007f93f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
