# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000a448`
- end: `0x18000a740`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18000717c`
- `0x1800074cc`

## callees

- `0x1800070c4`
- `0x1800095b0`
- `0x180009ee0`
- `0x18000a448`
- `0x18000bba0`
- `0x18000bbc0`
- `0x18000bbd4`
- `0x18000bbf0`
- `0x18000c85c`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a56b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a56b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000a68a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000a68a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000a6fc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000a6fc`

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
  int v16; // ebp
  unsigned int v19; // edi
  int v20; // eax
  _WORD *v21; // rax
  DWORD CurrentThreadId; // eax
  wil::details::in1diag3 *v23; // rcx
  const struct wil::FailureInfo *v24; // r9
  __int64 ModuleName; // rax
  bool v26; // zf
  wil::details *v27; // [rsp+30h] [rbp-48h]

  v16 = 0;
  *(_WORD *)lpOutputString = 0;
  *a13 = 0;
  v19 = *a8;
  *(_DWORD *)(a16 + 8) = *a8;
  *(_DWORD *)(a16 + 12) = a8[1];
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1:
        v20 = wil::details::RecordReturn((wil::details *)v19, a2);
        break;
      case 2:
        if ( (v19 & 0x80000000) == 0 )
        {
          v19 = -2147024228;
          LODWORD(v27) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v27);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL);
        }
        v20 = wil::details::RecordLog((wil::details *)v19, a2);
        break;
      case 3:
        v20 = wil::details::RecordFailFast((wil::details *)v19, a2);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v20 = wil::details::RecordException((wil::details *)v19, a2);
  }
  v16 = v20;
LABEL_12:
  *(_DWORD *)(a16 + 4) = a15;
  *(_DWORD *)a16 = a7;
  if ( a8[2] == 1 )
    *(_DWORD *)(a16 + 4) = a15 | 8;
  *(_DWORD *)(a16 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = a9;
  if ( !a9 || !*a9 )
    v21 = 0;
  *(_QWORD *)(a16 + 24) = v21;
  CurrentThreadId = GetCurrentThreadId();
  *(_QWORD *)(a16 + 56) = a3;
  *(_DWORD *)(a16 + 32) = CurrentThreadId;
  *(_DWORD *)(a16 + 64) = a2;
  *(_QWORD *)(a16 + 40) = a5;
  *(_QWORD *)(a16 + 136) = a6;
  *(_QWORD *)(a16 + 144) = a1;
  *(_DWORD *)(a16 + 68) = v16;
  *(_QWORD *)(a16 + 48) = a4;
  *(_QWORD *)(a16 + 72) = 0;
  *(_OWORD *)(a16 + 104) = 0;
  *(_QWORD *)(a16 + 120) = 0;
  *(_OWORD *)(a16 + 80) = 0;
  *(_QWORD *)(a16 + 96) = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v23);
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v23);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v26 = !IsDebuggerPresent())
      : (v26 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v23) == 0),
        v26)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v24);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v23);
  }
}

