# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140007c9c`
- end: `0x140007fa8`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `780`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140003df0`

## callees

- `0x1400034f8`
- `0x140006d84`
- `0x14000764c`
- `0x140007c9c`
- `0x14000adbc`
- `0x14000ade0`
- `0x14000adf4`
- `0x14000ae14`
- `0x14000bfc4`
- `0x14001a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140007dbf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140007dbf`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140007f5c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140007f5c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140007ee4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140007ee4`

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
0x140007c9c  mov     [rsp+arg_10], rbx
0x140007ca1  mov     [rsp+arg_8], edx
0x140007ca5  mov     [rsp+arg_0], rcx
0x140007caa  push    rbp
0x140007cab  push    rsi
0x140007cac  push    rdi
0x140007cad  push    r12
0x140007caf  push    r13
0x140007cb1  push    r14
0x140007cb3  push    r15
0x140007cb5  sub     rsp, 40h
0x140007cb9  mov     r12, r9
0x140007cbc  mov     r13, r8
0x140007cbf  mov     r10, rcx
0x140007cc2  xor     eax, eax
0x140007cc4  mov     rsi, [rsp+78h+lpOutputString]
0x140007ccc  mov     [rsi], ax
0x140007ccf  mov     rax, [rsp+78h+arg_60]
0x140007cd7  mov     byte ptr [rax], 0
0x140007cda  mov     r14, [rsp+78h+arg_38]
0x140007ce2  mov     edi, [r14]
0x140007ce5  mov     rbx, [rsp+78h+arg_78]
0x140007ced  mov     [rbx+8], edi
0x140007cf0  mov     eax, [r14+4]
0x140007cf4  mov     [rbx+0Ch], eax
0x140007cf7  xor     ebp, ebp
0x140007cf9  mov     r15d, [rsp+78h+arg_30]
0x140007d01  mov     ecx, r15d
0x140007d04  test    r15d, r15d
0x140007d07  jz      short loc_140007D6F
0x140007d09  sub     ecx, 1
0x140007d0c  jz      short loc_140007D66
0x140007d0e  sub     ecx, 1
0x140007d11  jz      short loc_140007D21
0x140007d13  cmp     ecx, 1
0x140007d16  jnz     short loc_140007D78
0x140007d18  mov     ecx, edi; this
0x140007d1a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140007d1f  jmp     short loc_140007D76
0x140007d21  test    edi, edi
0x140007d23  js      short loc_140007D5D
0x140007d25  mov     edi, 8007029Ch
0x140007d2a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x140007d2e  mov     rax, [rsp+78h+arg_28]
0x140007d36  mov     [rsp+78h+var_50], rax; __int64
0x140007d3b  mov     rax, [rsp+78h+arg_20]
0x140007d43  mov     [rsp+78h+var_58], rax; __int64
0x140007d48  mov     rcx, r10; int
0x140007d4b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140007d50  mov     [rbx+8], edi
0x140007d53  mov     ecx, edi; this
0x140007d55  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140007d5a  mov     [rbx+0Ch], eax
0x140007d5d  mov     ecx, edi; this
0x140007d5f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140007d64  jmp     short loc_140007D76
0x140007d66  mov     ecx, edi; this
0x140007d68  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140007d6d  jmp     short loc_140007D76
0x140007d6f  mov     ecx, edi; this
0x140007d71  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140007d76  mov     ebp, eax
0x140007d78  mov     [rbx], r15d
0x140007d7b  mov     eax, [rsp+78h+arg_70]
0x140007d82  mov     [rbx+4], eax
0x140007d85  cmp     dword ptr [r14+8], 1
0x140007d8a  jnz     short loc_140007D92
0x140007d8c  or      eax, 8
0x140007d8f  mov     [rbx+4], eax
0x140007d92  mov     eax, 1
0x140007d97  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140007d9f  inc     eax
0x140007da1  mov     [rbx+10h], eax
0x140007da4  mov     rax, [rsp+78h+arg_40]
0x140007dac  xor     edi, edi
0x140007dae  test    rax, rax
0x140007db1  jz      short loc_140007DB8
0x140007db3  cmp     [rax], di
0x140007db6  jnz     short loc_140007DBB
0x140007db8  mov     rax, rdi
0x140007dbb  mov     [rbx+18h], rax
0x140007dbf  call    cs:__imp_GetCurrentThreadId
0x140007dc6  nop     dword ptr [rax+rax+00h]
0x140007dcb  mov     [rbx+20h], eax
0x140007dce  mov     [rbx+38h], r13
0x140007dd2  mov     eax, [rsp+78h+arg_8]
0x140007dd9  mov     [rbx+40h], eax
0x140007ddc  mov     [rbx+44h], ebp
0x140007ddf  mov     rax, [rsp+78h+arg_20]
0x140007de7  mov     [rbx+28h], rax
0x140007deb  mov     [rbx+30h], r12
0x140007def  mov     rax, [rsp+78h+arg_28]
0x140007df7  mov     [rbx+88h], rax
0x140007dfe  mov     rax, [rsp+78h+arg_0]
0x140007e06  mov     [rbx+90h], rax
0x140007e0d  mov     [rbx+48h], rdi
0x140007e11  xorps   xmm0, xmm0
0x140007e14  xor     eax, eax
0x140007e16  movups  xmmword ptr [rbx+68h], xmm0
0x140007e1a  mov     [rbx+78h], rax
0x140007e1e  movups  xmmword ptr [rbx+50h], xmm0
0x140007e22  mov     [rbx+60h], rax
0x140007e26  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140007e2d  test    rax, rax
0x140007e30  jz      short loc_140007E39
0x140007e32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007e37  jmp     short loc_140007E3C
0x140007e39  mov     rax, rdi
0x140007e3c  mov     [rbx+80h], rax
0x140007e43  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140007e4a  test    rax, rax
0x140007e4d  jz      short loc_140007E57
0x140007e4f  mov     rcx, rbx
0x140007e52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007e57  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140007e5e  test    rax, rax
0x140007e61  jz      short loc_140007E79
0x140007e63  mov     r8d, 400h
0x140007e69  mov     rdx, [rsp+78h+arg_60]
0x140007e71  mov     rcx, rbx
0x140007e74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007e79  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140007e80  test    rax, rax
0x140007e83  jz      short loc_140007E8D
0x140007e85  mov     rcx, rbx
0x140007e88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007e8d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140007e94  test    rax, rax
0x140007e97  jz      short loc_140007EA7
0x140007e99  test    byte ptr [rbx+4], 2
0x140007e9d  jnz     short loc_140007EA7
0x140007e9f  mov     rcx, rbx
0x140007ea2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007ea7  cmp     [rbx+8], edi
0x140007eaa  jl      short loc_140007EC6
0x140007eac  cmp     r15d, 3
0x140007eb0  jnz     loc_140007FA2
0x140007eb6  mov     ecx, 8000FFFFh; this
0x140007ebb  mov     [rbx+8], ecx
0x140007ebe  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140007ec3  mov     [rbx+0Ch], eax
0x140007ec6  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x140007ecd  jnz     short loc_140007EF4
0x140007ecf  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140007ed6  test    rax, rax
0x140007ed9  jz      short loc_140007EE4
0x140007edb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007ee0  test    al, al
0x140007ee2  jmp     short loc_140007EF2
0x140007ee4  call    cs:__imp_IsDebuggerPresent
0x140007eeb  nop     dword ptr [rax+rax+00h]
0x140007ef0  test    eax, eax
0x140007ef2  jz      short loc_140007EFA
0x140007ef4  test    byte ptr [rbx+4], 2
0x140007ef8  jz      short loc_140007F1E
0x140007efa  mov     rax, cs:g_pfnResultLoggingCallback
0x140007f01  test    rax, rax
0x140007f04  jz      short loc_140007F68
0x140007f06  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140007f0d  jnz     short loc_140007F68
0x140007f0f  xor     r8d, r8d
0x140007f12  xor     edx, edx
0x140007f14  mov     rcx, rbx
0x140007f17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007f1c  jmp     short loc_140007F68
0x140007f1e  mov     ebp, 800h
0x140007f23  mov     rax, cs:g_pfnResultLoggingCallback
0x140007f2a  test    rax, rax
0x140007f2d  jz      short loc_140007F46
0x140007f2f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140007f36  jnz     short loc_140007F46
0x140007f38  mov     r8d, ebp
0x140007f3b  mov     rdx, rsi
0x140007f3e  mov     rcx, rbx
0x140007f41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007f46  cmp     [rsi], di
0x140007f49  jnz     short loc_140007F59
0x140007f4b  mov     r8, rbx; unsigned __int64
0x140007f4e  mov     rdx, rbp; unsigned __int16 *
0x140007f51  mov     rcx, rsi; this
0x140007f54  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140007f59  mov     rcx, rsi; lpOutputString
0x140007f5c  call    cs:__imp_OutputDebugStringW
0x140007f63  nop     dword ptr [rax+rax+00h]
0x140007f68  test    byte ptr [rbx+4], 4
0x140007f6c  jnz     short loc_140007F77
0x140007f6e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x140007f75  jz      short loc_140007F89
0x140007f77  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140007f7e  test    rax, rax
0x140007f81  jz      short loc_140007F89
0x140007f83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007f88  nop
0x140007f89  mov     rbx, [rsp+78h+arg_10]
0x140007f91  add     rsp, 40h
0x140007f95  pop     r15
0x140007f97  pop     r14
0x140007f99  pop     r13
0x140007f9b  pop     r12
0x140007f9d  pop     rdi
0x140007f9e  pop     rsi
0x140007f9f  pop     rbp
0x140007fa0  retn
0x140007fa2  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
