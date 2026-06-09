# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1400086ac`
- end: `0x1400089a5`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140004104`

## callees

- `0x140003b10`
- `0x1400073e4`
- `0x140007cd4`
- `0x1400086ac`
- `0x1400095a0`
- `0x1400095c0`
- `0x1400096ec`
- `0x140009708`
- `0x14000cdec`
- `0x140011010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400087cf`
- `KERNEL32!GetCurrentThreadId` at `0x1400087cf`
- `KERNEL32!IsDebuggerPresent` at `0x1400088ee`
- `KERNEL32!IsDebuggerPresent` at `0x1400088ee`
- `KERNEL32!OutputDebugStringW` at `0x140008960`
- `KERNEL32!OutputDebugStringW` at `0x140008960`

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
  _WORD *v21; // rax
  wil::details::in1diag3 *v22; // rcx
  const struct wil::FailureInfo *v23; // r9
  __int64 ModuleName; // rax
  bool v25; // zf
  wil::details *v26; // [rsp+30h] [rbp-48h]

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
          LODWORD(v26) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v26);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL);
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
  v21 = a9;
  if ( !a9 || !*a9 )
    v21 = 0;
  *(_QWORD *)(a16 + 24) = v21;
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
    ModuleName = wil::details::g_pfnGetModuleName(v22);
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v25 = !IsDebuggerPresent())
      : (v25 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v22) == 0),
        v25)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v23);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v22);
  }
}

```

## disassembly

