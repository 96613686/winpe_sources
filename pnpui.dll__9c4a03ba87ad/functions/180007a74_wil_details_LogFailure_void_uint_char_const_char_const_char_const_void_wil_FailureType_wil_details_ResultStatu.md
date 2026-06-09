# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180007a74`
- end: `0x180007d6c`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180004398`

## callees

- `0x180003dd4`
- `0x180006444`
- `0x180006eb8`
- `0x180007a74`
- `0x1800086c0`
- `0x1800086e0`
- `0x180008808`
- `0x180008824`
- `0x18000a56c`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007d28`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007d28`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007cb6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007cb6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007b97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007b97`

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
0x180007a74  mov     [rsp+arg_10], rbx
0x180007a79  mov     [rsp+arg_8], edx
0x180007a7d  mov     [rsp+arg_0], rcx
0x180007a82  push    rbp
0x180007a83  push    rsi
0x180007a84  push    rdi
0x180007a85  push    r12
0x180007a87  push    r13
0x180007a89  push    r14
0x180007a8b  push    r15
0x180007a8d  sub     rsp, 40h
0x180007a91  mov     r14, [rsp+78h+arg_38]
0x180007a99  xor     eax, eax
0x180007a9b  mov     rbx, [rsp+78h+arg_78]
0x180007aa3  xor     ebp, ebp
0x180007aa5  mov     r15d, [rsp+78h+arg_30]
0x180007aad  mov     r10, rcx
0x180007ab0  mov     rsi, [rsp+78h+lpOutputString]
0x180007ab8  mov     r12, r9
0x180007abb  mov     r13, r8
0x180007abe  mov     ecx, r15d
0x180007ac1  mov     [rsi], ax
0x180007ac4  mov     rax, [rsp+78h+arg_60]
0x180007acc  mov     byte ptr [rax], 0
0x180007acf  mov     edi, [r14]
0x180007ad2  mov     [rbx+8], edi
0x180007ad5  mov     eax, [r14+4]
0x180007ad9  mov     [rbx+0Ch], eax
0x180007adc  test    r15d, r15d
0x180007adf  jz      short loc_180007B47
0x180007ae1  sub     ecx, 1
0x180007ae4  jz      short loc_180007B3E
0x180007ae6  sub     ecx, 1
0x180007ae9  jz      short loc_180007AF9
0x180007aeb  cmp     ecx, 1
0x180007aee  jnz     short loc_180007B50
0x180007af0  mov     ecx, edi; this
0x180007af2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180007af7  jmp     short loc_180007B4E
0x180007af9  test    edi, edi
0x180007afb  js      short loc_180007B35
0x180007afd  mov     rax, [rsp+78h+arg_28]
0x180007b05  mov     edi, 8007029Ch
0x180007b0a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180007b0e  mov     rcx, r10; int
0x180007b11  mov     [rsp+78h+var_50], rax; __int64
0x180007b16  mov     rax, [rsp+78h+arg_20]
0x180007b1e  mov     [rsp+78h+var_58], rax; __int64
0x180007b23  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180007b28  mov     ecx, edi; this
0x180007b2a  mov     [rbx+8], edi
0x180007b2d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007b32  mov     [rbx+0Ch], eax
0x180007b35  mov     ecx, edi; this
0x180007b37  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180007b3c  jmp     short loc_180007B4E
0x180007b3e  mov     ecx, edi; this
0x180007b40  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180007b45  jmp     short loc_180007B4E
0x180007b47  mov     ecx, edi; this
0x180007b49  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180007b4e  mov     ebp, eax
0x180007b50  mov     eax, [rsp+78h+arg_70]
0x180007b57  mov     [rbx+4], eax
0x180007b5a  mov     [rbx], r15d
0x180007b5d  cmp     dword ptr [r14+8], 1
0x180007b62  jnz     short loc_180007B6A
0x180007b64  or      eax, 8
0x180007b67  mov     [rbx+4], eax
0x180007b6a  mov     eax, 1
0x180007b6f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180007b77  inc     eax
0x180007b79  xor     edi, edi
0x180007b7b  mov     [rbx+10h], eax
0x180007b7e  mov     rax, [rsp+78h+arg_40]
0x180007b86  test    rax, rax
0x180007b89  jz      short loc_180007B90
0x180007b8b  cmp     [rax], di
0x180007b8e  jnz     short loc_180007B93
0x180007b90  mov     rax, rdi
0x180007b93  mov     [rbx+18h], rax
0x180007b97  call    cs:__imp_GetCurrentThreadId
0x180007b9d  mov     [rbx+38h], r13
0x180007ba1  xorps   xmm0, xmm0
0x180007ba4  mov     [rbx+20h], eax
0x180007ba7  mov     eax, [rsp+78h+arg_8]
0x180007bae  mov     [rbx+40h], eax
0x180007bb1  mov     rax, [rsp+78h+arg_20]
0x180007bb9  mov     [rbx+28h], rax
0x180007bbd  mov     rax, [rsp+78h+arg_28]
0x180007bc5  mov     [rbx+88h], rax
0x180007bcc  mov     rax, [rsp+78h+arg_0]
0x180007bd4  mov     [rbx+90h], rax
0x180007bdb  xor     eax, eax
0x180007bdd  mov     [rbx+44h], ebp
0x180007be0  mov     [rbx+30h], r12
0x180007be4  mov     [rbx+48h], rdi
0x180007be8  movups  xmmword ptr [rbx+68h], xmm0
0x180007bec  mov     [rbx+78h], rax
0x180007bf0  movups  xmmword ptr [rbx+50h], xmm0
0x180007bf4  mov     [rbx+60h], rax
0x180007bf8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180007bff  test    rax, rax
0x180007c02  jz      short loc_180007C0B
0x180007c04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c09  jmp     short loc_180007C0E
0x180007c0b  mov     rax, rdi
0x180007c0e  mov     [rbx+80h], rax
0x180007c15  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180007c1c  test    rax, rax
0x180007c1f  jz      short loc_180007C29
0x180007c21  mov     rcx, rbx
0x180007c24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c29  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180007c30  test    rax, rax
0x180007c33  jz      short loc_180007C4B
0x180007c35  mov     rdx, [rsp+78h+arg_60]
0x180007c3d  mov     r8d, 400h
0x180007c43  mov     rcx, rbx
0x180007c46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c4b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007c52  test    rax, rax
0x180007c55  jz      short loc_180007C5F
0x180007c57  mov     rcx, rbx
0x180007c5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c5f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007c66  test    rax, rax
0x180007c69  jz      short loc_180007C79
0x180007c6b  test    byte ptr [rbx+4], 2
0x180007c6f  jnz     short loc_180007C79
0x180007c71  mov     rcx, rbx
0x180007c74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c79  cmp     [rbx+8], edi
0x180007c7c  jl      short loc_180007C98
0x180007c7e  cmp     r15d, 3
0x180007c82  jnz     loc_180007D66
0x180007c88  mov     ecx, 8000FFFFh; this
0x180007c8d  mov     [rbx+8], ecx
0x180007c90  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007c95  mov     [rbx+0Ch], eax
0x180007c98  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180007c9f  jnz     short loc_180007CC0
0x180007ca1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180007ca8  test    rax, rax
0x180007cab  jz      short loc_180007CB6
0x180007cad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cb2  test    al, al
0x180007cb4  jmp     short loc_180007CBE
0x180007cb6  call    cs:__imp_IsDebuggerPresent
0x180007cbc  test    eax, eax
0x180007cbe  jz      short loc_180007CC6
0x180007cc0  test    byte ptr [rbx+4], 2
0x180007cc4  jz      short loc_180007CEA
0x180007cc6  mov     rax, cs:g_pfnResultLoggingCallback
0x180007ccd  test    rax, rax
0x180007cd0  jz      short loc_180007D2E
0x180007cd2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180007cd9  jnz     short loc_180007D2E
0x180007cdb  xor     r8d, r8d
0x180007cde  xor     edx, edx
0x180007ce0  mov     rcx, rbx
0x180007ce3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ce8  jmp     short loc_180007D2E
0x180007cea  mov     rax, cs:g_pfnResultLoggingCallback
0x180007cf1  mov     ebp, 800h
0x180007cf6  test    rax, rax
0x180007cf9  jz      short loc_180007D12
0x180007cfb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180007d02  jnz     short loc_180007D12
0x180007d04  mov     r8d, ebp
0x180007d07  mov     rdx, rsi
0x180007d0a  mov     rcx, rbx
0x180007d0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d12  cmp     [rsi], di
0x180007d15  jnz     short loc_180007D25
0x180007d17  mov     r8, rbx; unsigned __int64
0x180007d1a  mov     rdx, rbp; unsigned __int16 *
0x180007d1d  mov     rcx, rsi; this
0x180007d20  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180007d25  mov     rcx, rsi; lpOutputString
0x180007d28  call    cs:__imp_OutputDebugStringW
0x180007d2e  test    byte ptr [rbx+4], 4
0x180007d32  jnz     short loc_180007D3D
0x180007d34  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180007d3b  jz      short loc_180007D4E
0x180007d3d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180007d44  test    rax, rax
0x180007d47  jz      short loc_180007D4E
0x180007d49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d4e  mov     rbx, [rsp+78h+arg_10]
0x180007d56  add     rsp, 40h
0x180007d5a  pop     r15
0x180007d5c  pop     r14
0x180007d5e  pop     r13
0x180007d60  pop     r12
0x180007d62  pop     rdi
0x180007d63  pop     rsi
0x180007d64  pop     rbp
0x180007d65  retn
0x180007d66  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
