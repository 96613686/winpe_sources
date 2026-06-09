# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140003640`
- end: `0x1400038d5`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `661`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140003304`

## callees

- `0x140002360`
- `0x140002d98`
- `0x140003640`
- `0x140004564`
- `0x1400055e0`
- `0x140006168`
- `0x1400062a4`
- `0x140029b70`
- `0x14002a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400036f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400036f7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400037ea`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400037ea`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140003874`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140003874`

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
  int v17; // [rsp+30h] [rbp-D0h] BYREF
  int v18; // [rsp+34h] [rbp-CCh]
  int v19; // [rsp+38h] [rbp-C8h]
  int v20; // [rsp+3Ch] [rbp-C4h]
  signed __int32 v21; // [rsp+40h] [rbp-C0h]
  __int64 v22; // [rsp+48h] [rbp-B8h]
  DWORD CurrentThreadId; // [rsp+50h] [rbp-B0h]
  __int64 v24; // [rsp+58h] [rbp-A8h]
  __int64 v25; // [rsp+60h] [rbp-A0h]
  __int64 v26; // [rsp+68h] [rbp-98h]
  int v27; // [rsp+70h] [rbp-90h]
  int v28; // [rsp+74h] [rbp-8Ch]
  __int64 v29; // [rsp+78h] [rbp-88h]
  __int128 v30; // [rsp+80h] [rbp-80h]
  __int64 v31; // [rsp+90h] [rbp-70h]
  __int128 v32; // [rsp+98h] [rbp-68h]
  __int64 v33; // [rsp+A8h] [rbp-58h]
  __int64 ModuleName; // [rsp+B0h] [rbp-50h]
  __int64 v35; // [rsp+B8h] [rbp-48h]
  __int64 v36; // [rsp+C0h] [rbp-40h]
  char v37[1024]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR OutputString[2048]; // [rsp+4D0h] [rbp+3D0h] BYREF

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
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v17, v15);
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
0x140003640  push    rbp
0x140003642  push    rbx
0x140003643  push    rsi
0x140003644  push    rdi
0x140003645  push    r12
0x140003647  push    r14
0x140003649  push    r15
0x14000364b  lea     rbp, [rsp-13E0h]
0x140003653  mov     eax, 14E0h
0x140003658  call    _alloca_probe
0x14000365d  sub     rsp, rax
0x140003660  mov     [rsp+1510h+var_14F0], 0FFFFFFFFFFFFFFFEh
0x140003669  mov     rax, cs:__security_cookie
0x140003670  xor     rax, rsp
0x140003673  mov     [rbp+1410h+var_40], rax
0x14000367a  mov     r14, r8
0x14000367d  mov     esi, edx
0x14000367f  mov     r15, rcx
0x140003682  mov     rdi, [rbp+1410h+arg_28]
0x140003689  xor     edx, edx; Val
0x14000368b  mov     r8d, 98h; Size
0x140003691  lea     rcx, [rsp+1510h+var_14E0]; void *
0x140003696  call    memset_0
0x14000369b  nop
0x14000369c  xor     r12d, r12d
0x14000369f  mov     [rbp+1410h+OutputString], r12w
0x1400036a7  mov     [rbp+1410h+var_1440], r12b
0x1400036ab  mov     rdx, qword ptr [rbp+1410h+arg_30]; int
0x1400036b2  mov     ecx, [rdx]; this
0x1400036b4  mov     [rsp+1510h+var_14D8], ecx
0x1400036b8  mov     eax, [rdx+4]
0x1400036bb  mov     [rsp+1510h+var_14D4], eax
0x1400036bf  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1400036c4  mov     ebx, eax
0x1400036c6  mov     dword ptr [rsp+1510h+var_14E0], 1
0x1400036ce  mov     ecx, r12d
0x1400036d1  lea     eax, [r12+8]
0x1400036d6  cmp     dword ptr [rdx+8], 1
0x1400036da  cmovz   ecx, eax
0x1400036dd  mov     dword ptr [rsp+1510h+var_14E0+4], ecx
0x1400036e1  lea     ecx, [rax-7]
0x1400036e4  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400036ec  inc     ecx
0x1400036ee  mov     [rsp+1510h+var_14D0], ecx
0x1400036f2  mov     [rsp+1510h+var_14C8], r12
0x1400036f7  call    cs:__imp_GetCurrentThreadId
0x1400036fd  mov     [rsp+1510h+var_14C0], eax
0x140003701  mov     [rsp+1510h+var_14A8], r14
0x140003706  mov     [rsp+1510h+var_14A0], esi
0x14000370a  mov     [rsp+1510h+var_149C], ebx
0x14000370e  mov     [rsp+1510h+var_14B8], r12
0x140003713  mov     [rsp+1510h+var_14B0], r12
0x140003718  mov     [rbp+1410h+var_1458], rdi
0x14000371c  mov     [rbp+1410h+var_1450], r15
0x140003720  mov     [rsp+1510h+var_1498], r12
0x140003725  xorps   xmm0, xmm0
0x140003728  xor     eax, eax
0x14000372a  movups  [rbp+1410h+var_1478], xmm0
0x14000372e  mov     [rbp+1410h+var_1468], rax
0x140003732  xorps   xmm1, xmm1
0x140003735  movups  [rbp+1410h+var_1490], xmm1
0x140003739  mov     [rbp+1410h+var_1480], rax
0x14000373d  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140003744  test    rax, rax
0x140003747  jz      short loc_140003754
0x140003749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000374e  mov     [rbp+1410h+var_1460], rax
0x140003752  jmp     short loc_140003758
0x140003754  mov     [rbp+1410h+var_1460], r12
0x140003758  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14000375f  test    rax, rax
0x140003762  jz      short loc_14000376E
0x140003764  lea     rcx, [rsp+1510h+var_14E0]
0x140003769  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000376e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140003775  test    rax, rax
0x140003778  jz      short loc_14000378E
0x14000377a  mov     r8d, 400h
0x140003780  lea     rdx, [rbp+1410h+var_1440]
0x140003784  lea     rcx, [rsp+1510h+var_14E0]
0x140003789  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000378e  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140003795  test    rax, rax
0x140003798  jz      short loc_1400037A4
0x14000379a  lea     rcx, [rsp+1510h+var_14E0]
0x14000379f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400037a4  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400037ab  test    rax, rax
0x1400037ae  jz      short loc_1400037C1
0x1400037b0  test    byte ptr [rsp+1510h+var_14E0+4], 2
0x1400037b5  jnz     short loc_1400037C1
0x1400037b7  lea     rcx, [rsp+1510h+var_14E0]
0x1400037bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400037c1  cmp     [rsp+1510h+var_14D8], r12d
0x1400037c6  jge     loc_1400038CF
0x1400037cc  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1400037d3  jnz     short loc_1400037F4
0x1400037d5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400037dc  test    rax, rax
0x1400037df  jz      short loc_1400037EA
0x1400037e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400037e6  test    al, al
0x1400037e8  jmp     short loc_1400037F2
0x1400037ea  call    cs:__imp_IsDebuggerPresent
0x1400037f0  test    eax, eax
0x1400037f2  jz      short loc_1400037FB
0x1400037f4  test    byte ptr [rsp+1510h+var_14E0+4], 2
0x1400037f9  jz      short loc_140003821
0x1400037fb  mov     rax, cs:g_pfnResultLoggingCallback
0x140003802  test    rax, rax
0x140003805  jz      short loc_14000387A
0x140003807  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x14000380e  jnz     short loc_14000387A
0x140003810  xor     r8d, r8d
0x140003813  xor     edx, edx
0x140003815  lea     rcx, [rsp+1510h+var_14E0]
0x14000381a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000381f  jmp     short loc_14000387A
0x140003821  mov     ebx, 800h
0x140003826  mov     rax, cs:g_pfnResultLoggingCallback
0x14000382d  test    rax, rax
0x140003830  jz      short loc_14000384F
0x140003832  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140003839  jnz     short loc_14000384F
0x14000383b  mov     r8d, ebx
0x14000383e  lea     rdx, [rbp+1410h+OutputString]
0x140003845  lea     rcx, [rsp+1510h+var_14E0]
0x14000384a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000384f  cmp     [rbp+1410h+OutputString], r12w
0x140003857  jnz     short loc_14000386D
0x140003859  lea     r8, [rsp+1510h+var_14E0]; unsigned __int64
0x14000385e  mov     rdx, rbx; wchar_t *
0x140003861  lea     rcx, [rbp+1410h+OutputString]; this
0x140003868  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x14000386d  lea     rcx, [rbp+1410h+OutputString]; lpOutputString
0x140003874  call    cs:__imp_OutputDebugStringW
0x14000387a  test    byte ptr [rsp+1510h+var_14E0+4], 4
0x14000387f  jnz     short loc_14000388A
0x140003881  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x140003888  jz      short loc_14000389C
0x14000388a  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140003891  test    rax, rax
0x140003894  jz      short loc_14000389C
0x140003896  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000389b  nop
0x14000389c  test    byte ptr [rsp+1510h+var_14E0+4], 1
0x1400038a1  jnz     short loc_1400038C4
0x1400038a3  mov     rcx, [rbp+1410h+var_40]
0x1400038aa  xor     rcx, rsp; StackCookie
0x1400038ad  call    __security_check_cookie
0x1400038b2  add     rsp, 14E0h
0x1400038b9  pop     r15
0x1400038bb  pop     r14
0x1400038bd  pop     r12
0x1400038bf  pop     rdi
0x1400038c0  pop     rsi
0x1400038c1  pop     rbx
0x1400038c2  pop     rbp
0x1400038c3  retn
0x1400038c4  lea     rcx, [rsp+1510h+var_14E0]; this
0x1400038c9  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1400038cf  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
