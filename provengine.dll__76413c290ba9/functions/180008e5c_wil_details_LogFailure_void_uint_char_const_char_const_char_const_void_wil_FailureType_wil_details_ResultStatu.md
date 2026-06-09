# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180008e5c`
- end: `0x180009155`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180007010`

## callees

- `0x180004494`
- `0x1800048d0`
- `0x180004e00`
- `0x180006a1c`
- `0x180008e5c`
- `0x18000965c`
- `0x180009678`
- `0x180009694`
- `0x18000ad08`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008f7f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008f7f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009110`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009110`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000909e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000909e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
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
0x180008e5c  mov     [rsp+arg_10], rbx
0x180008e61  mov     [rsp+arg_8], edx
0x180008e65  mov     [rsp+arg_0], rcx
0x180008e6a  push    rbp
0x180008e6b  push    rsi
0x180008e6c  push    rdi
0x180008e6d  push    r12
0x180008e6f  push    r13
0x180008e71  push    r14
0x180008e73  push    r15
0x180008e75  sub     rsp, 40h
0x180008e79  mov     r12, r9
0x180008e7c  mov     r13, r8
0x180008e7f  mov     r10, rcx
0x180008e82  xor     eax, eax
0x180008e84  mov     rsi, [rsp+78h+lpOutputString]
0x180008e8c  mov     [rsi], ax
0x180008e8f  mov     rax, [rsp+78h+arg_60]
0x180008e97  mov     byte ptr [rax], 0
0x180008e9a  mov     r14, [rsp+78h+arg_38]
0x180008ea2  mov     edi, [r14]
0x180008ea5  mov     rbx, [rsp+78h+arg_78]
0x180008ead  mov     [rbx+8], edi
0x180008eb0  mov     eax, [r14+4]
0x180008eb4  mov     [rbx+0Ch], eax
0x180008eb7  xor     ebp, ebp
0x180008eb9  mov     r15d, [rsp+78h+arg_30]
0x180008ec1  mov     ecx, r15d
0x180008ec4  test    r15d, r15d
0x180008ec7  jz      short loc_180008F2F
0x180008ec9  sub     ecx, 1
0x180008ecc  jz      short loc_180008F26
0x180008ece  sub     ecx, 1
0x180008ed1  jz      short loc_180008EE1
0x180008ed3  cmp     ecx, 1
0x180008ed6  jnz     short loc_180008F38
0x180008ed8  mov     ecx, edi; this
0x180008eda  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180008edf  jmp     short loc_180008F36
0x180008ee1  test    edi, edi
0x180008ee3  js      short loc_180008F1D
0x180008ee5  mov     edi, 8007029Ch
0x180008eea  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180008eee  mov     rax, [rsp+78h+arg_28]
0x180008ef6  mov     [rsp+78h+var_50], rax; __int64
0x180008efb  mov     rax, [rsp+78h+arg_20]
0x180008f03  mov     [rsp+78h+var_58], rax; __int64
0x180008f08  mov     rcx, r10; int
0x180008f0b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180008f10  mov     [rbx+8], edi
0x180008f13  mov     ecx, edi; this
0x180008f15  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180008f1a  mov     [rbx+0Ch], eax
0x180008f1d  mov     ecx, edi; this
0x180008f1f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180008f24  jmp     short loc_180008F36
0x180008f26  mov     ecx, edi; this
0x180008f28  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180008f2d  jmp     short loc_180008F36
0x180008f2f  mov     ecx, edi; this
0x180008f31  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180008f36  mov     ebp, eax
0x180008f38  mov     [rbx], r15d
0x180008f3b  mov     eax, [rsp+78h+arg_70]
0x180008f42  mov     [rbx+4], eax
0x180008f45  cmp     dword ptr [r14+8], 1
0x180008f4a  jnz     short loc_180008F52
0x180008f4c  or      eax, 8
0x180008f4f  mov     [rbx+4], eax
0x180008f52  mov     eax, 1
0x180008f57  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180008f5f  inc     eax
0x180008f61  mov     [rbx+10h], eax
0x180008f64  mov     rax, [rsp+78h+arg_40]
0x180008f6c  xor     edi, edi
0x180008f6e  test    rax, rax
0x180008f71  jz      short loc_180008F78
0x180008f73  cmp     [rax], di
0x180008f76  jnz     short loc_180008F7B
0x180008f78  mov     rax, rdi
0x180008f7b  mov     [rbx+18h], rax
0x180008f7f  call    cs:__imp_GetCurrentThreadId
0x180008f85  mov     [rbx+20h], eax
0x180008f88  mov     [rbx+38h], r13
0x180008f8c  mov     eax, [rsp+78h+arg_8]
0x180008f93  mov     [rbx+40h], eax
0x180008f96  mov     [rbx+44h], ebp
0x180008f99  mov     rax, [rsp+78h+arg_20]
0x180008fa1  mov     [rbx+28h], rax
0x180008fa5  mov     [rbx+30h], r12
0x180008fa9  mov     rax, [rsp+78h+arg_28]
0x180008fb1  mov     [rbx+88h], rax
0x180008fb8  mov     rax, [rsp+78h+arg_0]
0x180008fc0  mov     [rbx+90h], rax
0x180008fc7  mov     [rbx+48h], rdi
0x180008fcb  xorps   xmm0, xmm0
0x180008fce  xor     eax, eax
0x180008fd0  movups  xmmword ptr [rbx+68h], xmm0
0x180008fd4  mov     [rbx+78h], rax
0x180008fd8  movups  xmmword ptr [rbx+50h], xmm0
0x180008fdc  mov     [rbx+60h], rax
0x180008fe0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180008fe7  test    rax, rax
0x180008fea  jz      short loc_180008FF3
0x180008fec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ff1  jmp     short loc_180008FF6
0x180008ff3  mov     rax, rdi
0x180008ff6  mov     [rbx+80h], rax
0x180008ffd  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180009004  test    rax, rax
0x180009007  jz      short loc_180009011
0x180009009  mov     rcx, rbx
0x18000900c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009011  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180009018  test    rax, rax
0x18000901b  jz      short loc_180009033
0x18000901d  mov     r8d, 400h
0x180009023  mov     rdx, [rsp+78h+arg_60]
0x18000902b  mov     rcx, rbx
0x18000902e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009033  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000903a  test    rax, rax
0x18000903d  jz      short loc_180009047
0x18000903f  mov     rcx, rbx
0x180009042  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009047  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000904e  test    rax, rax
0x180009051  jz      short loc_180009061
0x180009053  test    byte ptr [rbx+4], 2
0x180009057  jnz     short loc_180009061
0x180009059  mov     rcx, rbx
0x18000905c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009061  cmp     [rbx+8], edi
0x180009064  jl      short loc_180009080
0x180009066  cmp     r15d, 3
0x18000906a  jnz     loc_18000914F
0x180009070  mov     ecx, 8000FFFFh; this
0x180009075  mov     [rbx+8], ecx
0x180009078  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000907d  mov     [rbx+0Ch], eax
0x180009080  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180009087  jnz     short loc_1800090A8
0x180009089  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180009090  test    rax, rax
0x180009093  jz      short loc_18000909E
0x180009095  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000909a  test    al, al
0x18000909c  jmp     short loc_1800090A6
0x18000909e  call    cs:__imp_IsDebuggerPresent
0x1800090a4  test    eax, eax
0x1800090a6  jz      short loc_1800090AE
0x1800090a8  test    byte ptr [rbx+4], 2
0x1800090ac  jz      short loc_1800090D2
0x1800090ae  mov     rax, cs:g_pfnResultLoggingCallback
0x1800090b5  test    rax, rax
0x1800090b8  jz      short loc_180009116
0x1800090ba  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800090c1  jnz     short loc_180009116
0x1800090c3  xor     r8d, r8d
0x1800090c6  xor     edx, edx
0x1800090c8  mov     rcx, rbx
0x1800090cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090d0  jmp     short loc_180009116
0x1800090d2  mov     ebp, 800h
0x1800090d7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800090de  test    rax, rax
0x1800090e1  jz      short loc_1800090FA
0x1800090e3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800090ea  jnz     short loc_1800090FA
0x1800090ec  mov     r8d, ebp
0x1800090ef  mov     rdx, rsi
0x1800090f2  mov     rcx, rbx
0x1800090f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090fa  cmp     [rsi], di
0x1800090fd  jnz     short loc_18000910D
0x1800090ff  mov     r8, rbx; unsigned __int64
0x180009102  mov     rdx, rbp; unsigned __int16 *
0x180009105  mov     rcx, rsi; this
0x180009108  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000910d  mov     rcx, rsi; lpOutputString
0x180009110  call    cs:__imp_OutputDebugStringW
0x180009116  test    byte ptr [rbx+4], 4
0x18000911a  jnz     short loc_180009125
0x18000911c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180009123  jz      short loc_180009137
0x180009125  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000912c  test    rax, rax
0x18000912f  jz      short loc_180009137
0x180009131  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009136  nop
0x180009137  mov     rbx, [rsp+78h+arg_10]
0x18000913f  add     rsp, 40h
0x180009143  pop     r15
0x180009145  pop     r14
0x180009147  pop     r13
0x180009149  pop     r12
0x18000914b  pop     rdi
0x18000914c  pop     rsi
0x18000914d  pop     rbp
0x18000914e  retn
0x18000914f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
