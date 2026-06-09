# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800025f8`
- end: `0x18000288c`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800020d8`

## callees

- `0x1800015d0`
- `0x180001ef0`
- `0x1800025f8`
- `0x1800044c4`
- `0x180005a14`
- `0x180007660`
- `0x18000782c`
- `0x18000f930`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800026a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800026a2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002827`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002827`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000279d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000279d`

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
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdx
  int v12; // ebx
  int v13; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v15; // rdx
  wil::details::in1diag3 *v16; // rcx
  const struct wil::FailureInfo *v17; // r9
  bool v18; // zf
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh]
  int v21; // [rsp+28h] [rbp-D8h]
  int v22; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v23; // [rsp+30h] [rbp-D0h]
  __int64 v24; // [rsp+38h] [rbp-C8h]
  DWORD v25; // [rsp+40h] [rbp-C0h]
  __int64 v26; // [rsp+48h] [rbp-B8h]
  __int64 v27; // [rsp+50h] [rbp-B0h]
  const char *v28; // [rsp+58h] [rbp-A8h]
  int v29; // [rsp+60h] [rbp-A0h]
  int v30; // [rsp+64h] [rbp-9Ch]
  __int64 v31; // [rsp+68h] [rbp-98h]
  __int128 v32; // [rsp+70h] [rbp-90h]
  __int64 v33; // [rsp+80h] [rbp-80h]
  __int128 v34; // [rsp+88h] [rbp-78h]
  __int64 v35; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v37; // [rsp+A8h] [rbp-58h]
  __int64 v38; // [rsp+B0h] [rbp-50h]
  char v39[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v19, 0, 0x98u);
  OutputString[0] = 0;
  v39[0] = 0;
  v9 = a7[1];
  v21 = *a7;
  v22 = v9;
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v21, (int)a7);
  v18 = *(_DWORD *)(v11 + 8) == 1;
  v12 = v10;
  v19 = 1;
  v13 = 0;
  if ( v18 )
    v13 = 8;
  v20 = v13;
  v24 = 0;
  v23 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a2;
  v25 = CurrentThreadId;
  v30 = v12;
  v28 = "wil";
  v35 = 0;
  v33 = 0;
  v26 = 0;
  v27 = 0;
  v37 = a6;
  v38 = a1;
  v31 = 0;
  v34 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v16);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v19);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v19, v39, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v19);
  if ( wil::details::g_pfnOriginateCallback && (v20 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v19);
  if ( v21 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v16);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v18 = !IsDebuggerPresent())
      : (v18 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v16) == 0),
        v18)
    || (v20 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v19, v17);
    OutputDebugStringW(OutputString);
  }
  if ( ((v20 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v16);
  if ( (v20 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v19, v15);
}

```

## disassembly

```asm
0x1800025f8  mov     [rsp-8+arg_10], rbx
0x1800025fd  push    rbp
0x1800025fe  push    rsi
0x1800025ff  push    rdi
0x180002600  push    r14
0x180002602  push    r15
0x180002604  lea     rbp, [rsp-13D0h]
0x18000260c  mov     eax, 14D0h
0x180002611  call    _alloca_probe
0x180002616  sub     rsp, rax
0x180002619  mov     rax, cs:__security_cookie
0x180002620  xor     rax, rsp
0x180002623  mov     [rbp+13F0h+var_30], rax
0x18000262a  mov     rdi, [rbp+13F0h+arg_28]
0x180002631  mov     esi, edx
0x180002633  mov     r14, rcx
0x180002636  xor     edx, edx; Val
0x180002638  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000263d  mov     r8d, 98h; Size
0x180002643  call    memset_0
0x180002648  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18000264f  xor     r15d, r15d
0x180002652  mov     [rbp+13F0h+OutputString], r15w
0x18000265a  mov     [rbp+13F0h+var_1430], r15b
0x18000265e  mov     ecx, [rdx]; this
0x180002660  mov     eax, [rdx+4]
0x180002663  mov     [rsp+14F0h+var_14C8], ecx
0x180002667  mov     [rsp+14F0h+var_14C4], eax
0x18000266b  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180002670  cmp     dword ptr [rdx+8], 1
0x180002674  mov     ebx, eax
0x180002676  lea     eax, [r15+8]
0x18000267a  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180002682  mov     ecx, r15d
0x180002685  cmovz   ecx, eax
0x180002688  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000268c  lea     ecx, [rax-7]
0x18000268f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002697  inc     ecx
0x180002699  mov     [rsp+14F0h+var_14B8], r15
0x18000269e  mov     [rsp+14F0h+var_14C0], ecx
0x1800026a2  call    cs:__imp_GetCurrentThreadId
0x1800026a8  xorps   xmm0, xmm0
0x1800026ab  mov     [rsp+14F0h+var_1490], esi
0x1800026af  mov     [rsp+14F0h+var_14B0], eax
0x1800026b3  xorps   xmm1, xmm1
0x1800026b6  lea     rax, aWil; "wil"
0x1800026bd  mov     [rsp+14F0h+var_148C], ebx
0x1800026c1  mov     [rsp+14F0h+var_1498], rax
0x1800026c6  xor     eax, eax
0x1800026c8  mov     [rbp+13F0h+var_1458], rax
0x1800026cc  mov     [rbp+13F0h+var_1470], rax
0x1800026d0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800026d7  mov     [rsp+14F0h+var_14A8], r15
0x1800026dc  mov     [rsp+14F0h+var_14A0], r15
0x1800026e1  mov     [rbp+13F0h+var_1448], rdi
0x1800026e5  mov     [rbp+13F0h+var_1440], r14
0x1800026e9  mov     [rsp+14F0h+var_1488], r15
0x1800026ee  movups  [rbp+13F0h+var_1468], xmm0
0x1800026f2  movups  [rsp+14F0h+var_1480], xmm1
0x1800026f7  test    rax, rax
0x1800026fa  jz      short loc_180002707
0x1800026fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002701  mov     [rbp+13F0h+var_1450], rax
0x180002705  jmp     short loc_18000270B
0x180002707  mov     [rbp+13F0h+var_1450], r15
0x18000270b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002712  test    rax, rax
0x180002715  jz      short loc_180002721
0x180002717  lea     rcx, [rsp+14F0h+var_14D0]
0x18000271c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002721  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002728  test    rax, rax
0x18000272b  jz      short loc_180002741
0x18000272d  mov     r8d, 400h
0x180002733  lea     rdx, [rbp+13F0h+var_1430]
0x180002737  lea     rcx, [rsp+14F0h+var_14D0]
0x18000273c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002741  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002748  test    rax, rax
0x18000274b  jz      short loc_180002757
0x18000274d  lea     rcx, [rsp+14F0h+var_14D0]
0x180002752  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002757  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000275e  test    rax, rax
0x180002761  jz      short loc_180002774
0x180002763  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002768  jnz     short loc_180002774
0x18000276a  lea     rcx, [rsp+14F0h+var_14D0]
0x18000276f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002774  cmp     [rsp+14F0h+var_14C8], r15d
0x180002779  jge     loc_18000287B
0x18000277f  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180002786  jnz     short loc_1800027A7
0x180002788  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000278f  test    rax, rax
0x180002792  jz      short loc_18000279D
0x180002794  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002799  test    al, al
0x18000279b  jmp     short loc_1800027A5
0x18000279d  call    cs:__imp_IsDebuggerPresent
0x1800027a3  test    eax, eax
0x1800027a5  jz      short loc_1800027AE
0x1800027a7  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800027ac  jz      short loc_1800027D4
0x1800027ae  mov     rax, cs:g_pfnResultLoggingCallback
0x1800027b5  test    rax, rax
0x1800027b8  jz      short loc_18000282D
0x1800027ba  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800027c1  jnz     short loc_18000282D
0x1800027c3  xor     r8d, r8d
0x1800027c6  lea     rcx, [rsp+14F0h+var_14D0]
0x1800027cb  xor     edx, edx
0x1800027cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027d2  jmp     short loc_18000282D
0x1800027d4  mov     rax, cs:g_pfnResultLoggingCallback
0x1800027db  mov     ebx, 800h
0x1800027e0  test    rax, rax
0x1800027e3  jz      short loc_180002802
0x1800027e5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800027ec  jnz     short loc_180002802
0x1800027ee  mov     r8d, ebx
0x1800027f1  lea     rdx, [rbp+13F0h+OutputString]
0x1800027f8  lea     rcx, [rsp+14F0h+var_14D0]
0x1800027fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002802  cmp     [rbp+13F0h+OutputString], r15w
0x18000280a  jnz     short loc_180002820
0x18000280c  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180002811  mov     rdx, rbx; unsigned __int16 *
0x180002814  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000281b  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002820  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180002827  call    cs:__imp_OutputDebugStringW
0x18000282d  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180002832  jnz     short loc_18000283D
0x180002834  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18000283b  jz      short loc_18000284E
0x18000283d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002844  test    rax, rax
0x180002847  jz      short loc_18000284E
0x180002849  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000284e  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180002853  jnz     short loc_180002881
0x180002855  mov     rcx, [rbp+13F0h+var_30]
0x18000285c  xor     rcx, rsp; StackCookie
0x18000285f  call    __security_check_cookie
0x180002864  mov     rbx, [rsp+14F0h+arg_10]
0x18000286c  add     rsp, 14D0h
0x180002873  pop     r15
0x180002875  pop     r14
0x180002877  pop     rdi
0x180002878  pop     rsi
0x180002879  pop     rbp
0x18000287a  retn
0x18000287b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180002881  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180002886  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
