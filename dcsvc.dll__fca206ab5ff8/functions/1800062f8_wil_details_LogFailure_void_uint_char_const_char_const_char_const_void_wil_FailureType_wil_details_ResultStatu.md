# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800062f8`
- end: `0x1800065f1`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800036b8`

## callees

- `0x1800030fc`
- `0x180005744`
- `0x180005eec`
- `0x1800062f8`
- `0x180006f68`
- `0x180006f90`
- `0x1800070bc`
- `0x1800070d8`
- `0x18000a12c`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000641b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000641b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000653a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000653a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800065ac`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800065ac`

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
0x1800062f8  mov     [rsp+arg_10], rbx
0x1800062fd  mov     [rsp+arg_8], edx
0x180006301  mov     [rsp+arg_0], rcx
0x180006306  push    rbp
0x180006307  push    rsi
0x180006308  push    rdi
0x180006309  push    r12
0x18000630b  push    r13
0x18000630d  push    r14
0x18000630f  push    r15
0x180006311  sub     rsp, 40h
0x180006315  mov     r12, r9
0x180006318  mov     r13, r8
0x18000631b  mov     r10, rcx
0x18000631e  xor     eax, eax
0x180006320  mov     rsi, [rsp+78h+lpOutputString]
0x180006328  mov     [rsi], ax
0x18000632b  mov     rax, [rsp+78h+arg_60]
0x180006333  mov     byte ptr [rax], 0
0x180006336  mov     r14, [rsp+78h+arg_38]
0x18000633e  mov     edi, [r14]
0x180006341  mov     rbx, [rsp+78h+arg_78]
0x180006349  mov     [rbx+8], edi
0x18000634c  mov     eax, [r14+4]
0x180006350  mov     [rbx+0Ch], eax
0x180006353  xor     ebp, ebp
0x180006355  mov     r15d, [rsp+78h+arg_30]
0x18000635d  mov     ecx, r15d
0x180006360  test    r15d, r15d
0x180006363  jz      short loc_1800063CB
0x180006365  sub     ecx, 1
0x180006368  jz      short loc_1800063C2
0x18000636a  sub     ecx, 1
0x18000636d  jz      short loc_18000637D
0x18000636f  cmp     ecx, 1
0x180006372  jnz     short loc_1800063D4
0x180006374  mov     ecx, edi; this
0x180006376  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000637b  jmp     short loc_1800063D2
0x18000637d  test    edi, edi
0x18000637f  js      short loc_1800063B9
0x180006381  mov     edi, 8007029Ch
0x180006386  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000638a  mov     rax, [rsp+78h+arg_28]
0x180006392  mov     [rsp+78h+var_50], rax; __int64
0x180006397  mov     rax, [rsp+78h+arg_20]
0x18000639f  mov     [rsp+78h+var_58], rax; __int64
0x1800063a4  mov     rcx, r10; int
0x1800063a7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800063ac  mov     [rbx+8], edi
0x1800063af  mov     ecx, edi; this
0x1800063b1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800063b6  mov     [rbx+0Ch], eax
0x1800063b9  mov     ecx, edi; this
0x1800063bb  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800063c0  jmp     short loc_1800063D2
0x1800063c2  mov     ecx, edi; this
0x1800063c4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800063c9  jmp     short loc_1800063D2
0x1800063cb  mov     ecx, edi; this
0x1800063cd  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800063d2  mov     ebp, eax
0x1800063d4  mov     [rbx], r15d
0x1800063d7  mov     eax, [rsp+78h+arg_70]
0x1800063de  mov     [rbx+4], eax
0x1800063e1  cmp     dword ptr [r14+8], 1
0x1800063e6  jnz     short loc_1800063EE
0x1800063e8  or      eax, 8
0x1800063eb  mov     [rbx+4], eax
0x1800063ee  mov     eax, 1
0x1800063f3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800063fb  inc     eax
0x1800063fd  mov     [rbx+10h], eax
0x180006400  mov     rax, [rsp+78h+arg_40]
0x180006408  xor     edi, edi
0x18000640a  test    rax, rax
0x18000640d  jz      short loc_180006414
0x18000640f  cmp     [rax], di
0x180006412  jnz     short loc_180006417
0x180006414  mov     rax, rdi
0x180006417  mov     [rbx+18h], rax
0x18000641b  call    cs:__imp_GetCurrentThreadId
0x180006421  mov     [rbx+20h], eax
0x180006424  mov     [rbx+38h], r13
0x180006428  mov     eax, [rsp+78h+arg_8]
0x18000642f  mov     [rbx+40h], eax
0x180006432  mov     [rbx+44h], ebp
0x180006435  mov     rax, [rsp+78h+arg_20]
0x18000643d  mov     [rbx+28h], rax
0x180006441  mov     [rbx+30h], r12
0x180006445  mov     rax, [rsp+78h+arg_28]
0x18000644d  mov     [rbx+88h], rax
0x180006454  mov     rax, [rsp+78h+arg_0]
0x18000645c  mov     [rbx+90h], rax
0x180006463  mov     [rbx+48h], rdi
0x180006467  xorps   xmm0, xmm0
0x18000646a  xor     eax, eax
0x18000646c  movups  xmmword ptr [rbx+68h], xmm0
0x180006470  mov     [rbx+78h], rax
0x180006474  movups  xmmword ptr [rbx+50h], xmm0
0x180006478  mov     [rbx+60h], rax
0x18000647c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180006483  test    rax, rax
0x180006486  jz      short loc_18000648F
0x180006488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000648d  jmp     short loc_180006492
0x18000648f  mov     rax, rdi
0x180006492  mov     [rbx+80h], rax
0x180006499  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800064a0  test    rax, rax
0x1800064a3  jz      short loc_1800064AD
0x1800064a5  mov     rcx, rbx
0x1800064a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064ad  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800064b4  test    rax, rax
0x1800064b7  jz      short loc_1800064CF
0x1800064b9  mov     r8d, 400h
0x1800064bf  mov     rdx, [rsp+78h+arg_60]
0x1800064c7  mov     rcx, rbx
0x1800064ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064cf  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800064d6  test    rax, rax
0x1800064d9  jz      short loc_1800064E3
0x1800064db  mov     rcx, rbx
0x1800064de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064e3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800064ea  test    rax, rax
0x1800064ed  jz      short loc_1800064FD
0x1800064ef  test    byte ptr [rbx+4], 2
0x1800064f3  jnz     short loc_1800064FD
0x1800064f5  mov     rcx, rbx
0x1800064f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064fd  cmp     [rbx+8], edi
0x180006500  jl      short loc_18000651C
0x180006502  cmp     r15d, 3
0x180006506  jnz     loc_1800065EB
0x18000650c  mov     ecx, 8000FFFFh; this
0x180006511  mov     [rbx+8], ecx
0x180006514  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006519  mov     [rbx+0Ch], eax
0x18000651c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180006523  jnz     short loc_180006544
0x180006525  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000652c  test    rax, rax
0x18000652f  jz      short loc_18000653A
0x180006531  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006536  test    al, al
0x180006538  jmp     short loc_180006542
0x18000653a  call    cs:__imp_IsDebuggerPresent
0x180006540  test    eax, eax
0x180006542  jz      short loc_18000654A
0x180006544  test    byte ptr [rbx+4], 2
0x180006548  jz      short loc_18000656E
0x18000654a  mov     rax, cs:g_pfnResultLoggingCallback
0x180006551  test    rax, rax
0x180006554  jz      short loc_1800065B2
0x180006556  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000655d  jnz     short loc_1800065B2
0x18000655f  xor     r8d, r8d
0x180006562  xor     edx, edx
0x180006564  mov     rcx, rbx
0x180006567  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000656c  jmp     short loc_1800065B2
0x18000656e  mov     ebp, 800h
0x180006573  mov     rax, cs:g_pfnResultLoggingCallback
0x18000657a  test    rax, rax
0x18000657d  jz      short loc_180006596
0x18000657f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006586  jnz     short loc_180006596
0x180006588  mov     r8d, ebp
0x18000658b  mov     rdx, rsi
0x18000658e  mov     rcx, rbx
0x180006591  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006596  cmp     [rsi], di
0x180006599  jnz     short loc_1800065A9
0x18000659b  mov     r8, rbx; unsigned __int64
0x18000659e  mov     rdx, rbp; unsigned __int16 *
0x1800065a1  mov     rcx, rsi; this
0x1800065a4  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800065a9  mov     rcx, rsi; lpOutputString
0x1800065ac  call    cs:__imp_OutputDebugStringW
0x1800065b2  test    byte ptr [rbx+4], 4
0x1800065b6  jnz     short loc_1800065C1
0x1800065b8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800065bf  jz      short loc_1800065D3
0x1800065c1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800065c8  test    rax, rax
0x1800065cb  jz      short loc_1800065D3
0x1800065cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065d2  nop
0x1800065d3  mov     rbx, [rsp+78h+arg_10]
0x1800065db  add     rsp, 40h
0x1800065df  pop     r15
0x1800065e1  pop     r14
0x1800065e3  pop     r13
0x1800065e5  pop     r12
0x1800065e7  pop     rdi
0x1800065e8  pop     rsi
0x1800065e9  pop     rbp
0x1800065ea  retn
0x1800065eb  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
