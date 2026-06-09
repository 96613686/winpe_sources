# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18001f928`
- end: `0x18001fc1d`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x18001f82c`
- `0x180037c2c`
- `0x180037cec`
- `0x18003c4d4`

## callees

- `0x18001f928`
- `0x18002b8cc`
- `0x180037b74`
- `0x180038f94`
- `0x180039fd0`
- `0x180039ff0`
- `0x18003a0ac`
- `0x18003a0c8`
- `0x18003b7bc`
- `0x18007c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001fa4b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001fa4b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001fbde`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001fbde`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001fb6c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001fb6c`

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
0x18001f928  mov     [rsp+arg_10], rbx
0x18001f92d  mov     [rsp+arg_8], edx
0x18001f931  mov     [rsp+arg_0], rcx
0x18001f936  push    rbp
0x18001f937  push    rsi
0x18001f938  push    rdi
0x18001f939  push    r12
0x18001f93b  push    r13
0x18001f93d  push    r14
0x18001f93f  push    r15
0x18001f941  sub     rsp, 40h
0x18001f945  mov     r12, r9
0x18001f948  mov     r13, r8
0x18001f94b  mov     r10, rcx
0x18001f94e  xor     eax, eax
0x18001f950  mov     rsi, [rsp+78h+lpOutputString]
0x18001f958  mov     [rsi], ax
0x18001f95b  mov     rax, [rsp+78h+arg_60]
0x18001f963  mov     byte ptr [rax], 0
0x18001f966  mov     r14, [rsp+78h+arg_38]
0x18001f96e  mov     edi, [r14]
0x18001f971  mov     rbx, [rsp+78h+arg_78]
0x18001f979  mov     [rbx+8], edi
0x18001f97c  mov     eax, [r14+4]
0x18001f980  mov     [rbx+0Ch], eax
0x18001f983  xor     ebp, ebp
0x18001f985  mov     r15d, [rsp+78h+arg_30]
0x18001f98d  mov     ecx, r15d
0x18001f990  test    r15d, r15d
0x18001f993  jz      short loc_18001F9FB
0x18001f995  sub     ecx, 1
0x18001f998  jz      short loc_18001F9F2
0x18001f99a  sub     ecx, 1
0x18001f99d  jz      short loc_18001F9AD
0x18001f99f  cmp     ecx, 1
0x18001f9a2  jnz     short loc_18001FA04
0x18001f9a4  mov     ecx, edi; this
0x18001f9a6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18001f9ab  jmp     short loc_18001FA02
0x18001f9ad  test    edi, edi
0x18001f9af  js      short loc_18001F9E9
0x18001f9b1  mov     edi, 8007029Ch
0x18001f9b6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18001f9ba  mov     rax, [rsp+78h+arg_28]
0x18001f9c2  mov     [rsp+78h+var_50], rax; __int64
0x18001f9c7  mov     rax, [rsp+78h+arg_20]
0x18001f9cf  mov     [rsp+78h+var_58], rax; __int64
0x18001f9d4  mov     rcx, r10; int
0x18001f9d7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18001f9dc  mov     [rbx+8], edi
0x18001f9df  mov     ecx, edi; this
0x18001f9e1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001f9e6  mov     [rbx+0Ch], eax
0x18001f9e9  mov     ecx, edi; this
0x18001f9eb  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18001f9f0  jmp     short loc_18001FA02
0x18001f9f2  mov     ecx, edi; this
0x18001f9f4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18001f9f9  jmp     short loc_18001FA02
0x18001f9fb  mov     ecx, edi; this
0x18001f9fd  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18001fa02  mov     ebp, eax
0x18001fa04  mov     [rbx], r15d
0x18001fa07  mov     eax, [rsp+78h+arg_70]
0x18001fa0e  mov     [rbx+4], eax
0x18001fa11  cmp     dword ptr [r14+8], 1
0x18001fa16  jnz     short loc_18001FA1E
0x18001fa18  or      eax, 8
0x18001fa1b  mov     [rbx+4], eax
0x18001fa1e  mov     eax, 1
0x18001fa23  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18001fa2b  inc     eax
0x18001fa2d  mov     [rbx+10h], eax
0x18001fa30  mov     rax, [rsp+78h+arg_40]
0x18001fa38  xor     edi, edi
0x18001fa3a  test    rax, rax
0x18001fa3d  jz      short loc_18001FA44
0x18001fa3f  cmp     [rax], di
0x18001fa42  jnz     short loc_18001FA47
0x18001fa44  mov     rax, rdi
0x18001fa47  mov     [rbx+18h], rax
0x18001fa4b  call    cs:__imp_GetCurrentThreadId
0x18001fa51  mov     [rbx+20h], eax
0x18001fa54  mov     [rbx+38h], r13
0x18001fa58  mov     eax, [rsp+78h+arg_8]
0x18001fa5f  mov     [rbx+40h], eax
0x18001fa62  mov     [rbx+44h], ebp
0x18001fa65  mov     rax, [rsp+78h+arg_20]
0x18001fa6d  mov     [rbx+28h], rax
0x18001fa71  mov     [rbx+30h], r12
0x18001fa75  mov     rax, [rsp+78h+arg_28]
0x18001fa7d  mov     [rbx+88h], rax
0x18001fa84  mov     rax, [rsp+78h+arg_0]
0x18001fa8c  mov     [rbx+90h], rax
0x18001fa93  mov     [rbx+48h], rdi
0x18001fa97  xorps   xmm0, xmm0
0x18001fa9a  xor     eax, eax
0x18001fa9c  movups  xmmword ptr [rbx+68h], xmm0
0x18001faa0  mov     [rbx+78h], rax
0x18001faa4  movups  xmmword ptr [rbx+50h], xmm0
0x18001faa8  mov     [rbx+60h], rax
0x18001faac  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001fab3  test    rax, rax
0x18001fab6  jz      short loc_18001FABF
0x18001fab8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fabd  jmp     short loc_18001FAC2
0x18001fabf  mov     rax, rdi
0x18001fac2  mov     [rbx+80h], rax
0x18001fac9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18001fad0  test    rax, rax
0x18001fad3  jz      short loc_18001FADD
0x18001fad5  mov     rcx, rbx
0x18001fad8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fadd  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001fae4  test    rax, rax
0x18001fae7  jz      short loc_18001FAFF
0x18001fae9  mov     r8d, 400h
0x18001faef  mov     rdx, [rsp+78h+arg_60]
0x18001faf7  mov     rcx, rbx
0x18001fafa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001faff  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001fb06  test    rax, rax
0x18001fb09  jz      short loc_18001FB13
0x18001fb0b  mov     rcx, rbx
0x18001fb0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb13  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001fb1a  test    rax, rax
0x18001fb1d  jz      short loc_18001FB2D
0x18001fb1f  test    byte ptr [rbx+4], 2
0x18001fb23  jnz     short loc_18001FB2D
0x18001fb25  mov     rcx, rbx
0x18001fb28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb2d  cmp     [rbx+8], edi
0x18001fb30  jl      short loc_18001FB4E
0x18001fb32  cmp     r15d, 3
0x18001fb36  jz      short loc_18001FB3E
0x18001fb38  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18001fb3e  mov     ecx, 8000FFFFh; this
0x18001fb43  mov     [rbx+8], ecx
0x18001fb46  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001fb4b  mov     [rbx+0Ch], eax
0x18001fb4e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18001fb55  jnz     short loc_18001FB76
0x18001fb57  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001fb5e  test    rax, rax
0x18001fb61  jz      short loc_18001FB6C
0x18001fb63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb68  test    al, al
0x18001fb6a  jmp     short loc_18001FB74
0x18001fb6c  call    cs:__imp_IsDebuggerPresent
0x18001fb72  test    eax, eax
0x18001fb74  jz      short loc_18001FB7C
0x18001fb76  test    byte ptr [rbx+4], 2
0x18001fb7a  jz      short loc_18001FBA0
0x18001fb7c  mov     rax, cs:g_pfnResultLoggingCallback
0x18001fb83  test    rax, rax
0x18001fb86  jz      short loc_18001FBE4
0x18001fb88  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001fb8f  jnz     short loc_18001FBE4
0x18001fb91  xor     r8d, r8d
0x18001fb94  xor     edx, edx
0x18001fb96  mov     rcx, rbx
0x18001fb99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb9e  jmp     short loc_18001FBE4
0x18001fba0  mov     ebp, 800h
0x18001fba5  mov     rax, cs:g_pfnResultLoggingCallback
0x18001fbac  test    rax, rax
0x18001fbaf  jz      short loc_18001FBC8
0x18001fbb1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001fbb8  jnz     short loc_18001FBC8
0x18001fbba  mov     r8d, ebp
0x18001fbbd  mov     rdx, rsi
0x18001fbc0  mov     rcx, rbx
0x18001fbc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fbc8  cmp     [rsi], di
0x18001fbcb  jnz     short loc_18001FBDB
0x18001fbcd  mov     r8, rbx; unsigned __int64
0x18001fbd0  mov     rdx, rbp; unsigned __int16 *
0x18001fbd3  mov     rcx, rsi; this
0x18001fbd6  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18001fbdb  mov     rcx, rsi; lpOutputString
0x18001fbde  call    cs:__imp_OutputDebugStringW
0x18001fbe4  test    byte ptr [rbx+4], 4
0x18001fbe8  jnz     short loc_18001FBF3
0x18001fbea  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18001fbf1  jz      short loc_18001FC05
0x18001fbf3  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001fbfa  test    rax, rax
0x18001fbfd  jz      short loc_18001FC05
0x18001fbff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc04  nop
0x18001fc05  mov     rbx, [rsp+78h+arg_10]
0x18001fc0d  add     rsp, 40h
0x18001fc11  pop     r15
0x18001fc13  pop     r14
0x18001fc15  pop     r13
0x18001fc17  pop     r12
0x18001fc19  pop     rdi
0x18001fc1a  pop     rsi
0x18001fc1b  pop     rbp
0x18001fc1c  retn
```
