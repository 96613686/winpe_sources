# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140007870`
- end: `0x140007b49`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `729`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x140005a94`
- `0x140005dd4`

## callees

- `0x140004bb0`
- `0x1400059dc`
- `0x140006f1c`
- `0x1400075ec`
- `0x140007830`
- `0x140007870`
- `0x140007ff8`
- `0x140008014`
- `0x140008030`
- `0x1400091d0`
- `0x14006b010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140007ae1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140007ae1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140007993`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140007993`

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
  __int64 ModuleName; // rax
  const struct wil::FailureInfo *v27; // r9
  wil::details *v28; // [rsp+30h] [rbp-48h]

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
          LODWORD(v28) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v28);
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
  if ( !wil::details::IsDebuggerPresent(v25) || (*(_BYTE *)(a16 + 4) & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v27);
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
0x140007870  mov     [rsp+arg_10], rbx
0x140007875  mov     [rsp+arg_8], edx
0x140007879  mov     [rsp+arg_0], rcx
0x14000787e  push    rbp
0x14000787f  push    rsi
0x140007880  push    rdi
0x140007881  push    r12
0x140007883  push    r13
0x140007885  push    r14
0x140007887  push    r15
0x140007889  sub     rsp, 40h
0x14000788d  mov     r14, [rsp+78h+arg_38]
0x140007895  xor     eax, eax
0x140007897  mov     rbx, [rsp+78h+arg_78]
0x14000789f  xor     ebp, ebp
0x1400078a1  mov     r15d, [rsp+78h+arg_30]
0x1400078a9  mov     r10, rcx
0x1400078ac  mov     rsi, [rsp+78h+lpOutputString]
0x1400078b4  mov     r12, r9
0x1400078b7  mov     r13, r8
0x1400078ba  mov     ecx, r15d
0x1400078bd  mov     [rsi], ax
0x1400078c0  mov     rax, [rsp+78h+arg_60]
0x1400078c8  mov     byte ptr [rax], 0
0x1400078cb  mov     edi, [r14]
0x1400078ce  mov     [rbx+8], edi
0x1400078d1  mov     eax, [r14+4]
0x1400078d5  mov     [rbx+0Ch], eax
0x1400078d8  test    r15d, r15d
0x1400078db  jz      short loc_140007943
0x1400078dd  sub     ecx, 1
0x1400078e0  jz      short loc_14000793A
0x1400078e2  sub     ecx, 1
0x1400078e5  jz      short loc_1400078F5
0x1400078e7  cmp     ecx, 1
0x1400078ea  jnz     short loc_14000794C
0x1400078ec  mov     ecx, edi; this
0x1400078ee  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1400078f3  jmp     short loc_14000794A
0x1400078f5  test    edi, edi
0x1400078f7  js      short loc_140007931
0x1400078f9  mov     rax, [rsp+78h+arg_28]
0x140007901  mov     edi, 8007029Ch
0x140007906  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x14000790a  mov     rcx, r10; int
0x14000790d  mov     [rsp+78h+var_50], rax; __int64
0x140007912  mov     rax, [rsp+78h+arg_20]
0x14000791a  mov     [rsp+78h+var_58], rax; __int64
0x14000791f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140007924  mov     ecx, edi; this
0x140007926  mov     [rbx+8], edi
0x140007929  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000792e  mov     [rbx+0Ch], eax
0x140007931  mov     ecx, edi; this
0x140007933  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140007938  jmp     short loc_14000794A
0x14000793a  mov     ecx, edi; this
0x14000793c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140007941  jmp     short loc_14000794A
0x140007943  mov     ecx, edi; this
0x140007945  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x14000794a  mov     ebp, eax
0x14000794c  mov     eax, [rsp+78h+arg_70]
0x140007953  mov     [rbx+4], eax
0x140007956  mov     [rbx], r15d
0x140007959  cmp     dword ptr [r14+8], 1
0x14000795e  jnz     short loc_140007966
0x140007960  or      eax, 8
0x140007963  mov     [rbx+4], eax
0x140007966  mov     eax, 1
0x14000796b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140007973  inc     eax
0x140007975  xor     edi, edi
0x140007977  mov     [rbx+10h], eax
0x14000797a  mov     rax, [rsp+78h+arg_40]
0x140007982  test    rax, rax
0x140007985  jz      short loc_14000798C
0x140007987  cmp     [rax], di
0x14000798a  jnz     short loc_14000798F
0x14000798c  mov     rax, rdi
0x14000798f  mov     [rbx+18h], rax
0x140007993  call    cs:__imp_GetCurrentThreadId
0x140007999  mov     [rbx+38h], r13
0x14000799d  xorps   xmm0, xmm0
0x1400079a0  mov     [rbx+20h], eax
0x1400079a3  mov     eax, [rsp+78h+arg_8]
0x1400079aa  mov     [rbx+40h], eax
0x1400079ad  mov     rax, [rsp+78h+arg_20]
0x1400079b5  mov     [rbx+28h], rax
0x1400079b9  mov     rax, [rsp+78h+arg_28]
0x1400079c1  mov     [rbx+88h], rax
0x1400079c8  mov     rax, [rsp+78h+arg_0]
0x1400079d0  mov     [rbx+90h], rax
0x1400079d7  xor     eax, eax
0x1400079d9  mov     [rbx+44h], ebp
0x1400079dc  mov     [rbx+30h], r12
0x1400079e0  mov     [rbx+48h], rdi
0x1400079e4  movups  xmmword ptr [rbx+68h], xmm0
0x1400079e8  mov     [rbx+78h], rax
0x1400079ec  movups  xmmword ptr [rbx+50h], xmm0
0x1400079f0  mov     [rbx+60h], rax
0x1400079f4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1400079fb  test    rax, rax
0x1400079fe  jz      short loc_140007A07
0x140007a00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007a05  jmp     short loc_140007A0A
0x140007a07  mov     rax, rdi
0x140007a0a  mov     [rbx+80h], rax
0x140007a11  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140007a18  test    rax, rax
0x140007a1b  jz      short loc_140007A25
0x140007a1d  mov     rcx, rbx
0x140007a20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007a25  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140007a2c  test    rax, rax
0x140007a2f  jz      short loc_140007A47
0x140007a31  mov     rdx, [rsp+78h+arg_60]
0x140007a39  mov     r8d, 400h
0x140007a3f  mov     rcx, rbx
0x140007a42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007a47  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140007a4e  test    rax, rax
0x140007a51  jz      short loc_140007A5B
0x140007a53  mov     rcx, rbx
0x140007a56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007a5b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140007a62  test    rax, rax
0x140007a65  jz      short loc_140007A75
0x140007a67  test    byte ptr [rbx+4], 2
0x140007a6b  jnz     short loc_140007A75
0x140007a6d  mov     rcx, rbx
0x140007a70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007a75  cmp     [rbx+8], edi
0x140007a78  jl      short loc_140007A94
0x140007a7a  cmp     r15d, 3
0x140007a7e  jnz     loc_140007B43
0x140007a84  mov     ecx, 8000FFFFh; this
0x140007a89  mov     [rbx+8], ecx
0x140007a8c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140007a91  mov     [rbx+0Ch], eax
0x140007a94  call    ?IsDebuggerPresent@details@wil@@YA_NXZ; wil::details::IsDebuggerPresent(void)
0x140007a99  test    al, al
0x140007a9b  jz      short loc_140007AE9
0x140007a9d  test    byte ptr [rbx+4], 2
0x140007aa1  jnz     short loc_140007AE9
0x140007aa3  mov     rax, cs:g_pfnResultLoggingCallback
0x140007aaa  mov     ebp, 800h
0x140007aaf  test    rax, rax
0x140007ab2  jz      short loc_140007ACB
0x140007ab4  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140007abb  jnz     short loc_140007ACB
0x140007abd  mov     r8d, ebp
0x140007ac0  mov     rdx, rsi
0x140007ac3  mov     rcx, rbx
0x140007ac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007acb  cmp     [rsi], di
0x140007ace  jnz     short loc_140007ADE
0x140007ad0  mov     r8, rbx; unsigned __int64
0x140007ad3  mov     rdx, rbp; unsigned __int16 *
0x140007ad6  mov     rcx, rsi; this
0x140007ad9  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140007ade  mov     rcx, rsi; lpOutputString
0x140007ae1  call    cs:__imp_OutputDebugStringW
0x140007ae7  jmp     short loc_140007B0B
0x140007ae9  mov     rax, cs:g_pfnResultLoggingCallback
0x140007af0  test    rax, rax
0x140007af3  jz      short loc_140007B0B
0x140007af5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140007afc  jnz     short loc_140007B0B
0x140007afe  xor     r8d, r8d
0x140007b01  xor     edx, edx
0x140007b03  mov     rcx, rbx
0x140007b06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007b0b  test    byte ptr [rbx+4], 4
0x140007b0f  jnz     short loc_140007B1A
0x140007b11  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x140007b18  jz      short loc_140007B2B
0x140007b1a  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140007b21  test    rax, rax
0x140007b24  jz      short loc_140007B2B
0x140007b26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007b2b  mov     rbx, [rsp+78h+arg_10]
0x140007b33  add     rsp, 40h
0x140007b37  pop     r15
0x140007b39  pop     r14
0x140007b3b  pop     r13
0x140007b3d  pop     r12
0x140007b3f  pop     rdi
0x140007b40  pop     rsi
0x140007b41  pop     rbp
0x140007b42  retn
0x140007b43  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
