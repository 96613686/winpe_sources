# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180004a08`
- end: `0x180004cae`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180004494`

## callees

- `0x1800024e0`
- `0x180002efc`
- `0x180004a08`
- `0x180006fe4`
- `0x180008558`
- `0x18000ab80`
- `0x18000ad4c`
- `0x1800588d0`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004ace`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004ace`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004c4d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004c4d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004bc3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004bc3`

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
0x180004a08  push    rbp
0x180004a0a  push    rbx
0x180004a0b  push    rsi
0x180004a0c  push    rdi
0x180004a0d  push    r12
0x180004a0f  push    r14
0x180004a11  push    r15
0x180004a13  lea     rbp, [rsp-13D0h]
0x180004a1b  mov     eax, 14D0h
0x180004a20  call    _alloca_probe
0x180004a25  sub     rsp, rax
0x180004a28  mov     rax, cs:__security_cookie
0x180004a2f  xor     rax, rsp
0x180004a32  mov     [rbp+1400h+var_40], rax
0x180004a39  mov     rsi, r8
0x180004a3c  mov     edi, edx
0x180004a3e  mov     rbx, rcx
0x180004a41  mov     r14, [rbp+1400h+arg_28]
0x180004a48  xor     edx, edx; Val
0x180004a4a  mov     r8d, 98h; Size
0x180004a50  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180004a55  call    memset_0
0x180004a5a  nop
0x180004a5b  xor     r12d, r12d
0x180004a5e  mov     [rbp+1400h+OutputString], r12w
0x180004a66  mov     [rbp+1400h+var_1440], r12b
0x180004a6a  mov     rdx, [rbp+1400h+arg_30]; int
0x180004a71  mov     ecx, [rdx]; this
0x180004a73  mov     [rsp+1500h+var_14D8], ecx
0x180004a77  mov     eax, [rdx+4]
0x180004a7a  mov     [rsp+1500h+var_14D4], eax
0x180004a7e  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004a83  mov     r15d, eax
0x180004a86  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180004a8e  mov     ecx, r12d
0x180004a91  lea     eax, [r12+8]
0x180004a96  cmp     dword ptr [rdx+8], 1
0x180004a9a  cmovz   ecx, eax
0x180004a9d  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180004aa1  lea     ecx, [rax-7]
0x180004aa4  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004aac  inc     ecx
0x180004aae  mov     [rsp+1500h+var_14D0], ecx
0x180004ab2  mov     rcx, [rbp+1400h+arg_38]
0x180004ab9  test    rcx, rcx
0x180004abc  jz      short loc_180004AC9
0x180004abe  cmp     [rcx], r12w
0x180004ac2  mov     [rsp+1500h+var_14C8], rcx
0x180004ac7  jnz     short loc_180004ACE
0x180004ac9  mov     [rsp+1500h+var_14C8], r12
0x180004ace  call    cs:__imp_GetCurrentThreadId
0x180004ad4  mov     [rsp+1500h+var_14C0], eax
0x180004ad8  mov     [rsp+1500h+var_14A8], rsi
0x180004add  mov     [rsp+1500h+var_14A0], edi
0x180004ae1  mov     [rsp+1500h+var_149C], r15d
0x180004ae6  mov     [rsp+1500h+var_14B8], r12
0x180004aeb  mov     [rsp+1500h+var_14B0], r12
0x180004af0  mov     [rbp+1400h+var_1458], r14
0x180004af4  mov     [rbp+1400h+var_1450], rbx
0x180004af8  mov     [rsp+1500h+var_1498], r12
0x180004afd  xorps   xmm0, xmm0
0x180004b00  xor     eax, eax
0x180004b02  movups  [rbp+1400h+var_1478], xmm0
0x180004b06  mov     [rbp+1400h+var_1468], rax
0x180004b0a  xorps   xmm1, xmm1
0x180004b0d  movups  [rsp+1500h+var_1490], xmm1
0x180004b12  mov     [rbp+1400h+var_1480], rax
0x180004b16  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004b1d  test    rax, rax
0x180004b20  jz      short loc_180004B2D
0x180004b22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b27  mov     [rbp+1400h+var_1460], rax
0x180004b2b  jmp     short loc_180004B31
0x180004b2d  mov     [rbp+1400h+var_1460], r12
0x180004b31  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004b38  test    rax, rax
0x180004b3b  jz      short loc_180004B47
0x180004b3d  lea     rcx, [rsp+1500h+var_14E0]
0x180004b42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b47  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004b4e  test    rax, rax
0x180004b51  jz      short loc_180004B67
0x180004b53  mov     r8d, 400h
0x180004b59  lea     rdx, [rbp+1400h+var_1440]
0x180004b5d  lea     rcx, [rsp+1500h+var_14E0]
0x180004b62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b67  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004b6e  test    rax, rax
0x180004b71  jz      short loc_180004B7D
0x180004b73  lea     rcx, [rsp+1500h+var_14E0]
0x180004b78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b7d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004b84  test    rax, rax
0x180004b87  jz      short loc_180004B9A
0x180004b89  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180004b8e  jnz     short loc_180004B9A
0x180004b90  lea     rcx, [rsp+1500h+var_14E0]
0x180004b95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b9a  cmp     [rsp+1500h+var_14D8], r12d
0x180004b9f  jge     loc_180004CA8
0x180004ba5  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180004bac  jnz     short loc_180004BCD
0x180004bae  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004bb5  test    rax, rax
0x180004bb8  jz      short loc_180004BC3
0x180004bba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bbf  test    al, al
0x180004bc1  jmp     short loc_180004BCB
0x180004bc3  call    cs:__imp_IsDebuggerPresent
0x180004bc9  test    eax, eax
0x180004bcb  jz      short loc_180004BD4
0x180004bcd  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180004bd2  jz      short loc_180004BFA
0x180004bd4  mov     rax, cs:g_pfnResultLoggingCallback
0x180004bdb  test    rax, rax
0x180004bde  jz      short loc_180004C53
0x180004be0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180004be7  jnz     short loc_180004C53
0x180004be9  xor     r8d, r8d
0x180004bec  xor     edx, edx
0x180004bee  lea     rcx, [rsp+1500h+var_14E0]
0x180004bf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bf8  jmp     short loc_180004C53
0x180004bfa  mov     ebx, 800h
0x180004bff  mov     rax, cs:g_pfnResultLoggingCallback
0x180004c06  test    rax, rax
0x180004c09  jz      short loc_180004C28
0x180004c0b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180004c12  jnz     short loc_180004C28
0x180004c14  mov     r8d, ebx
0x180004c17  lea     rdx, [rbp+1400h+OutputString]
0x180004c1e  lea     rcx, [rsp+1500h+var_14E0]
0x180004c23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c28  cmp     [rbp+1400h+OutputString], r12w
0x180004c30  jnz     short loc_180004C46
0x180004c32  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180004c37  mov     rdx, rbx; unsigned __int16 *
0x180004c3a  lea     rcx, [rbp+1400h+OutputString]; this
0x180004c41  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004c46  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180004c4d  call    cs:__imp_OutputDebugStringW
0x180004c53  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180004c58  jnz     short loc_180004C63
0x180004c5a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180004c61  jz      short loc_180004C75
0x180004c63  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004c6a  test    rax, rax
0x180004c6d  jz      short loc_180004C75
0x180004c6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c74  nop
0x180004c75  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180004c7a  jnz     short loc_180004C9D
0x180004c7c  mov     rcx, [rbp+1400h+var_40]
0x180004c83  xor     rcx, rsp; StackCookie
0x180004c86  call    __security_check_cookie
0x180004c8b  add     rsp, 14D0h
0x180004c92  pop     r15
0x180004c94  pop     r14
0x180004c96  pop     r12
0x180004c98  pop     rdi
0x180004c99  pop     rsi
0x180004c9a  pop     rbx
0x180004c9b  pop     rbp
0x180004c9c  retn
0x180004c9d  lea     rcx, [rsp+1500h+var_14E0]; this
0x180004ca2  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180004ca8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
