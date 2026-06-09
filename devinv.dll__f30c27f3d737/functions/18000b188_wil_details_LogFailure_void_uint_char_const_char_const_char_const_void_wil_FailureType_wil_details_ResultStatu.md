# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000b188`
- end: `0x18000b481`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180008108`

## callees

- `0x180007b4c`
- `0x18000a734`
- `0x18000aedc`
- `0x18000b188`
- `0x18000bf88`
- `0x18000bfb0`
- `0x18000c0dc`
- `0x18000c0f8`
- `0x18000eaac`
- `0x180116010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b2ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b2ab`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000b43c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000b43c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000b3ca`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000b3ca`

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
0x18000b188  mov     [rsp+arg_10], rbx
0x18000b18d  mov     [rsp+arg_8], edx
0x18000b191  mov     [rsp+arg_0], rcx
0x18000b196  push    rbp
0x18000b197  push    rsi
0x18000b198  push    rdi
0x18000b199  push    r12
0x18000b19b  push    r13
0x18000b19d  push    r14
0x18000b19f  push    r15
0x18000b1a1  sub     rsp, 40h
0x18000b1a5  mov     r12, r9
0x18000b1a8  mov     r13, r8
0x18000b1ab  mov     r10, rcx
0x18000b1ae  xor     eax, eax
0x18000b1b0  mov     rsi, [rsp+78h+lpOutputString]
0x18000b1b8  mov     [rsi], ax
0x18000b1bb  mov     rax, [rsp+78h+arg_60]
0x18000b1c3  mov     byte ptr [rax], 0
0x18000b1c6  mov     r14, [rsp+78h+arg_38]
0x18000b1ce  mov     edi, [r14]
0x18000b1d1  mov     rbx, [rsp+78h+arg_78]
0x18000b1d9  mov     [rbx+8], edi
0x18000b1dc  mov     eax, [r14+4]
0x18000b1e0  mov     [rbx+0Ch], eax
0x18000b1e3  xor     ebp, ebp
0x18000b1e5  mov     r15d, [rsp+78h+arg_30]
0x18000b1ed  mov     ecx, r15d
0x18000b1f0  test    r15d, r15d
0x18000b1f3  jz      short loc_18000B25B
0x18000b1f5  sub     ecx, 1
0x18000b1f8  jz      short loc_18000B252
0x18000b1fa  sub     ecx, 1
0x18000b1fd  jz      short loc_18000B20D
0x18000b1ff  cmp     ecx, 1
0x18000b202  jnz     short loc_18000B264
0x18000b204  mov     ecx, edi; this
0x18000b206  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000b20b  jmp     short loc_18000B262
0x18000b20d  test    edi, edi
0x18000b20f  js      short loc_18000B249
0x18000b211  mov     edi, 8007029Ch
0x18000b216  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000b21a  mov     rax, [rsp+78h+arg_28]
0x18000b222  mov     [rsp+78h+var_50], rax; __int64
0x18000b227  mov     rax, [rsp+78h+arg_20]
0x18000b22f  mov     [rsp+78h+var_58], rax; __int64
0x18000b234  mov     rcx, r10; int
0x18000b237  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000b23c  mov     [rbx+8], edi
0x18000b23f  mov     ecx, edi; this
0x18000b241  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000b246  mov     [rbx+0Ch], eax
0x18000b249  mov     ecx, edi; this
0x18000b24b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000b250  jmp     short loc_18000B262
0x18000b252  mov     ecx, edi; this
0x18000b254  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000b259  jmp     short loc_18000B262
0x18000b25b  mov     ecx, edi; this
0x18000b25d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000b262  mov     ebp, eax
0x18000b264  mov     [rbx], r15d
0x18000b267  mov     eax, [rsp+78h+arg_70]
0x18000b26e  mov     [rbx+4], eax
0x18000b271  cmp     dword ptr [r14+8], 1
0x18000b276  jnz     short loc_18000B27E
0x18000b278  or      eax, 8
0x18000b27b  mov     [rbx+4], eax
0x18000b27e  mov     eax, 1
0x18000b283  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000b28b  inc     eax
0x18000b28d  mov     [rbx+10h], eax
0x18000b290  mov     rax, [rsp+78h+arg_40]
0x18000b298  xor     edi, edi
0x18000b29a  test    rax, rax
0x18000b29d  jz      short loc_18000B2A4
0x18000b29f  cmp     [rax], di
0x18000b2a2  jnz     short loc_18000B2A7
0x18000b2a4  mov     rax, rdi
0x18000b2a7  mov     [rbx+18h], rax
0x18000b2ab  call    cs:__imp_GetCurrentThreadId
0x18000b2b1  mov     [rbx+20h], eax
0x18000b2b4  mov     [rbx+38h], r13
0x18000b2b8  mov     eax, [rsp+78h+arg_8]
0x18000b2bf  mov     [rbx+40h], eax
0x18000b2c2  mov     [rbx+44h], ebp
0x18000b2c5  mov     rax, [rsp+78h+arg_20]
0x18000b2cd  mov     [rbx+28h], rax
0x18000b2d1  mov     [rbx+30h], r12
0x18000b2d5  mov     rax, [rsp+78h+arg_28]
0x18000b2dd  mov     [rbx+88h], rax
0x18000b2e4  mov     rax, [rsp+78h+arg_0]
0x18000b2ec  mov     [rbx+90h], rax
0x18000b2f3  mov     [rbx+48h], rdi
0x18000b2f7  xorps   xmm0, xmm0
0x18000b2fa  xor     eax, eax
0x18000b2fc  movups  xmmword ptr [rbx+68h], xmm0
0x18000b300  mov     [rbx+78h], rax
0x18000b304  movups  xmmword ptr [rbx+50h], xmm0
0x18000b308  mov     [rbx+60h], rax
0x18000b30c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000b313  test    rax, rax
0x18000b316  jz      short loc_18000B31F
0x18000b318  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b31d  jmp     short loc_18000B322
0x18000b31f  mov     rax, rdi
0x18000b322  mov     [rbx+80h], rax
0x18000b329  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000b330  test    rax, rax
0x18000b333  jz      short loc_18000B33D
0x18000b335  mov     rcx, rbx
0x18000b338  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b33d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000b344  test    rax, rax
0x18000b347  jz      short loc_18000B35F
0x18000b349  mov     r8d, 400h
0x18000b34f  mov     rdx, [rsp+78h+arg_60]
0x18000b357  mov     rcx, rbx
0x18000b35a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b35f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000b366  test    rax, rax
0x18000b369  jz      short loc_18000B373
0x18000b36b  mov     rcx, rbx
0x18000b36e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b373  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000b37a  test    rax, rax
0x18000b37d  jz      short loc_18000B38D
0x18000b37f  test    byte ptr [rbx+4], 2
0x18000b383  jnz     short loc_18000B38D
0x18000b385  mov     rcx, rbx
0x18000b388  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b38d  cmp     [rbx+8], edi
0x18000b390  jl      short loc_18000B3AC
0x18000b392  cmp     r15d, 3
0x18000b396  jnz     loc_18000B47B
0x18000b39c  mov     ecx, 8000FFFFh; this
0x18000b3a1  mov     [rbx+8], ecx
0x18000b3a4  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000b3a9  mov     [rbx+0Ch], eax
0x18000b3ac  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000b3b3  jnz     short loc_18000B3D4
0x18000b3b5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000b3bc  test    rax, rax
0x18000b3bf  jz      short loc_18000B3CA
0x18000b3c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3c6  test    al, al
0x18000b3c8  jmp     short loc_18000B3D2
0x18000b3ca  call    cs:__imp_IsDebuggerPresent
0x18000b3d0  test    eax, eax
0x18000b3d2  jz      short loc_18000B3DA
0x18000b3d4  test    byte ptr [rbx+4], 2
0x18000b3d8  jz      short loc_18000B3FE
0x18000b3da  mov     rax, cs:g_pfnResultLoggingCallback
0x18000b3e1  test    rax, rax
0x18000b3e4  jz      short loc_18000B442
0x18000b3e6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000b3ed  jnz     short loc_18000B442
0x18000b3ef  xor     r8d, r8d
0x18000b3f2  xor     edx, edx
0x18000b3f4  mov     rcx, rbx
0x18000b3f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3fc  jmp     short loc_18000B442
0x18000b3fe  mov     ebp, 800h
0x18000b403  mov     rax, cs:g_pfnResultLoggingCallback
0x18000b40a  test    rax, rax
0x18000b40d  jz      short loc_18000B426
0x18000b40f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000b416  jnz     short loc_18000B426
0x18000b418  mov     r8d, ebp
0x18000b41b  mov     rdx, rsi
0x18000b41e  mov     rcx, rbx
0x18000b421  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b426  cmp     [rsi], di
0x18000b429  jnz     short loc_18000B439
0x18000b42b  mov     r8, rbx; unsigned __int64
0x18000b42e  mov     rdx, rbp; unsigned __int16 *
0x18000b431  mov     rcx, rsi; this
0x18000b434  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000b439  mov     rcx, rsi; lpOutputString
0x18000b43c  call    cs:__imp_OutputDebugStringW
0x18000b442  test    byte ptr [rbx+4], 4
0x18000b446  jnz     short loc_18000B451
0x18000b448  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000b44f  jz      short loc_18000B463
0x18000b451  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000b458  test    rax, rax
0x18000b45b  jz      short loc_18000B463
0x18000b45d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b462  nop
0x18000b463  mov     rbx, [rsp+78h+arg_10]
0x18000b46b  add     rsp, 40h
0x18000b46f  pop     r15
0x18000b471  pop     r14
0x18000b473  pop     r13
0x18000b475  pop     r12
0x18000b477  pop     rdi
0x18000b478  pop     rsi
0x18000b479  pop     rbp
0x18000b47a  retn
0x18000b47b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
