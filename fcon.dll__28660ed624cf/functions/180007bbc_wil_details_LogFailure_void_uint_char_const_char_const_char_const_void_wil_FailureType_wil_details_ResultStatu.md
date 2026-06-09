# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180007bbc`
- end: `0x180007eb5`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180005340`
- `0x1800056ac`
- `0x180010620`

## callees

- `0x180005274`
- `0x180006ef4`
- `0x1800077a8`
- `0x180007bbc`
- `0x180008b04`
- `0x180008b20`
- `0x180008c84`
- `0x180008ca0`
- `0x18000aa30`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007cdf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007cdf`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007dfe`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007dfe`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007e70`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007e70`

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
0x180007bbc  mov     [rsp+arg_10], rbx
0x180007bc1  mov     [rsp+arg_8], edx
0x180007bc5  mov     [rsp+arg_0], rcx
0x180007bca  push    rbp
0x180007bcb  push    rsi
0x180007bcc  push    rdi
0x180007bcd  push    r12
0x180007bcf  push    r13
0x180007bd1  push    r14
0x180007bd3  push    r15
0x180007bd5  sub     rsp, 40h
0x180007bd9  mov     r12, r9
0x180007bdc  mov     r13, r8
0x180007bdf  mov     r10, rcx
0x180007be2  xor     eax, eax
0x180007be4  mov     rsi, [rsp+78h+lpOutputString]
0x180007bec  mov     [rsi], ax
0x180007bef  mov     rax, [rsp+78h+arg_60]
0x180007bf7  mov     byte ptr [rax], 0
0x180007bfa  mov     r14, [rsp+78h+arg_38]
0x180007c02  mov     edi, [r14]
0x180007c05  mov     rbx, [rsp+78h+arg_78]
0x180007c0d  mov     [rbx+8], edi
0x180007c10  mov     eax, [r14+4]
0x180007c14  mov     [rbx+0Ch], eax
0x180007c17  xor     ebp, ebp
0x180007c19  mov     r15d, [rsp+78h+arg_30]
0x180007c21  mov     ecx, r15d
0x180007c24  test    r15d, r15d
0x180007c27  jz      short loc_180007C8F
0x180007c29  sub     ecx, 1
0x180007c2c  jz      short loc_180007C86
0x180007c2e  sub     ecx, 1
0x180007c31  jz      short loc_180007C41
0x180007c33  cmp     ecx, 1
0x180007c36  jnz     short loc_180007C98
0x180007c38  mov     ecx, edi; this
0x180007c3a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180007c3f  jmp     short loc_180007C96
0x180007c41  test    edi, edi
0x180007c43  js      short loc_180007C7D
0x180007c45  mov     edi, 8007029Ch
0x180007c4a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180007c4e  mov     rax, [rsp+78h+arg_28]
0x180007c56  mov     [rsp+78h+var_50], rax; __int64
0x180007c5b  mov     rax, [rsp+78h+arg_20]
0x180007c63  mov     [rsp+78h+var_58], rax; __int64
0x180007c68  mov     rcx, r10; int
0x180007c6b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180007c70  mov     [rbx+8], edi
0x180007c73  mov     ecx, edi; this
0x180007c75  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007c7a  mov     [rbx+0Ch], eax
0x180007c7d  mov     ecx, edi; this
0x180007c7f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180007c84  jmp     short loc_180007C96
0x180007c86  mov     ecx, edi; this
0x180007c88  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180007c8d  jmp     short loc_180007C96
0x180007c8f  mov     ecx, edi; this
0x180007c91  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180007c96  mov     ebp, eax
0x180007c98  mov     [rbx], r15d
0x180007c9b  mov     eax, [rsp+78h+arg_70]
0x180007ca2  mov     [rbx+4], eax
0x180007ca5  cmp     dword ptr [r14+8], 1
0x180007caa  jnz     short loc_180007CB2
0x180007cac  or      eax, 8
0x180007caf  mov     [rbx+4], eax
0x180007cb2  mov     eax, 1
0x180007cb7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180007cbf  inc     eax
0x180007cc1  mov     [rbx+10h], eax
0x180007cc4  mov     rax, [rsp+78h+arg_40]
0x180007ccc  xor     edi, edi
0x180007cce  test    rax, rax
0x180007cd1  jz      short loc_180007CD8
0x180007cd3  cmp     [rax], di
0x180007cd6  jnz     short loc_180007CDB
0x180007cd8  mov     rax, rdi
0x180007cdb  mov     [rbx+18h], rax
0x180007cdf  call    cs:__imp_GetCurrentThreadId
0x180007ce5  mov     [rbx+20h], eax
0x180007ce8  mov     [rbx+38h], r13
0x180007cec  mov     eax, [rsp+78h+arg_8]
0x180007cf3  mov     [rbx+40h], eax
0x180007cf6  mov     [rbx+44h], ebp
0x180007cf9  mov     rax, [rsp+78h+arg_20]
0x180007d01  mov     [rbx+28h], rax
0x180007d05  mov     [rbx+30h], r12
0x180007d09  mov     rax, [rsp+78h+arg_28]
0x180007d11  mov     [rbx+88h], rax
0x180007d18  mov     rax, [rsp+78h+arg_0]
0x180007d20  mov     [rbx+90h], rax
0x180007d27  mov     [rbx+48h], rdi
0x180007d2b  xorps   xmm0, xmm0
0x180007d2e  xor     eax, eax
0x180007d30  movups  xmmword ptr [rbx+68h], xmm0
0x180007d34  mov     [rbx+78h], rax
0x180007d38  movups  xmmword ptr [rbx+50h], xmm0
0x180007d3c  mov     [rbx+60h], rax
0x180007d40  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180007d47  test    rax, rax
0x180007d4a  jz      short loc_180007D53
0x180007d4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d51  jmp     short loc_180007D56
0x180007d53  mov     rax, rdi
0x180007d56  mov     [rbx+80h], rax
0x180007d5d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180007d64  test    rax, rax
0x180007d67  jz      short loc_180007D71
0x180007d69  mov     rcx, rbx
0x180007d6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d71  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180007d78  test    rax, rax
0x180007d7b  jz      short loc_180007D93
0x180007d7d  mov     r8d, 400h
0x180007d83  mov     rdx, [rsp+78h+arg_60]
0x180007d8b  mov     rcx, rbx
0x180007d8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d93  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007d9a  test    rax, rax
0x180007d9d  jz      short loc_180007DA7
0x180007d9f  mov     rcx, rbx
0x180007da2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007da7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007dae  test    rax, rax
0x180007db1  jz      short loc_180007DC1
0x180007db3  test    byte ptr [rbx+4], 2
0x180007db7  jnz     short loc_180007DC1
0x180007db9  mov     rcx, rbx
0x180007dbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007dc1  cmp     [rbx+8], edi
0x180007dc4  jl      short loc_180007DE0
0x180007dc6  cmp     r15d, 3
0x180007dca  jnz     loc_180007EAF
0x180007dd0  mov     ecx, 8000FFFFh; this
0x180007dd5  mov     [rbx+8], ecx
0x180007dd8  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007ddd  mov     [rbx+0Ch], eax
0x180007de0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180007de7  jnz     short loc_180007E08
0x180007de9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180007df0  test    rax, rax
0x180007df3  jz      short loc_180007DFE
0x180007df5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007dfa  test    al, al
0x180007dfc  jmp     short loc_180007E06
0x180007dfe  call    cs:__imp_IsDebuggerPresent
0x180007e04  test    eax, eax
0x180007e06  jz      short loc_180007E0E
0x180007e08  test    byte ptr [rbx+4], 2
0x180007e0c  jz      short loc_180007E32
0x180007e0e  mov     rax, cs:g_pfnResultLoggingCallback
0x180007e15  test    rax, rax
0x180007e18  jz      short loc_180007E76
0x180007e1a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180007e21  jnz     short loc_180007E76
0x180007e23  xor     r8d, r8d
0x180007e26  xor     edx, edx
0x180007e28  mov     rcx, rbx
0x180007e2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e30  jmp     short loc_180007E76
0x180007e32  mov     ebp, 800h
0x180007e37  mov     rax, cs:g_pfnResultLoggingCallback
0x180007e3e  test    rax, rax
0x180007e41  jz      short loc_180007E5A
0x180007e43  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180007e4a  jnz     short loc_180007E5A
0x180007e4c  mov     r8d, ebp
0x180007e4f  mov     rdx, rsi
0x180007e52  mov     rcx, rbx
0x180007e55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e5a  cmp     [rsi], di
0x180007e5d  jnz     short loc_180007E6D
0x180007e5f  mov     r8, rbx; unsigned __int64
0x180007e62  mov     rdx, rbp; unsigned __int16 *
0x180007e65  mov     rcx, rsi; this
0x180007e68  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180007e6d  mov     rcx, rsi; lpOutputString
0x180007e70  call    cs:__imp_OutputDebugStringW
0x180007e76  test    byte ptr [rbx+4], 4
0x180007e7a  jnz     short loc_180007E85
0x180007e7c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180007e83  jz      short loc_180007E97
0x180007e85  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180007e8c  test    rax, rax
0x180007e8f  jz      short loc_180007E97
0x180007e91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e96  nop
0x180007e97  mov     rbx, [rsp+78h+arg_10]
0x180007e9f  add     rsp, 40h
0x180007ea3  pop     r15
0x180007ea5  pop     r14
0x180007ea7  pop     r13
0x180007ea9  pop     r12
0x180007eab  pop     rdi
0x180007eac  pop     rsi
0x180007ead  pop     rbp
0x180007eae  retn
0x180007eaf  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
