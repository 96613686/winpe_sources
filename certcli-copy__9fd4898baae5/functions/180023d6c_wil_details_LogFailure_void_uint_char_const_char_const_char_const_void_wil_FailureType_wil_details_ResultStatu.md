# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180023d6c`
- end: `0x180024065`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800221d4`

## callees

- `0x18001b934`
- `0x18001bc44`
- `0x18001c020`
- `0x180021c10`
- `0x180023d6c`
- `0x180024918`
- `0x180024aa4`
- `0x180024ac0`
- `0x180025eb0`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023e8f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023e8f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180024020`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180024020`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180023fae`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180023fae`

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
0x180023d6c  mov     [rsp+arg_10], rbx
0x180023d71  mov     [rsp+arg_8], edx
0x180023d75  mov     [rsp+arg_0], rcx
0x180023d7a  push    rbp
0x180023d7b  push    rsi
0x180023d7c  push    rdi
0x180023d7d  push    r12
0x180023d7f  push    r13
0x180023d81  push    r14
0x180023d83  push    r15
0x180023d85  sub     rsp, 40h
0x180023d89  mov     r12, r9
0x180023d8c  mov     r13, r8
0x180023d8f  mov     r10, rcx
0x180023d92  xor     eax, eax
0x180023d94  mov     rsi, [rsp+78h+lpOutputString]
0x180023d9c  mov     [rsi], ax
0x180023d9f  mov     rax, [rsp+78h+arg_60]
0x180023da7  mov     byte ptr [rax], 0
0x180023daa  mov     r14, [rsp+78h+arg_38]
0x180023db2  mov     edi, [r14]
0x180023db5  mov     rbx, [rsp+78h+arg_78]
0x180023dbd  mov     [rbx+8], edi
0x180023dc0  mov     eax, [r14+4]
0x180023dc4  mov     [rbx+0Ch], eax
0x180023dc7  xor     ebp, ebp
0x180023dc9  mov     r15d, [rsp+78h+arg_30]
0x180023dd1  mov     ecx, r15d
0x180023dd4  test    r15d, r15d
0x180023dd7  jz      short loc_180023E3F
0x180023dd9  sub     ecx, 1
0x180023ddc  jz      short loc_180023E36
0x180023dde  sub     ecx, 1
0x180023de1  jz      short loc_180023DF1
0x180023de3  cmp     ecx, 1
0x180023de6  jnz     short loc_180023E48
0x180023de8  mov     ecx, edi; this
0x180023dea  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180023def  jmp     short loc_180023E46
0x180023df1  test    edi, edi
0x180023df3  js      short loc_180023E2D
0x180023df5  mov     edi, 8007029Ch
0x180023dfa  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180023dfe  mov     rax, [rsp+78h+arg_28]
0x180023e06  mov     [rsp+78h+var_50], rax; __int64
0x180023e0b  mov     rax, [rsp+78h+arg_20]
0x180023e13  mov     [rsp+78h+var_58], rax; __int64
0x180023e18  mov     rcx, r10; int
0x180023e1b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180023e20  mov     [rbx+8], edi
0x180023e23  mov     ecx, edi; this
0x180023e25  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180023e2a  mov     [rbx+0Ch], eax
0x180023e2d  mov     ecx, edi; this
0x180023e2f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180023e34  jmp     short loc_180023E46
0x180023e36  mov     ecx, edi; this
0x180023e38  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180023e3d  jmp     short loc_180023E46
0x180023e3f  mov     ecx, edi; this
0x180023e41  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180023e46  mov     ebp, eax
0x180023e48  mov     [rbx], r15d
0x180023e4b  mov     eax, [rsp+78h+arg_70]
0x180023e52  mov     [rbx+4], eax
0x180023e55  cmp     dword ptr [r14+8], 1
0x180023e5a  jnz     short loc_180023E62
0x180023e5c  or      eax, 8
0x180023e5f  mov     [rbx+4], eax
0x180023e62  mov     eax, 1
0x180023e67  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180023e6f  inc     eax
0x180023e71  mov     [rbx+10h], eax
0x180023e74  mov     rax, [rsp+78h+arg_40]
0x180023e7c  xor     edi, edi
0x180023e7e  test    rax, rax
0x180023e81  jz      short loc_180023E88
0x180023e83  cmp     [rax], di
0x180023e86  jnz     short loc_180023E8B
0x180023e88  mov     rax, rdi
0x180023e8b  mov     [rbx+18h], rax
0x180023e8f  call    cs:__imp_GetCurrentThreadId
0x180023e95  mov     [rbx+20h], eax
0x180023e98  mov     [rbx+38h], r13
0x180023e9c  mov     eax, [rsp+78h+arg_8]
0x180023ea3  mov     [rbx+40h], eax
0x180023ea6  mov     [rbx+44h], ebp
0x180023ea9  mov     rax, [rsp+78h+arg_20]
0x180023eb1  mov     [rbx+28h], rax
0x180023eb5  mov     [rbx+30h], r12
0x180023eb9  mov     rax, [rsp+78h+arg_28]
0x180023ec1  mov     [rbx+88h], rax
0x180023ec8  mov     rax, [rsp+78h+arg_0]
0x180023ed0  mov     [rbx+90h], rax
0x180023ed7  mov     [rbx+48h], rdi
0x180023edb  xorps   xmm0, xmm0
0x180023ede  xor     eax, eax
0x180023ee0  movups  xmmword ptr [rbx+68h], xmm0
0x180023ee4  mov     [rbx+78h], rax
0x180023ee8  movups  xmmword ptr [rbx+50h], xmm0
0x180023eec  mov     [rbx+60h], rax
0x180023ef0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180023ef7  test    rax, rax
0x180023efa  jz      short loc_180023F03
0x180023efc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023f01  jmp     short loc_180023F06
0x180023f03  mov     rax, rdi
0x180023f06  mov     [rbx+80h], rax
0x180023f0d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180023f14  test    rax, rax
0x180023f17  jz      short loc_180023F21
0x180023f19  mov     rcx, rbx
0x180023f1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023f21  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180023f28  test    rax, rax
0x180023f2b  jz      short loc_180023F43
0x180023f2d  mov     r8d, 400h
0x180023f33  mov     rdx, [rsp+78h+arg_60]
0x180023f3b  mov     rcx, rbx
0x180023f3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023f43  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180023f4a  test    rax, rax
0x180023f4d  jz      short loc_180023F57
0x180023f4f  mov     rcx, rbx
0x180023f52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023f57  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180023f5e  test    rax, rax
0x180023f61  jz      short loc_180023F71
0x180023f63  test    byte ptr [rbx+4], 2
0x180023f67  jnz     short loc_180023F71
0x180023f69  mov     rcx, rbx
0x180023f6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023f71  cmp     [rbx+8], edi
0x180023f74  jl      short loc_180023F90
0x180023f76  cmp     r15d, 3
0x180023f7a  jnz     loc_18002405F
0x180023f80  mov     ecx, 8000FFFFh; this
0x180023f85  mov     [rbx+8], ecx
0x180023f88  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180023f8d  mov     [rbx+0Ch], eax
0x180023f90  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180023f97  jnz     short loc_180023FB8
0x180023f99  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180023fa0  test    rax, rax
0x180023fa3  jz      short loc_180023FAE
0x180023fa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023faa  test    al, al
0x180023fac  jmp     short loc_180023FB6
0x180023fae  call    cs:__imp_IsDebuggerPresent
0x180023fb4  test    eax, eax
0x180023fb6  jz      short loc_180023FBE
0x180023fb8  test    byte ptr [rbx+4], 2
0x180023fbc  jz      short loc_180023FE2
0x180023fbe  mov     rax, cs:g_pfnResultLoggingCallback
0x180023fc5  test    rax, rax
0x180023fc8  jz      short loc_180024026
0x180023fca  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180023fd1  jnz     short loc_180024026
0x180023fd3  xor     r8d, r8d
0x180023fd6  xor     edx, edx
0x180023fd8  mov     rcx, rbx
0x180023fdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023fe0  jmp     short loc_180024026
0x180023fe2  mov     ebp, 800h
0x180023fe7  mov     rax, cs:g_pfnResultLoggingCallback
0x180023fee  test    rax, rax
0x180023ff1  jz      short loc_18002400A
0x180023ff3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180023ffa  jnz     short loc_18002400A
0x180023ffc  mov     r8d, ebp
0x180023fff  mov     rdx, rsi
0x180024002  mov     rcx, rbx
0x180024005  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002400a  cmp     [rsi], di
0x18002400d  jnz     short loc_18002401D
0x18002400f  mov     r8, rbx; unsigned __int64
0x180024012  mov     rdx, rbp; unsigned __int16 *
0x180024015  mov     rcx, rsi; this
0x180024018  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18002401d  mov     rcx, rsi; lpOutputString
0x180024020  call    cs:__imp_OutputDebugStringW
0x180024026  test    byte ptr [rbx+4], 4
0x18002402a  jnz     short loc_180024035
0x18002402c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180024033  jz      short loc_180024047
0x180024035  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18002403c  test    rax, rax
0x18002403f  jz      short loc_180024047
0x180024041  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024046  nop
0x180024047  mov     rbx, [rsp+78h+arg_10]
0x18002404f  add     rsp, 40h
0x180024053  pop     r15
0x180024055  pop     r14
0x180024057  pop     r13
0x180024059  pop     r12
0x18002405b  pop     rdi
0x18002405c  pop     rsi
0x18002405d  pop     rbp
0x18002405e  retn
0x18002405f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
