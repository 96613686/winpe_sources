# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800237f8`
- end: `0x180023b03`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `779`
- prototype: `void __fastcall(wil::details *this, __int64, __int64, const char *, char *, char *, void *, unsigned int *, const struct wil::details::ResultStatus *, const unsigned __int16 *, wil *lpOutputString, unsigned __int16 *, _BYTE *, char *, unsigned __int64, __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180020378`
- `0x1800206cc`

## callees

- `0x18001323c`
- `0x1800161a0`
- `0x180019424`
- `0x1800202b8`
- `0x1800237f8`
- `0x18002449c`
- `0x1800244c0`
- `0x1800244d4`
- `0x180025714`
- `0x180045010`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x180023ab8`
- `KERNEL32!OutputDebugStringW` at `0x180023ab8`
- `KERNEL32!GetCurrentThreadId` at `0x18002391b`
- `KERNEL32!GetCurrentThreadId` at `0x18002391b`
- `KERNEL32!IsDebuggerPresent` at `0x180023a40`
- `KERNEL32!IsDebuggerPresent` at `0x180023a40`

## pseudocode

```c
void __fastcall wil::details::LogFailure(
        wil::details *this,
        __int64 a2,
        __int64 a3,
        const char *a4,
        char *a5,
        char *a6,
        void *a7,
        unsigned int *a8,
        const struct wil::details::ResultStatus *a9,
        const unsigned __int16 *a10,
        wil *lpOutputString,
        unsigned __int16 *a12,
        _BYTE *a13,
        char *a14,
        unsigned __int64 a15,
        __int64 a16)
{
  int v16; // ebp
  unsigned int v19; // edi
  int v20; // eax
  const struct wil::details::ResultStatus *v21; // rax
  DWORD CurrentThreadId; // eax
  wil::details::in1diag3 *v23; // rcx
  const struct wil::FailureInfo *v24; // r9
  __int64 ModuleName; // rax
  bool v26; // zf
  wil::details *v27; // [rsp+30h] [rbp-48h]
  int v29; // [rsp+88h] [rbp+10h]

  v29 = a2;
  v16 = 0;
  *(_WORD *)lpOutputString = 0;
  *a13 = 0;
  v19 = *a8;
  *(_DWORD *)(a16 + 8) = *a8;
  *(_DWORD *)(a16 + 12) = a8[1];
  if ( (_DWORD)a7 )
  {
    switch ( (_DWORD)a7 )
    {
      case 1:
        v20 = wil::details::RecordReturn((wil::details *)v19);
        break;
      case 2:
        if ( (v19 & 0x80000000) == 0 )
        {
          v19 = -2147024228;
          LODWORD(v27) = -2147024228;
          wil::details::ReportFailure_Hr<2>((__int64)this, a2, a3, (__int64)a4, a5, a6, v27);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL);
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
  *(_DWORD *)a16 = (_DWORD)a7;
  if ( a8[2] == 1 )
    *(_DWORD *)(a16 + 4) = a15 | 8;
  *(_DWORD *)(a16 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = a9;
  if ( !a9 || !LOWORD(a9->hr) )
    v21 = 0;
  *(_QWORD *)(a16 + 24) = v21;
  CurrentThreadId = GetCurrentThreadId();
  *(_QWORD *)(a16 + 56) = a3;
  *(_DWORD *)(a16 + 32) = CurrentThreadId;
  *(_DWORD *)(a16 + 64) = v29;
  *(_QWORD *)(a16 + 40) = a5;
  *(_QWORD *)(a16 + 136) = a6;
  *(_QWORD *)(a16 + 144) = this;
  *(_DWORD *)(a16 + 68) = v16;
  *(_QWORD *)(a16 + 48) = a4;
  *(_QWORD *)(a16 + 72) = 0;
  *(_OWORD *)(a16 + 104) = 0;
  *(_QWORD *)(a16 + 120) = 0;
  *(_OWORD *)(a16 + 80) = 0;
  *(_QWORD *)(a16 + 96) = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v23);
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
    if ( (_DWORD)a7 != 3 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v23);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v26 = !IsDebuggerPresent())
      : (v26 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v23) == 0),
        v26)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v24);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v23);
  }
}

