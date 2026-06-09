# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180006ca0`
- end: `0x180006f99`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x1800046cc`
- `0x180004a38`
- `0x180028ecc`

## callees

- `0x180004604`
- `0x180006144`
- `0x1800069a8`
- `0x180006ca0`
- `0x180007a80`
- `0x180007aa0`
- `0x180007bf0`
- `0x180007c0c`
- `0x180009764`
- `0x180040010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006dc3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006dc3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006ee2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006ee2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006f54`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006f54`

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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v23);
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
0x180006ca0  mov     [rsp+arg_10], rbx
0x180006ca5  mov     [rsp+arg_8], edx
0x180006ca9  mov     [rsp+arg_0], rcx
0x180006cae  push    rbp
0x180006caf  push    rsi
0x180006cb0  push    rdi
0x180006cb1  push    r12
0x180006cb3  push    r13
0x180006cb5  push    r14
0x180006cb7  push    r15
0x180006cb9  sub     rsp, 40h
0x180006cbd  mov     r12, r9
0x180006cc0  mov     r13, r8
0x180006cc3  mov     r10, rcx
0x180006cc6  xor     eax, eax
0x180006cc8  mov     rsi, [rsp+78h+lpOutputString]
0x180006cd0  mov     [rsi], ax
0x180006cd3  mov     rax, [rsp+78h+arg_60]
0x180006cdb  mov     byte ptr [rax], 0
0x180006cde  mov     r14, [rsp+78h+arg_38]
0x180006ce6  mov     edi, [r14]
0x180006ce9  mov     rbx, [rsp+78h+arg_78]
0x180006cf1  mov     [rbx+8], edi
0x180006cf4  mov     eax, [r14+4]
0x180006cf8  mov     [rbx+0Ch], eax
0x180006cfb  xor     ebp, ebp
0x180006cfd  mov     r15d, [rsp+78h+arg_30]
0x180006d05  mov     ecx, r15d
0x180006d08  test    r15d, r15d
0x180006d0b  jz      short loc_180006D73
0x180006d0d  sub     ecx, 1
0x180006d10  jz      short loc_180006D6A
0x180006d12  sub     ecx, 1
0x180006d15  jz      short loc_180006D25
0x180006d17  cmp     ecx, 1
0x180006d1a  jnz     short loc_180006D7C
0x180006d1c  mov     ecx, edi; this
0x180006d1e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180006d23  jmp     short loc_180006D7A
0x180006d25  test    edi, edi
0x180006d27  js      short loc_180006D61
0x180006d29  mov     edi, 8007029Ch
0x180006d2e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180006d32  mov     rax, [rsp+78h+arg_28]
0x180006d3a  mov     [rsp+78h+var_50], rax; __int64
0x180006d3f  mov     rax, [rsp+78h+arg_20]
0x180006d47  mov     [rsp+78h+var_58], rax; __int64
0x180006d4c  mov     rcx, r10; int
0x180006d4f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180006d54  mov     [rbx+8], edi
0x180006d57  mov     ecx, edi; this
0x180006d59  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006d5e  mov     [rbx+0Ch], eax
0x180006d61  mov     ecx, edi; this
0x180006d63  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180006d68  jmp     short loc_180006D7A
0x180006d6a  mov     ecx, edi; this
0x180006d6c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180006d71  jmp     short loc_180006D7A
0x180006d73  mov     ecx, edi; this
0x180006d75  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180006d7a  mov     ebp, eax
0x180006d7c  mov     [rbx], r15d
0x180006d7f  mov     eax, [rsp+78h+arg_70]
0x180006d86  mov     [rbx+4], eax
0x180006d89  cmp     dword ptr [r14+8], 1
0x180006d8e  jnz     short loc_180006D96
0x180006d90  or      eax, 8
0x180006d93  mov     [rbx+4], eax
0x180006d96  mov     eax, 1
0x180006d9b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180006da3  inc     eax
0x180006da5  mov     [rbx+10h], eax
0x180006da8  mov     rax, [rsp+78h+arg_40]
0x180006db0  xor     edi, edi
0x180006db2  test    rax, rax
0x180006db5  jz      short loc_180006DBC
0x180006db7  cmp     [rax], di
0x180006dba  jnz     short loc_180006DBF
0x180006dbc  mov     rax, rdi
0x180006dbf  mov     [rbx+18h], rax
0x180006dc3  call    cs:__imp_GetCurrentThreadId
0x180006dc9  mov     [rbx+20h], eax
0x180006dcc  mov     [rbx+38h], r13
0x180006dd0  mov     eax, [rsp+78h+arg_8]
0x180006dd7  mov     [rbx+40h], eax
0x180006dda  mov     [rbx+44h], ebp
0x180006ddd  mov     rax, [rsp+78h+arg_20]
0x180006de5  mov     [rbx+28h], rax
0x180006de9  mov     [rbx+30h], r12
0x180006ded  mov     rax, [rsp+78h+arg_28]
0x180006df5  mov     [rbx+88h], rax
0x180006dfc  mov     rax, [rsp+78h+arg_0]
0x180006e04  mov     [rbx+90h], rax
0x180006e0b  mov     [rbx+48h], rdi
0x180006e0f  xorps   xmm0, xmm0
0x180006e12  xor     eax, eax
0x180006e14  movups  xmmword ptr [rbx+68h], xmm0
0x180006e18  mov     [rbx+78h], rax
0x180006e1c  movups  xmmword ptr [rbx+50h], xmm0
0x180006e20  mov     [rbx+60h], rax
0x180006e24  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180006e2b  test    rax, rax
0x180006e2e  jz      short loc_180006E37
0x180006e30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e35  jmp     short loc_180006E3A
0x180006e37  mov     rax, rdi
0x180006e3a  mov     [rbx+80h], rax
0x180006e41  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006e48  test    rax, rax
0x180006e4b  jz      short loc_180006E55
0x180006e4d  mov     rcx, rbx
0x180006e50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e55  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006e5c  test    rax, rax
0x180006e5f  jz      short loc_180006E77
0x180006e61  mov     r8d, 400h
0x180006e67  mov     rdx, [rsp+78h+arg_60]
0x180006e6f  mov     rcx, rbx
0x180006e72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e77  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006e7e  test    rax, rax
0x180006e81  jz      short loc_180006E8B
0x180006e83  mov     rcx, rbx
0x180006e86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e8b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006e92  test    rax, rax
0x180006e95  jz      short loc_180006EA5
0x180006e97  test    byte ptr [rbx+4], 2
0x180006e9b  jnz     short loc_180006EA5
0x180006e9d  mov     rcx, rbx
0x180006ea0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ea5  cmp     [rbx+8], edi
0x180006ea8  jl      short loc_180006EC4
0x180006eaa  cmp     r15d, 3
0x180006eae  jnz     loc_180006F93
0x180006eb4  mov     ecx, 8000FFFFh; this
0x180006eb9  mov     [rbx+8], ecx
0x180006ebc  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006ec1  mov     [rbx+0Ch], eax
0x180006ec4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180006ecb  jnz     short loc_180006EEC
0x180006ecd  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180006ed4  test    rax, rax
0x180006ed7  jz      short loc_180006EE2
0x180006ed9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ede  test    al, al
0x180006ee0  jmp     short loc_180006EEA
0x180006ee2  call    cs:__imp_IsDebuggerPresent
0x180006ee8  test    eax, eax
0x180006eea  jz      short loc_180006EF2
0x180006eec  test    byte ptr [rbx+4], 2
0x180006ef0  jz      short loc_180006F16
0x180006ef2  mov     rax, cs:g_pfnResultLoggingCallback
0x180006ef9  test    rax, rax
0x180006efc  jz      short loc_180006F5A
0x180006efe  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006f05  jnz     short loc_180006F5A
0x180006f07  xor     r8d, r8d
0x180006f0a  xor     edx, edx
0x180006f0c  mov     rcx, rbx
0x180006f0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f14  jmp     short loc_180006F5A
0x180006f16  mov     ebp, 800h
0x180006f1b  mov     rax, cs:g_pfnResultLoggingCallback
0x180006f22  test    rax, rax
0x180006f25  jz      short loc_180006F3E
0x180006f27  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006f2e  jnz     short loc_180006F3E
0x180006f30  mov     r8d, ebp
0x180006f33  mov     rdx, rsi
0x180006f36  mov     rcx, rbx
0x180006f39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f3e  cmp     [rsi], di
0x180006f41  jnz     short loc_180006F51
0x180006f43  mov     r8, rbx; unsigned __int64
0x180006f46  mov     rdx, rbp; unsigned __int16 *
0x180006f49  mov     rcx, rsi; this
0x180006f4c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180006f51  mov     rcx, rsi; lpOutputString
0x180006f54  call    cs:__imp_OutputDebugStringW
0x180006f5a  test    byte ptr [rbx+4], 4
0x180006f5e  jnz     short loc_180006F69
0x180006f60  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180006f67  jz      short loc_180006F7B
0x180006f69  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006f70  test    rax, rax
0x180006f73  jz      short loc_180006F7B
0x180006f75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f7a  nop
0x180006f7b  mov     rbx, [rsp+78h+arg_10]
0x180006f83  add     rsp, 40h
0x180006f87  pop     r15
0x180006f89  pop     r14
0x180006f8b  pop     r13
0x180006f8d  pop     r12
0x180006f8f  pop     rdi
0x180006f90  pop     rsi
0x180006f91  pop     rbp
0x180006f92  retn
0x180006f93  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
