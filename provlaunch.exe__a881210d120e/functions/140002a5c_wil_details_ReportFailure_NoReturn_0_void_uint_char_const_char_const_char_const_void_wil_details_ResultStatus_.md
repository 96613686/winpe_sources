# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x140002a5c`
- end: `0x140002d08`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `684`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x14000240c`

## callees

- `0x140002a5c`
- `0x1400042f4`
- `0x1400051e4`
- `0x140005ddc`
- `0x140006100`
- `0x140006474`
- `0x14000a33e`
- `0x14000a430`
- `0x14000b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002b05`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002b05`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140002c00`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140002c00`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140002c9c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140002c9c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  bool v10; // r12
  int v11; // ebx
  int v12; // ecx
  __int64 v13; // rdx
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  char v18; // bl
  const struct wil::FailureInfo *v19; // rdx
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v27; // [rsp+48h] [rbp-B8h]
  __int64 v28; // [rsp+50h] [rbp-B0h]
  __int64 v29; // [rsp+58h] [rbp-A8h]
  int v30; // [rsp+60h] [rbp-A0h]
  int v31; // [rsp+64h] [rbp-9Ch]
  __int64 v32; // [rsp+68h] [rbp-98h]
  __int128 v33; // [rsp+70h] [rbp-90h]
  __int64 v34; // [rsp+80h] [rbp-80h]
  __int128 v35; // [rsp+88h] [rbp-78h]
  __int64 v36; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v38; // [rsp+A8h] [rbp-58h]
  __int64 v39; // [rsp+B0h] [rbp-50h]
  char v40[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v10 = g_pfnThrowPlatformException != 0;
  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v22 = *a7;
  v23 = a7[1];
  v11 = wil::details::RecordException((wil::details *)(unsigned int)v22, (int)a7);
  v20 = 0;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  v21 = v12;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v25 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v30 = a2;
  v31 = v11;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v36 = 0;
  v33 = 0;
  v34 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && !v10 && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v18 = 1, (v21 & 2) != 0) )
  {
    v18 = 0;
  }
  if ( v10 || v18 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048, v16);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v20, v16);
    if ( v18 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v20, 0, 0, v16);
  }
  if ( ((v21 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v21 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v20, v14);
  if ( v10 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v20, OutputString);
  wil::ThrowResultException((wil *)&v20, v14);
  wil::details::WilFailFast((wil::details *)&v20, v19);
}

```

## disassembly

```asm
0x140002a5c  mov     [rsp-8+arg_18], rbx
0x140002a61  push    rbp
0x140002a62  push    rsi
0x140002a63  push    rdi
0x140002a64  push    r12
0x140002a66  push    r13
0x140002a68  push    r14
0x140002a6a  push    r15
0x140002a6c  lea     rbp, [rsp-13C0h]
0x140002a74  mov     eax, 14C0h
0x140002a79  call    _alloca_probe
0x140002a7e  sub     rsp, rax
0x140002a81  mov     r14, r8
0x140002a84  mov     esi, edx
0x140002a86  mov     r15, rcx
0x140002a89  mov     rdi, [rbp+13F0h+arg_28]
0x140002a90  xor     r13d, r13d
0x140002a93  cmp     cs:g_pfnThrowPlatformException, r13
0x140002a9a  setnz   r12b
0x140002a9e  xor     edx, edx; Val
0x140002aa0  mov     r8d, 98h; Size
0x140002aa6  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x140002aab  call    memset_0
0x140002ab0  nop
0x140002ab1  mov     [rbp+13F0h+OutputString], r13w
0x140002ab9  mov     [rbp+13F0h+var_1430], r13b
0x140002abd  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x140002ac4  mov     ecx, [rdx]; this
0x140002ac6  mov     [rsp+14F0h+var_14C8], ecx
0x140002aca  mov     eax, [rdx+4]
0x140002acd  mov     [rsp+14F0h+var_14C4], eax
0x140002ad1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140002ad6  mov     ebx, eax
0x140002ad8  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x140002add  mov     ecx, r13d
0x140002ae0  lea     eax, [r13+8]
0x140002ae4  cmp     dword ptr [rdx+8], 1
0x140002ae8  cmovz   ecx, eax
0x140002aeb  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x140002aef  lea     ecx, [rax-7]
0x140002af2  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140002afa  inc     ecx
0x140002afc  mov     [rsp+14F0h+var_14C0], ecx
0x140002b00  mov     [rsp+14F0h+var_14B8], r13
0x140002b05  call    cs:__imp_GetCurrentThreadId
0x140002b0b  mov     [rsp+14F0h+var_14B0], eax
0x140002b0f  mov     [rsp+14F0h+var_1498], r14
0x140002b14  mov     [rsp+14F0h+var_1490], esi
0x140002b18  mov     [rsp+14F0h+var_148C], ebx
0x140002b1c  mov     [rsp+14F0h+var_14A8], r13
0x140002b21  mov     [rsp+14F0h+var_14A0], r13
0x140002b26  mov     [rbp+13F0h+var_1448], rdi
0x140002b2a  mov     [rbp+13F0h+var_1440], r15
0x140002b2e  mov     [rsp+14F0h+var_1488], r13
0x140002b33  xorps   xmm0, xmm0
0x140002b36  xor     eax, eax
0x140002b38  movups  [rbp+13F0h+var_1468], xmm0
0x140002b3c  mov     [rbp+13F0h+var_1458], rax
0x140002b40  xorps   xmm1, xmm1
0x140002b43  movups  [rsp+14F0h+var_1480], xmm1
0x140002b48  mov     [rbp+13F0h+var_1470], rax
0x140002b4c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140002b53  test    rax, rax
0x140002b56  jz      short loc_140002B63
0x140002b58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002b5d  mov     [rbp+13F0h+var_1450], rax
0x140002b61  jmp     short loc_140002B67
0x140002b63  mov     [rbp+13F0h+var_1450], r13
0x140002b67  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140002b6e  test    rax, rax
0x140002b71  jz      short loc_140002B7D
0x140002b73  lea     rcx, [rsp+14F0h+var_14D0]
0x140002b78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002b7d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140002b84  test    rax, rax
0x140002b87  jz      short loc_140002B9D
0x140002b89  mov     r8d, 400h
0x140002b8f  lea     rdx, [rbp+13F0h+var_1430]
0x140002b93  lea     rcx, [rsp+14F0h+var_14D0]
0x140002b98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002b9d  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002ba4  test    rax, rax
0x140002ba7  jz      short loc_140002BB3
0x140002ba9  lea     rcx, [rsp+14F0h+var_14D0]
0x140002bae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002bb3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002bba  test    rax, rax
0x140002bbd  jz      short loc_140002BD5
0x140002bbf  test    r12b, r12b
0x140002bc2  jnz     short loc_140002BD5
0x140002bc4  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140002bc9  jnz     short loc_140002BD5
0x140002bcb  lea     rcx, [rsp+14F0h+var_14D0]
0x140002bd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002bd5  cmp     [rsp+14F0h+var_14C8], r13d
0x140002bda  jl      short loc_140002BE2
0x140002bdc  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140002be2  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x140002be9  jnz     short loc_140002C0A
0x140002beb  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140002bf2  test    rax, rax
0x140002bf5  jz      short loc_140002C00
0x140002bf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002bfc  test    al, al
0x140002bfe  jmp     short loc_140002C08
0x140002c00  call    cs:__imp_IsDebuggerPresent
0x140002c06  test    eax, eax
0x140002c08  jz      short loc_140002C13
0x140002c0a  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140002c0f  mov     bl, 1
0x140002c11  jz      short loc_140002C16
0x140002c13  mov     bl, r13b
0x140002c16  test    r12b, r12b
0x140002c19  jnz     short loc_140002C45
0x140002c1b  test    bl, bl
0x140002c1d  jnz     short loc_140002C45
0x140002c1f  mov     rax, cs:g_pfnResultLoggingCallback
0x140002c26  test    rax, rax
0x140002c29  jz      short loc_140002CA2
0x140002c2b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140002c32  jnz     short loc_140002CA2
0x140002c34  xor     r8d, r8d
0x140002c37  xor     edx, edx
0x140002c39  lea     rcx, [rsp+14F0h+var_14D0]
0x140002c3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002c43  jmp     short loc_140002CA2
0x140002c45  mov     edi, 800h
0x140002c4a  mov     rax, cs:g_pfnResultLoggingCallback
0x140002c51  test    rax, rax
0x140002c54  jz      short loc_140002C73
0x140002c56  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140002c5d  jnz     short loc_140002C73
0x140002c5f  mov     r8d, edi
0x140002c62  lea     rdx, [rbp+13F0h+OutputString]
0x140002c69  lea     rcx, [rsp+14F0h+var_14D0]
0x140002c6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002c73  cmp     [rbp+13F0h+OutputString], r13w
0x140002c7b  jnz     short loc_140002C91
0x140002c7d  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x140002c82  mov     rdx, rdi; unsigned __int16 *
0x140002c85  lea     rcx, [rbp+13F0h+OutputString]; this
0x140002c8c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140002c91  test    bl, bl
0x140002c93  jz      short loc_140002CA2
0x140002c95  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x140002c9c  call    cs:__imp_OutputDebugStringW
0x140002ca2  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x140002ca7  jnz     short loc_140002CB2
0x140002ca9  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x140002cb0  jz      short loc_140002CC4
0x140002cb2  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140002cb9  test    rax, rax
0x140002cbc  jz      short loc_140002CC4
0x140002cbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002cc3  nop
0x140002cc4  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x140002cc9  jz      short loc_140002CD6
0x140002ccb  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140002cd0  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x140002cd6  test    r12b, r12b
0x140002cd9  jz      short loc_140002CF3
0x140002cdb  lea     rdx, [rbp+13F0h+OutputString]
0x140002ce2  lea     rcx, [rsp+14F0h+var_14D0]
0x140002ce7  mov     rax, cs:g_pfnThrowPlatformException
0x140002cee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002cf3  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140002cf8  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x140002cfd  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140002d02  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
