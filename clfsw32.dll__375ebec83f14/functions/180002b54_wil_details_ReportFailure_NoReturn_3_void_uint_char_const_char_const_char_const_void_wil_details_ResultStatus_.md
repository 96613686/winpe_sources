# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180002b54`
- end: `0x180002dc6`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `626`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800028f0`

## callees

- `0x180002b54`
- `0x180004934`
- `0x18000513c`
- `0x180005d80`
- `0x180007c2c`
- `0x180014dce`
- `0x180014ec0`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002cfe`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002cfe`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002d8e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002d8e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002bf5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002bf5`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v10; // eax
  int v11; // edx
  int v12; // eax
  int v13; // edi
  int v14; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v16; // rdx
  __int64 v17; // rcx
  const struct wil::FailureInfo *v18; // r9
  bool v19; // zf
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD v26; // [rsp+40h] [rbp-C0h]
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

  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v10 = a7[1];
  v22 = *a7;
  v23 = v10;
  v12 = wil::details::RecordFailFast((wil::details *)(unsigned int)v22, v11);
  v19 = a7[2] == 1;
  v13 = v12;
  v20 = 3;
  v14 = 0;
  if ( v19 )
    v14 = 8;
  v21 = v14;
  v25 = 0;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v26 = CurrentThreadId;
  v30 = a2;
  v36 = 0;
  v34 = 0;
  v31 = v13;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v33 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v17);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
  {
    v22 = -2147418113;
    v23 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v16);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v19 = !IsDebuggerPresent())
      : (v19 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v17) == 0),
        v19)
    || (v21 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v20, v18);
    OutputDebugStringW(OutputString);
  }
  if ( (v21 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v17);
  }
  wil::details::WilFailFast((wil::details *)&v20, v16);
}

