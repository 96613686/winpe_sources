# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180002ef8`
- end: `0x18000318e`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800029d8`

## callees

- `0x180001d00`
- `0x180002722`
- `0x180002ef8`
- `0x180004034`
- `0x180004f60`
- `0x180005fb0`
- `0x18000608c`
- `0x18000c6c0`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002fa3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002fa3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000309e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000309e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003128`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003128`

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
0x180002ef8  mov     [rsp-8+arg_10], rbx
0x180002efd  push    rbp
0x180002efe  push    rsi
0x180002eff  push    rdi
0x180002f00  push    r14
0x180002f02  push    r15
0x180002f04  lea     rbp, [rsp-13D0h]
0x180002f0c  mov     eax, 14D0h
0x180002f11  call    _alloca_probe
0x180002f16  sub     rsp, rax
0x180002f19  mov     rax, cs:__security_cookie
0x180002f20  xor     rax, rsp
0x180002f23  mov     [rbp+13F0h+var_30], rax
0x180002f2a  mov     esi, edx
0x180002f2c  mov     r14, rcx
0x180002f2f  mov     rdi, [rbp+13F0h+arg_28]
0x180002f36  xor     edx, edx; Val
0x180002f38  mov     r8d, 98h; Size
0x180002f3e  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180002f43  call    memset_0
0x180002f48  nop
0x180002f49  xor     r15d, r15d
0x180002f4c  mov     [rbp+13F0h+OutputString], r15w
0x180002f54  mov     [rbp+13F0h+var_1430], r15b
0x180002f58  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180002f5f  mov     ecx, [rdx]; this
0x180002f61  mov     [rsp+14F0h+var_14C8], ecx
0x180002f65  mov     eax, [rdx+4]
0x180002f68  mov     [rsp+14F0h+var_14C4], eax
0x180002f6c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180002f71  mov     ebx, eax
0x180002f73  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180002f7b  mov     ecx, r15d
0x180002f7e  lea     eax, [r15+8]
0x180002f82  cmp     dword ptr [rdx+8], 1
0x180002f86  cmovz   ecx, eax
0x180002f89  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180002f8d  lea     ecx, [rax-7]
0x180002f90  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002f98  inc     ecx
0x180002f9a  mov     [rsp+14F0h+var_14C0], ecx
0x180002f9e  mov     [rsp+14F0h+var_14B8], r15
0x180002fa3  call    cs:__imp_GetCurrentThreadId
0x180002fa9  mov     [rsp+14F0h+var_14B0], eax
0x180002fad  lea     rax, aWil; "wil"
0x180002fb4  mov     [rsp+14F0h+var_1498], rax
0x180002fb9  mov     [rsp+14F0h+var_1490], esi
0x180002fbd  mov     [rsp+14F0h+var_148C], ebx
0x180002fc1  mov     [rsp+14F0h+var_14A8], r15
0x180002fc6  mov     [rsp+14F0h+var_14A0], r15
0x180002fcb  mov     [rbp+13F0h+var_1448], rdi
0x180002fcf  mov     [rbp+13F0h+var_1440], r14
0x180002fd3  mov     [rsp+14F0h+var_1488], r15
0x180002fd8  xorps   xmm0, xmm0
0x180002fdb  xor     eax, eax
0x180002fdd  movups  [rbp+13F0h+var_1468], xmm0
0x180002fe1  mov     [rbp+13F0h+var_1458], rax
0x180002fe5  xorps   xmm1, xmm1
0x180002fe8  movups  [rsp+14F0h+var_1480], xmm1
0x180002fed  mov     [rbp+13F0h+var_1470], rax
0x180002ff1  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002ff8  test    rax, rax
0x180002ffb  jz      short loc_180003008
0x180002ffd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003002  mov     [rbp+13F0h+var_1450], rax
0x180003006  jmp     short loc_18000300C
0x180003008  mov     [rbp+13F0h+var_1450], r15
0x18000300c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003013  test    rax, rax
0x180003016  jz      short loc_180003022
0x180003018  lea     rcx, [rsp+14F0h+var_14D0]
0x18000301d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003022  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003029  test    rax, rax
0x18000302c  jz      short loc_180003042
0x18000302e  mov     r8d, 400h
0x180003034  lea     rdx, [rbp+13F0h+var_1430]
0x180003038  lea     rcx, [rsp+14F0h+var_14D0]
0x18000303d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003042  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003049  test    rax, rax
0x18000304c  jz      short loc_180003058
0x18000304e  lea     rcx, [rsp+14F0h+var_14D0]
0x180003053  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003058  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000305f  test    rax, rax
0x180003062  jz      short loc_180003075
0x180003064  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003069  jnz     short loc_180003075
0x18000306b  lea     rcx, [rsp+14F0h+var_14D0]
0x180003070  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003075  cmp     [rsp+14F0h+var_14C8], r15d
0x18000307a  jge     loc_180003188
0x180003080  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180003087  jnz     short loc_1800030A8
0x180003089  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003090  test    rax, rax
0x180003093  jz      short loc_18000309E
0x180003095  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000309a  test    al, al
0x18000309c  jmp     short loc_1800030A6
0x18000309e  call    cs:__imp_IsDebuggerPresent
0x1800030a4  test    eax, eax
0x1800030a6  jz      short loc_1800030AF
0x1800030a8  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800030ad  jz      short loc_1800030D5
0x1800030af  mov     rax, cs:g_pfnResultLoggingCallback
0x1800030b6  test    rax, rax
0x1800030b9  jz      short loc_18000312E
0x1800030bb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800030c2  jnz     short loc_18000312E
0x1800030c4  xor     r8d, r8d
0x1800030c7  xor     edx, edx
0x1800030c9  lea     rcx, [rsp+14F0h+var_14D0]
0x1800030ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030d3  jmp     short loc_18000312E
0x1800030d5  mov     ebx, 800h
0x1800030da  mov     rax, cs:g_pfnResultLoggingCallback
0x1800030e1  test    rax, rax
0x1800030e4  jz      short loc_180003103
0x1800030e6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800030ed  jnz     short loc_180003103
0x1800030ef  mov     r8d, ebx
0x1800030f2  lea     rdx, [rbp+13F0h+OutputString]
0x1800030f9  lea     rcx, [rsp+14F0h+var_14D0]
0x1800030fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003103  cmp     [rbp+13F0h+OutputString], r15w
0x18000310b  jnz     short loc_180003121
0x18000310d  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180003112  mov     rdx, rbx; unsigned __int16 *
0x180003115  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000311c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003121  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180003128  call    cs:__imp_OutputDebugStringW
0x18000312e  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180003133  jnz     short loc_18000313E
0x180003135  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18000313c  jz      short loc_180003150
0x18000313e  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003145  test    rax, rax
0x180003148  jz      short loc_180003150
0x18000314a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000314f  nop
0x180003150  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180003155  jnz     short loc_18000317D
0x180003157  mov     rcx, [rbp+13F0h+var_30]
0x18000315e  xor     rcx, rsp; StackCookie
0x180003161  call    __security_check_cookie
0x180003166  mov     rbx, [rsp+14F0h+arg_10]
0x18000316e  add     rsp, 14D0h
0x180003175  pop     r15
0x180003177  pop     r14
0x180003179  pop     rdi
0x18000317a  pop     rsi
0x18000317b  pop     rbp
0x18000317c  retn
0x18000317d  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180003182  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180003188  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
