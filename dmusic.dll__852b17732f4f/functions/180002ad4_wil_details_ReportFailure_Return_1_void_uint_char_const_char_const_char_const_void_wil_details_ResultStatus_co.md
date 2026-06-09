# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180002ad4`
- end: `0x180002d61`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800025ac`

## callees

- `0x1800016d0`
- `0x1800021a8`
- `0x180002ad4`
- `0x180004de4`
- `0x1800068d8`
- `0x180008cf0`
- `0x180008ebc`
- `0x180021750`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002b82`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002b82`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002c76`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002c76`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002d00`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002d00`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v10; // ebx
  int v11; // ecx
  __int64 v12; // rdx
  const struct wil::FailureInfo *v13; // rdx
  wil::details::in1diag3 *v14; // rcx
  const struct wil::FailureInfo *v15; // r9
  bool v16; // zf
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh]
  int v19; // [rsp+28h] [rbp-D8h]
  int v20; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v21; // [rsp+30h] [rbp-D0h]
  __int64 v22; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v24; // [rsp+48h] [rbp-B8h]
  __int64 v25; // [rsp+50h] [rbp-B0h]
  __int64 v26; // [rsp+58h] [rbp-A8h]
  int v27; // [rsp+60h] [rbp-A0h]
  int v28; // [rsp+64h] [rbp-9Ch]
  __int64 v29; // [rsp+68h] [rbp-98h]
  __int128 v30; // [rsp+70h] [rbp-90h]
  __int64 v31; // [rsp+80h] [rbp-80h]
  __int128 v32; // [rsp+88h] [rbp-78h]
  __int64 v33; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v35; // [rsp+A8h] [rbp-58h]
  __int64 v36; // [rsp+B0h] [rbp-50h]
  char v37[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v17, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
  v19 = *a7;
  v20 = a7[1];
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v19, (int)a7);
  v17 = 1;
  v11 = 0;
  if ( *(_DWORD *)(v12 + 8) == 1 )
    v11 = 8;
  v18 = v11;
  v21 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v26 = a3;
  v27 = a2;
  v28 = v10;
  v24 = 0;
  v25 = 0;
  v35 = a6;
  v36 = a1;
  v29 = 0;
  v32 = 0;
  v33 = 0;
  v30 = 0;
  v31 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v14);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v17);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v17, v37, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v17);
  if ( wil::details::g_pfnOriginateCallback && (v18 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v17);
  if ( v19 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v14);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v16 = !IsDebuggerPresent())
      : (v16 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v14) == 0),
        v16)
    || (v18 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v17, v15);
    OutputDebugStringW(OutputString);
  }
  if ( ((v18 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v14);
  if ( (v18 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v17, v13);
}

```

## disassembly

