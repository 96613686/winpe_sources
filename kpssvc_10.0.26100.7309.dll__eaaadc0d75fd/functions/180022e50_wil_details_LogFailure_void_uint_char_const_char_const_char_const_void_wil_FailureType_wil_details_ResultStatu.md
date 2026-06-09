# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)

- ea: `0x180022e50`
- end: `0x180023157`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7PEAUFailureInfo@2@@Z`
- size: `775`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18001bd28`

## callees

- `0x18001b744`
- `0x18001d9d4`
- `0x18001e1e8`
- `0x180022e50`
- `0x180023c48`
- `0x180023c70`
- `0x180023dcc`
- `0x180023dec`
- `0x180026388`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022f6f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022f6f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180023093`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180023093`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18002310c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18002310c`

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
        unsigned __int64 a15)
{
  int v17; // esi
  unsigned int v18; // edi
  int v19; // eax
  int v20; // edx
  _WORD *v21; // rax
  DWORD CurrentThreadId; // eax
  int v23; // edx
  wil::details::in1diag3 *v24; // rcx
  const struct wil::FailureInfo *v25; // r9
  __int64 ModuleName; // rax
  bool v27; // zf
  wil::details *v28; // [rsp+30h] [rbp-48h]

  v17 = 0;
  *(_WORD *)lpOutputString = 0;
  *a13 = 0;
  v18 = *a8;
  *(_DWORD *)(a15 + 8) = *a8;
  *(_DWORD *)(a15 + 12) = a8[1];
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1:
        v19 = wil::details::RecordReturn((wil::details *)v18, a2);
        break;
      case 2:
        if ( (v18 & 0x80000000) == 0 )
        {
          v18 = -2147024228;
          LODWORD(v28) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v28);
          *(_DWORD *)(a15 + 8) = -2147024228;
          *(_DWORD *)(a15 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v20);
        }
        v19 = wil::details::RecordLog((wil::details *)v18, a2);
        break;
      case 3:
        v19 = wil::details::RecordFailFast((wil::details *)v18, a2);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v19 = wil::details::RecordException((wil::details *)v18, a2);
  }
  v17 = v19;
LABEL_12:
  *(_DWORD *)a15 = a7;
  *(_DWORD *)(a15 + 4) = 0;
  if ( a8[2] == 1 )
    *(_DWORD *)(a15 + 4) = 8;
  *(_DWORD *)(a15 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = a9;
  if ( !a9 || !*a9 )
    v21 = 0;
  *(_QWORD *)(a15 + 24) = v21;
  CurrentThreadId = GetCurrentThreadId();
  *(_QWORD *)(a15 + 56) = a3;
  *(_DWORD *)(a15 + 32) = CurrentThreadId;
  *(_DWORD *)(a15 + 64) = a2;
  *(_QWORD *)(a15 + 40) = a5;
  *(_QWORD *)(a15 + 136) = a6;
  *(_QWORD *)(a15 + 144) = a1;
  *(_DWORD *)(a15 + 68) = v17;
  *(_QWORD *)(a15 + 48) = a4;
  *(_QWORD *)(a15 + 72) = 0;
  *(_OWORD *)(a15 + 104) = 0;
  *(_QWORD *)(a15 + 120) = 0;
  *(_OWORD *)(a15 + 80) = 0;
  *(_QWORD *)(a15 + 96) = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName();
  else
    ModuleName = 0;
  *(_QWORD *)(a15 + 128) = ModuleName;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(a15);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(a15, a13, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(a15);
  if ( wil::details::g_pfnOriginateCallback && (*(_BYTE *)(a15 + 4) & 2) == 0 )
    wil::details::g_pfnOriginateCallback(a15);
  if ( *(int *)(a15 + 8) >= 0 )
  {
    if ( a7 != 3 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
    *(_DWORD *)(a15 + 8) = -2147418113;
    *(_DWORD *)(a15 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v23);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v27 = !IsDebuggerPresent())
      : (v27 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v27)
    || (*(_BYTE *)(a15 + 4) & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a15, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a15, lpOutputString, 2048);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a15, v25);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a15 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak();
  }
}

```

## disassembly

