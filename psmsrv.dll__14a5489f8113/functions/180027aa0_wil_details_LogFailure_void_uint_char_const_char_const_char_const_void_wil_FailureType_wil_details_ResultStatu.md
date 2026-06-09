# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180027aa0`
- end: `0x180027d98`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180025d20`
- `0x18002606c`

## callees

- `0x18001a908`
- `0x180025c60`
- `0x180027194`
- `0x180027aa0`
- `0x1800286fc`
- `0x180028720`
- `0x180028870`
- `0x18002888c`
- `0x180029c84`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027bc3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027bc3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180027ce2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180027ce2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180027d54`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180027d54`

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
  _WORD *v21; // rax
  DWORD CurrentThreadId; // eax
  wil::details::in1diag3 *v23; // rcx
  const struct wil::FailureInfo *v24; // r9
  __int64 ModuleName; // rax
  bool v26; // zf
  wil::details *v27; // [rsp+30h] [rbp-48h]

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
          LODWORD(v27) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v27);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL);
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
  v21 = a9;
  if ( !a9 || !*a9 )
    v21 = 0;
  *(_QWORD *)(a16 + 24) = v21;
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
    ModuleName = wil::details::g_pfnGetModuleName(v23);
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
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v26 = !IsDebuggerPresent())
      : (v26 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v23) == 0),
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
      wil::details::g_pfnDebugBreak(v23);
  }
}

```

## disassembly

