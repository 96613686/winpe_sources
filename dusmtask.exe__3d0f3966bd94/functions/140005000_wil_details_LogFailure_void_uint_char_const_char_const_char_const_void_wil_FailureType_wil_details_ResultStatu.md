# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140005000`
- end: `0x1400052f9`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140002ff4`

## callees

- `0x140002690`
- `0x140004684`
- `0x140004e3c`
- `0x140005000`
- `0x14000561c`
- `0x140005640`
- `0x140005654`
- `0x140005670`
- `0x140006ccc`
- `0x140008010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005123`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005123`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140005242`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140005242`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400052b4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400052b4`

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
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v23);
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
0x140005000  mov     [rsp+arg_10], rbx
0x140005005  mov     [rsp+arg_8], edx
0x140005009  mov     [rsp+arg_0], rcx
0x14000500e  push    rbp
0x14000500f  push    rsi
0x140005010  push    rdi
0x140005011  push    r12
0x140005013  push    r13
0x140005015  push    r14
0x140005017  push    r15
0x140005019  sub     rsp, 40h
0x14000501d  mov     r12, r9
0x140005020  mov     r13, r8
0x140005023  mov     r10, rcx
0x140005026  xor     eax, eax
0x140005028  mov     rsi, [rsp+78h+lpOutputString]
0x140005030  mov     [rsi], ax
0x140005033  mov     rax, [rsp+78h+arg_60]
0x14000503b  mov     byte ptr [rax], 0
0x14000503e  mov     r14, [rsp+78h+arg_38]
0x140005046  mov     edi, [r14]
0x140005049  mov     rbx, [rsp+78h+arg_78]
0x140005051  mov     [rbx+8], edi
0x140005054  mov     eax, [r14+4]
0x140005058  mov     [rbx+0Ch], eax
0x14000505b  xor     ebp, ebp
0x14000505d  mov     r15d, [rsp+78h+arg_30]
0x140005065  mov     ecx, r15d
0x140005068  test    r15d, r15d
0x14000506b  jz      short loc_1400050D3
0x14000506d  sub     ecx, 1
0x140005070  jz      short loc_1400050CA
0x140005072  sub     ecx, 1
0x140005075  jz      short loc_140005085
0x140005077  cmp     ecx, 1
0x14000507a  jnz     short loc_1400050DC
0x14000507c  mov     ecx, edi; this
0x14000507e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140005083  jmp     short loc_1400050DA
0x140005085  test    edi, edi
0x140005087  js      short loc_1400050C1
0x140005089  mov     edi, 8007029Ch
0x14000508e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x140005092  mov     rax, [rsp+78h+arg_28]
0x14000509a  mov     [rsp+78h+var_50], rax; __int64
0x14000509f  mov     rax, [rsp+78h+arg_20]
0x1400050a7  mov     [rsp+78h+var_58], rax; __int64
0x1400050ac  mov     rcx, r10; int
0x1400050af  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1400050b4  mov     [rbx+8], edi
0x1400050b7  mov     ecx, edi; this
0x1400050b9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400050be  mov     [rbx+0Ch], eax
0x1400050c1  mov     ecx, edi; this
0x1400050c3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1400050c8  jmp     short loc_1400050DA
0x1400050ca  mov     ecx, edi; this
0x1400050cc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1400050d1  jmp     short loc_1400050DA
0x1400050d3  mov     ecx, edi; this
0x1400050d5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1400050da  mov     ebp, eax
0x1400050dc  mov     [rbx], r15d
0x1400050df  mov     eax, [rsp+78h+arg_70]
0x1400050e6  mov     [rbx+4], eax
0x1400050e9  cmp     dword ptr [r14+8], 1
0x1400050ee  jnz     short loc_1400050F6
0x1400050f0  or      eax, 8
0x1400050f3  mov     [rbx+4], eax
0x1400050f6  mov     eax, 1
0x1400050fb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140005103  inc     eax
0x140005105  mov     [rbx+10h], eax
0x140005108  mov     rax, [rsp+78h+arg_40]
0x140005110  xor     edi, edi
0x140005112  test    rax, rax
0x140005115  jz      short loc_14000511C
0x140005117  cmp     [rax], di
0x14000511a  jnz     short loc_14000511F
0x14000511c  mov     rax, rdi
0x14000511f  mov     [rbx+18h], rax
0x140005123  call    cs:__imp_GetCurrentThreadId
0x140005129  mov     [rbx+20h], eax
0x14000512c  mov     [rbx+38h], r13
0x140005130  mov     eax, [rsp+78h+arg_8]
0x140005137  mov     [rbx+40h], eax
0x14000513a  mov     [rbx+44h], ebp
0x14000513d  mov     rax, [rsp+78h+arg_20]
0x140005145  mov     [rbx+28h], rax
0x140005149  mov     [rbx+30h], r12
0x14000514d  mov     rax, [rsp+78h+arg_28]
0x140005155  mov     [rbx+88h], rax
0x14000515c  mov     rax, [rsp+78h+arg_0]
0x140005164  mov     [rbx+90h], rax
0x14000516b  mov     [rbx+48h], rdi
0x14000516f  xorps   xmm0, xmm0
0x140005172  xor     eax, eax
0x140005174  movups  xmmword ptr [rbx+68h], xmm0
0x140005178  mov     [rbx+78h], rax
0x14000517c  movups  xmmword ptr [rbx+50h], xmm0
0x140005180  mov     [rbx+60h], rax
0x140005184  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000518b  test    rax, rax
0x14000518e  jz      short loc_140005197
0x140005190  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005195  jmp     short loc_14000519A
0x140005197  mov     rax, rdi
0x14000519a  mov     [rbx+80h], rax
0x1400051a1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400051a8  test    rax, rax
0x1400051ab  jz      short loc_1400051B5
0x1400051ad  mov     rcx, rbx
0x1400051b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400051b5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400051bc  test    rax, rax
0x1400051bf  jz      short loc_1400051D7
0x1400051c1  mov     r8d, 400h
0x1400051c7  mov     rdx, [rsp+78h+arg_60]
0x1400051cf  mov     rcx, rbx
0x1400051d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400051d7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400051de  test    rax, rax
0x1400051e1  jz      short loc_1400051EB
0x1400051e3  mov     rcx, rbx
0x1400051e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400051eb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400051f2  test    rax, rax
0x1400051f5  jz      short loc_140005205
0x1400051f7  test    byte ptr [rbx+4], 2
0x1400051fb  jnz     short loc_140005205
0x1400051fd  mov     rcx, rbx
0x140005200  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005205  cmp     [rbx+8], edi
0x140005208  jl      short loc_140005224
0x14000520a  cmp     r15d, 3
0x14000520e  jnz     loc_1400052F3
0x140005214  mov     ecx, 8000FFFFh; this
0x140005219  mov     [rbx+8], ecx
0x14000521c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140005221  mov     [rbx+0Ch], eax
0x140005224  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x14000522b  jnz     short loc_14000524C
0x14000522d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140005234  test    rax, rax
0x140005237  jz      short loc_140005242
0x140005239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000523e  test    al, al
0x140005240  jmp     short loc_14000524A
0x140005242  call    cs:__imp_IsDebuggerPresent
0x140005248  test    eax, eax
0x14000524a  jz      short loc_140005252
0x14000524c  test    byte ptr [rbx+4], 2
0x140005250  jz      short loc_140005276
0x140005252  mov     rax, cs:g_pfnResultLoggingCallback
0x140005259  test    rax, rax
0x14000525c  jz      short loc_1400052BA
0x14000525e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140005265  jnz     short loc_1400052BA
0x140005267  xor     r8d, r8d
0x14000526a  xor     edx, edx
0x14000526c  mov     rcx, rbx
0x14000526f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005274  jmp     short loc_1400052BA
0x140005276  mov     ebp, 800h
0x14000527b  mov     rax, cs:g_pfnResultLoggingCallback
0x140005282  test    rax, rax
0x140005285  jz      short loc_14000529E
0x140005287  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14000528e  jnz     short loc_14000529E
0x140005290  mov     r8d, ebp
0x140005293  mov     rdx, rsi
0x140005296  mov     rcx, rbx
0x140005299  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000529e  cmp     [rsi], di
0x1400052a1  jnz     short loc_1400052B1
0x1400052a3  mov     r8, rbx; unsigned __int64
0x1400052a6  mov     rdx, rbp; wchar_t *
0x1400052a9  mov     rcx, rsi; this
0x1400052ac  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1400052b1  mov     rcx, rsi; lpOutputString
0x1400052b4  call    cs:__imp_OutputDebugStringW
0x1400052ba  test    byte ptr [rbx+4], 4
0x1400052be  jnz     short loc_1400052C9
0x1400052c0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1400052c7  jz      short loc_1400052DB
0x1400052c9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400052d0  test    rax, rax
0x1400052d3  jz      short loc_1400052DB
0x1400052d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400052da  nop
0x1400052db  mov     rbx, [rsp+78h+arg_10]
0x1400052e3  add     rsp, 40h
0x1400052e7  pop     r15
0x1400052e9  pop     r14
0x1400052eb  pop     r13
0x1400052ed  pop     r12
0x1400052ef  pop     rdi
0x1400052f0  pop     rsi
0x1400052f1  pop     rbp
0x1400052f2  retn
0x1400052f3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
