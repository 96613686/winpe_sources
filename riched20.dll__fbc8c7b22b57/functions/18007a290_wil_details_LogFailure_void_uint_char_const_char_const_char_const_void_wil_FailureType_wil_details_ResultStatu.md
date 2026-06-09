# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18007a290`
- end: `0x18007a59b`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `779`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180077954`

## callees

- `0x18007736c`
- `0x180079424`
- `0x180079d70`
- `0x18007a290`
- `0x18007b524`
- `0x18007b550`
- `0x18007b6ec`
- `0x18007b70c`
- `0x18007d230`
- `0x180095010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18007a3b3`
- `KERNEL32!GetCurrentThreadId` at `0x18007a3b3`
- `KERNEL32!IsDebuggerPresent` at `0x18007a4d8`
- `KERNEL32!IsDebuggerPresent` at `0x18007a4d8`
- `KERNEL32!OutputDebugStringW` at `0x18007a550`
- `KERNEL32!OutputDebugStringW` at `0x18007a550`

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
0x18007a290  mov     [rsp+arg_10], rbx
0x18007a295  mov     [rsp+arg_8], edx
0x18007a299  mov     [rsp+arg_0], rcx
0x18007a29e  push    rbp
0x18007a29f  push    rsi
0x18007a2a0  push    rdi
0x18007a2a1  push    r12
0x18007a2a3  push    r13
0x18007a2a5  push    r14
0x18007a2a7  push    r15
0x18007a2a9  sub     rsp, 40h
0x18007a2ad  mov     r14, [rsp+78h+arg_38]
0x18007a2b5  xor     eax, eax
0x18007a2b7  mov     rbx, [rsp+78h+arg_78]
0x18007a2bf  xor     ebp, ebp
0x18007a2c1  mov     r15d, [rsp+78h+arg_30]
0x18007a2c9  mov     r10, rcx
0x18007a2cc  mov     rsi, [rsp+78h+lpOutputString]
0x18007a2d4  mov     r12, r9
0x18007a2d7  mov     r13, r8
0x18007a2da  mov     ecx, r15d
0x18007a2dd  mov     [rsi], ax
0x18007a2e0  mov     rax, [rsp+78h+arg_60]
0x18007a2e8  mov     byte ptr [rax], 0
0x18007a2eb  mov     edi, [r14]
0x18007a2ee  mov     [rbx+8], edi
0x18007a2f1  mov     eax, [r14+4]
0x18007a2f5  mov     [rbx+0Ch], eax
0x18007a2f8  test    r15d, r15d
0x18007a2fb  jz      short loc_18007A363
0x18007a2fd  sub     ecx, 1
0x18007a300  jz      short loc_18007A35A
0x18007a302  sub     ecx, 1
0x18007a305  jz      short loc_18007A315
0x18007a307  cmp     ecx, 1
0x18007a30a  jnz     short loc_18007A36C
0x18007a30c  mov     ecx, edi; this
0x18007a30e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18007a313  jmp     short loc_18007A36A
0x18007a315  test    edi, edi
0x18007a317  js      short loc_18007A351
0x18007a319  mov     rax, [rsp+78h+arg_28]
0x18007a321  mov     edi, 8007029Ch
0x18007a326  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18007a32a  mov     rcx, r10; int
0x18007a32d  mov     [rsp+78h+var_50], rax; __int64
0x18007a332  mov     rax, [rsp+78h+arg_20]
0x18007a33a  mov     [rsp+78h+var_58], rax; __int64
0x18007a33f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18007a344  mov     ecx, edi; this
0x18007a346  mov     [rbx+8], edi
0x18007a349  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18007a34e  mov     [rbx+0Ch], eax
0x18007a351  mov     ecx, edi; this
0x18007a353  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18007a358  jmp     short loc_18007A36A
0x18007a35a  mov     ecx, edi; this
0x18007a35c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18007a361  jmp     short loc_18007A36A
0x18007a363  mov     ecx, edi; this
0x18007a365  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18007a36a  mov     ebp, eax
0x18007a36c  mov     eax, [rsp+78h+arg_70]
0x18007a373  mov     [rbx+4], eax
0x18007a376  mov     [rbx], r15d
0x18007a379  cmp     dword ptr [r14+8], 1
0x18007a37e  jnz     short loc_18007A386
0x18007a380  or      eax, 8
0x18007a383  mov     [rbx+4], eax
0x18007a386  mov     eax, 1
0x18007a38b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18007a393  inc     eax
0x18007a395  xor     edi, edi
0x18007a397  mov     [rbx+10h], eax
0x18007a39a  mov     rax, [rsp+78h+arg_40]
0x18007a3a2  test    rax, rax
0x18007a3a5  jz      short loc_18007A3AC
0x18007a3a7  cmp     [rax], di
0x18007a3aa  jnz     short loc_18007A3AF
0x18007a3ac  mov     rax, rdi
0x18007a3af  mov     [rbx+18h], rax
0x18007a3b3  call    cs:__imp_GetCurrentThreadId
0x18007a3ba  nop     dword ptr [rax+rax+00h]
0x18007a3bf  mov     [rbx+38h], r13
0x18007a3c3  xorps   xmm0, xmm0
0x18007a3c6  mov     [rbx+20h], eax
0x18007a3c9  mov     eax, [rsp+78h+arg_8]
0x18007a3d0  mov     [rbx+40h], eax
0x18007a3d3  mov     rax, [rsp+78h+arg_20]
0x18007a3db  mov     [rbx+28h], rax
0x18007a3df  mov     rax, [rsp+78h+arg_28]
0x18007a3e7  mov     [rbx+88h], rax
0x18007a3ee  mov     rax, [rsp+78h+arg_0]
0x18007a3f6  mov     [rbx+90h], rax
0x18007a3fd  xor     eax, eax
0x18007a3ff  mov     [rbx+44h], ebp
0x18007a402  mov     [rbx+30h], r12
0x18007a406  mov     [rbx+48h], rdi
0x18007a40a  movups  xmmword ptr [rbx+68h], xmm0
0x18007a40e  mov     [rbx+78h], rax
0x18007a412  movups  xmmword ptr [rbx+50h], xmm0
0x18007a416  mov     [rbx+60h], rax
0x18007a41a  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18007a421  test    rax, rax
0x18007a424  jz      short loc_18007A42D
0x18007a426  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a42b  jmp     short loc_18007A430
0x18007a42d  mov     rax, rdi
0x18007a430  mov     [rbx+80h], rax
0x18007a437  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18007a43e  test    rax, rax
0x18007a441  jz      short loc_18007A44B
0x18007a443  mov     rcx, rbx
0x18007a446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a44b  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18007a452  test    rax, rax
0x18007a455  jz      short loc_18007A46D
0x18007a457  mov     rdx, [rsp+78h+arg_60]
0x18007a45f  mov     r8d, 400h
0x18007a465  mov     rcx, rbx
0x18007a468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a46d  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18007a474  test    rax, rax
0x18007a477  jz      short loc_18007A481
0x18007a479  mov     rcx, rbx
0x18007a47c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a481  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18007a488  test    rax, rax
0x18007a48b  jz      short loc_18007A49B
0x18007a48d  test    byte ptr [rbx+4], 2
0x18007a491  jnz     short loc_18007A49B
0x18007a493  mov     rcx, rbx
0x18007a496  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a49b  cmp     [rbx+8], edi
0x18007a49e  jl      short loc_18007A4BA
0x18007a4a0  cmp     r15d, 3
0x18007a4a4  jnz     loc_18007A595
0x18007a4aa  mov     ecx, 8000FFFFh; this
0x18007a4af  mov     [rbx+8], ecx
0x18007a4b2  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18007a4b7  mov     [rbx+0Ch], eax
0x18007a4ba  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18007a4c1  jnz     short loc_18007A4E8
0x18007a4c3  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18007a4ca  test    rax, rax
0x18007a4cd  jz      short loc_18007A4D8
0x18007a4cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a4d4  test    al, al
0x18007a4d6  jmp     short loc_18007A4E6
0x18007a4d8  call    cs:__imp_IsDebuggerPresent
0x18007a4df  nop     dword ptr [rax+rax+00h]
0x18007a4e4  test    eax, eax
0x18007a4e6  jz      short loc_18007A4EE
0x18007a4e8  test    byte ptr [rbx+4], 2
0x18007a4ec  jz      short loc_18007A512
0x18007a4ee  mov     rax, cs:g_pfnResultLoggingCallback
0x18007a4f5  test    rax, rax
0x18007a4f8  jz      short loc_18007A55C
0x18007a4fa  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18007a501  jnz     short loc_18007A55C
0x18007a503  xor     r8d, r8d
0x18007a506  xor     edx, edx
0x18007a508  mov     rcx, rbx
0x18007a50b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a510  jmp     short loc_18007A55C
0x18007a512  mov     rax, cs:g_pfnResultLoggingCallback
0x18007a519  mov     ebp, 800h
0x18007a51e  test    rax, rax
0x18007a521  jz      short loc_18007A53A
0x18007a523  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18007a52a  jnz     short loc_18007A53A
0x18007a52c  mov     r8d, ebp
0x18007a52f  mov     rdx, rsi
0x18007a532  mov     rcx, rbx
0x18007a535  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a53a  cmp     [rsi], di
0x18007a53d  jnz     short loc_18007A54D
0x18007a53f  mov     r8, rbx; unsigned __int64
0x18007a542  mov     rdx, rbp; unsigned __int16 *
0x18007a545  mov     rcx, rsi; this
0x18007a548  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18007a54d  mov     rcx, rsi; lpOutputString
0x18007a550  call    cs:__imp_OutputDebugStringW
0x18007a557  nop     dword ptr [rax+rax+00h]
0x18007a55c  test    byte ptr [rbx+4], 4
0x18007a560  jnz     short loc_18007A56B
0x18007a562  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18007a569  jz      short loc_18007A57C
0x18007a56b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18007a572  test    rax, rax
0x18007a575  jz      short loc_18007A57C
0x18007a577  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a57c  mov     rbx, [rsp+78h+arg_10]
0x18007a584  add     rsp, 40h
0x18007a588  pop     r15
0x18007a58a  pop     r14
0x18007a58c  pop     r13
0x18007a58e  pop     r12
0x18007a590  pop     rdi
0x18007a591  pop     rsi
0x18007a592  pop     rbp
0x18007a593  retn
0x18007a595  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
