# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140009ee4`
- end: `0x14000a1dd`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140004598`

## callees

- `0x140003bb4`
- `0x140009350`
- `0x140009b94`
- `0x140009ee4`
- `0x14000b2c8`
- `0x14000b2f0`
- `0x14000b41c`
- `0x14000b438`
- `0x1400100dc`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000a007`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000a007`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000a198`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000a198`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000a126`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000a126`

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
0x140009ee4  mov     [rsp+arg_10], rbx
0x140009ee9  mov     [rsp+arg_8], edx
0x140009eed  mov     [rsp+arg_0], rcx
0x140009ef2  push    rbp
0x140009ef3  push    rsi
0x140009ef4  push    rdi
0x140009ef5  push    r12
0x140009ef7  push    r13
0x140009ef9  push    r14
0x140009efb  push    r15
0x140009efd  sub     rsp, 40h
0x140009f01  mov     r12, r9
0x140009f04  mov     r13, r8
0x140009f07  mov     r10, rcx
0x140009f0a  xor     eax, eax
0x140009f0c  mov     rsi, [rsp+78h+lpOutputString]
0x140009f14  mov     [rsi], ax
0x140009f17  mov     rax, [rsp+78h+arg_60]
0x140009f1f  mov     byte ptr [rax], 0
0x140009f22  mov     r14, [rsp+78h+arg_38]
0x140009f2a  mov     edi, [r14]
0x140009f2d  mov     rbx, [rsp+78h+arg_78]
0x140009f35  mov     [rbx+8], edi
0x140009f38  mov     eax, [r14+4]
0x140009f3c  mov     [rbx+0Ch], eax
0x140009f3f  xor     ebp, ebp
0x140009f41  mov     r15d, [rsp+78h+arg_30]
0x140009f49  mov     ecx, r15d
0x140009f4c  test    r15d, r15d
0x140009f4f  jz      short loc_140009FB7
0x140009f51  sub     ecx, 1
0x140009f54  jz      short loc_140009FAE
0x140009f56  sub     ecx, 1
0x140009f59  jz      short loc_140009F69
0x140009f5b  cmp     ecx, 1
0x140009f5e  jnz     short loc_140009FC0
0x140009f60  mov     ecx, edi; this
0x140009f62  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140009f67  jmp     short loc_140009FBE
0x140009f69  test    edi, edi
0x140009f6b  js      short loc_140009FA5
0x140009f6d  mov     edi, 8007029Ch
0x140009f72  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x140009f76  mov     rax, [rsp+78h+arg_28]
0x140009f7e  mov     [rsp+78h+var_50], rax; __int64
0x140009f83  mov     rax, [rsp+78h+arg_20]
0x140009f8b  mov     [rsp+78h+var_58], rax; __int64
0x140009f90  mov     rcx, r10; int
0x140009f93  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140009f98  mov     [rbx+8], edi
0x140009f9b  mov     ecx, edi; this
0x140009f9d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140009fa2  mov     [rbx+0Ch], eax
0x140009fa5  mov     ecx, edi; this
0x140009fa7  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140009fac  jmp     short loc_140009FBE
0x140009fae  mov     ecx, edi; this
0x140009fb0  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140009fb5  jmp     short loc_140009FBE
0x140009fb7  mov     ecx, edi; this
0x140009fb9  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140009fbe  mov     ebp, eax
0x140009fc0  mov     [rbx], r15d
0x140009fc3  mov     eax, [rsp+78h+arg_70]
0x140009fca  mov     [rbx+4], eax
0x140009fcd  cmp     dword ptr [r14+8], 1
0x140009fd2  jnz     short loc_140009FDA
0x140009fd4  or      eax, 8
0x140009fd7  mov     [rbx+4], eax
0x140009fda  mov     eax, 1
0x140009fdf  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140009fe7  inc     eax
0x140009fe9  mov     [rbx+10h], eax
0x140009fec  mov     rax, [rsp+78h+arg_40]
0x140009ff4  xor     edi, edi
0x140009ff6  test    rax, rax
0x140009ff9  jz      short loc_14000A000
0x140009ffb  cmp     [rax], di
0x140009ffe  jnz     short loc_14000A003
0x14000a000  mov     rax, rdi
0x14000a003  mov     [rbx+18h], rax
0x14000a007  call    cs:__imp_GetCurrentThreadId
0x14000a00d  mov     [rbx+20h], eax
0x14000a010  mov     [rbx+38h], r13
0x14000a014  mov     eax, [rsp+78h+arg_8]
0x14000a01b  mov     [rbx+40h], eax
0x14000a01e  mov     [rbx+44h], ebp
0x14000a021  mov     rax, [rsp+78h+arg_20]
0x14000a029  mov     [rbx+28h], rax
0x14000a02d  mov     [rbx+30h], r12
0x14000a031  mov     rax, [rsp+78h+arg_28]
0x14000a039  mov     [rbx+88h], rax
0x14000a040  mov     rax, [rsp+78h+arg_0]
0x14000a048  mov     [rbx+90h], rax
0x14000a04f  mov     [rbx+48h], rdi
0x14000a053  xorps   xmm0, xmm0
0x14000a056  xor     eax, eax
0x14000a058  movups  xmmword ptr [rbx+68h], xmm0
0x14000a05c  mov     [rbx+78h], rax
0x14000a060  movups  xmmword ptr [rbx+50h], xmm0
0x14000a064  mov     [rbx+60h], rax
0x14000a068  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000a06f  test    rax, rax
0x14000a072  jz      short loc_14000A07B
0x14000a074  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a079  jmp     short loc_14000A07E
0x14000a07b  mov     rax, rdi
0x14000a07e  mov     [rbx+80h], rax
0x14000a085  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14000a08c  test    rax, rax
0x14000a08f  jz      short loc_14000A099
0x14000a091  mov     rcx, rbx
0x14000a094  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a099  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000a0a0  test    rax, rax
0x14000a0a3  jz      short loc_14000A0BB
0x14000a0a5  mov     r8d, 400h
0x14000a0ab  mov     rdx, [rsp+78h+arg_60]
0x14000a0b3  mov     rcx, rbx
0x14000a0b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a0bb  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000a0c2  test    rax, rax
0x14000a0c5  jz      short loc_14000A0CF
0x14000a0c7  mov     rcx, rbx
0x14000a0ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a0cf  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000a0d6  test    rax, rax
0x14000a0d9  jz      short loc_14000A0E9
0x14000a0db  test    byte ptr [rbx+4], 2
0x14000a0df  jnz     short loc_14000A0E9
0x14000a0e1  mov     rcx, rbx
0x14000a0e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a0e9  cmp     [rbx+8], edi
0x14000a0ec  jl      short loc_14000A108
0x14000a0ee  cmp     r15d, 3
0x14000a0f2  jnz     loc_14000A1D7
0x14000a0f8  mov     ecx, 8000FFFFh; this
0x14000a0fd  mov     [rbx+8], ecx
0x14000a100  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000a105  mov     [rbx+0Ch], eax
0x14000a108  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x14000a10f  jnz     short loc_14000A130
0x14000a111  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14000a118  test    rax, rax
0x14000a11b  jz      short loc_14000A126
0x14000a11d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a122  test    al, al
0x14000a124  jmp     short loc_14000A12E
0x14000a126  call    cs:__imp_IsDebuggerPresent
0x14000a12c  test    eax, eax
0x14000a12e  jz      short loc_14000A136
0x14000a130  test    byte ptr [rbx+4], 2
0x14000a134  jz      short loc_14000A15A
0x14000a136  mov     rax, cs:g_pfnResultLoggingCallback
0x14000a13d  test    rax, rax
0x14000a140  jz      short loc_14000A19E
0x14000a142  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14000a149  jnz     short loc_14000A19E
0x14000a14b  xor     r8d, r8d
0x14000a14e  xor     edx, edx
0x14000a150  mov     rcx, rbx
0x14000a153  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a158  jmp     short loc_14000A19E
0x14000a15a  mov     ebp, 800h
0x14000a15f  mov     rax, cs:g_pfnResultLoggingCallback
0x14000a166  test    rax, rax
0x14000a169  jz      short loc_14000A182
0x14000a16b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14000a172  jnz     short loc_14000A182
0x14000a174  mov     r8d, ebp
0x14000a177  mov     rdx, rsi
0x14000a17a  mov     rcx, rbx
0x14000a17d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a182  cmp     [rsi], di
0x14000a185  jnz     short loc_14000A195
0x14000a187  mov     r8, rbx; unsigned __int64
0x14000a18a  mov     rdx, rbp; unsigned __int16 *
0x14000a18d  mov     rcx, rsi; this
0x14000a190  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14000a195  mov     rcx, rsi; lpOutputString
0x14000a198  call    cs:__imp_OutputDebugStringW
0x14000a19e  test    byte ptr [rbx+4], 4
0x14000a1a2  jnz     short loc_14000A1AD
0x14000a1a4  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x14000a1ab  jz      short loc_14000A1BF
0x14000a1ad  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14000a1b4  test    rax, rax
0x14000a1b7  jz      short loc_14000A1BF
0x14000a1b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a1be  nop
0x14000a1bf  mov     rbx, [rsp+78h+arg_10]
0x14000a1c7  add     rsp, 40h
0x14000a1cb  pop     r15
0x14000a1cd  pop     r14
0x14000a1cf  pop     r13
0x14000a1d1  pop     r12
0x14000a1d3  pop     rdi
0x14000a1d4  pop     rsi
0x14000a1d5  pop     rbp
0x14000a1d6  retn
0x14000a1d7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
