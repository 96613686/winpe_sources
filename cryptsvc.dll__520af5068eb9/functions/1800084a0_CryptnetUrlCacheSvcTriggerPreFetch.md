# CryptnetUrlCacheSvcTriggerPreFetch

- ea: `0x1800084a0`
- end: `0x1800086f2`
- name: `CryptnetUrlCacheSvcTriggerPreFetch`
- size: `594`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800083d0`

## callees

- `0x1800068f0`
- `0x1800084a0`
- `0x1800088f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000862e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000862e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008628`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008673`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008688`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800086a0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800086ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800086bd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800086ce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800086e7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008628`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008673`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008688`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800086a0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800086ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800086bd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800086ce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800086e7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000857e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000857e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000856a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000856a`
- `RPCRT4!RpcImpersonateClient` at `0x180008557`
- `RPCRT4!RpcImpersonateClient` at `0x180008557`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800085d1`
- `RPCRT4!RpcRevertToSelfEx` at `0x18000867e`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800085d1`
- `RPCRT4!RpcRevertToSelfEx` at `0x18000867e`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000853d`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000853d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180008659`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180008659`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008504`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008520`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008504`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008520`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800085b3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800085b3`

## pseudocode

```c
__int64 __fastcall CryptnetUrlCacheSvcTriggerPreFetch(RPC_BINDING_HANDLE BindingHandle)
{
  char *v2; // rdi
  int v3; // ebp
  void **v4; // rax
  void **v5; // rsi
  RPC_STATUS v6; // eax
  HANDLE CurrentThread; // rax
  DWORD LastError; // esi
  HANDLE v10; // rax
  DWORD ReturnLength; // [rsp+58h] [rbp+10h] BYREF

  ReturnLength = 0;
  if ( fUrlCacheSvcStarted )
  {
    v2 = 0;
    v3 = 0;
    _InterlockedIncrement(&lUrlCacheSvcActiveRefCnt);
    if ( BindingHandle )
    {
      if ( !fUrlCacheSvcStarted )
      {
        SetLastError(0x426u);
        goto LABEL_17;
      }
      v2 = (char *)LocalAlloc(0x40u, 0x38u);
      if ( !v2 )
      {
        SetLastError(0x8007000E);
        goto LABEL_17;
      }
      v4 = (void **)LocalAlloc(0x40u, 0x10u);
      v5 = v4;
      if ( !v4 )
      {
        SetLastError(0x8007000E);
        *((_QWORD *)v2 + 4) = 0;
        goto LABEL_17;
      }
      *((_QWORD *)v2 + 4) = v4;
      v6 = I_RpcBindingInqLocalClientPID(BindingHandle, (unsigned int *)v2 + 11);
      if ( v6 )
        goto LABEL_32;
      if ( *((_DWORD *)v2 + 11) )
      {
        v6 = RpcImpersonateClient(BindingHandle);
        if ( !v6 )
        {
          v3 = 1;
          CurrentThread = GetCurrentThread();
          if ( !OpenThreadToken(CurrentThread, 0xCu, 1, v5) )
          {
            *v5 = 0;
            goto LABEL_17;
          }
          *((_DWORD *)v5 + 2) = 1;
          ReturnLength = 4;
          if ( !GetTokenInformation(*v5, TokenSessionId, v2 + 40, 4u, &ReturnLength) )
            goto LABEL_17;
          if ( ReturnLength != 4 )
            goto LABEL_17;
          if ( !*((_DWORD *)v2 + 10) )
          {
            v10 = OpenProcess(0x100000u, 0, *((_DWORD *)v2 + 11));
            *((_QWORD *)v2 + 6) = v10;
            if ( !v10 )
              goto LABEL_17;
          }
          v6 = RpcRevertToSelfEx(BindingHandle);
          v3 = 0;
          if ( !v6 )
          {
            LastError = 0;
            if ( (unsigned int)AddToBeRunJobEx(v2, 1, 0) )
            {
LABEL_15:
              _InterlockedDecrement(&lUrlCacheSvcActiveRefCnt);
              return LastError;
            }
LABEL_17:
            LastError = GetLastError();
            if ( !LastError )
              LastError = -2147418113;
            if ( v3 )
              RpcRevertToSelfEx(BindingHandle);
            FreeTriggerJob(v2);
            goto LABEL_15;
          }
        }
LABEL_32:
        SetLastError(v6);
        goto LABEL_17;
      }
    }
    SetLastError(0x57u);
    goto LABEL_17;
  }
  return 1062;
}

