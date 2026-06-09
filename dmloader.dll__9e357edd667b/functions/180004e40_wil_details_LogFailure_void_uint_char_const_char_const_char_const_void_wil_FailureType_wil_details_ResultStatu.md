# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180004e40`
- end: `0x180005138`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180002894`

## callees

- `0x1800022d0`
- `0x1800044c4`
- `0x180004c5c`
- `0x180004e40`
- `0x1800058ac`
- `0x1800058d0`
- `0x1800059f8`
- `0x180005a14`
- `0x18000782c`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004f63`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004f63`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800050f4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800050f4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005082`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005082`

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
0x180004e40  mov     [rsp+arg_10], rbx
0x180004e45  mov     [rsp+arg_8], edx
0x180004e49  mov     [rsp+arg_0], rcx
0x180004e4e  push    rbp
0x180004e4f  push    rsi
0x180004e50  push    rdi
0x180004e51  push    r12
0x180004e53  push    r13
0x180004e55  push    r14
0x180004e57  push    r15
0x180004e59  sub     rsp, 40h
0x180004e5d  mov     r14, [rsp+78h+arg_38]
0x180004e65  xor     eax, eax
0x180004e67  mov     rbx, [rsp+78h+arg_78]
0x180004e6f  xor     ebp, ebp
0x180004e71  mov     r15d, [rsp+78h+arg_30]
0x180004e79  mov     r10, rcx
0x180004e7c  mov     rsi, [rsp+78h+lpOutputString]
0x180004e84  mov     r12, r9
0x180004e87  mov     r13, r8
0x180004e8a  mov     ecx, r15d
0x180004e8d  mov     [rsi], ax
0x180004e90  mov     rax, [rsp+78h+arg_60]
0x180004e98  mov     byte ptr [rax], 0
0x180004e9b  mov     edi, [r14]
0x180004e9e  mov     [rbx+8], edi
0x180004ea1  mov     eax, [r14+4]
0x180004ea5  mov     [rbx+0Ch], eax
0x180004ea8  test    r15d, r15d
0x180004eab  jz      short loc_180004F13
0x180004ead  sub     ecx, 1
0x180004eb0  jz      short loc_180004F0A
0x180004eb2  sub     ecx, 1
0x180004eb5  jz      short loc_180004EC5
0x180004eb7  cmp     ecx, 1
0x180004eba  jnz     short loc_180004F1C
0x180004ebc  mov     ecx, edi; this
0x180004ebe  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180004ec3  jmp     short loc_180004F1A
0x180004ec5  test    edi, edi
0x180004ec7  js      short loc_180004F01
0x180004ec9  mov     rax, [rsp+78h+arg_28]
0x180004ed1  mov     edi, 8007029Ch
0x180004ed6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180004eda  mov     rcx, r10; int
0x180004edd  mov     [rsp+78h+var_50], rax; __int64
0x180004ee2  mov     rax, [rsp+78h+arg_20]
0x180004eea  mov     [rsp+78h+var_58], rax; __int64
0x180004eef  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180004ef4  mov     ecx, edi; this
0x180004ef6  mov     [rbx+8], edi
0x180004ef9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004efe  mov     [rbx+0Ch], eax
0x180004f01  mov     ecx, edi; this
0x180004f03  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180004f08  jmp     short loc_180004F1A
0x180004f0a  mov     ecx, edi; this
0x180004f0c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004f11  jmp     short loc_180004F1A
0x180004f13  mov     ecx, edi; this
0x180004f15  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180004f1a  mov     ebp, eax
0x180004f1c  mov     eax, [rsp+78h+arg_70]
0x180004f23  mov     [rbx+4], eax
0x180004f26  mov     [rbx], r15d
0x180004f29  cmp     dword ptr [r14+8], 1
0x180004f2e  jnz     short loc_180004F36
0x180004f30  or      eax, 8
0x180004f33  mov     [rbx+4], eax
0x180004f36  mov     eax, 1
0x180004f3b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004f43  inc     eax
0x180004f45  xor     edi, edi
0x180004f47  mov     [rbx+10h], eax
0x180004f4a  mov     rax, [rsp+78h+arg_40]
0x180004f52  test    rax, rax
0x180004f55  jz      short loc_180004F5C
0x180004f57  cmp     [rax], di
0x180004f5a  jnz     short loc_180004F5F
0x180004f5c  mov     rax, rdi
0x180004f5f  mov     [rbx+18h], rax
0x180004f63  call    cs:__imp_GetCurrentThreadId
0x180004f69  mov     [rbx+38h], r13
0x180004f6d  xorps   xmm0, xmm0
0x180004f70  mov     [rbx+20h], eax
0x180004f73  mov     eax, [rsp+78h+arg_8]
0x180004f7a  mov     [rbx+40h], eax
0x180004f7d  mov     rax, [rsp+78h+arg_20]
0x180004f85  mov     [rbx+28h], rax
0x180004f89  mov     rax, [rsp+78h+arg_28]
0x180004f91  mov     [rbx+88h], rax
0x180004f98  mov     rax, [rsp+78h+arg_0]
0x180004fa0  mov     [rbx+90h], rax
0x180004fa7  xor     eax, eax
0x180004fa9  mov     [rbx+44h], ebp
0x180004fac  mov     [rbx+30h], r12
0x180004fb0  mov     [rbx+48h], rdi
0x180004fb4  movups  xmmword ptr [rbx+68h], xmm0
0x180004fb8  mov     [rbx+78h], rax
0x180004fbc  movups  xmmword ptr [rbx+50h], xmm0
0x180004fc0  mov     [rbx+60h], rax
0x180004fc4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004fcb  test    rax, rax
0x180004fce  jz      short loc_180004FD7
0x180004fd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fd5  jmp     short loc_180004FDA
0x180004fd7  mov     rax, rdi
0x180004fda  mov     [rbx+80h], rax
0x180004fe1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004fe8  test    rax, rax
0x180004feb  jz      short loc_180004FF5
0x180004fed  mov     rcx, rbx
0x180004ff0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ff5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004ffc  test    rax, rax
0x180004fff  jz      short loc_180005017
0x180005001  mov     rdx, [rsp+78h+arg_60]
0x180005009  mov     r8d, 400h
0x18000500f  mov     rcx, rbx
0x180005012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005017  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000501e  test    rax, rax
0x180005021  jz      short loc_18000502B
0x180005023  mov     rcx, rbx
0x180005026  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000502b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005032  test    rax, rax
0x180005035  jz      short loc_180005045
0x180005037  test    byte ptr [rbx+4], 2
0x18000503b  jnz     short loc_180005045
0x18000503d  mov     rcx, rbx
0x180005040  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005045  cmp     [rbx+8], edi
0x180005048  jl      short loc_180005064
0x18000504a  cmp     r15d, 3
0x18000504e  jnz     loc_180005132
0x180005054  mov     ecx, 8000FFFFh; this
0x180005059  mov     [rbx+8], ecx
0x18000505c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005061  mov     [rbx+0Ch], eax
0x180005064  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000506b  jnz     short loc_18000508C
0x18000506d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005074  test    rax, rax
0x180005077  jz      short loc_180005082
0x180005079  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000507e  test    al, al
0x180005080  jmp     short loc_18000508A
0x180005082  call    cs:__imp_IsDebuggerPresent
0x180005088  test    eax, eax
0x18000508a  jz      short loc_180005092
0x18000508c  test    byte ptr [rbx+4], 2
0x180005090  jz      short loc_1800050B6
0x180005092  mov     rax, cs:g_pfnResultLoggingCallback
0x180005099  test    rax, rax
0x18000509c  jz      short loc_1800050FA
0x18000509e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800050a5  jnz     short loc_1800050FA
0x1800050a7  xor     r8d, r8d
0x1800050aa  xor     edx, edx
0x1800050ac  mov     rcx, rbx
0x1800050af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050b4  jmp     short loc_1800050FA
0x1800050b6  mov     rax, cs:g_pfnResultLoggingCallback
0x1800050bd  mov     ebp, 800h
0x1800050c2  test    rax, rax
0x1800050c5  jz      short loc_1800050DE
0x1800050c7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800050ce  jnz     short loc_1800050DE
0x1800050d0  mov     r8d, ebp
0x1800050d3  mov     rdx, rsi
0x1800050d6  mov     rcx, rbx
0x1800050d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050de  cmp     [rsi], di
0x1800050e1  jnz     short loc_1800050F1
0x1800050e3  mov     r8, rbx; unsigned __int64
0x1800050e6  mov     rdx, rbp; unsigned __int16 *
0x1800050e9  mov     rcx, rsi; this
0x1800050ec  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800050f1  mov     rcx, rsi; lpOutputString
0x1800050f4  call    cs:__imp_OutputDebugStringW
0x1800050fa  test    byte ptr [rbx+4], 4
0x1800050fe  jnz     short loc_180005109
0x180005100  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180005107  jz      short loc_18000511A
0x180005109  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005110  test    rax, rax
0x180005113  jz      short loc_18000511A
0x180005115  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000511a  mov     rbx, [rsp+78h+arg_10]
0x180005122  add     rsp, 40h
0x180005126  pop     r15
0x180005128  pop     r14
0x18000512a  pop     r13
0x18000512c  pop     r12
0x18000512e  pop     rdi
0x18000512f  pop     rsi
0x180005130  pop     rbp
0x180005131  retn
0x180005132  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