```

## disassembly

```asm
0x180002b54  mov     [rsp-8+arg_18], rbx
0x180002b59  push    rbp
0x180002b5a  push    rsi
0x180002b5b  push    rdi
0x180002b5c  push    r12
0x180002b5e  push    r13
0x180002b60  push    r14
0x180002b62  push    r15
0x180002b64  lea     rbp, [rsp-13C0h]
0x180002b6c  mov     eax, 14C0h
0x180002b71  call    _alloca_probe
0x180002b76  sub     rsp, rax
0x180002b79  mov     rsi, [rbp+13F0h+arg_28]
0x180002b80  mov     r15, r8
0x180002b83  mov     r14d, edx
0x180002b86  mov     r12, rcx
0x180002b89  xor     edx, edx; Val
0x180002b8b  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180002b90  mov     r8d, 98h; Size
0x180002b96  call    memset_0
0x180002b9b  mov     rbx, [rbp+13F0h+arg_30]
0x180002ba2  xor     r13d, r13d
0x180002ba5  mov     [rbp+13F0h+OutputString], r13w
0x180002bad  mov     [rbp+13F0h+var_1430], r13b
0x180002bb1  mov     ecx, [rbx]; this
0x180002bb3  mov     eax, [rbx+4]
0x180002bb6  mov     [rsp+14F0h+var_14C8], ecx
0x180002bba  mov     [rsp+14F0h+var_14C4], eax
0x180002bbe  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180002bc3  cmp     dword ptr [rbx+8], 1
0x180002bc7  mov     edi, eax
0x180002bc9  lea     eax, [r13+8]
0x180002bcd  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180002bd5  mov     ecx, r13d
0x180002bd8  cmovz   ecx, eax
0x180002bdb  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180002bdf  lea     ecx, [rax-7]
0x180002be2  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002bea  inc     ecx
0x180002bec  mov     [rsp+14F0h+var_14B8], r13
0x180002bf1  mov     [rsp+14F0h+var_14C0], ecx
0x180002bf5  call    cs:__imp_GetCurrentThreadId
0x180002bfc  nop     dword ptr [rax+rax+00h]
0x180002c01  xorps   xmm0, xmm0
0x180002c04  mov     [rsp+14F0h+var_1498], r15
0x180002c09  mov     [rsp+14F0h+var_14B0], eax
0x180002c0d  xorps   xmm1, xmm1
0x180002c10  xor     eax, eax
0x180002c12  mov     [rsp+14F0h+var_1490], r14d
0x180002c17  mov     [rbp+13F0h+var_1458], rax
0x180002c1b  mov     [rbp+13F0h+var_1470], rax
0x180002c1f  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002c26  mov     [rsp+14F0h+var_148C], edi
0x180002c2a  mov     [rsp+14F0h+var_14A8], r13
0x180002c2f  mov     [rsp+14F0h+var_14A0], r13
0x180002c34  mov     [rbp+13F0h+var_1448], rsi
0x180002c38  mov     [rbp+13F0h+var_1440], r12
0x180002c3c  mov     [rsp+14F0h+var_1488], r13
0x180002c41  movups  [rbp+13F0h+var_1468], xmm0
0x180002c45  movups  [rsp+14F0h+var_1480], xmm1
0x180002c4a  test    rax, rax
0x180002c4d  jz      short loc_180002C5A
0x180002c4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c54  mov     [rbp+13F0h+var_1450], rax
0x180002c58  jmp     short loc_180002C5E
0x180002c5a  mov     [rbp+13F0h+var_1450], r13
0x180002c5e  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002c65  test    rax, rax
0x180002c68  jz      short loc_180002C74
0x180002c6a  lea     rcx, [rsp+14F0h+var_14D0]
0x180002c6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c74  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002c7b  test    rax, rax
0x180002c7e  jz      short loc_180002C94
0x180002c80  mov     r8d, 400h
0x180002c86  lea     rdx, [rbp+13F0h+var_1430]
0x180002c8a  lea     rcx, [rsp+14F0h+var_14D0]
0x180002c8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c94  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002c9b  test    rax, rax
0x180002c9e  jz      short loc_180002CAA
0x180002ca0  lea     rcx, [rsp+14F0h+var_14D0]
0x180002ca5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002caa  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002cb1  test    rax, rax
0x180002cb4  jz      short loc_180002CC7
0x180002cb6  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002cbb  jnz     short loc_180002CC7
0x180002cbd  lea     rcx, [rsp+14F0h+var_14D0]
0x180002cc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cc7  cmp     [rsp+14F0h+var_14C8], r13d
0x180002ccc  jl      short loc_180002CE0
0x180002cce  mov     ecx, 8000FFFFh; this
0x180002cd3  mov     [rsp+14F0h+var_14C8], ecx
0x180002cd7  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180002cdc  mov     [rsp+14F0h+var_14C4], eax
0x180002ce0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180002ce7  jnz     short loc_180002D0E
0x180002ce9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002cf0  test    rax, rax
0x180002cf3  jz      short loc_180002CFE
0x180002cf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cfa  test    al, al
0x180002cfc  jmp     short loc_180002D0C
0x180002cfe  call    cs:__imp_IsDebuggerPresent
0x180002d05  nop     dword ptr [rax+rax+00h]
0x180002d0a  test    eax, eax
0x180002d0c  jz      short loc_180002D15
0x180002d0e  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002d13  jz      short loc_180002D3B
0x180002d15  mov     rax, cs:g_pfnResultLoggingCallback
0x180002d1c  test    rax, rax
0x180002d1f  jz      short loc_180002D9A
0x180002d21  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180002d28  jnz     short loc_180002D9A
0x180002d2a  xor     r8d, r8d
0x180002d2d  lea     rcx, [rsp+14F0h+var_14D0]
0x180002d32  xor     edx, edx
0x180002d34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d39  jmp     short loc_180002D9A
0x180002d3b  mov     rax, cs:g_pfnResultLoggingCallback
0x180002d42  mov     ebx, 800h
0x180002d47  test    rax, rax
0x180002d4a  jz      short loc_180002D69
0x180002d4c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180002d53  jnz     short loc_180002D69
0x180002d55  mov     r8d, ebx
0x180002d58  lea     rdx, [rbp+13F0h+OutputString]
0x180002d5f  lea     rcx, [rsp+14F0h+var_14D0]
0x180002d64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d69  cmp     [rbp+13F0h+OutputString], r13w
0x180002d71  jnz     short loc_180002D87
0x180002d73  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180002d78  mov     rdx, rbx; unsigned __int16 *
0x180002d7b  lea     rcx, [rbp+13F0h+OutputString]; this
0x180002d82  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002d87  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180002d8e  call    cs:__imp_OutputDebugStringW
0x180002d95  nop     dword ptr [rax+rax+00h]
0x180002d9a  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180002d9f  jnz     short loc_180002DAA
0x180002da1  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180002da8  jz      short loc_180002DBB
0x180002daa  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002db1  test    rax, rax
0x180002db4  jz      short loc_180002DBB
0x180002db6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dbb  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180002dc0  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
