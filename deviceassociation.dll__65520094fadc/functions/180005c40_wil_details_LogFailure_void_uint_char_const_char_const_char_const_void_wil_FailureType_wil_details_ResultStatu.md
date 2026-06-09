# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180005c40`
- end: `0x180005f38`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800038d4`

## callees

- `0x180003310`
- `0x1800052e4`
- `0x180005a7c`
- `0x180005c40`
- `0x180006628`
- `0x180006650`
- `0x180006778`
- `0x180006794`
- `0x18000843c`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005d63`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005d63`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005ef4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005ef4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005e82`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005e82`

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
0x180005c40  mov     [rsp+arg_10], rbx
0x180005c45  mov     [rsp+arg_8], edx
0x180005c49  mov     [rsp+arg_0], rcx
0x180005c4e  push    rbp
0x180005c4f  push    rsi
0x180005c50  push    rdi
0x180005c51  push    r12
0x180005c53  push    r13
0x180005c55  push    r14
0x180005c57  push    r15
0x180005c59  sub     rsp, 40h
0x180005c5d  mov     r14, [rsp+78h+arg_38]
0x180005c65  xor     eax, eax
0x180005c67  mov     rbx, [rsp+78h+arg_78]
0x180005c6f  xor     ebp, ebp
0x180005c71  mov     r15d, [rsp+78h+arg_30]
0x180005c79  mov     r10, rcx
0x180005c7c  mov     rsi, [rsp+78h+lpOutputString]
0x180005c84  mov     r12, r9
0x180005c87  mov     r13, r8
0x180005c8a  mov     ecx, r15d
0x180005c8d  mov     [rsi], ax
0x180005c90  mov     rax, [rsp+78h+arg_60]
0x180005c98  mov     byte ptr [rax], 0
0x180005c9b  mov     edi, [r14]
0x180005c9e  mov     [rbx+8], edi
0x180005ca1  mov     eax, [r14+4]
0x180005ca5  mov     [rbx+0Ch], eax
0x180005ca8  test    r15d, r15d
0x180005cab  jz      short loc_180005D13
0x180005cad  sub     ecx, 1
0x180005cb0  jz      short loc_180005D0A
0x180005cb2  sub     ecx, 1
0x180005cb5  jz      short loc_180005CC5
0x180005cb7  cmp     ecx, 1
0x180005cba  jnz     short loc_180005D1C
0x180005cbc  mov     ecx, edi; this
0x180005cbe  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180005cc3  jmp     short loc_180005D1A
0x180005cc5  test    edi, edi
0x180005cc7  js      short loc_180005D01
0x180005cc9  mov     rax, [rsp+78h+arg_28]
0x180005cd1  mov     edi, 8007029Ch
0x180005cd6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180005cda  mov     rcx, r10; int
0x180005cdd  mov     [rsp+78h+var_50], rax; __int64
0x180005ce2  mov     rax, [rsp+78h+arg_20]
0x180005cea  mov     [rsp+78h+var_58], rax; __int64
0x180005cef  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180005cf4  mov     ecx, edi; this
0x180005cf6  mov     [rbx+8], edi
0x180005cf9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005cfe  mov     [rbx+0Ch], eax
0x180005d01  mov     ecx, edi; this
0x180005d03  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180005d08  jmp     short loc_180005D1A
0x180005d0a  mov     ecx, edi; this
0x180005d0c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005d11  jmp     short loc_180005D1A
0x180005d13  mov     ecx, edi; this
0x180005d15  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180005d1a  mov     ebp, eax
0x180005d1c  mov     eax, [rsp+78h+arg_70]
0x180005d23  mov     [rbx+4], eax
0x180005d26  mov     [rbx], r15d
0x180005d29  cmp     dword ptr [r14+8], 1
0x180005d2e  jnz     short loc_180005D36
0x180005d30  or      eax, 8
0x180005d33  mov     [rbx+4], eax
0x180005d36  mov     eax, 1
0x180005d3b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005d43  inc     eax
0x180005d45  xor     edi, edi
0x180005d47  mov     [rbx+10h], eax
0x180005d4a  mov     rax, [rsp+78h+arg_40]
0x180005d52  test    rax, rax
0x180005d55  jz      short loc_180005D5C
0x180005d57  cmp     [rax], di
0x180005d5a  jnz     short loc_180005D5F
0x180005d5c  mov     rax, rdi
0x180005d5f  mov     [rbx+18h], rax
0x180005d63  call    cs:__imp_GetCurrentThreadId
0x180005d69  mov     [rbx+38h], r13
0x180005d6d  xorps   xmm0, xmm0
0x180005d70  mov     [rbx+20h], eax
0x180005d73  mov     eax, [rsp+78h+arg_8]
0x180005d7a  mov     [rbx+40h], eax
0x180005d7d  mov     rax, [rsp+78h+arg_20]
0x180005d85  mov     [rbx+28h], rax
0x180005d89  mov     rax, [rsp+78h+arg_28]
0x180005d91  mov     [rbx+88h], rax
0x180005d98  mov     rax, [rsp+78h+arg_0]
0x180005da0  mov     [rbx+90h], rax
0x180005da7  xor     eax, eax
0x180005da9  mov     [rbx+44h], ebp
0x180005dac  mov     [rbx+30h], r12
0x180005db0  mov     [rbx+48h], rdi
0x180005db4  movups  xmmword ptr [rbx+68h], xmm0
0x180005db8  mov     [rbx+78h], rax
0x180005dbc  movups  xmmword ptr [rbx+50h], xmm0
0x180005dc0  mov     [rbx+60h], rax
0x180005dc4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005dcb  test    rax, rax
0x180005dce  jz      short loc_180005DD7
0x180005dd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005dd5  jmp     short loc_180005DDA
0x180005dd7  mov     rax, rdi
0x180005dda  mov     [rbx+80h], rax
0x180005de1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005de8  test    rax, rax
0x180005deb  jz      short loc_180005DF5
0x180005ded  mov     rcx, rbx
0x180005df0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005df5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005dfc  test    rax, rax
0x180005dff  jz      short loc_180005E17
0x180005e01  mov     rdx, [rsp+78h+arg_60]
0x180005e09  mov     r8d, 400h
0x180005e0f  mov     rcx, rbx
0x180005e12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e17  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005e1e  test    rax, rax
0x180005e21  jz      short loc_180005E2B
0x180005e23  mov     rcx, rbx
0x180005e26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e2b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005e32  test    rax, rax
0x180005e35  jz      short loc_180005E45
0x180005e37  test    byte ptr [rbx+4], 2
0x180005e3b  jnz     short loc_180005E45
0x180005e3d  mov     rcx, rbx
0x180005e40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e45  cmp     [rbx+8], edi
0x180005e48  jl      short loc_180005E64
0x180005e4a  cmp     r15d, 3
0x180005e4e  jnz     loc_180005F32
0x180005e54  mov     ecx, 8000FFFFh; this
0x180005e59  mov     [rbx+8], ecx
0x180005e5c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005e61  mov     [rbx+0Ch], eax
0x180005e64  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180005e6b  jnz     short loc_180005E8C
0x180005e6d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005e74  test    rax, rax
0x180005e77  jz      short loc_180005E82
0x180005e79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e7e  test    al, al
0x180005e80  jmp     short loc_180005E8A
0x180005e82  call    cs:__imp_IsDebuggerPresent
0x180005e88  test    eax, eax
0x180005e8a  jz      short loc_180005E92
0x180005e8c  test    byte ptr [rbx+4], 2
0x180005e90  jz      short loc_180005EB6
0x180005e92  mov     rax, cs:g_pfnResultLoggingCallback
0x180005e99  test    rax, rax
0x180005e9c  jz      short loc_180005EFA
0x180005e9e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005ea5  jnz     short loc_180005EFA
0x180005ea7  xor     r8d, r8d
0x180005eaa  xor     edx, edx
0x180005eac  mov     rcx, rbx
0x180005eaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005eb4  jmp     short loc_180005EFA
0x180005eb6  mov     rax, cs:g_pfnResultLoggingCallback
0x180005ebd  mov     ebp, 800h
0x180005ec2  test    rax, rax
0x180005ec5  jz      short loc_180005EDE
0x180005ec7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005ece  jnz     short loc_180005EDE
0x180005ed0  mov     r8d, ebp
0x180005ed3  mov     rdx, rsi
0x180005ed6  mov     rcx, rbx
0x180005ed9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ede  cmp     [rsi], di
0x180005ee1  jnz     short loc_180005EF1
0x180005ee3  mov     r8, rbx; unsigned __int64
0x180005ee6  mov     rdx, rbp; unsigned __int16 *
0x180005ee9  mov     rcx, rsi; this
0x180005eec  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005ef1  mov     rcx, rsi; lpOutputString
0x180005ef4  call    cs:__imp_OutputDebugStringW
0x180005efa  test    byte ptr [rbx+4], 4
0x180005efe  jnz     short loc_180005F09
0x180005f00  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180005f07  jz      short loc_180005F1A
0x180005f09  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005f10  test    rax, rax
0x180005f13  jz      short loc_180005F1A
0x180005f15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f1a  mov     rbx, [rsp+78h+arg_10]
0x180005f22  add     rsp, 40h
0x180005f26  pop     r15
0x180005f28  pop     r14
0x180005f2a  pop     r13
0x180005f2c  pop     r12
0x180005f2e  pop     rdi
0x180005f2f  pop     rsi
0x180005f30  pop     rbp
0x180005f31  retn
0x180005f32  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
