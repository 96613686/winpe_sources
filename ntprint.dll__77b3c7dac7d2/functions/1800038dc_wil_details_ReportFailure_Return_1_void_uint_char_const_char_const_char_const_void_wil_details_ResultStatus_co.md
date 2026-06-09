# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800038dc`
- end: `0x180003b67`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `651`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800035a0`

## callees

- `0x180002300`
- `0x180002f48`
- `0x1800038dc`
- `0x1800050a4`
- `0x180006a9c`
- `0x1800082e8`
- `0x1800084f4`
- `0x180038fc0`
- `0x18003a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003989`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003989`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003b07`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003b07`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003a7d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003a7d`

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
0x1800038dc  push    rbp
0x1800038de  push    rbx
0x1800038df  push    rsi
0x1800038e0  push    rdi
0x1800038e1  push    r12
0x1800038e3  push    r14
0x1800038e5  push    r15
0x1800038e7  lea     rbp, [rsp-13D0h]
0x1800038ef  mov     eax, 14D0h
0x1800038f4  call    _alloca_probe
0x1800038f9  sub     rsp, rax
0x1800038fc  mov     rax, cs:__security_cookie
0x180003903  xor     rax, rsp
0x180003906  mov     [rbp+1400h+var_40], rax
0x18000390d  mov     rdi, [rbp+1400h+arg_28]
0x180003914  mov     r14, r8
0x180003917  mov     esi, edx
0x180003919  mov     r15, rcx
0x18000391c  xor     edx, edx; Val
0x18000391e  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180003923  mov     r8d, 98h; Size
0x180003929  call    memset_0
0x18000392e  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180003935  xor     r12d, r12d
0x180003938  mov     [rbp+1400h+OutputString], r12w
0x180003940  mov     [rbp+1400h+var_1440], r12b
0x180003944  mov     ecx, [rdx]; this
0x180003946  mov     eax, [rdx+4]
0x180003949  mov     [rsp+1500h+var_14D8], ecx
0x18000394d  mov     [rsp+1500h+var_14D4], eax
0x180003951  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180003956  cmp     dword ptr [rdx+8], 1
0x18000395a  mov     ebx, eax
0x18000395c  lea     eax, [r12+8]
0x180003961  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180003969  mov     ecx, r12d
0x18000396c  cmovz   ecx, eax
0x18000396f  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180003973  lea     ecx, [rax-7]
0x180003976  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000397e  inc     ecx
0x180003980  mov     [rsp+1500h+var_14C8], r12
0x180003985  mov     [rsp+1500h+var_14D0], ecx
0x180003989  call    cs:__imp_GetCurrentThreadId
0x18000398f  xorps   xmm0, xmm0
0x180003992  mov     [rsp+1500h+var_14A8], r14
0x180003997  mov     [rsp+1500h+var_14C0], eax
0x18000399b  xorps   xmm1, xmm1
0x18000399e  xor     eax, eax
0x1800039a0  mov     [rsp+1500h+var_14A0], esi
0x1800039a4  mov     [rbp+1400h+var_1468], rax
0x1800039a8  mov     [rbp+1400h+var_1480], rax
0x1800039ac  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800039b3  mov     [rsp+1500h+var_149C], ebx
0x1800039b7  mov     [rsp+1500h+var_14B8], r12
0x1800039bc  mov     [rsp+1500h+var_14B0], r12
0x1800039c1  mov     [rbp+1400h+var_1458], rdi
0x1800039c5  mov     [rbp+1400h+var_1450], r15
0x1800039c9  mov     [rsp+1500h+var_1498], r12
0x1800039ce  movups  [rbp+1400h+var_1478], xmm0
0x1800039d2  movups  [rsp+1500h+var_1490], xmm1
0x1800039d7  test    rax, rax
0x1800039da  jz      short loc_1800039E7
0x1800039dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039e1  mov     [rbp+1400h+var_1460], rax
0x1800039e5  jmp     short loc_1800039EB
0x1800039e7  mov     [rbp+1400h+var_1460], r12
0x1800039eb  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800039f2  test    rax, rax
0x1800039f5  jz      short loc_180003A01
0x1800039f7  lea     rcx, [rsp+1500h+var_14E0]
0x1800039fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a01  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003a08  test    rax, rax
0x180003a0b  jz      short loc_180003A21
0x180003a0d  mov     r8d, 400h
0x180003a13  lea     rdx, [rbp+1400h+var_1440]
0x180003a17  lea     rcx, [rsp+1500h+var_14E0]
0x180003a1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a21  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003a28  test    rax, rax
0x180003a2b  jz      short loc_180003A37
0x180003a2d  lea     rcx, [rsp+1500h+var_14E0]
0x180003a32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a37  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003a3e  test    rax, rax
0x180003a41  jz      short loc_180003A54
0x180003a43  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003a48  jnz     short loc_180003A54
0x180003a4a  lea     rcx, [rsp+1500h+var_14E0]
0x180003a4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a54  cmp     [rsp+1500h+var_14D8], r12d
0x180003a59  jge     loc_180003B56
0x180003a5f  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180003a66  jnz     short loc_180003A87
0x180003a68  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003a6f  test    rax, rax
0x180003a72  jz      short loc_180003A7D
0x180003a74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a79  test    al, al
0x180003a7b  jmp     short loc_180003A85
0x180003a7d  call    cs:__imp_IsDebuggerPresent
0x180003a83  test    eax, eax
0x180003a85  jz      short loc_180003A8E
0x180003a87  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003a8c  jz      short loc_180003AB4
0x180003a8e  mov     rax, cs:g_pfnResultLoggingCallback
0x180003a95  test    rax, rax
0x180003a98  jz      short loc_180003B0D
0x180003a9a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003aa1  jnz     short loc_180003B0D
0x180003aa3  xor     r8d, r8d
0x180003aa6  lea     rcx, [rsp+1500h+var_14E0]
0x180003aab  xor     edx, edx
0x180003aad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ab2  jmp     short loc_180003B0D
0x180003ab4  mov     rax, cs:g_pfnResultLoggingCallback
0x180003abb  mov     ebx, 800h
0x180003ac0  test    rax, rax
0x180003ac3  jz      short loc_180003AE2
0x180003ac5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003acc  jnz     short loc_180003AE2
0x180003ace  mov     r8d, ebx
0x180003ad1  lea     rdx, [rbp+1400h+OutputString]
0x180003ad8  lea     rcx, [rsp+1500h+var_14E0]
0x180003add  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ae2  cmp     [rbp+1400h+OutputString], r12w
0x180003aea  jnz     short loc_180003B00
0x180003aec  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180003af1  mov     rdx, rbx; unsigned __int16 *
0x180003af4  lea     rcx, [rbp+1400h+OutputString]; this
0x180003afb  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003b00  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180003b07  call    cs:__imp_OutputDebugStringW
0x180003b0d  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180003b12  jnz     short loc_180003B1D
0x180003b14  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180003b1b  jz      short loc_180003B2E
0x180003b1d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003b24  test    rax, rax
0x180003b27  jz      short loc_180003B2E
0x180003b29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b2e  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180003b33  jnz     short loc_180003B5C
0x180003b35  mov     rcx, [rbp+1400h+var_40]
0x180003b3c  xor     rcx, rsp; StackCookie
0x180003b3f  call    __security_check_cookie
0x180003b44  add     rsp, 14D0h
0x180003b4b  pop     r15
0x180003b4d  pop     r14
0x180003b4f  pop     r12
0x180003b51  pop     rdi
0x180003b52  pop     rsi
0x180003b53  pop     rbx
0x180003b54  pop     rbp
0x180003b55  retn
0x180003b56  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003b5c  lea     rcx, [rsp+1500h+var_14E0]; this
0x180003b61  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
