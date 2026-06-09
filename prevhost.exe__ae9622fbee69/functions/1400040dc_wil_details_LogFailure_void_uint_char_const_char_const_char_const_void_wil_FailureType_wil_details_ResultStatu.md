# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1400040dc`
- end: `0x1400043d4`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140002668`

## callees

- `0x1400020a4`
- `0x1400036a4`
- `0x140003e3c`
- `0x1400040dc`
- `0x14000498c`
- `0x1400049b0`
- `0x1400049c4`
- `0x1400049e0`
- `0x14000564c`
- `0x140006010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400041ff`
- `KERNEL32!GetCurrentThreadId` at `0x1400041ff`
- `KERNEL32!OutputDebugStringW` at `0x140004390`
- `KERNEL32!OutputDebugStringW` at `0x140004390`
- `KERNEL32!IsDebuggerPresent` at `0x14000431e`
- `KERNEL32!IsDebuggerPresent` at `0x14000431e`

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
    ModuleName = wil::details::g_pfnGetModuleName(v25);
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
      : (v28 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v25) == 0),
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
      wil::details::g_pfnDebugBreak(v25);
  }
}

```

## disassembly

```asm
0x1400040dc  mov     [rsp+arg_10], rbx
0x1400040e1  mov     [rsp+arg_8], edx
0x1400040e5  mov     [rsp+arg_0], rcx
0x1400040ea  push    rbp
0x1400040eb  push    rsi
0x1400040ec  push    rdi
0x1400040ed  push    r12
0x1400040ef  push    r13
0x1400040f1  push    r14
0x1400040f3  push    r15
0x1400040f5  sub     rsp, 40h
0x1400040f9  mov     r14, [rsp+78h+arg_38]
0x140004101  xor     eax, eax
0x140004103  mov     rbx, [rsp+78h+arg_78]
0x14000410b  xor     ebp, ebp
0x14000410d  mov     r15d, [rsp+78h+arg_30]
0x140004115  mov     r10, rcx
0x140004118  mov     rsi, [rsp+78h+lpOutputString]
0x140004120  mov     r12, r9
0x140004123  mov     r13, r8
0x140004126  mov     ecx, r15d
0x140004129  mov     [rsi], ax
0x14000412c  mov     rax, [rsp+78h+arg_60]
0x140004134  mov     byte ptr [rax], 0
0x140004137  mov     edi, [r14]
0x14000413a  mov     [rbx+8], edi
0x14000413d  mov     eax, [r14+4]
0x140004141  mov     [rbx+0Ch], eax
0x140004144  test    r15d, r15d
0x140004147  jz      short loc_1400041AF
0x140004149  sub     ecx, 1
0x14000414c  jz      short loc_1400041A6
0x14000414e  sub     ecx, 1
0x140004151  jz      short loc_140004161
0x140004153  cmp     ecx, 1
0x140004156  jnz     short loc_1400041B8
0x140004158  mov     ecx, edi; this
0x14000415a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x14000415f  jmp     short loc_1400041B6
0x140004161  test    edi, edi
0x140004163  js      short loc_14000419D
0x140004165  mov     rax, [rsp+78h+arg_28]
0x14000416d  mov     edi, 8007029Ch
0x140004172  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x140004176  mov     rcx, r10; int
0x140004179  mov     [rsp+78h+var_50], rax; __int64
0x14000417e  mov     rax, [rsp+78h+arg_20]
0x140004186  mov     [rsp+78h+var_58], rax; __int64
0x14000418b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140004190  mov     ecx, edi; this
0x140004192  mov     [rbx+8], edi
0x140004195  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000419a  mov     [rbx+0Ch], eax
0x14000419d  mov     ecx, edi; this
0x14000419f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1400041a4  jmp     short loc_1400041B6
0x1400041a6  mov     ecx, edi; this
0x1400041a8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1400041ad  jmp     short loc_1400041B6
0x1400041af  mov     ecx, edi; this
0x1400041b1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1400041b6  mov     ebp, eax
0x1400041b8  mov     eax, [rsp+78h+arg_70]
0x1400041bf  mov     [rbx+4], eax
0x1400041c2  mov     [rbx], r15d
0x1400041c5  cmp     dword ptr [r14+8], 1
0x1400041ca  jnz     short loc_1400041D2
0x1400041cc  or      eax, 8
0x1400041cf  mov     [rbx+4], eax
0x1400041d2  mov     eax, 1
0x1400041d7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400041df  inc     eax
0x1400041e1  xor     edi, edi
0x1400041e3  mov     [rbx+10h], eax
0x1400041e6  mov     rax, [rsp+78h+arg_40]
0x1400041ee  test    rax, rax
0x1400041f1  jz      short loc_1400041F8
0x1400041f3  cmp     [rax], di
0x1400041f6  jnz     short loc_1400041FB
0x1400041f8  mov     rax, rdi
0x1400041fb  mov     [rbx+18h], rax
0x1400041ff  call    cs:__imp_GetCurrentThreadId
0x140004205  mov     [rbx+38h], r13
0x140004209  xorps   xmm0, xmm0
0x14000420c  mov     [rbx+20h], eax
0x14000420f  mov     eax, [rsp+78h+arg_8]
0x140004216  mov     [rbx+40h], eax
0x140004219  mov     rax, [rsp+78h+arg_20]
0x140004221  mov     [rbx+28h], rax
0x140004225  mov     rax, [rsp+78h+arg_28]
0x14000422d  mov     [rbx+88h], rax
0x140004234  mov     rax, [rsp+78h+arg_0]
0x14000423c  mov     [rbx+90h], rax
0x140004243  xor     eax, eax
0x140004245  mov     [rbx+44h], ebp
0x140004248  mov     [rbx+30h], r12
0x14000424c  mov     [rbx+48h], rdi
0x140004250  movups  xmmword ptr [rbx+68h], xmm0
0x140004254  mov     [rbx+78h], rax
0x140004258  movups  xmmword ptr [rbx+50h], xmm0
0x14000425c  mov     [rbx+60h], rax
0x140004260  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140004267  test    rax, rax
0x14000426a  jz      short loc_140004273
0x14000426c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004271  jmp     short loc_140004276
0x140004273  mov     rax, rdi
0x140004276  mov     [rbx+80h], rax
0x14000427d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140004284  test    rax, rax
0x140004287  jz      short loc_140004291
0x140004289  mov     rcx, rbx
0x14000428c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004291  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140004298  test    rax, rax
0x14000429b  jz      short loc_1400042B3
0x14000429d  mov     rdx, [rsp+78h+arg_60]
0x1400042a5  mov     r8d, 400h
0x1400042ab  mov     rcx, rbx
0x1400042ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400042b3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400042ba  test    rax, rax
0x1400042bd  jz      short loc_1400042C7
0x1400042bf  mov     rcx, rbx
0x1400042c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400042c7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400042ce  test    rax, rax
0x1400042d1  jz      short loc_1400042E1
0x1400042d3  test    byte ptr [rbx+4], 2
0x1400042d7  jnz     short loc_1400042E1
0x1400042d9  mov     rcx, rbx
0x1400042dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400042e1  cmp     [rbx+8], edi
0x1400042e4  jl      short loc_140004300
0x1400042e6  cmp     r15d, 3
0x1400042ea  jnz     loc_1400043CE
0x1400042f0  mov     ecx, 8000FFFFh; this
0x1400042f5  mov     [rbx+8], ecx
0x1400042f8  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400042fd  mov     [rbx+0Ch], eax
0x140004300  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x140004307  jnz     short loc_140004328
0x140004309  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140004310  test    rax, rax
0x140004313  jz      short loc_14000431E
0x140004315  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000431a  test    al, al
0x14000431c  jmp     short loc_140004326
0x14000431e  call    cs:__imp_IsDebuggerPresent
0x140004324  test    eax, eax
0x140004326  jz      short loc_14000432E
0x140004328  test    byte ptr [rbx+4], 2
0x14000432c  jz      short loc_140004352
0x14000432e  mov     rax, cs:g_pfnResultLoggingCallback
0x140004335  test    rax, rax
0x140004338  jz      short loc_140004396
0x14000433a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140004341  jnz     short loc_140004396
0x140004343  xor     r8d, r8d
0x140004346  xor     edx, edx
0x140004348  mov     rcx, rbx
0x14000434b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004350  jmp     short loc_140004396
0x140004352  mov     rax, cs:g_pfnResultLoggingCallback
0x140004359  mov     ebp, 800h
0x14000435e  test    rax, rax
0x140004361  jz      short loc_14000437A
0x140004363  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14000436a  jnz     short loc_14000437A
0x14000436c  mov     r8d, ebp
0x14000436f  mov     rdx, rsi
0x140004372  mov     rcx, rbx
0x140004375  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000437a  cmp     [rsi], di
0x14000437d  jnz     short loc_14000438D
0x14000437f  mov     r8, rbx; unsigned __int64
0x140004382  mov     rdx, rbp; unsigned __int16 *
0x140004385  mov     rcx, rsi; this
0x140004388  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14000438d  mov     rcx, rsi; lpOutputString
0x140004390  call    cs:__imp_OutputDebugStringW
0x140004396  test    byte ptr [rbx+4], 4
0x14000439a  jnz     short loc_1400043A5
0x14000439c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1400043a3  jz      short loc_1400043B6
0x1400043a5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400043ac  test    rax, rax
0x1400043af  jz      short loc_1400043B6
0x1400043b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400043b6  mov     rbx, [rsp+78h+arg_10]
0x1400043be  add     rsp, 40h
0x1400043c2  pop     r15
0x1400043c4  pop     r14
0x1400043c6  pop     r13
0x1400043c8  pop     r12
0x1400043ca  pop     rdi
0x1400043cb  pop     rsi
0x1400043cc  pop     rbp
0x1400043cd  retn
0x1400043ce  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
