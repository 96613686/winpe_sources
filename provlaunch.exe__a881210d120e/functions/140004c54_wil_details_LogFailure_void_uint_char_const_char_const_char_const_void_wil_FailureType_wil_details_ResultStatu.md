# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140004c54`
- end: `0x140004f4d`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140002fbc`

## callees

- `0x140002714`
- `0x1400042f4`
- `0x140004a90`
- `0x140004c54`
- `0x1400051e4`
- `0x140005200`
- `0x140005214`
- `0x140005230`
- `0x140006474`
- `0x14000b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004d77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004d77`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140004e96`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140004e96`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140004f08`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140004f08`

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
0x140004c54  mov     [rsp+arg_10], rbx
0x140004c59  mov     [rsp+arg_8], edx
0x140004c5d  mov     [rsp+arg_0], rcx
0x140004c62  push    rbp
0x140004c63  push    rsi
0x140004c64  push    rdi
0x140004c65  push    r12
0x140004c67  push    r13
0x140004c69  push    r14
0x140004c6b  push    r15
0x140004c6d  sub     rsp, 40h
0x140004c71  mov     r12, r9
0x140004c74  mov     r13, r8
0x140004c77  mov     r10, rcx
0x140004c7a  xor     eax, eax
0x140004c7c  mov     rsi, [rsp+78h+lpOutputString]
0x140004c84  mov     [rsi], ax
0x140004c87  mov     rax, [rsp+78h+arg_60]
0x140004c8f  mov     byte ptr [rax], 0
0x140004c92  mov     r14, [rsp+78h+arg_38]
0x140004c9a  mov     edi, [r14]
0x140004c9d  mov     rbx, [rsp+78h+arg_78]
0x140004ca5  mov     [rbx+8], edi
0x140004ca8  mov     eax, [r14+4]
0x140004cac  mov     [rbx+0Ch], eax
0x140004caf  xor     ebp, ebp
0x140004cb1  mov     r15d, [rsp+78h+arg_30]
0x140004cb9  mov     ecx, r15d
0x140004cbc  test    r15d, r15d
0x140004cbf  jz      short loc_140004D27
0x140004cc1  sub     ecx, 1
0x140004cc4  jz      short loc_140004D1E
0x140004cc6  sub     ecx, 1
0x140004cc9  jz      short loc_140004CD9
0x140004ccb  cmp     ecx, 1
0x140004cce  jnz     short loc_140004D30
0x140004cd0  mov     ecx, edi; this
0x140004cd2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140004cd7  jmp     short loc_140004D2E
0x140004cd9  test    edi, edi
0x140004cdb  js      short loc_140004D15
0x140004cdd  mov     edi, 8007029Ch
0x140004ce2  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x140004ce6  mov     rax, [rsp+78h+arg_28]
0x140004cee  mov     [rsp+78h+var_50], rax; __int64
0x140004cf3  mov     rax, [rsp+78h+arg_20]
0x140004cfb  mov     [rsp+78h+var_58], rax; __int64
0x140004d00  mov     rcx, r10; int
0x140004d03  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140004d08  mov     [rbx+8], edi
0x140004d0b  mov     ecx, edi; this
0x140004d0d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140004d12  mov     [rbx+0Ch], eax
0x140004d15  mov     ecx, edi; this
0x140004d17  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140004d1c  jmp     short loc_140004D2E
0x140004d1e  mov     ecx, edi; this
0x140004d20  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140004d25  jmp     short loc_140004D2E
0x140004d27  mov     ecx, edi; this
0x140004d29  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140004d2e  mov     ebp, eax
0x140004d30  mov     [rbx], r15d
0x140004d33  mov     eax, [rsp+78h+arg_70]
0x140004d3a  mov     [rbx+4], eax
0x140004d3d  cmp     dword ptr [r14+8], 1
0x140004d42  jnz     short loc_140004D4A
0x140004d44  or      eax, 8
0x140004d47  mov     [rbx+4], eax
0x140004d4a  mov     eax, 1
0x140004d4f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140004d57  inc     eax
0x140004d59  mov     [rbx+10h], eax
0x140004d5c  mov     rax, [rsp+78h+arg_40]
0x140004d64  xor     edi, edi
0x140004d66  test    rax, rax
0x140004d69  jz      short loc_140004D70
0x140004d6b  cmp     [rax], di
0x140004d6e  jnz     short loc_140004D73
0x140004d70  mov     rax, rdi
0x140004d73  mov     [rbx+18h], rax
0x140004d77  call    cs:__imp_GetCurrentThreadId
0x140004d7d  mov     [rbx+20h], eax
0x140004d80  mov     [rbx+38h], r13
0x140004d84  mov     eax, [rsp+78h+arg_8]
0x140004d8b  mov     [rbx+40h], eax
0x140004d8e  mov     [rbx+44h], ebp
0x140004d91  mov     rax, [rsp+78h+arg_20]
0x140004d99  mov     [rbx+28h], rax
0x140004d9d  mov     [rbx+30h], r12
0x140004da1  mov     rax, [rsp+78h+arg_28]
0x140004da9  mov     [rbx+88h], rax
0x140004db0  mov     rax, [rsp+78h+arg_0]
0x140004db8  mov     [rbx+90h], rax
0x140004dbf  mov     [rbx+48h], rdi
0x140004dc3  xorps   xmm0, xmm0
0x140004dc6  xor     eax, eax
0x140004dc8  movups  xmmword ptr [rbx+68h], xmm0
0x140004dcc  mov     [rbx+78h], rax
0x140004dd0  movups  xmmword ptr [rbx+50h], xmm0
0x140004dd4  mov     [rbx+60h], rax
0x140004dd8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140004ddf  test    rax, rax
0x140004de2  jz      short loc_140004DEB
0x140004de4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004de9  jmp     short loc_140004DEE
0x140004deb  mov     rax, rdi
0x140004dee  mov     [rbx+80h], rax
0x140004df5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140004dfc  test    rax, rax
0x140004dff  jz      short loc_140004E09
0x140004e01  mov     rcx, rbx
0x140004e04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004e09  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140004e10  test    rax, rax
0x140004e13  jz      short loc_140004E2B
0x140004e15  mov     r8d, 400h
0x140004e1b  mov     rdx, [rsp+78h+arg_60]
0x140004e23  mov     rcx, rbx
0x140004e26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004e2b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140004e32  test    rax, rax
0x140004e35  jz      short loc_140004E3F
0x140004e37  mov     rcx, rbx
0x140004e3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004e3f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140004e46  test    rax, rax
0x140004e49  jz      short loc_140004E59
0x140004e4b  test    byte ptr [rbx+4], 2
0x140004e4f  jnz     short loc_140004E59
0x140004e51  mov     rcx, rbx
0x140004e54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004e59  cmp     [rbx+8], edi
0x140004e5c  jl      short loc_140004E78
0x140004e5e  cmp     r15d, 3
0x140004e62  jnz     loc_140004F47
0x140004e68  mov     ecx, 8000FFFFh; this
0x140004e6d  mov     [rbx+8], ecx
0x140004e70  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140004e75  mov     [rbx+0Ch], eax
0x140004e78  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x140004e7f  jnz     short loc_140004EA0
0x140004e81  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140004e88  test    rax, rax
0x140004e8b  jz      short loc_140004E96
0x140004e8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004e92  test    al, al
0x140004e94  jmp     short loc_140004E9E
0x140004e96  call    cs:__imp_IsDebuggerPresent
0x140004e9c  test    eax, eax
0x140004e9e  jz      short loc_140004EA6
0x140004ea0  test    byte ptr [rbx+4], 2
0x140004ea4  jz      short loc_140004ECA
0x140004ea6  mov     rax, cs:g_pfnResultLoggingCallback
0x140004ead  test    rax, rax
0x140004eb0  jz      short loc_140004F0E
0x140004eb2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140004eb9  jnz     short loc_140004F0E
0x140004ebb  xor     r8d, r8d
0x140004ebe  xor     edx, edx
0x140004ec0  mov     rcx, rbx
0x140004ec3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004ec8  jmp     short loc_140004F0E
0x140004eca  mov     ebp, 800h
0x140004ecf  mov     rax, cs:g_pfnResultLoggingCallback
0x140004ed6  test    rax, rax
0x140004ed9  jz      short loc_140004EF2
0x140004edb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140004ee2  jnz     short loc_140004EF2
0x140004ee4  mov     r8d, ebp
0x140004ee7  mov     rdx, rsi
0x140004eea  mov     rcx, rbx
0x140004eed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004ef2  cmp     [rsi], di
0x140004ef5  jnz     short loc_140004F05
0x140004ef7  mov     r8, rbx; unsigned __int64
0x140004efa  mov     rdx, rbp; unsigned __int16 *
0x140004efd  mov     rcx, rsi; this
0x140004f00  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140004f05  mov     rcx, rsi; lpOutputString
0x140004f08  call    cs:__imp_OutputDebugStringW
0x140004f0e  test    byte ptr [rbx+4], 4
0x140004f12  jnz     short loc_140004F1D
0x140004f14  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x140004f1b  jz      short loc_140004F2F
0x140004f1d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140004f24  test    rax, rax
0x140004f27  jz      short loc_140004F2F
0x140004f29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004f2e  nop
0x140004f2f  mov     rbx, [rsp+78h+arg_10]
0x140004f37  add     rsp, 40h
0x140004f3b  pop     r15
0x140004f3d  pop     r14
0x140004f3f  pop     r13
0x140004f41  pop     r12
0x140004f43  pop     rdi
0x140004f44  pop     rsi
0x140004f45  pop     rbp
0x140004f46  retn
0x140004f47  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
