# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140003adc`
- end: `0x140003d69`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140003284`

## callees

- `0x140003adc`
- `0x140006c94`
- `0x14000ab80`
- `0x14000b9b0`
- `0x14000bc1c`
- `0x1400187b2`
- `0x1400187e0`
- `0x1400188a0`
- `0x140019010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003b8a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003b8a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140003d08`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140003d08`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140003c7e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140003c7e`

## pseudocode

```c
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
0x140003adc  push    rbp
0x140003ade  push    rbx
0x140003adf  push    rsi
0x140003ae0  push    rdi
0x140003ae1  push    r12
0x140003ae3  push    r14
0x140003ae5  push    r15
0x140003ae7  lea     rbp, [rsp-13D0h]
0x140003aef  mov     eax, 14D0h
0x140003af4  call    _alloca_probe
0x140003af9  sub     rsp, rax
0x140003afc  mov     rax, cs:__security_cookie
0x140003b03  xor     rax, rsp
0x140003b06  mov     [rbp+1400h+var_40], rax
0x140003b0d  mov     r14, r8
0x140003b10  mov     esi, edx
0x140003b12  mov     r15, rcx
0x140003b15  mov     rdi, [rbp+1400h+arg_28]
0x140003b1c  xor     edx, edx; Val
0x140003b1e  mov     r8d, 98h; Size
0x140003b24  lea     rcx, [rsp+1500h+var_14E0]; void *
0x140003b29  call    memset_0
0x140003b2e  nop
0x140003b2f  xor     r12d, r12d
0x140003b32  mov     [rbp+1400h+OutputString], r12w
0x140003b3a  mov     [rbp+1400h+var_1440], r12b
0x140003b3e  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x140003b45  mov     ecx, [rdx]; this
0x140003b47  mov     [rsp+1500h+var_14D8], ecx
0x140003b4b  mov     eax, [rdx+4]
0x140003b4e  mov     [rsp+1500h+var_14D4], eax
0x140003b52  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140003b57  mov     ebx, eax
0x140003b59  mov     dword ptr [rsp+1500h+var_14E0], 1
0x140003b61  mov     ecx, r12d
0x140003b64  lea     eax, [r12+8]
0x140003b69  cmp     dword ptr [rdx+8], 1
0x140003b6d  cmovz   ecx, eax
0x140003b70  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x140003b74  lea     ecx, [rax-7]
0x140003b77  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140003b7f  inc     ecx
0x140003b81  mov     [rsp+1500h+var_14D0], ecx
0x140003b85  mov     [rsp+1500h+var_14C8], r12
0x140003b8a  call    cs:__imp_GetCurrentThreadId
0x140003b90  mov     [rsp+1500h+var_14C0], eax
0x140003b94  mov     [rsp+1500h+var_14A8], r14
0x140003b99  mov     [rsp+1500h+var_14A0], esi
0x140003b9d  mov     [rsp+1500h+var_149C], ebx
0x140003ba1  mov     [rsp+1500h+var_14B8], r12
0x140003ba6  mov     [rsp+1500h+var_14B0], r12
0x140003bab  mov     [rbp+1400h+var_1458], rdi
0x140003baf  mov     [rbp+1400h+var_1450], r15
0x140003bb3  mov     [rsp+1500h+var_1498], r12
0x140003bb8  xorps   xmm0, xmm0
0x140003bbb  xor     eax, eax
0x140003bbd  movups  [rbp+1400h+var_1478], xmm0
0x140003bc1  mov     [rbp+1400h+var_1468], rax
0x140003bc5  xorps   xmm1, xmm1
0x140003bc8  movups  [rsp+1500h+var_1490], xmm1
0x140003bcd  mov     [rbp+1400h+var_1480], rax
0x140003bd1  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140003bd8  test    rax, rax
0x140003bdb  jz      short loc_140003BE8
0x140003bdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003be2  mov     [rbp+1400h+var_1460], rax
0x140003be6  jmp     short loc_140003BEC
0x140003be8  mov     [rbp+1400h+var_1460], r12
0x140003bec  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140003bf3  test    rax, rax
0x140003bf6  jz      short loc_140003C02
0x140003bf8  lea     rcx, [rsp+1500h+var_14E0]
0x140003bfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003c02  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140003c09  test    rax, rax
0x140003c0c  jz      short loc_140003C22
0x140003c0e  mov     r8d, 400h
0x140003c14  lea     rdx, [rbp+1400h+var_1440]
0x140003c18  lea     rcx, [rsp+1500h+var_14E0]
0x140003c1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003c22  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140003c29  test    rax, rax
0x140003c2c  jz      short loc_140003C38
0x140003c2e  lea     rcx, [rsp+1500h+var_14E0]
0x140003c33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003c38  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140003c3f  test    rax, rax
0x140003c42  jz      short loc_140003C55
0x140003c44  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140003c49  jnz     short loc_140003C55
0x140003c4b  lea     rcx, [rsp+1500h+var_14E0]
0x140003c50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003c55  cmp     [rsp+1500h+var_14D8], r12d
0x140003c5a  jge     loc_140003D63
0x140003c60  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x140003c67  jnz     short loc_140003C88
0x140003c69  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140003c70  test    rax, rax
0x140003c73  jz      short loc_140003C7E
0x140003c75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003c7a  test    al, al
0x140003c7c  jmp     short loc_140003C86
0x140003c7e  call    cs:__imp_IsDebuggerPresent
0x140003c84  test    eax, eax
0x140003c86  jz      short loc_140003C8F
0x140003c88  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140003c8d  jz      short loc_140003CB5
0x140003c8f  mov     rax, cs:g_pfnResultLoggingCallback
0x140003c96  test    rax, rax
0x140003c99  jz      short loc_140003D0E
0x140003c9b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140003ca2  jnz     short loc_140003D0E
0x140003ca4  xor     r8d, r8d
0x140003ca7  xor     edx, edx
0x140003ca9  lea     rcx, [rsp+1500h+var_14E0]
0x140003cae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003cb3  jmp     short loc_140003D0E
0x140003cb5  mov     ebx, 800h
0x140003cba  mov     rax, cs:g_pfnResultLoggingCallback
0x140003cc1  test    rax, rax
0x140003cc4  jz      short loc_140003CE3
0x140003cc6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140003ccd  jnz     short loc_140003CE3
0x140003ccf  mov     r8d, ebx
0x140003cd2  lea     rdx, [rbp+1400h+OutputString]
0x140003cd9  lea     rcx, [rsp+1500h+var_14E0]
0x140003cde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003ce3  cmp     [rbp+1400h+OutputString], r12w
0x140003ceb  jnz     short loc_140003D01
0x140003ced  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x140003cf2  mov     rdx, rbx; unsigned __int16 *
0x140003cf5  lea     rcx, [rbp+1400h+OutputString]; this
0x140003cfc  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140003d01  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x140003d08  call    cs:__imp_OutputDebugStringW
0x140003d0e  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x140003d13  jnz     short loc_140003D1E
0x140003d15  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x140003d1c  jz      short loc_140003D30
0x140003d1e  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140003d25  test    rax, rax
0x140003d28  jz      short loc_140003D30
0x140003d2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003d2f  nop
0x140003d30  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x140003d35  jnz     short loc_140003D58
0x140003d37  mov     rcx, [rbp+1400h+var_40]
0x140003d3e  xor     rcx, rsp; StackCookie
0x140003d41  call    __security_check_cookie
0x140003d46  add     rsp, 14D0h
0x140003d4d  pop     r15
0x140003d4f  pop     r14
0x140003d51  pop     r12
0x140003d53  pop     rdi
0x140003d54  pop     rsi
0x140003d55  pop     rbx
0x140003d56  pop     rbp
0x140003d57  retn
0x140003d58  lea     rcx, [rsp+1500h+var_14E0]; this
0x140003d5d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x140003d63  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
