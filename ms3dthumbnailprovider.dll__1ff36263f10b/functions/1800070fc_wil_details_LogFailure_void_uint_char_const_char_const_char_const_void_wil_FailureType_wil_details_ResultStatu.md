# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800070fc`
- end: `0x1800073f5`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180004cb0`

## callees

- `0x1800046ec`
- `0x1800065f4`
- `0x180006e5c`
- `0x1800070fc`
- `0x180007de0`
- `0x180007e00`
- `0x180007e14`
- `0x180007e30`
- `0x1800099a8`
- `0x18000b010`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x1800073b0`
- `KERNEL32!OutputDebugStringW` at `0x1800073b0`
- `KERNEL32!IsDebuggerPresent` at `0x18000733e`
- `KERNEL32!IsDebuggerPresent` at `0x18000733e`
- `KERNEL32!GetCurrentThreadId` at `0x18000721f`
- `KERNEL32!GetCurrentThreadId` at `0x18000721f`

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
0x1800070fc  mov     [rsp+arg_10], rbx
0x180007101  mov     [rsp+arg_8], edx
0x180007105  mov     [rsp+arg_0], rcx
0x18000710a  push    rbp
0x18000710b  push    rsi
0x18000710c  push    rdi
0x18000710d  push    r12
0x18000710f  push    r13
0x180007111  push    r14
0x180007113  push    r15
0x180007115  sub     rsp, 40h
0x180007119  mov     r12, r9
0x18000711c  mov     r13, r8
0x18000711f  mov     r10, rcx
0x180007122  xor     eax, eax
0x180007124  mov     rsi, [rsp+78h+lpOutputString]
0x18000712c  mov     [rsi], ax
0x18000712f  mov     rax, [rsp+78h+arg_60]
0x180007137  mov     byte ptr [rax], 0
0x18000713a  mov     r14, [rsp+78h+arg_38]
0x180007142  mov     edi, [r14]
0x180007145  mov     rbx, [rsp+78h+arg_78]
0x18000714d  mov     [rbx+8], edi
0x180007150  mov     eax, [r14+4]
0x180007154  mov     [rbx+0Ch], eax
0x180007157  xor     ebp, ebp
0x180007159  mov     r15d, [rsp+78h+arg_30]
0x180007161  mov     ecx, r15d
0x180007164  test    r15d, r15d
0x180007167  jz      short loc_1800071CF
0x180007169  sub     ecx, 1
0x18000716c  jz      short loc_1800071C6
0x18000716e  sub     ecx, 1
0x180007171  jz      short loc_180007181
0x180007173  cmp     ecx, 1
0x180007176  jnz     short loc_1800071D8
0x180007178  mov     ecx, edi; this
0x18000717a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000717f  jmp     short loc_1800071D6
0x180007181  test    edi, edi
0x180007183  js      short loc_1800071BD
0x180007185  mov     edi, 8007029Ch
0x18000718a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000718e  mov     rax, [rsp+78h+arg_28]
0x180007196  mov     [rsp+78h+var_50], rax; __int64
0x18000719b  mov     rax, [rsp+78h+arg_20]
0x1800071a3  mov     [rsp+78h+var_58], rax; __int64
0x1800071a8  mov     rcx, r10; int
0x1800071ab  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800071b0  mov     [rbx+8], edi
0x1800071b3  mov     ecx, edi; this
0x1800071b5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800071ba  mov     [rbx+0Ch], eax
0x1800071bd  mov     ecx, edi; this
0x1800071bf  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800071c4  jmp     short loc_1800071D6
0x1800071c6  mov     ecx, edi; this
0x1800071c8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800071cd  jmp     short loc_1800071D6
0x1800071cf  mov     ecx, edi; this
0x1800071d1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800071d6  mov     ebp, eax
0x1800071d8  mov     [rbx], r15d
0x1800071db  mov     eax, [rsp+78h+arg_70]
0x1800071e2  mov     [rbx+4], eax
0x1800071e5  cmp     dword ptr [r14+8], 1
0x1800071ea  jnz     short loc_1800071F2
0x1800071ec  or      eax, 8
0x1800071ef  mov     [rbx+4], eax
0x1800071f2  mov     eax, 1
0x1800071f7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800071ff  inc     eax
0x180007201  mov     [rbx+10h], eax
0x180007204  mov     rax, [rsp+78h+arg_40]
0x18000720c  xor     edi, edi
0x18000720e  test    rax, rax
0x180007211  jz      short loc_180007218
0x180007213  cmp     [rax], di
0x180007216  jnz     short loc_18000721B
0x180007218  mov     rax, rdi
0x18000721b  mov     [rbx+18h], rax
0x18000721f  call    cs:__imp_GetCurrentThreadId
0x180007225  mov     [rbx+20h], eax
0x180007228  mov     [rbx+38h], r13
0x18000722c  mov     eax, [rsp+78h+arg_8]
0x180007233  mov     [rbx+40h], eax
0x180007236  mov     [rbx+44h], ebp
0x180007239  mov     rax, [rsp+78h+arg_20]
0x180007241  mov     [rbx+28h], rax
0x180007245  mov     [rbx+30h], r12
0x180007249  mov     rax, [rsp+78h+arg_28]
0x180007251  mov     [rbx+88h], rax
0x180007258  mov     rax, [rsp+78h+arg_0]
0x180007260  mov     [rbx+90h], rax
0x180007267  mov     [rbx+48h], rdi
0x18000726b  xorps   xmm0, xmm0
0x18000726e  xor     eax, eax
0x180007270  movups  xmmword ptr [rbx+68h], xmm0
0x180007274  mov     [rbx+78h], rax
0x180007278  movups  xmmword ptr [rbx+50h], xmm0
0x18000727c  mov     [rbx+60h], rax
0x180007280  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180007287  test    rax, rax
0x18000728a  jz      short loc_180007293
0x18000728c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007291  jmp     short loc_180007296
0x180007293  mov     rax, rdi
0x180007296  mov     [rbx+80h], rax
0x18000729d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800072a4  test    rax, rax
0x1800072a7  jz      short loc_1800072B1
0x1800072a9  mov     rcx, rbx
0x1800072ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072b1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800072b8  test    rax, rax
0x1800072bb  jz      short loc_1800072D3
0x1800072bd  mov     r8d, 400h
0x1800072c3  mov     rdx, [rsp+78h+arg_60]
0x1800072cb  mov     rcx, rbx
0x1800072ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072d3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800072da  test    rax, rax
0x1800072dd  jz      short loc_1800072E7
0x1800072df  mov     rcx, rbx
0x1800072e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072e7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800072ee  test    rax, rax
0x1800072f1  jz      short loc_180007301
0x1800072f3  test    byte ptr [rbx+4], 2
0x1800072f7  jnz     short loc_180007301
0x1800072f9  mov     rcx, rbx
0x1800072fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007301  cmp     [rbx+8], edi
0x180007304  jl      short loc_180007320
0x180007306  cmp     r15d, 3
0x18000730a  jnz     loc_1800073EF
0x180007310  mov     ecx, 8000FFFFh; this
0x180007315  mov     [rbx+8], ecx
0x180007318  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000731d  mov     [rbx+0Ch], eax
0x180007320  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180007327  jnz     short loc_180007348
0x180007329  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180007330  test    rax, rax
0x180007333  jz      short loc_18000733E
0x180007335  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000733a  test    al, al
0x18000733c  jmp     short loc_180007346
0x18000733e  call    cs:__imp_IsDebuggerPresent
0x180007344  test    eax, eax
0x180007346  jz      short loc_18000734E
0x180007348  test    byte ptr [rbx+4], 2
0x18000734c  jz      short loc_180007372
0x18000734e  mov     rax, cs:g_pfnResultLoggingCallback
0x180007355  test    rax, rax
0x180007358  jz      short loc_1800073B6
0x18000735a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180007361  jnz     short loc_1800073B6
0x180007363  xor     r8d, r8d
0x180007366  xor     edx, edx
0x180007368  mov     rcx, rbx
0x18000736b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007370  jmp     short loc_1800073B6
0x180007372  mov     ebp, 800h
0x180007377  mov     rax, cs:g_pfnResultLoggingCallback
0x18000737e  test    rax, rax
0x180007381  jz      short loc_18000739A
0x180007383  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000738a  jnz     short loc_18000739A
0x18000738c  mov     r8d, ebp
0x18000738f  mov     rdx, rsi
0x180007392  mov     rcx, rbx
0x180007395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000739a  cmp     [rsi], di
0x18000739d  jnz     short loc_1800073AD
0x18000739f  mov     r8, rbx; unsigned __int64
0x1800073a2  mov     rdx, rbp; unsigned __int16 *
0x1800073a5  mov     rcx, rsi; this
0x1800073a8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800073ad  mov     rcx, rsi; lpOutputString
0x1800073b0  call    cs:__imp_OutputDebugStringW
0x1800073b6  test    byte ptr [rbx+4], 4
0x1800073ba  jnz     short loc_1800073C5
0x1800073bc  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800073c3  jz      short loc_1800073D7
0x1800073c5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800073cc  test    rax, rax
0x1800073cf  jz      short loc_1800073D7
0x1800073d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073d6  nop
0x1800073d7  mov     rbx, [rsp+78h+arg_10]
0x1800073df  add     rsp, 40h
0x1800073e3  pop     r15
0x1800073e5  pop     r14
0x1800073e7  pop     r13
0x1800073e9  pop     r12
0x1800073eb  pop     rdi
0x1800073ec  pop     rsi
0x1800073ed  pop     rbp
0x1800073ee  retn
0x1800073ef  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
