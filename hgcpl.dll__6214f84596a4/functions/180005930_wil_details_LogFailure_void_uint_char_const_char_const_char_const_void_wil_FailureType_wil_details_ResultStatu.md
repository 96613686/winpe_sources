# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180005930`
- end: `0x180005c28`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1800041cc`
- `0x180004518`

## callees

- `0x18000410c`
- `0x180004f24`
- `0x180005740`
- `0x180005930`
- `0x180005f70`
- `0x180005f90`
- `0x180005fa4`
- `0x180005fc0`
- `0x180006954`
- `0x18001a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005a53`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005a53`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005be4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005be4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005b72`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005b72`

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
  int v21; // edx
  _WORD *v22; // rax
  DWORD CurrentThreadId; // eax
  int v24; // edx
  wil::details::in1diag3 *v25; // rcx
  const struct wil::FailureInfo *v26; // r9
  __int64 ModuleName; // rax
  bool v28; // zf
  wil::details *v29; // [rsp+30h] [rbp-48h]

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
          LODWORD(v29) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v29);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v21);
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
  v22 = a9;
  if ( !a9 || !*a9 )
    v22 = 0;
  *(_QWORD *)(a16 + 24) = v22;
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v25);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v24);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v28 = !IsDebuggerPresent())
      : (v28 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v28)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v26);
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
0x180005930  mov     [rsp+arg_10], rbx
0x180005935  mov     [rsp+arg_8], edx
0x180005939  mov     [rsp+arg_0], rcx
0x18000593e  push    rbp
0x18000593f  push    rsi
0x180005940  push    rdi
0x180005941  push    r12
0x180005943  push    r13
0x180005945  push    r14
0x180005947  push    r15
0x180005949  sub     rsp, 40h
0x18000594d  mov     r14, [rsp+78h+arg_38]
0x180005955  xor     eax, eax
0x180005957  mov     rbx, [rsp+78h+arg_78]
0x18000595f  xor     ebp, ebp
0x180005961  mov     r15d, [rsp+78h+arg_30]
0x180005969  mov     r10, rcx
0x18000596c  mov     rsi, [rsp+78h+lpOutputString]
0x180005974  mov     r12, r9
0x180005977  mov     r13, r8
0x18000597a  mov     ecx, r15d
0x18000597d  mov     [rsi], ax
0x180005980  mov     rax, [rsp+78h+arg_60]
0x180005988  mov     byte ptr [rax], 0
0x18000598b  mov     edi, [r14]
0x18000598e  mov     [rbx+8], edi
0x180005991  mov     eax, [r14+4]
0x180005995  mov     [rbx+0Ch], eax
0x180005998  test    r15d, r15d
0x18000599b  jz      short loc_180005A03
0x18000599d  sub     ecx, 1
0x1800059a0  jz      short loc_1800059FA
0x1800059a2  sub     ecx, 1
0x1800059a5  jz      short loc_1800059B5
0x1800059a7  cmp     ecx, 1
0x1800059aa  jnz     short loc_180005A0C
0x1800059ac  mov     ecx, edi; this
0x1800059ae  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800059b3  jmp     short loc_180005A0A
0x1800059b5  test    edi, edi
0x1800059b7  js      short loc_1800059F1
0x1800059b9  mov     rax, [rsp+78h+arg_28]
0x1800059c1  mov     edi, 8007029Ch
0x1800059c6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800059ca  mov     rcx, r10; int
0x1800059cd  mov     [rsp+78h+var_50], rax; __int64
0x1800059d2  mov     rax, [rsp+78h+arg_20]
0x1800059da  mov     [rsp+78h+var_58], rax; __int64
0x1800059df  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800059e4  mov     ecx, edi; this
0x1800059e6  mov     [rbx+8], edi
0x1800059e9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800059ee  mov     [rbx+0Ch], eax
0x1800059f1  mov     ecx, edi; this
0x1800059f3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800059f8  jmp     short loc_180005A0A
0x1800059fa  mov     ecx, edi; this
0x1800059fc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005a01  jmp     short loc_180005A0A
0x180005a03  mov     ecx, edi; this
0x180005a05  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180005a0a  mov     ebp, eax
0x180005a0c  mov     eax, [rsp+78h+arg_70]
0x180005a13  mov     [rbx+4], eax
0x180005a16  mov     [rbx], r15d
0x180005a19  cmp     dword ptr [r14+8], 1
0x180005a1e  jnz     short loc_180005A26
0x180005a20  or      eax, 8
0x180005a23  mov     [rbx+4], eax
0x180005a26  mov     eax, 1
0x180005a2b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005a33  inc     eax
0x180005a35  xor     edi, edi
0x180005a37  mov     [rbx+10h], eax
0x180005a3a  mov     rax, [rsp+78h+arg_40]
0x180005a42  test    rax, rax
0x180005a45  jz      short loc_180005A4C
0x180005a47  cmp     [rax], di
0x180005a4a  jnz     short loc_180005A4F
0x180005a4c  mov     rax, rdi
0x180005a4f  mov     [rbx+18h], rax
0x180005a53  call    cs:__imp_GetCurrentThreadId
0x180005a59  mov     [rbx+38h], r13
0x180005a5d  xorps   xmm0, xmm0
0x180005a60  mov     [rbx+20h], eax
0x180005a63  mov     eax, [rsp+78h+arg_8]
0x180005a6a  mov     [rbx+40h], eax
0x180005a6d  mov     rax, [rsp+78h+arg_20]
0x180005a75  mov     [rbx+28h], rax
0x180005a79  mov     rax, [rsp+78h+arg_28]
0x180005a81  mov     [rbx+88h], rax
0x180005a88  mov     rax, [rsp+78h+arg_0]
0x180005a90  mov     [rbx+90h], rax
0x180005a97  xor     eax, eax
0x180005a99  mov     [rbx+44h], ebp
0x180005a9c  mov     [rbx+30h], r12
0x180005aa0  mov     [rbx+48h], rdi
0x180005aa4  movups  xmmword ptr [rbx+68h], xmm0
0x180005aa8  mov     [rbx+78h], rax
0x180005aac  movups  xmmword ptr [rbx+50h], xmm0
0x180005ab0  mov     [rbx+60h], rax
0x180005ab4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005abb  test    rax, rax
0x180005abe  jz      short loc_180005AC7
0x180005ac0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ac5  jmp     short loc_180005ACA
0x180005ac7  mov     rax, rdi
0x180005aca  mov     [rbx+80h], rax
0x180005ad1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005ad8  test    rax, rax
0x180005adb  jz      short loc_180005AE5
0x180005add  mov     rcx, rbx
0x180005ae0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ae5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005aec  test    rax, rax
0x180005aef  jz      short loc_180005B07
0x180005af1  mov     rdx, [rsp+78h+arg_60]
0x180005af9  mov     r8d, 400h
0x180005aff  mov     rcx, rbx
0x180005b02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b07  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005b0e  test    rax, rax
0x180005b11  jz      short loc_180005B1B
0x180005b13  mov     rcx, rbx
0x180005b16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b1b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005b22  test    rax, rax
0x180005b25  jz      short loc_180005B35
0x180005b27  test    byte ptr [rbx+4], 2
0x180005b2b  jnz     short loc_180005B35
0x180005b2d  mov     rcx, rbx
0x180005b30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b35  cmp     [rbx+8], edi
0x180005b38  jl      short loc_180005B54
0x180005b3a  cmp     r15d, 3
0x180005b3e  jnz     loc_180005C22
0x180005b44  mov     ecx, 8000FFFFh; this
0x180005b49  mov     [rbx+8], ecx
0x180005b4c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005b51  mov     [rbx+0Ch], eax
0x180005b54  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180005b5b  jnz     short loc_180005B7C
0x180005b5d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005b64  test    rax, rax
0x180005b67  jz      short loc_180005B72
0x180005b69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b6e  test    al, al
0x180005b70  jmp     short loc_180005B7A
0x180005b72  call    cs:__imp_IsDebuggerPresent
0x180005b78  test    eax, eax
0x180005b7a  jz      short loc_180005B82
0x180005b7c  test    byte ptr [rbx+4], 2
0x180005b80  jz      short loc_180005BA6
0x180005b82  mov     rax, cs:g_pfnResultLoggingCallback
0x180005b89  test    rax, rax
0x180005b8c  jz      short loc_180005BEA
0x180005b8e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005b95  jnz     short loc_180005BEA
0x180005b97  xor     r8d, r8d
0x180005b9a  xor     edx, edx
0x180005b9c  mov     rcx, rbx
0x180005b9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ba4  jmp     short loc_180005BEA
0x180005ba6  mov     rax, cs:g_pfnResultLoggingCallback
0x180005bad  mov     ebp, 800h
0x180005bb2  test    rax, rax
0x180005bb5  jz      short loc_180005BCE
0x180005bb7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005bbe  jnz     short loc_180005BCE
0x180005bc0  mov     r8d, ebp
0x180005bc3  mov     rdx, rsi
0x180005bc6  mov     rcx, rbx
0x180005bc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bce  cmp     [rsi], di
0x180005bd1  jnz     short loc_180005BE1
0x180005bd3  mov     r8, rbx; unsigned __int64
0x180005bd6  mov     rdx, rbp; unsigned __int16 *
0x180005bd9  mov     rcx, rsi; this
0x180005bdc  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005be1  mov     rcx, rsi; lpOutputString
0x180005be4  call    cs:__imp_OutputDebugStringW
0x180005bea  test    byte ptr [rbx+4], 4
0x180005bee  jnz     short loc_180005BF9
0x180005bf0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180005bf7  jz      short loc_180005C0A
0x180005bf9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005c00  test    rax, rax
0x180005c03  jz      short loc_180005C0A
0x180005c05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c0a  mov     rbx, [rsp+78h+arg_10]
0x180005c12  add     rsp, 40h
0x180005c16  pop     r15
0x180005c18  pop     r14
0x180005c1a  pop     r13
0x180005c1c  pop     r12
0x180005c1e  pop     rdi
0x180005c1f  pop     rsi
0x180005c20  pop     rbp
0x180005c21  retn
0x180005c22  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
