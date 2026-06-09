# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1801410bc`
- end: `0x18014135a`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `670`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180138dd8`

## callees

- `0x18013ce80`
- `0x18013dce6`
- `0x1801410bc`
- `0x180142a04`
- `0x18014443c`
- `0x180145b30`
- `0x180145d40`
- `0x18027dbb0`
- `0x18027f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180141169`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180141169`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1801412f3`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1801412f3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180141263`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180141263`

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
      wil::GetFailureLogString(OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v20, v18);
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
0x1801410bc  push    rbp
0x1801410be  push    rbx
0x1801410bf  push    rsi
0x1801410c0  push    rdi
0x1801410c1  push    r12
0x1801410c3  push    r14
0x1801410c5  push    r15
0x1801410c7  lea     rbp, [rsp-13D0h]
0x1801410cf  mov     eax, 14D0h
0x1801410d4  call    _alloca_probe
0x1801410d9  sub     rsp, rax
0x1801410dc  mov     rax, cs:__security_cookie
0x1801410e3  xor     rax, rsp
0x1801410e6  mov     [rbp+1400h+var_40], rax
0x1801410ed  mov     rdi, [rbp+1400h+arg_28]
0x1801410f4  mov     r14, r8
0x1801410f7  mov     esi, edx
0x1801410f9  mov     r15, rcx
0x1801410fc  xor     edx, edx; Val
0x1801410fe  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180141103  mov     r8d, 98h; Size
0x180141109  call    memset_0
0x18014110e  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180141115  xor     r12d, r12d
0x180141118  mov     [rbp+1400h+OutputString], r12w
0x180141120  mov     [rbp+1400h+var_1440], r12b
0x180141124  mov     ecx, [rdx]; this
0x180141126  mov     eax, [rdx+4]
0x180141129  mov     [rsp+1500h+var_14D8], ecx
0x18014112d  mov     [rsp+1500h+var_14D4], eax
0x180141131  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180141136  cmp     dword ptr [rdx+8], 1
0x18014113a  mov     ebx, eax
0x18014113c  lea     eax, [r12+8]
0x180141141  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180141149  mov     ecx, r12d
0x18014114c  cmovz   ecx, eax
0x18014114f  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180141153  lea     ecx, [rax-7]
0x180141156  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18014115e  inc     ecx
0x180141160  mov     [rsp+1500h+var_14C8], r12
0x180141165  mov     [rsp+1500h+var_14D0], ecx
0x180141169  call    cs:__imp_GetCurrentThreadId
0x180141170  nop     dword ptr [rax+rax+00h]
0x180141175  xorps   xmm0, xmm0
0x180141178  mov     [rsp+1500h+var_14A8], r14
0x18014117d  mov     [rsp+1500h+var_14C0], eax
0x180141181  xorps   xmm1, xmm1
0x180141184  xor     eax, eax
0x180141186  mov     [rsp+1500h+var_14A0], esi
0x18014118a  mov     [rbp+1400h+var_1468], rax
0x18014118e  mov     [rbp+1400h+var_1480], rax
0x180141192  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180141199  mov     [rsp+1500h+var_149C], ebx
0x18014119d  mov     [rsp+1500h+var_14B8], r12
0x1801411a2  mov     [rsp+1500h+var_14B0], r12
0x1801411a7  mov     [rbp+1400h+var_1458], rdi
0x1801411ab  mov     [rbp+1400h+var_1450], r15
0x1801411af  mov     [rsp+1500h+var_1498], r12
0x1801411b4  movups  [rbp+1400h+var_1478], xmm0
0x1801411b8  movups  [rsp+1500h+var_1490], xmm1
0x1801411bd  test    rax, rax
0x1801411c0  jz      short loc_1801411CD
0x1801411c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801411c7  mov     [rbp+1400h+var_1460], rax
0x1801411cb  jmp     short loc_1801411D1
0x1801411cd  mov     [rbp+1400h+var_1460], r12
0x1801411d1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1801411d8  test    rax, rax
0x1801411db  jz      short loc_1801411E7
0x1801411dd  lea     rcx, [rsp+1500h+var_14E0]
0x1801411e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801411e7  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1801411ee  test    rax, rax
0x1801411f1  jz      short loc_180141207
0x1801411f3  mov     r8d, 400h
0x1801411f9  lea     rdx, [rbp+1400h+var_1440]
0x1801411fd  lea     rcx, [rsp+1500h+var_14E0]
0x180141202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180141207  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18014120e  test    rax, rax
0x180141211  jz      short loc_18014121D
0x180141213  lea     rcx, [rsp+1500h+var_14E0]
0x180141218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014121d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180141224  test    rax, rax
0x180141227  jz      short loc_18014123A
0x180141229  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18014122e  jnz     short loc_18014123A
0x180141230  lea     rcx, [rsp+1500h+var_14E0]
0x180141235  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014123a  cmp     [rsp+1500h+var_14D8], r12d
0x18014123f  jge     loc_180141349
0x180141245  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18014124c  jnz     short loc_180141273
0x18014124e  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180141255  test    rax, rax
0x180141258  jz      short loc_180141263
0x18014125a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014125f  test    al, al
0x180141261  jmp     short loc_180141271
0x180141263  call    cs:__imp_IsDebuggerPresent
0x18014126a  nop     dword ptr [rax+rax+00h]
0x18014126f  test    eax, eax
0x180141271  jz      short loc_18014127A
0x180141273  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180141278  jz      short loc_1801412A0
0x18014127a  mov     rax, cs:g_pfnResultLoggingCallback
0x180141281  test    rax, rax
0x180141284  jz      short loc_1801412FF
0x180141286  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18014128d  jnz     short loc_1801412FF
0x18014128f  xor     r8d, r8d
0x180141292  lea     rcx, [rsp+1500h+var_14E0]
0x180141297  xor     edx, edx
0x180141299  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014129e  jmp     short loc_1801412FF
0x1801412a0  mov     rax, cs:g_pfnResultLoggingCallback
0x1801412a7  mov     ebx, 800h
0x1801412ac  test    rax, rax
0x1801412af  jz      short loc_1801412CE
0x1801412b1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1801412b8  jnz     short loc_1801412CE
0x1801412ba  mov     r8d, ebx
0x1801412bd  lea     rdx, [rbp+1400h+OutputString]
0x1801412c4  lea     rcx, [rsp+1500h+var_14E0]
0x1801412c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801412ce  cmp     [rbp+1400h+OutputString], r12w
0x1801412d6  jnz     short loc_1801412EC
0x1801412d8  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1801412dd  mov     rdx, rbx; unsigned __int16 *
0x1801412e0  lea     rcx, [rbp+1400h+OutputString]; pszDest
0x1801412e7  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1801412ec  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1801412f3  call    cs:__imp_OutputDebugStringW
0x1801412fa  nop     dword ptr [rax+rax+00h]
0x1801412ff  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180141304  jnz     short loc_18014130F
0x180141306  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18014130d  jz      short loc_180141320
0x18014130f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180141316  test    rax, rax
0x180141319  jz      short loc_180141320
0x18014131b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180141320  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180141325  jnz     short loc_18014134F
0x180141327  mov     rcx, [rbp+1400h+var_40]
0x18014132e  xor     rcx, rsp; StackCookie
0x180141331  call    __security_check_cookie
0x180141336  add     rsp, 14D0h
0x18014133d  pop     r15
0x18014133f  pop     r14
0x180141341  pop     r12
0x180141343  pop     rdi
0x180141344  pop     rsi
0x180141345  pop     rbx
0x180141346  pop     rbp
0x180141347  retn
0x180141349  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18014134f  lea     rcx, [rsp+1500h+var_14E0]; this
0x180141354  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
