# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140005174`
- end: `0x14000546d`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1400037b8`
- `0x140003b04`

## callees

- `0x1400036f8`
- `0x140004794`
- `0x140004fb0`
- `0x140005174`
- `0x140005868`
- `0x140005890`
- `0x1400058a4`
- `0x1400058c0`
- `0x140006564`
- `0x140018010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005297`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005297`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140005428`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140005428`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400053b6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400053b6`

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
0x140005174  mov     [rsp+arg_10], rbx
0x140005179  mov     [rsp+arg_8], edx
0x14000517d  mov     [rsp+arg_0], rcx
0x140005182  push    rbp
0x140005183  push    rsi
0x140005184  push    rdi
0x140005185  push    r12
0x140005187  push    r13
0x140005189  push    r14
0x14000518b  push    r15
0x14000518d  sub     rsp, 40h
0x140005191  mov     r12, r9
0x140005194  mov     r13, r8
0x140005197  mov     r10, rcx
0x14000519a  xor     eax, eax
0x14000519c  mov     rsi, [rsp+78h+lpOutputString]
0x1400051a4  mov     [rsi], ax
0x1400051a7  mov     rax, [rsp+78h+arg_60]
0x1400051af  mov     byte ptr [rax], 0
0x1400051b2  mov     r14, [rsp+78h+arg_38]
0x1400051ba  mov     edi, [r14]
0x1400051bd  mov     rbx, [rsp+78h+arg_78]
0x1400051c5  mov     [rbx+8], edi
0x1400051c8  mov     eax, [r14+4]
0x1400051cc  mov     [rbx+0Ch], eax
0x1400051cf  xor     ebp, ebp
0x1400051d1  mov     r15d, [rsp+78h+arg_30]
0x1400051d9  mov     ecx, r15d
0x1400051dc  test    r15d, r15d
0x1400051df  jz      short loc_140005247
0x1400051e1  sub     ecx, 1
0x1400051e4  jz      short loc_14000523E
0x1400051e6  sub     ecx, 1
0x1400051e9  jz      short loc_1400051F9
0x1400051eb  cmp     ecx, 1
0x1400051ee  jnz     short loc_140005250
0x1400051f0  mov     ecx, edi; this
0x1400051f2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1400051f7  jmp     short loc_14000524E
0x1400051f9  test    edi, edi
0x1400051fb  js      short loc_140005235
0x1400051fd  mov     edi, 8007029Ch
0x140005202  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x140005206  mov     rax, [rsp+78h+arg_28]
0x14000520e  mov     [rsp+78h+var_50], rax; __int64
0x140005213  mov     rax, [rsp+78h+arg_20]
0x14000521b  mov     [rsp+78h+var_58], rax; __int64
0x140005220  mov     rcx, r10; int
0x140005223  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140005228  mov     [rbx+8], edi
0x14000522b  mov     ecx, edi; this
0x14000522d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140005232  mov     [rbx+0Ch], eax
0x140005235  mov     ecx, edi; this
0x140005237  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x14000523c  jmp     short loc_14000524E
0x14000523e  mov     ecx, edi; this
0x140005240  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140005245  jmp     short loc_14000524E
0x140005247  mov     ecx, edi; this
0x140005249  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x14000524e  mov     ebp, eax
0x140005250  mov     [rbx], r15d
0x140005253  mov     eax, [rsp+78h+arg_70]
0x14000525a  mov     [rbx+4], eax
0x14000525d  cmp     dword ptr [r14+8], 1
0x140005262  jnz     short loc_14000526A
0x140005264  or      eax, 8
0x140005267  mov     [rbx+4], eax
0x14000526a  mov     eax, 1
0x14000526f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140005277  inc     eax
0x140005279  mov     [rbx+10h], eax
0x14000527c  mov     rax, [rsp+78h+arg_40]
0x140005284  xor     edi, edi
0x140005286  test    rax, rax
0x140005289  jz      short loc_140005290
0x14000528b  cmp     [rax], di
0x14000528e  jnz     short loc_140005293
0x140005290  mov     rax, rdi
0x140005293  mov     [rbx+18h], rax
0x140005297  call    cs:__imp_GetCurrentThreadId
0x14000529d  mov     [rbx+20h], eax
0x1400052a0  mov     [rbx+38h], r13
0x1400052a4  mov     eax, [rsp+78h+arg_8]
0x1400052ab  mov     [rbx+40h], eax
0x1400052ae  mov     [rbx+44h], ebp
0x1400052b1  mov     rax, [rsp+78h+arg_20]
0x1400052b9  mov     [rbx+28h], rax
0x1400052bd  mov     [rbx+30h], r12
0x1400052c1  mov     rax, [rsp+78h+arg_28]
0x1400052c9  mov     [rbx+88h], rax
0x1400052d0  mov     rax, [rsp+78h+arg_0]
0x1400052d8  mov     [rbx+90h], rax
0x1400052df  mov     [rbx+48h], rdi
0x1400052e3  xorps   xmm0, xmm0
0x1400052e6  xor     eax, eax
0x1400052e8  movups  xmmword ptr [rbx+68h], xmm0
0x1400052ec  mov     [rbx+78h], rax
0x1400052f0  movups  xmmword ptr [rbx+50h], xmm0
0x1400052f4  mov     [rbx+60h], rax
0x1400052f8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1400052ff  test    rax, rax
0x140005302  jz      short loc_14000530B
0x140005304  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005309  jmp     short loc_14000530E
0x14000530b  mov     rax, rdi
0x14000530e  mov     [rbx+80h], rax
0x140005315  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14000531c  test    rax, rax
0x14000531f  jz      short loc_140005329
0x140005321  mov     rcx, rbx
0x140005324  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005329  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140005330  test    rax, rax
0x140005333  jz      short loc_14000534B
0x140005335  mov     r8d, 400h
0x14000533b  mov     rdx, [rsp+78h+arg_60]
0x140005343  mov     rcx, rbx
0x140005346  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000534b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140005352  test    rax, rax
0x140005355  jz      short loc_14000535F
0x140005357  mov     rcx, rbx
0x14000535a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000535f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140005366  test    rax, rax
0x140005369  jz      short loc_140005379
0x14000536b  test    byte ptr [rbx+4], 2
0x14000536f  jnz     short loc_140005379
0x140005371  mov     rcx, rbx
0x140005374  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005379  cmp     [rbx+8], edi
0x14000537c  jl      short loc_140005398
0x14000537e  cmp     r15d, 3
0x140005382  jnz     loc_140005467
0x140005388  mov     ecx, 8000FFFFh; this
0x14000538d  mov     [rbx+8], ecx
0x140005390  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140005395  mov     [rbx+0Ch], eax
0x140005398  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x14000539f  jnz     short loc_1400053C0
0x1400053a1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400053a8  test    rax, rax
0x1400053ab  jz      short loc_1400053B6
0x1400053ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400053b2  test    al, al
0x1400053b4  jmp     short loc_1400053BE
0x1400053b6  call    cs:__imp_IsDebuggerPresent
0x1400053bc  test    eax, eax
0x1400053be  jz      short loc_1400053C6
0x1400053c0  test    byte ptr [rbx+4], 2
0x1400053c4  jz      short loc_1400053EA
0x1400053c6  mov     rax, cs:g_pfnResultLoggingCallback
0x1400053cd  test    rax, rax
0x1400053d0  jz      short loc_14000542E
0x1400053d2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1400053d9  jnz     short loc_14000542E
0x1400053db  xor     r8d, r8d
0x1400053de  xor     edx, edx
0x1400053e0  mov     rcx, rbx
0x1400053e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400053e8  jmp     short loc_14000542E
0x1400053ea  mov     ebp, 800h
0x1400053ef  mov     rax, cs:g_pfnResultLoggingCallback
0x1400053f6  test    rax, rax
0x1400053f9  jz      short loc_140005412
0x1400053fb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140005402  jnz     short loc_140005412
0x140005404  mov     r8d, ebp
0x140005407  mov     rdx, rsi
0x14000540a  mov     rcx, rbx
0x14000540d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005412  cmp     [rsi], di
0x140005415  jnz     short loc_140005425
0x140005417  mov     r8, rbx; unsigned __int64
0x14000541a  mov     rdx, rbp; unsigned __int16 *
0x14000541d  mov     rcx, rsi; this
0x140005420  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140005425  mov     rcx, rsi; lpOutputString
0x140005428  call    cs:__imp_OutputDebugStringW
0x14000542e  test    byte ptr [rbx+4], 4
0x140005432  jnz     short loc_14000543D
0x140005434  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x14000543b  jz      short loc_14000544F
0x14000543d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140005444  test    rax, rax
0x140005447  jz      short loc_14000544F
0x140005449  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000544e  nop
0x14000544f  mov     rbx, [rsp+78h+arg_10]
0x140005457  add     rsp, 40h
0x14000545b  pop     r15
0x14000545d  pop     r14
0x14000545f  pop     r13
0x140005461  pop     r12
0x140005463  pop     rdi
0x140005464  pop     rsi
0x140005465  pop     rbp
0x140005466  retn
0x140005467  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
