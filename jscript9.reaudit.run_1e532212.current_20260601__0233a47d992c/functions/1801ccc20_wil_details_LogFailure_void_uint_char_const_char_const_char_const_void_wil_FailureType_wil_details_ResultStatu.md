# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1801ccc20`
- end: `0x1801ccf6e`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `846`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1801c9d18`
- `0x1801ca130`

## callees

- `0x180193af4`
- `0x1801c9be0`
- `0x1801cb954`
- `0x1801ccc20`
- `0x1801cdb9c`
- `0x1801cdbc0`
- `0x1801cde10`
- `0x1801cde34`
- `0x1801cfbd8`
- `0x18035e010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x1801cce99`
- `KERNEL32!IsDebuggerPresent` at `0x1801cce99`
- `KERNEL32!GetCurrentThreadId` at `0x1801ccd65`
- `KERNEL32!GetCurrentThreadId` at `0x1801ccd65`
- `KERNEL32!OutputDebugStringW` at `0x1801ccf30`
- `KERNEL32!OutputDebugStringW` at `0x1801ccf30`

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
        char a10,
        wil *lpOutputString,
        unsigned __int16 *a12,
        _BYTE *a13,
        __int64 a14,
        int a15,
        unsigned __int64 a16)
{
  unsigned int v16; // edi
  int v17; // esi
  int v18; // eax
  int v19; // edx
  _WORD *v20; // rax
  int v21; // edx
  wil::details::in1diag3 *v22; // rcx
  const struct wil::FailureInfo *v23; // r9
  __int64 (*ModuleName)(void); // rax
  bool v25; // zf
  bool v26; // di
  wil::details *v27; // [rsp+30h] [rbp-68h]

  *(_WORD *)lpOutputString = 0;
  *a13 = 0;
  v16 = *a8;
  *(_DWORD *)(a16 + 8) = *a8;
  *(_DWORD *)(a16 + 12) = a8[1];
  v17 = 0;
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1:
        v18 = wil::details::RecordReturn((wil::details *)v16, a2);
        break;
      case 2:
        if ( (v16 & 0x80000000) == 0 )
        {
          v16 = -2147024228;
          LODWORD(v27) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v27, 0);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v19);
        }
        v18 = wil::details::RecordLog((wil::details *)v16, a2);
        break;
      case 3:
        v18 = wil::details::RecordFailFast((wil::details *)v16, a2);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v18 = wil::details::RecordException((wil::details *)v16, a2);
  }
  v17 = v18;
LABEL_12:
  *(_DWORD *)a16 = a7;
  *(_DWORD *)(a16 + 4) = a15;
  if ( a8[2] == 1 )
    *(_DWORD *)(a16 + 4) = a15 | 8;
  *(_DWORD *)(a16 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v20 = a9;
  if ( !a9 || !*a9 )
    v20 = 0;
  *(_QWORD *)(a16 + 24) = v20;
  *(_DWORD *)(a16 + 32) = GetCurrentThreadId();
  *(_QWORD *)(a16 + 56) = a3;
  *(_DWORD *)(a16 + 64) = a2;
  *(_DWORD *)(a16 + 68) = v17;
  *(_QWORD *)(a16 + 40) = a5;
  *(_QWORD *)(a16 + 48) = a4;
  *(_QWORD *)(a16 + 136) = a6;
  *(_QWORD *)(a16 + 144) = a1;
  *(_QWORD *)(a16 + 72) = 0;
  *(_OWORD *)(a16 + 104) = 0;
  *(_QWORD *)(a16 + 120) = 0;
  *(_OWORD *)(a16 + 80) = 0;
  *(_QWORD *)(a16 + 96) = 0;
  ModuleName = wil::details::g_pfnGetModuleName;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = (__int64 (*)(void))wil::details::g_pfnGetModuleName();
  *(_QWORD *)(a16 + 128) = ModuleName;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(a16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(a16, a13, a14);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(a16);
  if ( wil::details::g_pfnOriginateCallback && !a10 && (*(_BYTE *)(a16 + 4) & 2) == 0 )
    wil::details::g_pfnOriginateCallback(a16);
  if ( *(int *)(a16 + 8) >= 0 )
  {
    if ( a7 != 3 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v21);
  }
  v26 = (wil::g_fIsDebuggerPresent
      || (!wil::g_pfnIsDebuggerPresent
        ? (v25 = !IsDebuggerPresent())
        : (v25 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
          !v25))
     && wil::g_fResultOutputDebugString
     && (*(_BYTE *)(a16 + 4) & 2) == 0;
  if ( a10 || v26 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, a12);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, a12, a16, v23);
    if ( v26 )
      OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(a16, 0, 0);
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
0x1801ccc20  mov     qword ptr [rsp+arg_18], r9
0x1801ccc25  mov     qword ptr [rsp+arg_10], r8
0x1801ccc2a  mov     [rsp+arg_8], edx
0x1801ccc2e  mov     qword ptr [rsp+arg_0], rcx
0x1801ccc33  push    rbx
0x1801ccc34  push    rbp
0x1801ccc35  push    rsi
0x1801ccc36  push    rdi
0x1801ccc37  push    r12
0x1801ccc39  push    r13
0x1801ccc3b  push    r14
0x1801ccc3d  push    r15
0x1801ccc3f  sub     rsp, 58h
0x1801ccc43  mov     [rsp+98h+var_58], 0FFFFFFFFFFFFFFFEh
0x1801ccc4c  xor     eax, eax
0x1801ccc4e  mov     r14, [rsp+98h+lpOutputString]
0x1801ccc56  mov     [r14], ax
0x1801ccc5a  mov     r12, [rsp+98h+arg_60]
0x1801ccc62  mov     [r12], al
0x1801ccc66  mov     r15, [rsp+98h+arg_38]
0x1801ccc6e  mov     edi, [r15]
0x1801ccc71  mov     rbx, [rsp+98h+arg_78]
0x1801ccc79  mov     [rbx+8], edi
0x1801ccc7c  mov     eax, [r15+4]
0x1801ccc80  mov     [rbx+0Ch], eax
0x1801ccc83  xor     esi, esi
0x1801ccc85  mov     ebp, [rsp+98h+arg_30]
0x1801ccc8c  mov     ecx, ebp
0x1801ccc8e  mov     r13, [rsp+98h+arg_28]
0x1801ccc96  test    ebp, ebp
0x1801ccc98  jz      short loc_1801CCD18
0x1801ccc9a  sub     ecx, 1
0x1801ccc9d  jz      short loc_1801CCD0F
0x1801ccc9f  sub     ecx, 1
0x1801ccca2  jz      short loc_1801CCCB2
0x1801ccca4  cmp     ecx, 1
0x1801ccca7  jnz     short loc_1801CCD21
0x1801ccca9  mov     ecx, edi; this
0x1801cccab  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1801cccb0  jmp     short loc_1801CCD1F
0x1801cccb2  test    edi, edi
0x1801cccb4  js      short loc_1801CCD06
0x1801cccb6  mov     [rsp+98h+var_60], esi; int
0x1801cccba  mov     edi, 8007029Ch
0x1801cccbf  mov     dword ptr [rsp+98h+var_68], edi; wil::details *
0x1801cccc3  mov     [rsp+98h+var_70], r13; __int64
0x1801cccc8  mov     rax, [rsp+98h+arg_20]
0x1801cccd0  mov     [rsp+98h+var_78], rax; __int64
0x1801cccd5  mov     r9, qword ptr [rsp+98h+arg_18]; int
0x1801cccdd  mov     r8, qword ptr [rsp+98h+arg_10]; int
0x1801ccce5  mov     edx, [rsp+98h+arg_8]; int
0x1801cccec  mov     rcx, qword ptr [rsp+98h+arg_0]; int
0x1801cccf4  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1801cccf9  mov     [rbx+8], edi
0x1801cccfc  mov     ecx, edi; this
0x1801cccfe  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1801ccd03  mov     [rbx+0Ch], eax
0x1801ccd06  mov     ecx, edi; this
0x1801ccd08  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1801ccd0d  jmp     short loc_1801CCD1F
0x1801ccd0f  mov     ecx, edi; this
0x1801ccd11  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1801ccd16  jmp     short loc_1801CCD1F
0x1801ccd18  mov     ecx, edi; this
0x1801ccd1a  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1801ccd1f  mov     esi, eax
0x1801ccd21  mov     [rbx], ebp
0x1801ccd23  mov     eax, [rsp+98h+arg_70]
0x1801ccd2a  mov     [rbx+4], eax
0x1801ccd2d  cmp     dword ptr [r15+8], 1
0x1801ccd32  jnz     short loc_1801CCD3A
0x1801ccd34  or      eax, 8
0x1801ccd37  mov     [rbx+4], eax
0x1801ccd3a  mov     eax, 1
0x1801ccd3f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1801ccd47  inc     eax
0x1801ccd49  mov     [rbx+10h], eax
0x1801ccd4c  mov     rax, [rsp+98h+arg_40]
0x1801ccd54  test    rax, rax
0x1801ccd57  jz      short loc_1801CCD5F
0x1801ccd59  cmp     word ptr [rax], 0
0x1801ccd5d  jnz     short loc_1801CCD61
0x1801ccd5f  xor     eax, eax
0x1801ccd61  mov     [rbx+18h], rax
0x1801ccd65  call    cs:__imp_GetCurrentThreadId
0x1801ccd6b  mov     [rbx+20h], eax
0x1801ccd6e  mov     rax, qword ptr [rsp+98h+arg_10]
0x1801ccd76  mov     [rbx+38h], rax
0x1801ccd7a  mov     eax, [rsp+98h+arg_8]
0x1801ccd81  mov     [rbx+40h], eax
0x1801ccd84  mov     [rbx+44h], esi
0x1801ccd87  mov     rax, [rsp+98h+arg_20]
0x1801ccd8f  mov     [rbx+28h], rax
0x1801ccd93  mov     rax, qword ptr [rsp+98h+arg_18]
0x1801ccd9b  mov     [rbx+30h], rax
0x1801ccd9f  mov     [rbx+88h], r13
0x1801ccda6  mov     rax, qword ptr [rsp+98h+arg_0]
0x1801ccdae  mov     [rbx+90h], rax
0x1801ccdb5  mov     qword ptr [rbx+48h], 0
0x1801ccdbd  xorps   xmm0, xmm0
0x1801ccdc0  xor     eax, eax
0x1801ccdc2  movups  xmmword ptr [rbx+68h], xmm0
0x1801ccdc6  mov     [rbx+78h], rax
0x1801ccdca  movups  xmmword ptr [rbx+50h], xmm0
0x1801ccdce  mov     [rbx+60h], rax
0x1801ccdd2  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1801ccdd9  test    rax, rax
0x1801ccddc  jz      short loc_1801CCDE3
0x1801ccdde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ccde3  mov     [rbx+80h], rax
0x1801ccdea  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1801ccdf1  test    rax, rax
0x1801ccdf4  jz      short loc_1801CCDFE
0x1801ccdf6  mov     rcx, rbx
0x1801ccdf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ccdfe  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1801cce05  test    rax, rax
0x1801cce08  jz      short loc_1801CCE1D
0x1801cce0a  mov     r8, [rsp+98h+arg_68]
0x1801cce12  mov     rdx, r12
0x1801cce15  mov     rcx, rbx
0x1801cce18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801cce1d  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1801cce24  test    rax, rax
0x1801cce27  jz      short loc_1801CCE31
0x1801cce29  mov     rcx, rbx
0x1801cce2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801cce31  movzx   esi, [rsp+98h+arg_48]
0x1801cce39  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1801cce40  test    rax, rax
0x1801cce43  jz      short loc_1801CCE58
0x1801cce45  test    sil, sil
0x1801cce48  jnz     short loc_1801CCE58
0x1801cce4a  test    byte ptr [rbx+4], 2
0x1801cce4e  jnz     short loc_1801CCE58
0x1801cce50  mov     rcx, rbx
0x1801cce53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801cce58  cmp     dword ptr [rbx+8], 0
0x1801cce5c  jl      short loc_1801CCE7B
0x1801cce5e  cmp     ebp, 3
0x1801cce61  jnz     loc_1801CCF68
0x1801cce67  mov     dword ptr [rbx+8], 8000FFFFh
0x1801cce6e  mov     ecx, 8000FFFFh; this
0x1801cce73  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1801cce78  mov     [rbx+0Ch], eax
0x1801cce7b  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, 0; bool wil::g_fIsDebuggerPresent
0x1801cce82  jnz     short loc_1801CCEA3
0x1801cce84  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1801cce8b  test    rax, rax
0x1801cce8e  jz      short loc_1801CCE99
0x1801cce90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801cce95  test    al, al
0x1801cce97  jmp     short loc_1801CCEA1
0x1801cce99  call    cs:__imp_IsDebuggerPresent
0x1801cce9f  test    eax, eax
0x1801ccea1  jz      short loc_1801CCEB7
0x1801ccea3  cmp     cs:?g_fResultOutputDebugString@wil@@3_NA, 0; bool wil::g_fResultOutputDebugString
0x1801cceaa  jz      short loc_1801CCEB7
0x1801cceac  test    byte ptr [rbx+4], 2
0x1801cceb0  jnz     short loc_1801CCEB7
0x1801cceb2  mov     dil, 1
0x1801cceb5  jmp     short loc_1801CCEBA
0x1801cceb7  xor     dil, dil
0x1801cceba  test    sil, sil
0x1801ccebd  jnz     short loc_1801CCEE8
0x1801ccebf  test    dil, dil
0x1801ccec2  jnz     short loc_1801CCEE8
0x1801ccec4  mov     rax, cs:g_pfnResultLoggingCallback
0x1801ccecb  test    rax, rax
0x1801ccece  jz      short loc_1801CCF36
0x1801cced0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1801cced7  jnz     short loc_1801CCF36
0x1801cced9  xor     r8d, r8d
0x1801ccedc  xor     edx, edx
0x1801ccede  mov     rcx, rbx
0x1801ccee1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ccee6  jmp     short loc_1801CCF36
0x1801ccee8  mov     rsi, [rsp+98h+arg_58]
0x1801ccef0  mov     rax, cs:g_pfnResultLoggingCallback
0x1801ccef7  test    rax, rax
0x1801ccefa  jz      short loc_1801CCF13
0x1801ccefc  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x1801ccf03  jnz     short loc_1801CCF13
0x1801ccf05  mov     r8, rsi
0x1801ccf08  mov     rdx, r14
0x1801ccf0b  mov     rcx, rbx
0x1801ccf0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ccf13  cmp     word ptr [r14], 0
0x1801ccf18  jnz     short loc_1801CCF28
0x1801ccf1a  mov     r8, rbx; unsigned __int64
0x1801ccf1d  mov     rdx, rsi; unsigned __int16 *
0x1801ccf20  mov     rcx, r14; this
0x1801ccf23  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1801ccf28  test    dil, dil
0x1801ccf2b  jz      short loc_1801CCF36
0x1801ccf2d  mov     rcx, r14; lpOutputString
0x1801ccf30  call    cs:__imp_OutputDebugStringW
0x1801ccf36  test    byte ptr [rbx+4], 4
0x1801ccf3a  jnz     short loc_1801CCF45
0x1801ccf3c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, 0; bool wil::g_fBreakOnFailure
0x1801ccf43  jz      short loc_1801CCF57
0x1801ccf45  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1801ccf4c  test    rax, rax
0x1801ccf4f  jz      short loc_1801CCF57
0x1801ccf51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ccf56  nop
0x1801ccf57  add     rsp, 58h
0x1801ccf5b  pop     r15
0x1801ccf5d  pop     r14
0x1801ccf5f  pop     r13
0x1801ccf61  pop     r12
0x1801ccf63  pop     rdi
0x1801ccf64  pop     rsi
0x1801ccf65  pop     rbp
0x1801ccf66  pop     rbx
0x1801ccf67  retn
0x1801ccf68  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
