# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180002a18`
- end: `0x180002cad`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `661`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800024dc`

## callees

- `0x180001540`
- `0x180001fd6`
- `0x180002a18`
- `0x1800043c4`
- `0x180005350`
- `0x1800065b0`
- `0x180006730`
- `0x180013d80`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002acf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002acf`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002c4c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002c4c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002bc2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002bc2`

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
0x180002a18  push    rbp
0x180002a1a  push    rbx
0x180002a1b  push    rsi
0x180002a1c  push    rdi
0x180002a1d  push    r12
0x180002a1f  push    r14
0x180002a21  push    r15
0x180002a23  lea     rbp, [rsp-13E0h]
0x180002a2b  mov     eax, 14E0h
0x180002a30  call    _alloca_probe
0x180002a35  sub     rsp, rax
0x180002a38  mov     [rsp+1510h+var_14F0], 0FFFFFFFFFFFFFFFEh
0x180002a41  mov     rax, cs:__security_cookie
0x180002a48  xor     rax, rsp
0x180002a4b  mov     [rbp+1410h+var_40], rax
0x180002a52  mov     r14, r8
0x180002a55  mov     esi, edx
0x180002a57  mov     r15, rcx
0x180002a5a  mov     rdi, [rbp+1410h+arg_28]
0x180002a61  xor     edx, edx; Val
0x180002a63  mov     r8d, 98h; Size
0x180002a69  lea     rcx, [rsp+1510h+var_14E0]; void *
0x180002a6e  call    memset_0
0x180002a73  nop
0x180002a74  xor     r12d, r12d
0x180002a77  mov     [rbp+1410h+OutputString], r12w
0x180002a7f  mov     [rbp+1410h+var_1440], r12b
0x180002a83  mov     rdx, qword ptr [rbp+1410h+arg_30]; int
0x180002a8a  mov     ecx, [rdx]; this
0x180002a8c  mov     [rsp+1510h+var_14D8], ecx
0x180002a90  mov     eax, [rdx+4]
0x180002a93  mov     [rsp+1510h+var_14D4], eax
0x180002a97  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180002a9c  mov     ebx, eax
0x180002a9e  mov     dword ptr [rsp+1510h+var_14E0], 1
0x180002aa6  mov     ecx, r12d
0x180002aa9  lea     eax, [r12+8]
0x180002aae  cmp     dword ptr [rdx+8], 1
0x180002ab2  cmovz   ecx, eax
0x180002ab5  mov     dword ptr [rsp+1510h+var_14E0+4], ecx
0x180002ab9  lea     ecx, [rax-7]
0x180002abc  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002ac4  inc     ecx
0x180002ac6  mov     [rsp+1510h+var_14D0], ecx
0x180002aca  mov     [rsp+1510h+var_14C8], r12
0x180002acf  call    cs:__imp_GetCurrentThreadId
0x180002ad5  mov     [rsp+1510h+var_14C0], eax
0x180002ad9  mov     [rsp+1510h+var_14A8], r14
0x180002ade  mov     [rsp+1510h+var_14A0], esi
0x180002ae2  mov     [rsp+1510h+var_149C], ebx
0x180002ae6  mov     [rsp+1510h+var_14B8], r12
0x180002aeb  mov     [rsp+1510h+var_14B0], r12
0x180002af0  mov     [rbp+1410h+var_1458], rdi
0x180002af4  mov     [rbp+1410h+var_1450], r15
0x180002af8  mov     [rsp+1510h+var_1498], r12
0x180002afd  xorps   xmm0, xmm0
0x180002b00  xor     eax, eax
0x180002b02  movups  [rbp+1410h+var_1478], xmm0
0x180002b06  mov     [rbp+1410h+var_1468], rax
0x180002b0a  xorps   xmm1, xmm1
0x180002b0d  movups  [rbp+1410h+var_1490], xmm1
0x180002b11  mov     [rbp+1410h+var_1480], rax
0x180002b15  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002b1c  test    rax, rax
0x180002b1f  jz      short loc_180002B2C
0x180002b21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b26  mov     [rbp+1410h+var_1460], rax
0x180002b2a  jmp     short loc_180002B30
0x180002b2c  mov     [rbp+1410h+var_1460], r12
0x180002b30  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002b37  test    rax, rax
0x180002b3a  jz      short loc_180002B46
0x180002b3c  lea     rcx, [rsp+1510h+var_14E0]
0x180002b41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b46  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002b4d  test    rax, rax
0x180002b50  jz      short loc_180002B66
0x180002b52  mov     r8d, 400h
0x180002b58  lea     rdx, [rbp+1410h+var_1440]
0x180002b5c  lea     rcx, [rsp+1510h+var_14E0]
0x180002b61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b66  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002b6d  test    rax, rax
0x180002b70  jz      short loc_180002B7C
0x180002b72  lea     rcx, [rsp+1510h+var_14E0]
0x180002b77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b7c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002b83  test    rax, rax
0x180002b86  jz      short loc_180002B99
0x180002b88  test    byte ptr [rsp+1510h+var_14E0+4], 2
0x180002b8d  jnz     short loc_180002B99
0x180002b8f  lea     rcx, [rsp+1510h+var_14E0]
0x180002b94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b99  cmp     [rsp+1510h+var_14D8], r12d
0x180002b9e  jge     loc_180002CA7
0x180002ba4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180002bab  jnz     short loc_180002BCC
0x180002bad  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002bb4  test    rax, rax
0x180002bb7  jz      short loc_180002BC2
0x180002bb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bbe  test    al, al
0x180002bc0  jmp     short loc_180002BCA
0x180002bc2  call    cs:__imp_IsDebuggerPresent
0x180002bc8  test    eax, eax
0x180002bca  jz      short loc_180002BD3
0x180002bcc  test    byte ptr [rsp+1510h+var_14E0+4], 2
0x180002bd1  jz      short loc_180002BF9
0x180002bd3  mov     rax, cs:g_pfnResultLoggingCallback
0x180002bda  test    rax, rax
0x180002bdd  jz      short loc_180002C52
0x180002bdf  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180002be6  jnz     short loc_180002C52
0x180002be8  xor     r8d, r8d
0x180002beb  xor     edx, edx
0x180002bed  lea     rcx, [rsp+1510h+var_14E0]
0x180002bf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bf7  jmp     short loc_180002C52
0x180002bf9  mov     ebx, 800h
0x180002bfe  mov     rax, cs:g_pfnResultLoggingCallback
0x180002c05  test    rax, rax
0x180002c08  jz      short loc_180002C27
0x180002c0a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180002c11  jnz     short loc_180002C27
0x180002c13  mov     r8d, ebx
0x180002c16  lea     rdx, [rbp+1410h+OutputString]
0x180002c1d  lea     rcx, [rsp+1510h+var_14E0]
0x180002c22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c27  cmp     [rbp+1410h+OutputString], r12w
0x180002c2f  jnz     short loc_180002C45
0x180002c31  lea     r8, [rsp+1510h+var_14E0]; unsigned __int64
0x180002c36  mov     rdx, rbx; wchar_t *
0x180002c39  lea     rcx, [rbp+1410h+OutputString]; this
0x180002c40  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180002c45  lea     rcx, [rbp+1410h+OutputString]; lpOutputString
0x180002c4c  call    cs:__imp_OutputDebugStringW
0x180002c52  test    byte ptr [rsp+1510h+var_14E0+4], 4
0x180002c57  jnz     short loc_180002C62
0x180002c59  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180002c60  jz      short loc_180002C74
0x180002c62  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002c69  test    rax, rax
0x180002c6c  jz      short loc_180002C74
0x180002c6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c73  nop
0x180002c74  test    byte ptr [rsp+1510h+var_14E0+4], 1
0x180002c79  jnz     short loc_180002C9C
0x180002c7b  mov     rcx, [rbp+1410h+var_40]
0x180002c82  xor     rcx, rsp; StackCookie
0x180002c85  call    __security_check_cookie
0x180002c8a  add     rsp, 14E0h
0x180002c91  pop     r15
0x180002c93  pop     r14
0x180002c95  pop     r12
0x180002c97  pop     rdi
0x180002c98  pop     rsi
0x180002c99  pop     rbx
0x180002c9a  pop     rbp
0x180002c9b  retn
0x180002c9c  lea     rcx, [rsp+1510h+var_14E0]; this
0x180002ca1  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180002ca7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