```

## disassembly

```asm
0x18000a448  mov     [rsp+arg_10], rbx
0x18000a44d  mov     [rsp+arg_8], edx
0x18000a451  mov     [rsp+arg_0], rcx
0x18000a456  push    rbp
0x18000a457  push    rsi
0x18000a458  push    rdi
0x18000a459  push    r12
0x18000a45b  push    r13
0x18000a45d  push    r14
0x18000a45f  push    r15
0x18000a461  sub     rsp, 40h
0x18000a465  mov     r14, [rsp+78h+arg_38]
0x18000a46d  xor     eax, eax
0x18000a46f  mov     rbx, [rsp+78h+arg_78]
0x18000a477  xor     ebp, ebp
0x18000a479  mov     r15d, [rsp+78h+arg_30]
0x18000a481  mov     r10, rcx
0x18000a484  mov     rsi, [rsp+78h+lpOutputString]
0x18000a48c  mov     r12, r9
0x18000a48f  mov     r13, r8
0x18000a492  mov     ecx, r15d
0x18000a495  mov     [rsi], ax
0x18000a498  mov     rax, [rsp+78h+arg_60]
0x18000a4a0  mov     byte ptr [rax], 0
0x18000a4a3  mov     edi, [r14]
0x18000a4a6  mov     [rbx+8], edi
0x18000a4a9  mov     eax, [r14+4]
0x18000a4ad  mov     [rbx+0Ch], eax
0x18000a4b0  test    r15d, r15d
0x18000a4b3  jz      short loc_18000A51B
0x18000a4b5  sub     ecx, 1
0x18000a4b8  jz      short loc_18000A512
0x18000a4ba  sub     ecx, 1
0x18000a4bd  jz      short loc_18000A4CD
0x18000a4bf  cmp     ecx, 1
0x18000a4c2  jnz     short loc_18000A524
0x18000a4c4  mov     ecx, edi; this
0x18000a4c6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000a4cb  jmp     short loc_18000A522
0x18000a4cd  test    edi, edi
0x18000a4cf  js      short loc_18000A509
0x18000a4d1  mov     rax, [rsp+78h+arg_28]
0x18000a4d9  mov     edi, 8007029Ch
0x18000a4de  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000a4e2  mov     rcx, r10; int
0x18000a4e5  mov     [rsp+78h+var_50], rax; __int64
0x18000a4ea  mov     rax, [rsp+78h+arg_20]
0x18000a4f2  mov     [rsp+78h+var_58], rax; __int64
0x18000a4f7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000a4fc  mov     ecx, edi; this
0x18000a4fe  mov     [rbx+8], edi
0x18000a501  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000a506  mov     [rbx+0Ch], eax
0x18000a509  mov     ecx, edi; this
0x18000a50b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000a510  jmp     short loc_18000A522
0x18000a512  mov     ecx, edi; this
0x18000a514  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000a519  jmp     short loc_18000A522
0x18000a51b  mov     ecx, edi; this
0x18000a51d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000a522  mov     ebp, eax
0x18000a524  mov     eax, [rsp+78h+arg_70]
0x18000a52b  mov     [rbx+4], eax
0x18000a52e  mov     [rbx], r15d
0x18000a531  cmp     dword ptr [r14+8], 1
0x18000a536  jnz     short loc_18000A53E
0x18000a538  or      eax, 8
0x18000a53b  mov     [rbx+4], eax
0x18000a53e  mov     eax, 1
0x18000a543  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000a54b  inc     eax
0x18000a54d  xor     edi, edi
0x18000a54f  mov     [rbx+10h], eax
0x18000a552  mov     rax, [rsp+78h+arg_40]
0x18000a55a  test    rax, rax
0x18000a55d  jz      short loc_18000A564
0x18000a55f  cmp     [rax], di
0x18000a562  jnz     short loc_18000A567
0x18000a564  mov     rax, rdi
0x18000a567  mov     [rbx+18h], rax
0x18000a56b  call    cs:__imp_GetCurrentThreadId
0x18000a571  mov     [rbx+38h], r13
0x18000a575  xorps   xmm0, xmm0
0x18000a578  mov     [rbx+20h], eax
0x18000a57b  mov     eax, [rsp+78h+arg_8]
0x18000a582  mov     [rbx+40h], eax
0x18000a585  mov     rax, [rsp+78h+arg_20]
0x18000a58d  mov     [rbx+28h], rax
0x18000a591  mov     rax, [rsp+78h+arg_28]
0x18000a599  mov     [rbx+88h], rax
0x18000a5a0  mov     rax, [rsp+78h+arg_0]
0x18000a5a8  mov     [rbx+90h], rax
0x18000a5af  xor     eax, eax
0x18000a5b1  mov     [rbx+44h], ebp
0x18000a5b4  mov     [rbx+30h], r12
0x18000a5b8  mov     [rbx+48h], rdi
0x18000a5bc  movups  xmmword ptr [rbx+68h], xmm0
0x18000a5c0  mov     [rbx+78h], rax
0x18000a5c4  movups  xmmword ptr [rbx+50h], xmm0
0x18000a5c8  mov     [rbx+60h], rax
0x18000a5cc  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000a5d3  test    rax, rax
0x18000a5d6  jz      short loc_18000A5DF
0x18000a5d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5dd  jmp     short loc_18000A5E2
0x18000a5df  mov     rax, rdi
0x18000a5e2  mov     [rbx+80h], rax
0x18000a5e9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000a5f0  test    rax, rax
0x18000a5f3  jz      short loc_18000A5FD
0x18000a5f5  mov     rcx, rbx
0x18000a5f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5fd  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000a604  test    rax, rax
0x18000a607  jz      short loc_18000A61F
0x18000a609  mov     rdx, [rsp+78h+arg_60]
0x18000a611  mov     r8d, 400h
0x18000a617  mov     rcx, rbx
0x18000a61a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a61f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a626  test    rax, rax
0x18000a629  jz      short loc_18000A633
0x18000a62b  mov     rcx, rbx
0x18000a62e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a633  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a63a  test    rax, rax
0x18000a63d  jz      short loc_18000A64D
0x18000a63f  test    byte ptr [rbx+4], 2
0x18000a643  jnz     short loc_18000A64D
0x18000a645  mov     rcx, rbx
0x18000a648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a64d  cmp     [rbx+8], edi
0x18000a650  jl      short loc_18000A66C
0x18000a652  cmp     r15d, 3
0x18000a656  jnz     loc_18000A73A
0x18000a65c  mov     ecx, 8000FFFFh; this
0x18000a661  mov     [rbx+8], ecx
0x18000a664  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000a669  mov     [rbx+0Ch], eax
0x18000a66c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000a673  jnz     short loc_18000A694
0x18000a675  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000a67c  test    rax, rax
0x18000a67f  jz      short loc_18000A68A
0x18000a681  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a686  test    al, al
0x18000a688  jmp     short loc_18000A692
0x18000a68a  call    cs:__imp_IsDebuggerPresent
0x18000a690  test    eax, eax
0x18000a692  jz      short loc_18000A69A
0x18000a694  test    byte ptr [rbx+4], 2
0x18000a698  jz      short loc_18000A6BE
0x18000a69a  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a6a1  test    rax, rax
0x18000a6a4  jz      short loc_18000A702
0x18000a6a6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000a6ad  jnz     short loc_18000A702
0x18000a6af  xor     r8d, r8d
0x18000a6b2  xor     edx, edx
0x18000a6b4  mov     rcx, rbx
0x18000a6b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6bc  jmp     short loc_18000A702
0x18000a6be  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a6c5  mov     ebp, 800h
0x18000a6ca  test    rax, rax
0x18000a6cd  jz      short loc_18000A6E6
0x18000a6cf  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000a6d6  jnz     short loc_18000A6E6
0x18000a6d8  mov     r8d, ebp
0x18000a6db  mov     rdx, rsi
0x18000a6de  mov     rcx, rbx
0x18000a6e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6e6  cmp     [rsi], di
0x18000a6e9  jnz     short loc_18000A6F9
0x18000a6eb  mov     r8, rbx; unsigned __int64
0x18000a6ee  mov     rdx, rbp; unsigned __int16 *
0x18000a6f1  mov     rcx, rsi; this
0x18000a6f4  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000a6f9  mov     rcx, rsi; lpOutputString
0x18000a6fc  call    cs:__imp_OutputDebugStringW
0x18000a702  test    byte ptr [rbx+4], 4
0x18000a706  jnz     short loc_18000A711
0x18000a708  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000a70f  jz      short loc_18000A722
0x18000a711  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000a718  test    rax, rax
0x18000a71b  jz      short loc_18000A722
0x18000a71d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a722  mov     rbx, [rsp+78h+arg_10]
0x18000a72a  add     rsp, 40h
0x18000a72e  pop     r15
0x18000a730  pop     r14
0x18000a732  pop     r13
0x18000a734  pop     r12
0x18000a736  pop     rdi
0x18000a737  pop     rsi
0x18000a738  pop     rbp
0x18000a739  retn
0x18000a73a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
