# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000e264`
- end: `0x18000e570`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `780`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180009674`

## callees

- `0x180005304`
- `0x180005708`
- `0x180005ac0`
- `0x180009058`
- `0x18000e264`
- `0x1800108e0`
- `0x180010a34`
- `0x180010a54`
- `0x180013ce8`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e387`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e387`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000e524`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000e524`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000e4ac`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000e4ac`

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
0x18000e264  mov     [rsp+arg_10], rbx
0x18000e269  mov     [rsp+arg_8], edx
0x18000e26d  mov     [rsp+arg_0], rcx
0x18000e272  push    rbp
0x18000e273  push    rsi
0x18000e274  push    rdi
0x18000e275  push    r12
0x18000e277  push    r13
0x18000e279  push    r14
0x18000e27b  push    r15
0x18000e27d  sub     rsp, 40h
0x18000e281  mov     r12, r9
0x18000e284  mov     r13, r8
0x18000e287  mov     r10, rcx
0x18000e28a  xor     eax, eax
0x18000e28c  mov     rsi, [rsp+78h+lpOutputString]
0x18000e294  mov     [rsi], ax
0x18000e297  mov     rax, [rsp+78h+arg_60]
0x18000e29f  mov     byte ptr [rax], 0
0x18000e2a2  mov     r14, [rsp+78h+arg_38]
0x18000e2aa  mov     edi, [r14]
0x18000e2ad  mov     rbx, [rsp+78h+arg_78]
0x18000e2b5  mov     [rbx+8], edi
0x18000e2b8  mov     eax, [r14+4]
0x18000e2bc  mov     [rbx+0Ch], eax
0x18000e2bf  xor     ebp, ebp
0x18000e2c1  mov     r15d, [rsp+78h+arg_30]
0x18000e2c9  mov     ecx, r15d
0x18000e2cc  test    r15d, r15d
0x18000e2cf  jz      short loc_18000E337
0x18000e2d1  sub     ecx, 1
0x18000e2d4  jz      short loc_18000E32E
0x18000e2d6  sub     ecx, 1
0x18000e2d9  jz      short loc_18000E2E9
0x18000e2db  cmp     ecx, 1
0x18000e2de  jnz     short loc_18000E340
0x18000e2e0  mov     ecx, edi; this
0x18000e2e2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000e2e7  jmp     short loc_18000E33E
0x18000e2e9  test    edi, edi
0x18000e2eb  js      short loc_18000E325
0x18000e2ed  mov     edi, 8007029Ch
0x18000e2f2  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000e2f6  mov     rax, [rsp+78h+arg_28]
0x18000e2fe  mov     [rsp+78h+var_50], rax; __int64
0x18000e303  mov     rax, [rsp+78h+arg_20]
0x18000e30b  mov     [rsp+78h+var_58], rax; __int64
0x18000e310  mov     rcx, r10; int
0x18000e313  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000e318  mov     [rbx+8], edi
0x18000e31b  mov     ecx, edi; this
0x18000e31d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000e322  mov     [rbx+0Ch], eax
0x18000e325  mov     ecx, edi; this
0x18000e327  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000e32c  jmp     short loc_18000E33E
0x18000e32e  mov     ecx, edi; this
0x18000e330  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000e335  jmp     short loc_18000E33E
0x18000e337  mov     ecx, edi; this
0x18000e339  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000e33e  mov     ebp, eax
0x18000e340  mov     [rbx], r15d
0x18000e343  mov     eax, [rsp+78h+arg_70]
0x18000e34a  mov     [rbx+4], eax
0x18000e34d  cmp     dword ptr [r14+8], 1
0x18000e352  jnz     short loc_18000E35A
0x18000e354  or      eax, 8
0x18000e357  mov     [rbx+4], eax
0x18000e35a  mov     eax, 1
0x18000e35f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000e367  inc     eax
0x18000e369  mov     [rbx+10h], eax
0x18000e36c  mov     rax, [rsp+78h+arg_40]
0x18000e374  xor     edi, edi
0x18000e376  test    rax, rax
0x18000e379  jz      short loc_18000E380
0x18000e37b  cmp     [rax], di
0x18000e37e  jnz     short loc_18000E383
0x18000e380  mov     rax, rdi
0x18000e383  mov     [rbx+18h], rax
0x18000e387  call    cs:__imp_GetCurrentThreadId
0x18000e38e  nop     dword ptr [rax+rax+00h]
0x18000e393  mov     [rbx+20h], eax
0x18000e396  mov     [rbx+38h], r13
0x18000e39a  mov     eax, [rsp+78h+arg_8]
0x18000e3a1  mov     [rbx+40h], eax
0x18000e3a4  mov     [rbx+44h], ebp
0x18000e3a7  mov     rax, [rsp+78h+arg_20]
0x18000e3af  mov     [rbx+28h], rax
0x18000e3b3  mov     [rbx+30h], r12
0x18000e3b7  mov     rax, [rsp+78h+arg_28]
0x18000e3bf  mov     [rbx+88h], rax
0x18000e3c6  mov     rax, [rsp+78h+arg_0]
0x18000e3ce  mov     [rbx+90h], rax
0x18000e3d5  mov     [rbx+48h], rdi
0x18000e3d9  xorps   xmm0, xmm0
0x18000e3dc  xor     eax, eax
0x18000e3de  movups  xmmword ptr [rbx+68h], xmm0
0x18000e3e2  mov     [rbx+78h], rax
0x18000e3e6  movups  xmmword ptr [rbx+50h], xmm0
0x18000e3ea  mov     [rbx+60h], rax
0x18000e3ee  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000e3f5  test    rax, rax
0x18000e3f8  jz      short loc_18000E401
0x18000e3fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e3ff  jmp     short loc_18000E404
0x18000e401  mov     rax, rdi
0x18000e404  mov     [rbx+80h], rax
0x18000e40b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000e412  test    rax, rax
0x18000e415  jz      short loc_18000E41F
0x18000e417  mov     rcx, rbx
0x18000e41a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e41f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000e426  test    rax, rax
0x18000e429  jz      short loc_18000E441
0x18000e42b  mov     r8d, 400h
0x18000e431  mov     rdx, [rsp+78h+arg_60]
0x18000e439  mov     rcx, rbx
0x18000e43c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e441  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000e448  test    rax, rax
0x18000e44b  jz      short loc_18000E455
0x18000e44d  mov     rcx, rbx
0x18000e450  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e455  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000e45c  test    rax, rax
0x18000e45f  jz      short loc_18000E46F
0x18000e461  test    byte ptr [rbx+4], 2
0x18000e465  jnz     short loc_18000E46F
0x18000e467  mov     rcx, rbx
0x18000e46a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e46f  cmp     [rbx+8], edi
0x18000e472  jl      short loc_18000E48E
0x18000e474  cmp     r15d, 3
0x18000e478  jnz     loc_18000E56A
0x18000e47e  mov     ecx, 8000FFFFh; this
0x18000e483  mov     [rbx+8], ecx
0x18000e486  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000e48b  mov     [rbx+0Ch], eax
0x18000e48e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000e495  jnz     short loc_18000E4BC
0x18000e497  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000e49e  test    rax, rax
0x18000e4a1  jz      short loc_18000E4AC
0x18000e4a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4a8  test    al, al
0x18000e4aa  jmp     short loc_18000E4BA
0x18000e4ac  call    cs:__imp_IsDebuggerPresent
0x18000e4b3  nop     dword ptr [rax+rax+00h]
0x18000e4b8  test    eax, eax
0x18000e4ba  jz      short loc_18000E4C2
0x18000e4bc  test    byte ptr [rbx+4], 2
0x18000e4c0  jz      short loc_18000E4E6
0x18000e4c2  mov     rax, cs:g_pfnResultLoggingCallback
0x18000e4c9  test    rax, rax
0x18000e4cc  jz      short loc_18000E530
0x18000e4ce  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000e4d5  jnz     short loc_18000E530
0x18000e4d7  xor     r8d, r8d
0x18000e4da  xor     edx, edx
0x18000e4dc  mov     rcx, rbx
0x18000e4df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4e4  jmp     short loc_18000E530
0x18000e4e6  mov     ebp, 800h
0x18000e4eb  mov     rax, cs:g_pfnResultLoggingCallback
0x18000e4f2  test    rax, rax
0x18000e4f5  jz      short loc_18000E50E
0x18000e4f7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000e4fe  jnz     short loc_18000E50E
0x18000e500  mov     r8d, ebp
0x18000e503  mov     rdx, rsi
0x18000e506  mov     rcx, rbx
0x18000e509  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e50e  cmp     [rsi], di
0x18000e511  jnz     short loc_18000E521
0x18000e513  mov     r8, rbx; unsigned __int64
0x18000e516  mov     rdx, rbp; unsigned __int16 *
0x18000e519  mov     rcx, rsi; this
0x18000e51c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000e521  mov     rcx, rsi; lpOutputString
0x18000e524  call    cs:__imp_OutputDebugStringW
0x18000e52b  nop     dword ptr [rax+rax+00h]
0x18000e530  test    byte ptr [rbx+4], 4
0x18000e534  jnz     short loc_18000E53F
0x18000e536  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000e53d  jz      short loc_18000E551
0x18000e53f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000e546  test    rax, rax
0x18000e549  jz      short loc_18000E551
0x18000e54b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e550  nop
0x18000e551  mov     rbx, [rsp+78h+arg_10]
0x18000e559  add     rsp, 40h
0x18000e55d  pop     r15
0x18000e55f  pop     r14
0x18000e561  pop     r13
0x18000e563  pop     r12
0x18000e565  pop     rdi
0x18000e566  pop     rsi
0x18000e567  pop     rbp
0x18000e568  retn
0x18000e56a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
