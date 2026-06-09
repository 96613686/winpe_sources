# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180007104`
- end: `0x180007391`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180006dd0`

## callees

- `0x180002270`
- `0x180002c2c`
- `0x180007104`
- `0x18000a91c`
- `0x18000f840`
- `0x180013208`
- `0x180013904`
- `0x180022330`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800071b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800071b2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007330`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007330`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800072a6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800072a6`

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
0x180007104  push    rbp
0x180007106  push    rbx
0x180007107  push    rsi
0x180007108  push    rdi
0x180007109  push    r12
0x18000710b  push    r14
0x18000710d  push    r15
0x18000710f  lea     rbp, [rsp-13D0h]
0x180007117  mov     eax, 14D0h
0x18000711c  call    _alloca_probe
0x180007121  sub     rsp, rax
0x180007124  mov     rax, cs:__security_cookie
0x18000712b  xor     rax, rsp
0x18000712e  mov     [rbp+1400h+var_40], rax
0x180007135  mov     r14, r8
0x180007138  mov     esi, edx
0x18000713a  mov     r15, rcx
0x18000713d  mov     rdi, [rbp+1400h+arg_28]
0x180007144  xor     edx, edx; Val
0x180007146  mov     r8d, 98h; Size
0x18000714c  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180007151  call    memset_0
0x180007156  nop
0x180007157  xor     r12d, r12d
0x18000715a  mov     [rbp+1400h+OutputString], r12w
0x180007162  mov     [rbp+1400h+var_1440], r12b
0x180007166  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x18000716d  mov     ecx, [rdx]; this
0x18000716f  mov     [rsp+1500h+var_14D8], ecx
0x180007173  mov     eax, [rdx+4]
0x180007176  mov     [rsp+1500h+var_14D4], eax
0x18000717a  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000717f  mov     ebx, eax
0x180007181  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180007189  mov     ecx, r12d
0x18000718c  lea     eax, [r12+8]
0x180007191  cmp     dword ptr [rdx+8], 1
0x180007195  cmovz   ecx, eax
0x180007198  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18000719c  lea     ecx, [rax-7]
0x18000719f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800071a7  inc     ecx
0x1800071a9  mov     [rsp+1500h+var_14D0], ecx
0x1800071ad  mov     [rsp+1500h+var_14C8], r12
0x1800071b2  call    cs:__imp_GetCurrentThreadId
0x1800071b8  mov     [rsp+1500h+var_14C0], eax
0x1800071bc  mov     [rsp+1500h+var_14A8], r14
0x1800071c1  mov     [rsp+1500h+var_14A0], esi
0x1800071c5  mov     [rsp+1500h+var_149C], ebx
0x1800071c9  mov     [rsp+1500h+var_14B8], r12
0x1800071ce  mov     [rsp+1500h+var_14B0], r12
0x1800071d3  mov     [rbp+1400h+var_1458], rdi
0x1800071d7  mov     [rbp+1400h+var_1450], r15
0x1800071db  mov     [rsp+1500h+var_1498], r12
0x1800071e0  xorps   xmm0, xmm0
0x1800071e3  xor     eax, eax
0x1800071e5  movups  [rbp+1400h+var_1478], xmm0
0x1800071e9  mov     [rbp+1400h+var_1468], rax
0x1800071ed  xorps   xmm1, xmm1
0x1800071f0  movups  [rsp+1500h+var_1490], xmm1
0x1800071f5  mov     [rbp+1400h+var_1480], rax
0x1800071f9  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180007200  test    rax, rax
0x180007203  jz      short loc_180007210
0x180007205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000720a  mov     [rbp+1400h+var_1460], rax
0x18000720e  jmp     short loc_180007214
0x180007210  mov     [rbp+1400h+var_1460], r12
0x180007214  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000721b  test    rax, rax
0x18000721e  jz      short loc_18000722A
0x180007220  lea     rcx, [rsp+1500h+var_14E0]
0x180007225  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000722a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180007231  test    rax, rax
0x180007234  jz      short loc_18000724A
0x180007236  mov     r8d, 400h
0x18000723c  lea     rdx, [rbp+1400h+var_1440]
0x180007240  lea     rcx, [rsp+1500h+var_14E0]
0x180007245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000724a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007251  test    rax, rax
0x180007254  jz      short loc_180007260
0x180007256  lea     rcx, [rsp+1500h+var_14E0]
0x18000725b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007260  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007267  test    rax, rax
0x18000726a  jz      short loc_18000727D
0x18000726c  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180007271  jnz     short loc_18000727D
0x180007273  lea     rcx, [rsp+1500h+var_14E0]
0x180007278  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000727d  cmp     [rsp+1500h+var_14D8], r12d
0x180007282  jge     loc_18000738B
0x180007288  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18000728f  jnz     short loc_1800072B0
0x180007291  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180007298  test    rax, rax
0x18000729b  jz      short loc_1800072A6
0x18000729d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072a2  test    al, al
0x1800072a4  jmp     short loc_1800072AE
0x1800072a6  call    cs:__imp_IsDebuggerPresent
0x1800072ac  test    eax, eax
0x1800072ae  jz      short loc_1800072B7
0x1800072b0  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800072b5  jz      short loc_1800072DD
0x1800072b7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800072be  test    rax, rax
0x1800072c1  jz      short loc_180007336
0x1800072c3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800072ca  jnz     short loc_180007336
0x1800072cc  xor     r8d, r8d
0x1800072cf  xor     edx, edx
0x1800072d1  lea     rcx, [rsp+1500h+var_14E0]
0x1800072d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072db  jmp     short loc_180007336
0x1800072dd  mov     ebx, 800h
0x1800072e2  mov     rax, cs:g_pfnResultLoggingCallback
0x1800072e9  test    rax, rax
0x1800072ec  jz      short loc_18000730B
0x1800072ee  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800072f5  jnz     short loc_18000730B
0x1800072f7  mov     r8d, ebx
0x1800072fa  lea     rdx, [rbp+1400h+OutputString]
0x180007301  lea     rcx, [rsp+1500h+var_14E0]
0x180007306  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000730b  cmp     [rbp+1400h+OutputString], r12w
0x180007313  jnz     short loc_180007329
0x180007315  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18000731a  mov     rdx, rbx; unsigned __int16 *
0x18000731d  lea     rcx, [rbp+1400h+OutputString]; this
0x180007324  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180007329  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180007330  call    cs:__imp_OutputDebugStringW
0x180007336  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18000733b  jnz     short loc_180007346
0x18000733d  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180007344  jz      short loc_180007358
0x180007346  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000734d  test    rax, rax
0x180007350  jz      short loc_180007358
0x180007352  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007357  nop
0x180007358  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18000735d  jnz     short loc_180007380
0x18000735f  mov     rcx, [rbp+1400h+var_40]
0x180007366  xor     rcx, rsp; StackCookie
0x180007369  call    __security_check_cookie
0x18000736e  add     rsp, 14D0h
0x180007375  pop     r15
0x180007377  pop     r14
0x180007379  pop     r12
0x18000737b  pop     rdi
0x18000737c  pop     rsi
0x18000737d  pop     rbx
0x18000737e  pop     rbp
0x18000737f  retn
0x180007380  lea     rcx, [rsp+1500h+var_14E0]; this
0x180007385  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000738b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
