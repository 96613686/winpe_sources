# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x180009600`
- end: `0x18000987f`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `639`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180008fb8`

## callees

- `0x180009600`
- `0x18000ae24`
- `0x18000b708`
- `0x18000bbb0`
- `0x18000cac4`
- `0x18032f050`
- `0x180375c40`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x1800097b4`
- `KERNEL32!IsDebuggerPresent` at `0x1800097b4`
- `KERNEL32!OutputDebugStringW` at `0x180009826`
- `KERNEL32!OutputDebugStringW` at `0x180009826`
- `KERNEL32!GetCurrentThreadId` at `0x1800096aa`
- `KERNEL32!GetCurrentThreadId` at `0x1800096aa`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v12; // ecx
  bool v13; // zf
  const struct wil::FailureInfo *v14; // rdx
  const struct wil::FailureInfo *v15; // r9
  int IsDebuggerPresent; // ecx
  int v17; // [rsp+20h] [rbp-E0h]
  int v18; // [rsp+30h] [rbp-D0h] BYREF
  int v19; // [rsp+34h] [rbp-CCh]
  int v20; // [rsp+38h] [rbp-C8h]
  int v21; // [rsp+3Ch] [rbp-C4h]
  signed __int32 v22; // [rsp+40h] [rbp-C0h]
  _WORD *v23; // [rsp+48h] [rbp-B8h]
  DWORD CurrentThreadId; // [rsp+50h] [rbp-B0h]
  __int64 v25; // [rsp+58h] [rbp-A8h]
  __int64 v26; // [rsp+60h] [rbp-A0h]
  __int64 v27; // [rsp+68h] [rbp-98h]
  int v28; // [rsp+70h] [rbp-90h]
  int v29; // [rsp+74h] [rbp-8Ch]
  __int64 v30; // [rsp+78h] [rbp-88h]
  __int128 v31; // [rsp+80h] [rbp-80h]
  __int64 v32; // [rsp+90h] [rbp-70h]
  __int128 v33; // [rsp+98h] [rbp-68h]
  __int64 v34; // [rsp+A8h] [rbp-58h]
  __int64 ModuleName; // [rsp+B0h] [rbp-50h]
  __int64 v36; // [rsp+B8h] [rbp-48h]
  __int64 v37; // [rsp+C0h] [rbp-40h]
  char v38[1024]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR OutputString[2080]; // [rsp+4D0h] [rbp+3D0h] BYREF

  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v17 = wil::details::RecordFailFast((wil::details *)(unsigned int)v20, a2);
  v18 = 3;
  v12 = 0;
  if ( a7[2] == 1 )
    v12 = 8;
  v19 = v12;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v13 = *a8 == 0, v23 = a8, v13) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v17;
  v25 = a5;
  v26 = a4;
  v36 = a6;
  v37 = a1;
  v30 = 0;
  v33 = 0;
  v34 = 0;
  v31 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName();
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
  {
    v20 = -2147418113;
    v21 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v14);
  }
  if ( (wil::g_fIsDebuggerPresent
     || (!wil::g_pfnIsDebuggerPresent
       ? (IsDebuggerPresent = ::IsDebuggerPresent())
       : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent()),
         IsDebuggerPresent))
    && wil::g_fResultOutputDebugString
    && (v19 & 2) == 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048, v15);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (__int64)&v18, v15);
    OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v18, 0, 0, v15);
  }
  if ( (v19 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak();
  }
  wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x180009600  push    rbp
0x180009602  push    rbx
0x180009603  push    rsi
0x180009604  push    rdi
0x180009605  push    r12
0x180009607  push    r13
0x180009609  push    r14
0x18000960b  push    r15
0x18000960d  lea     rbp, [rsp-13D8h]
0x180009615  mov     eax, 14D8h
0x18000961a  call    _alloca_probe
0x18000961f  sub     rsp, rax
0x180009622  mov     r15, r9
0x180009625  mov     r14, r8
0x180009628  mov     esi, edx
0x18000962a  mov     rdi, rcx
0x18000962d  mov     r12, [rbp+1410h+arg_20]
0x180009634  mov     r13, [rbp+1410h+arg_28]
0x18000963b  xor     eax, eax
0x18000963d  mov     [rbp+1410h+OutputString], ax
0x180009644  mov     [rbp+1410h+var_1440], al
0x180009647  mov     rbx, [rbp+1410h+arg_30]
0x18000964e  mov     ecx, [rbx]; this
0x180009650  mov     [rsp+1510h+var_14D8], ecx
0x180009654  mov     eax, [rbx+4]
0x180009657  mov     [rsp+1510h+var_14D4], eax
0x18000965b  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180009660  mov     [rsp+1510h+var_14F0], eax
0x180009664  mov     dword ptr [rsp+1510h+var_14E0], 3
0x18000966c  xor     ecx, ecx
0x18000966e  lea     eax, [rcx+8]
0x180009671  cmp     dword ptr [rbx+8], 1
0x180009675  cmovz   ecx, eax
0x180009678  mov     dword ptr [rsp+1510h+var_14E0+4], ecx
0x18000967c  lea     ecx, [rax-7]
0x18000967f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180009687  inc     ecx
0x180009689  mov     [rsp+1510h+var_14D0], ecx
0x18000968d  mov     rcx, [rbp+1410h+arg_38]
0x180009694  xor     ebx, ebx
0x180009696  test    rcx, rcx
0x180009699  jz      short loc_1800096A5
0x18000969b  cmp     [rcx], bx
0x18000969e  mov     [rsp+1510h+var_14C8], rcx
0x1800096a3  jnz     short loc_1800096AA
0x1800096a5  mov     [rsp+1510h+var_14C8], rbx
0x1800096aa  call    cs:__imp_GetCurrentThreadId
0x1800096b0  mov     [rsp+1510h+var_14C0], eax
0x1800096b4  mov     [rsp+1510h+var_14A8], r14
0x1800096b9  mov     [rsp+1510h+var_14A0], esi
0x1800096bd  mov     eax, [rsp+1510h+var_14F0]
0x1800096c1  mov     [rsp+1510h+var_149C], eax
0x1800096c5  mov     [rsp+1510h+var_14B8], r12
0x1800096ca  mov     [rsp+1510h+var_14B0], r15
0x1800096cf  mov     [rbp+1410h+var_1458], r13
0x1800096d3  mov     [rbp+1410h+var_1450], rdi
0x1800096d7  mov     [rsp+1510h+var_1498], rbx
0x1800096dc  xorps   xmm0, xmm0
0x1800096df  xor     eax, eax
0x1800096e1  movups  [rbp+1410h+var_1478], xmm0
0x1800096e5  mov     [rbp+1410h+var_1468], rax
0x1800096e9  xorps   xmm1, xmm1
0x1800096ec  movups  [rbp+1410h+var_1490], xmm1
0x1800096f0  mov     [rbp+1410h+var_1480], rax
0x1800096f4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800096fb  test    rax, rax
0x1800096fe  jz      short loc_18000970C
0x180009700  call    cs:__guard_dispatch_icall_fptr
0x180009706  mov     [rbp+1410h+var_1460], rax
0x18000970a  jmp     short loc_180009710
0x18000970c  mov     [rbp+1410h+var_1460], rbx
0x180009710  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180009717  test    rax, rax
0x18000971a  jz      short loc_180009727
0x18000971c  lea     rcx, [rsp+1510h+var_14E0]
0x180009721  call    cs:__guard_dispatch_icall_fptr
0x180009727  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000972e  test    rax, rax
0x180009731  jz      short loc_180009748
0x180009733  mov     r8d, 400h
0x180009739  lea     rdx, [rbp+1410h+var_1440]
0x18000973d  lea     rcx, [rsp+1510h+var_14E0]
0x180009742  call    cs:__guard_dispatch_icall_fptr
0x180009748  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000974f  test    rax, rax
0x180009752  jz      short loc_18000975F
0x180009754  lea     rcx, [rsp+1510h+var_14E0]
0x180009759  call    cs:__guard_dispatch_icall_fptr
0x18000975f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180009766  test    rax, rax
0x180009769  jz      short loc_18000977D
0x18000976b  test    byte ptr [rsp+1510h+var_14E0+4], 2
0x180009770  jnz     short loc_18000977D
0x180009772  lea     rcx, [rsp+1510h+var_14E0]
0x180009777  call    cs:__guard_dispatch_icall_fptr
0x18000977d  cmp     [rsp+1510h+var_14D8], ebx
0x180009781  jl      short loc_180009795
0x180009783  mov     ecx, 8000FFFFh; this
0x180009788  mov     [rsp+1510h+var_14D8], ecx
0x18000978c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180009791  mov     [rsp+1510h+var_14D4], eax
0x180009795  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, bl; bool wil::g_fIsDebuggerPresent
0x18000979b  jnz     short loc_1800097C5
0x18000979d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800097a4  test    rax, rax
0x1800097a7  jz      short loc_1800097B4
0x1800097a9  call    cs:__guard_dispatch_icall_fptr
0x1800097af  movzx   ecx, al
0x1800097b2  jmp     short loc_1800097C1
0x1800097b4  call    cs:__imp_IsDebuggerPresent
0x1800097ba  mov     ecx, ebx
0x1800097bc  test    eax, eax
0x1800097be  setnz   cl
0x1800097c1  test    ecx, ecx
0x1800097c3  jz      short loc_18000982E
0x1800097c5  cmp     cs:?g_fResultOutputDebugString@wil@@3_NA, bl; bool wil::g_fResultOutputDebugString
0x1800097cb  jz      short loc_18000982E
0x1800097cd  test    byte ptr [rsp+1510h+var_14E0+4], 2
0x1800097d2  jnz     short loc_18000982E
0x1800097d4  mov     edi, 800h
0x1800097d9  mov     rax, cs:g_pfnResultLoggingCallback
0x1800097e0  test    rax, rax
0x1800097e3  jz      short loc_180009802
0x1800097e5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, bl; bool wil::details::g_resultMessageCallbackSet
0x1800097eb  jnz     short loc_180009802
0x1800097ed  mov     r8d, edi
0x1800097f0  lea     rdx, [rbp+1410h+OutputString]
0x1800097f7  lea     rcx, [rsp+1510h+var_14E0]
0x1800097fc  call    cs:__guard_dispatch_icall_fptr
0x180009802  cmp     [rbp+1410h+OutputString], bx
0x180009809  jnz     short loc_18000981F
0x18000980b  lea     r8, [rsp+1510h+var_14E0]; unsigned __int64
0x180009810  mov     rdx, rdi; wchar_t *
0x180009813  lea     rcx, [rbp+1410h+OutputString]; this
0x18000981a  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18000981f  lea     rcx, [rbp+1410h+OutputString]; lpOutputString
0x180009826  call    cs:__imp_OutputDebugStringW
0x18000982c  jmp     short loc_180009852
0x18000982e  mov     rax, cs:g_pfnResultLoggingCallback
0x180009835  test    rax, rax
0x180009838  jz      short loc_180009852
0x18000983a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, bl; bool wil::details::g_resultMessageCallbackSet
0x180009840  jnz     short loc_180009852
0x180009842  xor     r8d, r8d
0x180009845  xor     edx, edx
0x180009847  lea     rcx, [rsp+1510h+var_14E0]
0x18000984c  call    cs:__guard_dispatch_icall_fptr
0x180009852  test    byte ptr [rsp+1510h+var_14E0+4], 4
0x180009857  jnz     short loc_180009861
0x180009859  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, bl; bool wil::g_fBreakOnFailure
0x18000985f  jz      short loc_180009874
0x180009861  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180009868  test    rax, rax
0x18000986b  jz      short loc_180009874
0x18000986d  call    cs:__guard_dispatch_icall_fptr
0x180009873  nop
0x180009874  lea     rcx, [rsp+1510h+var_14E0]; this
0x180009879  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
