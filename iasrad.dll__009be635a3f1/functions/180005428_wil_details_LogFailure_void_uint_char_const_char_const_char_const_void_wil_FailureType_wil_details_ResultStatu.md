# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180005428`
- end: `0x18000571d`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x1800028a0`
- `0x180002950`
- `0x180002a44`

## callees

- `0x1800027f4`
- `0x180004394`
- `0x180004aa0`
- `0x180005428`
- `0x180006230`
- `0x180006250`
- `0x1800063d4`
- `0x1800063f0`
- `0x18000855c`
- `0x180030010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000554b`
- `KERNEL32!GetCurrentThreadId` at `0x18000554b`
- `KERNEL32!IsDebuggerPresent` at `0x18000566c`
- `KERNEL32!IsDebuggerPresent` at `0x18000566c`
- `KERNEL32!OutputDebugStringW` at `0x1800056de`
- `KERNEL32!OutputDebugStringW` at `0x1800056de`

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
0x180005428  mov     [rsp+arg_10], rbx
0x18000542d  mov     [rsp+arg_8], edx
0x180005431  mov     [rsp+arg_0], rcx
0x180005436  push    rbp
0x180005437  push    rsi
0x180005438  push    rdi
0x180005439  push    r12
0x18000543b  push    r13
0x18000543d  push    r14
0x18000543f  push    r15
0x180005441  sub     rsp, 40h
0x180005445  mov     r12, r9
0x180005448  mov     r13, r8
0x18000544b  mov     r10, rcx
0x18000544e  xor     eax, eax
0x180005450  mov     rsi, [rsp+78h+lpOutputString]
0x180005458  mov     [rsi], ax
0x18000545b  mov     rax, [rsp+78h+arg_60]
0x180005463  mov     byte ptr [rax], 0
0x180005466  mov     r14, [rsp+78h+arg_38]
0x18000546e  mov     edi, [r14]
0x180005471  mov     rbx, [rsp+78h+arg_78]
0x180005479  mov     [rbx+8], edi
0x18000547c  mov     eax, [r14+4]
0x180005480  mov     [rbx+0Ch], eax
0x180005483  xor     ebp, ebp
0x180005485  mov     r15d, [rsp+78h+arg_30]
0x18000548d  mov     ecx, r15d
0x180005490  test    r15d, r15d
0x180005493  jz      short loc_1800054FB
0x180005495  sub     ecx, 1
0x180005498  jz      short loc_1800054F2
0x18000549a  sub     ecx, 1
0x18000549d  jz      short loc_1800054AD
0x18000549f  cmp     ecx, 1
0x1800054a2  jnz     short loc_180005504
0x1800054a4  mov     ecx, edi; this
0x1800054a6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800054ab  jmp     short loc_180005502
0x1800054ad  test    edi, edi
0x1800054af  js      short loc_1800054E9
0x1800054b1  mov     edi, 8007029Ch
0x1800054b6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800054ba  mov     rax, [rsp+78h+arg_28]
0x1800054c2  mov     [rsp+78h+var_50], rax; __int64
0x1800054c7  mov     rax, [rsp+78h+arg_20]
0x1800054cf  mov     [rsp+78h+var_58], rax; __int64
0x1800054d4  mov     rcx, r10; int
0x1800054d7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800054dc  mov     [rbx+8], edi
0x1800054df  mov     ecx, edi; this
0x1800054e1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800054e6  mov     [rbx+0Ch], eax
0x1800054e9  mov     ecx, edi; this
0x1800054eb  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800054f0  jmp     short loc_180005502
0x1800054f2  mov     ecx, edi; this
0x1800054f4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800054f9  jmp     short loc_180005502
0x1800054fb  mov     ecx, edi; this
0x1800054fd  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180005502  mov     ebp, eax
0x180005504  mov     [rbx], r15d
0x180005507  mov     eax, [rsp+78h+arg_70]
0x18000550e  mov     [rbx+4], eax
0x180005511  cmp     dword ptr [r14+8], 1
0x180005516  jnz     short loc_18000551E
0x180005518  or      eax, 8
0x18000551b  mov     [rbx+4], eax
0x18000551e  mov     eax, 1
0x180005523  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000552b  inc     eax
0x18000552d  mov     [rbx+10h], eax
0x180005530  mov     rax, [rsp+78h+arg_40]
0x180005538  xor     edi, edi
0x18000553a  test    rax, rax
0x18000553d  jz      short loc_180005544
0x18000553f  cmp     [rax], di
0x180005542  jnz     short loc_180005547
0x180005544  mov     rax, rdi
0x180005547  mov     [rbx+18h], rax
0x18000554b  call    cs:__imp_GetCurrentThreadId
0x180005551  mov     [rbx+20h], eax
0x180005554  mov     [rbx+38h], r13
0x180005558  mov     eax, [rsp+78h+arg_8]
0x18000555f  mov     [rbx+40h], eax
0x180005562  mov     [rbx+44h], ebp
0x180005565  mov     rax, [rsp+78h+arg_20]
0x18000556d  mov     [rbx+28h], rax
0x180005571  mov     [rbx+30h], r12
0x180005575  mov     rax, [rsp+78h+arg_28]
0x18000557d  mov     [rbx+88h], rax
0x180005584  mov     rax, [rsp+78h+arg_0]
0x18000558c  mov     [rbx+90h], rax
0x180005593  mov     [rbx+48h], rdi
0x180005597  xorps   xmm0, xmm0
0x18000559a  xor     eax, eax
0x18000559c  movups  xmmword ptr [rbx+68h], xmm0
0x1800055a0  mov     [rbx+78h], rax
0x1800055a4  movups  xmmword ptr [rbx+50h], xmm0
0x1800055a8  mov     [rbx+60h], rax
0x1800055ac  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800055b3  test    rax, rax
0x1800055b6  jz      short loc_1800055BF
0x1800055b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055bd  jmp     short loc_1800055C2
0x1800055bf  mov     rax, rdi
0x1800055c2  mov     [rbx+80h], rax
0x1800055c9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800055d0  test    rax, rax
0x1800055d3  jz      short loc_1800055DD
0x1800055d5  mov     rcx, rbx
0x1800055d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055dd  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800055e4  test    rax, rax
0x1800055e7  jz      short loc_1800055FF
0x1800055e9  mov     r8d, 400h
0x1800055ef  mov     rdx, [rsp+78h+arg_60]
0x1800055f7  mov     rcx, rbx
0x1800055fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055ff  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005606  test    rax, rax
0x180005609  jz      short loc_180005613
0x18000560b  mov     rcx, rbx
0x18000560e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005613  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000561a  test    rax, rax
0x18000561d  jz      short loc_18000562D
0x18000561f  test    byte ptr [rbx+4], 2
0x180005623  jnz     short loc_18000562D
0x180005625  mov     rcx, rbx
0x180005628  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000562d  cmp     [rbx+8], edi
0x180005630  jl      short loc_18000564E
0x180005632  cmp     r15d, 3
0x180005636  jz      short loc_18000563E
0x180005638  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000563e  mov     ecx, 8000FFFFh; this
0x180005643  mov     [rbx+8], ecx
0x180005646  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000564b  mov     [rbx+0Ch], eax
0x18000564e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180005655  jnz     short loc_180005676
0x180005657  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000565e  test    rax, rax
0x180005661  jz      short loc_18000566C
0x180005663  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005668  test    al, al
0x18000566a  jmp     short loc_180005674
0x18000566c  call    cs:__imp_IsDebuggerPresent
0x180005672  test    eax, eax
0x180005674  jz      short loc_18000567C
0x180005676  test    byte ptr [rbx+4], 2
0x18000567a  jz      short loc_1800056A0
0x18000567c  mov     rax, cs:g_pfnResultLoggingCallback
0x180005683  test    rax, rax
0x180005686  jz      short loc_1800056E4
0x180005688  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000568f  jnz     short loc_1800056E4
0x180005691  xor     r8d, r8d
0x180005694  xor     edx, edx
0x180005696  mov     rcx, rbx
0x180005699  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000569e  jmp     short loc_1800056E4
0x1800056a0  mov     ebp, 800h
0x1800056a5  mov     rax, cs:g_pfnResultLoggingCallback
0x1800056ac  test    rax, rax
0x1800056af  jz      short loc_1800056C8
0x1800056b1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800056b8  jnz     short loc_1800056C8
0x1800056ba  mov     r8d, ebp
0x1800056bd  mov     rdx, rsi
0x1800056c0  mov     rcx, rbx
0x1800056c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056c8  cmp     [rsi], di
0x1800056cb  jnz     short loc_1800056DB
0x1800056cd  mov     r8, rbx; unsigned __int64
0x1800056d0  mov     rdx, rbp; unsigned __int16 *
0x1800056d3  mov     rcx, rsi; this
0x1800056d6  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800056db  mov     rcx, rsi; lpOutputString
0x1800056de  call    cs:__imp_OutputDebugStringW
0x1800056e4  test    byte ptr [rbx+4], 4
0x1800056e8  jnz     short loc_1800056F3
0x1800056ea  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800056f1  jz      short loc_180005705
0x1800056f3  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800056fa  test    rax, rax
0x1800056fd  jz      short loc_180005705
0x1800056ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005704  nop
0x180005705  mov     rbx, [rsp+78h+arg_10]
0x18000570d  add     rsp, 40h
0x180005711  pop     r15
0x180005713  pop     r14
0x180005715  pop     r13
0x180005717  pop     r12
0x180005719  pop     rdi
0x18000571a  pop     rsi
0x18000571b  pop     rbp
0x18000571c  retn
```
