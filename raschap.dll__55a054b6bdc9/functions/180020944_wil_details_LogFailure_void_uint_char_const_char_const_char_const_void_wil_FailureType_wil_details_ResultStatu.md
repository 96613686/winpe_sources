# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180020944`
- end: `0x180020c39`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x18001e92c`
- `0x18001e9dc`
- `0x18001ead0`

## callees

- `0x180012748`
- `0x18001e880`
- `0x180020064`
- `0x180020944`
- `0x180021548`
- `0x180021570`
- `0x18002162c`
- `0x180021648`
- `0x180022cf8`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180020bfa`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180020bfa`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180020b88`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180020b88`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020a67`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020a67`

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
0x180020944  mov     [rsp+arg_10], rbx
0x180020949  mov     [rsp+arg_8], edx
0x18002094d  mov     [rsp+arg_0], rcx
0x180020952  push    rbp
0x180020953  push    rsi
0x180020954  push    rdi
0x180020955  push    r12
0x180020957  push    r13
0x180020959  push    r14
0x18002095b  push    r15
0x18002095d  sub     rsp, 40h
0x180020961  mov     r12, r9
0x180020964  mov     r13, r8
0x180020967  mov     r10, rcx
0x18002096a  xor     eax, eax
0x18002096c  mov     rsi, [rsp+78h+lpOutputString]
0x180020974  mov     [rsi], ax
0x180020977  mov     rax, [rsp+78h+arg_60]
0x18002097f  mov     byte ptr [rax], 0
0x180020982  mov     r14, [rsp+78h+arg_38]
0x18002098a  mov     edi, [r14]
0x18002098d  mov     rbx, [rsp+78h+arg_78]
0x180020995  mov     [rbx+8], edi
0x180020998  mov     eax, [r14+4]
0x18002099c  mov     [rbx+0Ch], eax
0x18002099f  xor     ebp, ebp
0x1800209a1  mov     r15d, [rsp+78h+arg_30]
0x1800209a9  mov     ecx, r15d
0x1800209ac  test    r15d, r15d
0x1800209af  jz      short loc_180020A17
0x1800209b1  sub     ecx, 1
0x1800209b4  jz      short loc_180020A0E
0x1800209b6  sub     ecx, 1
0x1800209b9  jz      short loc_1800209C9
0x1800209bb  cmp     ecx, 1
0x1800209be  jnz     short loc_180020A20
0x1800209c0  mov     ecx, edi; this
0x1800209c2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800209c7  jmp     short loc_180020A1E
0x1800209c9  test    edi, edi
0x1800209cb  js      short loc_180020A05
0x1800209cd  mov     edi, 8007029Ch
0x1800209d2  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800209d6  mov     rax, [rsp+78h+arg_28]
0x1800209de  mov     [rsp+78h+var_50], rax; __int64
0x1800209e3  mov     rax, [rsp+78h+arg_20]
0x1800209eb  mov     [rsp+78h+var_58], rax; __int64
0x1800209f0  mov     rcx, r10; int
0x1800209f3  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800209f8  mov     [rbx+8], edi
0x1800209fb  mov     ecx, edi; this
0x1800209fd  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180020a02  mov     [rbx+0Ch], eax
0x180020a05  mov     ecx, edi; this
0x180020a07  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180020a0c  jmp     short loc_180020A1E
0x180020a0e  mov     ecx, edi; this
0x180020a10  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180020a15  jmp     short loc_180020A1E
0x180020a17  mov     ecx, edi; this
0x180020a19  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180020a1e  mov     ebp, eax
0x180020a20  mov     [rbx], r15d
0x180020a23  mov     eax, [rsp+78h+arg_70]
0x180020a2a  mov     [rbx+4], eax
0x180020a2d  cmp     dword ptr [r14+8], 1
0x180020a32  jnz     short loc_180020A3A
0x180020a34  or      eax, 8
0x180020a37  mov     [rbx+4], eax
0x180020a3a  mov     eax, 1
0x180020a3f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180020a47  inc     eax
0x180020a49  mov     [rbx+10h], eax
0x180020a4c  mov     rax, [rsp+78h+arg_40]
0x180020a54  xor     edi, edi
0x180020a56  test    rax, rax
0x180020a59  jz      short loc_180020A60
0x180020a5b  cmp     [rax], di
0x180020a5e  jnz     short loc_180020A63
0x180020a60  mov     rax, rdi
0x180020a63  mov     [rbx+18h], rax
0x180020a67  call    cs:__imp_GetCurrentThreadId
0x180020a6d  mov     [rbx+20h], eax
0x180020a70  mov     [rbx+38h], r13
0x180020a74  mov     eax, [rsp+78h+arg_8]
0x180020a7b  mov     [rbx+40h], eax
0x180020a7e  mov     [rbx+44h], ebp
0x180020a81  mov     rax, [rsp+78h+arg_20]
0x180020a89  mov     [rbx+28h], rax
0x180020a8d  mov     [rbx+30h], r12
0x180020a91  mov     rax, [rsp+78h+arg_28]
0x180020a99  mov     [rbx+88h], rax
0x180020aa0  mov     rax, [rsp+78h+arg_0]
0x180020aa8  mov     [rbx+90h], rax
0x180020aaf  mov     [rbx+48h], rdi
0x180020ab3  xorps   xmm0, xmm0
0x180020ab6  xor     eax, eax
0x180020ab8  movups  xmmword ptr [rbx+68h], xmm0
0x180020abc  mov     [rbx+78h], rax
0x180020ac0  movups  xmmword ptr [rbx+50h], xmm0
0x180020ac4  mov     [rbx+60h], rax
0x180020ac8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180020acf  test    rax, rax
0x180020ad2  jz      short loc_180020ADB
0x180020ad4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ad9  jmp     short loc_180020ADE
0x180020adb  mov     rax, rdi
0x180020ade  mov     [rbx+80h], rax
0x180020ae5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180020aec  test    rax, rax
0x180020aef  jz      short loc_180020AF9
0x180020af1  mov     rcx, rbx
0x180020af4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020af9  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180020b00  test    rax, rax
0x180020b03  jz      short loc_180020B1B
0x180020b05  mov     r8d, 400h
0x180020b0b  mov     rdx, [rsp+78h+arg_60]
0x180020b13  mov     rcx, rbx
0x180020b16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b1b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180020b22  test    rax, rax
0x180020b25  jz      short loc_180020B2F
0x180020b27  mov     rcx, rbx
0x180020b2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b2f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180020b36  test    rax, rax
0x180020b39  jz      short loc_180020B49
0x180020b3b  test    byte ptr [rbx+4], 2
0x180020b3f  jnz     short loc_180020B49
0x180020b41  mov     rcx, rbx
0x180020b44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b49  cmp     [rbx+8], edi
0x180020b4c  jl      short loc_180020B6A
0x180020b4e  cmp     r15d, 3
0x180020b52  jz      short loc_180020B5A
0x180020b54  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180020b5a  mov     ecx, 8000FFFFh; this
0x180020b5f  mov     [rbx+8], ecx
0x180020b62  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180020b67  mov     [rbx+0Ch], eax
0x180020b6a  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180020b71  jnz     short loc_180020B92
0x180020b73  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180020b7a  test    rax, rax
0x180020b7d  jz      short loc_180020B88
0x180020b7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b84  test    al, al
0x180020b86  jmp     short loc_180020B90
0x180020b88  call    cs:__imp_IsDebuggerPresent
0x180020b8e  test    eax, eax
0x180020b90  jz      short loc_180020B98
0x180020b92  test    byte ptr [rbx+4], 2
0x180020b96  jz      short loc_180020BBC
0x180020b98  mov     rax, cs:g_pfnResultLoggingCallback
0x180020b9f  test    rax, rax
0x180020ba2  jz      short loc_180020C00
0x180020ba4  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180020bab  jnz     short loc_180020C00
0x180020bad  xor     r8d, r8d
0x180020bb0  xor     edx, edx
0x180020bb2  mov     rcx, rbx
0x180020bb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020bba  jmp     short loc_180020C00
0x180020bbc  mov     ebp, 800h
0x180020bc1  mov     rax, cs:g_pfnResultLoggingCallback
0x180020bc8  test    rax, rax
0x180020bcb  jz      short loc_180020BE4
0x180020bcd  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180020bd4  jnz     short loc_180020BE4
0x180020bd6  mov     r8d, ebp
0x180020bd9  mov     rdx, rsi
0x180020bdc  mov     rcx, rbx
0x180020bdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020be4  cmp     [rsi], di
0x180020be7  jnz     short loc_180020BF7
0x180020be9  mov     r8, rbx; unsigned __int64
0x180020bec  mov     rdx, rbp; unsigned __int16 *
0x180020bef  mov     rcx, rsi; this
0x180020bf2  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180020bf7  mov     rcx, rsi; lpOutputString
0x180020bfa  call    cs:__imp_OutputDebugStringW
0x180020c00  test    byte ptr [rbx+4], 4
0x180020c04  jnz     short loc_180020C0F
0x180020c06  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180020c0d  jz      short loc_180020C21
0x180020c0f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180020c16  test    rax, rax
0x180020c19  jz      short loc_180020C21
0x180020c1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c20  nop
0x180020c21  mov     rbx, [rsp+78h+arg_10]
0x180020c29  add     rsp, 40h
0x180020c2d  pop     r15
0x180020c2f  pop     r14
0x180020c31  pop     r13
0x180020c33  pop     r12
0x180020c35  pop     rdi
0x180020c36  pop     rsi
0x180020c37  pop     rbp
0x180020c38  retn
```
