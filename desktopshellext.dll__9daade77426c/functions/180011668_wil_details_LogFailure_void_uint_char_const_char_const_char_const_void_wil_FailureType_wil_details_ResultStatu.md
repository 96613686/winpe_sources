# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180011668`
- end: `0x180011942`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `730`
- prototype: ``
- caller_count: `4`
- callee_count: `11`
- tags: ``

## callers

- `0x18001156c`
- `0x18002d0b4`
- `0x18002d174`
- `0x180034b10`

## callees

- `0x180011668`
- `0x180011df4`
- `0x180023e40`
- `0x18002cffc`
- `0x18002da44`
- `0x18002e318`
- `0x18002e340`
- `0x18002e354`
- `0x18002e370`
- `0x18002ed14`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001178f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001178f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800118df`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800118df`

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
  __int64 ModuleName; // rax
  const struct wil::FailureInfo *v26; // r9
  wil::details *v27; // [rsp+30h] [rbp-48h]

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
          LODWORD(v27) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v27);
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
  if ( !wil::details::IsDebuggerPresent(v24) || (*(_BYTE *)(a16 + 4) & 2) != 0 )
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
0x180011668  mov     [rsp+arg_10], rbx
0x18001166d  mov     [rsp+arg_8], edx
0x180011671  mov     [rsp+arg_0], rcx
0x180011676  push    rbp
0x180011677  push    rsi
0x180011678  push    rdi
0x180011679  push    r12
0x18001167b  push    r13
0x18001167d  push    r14
0x18001167f  push    r15
0x180011681  sub     rsp, 40h
0x180011685  mov     r12, r9
0x180011688  mov     r13, r8
0x18001168b  mov     r10, rcx
0x18001168e  xor     eax, eax
0x180011690  mov     rsi, [rsp+78h+lpOutputString]
0x180011698  mov     [rsi], ax
0x18001169b  mov     rax, [rsp+78h+arg_60]
0x1800116a3  mov     byte ptr [rax], 0
0x1800116a6  mov     r14, [rsp+78h+arg_38]
0x1800116ae  mov     edi, [r14]
0x1800116b1  mov     rbx, [rsp+78h+arg_78]
0x1800116b9  mov     [rbx+8], edi
0x1800116bc  mov     eax, [r14+4]
0x1800116c0  mov     [rbx+0Ch], eax
0x1800116c3  xor     ebp, ebp
0x1800116c5  mov     r15d, [rsp+78h+arg_30]
0x1800116cd  mov     ecx, r15d
0x1800116d0  test    r15d, r15d
0x1800116d3  jz      short loc_18001173F
0x1800116d5  sub     ecx, 1
0x1800116d8  jz      short loc_180011736
0x1800116da  sub     ecx, 1
0x1800116dd  jz      short loc_1800116ED
0x1800116df  cmp     ecx, 1
0x1800116e2  jnz     short loc_180011748
0x1800116e4  mov     ecx, edi; this
0x1800116e6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800116eb  jmp     short loc_180011746
0x1800116ed  test    edi, edi
0x1800116ef  js      short loc_18001172D
0x1800116f1  mov     [rsp+78h+var_40], ebp
0x1800116f5  mov     edi, 8007029Ch
0x1800116fa  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800116fe  mov     rax, [rsp+78h+arg_28]
0x180011706  mov     [rsp+78h+var_50], rax; __int64
0x18001170b  mov     rax, [rsp+78h+arg_20]
0x180011713  mov     [rsp+78h+var_58], rax; __int64
0x180011718  mov     rcx, r10; int
0x18001171b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180011720  mov     [rbx+8], edi
0x180011723  mov     ecx, edi; this
0x180011725  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001172a  mov     [rbx+0Ch], eax
0x18001172d  mov     ecx, edi; this
0x18001172f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180011734  jmp     short loc_180011746
0x180011736  mov     ecx, edi; this
0x180011738  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18001173d  jmp     short loc_180011746
0x18001173f  mov     ecx, edi; this
0x180011741  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180011746  mov     ebp, eax
0x180011748  mov     [rbx], r15d
0x18001174b  mov     eax, [rsp+78h+arg_70]
0x180011752  mov     [rbx+4], eax
0x180011755  cmp     dword ptr [r14+8], 1
0x18001175a  jnz     short loc_180011762
0x18001175c  or      eax, 8
0x18001175f  mov     [rbx+4], eax
0x180011762  mov     eax, 1
0x180011767  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18001176f  inc     eax
0x180011771  mov     [rbx+10h], eax
0x180011774  mov     rax, [rsp+78h+arg_40]
0x18001177c  xor     edi, edi
0x18001177e  test    rax, rax
0x180011781  jz      short loc_180011788
0x180011783  cmp     [rax], di
0x180011786  jnz     short loc_18001178B
0x180011788  mov     rax, rdi
0x18001178b  mov     [rbx+18h], rax
0x18001178f  call    cs:__imp_GetCurrentThreadId
0x180011795  mov     [rbx+20h], eax
0x180011798  mov     [rbx+38h], r13
0x18001179c  mov     eax, [rsp+78h+arg_8]
0x1800117a3  mov     [rbx+40h], eax
0x1800117a6  mov     [rbx+44h], ebp
0x1800117a9  mov     rax, [rsp+78h+arg_20]
0x1800117b1  mov     [rbx+28h], rax
0x1800117b5  mov     [rbx+30h], r12
0x1800117b9  mov     rax, [rsp+78h+arg_28]
0x1800117c1  mov     [rbx+88h], rax
0x1800117c8  mov     rax, [rsp+78h+arg_0]
0x1800117d0  mov     [rbx+90h], rax
0x1800117d7  mov     [rbx+48h], rdi
0x1800117db  xorps   xmm0, xmm0
0x1800117de  xor     eax, eax
0x1800117e0  movups  xmmword ptr [rbx+68h], xmm0
0x1800117e4  mov     [rbx+78h], rax
0x1800117e8  movups  xmmword ptr [rbx+50h], xmm0
0x1800117ec  mov     [rbx+60h], rax
0x1800117f0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800117f7  test    rax, rax
0x1800117fa  jz      short loc_180011803
0x1800117fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011801  jmp     short loc_180011806
0x180011803  mov     rax, rdi
0x180011806  mov     [rbx+80h], rax
0x18001180d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180011814  test    rax, rax
0x180011817  jz      short loc_180011821
0x180011819  mov     rcx, rbx
0x18001181c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011821  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180011828  test    rax, rax
0x18001182b  jz      short loc_180011843
0x18001182d  mov     r8d, 400h
0x180011833  mov     rdx, [rsp+78h+arg_60]
0x18001183b  mov     rcx, rbx
0x18001183e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011843  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001184a  test    rax, rax
0x18001184d  jz      short loc_180011857
0x18001184f  mov     rcx, rbx
0x180011852  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011857  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001185e  test    rax, rax
0x180011861  jz      short loc_180011871
0x180011863  test    byte ptr [rbx+4], 2
0x180011867  jnz     short loc_180011871
0x180011869  mov     rcx, rbx
0x18001186c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011871  cmp     [rbx+8], edi
0x180011874  jl      short loc_180011892
0x180011876  cmp     r15d, 3
0x18001187a  jz      short loc_180011882
0x18001187c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180011882  mov     ecx, 8000FFFFh; this
0x180011887  mov     [rbx+8], ecx
0x18001188a  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001188f  mov     [rbx+0Ch], eax
0x180011892  call    ?IsDebuggerPresent@details@wil@@YA_NXZ; wil::details::IsDebuggerPresent(void)
0x180011897  test    al, al
0x180011899  jz      short loc_1800118E7
0x18001189b  test    byte ptr [rbx+4], 2
0x18001189f  jnz     short loc_1800118E7
0x1800118a1  mov     ebp, 800h
0x1800118a6  mov     rax, cs:g_pfnResultLoggingCallback
0x1800118ad  test    rax, rax
0x1800118b0  jz      short loc_1800118C9
0x1800118b2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800118b9  jnz     short loc_1800118C9
0x1800118bb  mov     r8d, ebp
0x1800118be  mov     rdx, rsi
0x1800118c1  mov     rcx, rbx
0x1800118c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118c9  cmp     [rsi], di
0x1800118cc  jnz     short loc_1800118DC
0x1800118ce  mov     r8, rbx; unsigned __int64
0x1800118d1  mov     rdx, rbp; unsigned __int16 *
0x1800118d4  mov     rcx, rsi; this
0x1800118d7  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800118dc  mov     rcx, rsi; lpOutputString
0x1800118df  call    cs:__imp_OutputDebugStringW
0x1800118e5  jmp     short loc_180011909
0x1800118e7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800118ee  test    rax, rax
0x1800118f1  jz      short loc_180011909
0x1800118f3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800118fa  jnz     short loc_180011909
0x1800118fc  xor     r8d, r8d
0x1800118ff  xor     edx, edx
0x180011901  mov     rcx, rbx
0x180011904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011909  test    byte ptr [rbx+4], 4
0x18001190d  jnz     short loc_180011918
0x18001190f  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180011916  jz      short loc_18001192A
0x180011918  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001191f  test    rax, rax
0x180011922  jz      short loc_18001192A
0x180011924  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011929  nop
0x18001192a  mov     rbx, [rsp+78h+arg_10]
0x180011932  add     rsp, 40h
0x180011936  pop     r15
0x180011938  pop     r14
0x18001193a  pop     r13
0x18001193c  pop     r12
0x18001193e  pop     rdi
0x18001193f  pop     rsi
0x180011940  pop     rbp
0x180011941  retn
```
