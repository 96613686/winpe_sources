# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140002d48`
- end: `0x140002fee`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140002264`

## callees

- `0x140001470`
- `0x140001f0e`
- `0x140002d48`
- `0x140004684`
- `0x140005670`
- `0x140006bf0`
- `0x140006ccc`
- `0x140007880`
- `0x140008010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002e0e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002e0e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140002f03`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140002f03`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140002f8d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140002f8d`

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
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v18, v16);
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
0x140002d48  push    rbp
0x140002d4a  push    rbx
0x140002d4b  push    rsi
0x140002d4c  push    rdi
0x140002d4d  push    r12
0x140002d4f  push    r14
0x140002d51  push    r15
0x140002d53  lea     rbp, [rsp-13D0h]
0x140002d5b  mov     eax, 14D0h
0x140002d60  call    _alloca_probe
0x140002d65  sub     rsp, rax
0x140002d68  mov     rax, cs:__security_cookie
0x140002d6f  xor     rax, rsp
0x140002d72  mov     [rbp+1400h+var_40], rax
0x140002d79  mov     rsi, r8
0x140002d7c  mov     edi, edx
0x140002d7e  mov     rbx, rcx
0x140002d81  mov     r14, [rbp+1400h+arg_28]
0x140002d88  xor     edx, edx; Val
0x140002d8a  mov     r8d, 98h; Size
0x140002d90  lea     rcx, [rsp+1500h+var_14E0]; void *
0x140002d95  call    memset_0
0x140002d9a  nop
0x140002d9b  xor     r12d, r12d
0x140002d9e  mov     [rbp+1400h+OutputString], r12w
0x140002da6  mov     [rbp+1400h+var_1440], r12b
0x140002daa  mov     rdx, [rbp+1400h+arg_30]; int
0x140002db1  mov     ecx, [rdx]; this
0x140002db3  mov     [rsp+1500h+var_14D8], ecx
0x140002db7  mov     eax, [rdx+4]
0x140002dba  mov     [rsp+1500h+var_14D4], eax
0x140002dbe  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140002dc3  mov     r15d, eax
0x140002dc6  mov     dword ptr [rsp+1500h+var_14E0], 1
0x140002dce  mov     ecx, r12d
0x140002dd1  lea     eax, [r12+8]
0x140002dd6  cmp     dword ptr [rdx+8], 1
0x140002dda  cmovz   ecx, eax
0x140002ddd  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x140002de1  lea     ecx, [rax-7]
0x140002de4  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140002dec  inc     ecx
0x140002dee  mov     [rsp+1500h+var_14D0], ecx
0x140002df2  mov     rcx, [rbp+1400h+arg_38]
0x140002df9  test    rcx, rcx
0x140002dfc  jz      short loc_140002E09
0x140002dfe  cmp     [rcx], r12w
0x140002e02  mov     [rsp+1500h+var_14C8], rcx
0x140002e07  jnz     short loc_140002E0E
0x140002e09  mov     [rsp+1500h+var_14C8], r12
0x140002e0e  call    cs:__imp_GetCurrentThreadId
0x140002e14  mov     [rsp+1500h+var_14C0], eax
0x140002e18  mov     [rsp+1500h+var_14A8], rsi
0x140002e1d  mov     [rsp+1500h+var_14A0], edi
0x140002e21  mov     [rsp+1500h+var_149C], r15d
0x140002e26  mov     [rsp+1500h+var_14B8], r12
0x140002e2b  mov     [rsp+1500h+var_14B0], r12
0x140002e30  mov     [rbp+1400h+var_1458], r14
0x140002e34  mov     [rbp+1400h+var_1450], rbx
0x140002e38  mov     [rsp+1500h+var_1498], r12
0x140002e3d  xorps   xmm0, xmm0
0x140002e40  xor     eax, eax
0x140002e42  movups  [rbp+1400h+var_1478], xmm0
0x140002e46  mov     [rbp+1400h+var_1468], rax
0x140002e4a  xorps   xmm1, xmm1
0x140002e4d  movups  [rsp+1500h+var_1490], xmm1
0x140002e52  mov     [rbp+1400h+var_1480], rax
0x140002e56  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140002e5d  test    rax, rax
0x140002e60  jz      short loc_140002E6D
0x140002e62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002e67  mov     [rbp+1400h+var_1460], rax
0x140002e6b  jmp     short loc_140002E71
0x140002e6d  mov     [rbp+1400h+var_1460], r12
0x140002e71  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140002e78  test    rax, rax
0x140002e7b  jz      short loc_140002E87
0x140002e7d  lea     rcx, [rsp+1500h+var_14E0]
0x140002e82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002e87  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140002e8e  test    rax, rax
0x140002e91  jz      short loc_140002EA7
0x140002e93  mov     r8d, 400h
0x140002e99  lea     rdx, [rbp+1400h+var_1440]
0x140002e9d  lea     rcx, [rsp+1500h+var_14E0]
0x140002ea2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002ea7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002eae  test    rax, rax
0x140002eb1  jz      short loc_140002EBD
0x140002eb3  lea     rcx, [rsp+1500h+var_14E0]
0x140002eb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002ebd  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002ec4  test    rax, rax
0x140002ec7  jz      short loc_140002EDA
0x140002ec9  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140002ece  jnz     short loc_140002EDA
0x140002ed0  lea     rcx, [rsp+1500h+var_14E0]
0x140002ed5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002eda  cmp     [rsp+1500h+var_14D8], r12d
0x140002edf  jge     loc_140002FE8
0x140002ee5  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x140002eec  jnz     short loc_140002F0D
0x140002eee  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140002ef5  test    rax, rax
0x140002ef8  jz      short loc_140002F03
0x140002efa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002eff  test    al, al
0x140002f01  jmp     short loc_140002F0B
0x140002f03  call    cs:__imp_IsDebuggerPresent
0x140002f09  test    eax, eax
0x140002f0b  jz      short loc_140002F14
0x140002f0d  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140002f12  jz      short loc_140002F3A
0x140002f14  mov     rax, cs:g_pfnResultLoggingCallback
0x140002f1b  test    rax, rax
0x140002f1e  jz      short loc_140002F93
0x140002f20  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140002f27  jnz     short loc_140002F93
0x140002f29  xor     r8d, r8d
0x140002f2c  xor     edx, edx
0x140002f2e  lea     rcx, [rsp+1500h+var_14E0]
0x140002f33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002f38  jmp     short loc_140002F93
0x140002f3a  mov     ebx, 800h
0x140002f3f  mov     rax, cs:g_pfnResultLoggingCallback
0x140002f46  test    rax, rax
0x140002f49  jz      short loc_140002F68
0x140002f4b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140002f52  jnz     short loc_140002F68
0x140002f54  mov     r8d, ebx
0x140002f57  lea     rdx, [rbp+1400h+OutputString]
0x140002f5e  lea     rcx, [rsp+1500h+var_14E0]
0x140002f63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002f68  cmp     [rbp+1400h+OutputString], r12w
0x140002f70  jnz     short loc_140002F86
0x140002f72  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x140002f77  mov     rdx, rbx; wchar_t *
0x140002f7a  lea     rcx, [rbp+1400h+OutputString]; this
0x140002f81  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x140002f86  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x140002f8d  call    cs:__imp_OutputDebugStringW
0x140002f93  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x140002f98  jnz     short loc_140002FA3
0x140002f9a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x140002fa1  jz      short loc_140002FB5
0x140002fa3  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140002faa  test    rax, rax
0x140002fad  jz      short loc_140002FB5
0x140002faf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002fb4  nop
0x140002fb5  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x140002fba  jnz     short loc_140002FDD
0x140002fbc  mov     rcx, [rbp+1400h+var_40]
0x140002fc3  xor     rcx, rsp; StackCookie
0x140002fc6  call    __security_check_cookie
0x140002fcb  add     rsp, 14D0h
0x140002fd2  pop     r15
0x140002fd4  pop     r14
0x140002fd6  pop     r12
0x140002fd8  pop     rdi
0x140002fd9  pop     rsi
0x140002fda  pop     rbx
0x140002fdb  pop     rbp
0x140002fdc  retn
0x140002fdd  lea     rcx, [rsp+1500h+var_14E0]; this
0x140002fe2  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x140002fe8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
