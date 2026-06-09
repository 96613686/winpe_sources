# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180005188`
- end: `0x180005481`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180002ce8`
- `0x180003034`

## callees

- `0x180002c28`
- `0x180004684`
- `0x180004e94`
- `0x180005188`
- `0x180005ff8`
- `0x180006020`
- `0x18000615c`
- `0x180006178`
- `0x180007b88`
- `0x180026010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800052ab`
- `KERNEL32!GetCurrentThreadId` at `0x1800052ab`
- `KERNEL32!IsDebuggerPresent` at `0x1800053ca`
- `KERNEL32!IsDebuggerPresent` at `0x1800053ca`
- `KERNEL32!OutputDebugStringW` at `0x18000543c`
- `KERNEL32!OutputDebugStringW` at `0x18000543c`

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
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v25);
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
0x180005188  mov     [rsp+arg_10], rbx
0x18000518d  mov     [rsp+arg_8], edx
0x180005191  mov     [rsp+arg_0], rcx
0x180005196  push    rbp
0x180005197  push    rsi
0x180005198  push    rdi
0x180005199  push    r12
0x18000519b  push    r13
0x18000519d  push    r14
0x18000519f  push    r15
0x1800051a1  sub     rsp, 40h
0x1800051a5  mov     r12, r9
0x1800051a8  mov     r13, r8
0x1800051ab  mov     r10, rcx
0x1800051ae  xor     eax, eax
0x1800051b0  mov     rsi, [rsp+78h+lpOutputString]
0x1800051b8  mov     [rsi], ax
0x1800051bb  mov     rax, [rsp+78h+arg_60]
0x1800051c3  mov     byte ptr [rax], 0
0x1800051c6  mov     r14, [rsp+78h+arg_38]
0x1800051ce  mov     edi, [r14]
0x1800051d1  mov     rbx, [rsp+78h+arg_78]
0x1800051d9  mov     [rbx+8], edi
0x1800051dc  mov     eax, [r14+4]
0x1800051e0  mov     [rbx+0Ch], eax
0x1800051e3  xor     ebp, ebp
0x1800051e5  mov     r15d, [rsp+78h+arg_30]
0x1800051ed  mov     ecx, r15d
0x1800051f0  test    r15d, r15d
0x1800051f3  jz      short loc_18000525B
0x1800051f5  sub     ecx, 1
0x1800051f8  jz      short loc_180005252
0x1800051fa  sub     ecx, 1
0x1800051fd  jz      short loc_18000520D
0x1800051ff  cmp     ecx, 1
0x180005202  jnz     short loc_180005264
0x180005204  mov     ecx, edi; this
0x180005206  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000520b  jmp     short loc_180005262
0x18000520d  test    edi, edi
0x18000520f  js      short loc_180005249
0x180005211  mov     edi, 8007029Ch
0x180005216  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000521a  mov     rax, [rsp+78h+arg_28]
0x180005222  mov     [rsp+78h+var_50], rax; __int64
0x180005227  mov     rax, [rsp+78h+arg_20]
0x18000522f  mov     [rsp+78h+var_58], rax; __int64
0x180005234  mov     rcx, r10; int
0x180005237  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000523c  mov     [rbx+8], edi
0x18000523f  mov     ecx, edi; this
0x180005241  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005246  mov     [rbx+0Ch], eax
0x180005249  mov     ecx, edi; this
0x18000524b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180005250  jmp     short loc_180005262
0x180005252  mov     ecx, edi; this
0x180005254  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005259  jmp     short loc_180005262
0x18000525b  mov     ecx, edi; this
0x18000525d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180005262  mov     ebp, eax
0x180005264  mov     [rbx], r15d
0x180005267  mov     eax, [rsp+78h+arg_70]
0x18000526e  mov     [rbx+4], eax
0x180005271  cmp     dword ptr [r14+8], 1
0x180005276  jnz     short loc_18000527E
0x180005278  or      eax, 8
0x18000527b  mov     [rbx+4], eax
0x18000527e  mov     eax, 1
0x180005283  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000528b  inc     eax
0x18000528d  mov     [rbx+10h], eax
0x180005290  mov     rax, [rsp+78h+arg_40]
0x180005298  xor     edi, edi
0x18000529a  test    rax, rax
0x18000529d  jz      short loc_1800052A4
0x18000529f  cmp     [rax], di
0x1800052a2  jnz     short loc_1800052A7
0x1800052a4  mov     rax, rdi
0x1800052a7  mov     [rbx+18h], rax
0x1800052ab  call    cs:__imp_GetCurrentThreadId
0x1800052b1  mov     [rbx+20h], eax
0x1800052b4  mov     [rbx+38h], r13
0x1800052b8  mov     eax, [rsp+78h+arg_8]
0x1800052bf  mov     [rbx+40h], eax
0x1800052c2  mov     [rbx+44h], ebp
0x1800052c5  mov     rax, [rsp+78h+arg_20]
0x1800052cd  mov     [rbx+28h], rax
0x1800052d1  mov     [rbx+30h], r12
0x1800052d5  mov     rax, [rsp+78h+arg_28]
0x1800052dd  mov     [rbx+88h], rax
0x1800052e4  mov     rax, [rsp+78h+arg_0]
0x1800052ec  mov     [rbx+90h], rax
0x1800052f3  mov     [rbx+48h], rdi
0x1800052f7  xorps   xmm0, xmm0
0x1800052fa  xor     eax, eax
0x1800052fc  movups  xmmword ptr [rbx+68h], xmm0
0x180005300  mov     [rbx+78h], rax
0x180005304  movups  xmmword ptr [rbx+50h], xmm0
0x180005308  mov     [rbx+60h], rax
0x18000530c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005313  test    rax, rax
0x180005316  jz      short loc_18000531F
0x180005318  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000531d  jmp     short loc_180005322
0x18000531f  mov     rax, rdi
0x180005322  mov     [rbx+80h], rax
0x180005329  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005330  test    rax, rax
0x180005333  jz      short loc_18000533D
0x180005335  mov     rcx, rbx
0x180005338  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000533d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005344  test    rax, rax
0x180005347  jz      short loc_18000535F
0x180005349  mov     r8d, 400h
0x18000534f  mov     rdx, [rsp+78h+arg_60]
0x180005357  mov     rcx, rbx
0x18000535a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000535f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005366  test    rax, rax
0x180005369  jz      short loc_180005373
0x18000536b  mov     rcx, rbx
0x18000536e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005373  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000537a  test    rax, rax
0x18000537d  jz      short loc_18000538D
0x18000537f  test    byte ptr [rbx+4], 2
0x180005383  jnz     short loc_18000538D
0x180005385  mov     rcx, rbx
0x180005388  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000538d  cmp     [rbx+8], edi
0x180005390  jl      short loc_1800053AC
0x180005392  cmp     r15d, 3
0x180005396  jnz     loc_18000547B
0x18000539c  mov     ecx, 8000FFFFh; this
0x1800053a1  mov     [rbx+8], ecx
0x1800053a4  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800053a9  mov     [rbx+0Ch], eax
0x1800053ac  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800053b3  jnz     short loc_1800053D4
0x1800053b5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800053bc  test    rax, rax
0x1800053bf  jz      short loc_1800053CA
0x1800053c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053c6  test    al, al
0x1800053c8  jmp     short loc_1800053D2
0x1800053ca  call    cs:__imp_IsDebuggerPresent
0x1800053d0  test    eax, eax
0x1800053d2  jz      short loc_1800053DA
0x1800053d4  test    byte ptr [rbx+4], 2
0x1800053d8  jz      short loc_1800053FE
0x1800053da  mov     rax, cs:g_pfnResultLoggingCallback
0x1800053e1  test    rax, rax
0x1800053e4  jz      short loc_180005442
0x1800053e6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800053ed  jnz     short loc_180005442
0x1800053ef  xor     r8d, r8d
0x1800053f2  xor     edx, edx
0x1800053f4  mov     rcx, rbx
0x1800053f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053fc  jmp     short loc_180005442
0x1800053fe  mov     ebp, 800h
0x180005403  mov     rax, cs:g_pfnResultLoggingCallback
0x18000540a  test    rax, rax
0x18000540d  jz      short loc_180005426
0x18000540f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005416  jnz     short loc_180005426
0x180005418  mov     r8d, ebp
0x18000541b  mov     rdx, rsi
0x18000541e  mov     rcx, rbx
0x180005421  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005426  cmp     [rsi], di
0x180005429  jnz     short loc_180005439
0x18000542b  mov     r8, rbx; unsigned __int64
0x18000542e  mov     rdx, rbp; wchar_t *
0x180005431  mov     rcx, rsi; this
0x180005434  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180005439  mov     rcx, rsi; lpOutputString
0x18000543c  call    cs:__imp_OutputDebugStringW
0x180005442  test    byte ptr [rbx+4], 4
0x180005446  jnz     short loc_180005451
0x180005448  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000544f  jz      short loc_180005463
0x180005451  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005458  test    rax, rax
0x18000545b  jz      short loc_180005463
0x18000545d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005462  nop
0x180005463  mov     rbx, [rsp+78h+arg_10]
0x18000546b  add     rsp, 40h
0x18000546f  pop     r15
0x180005471  pop     r14
0x180005473  pop     r13
0x180005475  pop     r12
0x180005477  pop     rdi
0x180005478  pop     rsi
0x180005479  pop     rbp
0x18000547a  retn
0x18000547b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
