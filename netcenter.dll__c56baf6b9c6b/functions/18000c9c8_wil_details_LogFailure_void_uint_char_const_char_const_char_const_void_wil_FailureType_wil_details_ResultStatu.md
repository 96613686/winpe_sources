# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000c9c8`
- end: `0x18000ccc1`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180007050`
- `0x180007398`

## callees

- `0x180006f98`
- `0x18000a91c`
- `0x18000bb14`
- `0x18000c9c8`
- `0x18000f7f0`
- `0x18000f810`
- `0x18000f824`
- `0x18000f840`
- `0x180013904`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000caeb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000caeb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000cc7c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000cc7c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000cc0a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000cc0a`

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
0x18000c9c8  mov     [rsp+arg_10], rbx
0x18000c9cd  mov     [rsp+arg_8], edx
0x18000c9d1  mov     [rsp+arg_0], rcx
0x18000c9d6  push    rbp
0x18000c9d7  push    rsi
0x18000c9d8  push    rdi
0x18000c9d9  push    r12
0x18000c9db  push    r13
0x18000c9dd  push    r14
0x18000c9df  push    r15
0x18000c9e1  sub     rsp, 40h
0x18000c9e5  mov     r12, r9
0x18000c9e8  mov     r13, r8
0x18000c9eb  mov     r10, rcx
0x18000c9ee  xor     eax, eax
0x18000c9f0  mov     rsi, [rsp+78h+lpOutputString]
0x18000c9f8  mov     [rsi], ax
0x18000c9fb  mov     rax, [rsp+78h+arg_60]
0x18000ca03  mov     byte ptr [rax], 0
0x18000ca06  mov     r14, [rsp+78h+arg_38]
0x18000ca0e  mov     edi, [r14]
0x18000ca11  mov     rbx, [rsp+78h+arg_78]
0x18000ca19  mov     [rbx+8], edi
0x18000ca1c  mov     eax, [r14+4]
0x18000ca20  mov     [rbx+0Ch], eax
0x18000ca23  xor     ebp, ebp
0x18000ca25  mov     r15d, [rsp+78h+arg_30]
0x18000ca2d  mov     ecx, r15d
0x18000ca30  test    r15d, r15d
0x18000ca33  jz      short loc_18000CA9B
0x18000ca35  sub     ecx, 1
0x18000ca38  jz      short loc_18000CA92
0x18000ca3a  sub     ecx, 1
0x18000ca3d  jz      short loc_18000CA4D
0x18000ca3f  cmp     ecx, 1
0x18000ca42  jnz     short loc_18000CAA4
0x18000ca44  mov     ecx, edi; this
0x18000ca46  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000ca4b  jmp     short loc_18000CAA2
0x18000ca4d  test    edi, edi
0x18000ca4f  js      short loc_18000CA89
0x18000ca51  mov     edi, 8007029Ch
0x18000ca56  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000ca5a  mov     rax, [rsp+78h+arg_28]
0x18000ca62  mov     [rsp+78h+var_50], rax; __int64
0x18000ca67  mov     rax, [rsp+78h+arg_20]
0x18000ca6f  mov     [rsp+78h+var_58], rax; __int64
0x18000ca74  mov     rcx, r10; int
0x18000ca77  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000ca7c  mov     [rbx+8], edi
0x18000ca7f  mov     ecx, edi; this
0x18000ca81  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000ca86  mov     [rbx+0Ch], eax
0x18000ca89  mov     ecx, edi; this
0x18000ca8b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000ca90  jmp     short loc_18000CAA2
0x18000ca92  mov     ecx, edi; this
0x18000ca94  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000ca99  jmp     short loc_18000CAA2
0x18000ca9b  mov     ecx, edi; this
0x18000ca9d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000caa2  mov     ebp, eax
0x18000caa4  mov     [rbx], r15d
0x18000caa7  mov     eax, [rsp+78h+arg_70]
0x18000caae  mov     [rbx+4], eax
0x18000cab1  cmp     dword ptr [r14+8], 1
0x18000cab6  jnz     short loc_18000CABE
0x18000cab8  or      eax, 8
0x18000cabb  mov     [rbx+4], eax
0x18000cabe  mov     eax, 1
0x18000cac3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000cacb  inc     eax
0x18000cacd  mov     [rbx+10h], eax
0x18000cad0  mov     rax, [rsp+78h+arg_40]
0x18000cad8  xor     edi, edi
0x18000cada  test    rax, rax
0x18000cadd  jz      short loc_18000CAE4
0x18000cadf  cmp     [rax], di
0x18000cae2  jnz     short loc_18000CAE7
0x18000cae4  mov     rax, rdi
0x18000cae7  mov     [rbx+18h], rax
0x18000caeb  call    cs:__imp_GetCurrentThreadId
0x18000caf1  mov     [rbx+20h], eax
0x18000caf4  mov     [rbx+38h], r13
0x18000caf8  mov     eax, [rsp+78h+arg_8]
0x18000caff  mov     [rbx+40h], eax
0x18000cb02  mov     [rbx+44h], ebp
0x18000cb05  mov     rax, [rsp+78h+arg_20]
0x18000cb0d  mov     [rbx+28h], rax
0x18000cb11  mov     [rbx+30h], r12
0x18000cb15  mov     rax, [rsp+78h+arg_28]
0x18000cb1d  mov     [rbx+88h], rax
0x18000cb24  mov     rax, [rsp+78h+arg_0]
0x18000cb2c  mov     [rbx+90h], rax
0x18000cb33  mov     [rbx+48h], rdi
0x18000cb37  xorps   xmm0, xmm0
0x18000cb3a  xor     eax, eax
0x18000cb3c  movups  xmmword ptr [rbx+68h], xmm0
0x18000cb40  mov     [rbx+78h], rax
0x18000cb44  movups  xmmword ptr [rbx+50h], xmm0
0x18000cb48  mov     [rbx+60h], rax
0x18000cb4c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000cb53  test    rax, rax
0x18000cb56  jz      short loc_18000CB5F
0x18000cb58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb5d  jmp     short loc_18000CB62
0x18000cb5f  mov     rax, rdi
0x18000cb62  mov     [rbx+80h], rax
0x18000cb69  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000cb70  test    rax, rax
0x18000cb73  jz      short loc_18000CB7D
0x18000cb75  mov     rcx, rbx
0x18000cb78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb7d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000cb84  test    rax, rax
0x18000cb87  jz      short loc_18000CB9F
0x18000cb89  mov     r8d, 400h
0x18000cb8f  mov     rdx, [rsp+78h+arg_60]
0x18000cb97  mov     rcx, rbx
0x18000cb9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb9f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000cba6  test    rax, rax
0x18000cba9  jz      short loc_18000CBB3
0x18000cbab  mov     rcx, rbx
0x18000cbae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbb3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000cbba  test    rax, rax
0x18000cbbd  jz      short loc_18000CBCD
0x18000cbbf  test    byte ptr [rbx+4], 2
0x18000cbc3  jnz     short loc_18000CBCD
0x18000cbc5  mov     rcx, rbx
0x18000cbc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbcd  cmp     [rbx+8], edi
0x18000cbd0  jl      short loc_18000CBEC
0x18000cbd2  cmp     r15d, 3
0x18000cbd6  jnz     loc_18000CCBB
0x18000cbdc  mov     ecx, 8000FFFFh; this
0x18000cbe1  mov     [rbx+8], ecx
0x18000cbe4  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000cbe9  mov     [rbx+0Ch], eax
0x18000cbec  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000cbf3  jnz     short loc_18000CC14
0x18000cbf5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000cbfc  test    rax, rax
0x18000cbff  jz      short loc_18000CC0A
0x18000cc01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc06  test    al, al
0x18000cc08  jmp     short loc_18000CC12
0x18000cc0a  call    cs:__imp_IsDebuggerPresent
0x18000cc10  test    eax, eax
0x18000cc12  jz      short loc_18000CC1A
0x18000cc14  test    byte ptr [rbx+4], 2
0x18000cc18  jz      short loc_18000CC3E
0x18000cc1a  mov     rax, cs:g_pfnResultLoggingCallback
0x18000cc21  test    rax, rax
0x18000cc24  jz      short loc_18000CC82
0x18000cc26  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000cc2d  jnz     short loc_18000CC82
0x18000cc2f  xor     r8d, r8d
0x18000cc32  xor     edx, edx
0x18000cc34  mov     rcx, rbx
0x18000cc37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc3c  jmp     short loc_18000CC82
0x18000cc3e  mov     ebp, 800h
0x18000cc43  mov     rax, cs:g_pfnResultLoggingCallback
0x18000cc4a  test    rax, rax
0x18000cc4d  jz      short loc_18000CC66
0x18000cc4f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000cc56  jnz     short loc_18000CC66
0x18000cc58  mov     r8d, ebp
0x18000cc5b  mov     rdx, rsi
0x18000cc5e  mov     rcx, rbx
0x18000cc61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc66  cmp     [rsi], di
0x18000cc69  jnz     short loc_18000CC79
0x18000cc6b  mov     r8, rbx; unsigned __int64
0x18000cc6e  mov     rdx, rbp; unsigned __int16 *
0x18000cc71  mov     rcx, rsi; this
0x18000cc74  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000cc79  mov     rcx, rsi; lpOutputString
0x18000cc7c  call    cs:__imp_OutputDebugStringW
0x18000cc82  test    byte ptr [rbx+4], 4
0x18000cc86  jnz     short loc_18000CC91
0x18000cc88  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000cc8f  jz      short loc_18000CCA3
0x18000cc91  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000cc98  test    rax, rax
0x18000cc9b  jz      short loc_18000CCA3
0x18000cc9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cca2  nop
0x18000cca3  mov     rbx, [rsp+78h+arg_10]
0x18000ccab  add     rsp, 40h
0x18000ccaf  pop     r15
0x18000ccb1  pop     r14
0x18000ccb3  pop     r13
0x18000ccb5  pop     r12
0x18000ccb7  pop     rdi
0x18000ccb8  pop     rsi
0x18000ccb9  pop     rbp
0x18000ccba  retn
0x18000ccbb  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
