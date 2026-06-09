# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000bcb8`
- end: `0x18000bfc4`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `780`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18000618c`

## callees

- `0x180005744`
- `0x18000b004`
- `0x18000b7f0`
- `0x18000bcb8`
- `0x18000dc68`
- `0x18000dc90`
- `0x18000dca4`
- `0x18000dcc4`
- `0x180013490`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bddb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bddb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000bf78`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000bf78`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000bf00`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000bf00`

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
0x18000bcb8  mov     [rsp+arg_10], rbx
0x18000bcbd  mov     [rsp+arg_8], edx
0x18000bcc1  mov     [rsp+arg_0], rcx
0x18000bcc6  push    rbp
0x18000bcc7  push    rsi
0x18000bcc8  push    rdi
0x18000bcc9  push    r12
0x18000bccb  push    r13
0x18000bccd  push    r14
0x18000bccf  push    r15
0x18000bcd1  sub     rsp, 40h
0x18000bcd5  mov     r12, r9
0x18000bcd8  mov     r13, r8
0x18000bcdb  mov     r10, rcx
0x18000bcde  xor     eax, eax
0x18000bce0  mov     rsi, [rsp+78h+lpOutputString]
0x18000bce8  mov     [rsi], ax
0x18000bceb  mov     rax, [rsp+78h+arg_60]
0x18000bcf3  mov     byte ptr [rax], 0
0x18000bcf6  mov     r14, [rsp+78h+arg_38]
0x18000bcfe  mov     edi, [r14]
0x18000bd01  mov     rbx, [rsp+78h+arg_78]
0x18000bd09  mov     [rbx+8], edi
0x18000bd0c  mov     eax, [r14+4]
0x18000bd10  mov     [rbx+0Ch], eax
0x18000bd13  xor     ebp, ebp
0x18000bd15  mov     r15d, [rsp+78h+arg_30]
0x18000bd1d  mov     ecx, r15d
0x18000bd20  test    r15d, r15d
0x18000bd23  jz      short loc_18000BD8B
0x18000bd25  sub     ecx, 1
0x18000bd28  jz      short loc_18000BD82
0x18000bd2a  sub     ecx, 1
0x18000bd2d  jz      short loc_18000BD3D
0x18000bd2f  cmp     ecx, 1
0x18000bd32  jnz     short loc_18000BD94
0x18000bd34  mov     ecx, edi; this
0x18000bd36  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000bd3b  jmp     short loc_18000BD92
0x18000bd3d  test    edi, edi
0x18000bd3f  js      short loc_18000BD79
0x18000bd41  mov     edi, 8007029Ch
0x18000bd46  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000bd4a  mov     rax, [rsp+78h+arg_28]
0x18000bd52  mov     [rsp+78h+var_50], rax; __int64
0x18000bd57  mov     rax, [rsp+78h+arg_20]
0x18000bd5f  mov     [rsp+78h+var_58], rax; __int64
0x18000bd64  mov     rcx, r10; int
0x18000bd67  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000bd6c  mov     [rbx+8], edi
0x18000bd6f  mov     ecx, edi; this
0x18000bd71  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000bd76  mov     [rbx+0Ch], eax
0x18000bd79  mov     ecx, edi; this
0x18000bd7b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000bd80  jmp     short loc_18000BD92
0x18000bd82  mov     ecx, edi; this
0x18000bd84  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000bd89  jmp     short loc_18000BD92
0x18000bd8b  mov     ecx, edi; this
0x18000bd8d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000bd92  mov     ebp, eax
0x18000bd94  mov     [rbx], r15d
0x18000bd97  mov     eax, [rsp+78h+arg_70]
0x18000bd9e  mov     [rbx+4], eax
0x18000bda1  cmp     dword ptr [r14+8], 1
0x18000bda6  jnz     short loc_18000BDAE
0x18000bda8  or      eax, 8
0x18000bdab  mov     [rbx+4], eax
0x18000bdae  mov     eax, 1
0x18000bdb3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000bdbb  inc     eax
0x18000bdbd  mov     [rbx+10h], eax
0x18000bdc0  mov     rax, [rsp+78h+arg_40]
0x18000bdc8  xor     edi, edi
0x18000bdca  test    rax, rax
0x18000bdcd  jz      short loc_18000BDD4
0x18000bdcf  cmp     [rax], di
0x18000bdd2  jnz     short loc_18000BDD7
0x18000bdd4  mov     rax, rdi
0x18000bdd7  mov     [rbx+18h], rax
0x18000bddb  call    cs:__imp_GetCurrentThreadId
0x18000bde2  nop     dword ptr [rax+rax+00h]
0x18000bde7  mov     [rbx+20h], eax
0x18000bdea  mov     [rbx+38h], r13
0x18000bdee  mov     eax, [rsp+78h+arg_8]
0x18000bdf5  mov     [rbx+40h], eax
0x18000bdf8  mov     [rbx+44h], ebp
0x18000bdfb  mov     rax, [rsp+78h+arg_20]
0x18000be03  mov     [rbx+28h], rax
0x18000be07  mov     [rbx+30h], r12
0x18000be0b  mov     rax, [rsp+78h+arg_28]
0x18000be13  mov     [rbx+88h], rax
0x18000be1a  mov     rax, [rsp+78h+arg_0]
0x18000be22  mov     [rbx+90h], rax
0x18000be29  mov     [rbx+48h], rdi
0x18000be2d  xorps   xmm0, xmm0
0x18000be30  xor     eax, eax
0x18000be32  movups  xmmword ptr [rbx+68h], xmm0
0x18000be36  mov     [rbx+78h], rax
0x18000be3a  movups  xmmword ptr [rbx+50h], xmm0
0x18000be3e  mov     [rbx+60h], rax
0x18000be42  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000be49  test    rax, rax
0x18000be4c  jz      short loc_18000BE55
0x18000be4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be53  jmp     short loc_18000BE58
0x18000be55  mov     rax, rdi
0x18000be58  mov     [rbx+80h], rax
0x18000be5f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000be66  test    rax, rax
0x18000be69  jz      short loc_18000BE73
0x18000be6b  mov     rcx, rbx
0x18000be6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be73  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000be7a  test    rax, rax
0x18000be7d  jz      short loc_18000BE95
0x18000be7f  mov     r8d, 400h
0x18000be85  mov     rdx, [rsp+78h+arg_60]
0x18000be8d  mov     rcx, rbx
0x18000be90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be95  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000be9c  test    rax, rax
0x18000be9f  jz      short loc_18000BEA9
0x18000bea1  mov     rcx, rbx
0x18000bea4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bea9  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000beb0  test    rax, rax
0x18000beb3  jz      short loc_18000BEC3
0x18000beb5  test    byte ptr [rbx+4], 2
0x18000beb9  jnz     short loc_18000BEC3
0x18000bebb  mov     rcx, rbx
0x18000bebe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bec3  cmp     [rbx+8], edi
0x18000bec6  jl      short loc_18000BEE2
0x18000bec8  cmp     r15d, 3
0x18000becc  jnz     loc_18000BFBE
0x18000bed2  mov     ecx, 8000FFFFh; this
0x18000bed7  mov     [rbx+8], ecx
0x18000beda  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000bedf  mov     [rbx+0Ch], eax
0x18000bee2  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000bee9  jnz     short loc_18000BF10
0x18000beeb  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000bef2  test    rax, rax
0x18000bef5  jz      short loc_18000BF00
0x18000bef7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000befc  test    al, al
0x18000befe  jmp     short loc_18000BF0E
0x18000bf00  call    cs:__imp_IsDebuggerPresent
0x18000bf07  nop     dword ptr [rax+rax+00h]
0x18000bf0c  test    eax, eax
0x18000bf0e  jz      short loc_18000BF16
0x18000bf10  test    byte ptr [rbx+4], 2
0x18000bf14  jz      short loc_18000BF3A
0x18000bf16  mov     rax, cs:g_pfnResultLoggingCallback
0x18000bf1d  test    rax, rax
0x18000bf20  jz      short loc_18000BF84
0x18000bf22  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000bf29  jnz     short loc_18000BF84
0x18000bf2b  xor     r8d, r8d
0x18000bf2e  xor     edx, edx
0x18000bf30  mov     rcx, rbx
0x18000bf33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf38  jmp     short loc_18000BF84
0x18000bf3a  mov     ebp, 800h
0x18000bf3f  mov     rax, cs:g_pfnResultLoggingCallback
0x18000bf46  test    rax, rax
0x18000bf49  jz      short loc_18000BF62
0x18000bf4b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000bf52  jnz     short loc_18000BF62
0x18000bf54  mov     r8d, ebp
0x18000bf57  mov     rdx, rsi
0x18000bf5a  mov     rcx, rbx
0x18000bf5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf62  cmp     [rsi], di
0x18000bf65  jnz     short loc_18000BF75
0x18000bf67  mov     r8, rbx; unsigned __int64
0x18000bf6a  mov     rdx, rbp; unsigned __int16 *
0x18000bf6d  mov     rcx, rsi; this
0x18000bf70  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000bf75  mov     rcx, rsi; lpOutputString
0x18000bf78  call    cs:__imp_OutputDebugStringW
0x18000bf7f  nop     dword ptr [rax+rax+00h]
0x18000bf84  test    byte ptr [rbx+4], 4
0x18000bf88  jnz     short loc_18000BF93
0x18000bf8a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000bf91  jz      short loc_18000BFA5
0x18000bf93  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000bf9a  test    rax, rax
0x18000bf9d  jz      short loc_18000BFA5
0x18000bf9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfa4  nop
0x18000bfa5  mov     rbx, [rsp+78h+arg_10]
0x18000bfad  add     rsp, 40h
0x18000bfb1  pop     r15
0x18000bfb3  pop     r14
0x18000bfb5  pop     r13
0x18000bfb7  pop     r12
0x18000bfb9  pop     rdi
0x18000bfba  pop     rsi
0x18000bfbb  pop     rbp
0x18000bfbc  retn
0x18000bfbe  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
