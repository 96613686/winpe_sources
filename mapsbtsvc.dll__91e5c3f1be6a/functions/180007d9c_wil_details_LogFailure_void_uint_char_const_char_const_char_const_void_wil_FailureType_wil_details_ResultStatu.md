# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180007d9c`
- end: `0x180008095`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180006598`
- `0x1800068e4`

## callees

- `0x1800064d8`
- `0x180007404`
- `0x180007bd8`
- `0x180007d9c`
- `0x18000845c`
- `0x180008480`
- `0x180008494`
- `0x1800084b0`
- `0x180009210`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007ebf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007ebf`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008050`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008050`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007fde`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007fde`

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
0x180007d9c  mov     [rsp+arg_10], rbx
0x180007da1  mov     [rsp+arg_8], edx
0x180007da5  mov     [rsp+arg_0], rcx
0x180007daa  push    rbp
0x180007dab  push    rsi
0x180007dac  push    rdi
0x180007dad  push    r12
0x180007daf  push    r13
0x180007db1  push    r14
0x180007db3  push    r15
0x180007db5  sub     rsp, 40h
0x180007db9  mov     r12, r9
0x180007dbc  mov     r13, r8
0x180007dbf  mov     r10, rcx
0x180007dc2  xor     eax, eax
0x180007dc4  mov     rsi, [rsp+78h+lpOutputString]
0x180007dcc  mov     [rsi], ax
0x180007dcf  mov     rax, [rsp+78h+arg_60]
0x180007dd7  mov     byte ptr [rax], 0
0x180007dda  mov     r14, [rsp+78h+arg_38]
0x180007de2  mov     edi, [r14]
0x180007de5  mov     rbx, [rsp+78h+arg_78]
0x180007ded  mov     [rbx+8], edi
0x180007df0  mov     eax, [r14+4]
0x180007df4  mov     [rbx+0Ch], eax
0x180007df7  xor     ebp, ebp
0x180007df9  mov     r15d, [rsp+78h+arg_30]
0x180007e01  mov     ecx, r15d
0x180007e04  test    r15d, r15d
0x180007e07  jz      short loc_180007E6F
0x180007e09  sub     ecx, 1
0x180007e0c  jz      short loc_180007E66
0x180007e0e  sub     ecx, 1
0x180007e11  jz      short loc_180007E21
0x180007e13  cmp     ecx, 1
0x180007e16  jnz     short loc_180007E78
0x180007e18  mov     ecx, edi; this
0x180007e1a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180007e1f  jmp     short loc_180007E76
0x180007e21  test    edi, edi
0x180007e23  js      short loc_180007E5D
0x180007e25  mov     edi, 8007029Ch
0x180007e2a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180007e2e  mov     rax, [rsp+78h+arg_28]
0x180007e36  mov     [rsp+78h+var_50], rax; __int64
0x180007e3b  mov     rax, [rsp+78h+arg_20]
0x180007e43  mov     [rsp+78h+var_58], rax; __int64
0x180007e48  mov     rcx, r10; int
0x180007e4b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180007e50  mov     [rbx+8], edi
0x180007e53  mov     ecx, edi; this
0x180007e55  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007e5a  mov     [rbx+0Ch], eax
0x180007e5d  mov     ecx, edi; this
0x180007e5f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180007e64  jmp     short loc_180007E76
0x180007e66  mov     ecx, edi; this
0x180007e68  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180007e6d  jmp     short loc_180007E76
0x180007e6f  mov     ecx, edi; this
0x180007e71  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180007e76  mov     ebp, eax
0x180007e78  mov     [rbx], r15d
0x180007e7b  mov     eax, [rsp+78h+arg_70]
0x180007e82  mov     [rbx+4], eax
0x180007e85  cmp     dword ptr [r14+8], 1
0x180007e8a  jnz     short loc_180007E92
0x180007e8c  or      eax, 8
0x180007e8f  mov     [rbx+4], eax
0x180007e92  mov     eax, 1
0x180007e97  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180007e9f  inc     eax
0x180007ea1  mov     [rbx+10h], eax
0x180007ea4  mov     rax, [rsp+78h+arg_40]
0x180007eac  xor     edi, edi
0x180007eae  test    rax, rax
0x180007eb1  jz      short loc_180007EB8
0x180007eb3  cmp     [rax], di
0x180007eb6  jnz     short loc_180007EBB
0x180007eb8  mov     rax, rdi
0x180007ebb  mov     [rbx+18h], rax
0x180007ebf  call    cs:__imp_GetCurrentThreadId
0x180007ec5  mov     [rbx+20h], eax
0x180007ec8  mov     [rbx+38h], r13
0x180007ecc  mov     eax, [rsp+78h+arg_8]
0x180007ed3  mov     [rbx+40h], eax
0x180007ed6  mov     [rbx+44h], ebp
0x180007ed9  mov     rax, [rsp+78h+arg_20]
0x180007ee1  mov     [rbx+28h], rax
0x180007ee5  mov     [rbx+30h], r12
0x180007ee9  mov     rax, [rsp+78h+arg_28]
0x180007ef1  mov     [rbx+88h], rax
0x180007ef8  mov     rax, [rsp+78h+arg_0]
0x180007f00  mov     [rbx+90h], rax
0x180007f07  mov     [rbx+48h], rdi
0x180007f0b  xorps   xmm0, xmm0
0x180007f0e  xor     eax, eax
0x180007f10  movups  xmmword ptr [rbx+68h], xmm0
0x180007f14  mov     [rbx+78h], rax
0x180007f18  movups  xmmword ptr [rbx+50h], xmm0
0x180007f1c  mov     [rbx+60h], rax
0x180007f20  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180007f27  test    rax, rax
0x180007f2a  jz      short loc_180007F33
0x180007f2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f31  jmp     short loc_180007F36
0x180007f33  mov     rax, rdi
0x180007f36  mov     [rbx+80h], rax
0x180007f3d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180007f44  test    rax, rax
0x180007f47  jz      short loc_180007F51
0x180007f49  mov     rcx, rbx
0x180007f4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f51  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180007f58  test    rax, rax
0x180007f5b  jz      short loc_180007F73
0x180007f5d  mov     r8d, 400h
0x180007f63  mov     rdx, [rsp+78h+arg_60]
0x180007f6b  mov     rcx, rbx
0x180007f6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f73  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007f7a  test    rax, rax
0x180007f7d  jz      short loc_180007F87
0x180007f7f  mov     rcx, rbx
0x180007f82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f87  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007f8e  test    rax, rax
0x180007f91  jz      short loc_180007FA1
0x180007f93  test    byte ptr [rbx+4], 2
0x180007f97  jnz     short loc_180007FA1
0x180007f99  mov     rcx, rbx
0x180007f9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fa1  cmp     [rbx+8], edi
0x180007fa4  jl      short loc_180007FC0
0x180007fa6  cmp     r15d, 3
0x180007faa  jnz     loc_18000808F
0x180007fb0  mov     ecx, 8000FFFFh; this
0x180007fb5  mov     [rbx+8], ecx
0x180007fb8  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007fbd  mov     [rbx+0Ch], eax
0x180007fc0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180007fc7  jnz     short loc_180007FE8
0x180007fc9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180007fd0  test    rax, rax
0x180007fd3  jz      short loc_180007FDE
0x180007fd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fda  test    al, al
0x180007fdc  jmp     short loc_180007FE6
0x180007fde  call    cs:__imp_IsDebuggerPresent
0x180007fe4  test    eax, eax
0x180007fe6  jz      short loc_180007FEE
0x180007fe8  test    byte ptr [rbx+4], 2
0x180007fec  jz      short loc_180008012
0x180007fee  mov     rax, cs:g_pfnResultLoggingCallback
0x180007ff5  test    rax, rax
0x180007ff8  jz      short loc_180008056
0x180007ffa  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180008001  jnz     short loc_180008056
0x180008003  xor     r8d, r8d
0x180008006  xor     edx, edx
0x180008008  mov     rcx, rbx
0x18000800b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008010  jmp     short loc_180008056
0x180008012  mov     ebp, 800h
0x180008017  mov     rax, cs:g_pfnResultLoggingCallback
0x18000801e  test    rax, rax
0x180008021  jz      short loc_18000803A
0x180008023  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000802a  jnz     short loc_18000803A
0x18000802c  mov     r8d, ebp
0x18000802f  mov     rdx, rsi
0x180008032  mov     rcx, rbx
0x180008035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000803a  cmp     [rsi], di
0x18000803d  jnz     short loc_18000804D
0x18000803f  mov     r8, rbx; unsigned __int64
0x180008042  mov     rdx, rbp; unsigned __int16 *
0x180008045  mov     rcx, rsi; this
0x180008048  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000804d  mov     rcx, rsi; lpOutputString
0x180008050  call    cs:__imp_OutputDebugStringW
0x180008056  test    byte ptr [rbx+4], 4
0x18000805a  jnz     short loc_180008065
0x18000805c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180008063  jz      short loc_180008077
0x180008065  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000806c  test    rax, rax
0x18000806f  jz      short loc_180008077
0x180008071  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008076  nop
0x180008077  mov     rbx, [rsp+78h+arg_10]
0x18000807f  add     rsp, 40h
0x180008083  pop     r15
0x180008085  pop     r14
0x180008087  pop     r13
0x180008089  pop     r12
0x18000808b  pop     rdi
0x18000808c  pop     rsi
0x18000808d  pop     rbp
0x18000808e  retn
0x18000808f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
