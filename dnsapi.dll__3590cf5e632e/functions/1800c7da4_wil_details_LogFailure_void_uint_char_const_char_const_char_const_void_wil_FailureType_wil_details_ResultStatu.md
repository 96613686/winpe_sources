# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800c7da4`
- end: `0x1800c80ab`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `775`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x1800c6270`
- `0x1800c6320`
- `0x1800c6418`

## callees

- `0x18008a8a0`
- `0x1800c61c4`
- `0x1800c7514`
- `0x1800c7da4`
- `0x1800c8994`
- `0x1800c89c0`
- `0x1800c8a8c`
- `0x1800c8aac`
- `0x1800c9ec0`
- `0x1800e4010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c7ec7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c7ec7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800c7fee`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800c7fee`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800c8066`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800c8066`

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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v25);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v24);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v28 = !IsDebuggerPresent())
      : (v28 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
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
      wil::details::g_pfnDebugBreak();
  }
}

```

## disassembly

```asm
0x1800c7da4  mov     [rsp+arg_10], rbx
0x1800c7da9  mov     [rsp+arg_8], edx
0x1800c7dad  mov     [rsp+arg_0], rcx
0x1800c7db2  push    rbp
0x1800c7db3  push    rsi
0x1800c7db4  push    rdi
0x1800c7db5  push    r12
0x1800c7db7  push    r13
0x1800c7db9  push    r14
0x1800c7dbb  push    r15
0x1800c7dbd  sub     rsp, 40h
0x1800c7dc1  mov     r14, [rsp+78h+arg_38]
0x1800c7dc9  xor     eax, eax
0x1800c7dcb  mov     rbx, [rsp+78h+arg_78]
0x1800c7dd3  xor     ebp, ebp
0x1800c7dd5  mov     r15d, [rsp+78h+arg_30]
0x1800c7ddd  mov     r10, rcx
0x1800c7de0  mov     rsi, [rsp+78h+lpOutputString]
0x1800c7de8  mov     r12, r9
0x1800c7deb  mov     r13, r8
0x1800c7dee  mov     ecx, r15d
0x1800c7df1  mov     [rsi], ax
0x1800c7df4  mov     rax, [rsp+78h+arg_60]
0x1800c7dfc  mov     byte ptr [rax], 0
0x1800c7dff  mov     edi, [r14]
0x1800c7e02  mov     [rbx+8], edi
0x1800c7e05  mov     eax, [r14+4]
0x1800c7e09  mov     [rbx+0Ch], eax
0x1800c7e0c  test    r15d, r15d
0x1800c7e0f  jz      short loc_1800C7E77
0x1800c7e11  sub     ecx, 1
0x1800c7e14  jz      short loc_1800C7E6E
0x1800c7e16  sub     ecx, 1
0x1800c7e19  jz      short loc_1800C7E29
0x1800c7e1b  cmp     ecx, 1
0x1800c7e1e  jnz     short loc_1800C7E80
0x1800c7e20  mov     ecx, edi; this
0x1800c7e22  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800c7e27  jmp     short loc_1800C7E7E
0x1800c7e29  test    edi, edi
0x1800c7e2b  js      short loc_1800C7E65
0x1800c7e2d  mov     rax, [rsp+78h+arg_28]
0x1800c7e35  mov     edi, 8007029Ch
0x1800c7e3a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800c7e3e  mov     rcx, r10; int
0x1800c7e41  mov     [rsp+78h+var_50], rax; __int64
0x1800c7e46  mov     rax, [rsp+78h+arg_20]
0x1800c7e4e  mov     [rsp+78h+var_58], rax; __int64
0x1800c7e53  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800c7e58  mov     ecx, edi; this
0x1800c7e5a  mov     [rbx+8], edi
0x1800c7e5d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800c7e62  mov     [rbx+0Ch], eax
0x1800c7e65  mov     ecx, edi; this
0x1800c7e67  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800c7e6c  jmp     short loc_1800C7E7E
0x1800c7e6e  mov     ecx, edi; this
0x1800c7e70  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800c7e75  jmp     short loc_1800C7E7E
0x1800c7e77  mov     ecx, edi; this
0x1800c7e79  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800c7e7e  mov     ebp, eax
0x1800c7e80  mov     eax, [rsp+78h+arg_70]
0x1800c7e87  mov     [rbx+4], eax
0x1800c7e8a  mov     [rbx], r15d
0x1800c7e8d  cmp     dword ptr [r14+8], 1
0x1800c7e92  jnz     short loc_1800C7E9A
0x1800c7e94  or      eax, 8
0x1800c7e97  mov     [rbx+4], eax
0x1800c7e9a  mov     eax, 1
0x1800c7e9f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800c7ea7  inc     eax
0x1800c7ea9  xor     edi, edi
0x1800c7eab  mov     [rbx+10h], eax
0x1800c7eae  mov     rax, [rsp+78h+arg_40]
0x1800c7eb6  test    rax, rax
0x1800c7eb9  jz      short loc_1800C7EC0
0x1800c7ebb  cmp     [rax], di
0x1800c7ebe  jnz     short loc_1800C7EC3
0x1800c7ec0  mov     rax, rdi
0x1800c7ec3  mov     [rbx+18h], rax
0x1800c7ec7  call    cs:__imp_GetCurrentThreadId
0x1800c7ece  nop     dword ptr [rax+rax+00h]
0x1800c7ed3  mov     [rbx+38h], r13
0x1800c7ed7  xorps   xmm0, xmm0
0x1800c7eda  mov     [rbx+20h], eax
0x1800c7edd  mov     eax, [rsp+78h+arg_8]
0x1800c7ee4  mov     [rbx+40h], eax
0x1800c7ee7  mov     rax, [rsp+78h+arg_20]
0x1800c7eef  mov     [rbx+28h], rax
0x1800c7ef3  mov     rax, [rsp+78h+arg_28]
0x1800c7efb  mov     [rbx+88h], rax
0x1800c7f02  mov     rax, [rsp+78h+arg_0]
0x1800c7f0a  mov     [rbx+90h], rax
0x1800c7f11  xor     eax, eax
0x1800c7f13  mov     [rbx+44h], ebp
0x1800c7f16  mov     [rbx+30h], r12
0x1800c7f1a  mov     [rbx+48h], rdi
0x1800c7f1e  movups  xmmword ptr [rbx+68h], xmm0
0x1800c7f22  mov     [rbx+78h], rax
0x1800c7f26  movups  xmmword ptr [rbx+50h], xmm0
0x1800c7f2a  mov     [rbx+60h], rax
0x1800c7f2e  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800c7f35  test    rax, rax
0x1800c7f38  jz      short loc_1800C7F41
0x1800c7f3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c7f3f  jmp     short loc_1800C7F44
0x1800c7f41  mov     rax, rdi
0x1800c7f44  mov     [rbx+80h], rax
0x1800c7f4b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800c7f52  test    rax, rax
0x1800c7f55  jz      short loc_1800C7F5F
0x1800c7f57  mov     rcx, rbx
0x1800c7f5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c7f5f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800c7f66  test    rax, rax
0x1800c7f69  jz      short loc_1800C7F81
0x1800c7f6b  mov     rdx, [rsp+78h+arg_60]
0x1800c7f73  mov     r8d, 400h
0x1800c7f79  mov     rcx, rbx
0x1800c7f7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c7f81  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800c7f88  test    rax, rax
0x1800c7f8b  jz      short loc_1800C7F95
0x1800c7f8d  mov     rcx, rbx
0x1800c7f90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c7f95  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800c7f9c  test    rax, rax
0x1800c7f9f  jz      short loc_1800C7FAF
0x1800c7fa1  test    byte ptr [rbx+4], 2
0x1800c7fa5  jnz     short loc_1800C7FAF
0x1800c7fa7  mov     rcx, rbx
0x1800c7faa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c7faf  cmp     [rbx+8], edi
0x1800c7fb2  jl      short loc_1800C7FD0
0x1800c7fb4  cmp     r15d, 3
0x1800c7fb8  jz      short loc_1800C7FC0
0x1800c7fba  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800c7fc0  mov     ecx, 8000FFFFh; this
0x1800c7fc5  mov     [rbx+8], ecx
0x1800c7fc8  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800c7fcd  mov     [rbx+0Ch], eax
0x1800c7fd0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800c7fd7  jnz     short loc_1800C7FFE
0x1800c7fd9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800c7fe0  test    rax, rax
0x1800c7fe3  jz      short loc_1800C7FEE
0x1800c7fe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c7fea  test    al, al
0x1800c7fec  jmp     short loc_1800C7FFC
0x1800c7fee  call    cs:__imp_IsDebuggerPresent
0x1800c7ff5  nop     dword ptr [rax+rax+00h]
0x1800c7ffa  test    eax, eax
0x1800c7ffc  jz      short loc_1800C8004
0x1800c7ffe  test    byte ptr [rbx+4], 2
0x1800c8002  jz      short loc_1800C8028
0x1800c8004  mov     rax, cs:g_pfnResultLoggingCallback
0x1800c800b  test    rax, rax
0x1800c800e  jz      short loc_1800C8072
0x1800c8010  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800c8017  jnz     short loc_1800C8072
0x1800c8019  xor     r8d, r8d
0x1800c801c  xor     edx, edx
0x1800c801e  mov     rcx, rbx
0x1800c8021  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8026  jmp     short loc_1800C8072
0x1800c8028  mov     rax, cs:g_pfnResultLoggingCallback
0x1800c802f  mov     ebp, 800h
0x1800c8034  test    rax, rax
0x1800c8037  jz      short loc_1800C8050
0x1800c8039  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800c8040  jnz     short loc_1800C8050
0x1800c8042  mov     r8d, ebp
0x1800c8045  mov     rdx, rsi
0x1800c8048  mov     rcx, rbx
0x1800c804b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8050  cmp     [rsi], di
0x1800c8053  jnz     short loc_1800C8063
0x1800c8055  mov     r8, rbx; unsigned __int64
0x1800c8058  mov     rdx, rbp; unsigned __int16 *
0x1800c805b  mov     rcx, rsi; this
0x1800c805e  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800c8063  mov     rcx, rsi; lpOutputString
0x1800c8066  call    cs:__imp_OutputDebugStringW
0x1800c806d  nop     dword ptr [rax+rax+00h]
0x1800c8072  test    byte ptr [rbx+4], 4
0x1800c8076  jnz     short loc_1800C8081
0x1800c8078  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800c807f  jz      short loc_1800C8092
0x1800c8081  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800c8088  test    rax, rax
0x1800c808b  jz      short loc_1800C8092
0x1800c808d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8092  mov     rbx, [rsp+78h+arg_10]
0x1800c809a  add     rsp, 40h
0x1800c809e  pop     r15
0x1800c80a0  pop     r14
0x1800c80a2  pop     r13
0x1800c80a4  pop     r12
0x1800c80a6  pop     rdi
0x1800c80a7  pop     rsi
0x1800c80a8  pop     rbp
0x1800c80a9  retn
```
