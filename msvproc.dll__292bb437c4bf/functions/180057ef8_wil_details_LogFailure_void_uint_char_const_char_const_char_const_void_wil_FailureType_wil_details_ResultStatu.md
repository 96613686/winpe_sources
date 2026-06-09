# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180057ef8`
- end: `0x1800581ec`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `756`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180056250`
- `0x180056304`
- `0x1800563f8`

## callees

- `0x18004ddec`
- `0x1800561a0`
- `0x180057374`
- `0x180057ef8`
- `0x1800586f8`
- `0x180058720`
- `0x180058734`
- `0x180058750`
- `0x18005932c`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005801b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005801b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18005813c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18005813c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800581ae`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800581ae`

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
0x180057ef8  mov     [rsp+arg_10], rbx
0x180057efd  mov     [rsp+arg_8], edx
0x180057f01  mov     [rsp+arg_0], rcx
0x180057f06  push    rbp
0x180057f07  push    rsi
0x180057f08  push    rdi
0x180057f09  push    r12
0x180057f0b  push    r13
0x180057f0d  push    r14
0x180057f0f  push    r15
0x180057f11  sub     rsp, 40h
0x180057f15  mov     r14, [rsp+78h+arg_38]
0x180057f1d  xor     eax, eax
0x180057f1f  mov     rbx, [rsp+78h+arg_78]
0x180057f27  xor     ebp, ebp
0x180057f29  mov     r15d, [rsp+78h+arg_30]
0x180057f31  mov     r10, rcx
0x180057f34  mov     rsi, [rsp+78h+lpOutputString]
0x180057f3c  mov     r12, r9
0x180057f3f  mov     r13, r8
0x180057f42  mov     ecx, r15d
0x180057f45  mov     [rsi], ax
0x180057f48  mov     rax, [rsp+78h+arg_60]
0x180057f50  mov     byte ptr [rax], 0
0x180057f53  mov     edi, [r14]
0x180057f56  mov     [rbx+8], edi
0x180057f59  mov     eax, [r14+4]
0x180057f5d  mov     [rbx+0Ch], eax
0x180057f60  test    r15d, r15d
0x180057f63  jz      short loc_180057FCB
0x180057f65  sub     ecx, 1
0x180057f68  jz      short loc_180057FC2
0x180057f6a  sub     ecx, 1
0x180057f6d  jz      short loc_180057F7D
0x180057f6f  cmp     ecx, 1
0x180057f72  jnz     short loc_180057FD4
0x180057f74  mov     ecx, edi; this
0x180057f76  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180057f7b  jmp     short loc_180057FD2
0x180057f7d  test    edi, edi
0x180057f7f  js      short loc_180057FB9
0x180057f81  mov     rax, [rsp+78h+arg_28]
0x180057f89  mov     edi, 8007029Ch
0x180057f8e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180057f92  mov     rcx, r10; int
0x180057f95  mov     [rsp+78h+var_50], rax; __int64
0x180057f9a  mov     rax, [rsp+78h+arg_20]
0x180057fa2  mov     [rsp+78h+var_58], rax; __int64
0x180057fa7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180057fac  mov     ecx, edi; this
0x180057fae  mov     [rbx+8], edi
0x180057fb1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180057fb6  mov     [rbx+0Ch], eax
0x180057fb9  mov     ecx, edi; this
0x180057fbb  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180057fc0  jmp     short loc_180057FD2
0x180057fc2  mov     ecx, edi; this
0x180057fc4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180057fc9  jmp     short loc_180057FD2
0x180057fcb  mov     ecx, edi; this
0x180057fcd  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180057fd2  mov     ebp, eax
0x180057fd4  mov     eax, [rsp+78h+arg_70]
0x180057fdb  mov     [rbx+4], eax
0x180057fde  mov     [rbx], r15d
0x180057fe1  cmp     dword ptr [r14+8], 1
0x180057fe6  jnz     short loc_180057FEE
0x180057fe8  or      eax, 8
0x180057feb  mov     [rbx+4], eax
0x180057fee  mov     eax, 1
0x180057ff3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180057ffb  inc     eax
0x180057ffd  xor     edi, edi
0x180057fff  mov     [rbx+10h], eax
0x180058002  mov     rax, [rsp+78h+arg_40]
0x18005800a  test    rax, rax
0x18005800d  jz      short loc_180058014
0x18005800f  cmp     [rax], di
0x180058012  jnz     short loc_180058017
0x180058014  mov     rax, rdi
0x180058017  mov     [rbx+18h], rax
0x18005801b  call    cs:__imp_GetCurrentThreadId
0x180058021  mov     [rbx+38h], r13
0x180058025  xorps   xmm0, xmm0
0x180058028  mov     [rbx+20h], eax
0x18005802b  mov     eax, [rsp+78h+arg_8]
0x180058032  mov     [rbx+40h], eax
0x180058035  mov     rax, [rsp+78h+arg_20]
0x18005803d  mov     [rbx+28h], rax
0x180058041  mov     rax, [rsp+78h+arg_28]
0x180058049  mov     [rbx+88h], rax
0x180058050  mov     rax, [rsp+78h+arg_0]
0x180058058  mov     [rbx+90h], rax
0x18005805f  xor     eax, eax
0x180058061  mov     [rbx+44h], ebp
0x180058064  mov     [rbx+30h], r12
0x180058068  mov     [rbx+48h], rdi
0x18005806c  movups  xmmword ptr [rbx+68h], xmm0
0x180058070  mov     [rbx+78h], rax
0x180058074  movups  xmmword ptr [rbx+50h], xmm0
0x180058078  mov     [rbx+60h], rax
0x18005807c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180058083  test    rax, rax
0x180058086  jz      short loc_18005808F
0x180058088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005808d  jmp     short loc_180058092
0x18005808f  mov     rax, rdi
0x180058092  mov     [rbx+80h], rax
0x180058099  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800580a0  test    rax, rax
0x1800580a3  jz      short loc_1800580AD
0x1800580a5  mov     rcx, rbx
0x1800580a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800580ad  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800580b4  test    rax, rax
0x1800580b7  jz      short loc_1800580CF
0x1800580b9  mov     rdx, [rsp+78h+arg_60]
0x1800580c1  mov     r8d, 400h
0x1800580c7  mov     rcx, rbx
0x1800580ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800580cf  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800580d6  test    rax, rax
0x1800580d9  jz      short loc_1800580E3
0x1800580db  mov     rcx, rbx
0x1800580de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800580e3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800580ea  test    rax, rax
0x1800580ed  jz      short loc_1800580FD
0x1800580ef  test    byte ptr [rbx+4], 2
0x1800580f3  jnz     short loc_1800580FD
0x1800580f5  mov     rcx, rbx
0x1800580f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800580fd  cmp     [rbx+8], edi
0x180058100  jl      short loc_18005811E
0x180058102  cmp     r15d, 3
0x180058106  jz      short loc_18005810E
0x180058108  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18005810e  mov     ecx, 8000FFFFh; this
0x180058113  mov     [rbx+8], ecx
0x180058116  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18005811b  mov     [rbx+0Ch], eax
0x18005811e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180058125  jnz     short loc_180058146
0x180058127  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18005812e  test    rax, rax
0x180058131  jz      short loc_18005813C
0x180058133  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058138  test    al, al
0x18005813a  jmp     short loc_180058144
0x18005813c  call    cs:__imp_IsDebuggerPresent
0x180058142  test    eax, eax
0x180058144  jz      short loc_18005814C
0x180058146  test    byte ptr [rbx+4], 2
0x18005814a  jz      short loc_180058170
0x18005814c  mov     rax, cs:g_pfnResultLoggingCallback
0x180058153  test    rax, rax
0x180058156  jz      short loc_1800581B4
0x180058158  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18005815f  jnz     short loc_1800581B4
0x180058161  xor     r8d, r8d
0x180058164  xor     edx, edx
0x180058166  mov     rcx, rbx
0x180058169  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005816e  jmp     short loc_1800581B4
0x180058170  mov     rax, cs:g_pfnResultLoggingCallback
0x180058177  mov     ebp, 800h
0x18005817c  test    rax, rax
0x18005817f  jz      short loc_180058198
0x180058181  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180058188  jnz     short loc_180058198
0x18005818a  mov     r8d, ebp
0x18005818d  mov     rdx, rsi
0x180058190  mov     rcx, rbx
0x180058193  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058198  cmp     [rsi], di
0x18005819b  jnz     short loc_1800581AB
0x18005819d  mov     r8, rbx; unsigned __int64
0x1800581a0  mov     rdx, rbp; unsigned __int16 *
0x1800581a3  mov     rcx, rsi; this
0x1800581a6  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800581ab  mov     rcx, rsi; lpOutputString
0x1800581ae  call    cs:__imp_OutputDebugStringW
0x1800581b4  test    byte ptr [rbx+4], 4
0x1800581b8  jnz     short loc_1800581C3
0x1800581ba  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800581c1  jz      short loc_1800581D4
0x1800581c3  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800581ca  test    rax, rax
0x1800581cd  jz      short loc_1800581D4
0x1800581cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800581d4  mov     rbx, [rsp+78h+arg_10]
0x1800581dc  add     rsp, 40h
0x1800581e0  pop     r15
0x1800581e2  pop     r14
0x1800581e4  pop     r13
0x1800581e6  pop     r12
0x1800581e8  pop     rdi
0x1800581e9  pop     rsi
0x1800581ea  pop     rbp
0x1800581eb  retn
```
