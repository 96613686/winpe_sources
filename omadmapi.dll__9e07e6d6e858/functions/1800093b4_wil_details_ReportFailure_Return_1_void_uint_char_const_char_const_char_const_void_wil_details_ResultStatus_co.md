# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800093b4`
- end: `0x18000966d`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `697`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180008cdc`

## callees

- `0x1800031b0`
- `0x180003db8`
- `0x180005304`
- `0x1800093b4`
- `0x180010a54`
- `0x180013b14`
- `0x180013ce8`
- `0x1800229a0`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000947a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000947a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009605`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009605`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180009575`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180009575`

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
0x1800093b4  push    rbp
0x1800093b6  push    rbx
0x1800093b7  push    rsi
0x1800093b8  push    rdi
0x1800093b9  push    r12
0x1800093bb  push    r14
0x1800093bd  push    r15
0x1800093bf  lea     rbp, [rsp-13D0h]
0x1800093c7  mov     eax, 14D0h
0x1800093cc  call    _alloca_probe
0x1800093d1  sub     rsp, rax
0x1800093d4  mov     rax, cs:__security_cookie
0x1800093db  xor     rax, rsp
0x1800093de  mov     [rbp+1400h+var_40], rax
0x1800093e5  mov     rsi, r8
0x1800093e8  mov     edi, edx
0x1800093ea  mov     rbx, rcx
0x1800093ed  mov     r14, [rbp+1400h+arg_28]
0x1800093f4  xor     edx, edx; Val
0x1800093f6  mov     r8d, 98h; Size
0x1800093fc  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180009401  call    memset_0
0x180009406  nop
0x180009407  xor     r12d, r12d
0x18000940a  mov     [rbp+1400h+OutputString], r12w
0x180009412  mov     [rbp+1400h+var_1440], r12b
0x180009416  mov     rdx, [rbp+1400h+arg_30]; int
0x18000941d  mov     ecx, [rdx]; this
0x18000941f  mov     [rsp+1500h+var_14D8], ecx
0x180009423  mov     eax, [rdx+4]
0x180009426  mov     [rsp+1500h+var_14D4], eax
0x18000942a  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000942f  mov     r15d, eax
0x180009432  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18000943a  mov     ecx, r12d
0x18000943d  lea     eax, [r12+8]
0x180009442  cmp     dword ptr [rdx+8], 1
0x180009446  cmovz   ecx, eax
0x180009449  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18000944d  lea     ecx, [rax-7]
0x180009450  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180009458  inc     ecx
0x18000945a  mov     [rsp+1500h+var_14D0], ecx
0x18000945e  mov     rcx, [rbp+1400h+arg_38]
0x180009465  test    rcx, rcx
0x180009468  jz      short loc_180009475
0x18000946a  cmp     [rcx], r12w
0x18000946e  mov     [rsp+1500h+var_14C8], rcx
0x180009473  jnz     short loc_18000947A
0x180009475  mov     [rsp+1500h+var_14C8], r12
0x18000947a  call    cs:__imp_GetCurrentThreadId
0x180009481  nop     dword ptr [rax+rax+00h]
0x180009486  mov     [rsp+1500h+var_14C0], eax
0x18000948a  mov     [rsp+1500h+var_14A8], rsi
0x18000948f  mov     [rsp+1500h+var_14A0], edi
0x180009493  mov     [rsp+1500h+var_149C], r15d
0x180009498  mov     [rsp+1500h+var_14B8], r12
0x18000949d  mov     [rsp+1500h+var_14B0], r12
0x1800094a2  mov     [rbp+1400h+var_1458], r14
0x1800094a6  mov     [rbp+1400h+var_1450], rbx
0x1800094aa  mov     [rsp+1500h+var_1498], r12
0x1800094af  xorps   xmm0, xmm0
0x1800094b2  xor     eax, eax
0x1800094b4  movups  [rbp+1400h+var_1478], xmm0
0x1800094b8  mov     [rbp+1400h+var_1468], rax
0x1800094bc  xorps   xmm1, xmm1
0x1800094bf  movups  [rsp+1500h+var_1490], xmm1
0x1800094c4  mov     [rbp+1400h+var_1480], rax
0x1800094c8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800094cf  test    rax, rax
0x1800094d2  jz      short loc_1800094DF
0x1800094d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094d9  mov     [rbp+1400h+var_1460], rax
0x1800094dd  jmp     short loc_1800094E3
0x1800094df  mov     [rbp+1400h+var_1460], r12
0x1800094e3  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800094ea  test    rax, rax
0x1800094ed  jz      short loc_1800094F9
0x1800094ef  lea     rcx, [rsp+1500h+var_14E0]
0x1800094f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094f9  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180009500  test    rax, rax
0x180009503  jz      short loc_180009519
0x180009505  mov     r8d, 400h
0x18000950b  lea     rdx, [rbp+1400h+var_1440]
0x18000950f  lea     rcx, [rsp+1500h+var_14E0]
0x180009514  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009519  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180009520  test    rax, rax
0x180009523  jz      short loc_18000952F
0x180009525  lea     rcx, [rsp+1500h+var_14E0]
0x18000952a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000952f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180009536  test    rax, rax
0x180009539  jz      short loc_18000954C
0x18000953b  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180009540  jnz     short loc_18000954C
0x180009542  lea     rcx, [rsp+1500h+var_14E0]
0x180009547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000954c  cmp     [rsp+1500h+var_14D8], r12d
0x180009551  jge     loc_180009667
0x180009557  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18000955e  jnz     short loc_180009585
0x180009560  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180009567  test    rax, rax
0x18000956a  jz      short loc_180009575
0x18000956c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009571  test    al, al
0x180009573  jmp     short loc_180009583
0x180009575  call    cs:__imp_IsDebuggerPresent
0x18000957c  nop     dword ptr [rax+rax+00h]
0x180009581  test    eax, eax
0x180009583  jz      short loc_18000958C
0x180009585  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000958a  jz      short loc_1800095B2
0x18000958c  mov     rax, cs:g_pfnResultLoggingCallback
0x180009593  test    rax, rax
0x180009596  jz      short loc_180009611
0x180009598  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000959f  jnz     short loc_180009611
0x1800095a1  xor     r8d, r8d
0x1800095a4  xor     edx, edx
0x1800095a6  lea     rcx, [rsp+1500h+var_14E0]
0x1800095ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095b0  jmp     short loc_180009611
0x1800095b2  mov     ebx, 800h
0x1800095b7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800095be  test    rax, rax
0x1800095c1  jz      short loc_1800095E0
0x1800095c3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800095ca  jnz     short loc_1800095E0
0x1800095cc  mov     r8d, ebx
0x1800095cf  lea     rdx, [rbp+1400h+OutputString]
0x1800095d6  lea     rcx, [rsp+1500h+var_14E0]
0x1800095db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095e0  cmp     [rbp+1400h+OutputString], r12w
0x1800095e8  jnz     short loc_1800095FE
0x1800095ea  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1800095ef  mov     rdx, rbx; unsigned __int16 *
0x1800095f2  lea     rcx, [rbp+1400h+OutputString]; this
0x1800095f9  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800095fe  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180009605  call    cs:__imp_OutputDebugStringW
0x18000960c  nop     dword ptr [rax+rax+00h]
0x180009611  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180009616  jnz     short loc_180009621
0x180009618  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18000961f  jz      short loc_180009633
0x180009621  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180009628  test    rax, rax
0x18000962b  jz      short loc_180009633
0x18000962d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009632  nop
0x180009633  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180009638  jnz     short loc_18000965C
0x18000963a  mov     rcx, [rbp+1400h+var_40]
0x180009641  xor     rcx, rsp; StackCookie
0x180009644  call    __security_check_cookie
0x180009649  add     rsp, 14D0h
0x180009650  pop     r15
0x180009652  pop     r14
0x180009654  pop     r12
0x180009656  pop     rdi
0x180009657  pop     rsi
0x180009658  pop     rbx
0x180009659  pop     rbp
0x18000965a  retn
0x18000965c  lea     rcx, [rsp+1500h+var_14E0]; this
0x180009661  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180009667  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
