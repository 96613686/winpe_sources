# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180009ed0`
- end: `0x18000a1c5`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180009654`
- `0x180009c34`
- `0x180009ddc`

## callees

- `0x180007618`
- `0x180009ed0`
- `0x18000a1d0`
- `0x18000c454`
- `0x18000cd34`
- `0x18000d714`
- `0x18000d730`
- `0x18000d74c`
- `0x18000dfd0`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009ff3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009ff3`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000a186`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000a186`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000a114`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000a114`

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
0x180009ed0  mov     [rsp+arg_10], rbx
0x180009ed5  mov     [rsp+arg_8], edx
0x180009ed9  mov     [rsp+arg_0], rcx
0x180009ede  push    rbp
0x180009edf  push    rsi
0x180009ee0  push    rdi
0x180009ee1  push    r12
0x180009ee3  push    r13
0x180009ee5  push    r14
0x180009ee7  push    r15
0x180009ee9  sub     rsp, 40h
0x180009eed  mov     r12, r9
0x180009ef0  mov     r13, r8
0x180009ef3  mov     r10, rcx
0x180009ef6  xor     eax, eax
0x180009ef8  mov     rsi, [rsp+78h+lpOutputString]
0x180009f00  mov     [rsi], ax
0x180009f03  mov     rax, [rsp+78h+arg_60]
0x180009f0b  mov     byte ptr [rax], 0
0x180009f0e  mov     r14, [rsp+78h+arg_38]
0x180009f16  mov     edi, [r14]
0x180009f19  mov     rbx, [rsp+78h+arg_78]
0x180009f21  mov     [rbx+8], edi
0x180009f24  mov     eax, [r14+4]
0x180009f28  mov     [rbx+0Ch], eax
0x180009f2b  xor     ebp, ebp
0x180009f2d  mov     r15d, [rsp+78h+arg_30]
0x180009f35  mov     ecx, r15d
0x180009f38  test    r15d, r15d
0x180009f3b  jz      short loc_180009FA3
0x180009f3d  sub     ecx, 1
0x180009f40  jz      short loc_180009F9A
0x180009f42  sub     ecx, 1
0x180009f45  jz      short loc_180009F55
0x180009f47  cmp     ecx, 1
0x180009f4a  jnz     short loc_180009FAC
0x180009f4c  mov     ecx, edi; this
0x180009f4e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180009f53  jmp     short loc_180009FAA
0x180009f55  test    edi, edi
0x180009f57  js      short loc_180009F91
0x180009f59  mov     edi, 8007029Ch
0x180009f5e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180009f62  mov     rax, [rsp+78h+arg_28]
0x180009f6a  mov     [rsp+78h+var_50], rax; __int64
0x180009f6f  mov     rax, [rsp+78h+arg_20]
0x180009f77  mov     [rsp+78h+var_58], rax; __int64
0x180009f7c  mov     rcx, r10; int
0x180009f7f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180009f84  mov     [rbx+8], edi
0x180009f87  mov     ecx, edi; this
0x180009f89  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180009f8e  mov     [rbx+0Ch], eax
0x180009f91  mov     ecx, edi; this
0x180009f93  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180009f98  jmp     short loc_180009FAA
0x180009f9a  mov     ecx, edi; this
0x180009f9c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180009fa1  jmp     short loc_180009FAA
0x180009fa3  mov     ecx, edi; this
0x180009fa5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180009faa  mov     ebp, eax
0x180009fac  mov     [rbx], r15d
0x180009faf  mov     eax, [rsp+78h+arg_70]
0x180009fb6  mov     [rbx+4], eax
0x180009fb9  cmp     dword ptr [r14+8], 1
0x180009fbe  jnz     short loc_180009FC6
0x180009fc0  or      eax, 8
0x180009fc3  mov     [rbx+4], eax
0x180009fc6  mov     eax, 1
0x180009fcb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180009fd3  inc     eax
0x180009fd5  mov     [rbx+10h], eax
0x180009fd8  mov     rax, [rsp+78h+arg_40]
0x180009fe0  xor     edi, edi
0x180009fe2  test    rax, rax
0x180009fe5  jz      short loc_180009FEC
0x180009fe7  cmp     [rax], di
0x180009fea  jnz     short loc_180009FEF
0x180009fec  mov     rax, rdi
0x180009fef  mov     [rbx+18h], rax
0x180009ff3  call    cs:__imp_GetCurrentThreadId
0x180009ff9  mov     [rbx+20h], eax
0x180009ffc  mov     [rbx+38h], r13
0x18000a000  mov     eax, [rsp+78h+arg_8]
0x18000a007  mov     [rbx+40h], eax
0x18000a00a  mov     [rbx+44h], ebp
0x18000a00d  mov     rax, [rsp+78h+arg_20]
0x18000a015  mov     [rbx+28h], rax
0x18000a019  mov     [rbx+30h], r12
0x18000a01d  mov     rax, [rsp+78h+arg_28]
0x18000a025  mov     [rbx+88h], rax
0x18000a02c  mov     rax, [rsp+78h+arg_0]
0x18000a034  mov     [rbx+90h], rax
0x18000a03b  mov     [rbx+48h], rdi
0x18000a03f  xorps   xmm0, xmm0
0x18000a042  xor     eax, eax
0x18000a044  movups  xmmword ptr [rbx+68h], xmm0
0x18000a048  mov     [rbx+78h], rax
0x18000a04c  movups  xmmword ptr [rbx+50h], xmm0
0x18000a050  mov     [rbx+60h], rax
0x18000a054  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000a05b  test    rax, rax
0x18000a05e  jz      short loc_18000A067
0x18000a060  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a065  jmp     short loc_18000A06A
0x18000a067  mov     rax, rdi
0x18000a06a  mov     [rbx+80h], rax
0x18000a071  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000a078  test    rax, rax
0x18000a07b  jz      short loc_18000A085
0x18000a07d  mov     rcx, rbx
0x18000a080  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a085  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000a08c  test    rax, rax
0x18000a08f  jz      short loc_18000A0A7
0x18000a091  mov     r8d, 400h
0x18000a097  mov     rdx, [rsp+78h+arg_60]
0x18000a09f  mov     rcx, rbx
0x18000a0a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0a7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a0ae  test    rax, rax
0x18000a0b1  jz      short loc_18000A0BB
0x18000a0b3  mov     rcx, rbx
0x18000a0b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0bb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a0c2  test    rax, rax
0x18000a0c5  jz      short loc_18000A0D5
0x18000a0c7  test    byte ptr [rbx+4], 2
0x18000a0cb  jnz     short loc_18000A0D5
0x18000a0cd  mov     rcx, rbx
0x18000a0d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0d5  cmp     [rbx+8], edi
0x18000a0d8  jl      short loc_18000A0F6
0x18000a0da  cmp     r15d, 3
0x18000a0de  jz      short loc_18000A0E6
0x18000a0e0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000a0e6  mov     ecx, 8000FFFFh; this
0x18000a0eb  mov     [rbx+8], ecx
0x18000a0ee  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000a0f3  mov     [rbx+0Ch], eax
0x18000a0f6  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000a0fd  jnz     short loc_18000A11E
0x18000a0ff  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000a106  test    rax, rax
0x18000a109  jz      short loc_18000A114
0x18000a10b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a110  test    al, al
0x18000a112  jmp     short loc_18000A11C
0x18000a114  call    cs:__imp_IsDebuggerPresent
0x18000a11a  test    eax, eax
0x18000a11c  jz      short loc_18000A124
0x18000a11e  test    byte ptr [rbx+4], 2
0x18000a122  jz      short loc_18000A148
0x18000a124  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a12b  test    rax, rax
0x18000a12e  jz      short loc_18000A18C
0x18000a130  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000a137  jnz     short loc_18000A18C
0x18000a139  xor     r8d, r8d
0x18000a13c  xor     edx, edx
0x18000a13e  mov     rcx, rbx
0x18000a141  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a146  jmp     short loc_18000A18C
0x18000a148  mov     ebp, 800h
0x18000a14d  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a154  test    rax, rax
0x18000a157  jz      short loc_18000A170
0x18000a159  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000a160  jnz     short loc_18000A170
0x18000a162  mov     r8d, ebp
0x18000a165  mov     rdx, rsi
0x18000a168  mov     rcx, rbx
0x18000a16b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a170  cmp     [rsi], di
0x18000a173  jnz     short loc_18000A183
0x18000a175  mov     r8, rbx; unsigned __int64
0x18000a178  mov     rdx, rbp; unsigned __int16 *
0x18000a17b  mov     rcx, rsi; this
0x18000a17e  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000a183  mov     rcx, rsi; lpOutputString
0x18000a186  call    cs:__imp_OutputDebugStringW
0x18000a18c  test    byte ptr [rbx+4], 4
0x18000a190  jnz     short loc_18000A19B
0x18000a192  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000a199  jz      short loc_18000A1AD
0x18000a19b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000a1a2  test    rax, rax
0x18000a1a5  jz      short loc_18000A1AD
0x18000a1a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1ac  nop
0x18000a1ad  mov     rbx, [rsp+78h+arg_10]
0x18000a1b5  add     rsp, 40h
0x18000a1b9  pop     r15
0x18000a1bb  pop     r14
0x18000a1bd  pop     r13
0x18000a1bf  pop     r12
0x18000a1c1  pop     rdi
0x18000a1c2  pop     rsi
0x18000a1c3  pop     rbp
0x18000a1c4  retn
```
