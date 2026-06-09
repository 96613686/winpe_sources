# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000a344`
- end: `0x18000a63d`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180007c94`

## callees

- `0x1800076d0`
- `0x1800099e4`
- `0x18000a180`
- `0x18000a344`
- `0x18000ad38`
- `0x18000ad60`
- `0x18000ae8c`
- `0x18000aea8`
- `0x18000cedc`
- `0x180017010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000a467`
- `KERNEL32!GetCurrentThreadId` at `0x18000a467`
- `KERNEL32!OutputDebugStringW` at `0x18000a5f8`
- `KERNEL32!OutputDebugStringW` at `0x18000a5f8`
- `KERNEL32!IsDebuggerPresent` at `0x18000a586`
- `KERNEL32!IsDebuggerPresent` at `0x18000a586`

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
0x18000a344  mov     [rsp+arg_10], rbx
0x18000a349  mov     [rsp+arg_8], edx
0x18000a34d  mov     [rsp+arg_0], rcx
0x18000a352  push    rbp
0x18000a353  push    rsi
0x18000a354  push    rdi
0x18000a355  push    r12
0x18000a357  push    r13
0x18000a359  push    r14
0x18000a35b  push    r15
0x18000a35d  sub     rsp, 40h
0x18000a361  mov     r12, r9
0x18000a364  mov     r13, r8
0x18000a367  mov     r10, rcx
0x18000a36a  xor     eax, eax
0x18000a36c  mov     rsi, [rsp+78h+lpOutputString]
0x18000a374  mov     [rsi], ax
0x18000a377  mov     rax, [rsp+78h+arg_60]
0x18000a37f  mov     byte ptr [rax], 0
0x18000a382  mov     r14, [rsp+78h+arg_38]
0x18000a38a  mov     edi, [r14]
0x18000a38d  mov     rbx, [rsp+78h+arg_78]
0x18000a395  mov     [rbx+8], edi
0x18000a398  mov     eax, [r14+4]
0x18000a39c  mov     [rbx+0Ch], eax
0x18000a39f  xor     ebp, ebp
0x18000a3a1  mov     r15d, [rsp+78h+arg_30]
0x18000a3a9  mov     ecx, r15d
0x18000a3ac  test    r15d, r15d
0x18000a3af  jz      short loc_18000A417
0x18000a3b1  sub     ecx, 1
0x18000a3b4  jz      short loc_18000A40E
0x18000a3b6  sub     ecx, 1
0x18000a3b9  jz      short loc_18000A3C9
0x18000a3bb  cmp     ecx, 1
0x18000a3be  jnz     short loc_18000A420
0x18000a3c0  mov     ecx, edi; this
0x18000a3c2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000a3c7  jmp     short loc_18000A41E
0x18000a3c9  test    edi, edi
0x18000a3cb  js      short loc_18000A405
0x18000a3cd  mov     edi, 8007029Ch
0x18000a3d2  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000a3d6  mov     rax, [rsp+78h+arg_28]
0x18000a3de  mov     [rsp+78h+var_50], rax; __int64
0x18000a3e3  mov     rax, [rsp+78h+arg_20]
0x18000a3eb  mov     [rsp+78h+var_58], rax; __int64
0x18000a3f0  mov     rcx, r10; int
0x18000a3f3  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000a3f8  mov     [rbx+8], edi
0x18000a3fb  mov     ecx, edi; this
0x18000a3fd  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000a402  mov     [rbx+0Ch], eax
0x18000a405  mov     ecx, edi; this
0x18000a407  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000a40c  jmp     short loc_18000A41E
0x18000a40e  mov     ecx, edi; this
0x18000a410  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000a415  jmp     short loc_18000A41E
0x18000a417  mov     ecx, edi; this
0x18000a419  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000a41e  mov     ebp, eax
0x18000a420  mov     [rbx], r15d
0x18000a423  mov     eax, [rsp+78h+arg_70]
0x18000a42a  mov     [rbx+4], eax
0x18000a42d  cmp     dword ptr [r14+8], 1
0x18000a432  jnz     short loc_18000A43A
0x18000a434  or      eax, 8
0x18000a437  mov     [rbx+4], eax
0x18000a43a  mov     eax, 1
0x18000a43f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000a447  inc     eax
0x18000a449  mov     [rbx+10h], eax
0x18000a44c  mov     rax, [rsp+78h+arg_40]
0x18000a454  xor     edi, edi
0x18000a456  test    rax, rax
0x18000a459  jz      short loc_18000A460
0x18000a45b  cmp     [rax], di
0x18000a45e  jnz     short loc_18000A463
0x18000a460  mov     rax, rdi
0x18000a463  mov     [rbx+18h], rax
0x18000a467  call    cs:__imp_GetCurrentThreadId
0x18000a46d  mov     [rbx+20h], eax
0x18000a470  mov     [rbx+38h], r13
0x18000a474  mov     eax, [rsp+78h+arg_8]
0x18000a47b  mov     [rbx+40h], eax
0x18000a47e  mov     [rbx+44h], ebp
0x18000a481  mov     rax, [rsp+78h+arg_20]
0x18000a489  mov     [rbx+28h], rax
0x18000a48d  mov     [rbx+30h], r12
0x18000a491  mov     rax, [rsp+78h+arg_28]
0x18000a499  mov     [rbx+88h], rax
0x18000a4a0  mov     rax, [rsp+78h+arg_0]
0x18000a4a8  mov     [rbx+90h], rax
0x18000a4af  mov     [rbx+48h], rdi
0x18000a4b3  xorps   xmm0, xmm0
0x18000a4b6  xor     eax, eax
0x18000a4b8  movups  xmmword ptr [rbx+68h], xmm0
0x18000a4bc  mov     [rbx+78h], rax
0x18000a4c0  movups  xmmword ptr [rbx+50h], xmm0
0x18000a4c4  mov     [rbx+60h], rax
0x18000a4c8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000a4cf  test    rax, rax
0x18000a4d2  jz      short loc_18000A4DB
0x18000a4d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4d9  jmp     short loc_18000A4DE
0x18000a4db  mov     rax, rdi
0x18000a4de  mov     [rbx+80h], rax
0x18000a4e5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000a4ec  test    rax, rax
0x18000a4ef  jz      short loc_18000A4F9
0x18000a4f1  mov     rcx, rbx
0x18000a4f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4f9  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000a500  test    rax, rax
0x18000a503  jz      short loc_18000A51B
0x18000a505  mov     r8d, 400h
0x18000a50b  mov     rdx, [rsp+78h+arg_60]
0x18000a513  mov     rcx, rbx
0x18000a516  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a51b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a522  test    rax, rax
0x18000a525  jz      short loc_18000A52F
0x18000a527  mov     rcx, rbx
0x18000a52a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a52f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a536  test    rax, rax
0x18000a539  jz      short loc_18000A549
0x18000a53b  test    byte ptr [rbx+4], 2
0x18000a53f  jnz     short loc_18000A549
0x18000a541  mov     rcx, rbx
0x18000a544  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a549  cmp     [rbx+8], edi
0x18000a54c  jl      short loc_18000A568
0x18000a54e  cmp     r15d, 3
0x18000a552  jnz     loc_18000A637
0x18000a558  mov     ecx, 8000FFFFh; this
0x18000a55d  mov     [rbx+8], ecx
0x18000a560  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000a565  mov     [rbx+0Ch], eax
0x18000a568  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000a56f  jnz     short loc_18000A590
0x18000a571  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000a578  test    rax, rax
0x18000a57b  jz      short loc_18000A586
0x18000a57d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a582  test    al, al
0x18000a584  jmp     short loc_18000A58E
0x18000a586  call    cs:__imp_IsDebuggerPresent
0x18000a58c  test    eax, eax
0x18000a58e  jz      short loc_18000A596
0x18000a590  test    byte ptr [rbx+4], 2
0x18000a594  jz      short loc_18000A5BA
0x18000a596  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a59d  test    rax, rax
0x18000a5a0  jz      short loc_18000A5FE
0x18000a5a2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000a5a9  jnz     short loc_18000A5FE
0x18000a5ab  xor     r8d, r8d
0x18000a5ae  xor     edx, edx
0x18000a5b0  mov     rcx, rbx
0x18000a5b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5b8  jmp     short loc_18000A5FE
0x18000a5ba  mov     ebp, 800h
0x18000a5bf  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a5c6  test    rax, rax
0x18000a5c9  jz      short loc_18000A5E2
0x18000a5cb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000a5d2  jnz     short loc_18000A5E2
0x18000a5d4  mov     r8d, ebp
0x18000a5d7  mov     rdx, rsi
0x18000a5da  mov     rcx, rbx
0x18000a5dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5e2  cmp     [rsi], di
0x18000a5e5  jnz     short loc_18000A5F5
0x18000a5e7  mov     r8, rbx; unsigned __int64
0x18000a5ea  mov     rdx, rbp; unsigned __int16 *
0x18000a5ed  mov     rcx, rsi; this
0x18000a5f0  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000a5f5  mov     rcx, rsi; lpOutputString
0x18000a5f8  call    cs:__imp_OutputDebugStringW
0x18000a5fe  test    byte ptr [rbx+4], 4
0x18000a602  jnz     short loc_18000A60D
0x18000a604  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000a60b  jz      short loc_18000A61F
0x18000a60d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000a614  test    rax, rax
0x18000a617  jz      short loc_18000A61F
0x18000a619  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a61e  nop
0x18000a61f  mov     rbx, [rsp+78h+arg_10]
0x18000a627  add     rsp, 40h
0x18000a62b  pop     r15
0x18000a62d  pop     r14
0x18000a62f  pop     r13
0x18000a631  pop     r12
0x18000a633  pop     rdi
0x18000a634  pop     rsi
0x18000a635  pop     rbp
0x18000a636  retn
0x18000a637  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
