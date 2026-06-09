# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180012c80`
- end: `0x180012f39`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `697`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180012904`

## callees

- `0x18000c568`
- `0x180012c80`
- `0x180018944`
- `0x18001b4f0`
- `0x18001b82c`
- `0x1800227f2`
- `0x180022830`
- `0x1800228f0`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012d46`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012d46`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180012e41`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180012e41`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180012ed1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180012ed1`

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
0x180012c80  push    rbp
0x180012c82  push    rbx
0x180012c83  push    rsi
0x180012c84  push    rdi
0x180012c85  push    r12
0x180012c87  push    r14
0x180012c89  push    r15
0x180012c8b  lea     rbp, [rsp-13D0h]
0x180012c93  mov     eax, 14D0h
0x180012c98  call    _alloca_probe
0x180012c9d  sub     rsp, rax
0x180012ca0  mov     rax, cs:__security_cookie
0x180012ca7  xor     rax, rsp
0x180012caa  mov     [rbp+1400h+var_40], rax
0x180012cb1  mov     rsi, r8
0x180012cb4  mov     edi, edx
0x180012cb6  mov     rbx, rcx
0x180012cb9  mov     r14, [rbp+1400h+arg_28]
0x180012cc0  xor     edx, edx; Val
0x180012cc2  mov     r8d, 98h; Size
0x180012cc8  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180012ccd  call    memset_0
0x180012cd2  nop
0x180012cd3  xor     r12d, r12d
0x180012cd6  mov     [rbp+1400h+OutputString], r12w
0x180012cde  mov     [rbp+1400h+var_1440], r12b
0x180012ce2  mov     rdx, [rbp+1400h+arg_30]; int
0x180012ce9  mov     ecx, [rdx]; this
0x180012ceb  mov     [rsp+1500h+var_14D8], ecx
0x180012cef  mov     eax, [rdx+4]
0x180012cf2  mov     [rsp+1500h+var_14D4], eax
0x180012cf6  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180012cfb  mov     r15d, eax
0x180012cfe  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180012d06  mov     ecx, r12d
0x180012d09  lea     eax, [r12+8]
0x180012d0e  cmp     dword ptr [rdx+8], 1
0x180012d12  cmovz   ecx, eax
0x180012d15  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180012d19  lea     ecx, [rax-7]
0x180012d1c  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180012d24  inc     ecx
0x180012d26  mov     [rsp+1500h+var_14D0], ecx
0x180012d2a  mov     rcx, [rbp+1400h+arg_38]
0x180012d31  test    rcx, rcx
0x180012d34  jz      short loc_180012D41
0x180012d36  cmp     [rcx], r12w
0x180012d3a  mov     [rsp+1500h+var_14C8], rcx
0x180012d3f  jnz     short loc_180012D46
0x180012d41  mov     [rsp+1500h+var_14C8], r12
0x180012d46  call    cs:__imp_GetCurrentThreadId
0x180012d4d  nop     dword ptr [rax+rax+00h]
0x180012d52  mov     [rsp+1500h+var_14C0], eax
0x180012d56  mov     [rsp+1500h+var_14A8], rsi
0x180012d5b  mov     [rsp+1500h+var_14A0], edi
0x180012d5f  mov     [rsp+1500h+var_149C], r15d
0x180012d64  mov     [rsp+1500h+var_14B8], r12
0x180012d69  mov     [rsp+1500h+var_14B0], r12
0x180012d6e  mov     [rbp+1400h+var_1458], r14
0x180012d72  mov     [rbp+1400h+var_1450], rbx
0x180012d76  mov     [rsp+1500h+var_1498], r12
0x180012d7b  xorps   xmm0, xmm0
0x180012d7e  xor     eax, eax
0x180012d80  movups  [rbp+1400h+var_1478], xmm0
0x180012d84  mov     [rbp+1400h+var_1468], rax
0x180012d88  xorps   xmm1, xmm1
0x180012d8b  movups  [rsp+1500h+var_1490], xmm1
0x180012d90  mov     [rbp+1400h+var_1480], rax
0x180012d94  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180012d9b  test    rax, rax
0x180012d9e  jz      short loc_180012DAB
0x180012da0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012da5  mov     [rbp+1400h+var_1460], rax
0x180012da9  jmp     short loc_180012DAF
0x180012dab  mov     [rbp+1400h+var_1460], r12
0x180012daf  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180012db6  test    rax, rax
0x180012db9  jz      short loc_180012DC5
0x180012dbb  lea     rcx, [rsp+1500h+var_14E0]
0x180012dc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012dc5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180012dcc  test    rax, rax
0x180012dcf  jz      short loc_180012DE5
0x180012dd1  mov     r8d, 400h
0x180012dd7  lea     rdx, [rbp+1400h+var_1440]
0x180012ddb  lea     rcx, [rsp+1500h+var_14E0]
0x180012de0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012de5  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180012dec  test    rax, rax
0x180012def  jz      short loc_180012DFB
0x180012df1  lea     rcx, [rsp+1500h+var_14E0]
0x180012df6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012dfb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180012e02  test    rax, rax
0x180012e05  jz      short loc_180012E18
0x180012e07  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180012e0c  jnz     short loc_180012E18
0x180012e0e  lea     rcx, [rsp+1500h+var_14E0]
0x180012e13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e18  cmp     [rsp+1500h+var_14D8], r12d
0x180012e1d  jge     loc_180012F33
0x180012e23  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180012e2a  jnz     short loc_180012E51
0x180012e2c  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180012e33  test    rax, rax
0x180012e36  jz      short loc_180012E41
0x180012e38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e3d  test    al, al
0x180012e3f  jmp     short loc_180012E4F
0x180012e41  call    cs:__imp_IsDebuggerPresent
0x180012e48  nop     dword ptr [rax+rax+00h]
0x180012e4d  test    eax, eax
0x180012e4f  jz      short loc_180012E58
0x180012e51  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180012e56  jz      short loc_180012E7E
0x180012e58  mov     rax, cs:g_pfnResultLoggingCallback
0x180012e5f  test    rax, rax
0x180012e62  jz      short loc_180012EDD
0x180012e64  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180012e6b  jnz     short loc_180012EDD
0x180012e6d  xor     r8d, r8d
0x180012e70  xor     edx, edx
0x180012e72  lea     rcx, [rsp+1500h+var_14E0]
0x180012e77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e7c  jmp     short loc_180012EDD
0x180012e7e  mov     ebx, 800h
0x180012e83  mov     rax, cs:g_pfnResultLoggingCallback
0x180012e8a  test    rax, rax
0x180012e8d  jz      short loc_180012EAC
0x180012e8f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180012e96  jnz     short loc_180012EAC
0x180012e98  mov     r8d, ebx
0x180012e9b  lea     rdx, [rbp+1400h+OutputString]
0x180012ea2  lea     rcx, [rsp+1500h+var_14E0]
0x180012ea7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012eac  cmp     [rbp+1400h+OutputString], r12w
0x180012eb4  jnz     short loc_180012ECA
0x180012eb6  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180012ebb  mov     rdx, rbx; unsigned __int16 *
0x180012ebe  lea     rcx, [rbp+1400h+OutputString]; this
0x180012ec5  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180012eca  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180012ed1  call    cs:__imp_OutputDebugStringW
0x180012ed8  nop     dword ptr [rax+rax+00h]
0x180012edd  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180012ee2  jnz     short loc_180012EED
0x180012ee4  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180012eeb  jz      short loc_180012EFF
0x180012eed  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180012ef4  test    rax, rax
0x180012ef7  jz      short loc_180012EFF
0x180012ef9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012efe  nop
0x180012eff  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180012f04  jnz     short loc_180012F28
0x180012f06  mov     rcx, [rbp+1400h+var_40]
0x180012f0d  xor     rcx, rsp; StackCookie
0x180012f10  call    __security_check_cookie
0x180012f15  add     rsp, 14D0h
0x180012f1c  pop     r15
0x180012f1e  pop     r14
0x180012f20  pop     r12
0x180012f22  pop     rdi
0x180012f23  pop     rsi
0x180012f24  pop     rbx
0x180012f25  pop     rbp
0x180012f26  retn
0x180012f28  lea     rcx, [rsp+1500h+var_14E0]; this
0x180012f2d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180012f33  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
