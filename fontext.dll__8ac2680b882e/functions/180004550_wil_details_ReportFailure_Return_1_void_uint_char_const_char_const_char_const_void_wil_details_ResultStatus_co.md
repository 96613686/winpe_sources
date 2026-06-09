# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180004550`
- end: `0x1800047db`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `651`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000420c`

## callees

- `0x180004550`
- `0x1800051b4`
- `0x180006220`
- `0x180006a58`
- `0x180006c14`
- `0x18003104a`
- `0x180031070`
- `0x180031100`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800045fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800045fd`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800046f1`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800046f1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000477b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000477b`

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
  int v10; // eax
  int v11; // eax
  __int64 v12; // rdx
  int v13; // ebx
  int v14; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v16; // rdx
  wil::details::in1diag3 *v17; // rcx
  const struct wil::FailureInfo *v18; // r9
  bool v19; // zf
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD v26; // [rsp+40h] [rbp-C0h]
  __int64 v27; // [rsp+48h] [rbp-B8h]
  __int64 v28; // [rsp+50h] [rbp-B0h]
  __int64 v29; // [rsp+58h] [rbp-A8h]
  int v30; // [rsp+60h] [rbp-A0h]
  int v31; // [rsp+64h] [rbp-9Ch]
  __int64 v32; // [rsp+68h] [rbp-98h]
  __int128 v33; // [rsp+70h] [rbp-90h]
  __int64 v34; // [rsp+80h] [rbp-80h]
  __int128 v35; // [rsp+88h] [rbp-78h]
  __int64 v36; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v38; // [rsp+A8h] [rbp-58h]
  __int64 v39; // [rsp+B0h] [rbp-50h]
  char v40[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v10 = a7[1];
  v22 = *a7;
  v23 = v10;
  v11 = wil::details::RecordReturn((wil::details *)(unsigned int)v22, (int)a7);
  v19 = *(_DWORD *)(v12 + 8) == 1;
  v13 = v11;
  v20 = 1;
  v14 = 0;
  if ( v19 )
    v14 = 8;
  v21 = v14;
  v25 = 0;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v26 = CurrentThreadId;
  v30 = a2;
  v36 = 0;
  v34 = 0;
  v31 = v13;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v33 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v17);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v17);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v19 = !IsDebuggerPresent())
      : (v19 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v17) == 0),
        v19)
    || (v21 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v20, v18);
    OutputDebugStringW(OutputString);
  }
  if ( ((v21 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v17);
  if ( (v21 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v20, v16);
}

```

## disassembly

```asm
0x180004550  push    rbp
0x180004552  push    rbx
0x180004553  push    rsi
0x180004554  push    rdi
0x180004555  push    r12
0x180004557  push    r14
0x180004559  push    r15
0x18000455b  lea     rbp, [rsp-13D0h]
0x180004563  mov     eax, 14D0h
0x180004568  call    _alloca_probe
0x18000456d  sub     rsp, rax
0x180004570  mov     rax, cs:__security_cookie
0x180004577  xor     rax, rsp
0x18000457a  mov     [rbp+1400h+var_40], rax
0x180004581  mov     rdi, [rbp+1400h+arg_28]
0x180004588  mov     r14, r8
0x18000458b  mov     esi, edx
0x18000458d  mov     r15, rcx
0x180004590  xor     edx, edx; Val
0x180004592  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180004597  mov     r8d, 98h; Size
0x18000459d  call    memset_0
0x1800045a2  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x1800045a9  xor     r12d, r12d
0x1800045ac  mov     [rbp+1400h+OutputString], r12w
0x1800045b4  mov     [rbp+1400h+var_1440], r12b
0x1800045b8  mov     ecx, [rdx]; this
0x1800045ba  mov     eax, [rdx+4]
0x1800045bd  mov     [rsp+1500h+var_14D8], ecx
0x1800045c1  mov     [rsp+1500h+var_14D4], eax
0x1800045c5  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800045ca  cmp     dword ptr [rdx+8], 1
0x1800045ce  mov     ebx, eax
0x1800045d0  lea     eax, [r12+8]
0x1800045d5  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800045dd  mov     ecx, r12d
0x1800045e0  cmovz   ecx, eax
0x1800045e3  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800045e7  lea     ecx, [rax-7]
0x1800045ea  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800045f2  inc     ecx
0x1800045f4  mov     [rsp+1500h+var_14C8], r12
0x1800045f9  mov     [rsp+1500h+var_14D0], ecx
0x1800045fd  call    cs:__imp_GetCurrentThreadId
0x180004603  xorps   xmm0, xmm0
0x180004606  mov     [rsp+1500h+var_14A8], r14
0x18000460b  mov     [rsp+1500h+var_14C0], eax
0x18000460f  xorps   xmm1, xmm1
0x180004612  xor     eax, eax
0x180004614  mov     [rsp+1500h+var_14A0], esi
0x180004618  mov     [rbp+1400h+var_1468], rax
0x18000461c  mov     [rbp+1400h+var_1480], rax
0x180004620  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004627  mov     [rsp+1500h+var_149C], ebx
0x18000462b  mov     [rsp+1500h+var_14B8], r12
0x180004630  mov     [rsp+1500h+var_14B0], r12
0x180004635  mov     [rbp+1400h+var_1458], rdi
0x180004639  mov     [rbp+1400h+var_1450], r15
0x18000463d  mov     [rsp+1500h+var_1498], r12
0x180004642  movups  [rbp+1400h+var_1478], xmm0
0x180004646  movups  [rsp+1500h+var_1490], xmm1
0x18000464b  test    rax, rax
0x18000464e  jz      short loc_18000465B
0x180004650  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004655  mov     [rbp+1400h+var_1460], rax
0x180004659  jmp     short loc_18000465F
0x18000465b  mov     [rbp+1400h+var_1460], r12
0x18000465f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004666  test    rax, rax
0x180004669  jz      short loc_180004675
0x18000466b  lea     rcx, [rsp+1500h+var_14E0]
0x180004670  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004675  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000467c  test    rax, rax
0x18000467f  jz      short loc_180004695
0x180004681  mov     r8d, 400h
0x180004687  lea     rdx, [rbp+1400h+var_1440]
0x18000468b  lea     rcx, [rsp+1500h+var_14E0]
0x180004690  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004695  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000469c  test    rax, rax
0x18000469f  jz      short loc_1800046AB
0x1800046a1  lea     rcx, [rsp+1500h+var_14E0]
0x1800046a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046ab  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800046b2  test    rax, rax
0x1800046b5  jz      short loc_1800046C8
0x1800046b7  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800046bc  jnz     short loc_1800046C8
0x1800046be  lea     rcx, [rsp+1500h+var_14E0]
0x1800046c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046c8  cmp     [rsp+1500h+var_14D8], r12d
0x1800046cd  jge     loc_1800047CA
0x1800046d3  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800046da  jnz     short loc_1800046FB
0x1800046dc  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800046e3  test    rax, rax
0x1800046e6  jz      short loc_1800046F1
0x1800046e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046ed  test    al, al
0x1800046ef  jmp     short loc_1800046F9
0x1800046f1  call    cs:__imp_IsDebuggerPresent
0x1800046f7  test    eax, eax
0x1800046f9  jz      short loc_180004702
0x1800046fb  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180004700  jz      short loc_180004728
0x180004702  mov     rax, cs:g_pfnResultLoggingCallback
0x180004709  test    rax, rax
0x18000470c  jz      short loc_180004781
0x18000470e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180004715  jnz     short loc_180004781
0x180004717  xor     r8d, r8d
0x18000471a  lea     rcx, [rsp+1500h+var_14E0]
0x18000471f  xor     edx, edx
0x180004721  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004726  jmp     short loc_180004781
0x180004728  mov     rax, cs:g_pfnResultLoggingCallback
0x18000472f  mov     ebx, 800h
0x180004734  test    rax, rax
0x180004737  jz      short loc_180004756
0x180004739  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180004740  jnz     short loc_180004756
0x180004742  mov     r8d, ebx
0x180004745  lea     rdx, [rbp+1400h+OutputString]
0x18000474c  lea     rcx, [rsp+1500h+var_14E0]
0x180004751  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004756  cmp     [rbp+1400h+OutputString], r12w
0x18000475e  jnz     short loc_180004774
0x180004760  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180004765  mov     rdx, rbx; unsigned __int16 *
0x180004768  lea     rcx, [rbp+1400h+OutputString]; this
0x18000476f  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004774  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18000477b  call    cs:__imp_OutputDebugStringW
0x180004781  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180004786  jnz     short loc_180004791
0x180004788  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18000478f  jz      short loc_1800047A2
0x180004791  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004798  test    rax, rax
0x18000479b  jz      short loc_1800047A2
0x18000479d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047a2  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1800047a7  jnz     short loc_1800047D0
0x1800047a9  mov     rcx, [rbp+1400h+var_40]
0x1800047b0  xor     rcx, rsp; StackCookie
0x1800047b3  call    __security_check_cookie
0x1800047b8  add     rsp, 14D0h
0x1800047bf  pop     r15
0x1800047c1  pop     r14
0x1800047c3  pop     r12
0x1800047c5  pop     rdi
0x1800047c6  pop     rsi
0x1800047c7  pop     rbx
0x1800047c8  pop     rbp
0x1800047c9  retn
0x1800047ca  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800047d0  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800047d5  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
