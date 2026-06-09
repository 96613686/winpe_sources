# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000941c`
- end: `0x180009711`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180006bf4`
- `0x180006ca4`
- `0x180006d94`

## callees

- `0x180005020`
- `0x1800053c4`
- `0x1800056c0`
- `0x180006b48`
- `0x18000941c`
- `0x18000a440`
- `0x18000a6b8`
- `0x18000a6d4`
- `0x18000c314`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000953f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000953f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180009660`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180009660`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800096d2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800096d2`

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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v25 = !IsDebuggerPresent())
      : (v25 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v25)
    || (*(_BYTE *)(a16 + 4) & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, 0, 0, v23);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048, v23);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v23);
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
0x18000941c  mov     [rsp+arg_10], rbx
0x180009421  mov     [rsp+arg_8], edx
0x180009425  mov     [rsp+arg_0], rcx
0x18000942a  push    rbp
0x18000942b  push    rsi
0x18000942c  push    rdi
0x18000942d  push    r12
0x18000942f  push    r13
0x180009431  push    r14
0x180009433  push    r15
0x180009435  sub     rsp, 40h
0x180009439  mov     r12, r9
0x18000943c  mov     r13, r8
0x18000943f  mov     r10, rcx
0x180009442  xor     eax, eax
0x180009444  mov     rsi, [rsp+78h+lpOutputString]
0x18000944c  mov     [rsi], ax
0x18000944f  mov     rax, [rsp+78h+arg_60]
0x180009457  mov     byte ptr [rax], 0
0x18000945a  mov     r14, [rsp+78h+arg_38]
0x180009462  mov     edi, [r14]
0x180009465  mov     rbx, [rsp+78h+arg_78]
0x18000946d  mov     [rbx+8], edi
0x180009470  mov     eax, [r14+4]
0x180009474  mov     [rbx+0Ch], eax
0x180009477  xor     ebp, ebp
0x180009479  mov     r15d, [rsp+78h+arg_30]
0x180009481  mov     ecx, r15d
0x180009484  test    r15d, r15d
0x180009487  jz      short loc_1800094EF
0x180009489  sub     ecx, 1
0x18000948c  jz      short loc_1800094E6
0x18000948e  sub     ecx, 1
0x180009491  jz      short loc_1800094A1
0x180009493  cmp     ecx, 1
0x180009496  jnz     short loc_1800094F8
0x180009498  mov     ecx, edi; this
0x18000949a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000949f  jmp     short loc_1800094F6
0x1800094a1  test    edi, edi
0x1800094a3  js      short loc_1800094DD
0x1800094a5  mov     edi, 8007029Ch
0x1800094aa  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800094ae  mov     rax, [rsp+78h+arg_28]
0x1800094b6  mov     [rsp+78h+var_50], rax; __int64
0x1800094bb  mov     rax, [rsp+78h+arg_20]
0x1800094c3  mov     [rsp+78h+var_58], rax; __int64
0x1800094c8  mov     rcx, r10; int
0x1800094cb  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800094d0  mov     [rbx+8], edi
0x1800094d3  mov     ecx, edi; this
0x1800094d5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800094da  mov     [rbx+0Ch], eax
0x1800094dd  mov     ecx, edi; this
0x1800094df  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800094e4  jmp     short loc_1800094F6
0x1800094e6  mov     ecx, edi; this
0x1800094e8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800094ed  jmp     short loc_1800094F6
0x1800094ef  mov     ecx, edi; this
0x1800094f1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800094f6  mov     ebp, eax
0x1800094f8  mov     [rbx], r15d
0x1800094fb  mov     eax, [rsp+78h+arg_70]
0x180009502  mov     [rbx+4], eax
0x180009505  cmp     dword ptr [r14+8], 1
0x18000950a  jnz     short loc_180009512
0x18000950c  or      eax, 8
0x18000950f  mov     [rbx+4], eax
0x180009512  mov     eax, 1
0x180009517  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000951f  inc     eax
0x180009521  mov     [rbx+10h], eax
0x180009524  mov     rax, [rsp+78h+arg_40]
0x18000952c  xor     edi, edi
0x18000952e  test    rax, rax
0x180009531  jz      short loc_180009538
0x180009533  cmp     [rax], di
0x180009536  jnz     short loc_18000953B
0x180009538  mov     rax, rdi
0x18000953b  mov     [rbx+18h], rax
0x18000953f  call    cs:__imp_GetCurrentThreadId
0x180009545  mov     [rbx+20h], eax
0x180009548  mov     [rbx+38h], r13
0x18000954c  mov     eax, [rsp+78h+arg_8]
0x180009553  mov     [rbx+40h], eax
0x180009556  mov     [rbx+44h], ebp
0x180009559  mov     rax, [rsp+78h+arg_20]
0x180009561  mov     [rbx+28h], rax
0x180009565  mov     [rbx+30h], r12
0x180009569  mov     rax, [rsp+78h+arg_28]
0x180009571  mov     [rbx+88h], rax
0x180009578  mov     rax, [rsp+78h+arg_0]
0x180009580  mov     [rbx+90h], rax
0x180009587  mov     [rbx+48h], rdi
0x18000958b  xorps   xmm0, xmm0
0x18000958e  xor     eax, eax
0x180009590  movups  xmmword ptr [rbx+68h], xmm0
0x180009594  mov     [rbx+78h], rax
0x180009598  movups  xmmword ptr [rbx+50h], xmm0
0x18000959c  mov     [rbx+60h], rax
0x1800095a0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800095a7  test    rax, rax
0x1800095aa  jz      short loc_1800095B3
0x1800095ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095b1  jmp     short loc_1800095B6
0x1800095b3  mov     rax, rdi
0x1800095b6  mov     [rbx+80h], rax
0x1800095bd  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800095c4  test    rax, rax
0x1800095c7  jz      short loc_1800095D1
0x1800095c9  mov     rcx, rbx
0x1800095cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095d1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800095d8  test    rax, rax
0x1800095db  jz      short loc_1800095F3
0x1800095dd  mov     r8d, 400h
0x1800095e3  mov     rdx, [rsp+78h+arg_60]
0x1800095eb  mov     rcx, rbx
0x1800095ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095f3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800095fa  test    rax, rax
0x1800095fd  jz      short loc_180009607
0x1800095ff  mov     rcx, rbx
0x180009602  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009607  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000960e  test    rax, rax
0x180009611  jz      short loc_180009621
0x180009613  test    byte ptr [rbx+4], 2
0x180009617  jnz     short loc_180009621
0x180009619  mov     rcx, rbx
0x18000961c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009621  cmp     [rbx+8], edi
0x180009624  jl      short loc_180009642
0x180009626  cmp     r15d, 3
0x18000962a  jz      short loc_180009632
0x18000962c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180009632  mov     ecx, 8000FFFFh; this
0x180009637  mov     [rbx+8], ecx
0x18000963a  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000963f  mov     [rbx+0Ch], eax
0x180009642  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180009649  jnz     short loc_18000966A
0x18000964b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180009652  test    rax, rax
0x180009655  jz      short loc_180009660
0x180009657  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000965c  test    al, al
0x18000965e  jmp     short loc_180009668
0x180009660  call    cs:__imp_IsDebuggerPresent
0x180009666  test    eax, eax
0x180009668  jz      short loc_180009670
0x18000966a  test    byte ptr [rbx+4], 2
0x18000966e  jz      short loc_180009694
0x180009670  mov     rax, cs:g_pfnResultLoggingCallback
0x180009677  test    rax, rax
0x18000967a  jz      short loc_1800096D8
0x18000967c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180009683  jnz     short loc_1800096D8
0x180009685  xor     r8d, r8d
0x180009688  xor     edx, edx
0x18000968a  mov     rcx, rbx
0x18000968d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009692  jmp     short loc_1800096D8
0x180009694  mov     ebp, 800h
0x180009699  mov     rax, cs:g_pfnResultLoggingCallback
0x1800096a0  test    rax, rax
0x1800096a3  jz      short loc_1800096BC
0x1800096a5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800096ac  jnz     short loc_1800096BC
0x1800096ae  mov     r8d, ebp
0x1800096b1  mov     rdx, rsi
0x1800096b4  mov     rcx, rbx
0x1800096b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096bc  cmp     [rsi], di
0x1800096bf  jnz     short loc_1800096CF
0x1800096c1  mov     r8, rbx; unsigned __int64
0x1800096c4  mov     rdx, rbp; unsigned __int16 *
0x1800096c7  mov     rcx, rsi; this
0x1800096ca  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800096cf  mov     rcx, rsi; lpOutputString
0x1800096d2  call    cs:__imp_OutputDebugStringW
0x1800096d8  test    byte ptr [rbx+4], 4
0x1800096dc  jnz     short loc_1800096E7
0x1800096de  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800096e5  jz      short loc_1800096F9
0x1800096e7  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800096ee  test    rax, rax
0x1800096f1  jz      short loc_1800096F9
0x1800096f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096f8  nop
0x1800096f9  mov     rbx, [rsp+78h+arg_10]
0x180009701  add     rsp, 40h
0x180009705  pop     r15
0x180009707  pop     r14
0x180009709  pop     r13
0x18000970b  pop     r12
0x18000970d  pop     rdi
0x18000970e  pop     rsi
0x18000970f  pop     rbp
0x180009710  retn
```
