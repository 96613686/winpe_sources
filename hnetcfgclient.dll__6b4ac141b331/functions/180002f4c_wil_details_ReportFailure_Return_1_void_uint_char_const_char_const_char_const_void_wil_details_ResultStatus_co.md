# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180002f4c`
- end: `0x1800031e2`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180002c14`

## callees

- `0x180002f4c`
- `0x180003db4`
- `0x180004e60`
- `0x180005a58`
- `0x180005ca0`
- `0x18002d1d2`
- `0x18002d200`
- `0x18002d2c0`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002ff7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002ff7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000317c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000317c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800030f2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800030f2`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
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
0x180002f4c  mov     [rsp-8+arg_10], rbx
0x180002f51  push    rbp
0x180002f52  push    rsi
0x180002f53  push    rdi
0x180002f54  push    r14
0x180002f56  push    r15
0x180002f58  lea     rbp, [rsp-13D0h]
0x180002f60  mov     eax, 14D0h
0x180002f65  call    _alloca_probe
0x180002f6a  sub     rsp, rax
0x180002f6d  mov     rax, cs:__security_cookie
0x180002f74  xor     rax, rsp
0x180002f77  mov     [rbp+13F0h+var_30], rax
0x180002f7e  mov     esi, edx
0x180002f80  mov     r14, rcx
0x180002f83  mov     rdi, [rbp+13F0h+arg_28]
0x180002f8a  xor     edx, edx; Val
0x180002f8c  mov     r8d, 98h; Size
0x180002f92  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180002f97  call    memset_0
0x180002f9c  nop
0x180002f9d  xor     r15d, r15d
0x180002fa0  mov     [rbp+13F0h+OutputString], r15w
0x180002fa8  mov     [rbp+13F0h+var_1430], r15b
0x180002fac  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180002fb3  mov     ecx, [rdx]; this
0x180002fb5  mov     [rsp+14F0h+var_14C8], ecx
0x180002fb9  mov     eax, [rdx+4]
0x180002fbc  mov     [rsp+14F0h+var_14C4], eax
0x180002fc0  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180002fc5  mov     ebx, eax
0x180002fc7  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180002fcf  mov     ecx, r15d
0x180002fd2  lea     eax, [r15+8]
0x180002fd6  cmp     dword ptr [rdx+8], 1
0x180002fda  cmovz   ecx, eax
0x180002fdd  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180002fe1  lea     ecx, [rax-7]
0x180002fe4  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002fec  inc     ecx
0x180002fee  mov     [rsp+14F0h+var_14C0], ecx
0x180002ff2  mov     [rsp+14F0h+var_14B8], r15
0x180002ff7  call    cs:__imp_GetCurrentThreadId
0x180002ffd  mov     [rsp+14F0h+var_14B0], eax
0x180003001  lea     rax, aWil; "wil"
0x180003008  mov     [rsp+14F0h+var_1498], rax
0x18000300d  mov     [rsp+14F0h+var_1490], esi
0x180003011  mov     [rsp+14F0h+var_148C], ebx
0x180003015  mov     [rsp+14F0h+var_14A8], r15
0x18000301a  mov     [rsp+14F0h+var_14A0], r15
0x18000301f  mov     [rbp+13F0h+var_1448], rdi
0x180003023  mov     [rbp+13F0h+var_1440], r14
0x180003027  mov     [rsp+14F0h+var_1488], r15
0x18000302c  xorps   xmm0, xmm0
0x18000302f  xor     eax, eax
0x180003031  movups  [rbp+13F0h+var_1468], xmm0
0x180003035  mov     [rbp+13F0h+var_1458], rax
0x180003039  xorps   xmm1, xmm1
0x18000303c  movups  [rsp+14F0h+var_1480], xmm1
0x180003041  mov     [rbp+13F0h+var_1470], rax
0x180003045  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000304c  test    rax, rax
0x18000304f  jz      short loc_18000305C
0x180003051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003056  mov     [rbp+13F0h+var_1450], rax
0x18000305a  jmp     short loc_180003060
0x18000305c  mov     [rbp+13F0h+var_1450], r15
0x180003060  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003067  test    rax, rax
0x18000306a  jz      short loc_180003076
0x18000306c  lea     rcx, [rsp+14F0h+var_14D0]
0x180003071  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003076  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000307d  test    rax, rax
0x180003080  jz      short loc_180003096
0x180003082  mov     r8d, 400h
0x180003088  lea     rdx, [rbp+13F0h+var_1430]
0x18000308c  lea     rcx, [rsp+14F0h+var_14D0]
0x180003091  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003096  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000309d  test    rax, rax
0x1800030a0  jz      short loc_1800030AC
0x1800030a2  lea     rcx, [rsp+14F0h+var_14D0]
0x1800030a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030ac  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800030b3  test    rax, rax
0x1800030b6  jz      short loc_1800030C9
0x1800030b8  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800030bd  jnz     short loc_1800030C9
0x1800030bf  lea     rcx, [rsp+14F0h+var_14D0]
0x1800030c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030c9  cmp     [rsp+14F0h+var_14C8], r15d
0x1800030ce  jge     loc_1800031DC
0x1800030d4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x1800030db  jnz     short loc_1800030FC
0x1800030dd  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800030e4  test    rax, rax
0x1800030e7  jz      short loc_1800030F2
0x1800030e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030ee  test    al, al
0x1800030f0  jmp     short loc_1800030FA
0x1800030f2  call    cs:__imp_IsDebuggerPresent
0x1800030f8  test    eax, eax
0x1800030fa  jz      short loc_180003103
0x1800030fc  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003101  jz      short loc_180003129
0x180003103  mov     rax, cs:g_pfnResultLoggingCallback
0x18000310a  test    rax, rax
0x18000310d  jz      short loc_180003182
0x18000310f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180003116  jnz     short loc_180003182
0x180003118  xor     r8d, r8d
0x18000311b  xor     edx, edx
0x18000311d  lea     rcx, [rsp+14F0h+var_14D0]
0x180003122  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003127  jmp     short loc_180003182
0x180003129  mov     ebx, 800h
0x18000312e  mov     rax, cs:g_pfnResultLoggingCallback
0x180003135  test    rax, rax
0x180003138  jz      short loc_180003157
0x18000313a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180003141  jnz     short loc_180003157
0x180003143  mov     r8d, ebx
0x180003146  lea     rdx, [rbp+13F0h+OutputString]
0x18000314d  lea     rcx, [rsp+14F0h+var_14D0]
0x180003152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003157  cmp     [rbp+13F0h+OutputString], r15w
0x18000315f  jnz     short loc_180003175
0x180003161  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180003166  mov     rdx, rbx; unsigned __int16 *
0x180003169  lea     rcx, [rbp+13F0h+OutputString]; this
0x180003170  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003175  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000317c  call    cs:__imp_OutputDebugStringW
0x180003182  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180003187  jnz     short loc_180003192
0x180003189  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180003190  jz      short loc_1800031A4
0x180003192  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003199  test    rax, rax
0x18000319c  jz      short loc_1800031A4
0x18000319e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031a3  nop
0x1800031a4  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x1800031a9  jnz     short loc_1800031D1
0x1800031ab  mov     rcx, [rbp+13F0h+var_30]
0x1800031b2  xor     rcx, rsp; StackCookie
0x1800031b5  call    __security_check_cookie
0x1800031ba  mov     rbx, [rsp+14F0h+arg_10]
0x1800031c2  add     rsp, 14D0h
0x1800031c9  pop     r15
0x1800031cb  pop     r14
0x1800031cd  pop     rdi
0x1800031ce  pop     rsi
0x1800031cf  pop     rbp
0x1800031d0  retn
0x1800031d1  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800031d6  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800031dc  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
