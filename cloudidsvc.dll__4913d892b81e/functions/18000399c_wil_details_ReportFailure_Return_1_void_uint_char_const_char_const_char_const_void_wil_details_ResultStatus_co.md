# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000399c`
- end: `0x180003c42`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800032fc`

## callees

- `0x180001a50`
- `0x1800024f0`
- `0x18000399c`
- `0x180005680`
- `0x180006990`
- `0x180007de8`
- `0x180007fe4`
- `0x180010720`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003a62`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003a62`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003be1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003be1`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003b57`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003b57`

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
0x18000399c  push    rbp
0x18000399e  push    rbx
0x18000399f  push    rsi
0x1800039a0  push    rdi
0x1800039a1  push    r12
0x1800039a3  push    r14
0x1800039a5  push    r15
0x1800039a7  lea     rbp, [rsp-13D0h]
0x1800039af  mov     eax, 14D0h
0x1800039b4  call    _alloca_probe
0x1800039b9  sub     rsp, rax
0x1800039bc  mov     rax, cs:__security_cookie
0x1800039c3  xor     rax, rsp
0x1800039c6  mov     [rbp+1400h+var_40], rax
0x1800039cd  mov     rsi, r8
0x1800039d0  mov     edi, edx
0x1800039d2  mov     rbx, rcx
0x1800039d5  mov     r14, [rbp+1400h+arg_28]
0x1800039dc  xor     edx, edx; Val
0x1800039de  mov     r8d, 98h; Size
0x1800039e4  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1800039e9  call    memset_0
0x1800039ee  nop
0x1800039ef  xor     r12d, r12d
0x1800039f2  mov     [rbp+1400h+OutputString], r12w
0x1800039fa  mov     [rbp+1400h+var_1440], r12b
0x1800039fe  mov     rdx, [rbp+1400h+arg_30]; int
0x180003a05  mov     ecx, [rdx]; this
0x180003a07  mov     [rsp+1500h+var_14D8], ecx
0x180003a0b  mov     eax, [rdx+4]
0x180003a0e  mov     [rsp+1500h+var_14D4], eax
0x180003a12  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180003a17  mov     r15d, eax
0x180003a1a  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180003a22  mov     ecx, r12d
0x180003a25  lea     eax, [r12+8]
0x180003a2a  cmp     dword ptr [rdx+8], 1
0x180003a2e  cmovz   ecx, eax
0x180003a31  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180003a35  lea     ecx, [rax-7]
0x180003a38  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003a40  inc     ecx
0x180003a42  mov     [rsp+1500h+var_14D0], ecx
0x180003a46  mov     rcx, [rbp+1400h+arg_38]
0x180003a4d  test    rcx, rcx
0x180003a50  jz      short loc_180003A5D
0x180003a52  cmp     [rcx], r12w
0x180003a56  mov     [rsp+1500h+var_14C8], rcx
0x180003a5b  jnz     short loc_180003A62
0x180003a5d  mov     [rsp+1500h+var_14C8], r12
0x180003a62  call    cs:__imp_GetCurrentThreadId
0x180003a68  mov     [rsp+1500h+var_14C0], eax
0x180003a6c  mov     [rsp+1500h+var_14A8], rsi
0x180003a71  mov     [rsp+1500h+var_14A0], edi
0x180003a75  mov     [rsp+1500h+var_149C], r15d
0x180003a7a  mov     [rsp+1500h+var_14B8], r12
0x180003a7f  mov     [rsp+1500h+var_14B0], r12
0x180003a84  mov     [rbp+1400h+var_1458], r14
0x180003a88  mov     [rbp+1400h+var_1450], rbx
0x180003a8c  mov     [rsp+1500h+var_1498], r12
0x180003a91  xorps   xmm0, xmm0
0x180003a94  xor     eax, eax
0x180003a96  movups  [rbp+1400h+var_1478], xmm0
0x180003a9a  mov     [rbp+1400h+var_1468], rax
0x180003a9e  xorps   xmm1, xmm1
0x180003aa1  movups  [rsp+1500h+var_1490], xmm1
0x180003aa6  mov     [rbp+1400h+var_1480], rax
0x180003aaa  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003ab1  test    rax, rax
0x180003ab4  jz      short loc_180003AC1
0x180003ab6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003abb  mov     [rbp+1400h+var_1460], rax
0x180003abf  jmp     short loc_180003AC5
0x180003ac1  mov     [rbp+1400h+var_1460], r12
0x180003ac5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003acc  test    rax, rax
0x180003acf  jz      short loc_180003ADB
0x180003ad1  lea     rcx, [rsp+1500h+var_14E0]
0x180003ad6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003adb  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003ae2  test    rax, rax
0x180003ae5  jz      short loc_180003AFB
0x180003ae7  mov     r8d, 400h
0x180003aed  lea     rdx, [rbp+1400h+var_1440]
0x180003af1  lea     rcx, [rsp+1500h+var_14E0]
0x180003af6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003afb  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003b02  test    rax, rax
0x180003b05  jz      short loc_180003B11
0x180003b07  lea     rcx, [rsp+1500h+var_14E0]
0x180003b0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b11  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003b18  test    rax, rax
0x180003b1b  jz      short loc_180003B2E
0x180003b1d  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003b22  jnz     short loc_180003B2E
0x180003b24  lea     rcx, [rsp+1500h+var_14E0]
0x180003b29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b2e  cmp     [rsp+1500h+var_14D8], r12d
0x180003b33  jge     loc_180003C3C
0x180003b39  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180003b40  jnz     short loc_180003B61
0x180003b42  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003b49  test    rax, rax
0x180003b4c  jz      short loc_180003B57
0x180003b4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b53  test    al, al
0x180003b55  jmp     short loc_180003B5F
0x180003b57  call    cs:__imp_IsDebuggerPresent
0x180003b5d  test    eax, eax
0x180003b5f  jz      short loc_180003B68
0x180003b61  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003b66  jz      short loc_180003B8E
0x180003b68  mov     rax, cs:g_pfnResultLoggingCallback
0x180003b6f  test    rax, rax
0x180003b72  jz      short loc_180003BE7
0x180003b74  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003b7b  jnz     short loc_180003BE7
0x180003b7d  xor     r8d, r8d
0x180003b80  xor     edx, edx
0x180003b82  lea     rcx, [rsp+1500h+var_14E0]
0x180003b87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b8c  jmp     short loc_180003BE7
0x180003b8e  mov     ebx, 800h
0x180003b93  mov     rax, cs:g_pfnResultLoggingCallback
0x180003b9a  test    rax, rax
0x180003b9d  jz      short loc_180003BBC
0x180003b9f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003ba6  jnz     short loc_180003BBC
0x180003ba8  mov     r8d, ebx
0x180003bab  lea     rdx, [rbp+1400h+OutputString]
0x180003bb2  lea     rcx, [rsp+1500h+var_14E0]
0x180003bb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bbc  cmp     [rbp+1400h+OutputString], r12w
0x180003bc4  jnz     short loc_180003BDA
0x180003bc6  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180003bcb  mov     rdx, rbx; unsigned __int16 *
0x180003bce  lea     rcx, [rbp+1400h+OutputString]; this
0x180003bd5  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003bda  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180003be1  call    cs:__imp_OutputDebugStringW
0x180003be7  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180003bec  jnz     short loc_180003BF7
0x180003bee  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180003bf5  jz      short loc_180003C09
0x180003bf7  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003bfe  test    rax, rax
0x180003c01  jz      short loc_180003C09
0x180003c03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c08  nop
0x180003c09  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180003c0e  jnz     short loc_180003C31
0x180003c10  mov     rcx, [rbp+1400h+var_40]
0x180003c17  xor     rcx, rsp; StackCookie
0x180003c1a  call    __security_check_cookie
0x180003c1f  add     rsp, 14D0h
0x180003c26  pop     r15
0x180003c28  pop     r14
0x180003c2a  pop     r12
0x180003c2c  pop     rdi
0x180003c2d  pop     rsi
0x180003c2e  pop     rbx
0x180003c2f  pop     rbp
0x180003c30  retn
0x180003c31  lea     rcx, [rsp+1500h+var_14E0]; this
0x180003c36  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180003c3c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
