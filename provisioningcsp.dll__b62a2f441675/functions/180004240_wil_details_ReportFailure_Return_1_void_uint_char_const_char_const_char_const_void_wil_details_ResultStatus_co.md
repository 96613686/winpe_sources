# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180004240`
- end: `0x1800044f9`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `697`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180003b50`

## callees

- `0x180004240`
- `0x180005534`
- `0x180006644`
- `0x18000768c`
- `0x180007824`
- `0x18003586a`
- `0x1800358a0`
- `0x180035960`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004306`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004306`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004401`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004401`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004491`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004491`

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
      g_pfnResultLoggingCallback(&v18, 0, 0, v16);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048, v16);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v18, v16);
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
0x180004240  push    rbp
0x180004242  push    rbx
0x180004243  push    rsi
0x180004244  push    rdi
0x180004245  push    r12
0x180004247  push    r14
0x180004249  push    r15
0x18000424b  lea     rbp, [rsp-13D0h]
0x180004253  mov     eax, 14D0h
0x180004258  call    _alloca_probe
0x18000425d  sub     rsp, rax
0x180004260  mov     rax, cs:__security_cookie
0x180004267  xor     rax, rsp
0x18000426a  mov     [rbp+1400h+var_40], rax
0x180004271  mov     rsi, r8
0x180004274  mov     edi, edx
0x180004276  mov     rbx, rcx
0x180004279  mov     r14, [rbp+1400h+arg_28]
0x180004280  xor     edx, edx; Val
0x180004282  mov     r8d, 98h; Size
0x180004288  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18000428d  call    memset_0
0x180004292  nop
0x180004293  xor     r12d, r12d
0x180004296  mov     [rbp+1400h+OutputString], r12w
0x18000429e  mov     [rbp+1400h+var_1440], r12b
0x1800042a2  mov     rdx, [rbp+1400h+arg_30]; int
0x1800042a9  mov     ecx, [rdx]; this
0x1800042ab  mov     [rsp+1500h+var_14D8], ecx
0x1800042af  mov     eax, [rdx+4]
0x1800042b2  mov     [rsp+1500h+var_14D4], eax
0x1800042b6  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800042bb  mov     r15d, eax
0x1800042be  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800042c6  mov     ecx, r12d
0x1800042c9  lea     eax, [r12+8]
0x1800042ce  cmp     dword ptr [rdx+8], 1
0x1800042d2  cmovz   ecx, eax
0x1800042d5  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800042d9  lea     ecx, [rax-7]
0x1800042dc  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800042e4  inc     ecx
0x1800042e6  mov     [rsp+1500h+var_14D0], ecx
0x1800042ea  mov     rcx, [rbp+1400h+arg_38]
0x1800042f1  test    rcx, rcx
0x1800042f4  jz      short loc_180004301
0x1800042f6  cmp     [rcx], r12w
0x1800042fa  mov     [rsp+1500h+var_14C8], rcx
0x1800042ff  jnz     short loc_180004306
0x180004301  mov     [rsp+1500h+var_14C8], r12
0x180004306  call    cs:__imp_GetCurrentThreadId
0x18000430d  nop     dword ptr [rax+rax+00h]
0x180004312  mov     [rsp+1500h+var_14C0], eax
0x180004316  mov     [rsp+1500h+var_14A8], rsi
0x18000431b  mov     [rsp+1500h+var_14A0], edi
0x18000431f  mov     [rsp+1500h+var_149C], r15d
0x180004324  mov     [rsp+1500h+var_14B8], r12
0x180004329  mov     [rsp+1500h+var_14B0], r12
0x18000432e  mov     [rbp+1400h+var_1458], r14
0x180004332  mov     [rbp+1400h+var_1450], rbx
0x180004336  mov     [rsp+1500h+var_1498], r12
0x18000433b  xorps   xmm0, xmm0
0x18000433e  xor     eax, eax
0x180004340  movups  [rbp+1400h+var_1478], xmm0
0x180004344  mov     [rbp+1400h+var_1468], rax
0x180004348  xorps   xmm1, xmm1
0x18000434b  movups  [rsp+1500h+var_1490], xmm1
0x180004350  mov     [rbp+1400h+var_1480], rax
0x180004354  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000435b  test    rax, rax
0x18000435e  jz      short loc_18000436B
0x180004360  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004365  mov     [rbp+1400h+var_1460], rax
0x180004369  jmp     short loc_18000436F
0x18000436b  mov     [rbp+1400h+var_1460], r12
0x18000436f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004376  test    rax, rax
0x180004379  jz      short loc_180004385
0x18000437b  lea     rcx, [rsp+1500h+var_14E0]
0x180004380  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004385  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000438c  test    rax, rax
0x18000438f  jz      short loc_1800043A5
0x180004391  mov     r8d, 400h
0x180004397  lea     rdx, [rbp+1400h+var_1440]
0x18000439b  lea     rcx, [rsp+1500h+var_14E0]
0x1800043a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043a5  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800043ac  test    rax, rax
0x1800043af  jz      short loc_1800043BB
0x1800043b1  lea     rcx, [rsp+1500h+var_14E0]
0x1800043b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043bb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800043c2  test    rax, rax
0x1800043c5  jz      short loc_1800043D8
0x1800043c7  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800043cc  jnz     short loc_1800043D8
0x1800043ce  lea     rcx, [rsp+1500h+var_14E0]
0x1800043d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043d8  cmp     [rsp+1500h+var_14D8], r12d
0x1800043dd  jge     loc_1800044F3
0x1800043e3  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800043ea  jnz     short loc_180004411
0x1800043ec  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800043f3  test    rax, rax
0x1800043f6  jz      short loc_180004401
0x1800043f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043fd  test    al, al
0x1800043ff  jmp     short loc_18000440F
0x180004401  call    cs:__imp_IsDebuggerPresent
0x180004408  nop     dword ptr [rax+rax+00h]
0x18000440d  test    eax, eax
0x18000440f  jz      short loc_180004418
0x180004411  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180004416  jz      short loc_18000443E
0x180004418  mov     rax, cs:g_pfnResultLoggingCallback
0x18000441f  test    rax, rax
0x180004422  jz      short loc_18000449D
0x180004424  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000442b  jnz     short loc_18000449D
0x18000442d  xor     r8d, r8d
0x180004430  xor     edx, edx
0x180004432  lea     rcx, [rsp+1500h+var_14E0]
0x180004437  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000443c  jmp     short loc_18000449D
0x18000443e  mov     ebx, 800h
0x180004443  mov     rax, cs:g_pfnResultLoggingCallback
0x18000444a  test    rax, rax
0x18000444d  jz      short loc_18000446C
0x18000444f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180004456  jnz     short loc_18000446C
0x180004458  mov     r8d, ebx
0x18000445b  lea     rdx, [rbp+1400h+OutputString]
0x180004462  lea     rcx, [rsp+1500h+var_14E0]
0x180004467  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000446c  cmp     [rbp+1400h+OutputString], r12w
0x180004474  jnz     short loc_18000448A
0x180004476  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18000447b  mov     rdx, rbx; unsigned __int16 *
0x18000447e  lea     rcx, [rbp+1400h+OutputString]; this
0x180004485  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000448a  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180004491  call    cs:__imp_OutputDebugStringW
0x180004498  nop     dword ptr [rax+rax+00h]
0x18000449d  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1800044a2  jnz     short loc_1800044AD
0x1800044a4  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800044ab  jz      short loc_1800044BF
0x1800044ad  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800044b4  test    rax, rax
0x1800044b7  jz      short loc_1800044BF
0x1800044b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044be  nop
0x1800044bf  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1800044c4  jnz     short loc_1800044E8
0x1800044c6  mov     rcx, [rbp+1400h+var_40]
0x1800044cd  xor     rcx, rsp; StackCookie
0x1800044d0  call    __security_check_cookie
0x1800044d5  add     rsp, 14D0h
0x1800044dc  pop     r15
0x1800044de  pop     r14
0x1800044e0  pop     r12
0x1800044e2  pop     rdi
0x1800044e3  pop     rsi
0x1800044e4  pop     rbx
0x1800044e5  pop     rbp
0x1800044e6  retn
0x1800044e8  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800044ed  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800044f3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
