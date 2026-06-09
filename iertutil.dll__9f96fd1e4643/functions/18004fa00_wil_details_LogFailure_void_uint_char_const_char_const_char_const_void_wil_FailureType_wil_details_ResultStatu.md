# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18004fa00`
- end: `0x18004fcf5`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x18004bff4`
- `0x18004f910`
- `0x18005bd9c`
- `0x18005f144`

## callees

- `0x18004bd98`
- `0x18004fa00`
- `0x18004fd00`
- `0x18005bd38`
- `0x18005c6e4`
- `0x18005ce90`
- `0x18005ceac`
- `0x18005cec8`
- `0x18005d710`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004fb23`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004fb23`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18004fcb6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18004fcb6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18004fc44`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18004fc44`

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
0x18004fa00  mov     [rsp+arg_10], rbx
0x18004fa05  mov     [rsp+arg_8], edx
0x18004fa09  mov     [rsp+arg_0], rcx
0x18004fa0e  push    rbp
0x18004fa0f  push    rsi
0x18004fa10  push    rdi
0x18004fa11  push    r12
0x18004fa13  push    r13
0x18004fa15  push    r14
0x18004fa17  push    r15
0x18004fa19  sub     rsp, 40h
0x18004fa1d  mov     r12, r9
0x18004fa20  mov     r13, r8
0x18004fa23  mov     r10, rcx
0x18004fa26  xor     eax, eax
0x18004fa28  mov     rsi, [rsp+78h+lpOutputString]
0x18004fa30  mov     [rsi], ax
0x18004fa33  mov     rax, [rsp+78h+arg_60]
0x18004fa3b  mov     byte ptr [rax], 0
0x18004fa3e  mov     r14, [rsp+78h+arg_38]
0x18004fa46  mov     edi, [r14]
0x18004fa49  mov     rbx, [rsp+78h+arg_78]
0x18004fa51  mov     [rbx+8], edi
0x18004fa54  mov     eax, [r14+4]
0x18004fa58  mov     [rbx+0Ch], eax
0x18004fa5b  xor     ebp, ebp
0x18004fa5d  mov     r15d, [rsp+78h+arg_30]
0x18004fa65  mov     ecx, r15d
0x18004fa68  test    r15d, r15d
0x18004fa6b  jz      short loc_18004FAD3
0x18004fa6d  sub     ecx, 1
0x18004fa70  jz      short loc_18004FACA
0x18004fa72  sub     ecx, 1
0x18004fa75  jz      short loc_18004FA85
0x18004fa77  cmp     ecx, 1
0x18004fa7a  jnz     short loc_18004FADC
0x18004fa7c  mov     ecx, edi; this
0x18004fa7e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18004fa83  jmp     short loc_18004FADA
0x18004fa85  test    edi, edi
0x18004fa87  js      short loc_18004FAC1
0x18004fa89  mov     edi, 8007029Ch
0x18004fa8e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18004fa92  mov     rax, [rsp+78h+arg_28]
0x18004fa9a  mov     [rsp+78h+var_50], rax; __int64
0x18004fa9f  mov     rax, [rsp+78h+arg_20]
0x18004faa7  mov     [rsp+78h+var_58], rax; __int64
0x18004faac  mov     rcx, r10; int
0x18004faaf  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18004fab4  mov     [rbx+8], edi
0x18004fab7  mov     ecx, edi; this
0x18004fab9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18004fabe  mov     [rbx+0Ch], eax
0x18004fac1  mov     ecx, edi; this
0x18004fac3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18004fac8  jmp     short loc_18004FADA
0x18004faca  mov     ecx, edi; this
0x18004facc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18004fad1  jmp     short loc_18004FADA
0x18004fad3  mov     ecx, edi; this
0x18004fad5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18004fada  mov     ebp, eax
0x18004fadc  mov     [rbx], r15d
0x18004fadf  mov     eax, [rsp+78h+arg_70]
0x18004fae6  mov     [rbx+4], eax
0x18004fae9  cmp     dword ptr [r14+8], 1
0x18004faee  jnz     short loc_18004FAF6
0x18004faf0  or      eax, 8
0x18004faf3  mov     [rbx+4], eax
0x18004faf6  mov     eax, 1
0x18004fafb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18004fb03  inc     eax
0x18004fb05  mov     [rbx+10h], eax
0x18004fb08  mov     rax, [rsp+78h+arg_40]
0x18004fb10  xor     edi, edi
0x18004fb12  test    rax, rax
0x18004fb15  jz      short loc_18004FB1C
0x18004fb17  cmp     [rax], di
0x18004fb1a  jnz     short loc_18004FB1F
0x18004fb1c  mov     rax, rdi
0x18004fb1f  mov     [rbx+18h], rax
0x18004fb23  call    cs:__imp_GetCurrentThreadId
0x18004fb29  mov     [rbx+20h], eax
0x18004fb2c  mov     [rbx+38h], r13
0x18004fb30  mov     eax, [rsp+78h+arg_8]
0x18004fb37  mov     [rbx+40h], eax
0x18004fb3a  mov     [rbx+44h], ebp
0x18004fb3d  mov     rax, [rsp+78h+arg_20]
0x18004fb45  mov     [rbx+28h], rax
0x18004fb49  mov     [rbx+30h], r12
0x18004fb4d  mov     rax, [rsp+78h+arg_28]
0x18004fb55  mov     [rbx+88h], rax
0x18004fb5c  mov     rax, [rsp+78h+arg_0]
0x18004fb64  mov     [rbx+90h], rax
0x18004fb6b  mov     [rbx+48h], rdi
0x18004fb6f  xorps   xmm0, xmm0
0x18004fb72  xor     eax, eax
0x18004fb74  movups  xmmword ptr [rbx+68h], xmm0
0x18004fb78  mov     [rbx+78h], rax
0x18004fb7c  movups  xmmword ptr [rbx+50h], xmm0
0x18004fb80  mov     [rbx+60h], rax
0x18004fb84  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18004fb8b  test    rax, rax
0x18004fb8e  jz      short loc_18004FB97
0x18004fb90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fb95  jmp     short loc_18004FB9A
0x18004fb97  mov     rax, rdi
0x18004fb9a  mov     [rbx+80h], rax
0x18004fba1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18004fba8  test    rax, rax
0x18004fbab  jz      short loc_18004FBB5
0x18004fbad  mov     rcx, rbx
0x18004fbb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fbb5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18004fbbc  test    rax, rax
0x18004fbbf  jz      short loc_18004FBD7
0x18004fbc1  mov     r8d, 400h
0x18004fbc7  mov     rdx, [rsp+78h+arg_60]
0x18004fbcf  mov     rcx, rbx
0x18004fbd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fbd7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18004fbde  test    rax, rax
0x18004fbe1  jz      short loc_18004FBEB
0x18004fbe3  mov     rcx, rbx
0x18004fbe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fbeb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18004fbf2  test    rax, rax
0x18004fbf5  jz      short loc_18004FC05
0x18004fbf7  test    byte ptr [rbx+4], 2
0x18004fbfb  jnz     short loc_18004FC05
0x18004fbfd  mov     rcx, rbx
0x18004fc00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fc05  cmp     [rbx+8], edi
0x18004fc08  jl      short loc_18004FC26
0x18004fc0a  cmp     r15d, 3
0x18004fc0e  jz      short loc_18004FC16
0x18004fc10  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18004fc16  mov     ecx, 8000FFFFh; this
0x18004fc1b  mov     [rbx+8], ecx
0x18004fc1e  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18004fc23  mov     [rbx+0Ch], eax
0x18004fc26  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18004fc2d  jnz     short loc_18004FC4E
0x18004fc2f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18004fc36  test    rax, rax
0x18004fc39  jz      short loc_18004FC44
0x18004fc3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fc40  test    al, al
0x18004fc42  jmp     short loc_18004FC4C
0x18004fc44  call    cs:__imp_IsDebuggerPresent
0x18004fc4a  test    eax, eax
0x18004fc4c  jz      short loc_18004FC54
0x18004fc4e  test    byte ptr [rbx+4], 2
0x18004fc52  jz      short loc_18004FC78
0x18004fc54  mov     rax, cs:g_pfnResultLoggingCallback
0x18004fc5b  test    rax, rax
0x18004fc5e  jz      short loc_18004FCBC
0x18004fc60  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18004fc67  jnz     short loc_18004FCBC
0x18004fc69  xor     r8d, r8d
0x18004fc6c  xor     edx, edx
0x18004fc6e  mov     rcx, rbx
0x18004fc71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fc76  jmp     short loc_18004FCBC
0x18004fc78  mov     ebp, 800h
0x18004fc7d  mov     rax, cs:g_pfnResultLoggingCallback
0x18004fc84  test    rax, rax
0x18004fc87  jz      short loc_18004FCA0
0x18004fc89  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18004fc90  jnz     short loc_18004FCA0
0x18004fc92  mov     r8d, ebp
0x18004fc95  mov     rdx, rsi
0x18004fc98  mov     rcx, rbx
0x18004fc9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fca0  cmp     [rsi], di
0x18004fca3  jnz     short loc_18004FCB3
0x18004fca5  mov     r8, rbx; unsigned __int64
0x18004fca8  mov     rdx, rbp; unsigned __int16 *
0x18004fcab  mov     rcx, rsi; this
0x18004fcae  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18004fcb3  mov     rcx, rsi; lpOutputString
0x18004fcb6  call    cs:__imp_OutputDebugStringW
0x18004fcbc  test    byte ptr [rbx+4], 4
0x18004fcc0  jnz     short loc_18004FCCB
0x18004fcc2  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18004fcc9  jz      short loc_18004FCDD
0x18004fccb  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18004fcd2  test    rax, rax
0x18004fcd5  jz      short loc_18004FCDD
0x18004fcd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fcdc  nop
0x18004fcdd  mov     rbx, [rsp+78h+arg_10]
0x18004fce5  add     rsp, 40h
0x18004fce9  pop     r15
0x18004fceb  pop     r14
0x18004fced  pop     r13
0x18004fcef  pop     r12
0x18004fcf1  pop     rdi
0x18004fcf2  pop     rsi
0x18004fcf3  pop     rbp
0x18004fcf4  retn
```
