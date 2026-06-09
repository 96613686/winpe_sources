# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180013b30`
- end: `0x180013e24`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `756`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180010a94`
- `0x180010b44`
- `0x180010c38`

## callees

- `0x18000ef10`
- `0x1800109e8`
- `0x180012f34`
- `0x180013b30`
- `0x180014ddc`
- `0x180014e00`
- `0x180014ebc`
- `0x180014ed8`
- `0x180017438`
- `0x180023010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180013c53`
- `KERNEL32!GetCurrentThreadId` at `0x180013c53`
- `KERNEL32!IsDebuggerPresent` at `0x180013d74`
- `KERNEL32!IsDebuggerPresent` at `0x180013d74`
- `KERNEL32!OutputDebugStringW` at `0x180013de6`
- `KERNEL32!OutputDebugStringW` at `0x180013de6`

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
0x180013b30  mov     [rsp+arg_10], rbx
0x180013b35  mov     [rsp+arg_8], edx
0x180013b39  mov     [rsp+arg_0], rcx
0x180013b3e  push    rbp
0x180013b3f  push    rsi
0x180013b40  push    rdi
0x180013b41  push    r12
0x180013b43  push    r13
0x180013b45  push    r14
0x180013b47  push    r15
0x180013b49  sub     rsp, 40h
0x180013b4d  mov     r14, [rsp+78h+arg_38]
0x180013b55  xor     eax, eax
0x180013b57  mov     rbx, [rsp+78h+arg_78]
0x180013b5f  xor     ebp, ebp
0x180013b61  mov     r15d, [rsp+78h+arg_30]
0x180013b69  mov     r10, rcx
0x180013b6c  mov     rsi, [rsp+78h+lpOutputString]
0x180013b74  mov     r12, r9
0x180013b77  mov     r13, r8
0x180013b7a  mov     ecx, r15d
0x180013b7d  mov     [rsi], ax
0x180013b80  mov     rax, [rsp+78h+arg_60]
0x180013b88  mov     byte ptr [rax], 0
0x180013b8b  mov     edi, [r14]
0x180013b8e  mov     [rbx+8], edi
0x180013b91  mov     eax, [r14+4]
0x180013b95  mov     [rbx+0Ch], eax
0x180013b98  test    r15d, r15d
0x180013b9b  jz      short loc_180013C03
0x180013b9d  sub     ecx, 1
0x180013ba0  jz      short loc_180013BFA
0x180013ba2  sub     ecx, 1
0x180013ba5  jz      short loc_180013BB5
0x180013ba7  cmp     ecx, 1
0x180013baa  jnz     short loc_180013C0C
0x180013bac  mov     ecx, edi; this
0x180013bae  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180013bb3  jmp     short loc_180013C0A
0x180013bb5  test    edi, edi
0x180013bb7  js      short loc_180013BF1
0x180013bb9  mov     rax, [rsp+78h+arg_28]
0x180013bc1  mov     edi, 8007029Ch
0x180013bc6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180013bca  mov     rcx, r10; int
0x180013bcd  mov     [rsp+78h+var_50], rax; __int64
0x180013bd2  mov     rax, [rsp+78h+arg_20]
0x180013bda  mov     [rsp+78h+var_58], rax; __int64
0x180013bdf  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180013be4  mov     ecx, edi; this
0x180013be6  mov     [rbx+8], edi
0x180013be9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180013bee  mov     [rbx+0Ch], eax
0x180013bf1  mov     ecx, edi; this
0x180013bf3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180013bf8  jmp     short loc_180013C0A
0x180013bfa  mov     ecx, edi; this
0x180013bfc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180013c01  jmp     short loc_180013C0A
0x180013c03  mov     ecx, edi; this
0x180013c05  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180013c0a  mov     ebp, eax
0x180013c0c  mov     eax, [rsp+78h+arg_70]
0x180013c13  mov     [rbx+4], eax
0x180013c16  mov     [rbx], r15d
0x180013c19  cmp     dword ptr [r14+8], 1
0x180013c1e  jnz     short loc_180013C26
0x180013c20  or      eax, 8
0x180013c23  mov     [rbx+4], eax
0x180013c26  mov     eax, 1
0x180013c2b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180013c33  inc     eax
0x180013c35  xor     edi, edi
0x180013c37  mov     [rbx+10h], eax
0x180013c3a  mov     rax, [rsp+78h+arg_40]
0x180013c42  test    rax, rax
0x180013c45  jz      short loc_180013C4C
0x180013c47  cmp     [rax], di
0x180013c4a  jnz     short loc_180013C4F
0x180013c4c  mov     rax, rdi
0x180013c4f  mov     [rbx+18h], rax
0x180013c53  call    cs:__imp_GetCurrentThreadId
0x180013c59  mov     [rbx+38h], r13
0x180013c5d  xorps   xmm0, xmm0
0x180013c60  mov     [rbx+20h], eax
0x180013c63  mov     eax, [rsp+78h+arg_8]
0x180013c6a  mov     [rbx+40h], eax
0x180013c6d  mov     rax, [rsp+78h+arg_20]
0x180013c75  mov     [rbx+28h], rax
0x180013c79  mov     rax, [rsp+78h+arg_28]
0x180013c81  mov     [rbx+88h], rax
0x180013c88  mov     rax, [rsp+78h+arg_0]
0x180013c90  mov     [rbx+90h], rax
0x180013c97  xor     eax, eax
0x180013c99  mov     [rbx+44h], ebp
0x180013c9c  mov     [rbx+30h], r12
0x180013ca0  mov     [rbx+48h], rdi
0x180013ca4  movups  xmmword ptr [rbx+68h], xmm0
0x180013ca8  mov     [rbx+78h], rax
0x180013cac  movups  xmmword ptr [rbx+50h], xmm0
0x180013cb0  mov     [rbx+60h], rax
0x180013cb4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180013cbb  test    rax, rax
0x180013cbe  jz      short loc_180013CC7
0x180013cc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013cc5  jmp     short loc_180013CCA
0x180013cc7  mov     rax, rdi
0x180013cca  mov     [rbx+80h], rax
0x180013cd1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180013cd8  test    rax, rax
0x180013cdb  jz      short loc_180013CE5
0x180013cdd  mov     rcx, rbx
0x180013ce0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ce5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180013cec  test    rax, rax
0x180013cef  jz      short loc_180013D07
0x180013cf1  mov     rdx, [rsp+78h+arg_60]
0x180013cf9  mov     r8d, 400h
0x180013cff  mov     rcx, rbx
0x180013d02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d07  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180013d0e  test    rax, rax
0x180013d11  jz      short loc_180013D1B
0x180013d13  mov     rcx, rbx
0x180013d16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d1b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180013d22  test    rax, rax
0x180013d25  jz      short loc_180013D35
0x180013d27  test    byte ptr [rbx+4], 2
0x180013d2b  jnz     short loc_180013D35
0x180013d2d  mov     rcx, rbx
0x180013d30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d35  cmp     [rbx+8], edi
0x180013d38  jl      short loc_180013D56
0x180013d3a  cmp     r15d, 3
0x180013d3e  jz      short loc_180013D46
0x180013d40  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180013d46  mov     ecx, 8000FFFFh; this
0x180013d4b  mov     [rbx+8], ecx
0x180013d4e  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180013d53  mov     [rbx+0Ch], eax
0x180013d56  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180013d5d  jnz     short loc_180013D7E
0x180013d5f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180013d66  test    rax, rax
0x180013d69  jz      short loc_180013D74
0x180013d6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d70  test    al, al
0x180013d72  jmp     short loc_180013D7C
0x180013d74  call    cs:__imp_IsDebuggerPresent
0x180013d7a  test    eax, eax
0x180013d7c  jz      short loc_180013D84
0x180013d7e  test    byte ptr [rbx+4], 2
0x180013d82  jz      short loc_180013DA8
0x180013d84  mov     rax, cs:g_pfnResultLoggingCallback
0x180013d8b  test    rax, rax
0x180013d8e  jz      short loc_180013DEC
0x180013d90  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180013d97  jnz     short loc_180013DEC
0x180013d99  xor     r8d, r8d
0x180013d9c  xor     edx, edx
0x180013d9e  mov     rcx, rbx
0x180013da1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013da6  jmp     short loc_180013DEC
0x180013da8  mov     rax, cs:g_pfnResultLoggingCallback
0x180013daf  mov     ebp, 800h
0x180013db4  test    rax, rax
0x180013db7  jz      short loc_180013DD0
0x180013db9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180013dc0  jnz     short loc_180013DD0
0x180013dc2  mov     r8d, ebp
0x180013dc5  mov     rdx, rsi
0x180013dc8  mov     rcx, rbx
0x180013dcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013dd0  cmp     [rsi], di
0x180013dd3  jnz     short loc_180013DE3
0x180013dd5  mov     r8, rbx; unsigned __int64
0x180013dd8  mov     rdx, rbp; unsigned __int16 *
0x180013ddb  mov     rcx, rsi; this
0x180013dde  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180013de3  mov     rcx, rsi; lpOutputString
0x180013de6  call    cs:__imp_OutputDebugStringW
0x180013dec  test    byte ptr [rbx+4], 4
0x180013df0  jnz     short loc_180013DFB
0x180013df2  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180013df9  jz      short loc_180013E0C
0x180013dfb  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180013e02  test    rax, rax
0x180013e05  jz      short loc_180013E0C
0x180013e07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e0c  mov     rbx, [rsp+78h+arg_10]
0x180013e14  add     rsp, 40h
0x180013e18  pop     r15
0x180013e1a  pop     r14
0x180013e1c  pop     r13
0x180013e1e  pop     r12
0x180013e20  pop     rdi
0x180013e21  pop     rsi
0x180013e22  pop     rbp
0x180013e23  retn
```
