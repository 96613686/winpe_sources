# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000a438`
- end: `0x18000a731`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180006734`

## callees

- `0x180006170`
- `0x180009a34`
- `0x18000a228`
- `0x18000a438`
- `0x18000abf8`
- `0x18000ac20`
- `0x18000ac34`
- `0x18000ac50`
- `0x18000c4cc`
- `0x1800f8010`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x18000a6ec`
- `KERNEL32!OutputDebugStringW` at `0x18000a6ec`
- `KERNEL32!IsDebuggerPresent` at `0x18000a67a`
- `KERNEL32!IsDebuggerPresent` at `0x18000a67a`
- `KERNEL32!GetCurrentThreadId` at `0x18000a55b`
- `KERNEL32!GetCurrentThreadId` at `0x18000a55b`

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
    ModuleName = wil::details::g_pfnGetModuleName(v24);
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
      : (v27 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v24) == 0),
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
      wil::details::g_pfnDebugBreak(v24);
  }
}

```

## disassembly

```asm
0x18000a438  mov     [rsp+arg_10], rbx
0x18000a43d  mov     [rsp+arg_8], edx
0x18000a441  mov     [rsp+arg_0], rcx
0x18000a446  push    rbp
0x18000a447  push    rsi
0x18000a448  push    rdi
0x18000a449  push    r12
0x18000a44b  push    r13
0x18000a44d  push    r14
0x18000a44f  push    r15
0x18000a451  sub     rsp, 40h
0x18000a455  mov     r12, r9
0x18000a458  mov     r13, r8
0x18000a45b  mov     r10, rcx
0x18000a45e  xor     eax, eax
0x18000a460  mov     rsi, [rsp+78h+lpOutputString]
0x18000a468  mov     [rsi], ax
0x18000a46b  mov     rax, [rsp+78h+arg_60]
0x18000a473  mov     byte ptr [rax], 0
0x18000a476  mov     r14, [rsp+78h+arg_38]
0x18000a47e  mov     edi, [r14]
0x18000a481  mov     rbx, [rsp+78h+arg_78]
0x18000a489  mov     [rbx+8], edi
0x18000a48c  mov     eax, [r14+4]
0x18000a490  mov     [rbx+0Ch], eax
0x18000a493  xor     ebp, ebp
0x18000a495  mov     r15d, [rsp+78h+arg_30]
0x18000a49d  mov     ecx, r15d
0x18000a4a0  test    r15d, r15d
0x18000a4a3  jz      short loc_18000A50B
0x18000a4a5  sub     ecx, 1
0x18000a4a8  jz      short loc_18000A502
0x18000a4aa  sub     ecx, 1
0x18000a4ad  jz      short loc_18000A4BD
0x18000a4af  cmp     ecx, 1
0x18000a4b2  jnz     short loc_18000A514
0x18000a4b4  mov     ecx, edi; this
0x18000a4b6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000a4bb  jmp     short loc_18000A512
0x18000a4bd  test    edi, edi
0x18000a4bf  js      short loc_18000A4F9
0x18000a4c1  mov     edi, 8007029Ch
0x18000a4c6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000a4ca  mov     rax, [rsp+78h+arg_28]
0x18000a4d2  mov     [rsp+78h+var_50], rax; __int64
0x18000a4d7  mov     rax, [rsp+78h+arg_20]
0x18000a4df  mov     [rsp+78h+var_58], rax; __int64
0x18000a4e4  mov     rcx, r10; int
0x18000a4e7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000a4ec  mov     [rbx+8], edi
0x18000a4ef  mov     ecx, edi; this
0x18000a4f1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000a4f6  mov     [rbx+0Ch], eax
0x18000a4f9  mov     ecx, edi; this
0x18000a4fb  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000a500  jmp     short loc_18000A512
0x18000a502  mov     ecx, edi; this
0x18000a504  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000a509  jmp     short loc_18000A512
0x18000a50b  mov     ecx, edi; this
0x18000a50d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000a512  mov     ebp, eax
0x18000a514  mov     [rbx], r15d
0x18000a517  mov     eax, [rsp+78h+arg_70]
0x18000a51e  mov     [rbx+4], eax
0x18000a521  cmp     dword ptr [r14+8], 1
0x18000a526  jnz     short loc_18000A52E
0x18000a528  or      eax, 8
0x18000a52b  mov     [rbx+4], eax
0x18000a52e  mov     eax, 1
0x18000a533  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000a53b  inc     eax
0x18000a53d  mov     [rbx+10h], eax
0x18000a540  mov     rax, [rsp+78h+arg_40]
0x18000a548  xor     edi, edi
0x18000a54a  test    rax, rax
0x18000a54d  jz      short loc_18000A554
0x18000a54f  cmp     [rax], di
0x18000a552  jnz     short loc_18000A557
0x18000a554  mov     rax, rdi
0x18000a557  mov     [rbx+18h], rax
0x18000a55b  call    cs:__imp_GetCurrentThreadId
0x18000a561  mov     [rbx+20h], eax
0x18000a564  mov     [rbx+38h], r13
0x18000a568  mov     eax, [rsp+78h+arg_8]
0x18000a56f  mov     [rbx+40h], eax
0x18000a572  mov     [rbx+44h], ebp
0x18000a575  mov     rax, [rsp+78h+arg_20]
0x18000a57d  mov     [rbx+28h], rax
0x18000a581  mov     [rbx+30h], r12
0x18000a585  mov     rax, [rsp+78h+arg_28]
0x18000a58d  mov     [rbx+88h], rax
0x18000a594  mov     rax, [rsp+78h+arg_0]
0x18000a59c  mov     [rbx+90h], rax
0x18000a5a3  mov     [rbx+48h], rdi
0x18000a5a7  xorps   xmm0, xmm0
0x18000a5aa  xor     eax, eax
0x18000a5ac  movups  xmmword ptr [rbx+68h], xmm0
0x18000a5b0  mov     [rbx+78h], rax
0x18000a5b4  movups  xmmword ptr [rbx+50h], xmm0
0x18000a5b8  mov     [rbx+60h], rax
0x18000a5bc  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000a5c3  test    rax, rax
0x18000a5c6  jz      short loc_18000A5CF
0x18000a5c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5cd  jmp     short loc_18000A5D2
0x18000a5cf  mov     rax, rdi
0x18000a5d2  mov     [rbx+80h], rax
0x18000a5d9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000a5e0  test    rax, rax
0x18000a5e3  jz      short loc_18000A5ED
0x18000a5e5  mov     rcx, rbx
0x18000a5e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5ed  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000a5f4  test    rax, rax
0x18000a5f7  jz      short loc_18000A60F
0x18000a5f9  mov     r8d, 400h
0x18000a5ff  mov     rdx, [rsp+78h+arg_60]
0x18000a607  mov     rcx, rbx
0x18000a60a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a60f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a616  test    rax, rax
0x18000a619  jz      short loc_18000A623
0x18000a61b  mov     rcx, rbx
0x18000a61e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a623  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a62a  test    rax, rax
0x18000a62d  jz      short loc_18000A63D
0x18000a62f  test    byte ptr [rbx+4], 2
0x18000a633  jnz     short loc_18000A63D
0x18000a635  mov     rcx, rbx
0x18000a638  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a63d  cmp     [rbx+8], edi
0x18000a640  jl      short loc_18000A65C
0x18000a642  cmp     r15d, 3
0x18000a646  jnz     loc_18000A72B
0x18000a64c  mov     ecx, 8000FFFFh; this
0x18000a651  mov     [rbx+8], ecx
0x18000a654  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000a659  mov     [rbx+0Ch], eax
0x18000a65c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000a663  jnz     short loc_18000A684
0x18000a665  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000a66c  test    rax, rax
0x18000a66f  jz      short loc_18000A67A
0x18000a671  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a676  test    al, al
0x18000a678  jmp     short loc_18000A682
0x18000a67a  call    cs:__imp_IsDebuggerPresent
0x18000a680  test    eax, eax
0x18000a682  jz      short loc_18000A68A
0x18000a684  test    byte ptr [rbx+4], 2
0x18000a688  jz      short loc_18000A6AE
0x18000a68a  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a691  test    rax, rax
0x18000a694  jz      short loc_18000A6F2
0x18000a696  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000a69d  jnz     short loc_18000A6F2
0x18000a69f  xor     r8d, r8d
0x18000a6a2  xor     edx, edx
0x18000a6a4  mov     rcx, rbx
0x18000a6a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6ac  jmp     short loc_18000A6F2
0x18000a6ae  mov     ebp, 800h
0x18000a6b3  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a6ba  test    rax, rax
0x18000a6bd  jz      short loc_18000A6D6
0x18000a6bf  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000a6c6  jnz     short loc_18000A6D6
0x18000a6c8  mov     r8d, ebp
0x18000a6cb  mov     rdx, rsi
0x18000a6ce  mov     rcx, rbx
0x18000a6d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6d6  cmp     [rsi], di
0x18000a6d9  jnz     short loc_18000A6E9
0x18000a6db  mov     r8, rbx; unsigned __int64
0x18000a6de  mov     rdx, rbp; unsigned __int16 *
0x18000a6e1  mov     rcx, rsi; this
0x18000a6e4  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000a6e9  mov     rcx, rsi; lpOutputString
0x18000a6ec  call    cs:__imp_OutputDebugStringW
0x18000a6f2  test    byte ptr [rbx+4], 4
0x18000a6f6  jnz     short loc_18000A701
0x18000a6f8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000a6ff  jz      short loc_18000A713
0x18000a701  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000a708  test    rax, rax
0x18000a70b  jz      short loc_18000A713
0x18000a70d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a712  nop
0x18000a713  mov     rbx, [rsp+78h+arg_10]
0x18000a71b  add     rsp, 40h
0x18000a71f  pop     r15
0x18000a721  pop     r14
0x18000a723  pop     r13
0x18000a725  pop     r12
0x18000a727  pop     rdi
0x18000a728  pop     rsi
0x18000a729  pop     rbp
0x18000a72a  retn
0x18000a72b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
