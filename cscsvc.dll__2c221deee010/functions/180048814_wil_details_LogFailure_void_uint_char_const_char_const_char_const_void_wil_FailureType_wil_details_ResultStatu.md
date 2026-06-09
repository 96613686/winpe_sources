# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180048814`
- end: `0x180048b0c`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180047120`
- `0x18004746c`

## callees

- `0x180038a84`
- `0x180047060`
- `0x180048028`
- `0x180048814`
- `0x180048fd8`
- `0x180049000`
- `0x180049014`
- `0x180049030`
- `0x180049dd8`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180048a56`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180048a56`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180048ac8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180048ac8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180048937`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180048937`

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
    ModuleName = wil::details::g_pfnGetModuleName(v25);
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
      : (v28 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v25) == 0),
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
      wil::details::g_pfnDebugBreak(v25);
  }
}

```

## disassembly

```asm
0x180048814  mov     [rsp+arg_10], rbx
0x180048819  mov     [rsp+arg_8], edx
0x18004881d  mov     [rsp+arg_0], rcx
0x180048822  push    rbp
0x180048823  push    rsi
0x180048824  push    rdi
0x180048825  push    r12
0x180048827  push    r13
0x180048829  push    r14
0x18004882b  push    r15
0x18004882d  sub     rsp, 40h
0x180048831  mov     r14, [rsp+78h+arg_38]
0x180048839  xor     eax, eax
0x18004883b  mov     rbx, [rsp+78h+arg_78]
0x180048843  xor     ebp, ebp
0x180048845  mov     r15d, [rsp+78h+arg_30]
0x18004884d  mov     r10, rcx
0x180048850  mov     rsi, [rsp+78h+lpOutputString]
0x180048858  mov     r12, r9
0x18004885b  mov     r13, r8
0x18004885e  mov     ecx, r15d
0x180048861  mov     [rsi], ax
0x180048864  mov     rax, [rsp+78h+arg_60]
0x18004886c  mov     byte ptr [rax], 0
0x18004886f  mov     edi, [r14]
0x180048872  mov     [rbx+8], edi
0x180048875  mov     eax, [r14+4]
0x180048879  mov     [rbx+0Ch], eax
0x18004887c  test    r15d, r15d
0x18004887f  jz      short loc_1800488E7
0x180048881  sub     ecx, 1
0x180048884  jz      short loc_1800488DE
0x180048886  sub     ecx, 1
0x180048889  jz      short loc_180048899
0x18004888b  cmp     ecx, 1
0x18004888e  jnz     short loc_1800488F0
0x180048890  mov     ecx, edi; this
0x180048892  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180048897  jmp     short loc_1800488EE
0x180048899  test    edi, edi
0x18004889b  js      short loc_1800488D5
0x18004889d  mov     rax, [rsp+78h+arg_28]
0x1800488a5  mov     edi, 8007029Ch
0x1800488aa  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800488ae  mov     rcx, r10; int
0x1800488b1  mov     [rsp+78h+var_50], rax; __int64
0x1800488b6  mov     rax, [rsp+78h+arg_20]
0x1800488be  mov     [rsp+78h+var_58], rax; __int64
0x1800488c3  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800488c8  mov     ecx, edi; this
0x1800488ca  mov     [rbx+8], edi
0x1800488cd  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800488d2  mov     [rbx+0Ch], eax
0x1800488d5  mov     ecx, edi; this
0x1800488d7  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800488dc  jmp     short loc_1800488EE
0x1800488de  mov     ecx, edi; this
0x1800488e0  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800488e5  jmp     short loc_1800488EE
0x1800488e7  mov     ecx, edi; this
0x1800488e9  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800488ee  mov     ebp, eax
0x1800488f0  mov     eax, [rsp+78h+arg_70]
0x1800488f7  mov     [rbx+4], eax
0x1800488fa  mov     [rbx], r15d
0x1800488fd  cmp     dword ptr [r14+8], 1
0x180048902  jnz     short loc_18004890A
0x180048904  or      eax, 8
0x180048907  mov     [rbx+4], eax
0x18004890a  mov     eax, 1
0x18004890f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180048917  inc     eax
0x180048919  xor     edi, edi
0x18004891b  mov     [rbx+10h], eax
0x18004891e  mov     rax, [rsp+78h+arg_40]
0x180048926  test    rax, rax
0x180048929  jz      short loc_180048930
0x18004892b  cmp     [rax], di
0x18004892e  jnz     short loc_180048933
0x180048930  mov     rax, rdi
0x180048933  mov     [rbx+18h], rax
0x180048937  call    cs:__imp_GetCurrentThreadId
0x18004893d  mov     [rbx+38h], r13
0x180048941  xorps   xmm0, xmm0
0x180048944  mov     [rbx+20h], eax
0x180048947  mov     eax, [rsp+78h+arg_8]
0x18004894e  mov     [rbx+40h], eax
0x180048951  mov     rax, [rsp+78h+arg_20]
0x180048959  mov     [rbx+28h], rax
0x18004895d  mov     rax, [rsp+78h+arg_28]
0x180048965  mov     [rbx+88h], rax
0x18004896c  mov     rax, [rsp+78h+arg_0]
0x180048974  mov     [rbx+90h], rax
0x18004897b  xor     eax, eax
0x18004897d  mov     [rbx+44h], ebp
0x180048980  mov     [rbx+30h], r12
0x180048984  mov     [rbx+48h], rdi
0x180048988  movups  xmmword ptr [rbx+68h], xmm0
0x18004898c  mov     [rbx+78h], rax
0x180048990  movups  xmmword ptr [rbx+50h], xmm0
0x180048994  mov     [rbx+60h], rax
0x180048998  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18004899f  test    rax, rax
0x1800489a2  jz      short loc_1800489AB
0x1800489a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800489a9  jmp     short loc_1800489AE
0x1800489ab  mov     rax, rdi
0x1800489ae  mov     [rbx+80h], rax
0x1800489b5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800489bc  test    rax, rax
0x1800489bf  jz      short loc_1800489C9
0x1800489c1  mov     rcx, rbx
0x1800489c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800489c9  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800489d0  test    rax, rax
0x1800489d3  jz      short loc_1800489EB
0x1800489d5  mov     rdx, [rsp+78h+arg_60]
0x1800489dd  mov     r8d, 400h
0x1800489e3  mov     rcx, rbx
0x1800489e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800489eb  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800489f2  test    rax, rax
0x1800489f5  jz      short loc_1800489FF
0x1800489f7  mov     rcx, rbx
0x1800489fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800489ff  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180048a06  test    rax, rax
0x180048a09  jz      short loc_180048A19
0x180048a0b  test    byte ptr [rbx+4], 2
0x180048a0f  jnz     short loc_180048A19
0x180048a11  mov     rcx, rbx
0x180048a14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048a19  cmp     [rbx+8], edi
0x180048a1c  jl      short loc_180048A38
0x180048a1e  cmp     r15d, 3
0x180048a22  jnz     loc_180048B06
0x180048a28  mov     ecx, 8000FFFFh; this
0x180048a2d  mov     [rbx+8], ecx
0x180048a30  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180048a35  mov     [rbx+0Ch], eax
0x180048a38  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180048a3f  jnz     short loc_180048A60
0x180048a41  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180048a48  test    rax, rax
0x180048a4b  jz      short loc_180048A56
0x180048a4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048a52  test    al, al
0x180048a54  jmp     short loc_180048A5E
0x180048a56  call    cs:__imp_IsDebuggerPresent
0x180048a5c  test    eax, eax
0x180048a5e  jz      short loc_180048A66
0x180048a60  test    byte ptr [rbx+4], 2
0x180048a64  jz      short loc_180048A8A
0x180048a66  mov     rax, cs:g_pfnResultLoggingCallback
0x180048a6d  test    rax, rax
0x180048a70  jz      short loc_180048ACE
0x180048a72  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180048a79  jnz     short loc_180048ACE
0x180048a7b  xor     r8d, r8d
0x180048a7e  xor     edx, edx
0x180048a80  mov     rcx, rbx
0x180048a83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048a88  jmp     short loc_180048ACE
0x180048a8a  mov     rax, cs:g_pfnResultLoggingCallback
0x180048a91  mov     ebp, 800h
0x180048a96  test    rax, rax
0x180048a99  jz      short loc_180048AB2
0x180048a9b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180048aa2  jnz     short loc_180048AB2
0x180048aa4  mov     r8d, ebp
0x180048aa7  mov     rdx, rsi
0x180048aaa  mov     rcx, rbx
0x180048aad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048ab2  cmp     [rsi], di
0x180048ab5  jnz     short loc_180048AC5
0x180048ab7  mov     r8, rbx; unsigned __int64
0x180048aba  mov     rdx, rbp; unsigned __int16 *
0x180048abd  mov     rcx, rsi; this
0x180048ac0  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180048ac5  mov     rcx, rsi; lpOutputString
0x180048ac8  call    cs:__imp_OutputDebugStringW
0x180048ace  test    byte ptr [rbx+4], 4
0x180048ad2  jnz     short loc_180048ADD
0x180048ad4  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180048adb  jz      short loc_180048AEE
0x180048add  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180048ae4  test    rax, rax
0x180048ae7  jz      short loc_180048AEE
0x180048ae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048aee  mov     rbx, [rsp+78h+arg_10]
0x180048af6  add     rsp, 40h
0x180048afa  pop     r15
0x180048afc  pop     r14
0x180048afe  pop     r13
0x180048b00  pop     r12
0x180048b02  pop     rdi
0x180048b03  pop     rsi
0x180048b04  pop     rbp
0x180048b05  retn
0x180048b06  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
