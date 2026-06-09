# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1400025a4`
- end: `0x140002838`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x14000208c`

## callees

- `0x1400017bf`
- `0x1400025a4`
- `0x1400033a4`
- `0x140004290`
- `0x140004b20`
- `0x140004bfc`
- `0x140004cd0`
- `0x140004d60`
- `0x140005010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14000264e`
- `KERNEL32!GetCurrentThreadId` at `0x14000264e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140002749`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140002749`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400027d3`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400027d3`

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
0x1400025a4  mov     [rsp-8+arg_10], rbx
0x1400025a9  push    rbp
0x1400025aa  push    rsi
0x1400025ab  push    rdi
0x1400025ac  push    r14
0x1400025ae  push    r15
0x1400025b0  lea     rbp, [rsp-13D0h]
0x1400025b8  mov     eax, 14D0h
0x1400025bd  call    _alloca_probe
0x1400025c2  sub     rsp, rax
0x1400025c5  mov     rax, cs:__security_cookie
0x1400025cc  xor     rax, rsp
0x1400025cf  mov     [rbp+13F0h+var_30], rax
0x1400025d6  mov     rdi, [rbp+13F0h+arg_28]
0x1400025dd  mov     esi, edx
0x1400025df  mov     r14, rcx
0x1400025e2  xor     edx, edx; Val
0x1400025e4  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1400025e9  mov     r8d, 98h; Size
0x1400025ef  call    memset_0
0x1400025f4  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x1400025fb  xor     r15d, r15d
0x1400025fe  mov     [rbp+13F0h+OutputString], r15w
0x140002606  mov     [rbp+13F0h+var_1430], r15b
0x14000260a  mov     ecx, [rdx]; this
0x14000260c  mov     eax, [rdx+4]
0x14000260f  mov     [rsp+14F0h+var_14C8], ecx
0x140002613  mov     [rsp+14F0h+var_14C4], eax
0x140002617  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x14000261c  cmp     dword ptr [rdx+8], 1
0x140002620  mov     ebx, eax
0x140002622  lea     eax, [r15+8]
0x140002626  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x14000262e  mov     ecx, r15d
0x140002631  cmovz   ecx, eax
0x140002634  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x140002638  lea     ecx, [rax-7]
0x14000263b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140002643  inc     ecx
0x140002645  mov     [rsp+14F0h+var_14B8], r15
0x14000264a  mov     [rsp+14F0h+var_14C0], ecx
0x14000264e  call    cs:__imp_GetCurrentThreadId
0x140002654  xorps   xmm0, xmm0
0x140002657  mov     [rsp+14F0h+var_1490], esi
0x14000265b  mov     [rsp+14F0h+var_14B0], eax
0x14000265f  xorps   xmm1, xmm1
0x140002662  lea     rax, aWil; "wil"
0x140002669  mov     [rsp+14F0h+var_148C], ebx
0x14000266d  mov     [rsp+14F0h+var_1498], rax
0x140002672  xor     eax, eax
0x140002674  mov     [rbp+13F0h+var_1458], rax
0x140002678  mov     [rbp+13F0h+var_1470], rax
0x14000267c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140002683  mov     [rsp+14F0h+var_14A8], r15
0x140002688  mov     [rsp+14F0h+var_14A0], r15
0x14000268d  mov     [rbp+13F0h+var_1448], rdi
0x140002691  mov     [rbp+13F0h+var_1440], r14
0x140002695  mov     [rsp+14F0h+var_1488], r15
0x14000269a  movups  [rbp+13F0h+var_1468], xmm0
0x14000269e  movups  [rsp+14F0h+var_1480], xmm1
0x1400026a3  test    rax, rax
0x1400026a6  jz      short loc_1400026B3
0x1400026a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400026ad  mov     [rbp+13F0h+var_1450], rax
0x1400026b1  jmp     short loc_1400026B7
0x1400026b3  mov     [rbp+13F0h+var_1450], r15
0x1400026b7  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400026be  test    rax, rax
0x1400026c1  jz      short loc_1400026CD
0x1400026c3  lea     rcx, [rsp+14F0h+var_14D0]
0x1400026c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400026cd  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400026d4  test    rax, rax
0x1400026d7  jz      short loc_1400026ED
0x1400026d9  mov     r8d, 400h
0x1400026df  lea     rdx, [rbp+13F0h+var_1430]
0x1400026e3  lea     rcx, [rsp+14F0h+var_14D0]
0x1400026e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400026ed  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400026f4  test    rax, rax
0x1400026f7  jz      short loc_140002703
0x1400026f9  lea     rcx, [rsp+14F0h+var_14D0]
0x1400026fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002703  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000270a  test    rax, rax
0x14000270d  jz      short loc_140002720
0x14000270f  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140002714  jnz     short loc_140002720
0x140002716  lea     rcx, [rsp+14F0h+var_14D0]
0x14000271b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002720  cmp     [rsp+14F0h+var_14C8], r15d
0x140002725  jge     loc_140002827
0x14000272b  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x140002732  jnz     short loc_140002753
0x140002734  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14000273b  test    rax, rax
0x14000273e  jz      short loc_140002749
0x140002740  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002745  test    al, al
0x140002747  jmp     short loc_140002751
0x140002749  call    cs:__imp_IsDebuggerPresent
0x14000274f  test    eax, eax
0x140002751  jz      short loc_14000275A
0x140002753  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140002758  jz      short loc_140002780
0x14000275a  mov     rax, cs:g_pfnResultLoggingCallback
0x140002761  test    rax, rax
0x140002764  jz      short loc_1400027D9
0x140002766  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14000276d  jnz     short loc_1400027D9
0x14000276f  xor     r8d, r8d
0x140002772  lea     rcx, [rsp+14F0h+var_14D0]
0x140002777  xor     edx, edx
0x140002779  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000277e  jmp     short loc_1400027D9
0x140002780  mov     rax, cs:g_pfnResultLoggingCallback
0x140002787  mov     ebx, 800h
0x14000278c  test    rax, rax
0x14000278f  jz      short loc_1400027AE
0x140002791  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140002798  jnz     short loc_1400027AE
0x14000279a  mov     r8d, ebx
0x14000279d  lea     rdx, [rbp+13F0h+OutputString]
0x1400027a4  lea     rcx, [rsp+14F0h+var_14D0]
0x1400027a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400027ae  cmp     [rbp+13F0h+OutputString], r15w
0x1400027b6  jnz     short loc_1400027CC
0x1400027b8  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1400027bd  mov     rdx, rbx; unsigned __int16 *
0x1400027c0  lea     rcx, [rbp+13F0h+OutputString]; this
0x1400027c7  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1400027cc  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1400027d3  call    cs:__imp_OutputDebugStringW
0x1400027d9  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1400027de  jnz     short loc_1400027E9
0x1400027e0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x1400027e7  jz      short loc_1400027FA
0x1400027e9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400027f0  test    rax, rax
0x1400027f3  jz      short loc_1400027FA
0x1400027f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400027fa  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x1400027ff  jnz     short loc_14000282D
0x140002801  mov     rcx, [rbp+13F0h+var_30]
0x140002808  xor     rcx, rsp; StackCookie
0x14000280b  call    __security_check_cookie
0x140002810  mov     rbx, [rsp+14F0h+arg_10]
0x140002818  add     rsp, 14D0h
0x14000281f  pop     r15
0x140002821  pop     r14
0x140002823  pop     rdi
0x140002824  pop     rsi
0x140002825  pop     rbp
0x140002826  retn
0x140002827  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14000282d  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140002832  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
