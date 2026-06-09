# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180005d2c`
- end: `0x180006024`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800031a8`

## callees

- `0x180002be4`
- `0x180004e14`
- `0x1800055ac`
- `0x180005d2c`
- `0x180006be0`
- `0x180006c00`
- `0x180006d28`
- `0x180006d44`
- `0x180008c7c`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005e4f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005e4f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005f6e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005f6e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005fe0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005fe0`

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
0x180005d2c  mov     [rsp+arg_10], rbx
0x180005d31  mov     [rsp+arg_8], edx
0x180005d35  mov     [rsp+arg_0], rcx
0x180005d3a  push    rbp
0x180005d3b  push    rsi
0x180005d3c  push    rdi
0x180005d3d  push    r12
0x180005d3f  push    r13
0x180005d41  push    r14
0x180005d43  push    r15
0x180005d45  sub     rsp, 40h
0x180005d49  mov     r14, [rsp+78h+arg_38]
0x180005d51  xor     eax, eax
0x180005d53  mov     rbx, [rsp+78h+arg_78]
0x180005d5b  xor     ebp, ebp
0x180005d5d  mov     r15d, [rsp+78h+arg_30]
0x180005d65  mov     r10, rcx
0x180005d68  mov     rsi, [rsp+78h+lpOutputString]
0x180005d70  mov     r12, r9
0x180005d73  mov     r13, r8
0x180005d76  mov     ecx, r15d
0x180005d79  mov     [rsi], ax
0x180005d7c  mov     rax, [rsp+78h+arg_60]
0x180005d84  mov     byte ptr [rax], 0
0x180005d87  mov     edi, [r14]
0x180005d8a  mov     [rbx+8], edi
0x180005d8d  mov     eax, [r14+4]
0x180005d91  mov     [rbx+0Ch], eax
0x180005d94  test    r15d, r15d
0x180005d97  jz      short loc_180005DFF
0x180005d99  sub     ecx, 1
0x180005d9c  jz      short loc_180005DF6
0x180005d9e  sub     ecx, 1
0x180005da1  jz      short loc_180005DB1
0x180005da3  cmp     ecx, 1
0x180005da6  jnz     short loc_180005E08
0x180005da8  mov     ecx, edi; this
0x180005daa  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180005daf  jmp     short loc_180005E06
0x180005db1  test    edi, edi
0x180005db3  js      short loc_180005DED
0x180005db5  mov     rax, [rsp+78h+arg_28]
0x180005dbd  mov     edi, 8007029Ch
0x180005dc2  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180005dc6  mov     rcx, r10; int
0x180005dc9  mov     [rsp+78h+var_50], rax; __int64
0x180005dce  mov     rax, [rsp+78h+arg_20]
0x180005dd6  mov     [rsp+78h+var_58], rax; __int64
0x180005ddb  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180005de0  mov     ecx, edi; this
0x180005de2  mov     [rbx+8], edi
0x180005de5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005dea  mov     [rbx+0Ch], eax
0x180005ded  mov     ecx, edi; this
0x180005def  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180005df4  jmp     short loc_180005E06
0x180005df6  mov     ecx, edi; this
0x180005df8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005dfd  jmp     short loc_180005E06
0x180005dff  mov     ecx, edi; this
0x180005e01  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180005e06  mov     ebp, eax
0x180005e08  mov     eax, [rsp+78h+arg_70]
0x180005e0f  mov     [rbx+4], eax
0x180005e12  mov     [rbx], r15d
0x180005e15  cmp     dword ptr [r14+8], 1
0x180005e1a  jnz     short loc_180005E22
0x180005e1c  or      eax, 8
0x180005e1f  mov     [rbx+4], eax
0x180005e22  mov     eax, 1
0x180005e27  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005e2f  inc     eax
0x180005e31  xor     edi, edi
0x180005e33  mov     [rbx+10h], eax
0x180005e36  mov     rax, [rsp+78h+arg_40]
0x180005e3e  test    rax, rax
0x180005e41  jz      short loc_180005E48
0x180005e43  cmp     [rax], di
0x180005e46  jnz     short loc_180005E4B
0x180005e48  mov     rax, rdi
0x180005e4b  mov     [rbx+18h], rax
0x180005e4f  call    cs:__imp_GetCurrentThreadId
0x180005e55  mov     [rbx+38h], r13
0x180005e59  xorps   xmm0, xmm0
0x180005e5c  mov     [rbx+20h], eax
0x180005e5f  mov     eax, [rsp+78h+arg_8]
0x180005e66  mov     [rbx+40h], eax
0x180005e69  mov     rax, [rsp+78h+arg_20]
0x180005e71  mov     [rbx+28h], rax
0x180005e75  mov     rax, [rsp+78h+arg_28]
0x180005e7d  mov     [rbx+88h], rax
0x180005e84  mov     rax, [rsp+78h+arg_0]
0x180005e8c  mov     [rbx+90h], rax
0x180005e93  xor     eax, eax
0x180005e95  mov     [rbx+44h], ebp
0x180005e98  mov     [rbx+30h], r12
0x180005e9c  mov     [rbx+48h], rdi
0x180005ea0  movups  xmmword ptr [rbx+68h], xmm0
0x180005ea4  mov     [rbx+78h], rax
0x180005ea8  movups  xmmword ptr [rbx+50h], xmm0
0x180005eac  mov     [rbx+60h], rax
0x180005eb0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005eb7  test    rax, rax
0x180005eba  jz      short loc_180005EC3
0x180005ebc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ec1  jmp     short loc_180005EC6
0x180005ec3  mov     rax, rdi
0x180005ec6  mov     [rbx+80h], rax
0x180005ecd  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005ed4  test    rax, rax
0x180005ed7  jz      short loc_180005EE1
0x180005ed9  mov     rcx, rbx
0x180005edc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ee1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005ee8  test    rax, rax
0x180005eeb  jz      short loc_180005F03
0x180005eed  mov     rdx, [rsp+78h+arg_60]
0x180005ef5  mov     r8d, 400h
0x180005efb  mov     rcx, rbx
0x180005efe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f03  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005f0a  test    rax, rax
0x180005f0d  jz      short loc_180005F17
0x180005f0f  mov     rcx, rbx
0x180005f12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f17  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005f1e  test    rax, rax
0x180005f21  jz      short loc_180005F31
0x180005f23  test    byte ptr [rbx+4], 2
0x180005f27  jnz     short loc_180005F31
0x180005f29  mov     rcx, rbx
0x180005f2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f31  cmp     [rbx+8], edi
0x180005f34  jl      short loc_180005F50
0x180005f36  cmp     r15d, 3
0x180005f3a  jnz     loc_18000601E
0x180005f40  mov     ecx, 8000FFFFh; this
0x180005f45  mov     [rbx+8], ecx
0x180005f48  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005f4d  mov     [rbx+0Ch], eax
0x180005f50  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180005f57  jnz     short loc_180005F78
0x180005f59  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005f60  test    rax, rax
0x180005f63  jz      short loc_180005F6E
0x180005f65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f6a  test    al, al
0x180005f6c  jmp     short loc_180005F76
0x180005f6e  call    cs:__imp_IsDebuggerPresent
0x180005f74  test    eax, eax
0x180005f76  jz      short loc_180005F7E
0x180005f78  test    byte ptr [rbx+4], 2
0x180005f7c  jz      short loc_180005FA2
0x180005f7e  mov     rax, cs:g_pfnResultLoggingCallback
0x180005f85  test    rax, rax
0x180005f88  jz      short loc_180005FE6
0x180005f8a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005f91  jnz     short loc_180005FE6
0x180005f93  xor     r8d, r8d
0x180005f96  xor     edx, edx
0x180005f98  mov     rcx, rbx
0x180005f9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fa0  jmp     short loc_180005FE6
0x180005fa2  mov     rax, cs:g_pfnResultLoggingCallback
0x180005fa9  mov     ebp, 800h
0x180005fae  test    rax, rax
0x180005fb1  jz      short loc_180005FCA
0x180005fb3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005fba  jnz     short loc_180005FCA
0x180005fbc  mov     r8d, ebp
0x180005fbf  mov     rdx, rsi
0x180005fc2  mov     rcx, rbx
0x180005fc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fca  cmp     [rsi], di
0x180005fcd  jnz     short loc_180005FDD
0x180005fcf  mov     r8, rbx; unsigned __int64
0x180005fd2  mov     rdx, rbp; unsigned __int16 *
0x180005fd5  mov     rcx, rsi; this
0x180005fd8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005fdd  mov     rcx, rsi; lpOutputString
0x180005fe0  call    cs:__imp_OutputDebugStringW
0x180005fe6  test    byte ptr [rbx+4], 4
0x180005fea  jnz     short loc_180005FF5
0x180005fec  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180005ff3  jz      short loc_180006006
0x180005ff5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005ffc  test    rax, rax
0x180005fff  jz      short loc_180006006
0x180006001  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006006  mov     rbx, [rsp+78h+arg_10]
0x18000600e  add     rsp, 40h
0x180006012  pop     r15
0x180006014  pop     r14
0x180006016  pop     r13
0x180006018  pop     r12
0x18000601a  pop     rdi
0x18000601b  pop     rsi
0x18000601c  pop     rbp
0x18000601d  retn
0x18000601e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
