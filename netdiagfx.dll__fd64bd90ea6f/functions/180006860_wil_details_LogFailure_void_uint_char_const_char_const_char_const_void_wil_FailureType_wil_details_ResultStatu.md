# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180006860`
- end: `0x180006b59`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1800054e4`
- `0x180005594`

## callees

- `0x180002bf4`
- `0x180002fac`
- `0x180003290`
- `0x180005424`
- `0x180006860`
- `0x180006d04`
- `0x180006d20`
- `0x180006d3c`
- `0x180007494`
- `0x18002f010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180006983`
- `KERNEL32!GetCurrentThreadId` at `0x180006983`
- `KERNEL32!OutputDebugStringW` at `0x180006b14`
- `KERNEL32!OutputDebugStringW` at `0x180006b14`
- `KERNEL32!IsDebuggerPresent` at `0x180006aa2`
- `KERNEL32!IsDebuggerPresent` at `0x180006aa2`

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
        WCHAR *lpOutputString,
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

  *lpOutputString = 0;
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
    if ( !*lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v25);
    OutputDebugStringW(lpOutputString);
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
0x180006860  mov     [rsp+arg_10], rbx
0x180006865  mov     [rsp+arg_8], edx
0x180006869  mov     [rsp+arg_0], rcx
0x18000686e  push    rbp
0x18000686f  push    rsi
0x180006870  push    rdi
0x180006871  push    r12
0x180006873  push    r13
0x180006875  push    r14
0x180006877  push    r15
0x180006879  sub     rsp, 40h
0x18000687d  mov     r12, r9
0x180006880  mov     r13, r8
0x180006883  mov     r10, rcx
0x180006886  xor     eax, eax
0x180006888  mov     rsi, [rsp+78h+lpOutputString]
0x180006890  mov     [rsi], ax
0x180006893  mov     rax, [rsp+78h+arg_60]
0x18000689b  mov     byte ptr [rax], 0
0x18000689e  mov     r14, [rsp+78h+arg_38]
0x1800068a6  mov     edi, [r14]
0x1800068a9  mov     rbx, [rsp+78h+arg_78]
0x1800068b1  mov     [rbx+8], edi
0x1800068b4  mov     eax, [r14+4]
0x1800068b8  mov     [rbx+0Ch], eax
0x1800068bb  xor     ebp, ebp
0x1800068bd  mov     r15d, [rsp+78h+arg_30]
0x1800068c5  mov     ecx, r15d
0x1800068c8  test    r15d, r15d
0x1800068cb  jz      short loc_180006933
0x1800068cd  sub     ecx, 1
0x1800068d0  jz      short loc_18000692A
0x1800068d2  sub     ecx, 1
0x1800068d5  jz      short loc_1800068E5
0x1800068d7  cmp     ecx, 1
0x1800068da  jnz     short loc_18000693C
0x1800068dc  mov     ecx, edi; this
0x1800068de  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800068e3  jmp     short loc_18000693A
0x1800068e5  test    edi, edi
0x1800068e7  js      short loc_180006921
0x1800068e9  mov     edi, 8007029Ch
0x1800068ee  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800068f2  mov     rax, [rsp+78h+arg_28]
0x1800068fa  mov     [rsp+78h+var_50], rax; __int64
0x1800068ff  mov     rax, [rsp+78h+arg_20]
0x180006907  mov     [rsp+78h+var_58], rax; __int64
0x18000690c  mov     rcx, r10; int
0x18000690f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180006914  mov     [rbx+8], edi
0x180006917  mov     ecx, edi; this
0x180006919  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000691e  mov     [rbx+0Ch], eax
0x180006921  mov     ecx, edi; this
0x180006923  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180006928  jmp     short loc_18000693A
0x18000692a  mov     ecx, edi; this
0x18000692c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180006931  jmp     short loc_18000693A
0x180006933  mov     ecx, edi; this
0x180006935  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000693a  mov     ebp, eax
0x18000693c  mov     [rbx], r15d
0x18000693f  mov     eax, [rsp+78h+arg_70]
0x180006946  mov     [rbx+4], eax
0x180006949  cmp     dword ptr [r14+8], 1
0x18000694e  jnz     short loc_180006956
0x180006950  or      eax, 8
0x180006953  mov     [rbx+4], eax
0x180006956  mov     eax, 1
0x18000695b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180006963  inc     eax
0x180006965  mov     [rbx+10h], eax
0x180006968  mov     rax, [rsp+78h+arg_40]
0x180006970  xor     edi, edi
0x180006972  test    rax, rax
0x180006975  jz      short loc_18000697C
0x180006977  cmp     [rax], di
0x18000697a  jnz     short loc_18000697F
0x18000697c  mov     rax, rdi
0x18000697f  mov     [rbx+18h], rax
0x180006983  call    cs:__imp_GetCurrentThreadId
0x180006989  mov     [rbx+20h], eax
0x18000698c  mov     [rbx+38h], r13
0x180006990  mov     eax, [rsp+78h+arg_8]
0x180006997  mov     [rbx+40h], eax
0x18000699a  mov     [rbx+44h], ebp
0x18000699d  mov     rax, [rsp+78h+arg_20]
0x1800069a5  mov     [rbx+28h], rax
0x1800069a9  mov     [rbx+30h], r12
0x1800069ad  mov     rax, [rsp+78h+arg_28]
0x1800069b5  mov     [rbx+88h], rax
0x1800069bc  mov     rax, [rsp+78h+arg_0]
0x1800069c4  mov     [rbx+90h], rax
0x1800069cb  mov     [rbx+48h], rdi
0x1800069cf  xorps   xmm0, xmm0
0x1800069d2  xor     eax, eax
0x1800069d4  movups  xmmword ptr [rbx+68h], xmm0
0x1800069d8  mov     [rbx+78h], rax
0x1800069dc  movups  xmmword ptr [rbx+50h], xmm0
0x1800069e0  mov     [rbx+60h], rax
0x1800069e4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800069eb  test    rax, rax
0x1800069ee  jz      short loc_1800069F7
0x1800069f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069f5  jmp     short loc_1800069FA
0x1800069f7  mov     rax, rdi
0x1800069fa  mov     [rbx+80h], rax
0x180006a01  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006a08  test    rax, rax
0x180006a0b  jz      short loc_180006A15
0x180006a0d  mov     rcx, rbx
0x180006a10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a15  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006a1c  test    rax, rax
0x180006a1f  jz      short loc_180006A37
0x180006a21  mov     r8d, 400h
0x180006a27  mov     rdx, [rsp+78h+arg_60]
0x180006a2f  mov     rcx, rbx
0x180006a32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a37  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006a3e  test    rax, rax
0x180006a41  jz      short loc_180006A4B
0x180006a43  mov     rcx, rbx
0x180006a46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a4b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006a52  test    rax, rax
0x180006a55  jz      short loc_180006A65
0x180006a57  test    byte ptr [rbx+4], 2
0x180006a5b  jnz     short loc_180006A65
0x180006a5d  mov     rcx, rbx
0x180006a60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a65  cmp     [rbx+8], edi
0x180006a68  jl      short loc_180006A84
0x180006a6a  cmp     r15d, 3
0x180006a6e  jnz     loc_180006B53
0x180006a74  mov     ecx, 8000FFFFh; this
0x180006a79  mov     [rbx+8], ecx
0x180006a7c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006a81  mov     [rbx+0Ch], eax
0x180006a84  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180006a8b  jnz     short loc_180006AAC
0x180006a8d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180006a94  test    rax, rax
0x180006a97  jz      short loc_180006AA2
0x180006a99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a9e  test    al, al
0x180006aa0  jmp     short loc_180006AAA
0x180006aa2  call    cs:__imp_IsDebuggerPresent
0x180006aa8  test    eax, eax
0x180006aaa  jz      short loc_180006AB2
0x180006aac  test    byte ptr [rbx+4], 2
0x180006ab0  jz      short loc_180006AD6
0x180006ab2  mov     rax, cs:g_pfnResultLoggingCallback
0x180006ab9  test    rax, rax
0x180006abc  jz      short loc_180006B1A
0x180006abe  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006ac5  jnz     short loc_180006B1A
0x180006ac7  xor     r8d, r8d
0x180006aca  xor     edx, edx
0x180006acc  mov     rcx, rbx
0x180006acf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ad4  jmp     short loc_180006B1A
0x180006ad6  mov     ebp, 800h
0x180006adb  mov     rax, cs:g_pfnResultLoggingCallback
0x180006ae2  test    rax, rax
0x180006ae5  jz      short loc_180006AFE
0x180006ae7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006aee  jnz     short loc_180006AFE
0x180006af0  mov     r8d, ebp
0x180006af3  mov     rdx, rsi
0x180006af6  mov     rcx, rbx
0x180006af9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006afe  cmp     [rsi], di
0x180006b01  jnz     short loc_180006B11
0x180006b03  mov     r8, rbx; unsigned __int64
0x180006b06  mov     rdx, rbp; unsigned __int16 *
0x180006b09  mov     rcx, rsi; pszDest
0x180006b0c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180006b11  mov     rcx, rsi; lpOutputString
0x180006b14  call    cs:__imp_OutputDebugStringW
0x180006b1a  test    byte ptr [rbx+4], 4
0x180006b1e  jnz     short loc_180006B29
0x180006b20  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180006b27  jz      short loc_180006B3B
0x180006b29  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006b30  test    rax, rax
0x180006b33  jz      short loc_180006B3B
0x180006b35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b3a  nop
0x180006b3b  mov     rbx, [rsp+78h+arg_10]
0x180006b43  add     rsp, 40h
0x180006b47  pop     r15
0x180006b49  pop     r14
0x180006b4b  pop     r13
0x180006b4d  pop     r12
0x180006b4f  pop     rdi
0x180006b50  pop     rsi
0x180006b51  pop     rbp
0x180006b52  retn
0x180006b53  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
