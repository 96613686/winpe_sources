# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000e034`
- end: `0x18000e32d`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18000bef0`

## callees

- `0x18000b92c`
- `0x18000d1f4`
- `0x18000ddd0`
- `0x18000e034`
- `0x18000ea28`
- `0x18000ea50`
- `0x18000ea64`
- `0x18000ea80`
- `0x180010398`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e157`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e157`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000e2e8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000e2e8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000e276`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000e276`

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
0x18000e034  mov     [rsp+arg_10], rbx
0x18000e039  mov     [rsp+arg_8], edx
0x18000e03d  mov     [rsp+arg_0], rcx
0x18000e042  push    rbp
0x18000e043  push    rsi
0x18000e044  push    rdi
0x18000e045  push    r12
0x18000e047  push    r13
0x18000e049  push    r14
0x18000e04b  push    r15
0x18000e04d  sub     rsp, 40h
0x18000e051  mov     r12, r9
0x18000e054  mov     r13, r8
0x18000e057  mov     r10, rcx
0x18000e05a  xor     eax, eax
0x18000e05c  mov     rsi, [rsp+78h+lpOutputString]
0x18000e064  mov     [rsi], ax
0x18000e067  mov     rax, [rsp+78h+arg_60]
0x18000e06f  mov     byte ptr [rax], 0
0x18000e072  mov     r14, [rsp+78h+arg_38]
0x18000e07a  mov     edi, [r14]
0x18000e07d  mov     rbx, [rsp+78h+arg_78]
0x18000e085  mov     [rbx+8], edi
0x18000e088  mov     eax, [r14+4]
0x18000e08c  mov     [rbx+0Ch], eax
0x18000e08f  xor     ebp, ebp
0x18000e091  mov     r15d, [rsp+78h+arg_30]
0x18000e099  mov     ecx, r15d
0x18000e09c  test    r15d, r15d
0x18000e09f  jz      short loc_18000E107
0x18000e0a1  sub     ecx, 1
0x18000e0a4  jz      short loc_18000E0FE
0x18000e0a6  sub     ecx, 1
0x18000e0a9  jz      short loc_18000E0B9
0x18000e0ab  cmp     ecx, 1
0x18000e0ae  jnz     short loc_18000E110
0x18000e0b0  mov     ecx, edi; this
0x18000e0b2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000e0b7  jmp     short loc_18000E10E
0x18000e0b9  test    edi, edi
0x18000e0bb  js      short loc_18000E0F5
0x18000e0bd  mov     edi, 8007029Ch
0x18000e0c2  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000e0c6  mov     rax, [rsp+78h+arg_28]
0x18000e0ce  mov     [rsp+78h+var_50], rax; __int64
0x18000e0d3  mov     rax, [rsp+78h+arg_20]
0x18000e0db  mov     [rsp+78h+var_58], rax; __int64
0x18000e0e0  mov     rcx, r10; int
0x18000e0e3  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000e0e8  mov     [rbx+8], edi
0x18000e0eb  mov     ecx, edi; this
0x18000e0ed  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000e0f2  mov     [rbx+0Ch], eax
0x18000e0f5  mov     ecx, edi; this
0x18000e0f7  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000e0fc  jmp     short loc_18000E10E
0x18000e0fe  mov     ecx, edi; this
0x18000e100  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000e105  jmp     short loc_18000E10E
0x18000e107  mov     ecx, edi; this
0x18000e109  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000e10e  mov     ebp, eax
0x18000e110  mov     [rbx], r15d
0x18000e113  mov     eax, [rsp+78h+arg_70]
0x18000e11a  mov     [rbx+4], eax
0x18000e11d  cmp     dword ptr [r14+8], 1
0x18000e122  jnz     short loc_18000E12A
0x18000e124  or      eax, 8
0x18000e127  mov     [rbx+4], eax
0x18000e12a  mov     eax, 1
0x18000e12f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000e137  inc     eax
0x18000e139  mov     [rbx+10h], eax
0x18000e13c  mov     rax, [rsp+78h+arg_40]
0x18000e144  xor     edi, edi
0x18000e146  test    rax, rax
0x18000e149  jz      short loc_18000E150
0x18000e14b  cmp     [rax], di
0x18000e14e  jnz     short loc_18000E153
0x18000e150  mov     rax, rdi
0x18000e153  mov     [rbx+18h], rax
0x18000e157  call    cs:__imp_GetCurrentThreadId
0x18000e15d  mov     [rbx+20h], eax
0x18000e160  mov     [rbx+38h], r13
0x18000e164  mov     eax, [rsp+78h+arg_8]
0x18000e16b  mov     [rbx+40h], eax
0x18000e16e  mov     [rbx+44h], ebp
0x18000e171  mov     rax, [rsp+78h+arg_20]
0x18000e179  mov     [rbx+28h], rax
0x18000e17d  mov     [rbx+30h], r12
0x18000e181  mov     rax, [rsp+78h+arg_28]
0x18000e189  mov     [rbx+88h], rax
0x18000e190  mov     rax, [rsp+78h+arg_0]
0x18000e198  mov     [rbx+90h], rax
0x18000e19f  mov     [rbx+48h], rdi
0x18000e1a3  xorps   xmm0, xmm0
0x18000e1a6  xor     eax, eax
0x18000e1a8  movups  xmmword ptr [rbx+68h], xmm0
0x18000e1ac  mov     [rbx+78h], rax
0x18000e1b0  movups  xmmword ptr [rbx+50h], xmm0
0x18000e1b4  mov     [rbx+60h], rax
0x18000e1b8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000e1bf  test    rax, rax
0x18000e1c2  jz      short loc_18000E1CB
0x18000e1c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1c9  jmp     short loc_18000E1CE
0x18000e1cb  mov     rax, rdi
0x18000e1ce  mov     [rbx+80h], rax
0x18000e1d5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000e1dc  test    rax, rax
0x18000e1df  jz      short loc_18000E1E9
0x18000e1e1  mov     rcx, rbx
0x18000e1e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1e9  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000e1f0  test    rax, rax
0x18000e1f3  jz      short loc_18000E20B
0x18000e1f5  mov     r8d, 400h
0x18000e1fb  mov     rdx, [rsp+78h+arg_60]
0x18000e203  mov     rcx, rbx
0x18000e206  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e20b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000e212  test    rax, rax
0x18000e215  jz      short loc_18000E21F
0x18000e217  mov     rcx, rbx
0x18000e21a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e21f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000e226  test    rax, rax
0x18000e229  jz      short loc_18000E239
0x18000e22b  test    byte ptr [rbx+4], 2
0x18000e22f  jnz     short loc_18000E239
0x18000e231  mov     rcx, rbx
0x18000e234  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e239  cmp     [rbx+8], edi
0x18000e23c  jl      short loc_18000E258
0x18000e23e  cmp     r15d, 3
0x18000e242  jnz     loc_18000E327
0x18000e248  mov     ecx, 8000FFFFh; this
0x18000e24d  mov     [rbx+8], ecx
0x18000e250  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000e255  mov     [rbx+0Ch], eax
0x18000e258  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000e25f  jnz     short loc_18000E280
0x18000e261  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000e268  test    rax, rax
0x18000e26b  jz      short loc_18000E276
0x18000e26d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e272  test    al, al
0x18000e274  jmp     short loc_18000E27E
0x18000e276  call    cs:__imp_IsDebuggerPresent
0x18000e27c  test    eax, eax
0x18000e27e  jz      short loc_18000E286
0x18000e280  test    byte ptr [rbx+4], 2
0x18000e284  jz      short loc_18000E2AA
0x18000e286  mov     rax, cs:g_pfnResultLoggingCallback
0x18000e28d  test    rax, rax
0x18000e290  jz      short loc_18000E2EE
0x18000e292  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000e299  jnz     short loc_18000E2EE
0x18000e29b  xor     r8d, r8d
0x18000e29e  xor     edx, edx
0x18000e2a0  mov     rcx, rbx
0x18000e2a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e2a8  jmp     short loc_18000E2EE
0x18000e2aa  mov     ebp, 800h
0x18000e2af  mov     rax, cs:g_pfnResultLoggingCallback
0x18000e2b6  test    rax, rax
0x18000e2b9  jz      short loc_18000E2D2
0x18000e2bb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000e2c2  jnz     short loc_18000E2D2
0x18000e2c4  mov     r8d, ebp
0x18000e2c7  mov     rdx, rsi
0x18000e2ca  mov     rcx, rbx
0x18000e2cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e2d2  cmp     [rsi], di
0x18000e2d5  jnz     short loc_18000E2E5
0x18000e2d7  mov     r8, rbx; unsigned __int64
0x18000e2da  mov     rdx, rbp; unsigned __int16 *
0x18000e2dd  mov     rcx, rsi; this
0x18000e2e0  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000e2e5  mov     rcx, rsi; lpOutputString
0x18000e2e8  call    cs:__imp_OutputDebugStringW
0x18000e2ee  test    byte ptr [rbx+4], 4
0x18000e2f2  jnz     short loc_18000E2FD
0x18000e2f4  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000e2fb  jz      short loc_18000E30F
0x18000e2fd  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000e304  test    rax, rax
0x18000e307  jz      short loc_18000E30F
0x18000e309  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e30e  nop
0x18000e30f  mov     rbx, [rsp+78h+arg_10]
0x18000e317  add     rsp, 40h
0x18000e31b  pop     r15
0x18000e31d  pop     r14
0x18000e31f  pop     r13
0x18000e321  pop     r12
0x18000e323  pop     rdi
0x18000e324  pop     rsi
0x18000e325  pop     rbp
0x18000e326  retn
0x18000e327  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
