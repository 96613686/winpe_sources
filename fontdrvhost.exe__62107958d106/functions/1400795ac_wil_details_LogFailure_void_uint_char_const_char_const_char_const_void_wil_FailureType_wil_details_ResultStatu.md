# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1400795ac`
- end: `0x1400798a5`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1400773c4`
- `0x140077710`

## callees

- `0x140077304`
- `0x140078a54`
- `0x1400792b4`
- `0x1400795ac`
- `0x140079f90`
- `0x140079fb0`
- `0x14007a100`
- `0x14007a11c`
- `0x14007b754`
- `0x140098010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x1400797ee`
- `KERNEL32!IsDebuggerPresent` at `0x1400797ee`
- `KERNEL32!OutputDebugStringW` at `0x140079860`
- `KERNEL32!OutputDebugStringW` at `0x140079860`
- `KERNEL32!GetCurrentThreadId` at `0x1400796cf`
- `KERNEL32!GetCurrentThreadId` at `0x1400796cf`

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
0x1400795ac  mov     [rsp+arg_10], rbx
0x1400795b1  mov     [rsp+arg_8], edx
0x1400795b5  mov     [rsp+arg_0], rcx
0x1400795ba  push    rbp
0x1400795bb  push    rsi
0x1400795bc  push    rdi
0x1400795bd  push    r12
0x1400795bf  push    r13
0x1400795c1  push    r14
0x1400795c3  push    r15
0x1400795c5  sub     rsp, 40h
0x1400795c9  mov     r12, r9
0x1400795cc  mov     r13, r8
0x1400795cf  mov     r10, rcx
0x1400795d2  xor     eax, eax
0x1400795d4  mov     rsi, [rsp+78h+lpOutputString]
0x1400795dc  mov     [rsi], ax
0x1400795df  mov     rax, [rsp+78h+arg_60]
0x1400795e7  mov     byte ptr [rax], 0
0x1400795ea  mov     r14, [rsp+78h+arg_38]
0x1400795f2  mov     edi, [r14]
0x1400795f5  mov     rbx, [rsp+78h+arg_78]
0x1400795fd  mov     [rbx+8], edi
0x140079600  mov     eax, [r14+4]
0x140079604  mov     [rbx+0Ch], eax
0x140079607  xor     ebp, ebp
0x140079609  mov     r15d, [rsp+78h+arg_30]
0x140079611  mov     ecx, r15d
0x140079614  test    r15d, r15d
0x140079617  jz      short loc_14007967F
0x140079619  sub     ecx, 1
0x14007961c  jz      short loc_140079676
0x14007961e  sub     ecx, 1
0x140079621  jz      short loc_140079631
0x140079623  cmp     ecx, 1
0x140079626  jnz     short loc_140079688
0x140079628  mov     ecx, edi; this
0x14007962a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x14007962f  jmp     short loc_140079686
0x140079631  test    edi, edi
0x140079633  js      short loc_14007966D
0x140079635  mov     edi, 8007029Ch
0x14007963a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x14007963e  mov     rax, [rsp+78h+arg_28]
0x140079646  mov     [rsp+78h+var_50], rax; __int64
0x14007964b  mov     rax, [rsp+78h+arg_20]
0x140079653  mov     [rsp+78h+var_58], rax; __int64
0x140079658  mov     rcx, r10; int
0x14007965b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140079660  mov     [rbx+8], edi
0x140079663  mov     ecx, edi; this
0x140079665  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14007966a  mov     [rbx+0Ch], eax
0x14007966d  mov     ecx, edi; this
0x14007966f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140079674  jmp     short loc_140079686
0x140079676  mov     ecx, edi; this
0x140079678  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x14007967d  jmp     short loc_140079686
0x14007967f  mov     ecx, edi; this
0x140079681  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140079686  mov     ebp, eax
0x140079688  mov     [rbx], r15d
0x14007968b  mov     eax, [rsp+78h+arg_70]
0x140079692  mov     [rbx+4], eax
0x140079695  cmp     dword ptr [r14+8], 1
0x14007969a  jnz     short loc_1400796A2
0x14007969c  or      eax, 8
0x14007969f  mov     [rbx+4], eax
0x1400796a2  mov     eax, 1
0x1400796a7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400796af  inc     eax
0x1400796b1  mov     [rbx+10h], eax
0x1400796b4  mov     rax, [rsp+78h+arg_40]
0x1400796bc  xor     edi, edi
0x1400796be  test    rax, rax
0x1400796c1  jz      short loc_1400796C8
0x1400796c3  cmp     [rax], di
0x1400796c6  jnz     short loc_1400796CB
0x1400796c8  mov     rax, rdi
0x1400796cb  mov     [rbx+18h], rax
0x1400796cf  call    cs:__imp_GetCurrentThreadId
0x1400796d5  mov     [rbx+20h], eax
0x1400796d8  mov     [rbx+38h], r13
0x1400796dc  mov     eax, [rsp+78h+arg_8]
0x1400796e3  mov     [rbx+40h], eax
0x1400796e6  mov     [rbx+44h], ebp
0x1400796e9  mov     rax, [rsp+78h+arg_20]
0x1400796f1  mov     [rbx+28h], rax
0x1400796f5  mov     [rbx+30h], r12
0x1400796f9  mov     rax, [rsp+78h+arg_28]
0x140079701  mov     [rbx+88h], rax
0x140079708  mov     rax, [rsp+78h+arg_0]
0x140079710  mov     [rbx+90h], rax
0x140079717  mov     [rbx+48h], rdi
0x14007971b  xorps   xmm0, xmm0
0x14007971e  xor     eax, eax
0x140079720  movups  xmmword ptr [rbx+68h], xmm0
0x140079724  mov     [rbx+78h], rax
0x140079728  movups  xmmword ptr [rbx+50h], xmm0
0x14007972c  mov     [rbx+60h], rax
0x140079730  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140079737  test    rax, rax
0x14007973a  jz      short loc_140079743
0x14007973c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140079741  jmp     short loc_140079746
0x140079743  mov     rax, rdi
0x140079746  mov     [rbx+80h], rax
0x14007974d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140079754  test    rax, rax
0x140079757  jz      short loc_140079761
0x140079759  mov     rcx, rbx
0x14007975c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140079761  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140079768  test    rax, rax
0x14007976b  jz      short loc_140079783
0x14007976d  mov     r8d, 400h
0x140079773  mov     rdx, [rsp+78h+arg_60]
0x14007977b  mov     rcx, rbx
0x14007977e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140079783  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14007978a  test    rax, rax
0x14007978d  jz      short loc_140079797
0x14007978f  mov     rcx, rbx
0x140079792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140079797  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14007979e  test    rax, rax
0x1400797a1  jz      short loc_1400797B1
0x1400797a3  test    byte ptr [rbx+4], 2
0x1400797a7  jnz     short loc_1400797B1
0x1400797a9  mov     rcx, rbx
0x1400797ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400797b1  cmp     [rbx+8], edi
0x1400797b4  jl      short loc_1400797D0
0x1400797b6  cmp     r15d, 3
0x1400797ba  jnz     loc_14007989F
0x1400797c0  mov     ecx, 8000FFFFh; this
0x1400797c5  mov     [rbx+8], ecx
0x1400797c8  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400797cd  mov     [rbx+0Ch], eax
0x1400797d0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1400797d7  jnz     short loc_1400797F8
0x1400797d9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400797e0  test    rax, rax
0x1400797e3  jz      short loc_1400797EE
0x1400797e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400797ea  test    al, al
0x1400797ec  jmp     short loc_1400797F6
0x1400797ee  call    cs:__imp_IsDebuggerPresent
0x1400797f4  test    eax, eax
0x1400797f6  jz      short loc_1400797FE
0x1400797f8  test    byte ptr [rbx+4], 2
0x1400797fc  jz      short loc_140079822
0x1400797fe  mov     rax, cs:g_pfnResultLoggingCallback
0x140079805  test    rax, rax
0x140079808  jz      short loc_140079866
0x14007980a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140079811  jnz     short loc_140079866
0x140079813  xor     r8d, r8d
0x140079816  xor     edx, edx
0x140079818  mov     rcx, rbx
0x14007981b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140079820  jmp     short loc_140079866
0x140079822  mov     ebp, 800h
0x140079827  mov     rax, cs:g_pfnResultLoggingCallback
0x14007982e  test    rax, rax
0x140079831  jz      short loc_14007984A
0x140079833  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14007983a  jnz     short loc_14007984A
0x14007983c  mov     r8d, ebp
0x14007983f  mov     rdx, rsi
0x140079842  mov     rcx, rbx
0x140079845  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007984a  cmp     [rsi], di
0x14007984d  jnz     short loc_14007985D
0x14007984f  mov     r8, rbx; unsigned __int64
0x140079852  mov     rdx, rbp; unsigned __int16 *
0x140079855  mov     rcx, rsi; this
0x140079858  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14007985d  mov     rcx, rsi; lpOutputString
0x140079860  call    cs:__imp_OutputDebugStringW
0x140079866  test    byte ptr [rbx+4], 4
0x14007986a  jnz     short loc_140079875
0x14007986c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x140079873  jz      short loc_140079887
0x140079875  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14007987c  test    rax, rax
0x14007987f  jz      short loc_140079887
0x140079881  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140079886  nop
0x140079887  mov     rbx, [rsp+78h+arg_10]
0x14007988f  add     rsp, 40h
0x140079893  pop     r15
0x140079895  pop     r14
0x140079897  pop     r13
0x140079899  pop     r12
0x14007989b  pop     rdi
0x14007989c  pop     rsi
0x14007989d  pop     rbp
0x14007989e  retn
0x14007989f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
