# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18001b270`
- end: `0x18001b568`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1800188a0`
- `0x180018bec`

## callees

- `0x1800187e0`
- `0x18001a714`
- `0x18001af74`
- `0x18001b270`
- `0x18001c06c`
- `0x18001c090`
- `0x18001c1e0`
- `0x18001c1fc`
- `0x18001d9d8`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b393`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b393`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001b4b2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001b4b2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001b524`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001b524`

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
0x18001b270  mov     [rsp+arg_10], rbx
0x18001b275  mov     [rsp+arg_8], edx
0x18001b279  mov     [rsp+arg_0], rcx
0x18001b27e  push    rbp
0x18001b27f  push    rsi
0x18001b280  push    rdi
0x18001b281  push    r12
0x18001b283  push    r13
0x18001b285  push    r14
0x18001b287  push    r15
0x18001b289  sub     rsp, 40h
0x18001b28d  mov     r14, [rsp+78h+arg_38]
0x18001b295  xor     eax, eax
0x18001b297  mov     rbx, [rsp+78h+arg_78]
0x18001b29f  xor     ebp, ebp
0x18001b2a1  mov     r15d, [rsp+78h+arg_30]
0x18001b2a9  mov     r10, rcx
0x18001b2ac  mov     rsi, [rsp+78h+lpOutputString]
0x18001b2b4  mov     r12, r9
0x18001b2b7  mov     r13, r8
0x18001b2ba  mov     ecx, r15d
0x18001b2bd  mov     [rsi], ax
0x18001b2c0  mov     rax, [rsp+78h+arg_60]
0x18001b2c8  mov     byte ptr [rax], 0
0x18001b2cb  mov     edi, [r14]
0x18001b2ce  mov     [rbx+8], edi
0x18001b2d1  mov     eax, [r14+4]
0x18001b2d5  mov     [rbx+0Ch], eax
0x18001b2d8  test    r15d, r15d
0x18001b2db  jz      short loc_18001B343
0x18001b2dd  sub     ecx, 1
0x18001b2e0  jz      short loc_18001B33A
0x18001b2e2  sub     ecx, 1
0x18001b2e5  jz      short loc_18001B2F5
0x18001b2e7  cmp     ecx, 1
0x18001b2ea  jnz     short loc_18001B34C
0x18001b2ec  mov     ecx, edi; this
0x18001b2ee  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18001b2f3  jmp     short loc_18001B34A
0x18001b2f5  test    edi, edi
0x18001b2f7  js      short loc_18001B331
0x18001b2f9  mov     rax, [rsp+78h+arg_28]
0x18001b301  mov     edi, 8007029Ch
0x18001b306  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18001b30a  mov     rcx, r10; int
0x18001b30d  mov     [rsp+78h+var_50], rax; __int64
0x18001b312  mov     rax, [rsp+78h+arg_20]
0x18001b31a  mov     [rsp+78h+var_58], rax; __int64
0x18001b31f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18001b324  mov     ecx, edi; this
0x18001b326  mov     [rbx+8], edi
0x18001b329  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001b32e  mov     [rbx+0Ch], eax
0x18001b331  mov     ecx, edi; this
0x18001b333  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18001b338  jmp     short loc_18001B34A
0x18001b33a  mov     ecx, edi; this
0x18001b33c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18001b341  jmp     short loc_18001B34A
0x18001b343  mov     ecx, edi; this
0x18001b345  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18001b34a  mov     ebp, eax
0x18001b34c  mov     eax, [rsp+78h+arg_70]
0x18001b353  mov     [rbx+4], eax
0x18001b356  mov     [rbx], r15d
0x18001b359  cmp     dword ptr [r14+8], 1
0x18001b35e  jnz     short loc_18001B366
0x18001b360  or      eax, 8
0x18001b363  mov     [rbx+4], eax
0x18001b366  mov     eax, 1
0x18001b36b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18001b373  inc     eax
0x18001b375  xor     edi, edi
0x18001b377  mov     [rbx+10h], eax
0x18001b37a  mov     rax, [rsp+78h+arg_40]
0x18001b382  test    rax, rax
0x18001b385  jz      short loc_18001B38C
0x18001b387  cmp     [rax], di
0x18001b38a  jnz     short loc_18001B38F
0x18001b38c  mov     rax, rdi
0x18001b38f  mov     [rbx+18h], rax
0x18001b393  call    cs:__imp_GetCurrentThreadId
0x18001b399  mov     [rbx+38h], r13
0x18001b39d  xorps   xmm0, xmm0
0x18001b3a0  mov     [rbx+20h], eax
0x18001b3a3  mov     eax, [rsp+78h+arg_8]
0x18001b3aa  mov     [rbx+40h], eax
0x18001b3ad  mov     rax, [rsp+78h+arg_20]
0x18001b3b5  mov     [rbx+28h], rax
0x18001b3b9  mov     rax, [rsp+78h+arg_28]
0x18001b3c1  mov     [rbx+88h], rax
0x18001b3c8  mov     rax, [rsp+78h+arg_0]
0x18001b3d0  mov     [rbx+90h], rax
0x18001b3d7  xor     eax, eax
0x18001b3d9  mov     [rbx+44h], ebp
0x18001b3dc  mov     [rbx+30h], r12
0x18001b3e0  mov     [rbx+48h], rdi
0x18001b3e4  movups  xmmword ptr [rbx+68h], xmm0
0x18001b3e8  mov     [rbx+78h], rax
0x18001b3ec  movups  xmmword ptr [rbx+50h], xmm0
0x18001b3f0  mov     [rbx+60h], rax
0x18001b3f4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001b3fb  test    rax, rax
0x18001b3fe  jz      short loc_18001B407
0x18001b400  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b405  jmp     short loc_18001B40A
0x18001b407  mov     rax, rdi
0x18001b40a  mov     [rbx+80h], rax
0x18001b411  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18001b418  test    rax, rax
0x18001b41b  jz      short loc_18001B425
0x18001b41d  mov     rcx, rbx
0x18001b420  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b425  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001b42c  test    rax, rax
0x18001b42f  jz      short loc_18001B447
0x18001b431  mov     rdx, [rsp+78h+arg_60]
0x18001b439  mov     r8d, 400h
0x18001b43f  mov     rcx, rbx
0x18001b442  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b447  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001b44e  test    rax, rax
0x18001b451  jz      short loc_18001B45B
0x18001b453  mov     rcx, rbx
0x18001b456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b45b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001b462  test    rax, rax
0x18001b465  jz      short loc_18001B475
0x18001b467  test    byte ptr [rbx+4], 2
0x18001b46b  jnz     short loc_18001B475
0x18001b46d  mov     rcx, rbx
0x18001b470  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b475  cmp     [rbx+8], edi
0x18001b478  jl      short loc_18001B494
0x18001b47a  cmp     r15d, 3
0x18001b47e  jnz     loc_18001B562
0x18001b484  mov     ecx, 8000FFFFh; this
0x18001b489  mov     [rbx+8], ecx
0x18001b48c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001b491  mov     [rbx+0Ch], eax
0x18001b494  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18001b49b  jnz     short loc_18001B4BC
0x18001b49d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001b4a4  test    rax, rax
0x18001b4a7  jz      short loc_18001B4B2
0x18001b4a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b4ae  test    al, al
0x18001b4b0  jmp     short loc_18001B4BA
0x18001b4b2  call    cs:__imp_IsDebuggerPresent
0x18001b4b8  test    eax, eax
0x18001b4ba  jz      short loc_18001B4C2
0x18001b4bc  test    byte ptr [rbx+4], 2
0x18001b4c0  jz      short loc_18001B4E6
0x18001b4c2  mov     rax, cs:g_pfnResultLoggingCallback
0x18001b4c9  test    rax, rax
0x18001b4cc  jz      short loc_18001B52A
0x18001b4ce  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001b4d5  jnz     short loc_18001B52A
0x18001b4d7  xor     r8d, r8d
0x18001b4da  xor     edx, edx
0x18001b4dc  mov     rcx, rbx
0x18001b4df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b4e4  jmp     short loc_18001B52A
0x18001b4e6  mov     rax, cs:g_pfnResultLoggingCallback
0x18001b4ed  mov     ebp, 800h
0x18001b4f2  test    rax, rax
0x18001b4f5  jz      short loc_18001B50E
0x18001b4f7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001b4fe  jnz     short loc_18001B50E
0x18001b500  mov     r8d, ebp
0x18001b503  mov     rdx, rsi
0x18001b506  mov     rcx, rbx
0x18001b509  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b50e  cmp     [rsi], di
0x18001b511  jnz     short loc_18001B521
0x18001b513  mov     r8, rbx; unsigned __int64
0x18001b516  mov     rdx, rbp; unsigned __int16 *
0x18001b519  mov     rcx, rsi; this
0x18001b51c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18001b521  mov     rcx, rsi; lpOutputString
0x18001b524  call    cs:__imp_OutputDebugStringW
0x18001b52a  test    byte ptr [rbx+4], 4
0x18001b52e  jnz     short loc_18001B539
0x18001b530  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18001b537  jz      short loc_18001B54A
0x18001b539  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001b540  test    rax, rax
0x18001b543  jz      short loc_18001B54A
0x18001b545  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b54a  mov     rbx, [rsp+78h+arg_10]
0x18001b552  add     rsp, 40h
0x18001b556  pop     r15
0x18001b558  pop     r14
0x18001b55a  pop     r13
0x18001b55c  pop     r12
0x18001b55e  pop     rdi
0x18001b55f  pop     rsi
0x18001b560  pop     rbp
0x18001b561  retn
0x18001b562  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
