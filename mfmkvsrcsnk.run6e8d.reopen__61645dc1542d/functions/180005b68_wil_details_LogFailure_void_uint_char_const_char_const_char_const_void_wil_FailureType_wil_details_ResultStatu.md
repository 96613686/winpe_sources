# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180005b68`
- end: `0x180005e5d`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x180003ec8`
- `0x180003f88`
- `0x180004084`
- `0x180007cac`

## callees

- `0x180003e08`
- `0x180005144`
- `0x1800058d4`
- `0x180005b68`
- `0x1800061f0`
- `0x180006210`
- `0x180006224`
- `0x180006240`
- `0x1800071ec`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005c8b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005c8b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005e1e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005e1e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005dac`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005dac`

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
0x180005b68  mov     [rsp+arg_10], rbx
0x180005b6d  mov     [rsp+arg_8], edx
0x180005b71  mov     [rsp+arg_0], rcx
0x180005b76  push    rbp
0x180005b77  push    rsi
0x180005b78  push    rdi
0x180005b79  push    r12
0x180005b7b  push    r13
0x180005b7d  push    r14
0x180005b7f  push    r15
0x180005b81  sub     rsp, 40h
0x180005b85  mov     r12, r9
0x180005b88  mov     r13, r8
0x180005b8b  mov     r10, rcx
0x180005b8e  xor     eax, eax
0x180005b90  mov     rsi, [rsp+78h+lpOutputString]
0x180005b98  mov     [rsi], ax
0x180005b9b  mov     rax, [rsp+78h+arg_60]
0x180005ba3  mov     byte ptr [rax], 0
0x180005ba6  mov     r14, [rsp+78h+arg_38]
0x180005bae  mov     edi, [r14]
0x180005bb1  mov     rbx, [rsp+78h+arg_78]
0x180005bb9  mov     [rbx+8], edi
0x180005bbc  mov     eax, [r14+4]
0x180005bc0  mov     [rbx+0Ch], eax
0x180005bc3  xor     ebp, ebp
0x180005bc5  mov     r15d, [rsp+78h+arg_30]
0x180005bcd  mov     ecx, r15d
0x180005bd0  test    r15d, r15d
0x180005bd3  jz      short loc_180005C3B
0x180005bd5  sub     ecx, 1
0x180005bd8  jz      short loc_180005C32
0x180005bda  sub     ecx, 1
0x180005bdd  jz      short loc_180005BED
0x180005bdf  cmp     ecx, 1
0x180005be2  jnz     short loc_180005C44
0x180005be4  mov     ecx, edi; this
0x180005be6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180005beb  jmp     short loc_180005C42
0x180005bed  test    edi, edi
0x180005bef  js      short loc_180005C29
0x180005bf1  mov     edi, 8007029Ch
0x180005bf6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180005bfa  mov     rax, [rsp+78h+arg_28]
0x180005c02  mov     [rsp+78h+var_50], rax; __int64
0x180005c07  mov     rax, [rsp+78h+arg_20]
0x180005c0f  mov     [rsp+78h+var_58], rax; __int64
0x180005c14  mov     rcx, r10; int
0x180005c17  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180005c1c  mov     [rbx+8], edi
0x180005c1f  mov     ecx, edi; this
0x180005c21  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005c26  mov     [rbx+0Ch], eax
0x180005c29  mov     ecx, edi; this
0x180005c2b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180005c30  jmp     short loc_180005C42
0x180005c32  mov     ecx, edi; this
0x180005c34  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005c39  jmp     short loc_180005C42
0x180005c3b  mov     ecx, edi; this
0x180005c3d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180005c42  mov     ebp, eax
0x180005c44  mov     [rbx], r15d
0x180005c47  mov     eax, [rsp+78h+arg_70]
0x180005c4e  mov     [rbx+4], eax
0x180005c51  cmp     dword ptr [r14+8], 1
0x180005c56  jnz     short loc_180005C5E
0x180005c58  or      eax, 8
0x180005c5b  mov     [rbx+4], eax
0x180005c5e  mov     eax, 1
0x180005c63  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005c6b  inc     eax
0x180005c6d  mov     [rbx+10h], eax
0x180005c70  mov     rax, [rsp+78h+arg_40]
0x180005c78  xor     edi, edi
0x180005c7a  test    rax, rax
0x180005c7d  jz      short loc_180005C84
0x180005c7f  cmp     [rax], di
0x180005c82  jnz     short loc_180005C87
0x180005c84  mov     rax, rdi
0x180005c87  mov     [rbx+18h], rax
0x180005c8b  call    cs:__imp_GetCurrentThreadId
0x180005c91  mov     [rbx+20h], eax
0x180005c94  mov     [rbx+38h], r13
0x180005c98  mov     eax, [rsp+78h+arg_8]
0x180005c9f  mov     [rbx+40h], eax
0x180005ca2  mov     [rbx+44h], ebp
0x180005ca5  mov     rax, [rsp+78h+arg_20]
0x180005cad  mov     [rbx+28h], rax
0x180005cb1  mov     [rbx+30h], r12
0x180005cb5  mov     rax, [rsp+78h+arg_28]
0x180005cbd  mov     [rbx+88h], rax
0x180005cc4  mov     rax, [rsp+78h+arg_0]
0x180005ccc  mov     [rbx+90h], rax
0x180005cd3  mov     [rbx+48h], rdi
0x180005cd7  xorps   xmm0, xmm0
0x180005cda  xor     eax, eax
0x180005cdc  movups  xmmword ptr [rbx+68h], xmm0
0x180005ce0  mov     [rbx+78h], rax
0x180005ce4  movups  xmmword ptr [rbx+50h], xmm0
0x180005ce8  mov     [rbx+60h], rax
0x180005cec  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005cf3  test    rax, rax
0x180005cf6  jz      short loc_180005CFF
0x180005cf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cfd  jmp     short loc_180005D02
0x180005cff  mov     rax, rdi
0x180005d02  mov     [rbx+80h], rax
0x180005d09  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005d10  test    rax, rax
0x180005d13  jz      short loc_180005D1D
0x180005d15  mov     rcx, rbx
0x180005d18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d1d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005d24  test    rax, rax
0x180005d27  jz      short loc_180005D3F
0x180005d29  mov     r8d, 400h
0x180005d2f  mov     rdx, [rsp+78h+arg_60]
0x180005d37  mov     rcx, rbx
0x180005d3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d3f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005d46  test    rax, rax
0x180005d49  jz      short loc_180005D53
0x180005d4b  mov     rcx, rbx
0x180005d4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d53  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005d5a  test    rax, rax
0x180005d5d  jz      short loc_180005D6D
0x180005d5f  test    byte ptr [rbx+4], 2
0x180005d63  jnz     short loc_180005D6D
0x180005d65  mov     rcx, rbx
0x180005d68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d6d  cmp     [rbx+8], edi
0x180005d70  jl      short loc_180005D8E
0x180005d72  cmp     r15d, 3
0x180005d76  jz      short loc_180005D7E
0x180005d78  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180005d7e  mov     ecx, 8000FFFFh; this
0x180005d83  mov     [rbx+8], ecx
0x180005d86  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005d8b  mov     [rbx+0Ch], eax
0x180005d8e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180005d95  jnz     short loc_180005DB6
0x180005d97  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005d9e  test    rax, rax
0x180005da1  jz      short loc_180005DAC
0x180005da3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005da8  test    al, al
0x180005daa  jmp     short loc_180005DB4
0x180005dac  call    cs:__imp_IsDebuggerPresent
0x180005db2  test    eax, eax
0x180005db4  jz      short loc_180005DBC
0x180005db6  test    byte ptr [rbx+4], 2
0x180005dba  jz      short loc_180005DE0
0x180005dbc  mov     rax, cs:g_pfnResultLoggingCallback
0x180005dc3  test    rax, rax
0x180005dc6  jz      short loc_180005E24
0x180005dc8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005dcf  jnz     short loc_180005E24
0x180005dd1  xor     r8d, r8d
0x180005dd4  xor     edx, edx
0x180005dd6  mov     rcx, rbx
0x180005dd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005dde  jmp     short loc_180005E24
0x180005de0  mov     ebp, 800h
0x180005de5  mov     rax, cs:g_pfnResultLoggingCallback
0x180005dec  test    rax, rax
0x180005def  jz      short loc_180005E08
0x180005df1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005df8  jnz     short loc_180005E08
0x180005dfa  mov     r8d, ebp
0x180005dfd  mov     rdx, rsi
0x180005e00  mov     rcx, rbx
0x180005e03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e08  cmp     [rsi], di
0x180005e0b  jnz     short loc_180005E1B
0x180005e0d  mov     r8, rbx; unsigned __int64
0x180005e10  mov     rdx, rbp; unsigned __int16 *
0x180005e13  mov     rcx, rsi; this
0x180005e16  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005e1b  mov     rcx, rsi; lpOutputString
0x180005e1e  call    cs:__imp_OutputDebugStringW
0x180005e24  test    byte ptr [rbx+4], 4
0x180005e28  jnz     short loc_180005E33
0x180005e2a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180005e31  jz      short loc_180005E45
0x180005e33  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005e3a  test    rax, rax
0x180005e3d  jz      short loc_180005E45
0x180005e3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e44  nop
0x180005e45  mov     rbx, [rsp+78h+arg_10]
0x180005e4d  add     rsp, 40h
0x180005e51  pop     r15
0x180005e53  pop     r14
0x180005e55  pop     r13
0x180005e57  pop     r12
0x180005e59  pop     rdi
0x180005e5a  pop     rsi
0x180005e5b  pop     rbp
0x180005e5c  retn
```
