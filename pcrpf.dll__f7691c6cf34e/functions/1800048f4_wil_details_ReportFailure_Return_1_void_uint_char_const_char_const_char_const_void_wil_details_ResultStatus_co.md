# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800048f4`
- end: `0x180004bad`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `697`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800042ec`

## callees

- `0x180003270`
- `0x180003cf0`
- `0x1800048f4`
- `0x180006d44`
- `0x180008978`
- `0x18000b30c`
- `0x18000b59c`
- `0x180057050`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800049ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800049ba`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004b45`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004b45`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004ab5`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004ab5`

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
0x1800048f4  push    rbp
0x1800048f6  push    rbx
0x1800048f7  push    rsi
0x1800048f8  push    rdi
0x1800048f9  push    r12
0x1800048fb  push    r14
0x1800048fd  push    r15
0x1800048ff  lea     rbp, [rsp-13D0h]
0x180004907  mov     eax, 14D0h
0x18000490c  call    _alloca_probe
0x180004911  sub     rsp, rax
0x180004914  mov     rax, cs:__security_cookie
0x18000491b  xor     rax, rsp
0x18000491e  mov     [rbp+1400h+var_40], rax
0x180004925  mov     rsi, r8
0x180004928  mov     edi, edx
0x18000492a  mov     rbx, rcx
0x18000492d  mov     r14, [rbp+1400h+arg_28]
0x180004934  xor     edx, edx; Val
0x180004936  mov     r8d, 98h; Size
0x18000493c  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180004941  call    memset_0
0x180004946  nop
0x180004947  xor     r12d, r12d
0x18000494a  mov     [rbp+1400h+OutputString], r12w
0x180004952  mov     [rbp+1400h+var_1440], r12b
0x180004956  mov     rdx, [rbp+1400h+arg_30]; int
0x18000495d  mov     ecx, [rdx]; this
0x18000495f  mov     [rsp+1500h+var_14D8], ecx
0x180004963  mov     eax, [rdx+4]
0x180004966  mov     [rsp+1500h+var_14D4], eax
0x18000496a  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000496f  mov     r15d, eax
0x180004972  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18000497a  mov     ecx, r12d
0x18000497d  lea     eax, [r12+8]
0x180004982  cmp     dword ptr [rdx+8], 1
0x180004986  cmovz   ecx, eax
0x180004989  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18000498d  lea     ecx, [rax-7]
0x180004990  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004998  inc     ecx
0x18000499a  mov     [rsp+1500h+var_14D0], ecx
0x18000499e  mov     rcx, [rbp+1400h+arg_38]
0x1800049a5  test    rcx, rcx
0x1800049a8  jz      short loc_1800049B5
0x1800049aa  cmp     [rcx], r12w
0x1800049ae  mov     [rsp+1500h+var_14C8], rcx
0x1800049b3  jnz     short loc_1800049BA
0x1800049b5  mov     [rsp+1500h+var_14C8], r12
0x1800049ba  call    cs:__imp_GetCurrentThreadId
0x1800049c1  nop     dword ptr [rax+rax+00h]
0x1800049c6  mov     [rsp+1500h+var_14C0], eax
0x1800049ca  mov     [rsp+1500h+var_14A8], rsi
0x1800049cf  mov     [rsp+1500h+var_14A0], edi
0x1800049d3  mov     [rsp+1500h+var_149C], r15d
0x1800049d8  mov     [rsp+1500h+var_14B8], r12
0x1800049dd  mov     [rsp+1500h+var_14B0], r12
0x1800049e2  mov     [rbp+1400h+var_1458], r14
0x1800049e6  mov     [rbp+1400h+var_1450], rbx
0x1800049ea  mov     [rsp+1500h+var_1498], r12
0x1800049ef  xorps   xmm0, xmm0
0x1800049f2  xor     eax, eax
0x1800049f4  movups  [rbp+1400h+var_1478], xmm0
0x1800049f8  mov     [rbp+1400h+var_1468], rax
0x1800049fc  xorps   xmm1, xmm1
0x1800049ff  movups  [rsp+1500h+var_1490], xmm1
0x180004a04  mov     [rbp+1400h+var_1480], rax
0x180004a08  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004a0f  test    rax, rax
0x180004a12  jz      short loc_180004A1F
0x180004a14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a19  mov     [rbp+1400h+var_1460], rax
0x180004a1d  jmp     short loc_180004A23
0x180004a1f  mov     [rbp+1400h+var_1460], r12
0x180004a23  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004a2a  test    rax, rax
0x180004a2d  jz      short loc_180004A39
0x180004a2f  lea     rcx, [rsp+1500h+var_14E0]
0x180004a34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a39  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004a40  test    rax, rax
0x180004a43  jz      short loc_180004A59
0x180004a45  mov     r8d, 400h
0x180004a4b  lea     rdx, [rbp+1400h+var_1440]
0x180004a4f  lea     rcx, [rsp+1500h+var_14E0]
0x180004a54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a59  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004a60  test    rax, rax
0x180004a63  jz      short loc_180004A6F
0x180004a65  lea     rcx, [rsp+1500h+var_14E0]
0x180004a6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a6f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004a76  test    rax, rax
0x180004a79  jz      short loc_180004A8C
0x180004a7b  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180004a80  jnz     short loc_180004A8C
0x180004a82  lea     rcx, [rsp+1500h+var_14E0]
0x180004a87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a8c  cmp     [rsp+1500h+var_14D8], r12d
0x180004a91  jge     loc_180004BA7
0x180004a97  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180004a9e  jnz     short loc_180004AC5
0x180004aa0  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004aa7  test    rax, rax
0x180004aaa  jz      short loc_180004AB5
0x180004aac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ab1  test    al, al
0x180004ab3  jmp     short loc_180004AC3
0x180004ab5  call    cs:__imp_IsDebuggerPresent
0x180004abc  nop     dword ptr [rax+rax+00h]
0x180004ac1  test    eax, eax
0x180004ac3  jz      short loc_180004ACC
0x180004ac5  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180004aca  jz      short loc_180004AF2
0x180004acc  mov     rax, cs:g_pfnResultLoggingCallback
0x180004ad3  test    rax, rax
0x180004ad6  jz      short loc_180004B51
0x180004ad8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180004adf  jnz     short loc_180004B51
0x180004ae1  xor     r8d, r8d
0x180004ae4  xor     edx, edx
0x180004ae6  lea     rcx, [rsp+1500h+var_14E0]
0x180004aeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004af0  jmp     short loc_180004B51
0x180004af2  mov     ebx, 800h
0x180004af7  mov     rax, cs:g_pfnResultLoggingCallback
0x180004afe  test    rax, rax
0x180004b01  jz      short loc_180004B20
0x180004b03  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180004b0a  jnz     short loc_180004B20
0x180004b0c  mov     r8d, ebx
0x180004b0f  lea     rdx, [rbp+1400h+OutputString]
0x180004b16  lea     rcx, [rsp+1500h+var_14E0]
0x180004b1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b20  cmp     [rbp+1400h+OutputString], r12w
0x180004b28  jnz     short loc_180004B3E
0x180004b2a  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180004b2f  mov     rdx, rbx; unsigned __int16 *
0x180004b32  lea     rcx, [rbp+1400h+OutputString]; this
0x180004b39  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004b3e  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180004b45  call    cs:__imp_OutputDebugStringW
0x180004b4c  nop     dword ptr [rax+rax+00h]
0x180004b51  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180004b56  jnz     short loc_180004B61
0x180004b58  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180004b5f  jz      short loc_180004B73
0x180004b61  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004b68  test    rax, rax
0x180004b6b  jz      short loc_180004B73
0x180004b6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b72  nop
0x180004b73  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180004b78  jnz     short loc_180004B9C
0x180004b7a  mov     rcx, [rbp+1400h+var_40]
0x180004b81  xor     rcx, rsp; StackCookie
0x180004b84  call    __security_check_cookie
0x180004b89  add     rsp, 14D0h
0x180004b90  pop     r15
0x180004b92  pop     r14
0x180004b94  pop     r12
0x180004b96  pop     rdi
0x180004b97  pop     rsi
0x180004b98  pop     rbx
0x180004b99  pop     rbp
0x180004b9a  retn
0x180004b9c  lea     rcx, [rsp+1500h+var_14E0]; this
0x180004ba1  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180004ba7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
