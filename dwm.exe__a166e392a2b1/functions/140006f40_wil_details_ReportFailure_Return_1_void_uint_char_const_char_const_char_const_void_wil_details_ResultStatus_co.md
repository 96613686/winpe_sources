# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140006f40`
- end: `0x1400071cb`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `651`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140004b94`

## callees

- `0x140005530`
- `0x1400061b8`
- `0x140006f40`
- `0x140008a44`
- `0x14000a0ac`
- `0x14000b668`
- `0x14000b874`
- `0x14000fc30`
- `0x140010010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006fed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006fed`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400070e1`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400070e1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000716b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000716b`

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
  int v10; // eax
  int v11; // eax
  __int64 v12; // rdx
  int v13; // ebx
  int v14; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v16; // rdx
  wil::details::in1diag3 *v17; // rcx
  const struct wil::FailureInfo *v18; // r9
  bool v19; // zf
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD v26; // [rsp+40h] [rbp-C0h]
  __int64 v27; // [rsp+48h] [rbp-B8h]
  __int64 v28; // [rsp+50h] [rbp-B0h]
  __int64 v29; // [rsp+58h] [rbp-A8h]
  int v30; // [rsp+60h] [rbp-A0h]
  int v31; // [rsp+64h] [rbp-9Ch]
  __int64 v32; // [rsp+68h] [rbp-98h]
  __int128 v33; // [rsp+70h] [rbp-90h]
  __int64 v34; // [rsp+80h] [rbp-80h]
  __int128 v35; // [rsp+88h] [rbp-78h]
  __int64 v36; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v38; // [rsp+A8h] [rbp-58h]
  __int64 v39; // [rsp+B0h] [rbp-50h]
  char v40[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v10 = a7[1];
  v22 = *a7;
  v23 = v10;
  v11 = wil::details::RecordReturn((wil::details *)(unsigned int)v22, (int)a7);
  v19 = *(_DWORD *)(v12 + 8) == 1;
  v13 = v11;
  v20 = 1;
  v14 = 0;
  if ( v19 )
    v14 = 8;
  v21 = v14;
  v25 = 0;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v26 = CurrentThreadId;
  v30 = a2;
  v36 = 0;
  v34 = 0;
  v31 = v13;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v33 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v17);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v17);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v19 = !IsDebuggerPresent())
      : (v19 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v17) == 0),
        v19)
    || (v21 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v20, v18);
    OutputDebugStringW(OutputString);
  }
  if ( ((v21 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v17);
  if ( (v21 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v20, v16);
}

```

## disassembly

