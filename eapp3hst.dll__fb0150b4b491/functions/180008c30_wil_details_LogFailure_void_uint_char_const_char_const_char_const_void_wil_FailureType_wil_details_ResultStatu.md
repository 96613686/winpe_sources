# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180008c30`
- end: `0x180008f29`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180005420`
- `0x18000576c`

## callees

- `0x180002ad4`
- `0x180002ec8`
- `0x180003190`
- `0x180005360`
- `0x180008c30`
- `0x180009c84`
- `0x180009ddc`
- `0x180009df8`
- `0x18000b944`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008d53`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008d53`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008ee4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008ee4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008e72`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008e72`

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
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v25);
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
0x180008c30  mov     [rsp+arg_10], rbx
0x180008c35  mov     [rsp+arg_8], edx
0x180008c39  mov     [rsp+arg_0], rcx
0x180008c3e  push    rbp
0x180008c3f  push    rsi
0x180008c40  push    rdi
0x180008c41  push    r12
0x180008c43  push    r13
0x180008c45  push    r14
0x180008c47  push    r15
0x180008c49  sub     rsp, 40h
0x180008c4d  mov     r12, r9
0x180008c50  mov     r13, r8
0x180008c53  mov     r10, rcx
0x180008c56  xor     eax, eax
0x180008c58  mov     rsi, [rsp+78h+lpOutputString]
0x180008c60  mov     [rsi], ax
0x180008c63  mov     rax, [rsp+78h+arg_60]
0x180008c6b  mov     byte ptr [rax], 0
0x180008c6e  mov     r14, [rsp+78h+arg_38]
0x180008c76  mov     edi, [r14]
0x180008c79  mov     rbx, [rsp+78h+arg_78]
0x180008c81  mov     [rbx+8], edi
0x180008c84  mov     eax, [r14+4]
0x180008c88  mov     [rbx+0Ch], eax
0x180008c8b  xor     ebp, ebp
0x180008c8d  mov     r15d, [rsp+78h+arg_30]
0x180008c95  mov     ecx, r15d
0x180008c98  test    r15d, r15d
0x180008c9b  jz      short loc_180008D03
0x180008c9d  sub     ecx, 1
0x180008ca0  jz      short loc_180008CFA
0x180008ca2  sub     ecx, 1
0x180008ca5  jz      short loc_180008CB5
0x180008ca7  cmp     ecx, 1
0x180008caa  jnz     short loc_180008D0C
0x180008cac  mov     ecx, edi; this
0x180008cae  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180008cb3  jmp     short loc_180008D0A
0x180008cb5  test    edi, edi
0x180008cb7  js      short loc_180008CF1
0x180008cb9  mov     edi, 8007029Ch
0x180008cbe  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180008cc2  mov     rax, [rsp+78h+arg_28]
0x180008cca  mov     [rsp+78h+var_50], rax; __int64
0x180008ccf  mov     rax, [rsp+78h+arg_20]
0x180008cd7  mov     [rsp+78h+var_58], rax; __int64
0x180008cdc  mov     rcx, r10; int
0x180008cdf  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180008ce4  mov     [rbx+8], edi
0x180008ce7  mov     ecx, edi; this
0x180008ce9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180008cee  mov     [rbx+0Ch], eax
0x180008cf1  mov     ecx, edi; this
0x180008cf3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180008cf8  jmp     short loc_180008D0A
0x180008cfa  mov     ecx, edi; this
0x180008cfc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180008d01  jmp     short loc_180008D0A
0x180008d03  mov     ecx, edi; this
0x180008d05  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180008d0a  mov     ebp, eax
0x180008d0c  mov     [rbx], r15d
0x180008d0f  mov     eax, [rsp+78h+arg_70]
0x180008d16  mov     [rbx+4], eax
0x180008d19  cmp     dword ptr [r14+8], 1
0x180008d1e  jnz     short loc_180008D26
0x180008d20  or      eax, 8
0x180008d23  mov     [rbx+4], eax
0x180008d26  mov     eax, 1
0x180008d2b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180008d33  inc     eax
0x180008d35  mov     [rbx+10h], eax
0x180008d38  mov     rax, [rsp+78h+arg_40]
0x180008d40  xor     edi, edi
0x180008d42  test    rax, rax
0x180008d45  jz      short loc_180008D4C
0x180008d47  cmp     [rax], di
0x180008d4a  jnz     short loc_180008D4F
0x180008d4c  mov     rax, rdi
0x180008d4f  mov     [rbx+18h], rax
0x180008d53  call    cs:__imp_GetCurrentThreadId
0x180008d59  mov     [rbx+20h], eax
0x180008d5c  mov     [rbx+38h], r13
0x180008d60  mov     eax, [rsp+78h+arg_8]
0x180008d67  mov     [rbx+40h], eax
0x180008d6a  mov     [rbx+44h], ebp
0x180008d6d  mov     rax, [rsp+78h+arg_20]
0x180008d75  mov     [rbx+28h], rax
0x180008d79  mov     [rbx+30h], r12
0x180008d7d  mov     rax, [rsp+78h+arg_28]
0x180008d85  mov     [rbx+88h], rax
0x180008d8c  mov     rax, [rsp+78h+arg_0]
0x180008d94  mov     [rbx+90h], rax
0x180008d9b  mov     [rbx+48h], rdi
0x180008d9f  xorps   xmm0, xmm0
0x180008da2  xor     eax, eax
0x180008da4  movups  xmmword ptr [rbx+68h], xmm0
0x180008da8  mov     [rbx+78h], rax
0x180008dac  movups  xmmword ptr [rbx+50h], xmm0
0x180008db0  mov     [rbx+60h], rax
0x180008db4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180008dbb  test    rax, rax
0x180008dbe  jz      short loc_180008DC7
0x180008dc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008dc5  jmp     short loc_180008DCA
0x180008dc7  mov     rax, rdi
0x180008dca  mov     [rbx+80h], rax
0x180008dd1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180008dd8  test    rax, rax
0x180008ddb  jz      short loc_180008DE5
0x180008ddd  mov     rcx, rbx
0x180008de0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008de5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180008dec  test    rax, rax
0x180008def  jz      short loc_180008E07
0x180008df1  mov     r8d, 400h
0x180008df7  mov     rdx, [rsp+78h+arg_60]
0x180008dff  mov     rcx, rbx
0x180008e02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e07  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008e0e  test    rax, rax
0x180008e11  jz      short loc_180008E1B
0x180008e13  mov     rcx, rbx
0x180008e16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e1b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008e22  test    rax, rax
0x180008e25  jz      short loc_180008E35
0x180008e27  test    byte ptr [rbx+4], 2
0x180008e2b  jnz     short loc_180008E35
0x180008e2d  mov     rcx, rbx
0x180008e30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e35  cmp     [rbx+8], edi
0x180008e38  jl      short loc_180008E54
0x180008e3a  cmp     r15d, 3
0x180008e3e  jnz     loc_180008F23
0x180008e44  mov     ecx, 8000FFFFh; this
0x180008e49  mov     [rbx+8], ecx
0x180008e4c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180008e51  mov     [rbx+0Ch], eax
0x180008e54  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180008e5b  jnz     short loc_180008E7C
0x180008e5d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180008e64  test    rax, rax
0x180008e67  jz      short loc_180008E72
0x180008e69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e6e  test    al, al
0x180008e70  jmp     short loc_180008E7A
0x180008e72  call    cs:__imp_IsDebuggerPresent
0x180008e78  test    eax, eax
0x180008e7a  jz      short loc_180008E82
0x180008e7c  test    byte ptr [rbx+4], 2
0x180008e80  jz      short loc_180008EA6
0x180008e82  mov     rax, cs:g_pfnResultLoggingCallback
0x180008e89  test    rax, rax
0x180008e8c  jz      short loc_180008EEA
0x180008e8e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180008e95  jnz     short loc_180008EEA
0x180008e97  xor     r8d, r8d
0x180008e9a  xor     edx, edx
0x180008e9c  mov     rcx, rbx
0x180008e9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ea4  jmp     short loc_180008EEA
0x180008ea6  mov     ebp, 800h
0x180008eab  mov     rax, cs:g_pfnResultLoggingCallback
0x180008eb2  test    rax, rax
0x180008eb5  jz      short loc_180008ECE
0x180008eb7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180008ebe  jnz     short loc_180008ECE
0x180008ec0  mov     r8d, ebp
0x180008ec3  mov     rdx, rsi
0x180008ec6  mov     rcx, rbx
0x180008ec9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ece  cmp     [rsi], di
0x180008ed1  jnz     short loc_180008EE1
0x180008ed3  mov     r8, rbx; unsigned __int64
0x180008ed6  mov     rdx, rbp; wchar_t *
0x180008ed9  mov     rcx, rsi; this
0x180008edc  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180008ee1  mov     rcx, rsi; lpOutputString
0x180008ee4  call    cs:__imp_OutputDebugStringW
0x180008eea  test    byte ptr [rbx+4], 4
0x180008eee  jnz     short loc_180008EF9
0x180008ef0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180008ef7  jz      short loc_180008F0B
0x180008ef9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180008f00  test    rax, rax
0x180008f03  jz      short loc_180008F0B
0x180008f05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f0a  nop
0x180008f0b  mov     rbx, [rsp+78h+arg_10]
0x180008f13  add     rsp, 40h
0x180008f17  pop     r15
0x180008f19  pop     r14
0x180008f1b  pop     r13
0x180008f1d  pop     r12
0x180008f1f  pop     rdi
0x180008f20  pop     rsi
0x180008f21  pop     rbp
0x180008f22  retn
0x180008f23  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
