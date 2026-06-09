# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140007d88`
- end: `0x140008081`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140004404`

## callees

- `0x1400039d4`
- `0x1400070c4`
- `0x140007908`
- `0x140007d88`
- `0x14000884c`
- `0x140008870`
- `0x14000899c`
- `0x1400089b8`
- `0x14000af58`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140007eab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140007eab`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140007fca`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140007fca`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000803c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000803c`

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
0x140007d88  mov     [rsp+arg_10], rbx
0x140007d8d  mov     [rsp+arg_8], edx
0x140007d91  mov     [rsp+arg_0], rcx
0x140007d96  push    rbp
0x140007d97  push    rsi
0x140007d98  push    rdi
0x140007d99  push    r12
0x140007d9b  push    r13
0x140007d9d  push    r14
0x140007d9f  push    r15
0x140007da1  sub     rsp, 40h
0x140007da5  mov     r12, r9
0x140007da8  mov     r13, r8
0x140007dab  mov     r10, rcx
0x140007dae  xor     eax, eax
0x140007db0  mov     rsi, [rsp+78h+lpOutputString]
0x140007db8  mov     [rsi], ax
0x140007dbb  mov     rax, [rsp+78h+arg_60]
0x140007dc3  mov     byte ptr [rax], 0
0x140007dc6  mov     r14, [rsp+78h+arg_38]
0x140007dce  mov     edi, [r14]
0x140007dd1  mov     rbx, [rsp+78h+arg_78]
0x140007dd9  mov     [rbx+8], edi
0x140007ddc  mov     eax, [r14+4]
0x140007de0  mov     [rbx+0Ch], eax
0x140007de3  xor     ebp, ebp
0x140007de5  mov     r15d, [rsp+78h+arg_30]
0x140007ded  mov     ecx, r15d
0x140007df0  test    r15d, r15d
0x140007df3  jz      short loc_140007E5B
0x140007df5  sub     ecx, 1
0x140007df8  jz      short loc_140007E52
0x140007dfa  sub     ecx, 1
0x140007dfd  jz      short loc_140007E0D
0x140007dff  cmp     ecx, 1
0x140007e02  jnz     short loc_140007E64
0x140007e04  mov     ecx, edi; this
0x140007e06  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140007e0b  jmp     short loc_140007E62
0x140007e0d  test    edi, edi
0x140007e0f  js      short loc_140007E49
0x140007e11  mov     edi, 8007029Ch
0x140007e16  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x140007e1a  mov     rax, [rsp+78h+arg_28]
0x140007e22  mov     [rsp+78h+var_50], rax; __int64
0x140007e27  mov     rax, [rsp+78h+arg_20]
0x140007e2f  mov     [rsp+78h+var_58], rax; __int64
0x140007e34  mov     rcx, r10; int
0x140007e37  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140007e3c  mov     [rbx+8], edi
0x140007e3f  mov     ecx, edi; this
0x140007e41  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140007e46  mov     [rbx+0Ch], eax
0x140007e49  mov     ecx, edi; this
0x140007e4b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140007e50  jmp     short loc_140007E62
0x140007e52  mov     ecx, edi; this
0x140007e54  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140007e59  jmp     short loc_140007E62
0x140007e5b  mov     ecx, edi; this
0x140007e5d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140007e62  mov     ebp, eax
0x140007e64  mov     [rbx], r15d
0x140007e67  mov     eax, [rsp+78h+arg_70]
0x140007e6e  mov     [rbx+4], eax
0x140007e71  cmp     dword ptr [r14+8], 1
0x140007e76  jnz     short loc_140007E7E
0x140007e78  or      eax, 8
0x140007e7b  mov     [rbx+4], eax
0x140007e7e  mov     eax, 1
0x140007e83  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140007e8b  inc     eax
0x140007e8d  mov     [rbx+10h], eax
0x140007e90  mov     rax, [rsp+78h+arg_40]
0x140007e98  xor     edi, edi
0x140007e9a  test    rax, rax
0x140007e9d  jz      short loc_140007EA4
0x140007e9f  cmp     [rax], di
0x140007ea2  jnz     short loc_140007EA7
0x140007ea4  mov     rax, rdi
0x140007ea7  mov     [rbx+18h], rax
0x140007eab  call    cs:__imp_GetCurrentThreadId
0x140007eb1  mov     [rbx+20h], eax
0x140007eb4  mov     [rbx+38h], r13
0x140007eb8  mov     eax, [rsp+78h+arg_8]
0x140007ebf  mov     [rbx+40h], eax
0x140007ec2  mov     [rbx+44h], ebp
0x140007ec5  mov     rax, [rsp+78h+arg_20]
0x140007ecd  mov     [rbx+28h], rax
0x140007ed1  mov     [rbx+30h], r12
0x140007ed5  mov     rax, [rsp+78h+arg_28]
0x140007edd  mov     [rbx+88h], rax
0x140007ee4  mov     rax, [rsp+78h+arg_0]
0x140007eec  mov     [rbx+90h], rax
0x140007ef3  mov     [rbx+48h], rdi
0x140007ef7  xorps   xmm0, xmm0
0x140007efa  xor     eax, eax
0x140007efc  movups  xmmword ptr [rbx+68h], xmm0
0x140007f00  mov     [rbx+78h], rax
0x140007f04  movups  xmmword ptr [rbx+50h], xmm0
0x140007f08  mov     [rbx+60h], rax
0x140007f0c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140007f13  test    rax, rax
0x140007f16  jz      short loc_140007F1F
0x140007f18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007f1d  jmp     short loc_140007F22
0x140007f1f  mov     rax, rdi
0x140007f22  mov     [rbx+80h], rax
0x140007f29  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140007f30  test    rax, rax
0x140007f33  jz      short loc_140007F3D
0x140007f35  mov     rcx, rbx
0x140007f38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007f3d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140007f44  test    rax, rax
0x140007f47  jz      short loc_140007F5F
0x140007f49  mov     r8d, 400h
0x140007f4f  mov     rdx, [rsp+78h+arg_60]
0x140007f57  mov     rcx, rbx
0x140007f5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007f5f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140007f66  test    rax, rax
0x140007f69  jz      short loc_140007F73
0x140007f6b  mov     rcx, rbx
0x140007f6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007f73  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140007f7a  test    rax, rax
0x140007f7d  jz      short loc_140007F8D
0x140007f7f  test    byte ptr [rbx+4], 2
0x140007f83  jnz     short loc_140007F8D
0x140007f85  mov     rcx, rbx
0x140007f88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007f8d  cmp     [rbx+8], edi
0x140007f90  jl      short loc_140007FAC
0x140007f92  cmp     r15d, 3
0x140007f96  jnz     loc_14000807B
0x140007f9c  mov     ecx, 8000FFFFh; this
0x140007fa1  mov     [rbx+8], ecx
0x140007fa4  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140007fa9  mov     [rbx+0Ch], eax
0x140007fac  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x140007fb3  jnz     short loc_140007FD4
0x140007fb5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140007fbc  test    rax, rax
0x140007fbf  jz      short loc_140007FCA
0x140007fc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007fc6  test    al, al
0x140007fc8  jmp     short loc_140007FD2
0x140007fca  call    cs:__imp_IsDebuggerPresent
0x140007fd0  test    eax, eax
0x140007fd2  jz      short loc_140007FDA
0x140007fd4  test    byte ptr [rbx+4], 2
0x140007fd8  jz      short loc_140007FFE
0x140007fda  mov     rax, cs:g_pfnResultLoggingCallback
0x140007fe1  test    rax, rax
0x140007fe4  jz      short loc_140008042
0x140007fe6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140007fed  jnz     short loc_140008042
0x140007fef  xor     r8d, r8d
0x140007ff2  xor     edx, edx
0x140007ff4  mov     rcx, rbx
0x140007ff7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007ffc  jmp     short loc_140008042
0x140007ffe  mov     ebp, 800h
0x140008003  mov     rax, cs:g_pfnResultLoggingCallback
0x14000800a  test    rax, rax
0x14000800d  jz      short loc_140008026
0x14000800f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140008016  jnz     short loc_140008026
0x140008018  mov     r8d, ebp
0x14000801b  mov     rdx, rsi
0x14000801e  mov     rcx, rbx
0x140008021  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008026  cmp     [rsi], di
0x140008029  jnz     short loc_140008039
0x14000802b  mov     r8, rbx; unsigned __int64
0x14000802e  mov     rdx, rbp; unsigned __int16 *
0x140008031  mov     rcx, rsi; this
0x140008034  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140008039  mov     rcx, rsi; lpOutputString
0x14000803c  call    cs:__imp_OutputDebugStringW
0x140008042  test    byte ptr [rbx+4], 4
0x140008046  jnz     short loc_140008051
0x140008048  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x14000804f  jz      short loc_140008063
0x140008051  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140008058  test    rax, rax
0x14000805b  jz      short loc_140008063
0x14000805d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008062  nop
0x140008063  mov     rbx, [rsp+78h+arg_10]
0x14000806b  add     rsp, 40h
0x14000806f  pop     r15
0x140008071  pop     r14
0x140008073  pop     r13
0x140008075  pop     r12
0x140008077  pop     rdi
0x140008078  pop     rsi
0x140008079  pop     rbp
0x14000807a  retn
0x14000807b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
