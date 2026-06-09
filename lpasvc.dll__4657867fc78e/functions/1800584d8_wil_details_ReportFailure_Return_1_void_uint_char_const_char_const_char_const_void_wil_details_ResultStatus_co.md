# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800584d8`
- end: `0x18005877e`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180057f90`

## callees

- `0x18000df90`
- `0x18000ebf4`
- `0x1800584d8`
- `0x180059fb4`
- `0x18005bc50`
- `0x18005d788`
- `0x18005d994`
- `0x1800f1c70`
- `0x180101010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005859e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005859e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180058693`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180058693`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18005871d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18005871d`

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
      g_pfnResultLoggingCallback(&v18, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v18, v16);
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
0x1800584d8  push    rbp
0x1800584da  push    rbx
0x1800584db  push    rsi
0x1800584dc  push    rdi
0x1800584dd  push    r12
0x1800584df  push    r14
0x1800584e1  push    r15
0x1800584e3  lea     rbp, [rsp-13D0h]
0x1800584eb  mov     eax, 14D0h
0x1800584f0  call    _alloca_probe
0x1800584f5  sub     rsp, rax
0x1800584f8  mov     rax, cs:__security_cookie
0x1800584ff  xor     rax, rsp
0x180058502  mov     [rbp+1400h+var_40], rax
0x180058509  mov     rsi, r8
0x18005850c  mov     edi, edx
0x18005850e  mov     rbx, rcx
0x180058511  mov     r14, [rbp+1400h+arg_28]
0x180058518  xor     edx, edx; Val
0x18005851a  mov     r8d, 98h; Size
0x180058520  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180058525  call    memset_0
0x18005852a  nop
0x18005852b  xor     r12d, r12d
0x18005852e  mov     [rbp+1400h+OutputString], r12w
0x180058536  mov     [rbp+1400h+var_1440], r12b
0x18005853a  mov     rdx, [rbp+1400h+arg_30]; int
0x180058541  mov     ecx, [rdx]; this
0x180058543  mov     [rsp+1500h+var_14D8], ecx
0x180058547  mov     eax, [rdx+4]
0x18005854a  mov     [rsp+1500h+var_14D4], eax
0x18005854e  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180058553  mov     r15d, eax
0x180058556  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18005855e  mov     ecx, r12d
0x180058561  lea     eax, [r12+8]
0x180058566  cmp     dword ptr [rdx+8], 1
0x18005856a  cmovz   ecx, eax
0x18005856d  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180058571  lea     ecx, [rax-7]
0x180058574  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18005857c  inc     ecx
0x18005857e  mov     [rsp+1500h+var_14D0], ecx
0x180058582  mov     rcx, [rbp+1400h+arg_38]
0x180058589  test    rcx, rcx
0x18005858c  jz      short loc_180058599
0x18005858e  cmp     [rcx], r12w
0x180058592  mov     [rsp+1500h+var_14C8], rcx
0x180058597  jnz     short loc_18005859E
0x180058599  mov     [rsp+1500h+var_14C8], r12
0x18005859e  call    cs:__imp_GetCurrentThreadId
0x1800585a4  mov     [rsp+1500h+var_14C0], eax
0x1800585a8  mov     [rsp+1500h+var_14A8], rsi
0x1800585ad  mov     [rsp+1500h+var_14A0], edi
0x1800585b1  mov     [rsp+1500h+var_149C], r15d
0x1800585b6  mov     [rsp+1500h+var_14B8], r12
0x1800585bb  mov     [rsp+1500h+var_14B0], r12
0x1800585c0  mov     [rbp+1400h+var_1458], r14
0x1800585c4  mov     [rbp+1400h+var_1450], rbx
0x1800585c8  mov     [rsp+1500h+var_1498], r12
0x1800585cd  xorps   xmm0, xmm0
0x1800585d0  xor     eax, eax
0x1800585d2  movups  [rbp+1400h+var_1478], xmm0
0x1800585d6  mov     [rbp+1400h+var_1468], rax
0x1800585da  xorps   xmm1, xmm1
0x1800585dd  movups  [rsp+1500h+var_1490], xmm1
0x1800585e2  mov     [rbp+1400h+var_1480], rax
0x1800585e6  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800585ed  test    rax, rax
0x1800585f0  jz      short loc_1800585FD
0x1800585f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800585f7  mov     [rbp+1400h+var_1460], rax
0x1800585fb  jmp     short loc_180058601
0x1800585fd  mov     [rbp+1400h+var_1460], r12
0x180058601  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180058608  test    rax, rax
0x18005860b  jz      short loc_180058617
0x18005860d  lea     rcx, [rsp+1500h+var_14E0]
0x180058612  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058617  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18005861e  test    rax, rax
0x180058621  jz      short loc_180058637
0x180058623  mov     r8d, 400h
0x180058629  lea     rdx, [rbp+1400h+var_1440]
0x18005862d  lea     rcx, [rsp+1500h+var_14E0]
0x180058632  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058637  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18005863e  test    rax, rax
0x180058641  jz      short loc_18005864D
0x180058643  lea     rcx, [rsp+1500h+var_14E0]
0x180058648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005864d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180058654  test    rax, rax
0x180058657  jz      short loc_18005866A
0x180058659  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18005865e  jnz     short loc_18005866A
0x180058660  lea     rcx, [rsp+1500h+var_14E0]
0x180058665  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005866a  cmp     [rsp+1500h+var_14D8], r12d
0x18005866f  jge     loc_180058778
0x180058675  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18005867c  jnz     short loc_18005869D
0x18005867e  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180058685  test    rax, rax
0x180058688  jz      short loc_180058693
0x18005868a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005868f  test    al, al
0x180058691  jmp     short loc_18005869B
0x180058693  call    cs:__imp_IsDebuggerPresent
0x180058699  test    eax, eax
0x18005869b  jz      short loc_1800586A4
0x18005869d  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800586a2  jz      short loc_1800586CA
0x1800586a4  mov     rax, cs:g_pfnResultLoggingCallback
0x1800586ab  test    rax, rax
0x1800586ae  jz      short loc_180058723
0x1800586b0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800586b7  jnz     short loc_180058723
0x1800586b9  xor     r8d, r8d
0x1800586bc  xor     edx, edx
0x1800586be  lea     rcx, [rsp+1500h+var_14E0]
0x1800586c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800586c8  jmp     short loc_180058723
0x1800586ca  mov     ebx, 800h
0x1800586cf  mov     rax, cs:g_pfnResultLoggingCallback
0x1800586d6  test    rax, rax
0x1800586d9  jz      short loc_1800586F8
0x1800586db  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800586e2  jnz     short loc_1800586F8
0x1800586e4  mov     r8d, ebx
0x1800586e7  lea     rdx, [rbp+1400h+OutputString]
0x1800586ee  lea     rcx, [rsp+1500h+var_14E0]
0x1800586f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800586f8  cmp     [rbp+1400h+OutputString], r12w
0x180058700  jnz     short loc_180058716
0x180058702  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180058707  mov     rdx, rbx; unsigned __int16 *
0x18005870a  lea     rcx, [rbp+1400h+OutputString]; this
0x180058711  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180058716  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18005871d  call    cs:__imp_OutputDebugStringW
0x180058723  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180058728  jnz     short loc_180058733
0x18005872a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180058731  jz      short loc_180058745
0x180058733  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18005873a  test    rax, rax
0x18005873d  jz      short loc_180058745
0x18005873f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058744  nop
0x180058745  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18005874a  jnz     short loc_18005876D
0x18005874c  mov     rcx, [rbp+1400h+var_40]
0x180058753  xor     rcx, rsp; StackCookie
0x180058756  call    __security_check_cookie
0x18005875b  add     rsp, 14D0h
0x180058762  pop     r15
0x180058764  pop     r14
0x180058766  pop     r12
0x180058768  pop     rdi
0x180058769  pop     rsi
0x18005876a  pop     rbx
0x18005876b  pop     rbp
0x18005876c  retn
0x18005876d  lea     rcx, [rsp+1500h+var_14E0]; this
0x180058772  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180058778  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
