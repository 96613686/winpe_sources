# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18001b090`
- end: `0x18001b385`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x18001af94`
- `0x18002fae8`
- `0x18002fba8`
- `0x180033d2c`

## callees

- `0x18000ee60`
- `0x18001a804`
- `0x18001b090`
- `0x18001bfa0`
- `0x18002fa2c`
- `0x1800309d4`
- `0x1800309f0`
- `0x180030a04`
- `0x180031868`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b1b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b1b3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001b2d4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001b2d4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001b346`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001b346`

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
0x18001b090  mov     [rsp+arg_10], rbx
0x18001b095  mov     [rsp+arg_8], edx
0x18001b099  mov     [rsp+arg_0], rcx
0x18001b09e  push    rbp
0x18001b09f  push    rsi
0x18001b0a0  push    rdi
0x18001b0a1  push    r12
0x18001b0a3  push    r13
0x18001b0a5  push    r14
0x18001b0a7  push    r15
0x18001b0a9  sub     rsp, 40h
0x18001b0ad  mov     r12, r9
0x18001b0b0  mov     r13, r8
0x18001b0b3  mov     r10, rcx
0x18001b0b6  xor     eax, eax
0x18001b0b8  mov     rsi, [rsp+78h+lpOutputString]
0x18001b0c0  mov     [rsi], ax
0x18001b0c3  mov     rax, [rsp+78h+arg_60]
0x18001b0cb  mov     byte ptr [rax], 0
0x18001b0ce  mov     r14, [rsp+78h+arg_38]
0x18001b0d6  mov     edi, [r14]
0x18001b0d9  mov     rbx, [rsp+78h+arg_78]
0x18001b0e1  mov     [rbx+8], edi
0x18001b0e4  mov     eax, [r14+4]
0x18001b0e8  mov     [rbx+0Ch], eax
0x18001b0eb  xor     ebp, ebp
0x18001b0ed  mov     r15d, [rsp+78h+arg_30]
0x18001b0f5  mov     ecx, r15d
0x18001b0f8  test    r15d, r15d
0x18001b0fb  jz      short loc_18001B163
0x18001b0fd  sub     ecx, 1
0x18001b100  jz      short loc_18001B15A
0x18001b102  sub     ecx, 1
0x18001b105  jz      short loc_18001B115
0x18001b107  cmp     ecx, 1
0x18001b10a  jnz     short loc_18001B16C
0x18001b10c  mov     ecx, edi; this
0x18001b10e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18001b113  jmp     short loc_18001B16A
0x18001b115  test    edi, edi
0x18001b117  js      short loc_18001B151
0x18001b119  mov     edi, 8007029Ch
0x18001b11e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18001b122  mov     rax, [rsp+78h+arg_28]
0x18001b12a  mov     [rsp+78h+var_50], rax; __int64
0x18001b12f  mov     rax, [rsp+78h+arg_20]
0x18001b137  mov     [rsp+78h+var_58], rax; __int64
0x18001b13c  mov     rcx, r10; int
0x18001b13f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18001b144  mov     [rbx+8], edi
0x18001b147  mov     ecx, edi; this
0x18001b149  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001b14e  mov     [rbx+0Ch], eax
0x18001b151  mov     ecx, edi; this
0x18001b153  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18001b158  jmp     short loc_18001B16A
0x18001b15a  mov     ecx, edi; this
0x18001b15c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18001b161  jmp     short loc_18001B16A
0x18001b163  mov     ecx, edi; this
0x18001b165  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18001b16a  mov     ebp, eax
0x18001b16c  mov     [rbx], r15d
0x18001b16f  mov     eax, [rsp+78h+arg_70]
0x18001b176  mov     [rbx+4], eax
0x18001b179  cmp     dword ptr [r14+8], 1
0x18001b17e  jnz     short loc_18001B186
0x18001b180  or      eax, 8
0x18001b183  mov     [rbx+4], eax
0x18001b186  mov     eax, 1
0x18001b18b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18001b193  inc     eax
0x18001b195  mov     [rbx+10h], eax
0x18001b198  mov     rax, [rsp+78h+arg_40]
0x18001b1a0  xor     edi, edi
0x18001b1a2  test    rax, rax
0x18001b1a5  jz      short loc_18001B1AC
0x18001b1a7  cmp     [rax], di
0x18001b1aa  jnz     short loc_18001B1AF
0x18001b1ac  mov     rax, rdi
0x18001b1af  mov     [rbx+18h], rax
0x18001b1b3  call    cs:__imp_GetCurrentThreadId
0x18001b1b9  mov     [rbx+20h], eax
0x18001b1bc  mov     [rbx+38h], r13
0x18001b1c0  mov     eax, [rsp+78h+arg_8]
0x18001b1c7  mov     [rbx+40h], eax
0x18001b1ca  mov     [rbx+44h], ebp
0x18001b1cd  mov     rax, [rsp+78h+arg_20]
0x18001b1d5  mov     [rbx+28h], rax
0x18001b1d9  mov     [rbx+30h], r12
0x18001b1dd  mov     rax, [rsp+78h+arg_28]
0x18001b1e5  mov     [rbx+88h], rax
0x18001b1ec  mov     rax, [rsp+78h+arg_0]
0x18001b1f4  mov     [rbx+90h], rax
0x18001b1fb  mov     [rbx+48h], rdi
0x18001b1ff  xorps   xmm0, xmm0
0x18001b202  xor     eax, eax
0x18001b204  movups  xmmword ptr [rbx+68h], xmm0
0x18001b208  mov     [rbx+78h], rax
0x18001b20c  movups  xmmword ptr [rbx+50h], xmm0
0x18001b210  mov     [rbx+60h], rax
0x18001b214  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001b21b  test    rax, rax
0x18001b21e  jz      short loc_18001B227
0x18001b220  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b225  jmp     short loc_18001B22A
0x18001b227  mov     rax, rdi
0x18001b22a  mov     [rbx+80h], rax
0x18001b231  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18001b238  test    rax, rax
0x18001b23b  jz      short loc_18001B245
0x18001b23d  mov     rcx, rbx
0x18001b240  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b245  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001b24c  test    rax, rax
0x18001b24f  jz      short loc_18001B267
0x18001b251  mov     r8d, 400h
0x18001b257  mov     rdx, [rsp+78h+arg_60]
0x18001b25f  mov     rcx, rbx
0x18001b262  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b267  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001b26e  test    rax, rax
0x18001b271  jz      short loc_18001B27B
0x18001b273  mov     rcx, rbx
0x18001b276  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b27b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001b282  test    rax, rax
0x18001b285  jz      short loc_18001B295
0x18001b287  test    byte ptr [rbx+4], 2
0x18001b28b  jnz     short loc_18001B295
0x18001b28d  mov     rcx, rbx
0x18001b290  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b295  cmp     [rbx+8], edi
0x18001b298  jl      short loc_18001B2B6
0x18001b29a  cmp     r15d, 3
0x18001b29e  jz      short loc_18001B2A6
0x18001b2a0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18001b2a6  mov     ecx, 8000FFFFh; this
0x18001b2ab  mov     [rbx+8], ecx
0x18001b2ae  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001b2b3  mov     [rbx+0Ch], eax
0x18001b2b6  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18001b2bd  jnz     short loc_18001B2DE
0x18001b2bf  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001b2c6  test    rax, rax
0x18001b2c9  jz      short loc_18001B2D4
0x18001b2cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b2d0  test    al, al
0x18001b2d2  jmp     short loc_18001B2DC
0x18001b2d4  call    cs:__imp_IsDebuggerPresent
0x18001b2da  test    eax, eax
0x18001b2dc  jz      short loc_18001B2E4
0x18001b2de  test    byte ptr [rbx+4], 2
0x18001b2e2  jz      short loc_18001B308
0x18001b2e4  mov     rax, cs:g_pfnResultLoggingCallback
0x18001b2eb  test    rax, rax
0x18001b2ee  jz      short loc_18001B34C
0x18001b2f0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001b2f7  jnz     short loc_18001B34C
0x18001b2f9  xor     r8d, r8d
0x18001b2fc  xor     edx, edx
0x18001b2fe  mov     rcx, rbx
0x18001b301  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b306  jmp     short loc_18001B34C
0x18001b308  mov     ebp, 800h
0x18001b30d  mov     rax, cs:g_pfnResultLoggingCallback
0x18001b314  test    rax, rax
0x18001b317  jz      short loc_18001B330
0x18001b319  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001b320  jnz     short loc_18001B330
0x18001b322  mov     r8d, ebp
0x18001b325  mov     rdx, rsi
0x18001b328  mov     rcx, rbx
0x18001b32b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b330  cmp     [rsi], di
0x18001b333  jnz     short loc_18001B343
0x18001b335  mov     r8, rbx; unsigned __int64
0x18001b338  mov     rdx, rbp; unsigned __int16 *
0x18001b33b  mov     rcx, rsi; this
0x18001b33e  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18001b343  mov     rcx, rsi; lpOutputString
0x18001b346  call    cs:__imp_OutputDebugStringW
0x18001b34c  test    byte ptr [rbx+4], 4
0x18001b350  jnz     short loc_18001B35B
0x18001b352  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18001b359  jz      short loc_18001B36D
0x18001b35b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001b362  test    rax, rax
0x18001b365  jz      short loc_18001B36D
0x18001b367  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b36c  nop
0x18001b36d  mov     rbx, [rsp+78h+arg_10]
0x18001b375  add     rsp, 40h
0x18001b379  pop     r15
0x18001b37b  pop     r14
0x18001b37d  pop     r13
0x18001b37f  pop     r12
0x18001b381  pop     rdi
0x18001b382  pop     rsi
0x18001b383  pop     rbp
0x18001b384  retn
```
