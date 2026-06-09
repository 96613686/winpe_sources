# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180075528`
- end: `0x18007581c`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `756`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180073a8c`
- `0x180073b3c`
- `0x180073c30`

## callees

- `0x1800455c0`
- `0x1800739e0`
- `0x180074c94`
- `0x180075528`
- `0x180076188`
- `0x1800761b0`
- `0x180076274`
- `0x180076290`
- `0x180077bac`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800757de`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800757de`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18007576c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18007576c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007564b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007564b`

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
  const struct wil::FailureInfo *v26; // r9
  __int64 ModuleName; // rax
  bool v28; // zf
  wil::details *v29; // [rsp+30h] [rbp-48h]

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
          LODWORD(v29) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v29);
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
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v28 = !IsDebuggerPresent())
      : (v28 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v28)
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
0x180075528  mov     [rsp+arg_10], rbx
0x18007552d  mov     [rsp+arg_8], edx
0x180075531  mov     [rsp+arg_0], rcx
0x180075536  push    rbp
0x180075537  push    rsi
0x180075538  push    rdi
0x180075539  push    r12
0x18007553b  push    r13
0x18007553d  push    r14
0x18007553f  push    r15
0x180075541  sub     rsp, 40h
0x180075545  mov     r14, [rsp+78h+arg_38]
0x18007554d  xor     eax, eax
0x18007554f  mov     rbx, [rsp+78h+arg_78]
0x180075557  xor     ebp, ebp
0x180075559  mov     r15d, [rsp+78h+arg_30]
0x180075561  mov     r10, rcx
0x180075564  mov     rsi, [rsp+78h+lpOutputString]
0x18007556c  mov     r12, r9
0x18007556f  mov     r13, r8
0x180075572  mov     ecx, r15d
0x180075575  mov     [rsi], ax
0x180075578  mov     rax, [rsp+78h+arg_60]
0x180075580  mov     byte ptr [rax], 0
0x180075583  mov     edi, [r14]
0x180075586  mov     [rbx+8], edi
0x180075589  mov     eax, [r14+4]
0x18007558d  mov     [rbx+0Ch], eax
0x180075590  test    r15d, r15d
0x180075593  jz      short loc_1800755FB
0x180075595  sub     ecx, 1
0x180075598  jz      short loc_1800755F2
0x18007559a  sub     ecx, 1
0x18007559d  jz      short loc_1800755AD
0x18007559f  cmp     ecx, 1
0x1800755a2  jnz     short loc_180075604
0x1800755a4  mov     ecx, edi; this
0x1800755a6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800755ab  jmp     short loc_180075602
0x1800755ad  test    edi, edi
0x1800755af  js      short loc_1800755E9
0x1800755b1  mov     rax, [rsp+78h+arg_28]
0x1800755b9  mov     edi, 8007029Ch
0x1800755be  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800755c2  mov     rcx, r10; int
0x1800755c5  mov     [rsp+78h+var_50], rax; __int64
0x1800755ca  mov     rax, [rsp+78h+arg_20]
0x1800755d2  mov     [rsp+78h+var_58], rax; __int64
0x1800755d7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800755dc  mov     ecx, edi; this
0x1800755de  mov     [rbx+8], edi
0x1800755e1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800755e6  mov     [rbx+0Ch], eax
0x1800755e9  mov     ecx, edi; this
0x1800755eb  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800755f0  jmp     short loc_180075602
0x1800755f2  mov     ecx, edi; this
0x1800755f4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800755f9  jmp     short loc_180075602
0x1800755fb  mov     ecx, edi; this
0x1800755fd  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180075602  mov     ebp, eax
0x180075604  mov     eax, [rsp+78h+arg_70]
0x18007560b  mov     [rbx+4], eax
0x18007560e  mov     [rbx], r15d
0x180075611  cmp     dword ptr [r14+8], 1
0x180075616  jnz     short loc_18007561E
0x180075618  or      eax, 8
0x18007561b  mov     [rbx+4], eax
0x18007561e  mov     eax, 1
0x180075623  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18007562b  inc     eax
0x18007562d  xor     edi, edi
0x18007562f  mov     [rbx+10h], eax
0x180075632  mov     rax, [rsp+78h+arg_40]
0x18007563a  test    rax, rax
0x18007563d  jz      short loc_180075644
0x18007563f  cmp     [rax], di
0x180075642  jnz     short loc_180075647
0x180075644  mov     rax, rdi
0x180075647  mov     [rbx+18h], rax
0x18007564b  call    cs:__imp_GetCurrentThreadId
0x180075651  mov     [rbx+38h], r13
0x180075655  xorps   xmm0, xmm0
0x180075658  mov     [rbx+20h], eax
0x18007565b  mov     eax, [rsp+78h+arg_8]
0x180075662  mov     [rbx+40h], eax
0x180075665  mov     rax, [rsp+78h+arg_20]
0x18007566d  mov     [rbx+28h], rax
0x180075671  mov     rax, [rsp+78h+arg_28]
0x180075679  mov     [rbx+88h], rax
0x180075680  mov     rax, [rsp+78h+arg_0]
0x180075688  mov     [rbx+90h], rax
0x18007568f  xor     eax, eax
0x180075691  mov     [rbx+44h], ebp
0x180075694  mov     [rbx+30h], r12
0x180075698  mov     [rbx+48h], rdi
0x18007569c  movups  xmmword ptr [rbx+68h], xmm0
0x1800756a0  mov     [rbx+78h], rax
0x1800756a4  movups  xmmword ptr [rbx+50h], xmm0
0x1800756a8  mov     [rbx+60h], rax
0x1800756ac  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800756b3  test    rax, rax
0x1800756b6  jz      short loc_1800756BF
0x1800756b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800756bd  jmp     short loc_1800756C2
0x1800756bf  mov     rax, rdi
0x1800756c2  mov     [rbx+80h], rax
0x1800756c9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800756d0  test    rax, rax
0x1800756d3  jz      short loc_1800756DD
0x1800756d5  mov     rcx, rbx
0x1800756d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800756dd  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800756e4  test    rax, rax
0x1800756e7  jz      short loc_1800756FF
0x1800756e9  mov     rdx, [rsp+78h+arg_60]
0x1800756f1  mov     r8d, 400h
0x1800756f7  mov     rcx, rbx
0x1800756fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800756ff  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180075706  test    rax, rax
0x180075709  jz      short loc_180075713
0x18007570b  mov     rcx, rbx
0x18007570e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075713  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18007571a  test    rax, rax
0x18007571d  jz      short loc_18007572D
0x18007571f  test    byte ptr [rbx+4], 2
0x180075723  jnz     short loc_18007572D
0x180075725  mov     rcx, rbx
0x180075728  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007572d  cmp     [rbx+8], edi
0x180075730  jl      short loc_18007574E
0x180075732  cmp     r15d, 3
0x180075736  jz      short loc_18007573E
0x180075738  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18007573e  mov     ecx, 8000FFFFh; this
0x180075743  mov     [rbx+8], ecx
0x180075746  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18007574b  mov     [rbx+0Ch], eax
0x18007574e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180075755  jnz     short loc_180075776
0x180075757  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18007575e  test    rax, rax
0x180075761  jz      short loc_18007576C
0x180075763  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075768  test    al, al
0x18007576a  jmp     short loc_180075774
0x18007576c  call    cs:__imp_IsDebuggerPresent
0x180075772  test    eax, eax
0x180075774  jz      short loc_18007577C
0x180075776  test    byte ptr [rbx+4], 2
0x18007577a  jz      short loc_1800757A0
0x18007577c  mov     rax, cs:g_pfnResultLoggingCallback
0x180075783  test    rax, rax
0x180075786  jz      short loc_1800757E4
0x180075788  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18007578f  jnz     short loc_1800757E4
0x180075791  xor     r8d, r8d
0x180075794  xor     edx, edx
0x180075796  mov     rcx, rbx
0x180075799  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007579e  jmp     short loc_1800757E4
0x1800757a0  mov     rax, cs:g_pfnResultLoggingCallback
0x1800757a7  mov     ebp, 800h
0x1800757ac  test    rax, rax
0x1800757af  jz      short loc_1800757C8
0x1800757b1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800757b8  jnz     short loc_1800757C8
0x1800757ba  mov     r8d, ebp
0x1800757bd  mov     rdx, rsi
0x1800757c0  mov     rcx, rbx
0x1800757c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800757c8  cmp     [rsi], di
0x1800757cb  jnz     short loc_1800757DB
0x1800757cd  mov     r8, rbx; unsigned __int64
0x1800757d0  mov     rdx, rbp; unsigned __int16 *
0x1800757d3  mov     rcx, rsi; this
0x1800757d6  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800757db  mov     rcx, rsi; lpOutputString
0x1800757de  call    cs:__imp_OutputDebugStringW
0x1800757e4  test    byte ptr [rbx+4], 4
0x1800757e8  jnz     short loc_1800757F3
0x1800757ea  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800757f1  jz      short loc_180075804
0x1800757f3  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800757fa  test    rax, rax
0x1800757fd  jz      short loc_180075804
0x1800757ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075804  mov     rbx, [rsp+78h+arg_10]
0x18007580c  add     rsp, 40h
0x180075810  pop     r15
0x180075812  pop     r14
0x180075814  pop     r13
0x180075816  pop     r12
0x180075818  pop     rdi
0x180075819  pop     rsi
0x18007581a  pop     rbp
0x18007581b  retn
```