```asm
0x1400086ac  mov     [rsp+arg_10], rbx
0x1400086b1  mov     [rsp+arg_8], edx
0x1400086b5  mov     [rsp+arg_0], rcx
0x1400086ba  push    rbp
0x1400086bb  push    rsi
0x1400086bc  push    rdi
0x1400086bd  push    r12
0x1400086bf  push    r13
0x1400086c1  push    r14
0x1400086c3  push    r15
0x1400086c5  sub     rsp, 40h
0x1400086c9  mov     r12, r9
0x1400086cc  mov     r13, r8
0x1400086cf  mov     r10, rcx
0x1400086d2  xor     eax, eax
0x1400086d4  mov     rsi, [rsp+78h+lpOutputString]
0x1400086dc  mov     [rsi], ax
0x1400086df  mov     rax, [rsp+78h+arg_60]
0x1400086e7  mov     byte ptr [rax], 0
0x1400086ea  mov     r14, [rsp+78h+arg_38]
0x1400086f2  mov     edi, [r14]
0x1400086f5  mov     rbx, [rsp+78h+arg_78]
0x1400086fd  mov     [rbx+8], edi
0x140008700  mov     eax, [r14+4]
0x140008704  mov     [rbx+0Ch], eax
0x140008707  xor     ebp, ebp
0x140008709  mov     r15d, [rsp+78h+arg_30]
0x140008711  mov     ecx, r15d
0x140008714  test    r15d, r15d
0x140008717  jz      short loc_14000877F
0x140008719  sub     ecx, 1
0x14000871c  jz      short loc_140008776
0x14000871e  sub     ecx, 1
0x140008721  jz      short loc_140008731
0x140008723  cmp     ecx, 1
0x140008726  jnz     short loc_140008788
0x140008728  mov     ecx, edi; this
0x14000872a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x14000872f  jmp     short loc_140008786
0x140008731  test    edi, edi
0x140008733  js      short loc_14000876D
0x140008735  mov     edi, 8007029Ch
0x14000873a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x14000873e  mov     rax, [rsp+78h+arg_28]
0x140008746  mov     [rsp+78h+var_50], rax; __int64
0x14000874b  mov     rax, [rsp+78h+arg_20]
0x140008753  mov     [rsp+78h+var_58], rax; __int64
0x140008758  mov     rcx, r10; int
0x14000875b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140008760  mov     [rbx+8], edi
0x140008763  mov     ecx, edi; this
0x140008765  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000876a  mov     [rbx+0Ch], eax
0x14000876d  mov     ecx, edi; this
0x14000876f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140008774  jmp     short loc_140008786
0x140008776  mov     ecx, edi; this
0x140008778  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x14000877d  jmp     short loc_140008786
0x14000877f  mov     ecx, edi; this
0x140008781  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140008786  mov     ebp, eax
0x140008788  mov     [rbx], r15d
0x14000878b  mov     eax, [rsp+78h+arg_70]
0x140008792  mov     [rbx+4], eax
0x140008795  cmp     dword ptr [r14+8], 1
0x14000879a  jnz     short loc_1400087A2
0x14000879c  or      eax, 8
0x14000879f  mov     [rbx+4], eax
0x1400087a2  mov     eax, 1
0x1400087a7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400087af  inc     eax
0x1400087b1  mov     [rbx+10h], eax
0x1400087b4  mov     rax, [rsp+78h+arg_40]
0x1400087bc  xor     edi, edi
0x1400087be  test    rax, rax
0x1400087c1  jz      short loc_1400087C8
0x1400087c3  cmp     [rax], di
0x1400087c6  jnz     short loc_1400087CB
0x1400087c8  mov     rax, rdi
0x1400087cb  mov     [rbx+18h], rax
0x1400087cf  call    cs:__imp_GetCurrentThreadId
0x1400087d5  mov     [rbx+20h], eax
0x1400087d8  mov     [rbx+38h], r13
0x1400087dc  mov     eax, [rsp+78h+arg_8]
0x1400087e3  mov     [rbx+40h], eax
0x1400087e6  mov     [rbx+44h], ebp
0x1400087e9  mov     rax, [rsp+78h+arg_20]
0x1400087f1  mov     [rbx+28h], rax
0x1400087f5  mov     [rbx+30h], r12
0x1400087f9  mov     rax, [rsp+78h+arg_28]
0x140008801  mov     [rbx+88h], rax
0x140008808  mov     rax, [rsp+78h+arg_0]
0x140008810  mov     [rbx+90h], rax
0x140008817  mov     [rbx+48h], rdi
0x14000881b  xorps   xmm0, xmm0
0x14000881e  xor     eax, eax
0x140008820  movups  xmmword ptr [rbx+68h], xmm0
0x140008824  mov     [rbx+78h], rax
0x140008828  movups  xmmword ptr [rbx+50h], xmm0
0x14000882c  mov     [rbx+60h], rax
0x140008830  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140008837  test    rax, rax
0x14000883a  jz      short loc_140008843
0x14000883c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008841  jmp     short loc_140008846
0x140008843  mov     rax, rdi
0x140008846  mov     [rbx+80h], rax
0x14000884d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140008854  test    rax, rax
0x140008857  jz      short loc_140008861
0x140008859  mov     rcx, rbx
0x14000885c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008861  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140008868  test    rax, rax
0x14000886b  jz      short loc_140008883
0x14000886d  mov     r8d, 400h
0x140008873  mov     rdx, [rsp+78h+arg_60]
0x14000887b  mov     rcx, rbx
0x14000887e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008883  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000888a  test    rax, rax
0x14000888d  jz      short loc_140008897
0x14000888f  mov     rcx, rbx
0x140008892  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008897  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000889e  test    rax, rax
0x1400088a1  jz      short loc_1400088B1
0x1400088a3  test    byte ptr [rbx+4], 2
0x1400088a7  jnz     short loc_1400088B1
0x1400088a9  mov     rcx, rbx
0x1400088ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400088b1  cmp     [rbx+8], edi
0x1400088b4  jl      short loc_1400088D0
0x1400088b6  cmp     r15d, 3
0x1400088ba  jnz     loc_14000899F
0x1400088c0  mov     ecx, 8000FFFFh; this
0x1400088c5  mov     [rbx+8], ecx
0x1400088c8  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400088cd  mov     [rbx+0Ch], eax
0x1400088d0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1400088d7  jnz     short loc_1400088F8
0x1400088d9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400088e0  test    rax, rax
0x1400088e3  jz      short loc_1400088EE
0x1400088e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400088ea  test    al, al
0x1400088ec  jmp     short loc_1400088F6
0x1400088ee  call    cs:__imp_IsDebuggerPresent
0x1400088f4  test    eax, eax
0x1400088f6  jz      short loc_1400088FE
0x1400088f8  test    byte ptr [rbx+4], 2
0x1400088fc  jz      short loc_140008922
0x1400088fe  mov     rax, cs:g_pfnResultLoggingCallback
0x140008905  test    rax, rax
0x140008908  jz      short loc_140008966
0x14000890a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140008911  jnz     short loc_140008966
0x140008913  xor     r8d, r8d
0x140008916  xor     edx, edx
0x140008918  mov     rcx, rbx
0x14000891b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008920  jmp     short loc_140008966
0x140008922  mov     ebp, 800h
0x140008927  mov     rax, cs:g_pfnResultLoggingCallback
0x14000892e  test    rax, rax
0x140008931  jz      short loc_14000894A
0x140008933  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14000893a  jnz     short loc_14000894A
0x14000893c  mov     r8d, ebp
0x14000893f  mov     rdx, rsi
0x140008942  mov     rcx, rbx
0x140008945  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000894a  cmp     [rsi], di
0x14000894d  jnz     short loc_14000895D
0x14000894f  mov     r8, rbx; unsigned __int64
0x140008952  mov     rdx, rbp; unsigned __int16 *
0x140008955  mov     rcx, rsi; this
0x140008958  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14000895d  mov     rcx, rsi; lpOutputString
0x140008960  call    cs:__imp_OutputDebugStringW
0x140008966  test    byte ptr [rbx+4], 4
0x14000896a  jnz     short loc_140008975
0x14000896c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x140008973  jz      short loc_140008987
0x140008975  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14000897c  test    rax, rax
0x14000897f  jz      short loc_140008987
0x140008981  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008986  nop
0x140008987  mov     rbx, [rsp+78h+arg_10]
0x14000898f  add     rsp, 40h
0x140008993  pop     r15
0x140008995  pop     r14
0x140008997  pop     r13
0x140008999  pop     r12
0x14000899b  pop     rdi
0x14000899c  pop     rsi
0x14000899d  pop     rbp
0x14000899e  retn
0x14000899f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
