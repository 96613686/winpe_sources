# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800050d4`
- end: `0x18000538d`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `697`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180004b4c`

## callees

- `0x1800026d0`
- `0x1800031a0`
- `0x1800050d4`
- `0x1800083c4`
- `0x18000a108`
- `0x18000ca1c`
- `0x18000cbf0`
- `0x18004b910`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000519a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000519a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005295`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005295`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005325`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005325`

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
0x1800050d4  push    rbp
0x1800050d6  push    rbx
0x1800050d7  push    rsi
0x1800050d8  push    rdi
0x1800050d9  push    r12
0x1800050db  push    r14
0x1800050dd  push    r15
0x1800050df  lea     rbp, [rsp-13D0h]
0x1800050e7  mov     eax, 14D0h
0x1800050ec  call    _alloca_probe
0x1800050f1  sub     rsp, rax
0x1800050f4  mov     rax, cs:__security_cookie
0x1800050fb  xor     rax, rsp
0x1800050fe  mov     [rbp+1400h+var_40], rax
0x180005105  mov     rsi, r8
0x180005108  mov     edi, edx
0x18000510a  mov     rbx, rcx
0x18000510d  mov     r14, [rbp+1400h+arg_28]
0x180005114  xor     edx, edx; Val
0x180005116  mov     r8d, 98h; Size
0x18000511c  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180005121  call    memset_0
0x180005126  nop
0x180005127  xor     r12d, r12d
0x18000512a  mov     [rbp+1400h+OutputString], r12w
0x180005132  mov     [rbp+1400h+var_1440], r12b
0x180005136  mov     rdx, [rbp+1400h+arg_30]; int
0x18000513d  mov     ecx, [rdx]; this
0x18000513f  mov     [rsp+1500h+var_14D8], ecx
0x180005143  mov     eax, [rdx+4]
0x180005146  mov     [rsp+1500h+var_14D4], eax
0x18000514a  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000514f  mov     r15d, eax
0x180005152  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18000515a  mov     ecx, r12d
0x18000515d  lea     eax, [r12+8]
0x180005162  cmp     dword ptr [rdx+8], 1
0x180005166  cmovz   ecx, eax
0x180005169  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18000516d  lea     ecx, [rax-7]
0x180005170  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005178  inc     ecx
0x18000517a  mov     [rsp+1500h+var_14D0], ecx
0x18000517e  mov     rcx, [rbp+1400h+arg_38]
0x180005185  test    rcx, rcx
0x180005188  jz      short loc_180005195
0x18000518a  cmp     [rcx], r12w
0x18000518e  mov     [rsp+1500h+var_14C8], rcx
0x180005193  jnz     short loc_18000519A
0x180005195  mov     [rsp+1500h+var_14C8], r12
0x18000519a  call    cs:__imp_GetCurrentThreadId
0x1800051a1  nop     dword ptr [rax+rax+00h]
0x1800051a6  mov     [rsp+1500h+var_14C0], eax
0x1800051aa  mov     [rsp+1500h+var_14A8], rsi
0x1800051af  mov     [rsp+1500h+var_14A0], edi
0x1800051b3  mov     [rsp+1500h+var_149C], r15d
0x1800051b8  mov     [rsp+1500h+var_14B8], r12
0x1800051bd  mov     [rsp+1500h+var_14B0], r12
0x1800051c2  mov     [rbp+1400h+var_1458], r14
0x1800051c6  mov     [rbp+1400h+var_1450], rbx
0x1800051ca  mov     [rsp+1500h+var_1498], r12
0x1800051cf  xorps   xmm0, xmm0
0x1800051d2  xor     eax, eax
0x1800051d4  movups  [rbp+1400h+var_1478], xmm0
0x1800051d8  mov     [rbp+1400h+var_1468], rax
0x1800051dc  xorps   xmm1, xmm1
0x1800051df  movups  [rsp+1500h+var_1490], xmm1
0x1800051e4  mov     [rbp+1400h+var_1480], rax
0x1800051e8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800051ef  test    rax, rax
0x1800051f2  jz      short loc_1800051FF
0x1800051f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051f9  mov     [rbp+1400h+var_1460], rax
0x1800051fd  jmp     short loc_180005203
0x1800051ff  mov     [rbp+1400h+var_1460], r12
0x180005203  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000520a  test    rax, rax
0x18000520d  jz      short loc_180005219
0x18000520f  lea     rcx, [rsp+1500h+var_14E0]
0x180005214  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005219  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005220  test    rax, rax
0x180005223  jz      short loc_180005239
0x180005225  mov     r8d, 400h
0x18000522b  lea     rdx, [rbp+1400h+var_1440]
0x18000522f  lea     rcx, [rsp+1500h+var_14E0]
0x180005234  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005239  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005240  test    rax, rax
0x180005243  jz      short loc_18000524F
0x180005245  lea     rcx, [rsp+1500h+var_14E0]
0x18000524a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000524f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005256  test    rax, rax
0x180005259  jz      short loc_18000526C
0x18000525b  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180005260  jnz     short loc_18000526C
0x180005262  lea     rcx, [rsp+1500h+var_14E0]
0x180005267  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000526c  cmp     [rsp+1500h+var_14D8], r12d
0x180005271  jge     loc_180005387
0x180005277  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18000527e  jnz     short loc_1800052A5
0x180005280  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005287  test    rax, rax
0x18000528a  jz      short loc_180005295
0x18000528c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005291  test    al, al
0x180005293  jmp     short loc_1800052A3
0x180005295  call    cs:__imp_IsDebuggerPresent
0x18000529c  nop     dword ptr [rax+rax+00h]
0x1800052a1  test    eax, eax
0x1800052a3  jz      short loc_1800052AC
0x1800052a5  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800052aa  jz      short loc_1800052D2
0x1800052ac  mov     rax, cs:g_pfnResultLoggingCallback
0x1800052b3  test    rax, rax
0x1800052b6  jz      short loc_180005331
0x1800052b8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800052bf  jnz     short loc_180005331
0x1800052c1  xor     r8d, r8d
0x1800052c4  xor     edx, edx
0x1800052c6  lea     rcx, [rsp+1500h+var_14E0]
0x1800052cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052d0  jmp     short loc_180005331
0x1800052d2  mov     ebx, 800h
0x1800052d7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800052de  test    rax, rax
0x1800052e1  jz      short loc_180005300
0x1800052e3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800052ea  jnz     short loc_180005300
0x1800052ec  mov     r8d, ebx
0x1800052ef  lea     rdx, [rbp+1400h+OutputString]
0x1800052f6  lea     rcx, [rsp+1500h+var_14E0]
0x1800052fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005300  cmp     [rbp+1400h+OutputString], r12w
0x180005308  jnz     short loc_18000531E
0x18000530a  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18000530f  mov     rdx, rbx; unsigned __int16 *
0x180005312  lea     rcx, [rbp+1400h+OutputString]; this
0x180005319  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000531e  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180005325  call    cs:__imp_OutputDebugStringW
0x18000532c  nop     dword ptr [rax+rax+00h]
0x180005331  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180005336  jnz     short loc_180005341
0x180005338  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18000533f  jz      short loc_180005353
0x180005341  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005348  test    rax, rax
0x18000534b  jz      short loc_180005353
0x18000534d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005352  nop
0x180005353  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180005358  jnz     short loc_18000537C
0x18000535a  mov     rcx, [rbp+1400h+var_40]
0x180005361  xor     rcx, rsp; StackCookie
0x180005364  call    __security_check_cookie
0x180005369  add     rsp, 14D0h
0x180005370  pop     r15
0x180005372  pop     r14
0x180005374  pop     r12
0x180005376  pop     rdi
0x180005377  pop     rsi
0x180005378  pop     rbx
0x180005379  pop     rbp
0x18000537a  retn
0x18000537c  lea     rcx, [rsp+1500h+var_14E0]; this
0x180005381  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180005387  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
