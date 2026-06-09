# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18004d60c`
- end: `0x18004d905`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x18004badc`
- `0x18004bb9c`
- `0x18004bf54`

## callees

- `0x18002eec0`
- `0x18004a3d4`
- `0x18004a9a0`
- `0x18004b9b0`
- `0x18004d60c`
- `0x18004e388`
- `0x18004e454`
- `0x18004e470`
- `0x18004f52c`
- `0x18007c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004d72f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004d72f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18004d8c0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18004d8c0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18004d84e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18004d84e`

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
0x18004d60c  mov     [rsp+arg_10], rbx
0x18004d611  mov     [rsp+arg_8], edx
0x18004d615  mov     [rsp+arg_0], rcx
0x18004d61a  push    rbp
0x18004d61b  push    rsi
0x18004d61c  push    rdi
0x18004d61d  push    r12
0x18004d61f  push    r13
0x18004d621  push    r14
0x18004d623  push    r15
0x18004d625  sub     rsp, 40h
0x18004d629  mov     r12, r9
0x18004d62c  mov     r13, r8
0x18004d62f  mov     r10, rcx
0x18004d632  xor     eax, eax
0x18004d634  mov     rsi, [rsp+78h+lpOutputString]
0x18004d63c  mov     [rsi], ax
0x18004d63f  mov     rax, [rsp+78h+arg_60]
0x18004d647  mov     byte ptr [rax], 0
0x18004d64a  mov     r14, [rsp+78h+arg_38]
0x18004d652  mov     edi, [r14]
0x18004d655  mov     rbx, [rsp+78h+arg_78]
0x18004d65d  mov     [rbx+8], edi
0x18004d660  mov     eax, [r14+4]
0x18004d664  mov     [rbx+0Ch], eax
0x18004d667  xor     ebp, ebp
0x18004d669  mov     r15d, [rsp+78h+arg_30]
0x18004d671  mov     ecx, r15d
0x18004d674  test    r15d, r15d
0x18004d677  jz      short loc_18004D6DF
0x18004d679  sub     ecx, 1
0x18004d67c  jz      short loc_18004D6D6
0x18004d67e  sub     ecx, 1
0x18004d681  jz      short loc_18004D691
0x18004d683  cmp     ecx, 1
0x18004d686  jnz     short loc_18004D6E8
0x18004d688  mov     ecx, edi; this
0x18004d68a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18004d68f  jmp     short loc_18004D6E6
0x18004d691  test    edi, edi
0x18004d693  js      short loc_18004D6CD
0x18004d695  mov     edi, 8007029Ch
0x18004d69a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18004d69e  mov     rax, [rsp+78h+arg_28]
0x18004d6a6  mov     [rsp+78h+var_50], rax; __int64
0x18004d6ab  mov     rax, [rsp+78h+arg_20]
0x18004d6b3  mov     [rsp+78h+var_58], rax; __int64
0x18004d6b8  mov     rcx, r10; int
0x18004d6bb  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18004d6c0  mov     [rbx+8], edi
0x18004d6c3  mov     ecx, edi; this
0x18004d6c5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18004d6ca  mov     [rbx+0Ch], eax
0x18004d6cd  mov     ecx, edi; this
0x18004d6cf  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18004d6d4  jmp     short loc_18004D6E6
0x18004d6d6  mov     ecx, edi; this
0x18004d6d8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18004d6dd  jmp     short loc_18004D6E6
0x18004d6df  mov     ecx, edi; this
0x18004d6e1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18004d6e6  mov     ebp, eax
0x18004d6e8  mov     [rbx], r15d
0x18004d6eb  mov     eax, [rsp+78h+arg_70]
0x18004d6f2  mov     [rbx+4], eax
0x18004d6f5  cmp     dword ptr [r14+8], 1
0x18004d6fa  jnz     short loc_18004D702
0x18004d6fc  or      eax, 8
0x18004d6ff  mov     [rbx+4], eax
0x18004d702  mov     eax, 1
0x18004d707  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18004d70f  inc     eax
0x18004d711  mov     [rbx+10h], eax
0x18004d714  mov     rax, [rsp+78h+arg_40]
0x18004d71c  xor     edi, edi
0x18004d71e  test    rax, rax
0x18004d721  jz      short loc_18004D728
0x18004d723  cmp     [rax], di
0x18004d726  jnz     short loc_18004D72B
0x18004d728  mov     rax, rdi
0x18004d72b  mov     [rbx+18h], rax
0x18004d72f  call    cs:__imp_GetCurrentThreadId
0x18004d735  mov     [rbx+20h], eax
0x18004d738  mov     [rbx+38h], r13
0x18004d73c  mov     eax, [rsp+78h+arg_8]
0x18004d743  mov     [rbx+40h], eax
0x18004d746  mov     [rbx+44h], ebp
0x18004d749  mov     rax, [rsp+78h+arg_20]
0x18004d751  mov     [rbx+28h], rax
0x18004d755  mov     [rbx+30h], r12
0x18004d759  mov     rax, [rsp+78h+arg_28]
0x18004d761  mov     [rbx+88h], rax
0x18004d768  mov     rax, [rsp+78h+arg_0]
0x18004d770  mov     [rbx+90h], rax
0x18004d777  mov     [rbx+48h], rdi
0x18004d77b  xorps   xmm0, xmm0
0x18004d77e  xor     eax, eax
0x18004d780  movups  xmmword ptr [rbx+68h], xmm0
0x18004d784  mov     [rbx+78h], rax
0x18004d788  movups  xmmword ptr [rbx+50h], xmm0
0x18004d78c  mov     [rbx+60h], rax
0x18004d790  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18004d797  test    rax, rax
0x18004d79a  jz      short loc_18004D7A3
0x18004d79c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d7a1  jmp     short loc_18004D7A6
0x18004d7a3  mov     rax, rdi
0x18004d7a6  mov     [rbx+80h], rax
0x18004d7ad  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18004d7b4  test    rax, rax
0x18004d7b7  jz      short loc_18004D7C1
0x18004d7b9  mov     rcx, rbx
0x18004d7bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d7c1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18004d7c8  test    rax, rax
0x18004d7cb  jz      short loc_18004D7E3
0x18004d7cd  mov     r8d, 400h
0x18004d7d3  mov     rdx, [rsp+78h+arg_60]
0x18004d7db  mov     rcx, rbx
0x18004d7de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d7e3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18004d7ea  test    rax, rax
0x18004d7ed  jz      short loc_18004D7F7
0x18004d7ef  mov     rcx, rbx
0x18004d7f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d7f7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18004d7fe  test    rax, rax
0x18004d801  jz      short loc_18004D811
0x18004d803  test    byte ptr [rbx+4], 2
0x18004d807  jnz     short loc_18004D811
0x18004d809  mov     rcx, rbx
0x18004d80c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d811  cmp     [rbx+8], edi
0x18004d814  jl      short loc_18004D830
0x18004d816  cmp     r15d, 3
0x18004d81a  jnz     loc_18004D8FF
0x18004d820  mov     ecx, 8000FFFFh; this
0x18004d825  mov     [rbx+8], ecx
0x18004d828  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18004d82d  mov     [rbx+0Ch], eax
0x18004d830  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18004d837  jnz     short loc_18004D858
0x18004d839  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18004d840  test    rax, rax
0x18004d843  jz      short loc_18004D84E
0x18004d845  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d84a  test    al, al
0x18004d84c  jmp     short loc_18004D856
0x18004d84e  call    cs:__imp_IsDebuggerPresent
0x18004d854  test    eax, eax
0x18004d856  jz      short loc_18004D85E
0x18004d858  test    byte ptr [rbx+4], 2
0x18004d85c  jz      short loc_18004D882
0x18004d85e  mov     rax, cs:g_pfnResultLoggingCallback
0x18004d865  test    rax, rax
0x18004d868  jz      short loc_18004D8C6
0x18004d86a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18004d871  jnz     short loc_18004D8C6
0x18004d873  xor     r8d, r8d
0x18004d876  xor     edx, edx
0x18004d878  mov     rcx, rbx
0x18004d87b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d880  jmp     short loc_18004D8C6
0x18004d882  mov     ebp, 800h
0x18004d887  mov     rax, cs:g_pfnResultLoggingCallback
0x18004d88e  test    rax, rax
0x18004d891  jz      short loc_18004D8AA
0x18004d893  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18004d89a  jnz     short loc_18004D8AA
0x18004d89c  mov     r8d, ebp
0x18004d89f  mov     rdx, rsi
0x18004d8a2  mov     rcx, rbx
0x18004d8a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d8aa  cmp     [rsi], di
0x18004d8ad  jnz     short loc_18004D8BD
0x18004d8af  mov     r8, rbx; unsigned __int64
0x18004d8b2  mov     rdx, rbp; unsigned __int16 *
0x18004d8b5  mov     rcx, rsi; this
0x18004d8b8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18004d8bd  mov     rcx, rsi; lpOutputString
0x18004d8c0  call    cs:__imp_OutputDebugStringW
0x18004d8c6  test    byte ptr [rbx+4], 4
0x18004d8ca  jnz     short loc_18004D8D5
0x18004d8cc  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18004d8d3  jz      short loc_18004D8E7
0x18004d8d5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18004d8dc  test    rax, rax
0x18004d8df  jz      short loc_18004D8E7
0x18004d8e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d8e6  nop
0x18004d8e7  mov     rbx, [rsp+78h+arg_10]
0x18004d8ef  add     rsp, 40h
0x18004d8f3  pop     r15
0x18004d8f5  pop     r14
0x18004d8f7  pop     r13
0x18004d8f9  pop     r12
0x18004d8fb  pop     rdi
0x18004d8fc  pop     rsi
0x18004d8fd  pop     rbp
0x18004d8fe  retn
0x18004d8ff  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
