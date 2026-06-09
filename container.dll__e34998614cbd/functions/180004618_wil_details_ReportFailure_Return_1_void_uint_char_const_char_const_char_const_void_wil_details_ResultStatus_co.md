# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180004618`
- end: `0x1800048d1`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `697`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180003c84`

## callees

- `0x180002ad0`
- `0x18000362c`
- `0x180004618`
- `0x1800070f4`
- `0x180008f78`
- `0x18000bb0c`
- `0x18000bd9c`
- `0x180031e00`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800046de`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800046de`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800047d9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800047d9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004869`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004869`

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
0x180004618  push    rbp
0x18000461a  push    rbx
0x18000461b  push    rsi
0x18000461c  push    rdi
0x18000461d  push    r12
0x18000461f  push    r14
0x180004621  push    r15
0x180004623  lea     rbp, [rsp-13D0h]
0x18000462b  mov     eax, 14D0h
0x180004630  call    _alloca_probe
0x180004635  sub     rsp, rax
0x180004638  mov     rax, cs:__security_cookie
0x18000463f  xor     rax, rsp
0x180004642  mov     [rbp+1400h+var_40], rax
0x180004649  mov     rsi, r8
0x18000464c  mov     edi, edx
0x18000464e  mov     rbx, rcx
0x180004651  mov     r14, [rbp+1400h+arg_28]
0x180004658  xor     edx, edx; Val
0x18000465a  mov     r8d, 98h; Size
0x180004660  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180004665  call    memset_0
0x18000466a  nop
0x18000466b  xor     r12d, r12d
0x18000466e  mov     [rbp+1400h+OutputString], r12w
0x180004676  mov     [rbp+1400h+var_1440], r12b
0x18000467a  mov     rdx, [rbp+1400h+arg_30]; int
0x180004681  mov     ecx, [rdx]; this
0x180004683  mov     [rsp+1500h+var_14D8], ecx
0x180004687  mov     eax, [rdx+4]
0x18000468a  mov     [rsp+1500h+var_14D4], eax
0x18000468e  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004693  mov     r15d, eax
0x180004696  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18000469e  mov     ecx, r12d
0x1800046a1  lea     eax, [r12+8]
0x1800046a6  cmp     dword ptr [rdx+8], 1
0x1800046aa  cmovz   ecx, eax
0x1800046ad  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800046b1  lea     ecx, [rax-7]
0x1800046b4  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800046bc  inc     ecx
0x1800046be  mov     [rsp+1500h+var_14D0], ecx
0x1800046c2  mov     rcx, [rbp+1400h+arg_38]
0x1800046c9  test    rcx, rcx
0x1800046cc  jz      short loc_1800046D9
0x1800046ce  cmp     [rcx], r12w
0x1800046d2  mov     [rsp+1500h+var_14C8], rcx
0x1800046d7  jnz     short loc_1800046DE
0x1800046d9  mov     [rsp+1500h+var_14C8], r12
0x1800046de  call    cs:__imp_GetCurrentThreadId
0x1800046e5  nop     dword ptr [rax+rax+00h]
0x1800046ea  mov     [rsp+1500h+var_14C0], eax
0x1800046ee  mov     [rsp+1500h+var_14A8], rsi
0x1800046f3  mov     [rsp+1500h+var_14A0], edi
0x1800046f7  mov     [rsp+1500h+var_149C], r15d
0x1800046fc  mov     [rsp+1500h+var_14B8], r12
0x180004701  mov     [rsp+1500h+var_14B0], r12
0x180004706  mov     [rbp+1400h+var_1458], r14
0x18000470a  mov     [rbp+1400h+var_1450], rbx
0x18000470e  mov     [rsp+1500h+var_1498], r12
0x180004713  xorps   xmm0, xmm0
0x180004716  xor     eax, eax
0x180004718  movups  [rbp+1400h+var_1478], xmm0
0x18000471c  mov     [rbp+1400h+var_1468], rax
0x180004720  xorps   xmm1, xmm1
0x180004723  movups  [rsp+1500h+var_1490], xmm1
0x180004728  mov     [rbp+1400h+var_1480], rax
0x18000472c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004733  test    rax, rax
0x180004736  jz      short loc_180004743
0x180004738  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000473d  mov     [rbp+1400h+var_1460], rax
0x180004741  jmp     short loc_180004747
0x180004743  mov     [rbp+1400h+var_1460], r12
0x180004747  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000474e  test    rax, rax
0x180004751  jz      short loc_18000475D
0x180004753  lea     rcx, [rsp+1500h+var_14E0]
0x180004758  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000475d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004764  test    rax, rax
0x180004767  jz      short loc_18000477D
0x180004769  mov     r8d, 400h
0x18000476f  lea     rdx, [rbp+1400h+var_1440]
0x180004773  lea     rcx, [rsp+1500h+var_14E0]
0x180004778  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000477d  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004784  test    rax, rax
0x180004787  jz      short loc_180004793
0x180004789  lea     rcx, [rsp+1500h+var_14E0]
0x18000478e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004793  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000479a  test    rax, rax
0x18000479d  jz      short loc_1800047B0
0x18000479f  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800047a4  jnz     short loc_1800047B0
0x1800047a6  lea     rcx, [rsp+1500h+var_14E0]
0x1800047ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047b0  cmp     [rsp+1500h+var_14D8], r12d
0x1800047b5  jge     loc_1800048CB
0x1800047bb  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800047c2  jnz     short loc_1800047E9
0x1800047c4  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800047cb  test    rax, rax
0x1800047ce  jz      short loc_1800047D9
0x1800047d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047d5  test    al, al
0x1800047d7  jmp     short loc_1800047E7
0x1800047d9  call    cs:__imp_IsDebuggerPresent
0x1800047e0  nop     dword ptr [rax+rax+00h]
0x1800047e5  test    eax, eax
0x1800047e7  jz      short loc_1800047F0
0x1800047e9  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800047ee  jz      short loc_180004816
0x1800047f0  mov     rax, cs:g_pfnResultLoggingCallback
0x1800047f7  test    rax, rax
0x1800047fa  jz      short loc_180004875
0x1800047fc  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180004803  jnz     short loc_180004875
0x180004805  xor     r8d, r8d
0x180004808  xor     edx, edx
0x18000480a  lea     rcx, [rsp+1500h+var_14E0]
0x18000480f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004814  jmp     short loc_180004875
0x180004816  mov     ebx, 800h
0x18000481b  mov     rax, cs:g_pfnResultLoggingCallback
0x180004822  test    rax, rax
0x180004825  jz      short loc_180004844
0x180004827  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000482e  jnz     short loc_180004844
0x180004830  mov     r8d, ebx
0x180004833  lea     rdx, [rbp+1400h+OutputString]
0x18000483a  lea     rcx, [rsp+1500h+var_14E0]
0x18000483f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004844  cmp     [rbp+1400h+OutputString], r12w
0x18000484c  jnz     short loc_180004862
0x18000484e  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180004853  mov     rdx, rbx; unsigned __int16 *
0x180004856  lea     rcx, [rbp+1400h+OutputString]; this
0x18000485d  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004862  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180004869  call    cs:__imp_OutputDebugStringW
0x180004870  nop     dword ptr [rax+rax+00h]
0x180004875  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18000487a  jnz     short loc_180004885
0x18000487c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180004883  jz      short loc_180004897
0x180004885  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000488c  test    rax, rax
0x18000488f  jz      short loc_180004897
0x180004891  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004896  nop
0x180004897  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18000489c  jnz     short loc_1800048C0
0x18000489e  mov     rcx, [rbp+1400h+var_40]
0x1800048a5  xor     rcx, rsp; StackCookie
0x1800048a8  call    __security_check_cookie
0x1800048ad  add     rsp, 14D0h
0x1800048b4  pop     r15
0x1800048b6  pop     r14
0x1800048b8  pop     r12
0x1800048ba  pop     rdi
0x1800048bb  pop     rsi
0x1800048bc  pop     rbx
0x1800048bd  pop     rbp
0x1800048be  retn
0x1800048c0  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800048c5  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800048cb  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
