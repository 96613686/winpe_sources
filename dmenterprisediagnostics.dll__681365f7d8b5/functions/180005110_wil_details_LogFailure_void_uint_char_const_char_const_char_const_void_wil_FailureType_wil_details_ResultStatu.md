# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180005110`
- end: `0x18000541c`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `780`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180002e84`
- `0x180003204`

## callees

- `0x180002dbc`
- `0x1800046d4`
- `0x180004f1c`
- `0x180005110`
- `0x180005888`
- `0x1800058b0`
- `0x1800058c4`
- `0x1800058e4`
- `0x18000748c`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005233`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005233`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005358`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005358`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800053d0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800053d0`

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
0x180005110  mov     [rsp+arg_10], rbx
0x180005115  mov     [rsp+arg_8], edx
0x180005119  mov     [rsp+arg_0], rcx
0x18000511e  push    rbp
0x18000511f  push    rsi
0x180005120  push    rdi
0x180005121  push    r12
0x180005123  push    r13
0x180005125  push    r14
0x180005127  push    r15
0x180005129  sub     rsp, 40h
0x18000512d  mov     r12, r9
0x180005130  mov     r13, r8
0x180005133  mov     r10, rcx
0x180005136  xor     eax, eax
0x180005138  mov     rsi, [rsp+78h+lpOutputString]
0x180005140  mov     [rsi], ax
0x180005143  mov     rax, [rsp+78h+arg_60]
0x18000514b  mov     byte ptr [rax], 0
0x18000514e  mov     r14, [rsp+78h+arg_38]
0x180005156  mov     edi, [r14]
0x180005159  mov     rbx, [rsp+78h+arg_78]
0x180005161  mov     [rbx+8], edi
0x180005164  mov     eax, [r14+4]
0x180005168  mov     [rbx+0Ch], eax
0x18000516b  xor     ebp, ebp
0x18000516d  mov     r15d, [rsp+78h+arg_30]
0x180005175  mov     ecx, r15d
0x180005178  test    r15d, r15d
0x18000517b  jz      short loc_1800051E3
0x18000517d  sub     ecx, 1
0x180005180  jz      short loc_1800051DA
0x180005182  sub     ecx, 1
0x180005185  jz      short loc_180005195
0x180005187  cmp     ecx, 1
0x18000518a  jnz     short loc_1800051EC
0x18000518c  mov     ecx, edi; this
0x18000518e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180005193  jmp     short loc_1800051EA
0x180005195  test    edi, edi
0x180005197  js      short loc_1800051D1
0x180005199  mov     edi, 8007029Ch
0x18000519e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800051a2  mov     rax, [rsp+78h+arg_28]
0x1800051aa  mov     [rsp+78h+var_50], rax; __int64
0x1800051af  mov     rax, [rsp+78h+arg_20]
0x1800051b7  mov     [rsp+78h+var_58], rax; __int64
0x1800051bc  mov     rcx, r10; int
0x1800051bf  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800051c4  mov     [rbx+8], edi
0x1800051c7  mov     ecx, edi; this
0x1800051c9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800051ce  mov     [rbx+0Ch], eax
0x1800051d1  mov     ecx, edi; this
0x1800051d3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800051d8  jmp     short loc_1800051EA
0x1800051da  mov     ecx, edi; this
0x1800051dc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800051e1  jmp     short loc_1800051EA
0x1800051e3  mov     ecx, edi; this
0x1800051e5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800051ea  mov     ebp, eax
0x1800051ec  mov     [rbx], r15d
0x1800051ef  mov     eax, [rsp+78h+arg_70]
0x1800051f6  mov     [rbx+4], eax
0x1800051f9  cmp     dword ptr [r14+8], 1
0x1800051fe  jnz     short loc_180005206
0x180005200  or      eax, 8
0x180005203  mov     [rbx+4], eax
0x180005206  mov     eax, 1
0x18000520b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005213  inc     eax
0x180005215  mov     [rbx+10h], eax
0x180005218  mov     rax, [rsp+78h+arg_40]
0x180005220  xor     edi, edi
0x180005222  test    rax, rax
0x180005225  jz      short loc_18000522C
0x180005227  cmp     [rax], di
0x18000522a  jnz     short loc_18000522F
0x18000522c  mov     rax, rdi
0x18000522f  mov     [rbx+18h], rax
0x180005233  call    cs:__imp_GetCurrentThreadId
0x18000523a  nop     dword ptr [rax+rax+00h]
0x18000523f  mov     [rbx+20h], eax
0x180005242  mov     [rbx+38h], r13
0x180005246  mov     eax, [rsp+78h+arg_8]
0x18000524d  mov     [rbx+40h], eax
0x180005250  mov     [rbx+44h], ebp
0x180005253  mov     rax, [rsp+78h+arg_20]
0x18000525b  mov     [rbx+28h], rax
0x18000525f  mov     [rbx+30h], r12
0x180005263  mov     rax, [rsp+78h+arg_28]
0x18000526b  mov     [rbx+88h], rax
0x180005272  mov     rax, [rsp+78h+arg_0]
0x18000527a  mov     [rbx+90h], rax
0x180005281  mov     [rbx+48h], rdi
0x180005285  xorps   xmm0, xmm0
0x180005288  xor     eax, eax
0x18000528a  movups  xmmword ptr [rbx+68h], xmm0
0x18000528e  mov     [rbx+78h], rax
0x180005292  movups  xmmword ptr [rbx+50h], xmm0
0x180005296  mov     [rbx+60h], rax
0x18000529a  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800052a1  test    rax, rax
0x1800052a4  jz      short loc_1800052AD
0x1800052a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052ab  jmp     short loc_1800052B0
0x1800052ad  mov     rax, rdi
0x1800052b0  mov     [rbx+80h], rax
0x1800052b7  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800052be  test    rax, rax
0x1800052c1  jz      short loc_1800052CB
0x1800052c3  mov     rcx, rbx
0x1800052c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052cb  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800052d2  test    rax, rax
0x1800052d5  jz      short loc_1800052ED
0x1800052d7  mov     r8d, 400h
0x1800052dd  mov     rdx, [rsp+78h+arg_60]
0x1800052e5  mov     rcx, rbx
0x1800052e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052ed  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800052f4  test    rax, rax
0x1800052f7  jz      short loc_180005301
0x1800052f9  mov     rcx, rbx
0x1800052fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005301  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005308  test    rax, rax
0x18000530b  jz      short loc_18000531B
0x18000530d  test    byte ptr [rbx+4], 2
0x180005311  jnz     short loc_18000531B
0x180005313  mov     rcx, rbx
0x180005316  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000531b  cmp     [rbx+8], edi
0x18000531e  jl      short loc_18000533A
0x180005320  cmp     r15d, 3
0x180005324  jnz     loc_180005416
0x18000532a  mov     ecx, 8000FFFFh; this
0x18000532f  mov     [rbx+8], ecx
0x180005332  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005337  mov     [rbx+0Ch], eax
0x18000533a  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180005341  jnz     short loc_180005368
0x180005343  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000534a  test    rax, rax
0x18000534d  jz      short loc_180005358
0x18000534f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005354  test    al, al
0x180005356  jmp     short loc_180005366
0x180005358  call    cs:__imp_IsDebuggerPresent
0x18000535f  nop     dword ptr [rax+rax+00h]
0x180005364  test    eax, eax
0x180005366  jz      short loc_18000536E
0x180005368  test    byte ptr [rbx+4], 2
0x18000536c  jz      short loc_180005392
0x18000536e  mov     rax, cs:g_pfnResultLoggingCallback
0x180005375  test    rax, rax
0x180005378  jz      short loc_1800053DC
0x18000537a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005381  jnz     short loc_1800053DC
0x180005383  xor     r8d, r8d
0x180005386  xor     edx, edx
0x180005388  mov     rcx, rbx
0x18000538b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005390  jmp     short loc_1800053DC
0x180005392  mov     ebp, 800h
0x180005397  mov     rax, cs:g_pfnResultLoggingCallback
0x18000539e  test    rax, rax
0x1800053a1  jz      short loc_1800053BA
0x1800053a3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800053aa  jnz     short loc_1800053BA
0x1800053ac  mov     r8d, ebp
0x1800053af  mov     rdx, rsi
0x1800053b2  mov     rcx, rbx
0x1800053b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053ba  cmp     [rsi], di
0x1800053bd  jnz     short loc_1800053CD
0x1800053bf  mov     r8, rbx; unsigned __int64
0x1800053c2  mov     rdx, rbp; unsigned __int16 *
0x1800053c5  mov     rcx, rsi; this
0x1800053c8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800053cd  mov     rcx, rsi; lpOutputString
0x1800053d0  call    cs:__imp_OutputDebugStringW
0x1800053d7  nop     dword ptr [rax+rax+00h]
0x1800053dc  test    byte ptr [rbx+4], 4
0x1800053e0  jnz     short loc_1800053EB
0x1800053e2  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800053e9  jz      short loc_1800053FD
0x1800053eb  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800053f2  test    rax, rax
0x1800053f5  jz      short loc_1800053FD
0x1800053f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053fc  nop
0x1800053fd  mov     rbx, [rsp+78h+arg_10]
0x180005405  add     rsp, 40h
0x180005409  pop     r15
0x18000540b  pop     r14
0x18000540d  pop     r13
0x18000540f  pop     r12
0x180005411  pop     rdi
0x180005412  pop     rsi
0x180005413  pop     rbp
0x180005414  retn
0x180005416  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
