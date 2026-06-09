# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180006e40`
- end: `0x180007138`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800039a8`

## callees

- `0x1800033e4`
- `0x1800061e4`
- `0x18000697c`
- `0x180006e40`
- `0x180007cd8`
- `0x180007d00`
- `0x180007e28`
- `0x180007e44`
- `0x18000a3bc`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006f63`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006f63`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800070f4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800070f4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007082`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007082`

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
0x180006e40  mov     [rsp+arg_10], rbx
0x180006e45  mov     [rsp+arg_8], edx
0x180006e49  mov     [rsp+arg_0], rcx
0x180006e4e  push    rbp
0x180006e4f  push    rsi
0x180006e50  push    rdi
0x180006e51  push    r12
0x180006e53  push    r13
0x180006e55  push    r14
0x180006e57  push    r15
0x180006e59  sub     rsp, 40h
0x180006e5d  mov     r14, [rsp+78h+arg_38]
0x180006e65  xor     eax, eax
0x180006e67  mov     rbx, [rsp+78h+arg_78]
0x180006e6f  xor     ebp, ebp
0x180006e71  mov     r15d, [rsp+78h+arg_30]
0x180006e79  mov     r10, rcx
0x180006e7c  mov     rsi, [rsp+78h+lpOutputString]
0x180006e84  mov     r12, r9
0x180006e87  mov     r13, r8
0x180006e8a  mov     ecx, r15d
0x180006e8d  mov     [rsi], ax
0x180006e90  mov     rax, [rsp+78h+arg_60]
0x180006e98  mov     byte ptr [rax], 0
0x180006e9b  mov     edi, [r14]
0x180006e9e  mov     [rbx+8], edi
0x180006ea1  mov     eax, [r14+4]
0x180006ea5  mov     [rbx+0Ch], eax
0x180006ea8  test    r15d, r15d
0x180006eab  jz      short loc_180006F13
0x180006ead  sub     ecx, 1
0x180006eb0  jz      short loc_180006F0A
0x180006eb2  sub     ecx, 1
0x180006eb5  jz      short loc_180006EC5
0x180006eb7  cmp     ecx, 1
0x180006eba  jnz     short loc_180006F1C
0x180006ebc  mov     ecx, edi; this
0x180006ebe  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180006ec3  jmp     short loc_180006F1A
0x180006ec5  test    edi, edi
0x180006ec7  js      short loc_180006F01
0x180006ec9  mov     rax, [rsp+78h+arg_28]
0x180006ed1  mov     edi, 8007029Ch
0x180006ed6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180006eda  mov     rcx, r10; int
0x180006edd  mov     [rsp+78h+var_50], rax; __int64
0x180006ee2  mov     rax, [rsp+78h+arg_20]
0x180006eea  mov     [rsp+78h+var_58], rax; __int64
0x180006eef  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180006ef4  mov     ecx, edi; this
0x180006ef6  mov     [rbx+8], edi
0x180006ef9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006efe  mov     [rbx+0Ch], eax
0x180006f01  mov     ecx, edi; this
0x180006f03  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180006f08  jmp     short loc_180006F1A
0x180006f0a  mov     ecx, edi; this
0x180006f0c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180006f11  jmp     short loc_180006F1A
0x180006f13  mov     ecx, edi; this
0x180006f15  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180006f1a  mov     ebp, eax
0x180006f1c  mov     eax, [rsp+78h+arg_70]
0x180006f23  mov     [rbx+4], eax
0x180006f26  mov     [rbx], r15d
0x180006f29  cmp     dword ptr [r14+8], 1
0x180006f2e  jnz     short loc_180006F36
0x180006f30  or      eax, 8
0x180006f33  mov     [rbx+4], eax
0x180006f36  mov     eax, 1
0x180006f3b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180006f43  inc     eax
0x180006f45  xor     edi, edi
0x180006f47  mov     [rbx+10h], eax
0x180006f4a  mov     rax, [rsp+78h+arg_40]
0x180006f52  test    rax, rax
0x180006f55  jz      short loc_180006F5C
0x180006f57  cmp     [rax], di
0x180006f5a  jnz     short loc_180006F5F
0x180006f5c  mov     rax, rdi
0x180006f5f  mov     [rbx+18h], rax
0x180006f63  call    cs:__imp_GetCurrentThreadId
0x180006f69  mov     [rbx+38h], r13
0x180006f6d  xorps   xmm0, xmm0
0x180006f70  mov     [rbx+20h], eax
0x180006f73  mov     eax, [rsp+78h+arg_8]
0x180006f7a  mov     [rbx+40h], eax
0x180006f7d  mov     rax, [rsp+78h+arg_20]
0x180006f85  mov     [rbx+28h], rax
0x180006f89  mov     rax, [rsp+78h+arg_28]
0x180006f91  mov     [rbx+88h], rax
0x180006f98  mov     rax, [rsp+78h+arg_0]
0x180006fa0  mov     [rbx+90h], rax
0x180006fa7  xor     eax, eax
0x180006fa9  mov     [rbx+44h], ebp
0x180006fac  mov     [rbx+30h], r12
0x180006fb0  mov     [rbx+48h], rdi
0x180006fb4  movups  xmmword ptr [rbx+68h], xmm0
0x180006fb8  mov     [rbx+78h], rax
0x180006fbc  movups  xmmword ptr [rbx+50h], xmm0
0x180006fc0  mov     [rbx+60h], rax
0x180006fc4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180006fcb  test    rax, rax
0x180006fce  jz      short loc_180006FD7
0x180006fd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fd5  jmp     short loc_180006FDA
0x180006fd7  mov     rax, rdi
0x180006fda  mov     [rbx+80h], rax
0x180006fe1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006fe8  test    rax, rax
0x180006feb  jz      short loc_180006FF5
0x180006fed  mov     rcx, rbx
0x180006ff0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ff5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006ffc  test    rax, rax
0x180006fff  jz      short loc_180007017
0x180007001  mov     rdx, [rsp+78h+arg_60]
0x180007009  mov     r8d, 400h
0x18000700f  mov     rcx, rbx
0x180007012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007017  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000701e  test    rax, rax
0x180007021  jz      short loc_18000702B
0x180007023  mov     rcx, rbx
0x180007026  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000702b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007032  test    rax, rax
0x180007035  jz      short loc_180007045
0x180007037  test    byte ptr [rbx+4], 2
0x18000703b  jnz     short loc_180007045
0x18000703d  mov     rcx, rbx
0x180007040  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007045  cmp     [rbx+8], edi
0x180007048  jl      short loc_180007064
0x18000704a  cmp     r15d, 3
0x18000704e  jnz     loc_180007132
0x180007054  mov     ecx, 8000FFFFh; this
0x180007059  mov     [rbx+8], ecx
0x18000705c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007061  mov     [rbx+0Ch], eax
0x180007064  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000706b  jnz     short loc_18000708C
0x18000706d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180007074  test    rax, rax
0x180007077  jz      short loc_180007082
0x180007079  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000707e  test    al, al
0x180007080  jmp     short loc_18000708A
0x180007082  call    cs:__imp_IsDebuggerPresent
0x180007088  test    eax, eax
0x18000708a  jz      short loc_180007092
0x18000708c  test    byte ptr [rbx+4], 2
0x180007090  jz      short loc_1800070B6
0x180007092  mov     rax, cs:g_pfnResultLoggingCallback
0x180007099  test    rax, rax
0x18000709c  jz      short loc_1800070FA
0x18000709e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800070a5  jnz     short loc_1800070FA
0x1800070a7  xor     r8d, r8d
0x1800070aa  xor     edx, edx
0x1800070ac  mov     rcx, rbx
0x1800070af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070b4  jmp     short loc_1800070FA
0x1800070b6  mov     rax, cs:g_pfnResultLoggingCallback
0x1800070bd  mov     ebp, 800h
0x1800070c2  test    rax, rax
0x1800070c5  jz      short loc_1800070DE
0x1800070c7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800070ce  jnz     short loc_1800070DE
0x1800070d0  mov     r8d, ebp
0x1800070d3  mov     rdx, rsi
0x1800070d6  mov     rcx, rbx
0x1800070d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070de  cmp     [rsi], di
0x1800070e1  jnz     short loc_1800070F1
0x1800070e3  mov     r8, rbx; unsigned __int64
0x1800070e6  mov     rdx, rbp; unsigned __int16 *
0x1800070e9  mov     rcx, rsi; this
0x1800070ec  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800070f1  mov     rcx, rsi; lpOutputString
0x1800070f4  call    cs:__imp_OutputDebugStringW
0x1800070fa  test    byte ptr [rbx+4], 4
0x1800070fe  jnz     short loc_180007109
0x180007100  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180007107  jz      short loc_18000711A
0x180007109  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180007110  test    rax, rax
0x180007113  jz      short loc_18000711A
0x180007115  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000711a  mov     rbx, [rsp+78h+arg_10]
0x180007122  add     rsp, 40h
0x180007126  pop     r15
0x180007128  pop     r14
0x18000712a  pop     r13
0x18000712c  pop     r12
0x18000712e  pop     rdi
0x18000712f  pop     rsi
0x180007130  pop     rbp
0x180007131  retn
0x180007132  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
