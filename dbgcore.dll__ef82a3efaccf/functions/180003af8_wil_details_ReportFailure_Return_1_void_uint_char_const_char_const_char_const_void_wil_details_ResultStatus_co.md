# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180003af8`
- end: `0x180003d9a`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `674`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800035c4`

## callees

- `0x180001710`
- `0x1800021f4`
- `0x1800033d0`
- `0x180003af8`
- `0x180007470`
- `0x180009200`
- `0x18000baf0`
- `0x18000f33c`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003baf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003baf`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003d34`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003d34`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003caa`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003caa`

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
  int v9; // ebx
  int v10; // ecx
  __int64 v11; // rdx
  const struct wil::FailureInfo *v12; // rdx
  wil::details::in1diag3 *v13; // rcx
  const struct wil::FailureInfo *v14; // r9
  bool v15; // zf
  int v16; // [rsp+20h] [rbp-E0h] BYREF
  int v17; // [rsp+24h] [rbp-DCh]
  int v18; // [rsp+28h] [rbp-D8h]
  int v19; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v20; // [rsp+30h] [rbp-D0h]
  __int64 v21; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v23; // [rsp+48h] [rbp-B8h]
  __int64 v24; // [rsp+50h] [rbp-B0h]
  const char *v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+60h] [rbp-A0h]
  int v27; // [rsp+64h] [rbp-9Ch]
  __int64 v28; // [rsp+68h] [rbp-98h]
  __int128 v29; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+80h] [rbp-80h]
  __int128 v31; // [rsp+88h] [rbp-78h]
  __int64 v32; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v34; // [rsp+A8h] [rbp-58h]
  __int64 v35; // [rsp+B0h] [rbp-50h]
  __int64 v36; // [rsp+C0h] [rbp-40h]
  char v37[1024]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR OutputString[2048]; // [rsp+4D0h] [rbp+3D0h] BYREF

  v36 = -2;
  memset_0(&v16, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
  v18 = *a7;
  v19 = a7[1];
  v9 = wil::details::RecordReturn((wil::details *)(unsigned int)v18, (int)a7);
  v16 = 1;
  v10 = 0;
  if ( *(_DWORD *)(v11 + 8) == 1 )
    v10 = 8;
  v17 = v10;
  v20 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v25 = "wil";
  v26 = a2;
  v27 = v9;
  v23 = 0;
  v24 = 0;
  v34 = a6;
  v35 = a1;
  v28 = 0;
  v31 = 0;
  v32 = 0;
  v29 = 0;
  v30 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v13);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v16, v37, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v16);
  if ( wil::details::g_pfnOriginateCallback && (v17 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v16);
  if ( v18 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v15 = !IsDebuggerPresent())
      : (v15 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v13) == 0),
        v15)
    || (v17 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString(OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v16, v14);
    OutputDebugStringW(OutputString);
  }
  if ( ((v17 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v13);
  if ( (v17 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v16, v12);
}

```

## disassembly

```asm
0x180003af8  push    rbp
0x180003afa  push    rsi
0x180003afb  push    rdi
0x180003afc  push    r14
0x180003afe  push    r15
0x180003b00  lea     rbp, [rsp-13E0h]
0x180003b08  mov     eax, 14E0h
0x180003b0d  call    _alloca_probe
0x180003b12  sub     rsp, rax
0x180003b15  mov     [rbp+1400h+var_1440], 0FFFFFFFFFFFFFFFEh
0x180003b1d  mov     [rsp+1500h+arg_10], rbx
0x180003b25  mov     rax, cs:__security_cookie
0x180003b2c  xor     rax, rsp
0x180003b2f  mov     [rbp+1400h+var_30], rax
0x180003b36  mov     esi, edx
0x180003b38  mov     r14, rcx
0x180003b3b  mov     rdi, [rbp+1400h+arg_28]
0x180003b42  xor     edx, edx; Val
0x180003b44  mov     r8d, 98h; Size
0x180003b4a  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180003b4f  call    memset_0
0x180003b54  nop
0x180003b55  xor     r15d, r15d
0x180003b58  mov     [rbp+1400h+OutputString], r15w
0x180003b60  mov     [rbp+1400h+var_1430], r15b
0x180003b64  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180003b6b  mov     ecx, [rdx]; this
0x180003b6d  mov     [rsp+1500h+var_14D8], ecx
0x180003b71  mov     eax, [rdx+4]
0x180003b74  mov     [rsp+1500h+var_14D4], eax
0x180003b78  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180003b7d  mov     ebx, eax
0x180003b7f  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180003b87  mov     ecx, r15d
0x180003b8a  lea     eax, [r15+8]
0x180003b8e  cmp     dword ptr [rdx+8], 1
0x180003b92  cmovz   ecx, eax
0x180003b95  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180003b99  lea     ecx, [rax-7]
0x180003b9c  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003ba4  inc     ecx
0x180003ba6  mov     [rsp+1500h+var_14D0], ecx
0x180003baa  mov     [rsp+1500h+var_14C8], r15
0x180003baf  call    cs:__imp_GetCurrentThreadId
0x180003bb5  mov     [rsp+1500h+var_14C0], eax
0x180003bb9  lea     rax, aWil; "wil"
0x180003bc0  mov     [rsp+1500h+var_14A8], rax
0x180003bc5  mov     [rsp+1500h+var_14A0], esi
0x180003bc9  mov     [rsp+1500h+var_149C], ebx
0x180003bcd  mov     [rsp+1500h+var_14B8], r15
0x180003bd2  mov     [rsp+1500h+var_14B0], r15
0x180003bd7  mov     [rbp+1400h+var_1458], rdi
0x180003bdb  mov     [rbp+1400h+var_1450], r14
0x180003bdf  mov     [rsp+1500h+var_1498], r15
0x180003be4  xorps   xmm0, xmm0
0x180003be7  xor     eax, eax
0x180003be9  movups  [rbp+1400h+var_1478], xmm0
0x180003bed  mov     [rbp+1400h+var_1468], rax
0x180003bf1  xorps   xmm1, xmm1
0x180003bf4  movups  [rsp+1500h+var_1490], xmm1
0x180003bf9  mov     [rbp+1400h+var_1480], rax
0x180003bfd  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003c04  test    rax, rax
0x180003c07  jz      short loc_180003C14
0x180003c09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c0e  mov     [rbp+1400h+var_1460], rax
0x180003c12  jmp     short loc_180003C18
0x180003c14  mov     [rbp+1400h+var_1460], r15
0x180003c18  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003c1f  test    rax, rax
0x180003c22  jz      short loc_180003C2E
0x180003c24  lea     rcx, [rsp+1500h+var_14E0]
0x180003c29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c2e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003c35  test    rax, rax
0x180003c38  jz      short loc_180003C4E
0x180003c3a  mov     r8d, 400h
0x180003c40  lea     rdx, [rbp+1400h+var_1430]
0x180003c44  lea     rcx, [rsp+1500h+var_14E0]
0x180003c49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c4e  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003c55  test    rax, rax
0x180003c58  jz      short loc_180003C64
0x180003c5a  lea     rcx, [rsp+1500h+var_14E0]
0x180003c5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c64  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003c6b  test    rax, rax
0x180003c6e  jz      short loc_180003C81
0x180003c70  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003c75  jnz     short loc_180003C81
0x180003c77  lea     rcx, [rsp+1500h+var_14E0]
0x180003c7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c81  cmp     [rsp+1500h+var_14D8], r15d
0x180003c86  jge     loc_180003D94
0x180003c8c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180003c93  jnz     short loc_180003CB4
0x180003c95  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003c9c  test    rax, rax
0x180003c9f  jz      short loc_180003CAA
0x180003ca1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ca6  test    al, al
0x180003ca8  jmp     short loc_180003CB2
0x180003caa  call    cs:__imp_IsDebuggerPresent
0x180003cb0  test    eax, eax
0x180003cb2  jz      short loc_180003CBB
0x180003cb4  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003cb9  jz      short loc_180003CE1
0x180003cbb  mov     rax, cs:g_pfnResultLoggingCallback
0x180003cc2  test    rax, rax
0x180003cc5  jz      short loc_180003D3A
0x180003cc7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180003cce  jnz     short loc_180003D3A
0x180003cd0  xor     r8d, r8d
0x180003cd3  xor     edx, edx
0x180003cd5  lea     rcx, [rsp+1500h+var_14E0]
0x180003cda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cdf  jmp     short loc_180003D3A
0x180003ce1  mov     ebx, 800h
0x180003ce6  mov     rax, cs:g_pfnResultLoggingCallback
0x180003ced  test    rax, rax
0x180003cf0  jz      short loc_180003D0F
0x180003cf2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180003cf9  jnz     short loc_180003D0F
0x180003cfb  mov     r8d, ebx
0x180003cfe  lea     rdx, [rbp+1400h+OutputString]
0x180003d05  lea     rcx, [rsp+1500h+var_14E0]
0x180003d0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d0f  cmp     [rbp+1400h+OutputString], r15w
0x180003d17  jnz     short loc_180003D2D
0x180003d19  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180003d1e  mov     rdx, rbx; unsigned __int16 *
0x180003d21  lea     rcx, [rbp+1400h+OutputString]; Buffer
0x180003d28  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003d2d  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180003d34  call    cs:__imp_OutputDebugStringW
0x180003d3a  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180003d3f  jnz     short loc_180003D4A
0x180003d41  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180003d48  jz      short loc_180003D5C
0x180003d4a  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003d51  test    rax, rax
0x180003d54  jz      short loc_180003D5C
0x180003d56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d5b  nop
0x180003d5c  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180003d61  jnz     short loc_180003D89
0x180003d63  mov     rcx, [rbp+1400h+var_30]
0x180003d6a  xor     rcx, rsp; StackCookie
0x180003d6d  call    __security_check_cookie
0x180003d72  mov     rbx, [rsp+1500h+arg_10]
0x180003d7a  add     rsp, 14E0h
0x180003d81  pop     r15
0x180003d83  pop     r14
0x180003d85  pop     rdi
0x180003d86  pop     rsi
0x180003d87  pop     rbp
0x180003d88  retn
0x180003d89  lea     rcx, [rsp+1500h+var_14E0]; this
0x180003d8e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180003d94  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
