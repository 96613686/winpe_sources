# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180011184`
- end: `0x18001147c`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18000f47c`
- `0x18000f7cc`

## callees

- `0x18000f3c4`
- `0x180010254`
- `0x180010a28`
- `0x180011184`
- `0x180011d80`
- `0x180011da0`
- `0x180011db4`
- `0x180011dd0`
- `0x1800146b8`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800112a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800112a7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800113c6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800113c6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180011438`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180011438`

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
0x180011184  mov     [rsp+arg_10], rbx
0x180011189  mov     [rsp+arg_8], edx
0x18001118d  mov     [rsp+arg_0], rcx
0x180011192  push    rbp
0x180011193  push    rsi
0x180011194  push    rdi
0x180011195  push    r12
0x180011197  push    r13
0x180011199  push    r14
0x18001119b  push    r15
0x18001119d  sub     rsp, 40h
0x1800111a1  mov     r14, [rsp+78h+arg_38]
0x1800111a9  xor     eax, eax
0x1800111ab  mov     rbx, [rsp+78h+arg_78]
0x1800111b3  xor     ebp, ebp
0x1800111b5  mov     r15d, [rsp+78h+arg_30]
0x1800111bd  mov     r10, rcx
0x1800111c0  mov     rsi, [rsp+78h+lpOutputString]
0x1800111c8  mov     r12, r9
0x1800111cb  mov     r13, r8
0x1800111ce  mov     ecx, r15d
0x1800111d1  mov     [rsi], ax
0x1800111d4  mov     rax, [rsp+78h+arg_60]
0x1800111dc  mov     byte ptr [rax], 0
0x1800111df  mov     edi, [r14]
0x1800111e2  mov     [rbx+8], edi
0x1800111e5  mov     eax, [r14+4]
0x1800111e9  mov     [rbx+0Ch], eax
0x1800111ec  test    r15d, r15d
0x1800111ef  jz      short loc_180011257
0x1800111f1  sub     ecx, 1
0x1800111f4  jz      short loc_18001124E
0x1800111f6  sub     ecx, 1
0x1800111f9  jz      short loc_180011209
0x1800111fb  cmp     ecx, 1
0x1800111fe  jnz     short loc_180011260
0x180011200  mov     ecx, edi; this
0x180011202  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180011207  jmp     short loc_18001125E
0x180011209  test    edi, edi
0x18001120b  js      short loc_180011245
0x18001120d  mov     rax, [rsp+78h+arg_28]
0x180011215  mov     edi, 8007029Ch
0x18001121a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18001121e  mov     rcx, r10; int
0x180011221  mov     [rsp+78h+var_50], rax; __int64
0x180011226  mov     rax, [rsp+78h+arg_20]
0x18001122e  mov     [rsp+78h+var_58], rax; __int64
0x180011233  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180011238  mov     ecx, edi; this
0x18001123a  mov     [rbx+8], edi
0x18001123d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180011242  mov     [rbx+0Ch], eax
0x180011245  mov     ecx, edi; this
0x180011247  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18001124c  jmp     short loc_18001125E
0x18001124e  mov     ecx, edi; this
0x180011250  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180011255  jmp     short loc_18001125E
0x180011257  mov     ecx, edi; this
0x180011259  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18001125e  mov     ebp, eax
0x180011260  mov     eax, [rsp+78h+arg_70]
0x180011267  mov     [rbx+4], eax
0x18001126a  mov     [rbx], r15d
0x18001126d  cmp     dword ptr [r14+8], 1
0x180011272  jnz     short loc_18001127A
0x180011274  or      eax, 8
0x180011277  mov     [rbx+4], eax
0x18001127a  mov     eax, 1
0x18001127f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180011287  inc     eax
0x180011289  xor     edi, edi
0x18001128b  mov     [rbx+10h], eax
0x18001128e  mov     rax, [rsp+78h+arg_40]
0x180011296  test    rax, rax
0x180011299  jz      short loc_1800112A0
0x18001129b  cmp     [rax], di
0x18001129e  jnz     short loc_1800112A3
0x1800112a0  mov     rax, rdi
0x1800112a3  mov     [rbx+18h], rax
0x1800112a7  call    cs:__imp_GetCurrentThreadId
0x1800112ad  mov     [rbx+38h], r13
0x1800112b1  xorps   xmm0, xmm0
0x1800112b4  mov     [rbx+20h], eax
0x1800112b7  mov     eax, [rsp+78h+arg_8]
0x1800112be  mov     [rbx+40h], eax
0x1800112c1  mov     rax, [rsp+78h+arg_20]
0x1800112c9  mov     [rbx+28h], rax
0x1800112cd  mov     rax, [rsp+78h+arg_28]
0x1800112d5  mov     [rbx+88h], rax
0x1800112dc  mov     rax, [rsp+78h+arg_0]
0x1800112e4  mov     [rbx+90h], rax
0x1800112eb  xor     eax, eax
0x1800112ed  mov     [rbx+44h], ebp
0x1800112f0  mov     [rbx+30h], r12
0x1800112f4  mov     [rbx+48h], rdi
0x1800112f8  movups  xmmword ptr [rbx+68h], xmm0
0x1800112fc  mov     [rbx+78h], rax
0x180011300  movups  xmmword ptr [rbx+50h], xmm0
0x180011304  mov     [rbx+60h], rax
0x180011308  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001130f  test    rax, rax
0x180011312  jz      short loc_18001131B
0x180011314  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011319  jmp     short loc_18001131E
0x18001131b  mov     rax, rdi
0x18001131e  mov     [rbx+80h], rax
0x180011325  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18001132c  test    rax, rax
0x18001132f  jz      short loc_180011339
0x180011331  mov     rcx, rbx
0x180011334  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011339  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180011340  test    rax, rax
0x180011343  jz      short loc_18001135B
0x180011345  mov     rdx, [rsp+78h+arg_60]
0x18001134d  mov     r8d, 400h
0x180011353  mov     rcx, rbx
0x180011356  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001135b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180011362  test    rax, rax
0x180011365  jz      short loc_18001136F
0x180011367  mov     rcx, rbx
0x18001136a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001136f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180011376  test    rax, rax
0x180011379  jz      short loc_180011389
0x18001137b  test    byte ptr [rbx+4], 2
0x18001137f  jnz     short loc_180011389
0x180011381  mov     rcx, rbx
0x180011384  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011389  cmp     [rbx+8], edi
0x18001138c  jl      short loc_1800113A8
0x18001138e  cmp     r15d, 3
0x180011392  jnz     loc_180011476
0x180011398  mov     ecx, 8000FFFFh; this
0x18001139d  mov     [rbx+8], ecx
0x1800113a0  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800113a5  mov     [rbx+0Ch], eax
0x1800113a8  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800113af  jnz     short loc_1800113D0
0x1800113b1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800113b8  test    rax, rax
0x1800113bb  jz      short loc_1800113C6
0x1800113bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113c2  test    al, al
0x1800113c4  jmp     short loc_1800113CE
0x1800113c6  call    cs:__imp_IsDebuggerPresent
0x1800113cc  test    eax, eax
0x1800113ce  jz      short loc_1800113D6
0x1800113d0  test    byte ptr [rbx+4], 2
0x1800113d4  jz      short loc_1800113FA
0x1800113d6  mov     rax, cs:g_pfnResultLoggingCallback
0x1800113dd  test    rax, rax
0x1800113e0  jz      short loc_18001143E
0x1800113e2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800113e9  jnz     short loc_18001143E
0x1800113eb  xor     r8d, r8d
0x1800113ee  xor     edx, edx
0x1800113f0  mov     rcx, rbx
0x1800113f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113f8  jmp     short loc_18001143E
0x1800113fa  mov     rax, cs:g_pfnResultLoggingCallback
0x180011401  mov     ebp, 800h
0x180011406  test    rax, rax
0x180011409  jz      short loc_180011422
0x18001140b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180011412  jnz     short loc_180011422
0x180011414  mov     r8d, ebp
0x180011417  mov     rdx, rsi
0x18001141a  mov     rcx, rbx
0x18001141d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011422  cmp     [rsi], di
0x180011425  jnz     short loc_180011435
0x180011427  mov     r8, rbx; unsigned __int64
0x18001142a  mov     rdx, rbp; unsigned __int16 *
0x18001142d  mov     rcx, rsi; this
0x180011430  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180011435  mov     rcx, rsi; lpOutputString
0x180011438  call    cs:__imp_OutputDebugStringW
0x18001143e  test    byte ptr [rbx+4], 4
0x180011442  jnz     short loc_18001144D
0x180011444  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18001144b  jz      short loc_18001145E
0x18001144d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180011454  test    rax, rax
0x180011457  jz      short loc_18001145E
0x180011459  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001145e  mov     rbx, [rsp+78h+arg_10]
0x180011466  add     rsp, 40h
0x18001146a  pop     r15
0x18001146c  pop     r14
0x18001146e  pop     r13
0x180011470  pop     r12
0x180011472  pop     rdi
0x180011473  pop     rsi
0x180011474  pop     rbp
0x180011475  retn
0x180011476  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
