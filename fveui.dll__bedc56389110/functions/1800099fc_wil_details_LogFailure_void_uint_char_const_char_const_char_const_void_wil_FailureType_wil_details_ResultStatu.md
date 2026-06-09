# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800099fc`
- end: `0x180009cf1`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180003d04`
- `0x180003db4`
- `0x180003ea8`

## callees

- `0x180003c58`
- `0x180008bd4`
- `0x1800093a4`
- `0x1800099fc`
- `0x18000a860`
- `0x18000a880`
- `0x18000aa04`
- `0x18000aa20`
- `0x18000cf10`
- `0x18002d010`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x180009cb2`
- `KERNEL32!OutputDebugStringW` at `0x180009cb2`
- `KERNEL32!IsDebuggerPresent` at `0x180009c40`
- `KERNEL32!IsDebuggerPresent` at `0x180009c40`
- `KERNEL32!GetCurrentThreadId` at `0x180009b1f`
- `KERNEL32!GetCurrentThreadId` at `0x180009b1f`

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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v25 = !IsDebuggerPresent())
      : (v25 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v25)
    || (*(_BYTE *)(a16 + 4) & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, 0, 0, v23);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048, v23);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v23);
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
0x1800099fc  mov     [rsp+arg_10], rbx
0x180009a01  mov     [rsp+arg_8], edx
0x180009a05  mov     [rsp+arg_0], rcx
0x180009a0a  push    rbp
0x180009a0b  push    rsi
0x180009a0c  push    rdi
0x180009a0d  push    r12
0x180009a0f  push    r13
0x180009a11  push    r14
0x180009a13  push    r15
0x180009a15  sub     rsp, 40h
0x180009a19  mov     r12, r9
0x180009a1c  mov     r13, r8
0x180009a1f  mov     r10, rcx
0x180009a22  xor     eax, eax
0x180009a24  mov     rsi, [rsp+78h+lpOutputString]
0x180009a2c  mov     [rsi], ax
0x180009a2f  mov     rax, [rsp+78h+arg_60]
0x180009a37  mov     byte ptr [rax], 0
0x180009a3a  mov     r14, [rsp+78h+arg_38]
0x180009a42  mov     edi, [r14]
0x180009a45  mov     rbx, [rsp+78h+arg_78]
0x180009a4d  mov     [rbx+8], edi
0x180009a50  mov     eax, [r14+4]
0x180009a54  mov     [rbx+0Ch], eax
0x180009a57  xor     ebp, ebp
0x180009a59  mov     r15d, [rsp+78h+arg_30]
0x180009a61  mov     ecx, r15d
0x180009a64  test    r15d, r15d
0x180009a67  jz      short loc_180009ACF
0x180009a69  sub     ecx, 1
0x180009a6c  jz      short loc_180009AC6
0x180009a6e  sub     ecx, 1
0x180009a71  jz      short loc_180009A81
0x180009a73  cmp     ecx, 1
0x180009a76  jnz     short loc_180009AD8
0x180009a78  mov     ecx, edi; this
0x180009a7a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180009a7f  jmp     short loc_180009AD6
0x180009a81  test    edi, edi
0x180009a83  js      short loc_180009ABD
0x180009a85  mov     edi, 8007029Ch
0x180009a8a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180009a8e  mov     rax, [rsp+78h+arg_28]
0x180009a96  mov     [rsp+78h+var_50], rax; __int64
0x180009a9b  mov     rax, [rsp+78h+arg_20]
0x180009aa3  mov     [rsp+78h+var_58], rax; __int64
0x180009aa8  mov     rcx, r10; int
0x180009aab  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180009ab0  mov     [rbx+8], edi
0x180009ab3  mov     ecx, edi; this
0x180009ab5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180009aba  mov     [rbx+0Ch], eax
0x180009abd  mov     ecx, edi; this
0x180009abf  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180009ac4  jmp     short loc_180009AD6
0x180009ac6  mov     ecx, edi; this
0x180009ac8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180009acd  jmp     short loc_180009AD6
0x180009acf  mov     ecx, edi; this
0x180009ad1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180009ad6  mov     ebp, eax
0x180009ad8  mov     [rbx], r15d
0x180009adb  mov     eax, [rsp+78h+arg_70]
0x180009ae2  mov     [rbx+4], eax
0x180009ae5  cmp     dword ptr [r14+8], 1
0x180009aea  jnz     short loc_180009AF2
0x180009aec  or      eax, 8
0x180009aef  mov     [rbx+4], eax
0x180009af2  mov     eax, 1
0x180009af7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180009aff  inc     eax
0x180009b01  mov     [rbx+10h], eax
0x180009b04  mov     rax, [rsp+78h+arg_40]
0x180009b0c  xor     edi, edi
0x180009b0e  test    rax, rax
0x180009b11  jz      short loc_180009B18
0x180009b13  cmp     [rax], di
0x180009b16  jnz     short loc_180009B1B
0x180009b18  mov     rax, rdi
0x180009b1b  mov     [rbx+18h], rax
0x180009b1f  call    cs:__imp_GetCurrentThreadId
0x180009b25  mov     [rbx+20h], eax
0x180009b28  mov     [rbx+38h], r13
0x180009b2c  mov     eax, [rsp+78h+arg_8]
0x180009b33  mov     [rbx+40h], eax
0x180009b36  mov     [rbx+44h], ebp
0x180009b39  mov     rax, [rsp+78h+arg_20]
0x180009b41  mov     [rbx+28h], rax
0x180009b45  mov     [rbx+30h], r12
0x180009b49  mov     rax, [rsp+78h+arg_28]
0x180009b51  mov     [rbx+88h], rax
0x180009b58  mov     rax, [rsp+78h+arg_0]
0x180009b60  mov     [rbx+90h], rax
0x180009b67  mov     [rbx+48h], rdi
0x180009b6b  xorps   xmm0, xmm0
0x180009b6e  xor     eax, eax
0x180009b70  movups  xmmword ptr [rbx+68h], xmm0
0x180009b74  mov     [rbx+78h], rax
0x180009b78  movups  xmmword ptr [rbx+50h], xmm0
0x180009b7c  mov     [rbx+60h], rax
0x180009b80  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180009b87  test    rax, rax
0x180009b8a  jz      short loc_180009B93
0x180009b8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b91  jmp     short loc_180009B96
0x180009b93  mov     rax, rdi
0x180009b96  mov     [rbx+80h], rax
0x180009b9d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180009ba4  test    rax, rax
0x180009ba7  jz      short loc_180009BB1
0x180009ba9  mov     rcx, rbx
0x180009bac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bb1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180009bb8  test    rax, rax
0x180009bbb  jz      short loc_180009BD3
0x180009bbd  mov     r8d, 400h
0x180009bc3  mov     rdx, [rsp+78h+arg_60]
0x180009bcb  mov     rcx, rbx
0x180009bce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bd3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180009bda  test    rax, rax
0x180009bdd  jz      short loc_180009BE7
0x180009bdf  mov     rcx, rbx
0x180009be2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009be7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180009bee  test    rax, rax
0x180009bf1  jz      short loc_180009C01
0x180009bf3  test    byte ptr [rbx+4], 2
0x180009bf7  jnz     short loc_180009C01
0x180009bf9  mov     rcx, rbx
0x180009bfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c01  cmp     [rbx+8], edi
0x180009c04  jl      short loc_180009C22
0x180009c06  cmp     r15d, 3
0x180009c0a  jz      short loc_180009C12
0x180009c0c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180009c12  mov     ecx, 8000FFFFh; this
0x180009c17  mov     [rbx+8], ecx
0x180009c1a  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180009c1f  mov     [rbx+0Ch], eax
0x180009c22  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180009c29  jnz     short loc_180009C4A
0x180009c2b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180009c32  test    rax, rax
0x180009c35  jz      short loc_180009C40
0x180009c37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c3c  test    al, al
0x180009c3e  jmp     short loc_180009C48
0x180009c40  call    cs:__imp_IsDebuggerPresent
0x180009c46  test    eax, eax
0x180009c48  jz      short loc_180009C50
0x180009c4a  test    byte ptr [rbx+4], 2
0x180009c4e  jz      short loc_180009C74
0x180009c50  mov     rax, cs:g_pfnResultLoggingCallback
0x180009c57  test    rax, rax
0x180009c5a  jz      short loc_180009CB8
0x180009c5c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180009c63  jnz     short loc_180009CB8
0x180009c65  xor     r8d, r8d
0x180009c68  xor     edx, edx
0x180009c6a  mov     rcx, rbx
0x180009c6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c72  jmp     short loc_180009CB8
0x180009c74  mov     ebp, 800h
0x180009c79  mov     rax, cs:g_pfnResultLoggingCallback
0x180009c80  test    rax, rax
0x180009c83  jz      short loc_180009C9C
0x180009c85  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180009c8c  jnz     short loc_180009C9C
0x180009c8e  mov     r8d, ebp
0x180009c91  mov     rdx, rsi
0x180009c94  mov     rcx, rbx
0x180009c97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c9c  cmp     [rsi], di
0x180009c9f  jnz     short loc_180009CAF
0x180009ca1  mov     r8, rbx; unsigned __int64
0x180009ca4  mov     rdx, rbp; unsigned __int16 *
0x180009ca7  mov     rcx, rsi; this
0x180009caa  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180009caf  mov     rcx, rsi; lpOutputString
0x180009cb2  call    cs:__imp_OutputDebugStringW
0x180009cb8  test    byte ptr [rbx+4], 4
0x180009cbc  jnz     short loc_180009CC7
0x180009cbe  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180009cc5  jz      short loc_180009CD9
0x180009cc7  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180009cce  test    rax, rax
0x180009cd1  jz      short loc_180009CD9
0x180009cd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009cd8  nop
0x180009cd9  mov     rbx, [rsp+78h+arg_10]
0x180009ce1  add     rsp, 40h
0x180009ce5  pop     r15
0x180009ce7  pop     r14
0x180009ce9  pop     r13
0x180009ceb  pop     r12
0x180009ced  pop     rdi
0x180009cee  pop     rsi
0x180009cef  pop     rbp
0x180009cf0  retn
```