```

## disassembly

```asm
0x1800084a0  push    rbx
0x1800084a2  sub     rsp, 40h
0x1800084a6  mov     eax, cs:?fUrlCacheSvcStarted@@3HC; int volatile fUrlCacheSvcStarted
0x1800084ac  mov     rbx, rcx
0x1800084af  mov     [rsp+48h+arg_8], 0
0x1800084b7  test    eax, eax
0x1800084b9  jz      loc_180008690
0x1800084bf  mov     [rsp+48h+arg_0], rbp
0x1800084c4  mov     [rsp+48h+arg_10], rsi
0x1800084c9  mov     [rsp+48h+arg_18], rdi
0x1800084ce  xor     edi, edi
0x1800084d0  mov     [rsp+48h+var_10], r14
0x1800084d5  xor     ebp, ebp
0x1800084d7  mov     [rsp+48h+var_18], r15
0x1800084dc  lock inc cs:?lUrlCacheSvcActiveRefCnt@@3JC; long volatile lUrlCacheSvcActiveRefCnt
0x1800084e3  test    rcx, rcx
0x1800084e6  jz      loc_180008623
0x1800084ec  mov     eax, cs:?fUrlCacheSvcStarted@@3HC; int volatile fUrlCacheSvcStarted
0x1800084f2  test    eax, eax
0x1800084f4  jz      loc_18000869B
0x1800084fa  mov     edx, 38h ; '8'; uBytes
0x1800084ff  mov     ecx, 40h ; '@'; uFlags
0x180008504  call    cs:__imp_LocalAlloc
0x18000850a  mov     rdi, rax
0x18000850d  test    rax, rax
0x180008510  jz      loc_1800086A8
0x180008516  mov     edx, 10h; uBytes
0x18000851b  mov     ecx, 40h ; '@'; uFlags
0x180008520  call    cs:__imp_LocalAlloc
0x180008526  mov     rsi, rax
0x180008529  test    rax, rax
0x18000852c  jz      loc_1800086B8
0x180008532  lea     rdx, [rdi+2Ch]; Pid
0x180008536  mov     [rdi+20h], rax
0x18000853a  mov     rcx, rbx; Binding
0x18000853d  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x180008543  test    eax, eax
0x180008545  jnz     loc_1800086CC
0x18000854b  cmp     [rdi+2Ch], ebp
0x18000854e  jz      loc_18000866E
0x180008554  mov     rcx, rbx; BindingHandle
0x180008557  call    cs:__imp_RpcImpersonateClient
0x18000855d  test    eax, eax
0x18000855f  jnz     loc_180008686
0x180008565  mov     ebp, 1
0x18000856a  call    cs:__imp_GetCurrentThread
0x180008570  mov     r9, rsi; TokenHandle
0x180008573  mov     edx, 0Ch; DesiredAccess
0x180008578  mov     rcx, rax; ThreadHandle
0x18000857b  mov     r8d, ebp; OpenAsSelf
0x18000857e  call    cs:__imp_OpenThreadToken
0x180008584  test    eax, eax
0x180008586  jz      loc_1800086D9
0x18000858c  mov     [rsi+8], ebp
0x18000858f  lea     rax, [rsp+48h+arg_8]
0x180008594  mov     [rsp+48h+arg_8], 4
0x18000859c  lea     r8, [rdi+28h]; TokenInformation
0x1800085a0  mov     rcx, [rsi]; TokenHandle
0x1800085a3  mov     r9d, 4; TokenInformationLength
0x1800085a9  mov     edx, 0Ch; TokenInformationClass
0x1800085ae  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x1800085b3  call    cs:__imp_GetTokenInformation
0x1800085b9  test    eax, eax
0x1800085bb  jz      short loc_18000862E
0x1800085bd  cmp     [rsp+48h+arg_8], 4
0x1800085c2  jnz     short loc_18000862E
0x1800085c4  cmp     dword ptr [rdi+28h], 0
0x1800085c8  jz      loc_18000864E
0x1800085ce  mov     rcx, rbx; BindingHandle
0x1800085d1  call    cs:__imp_RpcRevertToSelfEx
0x1800085d7  xor     ebp, ebp
0x1800085d9  test    eax, eax
0x1800085db  jnz     loc_1800086E5
0x1800085e1  mov     r9d, 1
0x1800085e7  xor     r8d, r8d
0x1800085ea  mov     edx, r9d
0x1800085ed  mov     rcx, rdi
0x1800085f0  xor     esi, esi
0x1800085f2  call    AddToBeRunJobEx
0x1800085f7  test    eax, eax
0x1800085f9  jz      short loc_18000862E
0x1800085fb  lock dec cs:?lUrlCacheSvcActiveRefCnt@@3JC; long volatile lUrlCacheSvcActiveRefCnt
0x180008602  mov     eax, esi
0x180008604  mov     rsi, [rsp+48h+arg_10]
0x180008609  mov     r15, [rsp+48h+var_18]
0x18000860e  mov     r14, [rsp+48h+var_10]
0x180008613  mov     rdi, [rsp+48h+arg_18]
0x180008618  mov     rbp, [rsp+48h+arg_0]
0x18000861d  add     rsp, 40h
0x180008621  pop     rbx
0x180008622  retn
0x180008623  mov     ecx, 57h ; 'W'; dwErrCode
0x180008628  call    cs:__imp_SetLastError
0x18000862e  call    cs:__imp_GetLastError
0x180008634  mov     esi, eax
0x180008636  mov     eax, 8000FFFFh
0x18000863b  test    esi, esi
0x18000863d  cmovz   esi, eax
0x180008640  test    ebp, ebp
0x180008642  jnz     short loc_18000867B
0x180008644  mov     rcx, rdi; hMem
0x180008647  call    FreeTriggerJob
0x18000864c  jmp     short loc_1800085FB
0x18000864e  mov     r8d, [rdi+2Ch]; dwProcessId
0x180008652  xor     edx, edx; bInheritHandle
0x180008654  mov     ecx, 100000h; dwDesiredAccess
0x180008659  call    cs:__imp_OpenProcess
0x18000865f  mov     [rdi+30h], rax
0x180008663  test    rax, rax
0x180008666  jnz     loc_1800085CE
0x18000866c  jmp     short loc_18000862E
0x18000866e  mov     ecx, 57h ; 'W'; dwErrCode
0x180008673  call    cs:__imp_SetLastError
0x180008679  jmp     short loc_18000862E
0x18000867b  mov     rcx, rbx; BindingHandle
0x18000867e  call    cs:__imp_RpcRevertToSelfEx
0x180008684  jmp     short loc_180008644
0x180008686  mov     ecx, eax; dwErrCode
0x180008688  call    cs:__imp_SetLastError
0x18000868e  jmp     short loc_18000862E
0x180008690  mov     eax, 426h
0x180008695  add     rsp, 40h
0x180008699  pop     rbx
0x18000869a  retn
0x18000869b  mov     ecx, 426h; dwErrCode
0x1800086a0  call    cs:__imp_SetLastError
0x1800086a6  jmp     short loc_18000862E
0x1800086a8  mov     ecx, 8007000Eh; dwErrCode
0x1800086ad  call    cs:__imp_SetLastError
0x1800086b3  jmp     loc_18000862E
0x1800086b8  mov     ecx, 8007000Eh; dwErrCode
0x1800086bd  call    cs:__imp_SetLastError
0x1800086c3  mov     [rdi+20h], rsi
0x1800086c7  jmp     loc_18000862E
0x1800086cc  mov     ecx, eax; dwErrCode
0x1800086ce  call    cs:__imp_SetLastError
0x1800086d4  jmp     loc_18000862E
0x1800086d9  mov     qword ptr [rsi], 0
0x1800086e0  jmp     loc_18000862E
0x1800086e5  mov     ecx, eax; dwErrCode
0x1800086e7  call    cs:__imp_SetLastError
0x1800086ed  jmp     loc_18000862E
```
