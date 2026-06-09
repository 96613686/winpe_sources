# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180007ae8`
- end: `0x180007de1`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800053e0`

## callees

- `0x180004e1c`
- `0x180006b34`
- `0x1800077e8`
- `0x180007ae8`
- `0x180008ee0`
- `0x180008f00`
- `0x180009088`
- `0x1800090a4`
- `0x18000abec`
- `0x180031010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x180007d2a`
- `KERNEL32!IsDebuggerPresent` at `0x180007d2a`
- `KERNEL32!OutputDebugStringW` at `0x180007d9c`
- `KERNEL32!OutputDebugStringW` at `0x180007d9c`
- `KERNEL32!GetCurrentThreadId` at `0x180007c0b`
- `KERNEL32!GetCurrentThreadId` at `0x180007c0b`

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
        WCHAR *lpOutputString,
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

  *lpOutputString = 0;
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
    if ( !*lpOutputString )
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v25);
    OutputDebugStringW(lpOutputString);
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
0x180007ae8  mov     [rsp+arg_10], rbx
0x180007aed  mov     [rsp+arg_8], edx
0x180007af1  mov     [rsp+arg_0], rcx
0x180007af6  push    rbp
0x180007af7  push    rsi
0x180007af8  push    rdi
0x180007af9  push    r12
0x180007afb  push    r13
0x180007afd  push    r14
0x180007aff  push    r15
0x180007b01  sub     rsp, 40h
0x180007b05  mov     r12, r9
0x180007b08  mov     r13, r8
0x180007b0b  mov     r10, rcx
0x180007b0e  xor     eax, eax
0x180007b10  mov     rsi, [rsp+78h+lpOutputString]
0x180007b18  mov     [rsi], ax
0x180007b1b  mov     rax, [rsp+78h+arg_60]
0x180007b23  mov     byte ptr [rax], 0
0x180007b26  mov     r14, [rsp+78h+arg_38]
0x180007b2e  mov     edi, [r14]
0x180007b31  mov     rbx, [rsp+78h+arg_78]
0x180007b39  mov     [rbx+8], edi
0x180007b3c  mov     eax, [r14+4]
0x180007b40  mov     [rbx+0Ch], eax
0x180007b43  xor     ebp, ebp
0x180007b45  mov     r15d, [rsp+78h+arg_30]
0x180007b4d  mov     ecx, r15d
0x180007b50  test    r15d, r15d
0x180007b53  jz      short loc_180007BBB
0x180007b55  sub     ecx, 1
0x180007b58  jz      short loc_180007BB2
0x180007b5a  sub     ecx, 1
0x180007b5d  jz      short loc_180007B6D
0x180007b5f  cmp     ecx, 1
0x180007b62  jnz     short loc_180007BC4
0x180007b64  mov     ecx, edi; this
0x180007b66  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180007b6b  jmp     short loc_180007BC2
0x180007b6d  test    edi, edi
0x180007b6f  js      short loc_180007BA9
0x180007b71  mov     edi, 8007029Ch
0x180007b76  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180007b7a  mov     rax, [rsp+78h+arg_28]
0x180007b82  mov     [rsp+78h+var_50], rax; __int64
0x180007b87  mov     rax, [rsp+78h+arg_20]
0x180007b8f  mov     [rsp+78h+var_58], rax; __int64
0x180007b94  mov     rcx, r10; int
0x180007b97  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180007b9c  mov     [rbx+8], edi
0x180007b9f  mov     ecx, edi; this
0x180007ba1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007ba6  mov     [rbx+0Ch], eax
0x180007ba9  mov     ecx, edi; this
0x180007bab  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180007bb0  jmp     short loc_180007BC2
0x180007bb2  mov     ecx, edi; this
0x180007bb4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180007bb9  jmp     short loc_180007BC2
0x180007bbb  mov     ecx, edi; this
0x180007bbd  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180007bc2  mov     ebp, eax
0x180007bc4  mov     [rbx], r15d
0x180007bc7  mov     eax, [rsp+78h+arg_70]
0x180007bce  mov     [rbx+4], eax
0x180007bd1  cmp     dword ptr [r14+8], 1
0x180007bd6  jnz     short loc_180007BDE
0x180007bd8  or      eax, 8
0x180007bdb  mov     [rbx+4], eax
0x180007bde  mov     eax, 1
0x180007be3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180007beb  inc     eax
0x180007bed  mov     [rbx+10h], eax
0x180007bf0  mov     rax, [rsp+78h+arg_40]
0x180007bf8  xor     edi, edi
0x180007bfa  test    rax, rax
0x180007bfd  jz      short loc_180007C04
0x180007bff  cmp     [rax], di
0x180007c02  jnz     short loc_180007C07
0x180007c04  mov     rax, rdi
0x180007c07  mov     [rbx+18h], rax
0x180007c0b  call    cs:__imp_GetCurrentThreadId
0x180007c11  mov     [rbx+20h], eax
0x180007c14  mov     [rbx+38h], r13
0x180007c18  mov     eax, [rsp+78h+arg_8]
0x180007c1f  mov     [rbx+40h], eax
0x180007c22  mov     [rbx+44h], ebp
0x180007c25  mov     rax, [rsp+78h+arg_20]
0x180007c2d  mov     [rbx+28h], rax
0x180007c31  mov     [rbx+30h], r12
0x180007c35  mov     rax, [rsp+78h+arg_28]
0x180007c3d  mov     [rbx+88h], rax
0x180007c44  mov     rax, [rsp+78h+arg_0]
0x180007c4c  mov     [rbx+90h], rax
0x180007c53  mov     [rbx+48h], rdi
0x180007c57  xorps   xmm0, xmm0
0x180007c5a  xor     eax, eax
0x180007c5c  movups  xmmword ptr [rbx+68h], xmm0
0x180007c60  mov     [rbx+78h], rax
0x180007c64  movups  xmmword ptr [rbx+50h], xmm0
0x180007c68  mov     [rbx+60h], rax
0x180007c6c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180007c73  test    rax, rax
0x180007c76  jz      short loc_180007C7F
0x180007c78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c7d  jmp     short loc_180007C82
0x180007c7f  mov     rax, rdi
0x180007c82  mov     [rbx+80h], rax
0x180007c89  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180007c90  test    rax, rax
0x180007c93  jz      short loc_180007C9D
0x180007c95  mov     rcx, rbx
0x180007c98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c9d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180007ca4  test    rax, rax
0x180007ca7  jz      short loc_180007CBF
0x180007ca9  mov     r8d, 400h
0x180007caf  mov     rdx, [rsp+78h+arg_60]
0x180007cb7  mov     rcx, rbx
0x180007cba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cbf  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007cc6  test    rax, rax
0x180007cc9  jz      short loc_180007CD3
0x180007ccb  mov     rcx, rbx
0x180007cce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cd3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007cda  test    rax, rax
0x180007cdd  jz      short loc_180007CED
0x180007cdf  test    byte ptr [rbx+4], 2
0x180007ce3  jnz     short loc_180007CED
0x180007ce5  mov     rcx, rbx
0x180007ce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ced  cmp     [rbx+8], edi
0x180007cf0  jl      short loc_180007D0C
0x180007cf2  cmp     r15d, 3
0x180007cf6  jnz     loc_180007DDB
0x180007cfc  mov     ecx, 8000FFFFh; this
0x180007d01  mov     [rbx+8], ecx
0x180007d04  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007d09  mov     [rbx+0Ch], eax
0x180007d0c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180007d13  jnz     short loc_180007D34
0x180007d15  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180007d1c  test    rax, rax
0x180007d1f  jz      short loc_180007D2A
0x180007d21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d26  test    al, al
0x180007d28  jmp     short loc_180007D32
0x180007d2a  call    cs:__imp_IsDebuggerPresent
0x180007d30  test    eax, eax
0x180007d32  jz      short loc_180007D3A
0x180007d34  test    byte ptr [rbx+4], 2
0x180007d38  jz      short loc_180007D5E
0x180007d3a  mov     rax, cs:g_pfnResultLoggingCallback
0x180007d41  test    rax, rax
0x180007d44  jz      short loc_180007DA2
0x180007d46  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180007d4d  jnz     short loc_180007DA2
0x180007d4f  xor     r8d, r8d
0x180007d52  xor     edx, edx
0x180007d54  mov     rcx, rbx
0x180007d57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d5c  jmp     short loc_180007DA2
0x180007d5e  mov     ebp, 800h
0x180007d63  mov     rax, cs:g_pfnResultLoggingCallback
0x180007d6a  test    rax, rax
0x180007d6d  jz      short loc_180007D86
0x180007d6f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180007d76  jnz     short loc_180007D86
0x180007d78  mov     r8d, ebp
0x180007d7b  mov     rdx, rsi
0x180007d7e  mov     rcx, rbx
0x180007d81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d86  cmp     [rsi], di
0x180007d89  jnz     short loc_180007D99
0x180007d8b  mov     r8, rbx; unsigned __int64
0x180007d8e  mov     rdx, rbp; wchar_t *
0x180007d91  mov     rcx, rsi; this
0x180007d94  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180007d99  mov     rcx, rsi; lpOutputString
0x180007d9c  call    cs:__imp_OutputDebugStringW
0x180007da2  test    byte ptr [rbx+4], 4
0x180007da6  jnz     short loc_180007DB1
0x180007da8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180007daf  jz      short loc_180007DC3
0x180007db1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180007db8  test    rax, rax
0x180007dbb  jz      short loc_180007DC3
0x180007dbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007dc2  nop
0x180007dc3  mov     rbx, [rsp+78h+arg_10]
0x180007dcb  add     rsp, 40h
0x180007dcf  pop     r15
0x180007dd1  pop     r14
0x180007dd3  pop     r13
0x180007dd5  pop     r12
0x180007dd7  pop     rdi
0x180007dd8  pop     rsi
0x180007dd9  pop     rbp
0x180007dda  retn
0x180007ddb  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
