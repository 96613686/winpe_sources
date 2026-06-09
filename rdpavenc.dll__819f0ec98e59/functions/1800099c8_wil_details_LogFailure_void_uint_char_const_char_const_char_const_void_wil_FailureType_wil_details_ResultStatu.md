# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800099c8`
- end: `0x180009cc1`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180007d08`

## callees

- `0x180007714`
- `0x180009064`
- `0x180009804`
- `0x1800099c8`
- `0x180009e30`
- `0x180009e50`
- `0x180009e64`
- `0x180009e80`
- `0x18000b06c`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009aeb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009aeb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009c7c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009c7c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180009c0a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180009c0a`

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
      g_pfnResultLoggingCallback(a16, 0, 0, v25);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048, v25);
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
0x1800099c8  mov     [rsp+arg_10], rbx
0x1800099cd  mov     [rsp+arg_8], edx
0x1800099d1  mov     [rsp+arg_0], rcx
0x1800099d6  push    rbp
0x1800099d7  push    rsi
0x1800099d8  push    rdi
0x1800099d9  push    r12
0x1800099db  push    r13
0x1800099dd  push    r14
0x1800099df  push    r15
0x1800099e1  sub     rsp, 40h
0x1800099e5  mov     r12, r9
0x1800099e8  mov     r13, r8
0x1800099eb  mov     r10, rcx
0x1800099ee  xor     eax, eax
0x1800099f0  mov     rsi, [rsp+78h+lpOutputString]
0x1800099f8  mov     [rsi], ax
0x1800099fb  mov     rax, [rsp+78h+arg_60]
0x180009a03  mov     byte ptr [rax], 0
0x180009a06  mov     r14, [rsp+78h+arg_38]
0x180009a0e  mov     edi, [r14]
0x180009a11  mov     rbx, [rsp+78h+arg_78]
0x180009a19  mov     [rbx+8], edi
0x180009a1c  mov     eax, [r14+4]
0x180009a20  mov     [rbx+0Ch], eax
0x180009a23  xor     ebp, ebp
0x180009a25  mov     r15d, [rsp+78h+arg_30]
0x180009a2d  mov     ecx, r15d
0x180009a30  test    r15d, r15d
0x180009a33  jz      short loc_180009A9B
0x180009a35  sub     ecx, 1
0x180009a38  jz      short loc_180009A92
0x180009a3a  sub     ecx, 1
0x180009a3d  jz      short loc_180009A4D
0x180009a3f  cmp     ecx, 1
0x180009a42  jnz     short loc_180009AA4
0x180009a44  mov     ecx, edi; this
0x180009a46  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180009a4b  jmp     short loc_180009AA2
0x180009a4d  test    edi, edi
0x180009a4f  js      short loc_180009A89
0x180009a51  mov     edi, 8007029Ch
0x180009a56  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180009a5a  mov     rax, [rsp+78h+arg_28]
0x180009a62  mov     [rsp+78h+var_50], rax; __int64
0x180009a67  mov     rax, [rsp+78h+arg_20]
0x180009a6f  mov     [rsp+78h+var_58], rax; __int64
0x180009a74  mov     rcx, r10; int
0x180009a77  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180009a7c  mov     [rbx+8], edi
0x180009a7f  mov     ecx, edi; this
0x180009a81  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180009a86  mov     [rbx+0Ch], eax
0x180009a89  mov     ecx, edi; this
0x180009a8b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180009a90  jmp     short loc_180009AA2
0x180009a92  mov     ecx, edi; this
0x180009a94  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180009a99  jmp     short loc_180009AA2
0x180009a9b  mov     ecx, edi; this
0x180009a9d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180009aa2  mov     ebp, eax
0x180009aa4  mov     [rbx], r15d
0x180009aa7  mov     eax, [rsp+78h+arg_70]
0x180009aae  mov     [rbx+4], eax
0x180009ab1  cmp     dword ptr [r14+8], 1
0x180009ab6  jnz     short loc_180009ABE
0x180009ab8  or      eax, 8
0x180009abb  mov     [rbx+4], eax
0x180009abe  mov     eax, 1
0x180009ac3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180009acb  inc     eax
0x180009acd  mov     [rbx+10h], eax
0x180009ad0  mov     rax, [rsp+78h+arg_40]
0x180009ad8  xor     edi, edi
0x180009ada  test    rax, rax
0x180009add  jz      short loc_180009AE4
0x180009adf  cmp     [rax], di
0x180009ae2  jnz     short loc_180009AE7
0x180009ae4  mov     rax, rdi
0x180009ae7  mov     [rbx+18h], rax
0x180009aeb  call    cs:__imp_GetCurrentThreadId
0x180009af1  mov     [rbx+20h], eax
0x180009af4  mov     [rbx+38h], r13
0x180009af8  mov     eax, [rsp+78h+arg_8]
0x180009aff  mov     [rbx+40h], eax
0x180009b02  mov     [rbx+44h], ebp
0x180009b05  mov     rax, [rsp+78h+arg_20]
0x180009b0d  mov     [rbx+28h], rax
0x180009b11  mov     [rbx+30h], r12
0x180009b15  mov     rax, [rsp+78h+arg_28]
0x180009b1d  mov     [rbx+88h], rax
0x180009b24  mov     rax, [rsp+78h+arg_0]
0x180009b2c  mov     [rbx+90h], rax
0x180009b33  mov     [rbx+48h], rdi
0x180009b37  xorps   xmm0, xmm0
0x180009b3a  xor     eax, eax
0x180009b3c  movups  xmmword ptr [rbx+68h], xmm0
0x180009b40  mov     [rbx+78h], rax
0x180009b44  movups  xmmword ptr [rbx+50h], xmm0
0x180009b48  mov     [rbx+60h], rax
0x180009b4c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180009b53  test    rax, rax
0x180009b56  jz      short loc_180009B5F
0x180009b58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b5d  jmp     short loc_180009B62
0x180009b5f  mov     rax, rdi
0x180009b62  mov     [rbx+80h], rax
0x180009b69  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180009b70  test    rax, rax
0x180009b73  jz      short loc_180009B7D
0x180009b75  mov     rcx, rbx
0x180009b78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b7d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180009b84  test    rax, rax
0x180009b87  jz      short loc_180009B9F
0x180009b89  mov     r8d, 400h
0x180009b8f  mov     rdx, [rsp+78h+arg_60]
0x180009b97  mov     rcx, rbx
0x180009b9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b9f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180009ba6  test    rax, rax
0x180009ba9  jz      short loc_180009BB3
0x180009bab  mov     rcx, rbx
0x180009bae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bb3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180009bba  test    rax, rax
0x180009bbd  jz      short loc_180009BCD
0x180009bbf  test    byte ptr [rbx+4], 2
0x180009bc3  jnz     short loc_180009BCD
0x180009bc5  mov     rcx, rbx
0x180009bc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bcd  cmp     [rbx+8], edi
0x180009bd0  jl      short loc_180009BEC
0x180009bd2  cmp     r15d, 3
0x180009bd6  jnz     loc_180009CBB
0x180009bdc  mov     ecx, 8000FFFFh; this
0x180009be1  mov     [rbx+8], ecx
0x180009be4  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180009be9  mov     [rbx+0Ch], eax
0x180009bec  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180009bf3  jnz     short loc_180009C14
0x180009bf5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180009bfc  test    rax, rax
0x180009bff  jz      short loc_180009C0A
0x180009c01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c06  test    al, al
0x180009c08  jmp     short loc_180009C12
0x180009c0a  call    cs:__imp_IsDebuggerPresent
0x180009c10  test    eax, eax
0x180009c12  jz      short loc_180009C1A
0x180009c14  test    byte ptr [rbx+4], 2
0x180009c18  jz      short loc_180009C3E
0x180009c1a  mov     rax, cs:g_pfnResultLoggingCallback
0x180009c21  test    rax, rax
0x180009c24  jz      short loc_180009C82
0x180009c26  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180009c2d  jnz     short loc_180009C82
0x180009c2f  xor     r8d, r8d
0x180009c32  xor     edx, edx
0x180009c34  mov     rcx, rbx
0x180009c37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c3c  jmp     short loc_180009C82
0x180009c3e  mov     ebp, 800h
0x180009c43  mov     rax, cs:g_pfnResultLoggingCallback
0x180009c4a  test    rax, rax
0x180009c4d  jz      short loc_180009C66
0x180009c4f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180009c56  jnz     short loc_180009C66
0x180009c58  mov     r8d, ebp
0x180009c5b  mov     rdx, rsi
0x180009c5e  mov     rcx, rbx
0x180009c61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c66  cmp     [rsi], di
0x180009c69  jnz     short loc_180009C79
0x180009c6b  mov     r8, rbx; unsigned __int64
0x180009c6e  mov     rdx, rbp; unsigned __int16 *
0x180009c71  mov     rcx, rsi; this
0x180009c74  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180009c79  mov     rcx, rsi; lpOutputString
0x180009c7c  call    cs:__imp_OutputDebugStringW
0x180009c82  test    byte ptr [rbx+4], 4
0x180009c86  jnz     short loc_180009C91
0x180009c88  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180009c8f  jz      short loc_180009CA3
0x180009c91  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180009c98  test    rax, rax
0x180009c9b  jz      short loc_180009CA3
0x180009c9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ca2  nop
0x180009ca3  mov     rbx, [rsp+78h+arg_10]
0x180009cab  add     rsp, 40h
0x180009caf  pop     r15
0x180009cb1  pop     r14
0x180009cb3  pop     r13
0x180009cb5  pop     r12
0x180009cb7  pop     rdi
0x180009cb8  pop     rsi
0x180009cb9  pop     rbp
0x180009cba  retn
0x180009cbb  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
