# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180004dfc`
- end: `0x180005108`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `780`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180003404`
- `0x180003784`
- `0x1800145d4`

## callees

- `0x18000333c`
- `0x1800043c4`
- `0x180004c08`
- `0x180004dfc`
- `0x18000553c`
- `0x180005560`
- `0x180005574`
- `0x180005594`
- `0x18000633c`
- `0x18001a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004f1f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004f1f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005044`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005044`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800050bc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800050bc`

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
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v25);
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
0x180004dfc  mov     [rsp+arg_10], rbx
0x180004e01  mov     [rsp+arg_8], edx
0x180004e05  mov     [rsp+arg_0], rcx
0x180004e0a  push    rbp
0x180004e0b  push    rsi
0x180004e0c  push    rdi
0x180004e0d  push    r12
0x180004e0f  push    r13
0x180004e11  push    r14
0x180004e13  push    r15
0x180004e15  sub     rsp, 40h
0x180004e19  mov     r12, r9
0x180004e1c  mov     r13, r8
0x180004e1f  mov     r10, rcx
0x180004e22  xor     eax, eax
0x180004e24  mov     rsi, [rsp+78h+lpOutputString]
0x180004e2c  mov     [rsi], ax
0x180004e2f  mov     rax, [rsp+78h+arg_60]
0x180004e37  mov     byte ptr [rax], 0
0x180004e3a  mov     r14, [rsp+78h+arg_38]
0x180004e42  mov     edi, [r14]
0x180004e45  mov     rbx, [rsp+78h+arg_78]
0x180004e4d  mov     [rbx+8], edi
0x180004e50  mov     eax, [r14+4]
0x180004e54  mov     [rbx+0Ch], eax
0x180004e57  xor     ebp, ebp
0x180004e59  mov     r15d, [rsp+78h+arg_30]
0x180004e61  mov     ecx, r15d
0x180004e64  test    r15d, r15d
0x180004e67  jz      short loc_180004ECF
0x180004e69  sub     ecx, 1
0x180004e6c  jz      short loc_180004EC6
0x180004e6e  sub     ecx, 1
0x180004e71  jz      short loc_180004E81
0x180004e73  cmp     ecx, 1
0x180004e76  jnz     short loc_180004ED8
0x180004e78  mov     ecx, edi; this
0x180004e7a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180004e7f  jmp     short loc_180004ED6
0x180004e81  test    edi, edi
0x180004e83  js      short loc_180004EBD
0x180004e85  mov     edi, 8007029Ch
0x180004e8a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180004e8e  mov     rax, [rsp+78h+arg_28]
0x180004e96  mov     [rsp+78h+var_50], rax; __int64
0x180004e9b  mov     rax, [rsp+78h+arg_20]
0x180004ea3  mov     [rsp+78h+var_58], rax; __int64
0x180004ea8  mov     rcx, r10; int
0x180004eab  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180004eb0  mov     [rbx+8], edi
0x180004eb3  mov     ecx, edi; this
0x180004eb5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004eba  mov     [rbx+0Ch], eax
0x180004ebd  mov     ecx, edi; this
0x180004ebf  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180004ec4  jmp     short loc_180004ED6
0x180004ec6  mov     ecx, edi; this
0x180004ec8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004ecd  jmp     short loc_180004ED6
0x180004ecf  mov     ecx, edi; this
0x180004ed1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180004ed6  mov     ebp, eax
0x180004ed8  mov     [rbx], r15d
0x180004edb  mov     eax, [rsp+78h+arg_70]
0x180004ee2  mov     [rbx+4], eax
0x180004ee5  cmp     dword ptr [r14+8], 1
0x180004eea  jnz     short loc_180004EF2
0x180004eec  or      eax, 8
0x180004eef  mov     [rbx+4], eax
0x180004ef2  mov     eax, 1
0x180004ef7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004eff  inc     eax
0x180004f01  mov     [rbx+10h], eax
0x180004f04  mov     rax, [rsp+78h+arg_40]
0x180004f0c  xor     edi, edi
0x180004f0e  test    rax, rax
0x180004f11  jz      short loc_180004F18
0x180004f13  cmp     [rax], di
0x180004f16  jnz     short loc_180004F1B
0x180004f18  mov     rax, rdi
0x180004f1b  mov     [rbx+18h], rax
0x180004f1f  call    cs:__imp_GetCurrentThreadId
0x180004f26  nop     dword ptr [rax+rax+00h]
0x180004f2b  mov     [rbx+20h], eax
0x180004f2e  mov     [rbx+38h], r13
0x180004f32  mov     eax, [rsp+78h+arg_8]
0x180004f39  mov     [rbx+40h], eax
0x180004f3c  mov     [rbx+44h], ebp
0x180004f3f  mov     rax, [rsp+78h+arg_20]
0x180004f47  mov     [rbx+28h], rax
0x180004f4b  mov     [rbx+30h], r12
0x180004f4f  mov     rax, [rsp+78h+arg_28]
0x180004f57  mov     [rbx+88h], rax
0x180004f5e  mov     rax, [rsp+78h+arg_0]
0x180004f66  mov     [rbx+90h], rax
0x180004f6d  mov     [rbx+48h], rdi
0x180004f71  xorps   xmm0, xmm0
0x180004f74  xor     eax, eax
0x180004f76  movups  xmmword ptr [rbx+68h], xmm0
0x180004f7a  mov     [rbx+78h], rax
0x180004f7e  movups  xmmword ptr [rbx+50h], xmm0
0x180004f82  mov     [rbx+60h], rax
0x180004f86  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004f8d  test    rax, rax
0x180004f90  jz      short loc_180004F99
0x180004f92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f97  jmp     short loc_180004F9C
0x180004f99  mov     rax, rdi
0x180004f9c  mov     [rbx+80h], rax
0x180004fa3  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004faa  test    rax, rax
0x180004fad  jz      short loc_180004FB7
0x180004faf  mov     rcx, rbx
0x180004fb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fb7  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004fbe  test    rax, rax
0x180004fc1  jz      short loc_180004FD9
0x180004fc3  mov     r8d, 400h
0x180004fc9  mov     rdx, [rsp+78h+arg_60]
0x180004fd1  mov     rcx, rbx
0x180004fd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fd9  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004fe0  test    rax, rax
0x180004fe3  jz      short loc_180004FED
0x180004fe5  mov     rcx, rbx
0x180004fe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fed  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004ff4  test    rax, rax
0x180004ff7  jz      short loc_180005007
0x180004ff9  test    byte ptr [rbx+4], 2
0x180004ffd  jnz     short loc_180005007
0x180004fff  mov     rcx, rbx
0x180005002  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005007  cmp     [rbx+8], edi
0x18000500a  jl      short loc_180005026
0x18000500c  cmp     r15d, 3
0x180005010  jnz     loc_180005102
0x180005016  mov     ecx, 8000FFFFh; this
0x18000501b  mov     [rbx+8], ecx
0x18000501e  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005023  mov     [rbx+0Ch], eax
0x180005026  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000502d  jnz     short loc_180005054
0x18000502f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005036  test    rax, rax
0x180005039  jz      short loc_180005044
0x18000503b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005040  test    al, al
0x180005042  jmp     short loc_180005052
0x180005044  call    cs:__imp_IsDebuggerPresent
0x18000504b  nop     dword ptr [rax+rax+00h]
0x180005050  test    eax, eax
0x180005052  jz      short loc_18000505A
0x180005054  test    byte ptr [rbx+4], 2
0x180005058  jz      short loc_18000507E
0x18000505a  mov     rax, cs:g_pfnResultLoggingCallback
0x180005061  test    rax, rax
0x180005064  jz      short loc_1800050C8
0x180005066  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000506d  jnz     short loc_1800050C8
0x18000506f  xor     r8d, r8d
0x180005072  xor     edx, edx
0x180005074  mov     rcx, rbx
0x180005077  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000507c  jmp     short loc_1800050C8
0x18000507e  mov     ebp, 800h
0x180005083  mov     rax, cs:g_pfnResultLoggingCallback
0x18000508a  test    rax, rax
0x18000508d  jz      short loc_1800050A6
0x18000508f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005096  jnz     short loc_1800050A6
0x180005098  mov     r8d, ebp
0x18000509b  mov     rdx, rsi
0x18000509e  mov     rcx, rbx
0x1800050a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050a6  cmp     [rsi], di
0x1800050a9  jnz     short loc_1800050B9
0x1800050ab  mov     r8, rbx; unsigned __int64
0x1800050ae  mov     rdx, rbp; wchar_t *
0x1800050b1  mov     rcx, rsi; this
0x1800050b4  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1800050b9  mov     rcx, rsi; lpOutputString
0x1800050bc  call    cs:__imp_OutputDebugStringW
0x1800050c3  nop     dword ptr [rax+rax+00h]
0x1800050c8  test    byte ptr [rbx+4], 4
0x1800050cc  jnz     short loc_1800050D7
0x1800050ce  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800050d5  jz      short loc_1800050E9
0x1800050d7  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800050de  test    rax, rax
0x1800050e1  jz      short loc_1800050E9
0x1800050e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050e8  nop
0x1800050e9  mov     rbx, [rsp+78h+arg_10]
0x1800050f1  add     rsp, 40h
0x1800050f5  pop     r15
0x1800050f7  pop     r14
0x1800050f9  pop     r13
0x1800050fb  pop     r12
0x1800050fd  pop     rdi
0x1800050fe  pop     rsi
0x1800050ff  pop     rbp
0x180005100  retn
0x180005102  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
