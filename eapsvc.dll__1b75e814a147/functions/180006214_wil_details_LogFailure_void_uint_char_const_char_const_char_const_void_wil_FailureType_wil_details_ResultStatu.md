# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180006214`
- end: `0x18000650d`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180003528`

## callees

- `0x180002f64`
- `0x1800057b4`
- `0x180005f50`
- `0x180006214`
- `0x180006f38`
- `0x180006f60`
- `0x18000708c`
- `0x1800070a8`
- `0x180009a4c`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006337`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006337`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006456`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006456`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800064c8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800064c8`

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
0x180006214  mov     [rsp+arg_10], rbx
0x180006219  mov     [rsp+arg_8], edx
0x18000621d  mov     [rsp+arg_0], rcx
0x180006222  push    rbp
0x180006223  push    rsi
0x180006224  push    rdi
0x180006225  push    r12
0x180006227  push    r13
0x180006229  push    r14
0x18000622b  push    r15
0x18000622d  sub     rsp, 40h
0x180006231  mov     r12, r9
0x180006234  mov     r13, r8
0x180006237  mov     r10, rcx
0x18000623a  xor     eax, eax
0x18000623c  mov     rsi, [rsp+78h+lpOutputString]
0x180006244  mov     [rsi], ax
0x180006247  mov     rax, [rsp+78h+arg_60]
0x18000624f  mov     byte ptr [rax], 0
0x180006252  mov     r14, [rsp+78h+arg_38]
0x18000625a  mov     edi, [r14]
0x18000625d  mov     rbx, [rsp+78h+arg_78]
0x180006265  mov     [rbx+8], edi
0x180006268  mov     eax, [r14+4]
0x18000626c  mov     [rbx+0Ch], eax
0x18000626f  xor     ebp, ebp
0x180006271  mov     r15d, [rsp+78h+arg_30]
0x180006279  mov     ecx, r15d
0x18000627c  test    r15d, r15d
0x18000627f  jz      short loc_1800062E7
0x180006281  sub     ecx, 1
0x180006284  jz      short loc_1800062DE
0x180006286  sub     ecx, 1
0x180006289  jz      short loc_180006299
0x18000628b  cmp     ecx, 1
0x18000628e  jnz     short loc_1800062F0
0x180006290  mov     ecx, edi; this
0x180006292  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180006297  jmp     short loc_1800062EE
0x180006299  test    edi, edi
0x18000629b  js      short loc_1800062D5
0x18000629d  mov     edi, 8007029Ch
0x1800062a2  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800062a6  mov     rax, [rsp+78h+arg_28]
0x1800062ae  mov     [rsp+78h+var_50], rax; __int64
0x1800062b3  mov     rax, [rsp+78h+arg_20]
0x1800062bb  mov     [rsp+78h+var_58], rax; __int64
0x1800062c0  mov     rcx, r10; int
0x1800062c3  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800062c8  mov     [rbx+8], edi
0x1800062cb  mov     ecx, edi; this
0x1800062cd  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800062d2  mov     [rbx+0Ch], eax
0x1800062d5  mov     ecx, edi; this
0x1800062d7  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800062dc  jmp     short loc_1800062EE
0x1800062de  mov     ecx, edi; this
0x1800062e0  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800062e5  jmp     short loc_1800062EE
0x1800062e7  mov     ecx, edi; this
0x1800062e9  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800062ee  mov     ebp, eax
0x1800062f0  mov     [rbx], r15d
0x1800062f3  mov     eax, [rsp+78h+arg_70]
0x1800062fa  mov     [rbx+4], eax
0x1800062fd  cmp     dword ptr [r14+8], 1
0x180006302  jnz     short loc_18000630A
0x180006304  or      eax, 8
0x180006307  mov     [rbx+4], eax
0x18000630a  mov     eax, 1
0x18000630f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180006317  inc     eax
0x180006319  mov     [rbx+10h], eax
0x18000631c  mov     rax, [rsp+78h+arg_40]
0x180006324  xor     edi, edi
0x180006326  test    rax, rax
0x180006329  jz      short loc_180006330
0x18000632b  cmp     [rax], di
0x18000632e  jnz     short loc_180006333
0x180006330  mov     rax, rdi
0x180006333  mov     [rbx+18h], rax
0x180006337  call    cs:__imp_GetCurrentThreadId
0x18000633d  mov     [rbx+20h], eax
0x180006340  mov     [rbx+38h], r13
0x180006344  mov     eax, [rsp+78h+arg_8]
0x18000634b  mov     [rbx+40h], eax
0x18000634e  mov     [rbx+44h], ebp
0x180006351  mov     rax, [rsp+78h+arg_20]
0x180006359  mov     [rbx+28h], rax
0x18000635d  mov     [rbx+30h], r12
0x180006361  mov     rax, [rsp+78h+arg_28]
0x180006369  mov     [rbx+88h], rax
0x180006370  mov     rax, [rsp+78h+arg_0]
0x180006378  mov     [rbx+90h], rax
0x18000637f  mov     [rbx+48h], rdi
0x180006383  xorps   xmm0, xmm0
0x180006386  xor     eax, eax
0x180006388  movups  xmmword ptr [rbx+68h], xmm0
0x18000638c  mov     [rbx+78h], rax
0x180006390  movups  xmmword ptr [rbx+50h], xmm0
0x180006394  mov     [rbx+60h], rax
0x180006398  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000639f  test    rax, rax
0x1800063a2  jz      short loc_1800063AB
0x1800063a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063a9  jmp     short loc_1800063AE
0x1800063ab  mov     rax, rdi
0x1800063ae  mov     [rbx+80h], rax
0x1800063b5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800063bc  test    rax, rax
0x1800063bf  jz      short loc_1800063C9
0x1800063c1  mov     rcx, rbx
0x1800063c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063c9  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800063d0  test    rax, rax
0x1800063d3  jz      short loc_1800063EB
0x1800063d5  mov     r8d, 400h
0x1800063db  mov     rdx, [rsp+78h+arg_60]
0x1800063e3  mov     rcx, rbx
0x1800063e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063eb  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800063f2  test    rax, rax
0x1800063f5  jz      short loc_1800063FF
0x1800063f7  mov     rcx, rbx
0x1800063fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063ff  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006406  test    rax, rax
0x180006409  jz      short loc_180006419
0x18000640b  test    byte ptr [rbx+4], 2
0x18000640f  jnz     short loc_180006419
0x180006411  mov     rcx, rbx
0x180006414  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006419  cmp     [rbx+8], edi
0x18000641c  jl      short loc_180006438
0x18000641e  cmp     r15d, 3
0x180006422  jnz     loc_180006507
0x180006428  mov     ecx, 8000FFFFh; this
0x18000642d  mov     [rbx+8], ecx
0x180006430  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006435  mov     [rbx+0Ch], eax
0x180006438  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000643f  jnz     short loc_180006460
0x180006441  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180006448  test    rax, rax
0x18000644b  jz      short loc_180006456
0x18000644d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006452  test    al, al
0x180006454  jmp     short loc_18000645E
0x180006456  call    cs:__imp_IsDebuggerPresent
0x18000645c  test    eax, eax
0x18000645e  jz      short loc_180006466
0x180006460  test    byte ptr [rbx+4], 2
0x180006464  jz      short loc_18000648A
0x180006466  mov     rax, cs:g_pfnResultLoggingCallback
0x18000646d  test    rax, rax
0x180006470  jz      short loc_1800064CE
0x180006472  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006479  jnz     short loc_1800064CE
0x18000647b  xor     r8d, r8d
0x18000647e  xor     edx, edx
0x180006480  mov     rcx, rbx
0x180006483  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006488  jmp     short loc_1800064CE
0x18000648a  mov     ebp, 800h
0x18000648f  mov     rax, cs:g_pfnResultLoggingCallback
0x180006496  test    rax, rax
0x180006499  jz      short loc_1800064B2
0x18000649b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800064a2  jnz     short loc_1800064B2
0x1800064a4  mov     r8d, ebp
0x1800064a7  mov     rdx, rsi
0x1800064aa  mov     rcx, rbx
0x1800064ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064b2  cmp     [rsi], di
0x1800064b5  jnz     short loc_1800064C5
0x1800064b7  mov     r8, rbx; unsigned __int64
0x1800064ba  mov     rdx, rbp; wchar_t *
0x1800064bd  mov     rcx, rsi; this
0x1800064c0  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1800064c5  mov     rcx, rsi; lpOutputString
0x1800064c8  call    cs:__imp_OutputDebugStringW
0x1800064ce  test    byte ptr [rbx+4], 4
0x1800064d2  jnz     short loc_1800064DD
0x1800064d4  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800064db  jz      short loc_1800064EF
0x1800064dd  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800064e4  test    rax, rax
0x1800064e7  jz      short loc_1800064EF
0x1800064e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064ee  nop
0x1800064ef  mov     rbx, [rsp+78h+arg_10]
0x1800064f7  add     rsp, 40h
0x1800064fb  pop     r15
0x1800064fd  pop     r14
0x1800064ff  pop     r13
0x180006501  pop     r12
0x180006503  pop     rdi
0x180006504  pop     rsi
0x180006505  pop     rbp
0x180006506  retn
0x180006507  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
