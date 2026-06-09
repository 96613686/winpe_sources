# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800218cc`
- end: `0x180021bc1`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x18002053c`
- `0x1800205fc`
- `0x1800206f8`
- `0x18004cba4`

## callees

- `0x18001c0e4`
- `0x180020488`
- `0x180021184`
- `0x1800218cc`
- `0x180021fac`
- `0x180021fd0`
- `0x180021fe4`
- `0x180022000`
- `0x180022e04`
- `0x180065010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800219ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800219ef`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180021b10`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180021b10`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180021b82`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180021b82`

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
0x1800218cc  mov     [rsp+arg_10], rbx
0x1800218d1  mov     [rsp+arg_8], edx
0x1800218d5  mov     [rsp+arg_0], rcx
0x1800218da  push    rbp
0x1800218db  push    rsi
0x1800218dc  push    rdi
0x1800218dd  push    r12
0x1800218df  push    r13
0x1800218e1  push    r14
0x1800218e3  push    r15
0x1800218e5  sub     rsp, 40h
0x1800218e9  mov     r12, r9
0x1800218ec  mov     r13, r8
0x1800218ef  mov     r10, rcx
0x1800218f2  xor     eax, eax
0x1800218f4  mov     rsi, [rsp+78h+lpOutputString]
0x1800218fc  mov     [rsi], ax
0x1800218ff  mov     rax, [rsp+78h+arg_60]
0x180021907  mov     byte ptr [rax], 0
0x18002190a  mov     r14, [rsp+78h+arg_38]
0x180021912  mov     edi, [r14]
0x180021915  mov     rbx, [rsp+78h+arg_78]
0x18002191d  mov     [rbx+8], edi
0x180021920  mov     eax, [r14+4]
0x180021924  mov     [rbx+0Ch], eax
0x180021927  xor     ebp, ebp
0x180021929  mov     r15d, [rsp+78h+arg_30]
0x180021931  mov     ecx, r15d
0x180021934  test    r15d, r15d
0x180021937  jz      short loc_18002199F
0x180021939  sub     ecx, 1
0x18002193c  jz      short loc_180021996
0x18002193e  sub     ecx, 1
0x180021941  jz      short loc_180021951
0x180021943  cmp     ecx, 1
0x180021946  jnz     short loc_1800219A8
0x180021948  mov     ecx, edi; this
0x18002194a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18002194f  jmp     short loc_1800219A6
0x180021951  test    edi, edi
0x180021953  js      short loc_18002198D
0x180021955  mov     edi, 8007029Ch
0x18002195a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18002195e  mov     rax, [rsp+78h+arg_28]
0x180021966  mov     [rsp+78h+var_50], rax; __int64
0x18002196b  mov     rax, [rsp+78h+arg_20]
0x180021973  mov     [rsp+78h+var_58], rax; __int64
0x180021978  mov     rcx, r10; int
0x18002197b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180021980  mov     [rbx+8], edi
0x180021983  mov     ecx, edi; this
0x180021985  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18002198a  mov     [rbx+0Ch], eax
0x18002198d  mov     ecx, edi; this
0x18002198f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180021994  jmp     short loc_1800219A6
0x180021996  mov     ecx, edi; this
0x180021998  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18002199d  jmp     short loc_1800219A6
0x18002199f  mov     ecx, edi; this
0x1800219a1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800219a6  mov     ebp, eax
0x1800219a8  mov     [rbx], r15d
0x1800219ab  mov     eax, [rsp+78h+arg_70]
0x1800219b2  mov     [rbx+4], eax
0x1800219b5  cmp     dword ptr [r14+8], 1
0x1800219ba  jnz     short loc_1800219C2
0x1800219bc  or      eax, 8
0x1800219bf  mov     [rbx+4], eax
0x1800219c2  mov     eax, 1
0x1800219c7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800219cf  inc     eax
0x1800219d1  mov     [rbx+10h], eax
0x1800219d4  mov     rax, [rsp+78h+arg_40]
0x1800219dc  xor     edi, edi
0x1800219de  test    rax, rax
0x1800219e1  jz      short loc_1800219E8
0x1800219e3  cmp     [rax], di
0x1800219e6  jnz     short loc_1800219EB
0x1800219e8  mov     rax, rdi
0x1800219eb  mov     [rbx+18h], rax
0x1800219ef  call    cs:__imp_GetCurrentThreadId
0x1800219f5  mov     [rbx+20h], eax
0x1800219f8  mov     [rbx+38h], r13
0x1800219fc  mov     eax, [rsp+78h+arg_8]
0x180021a03  mov     [rbx+40h], eax
0x180021a06  mov     [rbx+44h], ebp
0x180021a09  mov     rax, [rsp+78h+arg_20]
0x180021a11  mov     [rbx+28h], rax
0x180021a15  mov     [rbx+30h], r12
0x180021a19  mov     rax, [rsp+78h+arg_28]
0x180021a21  mov     [rbx+88h], rax
0x180021a28  mov     rax, [rsp+78h+arg_0]
0x180021a30  mov     [rbx+90h], rax
0x180021a37  mov     [rbx+48h], rdi
0x180021a3b  xorps   xmm0, xmm0
0x180021a3e  xor     eax, eax
0x180021a40  movups  xmmword ptr [rbx+68h], xmm0
0x180021a44  mov     [rbx+78h], rax
0x180021a48  movups  xmmword ptr [rbx+50h], xmm0
0x180021a4c  mov     [rbx+60h], rax
0x180021a50  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180021a57  test    rax, rax
0x180021a5a  jz      short loc_180021A63
0x180021a5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a61  jmp     short loc_180021A66
0x180021a63  mov     rax, rdi
0x180021a66  mov     [rbx+80h], rax
0x180021a6d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180021a74  test    rax, rax
0x180021a77  jz      short loc_180021A81
0x180021a79  mov     rcx, rbx
0x180021a7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a81  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180021a88  test    rax, rax
0x180021a8b  jz      short loc_180021AA3
0x180021a8d  mov     r8d, 400h
0x180021a93  mov     rdx, [rsp+78h+arg_60]
0x180021a9b  mov     rcx, rbx
0x180021a9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021aa3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180021aaa  test    rax, rax
0x180021aad  jz      short loc_180021AB7
0x180021aaf  mov     rcx, rbx
0x180021ab2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ab7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180021abe  test    rax, rax
0x180021ac1  jz      short loc_180021AD1
0x180021ac3  test    byte ptr [rbx+4], 2
0x180021ac7  jnz     short loc_180021AD1
0x180021ac9  mov     rcx, rbx
0x180021acc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ad1  cmp     [rbx+8], edi
0x180021ad4  jl      short loc_180021AF2
0x180021ad6  cmp     r15d, 3
0x180021ada  jz      short loc_180021AE2
0x180021adc  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180021ae2  mov     ecx, 8000FFFFh; this
0x180021ae7  mov     [rbx+8], ecx
0x180021aea  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180021aef  mov     [rbx+0Ch], eax
0x180021af2  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180021af9  jnz     short loc_180021B1A
0x180021afb  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180021b02  test    rax, rax
0x180021b05  jz      short loc_180021B10
0x180021b07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021b0c  test    al, al
0x180021b0e  jmp     short loc_180021B18
0x180021b10  call    cs:__imp_IsDebuggerPresent
0x180021b16  test    eax, eax
0x180021b18  jz      short loc_180021B20
0x180021b1a  test    byte ptr [rbx+4], 2
0x180021b1e  jz      short loc_180021B44
0x180021b20  mov     rax, cs:g_pfnResultLoggingCallback
0x180021b27  test    rax, rax
0x180021b2a  jz      short loc_180021B88
0x180021b2c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180021b33  jnz     short loc_180021B88
0x180021b35  xor     r8d, r8d
0x180021b38  xor     edx, edx
0x180021b3a  mov     rcx, rbx
0x180021b3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021b42  jmp     short loc_180021B88
0x180021b44  mov     ebp, 800h
0x180021b49  mov     rax, cs:g_pfnResultLoggingCallback
0x180021b50  test    rax, rax
0x180021b53  jz      short loc_180021B6C
0x180021b55  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180021b5c  jnz     short loc_180021B6C
0x180021b5e  mov     r8d, ebp
0x180021b61  mov     rdx, rsi
0x180021b64  mov     rcx, rbx
0x180021b67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021b6c  cmp     [rsi], di
0x180021b6f  jnz     short loc_180021B7F
0x180021b71  mov     r8, rbx; unsigned __int64
0x180021b74  mov     rdx, rbp; unsigned __int16 *
0x180021b77  mov     rcx, rsi; this
0x180021b7a  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180021b7f  mov     rcx, rsi; lpOutputString
0x180021b82  call    cs:__imp_OutputDebugStringW
0x180021b88  test    byte ptr [rbx+4], 4
0x180021b8c  jnz     short loc_180021B97
0x180021b8e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180021b95  jz      short loc_180021BA9
0x180021b97  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180021b9e  test    rax, rax
0x180021ba1  jz      short loc_180021BA9
0x180021ba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ba8  nop
0x180021ba9  mov     rbx, [rsp+78h+arg_10]
0x180021bb1  add     rsp, 40h
0x180021bb5  pop     r15
0x180021bb7  pop     r14
0x180021bb9  pop     r13
0x180021bbb  pop     r12
0x180021bbd  pop     rdi
0x180021bbe  pop     rsi
0x180021bbf  pop     rbp
0x180021bc0  retn
```
