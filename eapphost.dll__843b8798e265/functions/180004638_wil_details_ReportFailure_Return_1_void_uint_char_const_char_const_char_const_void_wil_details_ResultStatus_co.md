# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180004638`
- end: `0x1800048e1`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `681`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800042d0`

## callees

- `0x180002af0`
- `0x1800034cc`
- `0x180004638`
- `0x180007794`
- `0x180008c04`
- `0x1800099e0`
- `0x180009b10`
- `0x1800350c0`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800046e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800046e3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800047e4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800047e4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004874`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004874`

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
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v16, v14);
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
0x180004638  mov     [rsp-8+arg_10], rbx
0x18000463d  push    rbp
0x18000463e  push    rsi
0x18000463f  push    rdi
0x180004640  push    r14
0x180004642  push    r15
0x180004644  lea     rbp, [rsp-13D0h]
0x18000464c  mov     eax, 14D0h
0x180004651  call    _alloca_probe
0x180004656  sub     rsp, rax
0x180004659  mov     rax, cs:__security_cookie
0x180004660  xor     rax, rsp
0x180004663  mov     [rbp+13F0h+var_30], rax
0x18000466a  mov     esi, edx
0x18000466c  mov     r14, rcx
0x18000466f  mov     rdi, [rbp+13F0h+arg_28]
0x180004676  xor     edx, edx; Val
0x180004678  mov     r8d, 98h; Size
0x18000467e  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180004683  call    memset_0
0x180004688  nop
0x180004689  xor     r15d, r15d
0x18000468c  mov     [rbp+13F0h+OutputString], r15w
0x180004694  mov     [rbp+13F0h+var_1430], r15b
0x180004698  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18000469f  mov     ecx, [rdx]; this
0x1800046a1  mov     [rsp+14F0h+var_14C8], ecx
0x1800046a5  mov     eax, [rdx+4]
0x1800046a8  mov     [rsp+14F0h+var_14C4], eax
0x1800046ac  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800046b1  mov     ebx, eax
0x1800046b3  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x1800046bb  mov     ecx, r15d
0x1800046be  lea     eax, [r15+8]
0x1800046c2  cmp     dword ptr [rdx+8], 1
0x1800046c6  cmovz   ecx, eax
0x1800046c9  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800046cd  lea     ecx, [rax-7]
0x1800046d0  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800046d8  inc     ecx
0x1800046da  mov     [rsp+14F0h+var_14C0], ecx
0x1800046de  mov     [rsp+14F0h+var_14B8], r15
0x1800046e3  call    cs:__imp_GetCurrentThreadId
0x1800046ea  nop     dword ptr [rax+rax+00h]
0x1800046ef  mov     [rsp+14F0h+var_14B0], eax
0x1800046f3  lea     rax, aWil; "wil"
0x1800046fa  mov     [rsp+14F0h+var_1498], rax
0x1800046ff  mov     [rsp+14F0h+var_1490], esi
0x180004703  mov     [rsp+14F0h+var_148C], ebx
0x180004707  mov     [rsp+14F0h+var_14A8], r15
0x18000470c  mov     [rsp+14F0h+var_14A0], r15
0x180004711  mov     [rbp+13F0h+var_1448], rdi
0x180004715  mov     [rbp+13F0h+var_1440], r14
0x180004719  mov     [rsp+14F0h+var_1488], r15
0x18000471e  xorps   xmm0, xmm0
0x180004721  xor     eax, eax
0x180004723  movups  [rbp+13F0h+var_1468], xmm0
0x180004727  mov     [rbp+13F0h+var_1458], rax
0x18000472b  xorps   xmm1, xmm1
0x18000472e  movups  [rsp+14F0h+var_1480], xmm1
0x180004733  mov     [rbp+13F0h+var_1470], rax
0x180004737  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000473e  test    rax, rax
0x180004741  jz      short loc_18000474E
0x180004743  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004748  mov     [rbp+13F0h+var_1450], rax
0x18000474c  jmp     short loc_180004752
0x18000474e  mov     [rbp+13F0h+var_1450], r15
0x180004752  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004759  test    rax, rax
0x18000475c  jz      short loc_180004768
0x18000475e  lea     rcx, [rsp+14F0h+var_14D0]
0x180004763  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004768  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000476f  test    rax, rax
0x180004772  jz      short loc_180004788
0x180004774  mov     r8d, 400h
0x18000477a  lea     rdx, [rbp+13F0h+var_1430]
0x18000477e  lea     rcx, [rsp+14F0h+var_14D0]
0x180004783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004788  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000478f  test    rax, rax
0x180004792  jz      short loc_18000479E
0x180004794  lea     rcx, [rsp+14F0h+var_14D0]
0x180004799  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000479e  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800047a5  test    rax, rax
0x1800047a8  jz      short loc_1800047BB
0x1800047aa  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800047af  jnz     short loc_1800047BB
0x1800047b1  lea     rcx, [rsp+14F0h+var_14D0]
0x1800047b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047bb  cmp     [rsp+14F0h+var_14C8], r15d
0x1800047c0  jge     loc_1800048DB
0x1800047c6  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x1800047cd  jnz     short loc_1800047F4
0x1800047cf  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800047d6  test    rax, rax
0x1800047d9  jz      short loc_1800047E4
0x1800047db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047e0  test    al, al
0x1800047e2  jmp     short loc_1800047F2
0x1800047e4  call    cs:__imp_IsDebuggerPresent
0x1800047eb  nop     dword ptr [rax+rax+00h]
0x1800047f0  test    eax, eax
0x1800047f2  jz      short loc_1800047FB
0x1800047f4  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800047f9  jz      short loc_180004821
0x1800047fb  mov     rax, cs:g_pfnResultLoggingCallback
0x180004802  test    rax, rax
0x180004805  jz      short loc_180004880
0x180004807  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000480e  jnz     short loc_180004880
0x180004810  xor     r8d, r8d
0x180004813  xor     edx, edx
0x180004815  lea     rcx, [rsp+14F0h+var_14D0]
0x18000481a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000481f  jmp     short loc_180004880
0x180004821  mov     ebx, 800h
0x180004826  mov     rax, cs:g_pfnResultLoggingCallback
0x18000482d  test    rax, rax
0x180004830  jz      short loc_18000484F
0x180004832  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180004839  jnz     short loc_18000484F
0x18000483b  mov     r8d, ebx
0x18000483e  lea     rdx, [rbp+13F0h+OutputString]
0x180004845  lea     rcx, [rsp+14F0h+var_14D0]
0x18000484a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000484f  cmp     [rbp+13F0h+OutputString], r15w
0x180004857  jnz     short loc_18000486D
0x180004859  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000485e  mov     rdx, rbx; wchar_t *
0x180004861  lea     rcx, [rbp+13F0h+OutputString]; this
0x180004868  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18000486d  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180004874  call    cs:__imp_OutputDebugStringW
0x18000487b  nop     dword ptr [rax+rax+00h]
0x180004880  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180004885  jnz     short loc_180004890
0x180004887  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18000488e  jz      short loc_1800048A2
0x180004890  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004897  test    rax, rax
0x18000489a  jz      short loc_1800048A2
0x18000489c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048a1  nop
0x1800048a2  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x1800048a7  jnz     short loc_1800048D0
0x1800048a9  mov     rcx, [rbp+13F0h+var_30]
0x1800048b0  xor     rcx, rsp; StackCookie
0x1800048b3  call    __security_check_cookie
0x1800048b8  mov     rbx, [rsp+14F0h+arg_10]
0x1800048c0  add     rsp, 14D0h
0x1800048c7  pop     r15
0x1800048c9  pop     r14
0x1800048cb  pop     rdi
0x1800048cc  pop     rsi
0x1800048cd  pop     rbp
0x1800048ce  retn
0x1800048d0  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800048d5  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800048db  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
