# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18001cfec`
- end: `0x18001d2e5`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18001c190`
- `0x18001c250`

## callees

- `0x18001c0c4`
- `0x18001c9a4`
- `0x18001cd8c`
- `0x18001cfec`
- `0x18001d570`
- `0x18001d590`
- `0x18001d5a4`
- `0x18001d5c0`
- `0x18001dcb4`
- `0x180026010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d10f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d10f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001d22e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001d22e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001d2a0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001d2a0`

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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v25 = !IsDebuggerPresent())
      : (v25 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v25)
    || (*(_BYTE *)(a16 + 4) & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, 0, 0, v23);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048, v23);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v23);
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
0x18001cfec  mov     [rsp+arg_10], rbx
0x18001cff1  mov     [rsp+arg_8], edx
0x18001cff5  mov     [rsp+arg_0], rcx
0x18001cffa  push    rbp
0x18001cffb  push    rsi
0x18001cffc  push    rdi
0x18001cffd  push    r12
0x18001cfff  push    r13
0x18001d001  push    r14
0x18001d003  push    r15
0x18001d005  sub     rsp, 40h
0x18001d009  mov     r12, r9
0x18001d00c  mov     r13, r8
0x18001d00f  mov     r10, rcx
0x18001d012  xor     eax, eax
0x18001d014  mov     rsi, [rsp+78h+lpOutputString]
0x18001d01c  mov     [rsi], ax
0x18001d01f  mov     rax, [rsp+78h+arg_60]
0x18001d027  mov     byte ptr [rax], 0
0x18001d02a  mov     r14, [rsp+78h+arg_38]
0x18001d032  mov     edi, [r14]
0x18001d035  mov     rbx, [rsp+78h+arg_78]
0x18001d03d  mov     [rbx+8], edi
0x18001d040  mov     eax, [r14+4]
0x18001d044  mov     [rbx+0Ch], eax
0x18001d047  xor     ebp, ebp
0x18001d049  mov     r15d, [rsp+78h+arg_30]
0x18001d051  mov     ecx, r15d
0x18001d054  test    r15d, r15d
0x18001d057  jz      short loc_18001D0BF
0x18001d059  sub     ecx, 1
0x18001d05c  jz      short loc_18001D0B6
0x18001d05e  sub     ecx, 1
0x18001d061  jz      short loc_18001D071
0x18001d063  cmp     ecx, 1
0x18001d066  jnz     short loc_18001D0C8
0x18001d068  mov     ecx, edi; this
0x18001d06a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18001d06f  jmp     short loc_18001D0C6
0x18001d071  test    edi, edi
0x18001d073  js      short loc_18001D0AD
0x18001d075  mov     edi, 8007029Ch
0x18001d07a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18001d07e  mov     rax, [rsp+78h+arg_28]
0x18001d086  mov     [rsp+78h+var_50], rax; __int64
0x18001d08b  mov     rax, [rsp+78h+arg_20]
0x18001d093  mov     [rsp+78h+var_58], rax; __int64
0x18001d098  mov     rcx, r10; int
0x18001d09b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18001d0a0  mov     [rbx+8], edi
0x18001d0a3  mov     ecx, edi; this
0x18001d0a5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001d0aa  mov     [rbx+0Ch], eax
0x18001d0ad  mov     ecx, edi; this
0x18001d0af  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18001d0b4  jmp     short loc_18001D0C6
0x18001d0b6  mov     ecx, edi; this
0x18001d0b8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18001d0bd  jmp     short loc_18001D0C6
0x18001d0bf  mov     ecx, edi; this
0x18001d0c1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18001d0c6  mov     ebp, eax
0x18001d0c8  mov     [rbx], r15d
0x18001d0cb  mov     eax, [rsp+78h+arg_70]
0x18001d0d2  mov     [rbx+4], eax
0x18001d0d5  cmp     dword ptr [r14+8], 1
0x18001d0da  jnz     short loc_18001D0E2
0x18001d0dc  or      eax, 8
0x18001d0df  mov     [rbx+4], eax
0x18001d0e2  mov     eax, 1
0x18001d0e7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18001d0ef  inc     eax
0x18001d0f1  mov     [rbx+10h], eax
0x18001d0f4  mov     rax, [rsp+78h+arg_40]
0x18001d0fc  xor     edi, edi
0x18001d0fe  test    rax, rax
0x18001d101  jz      short loc_18001D108
0x18001d103  cmp     [rax], di
0x18001d106  jnz     short loc_18001D10B
0x18001d108  mov     rax, rdi
0x18001d10b  mov     [rbx+18h], rax
0x18001d10f  call    cs:__imp_GetCurrentThreadId
0x18001d115  mov     [rbx+20h], eax
0x18001d118  mov     [rbx+38h], r13
0x18001d11c  mov     eax, [rsp+78h+arg_8]
0x18001d123  mov     [rbx+40h], eax
0x18001d126  mov     [rbx+44h], ebp
0x18001d129  mov     rax, [rsp+78h+arg_20]
0x18001d131  mov     [rbx+28h], rax
0x18001d135  mov     [rbx+30h], r12
0x18001d139  mov     rax, [rsp+78h+arg_28]
0x18001d141  mov     [rbx+88h], rax
0x18001d148  mov     rax, [rsp+78h+arg_0]
0x18001d150  mov     [rbx+90h], rax
0x18001d157  mov     [rbx+48h], rdi
0x18001d15b  xorps   xmm0, xmm0
0x18001d15e  xor     eax, eax
0x18001d160  movups  xmmword ptr [rbx+68h], xmm0
0x18001d164  mov     [rbx+78h], rax
0x18001d168  movups  xmmword ptr [rbx+50h], xmm0
0x18001d16c  mov     [rbx+60h], rax
0x18001d170  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001d177  test    rax, rax
0x18001d17a  jz      short loc_18001D183
0x18001d17c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d181  jmp     short loc_18001D186
0x18001d183  mov     rax, rdi
0x18001d186  mov     [rbx+80h], rax
0x18001d18d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18001d194  test    rax, rax
0x18001d197  jz      short loc_18001D1A1
0x18001d199  mov     rcx, rbx
0x18001d19c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d1a1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001d1a8  test    rax, rax
0x18001d1ab  jz      short loc_18001D1C3
0x18001d1ad  mov     r8d, 400h
0x18001d1b3  mov     rdx, [rsp+78h+arg_60]
0x18001d1bb  mov     rcx, rbx
0x18001d1be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d1c3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001d1ca  test    rax, rax
0x18001d1cd  jz      short loc_18001D1D7
0x18001d1cf  mov     rcx, rbx
0x18001d1d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d1d7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001d1de  test    rax, rax
0x18001d1e1  jz      short loc_18001D1F1
0x18001d1e3  test    byte ptr [rbx+4], 2
0x18001d1e7  jnz     short loc_18001D1F1
0x18001d1e9  mov     rcx, rbx
0x18001d1ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d1f1  cmp     [rbx+8], edi
0x18001d1f4  jl      short loc_18001D210
0x18001d1f6  cmp     r15d, 3
0x18001d1fa  jnz     loc_18001D2DF
0x18001d200  mov     ecx, 8000FFFFh; this
0x18001d205  mov     [rbx+8], ecx
0x18001d208  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001d20d  mov     [rbx+0Ch], eax
0x18001d210  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18001d217  jnz     short loc_18001D238
0x18001d219  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001d220  test    rax, rax
0x18001d223  jz      short loc_18001D22E
0x18001d225  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d22a  test    al, al
0x18001d22c  jmp     short loc_18001D236
0x18001d22e  call    cs:__imp_IsDebuggerPresent
0x18001d234  test    eax, eax
0x18001d236  jz      short loc_18001D23E
0x18001d238  test    byte ptr [rbx+4], 2
0x18001d23c  jz      short loc_18001D262
0x18001d23e  mov     rax, cs:g_pfnResultLoggingCallback
0x18001d245  test    rax, rax
0x18001d248  jz      short loc_18001D2A6
0x18001d24a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001d251  jnz     short loc_18001D2A6
0x18001d253  xor     r8d, r8d
0x18001d256  xor     edx, edx
0x18001d258  mov     rcx, rbx
0x18001d25b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d260  jmp     short loc_18001D2A6
0x18001d262  mov     ebp, 800h
0x18001d267  mov     rax, cs:g_pfnResultLoggingCallback
0x18001d26e  test    rax, rax
0x18001d271  jz      short loc_18001D28A
0x18001d273  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001d27a  jnz     short loc_18001D28A
0x18001d27c  mov     r8d, ebp
0x18001d27f  mov     rdx, rsi
0x18001d282  mov     rcx, rbx
0x18001d285  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d28a  cmp     [rsi], di
0x18001d28d  jnz     short loc_18001D29D
0x18001d28f  mov     r8, rbx; unsigned __int64
0x18001d292  mov     rdx, rbp; unsigned __int16 *
0x18001d295  mov     rcx, rsi; this
0x18001d298  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18001d29d  mov     rcx, rsi; lpOutputString
0x18001d2a0  call    cs:__imp_OutputDebugStringW
0x18001d2a6  test    byte ptr [rbx+4], 4
0x18001d2aa  jnz     short loc_18001D2B5
0x18001d2ac  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18001d2b3  jz      short loc_18001D2C7
0x18001d2b5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001d2bc  test    rax, rax
0x18001d2bf  jz      short loc_18001D2C7
0x18001d2c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d2c6  nop
0x18001d2c7  mov     rbx, [rsp+78h+arg_10]
0x18001d2cf  add     rsp, 40h
0x18001d2d3  pop     r15
0x18001d2d5  pop     r14
0x18001d2d7  pop     r13
0x18001d2d9  pop     r12
0x18001d2db  pop     rdi
0x18001d2dc  pop     rsi
0x18001d2dd  pop     rbp
0x18001d2de  retn
0x18001d2df  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