```asm
0x180027aa0  mov     [rsp+arg_10], rbx
0x180027aa5  mov     [rsp+arg_8], edx
0x180027aa9  mov     [rsp+arg_0], rcx
0x180027aae  push    rbp
0x180027aaf  push    rsi
0x180027ab0  push    rdi
0x180027ab1  push    r12
0x180027ab3  push    r13
0x180027ab5  push    r14
0x180027ab7  push    r15
0x180027ab9  sub     rsp, 40h
0x180027abd  mov     r14, [rsp+78h+arg_38]
0x180027ac5  xor     eax, eax
0x180027ac7  mov     rbx, [rsp+78h+arg_78]
0x180027acf  xor     ebp, ebp
0x180027ad1  mov     r15d, [rsp+78h+arg_30]
0x180027ad9  mov     r10, rcx
0x180027adc  mov     rsi, [rsp+78h+lpOutputString]
0x180027ae4  mov     r12, r9
0x180027ae7  mov     r13, r8
0x180027aea  mov     ecx, r15d
0x180027aed  mov     [rsi], ax
0x180027af0  mov     rax, [rsp+78h+arg_60]
0x180027af8  mov     byte ptr [rax], 0
0x180027afb  mov     edi, [r14]
0x180027afe  mov     [rbx+8], edi
0x180027b01  mov     eax, [r14+4]
0x180027b05  mov     [rbx+0Ch], eax
0x180027b08  test    r15d, r15d
0x180027b0b  jz      short loc_180027B73
0x180027b0d  sub     ecx, 1
0x180027b10  jz      short loc_180027B6A
0x180027b12  sub     ecx, 1
0x180027b15  jz      short loc_180027B25
0x180027b17  cmp     ecx, 1
0x180027b1a  jnz     short loc_180027B7C
0x180027b1c  mov     ecx, edi; this
0x180027b1e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180027b23  jmp     short loc_180027B7A
0x180027b25  test    edi, edi
0x180027b27  js      short loc_180027B61
0x180027b29  mov     rax, [rsp+78h+arg_28]
0x180027b31  mov     edi, 8007029Ch
0x180027b36  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180027b3a  mov     rcx, r10; int
0x180027b3d  mov     [rsp+78h+var_50], rax; __int64
0x180027b42  mov     rax, [rsp+78h+arg_20]
0x180027b4a  mov     [rsp+78h+var_58], rax; __int64
0x180027b4f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180027b54  mov     ecx, edi; this
0x180027b56  mov     [rbx+8], edi
0x180027b59  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180027b5e  mov     [rbx+0Ch], eax
0x180027b61  mov     ecx, edi; this
0x180027b63  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180027b68  jmp     short loc_180027B7A
0x180027b6a  mov     ecx, edi; this
0x180027b6c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180027b71  jmp     short loc_180027B7A
0x180027b73  mov     ecx, edi; this
0x180027b75  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180027b7a  mov     ebp, eax
0x180027b7c  mov     eax, [rsp+78h+arg_70]
0x180027b83  mov     [rbx+4], eax
0x180027b86  mov     [rbx], r15d
0x180027b89  cmp     dword ptr [r14+8], 1
0x180027b8e  jnz     short loc_180027B96
0x180027b90  or      eax, 8
0x180027b93  mov     [rbx+4], eax
0x180027b96  mov     eax, 1
0x180027b9b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180027ba3  inc     eax
0x180027ba5  xor     edi, edi
0x180027ba7  mov     [rbx+10h], eax
0x180027baa  mov     rax, [rsp+78h+arg_40]
0x180027bb2  test    rax, rax
0x180027bb5  jz      short loc_180027BBC
0x180027bb7  cmp     [rax], di
0x180027bba  jnz     short loc_180027BBF
0x180027bbc  mov     rax, rdi
0x180027bbf  mov     [rbx+18h], rax
0x180027bc3  call    cs:__imp_GetCurrentThreadId
0x180027bc9  mov     [rbx+38h], r13
0x180027bcd  xorps   xmm0, xmm0
0x180027bd0  mov     [rbx+20h], eax
0x180027bd3  mov     eax, [rsp+78h+arg_8]
0x180027bda  mov     [rbx+40h], eax
0x180027bdd  mov     rax, [rsp+78h+arg_20]
0x180027be5  mov     [rbx+28h], rax
0x180027be9  mov     rax, [rsp+78h+arg_28]
0x180027bf1  mov     [rbx+88h], rax
0x180027bf8  mov     rax, [rsp+78h+arg_0]
0x180027c00  mov     [rbx+90h], rax
0x180027c07  xor     eax, eax
0x180027c09  mov     [rbx+44h], ebp
0x180027c0c  mov     [rbx+30h], r12
0x180027c10  mov     [rbx+48h], rdi
0x180027c14  movups  xmmword ptr [rbx+68h], xmm0
0x180027c18  mov     [rbx+78h], rax
0x180027c1c  movups  xmmword ptr [rbx+50h], xmm0
0x180027c20  mov     [rbx+60h], rax
0x180027c24  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180027c2b  test    rax, rax
0x180027c2e  jz      short loc_180027C37
0x180027c30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027c35  jmp     short loc_180027C3A
0x180027c37  mov     rax, rdi
0x180027c3a  mov     [rbx+80h], rax
0x180027c41  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180027c48  test    rax, rax
0x180027c4b  jz      short loc_180027C55
0x180027c4d  mov     rcx, rbx
0x180027c50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027c55  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180027c5c  test    rax, rax
0x180027c5f  jz      short loc_180027C77
0x180027c61  mov     rdx, [rsp+78h+arg_60]
0x180027c69  mov     r8d, 400h
0x180027c6f  mov     rcx, rbx
0x180027c72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027c77  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180027c7e  test    rax, rax
0x180027c81  jz      short loc_180027C8B
0x180027c83  mov     rcx, rbx
0x180027c86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027c8b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180027c92  test    rax, rax
0x180027c95  jz      short loc_180027CA5
0x180027c97  test    byte ptr [rbx+4], 2
0x180027c9b  jnz     short loc_180027CA5
0x180027c9d  mov     rcx, rbx
0x180027ca0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ca5  cmp     [rbx+8], edi
0x180027ca8  jl      short loc_180027CC4
0x180027caa  cmp     r15d, 3
0x180027cae  jnz     loc_180027D92
0x180027cb4  mov     ecx, 8000FFFFh; this
0x180027cb9  mov     [rbx+8], ecx
0x180027cbc  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180027cc1  mov     [rbx+0Ch], eax
0x180027cc4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180027ccb  jnz     short loc_180027CEC
0x180027ccd  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180027cd4  test    rax, rax
0x180027cd7  jz      short loc_180027CE2
0x180027cd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027cde  test    al, al
0x180027ce0  jmp     short loc_180027CEA
0x180027ce2  call    cs:__imp_IsDebuggerPresent
0x180027ce8  test    eax, eax
0x180027cea  jz      short loc_180027CF2
0x180027cec  test    byte ptr [rbx+4], 2
0x180027cf0  jz      short loc_180027D16
0x180027cf2  mov     rax, cs:g_pfnResultLoggingCallback
0x180027cf9  test    rax, rax
0x180027cfc  jz      short loc_180027D5A
0x180027cfe  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180027d05  jnz     short loc_180027D5A
0x180027d07  xor     r8d, r8d
0x180027d0a  xor     edx, edx
0x180027d0c  mov     rcx, rbx
0x180027d0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027d14  jmp     short loc_180027D5A
0x180027d16  mov     rax, cs:g_pfnResultLoggingCallback
0x180027d1d  mov     ebp, 800h
0x180027d22  test    rax, rax
0x180027d25  jz      short loc_180027D3E
0x180027d27  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180027d2e  jnz     short loc_180027D3E
0x180027d30  mov     r8d, ebp
0x180027d33  mov     rdx, rsi
0x180027d36  mov     rcx, rbx
0x180027d39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027d3e  cmp     [rsi], di
0x180027d41  jnz     short loc_180027D51
0x180027d43  mov     r8, rbx; unsigned __int64
0x180027d46  mov     rdx, rbp; unsigned __int16 *
0x180027d49  mov     rcx, rsi; this
0x180027d4c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180027d51  mov     rcx, rsi; lpOutputString
0x180027d54  call    cs:__imp_OutputDebugStringW
0x180027d5a  test    byte ptr [rbx+4], 4
0x180027d5e  jnz     short loc_180027D69
0x180027d60  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180027d67  jz      short loc_180027D7A
0x180027d69  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180027d70  test    rax, rax
0x180027d73  jz      short loc_180027D7A
0x180027d75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027d7a  mov     rbx, [rsp+78h+arg_10]
0x180027d82  add     rsp, 40h
0x180027d86  pop     r15
0x180027d88  pop     r14
0x180027d8a  pop     r13
0x180027d8c  pop     r12
0x180027d8e  pop     rdi
0x180027d8f  pop     rsi
0x180027d90  pop     rbp
0x180027d91  retn
0x180027d92  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
