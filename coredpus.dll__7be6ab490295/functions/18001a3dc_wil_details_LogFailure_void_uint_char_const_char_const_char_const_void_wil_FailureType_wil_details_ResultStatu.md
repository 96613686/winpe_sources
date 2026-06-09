# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18001a3dc`
- end: `0x18001a6e8`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `780`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180016e58`
- `0x180016f08`
- `0x1800172bc`

## callees

- `0x1800047b0`
- `0x180016d2c`
- `0x1800199f4`
- `0x18001a3dc`
- `0x18001b134`
- `0x18001b160`
- `0x18001b224`
- `0x18001b244`
- `0x18001d4fc`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a4ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a4ff`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001a69c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001a69c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001a624`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001a624`

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
0x18001a3dc  mov     [rsp+arg_10], rbx
0x18001a3e1  mov     [rsp+arg_8], edx
0x18001a3e5  mov     [rsp+arg_0], rcx
0x18001a3ea  push    rbp
0x18001a3eb  push    rsi
0x18001a3ec  push    rdi
0x18001a3ed  push    r12
0x18001a3ef  push    r13
0x18001a3f1  push    r14
0x18001a3f3  push    r15
0x18001a3f5  sub     rsp, 40h
0x18001a3f9  mov     r12, r9
0x18001a3fc  mov     r13, r8
0x18001a3ff  mov     r10, rcx
0x18001a402  xor     eax, eax
0x18001a404  mov     rsi, [rsp+78h+lpOutputString]
0x18001a40c  mov     [rsi], ax
0x18001a40f  mov     rax, [rsp+78h+arg_60]
0x18001a417  mov     byte ptr [rax], 0
0x18001a41a  mov     r14, [rsp+78h+arg_38]
0x18001a422  mov     edi, [r14]
0x18001a425  mov     rbx, [rsp+78h+arg_78]
0x18001a42d  mov     [rbx+8], edi
0x18001a430  mov     eax, [r14+4]
0x18001a434  mov     [rbx+0Ch], eax
0x18001a437  xor     ebp, ebp
0x18001a439  mov     r15d, [rsp+78h+arg_30]
0x18001a441  mov     ecx, r15d
0x18001a444  test    r15d, r15d
0x18001a447  jz      short loc_18001A4AF
0x18001a449  sub     ecx, 1
0x18001a44c  jz      short loc_18001A4A6
0x18001a44e  sub     ecx, 1
0x18001a451  jz      short loc_18001A461
0x18001a453  cmp     ecx, 1
0x18001a456  jnz     short loc_18001A4B8
0x18001a458  mov     ecx, edi; this
0x18001a45a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18001a45f  jmp     short loc_18001A4B6
0x18001a461  test    edi, edi
0x18001a463  js      short loc_18001A49D
0x18001a465  mov     edi, 8007029Ch
0x18001a46a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18001a46e  mov     rax, [rsp+78h+arg_28]
0x18001a476  mov     [rsp+78h+var_50], rax; __int64
0x18001a47b  mov     rax, [rsp+78h+arg_20]
0x18001a483  mov     [rsp+78h+var_58], rax; __int64
0x18001a488  mov     rcx, r10; int
0x18001a48b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18001a490  mov     [rbx+8], edi
0x18001a493  mov     ecx, edi; this
0x18001a495  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001a49a  mov     [rbx+0Ch], eax
0x18001a49d  mov     ecx, edi; this
0x18001a49f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18001a4a4  jmp     short loc_18001A4B6
0x18001a4a6  mov     ecx, edi; this
0x18001a4a8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18001a4ad  jmp     short loc_18001A4B6
0x18001a4af  mov     ecx, edi; this
0x18001a4b1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18001a4b6  mov     ebp, eax
0x18001a4b8  mov     [rbx], r15d
0x18001a4bb  mov     eax, [rsp+78h+arg_70]
0x18001a4c2  mov     [rbx+4], eax
0x18001a4c5  cmp     dword ptr [r14+8], 1
0x18001a4ca  jnz     short loc_18001A4D2
0x18001a4cc  or      eax, 8
0x18001a4cf  mov     [rbx+4], eax
0x18001a4d2  mov     eax, 1
0x18001a4d7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18001a4df  inc     eax
0x18001a4e1  mov     [rbx+10h], eax
0x18001a4e4  mov     rax, [rsp+78h+arg_40]
0x18001a4ec  xor     edi, edi
0x18001a4ee  test    rax, rax
0x18001a4f1  jz      short loc_18001A4F8
0x18001a4f3  cmp     [rax], di
0x18001a4f6  jnz     short loc_18001A4FB
0x18001a4f8  mov     rax, rdi
0x18001a4fb  mov     [rbx+18h], rax
0x18001a4ff  call    cs:__imp_GetCurrentThreadId
0x18001a506  nop     dword ptr [rax+rax+00h]
0x18001a50b  mov     [rbx+20h], eax
0x18001a50e  mov     [rbx+38h], r13
0x18001a512  mov     eax, [rsp+78h+arg_8]
0x18001a519  mov     [rbx+40h], eax
0x18001a51c  mov     [rbx+44h], ebp
0x18001a51f  mov     rax, [rsp+78h+arg_20]
0x18001a527  mov     [rbx+28h], rax
0x18001a52b  mov     [rbx+30h], r12
0x18001a52f  mov     rax, [rsp+78h+arg_28]
0x18001a537  mov     [rbx+88h], rax
0x18001a53e  mov     rax, [rsp+78h+arg_0]
0x18001a546  mov     [rbx+90h], rax
0x18001a54d  mov     [rbx+48h], rdi
0x18001a551  xorps   xmm0, xmm0
0x18001a554  xor     eax, eax
0x18001a556  movups  xmmword ptr [rbx+68h], xmm0
0x18001a55a  mov     [rbx+78h], rax
0x18001a55e  movups  xmmword ptr [rbx+50h], xmm0
0x18001a562  mov     [rbx+60h], rax
0x18001a566  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001a56d  test    rax, rax
0x18001a570  jz      short loc_18001A579
0x18001a572  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a577  jmp     short loc_18001A57C
0x18001a579  mov     rax, rdi
0x18001a57c  mov     [rbx+80h], rax
0x18001a583  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18001a58a  test    rax, rax
0x18001a58d  jz      short loc_18001A597
0x18001a58f  mov     rcx, rbx
0x18001a592  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a597  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001a59e  test    rax, rax
0x18001a5a1  jz      short loc_18001A5B9
0x18001a5a3  mov     r8d, 400h
0x18001a5a9  mov     rdx, [rsp+78h+arg_60]
0x18001a5b1  mov     rcx, rbx
0x18001a5b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a5b9  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001a5c0  test    rax, rax
0x18001a5c3  jz      short loc_18001A5CD
0x18001a5c5  mov     rcx, rbx
0x18001a5c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a5cd  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001a5d4  test    rax, rax
0x18001a5d7  jz      short loc_18001A5E7
0x18001a5d9  test    byte ptr [rbx+4], 2
0x18001a5dd  jnz     short loc_18001A5E7
0x18001a5df  mov     rcx, rbx
0x18001a5e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a5e7  cmp     [rbx+8], edi
0x18001a5ea  jl      short loc_18001A606
0x18001a5ec  cmp     r15d, 3
0x18001a5f0  jnz     loc_18001A6E2
0x18001a5f6  mov     ecx, 8000FFFFh; this
0x18001a5fb  mov     [rbx+8], ecx
0x18001a5fe  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001a603  mov     [rbx+0Ch], eax
0x18001a606  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18001a60d  jnz     short loc_18001A634
0x18001a60f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001a616  test    rax, rax
0x18001a619  jz      short loc_18001A624
0x18001a61b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a620  test    al, al
0x18001a622  jmp     short loc_18001A632
0x18001a624  call    cs:__imp_IsDebuggerPresent
0x18001a62b  nop     dword ptr [rax+rax+00h]
0x18001a630  test    eax, eax
0x18001a632  jz      short loc_18001A63A
0x18001a634  test    byte ptr [rbx+4], 2
0x18001a638  jz      short loc_18001A65E
0x18001a63a  mov     rax, cs:g_pfnResultLoggingCallback
0x18001a641  test    rax, rax
0x18001a644  jz      short loc_18001A6A8
0x18001a646  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001a64d  jnz     short loc_18001A6A8
0x18001a64f  xor     r8d, r8d
0x18001a652  xor     edx, edx
0x18001a654  mov     rcx, rbx
0x18001a657  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a65c  jmp     short loc_18001A6A8
0x18001a65e  mov     ebp, 800h
0x18001a663  mov     rax, cs:g_pfnResultLoggingCallback
0x18001a66a  test    rax, rax
0x18001a66d  jz      short loc_18001A686
0x18001a66f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001a676  jnz     short loc_18001A686
0x18001a678  mov     r8d, ebp
0x18001a67b  mov     rdx, rsi
0x18001a67e  mov     rcx, rbx
0x18001a681  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a686  cmp     [rsi], di
0x18001a689  jnz     short loc_18001A699
0x18001a68b  mov     r8, rbx; unsigned __int64
0x18001a68e  mov     rdx, rbp; unsigned __int16 *
0x18001a691  mov     rcx, rsi; this
0x18001a694  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18001a699  mov     rcx, rsi; lpOutputString
0x18001a69c  call    cs:__imp_OutputDebugStringW
0x18001a6a3  nop     dword ptr [rax+rax+00h]
0x18001a6a8  test    byte ptr [rbx+4], 4
0x18001a6ac  jnz     short loc_18001A6B7
0x18001a6ae  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18001a6b5  jz      short loc_18001A6C9
0x18001a6b7  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001a6be  test    rax, rax
0x18001a6c1  jz      short loc_18001A6C9
0x18001a6c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a6c8  nop
0x18001a6c9  mov     rbx, [rsp+78h+arg_10]
0x18001a6d1  add     rsp, 40h
0x18001a6d5  pop     r15
0x18001a6d7  pop     r14
0x18001a6d9  pop     r13
0x18001a6db  pop     r12
0x18001a6dd  pop     rdi
0x18001a6de  pop     rsi
0x18001a6df  pop     rbp
0x18001a6e0  retn
0x18001a6e2  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
