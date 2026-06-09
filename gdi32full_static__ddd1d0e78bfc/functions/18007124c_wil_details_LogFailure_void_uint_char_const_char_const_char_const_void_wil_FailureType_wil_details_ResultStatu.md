# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18007124c`
- end: `0x180071554`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `776`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x18007114c`
- `0x180086180`
- `0x180086240`
- `0x1800a2fdc`

## callees

- `0x18007124c`
- `0x180073e10`
- `0x1800860c8`
- `0x180087294`
- `0x18008820c`
- `0x180088230`
- `0x1800882f4`
- `0x180088314`
- `0x18008960c`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007136f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007136f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180071496`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180071496`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18007150e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18007150e`

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
0x18007124c  mov     [rsp+arg_10], rbx
0x180071251  mov     [rsp+arg_8], edx
0x180071255  mov     [rsp+arg_0], rcx
0x18007125a  push    rbp
0x18007125b  push    rsi
0x18007125c  push    rdi
0x18007125d  push    r12
0x18007125f  push    r13
0x180071261  push    r14
0x180071263  push    r15
0x180071265  sub     rsp, 40h
0x180071269  mov     r12, r9
0x18007126c  mov     r13, r8
0x18007126f  mov     r10, rcx
0x180071272  xor     eax, eax
0x180071274  mov     rsi, [rsp+78h+lpOutputString]
0x18007127c  mov     [rsi], ax
0x18007127f  mov     rax, [rsp+78h+arg_60]
0x180071287  mov     byte ptr [rax], 0
0x18007128a  mov     r14, [rsp+78h+arg_38]
0x180071292  mov     edi, [r14]
0x180071295  mov     rbx, [rsp+78h+arg_78]
0x18007129d  mov     [rbx+8], edi
0x1800712a0  mov     eax, [r14+4]
0x1800712a4  mov     [rbx+0Ch], eax
0x1800712a7  xor     ebp, ebp
0x1800712a9  mov     r15d, [rsp+78h+arg_30]
0x1800712b1  mov     ecx, r15d
0x1800712b4  test    r15d, r15d
0x1800712b7  jz      short loc_18007131F
0x1800712b9  sub     ecx, 1
0x1800712bc  jz      short loc_180071316
0x1800712be  sub     ecx, 1
0x1800712c1  jz      short loc_1800712D1
0x1800712c3  cmp     ecx, 1
0x1800712c6  jnz     short loc_180071328
0x1800712c8  mov     ecx, edi; this
0x1800712ca  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800712cf  jmp     short loc_180071326
0x1800712d1  test    edi, edi
0x1800712d3  js      short loc_18007130D
0x1800712d5  mov     edi, 8007029Ch
0x1800712da  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800712de  mov     rax, [rsp+78h+arg_28]
0x1800712e6  mov     [rsp+78h+var_50], rax; __int64
0x1800712eb  mov     rax, [rsp+78h+arg_20]
0x1800712f3  mov     [rsp+78h+var_58], rax; __int64
0x1800712f8  mov     rcx, r10; int
0x1800712fb  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180071300  mov     [rbx+8], edi
0x180071303  mov     ecx, edi; this
0x180071305  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18007130a  mov     [rbx+0Ch], eax
0x18007130d  mov     ecx, edi; this
0x18007130f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180071314  jmp     short loc_180071326
0x180071316  mov     ecx, edi; this
0x180071318  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18007131d  jmp     short loc_180071326
0x18007131f  mov     ecx, edi; this
0x180071321  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180071326  mov     ebp, eax
0x180071328  mov     [rbx], r15d
0x18007132b  mov     eax, [rsp+78h+arg_70]
0x180071332  mov     [rbx+4], eax
0x180071335  cmp     dword ptr [r14+8], 1
0x18007133a  jnz     short loc_180071342
0x18007133c  or      eax, 8
0x18007133f  mov     [rbx+4], eax
0x180071342  mov     eax, 1
0x180071347  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18007134f  inc     eax
0x180071351  mov     [rbx+10h], eax
0x180071354  mov     rax, [rsp+78h+arg_40]
0x18007135c  xor     edi, edi
0x18007135e  test    rax, rax
0x180071361  jz      short loc_180071368
0x180071363  cmp     [rax], di
0x180071366  jnz     short loc_18007136B
0x180071368  mov     rax, rdi
0x18007136b  mov     [rbx+18h], rax
0x18007136f  call    cs:__imp_GetCurrentThreadId
0x180071376  nop     dword ptr [rax+rax+00h]
0x18007137b  mov     [rbx+20h], eax
0x18007137e  mov     [rbx+38h], r13
0x180071382  mov     eax, [rsp+78h+arg_8]
0x180071389  mov     [rbx+40h], eax
0x18007138c  mov     [rbx+44h], ebp
0x18007138f  mov     rax, [rsp+78h+arg_20]
0x180071397  mov     [rbx+28h], rax
0x18007139b  mov     [rbx+30h], r12
0x18007139f  mov     rax, [rsp+78h+arg_28]
0x1800713a7  mov     [rbx+88h], rax
0x1800713ae  mov     rax, [rsp+78h+arg_0]
0x1800713b6  mov     [rbx+90h], rax
0x1800713bd  mov     [rbx+48h], rdi
0x1800713c1  xorps   xmm0, xmm0
0x1800713c4  xor     eax, eax
0x1800713c6  movups  xmmword ptr [rbx+68h], xmm0
0x1800713ca  mov     [rbx+78h], rax
0x1800713ce  movups  xmmword ptr [rbx+50h], xmm0
0x1800713d2  mov     [rbx+60h], rax
0x1800713d6  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800713dd  test    rax, rax
0x1800713e0  jz      short loc_1800713E9
0x1800713e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800713e7  jmp     short loc_1800713EC
0x1800713e9  mov     rax, rdi
0x1800713ec  mov     [rbx+80h], rax
0x1800713f3  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800713fa  test    rax, rax
0x1800713fd  jz      short loc_180071407
0x1800713ff  mov     rcx, rbx
0x180071402  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071407  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18007140e  test    rax, rax
0x180071411  jz      short loc_180071429
0x180071413  mov     r8d, 400h
0x180071419  mov     rdx, [rsp+78h+arg_60]
0x180071421  mov     rcx, rbx
0x180071424  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071429  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180071430  test    rax, rax
0x180071433  jz      short loc_18007143D
0x180071435  mov     rcx, rbx
0x180071438  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007143d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180071444  test    rax, rax
0x180071447  jz      short loc_180071457
0x180071449  test    byte ptr [rbx+4], 2
0x18007144d  jnz     short loc_180071457
0x18007144f  mov     rcx, rbx
0x180071452  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071457  cmp     [rbx+8], edi
0x18007145a  jl      short loc_180071478
0x18007145c  cmp     r15d, 3
0x180071460  jz      short loc_180071468
0x180071462  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180071468  mov     ecx, 8000FFFFh; this
0x18007146d  mov     [rbx+8], ecx
0x180071470  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180071475  mov     [rbx+0Ch], eax
0x180071478  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18007147f  jnz     short loc_1800714A6
0x180071481  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180071488  test    rax, rax
0x18007148b  jz      short loc_180071496
0x18007148d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071492  test    al, al
0x180071494  jmp     short loc_1800714A4
0x180071496  call    cs:__imp_IsDebuggerPresent
0x18007149d  nop     dword ptr [rax+rax+00h]
0x1800714a2  test    eax, eax
0x1800714a4  jz      short loc_1800714AC
0x1800714a6  test    byte ptr [rbx+4], 2
0x1800714aa  jz      short loc_1800714D0
0x1800714ac  mov     rax, cs:g_pfnResultLoggingCallback
0x1800714b3  test    rax, rax
0x1800714b6  jz      short loc_18007151A
0x1800714b8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800714bf  jnz     short loc_18007151A
0x1800714c1  xor     r8d, r8d
0x1800714c4  xor     edx, edx
0x1800714c6  mov     rcx, rbx
0x1800714c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800714ce  jmp     short loc_18007151A
0x1800714d0  mov     ebp, 800h
0x1800714d5  mov     rax, cs:g_pfnResultLoggingCallback
0x1800714dc  test    rax, rax
0x1800714df  jz      short loc_1800714F8
0x1800714e1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800714e8  jnz     short loc_1800714F8
0x1800714ea  mov     r8d, ebp
0x1800714ed  mov     rdx, rsi
0x1800714f0  mov     rcx, rbx
0x1800714f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800714f8  cmp     [rsi], di
0x1800714fb  jnz     short loc_18007150B
0x1800714fd  mov     r8, rbx; unsigned __int64
0x180071500  mov     rdx, rbp; unsigned __int16 *
0x180071503  mov     rcx, rsi; this
0x180071506  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18007150b  mov     rcx, rsi; lpOutputString
0x18007150e  call    cs:__imp_OutputDebugStringW
0x180071515  nop     dword ptr [rax+rax+00h]
0x18007151a  test    byte ptr [rbx+4], 4
0x18007151e  jnz     short loc_180071529
0x180071520  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180071527  jz      short loc_18007153B
0x180071529  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180071530  test    rax, rax
0x180071533  jz      short loc_18007153B
0x180071535  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007153a  nop
0x18007153b  mov     rbx, [rsp+78h+arg_10]
0x180071543  add     rsp, 40h
0x180071547  pop     r15
0x180071549  pop     r14
0x18007154b  pop     r13
0x18007154d  pop     r12
0x18007154f  pop     rdi
0x180071550  pop     rsi
0x180071551  pop     rbp
0x180071552  retn
```
