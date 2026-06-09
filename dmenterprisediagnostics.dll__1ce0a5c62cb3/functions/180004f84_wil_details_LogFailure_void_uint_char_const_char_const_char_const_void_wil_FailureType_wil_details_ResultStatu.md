# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180004f84`
- end: `0x18000527d`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180002e48`
- `0x1800031b4`

## callees

- `0x180002d80`
- `0x1800045b4`
- `0x180004d94`
- `0x180004f84`
- `0x1800056b8`
- `0x1800056e0`
- `0x1800056f4`
- `0x180005710`
- `0x1800071e0`
- `0x180026010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800050a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800050a7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800051c6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800051c6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005238`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005238`

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
    ModuleName = wil::details::g_pfnGetModuleName(v24);
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
      : (v27 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v24) == 0),
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
      wil::details::g_pfnDebugBreak(v24);
  }
}

```

## disassembly

```asm
0x180004f84  mov     [rsp+arg_10], rbx
0x180004f89  mov     [rsp+arg_8], edx
0x180004f8d  mov     [rsp+arg_0], rcx
0x180004f92  push    rbp
0x180004f93  push    rsi
0x180004f94  push    rdi
0x180004f95  push    r12
0x180004f97  push    r13
0x180004f99  push    r14
0x180004f9b  push    r15
0x180004f9d  sub     rsp, 40h
0x180004fa1  mov     r12, r9
0x180004fa4  mov     r13, r8
0x180004fa7  mov     r10, rcx
0x180004faa  xor     eax, eax
0x180004fac  mov     rsi, [rsp+78h+lpOutputString]
0x180004fb4  mov     [rsi], ax
0x180004fb7  mov     rax, [rsp+78h+arg_60]
0x180004fbf  mov     byte ptr [rax], 0
0x180004fc2  mov     r14, [rsp+78h+arg_38]
0x180004fca  mov     edi, [r14]
0x180004fcd  mov     rbx, [rsp+78h+arg_78]
0x180004fd5  mov     [rbx+8], edi
0x180004fd8  mov     eax, [r14+4]
0x180004fdc  mov     [rbx+0Ch], eax
0x180004fdf  xor     ebp, ebp
0x180004fe1  mov     r15d, [rsp+78h+arg_30]
0x180004fe9  mov     ecx, r15d
0x180004fec  test    r15d, r15d
0x180004fef  jz      short loc_180005057
0x180004ff1  sub     ecx, 1
0x180004ff4  jz      short loc_18000504E
0x180004ff6  sub     ecx, 1
0x180004ff9  jz      short loc_180005009
0x180004ffb  cmp     ecx, 1
0x180004ffe  jnz     short loc_180005060
0x180005000  mov     ecx, edi; this
0x180005002  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180005007  jmp     short loc_18000505E
0x180005009  test    edi, edi
0x18000500b  js      short loc_180005045
0x18000500d  mov     edi, 8007029Ch
0x180005012  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180005016  mov     rax, [rsp+78h+arg_28]
0x18000501e  mov     [rsp+78h+var_50], rax; __int64
0x180005023  mov     rax, [rsp+78h+arg_20]
0x18000502b  mov     [rsp+78h+var_58], rax; __int64
0x180005030  mov     rcx, r10; int
0x180005033  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180005038  mov     [rbx+8], edi
0x18000503b  mov     ecx, edi; this
0x18000503d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005042  mov     [rbx+0Ch], eax
0x180005045  mov     ecx, edi; this
0x180005047  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000504c  jmp     short loc_18000505E
0x18000504e  mov     ecx, edi; this
0x180005050  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005055  jmp     short loc_18000505E
0x180005057  mov     ecx, edi; this
0x180005059  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000505e  mov     ebp, eax
0x180005060  mov     [rbx], r15d
0x180005063  mov     eax, [rsp+78h+arg_70]
0x18000506a  mov     [rbx+4], eax
0x18000506d  cmp     dword ptr [r14+8], 1
0x180005072  jnz     short loc_18000507A
0x180005074  or      eax, 8
0x180005077  mov     [rbx+4], eax
0x18000507a  mov     eax, 1
0x18000507f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005087  inc     eax
0x180005089  mov     [rbx+10h], eax
0x18000508c  mov     rax, [rsp+78h+arg_40]
0x180005094  xor     edi, edi
0x180005096  test    rax, rax
0x180005099  jz      short loc_1800050A0
0x18000509b  cmp     [rax], di
0x18000509e  jnz     short loc_1800050A3
0x1800050a0  mov     rax, rdi
0x1800050a3  mov     [rbx+18h], rax
0x1800050a7  call    cs:__imp_GetCurrentThreadId
0x1800050ad  mov     [rbx+20h], eax
0x1800050b0  mov     [rbx+38h], r13
0x1800050b4  mov     eax, [rsp+78h+arg_8]
0x1800050bb  mov     [rbx+40h], eax
0x1800050be  mov     [rbx+44h], ebp
0x1800050c1  mov     rax, [rsp+78h+arg_20]
0x1800050c9  mov     [rbx+28h], rax
0x1800050cd  mov     [rbx+30h], r12
0x1800050d1  mov     rax, [rsp+78h+arg_28]
0x1800050d9  mov     [rbx+88h], rax
0x1800050e0  mov     rax, [rsp+78h+arg_0]
0x1800050e8  mov     [rbx+90h], rax
0x1800050ef  mov     [rbx+48h], rdi
0x1800050f3  xorps   xmm0, xmm0
0x1800050f6  xor     eax, eax
0x1800050f8  movups  xmmword ptr [rbx+68h], xmm0
0x1800050fc  mov     [rbx+78h], rax
0x180005100  movups  xmmword ptr [rbx+50h], xmm0
0x180005104  mov     [rbx+60h], rax
0x180005108  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000510f  test    rax, rax
0x180005112  jz      short loc_18000511B
0x180005114  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005119  jmp     short loc_18000511E
0x18000511b  mov     rax, rdi
0x18000511e  mov     [rbx+80h], rax
0x180005125  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000512c  test    rax, rax
0x18000512f  jz      short loc_180005139
0x180005131  mov     rcx, rbx
0x180005134  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005139  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005140  test    rax, rax
0x180005143  jz      short loc_18000515B
0x180005145  mov     r8d, 400h
0x18000514b  mov     rdx, [rsp+78h+arg_60]
0x180005153  mov     rcx, rbx
0x180005156  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000515b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005162  test    rax, rax
0x180005165  jz      short loc_18000516F
0x180005167  mov     rcx, rbx
0x18000516a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000516f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005176  test    rax, rax
0x180005179  jz      short loc_180005189
0x18000517b  test    byte ptr [rbx+4], 2
0x18000517f  jnz     short loc_180005189
0x180005181  mov     rcx, rbx
0x180005184  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005189  cmp     [rbx+8], edi
0x18000518c  jl      short loc_1800051A8
0x18000518e  cmp     r15d, 3
0x180005192  jnz     loc_180005277
0x180005198  mov     ecx, 8000FFFFh; this
0x18000519d  mov     [rbx+8], ecx
0x1800051a0  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800051a5  mov     [rbx+0Ch], eax
0x1800051a8  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800051af  jnz     short loc_1800051D0
0x1800051b1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800051b8  test    rax, rax
0x1800051bb  jz      short loc_1800051C6
0x1800051bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051c2  test    al, al
0x1800051c4  jmp     short loc_1800051CE
0x1800051c6  call    cs:__imp_IsDebuggerPresent
0x1800051cc  test    eax, eax
0x1800051ce  jz      short loc_1800051D6
0x1800051d0  test    byte ptr [rbx+4], 2
0x1800051d4  jz      short loc_1800051FA
0x1800051d6  mov     rax, cs:g_pfnResultLoggingCallback
0x1800051dd  test    rax, rax
0x1800051e0  jz      short loc_18000523E
0x1800051e2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800051e9  jnz     short loc_18000523E
0x1800051eb  xor     r8d, r8d
0x1800051ee  xor     edx, edx
0x1800051f0  mov     rcx, rbx
0x1800051f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051f8  jmp     short loc_18000523E
0x1800051fa  mov     ebp, 800h
0x1800051ff  mov     rax, cs:g_pfnResultLoggingCallback
0x180005206  test    rax, rax
0x180005209  jz      short loc_180005222
0x18000520b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005212  jnz     short loc_180005222
0x180005214  mov     r8d, ebp
0x180005217  mov     rdx, rsi
0x18000521a  mov     rcx, rbx
0x18000521d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005222  cmp     [rsi], di
0x180005225  jnz     short loc_180005235
0x180005227  mov     r8, rbx; unsigned __int64
0x18000522a  mov     rdx, rbp; unsigned __int16 *
0x18000522d  mov     rcx, rsi; this
0x180005230  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005235  mov     rcx, rsi; lpOutputString
0x180005238  call    cs:__imp_OutputDebugStringW
0x18000523e  test    byte ptr [rbx+4], 4
0x180005242  jnz     short loc_18000524D
0x180005244  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000524b  jz      short loc_18000525F
0x18000524d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005254  test    rax, rax
0x180005257  jz      short loc_18000525F
0x180005259  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000525e  nop
0x18000525f  mov     rbx, [rsp+78h+arg_10]
0x180005267  add     rsp, 40h
0x18000526b  pop     r15
0x18000526d  pop     r14
0x18000526f  pop     r13
0x180005271  pop     r12
0x180005273  pop     rdi
0x180005274  pop     rsi
0x180005275  pop     rbp
0x180005276  retn
0x180005277  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
