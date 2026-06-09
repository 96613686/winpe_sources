# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000bf5c`
- end: `0x18000c202`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000554c`

## callees

- `0x18000a520`
- `0x18000aef8`
- `0x18000bf5c`
- `0x18000cea4`
- `0x18000dda0`
- `0x18000ead8`
- `0x18000ec08`
- `0x18001e520`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c022`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c022`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000c117`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000c117`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000c1a1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000c1a1`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v11; // r15d
  int v12; // ecx
  __int64 v13; // rdx
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh]
  int v20; // [rsp+28h] [rbp-D8h]
  int v21; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v22; // [rsp+30h] [rbp-D0h]
  _WORD *v23; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+48h] [rbp-B8h]
  __int64 v26; // [rsp+50h] [rbp-B0h]
  __int64 v27; // [rsp+58h] [rbp-A8h]
  int v28; // [rsp+60h] [rbp-A0h]
  int v29; // [rsp+64h] [rbp-9Ch]
  __int64 v30; // [rsp+68h] [rbp-98h]
  __int128 v31; // [rsp+70h] [rbp-90h]
  __int64 v32; // [rsp+80h] [rbp-80h]
  __int128 v33; // [rsp+88h] [rbp-78h]
  __int64 v34; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v36; // [rsp+A8h] [rbp-58h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  char v38[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v11 = wil::details::RecordReturn((wil::details *)(unsigned int)v20, (int)a7);
  v18 = 1;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  v19 = v12;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v11;
  v25 = 0;
  v26 = 0;
  v36 = a6;
  v37 = a1;
  v30 = 0;
  v33 = 0;
  v34 = 0;
  v31 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v18);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v18, v38, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v18);
  if ( wil::details::g_pfnOriginateCallback && (v19 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v18);
  if ( v20 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v19 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v18, v16);
    OutputDebugStringW(OutputString);
  }
  if ( ((v19 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v19 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x18000bf5c  push    rbp
0x18000bf5e  push    rbx
0x18000bf5f  push    rsi
0x18000bf60  push    rdi
0x18000bf61  push    r12
0x18000bf63  push    r14
0x18000bf65  push    r15
0x18000bf67  lea     rbp, [rsp-13D0h]
0x18000bf6f  mov     eax, 14D0h
0x18000bf74  call    _alloca_probe
0x18000bf79  sub     rsp, rax
0x18000bf7c  mov     rax, cs:__security_cookie
0x18000bf83  xor     rax, rsp
0x18000bf86  mov     [rbp+1400h+var_40], rax
0x18000bf8d  mov     rsi, r8
0x18000bf90  mov     edi, edx
0x18000bf92  mov     rbx, rcx
0x18000bf95  mov     r14, [rbp+1400h+arg_28]
0x18000bf9c  xor     edx, edx; Val
0x18000bf9e  mov     r8d, 98h; Size
0x18000bfa4  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18000bfa9  call    memset_0
0x18000bfae  nop
0x18000bfaf  xor     r12d, r12d
0x18000bfb2  mov     [rbp+1400h+OutputString], r12w
0x18000bfba  mov     [rbp+1400h+var_1440], r12b
0x18000bfbe  mov     rdx, [rbp+1400h+arg_30]; int
0x18000bfc5  mov     ecx, [rdx]; this
0x18000bfc7  mov     [rsp+1500h+var_14D8], ecx
0x18000bfcb  mov     eax, [rdx+4]
0x18000bfce  mov     [rsp+1500h+var_14D4], eax
0x18000bfd2  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000bfd7  mov     r15d, eax
0x18000bfda  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18000bfe2  mov     ecx, r12d
0x18000bfe5  lea     eax, [r12+8]
0x18000bfea  cmp     dword ptr [rdx+8], 1
0x18000bfee  cmovz   ecx, eax
0x18000bff1  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18000bff5  lea     ecx, [rax-7]
0x18000bff8  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000c000  inc     ecx
0x18000c002  mov     [rsp+1500h+var_14D0], ecx
0x18000c006  mov     rcx, [rbp+1400h+arg_38]
0x18000c00d  test    rcx, rcx
0x18000c010  jz      short loc_18000C01D
0x18000c012  cmp     [rcx], r12w
0x18000c016  mov     [rsp+1500h+var_14C8], rcx
0x18000c01b  jnz     short loc_18000C022
0x18000c01d  mov     [rsp+1500h+var_14C8], r12
0x18000c022  call    cs:__imp_GetCurrentThreadId
0x18000c028  mov     [rsp+1500h+var_14C0], eax
0x18000c02c  mov     [rsp+1500h+var_14A8], rsi
0x18000c031  mov     [rsp+1500h+var_14A0], edi
0x18000c035  mov     [rsp+1500h+var_149C], r15d
0x18000c03a  mov     [rsp+1500h+var_14B8], r12
0x18000c03f  mov     [rsp+1500h+var_14B0], r12
0x18000c044  mov     [rbp+1400h+var_1458], r14
0x18000c048  mov     [rbp+1400h+var_1450], rbx
0x18000c04c  mov     [rsp+1500h+var_1498], r12
0x18000c051  xorps   xmm0, xmm0
0x18000c054  xor     eax, eax
0x18000c056  movups  [rbp+1400h+var_1478], xmm0
0x18000c05a  mov     [rbp+1400h+var_1468], rax
0x18000c05e  xorps   xmm1, xmm1
0x18000c061  movups  [rsp+1500h+var_1490], xmm1
0x18000c066  mov     [rbp+1400h+var_1480], rax
0x18000c06a  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000c071  test    rax, rax
0x18000c074  jz      short loc_18000C081
0x18000c076  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c07b  mov     [rbp+1400h+var_1460], rax
0x18000c07f  jmp     short loc_18000C085
0x18000c081  mov     [rbp+1400h+var_1460], r12
0x18000c085  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000c08c  test    rax, rax
0x18000c08f  jz      short loc_18000C09B
0x18000c091  lea     rcx, [rsp+1500h+var_14E0]
0x18000c096  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c09b  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000c0a2  test    rax, rax
0x18000c0a5  jz      short loc_18000C0BB
0x18000c0a7  mov     r8d, 400h
0x18000c0ad  lea     rdx, [rbp+1400h+var_1440]
0x18000c0b1  lea     rcx, [rsp+1500h+var_14E0]
0x18000c0b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0bb  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000c0c2  test    rax, rax
0x18000c0c5  jz      short loc_18000C0D1
0x18000c0c7  lea     rcx, [rsp+1500h+var_14E0]
0x18000c0cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0d1  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000c0d8  test    rax, rax
0x18000c0db  jz      short loc_18000C0EE
0x18000c0dd  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000c0e2  jnz     short loc_18000C0EE
0x18000c0e4  lea     rcx, [rsp+1500h+var_14E0]
0x18000c0e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0ee  cmp     [rsp+1500h+var_14D8], r12d
0x18000c0f3  jge     loc_18000C1FC
0x18000c0f9  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18000c100  jnz     short loc_18000C121
0x18000c102  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000c109  test    rax, rax
0x18000c10c  jz      short loc_18000C117
0x18000c10e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c113  test    al, al
0x18000c115  jmp     short loc_18000C11F
0x18000c117  call    cs:__imp_IsDebuggerPresent
0x18000c11d  test    eax, eax
0x18000c11f  jz      short loc_18000C128
0x18000c121  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000c126  jz      short loc_18000C14E
0x18000c128  mov     rax, cs:g_pfnResultLoggingCallback
0x18000c12f  test    rax, rax
0x18000c132  jz      short loc_18000C1A7
0x18000c134  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000c13b  jnz     short loc_18000C1A7
0x18000c13d  xor     r8d, r8d
0x18000c140  xor     edx, edx
0x18000c142  lea     rcx, [rsp+1500h+var_14E0]
0x18000c147  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c14c  jmp     short loc_18000C1A7
0x18000c14e  mov     ebx, 800h
0x18000c153  mov     rax, cs:g_pfnResultLoggingCallback
0x18000c15a  test    rax, rax
0x18000c15d  jz      short loc_18000C17C
0x18000c15f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000c166  jnz     short loc_18000C17C
0x18000c168  mov     r8d, ebx
0x18000c16b  lea     rdx, [rbp+1400h+OutputString]
0x18000c172  lea     rcx, [rsp+1500h+var_14E0]
0x18000c177  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c17c  cmp     [rbp+1400h+OutputString], r12w
0x18000c184  jnz     short loc_18000C19A
0x18000c186  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18000c18b  mov     rdx, rbx; unsigned __int16 *
0x18000c18e  lea     rcx, [rbp+1400h+OutputString]; this
0x18000c195  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000c19a  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18000c1a1  call    cs:__imp_OutputDebugStringW
0x18000c1a7  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18000c1ac  jnz     short loc_18000C1B7
0x18000c1ae  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18000c1b5  jz      short loc_18000C1C9
0x18000c1b7  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000c1be  test    rax, rax
0x18000c1c1  jz      short loc_18000C1C9
0x18000c1c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1c8  nop
0x18000c1c9  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18000c1ce  jnz     short loc_18000C1F1
0x18000c1d0  mov     rcx, [rbp+1400h+var_40]
0x18000c1d7  xor     rcx, rsp; StackCookie
0x18000c1da  call    __security_check_cookie
0x18000c1df  add     rsp, 14D0h
0x18000c1e6  pop     r15
0x18000c1e8  pop     r14
0x18000c1ea  pop     r12
0x18000c1ec  pop     rdi
0x18000c1ed  pop     rsi
0x18000c1ee  pop     rbx
0x18000c1ef  pop     rbp
0x18000c1f0  retn
0x18000c1f1  lea     rcx, [rsp+1500h+var_14E0]; this
0x18000c1f6  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000c1fc  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
