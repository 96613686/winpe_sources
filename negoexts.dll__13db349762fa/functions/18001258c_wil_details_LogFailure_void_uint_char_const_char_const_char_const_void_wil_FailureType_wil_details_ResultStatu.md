# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18001258c`
- end: `0x180012880`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `756`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x1800103d0`
- `0x180010480`
- `0x180010574`

## callees

- `0x180010324`
- `0x1800119d4`
- `0x1800121ac`
- `0x18001258c`
- `0x180013328`
- `0x180013350`
- `0x18001340c`
- `0x180013428`
- `0x18001509c`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800126af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800126af`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180012842`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180012842`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800127d0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800127d0`

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
  *lpOutputString = 0;
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
    if ( !*lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v26);
    OutputDebugStringW(lpOutputString);
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
0x18001258c  mov     [rsp+arg_10], rbx
0x180012591  mov     [rsp+arg_8], edx
0x180012595  mov     [rsp+arg_0], rcx
0x18001259a  push    rbp
0x18001259b  push    rsi
0x18001259c  push    rdi
0x18001259d  push    r12
0x18001259f  push    r13
0x1800125a1  push    r14
0x1800125a3  push    r15
0x1800125a5  sub     rsp, 40h
0x1800125a9  mov     r14, [rsp+78h+arg_38]
0x1800125b1  xor     eax, eax
0x1800125b3  mov     rbx, [rsp+78h+arg_78]
0x1800125bb  xor     ebp, ebp
0x1800125bd  mov     r15d, [rsp+78h+arg_30]
0x1800125c5  mov     r10, rcx
0x1800125c8  mov     rsi, [rsp+78h+lpOutputString]
0x1800125d0  mov     r12, r9
0x1800125d3  mov     r13, r8
0x1800125d6  mov     ecx, r15d
0x1800125d9  mov     [rsi], ax
0x1800125dc  mov     rax, [rsp+78h+arg_60]
0x1800125e4  mov     byte ptr [rax], 0
0x1800125e7  mov     edi, [r14]
0x1800125ea  mov     [rbx+8], edi
0x1800125ed  mov     eax, [r14+4]
0x1800125f1  mov     [rbx+0Ch], eax
0x1800125f4  test    r15d, r15d
0x1800125f7  jz      short loc_18001265F
0x1800125f9  sub     ecx, 1
0x1800125fc  jz      short loc_180012656
0x1800125fe  sub     ecx, 1
0x180012601  jz      short loc_180012611
0x180012603  cmp     ecx, 1
0x180012606  jnz     short loc_180012668
0x180012608  mov     ecx, edi; this
0x18001260a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18001260f  jmp     short loc_180012666
0x180012611  test    edi, edi
0x180012613  js      short loc_18001264D
0x180012615  mov     rax, [rsp+78h+arg_28]
0x18001261d  mov     edi, 8007029Ch
0x180012622  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180012626  mov     rcx, r10; int
0x180012629  mov     [rsp+78h+var_50], rax; __int64
0x18001262e  mov     rax, [rsp+78h+arg_20]
0x180012636  mov     [rsp+78h+var_58], rax; __int64
0x18001263b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180012640  mov     ecx, edi; this
0x180012642  mov     [rbx+8], edi
0x180012645  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001264a  mov     [rbx+0Ch], eax
0x18001264d  mov     ecx, edi; this
0x18001264f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180012654  jmp     short loc_180012666
0x180012656  mov     ecx, edi; this
0x180012658  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18001265d  jmp     short loc_180012666
0x18001265f  mov     ecx, edi; this
0x180012661  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180012666  mov     ebp, eax
0x180012668  mov     eax, [rsp+78h+arg_70]
0x18001266f  mov     [rbx+4], eax
0x180012672  mov     [rbx], r15d
0x180012675  cmp     dword ptr [r14+8], 1
0x18001267a  jnz     short loc_180012682
0x18001267c  or      eax, 8
0x18001267f  mov     [rbx+4], eax
0x180012682  mov     eax, 1
0x180012687  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18001268f  inc     eax
0x180012691  xor     edi, edi
0x180012693  mov     [rbx+10h], eax
0x180012696  mov     rax, [rsp+78h+arg_40]
0x18001269e  test    rax, rax
0x1800126a1  jz      short loc_1800126A8
0x1800126a3  cmp     [rax], di
0x1800126a6  jnz     short loc_1800126AB
0x1800126a8  mov     rax, rdi
0x1800126ab  mov     [rbx+18h], rax
0x1800126af  call    cs:__imp_GetCurrentThreadId
0x1800126b5  mov     [rbx+38h], r13
0x1800126b9  xorps   xmm0, xmm0
0x1800126bc  mov     [rbx+20h], eax
0x1800126bf  mov     eax, [rsp+78h+arg_8]
0x1800126c6  mov     [rbx+40h], eax
0x1800126c9  mov     rax, [rsp+78h+arg_20]
0x1800126d1  mov     [rbx+28h], rax
0x1800126d5  mov     rax, [rsp+78h+arg_28]
0x1800126dd  mov     [rbx+88h], rax
0x1800126e4  mov     rax, [rsp+78h+arg_0]
0x1800126ec  mov     [rbx+90h], rax
0x1800126f3  xor     eax, eax
0x1800126f5  mov     [rbx+44h], ebp
0x1800126f8  mov     [rbx+30h], r12
0x1800126fc  mov     [rbx+48h], rdi
0x180012700  movups  xmmword ptr [rbx+68h], xmm0
0x180012704  mov     [rbx+78h], rax
0x180012708  movups  xmmword ptr [rbx+50h], xmm0
0x18001270c  mov     [rbx+60h], rax
0x180012710  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180012717  test    rax, rax
0x18001271a  jz      short loc_180012723
0x18001271c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012721  jmp     short loc_180012726
0x180012723  mov     rax, rdi
0x180012726  mov     [rbx+80h], rax
0x18001272d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180012734  test    rax, rax
0x180012737  jz      short loc_180012741
0x180012739  mov     rcx, rbx
0x18001273c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012741  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180012748  test    rax, rax
0x18001274b  jz      short loc_180012763
0x18001274d  mov     rdx, [rsp+78h+arg_60]
0x180012755  mov     r8d, 400h
0x18001275b  mov     rcx, rbx
0x18001275e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012763  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001276a  test    rax, rax
0x18001276d  jz      short loc_180012777
0x18001276f  mov     rcx, rbx
0x180012772  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012777  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001277e  test    rax, rax
0x180012781  jz      short loc_180012791
0x180012783  test    byte ptr [rbx+4], 2
0x180012787  jnz     short loc_180012791
0x180012789  mov     rcx, rbx
0x18001278c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012791  cmp     [rbx+8], edi
0x180012794  jl      short loc_1800127B2
0x180012796  cmp     r15d, 3
0x18001279a  jz      short loc_1800127A2
0x18001279c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800127a2  mov     ecx, 8000FFFFh; this
0x1800127a7  mov     [rbx+8], ecx
0x1800127aa  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800127af  mov     [rbx+0Ch], eax
0x1800127b2  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800127b9  jnz     short loc_1800127DA
0x1800127bb  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800127c2  test    rax, rax
0x1800127c5  jz      short loc_1800127D0
0x1800127c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127cc  test    al, al
0x1800127ce  jmp     short loc_1800127D8
0x1800127d0  call    cs:__imp_IsDebuggerPresent
0x1800127d6  test    eax, eax
0x1800127d8  jz      short loc_1800127E0
0x1800127da  test    byte ptr [rbx+4], 2
0x1800127de  jz      short loc_180012804
0x1800127e0  mov     rax, cs:g_pfnResultLoggingCallback
0x1800127e7  test    rax, rax
0x1800127ea  jz      short loc_180012848
0x1800127ec  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800127f3  jnz     short loc_180012848
0x1800127f5  xor     r8d, r8d
0x1800127f8  xor     edx, edx
0x1800127fa  mov     rcx, rbx
0x1800127fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012802  jmp     short loc_180012848
0x180012804  mov     rax, cs:g_pfnResultLoggingCallback
0x18001280b  mov     ebp, 800h
0x180012810  test    rax, rax
0x180012813  jz      short loc_18001282C
0x180012815  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001281c  jnz     short loc_18001282C
0x18001281e  mov     r8d, ebp
0x180012821  mov     rdx, rsi
0x180012824  mov     rcx, rbx
0x180012827  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001282c  cmp     [rsi], di
0x18001282f  jnz     short loc_18001283F
0x180012831  mov     r8, rbx; unsigned __int64
0x180012834  mov     rdx, rbp; unsigned __int16 *
0x180012837  mov     rcx, rsi; pszDest
0x18001283a  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18001283f  mov     rcx, rsi; lpOutputString
0x180012842  call    cs:__imp_OutputDebugStringW
0x180012848  test    byte ptr [rbx+4], 4
0x18001284c  jnz     short loc_180012857
0x18001284e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180012855  jz      short loc_180012868
0x180012857  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001285e  test    rax, rax
0x180012861  jz      short loc_180012868
0x180012863  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012868  mov     rbx, [rsp+78h+arg_10]
0x180012870  add     rsp, 40h
0x180012874  pop     r15
0x180012876  pop     r14
0x180012878  pop     r13
0x18001287a  pop     r12
0x18001287c  pop     rdi
0x18001287d  pop     rsi
0x18001287e  pop     rbp
0x18001287f  retn
```
