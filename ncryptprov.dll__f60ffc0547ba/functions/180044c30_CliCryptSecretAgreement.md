# CliCryptSecretAgreement

- ea: `0x180044c30`
- end: `0x180044f3b`
- name: `CliCryptSecretAgreement`
- size: `779`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002da4`
- `0x180002f8c`
- `0x18000af80`
- `0x18000d3d0`
- `0x18000def0`
- `0x180038970`
- `0x18003948c`
- `0x180044c30`
- `0x180045c44`
- `0x180060f5c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044caa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044db0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044e0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044caa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044db0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044e0a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180044da0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180044da0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180044d83`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180044d83`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180044c94`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180044c94`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180044f00`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180044f1b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180044f00`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180044f1b`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180044dfa`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180044dfa`

## string_xrefs

- `0x180044cbe`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x180044dc4`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x180044e9a`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x180044ecd`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`

## pseudocode

```c
__int64 __fastcall CliCryptSecretAgreement(__int64 *a1, __int64 *a2, __int64 *a3, _QWORD *a4, int a5)
{
  void *v9; // rsi
  unsigned int v10; // edi
  DWORD LastError; // ebx
  HANDLE CurrentThread; // rax
  signed int v14; // eax
  __int64 v15; // r9
  __int64 v16; // rcx
  __int64 v17; // r9
  __int64 v18; // r8
  int v19; // eax
  HANDLE hObject; // [rsp+40h] [rbp-F8h] BYREF
  int v21; // [rsp+48h] [rbp-F0h]
  void *TokenHandle[2]; // [rsp+50h] [rbp-E8h] BYREF
  _QWORD pv[2]; // [rsp+60h] [rbp-D8h] BYREF
  __int64 v24; // [rsp+70h] [rbp-C8h]
  __int64 v25; // [rsp+78h] [rbp-C0h]
  __int64 v26; // [rsp+80h] [rbp-B8h]
  int v27; // [rsp+C0h] [rbp-78h]
  HANDLE *p_hObject; // [rsp+C8h] [rbp-70h]
  void *v29; // [rsp+D0h] [rbp-68h]
  void *v30; // [rsp+D8h] [rbp-60h]

  hObject = 0;
  memset_0(pv, 0, 0x98u);
  TokenHandle[0] = 0;
  v9 = (void *)SafeAllocaAllocateFromHeap(8);
  TokenHandle[1] = v9;
  if ( v9 )
  {
    hObject = CreateEventW(0, 0, 0, 0);
    if ( !hObject )
    {
      LastError = GetLastError();
      DebugTraceError(LastError, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c", 2533);
      return LastError;
    }
    if ( (unsigned __int8)IsGetMessageWPresent() && (unsigned int)IsKeyProtected(a1, a2) )
    {
      pv[0] = g_RpcBindingContext;
      pv[1] = qword_18007A5E0;
      if ( a1 )
        v24 = *a1;
      else
        v24 = 0;
      if ( a2 )
        v25 = *a2;
      else
        v25 = 0;
      if ( a3 )
        v26 = *a3;
      else
        v26 = 0;
      v30 = v9;
      v27 = a5;
      p_hObject = &hObject;
      if ( NtCurrentTeb()->IsImpersonating )
      {
        CurrentThread = GetCurrentThread();
        if ( !OpenThreadToken(CurrentThread, 0xCu, 1, TokenHandle) )
        {
          v14 = GetLastError();
          v15 = 2568;
LABEL_19:
          v10 = v14;
LABEL_20:
          DebugTraceError(
            (unsigned int)v14,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c",
            v15);
          goto LABEL_38;
        }
        v29 = TokenHandle[0];
      }
      if ( !TrySubmitThreadpoolCallback(CliThreadCryptSecretAgreementCallback, pv, 0) )
      {
        v14 = GetLastError();
        v15 = 2577;
        goto LABEL_19;
      }
      v14 = CliWaitForCallBackCompletion(hObject, pv);
      v10 = v14;
      if ( v14 < 0 )
      {
        v15 = 2584;
        goto LABEL_20;
      }
    }
    else
    {
      if ( a3 )
        v16 = *a3;
      else
        v16 = 0;
      if ( a2 )
        v17 = *a2;
      else
        LODWORD(v17) = 0;
      if ( a1 )
        v18 = *a1;
      else
        LODWORD(v18) = 0;
      v19 = c_SrvRpcCryptSecretAgreement((_DWORD)g_RpcBindingContext, qword_18007A5E0, v18, v17, v16, (__int64)v9, a5);
      v10 = v19;
      v21 = v19;
      if ( v19 < 0 )
      {
        DebugTraceError(
          (unsigned int)v19,
          "Status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c",
          2601);
        goto LABEL_38;
      }
    }
    *a4 = v9;
    v9 = 0;
    goto LABEL_38;
  }
  v10 = -2146893810;
LABEL_38:
  if ( v9 )
    MSCryptFree(v9);
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  if ( TokenHandle[0] )
    CloseHandle(TokenHandle[0]);
  return v10;
}

```

## disassembly

```asm
0x180044c30  push    rbx
0x180044c32  push    rsi
0x180044c33  push    rdi
0x180044c34  push    r12
0x180044c36  push    r14
0x180044c38  push    r15
0x180044c3a  sub     rsp, 108h
0x180044c41  mov     r12, r9
0x180044c44  mov     r15, r8
0x180044c47  mov     rdi, rdx
0x180044c4a  mov     r14, rcx
0x180044c4d  xor     ebx, ebx
0x180044c4f  mov     [rsp+138h+hObject], rbx
0x180044c54  xor     edx, edx; Val
0x180044c56  mov     r8d, 98h; Size
0x180044c5c  lea     rcx, [rsp+138h+pv]; void *
0x180044c61  call    memset_0
0x180044c66  mov     [rsp+138h+TokenHandle], rbx
0x180044c6b  lea     ecx, [rbx+8]
0x180044c6e  call    SafeAllocaAllocateFromHeap
0x180044c73  mov     rsi, rax
0x180044c76  mov     [rsp+138h+var_E0], rax
0x180044c7b  test    rax, rax
0x180044c7e  jnz     short loc_180044C8A
0x180044c80  mov     edi, 8009000Eh
0x180044c85  jmp     loc_180044EE9
0x180044c8a  xor     r9d, r9d; lpName
0x180044c8d  xor     r8d, r8d; bInitialState
0x180044c90  xor     edx, edx; bManualReset
0x180044c92  xor     ecx, ecx; lpEventAttributes
0x180044c94  call    cs:__imp_CreateEventW
0x180044c9b  nop     dword ptr [rax+rax+00h]
0x180044ca0  mov     [rsp+138h+hObject], rax
0x180044ca5  test    rax, rax
0x180044ca8  jnz     short loc_180044CDA
0x180044caa  call    cs:__imp_GetLastError
0x180044cb1  nop     dword ptr [rax+rax+00h]
0x180044cb6  mov     ebx, eax
0x180044cb8  mov     r9d, 9E5h
0x180044cbe  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180044cc5  lea     rdx, aStatus; "Status"
0x180044ccc  mov     ecx, eax
0x180044cce  call    DebugTraceError
0x180044cd3  mov     eax, ebx
0x180044cd5  jmp     loc_180044F29
0x180044cda  call    IsGetMessageWPresent
0x180044cdf  test    al, al
0x180044ce1  jz      loc_180044E3B
0x180044ce7  mov     rdx, rdi
0x180044cea  mov     rcx, r14
0x180044ced  call    IsKeyProtected
0x180044cf2  test    eax, eax
0x180044cf4  jz      loc_180044E3B
0x180044cfa  mov     rax, cs:g_RpcBindingContext
0x180044d01  mov     [rsp+138h+pv], rax
0x180044d06  mov     rax, cs:qword_18007A5E0
0x180044d0d  mov     [rsp+138h+var_D0], rax
0x180044d12  test    r14, r14
0x180044d15  jz      short loc_180044D21
0x180044d17  mov     rax, [r14]
0x180044d1a  mov     [rsp+138h+var_C8], rax
0x180044d1f  jmp     short loc_180044D26
0x180044d21  mov     [rsp+138h+var_C8], rbx
0x180044d26  test    rdi, rdi
0x180044d29  jz      short loc_180044D35
0x180044d2b  mov     rax, [rdi]
0x180044d2e  mov     [rsp+138h+var_C0], rax
0x180044d33  jmp     short loc_180044D3A
0x180044d35  mov     [rsp+138h+var_C0], rbx
0x180044d3a  test    r15, r15
0x180044d3d  jz      short loc_180044D4C
0x180044d3f  mov     rax, [r15]
0x180044d42  mov     [rsp+138h+var_B8], rax
0x180044d4a  jmp     short loc_180044D54
0x180044d4c  mov     [rsp+138h+var_B8], rbx
0x180044d54  mov     [rsp+138h+var_60], rsi
0x180044d5c  mov     eax, [rsp+138h+arg_20]
0x180044d63  mov     [rsp+138h+var_78], eax
0x180044d6a  lea     rax, [rsp+138h+hObject]
0x180044d6f  mov     [rsp+138h+var_70], rax
0x180044d77  mov     eax, gs:179Ch
0x180044d7f  test    eax, eax
0x180044d81  jz      short loc_180044DEB
0x180044d83  call    cs:__imp_GetCurrentThread
0x180044d8a  nop     dword ptr [rax+rax+00h]
0x180044d8f  mov     rcx, rax; ThreadHandle
0x180044d92  lea     r9, [rsp+138h+TokenHandle]; TokenHandle
0x180044d97  mov     edx, 0Ch; DesiredAccess
0x180044d9c  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x180044da0  call    cs:__imp_OpenThreadToken
0x180044da7  nop     dword ptr [rax+rax+00h]
0x180044dac  test    eax, eax
0x180044dae  jnz     short loc_180044DDE
0x180044db0  call    cs:__imp_GetLastError
0x180044db7  nop     dword ptr [rax+rax+00h]
0x180044dbc  mov     r9d, 0A08h
0x180044dc2  mov     edi, eax
0x180044dc4  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180044dcb  lea     rdx, aStatus; "Status"
0x180044dd2  mov     ecx, eax
0x180044dd4  call    DebugTraceError
0x180044dd9  jmp     loc_180044EE9
0x180044dde  mov     rax, [rsp+138h+TokenHandle]
0x180044de3  mov     [rsp+138h+var_68], rax
0x180044deb  xor     r8d, r8d; pcbe
0x180044dee  lea     rdx, [rsp+138h+pv]; pv
0x180044df3  lea     rcx, _CliThreadCryptSecretAgreementCallback; pfns
0x180044dfa  call    cs:__imp_TrySubmitThreadpoolCallback
0x180044e01  nop     dword ptr [rax+rax+00h]
0x180044e06  test    eax, eax
0x180044e08  jnz     short loc_180044E1E
0x180044e0a  call    cs:__imp_GetLastError
0x180044e11  nop     dword ptr [rax+rax+00h]
0x180044e16  mov     r9d, 0A11h
0x180044e1c  jmp     short loc_180044DC2
0x180044e1e  lea     rdx, [rsp+138h+pv]
0x180044e23  mov     rcx, [rsp+138h+hObject]
0x180044e28  call    _CliWaitForCallBackCompletion
0x180044e2d  mov     edi, eax
0x180044e2f  test    eax, eax
0x180044e31  jns     short loc_180044EB1
0x180044e33  mov     r9d, 0A18h
0x180044e39  jmp     short loc_180044DC4
0x180044e3b  test    r15, r15
0x180044e3e  jz      short loc_180044E45
0x180044e40  mov     rcx, [r15]
0x180044e43  jmp     short loc_180044E48
0x180044e45  mov     rcx, rbx
0x180044e48  test    rdi, rdi
0x180044e4b  jz      short loc_180044E52
0x180044e4d  mov     r9, [rdi]
0x180044e50  jmp     short loc_180044E55
0x180044e52  mov     r9, rbx
0x180044e55  test    r14, r14
0x180044e58  jz      short loc_180044E5F
0x180044e5a  mov     r8, [r14]
0x180044e5d  jmp     short loc_180044E62
0x180044e5f  mov     r8, rbx
0x180044e62  mov     eax, [rsp+138h+arg_20]
0x180044e69  mov     [rsp+138h+var_108], eax
0x180044e6d  mov     [rsp+138h+var_110], rsi
0x180044e72  mov     [rsp+138h+var_118], rcx
0x180044e77  mov     rdx, cs:qword_18007A5E0
0x180044e7e  mov     rcx, cs:g_RpcBindingContext
0x180044e85  call    c_SrvRpcCryptSecretAgreement
0x180044e8a  mov     edi, eax
0x180044e8c  mov     [rsp+138h+var_F0], eax
0x180044e90  test    eax, eax
0x180044e92  jns     short loc_180044EB1
0x180044e94  mov     r9d, 0A29h
0x180044e9a  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180044ea1  lea     rdx, aStatus; "Status"
0x180044ea8  mov     ecx, eax
0x180044eaa  call    DebugTraceError
0x180044eaf  jmp     short loc_180044EE9
0x180044eb1  mov     [r12], rsi
0x180044eb5  mov     rsi, rbx
0x180044eb8  jmp     short loc_180044EE9
0x180044eba  mov     ecx, eax
0x180044ebc  call    HResultFromRpcException
0x180044ec1  mov     edi, eax
0x180044ec3  mov     [rsp+138h+var_F0], eax
0x180044ec7  mov     r9d, 0A2Fh
0x180044ecd  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180044ed4  lea     rdx, aStatus; "Status"
0x180044edb  mov     ecx, eax
0x180044edd  call    DebugTraceError
0x180044ee2  xor     ebx, ebx
0x180044ee4  mov     rsi, [rsp+138h+var_E0]
0x180044ee9  test    rsi, rsi
0x180044eec  jz      short loc_180044EF6
0x180044eee  mov     rcx, rsi
0x180044ef1  call    MSCryptFree
0x180044ef6  mov     rcx, [rsp+138h+hObject]; hObject
0x180044efb  test    rcx, rcx
0x180044efe  jz      short loc_180044F11
0x180044f00  call    cs:__imp_CloseHandle
0x180044f07  nop     dword ptr [rax+rax+00h]
0x180044f0c  mov     [rsp+138h+hObject], rbx
0x180044f11  mov     rcx, [rsp+138h+TokenHandle]; hObject
0x180044f16  test    rcx, rcx
0x180044f19  jz      short loc_180044F27
0x180044f1b  call    cs:__imp_CloseHandle
0x180044f22  nop     dword ptr [rax+rax+00h]
0x180044f27  mov     eax, edi
0x180044f29  add     rsp, 108h
0x180044f30  pop     r15
0x180044f32  pop     r14
0x180044f34  pop     r12
0x180044f36  pop     rdi
0x180044f37  pop     rsi
0x180044f38  pop     rbx
0x180044f39  retn
0x180062c38  push    rbp
0x180062c3a  sub     rsp, 40h
0x180062c3e  mov     rbp, rdx
0x180062c41  mov     rcx, [rcx]
0x180062c44  mov     ecx, [rcx]; ExceptionCode
0x180062c46  call    cs:__imp_I_RpcExceptionFilter
0x180062c4d  nop     dword ptr [rax+rax+00h]
0x180062c52  nop
0x180062c53  add     rsp, 40h
0x180062c57  pop     rbp
0x180062c58  retn
```