```asm
0x140006f40  push    rbp
0x140006f42  push    rbx
0x140006f43  push    rsi
0x140006f44  push    rdi
0x140006f45  push    r12
0x140006f47  push    r14
0x140006f49  push    r15
0x140006f4b  lea     rbp, [rsp-13D0h]
0x140006f53  mov     eax, 14D0h
0x140006f58  call    _alloca_probe
0x140006f5d  sub     rsp, rax
0x140006f60  mov     rax, cs:__security_cookie
0x140006f67  xor     rax, rsp
0x140006f6a  mov     [rbp+1400h+var_40], rax
0x140006f71  mov     rdi, [rbp+1400h+arg_28]
0x140006f78  mov     r14, r8
0x140006f7b  mov     esi, edx
0x140006f7d  mov     r15, rcx
0x140006f80  xor     edx, edx; Val
0x140006f82  lea     rcx, [rsp+1500h+var_14E0]; void *
0x140006f87  mov     r8d, 98h; Size
0x140006f8d  call    memset_0
0x140006f92  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x140006f99  xor     r12d, r12d
0x140006f9c  mov     [rbp+1400h+OutputString], r12w
0x140006fa4  mov     [rbp+1400h+var_1440], r12b
0x140006fa8  mov     ecx, [rdx]; this
0x140006faa  mov     eax, [rdx+4]
0x140006fad  mov     [rsp+1500h+var_14D8], ecx
0x140006fb1  mov     [rsp+1500h+var_14D4], eax
0x140006fb5  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140006fba  cmp     dword ptr [rdx+8], 1
0x140006fbe  mov     ebx, eax
0x140006fc0  lea     eax, [r12+8]
0x140006fc5  mov     dword ptr [rsp+1500h+var_14E0], 1
0x140006fcd  mov     ecx, r12d
0x140006fd0  cmovz   ecx, eax
0x140006fd3  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x140006fd7  lea     ecx, [rax-7]
0x140006fda  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140006fe2  inc     ecx
0x140006fe4  mov     [rsp+1500h+var_14C8], r12
0x140006fe9  mov     [rsp+1500h+var_14D0], ecx
0x140006fed  call    cs:__imp_GetCurrentThreadId
0x140006ff3  xorps   xmm0, xmm0
0x140006ff6  mov     [rsp+1500h+var_14A8], r14
0x140006ffb  mov     [rsp+1500h+var_14C0], eax
0x140006fff  xorps   xmm1, xmm1
0x140007002  xor     eax, eax
0x140007004  mov     [rsp+1500h+var_14A0], esi
0x140007008  mov     [rbp+1400h+var_1468], rax
0x14000700c  mov     [rbp+1400h+var_1480], rax
0x140007010  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140007017  mov     [rsp+1500h+var_149C], ebx
0x14000701b  mov     [rsp+1500h+var_14B8], r12
0x140007020  mov     [rsp+1500h+var_14B0], r12
0x140007025  mov     [rbp+1400h+var_1458], rdi
0x140007029  mov     [rbp+1400h+var_1450], r15
0x14000702d  mov     [rsp+1500h+var_1498], r12
0x140007032  movups  [rbp+1400h+var_1478], xmm0
0x140007036  movups  [rsp+1500h+var_1490], xmm1
0x14000703b  test    rax, rax
0x14000703e  jz      short loc_14000704B
0x140007040  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007045  mov     [rbp+1400h+var_1460], rax
0x140007049  jmp     short loc_14000704F
0x14000704b  mov     [rbp+1400h+var_1460], r12
0x14000704f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140007056  test    rax, rax
0x140007059  jz      short loc_140007065
0x14000705b  lea     rcx, [rsp+1500h+var_14E0]
0x140007060  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007065  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000706c  test    rax, rax
0x14000706f  jz      short loc_140007085
0x140007071  mov     r8d, 400h
0x140007077  lea     rdx, [rbp+1400h+var_1440]
0x14000707b  lea     rcx, [rsp+1500h+var_14E0]
0x140007080  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007085  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000708c  test    rax, rax
0x14000708f  jz      short loc_14000709B
0x140007091  lea     rcx, [rsp+1500h+var_14E0]
0x140007096  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000709b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400070a2  test    rax, rax
0x1400070a5  jz      short loc_1400070B8
0x1400070a7  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1400070ac  jnz     short loc_1400070B8
0x1400070ae  lea     rcx, [rsp+1500h+var_14E0]
0x1400070b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400070b8  cmp     [rsp+1500h+var_14D8], r12d
0x1400070bd  jge     loc_1400071BA
0x1400070c3  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1400070ca  jnz     short loc_1400070EB
0x1400070cc  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400070d3  test    rax, rax
0x1400070d6  jz      short loc_1400070E1
0x1400070d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400070dd  test    al, al
0x1400070df  jmp     short loc_1400070E9
0x1400070e1  call    cs:__imp_IsDebuggerPresent
0x1400070e7  test    eax, eax
0x1400070e9  jz      short loc_1400070F2
0x1400070eb  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1400070f0  jz      short loc_140007118
0x1400070f2  mov     rax, cs:g_pfnResultLoggingCallback
0x1400070f9  test    rax, rax
0x1400070fc  jz      short loc_140007171
0x1400070fe  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140007105  jnz     short loc_140007171
0x140007107  xor     r8d, r8d
0x14000710a  lea     rcx, [rsp+1500h+var_14E0]
0x14000710f  xor     edx, edx
0x140007111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007116  jmp     short loc_140007171
0x140007118  mov     rax, cs:g_pfnResultLoggingCallback
0x14000711f  mov     ebx, 800h
0x140007124  test    rax, rax
0x140007127  jz      short loc_140007146
0x140007129  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140007130  jnz     short loc_140007146
0x140007132  mov     r8d, ebx
0x140007135  lea     rdx, [rbp+1400h+OutputString]
0x14000713c  lea     rcx, [rsp+1500h+var_14E0]
0x140007141  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007146  cmp     [rbp+1400h+OutputString], r12w
0x14000714e  jnz     short loc_140007164
0x140007150  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x140007155  mov     rdx, rbx; unsigned __int16 *
0x140007158  lea     rcx, [rbp+1400h+OutputString]; this
0x14000715f  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140007164  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x14000716b  call    cs:__imp_OutputDebugStringW
0x140007171  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x140007176  jnz     short loc_140007181
0x140007178  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x14000717f  jz      short loc_140007192
0x140007181  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140007188  test    rax, rax
0x14000718b  jz      short loc_140007192
0x14000718d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007192  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x140007197  jnz     short loc_1400071C0
0x140007199  mov     rcx, [rbp+1400h+var_40]
0x1400071a0  xor     rcx, rsp; StackCookie
0x1400071a3  call    __security_check_cookie
0x1400071a8  add     rsp, 14D0h
0x1400071af  pop     r15
0x1400071b1  pop     r14
0x1400071b3  pop     r12
0x1400071b5  pop     rdi
0x1400071b6  pop     rsi
0x1400071b7  pop     rbx
0x1400071b8  pop     rbp
0x1400071b9  retn
0x1400071ba  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1400071c0  lea     rcx, [rsp+1500h+var_14E0]; this
0x1400071c5  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