```asm
0x180002ad4  push    rbp
0x180002ad6  push    rbx
0x180002ad7  push    rsi
0x180002ad8  push    rdi
0x180002ad9  push    r12
0x180002adb  push    r14
0x180002add  push    r15
0x180002adf  lea     rbp, [rsp-13D0h]
0x180002ae7  mov     eax, 14D0h
0x180002aec  call    _alloca_probe
0x180002af1  sub     rsp, rax
0x180002af4  mov     rax, cs:__security_cookie
0x180002afb  xor     rax, rsp
0x180002afe  mov     [rbp+1400h+var_40], rax
0x180002b05  mov     r14, r8
0x180002b08  mov     esi, edx
0x180002b0a  mov     r15, rcx
0x180002b0d  mov     rdi, [rbp+1400h+arg_28]
0x180002b14  xor     edx, edx; Val
0x180002b16  mov     r8d, 98h; Size
0x180002b1c  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180002b21  call    memset_0
0x180002b26  nop
0x180002b27  xor     r12d, r12d
0x180002b2a  mov     [rbp+1400h+OutputString], r12w
0x180002b32  mov     [rbp+1400h+var_1440], r12b
0x180002b36  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180002b3d  mov     ecx, [rdx]; this
0x180002b3f  mov     [rsp+1500h+var_14D8], ecx
0x180002b43  mov     eax, [rdx+4]
0x180002b46  mov     [rsp+1500h+var_14D4], eax
0x180002b4a  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180002b4f  mov     ebx, eax
0x180002b51  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180002b59  mov     ecx, r12d
0x180002b5c  lea     eax, [r12+8]
0x180002b61  cmp     dword ptr [rdx+8], 1
0x180002b65  cmovz   ecx, eax
0x180002b68  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180002b6c  lea     ecx, [rax-7]
0x180002b6f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002b77  inc     ecx
0x180002b79  mov     [rsp+1500h+var_14D0], ecx
0x180002b7d  mov     [rsp+1500h+var_14C8], r12
0x180002b82  call    cs:__imp_GetCurrentThreadId
0x180002b88  mov     [rsp+1500h+var_14C0], eax
0x180002b8c  mov     [rsp+1500h+var_14A8], r14
0x180002b91  mov     [rsp+1500h+var_14A0], esi
0x180002b95  mov     [rsp+1500h+var_149C], ebx
0x180002b99  mov     [rsp+1500h+var_14B8], r12
0x180002b9e  mov     [rsp+1500h+var_14B0], r12
0x180002ba3  mov     [rbp+1400h+var_1458], rdi
0x180002ba7  mov     [rbp+1400h+var_1450], r15
0x180002bab  mov     [rsp+1500h+var_1498], r12
0x180002bb0  xorps   xmm0, xmm0
0x180002bb3  xor     eax, eax
0x180002bb5  movups  [rbp+1400h+var_1478], xmm0
0x180002bb9  mov     [rbp+1400h+var_1468], rax
0x180002bbd  xorps   xmm1, xmm1
0x180002bc0  movups  [rsp+1500h+var_1490], xmm1
0x180002bc5  mov     [rbp+1400h+var_1480], rax
0x180002bc9  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002bd0  test    rax, rax
0x180002bd3  jz      short loc_180002BE0
0x180002bd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bda  mov     [rbp+1400h+var_1460], rax
0x180002bde  jmp     short loc_180002BE4
0x180002be0  mov     [rbp+1400h+var_1460], r12
0x180002be4  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002beb  test    rax, rax
0x180002bee  jz      short loc_180002BFA
0x180002bf0  lea     rcx, [rsp+1500h+var_14E0]
0x180002bf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bfa  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002c01  test    rax, rax
0x180002c04  jz      short loc_180002C1A
0x180002c06  mov     r8d, 400h
0x180002c0c  lea     rdx, [rbp+1400h+var_1440]
0x180002c10  lea     rcx, [rsp+1500h+var_14E0]
0x180002c15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c1a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002c21  test    rax, rax
0x180002c24  jz      short loc_180002C30
0x180002c26  lea     rcx, [rsp+1500h+var_14E0]
0x180002c2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c30  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002c37  test    rax, rax
0x180002c3a  jz      short loc_180002C4D
0x180002c3c  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180002c41  jnz     short loc_180002C4D
0x180002c43  lea     rcx, [rsp+1500h+var_14E0]
0x180002c48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c4d  cmp     [rsp+1500h+var_14D8], r12d
0x180002c52  jge     loc_180002D5B
0x180002c58  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180002c5f  jnz     short loc_180002C80
0x180002c61  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002c68  test    rax, rax
0x180002c6b  jz      short loc_180002C76
0x180002c6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c72  test    al, al
0x180002c74  jmp     short loc_180002C7E
0x180002c76  call    cs:__imp_IsDebuggerPresent
0x180002c7c  test    eax, eax
0x180002c7e  jz      short loc_180002C87
0x180002c80  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180002c85  jz      short loc_180002CAD
0x180002c87  mov     rax, cs:g_pfnResultLoggingCallback
0x180002c8e  test    rax, rax
0x180002c91  jz      short loc_180002D06
0x180002c93  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180002c9a  jnz     short loc_180002D06
0x180002c9c  xor     r8d, r8d
0x180002c9f  xor     edx, edx
0x180002ca1  lea     rcx, [rsp+1500h+var_14E0]
0x180002ca6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cab  jmp     short loc_180002D06
0x180002cad  mov     ebx, 800h
0x180002cb2  mov     rax, cs:g_pfnResultLoggingCallback
0x180002cb9  test    rax, rax
0x180002cbc  jz      short loc_180002CDB
0x180002cbe  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180002cc5  jnz     short loc_180002CDB
0x180002cc7  mov     r8d, ebx
0x180002cca  lea     rdx, [rbp+1400h+OutputString]
0x180002cd1  lea     rcx, [rsp+1500h+var_14E0]
0x180002cd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cdb  cmp     [rbp+1400h+OutputString], r12w
0x180002ce3  jnz     short loc_180002CF9
0x180002ce5  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180002cea  mov     rdx, rbx; unsigned __int16 *
0x180002ced  lea     rcx, [rbp+1400h+OutputString]; this
0x180002cf4  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002cf9  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180002d00  call    cs:__imp_OutputDebugStringW
0x180002d06  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180002d0b  jnz     short loc_180002D16
0x180002d0d  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180002d14  jz      short loc_180002D28
0x180002d16  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002d1d  test    rax, rax
0x180002d20  jz      short loc_180002D28
0x180002d22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d27  nop
0x180002d28  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180002d2d  jnz     short loc_180002D50
0x180002d2f  mov     rcx, [rbp+1400h+var_40]
0x180002d36  xor     rcx, rsp; StackCookie
0x180002d39  call    __security_check_cookie
0x180002d3e  add     rsp, 14D0h
0x180002d45  pop     r15
0x180002d47  pop     r14
0x180002d49  pop     r12
0x180002d4b  pop     rdi
0x180002d4c  pop     rsi
0x180002d4d  pop     rbx
0x180002d4e  pop     rbp
0x180002d4f  retn
0x180002d50  lea     rcx, [rsp+1500h+var_14E0]; this
0x180002d55  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180002d5b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
