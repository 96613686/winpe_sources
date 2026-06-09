# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180013b4c`
- end: `0x180013e44`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180011954`
- `0x180011ca0`

## callees

- `0x180011894`
- `0x180012f24`
- `0x180013760`
- `0x180013b4c`
- `0x180014370`
- `0x180014390`
- `0x180014400`
- `0x18001441c`
- `0x180015754`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013c6f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013c6f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180013d8e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180013d8e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180013e00`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180013e00`

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
  _WORD *v21; // rax
  DWORD CurrentThreadId; // eax
  wil::details::in1diag3 *v23; // rcx
  const struct wil::FailureInfo *v24; // r9
  __int64 ModuleName; // rax
  bool v26; // zf
  wil::details *v27; // [rsp+30h] [rbp-48h]

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
          LODWORD(v27) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v27);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL);
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
  v21 = a9;
  if ( !a9 || !*a9 )
    v21 = 0;
  *(_QWORD *)(a16 + 24) = v21;
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
    ModuleName = wil::details::g_pfnGetModuleName(v23);
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v23);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v26 = !IsDebuggerPresent())
      : (v26 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v23) == 0),
        v26)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v24);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v23);
  }
}

```

## disassembly

```asm
0x180013b4c  mov     [rsp+arg_10], rbx
0x180013b51  mov     [rsp+arg_8], edx
0x180013b55  mov     [rsp+arg_0], rcx
0x180013b5a  push    rbp
0x180013b5b  push    rsi
0x180013b5c  push    rdi
0x180013b5d  push    r12
0x180013b5f  push    r13
0x180013b61  push    r14
0x180013b63  push    r15
0x180013b65  sub     rsp, 40h
0x180013b69  mov     r14, [rsp+78h+arg_38]
0x180013b71  xor     eax, eax
0x180013b73  mov     rbx, [rsp+78h+arg_78]
0x180013b7b  xor     ebp, ebp
0x180013b7d  mov     r15d, [rsp+78h+arg_30]
0x180013b85  mov     r10, rcx
0x180013b88  mov     rsi, [rsp+78h+lpOutputString]
0x180013b90  mov     r12, r9
0x180013b93  mov     r13, r8
0x180013b96  mov     ecx, r15d
0x180013b99  mov     [rsi], ax
0x180013b9c  mov     rax, [rsp+78h+arg_60]
0x180013ba4  mov     byte ptr [rax], 0
0x180013ba7  mov     edi, [r14]
0x180013baa  mov     [rbx+8], edi
0x180013bad  mov     eax, [r14+4]
0x180013bb1  mov     [rbx+0Ch], eax
0x180013bb4  test    r15d, r15d
0x180013bb7  jz      short loc_180013C1F
0x180013bb9  sub     ecx, 1
0x180013bbc  jz      short loc_180013C16
0x180013bbe  sub     ecx, 1
0x180013bc1  jz      short loc_180013BD1
0x180013bc3  cmp     ecx, 1
0x180013bc6  jnz     short loc_180013C28
0x180013bc8  mov     ecx, edi; this
0x180013bca  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180013bcf  jmp     short loc_180013C26
0x180013bd1  test    edi, edi
0x180013bd3  js      short loc_180013C0D
0x180013bd5  mov     rax, [rsp+78h+arg_28]
0x180013bdd  mov     edi, 8007029Ch
0x180013be2  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180013be6  mov     rcx, r10; int
0x180013be9  mov     [rsp+78h+var_50], rax; __int64
0x180013bee  mov     rax, [rsp+78h+arg_20]
0x180013bf6  mov     [rsp+78h+var_58], rax; __int64
0x180013bfb  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180013c00  mov     ecx, edi; this
0x180013c02  mov     [rbx+8], edi
0x180013c05  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180013c0a  mov     [rbx+0Ch], eax
0x180013c0d  mov     ecx, edi; this
0x180013c0f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180013c14  jmp     short loc_180013C26
0x180013c16  mov     ecx, edi; this
0x180013c18  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180013c1d  jmp     short loc_180013C26
0x180013c1f  mov     ecx, edi; this
0x180013c21  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180013c26  mov     ebp, eax
0x180013c28  mov     eax, [rsp+78h+arg_70]
0x180013c2f  mov     [rbx+4], eax
0x180013c32  mov     [rbx], r15d
0x180013c35  cmp     dword ptr [r14+8], 1
0x180013c3a  jnz     short loc_180013C42
0x180013c3c  or      eax, 8
0x180013c3f  mov     [rbx+4], eax
0x180013c42  mov     eax, 1
0x180013c47  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180013c4f  inc     eax
0x180013c51  xor     edi, edi
0x180013c53  mov     [rbx+10h], eax
0x180013c56  mov     rax, [rsp+78h+arg_40]
0x180013c5e  test    rax, rax
0x180013c61  jz      short loc_180013C68
0x180013c63  cmp     [rax], di
0x180013c66  jnz     short loc_180013C6B
0x180013c68  mov     rax, rdi
0x180013c6b  mov     [rbx+18h], rax
0x180013c6f  call    cs:__imp_GetCurrentThreadId
0x180013c75  mov     [rbx+38h], r13
0x180013c79  xorps   xmm0, xmm0
0x180013c7c  mov     [rbx+20h], eax
0x180013c7f  mov     eax, [rsp+78h+arg_8]
0x180013c86  mov     [rbx+40h], eax
0x180013c89  mov     rax, [rsp+78h+arg_20]
0x180013c91  mov     [rbx+28h], rax
0x180013c95  mov     rax, [rsp+78h+arg_28]
0x180013c9d  mov     [rbx+88h], rax
0x180013ca4  mov     rax, [rsp+78h+arg_0]
0x180013cac  mov     [rbx+90h], rax
0x180013cb3  xor     eax, eax
0x180013cb5  mov     [rbx+44h], ebp
0x180013cb8  mov     [rbx+30h], r12
0x180013cbc  mov     [rbx+48h], rdi
0x180013cc0  movups  xmmword ptr [rbx+68h], xmm0
0x180013cc4  mov     [rbx+78h], rax
0x180013cc8  movups  xmmword ptr [rbx+50h], xmm0
0x180013ccc  mov     [rbx+60h], rax
0x180013cd0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180013cd7  test    rax, rax
0x180013cda  jz      short loc_180013CE3
0x180013cdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ce1  jmp     short loc_180013CE6
0x180013ce3  mov     rax, rdi
0x180013ce6  mov     [rbx+80h], rax
0x180013ced  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180013cf4  test    rax, rax
0x180013cf7  jz      short loc_180013D01
0x180013cf9  mov     rcx, rbx
0x180013cfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d01  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180013d08  test    rax, rax
0x180013d0b  jz      short loc_180013D23
0x180013d0d  mov     rdx, [rsp+78h+arg_60]
0x180013d15  mov     r8d, 400h
0x180013d1b  mov     rcx, rbx
0x180013d1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d23  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180013d2a  test    rax, rax
0x180013d2d  jz      short loc_180013D37
0x180013d2f  mov     rcx, rbx
0x180013d32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d37  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180013d3e  test    rax, rax
0x180013d41  jz      short loc_180013D51
0x180013d43  test    byte ptr [rbx+4], 2
0x180013d47  jnz     short loc_180013D51
0x180013d49  mov     rcx, rbx
0x180013d4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d51  cmp     [rbx+8], edi
0x180013d54  jl      short loc_180013D70
0x180013d56  cmp     r15d, 3
0x180013d5a  jnz     loc_180013E3E
0x180013d60  mov     ecx, 8000FFFFh; this
0x180013d65  mov     [rbx+8], ecx
0x180013d68  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180013d6d  mov     [rbx+0Ch], eax
0x180013d70  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180013d77  jnz     short loc_180013D98
0x180013d79  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180013d80  test    rax, rax
0x180013d83  jz      short loc_180013D8E
0x180013d85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d8a  test    al, al
0x180013d8c  jmp     short loc_180013D96
0x180013d8e  call    cs:__imp_IsDebuggerPresent
0x180013d94  test    eax, eax
0x180013d96  jz      short loc_180013D9E
0x180013d98  test    byte ptr [rbx+4], 2
0x180013d9c  jz      short loc_180013DC2
0x180013d9e  mov     rax, cs:g_pfnResultLoggingCallback
0x180013da5  test    rax, rax
0x180013da8  jz      short loc_180013E06
0x180013daa  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180013db1  jnz     short loc_180013E06
0x180013db3  xor     r8d, r8d
0x180013db6  xor     edx, edx
0x180013db8  mov     rcx, rbx
0x180013dbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013dc0  jmp     short loc_180013E06
0x180013dc2  mov     rax, cs:g_pfnResultLoggingCallback
0x180013dc9  mov     ebp, 800h
0x180013dce  test    rax, rax
0x180013dd1  jz      short loc_180013DEA
0x180013dd3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180013dda  jnz     short loc_180013DEA
0x180013ddc  mov     r8d, ebp
0x180013ddf  mov     rdx, rsi
0x180013de2  mov     rcx, rbx
0x180013de5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013dea  cmp     [rsi], di
0x180013ded  jnz     short loc_180013DFD
0x180013def  mov     r8, rbx; unsigned __int64
0x180013df2  mov     rdx, rbp; unsigned __int16 *
0x180013df5  mov     rcx, rsi; this
0x180013df8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180013dfd  mov     rcx, rsi; lpOutputString
0x180013e00  call    cs:__imp_OutputDebugStringW
0x180013e06  test    byte ptr [rbx+4], 4
0x180013e0a  jnz     short loc_180013E15
0x180013e0c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180013e13  jz      short loc_180013E26
0x180013e15  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180013e1c  test    rax, rax
0x180013e1f  jz      short loc_180013E26
0x180013e21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e26  mov     rbx, [rsp+78h+arg_10]
0x180013e2e  add     rsp, 40h
0x180013e32  pop     r15
0x180013e34  pop     r14
0x180013e36  pop     r13
0x180013e38  pop     r12
0x180013e3a  pop     rdi
0x180013e3b  pop     rsi
0x180013e3c  pop     rbp
0x180013e3d  retn
0x180013e3e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
