# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180025f64`
- end: `0x18002626c`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `776`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x180025c48`
- `0x180025d48`
- `0x18003dce0`
- `0x18003dda0`

## callees

- `0x1800187b8`
- `0x180025f64`
- `0x180029c28`
- `0x18003dc28`
- `0x18003e664`
- `0x18003f0c8`
- `0x18003f0f0`
- `0x18003f104`
- `0x18003fa28`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026087`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026087`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180026226`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180026226`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800261ae`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800261ae`

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
0x180025f64  mov     [rsp+arg_10], rbx
0x180025f69  mov     [rsp+arg_8], edx
0x180025f6d  mov     [rsp+arg_0], rcx
0x180025f72  push    rbp
0x180025f73  push    rsi
0x180025f74  push    rdi
0x180025f75  push    r12
0x180025f77  push    r13
0x180025f79  push    r14
0x180025f7b  push    r15
0x180025f7d  sub     rsp, 40h
0x180025f81  mov     r12, r9
0x180025f84  mov     r13, r8
0x180025f87  mov     r10, rcx
0x180025f8a  xor     eax, eax
0x180025f8c  mov     rsi, [rsp+78h+lpOutputString]
0x180025f94  mov     [rsi], ax
0x180025f97  mov     rax, [rsp+78h+arg_60]
0x180025f9f  mov     byte ptr [rax], 0
0x180025fa2  mov     r14, [rsp+78h+arg_38]
0x180025faa  mov     edi, [r14]
0x180025fad  mov     rbx, [rsp+78h+arg_78]
0x180025fb5  mov     [rbx+8], edi
0x180025fb8  mov     eax, [r14+4]
0x180025fbc  mov     [rbx+0Ch], eax
0x180025fbf  xor     ebp, ebp
0x180025fc1  mov     r15d, [rsp+78h+arg_30]
0x180025fc9  mov     ecx, r15d
0x180025fcc  test    r15d, r15d
0x180025fcf  jz      short loc_180026037
0x180025fd1  sub     ecx, 1
0x180025fd4  jz      short loc_18002602E
0x180025fd6  sub     ecx, 1
0x180025fd9  jz      short loc_180025FE9
0x180025fdb  cmp     ecx, 1
0x180025fde  jnz     short loc_180026040
0x180025fe0  mov     ecx, edi; this
0x180025fe2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180025fe7  jmp     short loc_18002603E
0x180025fe9  test    edi, edi
0x180025feb  js      short loc_180026025
0x180025fed  mov     edi, 8007029Ch
0x180025ff2  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180025ff6  mov     rax, [rsp+78h+arg_28]
0x180025ffe  mov     [rsp+78h+var_50], rax; __int64
0x180026003  mov     rax, [rsp+78h+arg_20]
0x18002600b  mov     [rsp+78h+var_58], rax; __int64
0x180026010  mov     rcx, r10; int
0x180026013  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180026018  mov     [rbx+8], edi
0x18002601b  mov     ecx, edi; this
0x18002601d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180026022  mov     [rbx+0Ch], eax
0x180026025  mov     ecx, edi; this
0x180026027  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18002602c  jmp     short loc_18002603E
0x18002602e  mov     ecx, edi; this
0x180026030  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180026035  jmp     short loc_18002603E
0x180026037  mov     ecx, edi; this
0x180026039  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18002603e  mov     ebp, eax
0x180026040  mov     [rbx], r15d
0x180026043  mov     eax, [rsp+78h+arg_70]
0x18002604a  mov     [rbx+4], eax
0x18002604d  cmp     dword ptr [r14+8], 1
0x180026052  jnz     short loc_18002605A
0x180026054  or      eax, 8
0x180026057  mov     [rbx+4], eax
0x18002605a  mov     eax, 1
0x18002605f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180026067  inc     eax
0x180026069  mov     [rbx+10h], eax
0x18002606c  mov     rax, [rsp+78h+arg_40]
0x180026074  xor     edi, edi
0x180026076  test    rax, rax
0x180026079  jz      short loc_180026080
0x18002607b  cmp     [rax], di
0x18002607e  jnz     short loc_180026083
0x180026080  mov     rax, rdi
0x180026083  mov     [rbx+18h], rax
0x180026087  call    cs:__imp_GetCurrentThreadId
0x18002608e  nop     dword ptr [rax+rax+00h]
0x180026093  mov     [rbx+20h], eax
0x180026096  mov     [rbx+38h], r13
0x18002609a  mov     eax, [rsp+78h+arg_8]
0x1800260a1  mov     [rbx+40h], eax
0x1800260a4  mov     [rbx+44h], ebp
0x1800260a7  mov     rax, [rsp+78h+arg_20]
0x1800260af  mov     [rbx+28h], rax
0x1800260b3  mov     [rbx+30h], r12
0x1800260b7  mov     rax, [rsp+78h+arg_28]
0x1800260bf  mov     [rbx+88h], rax
0x1800260c6  mov     rax, [rsp+78h+arg_0]
0x1800260ce  mov     [rbx+90h], rax
0x1800260d5  mov     [rbx+48h], rdi
0x1800260d9  xorps   xmm0, xmm0
0x1800260dc  xor     eax, eax
0x1800260de  movups  xmmword ptr [rbx+68h], xmm0
0x1800260e2  mov     [rbx+78h], rax
0x1800260e6  movups  xmmword ptr [rbx+50h], xmm0
0x1800260ea  mov     [rbx+60h], rax
0x1800260ee  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800260f5  test    rax, rax
0x1800260f8  jz      short loc_180026101
0x1800260fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800260ff  jmp     short loc_180026104
0x180026101  mov     rax, rdi
0x180026104  mov     [rbx+80h], rax
0x18002610b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180026112  test    rax, rax
0x180026115  jz      short loc_18002611F
0x180026117  mov     rcx, rbx
0x18002611a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002611f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180026126  test    rax, rax
0x180026129  jz      short loc_180026141
0x18002612b  mov     r8d, 400h
0x180026131  mov     rdx, [rsp+78h+arg_60]
0x180026139  mov     rcx, rbx
0x18002613c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026141  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180026148  test    rax, rax
0x18002614b  jz      short loc_180026155
0x18002614d  mov     rcx, rbx
0x180026150  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026155  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002615c  test    rax, rax
0x18002615f  jz      short loc_18002616F
0x180026161  test    byte ptr [rbx+4], 2
0x180026165  jnz     short loc_18002616F
0x180026167  mov     rcx, rbx
0x18002616a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002616f  cmp     [rbx+8], edi
0x180026172  jl      short loc_180026190
0x180026174  cmp     r15d, 3
0x180026178  jz      short loc_180026180
0x18002617a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180026180  mov     ecx, 8000FFFFh; this
0x180026185  mov     [rbx+8], ecx
0x180026188  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18002618d  mov     [rbx+0Ch], eax
0x180026190  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180026197  jnz     short loc_1800261BE
0x180026199  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800261a0  test    rax, rax
0x1800261a3  jz      short loc_1800261AE
0x1800261a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800261aa  test    al, al
0x1800261ac  jmp     short loc_1800261BC
0x1800261ae  call    cs:__imp_IsDebuggerPresent
0x1800261b5  nop     dword ptr [rax+rax+00h]
0x1800261ba  test    eax, eax
0x1800261bc  jz      short loc_1800261C4
0x1800261be  test    byte ptr [rbx+4], 2
0x1800261c2  jz      short loc_1800261E8
0x1800261c4  mov     rax, cs:g_pfnResultLoggingCallback
0x1800261cb  test    rax, rax
0x1800261ce  jz      short loc_180026232
0x1800261d0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800261d7  jnz     short loc_180026232
0x1800261d9  xor     r8d, r8d
0x1800261dc  xor     edx, edx
0x1800261de  mov     rcx, rbx
0x1800261e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800261e6  jmp     short loc_180026232
0x1800261e8  mov     ebp, 800h
0x1800261ed  mov     rax, cs:g_pfnResultLoggingCallback
0x1800261f4  test    rax, rax
0x1800261f7  jz      short loc_180026210
0x1800261f9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180026200  jnz     short loc_180026210
0x180026202  mov     r8d, ebp
0x180026205  mov     rdx, rsi
0x180026208  mov     rcx, rbx
0x18002620b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026210  cmp     [rsi], di
0x180026213  jnz     short loc_180026223
0x180026215  mov     r8, rbx; unsigned __int64
0x180026218  mov     rdx, rbp; unsigned __int16 *
0x18002621b  mov     rcx, rsi; this
0x18002621e  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180026223  mov     rcx, rsi; lpOutputString
0x180026226  call    cs:__imp_OutputDebugStringW
0x18002622d  nop     dword ptr [rax+rax+00h]
0x180026232  test    byte ptr [rbx+4], 4
0x180026236  jnz     short loc_180026241
0x180026238  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18002623f  jz      short loc_180026253
0x180026241  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180026248  test    rax, rax
0x18002624b  jz      short loc_180026253
0x18002624d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026252  nop
0x180026253  mov     rbx, [rsp+78h+arg_10]
0x18002625b  add     rsp, 40h
0x18002625f  pop     r15
0x180026261  pop     r14
0x180026263  pop     r13
0x180026265  pop     r12
0x180026267  pop     rdi
0x180026268  pop     rsi
0x180026269  pop     rbp
0x18002626a  retn
```
