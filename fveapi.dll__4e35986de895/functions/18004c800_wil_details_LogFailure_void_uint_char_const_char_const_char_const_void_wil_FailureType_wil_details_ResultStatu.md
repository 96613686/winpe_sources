# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18004c800`
- end: `0x18004cb07`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `775`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x18004c550`
- `0x18004c700`
- `0x180060e70`

## callees

- `0x180047cec`
- `0x18004c800`
- `0x18004cb10`
- `0x180060dc4`
- `0x180061674`
- `0x180062284`
- `0x1800622a4`
- `0x1800622c4`
- `0x180062ab0`
- `0x180129010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004c923`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004c923`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18004ca4a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18004ca4a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18004cac2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18004cac2`

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
0x18004c800  mov     [rsp+arg_10], rbx
0x18004c805  mov     [rsp+arg_8], edx
0x18004c809  mov     [rsp+arg_0], rcx
0x18004c80e  push    rbp
0x18004c80f  push    rsi
0x18004c810  push    rdi
0x18004c811  push    r12
0x18004c813  push    r13
0x18004c815  push    r14
0x18004c817  push    r15
0x18004c819  sub     rsp, 40h
0x18004c81d  mov     r14, [rsp+78h+arg_38]
0x18004c825  xor     eax, eax
0x18004c827  mov     rbx, [rsp+78h+arg_78]
0x18004c82f  xor     ebp, ebp
0x18004c831  mov     r15d, [rsp+78h+arg_30]
0x18004c839  mov     r10, rcx
0x18004c83c  mov     rsi, [rsp+78h+lpOutputString]
0x18004c844  mov     r12, r9
0x18004c847  mov     r13, r8
0x18004c84a  mov     ecx, r15d
0x18004c84d  mov     [rsi], ax
0x18004c850  mov     rax, [rsp+78h+arg_60]
0x18004c858  mov     byte ptr [rax], 0
0x18004c85b  mov     edi, [r14]
0x18004c85e  mov     [rbx+8], edi
0x18004c861  mov     eax, [r14+4]
0x18004c865  mov     [rbx+0Ch], eax
0x18004c868  test    r15d, r15d
0x18004c86b  jz      short loc_18004C8D3
0x18004c86d  sub     ecx, 1
0x18004c870  jz      short loc_18004C8CA
0x18004c872  sub     ecx, 1
0x18004c875  jz      short loc_18004C885
0x18004c877  cmp     ecx, 1
0x18004c87a  jnz     short loc_18004C8DC
0x18004c87c  mov     ecx, edi; this
0x18004c87e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18004c883  jmp     short loc_18004C8DA
0x18004c885  test    edi, edi
0x18004c887  js      short loc_18004C8C1
0x18004c889  mov     rax, [rsp+78h+arg_28]
0x18004c891  mov     edi, 8007029Ch
0x18004c896  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18004c89a  mov     rcx, r10; int
0x18004c89d  mov     [rsp+78h+var_50], rax; __int64
0x18004c8a2  mov     rax, [rsp+78h+arg_20]
0x18004c8aa  mov     [rsp+78h+var_58], rax; __int64
0x18004c8af  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18004c8b4  mov     ecx, edi; this
0x18004c8b6  mov     [rbx+8], edi
0x18004c8b9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18004c8be  mov     [rbx+0Ch], eax
0x18004c8c1  mov     ecx, edi; this
0x18004c8c3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18004c8c8  jmp     short loc_18004C8DA
0x18004c8ca  mov     ecx, edi; this
0x18004c8cc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18004c8d1  jmp     short loc_18004C8DA
0x18004c8d3  mov     ecx, edi; this
0x18004c8d5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18004c8da  mov     ebp, eax
0x18004c8dc  mov     eax, [rsp+78h+arg_70]
0x18004c8e3  mov     [rbx+4], eax
0x18004c8e6  mov     [rbx], r15d
0x18004c8e9  cmp     dword ptr [r14+8], 1
0x18004c8ee  jnz     short loc_18004C8F6
0x18004c8f0  or      eax, 8
0x18004c8f3  mov     [rbx+4], eax
0x18004c8f6  mov     eax, 1
0x18004c8fb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18004c903  inc     eax
0x18004c905  xor     edi, edi
0x18004c907  mov     [rbx+10h], eax
0x18004c90a  mov     rax, [rsp+78h+arg_40]
0x18004c912  test    rax, rax
0x18004c915  jz      short loc_18004C91C
0x18004c917  cmp     [rax], di
0x18004c91a  jnz     short loc_18004C91F
0x18004c91c  mov     rax, rdi
0x18004c91f  mov     [rbx+18h], rax
0x18004c923  call    cs:__imp_GetCurrentThreadId
0x18004c92a  nop     dword ptr [rax+rax+00h]
0x18004c92f  mov     [rbx+38h], r13
0x18004c933  xorps   xmm0, xmm0
0x18004c936  mov     [rbx+20h], eax
0x18004c939  mov     eax, [rsp+78h+arg_8]
0x18004c940  mov     [rbx+40h], eax
0x18004c943  mov     rax, [rsp+78h+arg_20]
0x18004c94b  mov     [rbx+28h], rax
0x18004c94f  mov     rax, [rsp+78h+arg_28]
0x18004c957  mov     [rbx+88h], rax
0x18004c95e  mov     rax, [rsp+78h+arg_0]
0x18004c966  mov     [rbx+90h], rax
0x18004c96d  xor     eax, eax
0x18004c96f  mov     [rbx+44h], ebp
0x18004c972  mov     [rbx+30h], r12
0x18004c976  mov     [rbx+48h], rdi
0x18004c97a  movups  xmmword ptr [rbx+68h], xmm0
0x18004c97e  mov     [rbx+78h], rax
0x18004c982  movups  xmmword ptr [rbx+50h], xmm0
0x18004c986  mov     [rbx+60h], rax
0x18004c98a  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18004c991  test    rax, rax
0x18004c994  jz      short loc_18004C99D
0x18004c996  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c99b  jmp     short loc_18004C9A0
0x18004c99d  mov     rax, rdi
0x18004c9a0  mov     [rbx+80h], rax
0x18004c9a7  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18004c9ae  test    rax, rax
0x18004c9b1  jz      short loc_18004C9BB
0x18004c9b3  mov     rcx, rbx
0x18004c9b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c9bb  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18004c9c2  test    rax, rax
0x18004c9c5  jz      short loc_18004C9DD
0x18004c9c7  mov     rdx, [rsp+78h+arg_60]
0x18004c9cf  mov     r8d, 400h
0x18004c9d5  mov     rcx, rbx
0x18004c9d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c9dd  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18004c9e4  test    rax, rax
0x18004c9e7  jz      short loc_18004C9F1
0x18004c9e9  mov     rcx, rbx
0x18004c9ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c9f1  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18004c9f8  test    rax, rax
0x18004c9fb  jz      short loc_18004CA0B
0x18004c9fd  test    byte ptr [rbx+4], 2
0x18004ca01  jnz     short loc_18004CA0B
0x18004ca03  mov     rcx, rbx
0x18004ca06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ca0b  cmp     [rbx+8], edi
0x18004ca0e  jl      short loc_18004CA2C
0x18004ca10  cmp     r15d, 3
0x18004ca14  jz      short loc_18004CA1C
0x18004ca16  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18004ca1c  mov     ecx, 8000FFFFh; this
0x18004ca21  mov     [rbx+8], ecx
0x18004ca24  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18004ca29  mov     [rbx+0Ch], eax
0x18004ca2c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18004ca33  jnz     short loc_18004CA5A
0x18004ca35  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18004ca3c  test    rax, rax
0x18004ca3f  jz      short loc_18004CA4A
0x18004ca41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ca46  test    al, al
0x18004ca48  jmp     short loc_18004CA58
0x18004ca4a  call    cs:__imp_IsDebuggerPresent
0x18004ca51  nop     dword ptr [rax+rax+00h]
0x18004ca56  test    eax, eax
0x18004ca58  jz      short loc_18004CA60
0x18004ca5a  test    byte ptr [rbx+4], 2
0x18004ca5e  jz      short loc_18004CA84
0x18004ca60  mov     rax, cs:g_pfnResultLoggingCallback
0x18004ca67  test    rax, rax
0x18004ca6a  jz      short loc_18004CACE
0x18004ca6c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18004ca73  jnz     short loc_18004CACE
0x18004ca75  xor     r8d, r8d
0x18004ca78  xor     edx, edx
0x18004ca7a  mov     rcx, rbx
0x18004ca7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ca82  jmp     short loc_18004CACE
0x18004ca84  mov     rax, cs:g_pfnResultLoggingCallback
0x18004ca8b  mov     ebp, 800h
0x18004ca90  test    rax, rax
0x18004ca93  jz      short loc_18004CAAC
0x18004ca95  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18004ca9c  jnz     short loc_18004CAAC
0x18004ca9e  mov     r8d, ebp
0x18004caa1  mov     rdx, rsi
0x18004caa4  mov     rcx, rbx
0x18004caa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004caac  cmp     [rsi], di
0x18004caaf  jnz     short loc_18004CABF
0x18004cab1  mov     r8, rbx; unsigned __int64
0x18004cab4  mov     rdx, rbp; unsigned __int16 *
0x18004cab7  mov     rcx, rsi; this
0x18004caba  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18004cabf  mov     rcx, rsi; lpOutputString
0x18004cac2  call    cs:__imp_OutputDebugStringW
0x18004cac9  nop     dword ptr [rax+rax+00h]
0x18004cace  test    byte ptr [rbx+4], 4
0x18004cad2  jnz     short loc_18004CADD
0x18004cad4  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18004cadb  jz      short loc_18004CAEE
0x18004cadd  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18004cae4  test    rax, rax
0x18004cae7  jz      short loc_18004CAEE
0x18004cae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004caee  mov     rbx, [rsp+78h+arg_10]
0x18004caf6  add     rsp, 40h
0x18004cafa  pop     r15
0x18004cafc  pop     r14
0x18004cafe  pop     r13
0x18004cb00  pop     r12
0x18004cb02  pop     rdi
0x18004cb03  pop     rsi
0x18004cb04  pop     rbp
0x18004cb05  retn
```
