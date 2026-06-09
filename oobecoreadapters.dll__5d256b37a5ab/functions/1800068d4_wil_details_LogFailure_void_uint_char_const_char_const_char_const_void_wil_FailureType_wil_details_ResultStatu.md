# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800068d4`
- end: `0x180006bd1`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `765`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x18000495c`
- `0x180004cc8`
- `0x18000cb00`

## callees

- `0x180004894`
- `0x180005e04`
- `0x180006640`
- `0x1800068d4`
- `0x1800070b4`
- `0x1800070d0`
- `0x1800070e4`
- `0x180007100`
- `0x1800083e8`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800069fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800069fb`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006b1a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006b1a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006b8c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006b8c`

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
0x1800068d4  mov     [rsp+arg_10], rbx
0x1800068d9  mov     [rsp+arg_8], edx
0x1800068dd  mov     [rsp+arg_0], rcx
0x1800068e2  push    rbp
0x1800068e3  push    rsi
0x1800068e4  push    rdi
0x1800068e5  push    r12
0x1800068e7  push    r13
0x1800068e9  push    r14
0x1800068eb  push    r15
0x1800068ed  sub     rsp, 40h
0x1800068f1  mov     r12, r9
0x1800068f4  mov     r13, r8
0x1800068f7  mov     r10, rcx
0x1800068fa  xor     eax, eax
0x1800068fc  mov     rsi, [rsp+78h+lpOutputString]
0x180006904  mov     [rsi], ax
0x180006907  mov     rax, [rsp+78h+arg_60]
0x18000690f  mov     byte ptr [rax], 0
0x180006912  mov     r14, [rsp+78h+arg_38]
0x18000691a  mov     edi, [r14]
0x18000691d  mov     rbx, [rsp+78h+arg_78]
0x180006925  mov     [rbx+8], edi
0x180006928  mov     eax, [r14+4]
0x18000692c  mov     [rbx+0Ch], eax
0x18000692f  xor     ebp, ebp
0x180006931  mov     r15d, [rsp+78h+arg_30]
0x180006939  mov     ecx, r15d
0x18000693c  test    r15d, r15d
0x18000693f  jz      short loc_1800069AB
0x180006941  sub     ecx, 1
0x180006944  jz      short loc_1800069A2
0x180006946  sub     ecx, 1
0x180006949  jz      short loc_180006959
0x18000694b  cmp     ecx, 1
0x18000694e  jnz     short loc_1800069B4
0x180006950  mov     ecx, edi; this
0x180006952  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180006957  jmp     short loc_1800069B2
0x180006959  test    edi, edi
0x18000695b  js      short loc_180006999
0x18000695d  mov     [rsp+78h+var_40], ebp
0x180006961  mov     edi, 8007029Ch
0x180006966  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000696a  mov     rax, [rsp+78h+arg_28]
0x180006972  mov     [rsp+78h+var_50], rax; __int64
0x180006977  mov     rax, [rsp+78h+arg_20]
0x18000697f  mov     [rsp+78h+var_58], rax; __int64
0x180006984  mov     rcx, r10; int
0x180006987  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000698c  mov     [rbx+8], edi
0x18000698f  mov     ecx, edi; this
0x180006991  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006996  mov     [rbx+0Ch], eax
0x180006999  mov     ecx, edi; this
0x18000699b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800069a0  jmp     short loc_1800069B2
0x1800069a2  mov     ecx, edi; this
0x1800069a4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800069a9  jmp     short loc_1800069B2
0x1800069ab  mov     ecx, edi; this
0x1800069ad  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800069b2  mov     ebp, eax
0x1800069b4  mov     [rbx], r15d
0x1800069b7  mov     eax, [rsp+78h+arg_70]
0x1800069be  mov     [rbx+4], eax
0x1800069c1  cmp     dword ptr [r14+8], 1
0x1800069c6  jnz     short loc_1800069CE
0x1800069c8  or      eax, 8
0x1800069cb  mov     [rbx+4], eax
0x1800069ce  mov     eax, 1
0x1800069d3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800069db  inc     eax
0x1800069dd  mov     [rbx+10h], eax
0x1800069e0  mov     rax, [rsp+78h+arg_40]
0x1800069e8  xor     edi, edi
0x1800069ea  test    rax, rax
0x1800069ed  jz      short loc_1800069F4
0x1800069ef  cmp     [rax], di
0x1800069f2  jnz     short loc_1800069F7
0x1800069f4  mov     rax, rdi
0x1800069f7  mov     [rbx+18h], rax
0x1800069fb  call    cs:__imp_GetCurrentThreadId
0x180006a01  mov     [rbx+20h], eax
0x180006a04  mov     [rbx+38h], r13
0x180006a08  mov     eax, [rsp+78h+arg_8]
0x180006a0f  mov     [rbx+40h], eax
0x180006a12  mov     [rbx+44h], ebp
0x180006a15  mov     rax, [rsp+78h+arg_20]
0x180006a1d  mov     [rbx+28h], rax
0x180006a21  mov     [rbx+30h], r12
0x180006a25  mov     rax, [rsp+78h+arg_28]
0x180006a2d  mov     [rbx+88h], rax
0x180006a34  mov     rax, [rsp+78h+arg_0]
0x180006a3c  mov     [rbx+90h], rax
0x180006a43  mov     [rbx+48h], rdi
0x180006a47  xorps   xmm0, xmm0
0x180006a4a  xor     eax, eax
0x180006a4c  movups  xmmword ptr [rbx+68h], xmm0
0x180006a50  mov     [rbx+78h], rax
0x180006a54  movups  xmmword ptr [rbx+50h], xmm0
0x180006a58  mov     [rbx+60h], rax
0x180006a5c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180006a63  test    rax, rax
0x180006a66  jz      short loc_180006A6F
0x180006a68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a6d  jmp     short loc_180006A72
0x180006a6f  mov     rax, rdi
0x180006a72  mov     [rbx+80h], rax
0x180006a79  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006a80  test    rax, rax
0x180006a83  jz      short loc_180006A8D
0x180006a85  mov     rcx, rbx
0x180006a88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a8d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006a94  test    rax, rax
0x180006a97  jz      short loc_180006AAF
0x180006a99  mov     r8d, 400h
0x180006a9f  mov     rdx, [rsp+78h+arg_60]
0x180006aa7  mov     rcx, rbx
0x180006aaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006aaf  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006ab6  test    rax, rax
0x180006ab9  jz      short loc_180006AC3
0x180006abb  mov     rcx, rbx
0x180006abe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ac3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006aca  test    rax, rax
0x180006acd  jz      short loc_180006ADD
0x180006acf  test    byte ptr [rbx+4], 2
0x180006ad3  jnz     short loc_180006ADD
0x180006ad5  mov     rcx, rbx
0x180006ad8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006add  cmp     [rbx+8], edi
0x180006ae0  jl      short loc_180006AFC
0x180006ae2  cmp     r15d, 3
0x180006ae6  jnz     loc_180006BCB
0x180006aec  mov     ecx, 8000FFFFh; this
0x180006af1  mov     [rbx+8], ecx
0x180006af4  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006af9  mov     [rbx+0Ch], eax
0x180006afc  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180006b03  jnz     short loc_180006B24
0x180006b05  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180006b0c  test    rax, rax
0x180006b0f  jz      short loc_180006B1A
0x180006b11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b16  test    al, al
0x180006b18  jmp     short loc_180006B22
0x180006b1a  call    cs:__imp_IsDebuggerPresent
0x180006b20  test    eax, eax
0x180006b22  jz      short loc_180006B2A
0x180006b24  test    byte ptr [rbx+4], 2
0x180006b28  jz      short loc_180006B4E
0x180006b2a  mov     rax, cs:g_pfnResultLoggingCallback
0x180006b31  test    rax, rax
0x180006b34  jz      short loc_180006B92
0x180006b36  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006b3d  jnz     short loc_180006B92
0x180006b3f  xor     r8d, r8d
0x180006b42  xor     edx, edx
0x180006b44  mov     rcx, rbx
0x180006b47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b4c  jmp     short loc_180006B92
0x180006b4e  mov     ebp, 800h
0x180006b53  mov     rax, cs:g_pfnResultLoggingCallback
0x180006b5a  test    rax, rax
0x180006b5d  jz      short loc_180006B76
0x180006b5f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006b66  jnz     short loc_180006B76
0x180006b68  mov     r8d, ebp
0x180006b6b  mov     rdx, rsi
0x180006b6e  mov     rcx, rbx
0x180006b71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b76  cmp     [rsi], di
0x180006b79  jnz     short loc_180006B89
0x180006b7b  mov     r8, rbx; unsigned __int64
0x180006b7e  mov     rdx, rbp; unsigned __int16 *
0x180006b81  mov     rcx, rsi; this
0x180006b84  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180006b89  mov     rcx, rsi; lpOutputString
0x180006b8c  call    cs:__imp_OutputDebugStringW
0x180006b92  test    byte ptr [rbx+4], 4
0x180006b96  jnz     short loc_180006BA1
0x180006b98  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180006b9f  jz      short loc_180006BB3
0x180006ba1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006ba8  test    rax, rax
0x180006bab  jz      short loc_180006BB3
0x180006bad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bb2  nop
0x180006bb3  mov     rbx, [rsp+78h+arg_10]
0x180006bbb  add     rsp, 40h
0x180006bbf  pop     r15
0x180006bc1  pop     r14
0x180006bc3  pop     r13
0x180006bc5  pop     r12
0x180006bc7  pop     rdi
0x180006bc8  pop     rsi
0x180006bc9  pop     rbp
0x180006bca  retn
0x180006bcb  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
