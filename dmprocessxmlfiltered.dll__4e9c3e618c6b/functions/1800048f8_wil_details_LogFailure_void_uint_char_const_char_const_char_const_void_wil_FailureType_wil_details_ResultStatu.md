# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800048f8`
- end: `0x180004bf1`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180002e64`

## callees

- `0x180002870`
- `0x180003f94`
- `0x180004734`
- `0x1800048f8`
- `0x180004e84`
- `0x180004ea0`
- `0x180004eb4`
- `0x180004ed0`
- `0x18000602c`
- `0x180008010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004a1b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004a1b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004b3a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004b3a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004bac`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004bac`

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
      g_pfnResultLoggingCallback(a16, 0, 0, v25);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048, v25);
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
0x1800048f8  mov     [rsp+arg_10], rbx
0x1800048fd  mov     [rsp+arg_8], edx
0x180004901  mov     [rsp+arg_0], rcx
0x180004906  push    rbp
0x180004907  push    rsi
0x180004908  push    rdi
0x180004909  push    r12
0x18000490b  push    r13
0x18000490d  push    r14
0x18000490f  push    r15
0x180004911  sub     rsp, 40h
0x180004915  mov     r12, r9
0x180004918  mov     r13, r8
0x18000491b  mov     r10, rcx
0x18000491e  xor     eax, eax
0x180004920  mov     rsi, [rsp+78h+lpOutputString]
0x180004928  mov     [rsi], ax
0x18000492b  mov     rax, [rsp+78h+arg_60]
0x180004933  mov     byte ptr [rax], 0
0x180004936  mov     r14, [rsp+78h+arg_38]
0x18000493e  mov     edi, [r14]
0x180004941  mov     rbx, [rsp+78h+arg_78]
0x180004949  mov     [rbx+8], edi
0x18000494c  mov     eax, [r14+4]
0x180004950  mov     [rbx+0Ch], eax
0x180004953  xor     ebp, ebp
0x180004955  mov     r15d, [rsp+78h+arg_30]
0x18000495d  mov     ecx, r15d
0x180004960  test    r15d, r15d
0x180004963  jz      short loc_1800049CB
0x180004965  sub     ecx, 1
0x180004968  jz      short loc_1800049C2
0x18000496a  sub     ecx, 1
0x18000496d  jz      short loc_18000497D
0x18000496f  cmp     ecx, 1
0x180004972  jnz     short loc_1800049D4
0x180004974  mov     ecx, edi; this
0x180004976  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000497b  jmp     short loc_1800049D2
0x18000497d  test    edi, edi
0x18000497f  js      short loc_1800049B9
0x180004981  mov     edi, 8007029Ch
0x180004986  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000498a  mov     rax, [rsp+78h+arg_28]
0x180004992  mov     [rsp+78h+var_50], rax; __int64
0x180004997  mov     rax, [rsp+78h+arg_20]
0x18000499f  mov     [rsp+78h+var_58], rax; __int64
0x1800049a4  mov     rcx, r10; int
0x1800049a7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800049ac  mov     [rbx+8], edi
0x1800049af  mov     ecx, edi; this
0x1800049b1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800049b6  mov     [rbx+0Ch], eax
0x1800049b9  mov     ecx, edi; this
0x1800049bb  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800049c0  jmp     short loc_1800049D2
0x1800049c2  mov     ecx, edi; this
0x1800049c4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800049c9  jmp     short loc_1800049D2
0x1800049cb  mov     ecx, edi; this
0x1800049cd  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800049d2  mov     ebp, eax
0x1800049d4  mov     [rbx], r15d
0x1800049d7  mov     eax, [rsp+78h+arg_70]
0x1800049de  mov     [rbx+4], eax
0x1800049e1  cmp     dword ptr [r14+8], 1
0x1800049e6  jnz     short loc_1800049EE
0x1800049e8  or      eax, 8
0x1800049eb  mov     [rbx+4], eax
0x1800049ee  mov     eax, 1
0x1800049f3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800049fb  inc     eax
0x1800049fd  mov     [rbx+10h], eax
0x180004a00  mov     rax, [rsp+78h+arg_40]
0x180004a08  xor     edi, edi
0x180004a0a  test    rax, rax
0x180004a0d  jz      short loc_180004A14
0x180004a0f  cmp     [rax], di
0x180004a12  jnz     short loc_180004A17
0x180004a14  mov     rax, rdi
0x180004a17  mov     [rbx+18h], rax
0x180004a1b  call    cs:__imp_GetCurrentThreadId
0x180004a21  mov     [rbx+20h], eax
0x180004a24  mov     [rbx+38h], r13
0x180004a28  mov     eax, [rsp+78h+arg_8]
0x180004a2f  mov     [rbx+40h], eax
0x180004a32  mov     [rbx+44h], ebp
0x180004a35  mov     rax, [rsp+78h+arg_20]
0x180004a3d  mov     [rbx+28h], rax
0x180004a41  mov     [rbx+30h], r12
0x180004a45  mov     rax, [rsp+78h+arg_28]
0x180004a4d  mov     [rbx+88h], rax
0x180004a54  mov     rax, [rsp+78h+arg_0]
0x180004a5c  mov     [rbx+90h], rax
0x180004a63  mov     [rbx+48h], rdi
0x180004a67  xorps   xmm0, xmm0
0x180004a6a  xor     eax, eax
0x180004a6c  movups  xmmword ptr [rbx+68h], xmm0
0x180004a70  mov     [rbx+78h], rax
0x180004a74  movups  xmmword ptr [rbx+50h], xmm0
0x180004a78  mov     [rbx+60h], rax
0x180004a7c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004a83  test    rax, rax
0x180004a86  jz      short loc_180004A8F
0x180004a88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a8d  jmp     short loc_180004A92
0x180004a8f  mov     rax, rdi
0x180004a92  mov     [rbx+80h], rax
0x180004a99  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004aa0  test    rax, rax
0x180004aa3  jz      short loc_180004AAD
0x180004aa5  mov     rcx, rbx
0x180004aa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004aad  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004ab4  test    rax, rax
0x180004ab7  jz      short loc_180004ACF
0x180004ab9  mov     r8d, 400h
0x180004abf  mov     rdx, [rsp+78h+arg_60]
0x180004ac7  mov     rcx, rbx
0x180004aca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004acf  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004ad6  test    rax, rax
0x180004ad9  jz      short loc_180004AE3
0x180004adb  mov     rcx, rbx
0x180004ade  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ae3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004aea  test    rax, rax
0x180004aed  jz      short loc_180004AFD
0x180004aef  test    byte ptr [rbx+4], 2
0x180004af3  jnz     short loc_180004AFD
0x180004af5  mov     rcx, rbx
0x180004af8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004afd  cmp     [rbx+8], edi
0x180004b00  jl      short loc_180004B1C
0x180004b02  cmp     r15d, 3
0x180004b06  jnz     loc_180004BEB
0x180004b0c  mov     ecx, 8000FFFFh; this
0x180004b11  mov     [rbx+8], ecx
0x180004b14  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004b19  mov     [rbx+0Ch], eax
0x180004b1c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180004b23  jnz     short loc_180004B44
0x180004b25  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004b2c  test    rax, rax
0x180004b2f  jz      short loc_180004B3A
0x180004b31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b36  test    al, al
0x180004b38  jmp     short loc_180004B42
0x180004b3a  call    cs:__imp_IsDebuggerPresent
0x180004b40  test    eax, eax
0x180004b42  jz      short loc_180004B4A
0x180004b44  test    byte ptr [rbx+4], 2
0x180004b48  jz      short loc_180004B6E
0x180004b4a  mov     rax, cs:g_pfnResultLoggingCallback
0x180004b51  test    rax, rax
0x180004b54  jz      short loc_180004BB2
0x180004b56  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180004b5d  jnz     short loc_180004BB2
0x180004b5f  xor     r8d, r8d
0x180004b62  xor     edx, edx
0x180004b64  mov     rcx, rbx
0x180004b67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b6c  jmp     short loc_180004BB2
0x180004b6e  mov     ebp, 800h
0x180004b73  mov     rax, cs:g_pfnResultLoggingCallback
0x180004b7a  test    rax, rax
0x180004b7d  jz      short loc_180004B96
0x180004b7f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180004b86  jnz     short loc_180004B96
0x180004b88  mov     r8d, ebp
0x180004b8b  mov     rdx, rsi
0x180004b8e  mov     rcx, rbx
0x180004b91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b96  cmp     [rsi], di
0x180004b99  jnz     short loc_180004BA9
0x180004b9b  mov     r8, rbx; unsigned __int64
0x180004b9e  mov     rdx, rbp; unsigned __int16 *
0x180004ba1  mov     rcx, rsi; this
0x180004ba4  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004ba9  mov     rcx, rsi; lpOutputString
0x180004bac  call    cs:__imp_OutputDebugStringW
0x180004bb2  test    byte ptr [rbx+4], 4
0x180004bb6  jnz     short loc_180004BC1
0x180004bb8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180004bbf  jz      short loc_180004BD3
0x180004bc1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004bc8  test    rax, rax
0x180004bcb  jz      short loc_180004BD3
0x180004bcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bd2  nop
0x180004bd3  mov     rbx, [rsp+78h+arg_10]
0x180004bdb  add     rsp, 40h
0x180004bdf  pop     r15
0x180004be1  pop     r14
0x180004be3  pop     r13
0x180004be5  pop     r12
0x180004be7  pop     rdi
0x180004be8  pop     rsi
0x180004be9  pop     rbp
0x180004bea  retn
0x180004beb  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
