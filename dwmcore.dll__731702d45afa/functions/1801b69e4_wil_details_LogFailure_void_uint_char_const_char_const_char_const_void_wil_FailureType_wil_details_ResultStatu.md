# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1801b69e4`
- end: `0x1801b6d24`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `832`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x1801b5880`
- `0x1801b5984`
- `0x1801b68f4`

## callees

- `0x1801b6740`
- `0x1801b69e4`
- `0x1801b6d2c`
- `0x180202bb8`
- `0x18022aae8`
- `0x18022b4f8`
- `0x18022b520`
- `0x18022b534`
- `0x18022be5c`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801b6ab4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801b6ab4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1802b242c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1802b242c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1801b6ba9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1801b6ba9`

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
  _WORD *v20; // rax
  DWORD CurrentThreadId; // eax
  int v22; // edx
  wil::details::in1diag3 *v23; // rcx
  const struct wil::FailureInfo *v24; // r9
  __int64 ModuleName; // rax
  bool v26; // zf
  int v27; // eax
  int v28; // edx
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
        v27 = wil::details::RecordReturn((wil::details *)v19, a2);
        break;
      case 2:
        if ( (v19 & 0x80000000) == 0 )
        {
          v19 = -2147024228;
          LODWORD(v29) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v29);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v28);
        }
        v27 = wil::details::RecordLog((wil::details *)v19, a2);
        break;
      case 3:
        v27 = wil::details::RecordFailFast((wil::details *)v19, a2);
        break;
      default:
        goto LABEL_5;
    }
  }
  else
  {
    v27 = wil::details::RecordException((wil::details *)v19, a2);
  }
  v16 = v27;
