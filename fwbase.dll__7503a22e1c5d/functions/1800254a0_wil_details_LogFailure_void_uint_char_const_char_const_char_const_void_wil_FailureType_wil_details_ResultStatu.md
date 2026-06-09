# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800254a0`
- end: `0x18002579c`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `764`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180022070`

## callees

- `0x180021a50`
- `0x180024540`
- `0x180024d90`
- `0x1800254a0`
- `0x180026590`
- `0x1800265b0`
- `0x180026780`
- `0x1800267a0`
- `0x180029310`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800255c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800255c1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180025757`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180025757`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800256e4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800256e4`

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
  __int64 (*ModuleName)(void); // rax
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
  ModuleName = wil::details::g_pfnGetModuleName;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = (__int64 (*)(void))wil::details::g_pfnGetModuleName();
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
0x1800254a0  mov     [rsp+arg_10], rbx
0x1800254a5  mov     [rsp+arg_8], edx
0x1800254a9  mov     [rsp+arg_0], rcx
0x1800254ae  push    rbp
0x1800254af  push    rsi
0x1800254b0  push    rdi
0x1800254b1  push    r12
0x1800254b3  push    r13
0x1800254b5  push    r14
0x1800254b7  push    r15
0x1800254b9  sub     rsp, 40h
0x1800254bd  mov     r12, r9
0x1800254c0  mov     r13, r8
0x1800254c3  mov     r10, rcx
0x1800254c6  xor     eax, eax
0x1800254c8  mov     rsi, [rsp+78h+lpOutputString]
0x1800254d0  mov     [rsi], ax
0x1800254d3  mov     rax, [rsp+78h+arg_60]
0x1800254db  mov     byte ptr [rax], 0
0x1800254de  mov     r14, [rsp+78h+arg_38]
0x1800254e6  mov     edi, [r14]
0x1800254e9  mov     rbx, [rsp+78h+arg_78]
0x1800254f1  mov     [rbx+8], edi
0x1800254f4  mov     eax, [r14+4]
0x1800254f8  mov     [rbx+0Ch], eax
0x1800254fb  xor     ebp, ebp
0x1800254fd  mov     r15d, [rsp+78h+arg_30]
0x180025505  mov     ecx, r15d
0x180025508  test    r15d, r15d
0x18002550b  jz      short loc_180025573
0x18002550d  sub     ecx, 1
0x180025510  jz      short loc_18002556A
0x180025512  sub     ecx, 1
0x180025515  jz      short loc_180025525
0x180025517  cmp     ecx, 1
0x18002551a  jnz     short loc_18002557C
0x18002551c  mov     ecx, edi; this
0x18002551e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180025523  jmp     short loc_18002557A
0x180025525  test    edi, edi
0x180025527  js      short loc_180025561
0x180025529  mov     edi, 8007029Ch
0x18002552e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180025532  mov     rax, [rsp+78h+arg_28]
0x18002553a  mov     [rsp+78h+var_50], rax; __int64
0x18002553f  mov     rax, [rsp+78h+arg_20]
0x180025547  mov     [rsp+78h+var_58], rax; __int64
0x18002554c  mov     rcx, r10; int
0x18002554f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180025554  mov     [rbx+8], edi
0x180025557  mov     ecx, edi; this
0x180025559  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18002555e  mov     [rbx+0Ch], eax
0x180025561  mov     ecx, edi; this
0x180025563  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180025568  jmp     short loc_18002557A
0x18002556a  mov     ecx, edi; this
0x18002556c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180025571  jmp     short loc_18002557A
0x180025573  mov     ecx, edi; this
0x180025575  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18002557a  mov     ebp, eax
0x18002557c  mov     [rbx], r15d
0x18002557f  mov     eax, [rsp+78h+arg_70]
0x180025586  mov     [rbx+4], eax
0x180025589  cmp     dword ptr [r14+8], 1
0x18002558e  jnz     short loc_180025596
0x180025590  or      eax, 8
0x180025593  mov     [rbx+4], eax
0x180025596  mov     eax, 1
0x18002559b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800255a3  inc     eax
0x1800255a5  mov     [rbx+10h], eax
0x1800255a8  mov     rax, [rsp+78h+arg_40]
0x1800255b0  test    rax, rax
0x1800255b3  jz      short loc_1800255BB
0x1800255b5  cmp     word ptr [rax], 0
0x1800255b9  jnz     short loc_1800255BD
0x1800255bb  xor     eax, eax
0x1800255bd  mov     [rbx+18h], rax
0x1800255c1  call    cs:__imp_GetCurrentThreadId
0x1800255c7  mov     [rbx+20h], eax
0x1800255ca  mov     [rbx+38h], r13
0x1800255ce  mov     eax, [rsp+78h+arg_8]
0x1800255d5  mov     [rbx+40h], eax
0x1800255d8  mov     [rbx+44h], ebp
0x1800255db  mov     rax, [rsp+78h+arg_20]
0x1800255e3  mov     [rbx+28h], rax
0x1800255e7  mov     [rbx+30h], r12
0x1800255eb  mov     rax, [rsp+78h+arg_28]
0x1800255f3  mov     [rbx+88h], rax
0x1800255fa  mov     rax, [rsp+78h+arg_0]
0x180025602  mov     [rbx+90h], rax
0x180025609  mov     qword ptr [rbx+48h], 0
0x180025611  xorps   xmm0, xmm0
0x180025614  xor     eax, eax
0x180025616  movups  xmmword ptr [rbx+68h], xmm0
0x18002561a  mov     [rbx+78h], rax
0x18002561e  movups  xmmword ptr [rbx+50h], xmm0
0x180025622  mov     [rbx+60h], rax
0x180025626  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18002562d  test    rax, rax
0x180025630  jz      short loc_180025637
0x180025632  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025637  mov     [rbx+80h], rax
0x18002563e  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180025645  test    rax, rax
0x180025648  jz      short loc_180025652
0x18002564a  mov     rcx, rbx
0x18002564d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025652  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180025659  test    rax, rax
0x18002565c  jz      short loc_180025674
0x18002565e  mov     r8d, 400h
0x180025664  mov     rdx, [rsp+78h+arg_60]
0x18002566c  mov     rcx, rbx
0x18002566f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025674  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002567b  test    rax, rax
0x18002567e  jz      short loc_180025688
0x180025680  mov     rcx, rbx
0x180025683  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025688  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002568f  test    rax, rax
0x180025692  jz      short loc_1800256A2
0x180025694  test    byte ptr [rbx+4], 2
0x180025698  jnz     short loc_1800256A2
0x18002569a  mov     rcx, rbx
0x18002569d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800256a2  cmp     dword ptr [rbx+8], 0
0x1800256a6  jl      short loc_1800256C6
0x1800256a8  cmp     r15d, 3
0x1800256ac  jnz     loc_180025796
0x1800256b2  mov     dword ptr [rbx+8], 8000FFFFh
0x1800256b9  mov     ecx, 8000FFFFh; this
0x1800256be  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800256c3  mov     [rbx+0Ch], eax
0x1800256c6  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, 0; bool wil::g_fIsDebuggerPresent
0x1800256cd  jnz     short loc_1800256EE
0x1800256cf  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800256d6  test    rax, rax
0x1800256d9  jz      short loc_1800256E4
0x1800256db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800256e0  test    al, al
0x1800256e2  jmp     short loc_1800256EC
0x1800256e4  call    cs:__imp_IsDebuggerPresent
0x1800256ea  test    eax, eax
0x1800256ec  jz      short loc_1800256F4
0x1800256ee  test    byte ptr [rbx+4], 2
0x1800256f2  jz      short loc_180025718
0x1800256f4  mov     rax, cs:g_pfnResultLoggingCallback
0x1800256fb  test    rax, rax
0x1800256fe  jz      short loc_18002575D
0x180025700  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x180025707  jnz     short loc_18002575D
0x180025709  xor     r8d, r8d
0x18002570c  xor     edx, edx
0x18002570e  mov     rcx, rbx
0x180025711  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025716  jmp     short loc_18002575D
0x180025718  mov     rax, cs:g_pfnResultLoggingCallback
0x18002571f  test    rax, rax
0x180025722  jz      short loc_18002573E
0x180025724  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x18002572b  jnz     short loc_18002573E
0x18002572d  mov     r8d, 800h
0x180025733  mov     rdx, rsi
0x180025736  mov     rcx, rbx
0x180025739  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002573e  cmp     word ptr [rsi], 0
0x180025742  jnz     short loc_180025754
0x180025744  mov     r8, rbx; unsigned __int64
0x180025747  mov     edx, 800h; unsigned __int16 *
0x18002574c  mov     rcx, rsi; this
0x18002574f  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180025754  mov     rcx, rsi; lpOutputString
0x180025757  call    cs:__imp_OutputDebugStringW
0x18002575d  test    byte ptr [rbx+4], 4
0x180025761  jnz     short loc_18002576C
0x180025763  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, 0; bool wil::g_fBreakOnFailure
0x18002576a  jz      short loc_18002577E
0x18002576c  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180025773  test    rax, rax
0x180025776  jz      short loc_18002577E
0x180025778  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002577d  nop
0x18002577e  mov     rbx, [rsp+78h+arg_10]
0x180025786  add     rsp, 40h
0x18002578a  pop     r15
0x18002578c  pop     r14
0x18002578e  pop     r13
0x180025790  pop     r12
0x180025792  pop     rdi
0x180025793  pop     rsi
0x180025794  pop     rbp
0x180025795  retn
0x180025796  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
