# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180002f44`
- end: `0x1800031fd`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `697`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180002a40`

## callees

- `0x180001800`
- `0x1800023e0`
- `0x180002f44`
- `0x1800046d4`
- `0x1800058e4`
- `0x180007350`
- `0x18000748c`
- `0x180025230`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000300a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000300a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003105`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003105`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003195`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003195`

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
0x180002f44  push    rbp
0x180002f46  push    rbx
0x180002f47  push    rsi
0x180002f48  push    rdi
0x180002f49  push    r12
0x180002f4b  push    r14
0x180002f4d  push    r15
0x180002f4f  lea     rbp, [rsp-13D0h]
0x180002f57  mov     eax, 14D0h
0x180002f5c  call    _alloca_probe
0x180002f61  sub     rsp, rax
0x180002f64  mov     rax, cs:__security_cookie
0x180002f6b  xor     rax, rsp
0x180002f6e  mov     [rbp+1400h+var_40], rax
0x180002f75  mov     rsi, r8
0x180002f78  mov     edi, edx
0x180002f7a  mov     rbx, rcx
0x180002f7d  mov     r14, [rbp+1400h+arg_28]
0x180002f84  xor     edx, edx; Val
0x180002f86  mov     r8d, 98h; Size
0x180002f8c  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180002f91  call    memset_0
0x180002f96  nop
0x180002f97  xor     r12d, r12d
0x180002f9a  mov     [rbp+1400h+OutputString], r12w
0x180002fa2  mov     [rbp+1400h+var_1440], r12b
0x180002fa6  mov     rdx, [rbp+1400h+arg_30]; int
0x180002fad  mov     ecx, [rdx]; this
0x180002faf  mov     [rsp+1500h+var_14D8], ecx
0x180002fb3  mov     eax, [rdx+4]
0x180002fb6  mov     [rsp+1500h+var_14D4], eax
0x180002fba  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180002fbf  mov     r15d, eax
0x180002fc2  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180002fca  mov     ecx, r12d
0x180002fcd  lea     eax, [r12+8]
0x180002fd2  cmp     dword ptr [rdx+8], 1
0x180002fd6  cmovz   ecx, eax
0x180002fd9  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180002fdd  lea     ecx, [rax-7]
0x180002fe0  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002fe8  inc     ecx
0x180002fea  mov     [rsp+1500h+var_14D0], ecx
0x180002fee  mov     rcx, [rbp+1400h+arg_38]
0x180002ff5  test    rcx, rcx
0x180002ff8  jz      short loc_180003005
0x180002ffa  cmp     [rcx], r12w
0x180002ffe  mov     [rsp+1500h+var_14C8], rcx
0x180003003  jnz     short loc_18000300A
0x180003005  mov     [rsp+1500h+var_14C8], r12
0x18000300a  call    cs:__imp_GetCurrentThreadId
0x180003011  nop     dword ptr [rax+rax+00h]
0x180003016  mov     [rsp+1500h+var_14C0], eax
0x18000301a  mov     [rsp+1500h+var_14A8], rsi
0x18000301f  mov     [rsp+1500h+var_14A0], edi
0x180003023  mov     [rsp+1500h+var_149C], r15d
0x180003028  mov     [rsp+1500h+var_14B8], r12
0x18000302d  mov     [rsp+1500h+var_14B0], r12
0x180003032  mov     [rbp+1400h+var_1458], r14
0x180003036  mov     [rbp+1400h+var_1450], rbx
0x18000303a  mov     [rsp+1500h+var_1498], r12
0x18000303f  xorps   xmm0, xmm0
0x180003042  xor     eax, eax
0x180003044  movups  [rbp+1400h+var_1478], xmm0
0x180003048  mov     [rbp+1400h+var_1468], rax
0x18000304c  xorps   xmm1, xmm1
0x18000304f  movups  [rsp+1500h+var_1490], xmm1
0x180003054  mov     [rbp+1400h+var_1480], rax
0x180003058  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000305f  test    rax, rax
0x180003062  jz      short loc_18000306F
0x180003064  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003069  mov     [rbp+1400h+var_1460], rax
0x18000306d  jmp     short loc_180003073
0x18000306f  mov     [rbp+1400h+var_1460], r12
0x180003073  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000307a  test    rax, rax
0x18000307d  jz      short loc_180003089
0x18000307f  lea     rcx, [rsp+1500h+var_14E0]
0x180003084  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003089  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003090  test    rax, rax
0x180003093  jz      short loc_1800030A9
0x180003095  mov     r8d, 400h
0x18000309b  lea     rdx, [rbp+1400h+var_1440]
0x18000309f  lea     rcx, [rsp+1500h+var_14E0]
0x1800030a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030a9  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800030b0  test    rax, rax
0x1800030b3  jz      short loc_1800030BF
0x1800030b5  lea     rcx, [rsp+1500h+var_14E0]
0x1800030ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030bf  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800030c6  test    rax, rax
0x1800030c9  jz      short loc_1800030DC
0x1800030cb  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800030d0  jnz     short loc_1800030DC
0x1800030d2  lea     rcx, [rsp+1500h+var_14E0]
0x1800030d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030dc  cmp     [rsp+1500h+var_14D8], r12d
0x1800030e1  jge     loc_1800031F7
0x1800030e7  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800030ee  jnz     short loc_180003115
0x1800030f0  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800030f7  test    rax, rax
0x1800030fa  jz      short loc_180003105
0x1800030fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003101  test    al, al
0x180003103  jmp     short loc_180003113
0x180003105  call    cs:__imp_IsDebuggerPresent
0x18000310c  nop     dword ptr [rax+rax+00h]
0x180003111  test    eax, eax
0x180003113  jz      short loc_18000311C
0x180003115  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000311a  jz      short loc_180003142
0x18000311c  mov     rax, cs:g_pfnResultLoggingCallback
0x180003123  test    rax, rax
0x180003126  jz      short loc_1800031A1
0x180003128  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000312f  jnz     short loc_1800031A1
0x180003131  xor     r8d, r8d
0x180003134  xor     edx, edx
0x180003136  lea     rcx, [rsp+1500h+var_14E0]
0x18000313b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003140  jmp     short loc_1800031A1
0x180003142  mov     ebx, 800h
0x180003147  mov     rax, cs:g_pfnResultLoggingCallback
0x18000314e  test    rax, rax
0x180003151  jz      short loc_180003170
0x180003153  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000315a  jnz     short loc_180003170
0x18000315c  mov     r8d, ebx
0x18000315f  lea     rdx, [rbp+1400h+OutputString]
0x180003166  lea     rcx, [rsp+1500h+var_14E0]
0x18000316b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003170  cmp     [rbp+1400h+OutputString], r12w
0x180003178  jnz     short loc_18000318E
0x18000317a  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18000317f  mov     rdx, rbx; unsigned __int16 *
0x180003182  lea     rcx, [rbp+1400h+OutputString]; this
0x180003189  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000318e  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180003195  call    cs:__imp_OutputDebugStringW
0x18000319c  nop     dword ptr [rax+rax+00h]
0x1800031a1  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1800031a6  jnz     short loc_1800031B1
0x1800031a8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800031af  jz      short loc_1800031C3
0x1800031b1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800031b8  test    rax, rax
0x1800031bb  jz      short loc_1800031C3
0x1800031bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031c2  nop
0x1800031c3  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1800031c8  jnz     short loc_1800031EC
0x1800031ca  mov     rcx, [rbp+1400h+var_40]
0x1800031d1  xor     rcx, rsp; StackCookie
0x1800031d4  call    __security_check_cookie
0x1800031d9  add     rsp, 14D0h
0x1800031e0  pop     r15
0x1800031e2  pop     r14
0x1800031e4  pop     r12
0x1800031e6  pop     rdi
0x1800031e7  pop     rsi
0x1800031e8  pop     rbx
0x1800031e9  pop     rbp
0x1800031ea  retn
0x1800031ec  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800031f1  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800031f7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
