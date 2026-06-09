# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180011c80`
- end: `0x180011f75`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x180011b84`
- `0x1800311b8`
- `0x180031278`
- `0x180035694`

## callees

- `0x1800119c0`
- `0x180011c80`
- `0x180011f80`
- `0x180031100`
- `0x180031d14`
- `0x18003277c`
- `0x180032798`
- `0x1800327b4`
- `0x18003343c`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011da3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011da3`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180011f36`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180011f36`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180011ec4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180011ec4`

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
0x180011c80  mov     [rsp+arg_10], rbx
0x180011c85  mov     [rsp+arg_8], edx
0x180011c89  mov     [rsp+arg_0], rcx
0x180011c8e  push    rbp
0x180011c8f  push    rsi
0x180011c90  push    rdi
0x180011c91  push    r12
0x180011c93  push    r13
0x180011c95  push    r14
0x180011c97  push    r15
0x180011c99  sub     rsp, 40h
0x180011c9d  mov     r12, r9
0x180011ca0  mov     r13, r8
0x180011ca3  mov     r10, rcx
0x180011ca6  xor     eax, eax
0x180011ca8  mov     rsi, [rsp+78h+lpOutputString]
0x180011cb0  mov     [rsi], ax
0x180011cb3  mov     rax, [rsp+78h+arg_60]
0x180011cbb  mov     byte ptr [rax], 0
0x180011cbe  mov     r14, [rsp+78h+arg_38]
0x180011cc6  mov     edi, [r14]
0x180011cc9  mov     rbx, [rsp+78h+arg_78]
0x180011cd1  mov     [rbx+8], edi
0x180011cd4  mov     eax, [r14+4]
0x180011cd8  mov     [rbx+0Ch], eax
0x180011cdb  xor     ebp, ebp
0x180011cdd  mov     r15d, [rsp+78h+arg_30]
0x180011ce5  mov     ecx, r15d
0x180011ce8  test    r15d, r15d
0x180011ceb  jz      short loc_180011D53
0x180011ced  sub     ecx, 1
0x180011cf0  jz      short loc_180011D4A
0x180011cf2  sub     ecx, 1
0x180011cf5  jz      short loc_180011D05
0x180011cf7  cmp     ecx, 1
0x180011cfa  jnz     short loc_180011D5C
0x180011cfc  mov     ecx, edi; this
0x180011cfe  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180011d03  jmp     short loc_180011D5A
0x180011d05  test    edi, edi
0x180011d07  js      short loc_180011D41
0x180011d09  mov     edi, 8007029Ch
0x180011d0e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180011d12  mov     rax, [rsp+78h+arg_28]
0x180011d1a  mov     [rsp+78h+var_50], rax; __int64
0x180011d1f  mov     rax, [rsp+78h+arg_20]
0x180011d27  mov     [rsp+78h+var_58], rax; __int64
0x180011d2c  mov     rcx, r10; int
0x180011d2f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180011d34  mov     [rbx+8], edi
0x180011d37  mov     ecx, edi; this
0x180011d39  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180011d3e  mov     [rbx+0Ch], eax
0x180011d41  mov     ecx, edi; this
0x180011d43  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180011d48  jmp     short loc_180011D5A
0x180011d4a  mov     ecx, edi; this
0x180011d4c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180011d51  jmp     short loc_180011D5A
0x180011d53  mov     ecx, edi; this
0x180011d55  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180011d5a  mov     ebp, eax
0x180011d5c  mov     [rbx], r15d
0x180011d5f  mov     eax, [rsp+78h+arg_70]
0x180011d66  mov     [rbx+4], eax
0x180011d69  cmp     dword ptr [r14+8], 1
0x180011d6e  jnz     short loc_180011D76
0x180011d70  or      eax, 8
0x180011d73  mov     [rbx+4], eax
0x180011d76  mov     eax, 1
0x180011d7b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180011d83  inc     eax
0x180011d85  mov     [rbx+10h], eax
0x180011d88  mov     rax, [rsp+78h+arg_40]
0x180011d90  xor     edi, edi
0x180011d92  test    rax, rax
0x180011d95  jz      short loc_180011D9C
0x180011d97  cmp     [rax], di
0x180011d9a  jnz     short loc_180011D9F
0x180011d9c  mov     rax, rdi
0x180011d9f  mov     [rbx+18h], rax
0x180011da3  call    cs:__imp_GetCurrentThreadId
0x180011da9  mov     [rbx+20h], eax
0x180011dac  mov     [rbx+38h], r13
0x180011db0  mov     eax, [rsp+78h+arg_8]
0x180011db7  mov     [rbx+40h], eax
0x180011dba  mov     [rbx+44h], ebp
0x180011dbd  mov     rax, [rsp+78h+arg_20]
0x180011dc5  mov     [rbx+28h], rax
0x180011dc9  mov     [rbx+30h], r12
0x180011dcd  mov     rax, [rsp+78h+arg_28]
0x180011dd5  mov     [rbx+88h], rax
0x180011ddc  mov     rax, [rsp+78h+arg_0]
0x180011de4  mov     [rbx+90h], rax
0x180011deb  mov     [rbx+48h], rdi
0x180011def  xorps   xmm0, xmm0
0x180011df2  xor     eax, eax
0x180011df4  movups  xmmword ptr [rbx+68h], xmm0
0x180011df8  mov     [rbx+78h], rax
0x180011dfc  movups  xmmword ptr [rbx+50h], xmm0
0x180011e00  mov     [rbx+60h], rax
0x180011e04  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180011e0b  test    rax, rax
0x180011e0e  jz      short loc_180011E17
0x180011e10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e15  jmp     short loc_180011E1A
0x180011e17  mov     rax, rdi
0x180011e1a  mov     [rbx+80h], rax
0x180011e21  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180011e28  test    rax, rax
0x180011e2b  jz      short loc_180011E35
0x180011e2d  mov     rcx, rbx
0x180011e30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e35  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180011e3c  test    rax, rax
0x180011e3f  jz      short loc_180011E57
0x180011e41  mov     r8d, 400h
0x180011e47  mov     rdx, [rsp+78h+arg_60]
0x180011e4f  mov     rcx, rbx
0x180011e52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e57  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180011e5e  test    rax, rax
0x180011e61  jz      short loc_180011E6B
0x180011e63  mov     rcx, rbx
0x180011e66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e6b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180011e72  test    rax, rax
0x180011e75  jz      short loc_180011E85
0x180011e77  test    byte ptr [rbx+4], 2
0x180011e7b  jnz     short loc_180011E85
0x180011e7d  mov     rcx, rbx
0x180011e80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e85  cmp     [rbx+8], edi
0x180011e88  jl      short loc_180011EA6
0x180011e8a  cmp     r15d, 3
0x180011e8e  jz      short loc_180011E96
0x180011e90  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180011e96  mov     ecx, 8000FFFFh; this
0x180011e9b  mov     [rbx+8], ecx
0x180011e9e  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180011ea3  mov     [rbx+0Ch], eax
0x180011ea6  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180011ead  jnz     short loc_180011ECE
0x180011eaf  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180011eb6  test    rax, rax
0x180011eb9  jz      short loc_180011EC4
0x180011ebb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ec0  test    al, al
0x180011ec2  jmp     short loc_180011ECC
0x180011ec4  call    cs:__imp_IsDebuggerPresent
0x180011eca  test    eax, eax
0x180011ecc  jz      short loc_180011ED4
0x180011ece  test    byte ptr [rbx+4], 2
0x180011ed2  jz      short loc_180011EF8
0x180011ed4  mov     rax, cs:g_pfnResultLoggingCallback
0x180011edb  test    rax, rax
0x180011ede  jz      short loc_180011F3C
0x180011ee0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180011ee7  jnz     short loc_180011F3C
0x180011ee9  xor     r8d, r8d
0x180011eec  xor     edx, edx
0x180011eee  mov     rcx, rbx
0x180011ef1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ef6  jmp     short loc_180011F3C
0x180011ef8  mov     ebp, 800h
0x180011efd  mov     rax, cs:g_pfnResultLoggingCallback
0x180011f04  test    rax, rax
0x180011f07  jz      short loc_180011F20
0x180011f09  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180011f10  jnz     short loc_180011F20
0x180011f12  mov     r8d, ebp
0x180011f15  mov     rdx, rsi
0x180011f18  mov     rcx, rbx
0x180011f1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f20  cmp     [rsi], di
0x180011f23  jnz     short loc_180011F33
0x180011f25  mov     r8, rbx; unsigned __int64
0x180011f28  mov     rdx, rbp; unsigned __int16 *
0x180011f2b  mov     rcx, rsi; this
0x180011f2e  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180011f33  mov     rcx, rsi; lpOutputString
0x180011f36  call    cs:__imp_OutputDebugStringW
0x180011f3c  test    byte ptr [rbx+4], 4
0x180011f40  jnz     short loc_180011F4B
0x180011f42  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180011f49  jz      short loc_180011F5D
0x180011f4b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180011f52  test    rax, rax
0x180011f55  jz      short loc_180011F5D
0x180011f57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f5c  nop
0x180011f5d  mov     rbx, [rsp+78h+arg_10]
0x180011f65  add     rsp, 40h
0x180011f69  pop     r15
0x180011f6b  pop     r14
0x180011f6d  pop     r13
0x180011f6f  pop     r12
0x180011f71  pop     rdi
0x180011f72  pop     rsi
0x180011f73  pop     rbp
0x180011f74  retn
```