```asm
0x180022e50  mov     [rsp+arg_10], rbx
0x180022e55  mov     [rsp+arg_8], edx
0x180022e59  mov     [rsp+arg_0], rcx
0x180022e5e  push    rbp
0x180022e5f  push    rsi
0x180022e60  push    rdi
0x180022e61  push    r12
0x180022e63  push    r13
0x180022e65  push    r14
0x180022e67  push    r15
0x180022e69  sub     rsp, 40h
0x180022e6d  mov     rax, [rsp+78h+arg_60]
0x180022e75  mov     r13, r8
0x180022e78  mov     r15, [rsp+78h+arg_38]
0x180022e80  xor     r8d, r8d
0x180022e83  mov     rbx, [rsp+78h+arg_70]
0x180022e8b  mov     r10, rcx
0x180022e8e  mov     ebp, [rsp+78h+arg_30]
0x180022e95  mov     r12, r9
0x180022e98  mov     r14, [rsp+78h+lpOutputString]
0x180022ea0  mov     esi, r8d
0x180022ea3  mov     ecx, ebp
0x180022ea5  mov     [r14], r8w
0x180022ea9  mov     [rax], r8b
0x180022eac  mov     edi, [r15]
0x180022eaf  mov     [rbx+8], edi
0x180022eb2  mov     eax, [r15+4]
0x180022eb6  mov     [rbx+0Ch], eax
0x180022eb9  test    ebp, ebp
0x180022ebb  jz      short loc_180022F26
0x180022ebd  sub     ecx, 1
0x180022ec0  jz      short loc_180022F1D
0x180022ec2  sub     ecx, 1
0x180022ec5  jz      short loc_180022ED5
0x180022ec7  cmp     ecx, 1
0x180022eca  jnz     short loc_180022F2F
0x180022ecc  mov     ecx, edi; this
0x180022ece  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180022ed3  jmp     short loc_180022F2D
0x180022ed5  test    edi, edi
0x180022ed7  js      short loc_180022F14
0x180022ed9  mov     rax, [rsp+78h+arg_28]
0x180022ee1  mov     edi, 8007029Ch
0x180022ee6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180022eea  mov     r8, r13; int
0x180022eed  mov     [rsp+78h+var_50], rax; __int64
0x180022ef2  mov     rcx, r10; int
0x180022ef5  mov     rax, [rsp+78h+arg_20]
0x180022efd  mov     [rsp+78h+var_58], rax; __int64
0x180022f02  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110J@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long)
0x180022f07  mov     ecx, edi; this
0x180022f09  mov     [rbx+8], edi
0x180022f0c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180022f11  mov     [rbx+0Ch], eax
0x180022f14  mov     ecx, edi; this
0x180022f16  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180022f1b  jmp     short loc_180022F2D
0x180022f1d  mov     ecx, edi; this
0x180022f1f  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180022f24  jmp     short loc_180022F2D
0x180022f26  mov     ecx, edi; this
0x180022f28  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180022f2d  mov     esi, eax
0x180022f2f  xor     edi, edi
0x180022f31  mov     [rbx], ebp
0x180022f33  mov     [rbx+4], edi
0x180022f36  cmp     dword ptr [r15+8], 1
0x180022f3b  jnz     short loc_180022F44
0x180022f3d  mov     dword ptr [rbx+4], 8
0x180022f44  mov     eax, 1
0x180022f49  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)'::`2'::s_failureId
0x180022f51  inc     eax
0x180022f53  mov     [rbx+10h], eax
0x180022f56  mov     rax, [rsp+78h+arg_40]
0x180022f5e  test    rax, rax
0x180022f61  jz      short loc_180022F68
0x180022f63  cmp     [rax], di
0x180022f66  jnz     short loc_180022F6B
0x180022f68  mov     rax, rdi
0x180022f6b  mov     [rbx+18h], rax
0x180022f6f  call    cs:__imp_GetCurrentThreadId
0x180022f76  nop     dword ptr [rax+rax+00h]
0x180022f7b  mov     [rbx+38h], r13
0x180022f7f  xorps   xmm0, xmm0
0x180022f82  mov     [rbx+20h], eax
0x180022f85  mov     eax, [rsp+78h+arg_8]
0x180022f8c  mov     [rbx+40h], eax
0x180022f8f  mov     rax, [rsp+78h+arg_20]
0x180022f97  mov     [rbx+28h], rax
0x180022f9b  mov     rax, [rsp+78h+arg_28]
0x180022fa3  mov     [rbx+88h], rax
0x180022faa  mov     rax, [rsp+78h+arg_0]
0x180022fb2  mov     [rbx+90h], rax
0x180022fb9  xor     eax, eax
0x180022fbb  mov     [rbx+44h], esi
0x180022fbe  mov     [rbx+30h], r12
0x180022fc2  mov     [rbx+48h], rdi
0x180022fc6  movups  xmmword ptr [rbx+68h], xmm0
0x180022fca  mov     [rbx+78h], rax
0x180022fce  movups  xmmword ptr [rbx+50h], xmm0
0x180022fd2  mov     [rbx+60h], rax
0x180022fd6  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180022fdd  test    rax, rax
0x180022fe0  jz      short loc_180022FE9
0x180022fe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022fe7  jmp     short loc_180022FEC
0x180022fe9  mov     rax, rdi
0x180022fec  mov     [rbx+80h], rax
0x180022ff3  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180022ffa  test    rax, rax
0x180022ffd  jz      short loc_180023007
0x180022fff  mov     rcx, rbx
0x180023002  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023007  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18002300e  test    rax, rax
0x180023011  jz      short loc_180023029
0x180023013  mov     rdx, [rsp+78h+arg_60]
0x18002301b  mov     r8d, 400h
0x180023021  mov     rcx, rbx
0x180023024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023029  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180023030  test    rax, rax
0x180023033  jz      short loc_18002303D
0x180023035  mov     rcx, rbx
0x180023038  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002303d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180023044  test    rax, rax
0x180023047  jz      short loc_180023057
0x180023049  test    byte ptr [rbx+4], 2
0x18002304d  jnz     short loc_180023057
0x18002304f  mov     rcx, rbx
0x180023052  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023057  cmp     [rbx+8], edi
0x18002305a  jl      short loc_180023075
0x18002305c  cmp     ebp, 3
0x18002305f  jnz     loc_180023151
0x180023065  mov     ecx, 8000FFFFh; this
0x18002306a  mov     [rbx+8], ecx
0x18002306d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180023072  mov     [rbx+0Ch], eax
0x180023075  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18002307c  jnz     short loc_1800230A3
0x18002307e  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180023085  test    rax, rax
0x180023088  jz      short loc_180023093
0x18002308a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002308f  test    al, al
0x180023091  jmp     short loc_1800230A1
0x180023093  call    cs:__imp_IsDebuggerPresent
0x18002309a  nop     dword ptr [rax+rax+00h]
0x18002309f  test    eax, eax
0x1800230a1  jz      short loc_1800230A9
0x1800230a3  test    byte ptr [rbx+4], 2
0x1800230a7  jz      short loc_1800230CD
0x1800230a9  mov     rax, cs:g_pfnResultLoggingCallback
0x1800230b0  test    rax, rax
0x1800230b3  jz      short loc_180023118
0x1800230b5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800230bc  jnz     short loc_180023118
0x1800230be  xor     r8d, r8d
0x1800230c1  xor     edx, edx
0x1800230c3  mov     rcx, rbx
0x1800230c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800230cb  jmp     short loc_180023118
0x1800230cd  mov     rax, cs:g_pfnResultLoggingCallback
0x1800230d4  mov     esi, 800h
0x1800230d9  test    rax, rax
0x1800230dc  jz      short loc_1800230F5
0x1800230de  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800230e5  jnz     short loc_1800230F5
0x1800230e7  mov     r8d, esi
0x1800230ea  mov     rdx, r14
0x1800230ed  mov     rcx, rbx
0x1800230f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800230f5  cmp     [r14], di
0x1800230f9  jnz     short loc_180023109
0x1800230fb  mov     r8, rbx; unsigned __int64
0x1800230fe  mov     rdx, rsi; unsigned __int16 *
0x180023101  mov     rcx, r14; this
0x180023104  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180023109  mov     rcx, r14; lpOutputString
0x18002310c  call    cs:__imp_OutputDebugStringW
0x180023113  nop     dword ptr [rax+rax+00h]
0x180023118  test    byte ptr [rbx+4], 4
0x18002311c  jnz     short loc_180023127
0x18002311e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180023125  jz      short loc_180023138
0x180023127  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18002312e  test    rax, rax
0x180023131  jz      short loc_180023138
0x180023133  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023138  mov     rbx, [rsp+78h+arg_10]
0x180023140  add     rsp, 40h
0x180023144  pop     r15
0x180023146  pop     r14
0x180023148  pop     r13
0x18002314a  pop     r12
0x18002314c  pop     rdi
0x18002314d  pop     rsi
0x18002314e  pop     rbp
0x18002314f  retn
0x180023151  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