LABEL_5:
  *(_DWORD *)(a16 + 4) = a15;
  *(_DWORD *)a16 = a7;
  if ( a8[2] == 1 )
    *(_DWORD *)(a16 + 4) = a15 | 8;
  *(_DWORD *)(a16 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v20 = a9;
  if ( !a9 || !*a9 )
    v20 = 0;
  *(_QWORD *)(a16 + 24) = v20;
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v23);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v22);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (wil::g_pfnIsDebuggerPresent
      ? (v26 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0)
      : (v26 = !IsDebuggerPresent()),
        v26)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v24);
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
0x1801b69e4  mov     [rsp+arg_10], rbx
0x1801b69e9  mov     [rsp+arg_8], edx
0x1801b69ed  mov     [rsp+arg_0], rcx
0x1801b69f2  push    rbp
0x1801b69f3  push    rsi
0x1801b69f4  push    rdi
0x1801b69f5  push    r12
0x1801b69f7  push    r13
0x1801b69f9  push    r14
0x1801b69fb  push    r15
0x1801b69fd  sub     rsp, 40h
0x1801b6a01  mov     r14, [rsp+78h+arg_38]
0x1801b6a09  xor     eax, eax
0x1801b6a0b  mov     rbx, [rsp+78h+arg_78]
0x1801b6a13  xor     ebp, ebp
0x1801b6a15  mov     r15d, [rsp+78h+arg_30]
0x1801b6a1d  mov     r10, rcx
0x1801b6a20  mov     rsi, [rsp+78h+lpOutputString]
0x1801b6a28  mov     r12, r9
0x1801b6a2b  mov     r13, r8
0x1801b6a2e  mov     ecx, r15d
0x1801b6a31  mov     [rsi], ax
0x1801b6a34  mov     rax, [rsp+78h+arg_60]
0x1801b6a3c  mov     byte ptr [rax], 0
0x1801b6a3f  mov     edi, [r14]
0x1801b6a42  mov     [rbx+8], edi
0x1801b6a45  mov     eax, [r14+4]
0x1801b6a49  mov     [rbx+0Ch], eax
0x1801b6a4c  test    r15d, r15d
0x1801b6a4f  jz      loc_1801B6C9F
0x1801b6a55  sub     ecx, 1
0x1801b6a58  jz      loc_1801B6BFB
0x1801b6a5e  sub     ecx, 1
0x1801b6a61  jz      loc_1801B6C56
0x1801b6a67  cmp     ecx, 1
0x1801b6a6a  jz      loc_1801B6C4D
0x1801b6a70  mov     eax, [rsp+78h+arg_70]
0x1801b6a77  mov     [rbx+4], eax
0x1801b6a7a  mov     [rbx], r15d
0x1801b6a7d  cmp     dword ptr [r14+8], 1
0x1801b6a82  jz      loc_1801B6CAB
0x1801b6a88  mov     eax, 1
0x1801b6a8d  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1801b6a95  inc     eax
0x1801b6a97  xor     edi, edi
0x1801b6a99  mov     [rbx+10h], eax
0x1801b6a9c  mov     rax, [rsp+78h+arg_40]
0x1801b6aa4  test    rax, rax
0x1801b6aa7  jnz     loc_1801B6CB6
0x1801b6aad  mov     rax, rdi
0x1801b6ab0  mov     [rbx+18h], rax
0x1801b6ab4  call    cs:__imp_GetCurrentThreadId
0x1801b6aba  mov     [rbx+38h], r13
0x1801b6abe  xorps   xmm0, xmm0
0x1801b6ac1  mov     [rbx+20h], eax
0x1801b6ac4  mov     eax, [rsp+78h+arg_8]
0x1801b6acb  mov     [rbx+40h], eax
0x1801b6ace  mov     rax, [rsp+78h+arg_20]
0x1801b6ad6  mov     [rbx+28h], rax
0x1801b6ada  mov     rax, [rsp+78h+arg_28]
0x1801b6ae2  mov     [rbx+88h], rax
0x1801b6ae9  mov     rax, [rsp+78h+arg_0]
0x1801b6af1  mov     [rbx+90h], rax
0x1801b6af8  xor     eax, eax
0x1801b6afa  mov     [rbx+44h], ebp
0x1801b6afd  mov     [rbx+30h], r12
0x1801b6b01  mov     [rbx+48h], rdi
0x1801b6b05  movups  xmmword ptr [rbx+68h], xmm0
0x1801b6b09  mov     [rbx+78h], rax
0x1801b6b0d  movups  xmmword ptr [rbx+50h], xmm0
0x1801b6b11  mov     [rbx+60h], rax
0x1801b6b15  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1801b6b1c  test    rax, rax
0x1801b6b1f  jz      loc_1801B6C45
0x1801b6b25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b6b2a  mov     [rbx+80h], rax
0x1801b6b31  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1801b6b38  test    rax, rax
0x1801b6b3b  jz      short loc_1801B6B45
0x1801b6b3d  mov     rcx, rbx
0x1801b6b40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b6b45  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1801b6b4c  test    rax, rax
0x1801b6b4f  jz      short loc_1801B6B67
0x1801b6b51  mov     rdx, [rsp+78h+arg_60]
0x1801b6b59  mov     r8d, 400h
0x1801b6b5f  mov     rcx, rbx
0x1801b6b62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b6b67  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1801b6b6e  test    rax, rax
0x1801b6b71  jz      short loc_1801B6B7B
0x1801b6b73  mov     rcx, rbx
0x1801b6b76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b6b7b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1801b6b82  test    rax, rax
0x1801b6b85  jnz     loc_1801B6CC4
0x1801b6b8b  cmp     [rbx+8], edi
0x1801b6b8e  jge     loc_1801B6CDB
0x1801b6b94  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1801b6b9b  jnz     short loc_1801B6C09
0x1801b6b9d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1801b6ba4  test    rax, rax
0x1801b6ba7  jnz     short loc_1801B6BF2
0x1801b6ba9  call    cs:__imp_IsDebuggerPresent
0x1801b6baf  test    eax, eax
0x1801b6bb1  jnz     short loc_1801B6C09
0x1801b6bb3  mov     rax, cs:g_pfnResultLoggingCallback
0x1801b6bba  test    rax, rax
0x1801b6bbd  jnz     loc_1801B6CEB
0x1801b6bc3  test    byte ptr [rbx+4], 4
0x1801b6bc7  jnz     loc_1801B6D0A
0x1801b6bcd  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1801b6bd4  jnz     loc_1801B6D0A
0x1801b6bda  mov     rbx, [rsp+78h+arg_10]
0x1801b6be2  add     rsp, 40h
0x1801b6be6  pop     r15
0x1801b6be8  pop     r14
0x1801b6bea  pop     r13
0x1801b6bec  pop     r12
0x1801b6bee  pop     rdi
0x1801b6bef  pop     rsi
0x1801b6bf0  pop     rbp
0x1801b6bf1  retn
0x1801b6bf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b6bf7  test    al, al
0x1801b6bf9  jmp     short loc_1801B6BB1
0x1801b6bfb  mov     ecx, edi; this
0x1801b6bfd  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1801b6c02  mov     ebp, eax
0x1801b6c04  jmp     loc_1801B6A70
0x1801b6c09  test    byte ptr [rbx+4], 2
0x1801b6c0d  jnz     short loc_1801B6BB3
0x1801b6c0f  mov     rax, cs:g_pfnResultLoggingCallback
0x1801b6c16  mov     ebp, 800h
0x1801b6c1b  test    rax, rax
0x1801b6c1e  jz      loc_1802B2416
0x1801b6c24  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1801b6c2b  jnz     loc_1802B2416
0x1801b6c31  mov     r8d, ebp
0x1801b6c34  mov     rdx, rsi
0x1801b6c37  mov     rcx, rbx
0x1801b6c3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b6c3f  nop
0x1801b6c40  jmp     loc_1802B2416
0x1801b6c45  mov     rax, rdi
0x1801b6c48  jmp     loc_1801B6B2A
0x1801b6c4d  mov     ecx, edi; this
0x1801b6c4f  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1801b6c54  jmp     short loc_1801B6C02
0x1801b6c56  test    edi, edi
0x1801b6c58  js      loc_1802B23F4
0x1801b6c5e  mov     rax, [rsp+78h+arg_28]
0x1801b6c66  mov     edi, 8007029Ch
0x1801b6c6b  mov     [rsp+78h+var_40], ebp
0x1801b6c6f  mov     rcx, r10; int
0x1801b6c72  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1801b6c76  mov     [rsp+78h+var_50], rax; __int64
0x1801b6c7b  mov     rax, [rsp+78h+arg_20]
0x1801b6c83  mov     [rsp+78h+var_58], rax; __int64
0x1801b6c88  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1801b6c8d  mov     ecx, edi; this
0x1801b6c8f  mov     [rbx+8], edi
0x1801b6c92  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1801b6c97  mov     [rbx+0Ch], eax
0x1801b6c9a  jmp     loc_1802B23F4
0x1801b6c9f  mov     ecx, edi; this
0x1801b6ca1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1801b6ca6  jmp     loc_1801B6C02
0x1801b6cab  or      eax, 8
0x1801b6cae  mov     [rbx+4], eax
0x1801b6cb1  jmp     loc_1801B6A88
0x1801b6cb6  cmp     [rax], di
0x1801b6cb9  jnz     loc_1801B6AB0
0x1801b6cbf  jmp     loc_1801B6AAD
0x1801b6cc4  test    byte ptr [rbx+4], 2
0x1801b6cc8  jnz     loc_1801B6B8B
0x1801b6cce  mov     rcx, rbx
0x1801b6cd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b6cd6  jmp     loc_1801B6B8B
0x1801b6cdb  cmp     r15d, 3
0x1801b6cdf  jz      loc_1802B2401
0x1801b6ce5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1801b6ceb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1801b6cf2  jnz     loc_1801B6BC3
0x1801b6cf8  xor     r8d, r8d
0x1801b6cfb  xor     edx, edx
0x1801b6cfd  mov     rcx, rbx
0x1801b6d00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b6d05  jmp     loc_1801B6BC3
0x1801b6d0a  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1801b6d11  test    rax, rax
0x1801b6d14  jz      loc_1801B6BDA
0x1801b6d1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b6d1f  jmp     loc_1801B6BDA
0x1802b23f4  mov     ecx, edi; this
0x1802b23f6  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1802b23fb  nop
0x1802b23fc  jmp     loc_1801B6C02
0x1802b2401  mov     ecx, 8000FFFFh; this
0x1802b2406  mov     [rbx+8], ecx
0x1802b2409  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1802b240e  mov     [rbx+0Ch], eax
0x1802b2411  jmp     loc_1801B6B94
0x1802b2416  cmp     [rsi], di
0x1802b2419  jnz     short loc_1802B2429
0x1802b241b  mov     r8, rbx; unsigned __int64
0x1802b241e  mov     rdx, rbp; unsigned __int16 *
0x1802b2421  mov     rcx, rsi; this
0x1802b2424  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1802b2429  mov     rcx, rsi; lpOutputString
0x1802b242c  call    cs:__imp_OutputDebugStringW
0x1802b2432  nop
0x1802b2433  jmp     loc_1801B6BC3
```
