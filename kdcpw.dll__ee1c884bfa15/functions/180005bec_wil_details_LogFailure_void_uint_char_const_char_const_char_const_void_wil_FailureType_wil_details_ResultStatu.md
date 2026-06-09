# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180005bec`
- end: `0x180005ee4`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180003018`

## callees

- `0x180002a54`
- `0x180004f34`
- `0x1800056cc`
- `0x180005bec`
- `0x180006a0c`
- `0x180006a30`
- `0x180006b58`
- `0x180006b74`
- `0x180008eac`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005d0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005d0f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005e2e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005e2e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005ea0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005ea0`

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
0x180005bec  mov     [rsp+arg_10], rbx
0x180005bf1  mov     [rsp+arg_8], edx
0x180005bf5  mov     [rsp+arg_0], rcx
0x180005bfa  push    rbp
0x180005bfb  push    rsi
0x180005bfc  push    rdi
0x180005bfd  push    r12
0x180005bff  push    r13
0x180005c01  push    r14
0x180005c03  push    r15
0x180005c05  sub     rsp, 40h
0x180005c09  mov     r14, [rsp+78h+arg_38]
0x180005c11  xor     eax, eax
0x180005c13  mov     rbx, [rsp+78h+arg_78]
0x180005c1b  xor     ebp, ebp
0x180005c1d  mov     r15d, [rsp+78h+arg_30]
0x180005c25  mov     r10, rcx
0x180005c28  mov     rsi, [rsp+78h+lpOutputString]
0x180005c30  mov     r12, r9
0x180005c33  mov     r13, r8
0x180005c36  mov     ecx, r15d
0x180005c39  mov     [rsi], ax
0x180005c3c  mov     rax, [rsp+78h+arg_60]
0x180005c44  mov     byte ptr [rax], 0
0x180005c47  mov     edi, [r14]
0x180005c4a  mov     [rbx+8], edi
0x180005c4d  mov     eax, [r14+4]
0x180005c51  mov     [rbx+0Ch], eax
0x180005c54  test    r15d, r15d
0x180005c57  jz      short loc_180005CBF
0x180005c59  sub     ecx, 1
0x180005c5c  jz      short loc_180005CB6
0x180005c5e  sub     ecx, 1
0x180005c61  jz      short loc_180005C71
0x180005c63  cmp     ecx, 1
0x180005c66  jnz     short loc_180005CC8
0x180005c68  mov     ecx, edi; this
0x180005c6a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180005c6f  jmp     short loc_180005CC6
0x180005c71  test    edi, edi
0x180005c73  js      short loc_180005CAD
0x180005c75  mov     rax, [rsp+78h+arg_28]
0x180005c7d  mov     edi, 8007029Ch
0x180005c82  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180005c86  mov     rcx, r10; int
0x180005c89  mov     [rsp+78h+var_50], rax; __int64
0x180005c8e  mov     rax, [rsp+78h+arg_20]
0x180005c96  mov     [rsp+78h+var_58], rax; __int64
0x180005c9b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180005ca0  mov     ecx, edi; this
0x180005ca2  mov     [rbx+8], edi
0x180005ca5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005caa  mov     [rbx+0Ch], eax
0x180005cad  mov     ecx, edi; this
0x180005caf  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180005cb4  jmp     short loc_180005CC6
0x180005cb6  mov     ecx, edi; this
0x180005cb8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005cbd  jmp     short loc_180005CC6
0x180005cbf  mov     ecx, edi; this
0x180005cc1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180005cc6  mov     ebp, eax
0x180005cc8  mov     eax, [rsp+78h+arg_70]
0x180005ccf  mov     [rbx+4], eax
0x180005cd2  mov     [rbx], r15d
0x180005cd5  cmp     dword ptr [r14+8], 1
0x180005cda  jnz     short loc_180005CE2
0x180005cdc  or      eax, 8
0x180005cdf  mov     [rbx+4], eax
0x180005ce2  mov     eax, 1
0x180005ce7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005cef  inc     eax
0x180005cf1  xor     edi, edi
0x180005cf3  mov     [rbx+10h], eax
0x180005cf6  mov     rax, [rsp+78h+arg_40]
0x180005cfe  test    rax, rax
0x180005d01  jz      short loc_180005D08
0x180005d03  cmp     [rax], di
0x180005d06  jnz     short loc_180005D0B
0x180005d08  mov     rax, rdi
0x180005d0b  mov     [rbx+18h], rax
0x180005d0f  call    cs:__imp_GetCurrentThreadId
0x180005d15  mov     [rbx+38h], r13
0x180005d19  xorps   xmm0, xmm0
0x180005d1c  mov     [rbx+20h], eax
0x180005d1f  mov     eax, [rsp+78h+arg_8]
0x180005d26  mov     [rbx+40h], eax
0x180005d29  mov     rax, [rsp+78h+arg_20]
0x180005d31  mov     [rbx+28h], rax
0x180005d35  mov     rax, [rsp+78h+arg_28]
0x180005d3d  mov     [rbx+88h], rax
0x180005d44  mov     rax, [rsp+78h+arg_0]
0x180005d4c  mov     [rbx+90h], rax
0x180005d53  xor     eax, eax
0x180005d55  mov     [rbx+44h], ebp
0x180005d58  mov     [rbx+30h], r12
0x180005d5c  mov     [rbx+48h], rdi
0x180005d60  movups  xmmword ptr [rbx+68h], xmm0
0x180005d64  mov     [rbx+78h], rax
0x180005d68  movups  xmmword ptr [rbx+50h], xmm0
0x180005d6c  mov     [rbx+60h], rax
0x180005d70  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005d77  test    rax, rax
0x180005d7a  jz      short loc_180005D83
0x180005d7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d81  jmp     short loc_180005D86
0x180005d83  mov     rax, rdi
0x180005d86  mov     [rbx+80h], rax
0x180005d8d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005d94  test    rax, rax
0x180005d97  jz      short loc_180005DA1
0x180005d99  mov     rcx, rbx
0x180005d9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005da1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005da8  test    rax, rax
0x180005dab  jz      short loc_180005DC3
0x180005dad  mov     rdx, [rsp+78h+arg_60]
0x180005db5  mov     r8d, 400h
0x180005dbb  mov     rcx, rbx
0x180005dbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005dc3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005dca  test    rax, rax
0x180005dcd  jz      short loc_180005DD7
0x180005dcf  mov     rcx, rbx
0x180005dd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005dd7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005dde  test    rax, rax
0x180005de1  jz      short loc_180005DF1
0x180005de3  test    byte ptr [rbx+4], 2
0x180005de7  jnz     short loc_180005DF1
0x180005de9  mov     rcx, rbx
0x180005dec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005df1  cmp     [rbx+8], edi
0x180005df4  jl      short loc_180005E10
0x180005df6  cmp     r15d, 3
0x180005dfa  jnz     loc_180005EDE
0x180005e00  mov     ecx, 8000FFFFh; this
0x180005e05  mov     [rbx+8], ecx
0x180005e08  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005e0d  mov     [rbx+0Ch], eax
0x180005e10  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180005e17  jnz     short loc_180005E38
0x180005e19  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005e20  test    rax, rax
0x180005e23  jz      short loc_180005E2E
0x180005e25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e2a  test    al, al
0x180005e2c  jmp     short loc_180005E36
0x180005e2e  call    cs:__imp_IsDebuggerPresent
0x180005e34  test    eax, eax
0x180005e36  jz      short loc_180005E3E
0x180005e38  test    byte ptr [rbx+4], 2
0x180005e3c  jz      short loc_180005E62
0x180005e3e  mov     rax, cs:g_pfnResultLoggingCallback
0x180005e45  test    rax, rax
0x180005e48  jz      short loc_180005EA6
0x180005e4a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005e51  jnz     short loc_180005EA6
0x180005e53  xor     r8d, r8d
0x180005e56  xor     edx, edx
0x180005e58  mov     rcx, rbx
0x180005e5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e60  jmp     short loc_180005EA6
0x180005e62  mov     rax, cs:g_pfnResultLoggingCallback
0x180005e69  mov     ebp, 800h
0x180005e6e  test    rax, rax
0x180005e71  jz      short loc_180005E8A
0x180005e73  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005e7a  jnz     short loc_180005E8A
0x180005e7c  mov     r8d, ebp
0x180005e7f  mov     rdx, rsi
0x180005e82  mov     rcx, rbx
0x180005e85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e8a  cmp     [rsi], di
0x180005e8d  jnz     short loc_180005E9D
0x180005e8f  mov     r8, rbx; unsigned __int64
0x180005e92  mov     rdx, rbp; unsigned __int16 *
0x180005e95  mov     rcx, rsi; this
0x180005e98  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005e9d  mov     rcx, rsi; lpOutputString
0x180005ea0  call    cs:__imp_OutputDebugStringW
0x180005ea6  test    byte ptr [rbx+4], 4
0x180005eaa  jnz     short loc_180005EB5
0x180005eac  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180005eb3  jz      short loc_180005EC6
0x180005eb5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005ebc  test    rax, rax
0x180005ebf  jz      short loc_180005EC6
0x180005ec1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ec6  mov     rbx, [rsp+78h+arg_10]
0x180005ece  add     rsp, 40h
0x180005ed2  pop     r15
0x180005ed4  pop     r14
0x180005ed6  pop     r13
0x180005ed8  pop     r12
0x180005eda  pop     rdi
0x180005edb  pop     rsi
0x180005edc  pop     rbp
0x180005edd  retn
0x180005ede  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
