# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800078c8`
- end: `0x180007bd4`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `780`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180004bb4`

## callees

- `0x18000451c`
- `0x180006d44`
- `0x180007600`
- `0x1800078c8`
- `0x1800087e4`
- `0x180008810`
- `0x180008958`
- `0x180008978`
- `0x18000b59c`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800079eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800079eb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007b88`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007b88`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007b10`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007b10`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  _WORD *v21; // rax
  wil::details::in1diag3 *v22; // rcx
  const struct wil::FailureInfo *v23; // r9
  __int64 ModuleName; // rax
  bool v25; // zf
  wil::details *v26; // [rsp+30h] [rbp-48h]

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
          LODWORD(v26) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v26);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL);
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
  v21 = a9;
  if ( !a9 || !*a9 )
    v21 = 0;
  *(_QWORD *)(a16 + 24) = v21;
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
    ModuleName = wil::details::g_pfnGetModuleName(v22);
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v25 = !IsDebuggerPresent())
      : (v25 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v22) == 0),
        v25)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v23);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v22);
  }
}

```

## disassembly

```asm
0x1800078c8  mov     [rsp+arg_10], rbx
0x1800078cd  mov     [rsp+arg_8], edx
0x1800078d1  mov     [rsp+arg_0], rcx
0x1800078d6  push    rbp
0x1800078d7  push    rsi
0x1800078d8  push    rdi
0x1800078d9  push    r12
0x1800078db  push    r13
0x1800078dd  push    r14
0x1800078df  push    r15
0x1800078e1  sub     rsp, 40h
0x1800078e5  mov     r12, r9
0x1800078e8  mov     r13, r8
0x1800078eb  mov     r10, rcx
0x1800078ee  xor     eax, eax
0x1800078f0  mov     rsi, [rsp+78h+lpOutputString]
0x1800078f8  mov     [rsi], ax
0x1800078fb  mov     rax, [rsp+78h+arg_60]
0x180007903  mov     byte ptr [rax], 0
0x180007906  mov     r14, [rsp+78h+arg_38]
0x18000790e  mov     edi, [r14]
0x180007911  mov     rbx, [rsp+78h+arg_78]
0x180007919  mov     [rbx+8], edi
0x18000791c  mov     eax, [r14+4]
0x180007920  mov     [rbx+0Ch], eax
0x180007923  xor     ebp, ebp
0x180007925  mov     r15d, [rsp+78h+arg_30]
0x18000792d  mov     ecx, r15d
0x180007930  test    r15d, r15d
0x180007933  jz      short loc_18000799B
0x180007935  sub     ecx, 1
0x180007938  jz      short loc_180007992
0x18000793a  sub     ecx, 1
0x18000793d  jz      short loc_18000794D
0x18000793f  cmp     ecx, 1
0x180007942  jnz     short loc_1800079A4
0x180007944  mov     ecx, edi; this
0x180007946  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000794b  jmp     short loc_1800079A2
0x18000794d  test    edi, edi
0x18000794f  js      short loc_180007989
0x180007951  mov     edi, 8007029Ch
0x180007956  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000795a  mov     rax, [rsp+78h+arg_28]
0x180007962  mov     [rsp+78h+var_50], rax; __int64
0x180007967  mov     rax, [rsp+78h+arg_20]
0x18000796f  mov     [rsp+78h+var_58], rax; __int64
0x180007974  mov     rcx, r10; int
0x180007977  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000797c  mov     [rbx+8], edi
0x18000797f  mov     ecx, edi; this
0x180007981  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007986  mov     [rbx+0Ch], eax
0x180007989  mov     ecx, edi; this
0x18000798b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180007990  jmp     short loc_1800079A2
0x180007992  mov     ecx, edi; this
0x180007994  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180007999  jmp     short loc_1800079A2
0x18000799b  mov     ecx, edi; this
0x18000799d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800079a2  mov     ebp, eax
0x1800079a4  mov     [rbx], r15d
0x1800079a7  mov     eax, [rsp+78h+arg_70]
0x1800079ae  mov     [rbx+4], eax
0x1800079b1  cmp     dword ptr [r14+8], 1
0x1800079b6  jnz     short loc_1800079BE
0x1800079b8  or      eax, 8
0x1800079bb  mov     [rbx+4], eax
0x1800079be  mov     eax, 1
0x1800079c3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800079cb  inc     eax
0x1800079cd  mov     [rbx+10h], eax
0x1800079d0  mov     rax, [rsp+78h+arg_40]
0x1800079d8  xor     edi, edi
0x1800079da  test    rax, rax
0x1800079dd  jz      short loc_1800079E4
0x1800079df  cmp     [rax], di
0x1800079e2  jnz     short loc_1800079E7
0x1800079e4  mov     rax, rdi
0x1800079e7  mov     [rbx+18h], rax
0x1800079eb  call    cs:__imp_GetCurrentThreadId
0x1800079f2  nop     dword ptr [rax+rax+00h]
0x1800079f7  mov     [rbx+20h], eax
0x1800079fa  mov     [rbx+38h], r13
0x1800079fe  mov     eax, [rsp+78h+arg_8]
0x180007a05  mov     [rbx+40h], eax
0x180007a08  mov     [rbx+44h], ebp
0x180007a0b  mov     rax, [rsp+78h+arg_20]
0x180007a13  mov     [rbx+28h], rax
0x180007a17  mov     [rbx+30h], r12
0x180007a1b  mov     rax, [rsp+78h+arg_28]
0x180007a23  mov     [rbx+88h], rax
0x180007a2a  mov     rax, [rsp+78h+arg_0]
0x180007a32  mov     [rbx+90h], rax
0x180007a39  mov     [rbx+48h], rdi
0x180007a3d  xorps   xmm0, xmm0
0x180007a40  xor     eax, eax
0x180007a42  movups  xmmword ptr [rbx+68h], xmm0
0x180007a46  mov     [rbx+78h], rax
0x180007a4a  movups  xmmword ptr [rbx+50h], xmm0
0x180007a4e  mov     [rbx+60h], rax
0x180007a52  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180007a59  test    rax, rax
0x180007a5c  jz      short loc_180007A65
0x180007a5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a63  jmp     short loc_180007A68
0x180007a65  mov     rax, rdi
0x180007a68  mov     [rbx+80h], rax
0x180007a6f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180007a76  test    rax, rax
0x180007a79  jz      short loc_180007A83
0x180007a7b  mov     rcx, rbx
0x180007a7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a83  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180007a8a  test    rax, rax
0x180007a8d  jz      short loc_180007AA5
0x180007a8f  mov     r8d, 400h
0x180007a95  mov     rdx, [rsp+78h+arg_60]
0x180007a9d  mov     rcx, rbx
0x180007aa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007aa5  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007aac  test    rax, rax
0x180007aaf  jz      short loc_180007AB9
0x180007ab1  mov     rcx, rbx
0x180007ab4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ab9  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007ac0  test    rax, rax
0x180007ac3  jz      short loc_180007AD3
0x180007ac5  test    byte ptr [rbx+4], 2
0x180007ac9  jnz     short loc_180007AD3
0x180007acb  mov     rcx, rbx
0x180007ace  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ad3  cmp     [rbx+8], edi
0x180007ad6  jl      short loc_180007AF2
0x180007ad8  cmp     r15d, 3
0x180007adc  jnz     loc_180007BCE
0x180007ae2  mov     ecx, 8000FFFFh; this
0x180007ae7  mov     [rbx+8], ecx
0x180007aea  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007aef  mov     [rbx+0Ch], eax
0x180007af2  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180007af9  jnz     short loc_180007B20
0x180007afb  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180007b02  test    rax, rax
0x180007b05  jz      short loc_180007B10
0x180007b07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b0c  test    al, al
0x180007b0e  jmp     short loc_180007B1E
0x180007b10  call    cs:__imp_IsDebuggerPresent
0x180007b17  nop     dword ptr [rax+rax+00h]
0x180007b1c  test    eax, eax
0x180007b1e  jz      short loc_180007B26
0x180007b20  test    byte ptr [rbx+4], 2
0x180007b24  jz      short loc_180007B4A
0x180007b26  mov     rax, cs:g_pfnResultLoggingCallback
0x180007b2d  test    rax, rax
0x180007b30  jz      short loc_180007B94
0x180007b32  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180007b39  jnz     short loc_180007B94
0x180007b3b  xor     r8d, r8d
0x180007b3e  xor     edx, edx
0x180007b40  mov     rcx, rbx
0x180007b43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b48  jmp     short loc_180007B94
0x180007b4a  mov     ebp, 800h
0x180007b4f  mov     rax, cs:g_pfnResultLoggingCallback
0x180007b56  test    rax, rax
0x180007b59  jz      short loc_180007B72
0x180007b5b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180007b62  jnz     short loc_180007B72
0x180007b64  mov     r8d, ebp
0x180007b67  mov     rdx, rsi
0x180007b6a  mov     rcx, rbx
0x180007b6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b72  cmp     [rsi], di
0x180007b75  jnz     short loc_180007B85
0x180007b77  mov     r8, rbx; unsigned __int64
0x180007b7a  mov     rdx, rbp; unsigned __int16 *
0x180007b7d  mov     rcx, rsi; this
0x180007b80  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180007b85  mov     rcx, rsi; lpOutputString
0x180007b88  call    cs:__imp_OutputDebugStringW
0x180007b8f  nop     dword ptr [rax+rax+00h]
0x180007b94  test    byte ptr [rbx+4], 4
0x180007b98  jnz     short loc_180007BA3
0x180007b9a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180007ba1  jz      short loc_180007BB5
0x180007ba3  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180007baa  test    rax, rax
0x180007bad  jz      short loc_180007BB5
0x180007baf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bb4  nop
0x180007bb5  mov     rbx, [rsp+78h+arg_10]
0x180007bbd  add     rsp, 40h
0x180007bc1  pop     r15
0x180007bc3  pop     r14
0x180007bc5  pop     r13
0x180007bc7  pop     r12
0x180007bc9  pop     rdi
0x180007bca  pop     rsi
0x180007bcb  pop     rbp
0x180007bcc  retn
0x180007bce  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
