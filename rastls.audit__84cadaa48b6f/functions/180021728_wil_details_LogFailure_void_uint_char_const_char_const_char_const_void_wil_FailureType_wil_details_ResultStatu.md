# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180021728`
- end: `0x180021a30`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `776`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x180021628`
- `0x18003a860`
- `0x18003a920`
- `0x18003f42c`

## callees

- `0x180021728`
- `0x18002dd48`
- `0x18003a7a8`
- `0x18003bc84`
- `0x18003cd68`
- `0x18003cd90`
- `0x18003ce54`
- `0x18003ce74`
- `0x18003e638`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002184b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002184b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800219ea`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800219ea`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180021972`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180021972`

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
0x180021728  mov     [rsp+arg_10], rbx
0x18002172d  mov     [rsp+arg_8], edx
0x180021731  mov     [rsp+arg_0], rcx
0x180021736  push    rbp
0x180021737  push    rsi
0x180021738  push    rdi
0x180021739  push    r12
0x18002173b  push    r13
0x18002173d  push    r14
0x18002173f  push    r15
0x180021741  sub     rsp, 40h
0x180021745  mov     r12, r9
0x180021748  mov     r13, r8
0x18002174b  mov     r10, rcx
0x18002174e  xor     eax, eax
0x180021750  mov     rsi, [rsp+78h+lpOutputString]
0x180021758  mov     [rsi], ax
0x18002175b  mov     rax, [rsp+78h+arg_60]
0x180021763  mov     byte ptr [rax], 0
0x180021766  mov     r14, [rsp+78h+arg_38]
0x18002176e  mov     edi, [r14]
0x180021771  mov     rbx, [rsp+78h+arg_78]
0x180021779  mov     [rbx+8], edi
0x18002177c  mov     eax, [r14+4]
0x180021780  mov     [rbx+0Ch], eax
0x180021783  xor     ebp, ebp
0x180021785  mov     r15d, [rsp+78h+arg_30]
0x18002178d  mov     ecx, r15d
0x180021790  test    r15d, r15d
0x180021793  jz      short loc_1800217FB
0x180021795  sub     ecx, 1
0x180021798  jz      short loc_1800217F2
0x18002179a  sub     ecx, 1
0x18002179d  jz      short loc_1800217AD
0x18002179f  cmp     ecx, 1
0x1800217a2  jnz     short loc_180021804
0x1800217a4  mov     ecx, edi; this
0x1800217a6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800217ab  jmp     short loc_180021802
0x1800217ad  test    edi, edi
0x1800217af  js      short loc_1800217E9
0x1800217b1  mov     edi, 8007029Ch
0x1800217b6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800217ba  mov     rax, [rsp+78h+arg_28]
0x1800217c2  mov     [rsp+78h+var_50], rax; __int64
0x1800217c7  mov     rax, [rsp+78h+arg_20]
0x1800217cf  mov     [rsp+78h+var_58], rax; __int64
0x1800217d4  mov     rcx, r10; int
0x1800217d7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800217dc  mov     [rbx+8], edi
0x1800217df  mov     ecx, edi; this
0x1800217e1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800217e6  mov     [rbx+0Ch], eax
0x1800217e9  mov     ecx, edi; this
0x1800217eb  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800217f0  jmp     short loc_180021802
0x1800217f2  mov     ecx, edi; this
0x1800217f4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800217f9  jmp     short loc_180021802
0x1800217fb  mov     ecx, edi; this
0x1800217fd  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180021802  mov     ebp, eax
0x180021804  mov     [rbx], r15d
0x180021807  mov     eax, [rsp+78h+arg_70]
0x18002180e  mov     [rbx+4], eax
0x180021811  cmp     dword ptr [r14+8], 1
0x180021816  jnz     short loc_18002181E
0x180021818  or      eax, 8
0x18002181b  mov     [rbx+4], eax
0x18002181e  mov     eax, 1
0x180021823  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18002182b  inc     eax
0x18002182d  mov     [rbx+10h], eax
0x180021830  mov     rax, [rsp+78h+arg_40]
0x180021838  xor     edi, edi
0x18002183a  test    rax, rax
0x18002183d  jz      short loc_180021844
0x18002183f  cmp     [rax], di
0x180021842  jnz     short loc_180021847
0x180021844  mov     rax, rdi
0x180021847  mov     [rbx+18h], rax
0x18002184b  call    cs:__imp_GetCurrentThreadId
0x180021852  nop     dword ptr [rax+rax+00h]
0x180021857  mov     [rbx+20h], eax
0x18002185a  mov     [rbx+38h], r13
0x18002185e  mov     eax, [rsp+78h+arg_8]
0x180021865  mov     [rbx+40h], eax
0x180021868  mov     [rbx+44h], ebp
0x18002186b  mov     rax, [rsp+78h+arg_20]
0x180021873  mov     [rbx+28h], rax
0x180021877  mov     [rbx+30h], r12
0x18002187b  mov     rax, [rsp+78h+arg_28]
0x180021883  mov     [rbx+88h], rax
0x18002188a  mov     rax, [rsp+78h+arg_0]
0x180021892  mov     [rbx+90h], rax
0x180021899  mov     [rbx+48h], rdi
0x18002189d  xorps   xmm0, xmm0
0x1800218a0  xor     eax, eax
0x1800218a2  movups  xmmword ptr [rbx+68h], xmm0
0x1800218a6  mov     [rbx+78h], rax
0x1800218aa  movups  xmmword ptr [rbx+50h], xmm0
0x1800218ae  mov     [rbx+60h], rax
0x1800218b2  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800218b9  test    rax, rax
0x1800218bc  jz      short loc_1800218C5
0x1800218be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800218c3  jmp     short loc_1800218C8
0x1800218c5  mov     rax, rdi
0x1800218c8  mov     [rbx+80h], rax
0x1800218cf  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800218d6  test    rax, rax
0x1800218d9  jz      short loc_1800218E3
0x1800218db  mov     rcx, rbx
0x1800218de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800218e3  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800218ea  test    rax, rax
0x1800218ed  jz      short loc_180021905
0x1800218ef  mov     r8d, 400h
0x1800218f5  mov     rdx, [rsp+78h+arg_60]
0x1800218fd  mov     rcx, rbx
0x180021900  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021905  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002190c  test    rax, rax
0x18002190f  jz      short loc_180021919
0x180021911  mov     rcx, rbx
0x180021914  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021919  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180021920  test    rax, rax
0x180021923  jz      short loc_180021933
0x180021925  test    byte ptr [rbx+4], 2
0x180021929  jnz     short loc_180021933
0x18002192b  mov     rcx, rbx
0x18002192e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021933  cmp     [rbx+8], edi
0x180021936  jl      short loc_180021954
0x180021938  cmp     r15d, 3
0x18002193c  jz      short loc_180021944
0x18002193e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180021944  mov     ecx, 8000FFFFh; this
0x180021949  mov     [rbx+8], ecx
0x18002194c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180021951  mov     [rbx+0Ch], eax
0x180021954  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18002195b  jnz     short loc_180021982
0x18002195d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180021964  test    rax, rax
0x180021967  jz      short loc_180021972
0x180021969  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002196e  test    al, al
0x180021970  jmp     short loc_180021980
0x180021972  call    cs:__imp_IsDebuggerPresent
0x180021979  nop     dword ptr [rax+rax+00h]
0x18002197e  test    eax, eax
0x180021980  jz      short loc_180021988
0x180021982  test    byte ptr [rbx+4], 2
0x180021986  jz      short loc_1800219AC
0x180021988  mov     rax, cs:g_pfnResultLoggingCallback
0x18002198f  test    rax, rax
0x180021992  jz      short loc_1800219F6
0x180021994  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18002199b  jnz     short loc_1800219F6
0x18002199d  xor     r8d, r8d
0x1800219a0  xor     edx, edx
0x1800219a2  mov     rcx, rbx
0x1800219a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800219aa  jmp     short loc_1800219F6
0x1800219ac  mov     ebp, 800h
0x1800219b1  mov     rax, cs:g_pfnResultLoggingCallback
0x1800219b8  test    rax, rax
0x1800219bb  jz      short loc_1800219D4
0x1800219bd  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800219c4  jnz     short loc_1800219D4
0x1800219c6  mov     r8d, ebp
0x1800219c9  mov     rdx, rsi
0x1800219cc  mov     rcx, rbx
0x1800219cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800219d4  cmp     [rsi], di
0x1800219d7  jnz     short loc_1800219E7
0x1800219d9  mov     r8, rbx; unsigned __int64
0x1800219dc  mov     rdx, rbp; unsigned __int16 *
0x1800219df  mov     rcx, rsi; this
0x1800219e2  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800219e7  mov     rcx, rsi; lpOutputString
0x1800219ea  call    cs:__imp_OutputDebugStringW
0x1800219f1  nop     dword ptr [rax+rax+00h]
0x1800219f6  test    byte ptr [rbx+4], 4
0x1800219fa  jnz     short loc_180021A05
0x1800219fc  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180021a03  jz      short loc_180021A17
0x180021a05  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180021a0c  test    rax, rax
0x180021a0f  jz      short loc_180021A17
0x180021a11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a16  nop
0x180021a17  mov     rbx, [rsp+78h+arg_10]
0x180021a1f  add     rsp, 40h
0x180021a23  pop     r15
0x180021a25  pop     r14
0x180021a27  pop     r13
0x180021a29  pop     r12
0x180021a2b  pop     rdi
0x180021a2c  pop     rsi
0x180021a2d  pop     rbp
0x180021a2e  retn
```
