# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18003f610`
- end: `0x18003f91f`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `783`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18003d3ac`
- `0x18003d730`

## callees

- `0x18002396c`
- `0x18003d2f0`
- `0x18003efe4`
- `0x18003f610`
- `0x1800400c4`
- `0x1800400f0`
- `0x180040104`
- `0x180040124`
- `0x18004152c`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003f731`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003f731`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18003f8d3`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18003f8d3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18003f85a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18003f85a`

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
  __int64 (*ModuleName)(void); // rax
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
    ModuleName = (__int64 (*)(void))wil::details::g_pfnGetModuleName();
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
0x18003f610  mov     [rsp+arg_10], rbx
0x18003f615  mov     [rsp+arg_8], edx
0x18003f619  mov     [rsp+arg_0], rcx
0x18003f61e  push    rbp
0x18003f61f  push    rsi
0x18003f620  push    rdi
0x18003f621  push    r12
0x18003f623  push    r13
0x18003f625  push    r14
0x18003f627  push    r15
0x18003f629  sub     rsp, 40h
0x18003f62d  mov     r12, r9
0x18003f630  mov     r13, r8
0x18003f633  mov     r10, rcx
0x18003f636  xor     eax, eax
0x18003f638  mov     rsi, [rsp+78h+lpOutputString]
0x18003f640  mov     [rsi], ax
0x18003f643  mov     rax, [rsp+78h+arg_60]
0x18003f64b  mov     byte ptr [rax], 0
0x18003f64e  mov     r14, [rsp+78h+arg_38]
0x18003f656  mov     edi, [r14]
0x18003f659  mov     rbx, [rsp+78h+arg_78]
0x18003f661  mov     [rbx+8], edi
0x18003f664  mov     eax, [r14+4]
0x18003f668  mov     [rbx+0Ch], eax
0x18003f66b  xor     ebp, ebp
0x18003f66d  mov     r15d, [rsp+78h+arg_30]
0x18003f675  mov     ecx, r15d
0x18003f678  test    r15d, r15d
0x18003f67b  jz      short loc_18003F6E3
0x18003f67d  sub     ecx, 1
0x18003f680  jz      short loc_18003F6DA
0x18003f682  sub     ecx, 1
0x18003f685  jz      short loc_18003F695
0x18003f687  cmp     ecx, 1
0x18003f68a  jnz     short loc_18003F6EC
0x18003f68c  mov     ecx, edi; this
0x18003f68e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18003f693  jmp     short loc_18003F6EA
0x18003f695  test    edi, edi
0x18003f697  js      short loc_18003F6D1
0x18003f699  mov     edi, 8007029Ch
0x18003f69e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18003f6a2  mov     rax, [rsp+78h+arg_28]
0x18003f6aa  mov     [rsp+78h+var_50], rax; __int64
0x18003f6af  mov     rax, [rsp+78h+arg_20]
0x18003f6b7  mov     [rsp+78h+var_58], rax; __int64
0x18003f6bc  mov     rcx, r10; int
0x18003f6bf  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18003f6c4  mov     [rbx+8], edi
0x18003f6c7  mov     ecx, edi; this
0x18003f6c9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18003f6ce  mov     [rbx+0Ch], eax
0x18003f6d1  mov     ecx, edi; this
0x18003f6d3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18003f6d8  jmp     short loc_18003F6EA
0x18003f6da  mov     ecx, edi; this
0x18003f6dc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18003f6e1  jmp     short loc_18003F6EA
0x18003f6e3  mov     ecx, edi; this
0x18003f6e5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18003f6ea  mov     ebp, eax
0x18003f6ec  mov     [rbx], r15d
0x18003f6ef  mov     eax, [rsp+78h+arg_70]
0x18003f6f6  mov     [rbx+4], eax
0x18003f6f9  cmp     dword ptr [r14+8], 1
0x18003f6fe  jnz     short loc_18003F706
0x18003f700  or      eax, 8
0x18003f703  mov     [rbx+4], eax
0x18003f706  mov     eax, 1
0x18003f70b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18003f713  inc     eax
0x18003f715  mov     [rbx+10h], eax
0x18003f718  mov     rax, [rsp+78h+arg_40]
0x18003f720  test    rax, rax
0x18003f723  jz      short loc_18003F72B
0x18003f725  cmp     word ptr [rax], 0
0x18003f729  jnz     short loc_18003F72D
0x18003f72b  xor     eax, eax
0x18003f72d  mov     [rbx+18h], rax
0x18003f731  call    cs:__imp_GetCurrentThreadId
0x18003f738  nop     dword ptr [rax+rax+00h]
0x18003f73d  mov     [rbx+20h], eax
0x18003f740  mov     [rbx+38h], r13
0x18003f744  mov     eax, [rsp+78h+arg_8]
0x18003f74b  mov     [rbx+40h], eax
0x18003f74e  mov     [rbx+44h], ebp
0x18003f751  mov     rax, [rsp+78h+arg_20]
0x18003f759  mov     [rbx+28h], rax
0x18003f75d  mov     [rbx+30h], r12
0x18003f761  mov     rax, [rsp+78h+arg_28]
0x18003f769  mov     [rbx+88h], rax
0x18003f770  mov     rax, [rsp+78h+arg_0]
0x18003f778  mov     [rbx+90h], rax
0x18003f77f  mov     qword ptr [rbx+48h], 0
0x18003f787  xorps   xmm0, xmm0
0x18003f78a  xor     eax, eax
0x18003f78c  movups  xmmword ptr [rbx+68h], xmm0
0x18003f790  mov     [rbx+78h], rax
0x18003f794  movups  xmmword ptr [rbx+50h], xmm0
0x18003f798  mov     [rbx+60h], rax
0x18003f79c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18003f7a3  test    rax, rax
0x18003f7a6  jz      short loc_18003F7AD
0x18003f7a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f7ad  mov     [rbx+80h], rax
0x18003f7b4  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18003f7bb  test    rax, rax
0x18003f7be  jz      short loc_18003F7C8
0x18003f7c0  mov     rcx, rbx
0x18003f7c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f7c8  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18003f7cf  test    rax, rax
0x18003f7d2  jz      short loc_18003F7EA
0x18003f7d4  mov     r8d, 400h
0x18003f7da  mov     rdx, [rsp+78h+arg_60]
0x18003f7e2  mov     rcx, rbx
0x18003f7e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f7ea  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18003f7f1  test    rax, rax
0x18003f7f4  jz      short loc_18003F7FE
0x18003f7f6  mov     rcx, rbx
0x18003f7f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f7fe  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18003f805  test    rax, rax
0x18003f808  jz      short loc_18003F818
0x18003f80a  test    byte ptr [rbx+4], 2
0x18003f80e  jnz     short loc_18003F818
0x18003f810  mov     rcx, rbx
0x18003f813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f818  cmp     dword ptr [rbx+8], 0
0x18003f81c  jl      short loc_18003F83C
0x18003f81e  cmp     r15d, 3
0x18003f822  jnz     loc_18003F919
0x18003f828  mov     dword ptr [rbx+8], 8000FFFFh
0x18003f82f  mov     ecx, 8000FFFFh; this
0x18003f834  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18003f839  mov     [rbx+0Ch], eax
0x18003f83c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, 0; bool wil::g_fIsDebuggerPresent
0x18003f843  jnz     short loc_18003F86A
0x18003f845  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18003f84c  test    rax, rax
0x18003f84f  jz      short loc_18003F85A
0x18003f851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f856  test    al, al
0x18003f858  jmp     short loc_18003F868
0x18003f85a  call    cs:__imp_IsDebuggerPresent
0x18003f861  nop     dword ptr [rax+rax+00h]
0x18003f866  test    eax, eax
0x18003f868  jz      short loc_18003F870
0x18003f86a  test    byte ptr [rbx+4], 2
0x18003f86e  jz      short loc_18003F894
0x18003f870  mov     rax, cs:g_pfnResultLoggingCallback
0x18003f877  test    rax, rax
0x18003f87a  jz      short loc_18003F8DF
0x18003f87c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x18003f883  jnz     short loc_18003F8DF
0x18003f885  xor     r8d, r8d
0x18003f888  xor     edx, edx
0x18003f88a  mov     rcx, rbx
0x18003f88d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f892  jmp     short loc_18003F8DF
0x18003f894  mov     rax, cs:g_pfnResultLoggingCallback
0x18003f89b  test    rax, rax
0x18003f89e  jz      short loc_18003F8BA
0x18003f8a0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x18003f8a7  jnz     short loc_18003F8BA
0x18003f8a9  mov     r8d, 800h
0x18003f8af  mov     rdx, rsi
0x18003f8b2  mov     rcx, rbx
0x18003f8b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f8ba  cmp     word ptr [rsi], 0
0x18003f8be  jnz     short loc_18003F8D0
0x18003f8c0  mov     r8, rbx; unsigned __int64
0x18003f8c3  mov     edx, 800h; unsigned __int16 *
0x18003f8c8  mov     rcx, rsi; this
0x18003f8cb  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18003f8d0  mov     rcx, rsi; lpOutputString
0x18003f8d3  call    cs:__imp_OutputDebugStringW
0x18003f8da  nop     dword ptr [rax+rax+00h]
0x18003f8df  test    byte ptr [rbx+4], 4
0x18003f8e3  jnz     short loc_18003F8EE
0x18003f8e5  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, 0; bool wil::g_fBreakOnFailure
0x18003f8ec  jz      short loc_18003F900
0x18003f8ee  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18003f8f5  test    rax, rax
0x18003f8f8  jz      short loc_18003F900
0x18003f8fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f8ff  nop
0x18003f900  mov     rbx, [rsp+78h+arg_10]
0x18003f908  add     rsp, 40h
0x18003f90c  pop     r15
0x18003f90e  pop     r14
0x18003f910  pop     r13
0x18003f912  pop     r12
0x18003f914  pop     rdi
0x18003f915  pop     rsi
0x18003f916  pop     rbp
0x18003f917  retn
0x18003f919  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
