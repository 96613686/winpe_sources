# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180003424`
- end: `0x1800036b1`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180002efc`

## callees

- `0x180001cf0`
- `0x1800026c8`
- `0x180003424`
- `0x180005744`
- `0x1800070d8`
- `0x180009f60`
- `0x18000a12c`
- `0x180011c00`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800034d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800034d2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800035c6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800035c6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003650`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003650`

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
0x180003424  push    rbp
0x180003426  push    rbx
0x180003427  push    rsi
0x180003428  push    rdi
0x180003429  push    r12
0x18000342b  push    r14
0x18000342d  push    r15
0x18000342f  lea     rbp, [rsp-13D0h]
0x180003437  mov     eax, 14D0h
0x18000343c  call    _alloca_probe
0x180003441  sub     rsp, rax
0x180003444  mov     rax, cs:__security_cookie
0x18000344b  xor     rax, rsp
0x18000344e  mov     [rbp+1400h+var_40], rax
0x180003455  mov     r14, r8
0x180003458  mov     esi, edx
0x18000345a  mov     r15, rcx
0x18000345d  mov     rdi, [rbp+1400h+arg_28]
0x180003464  xor     edx, edx; Val
0x180003466  mov     r8d, 98h; Size
0x18000346c  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180003471  call    memset_0
0x180003476  nop
0x180003477  xor     r12d, r12d
0x18000347a  mov     [rbp+1400h+OutputString], r12w
0x180003482  mov     [rbp+1400h+var_1440], r12b
0x180003486  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x18000348d  mov     ecx, [rdx]; this
0x18000348f  mov     [rsp+1500h+var_14D8], ecx
0x180003493  mov     eax, [rdx+4]
0x180003496  mov     [rsp+1500h+var_14D4], eax
0x18000349a  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000349f  mov     ebx, eax
0x1800034a1  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800034a9  mov     ecx, r12d
0x1800034ac  lea     eax, [r12+8]
0x1800034b1  cmp     dword ptr [rdx+8], 1
0x1800034b5  cmovz   ecx, eax
0x1800034b8  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800034bc  lea     ecx, [rax-7]
0x1800034bf  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800034c7  inc     ecx
0x1800034c9  mov     [rsp+1500h+var_14D0], ecx
0x1800034cd  mov     [rsp+1500h+var_14C8], r12
0x1800034d2  call    cs:__imp_GetCurrentThreadId
0x1800034d8  mov     [rsp+1500h+var_14C0], eax
0x1800034dc  mov     [rsp+1500h+var_14A8], r14
0x1800034e1  mov     [rsp+1500h+var_14A0], esi
0x1800034e5  mov     [rsp+1500h+var_149C], ebx
0x1800034e9  mov     [rsp+1500h+var_14B8], r12
0x1800034ee  mov     [rsp+1500h+var_14B0], r12
0x1800034f3  mov     [rbp+1400h+var_1458], rdi
0x1800034f7  mov     [rbp+1400h+var_1450], r15
0x1800034fb  mov     [rsp+1500h+var_1498], r12
0x180003500  xorps   xmm0, xmm0
0x180003503  xor     eax, eax
0x180003505  movups  [rbp+1400h+var_1478], xmm0
0x180003509  mov     [rbp+1400h+var_1468], rax
0x18000350d  xorps   xmm1, xmm1
0x180003510  movups  [rsp+1500h+var_1490], xmm1
0x180003515  mov     [rbp+1400h+var_1480], rax
0x180003519  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003520  test    rax, rax
0x180003523  jz      short loc_180003530
0x180003525  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000352a  mov     [rbp+1400h+var_1460], rax
0x18000352e  jmp     short loc_180003534
0x180003530  mov     [rbp+1400h+var_1460], r12
0x180003534  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000353b  test    rax, rax
0x18000353e  jz      short loc_18000354A
0x180003540  lea     rcx, [rsp+1500h+var_14E0]
0x180003545  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000354a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003551  test    rax, rax
0x180003554  jz      short loc_18000356A
0x180003556  mov     r8d, 400h
0x18000355c  lea     rdx, [rbp+1400h+var_1440]
0x180003560  lea     rcx, [rsp+1500h+var_14E0]
0x180003565  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000356a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003571  test    rax, rax
0x180003574  jz      short loc_180003580
0x180003576  lea     rcx, [rsp+1500h+var_14E0]
0x18000357b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003580  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003587  test    rax, rax
0x18000358a  jz      short loc_18000359D
0x18000358c  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003591  jnz     short loc_18000359D
0x180003593  lea     rcx, [rsp+1500h+var_14E0]
0x180003598  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000359d  cmp     [rsp+1500h+var_14D8], r12d
0x1800035a2  jge     loc_1800036AB
0x1800035a8  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800035af  jnz     short loc_1800035D0
0x1800035b1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800035b8  test    rax, rax
0x1800035bb  jz      short loc_1800035C6
0x1800035bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035c2  test    al, al
0x1800035c4  jmp     short loc_1800035CE
0x1800035c6  call    cs:__imp_IsDebuggerPresent
0x1800035cc  test    eax, eax
0x1800035ce  jz      short loc_1800035D7
0x1800035d0  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800035d5  jz      short loc_1800035FD
0x1800035d7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800035de  test    rax, rax
0x1800035e1  jz      short loc_180003656
0x1800035e3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800035ea  jnz     short loc_180003656
0x1800035ec  xor     r8d, r8d
0x1800035ef  xor     edx, edx
0x1800035f1  lea     rcx, [rsp+1500h+var_14E0]
0x1800035f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035fb  jmp     short loc_180003656
0x1800035fd  mov     ebx, 800h
0x180003602  mov     rax, cs:g_pfnResultLoggingCallback
0x180003609  test    rax, rax
0x18000360c  jz      short loc_18000362B
0x18000360e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003615  jnz     short loc_18000362B
0x180003617  mov     r8d, ebx
0x18000361a  lea     rdx, [rbp+1400h+OutputString]
0x180003621  lea     rcx, [rsp+1500h+var_14E0]
0x180003626  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000362b  cmp     [rbp+1400h+OutputString], r12w
0x180003633  jnz     short loc_180003649
0x180003635  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18000363a  mov     rdx, rbx; unsigned __int16 *
0x18000363d  lea     rcx, [rbp+1400h+OutputString]; this
0x180003644  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003649  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180003650  call    cs:__imp_OutputDebugStringW
0x180003656  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18000365b  jnz     short loc_180003666
0x18000365d  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180003664  jz      short loc_180003678
0x180003666  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000366d  test    rax, rax
0x180003670  jz      short loc_180003678
0x180003672  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003677  nop
0x180003678  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18000367d  jnz     short loc_1800036A0
0x18000367f  mov     rcx, [rbp+1400h+var_40]
0x180003686  xor     rcx, rsp; StackCookie
0x180003689  call    __security_check_cookie
0x18000368e  add     rsp, 14D0h
0x180003695  pop     r15
0x180003697  pop     r14
0x180003699  pop     r12
0x18000369b  pop     rdi
0x18000369c  pop     rsi
0x18000369d  pop     rbx
0x18000369e  pop     rbp
0x18000369f  retn
0x1800036a0  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800036a5  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800036ab  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
