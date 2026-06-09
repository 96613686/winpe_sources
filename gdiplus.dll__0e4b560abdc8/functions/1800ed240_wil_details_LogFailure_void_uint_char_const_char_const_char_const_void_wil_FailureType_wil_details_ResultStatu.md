# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)

- ea: `0x1800ed240`
- end: `0x1800ed543`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7PEAUFailureInfo@2@@Z`
- size: `771`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x1800ea7a4`
- `0x1800ea850`
- `0x1800ea944`

## callees

- `0x1800ea6f8`
- `0x1800ec298`
- `0x1800ecb7c`
- `0x1800ed240`
- `0x1800edfcc`
- `0x1800edff0`
- `0x1800ee0cc`
- `0x1800ee0ec`
- `0x1800efbd4`
- `0x180175010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ed35f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ed35f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800ed4fe`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800ed4fe`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800ed485`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800ed485`

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
        WCHAR *lpOutputString,
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
  *lpOutputString = 0;
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
    if ( !*lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a15, v25);
    OutputDebugStringW(lpOutputString);
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
0x1800ed240  mov     [rsp+arg_10], rbx
0x1800ed245  mov     [rsp+arg_8], edx
0x1800ed249  mov     [rsp+arg_0], rcx
0x1800ed24e  push    rbp
0x1800ed24f  push    rsi
0x1800ed250  push    rdi
0x1800ed251  push    r12
0x1800ed253  push    r13
0x1800ed255  push    r14
0x1800ed257  push    r15
0x1800ed259  sub     rsp, 40h
0x1800ed25d  mov     rax, [rsp+78h+arg_60]
0x1800ed265  mov     r13, r8
0x1800ed268  mov     r15, [rsp+78h+arg_38]
0x1800ed270  xor     r8d, r8d
0x1800ed273  mov     rbx, [rsp+78h+arg_70]
0x1800ed27b  mov     r10, rcx
0x1800ed27e  mov     ebp, [rsp+78h+arg_30]
0x1800ed285  mov     r12, r9
0x1800ed288  mov     r14, [rsp+78h+lpOutputString]
0x1800ed290  mov     esi, r8d
0x1800ed293  mov     ecx, ebp
0x1800ed295  mov     [r14], r8w
0x1800ed299  mov     [rax], r8b
0x1800ed29c  mov     edi, [r15]
0x1800ed29f  mov     [rbx+8], edi
0x1800ed2a2  mov     eax, [r15+4]
0x1800ed2a6  mov     [rbx+0Ch], eax
0x1800ed2a9  test    ebp, ebp
0x1800ed2ab  jz      short loc_1800ED316
0x1800ed2ad  sub     ecx, 1
0x1800ed2b0  jz      short loc_1800ED30D
0x1800ed2b2  sub     ecx, 1
0x1800ed2b5  jz      short loc_1800ED2C5
0x1800ed2b7  cmp     ecx, 1
0x1800ed2ba  jnz     short loc_1800ED31F
0x1800ed2bc  mov     ecx, edi; this
0x1800ed2be  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800ed2c3  jmp     short loc_1800ED31D
0x1800ed2c5  test    edi, edi
0x1800ed2c7  js      short loc_1800ED304
0x1800ed2c9  mov     rax, [rsp+78h+arg_28]
0x1800ed2d1  mov     edi, 8007029Ch
0x1800ed2d6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800ed2da  mov     r8, r13; int
0x1800ed2dd  mov     [rsp+78h+var_50], rax; __int64
0x1800ed2e2  mov     rcx, r10; int
0x1800ed2e5  mov     rax, [rsp+78h+arg_20]
0x1800ed2ed  mov     [rsp+78h+var_58], rax; __int64
0x1800ed2f2  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110J@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long)
0x1800ed2f7  mov     ecx, edi; this
0x1800ed2f9  mov     [rbx+8], edi
0x1800ed2fc  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800ed301  mov     [rbx+0Ch], eax
0x1800ed304  mov     ecx, edi; this
0x1800ed306  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800ed30b  jmp     short loc_1800ED31D
0x1800ed30d  mov     ecx, edi; this
0x1800ed30f  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800ed314  jmp     short loc_1800ED31D
0x1800ed316  mov     ecx, edi; this
0x1800ed318  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800ed31d  mov     esi, eax
0x1800ed31f  xor     edi, edi
0x1800ed321  mov     [rbx], ebp
0x1800ed323  mov     [rbx+4], edi
0x1800ed326  cmp     dword ptr [r15+8], 1
0x1800ed32b  jnz     short loc_1800ED334
0x1800ed32d  mov     dword ptr [rbx+4], 8
0x1800ed334  mov     eax, 1
0x1800ed339  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)'::`2'::s_failureId
0x1800ed341  inc     eax
0x1800ed343  mov     [rbx+10h], eax
0x1800ed346  mov     rax, [rsp+78h+arg_40]
0x1800ed34e  test    rax, rax
0x1800ed351  jz      short loc_1800ED358
0x1800ed353  cmp     [rax], di
0x1800ed356  jnz     short loc_1800ED35B
0x1800ed358  mov     rax, rdi
0x1800ed35b  mov     [rbx+18h], rax
0x1800ed35f  call    cs:__imp_GetCurrentThreadId
0x1800ed366  nop     dword ptr [rax+rax+00h]
0x1800ed36b  mov     [rbx+38h], r13
0x1800ed36f  xorps   xmm0, xmm0
0x1800ed372  mov     [rbx+20h], eax
0x1800ed375  mov     eax, [rsp+78h+arg_8]
0x1800ed37c  mov     [rbx+40h], eax
0x1800ed37f  mov     rax, [rsp+78h+arg_20]
0x1800ed387  mov     [rbx+28h], rax
0x1800ed38b  mov     rax, [rsp+78h+arg_28]
0x1800ed393  mov     [rbx+88h], rax
0x1800ed39a  mov     rax, [rsp+78h+arg_0]
0x1800ed3a2  mov     [rbx+90h], rax
0x1800ed3a9  xor     eax, eax
0x1800ed3ab  mov     [rbx+44h], esi
0x1800ed3ae  mov     [rbx+30h], r12
0x1800ed3b2  mov     [rbx+48h], rdi
0x1800ed3b6  movups  xmmword ptr [rbx+68h], xmm0
0x1800ed3ba  mov     [rbx+78h], rax
0x1800ed3be  movups  xmmword ptr [rbx+50h], xmm0
0x1800ed3c2  mov     [rbx+60h], rax
0x1800ed3c6  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800ed3cd  test    rax, rax
0x1800ed3d0  jz      short loc_1800ED3D9
0x1800ed3d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed3d7  jmp     short loc_1800ED3DC
0x1800ed3d9  mov     rax, rdi
0x1800ed3dc  mov     [rbx+80h], rax
0x1800ed3e3  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800ed3ea  test    rax, rax
0x1800ed3ed  jz      short loc_1800ED3F7
0x1800ed3ef  mov     rcx, rbx
0x1800ed3f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed3f7  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800ed3fe  test    rax, rax
0x1800ed401  jz      short loc_1800ED419
0x1800ed403  mov     rdx, [rsp+78h+arg_60]
0x1800ed40b  mov     r8d, 400h
0x1800ed411  mov     rcx, rbx
0x1800ed414  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed419  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800ed420  test    rax, rax
0x1800ed423  jz      short loc_1800ED42D
0x1800ed425  mov     rcx, rbx
0x1800ed428  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed42d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800ed434  test    rax, rax
0x1800ed437  jz      short loc_1800ED447
0x1800ed439  test    byte ptr [rbx+4], 2
0x1800ed43d  jnz     short loc_1800ED447
0x1800ed43f  mov     rcx, rbx
0x1800ed442  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed447  cmp     [rbx+8], edi
0x1800ed44a  jl      short loc_1800ED467
0x1800ed44c  cmp     ebp, 3
0x1800ed44f  jz      short loc_1800ED457
0x1800ed451  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800ed457  mov     ecx, 8000FFFFh; this
0x1800ed45c  mov     [rbx+8], ecx
0x1800ed45f  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800ed464  mov     [rbx+0Ch], eax
0x1800ed467  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800ed46e  jnz     short loc_1800ED495
0x1800ed470  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800ed477  test    rax, rax
0x1800ed47a  jz      short loc_1800ED485
0x1800ed47c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed481  test    al, al
0x1800ed483  jmp     short loc_1800ED493
0x1800ed485  call    cs:__imp_IsDebuggerPresent
0x1800ed48c  nop     dword ptr [rax+rax+00h]
0x1800ed491  test    eax, eax
0x1800ed493  jz      short loc_1800ED49B
0x1800ed495  test    byte ptr [rbx+4], 2
0x1800ed499  jz      short loc_1800ED4BF
0x1800ed49b  mov     rax, cs:g_pfnResultLoggingCallback
0x1800ed4a2  test    rax, rax
0x1800ed4a5  jz      short loc_1800ED50A
0x1800ed4a7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800ed4ae  jnz     short loc_1800ED50A
0x1800ed4b0  xor     r8d, r8d
0x1800ed4b3  xor     edx, edx
0x1800ed4b5  mov     rcx, rbx
0x1800ed4b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed4bd  jmp     short loc_1800ED50A
0x1800ed4bf  mov     rax, cs:g_pfnResultLoggingCallback
0x1800ed4c6  mov     esi, 800h
0x1800ed4cb  test    rax, rax
0x1800ed4ce  jz      short loc_1800ED4E7
0x1800ed4d0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800ed4d7  jnz     short loc_1800ED4E7
0x1800ed4d9  mov     r8d, esi
0x1800ed4dc  mov     rdx, r14
0x1800ed4df  mov     rcx, rbx
0x1800ed4e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed4e7  cmp     [r14], di
0x1800ed4eb  jnz     short loc_1800ED4FB
0x1800ed4ed  mov     r8, rbx; unsigned __int64
0x1800ed4f0  mov     rdx, rsi; unsigned __int16 *
0x1800ed4f3  mov     rcx, r14; pszDest
0x1800ed4f6  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800ed4fb  mov     rcx, r14; lpOutputString
0x1800ed4fe  call    cs:__imp_OutputDebugStringW
0x1800ed505  nop     dword ptr [rax+rax+00h]
0x1800ed50a  test    byte ptr [rbx+4], 4
0x1800ed50e  jnz     short loc_1800ED519
0x1800ed510  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800ed517  jz      short loc_1800ED52A
0x1800ed519  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800ed520  test    rax, rax
0x1800ed523  jz      short loc_1800ED52A
0x1800ed525  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed52a  mov     rbx, [rsp+78h+arg_10]
0x1800ed532  add     rsp, 40h
0x1800ed536  pop     r15
0x1800ed538  pop     r14
0x1800ed53a  pop     r13
0x1800ed53c  pop     r12
0x1800ed53e  pop     rdi
0x1800ed53f  pop     rsi
0x1800ed540  pop     rbp
0x1800ed541  retn
```
