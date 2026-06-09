# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000e2d0`
- end: `0x18000e5c9`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180009498`
- `0x180009558`
- `0x18000990c`

## callees

- `0x180005c50`
- `0x180007ec4`
- `0x1800084e0`
- `0x180009374`
- `0x18000e2d0`
- `0x18000f988`
- `0x18000fb14`
- `0x18000fb30`
- `0x180012a68`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e3f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e3f3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000e512`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000e512`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000e584`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000e584`

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
0x18000e2d0  mov     [rsp+arg_10], rbx
0x18000e2d5  mov     [rsp+arg_8], edx
0x18000e2d9  mov     [rsp+arg_0], rcx
0x18000e2de  push    rbp
0x18000e2df  push    rsi
0x18000e2e0  push    rdi
0x18000e2e1  push    r12
0x18000e2e3  push    r13
0x18000e2e5  push    r14
0x18000e2e7  push    r15
0x18000e2e9  sub     rsp, 40h
0x18000e2ed  mov     r12, r9
0x18000e2f0  mov     r13, r8
0x18000e2f3  mov     r10, rcx
0x18000e2f6  xor     eax, eax
0x18000e2f8  mov     rsi, [rsp+78h+lpOutputString]
0x18000e300  mov     [rsi], ax
0x18000e303  mov     rax, [rsp+78h+arg_60]
0x18000e30b  mov     byte ptr [rax], 0
0x18000e30e  mov     r14, [rsp+78h+arg_38]
0x18000e316  mov     edi, [r14]
0x18000e319  mov     rbx, [rsp+78h+arg_78]
0x18000e321  mov     [rbx+8], edi
0x18000e324  mov     eax, [r14+4]
0x18000e328  mov     [rbx+0Ch], eax
0x18000e32b  xor     ebp, ebp
0x18000e32d  mov     r15d, [rsp+78h+arg_30]
0x18000e335  mov     ecx, r15d
0x18000e338  test    r15d, r15d
0x18000e33b  jz      short loc_18000E3A3
0x18000e33d  sub     ecx, 1
0x18000e340  jz      short loc_18000E39A
0x18000e342  sub     ecx, 1
0x18000e345  jz      short loc_18000E355
0x18000e347  cmp     ecx, 1
0x18000e34a  jnz     short loc_18000E3AC
0x18000e34c  mov     ecx, edi; this
0x18000e34e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000e353  jmp     short loc_18000E3AA
0x18000e355  test    edi, edi
0x18000e357  js      short loc_18000E391
0x18000e359  mov     edi, 8007029Ch
0x18000e35e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000e362  mov     rax, [rsp+78h+arg_28]
0x18000e36a  mov     [rsp+78h+var_50], rax; __int64
0x18000e36f  mov     rax, [rsp+78h+arg_20]
0x18000e377  mov     [rsp+78h+var_58], rax; __int64
0x18000e37c  mov     rcx, r10; int
0x18000e37f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000e384  mov     [rbx+8], edi
0x18000e387  mov     ecx, edi; this
0x18000e389  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000e38e  mov     [rbx+0Ch], eax
0x18000e391  mov     ecx, edi; this
0x18000e393  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000e398  jmp     short loc_18000E3AA
0x18000e39a  mov     ecx, edi; this
0x18000e39c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000e3a1  jmp     short loc_18000E3AA
0x18000e3a3  mov     ecx, edi; this
0x18000e3a5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000e3aa  mov     ebp, eax
0x18000e3ac  mov     [rbx], r15d
0x18000e3af  mov     eax, [rsp+78h+arg_70]
0x18000e3b6  mov     [rbx+4], eax
0x18000e3b9  cmp     dword ptr [r14+8], 1
0x18000e3be  jnz     short loc_18000E3C6
0x18000e3c0  or      eax, 8
0x18000e3c3  mov     [rbx+4], eax
0x18000e3c6  mov     eax, 1
0x18000e3cb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000e3d3  inc     eax
0x18000e3d5  mov     [rbx+10h], eax
0x18000e3d8  mov     rax, [rsp+78h+arg_40]
0x18000e3e0  xor     edi, edi
0x18000e3e2  test    rax, rax
0x18000e3e5  jz      short loc_18000E3EC
0x18000e3e7  cmp     [rax], di
0x18000e3ea  jnz     short loc_18000E3EF
0x18000e3ec  mov     rax, rdi
0x18000e3ef  mov     [rbx+18h], rax
0x18000e3f3  call    cs:__imp_GetCurrentThreadId
0x18000e3f9  mov     [rbx+20h], eax
0x18000e3fc  mov     [rbx+38h], r13
0x18000e400  mov     eax, [rsp+78h+arg_8]
0x18000e407  mov     [rbx+40h], eax
0x18000e40a  mov     [rbx+44h], ebp
0x18000e40d  mov     rax, [rsp+78h+arg_20]
0x18000e415  mov     [rbx+28h], rax
0x18000e419  mov     [rbx+30h], r12
0x18000e41d  mov     rax, [rsp+78h+arg_28]
0x18000e425  mov     [rbx+88h], rax
0x18000e42c  mov     rax, [rsp+78h+arg_0]
0x18000e434  mov     [rbx+90h], rax
0x18000e43b  mov     [rbx+48h], rdi
0x18000e43f  xorps   xmm0, xmm0
0x18000e442  xor     eax, eax
0x18000e444  movups  xmmword ptr [rbx+68h], xmm0
0x18000e448  mov     [rbx+78h], rax
0x18000e44c  movups  xmmword ptr [rbx+50h], xmm0
0x18000e450  mov     [rbx+60h], rax
0x18000e454  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000e45b  test    rax, rax
0x18000e45e  jz      short loc_18000E467
0x18000e460  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e465  jmp     short loc_18000E46A
0x18000e467  mov     rax, rdi
0x18000e46a  mov     [rbx+80h], rax
0x18000e471  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000e478  test    rax, rax
0x18000e47b  jz      short loc_18000E485
0x18000e47d  mov     rcx, rbx
0x18000e480  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e485  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000e48c  test    rax, rax
0x18000e48f  jz      short loc_18000E4A7
0x18000e491  mov     r8d, 400h
0x18000e497  mov     rdx, [rsp+78h+arg_60]
0x18000e49f  mov     rcx, rbx
0x18000e4a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4a7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000e4ae  test    rax, rax
0x18000e4b1  jz      short loc_18000E4BB
0x18000e4b3  mov     rcx, rbx
0x18000e4b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4bb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000e4c2  test    rax, rax
0x18000e4c5  jz      short loc_18000E4D5
0x18000e4c7  test    byte ptr [rbx+4], 2
0x18000e4cb  jnz     short loc_18000E4D5
0x18000e4cd  mov     rcx, rbx
0x18000e4d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4d5  cmp     [rbx+8], edi
0x18000e4d8  jl      short loc_18000E4F4
0x18000e4da  cmp     r15d, 3
0x18000e4de  jnz     loc_18000E5C3
0x18000e4e4  mov     ecx, 8000FFFFh; this
0x18000e4e9  mov     [rbx+8], ecx
0x18000e4ec  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000e4f1  mov     [rbx+0Ch], eax
0x18000e4f4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000e4fb  jnz     short loc_18000E51C
0x18000e4fd  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000e504  test    rax, rax
0x18000e507  jz      short loc_18000E512
0x18000e509  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e50e  test    al, al
0x18000e510  jmp     short loc_18000E51A
0x18000e512  call    cs:__imp_IsDebuggerPresent
0x18000e518  test    eax, eax
0x18000e51a  jz      short loc_18000E522
0x18000e51c  test    byte ptr [rbx+4], 2
0x18000e520  jz      short loc_18000E546
0x18000e522  mov     rax, cs:g_pfnResultLoggingCallback
0x18000e529  test    rax, rax
0x18000e52c  jz      short loc_18000E58A
0x18000e52e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000e535  jnz     short loc_18000E58A
0x18000e537  xor     r8d, r8d
0x18000e53a  xor     edx, edx
0x18000e53c  mov     rcx, rbx
0x18000e53f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e544  jmp     short loc_18000E58A
0x18000e546  mov     ebp, 800h
0x18000e54b  mov     rax, cs:g_pfnResultLoggingCallback
0x18000e552  test    rax, rax
0x18000e555  jz      short loc_18000E56E
0x18000e557  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000e55e  jnz     short loc_18000E56E
0x18000e560  mov     r8d, ebp
0x18000e563  mov     rdx, rsi
0x18000e566  mov     rcx, rbx
0x18000e569  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e56e  cmp     [rsi], di
0x18000e571  jnz     short loc_18000E581
0x18000e573  mov     r8, rbx; unsigned __int64
0x18000e576  mov     rdx, rbp; wchar_t *
0x18000e579  mov     rcx, rsi; this
0x18000e57c  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18000e581  mov     rcx, rsi; lpOutputString
0x18000e584  call    cs:__imp_OutputDebugStringW
0x18000e58a  test    byte ptr [rbx+4], 4
0x18000e58e  jnz     short loc_18000E599
0x18000e590  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000e597  jz      short loc_18000E5AB
0x18000e599  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000e5a0  test    rax, rax
0x18000e5a3  jz      short loc_18000E5AB
0x18000e5a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5aa  nop
0x18000e5ab  mov     rbx, [rsp+78h+arg_10]
0x18000e5b3  add     rsp, 40h
0x18000e5b7  pop     r15
0x18000e5b9  pop     r14
0x18000e5bb  pop     r13
0x18000e5bd  pop     r12
0x18000e5bf  pop     rdi
0x18000e5c0  pop     rsi
0x18000e5c1  pop     rbp
0x18000e5c2  retn
0x18000e5c3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
