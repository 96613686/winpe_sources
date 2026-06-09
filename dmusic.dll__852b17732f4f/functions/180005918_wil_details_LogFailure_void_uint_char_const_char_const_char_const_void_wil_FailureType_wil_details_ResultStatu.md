# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180005918`
- end: `0x180005c11`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180002d68`

## callees

- `0x1800027ac`
- `0x180004de4`
- `0x18000558c`
- `0x180005918`
- `0x180006774`
- `0x180006790`
- `0x1800068bc`
- `0x1800068d8`
- `0x180008ebc`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005a3b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005a3b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005b5a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005b5a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005bcc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005bcc`

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
0x180005918  mov     [rsp+arg_10], rbx
0x18000591d  mov     [rsp+arg_8], edx
0x180005921  mov     [rsp+arg_0], rcx
0x180005926  push    rbp
0x180005927  push    rsi
0x180005928  push    rdi
0x180005929  push    r12
0x18000592b  push    r13
0x18000592d  push    r14
0x18000592f  push    r15
0x180005931  sub     rsp, 40h
0x180005935  mov     r12, r9
0x180005938  mov     r13, r8
0x18000593b  mov     r10, rcx
0x18000593e  xor     eax, eax
0x180005940  mov     rsi, [rsp+78h+lpOutputString]
0x180005948  mov     [rsi], ax
0x18000594b  mov     rax, [rsp+78h+arg_60]
0x180005953  mov     byte ptr [rax], 0
0x180005956  mov     r14, [rsp+78h+arg_38]
0x18000595e  mov     edi, [r14]
0x180005961  mov     rbx, [rsp+78h+arg_78]
0x180005969  mov     [rbx+8], edi
0x18000596c  mov     eax, [r14+4]
0x180005970  mov     [rbx+0Ch], eax
0x180005973  xor     ebp, ebp
0x180005975  mov     r15d, [rsp+78h+arg_30]
0x18000597d  mov     ecx, r15d
0x180005980  test    r15d, r15d
0x180005983  jz      short loc_1800059EB
0x180005985  sub     ecx, 1
0x180005988  jz      short loc_1800059E2
0x18000598a  sub     ecx, 1
0x18000598d  jz      short loc_18000599D
0x18000598f  cmp     ecx, 1
0x180005992  jnz     short loc_1800059F4
0x180005994  mov     ecx, edi; this
0x180005996  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000599b  jmp     short loc_1800059F2
0x18000599d  test    edi, edi
0x18000599f  js      short loc_1800059D9
0x1800059a1  mov     edi, 8007029Ch
0x1800059a6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800059aa  mov     rax, [rsp+78h+arg_28]
0x1800059b2  mov     [rsp+78h+var_50], rax; __int64
0x1800059b7  mov     rax, [rsp+78h+arg_20]
0x1800059bf  mov     [rsp+78h+var_58], rax; __int64
0x1800059c4  mov     rcx, r10; int
0x1800059c7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800059cc  mov     [rbx+8], edi
0x1800059cf  mov     ecx, edi; this
0x1800059d1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800059d6  mov     [rbx+0Ch], eax
0x1800059d9  mov     ecx, edi; this
0x1800059db  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800059e0  jmp     short loc_1800059F2
0x1800059e2  mov     ecx, edi; this
0x1800059e4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800059e9  jmp     short loc_1800059F2
0x1800059eb  mov     ecx, edi; this
0x1800059ed  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800059f2  mov     ebp, eax
0x1800059f4  mov     [rbx], r15d
0x1800059f7  mov     eax, [rsp+78h+arg_70]
0x1800059fe  mov     [rbx+4], eax
0x180005a01  cmp     dword ptr [r14+8], 1
0x180005a06  jnz     short loc_180005A0E
0x180005a08  or      eax, 8
0x180005a0b  mov     [rbx+4], eax
0x180005a0e  mov     eax, 1
0x180005a13  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005a1b  inc     eax
0x180005a1d  mov     [rbx+10h], eax
0x180005a20  mov     rax, [rsp+78h+arg_40]
0x180005a28  xor     edi, edi
0x180005a2a  test    rax, rax
0x180005a2d  jz      short loc_180005A34
0x180005a2f  cmp     [rax], di
0x180005a32  jnz     short loc_180005A37
0x180005a34  mov     rax, rdi
0x180005a37  mov     [rbx+18h], rax
0x180005a3b  call    cs:__imp_GetCurrentThreadId
0x180005a41  mov     [rbx+20h], eax
0x180005a44  mov     [rbx+38h], r13
0x180005a48  mov     eax, [rsp+78h+arg_8]
0x180005a4f  mov     [rbx+40h], eax
0x180005a52  mov     [rbx+44h], ebp
0x180005a55  mov     rax, [rsp+78h+arg_20]
0x180005a5d  mov     [rbx+28h], rax
0x180005a61  mov     [rbx+30h], r12
0x180005a65  mov     rax, [rsp+78h+arg_28]
0x180005a6d  mov     [rbx+88h], rax
0x180005a74  mov     rax, [rsp+78h+arg_0]
0x180005a7c  mov     [rbx+90h], rax
0x180005a83  mov     [rbx+48h], rdi
0x180005a87  xorps   xmm0, xmm0
0x180005a8a  xor     eax, eax
0x180005a8c  movups  xmmword ptr [rbx+68h], xmm0
0x180005a90  mov     [rbx+78h], rax
0x180005a94  movups  xmmword ptr [rbx+50h], xmm0
0x180005a98  mov     [rbx+60h], rax
0x180005a9c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005aa3  test    rax, rax
0x180005aa6  jz      short loc_180005AAF
0x180005aa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005aad  jmp     short loc_180005AB2
0x180005aaf  mov     rax, rdi
0x180005ab2  mov     [rbx+80h], rax
0x180005ab9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005ac0  test    rax, rax
0x180005ac3  jz      short loc_180005ACD
0x180005ac5  mov     rcx, rbx
0x180005ac8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005acd  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005ad4  test    rax, rax
0x180005ad7  jz      short loc_180005AEF
0x180005ad9  mov     r8d, 400h
0x180005adf  mov     rdx, [rsp+78h+arg_60]
0x180005ae7  mov     rcx, rbx
0x180005aea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005aef  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005af6  test    rax, rax
0x180005af9  jz      short loc_180005B03
0x180005afb  mov     rcx, rbx
0x180005afe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b03  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005b0a  test    rax, rax
0x180005b0d  jz      short loc_180005B1D
0x180005b0f  test    byte ptr [rbx+4], 2
0x180005b13  jnz     short loc_180005B1D
0x180005b15  mov     rcx, rbx
0x180005b18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b1d  cmp     [rbx+8], edi
0x180005b20  jl      short loc_180005B3C
0x180005b22  cmp     r15d, 3
0x180005b26  jnz     loc_180005C0B
0x180005b2c  mov     ecx, 8000FFFFh; this
0x180005b31  mov     [rbx+8], ecx
0x180005b34  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005b39  mov     [rbx+0Ch], eax
0x180005b3c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180005b43  jnz     short loc_180005B64
0x180005b45  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005b4c  test    rax, rax
0x180005b4f  jz      short loc_180005B5A
0x180005b51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b56  test    al, al
0x180005b58  jmp     short loc_180005B62
0x180005b5a  call    cs:__imp_IsDebuggerPresent
0x180005b60  test    eax, eax
0x180005b62  jz      short loc_180005B6A
0x180005b64  test    byte ptr [rbx+4], 2
0x180005b68  jz      short loc_180005B8E
0x180005b6a  mov     rax, cs:g_pfnResultLoggingCallback
0x180005b71  test    rax, rax
0x180005b74  jz      short loc_180005BD2
0x180005b76  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005b7d  jnz     short loc_180005BD2
0x180005b7f  xor     r8d, r8d
0x180005b82  xor     edx, edx
0x180005b84  mov     rcx, rbx
0x180005b87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b8c  jmp     short loc_180005BD2
0x180005b8e  mov     ebp, 800h
0x180005b93  mov     rax, cs:g_pfnResultLoggingCallback
0x180005b9a  test    rax, rax
0x180005b9d  jz      short loc_180005BB6
0x180005b9f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005ba6  jnz     short loc_180005BB6
0x180005ba8  mov     r8d, ebp
0x180005bab  mov     rdx, rsi
0x180005bae  mov     rcx, rbx
0x180005bb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bb6  cmp     [rsi], di
0x180005bb9  jnz     short loc_180005BC9
0x180005bbb  mov     r8, rbx; unsigned __int64
0x180005bbe  mov     rdx, rbp; unsigned __int16 *
0x180005bc1  mov     rcx, rsi; this
0x180005bc4  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005bc9  mov     rcx, rsi; lpOutputString
0x180005bcc  call    cs:__imp_OutputDebugStringW
0x180005bd2  test    byte ptr [rbx+4], 4
0x180005bd6  jnz     short loc_180005BE1
0x180005bd8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180005bdf  jz      short loc_180005BF3
0x180005be1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005be8  test    rax, rax
0x180005beb  jz      short loc_180005BF3
0x180005bed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bf2  nop
0x180005bf3  mov     rbx, [rsp+78h+arg_10]
0x180005bfb  add     rsp, 40h
0x180005bff  pop     r15
0x180005c01  pop     r14
0x180005c03  pop     r13
0x180005c05  pop     r12
0x180005c07  pop     rdi
0x180005c08  pop     rsi
0x180005c09  pop     rbp
0x180005c0a  retn
0x180005c0b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
