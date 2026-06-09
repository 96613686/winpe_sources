# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180043b4c`
- end: `0x180043df2`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18003a940`

## callees

- `0x180040c98`
- `0x180042410`
- `0x18004317c`
- `0x180043b4c`
- `0x1800456b4`
- `0x1800463d8`
- `0x180046544`
- `0x18007f990`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180043c12`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180043c12`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180043d91`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180043d91`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180043d07`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180043d07`

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
0x180043b4c  push    rbp
0x180043b4e  push    rbx
0x180043b4f  push    rsi
0x180043b50  push    rdi
0x180043b51  push    r12
0x180043b53  push    r14
0x180043b55  push    r15
0x180043b57  lea     rbp, [rsp-13D0h]
0x180043b5f  mov     eax, 14D0h
0x180043b64  call    _alloca_probe
0x180043b69  sub     rsp, rax
0x180043b6c  mov     rax, cs:__security_cookie
0x180043b73  xor     rax, rsp
0x180043b76  mov     [rbp+1400h+var_40], rax
0x180043b7d  mov     rsi, r8
0x180043b80  mov     edi, edx
0x180043b82  mov     rbx, rcx
0x180043b85  mov     r14, [rbp+1400h+arg_28]
0x180043b8c  xor     edx, edx; Val
0x180043b8e  mov     r8d, 98h; Size
0x180043b94  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180043b99  call    memset_0
0x180043b9e  nop
0x180043b9f  xor     r12d, r12d
0x180043ba2  mov     [rbp+1400h+OutputString], r12w
0x180043baa  mov     [rbp+1400h+var_1440], r12b
0x180043bae  mov     rdx, [rbp+1400h+arg_30]; int
0x180043bb5  mov     ecx, [rdx]; this
0x180043bb7  mov     [rsp+1500h+var_14D8], ecx
0x180043bbb  mov     eax, [rdx+4]
0x180043bbe  mov     [rsp+1500h+var_14D4], eax
0x180043bc2  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180043bc7  mov     r15d, eax
0x180043bca  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180043bd2  mov     ecx, r12d
0x180043bd5  lea     eax, [r12+8]
0x180043bda  cmp     dword ptr [rdx+8], 1
0x180043bde  cmovz   ecx, eax
0x180043be1  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180043be5  lea     ecx, [rax-7]
0x180043be8  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180043bf0  inc     ecx
0x180043bf2  mov     [rsp+1500h+var_14D0], ecx
0x180043bf6  mov     rcx, [rbp+1400h+arg_38]
0x180043bfd  test    rcx, rcx
0x180043c00  jz      short loc_180043C0D
0x180043c02  cmp     [rcx], r12w
0x180043c06  mov     [rsp+1500h+var_14C8], rcx
0x180043c0b  jnz     short loc_180043C12
0x180043c0d  mov     [rsp+1500h+var_14C8], r12
0x180043c12  call    cs:__imp_GetCurrentThreadId
0x180043c18  mov     [rsp+1500h+var_14C0], eax
0x180043c1c  mov     [rsp+1500h+var_14A8], rsi
0x180043c21  mov     [rsp+1500h+var_14A0], edi
0x180043c25  mov     [rsp+1500h+var_149C], r15d
0x180043c2a  mov     [rsp+1500h+var_14B8], r12
0x180043c2f  mov     [rsp+1500h+var_14B0], r12
0x180043c34  mov     [rbp+1400h+var_1458], r14
0x180043c38  mov     [rbp+1400h+var_1450], rbx
0x180043c3c  mov     [rsp+1500h+var_1498], r12
0x180043c41  xorps   xmm0, xmm0
0x180043c44  xor     eax, eax
0x180043c46  movups  [rbp+1400h+var_1478], xmm0
0x180043c4a  mov     [rbp+1400h+var_1468], rax
0x180043c4e  xorps   xmm1, xmm1
0x180043c51  movups  [rsp+1500h+var_1490], xmm1
0x180043c56  mov     [rbp+1400h+var_1480], rax
0x180043c5a  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180043c61  test    rax, rax
0x180043c64  jz      short loc_180043C71
0x180043c66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043c6b  mov     [rbp+1400h+var_1460], rax
0x180043c6f  jmp     short loc_180043C75
0x180043c71  mov     [rbp+1400h+var_1460], r12
0x180043c75  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180043c7c  test    rax, rax
0x180043c7f  jz      short loc_180043C8B
0x180043c81  lea     rcx, [rsp+1500h+var_14E0]
0x180043c86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043c8b  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180043c92  test    rax, rax
0x180043c95  jz      short loc_180043CAB
0x180043c97  mov     r8d, 400h
0x180043c9d  lea     rdx, [rbp+1400h+var_1440]
0x180043ca1  lea     rcx, [rsp+1500h+var_14E0]
0x180043ca6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043cab  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180043cb2  test    rax, rax
0x180043cb5  jz      short loc_180043CC1
0x180043cb7  lea     rcx, [rsp+1500h+var_14E0]
0x180043cbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043cc1  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180043cc8  test    rax, rax
0x180043ccb  jz      short loc_180043CDE
0x180043ccd  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180043cd2  jnz     short loc_180043CDE
0x180043cd4  lea     rcx, [rsp+1500h+var_14E0]
0x180043cd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043cde  cmp     [rsp+1500h+var_14D8], r12d
0x180043ce3  jge     loc_180043DEC
0x180043ce9  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180043cf0  jnz     short loc_180043D11
0x180043cf2  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180043cf9  test    rax, rax
0x180043cfc  jz      short loc_180043D07
0x180043cfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043d03  test    al, al
0x180043d05  jmp     short loc_180043D0F
0x180043d07  call    cs:__imp_IsDebuggerPresent
0x180043d0d  test    eax, eax
0x180043d0f  jz      short loc_180043D18
0x180043d11  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180043d16  jz      short loc_180043D3E
0x180043d18  mov     rax, cs:g_pfnResultLoggingCallback
0x180043d1f  test    rax, rax
0x180043d22  jz      short loc_180043D97
0x180043d24  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180043d2b  jnz     short loc_180043D97
0x180043d2d  xor     r8d, r8d
0x180043d30  xor     edx, edx
0x180043d32  lea     rcx, [rsp+1500h+var_14E0]
0x180043d37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043d3c  jmp     short loc_180043D97
0x180043d3e  mov     ebx, 800h
0x180043d43  mov     rax, cs:g_pfnResultLoggingCallback
0x180043d4a  test    rax, rax
0x180043d4d  jz      short loc_180043D6C
0x180043d4f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180043d56  jnz     short loc_180043D6C
0x180043d58  mov     r8d, ebx
0x180043d5b  lea     rdx, [rbp+1400h+OutputString]
0x180043d62  lea     rcx, [rsp+1500h+var_14E0]
0x180043d67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043d6c  cmp     [rbp+1400h+OutputString], r12w
0x180043d74  jnz     short loc_180043D8A
0x180043d76  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180043d7b  mov     rdx, rbx; unsigned __int16 *
0x180043d7e  lea     rcx, [rbp+1400h+OutputString]; this
0x180043d85  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180043d8a  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180043d91  call    cs:__imp_OutputDebugStringW
0x180043d97  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180043d9c  jnz     short loc_180043DA7
0x180043d9e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180043da5  jz      short loc_180043DB9
0x180043da7  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180043dae  test    rax, rax
0x180043db1  jz      short loc_180043DB9
0x180043db3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043db8  nop
0x180043db9  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180043dbe  jnz     short loc_180043DE1
0x180043dc0  mov     rcx, [rbp+1400h+var_40]
0x180043dc7  xor     rcx, rsp; StackCookie
0x180043dca  call    __security_check_cookie
0x180043dcf  add     rsp, 14D0h
0x180043dd6  pop     r15
0x180043dd8  pop     r14
0x180043dda  pop     r12
0x180043ddc  pop     rdi
0x180043ddd  pop     rsi
0x180043dde  pop     rbx
0x180043ddf  pop     rbp
0x180043de0  retn
0x180043de1  lea     rcx, [rsp+1500h+var_14E0]; this
0x180043de6  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180043dec  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
