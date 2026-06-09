# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1400059c0`
- end: `0x140005ccc`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `780`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140003098`

## callees

- `0x140002aac`
- `0x140004f04`
- `0x140005710`
- `0x1400059c0`
- `0x140006728`
- `0x140006750`
- `0x140006898`
- `0x1400068b8`
- `0x140009030`
- `0x14004d010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x140005c08`
- `KERNEL32!IsDebuggerPresent` at `0x140005c08`
- `KERNEL32!OutputDebugStringW` at `0x140005c80`
- `KERNEL32!OutputDebugStringW` at `0x140005c80`
- `KERNEL32!GetCurrentThreadId` at `0x140005ae3`
- `KERNEL32!GetCurrentThreadId` at `0x140005ae3`

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
0x1400059c0  mov     [rsp+arg_10], rbx
0x1400059c5  mov     [rsp+arg_8], edx
0x1400059c9  mov     [rsp+arg_0], rcx
0x1400059ce  push    rbp
0x1400059cf  push    rsi
0x1400059d0  push    rdi
0x1400059d1  push    r12
0x1400059d3  push    r13
0x1400059d5  push    r14
0x1400059d7  push    r15
0x1400059d9  sub     rsp, 40h
0x1400059dd  mov     r12, r9
0x1400059e0  mov     r13, r8
0x1400059e3  mov     r10, rcx
0x1400059e6  xor     eax, eax
0x1400059e8  mov     rsi, [rsp+78h+lpOutputString]
0x1400059f0  mov     [rsi], ax
0x1400059f3  mov     rax, [rsp+78h+arg_60]
0x1400059fb  mov     byte ptr [rax], 0
0x1400059fe  mov     r14, [rsp+78h+arg_38]
0x140005a06  mov     edi, [r14]
0x140005a09  mov     rbx, [rsp+78h+arg_78]
0x140005a11  mov     [rbx+8], edi
0x140005a14  mov     eax, [r14+4]
0x140005a18  mov     [rbx+0Ch], eax
0x140005a1b  xor     ebp, ebp
0x140005a1d  mov     r15d, [rsp+78h+arg_30]
0x140005a25  mov     ecx, r15d
0x140005a28  test    r15d, r15d
0x140005a2b  jz      short loc_140005A93
0x140005a2d  sub     ecx, 1
0x140005a30  jz      short loc_140005A8A
0x140005a32  sub     ecx, 1
0x140005a35  jz      short loc_140005A45
0x140005a37  cmp     ecx, 1
0x140005a3a  jnz     short loc_140005A9C
0x140005a3c  mov     ecx, edi; this
0x140005a3e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140005a43  jmp     short loc_140005A9A
0x140005a45  test    edi, edi
0x140005a47  js      short loc_140005A81
0x140005a49  mov     edi, 8007029Ch
0x140005a4e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x140005a52  mov     rax, [rsp+78h+arg_28]
0x140005a5a  mov     [rsp+78h+var_50], rax; __int64
0x140005a5f  mov     rax, [rsp+78h+arg_20]
0x140005a67  mov     [rsp+78h+var_58], rax; __int64
0x140005a6c  mov     rcx, r10; int
0x140005a6f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140005a74  mov     [rbx+8], edi
0x140005a77  mov     ecx, edi; this
0x140005a79  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140005a7e  mov     [rbx+0Ch], eax
0x140005a81  mov     ecx, edi; this
0x140005a83  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140005a88  jmp     short loc_140005A9A
0x140005a8a  mov     ecx, edi; this
0x140005a8c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140005a91  jmp     short loc_140005A9A
0x140005a93  mov     ecx, edi; this
0x140005a95  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140005a9a  mov     ebp, eax
0x140005a9c  mov     [rbx], r15d
0x140005a9f  mov     eax, [rsp+78h+arg_70]
0x140005aa6  mov     [rbx+4], eax
0x140005aa9  cmp     dword ptr [r14+8], 1
0x140005aae  jnz     short loc_140005AB6
0x140005ab0  or      eax, 8
0x140005ab3  mov     [rbx+4], eax
0x140005ab6  mov     eax, 1
0x140005abb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140005ac3  inc     eax
0x140005ac5  mov     [rbx+10h], eax
0x140005ac8  mov     rax, [rsp+78h+arg_40]
0x140005ad0  xor     edi, edi
0x140005ad2  test    rax, rax
0x140005ad5  jz      short loc_140005ADC
0x140005ad7  cmp     [rax], di
0x140005ada  jnz     short loc_140005ADF
0x140005adc  mov     rax, rdi
0x140005adf  mov     [rbx+18h], rax
0x140005ae3  call    cs:__imp_GetCurrentThreadId
0x140005aea  nop     dword ptr [rax+rax+00h]
0x140005aef  mov     [rbx+20h], eax
0x140005af2  mov     [rbx+38h], r13
0x140005af6  mov     eax, [rsp+78h+arg_8]
0x140005afd  mov     [rbx+40h], eax
0x140005b00  mov     [rbx+44h], ebp
0x140005b03  mov     rax, [rsp+78h+arg_20]
0x140005b0b  mov     [rbx+28h], rax
0x140005b0f  mov     [rbx+30h], r12
0x140005b13  mov     rax, [rsp+78h+arg_28]
0x140005b1b  mov     [rbx+88h], rax
0x140005b22  mov     rax, [rsp+78h+arg_0]
0x140005b2a  mov     [rbx+90h], rax
0x140005b31  mov     [rbx+48h], rdi
0x140005b35  xorps   xmm0, xmm0
0x140005b38  xor     eax, eax
0x140005b3a  movups  xmmword ptr [rbx+68h], xmm0
0x140005b3e  mov     [rbx+78h], rax
0x140005b42  movups  xmmword ptr [rbx+50h], xmm0
0x140005b46  mov     [rbx+60h], rax
0x140005b4a  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140005b51  test    rax, rax
0x140005b54  jz      short loc_140005B5D
0x140005b56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005b5b  jmp     short loc_140005B60
0x140005b5d  mov     rax, rdi
0x140005b60  mov     [rbx+80h], rax
0x140005b67  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140005b6e  test    rax, rax
0x140005b71  jz      short loc_140005B7B
0x140005b73  mov     rcx, rbx
0x140005b76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005b7b  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140005b82  test    rax, rax
0x140005b85  jz      short loc_140005B9D
0x140005b87  mov     r8d, 400h
0x140005b8d  mov     rdx, [rsp+78h+arg_60]
0x140005b95  mov     rcx, rbx
0x140005b98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005b9d  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140005ba4  test    rax, rax
0x140005ba7  jz      short loc_140005BB1
0x140005ba9  mov     rcx, rbx
0x140005bac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005bb1  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140005bb8  test    rax, rax
0x140005bbb  jz      short loc_140005BCB
0x140005bbd  test    byte ptr [rbx+4], 2
0x140005bc1  jnz     short loc_140005BCB
0x140005bc3  mov     rcx, rbx
0x140005bc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005bcb  cmp     [rbx+8], edi
0x140005bce  jl      short loc_140005BEA
0x140005bd0  cmp     r15d, 3
0x140005bd4  jnz     loc_140005CC6
0x140005bda  mov     ecx, 8000FFFFh; this
0x140005bdf  mov     [rbx+8], ecx
0x140005be2  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140005be7  mov     [rbx+0Ch], eax
0x140005bea  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x140005bf1  jnz     short loc_140005C18
0x140005bf3  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140005bfa  test    rax, rax
0x140005bfd  jz      short loc_140005C08
0x140005bff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005c04  test    al, al
0x140005c06  jmp     short loc_140005C16
0x140005c08  call    cs:__imp_IsDebuggerPresent
0x140005c0f  nop     dword ptr [rax+rax+00h]
0x140005c14  test    eax, eax
0x140005c16  jz      short loc_140005C1E
0x140005c18  test    byte ptr [rbx+4], 2
0x140005c1c  jz      short loc_140005C42
0x140005c1e  mov     rax, cs:g_pfnResultLoggingCallback
0x140005c25  test    rax, rax
0x140005c28  jz      short loc_140005C8C
0x140005c2a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140005c31  jnz     short loc_140005C8C
0x140005c33  xor     r8d, r8d
0x140005c36  xor     edx, edx
0x140005c38  mov     rcx, rbx
0x140005c3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005c40  jmp     short loc_140005C8C
0x140005c42  mov     ebp, 800h
0x140005c47  mov     rax, cs:g_pfnResultLoggingCallback
0x140005c4e  test    rax, rax
0x140005c51  jz      short loc_140005C6A
0x140005c53  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140005c5a  jnz     short loc_140005C6A
0x140005c5c  mov     r8d, ebp
0x140005c5f  mov     rdx, rsi
0x140005c62  mov     rcx, rbx
0x140005c65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005c6a  cmp     [rsi], di
0x140005c6d  jnz     short loc_140005C7D
0x140005c6f  mov     r8, rbx; unsigned __int64
0x140005c72  mov     rdx, rbp; unsigned __int16 *
0x140005c75  mov     rcx, rsi; this
0x140005c78  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140005c7d  mov     rcx, rsi; lpOutputString
0x140005c80  call    cs:__imp_OutputDebugStringW
0x140005c87  nop     dword ptr [rax+rax+00h]
0x140005c8c  test    byte ptr [rbx+4], 4
0x140005c90  jnz     short loc_140005C9B
0x140005c92  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x140005c99  jz      short loc_140005CAD
0x140005c9b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140005ca2  test    rax, rax
0x140005ca5  jz      short loc_140005CAD
0x140005ca7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005cac  nop
0x140005cad  mov     rbx, [rsp+78h+arg_10]
0x140005cb5  add     rsp, 40h
0x140005cb9  pop     r15
0x140005cbb  pop     r14
0x140005cbd  pop     r13
0x140005cbf  pop     r12
0x140005cc1  pop     rdi
0x140005cc2  pop     rsi
0x140005cc3  pop     rbp
0x140005cc4  retn
0x140005cc6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