```

## disassembly

```asm
0x1800237f8  mov     [rsp+arg_10], rbx
0x1800237fd  mov     [rsp+arg_8], edx
0x180023801  mov     [rsp+arg_0], rcx
0x180023806  push    rbp
0x180023807  push    rsi
0x180023808  push    rdi
0x180023809  push    r12
0x18002380b  push    r13
0x18002380d  push    r14
0x18002380f  push    r15
0x180023811  sub     rsp, 40h
0x180023815  mov     r14, [rsp+78h+arg_38]
0x18002381d  xor     eax, eax
0x18002381f  mov     rbx, qword ptr [rsp+78h+arg_78]
0x180023827  xor     ebp, ebp
0x180023829  mov     r15d, dword ptr [rsp+78h+arg_30]
0x180023831  mov     r10, rcx
0x180023834  mov     rsi, [rsp+78h+lpOutputString]
0x18002383c  mov     r12, r9
0x18002383f  mov     r13, r8
0x180023842  mov     ecx, r15d
0x180023845  mov     [rsi], ax
0x180023848  mov     rax, [rsp+78h+arg_60]
0x180023850  mov     byte ptr [rax], 0
0x180023853  mov     edi, [r14]
0x180023856  mov     [rbx+8], edi
0x180023859  mov     eax, [r14+4]
0x18002385d  mov     [rbx+0Ch], eax
0x180023860  test    r15d, r15d
0x180023863  jz      short loc_1800238CB
0x180023865  sub     ecx, 1
0x180023868  jz      short loc_1800238C2
0x18002386a  sub     ecx, 1
0x18002386d  jz      short loc_18002387D
0x18002386f  cmp     ecx, 1
0x180023872  jnz     short loc_1800238D4
0x180023874  mov     ecx, edi; this
0x180023876  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18002387b  jmp     short loc_1800238D2
0x18002387d  test    edi, edi
0x18002387f  js      short loc_1800238B9
0x180023881  mov     rax, [rsp+78h+arg_28]
0x180023889  mov     edi, 8007029Ch
0x18002388e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180023892  mov     rcx, r10; int
0x180023895  mov     [rsp+78h+var_50], rax; __int64
0x18002389a  mov     rax, [rsp+78h+arg_20]
0x1800238a2  mov     [rsp+78h+var_58], rax; __int64
0x1800238a7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800238ac  mov     ecx, edi; this
0x1800238ae  mov     [rbx+8], edi
0x1800238b1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800238b6  mov     [rbx+0Ch], eax
0x1800238b9  mov     ecx, edi; this
0x1800238bb  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800238c0  jmp     short loc_1800238D2
0x1800238c2  mov     ecx, edi; this
0x1800238c4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800238c9  jmp     short loc_1800238D2
0x1800238cb  mov     ecx, edi; this
0x1800238cd  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800238d2  mov     ebp, eax
0x1800238d4  mov     eax, dword ptr [rsp+78h+arg_70]
0x1800238db  mov     [rbx+4], eax
0x1800238de  mov     [rbx], r15d
0x1800238e1  cmp     dword ptr [r14+8], 1
0x1800238e6  jnz     short loc_1800238EE
0x1800238e8  or      eax, 8
0x1800238eb  mov     [rbx+4], eax
0x1800238ee  mov     eax, 1
0x1800238f3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800238fb  inc     eax
0x1800238fd  xor     edi, edi
0x1800238ff  mov     [rbx+10h], eax
0x180023902  mov     rax, [rsp+78h+arg_40]
0x18002390a  test    rax, rax
0x18002390d  jz      short loc_180023914
0x18002390f  cmp     [rax], di
0x180023912  jnz     short loc_180023917
0x180023914  mov     rax, rdi
0x180023917  mov     [rbx+18h], rax
0x18002391b  call    cs:__imp_GetCurrentThreadId
0x180023922  nop     dword ptr [rax+rax+00h]
0x180023927  mov     [rbx+38h], r13
0x18002392b  xorps   xmm0, xmm0
0x18002392e  mov     [rbx+20h], eax
0x180023931  mov     eax, [rsp+78h+arg_8]
0x180023938  mov     [rbx+40h], eax
0x18002393b  mov     rax, [rsp+78h+arg_20]
0x180023943  mov     [rbx+28h], rax
0x180023947  mov     rax, [rsp+78h+arg_28]
0x18002394f  mov     [rbx+88h], rax
0x180023956  mov     rax, [rsp+78h+arg_0]
0x18002395e  mov     [rbx+90h], rax
0x180023965  xor     eax, eax
0x180023967  mov     [rbx+44h], ebp
0x18002396a  mov     [rbx+30h], r12
0x18002396e  mov     [rbx+48h], rdi
0x180023972  movups  xmmword ptr [rbx+68h], xmm0
0x180023976  mov     [rbx+78h], rax
0x18002397a  movups  xmmword ptr [rbx+50h], xmm0
0x18002397e  mov     [rbx+60h], rax
0x180023982  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180023989  test    rax, rax
0x18002398c  jz      short loc_180023995
0x18002398e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023993  jmp     short loc_180023998
0x180023995  mov     rax, rdi
0x180023998  mov     [rbx+80h], rax
0x18002399f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800239a6  test    rax, rax
0x1800239a9  jz      short loc_1800239B3
0x1800239ab  mov     rcx, rbx
0x1800239ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800239b3  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800239ba  test    rax, rax
0x1800239bd  jz      short loc_1800239D5
0x1800239bf  mov     rdx, [rsp+78h+arg_60]
0x1800239c7  mov     r8d, 400h
0x1800239cd  mov     rcx, rbx
0x1800239d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800239d5  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800239dc  test    rax, rax
0x1800239df  jz      short loc_1800239E9
0x1800239e1  mov     rcx, rbx
0x1800239e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800239e9  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800239f0  test    rax, rax
0x1800239f3  jz      short loc_180023A03
0x1800239f5  test    byte ptr [rbx+4], 2
0x1800239f9  jnz     short loc_180023A03
0x1800239fb  mov     rcx, rbx
0x1800239fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023a03  cmp     [rbx+8], edi
0x180023a06  jl      short loc_180023A22
0x180023a08  cmp     r15d, 3
0x180023a0c  jnz     loc_180023AFD
0x180023a12  mov     ecx, 8000FFFFh; this
0x180023a17  mov     [rbx+8], ecx
0x180023a1a  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180023a1f  mov     [rbx+0Ch], eax
0x180023a22  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180023a29  jnz     short loc_180023A50
0x180023a2b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180023a32  test    rax, rax
0x180023a35  jz      short loc_180023A40
0x180023a37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023a3c  test    al, al
0x180023a3e  jmp     short loc_180023A4E
0x180023a40  call    cs:__imp_IsDebuggerPresent
0x180023a47  nop     dword ptr [rax+rax+00h]
0x180023a4c  test    eax, eax
0x180023a4e  jz      short loc_180023A56
0x180023a50  test    byte ptr [rbx+4], 2
0x180023a54  jz      short loc_180023A7A
0x180023a56  mov     rax, cs:g_pfnResultLoggingCallback
0x180023a5d  test    rax, rax
0x180023a60  jz      short loc_180023AC4
0x180023a62  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180023a69  jnz     short loc_180023AC4
0x180023a6b  xor     r8d, r8d
0x180023a6e  xor     edx, edx
0x180023a70  mov     rcx, rbx
0x180023a73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023a78  jmp     short loc_180023AC4
0x180023a7a  mov     rax, cs:g_pfnResultLoggingCallback
0x180023a81  mov     ebp, 800h
0x180023a86  test    rax, rax
0x180023a89  jz      short loc_180023AA2
0x180023a8b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180023a92  jnz     short loc_180023AA2
0x180023a94  mov     r8d, ebp
0x180023a97  mov     rdx, rsi
0x180023a9a  mov     rcx, rbx
0x180023a9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023aa2  cmp     [rsi], di
0x180023aa5  jnz     short loc_180023AB5
0x180023aa7  mov     r8, rbx; unsigned __int64
0x180023aaa  mov     rdx, rbp; unsigned __int16 *
0x180023aad  mov     rcx, rsi; this
0x180023ab0  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180023ab5  mov     rcx, rsi; lpOutputString
0x180023ab8  call    cs:__imp_OutputDebugStringW
0x180023abf  nop     dword ptr [rax+rax+00h]
0x180023ac4  test    byte ptr [rbx+4], 4
0x180023ac8  jnz     short loc_180023AD3
0x180023aca  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180023ad1  jz      short loc_180023AE4
0x180023ad3  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180023ada  test    rax, rax
0x180023add  jz      short loc_180023AE4
0x180023adf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023ae4  mov     rbx, [rsp+78h+arg_10]
0x180023aec  add     rsp, 40h
0x180023af0  pop     r15
0x180023af2  pop     r14
0x180023af4  pop     r13
0x180023af6  pop     r12
0x180023af8  pop     rdi
0x180023af9  pop     rsi
0x180023afa  pop     rbp
0x180023afb  retn
0x180023afd  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
