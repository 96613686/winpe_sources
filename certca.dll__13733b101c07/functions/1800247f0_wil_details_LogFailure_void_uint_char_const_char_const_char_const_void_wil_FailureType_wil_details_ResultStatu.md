# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800247f0`
- end: `0x180024ae9`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180022cd4`

## callees

- `0x18001c7f4`
- `0x18001cab0`
- `0x18001ce90`
- `0x180022710`
- `0x1800247f0`
- `0x18002539c`
- `0x180025528`
- `0x180025544`
- `0x180026930`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024913`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024913`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180024a32`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180024a32`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180024aa4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180024aa4`

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
0x1800247f0  mov     [rsp+arg_10], rbx
0x1800247f5  mov     [rsp+arg_8], edx
0x1800247f9  mov     [rsp+arg_0], rcx
0x1800247fe  push    rbp
0x1800247ff  push    rsi
0x180024800  push    rdi
0x180024801  push    r12
0x180024803  push    r13
0x180024805  push    r14
0x180024807  push    r15
0x180024809  sub     rsp, 40h
0x18002480d  mov     r12, r9
0x180024810  mov     r13, r8
0x180024813  mov     r10, rcx
0x180024816  xor     eax, eax
0x180024818  mov     rsi, [rsp+78h+lpOutputString]
0x180024820  mov     [rsi], ax
0x180024823  mov     rax, [rsp+78h+arg_60]
0x18002482b  mov     byte ptr [rax], 0
0x18002482e  mov     r14, [rsp+78h+arg_38]
0x180024836  mov     edi, [r14]
0x180024839  mov     rbx, [rsp+78h+arg_78]
0x180024841  mov     [rbx+8], edi
0x180024844  mov     eax, [r14+4]
0x180024848  mov     [rbx+0Ch], eax
0x18002484b  xor     ebp, ebp
0x18002484d  mov     r15d, [rsp+78h+arg_30]
0x180024855  mov     ecx, r15d
0x180024858  test    r15d, r15d
0x18002485b  jz      short loc_1800248C3
0x18002485d  sub     ecx, 1
0x180024860  jz      short loc_1800248BA
0x180024862  sub     ecx, 1
0x180024865  jz      short loc_180024875
0x180024867  cmp     ecx, 1
0x18002486a  jnz     short loc_1800248CC
0x18002486c  mov     ecx, edi; this
0x18002486e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180024873  jmp     short loc_1800248CA
0x180024875  test    edi, edi
0x180024877  js      short loc_1800248B1
0x180024879  mov     edi, 8007029Ch
0x18002487e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180024882  mov     rax, [rsp+78h+arg_28]
0x18002488a  mov     [rsp+78h+var_50], rax; __int64
0x18002488f  mov     rax, [rsp+78h+arg_20]
0x180024897  mov     [rsp+78h+var_58], rax; __int64
0x18002489c  mov     rcx, r10; int
0x18002489f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800248a4  mov     [rbx+8], edi
0x1800248a7  mov     ecx, edi; this
0x1800248a9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800248ae  mov     [rbx+0Ch], eax
0x1800248b1  mov     ecx, edi; this
0x1800248b3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800248b8  jmp     short loc_1800248CA
0x1800248ba  mov     ecx, edi; this
0x1800248bc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800248c1  jmp     short loc_1800248CA
0x1800248c3  mov     ecx, edi; this
0x1800248c5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800248ca  mov     ebp, eax
0x1800248cc  mov     [rbx], r15d
0x1800248cf  mov     eax, [rsp+78h+arg_70]
0x1800248d6  mov     [rbx+4], eax
0x1800248d9  cmp     dword ptr [r14+8], 1
0x1800248de  jnz     short loc_1800248E6
0x1800248e0  or      eax, 8
0x1800248e3  mov     [rbx+4], eax
0x1800248e6  mov     eax, 1
0x1800248eb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800248f3  inc     eax
0x1800248f5  mov     [rbx+10h], eax
0x1800248f8  mov     rax, [rsp+78h+arg_40]
0x180024900  xor     edi, edi
0x180024902  test    rax, rax
0x180024905  jz      short loc_18002490C
0x180024907  cmp     [rax], di
0x18002490a  jnz     short loc_18002490F
0x18002490c  mov     rax, rdi
0x18002490f  mov     [rbx+18h], rax
0x180024913  call    cs:__imp_GetCurrentThreadId
0x180024919  mov     [rbx+20h], eax
0x18002491c  mov     [rbx+38h], r13
0x180024920  mov     eax, [rsp+78h+arg_8]
0x180024927  mov     [rbx+40h], eax
0x18002492a  mov     [rbx+44h], ebp
0x18002492d  mov     rax, [rsp+78h+arg_20]
0x180024935  mov     [rbx+28h], rax
0x180024939  mov     [rbx+30h], r12
0x18002493d  mov     rax, [rsp+78h+arg_28]
0x180024945  mov     [rbx+88h], rax
0x18002494c  mov     rax, [rsp+78h+arg_0]
0x180024954  mov     [rbx+90h], rax
0x18002495b  mov     [rbx+48h], rdi
0x18002495f  xorps   xmm0, xmm0
0x180024962  xor     eax, eax
0x180024964  movups  xmmword ptr [rbx+68h], xmm0
0x180024968  mov     [rbx+78h], rax
0x18002496c  movups  xmmword ptr [rbx+50h], xmm0
0x180024970  mov     [rbx+60h], rax
0x180024974  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18002497b  test    rax, rax
0x18002497e  jz      short loc_180024987
0x180024980  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024985  jmp     short loc_18002498A
0x180024987  mov     rax, rdi
0x18002498a  mov     [rbx+80h], rax
0x180024991  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180024998  test    rax, rax
0x18002499b  jz      short loc_1800249A5
0x18002499d  mov     rcx, rbx
0x1800249a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800249a5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800249ac  test    rax, rax
0x1800249af  jz      short loc_1800249C7
0x1800249b1  mov     r8d, 400h
0x1800249b7  mov     rdx, [rsp+78h+arg_60]
0x1800249bf  mov     rcx, rbx
0x1800249c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800249c7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800249ce  test    rax, rax
0x1800249d1  jz      short loc_1800249DB
0x1800249d3  mov     rcx, rbx
0x1800249d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800249db  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800249e2  test    rax, rax
0x1800249e5  jz      short loc_1800249F5
0x1800249e7  test    byte ptr [rbx+4], 2
0x1800249eb  jnz     short loc_1800249F5
0x1800249ed  mov     rcx, rbx
0x1800249f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800249f5  cmp     [rbx+8], edi
0x1800249f8  jl      short loc_180024A14
0x1800249fa  cmp     r15d, 3
0x1800249fe  jnz     loc_180024AE3
0x180024a04  mov     ecx, 8000FFFFh; this
0x180024a09  mov     [rbx+8], ecx
0x180024a0c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180024a11  mov     [rbx+0Ch], eax
0x180024a14  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180024a1b  jnz     short loc_180024A3C
0x180024a1d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180024a24  test    rax, rax
0x180024a27  jz      short loc_180024A32
0x180024a29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024a2e  test    al, al
0x180024a30  jmp     short loc_180024A3A
0x180024a32  call    cs:__imp_IsDebuggerPresent
0x180024a38  test    eax, eax
0x180024a3a  jz      short loc_180024A42
0x180024a3c  test    byte ptr [rbx+4], 2
0x180024a40  jz      short loc_180024A66
0x180024a42  mov     rax, cs:g_pfnResultLoggingCallback
0x180024a49  test    rax, rax
0x180024a4c  jz      short loc_180024AAA
0x180024a4e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180024a55  jnz     short loc_180024AAA
0x180024a57  xor     r8d, r8d
0x180024a5a  xor     edx, edx
0x180024a5c  mov     rcx, rbx
0x180024a5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024a64  jmp     short loc_180024AAA
0x180024a66  mov     ebp, 800h
0x180024a6b  mov     rax, cs:g_pfnResultLoggingCallback
0x180024a72  test    rax, rax
0x180024a75  jz      short loc_180024A8E
0x180024a77  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180024a7e  jnz     short loc_180024A8E
0x180024a80  mov     r8d, ebp
0x180024a83  mov     rdx, rsi
0x180024a86  mov     rcx, rbx
0x180024a89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024a8e  cmp     [rsi], di
0x180024a91  jnz     short loc_180024AA1
0x180024a93  mov     r8, rbx; unsigned __int64
0x180024a96  mov     rdx, rbp; unsigned __int16 *
0x180024a99  mov     rcx, rsi; this
0x180024a9c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180024aa1  mov     rcx, rsi; lpOutputString
0x180024aa4  call    cs:__imp_OutputDebugStringW
0x180024aaa  test    byte ptr [rbx+4], 4
0x180024aae  jnz     short loc_180024AB9
0x180024ab0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180024ab7  jz      short loc_180024ACB
0x180024ab9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180024ac0  test    rax, rax
0x180024ac3  jz      short loc_180024ACB
0x180024ac5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024aca  nop
0x180024acb  mov     rbx, [rsp+78h+arg_10]
0x180024ad3  add     rsp, 40h
0x180024ad7  pop     r15
0x180024ad9  pop     r14
0x180024adb  pop     r13
0x180024add  pop     r12
0x180024adf  pop     rdi
0x180024ae0  pop     rsi
0x180024ae1  pop     rbp
0x180024ae2  retn
0x180024ae3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
