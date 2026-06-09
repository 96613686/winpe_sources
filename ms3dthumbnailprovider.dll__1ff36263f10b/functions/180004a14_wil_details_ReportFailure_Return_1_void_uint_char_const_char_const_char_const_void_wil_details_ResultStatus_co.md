# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180004a14`
- end: `0x180004caa`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800044fc`

## callees

- `0x180001ef0`
- `0x180002954`
- `0x180004a14`
- `0x1800065f4`
- `0x180007e30`
- `0x180009820`
- `0x1800099a8`
- `0x18000a270`
- `0x18000b010`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x180004c44`
- `KERNEL32!OutputDebugStringW` at `0x180004c44`
- `KERNEL32!IsDebuggerPresent` at `0x180004bba`
- `KERNEL32!IsDebuggerPresent` at `0x180004bba`
- `KERNEL32!GetCurrentThreadId` at `0x180004abf`
- `KERNEL32!GetCurrentThreadId` at `0x180004abf`

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
  char v36[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v16, 0, 0x98u);
  OutputString[0] = 0;
  v36[0] = 0;
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
    wil::details::g_pfnGetContextAndNotifyFailure(&v16, v36, 1024);
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
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v16, v14);
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
0x180004a14  mov     [rsp-8+arg_10], rbx
0x180004a19  push    rbp
0x180004a1a  push    rsi
0x180004a1b  push    rdi
0x180004a1c  push    r14
0x180004a1e  push    r15
0x180004a20  lea     rbp, [rsp-13D0h]
0x180004a28  mov     eax, 14D0h
0x180004a2d  call    _alloca_probe
0x180004a32  sub     rsp, rax
0x180004a35  mov     rax, cs:__security_cookie
0x180004a3c  xor     rax, rsp
0x180004a3f  mov     [rbp+13F0h+var_30], rax
0x180004a46  mov     esi, edx
0x180004a48  mov     r14, rcx
0x180004a4b  mov     rdi, [rbp+13F0h+arg_28]
0x180004a52  xor     edx, edx; Val
0x180004a54  mov     r8d, 98h; Size
0x180004a5a  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180004a5f  call    memset_0
0x180004a64  nop
0x180004a65  xor     r15d, r15d
0x180004a68  mov     [rbp+13F0h+OutputString], r15w
0x180004a70  mov     [rbp+13F0h+var_1430], r15b
0x180004a74  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180004a7b  mov     ecx, [rdx]; this
0x180004a7d  mov     [rsp+14F0h+var_14C8], ecx
0x180004a81  mov     eax, [rdx+4]
0x180004a84  mov     [rsp+14F0h+var_14C4], eax
0x180004a88  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004a8d  mov     ebx, eax
0x180004a8f  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180004a97  mov     ecx, r15d
0x180004a9a  lea     eax, [r15+8]
0x180004a9e  cmp     dword ptr [rdx+8], 1
0x180004aa2  cmovz   ecx, eax
0x180004aa5  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180004aa9  lea     ecx, [rax-7]
0x180004aac  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004ab4  inc     ecx
0x180004ab6  mov     [rsp+14F0h+var_14C0], ecx
0x180004aba  mov     [rsp+14F0h+var_14B8], r15
0x180004abf  call    cs:__imp_GetCurrentThreadId
0x180004ac5  mov     [rsp+14F0h+var_14B0], eax
0x180004ac9  lea     rax, aWil; "wil"
0x180004ad0  mov     [rsp+14F0h+var_1498], rax
0x180004ad5  mov     [rsp+14F0h+var_1490], esi
0x180004ad9  mov     [rsp+14F0h+var_148C], ebx
0x180004add  mov     [rsp+14F0h+var_14A8], r15
0x180004ae2  mov     [rsp+14F0h+var_14A0], r15
0x180004ae7  mov     [rbp+13F0h+var_1448], rdi
0x180004aeb  mov     [rbp+13F0h+var_1440], r14
0x180004aef  mov     [rsp+14F0h+var_1488], r15
0x180004af4  xorps   xmm0, xmm0
0x180004af7  xor     eax, eax
0x180004af9  movups  [rbp+13F0h+var_1468], xmm0
0x180004afd  mov     [rbp+13F0h+var_1458], rax
0x180004b01  xorps   xmm1, xmm1
0x180004b04  movups  [rsp+14F0h+var_1480], xmm1
0x180004b09  mov     [rbp+13F0h+var_1470], rax
0x180004b0d  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004b14  test    rax, rax
0x180004b17  jz      short loc_180004B24
0x180004b19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b1e  mov     [rbp+13F0h+var_1450], rax
0x180004b22  jmp     short loc_180004B28
0x180004b24  mov     [rbp+13F0h+var_1450], r15
0x180004b28  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004b2f  test    rax, rax
0x180004b32  jz      short loc_180004B3E
0x180004b34  lea     rcx, [rsp+14F0h+var_14D0]
0x180004b39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b3e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004b45  test    rax, rax
0x180004b48  jz      short loc_180004B5E
0x180004b4a  mov     r8d, 400h
0x180004b50  lea     rdx, [rbp+13F0h+var_1430]
0x180004b54  lea     rcx, [rsp+14F0h+var_14D0]
0x180004b59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b5e  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004b65  test    rax, rax
0x180004b68  jz      short loc_180004B74
0x180004b6a  lea     rcx, [rsp+14F0h+var_14D0]
0x180004b6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b74  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004b7b  test    rax, rax
0x180004b7e  jz      short loc_180004B91
0x180004b80  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180004b85  jnz     short loc_180004B91
0x180004b87  lea     rcx, [rsp+14F0h+var_14D0]
0x180004b8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b91  cmp     [rsp+14F0h+var_14C8], r15d
0x180004b96  jge     loc_180004CA4
0x180004b9c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180004ba3  jnz     short loc_180004BC4
0x180004ba5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004bac  test    rax, rax
0x180004baf  jz      short loc_180004BBA
0x180004bb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bb6  test    al, al
0x180004bb8  jmp     short loc_180004BC2
0x180004bba  call    cs:__imp_IsDebuggerPresent
0x180004bc0  test    eax, eax
0x180004bc2  jz      short loc_180004BCB
0x180004bc4  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180004bc9  jz      short loc_180004BF1
0x180004bcb  mov     rax, cs:g_pfnResultLoggingCallback
0x180004bd2  test    rax, rax
0x180004bd5  jz      short loc_180004C4A
0x180004bd7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180004bde  jnz     short loc_180004C4A
0x180004be0  xor     r8d, r8d
0x180004be3  xor     edx, edx
0x180004be5  lea     rcx, [rsp+14F0h+var_14D0]
0x180004bea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bef  jmp     short loc_180004C4A
0x180004bf1  mov     ebx, 800h
0x180004bf6  mov     rax, cs:g_pfnResultLoggingCallback
0x180004bfd  test    rax, rax
0x180004c00  jz      short loc_180004C1F
0x180004c02  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180004c09  jnz     short loc_180004C1F
0x180004c0b  mov     r8d, ebx
0x180004c0e  lea     rdx, [rbp+13F0h+OutputString]
0x180004c15  lea     rcx, [rsp+14F0h+var_14D0]
0x180004c1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c1f  cmp     [rbp+13F0h+OutputString], r15w
0x180004c27  jnz     short loc_180004C3D
0x180004c29  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180004c2e  mov     rdx, rbx; unsigned __int16 *
0x180004c31  lea     rcx, [rbp+13F0h+OutputString]; this
0x180004c38  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004c3d  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180004c44  call    cs:__imp_OutputDebugStringW
0x180004c4a  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180004c4f  jnz     short loc_180004C5A
0x180004c51  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180004c58  jz      short loc_180004C6C
0x180004c5a  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004c61  test    rax, rax
0x180004c64  jz      short loc_180004C6C
0x180004c66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c6b  nop
0x180004c6c  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180004c71  jnz     short loc_180004C99
0x180004c73  mov     rcx, [rbp+13F0h+var_30]
0x180004c7a  xor     rcx, rsp; StackCookie
0x180004c7d  call    __security_check_cookie
0x180004c82  mov     rbx, [rsp+14F0h+arg_10]
0x180004c8a  add     rsp, 14D0h
0x180004c91  pop     r15
0x180004c93  pop     r14
0x180004c95  pop     rdi
0x180004c96  pop     rsi
0x180004c97  pop     rbp
0x180004c98  retn
0x180004c99  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180004c9e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180004ca4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
