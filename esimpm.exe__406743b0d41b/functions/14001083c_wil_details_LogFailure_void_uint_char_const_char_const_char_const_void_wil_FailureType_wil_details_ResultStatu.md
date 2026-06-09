# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x14001083c`
- end: `0x140010b35`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x14000dbb8`

## callees

- `0x14000d5d4`
- `0x14000fdf4`
- `0x140010590`
- `0x14001083c`
- `0x1400114f0`
- `0x140011510`
- `0x14001163c`
- `0x140011658`
- `0x140013d7c`
- `0x14003e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001095f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001095f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140010af0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140010af0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140010a7e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140010a7e`

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
    ModuleName = wil::details::g_pfnGetModuleName(v24);
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
      : (v27 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v24) == 0),
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
      wil::details::g_pfnDebugBreak(v24);
  }
}

```

## disassembly

```asm
0x14001083c  mov     [rsp+arg_10], rbx
0x140010841  mov     [rsp+arg_8], edx
0x140010845  mov     [rsp+arg_0], rcx
0x14001084a  push    rbp
0x14001084b  push    rsi
0x14001084c  push    rdi
0x14001084d  push    r12
0x14001084f  push    r13
0x140010851  push    r14
0x140010853  push    r15
0x140010855  sub     rsp, 40h
0x140010859  mov     r12, r9
0x14001085c  mov     r13, r8
0x14001085f  mov     r10, rcx
0x140010862  xor     eax, eax
0x140010864  mov     rsi, [rsp+78h+lpOutputString]
0x14001086c  mov     [rsi], ax
0x14001086f  mov     rax, [rsp+78h+arg_60]
0x140010877  mov     byte ptr [rax], 0
0x14001087a  mov     r14, [rsp+78h+arg_38]
0x140010882  mov     edi, [r14]
0x140010885  mov     rbx, [rsp+78h+arg_78]
0x14001088d  mov     [rbx+8], edi
0x140010890  mov     eax, [r14+4]
0x140010894  mov     [rbx+0Ch], eax
0x140010897  xor     ebp, ebp
0x140010899  mov     r15d, [rsp+78h+arg_30]
0x1400108a1  mov     ecx, r15d
0x1400108a4  test    r15d, r15d
0x1400108a7  jz      short loc_14001090F
0x1400108a9  sub     ecx, 1
0x1400108ac  jz      short loc_140010906
0x1400108ae  sub     ecx, 1
0x1400108b1  jz      short loc_1400108C1
0x1400108b3  cmp     ecx, 1
0x1400108b6  jnz     short loc_140010918
0x1400108b8  mov     ecx, edi; this
0x1400108ba  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1400108bf  jmp     short loc_140010916
0x1400108c1  test    edi, edi
0x1400108c3  js      short loc_1400108FD
0x1400108c5  mov     edi, 8007029Ch
0x1400108ca  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1400108ce  mov     rax, [rsp+78h+arg_28]
0x1400108d6  mov     [rsp+78h+var_50], rax; __int64
0x1400108db  mov     rax, [rsp+78h+arg_20]
0x1400108e3  mov     [rsp+78h+var_58], rax; __int64
0x1400108e8  mov     rcx, r10; int
0x1400108eb  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1400108f0  mov     [rbx+8], edi
0x1400108f3  mov     ecx, edi; this
0x1400108f5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400108fa  mov     [rbx+0Ch], eax
0x1400108fd  mov     ecx, edi; this
0x1400108ff  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140010904  jmp     short loc_140010916
0x140010906  mov     ecx, edi; this
0x140010908  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x14001090d  jmp     short loc_140010916
0x14001090f  mov     ecx, edi; this
0x140010911  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140010916  mov     ebp, eax
0x140010918  mov     [rbx], r15d
0x14001091b  mov     eax, [rsp+78h+arg_70]
0x140010922  mov     [rbx+4], eax
0x140010925  cmp     dword ptr [r14+8], 1
0x14001092a  jnz     short loc_140010932
0x14001092c  or      eax, 8
0x14001092f  mov     [rbx+4], eax
0x140010932  mov     eax, 1
0x140010937  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14001093f  inc     eax
0x140010941  mov     [rbx+10h], eax
0x140010944  mov     rax, [rsp+78h+arg_40]
0x14001094c  xor     edi, edi
0x14001094e  test    rax, rax
0x140010951  jz      short loc_140010958
0x140010953  cmp     [rax], di
0x140010956  jnz     short loc_14001095B
0x140010958  mov     rax, rdi
0x14001095b  mov     [rbx+18h], rax
0x14001095f  call    cs:__imp_GetCurrentThreadId
0x140010965  mov     [rbx+20h], eax
0x140010968  mov     [rbx+38h], r13
0x14001096c  mov     eax, [rsp+78h+arg_8]
0x140010973  mov     [rbx+40h], eax
0x140010976  mov     [rbx+44h], ebp
0x140010979  mov     rax, [rsp+78h+arg_20]
0x140010981  mov     [rbx+28h], rax
0x140010985  mov     [rbx+30h], r12
0x140010989  mov     rax, [rsp+78h+arg_28]
0x140010991  mov     [rbx+88h], rax
0x140010998  mov     rax, [rsp+78h+arg_0]
0x1400109a0  mov     [rbx+90h], rax
0x1400109a7  mov     [rbx+48h], rdi
0x1400109ab  xorps   xmm0, xmm0
0x1400109ae  xor     eax, eax
0x1400109b0  movups  xmmword ptr [rbx+68h], xmm0
0x1400109b4  mov     [rbx+78h], rax
0x1400109b8  movups  xmmword ptr [rbx+50h], xmm0
0x1400109bc  mov     [rbx+60h], rax
0x1400109c0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1400109c7  test    rax, rax
0x1400109ca  jz      short loc_1400109D3
0x1400109cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400109d1  jmp     short loc_1400109D6
0x1400109d3  mov     rax, rdi
0x1400109d6  mov     [rbx+80h], rax
0x1400109dd  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400109e4  test    rax, rax
0x1400109e7  jz      short loc_1400109F1
0x1400109e9  mov     rcx, rbx
0x1400109ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400109f1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400109f8  test    rax, rax
0x1400109fb  jz      short loc_140010A13
0x1400109fd  mov     r8d, 400h
0x140010a03  mov     rdx, [rsp+78h+arg_60]
0x140010a0b  mov     rcx, rbx
0x140010a0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010a13  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140010a1a  test    rax, rax
0x140010a1d  jz      short loc_140010A27
0x140010a1f  mov     rcx, rbx
0x140010a22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010a27  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140010a2e  test    rax, rax
0x140010a31  jz      short loc_140010A41
0x140010a33  test    byte ptr [rbx+4], 2
0x140010a37  jnz     short loc_140010A41
0x140010a39  mov     rcx, rbx
0x140010a3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010a41  cmp     [rbx+8], edi
0x140010a44  jl      short loc_140010A60
0x140010a46  cmp     r15d, 3
0x140010a4a  jnz     loc_140010B2F
0x140010a50  mov     ecx, 8000FFFFh; this
0x140010a55  mov     [rbx+8], ecx
0x140010a58  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140010a5d  mov     [rbx+0Ch], eax
0x140010a60  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x140010a67  jnz     short loc_140010A88
0x140010a69  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140010a70  test    rax, rax
0x140010a73  jz      short loc_140010A7E
0x140010a75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010a7a  test    al, al
0x140010a7c  jmp     short loc_140010A86
0x140010a7e  call    cs:__imp_IsDebuggerPresent
0x140010a84  test    eax, eax
0x140010a86  jz      short loc_140010A8E
0x140010a88  test    byte ptr [rbx+4], 2
0x140010a8c  jz      short loc_140010AB2
0x140010a8e  mov     rax, cs:g_pfnResultLoggingCallback
0x140010a95  test    rax, rax
0x140010a98  jz      short loc_140010AF6
0x140010a9a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140010aa1  jnz     short loc_140010AF6
0x140010aa3  xor     r8d, r8d
0x140010aa6  xor     edx, edx
0x140010aa8  mov     rcx, rbx
0x140010aab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010ab0  jmp     short loc_140010AF6
0x140010ab2  mov     ebp, 800h
0x140010ab7  mov     rax, cs:g_pfnResultLoggingCallback
0x140010abe  test    rax, rax
0x140010ac1  jz      short loc_140010ADA
0x140010ac3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140010aca  jnz     short loc_140010ADA
0x140010acc  mov     r8d, ebp
0x140010acf  mov     rdx, rsi
0x140010ad2  mov     rcx, rbx
0x140010ad5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010ada  cmp     [rsi], di
0x140010add  jnz     short loc_140010AED
0x140010adf  mov     r8, rbx; unsigned __int64
0x140010ae2  mov     rdx, rbp; unsigned __int16 *
0x140010ae5  mov     rcx, rsi; this
0x140010ae8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140010aed  mov     rcx, rsi; lpOutputString
0x140010af0  call    cs:__imp_OutputDebugStringW
0x140010af6  test    byte ptr [rbx+4], 4
0x140010afa  jnz     short loc_140010B05
0x140010afc  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x140010b03  jz      short loc_140010B17
0x140010b05  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140010b0c  test    rax, rax
0x140010b0f  jz      short loc_140010B17
0x140010b11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010b16  nop
0x140010b17  mov     rbx, [rsp+78h+arg_10]
0x140010b1f  add     rsp, 40h
0x140010b23  pop     r15
0x140010b25  pop     r14
0x140010b27  pop     r13
0x140010b29  pop     r12
0x140010b2b  pop     rdi
0x140010b2c  pop     rsi
0x140010b2d  pop     rbp
0x140010b2e  retn
0x140010b2f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
