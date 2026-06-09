# CRpcUtils::GetClientToken(void * *,int)

- ea: `0x18001ed10`
- end: `0x18001ee2f`
- name: `?GetClientToken@CRpcUtils@@SAJPEAPEAXH@Z`
- size: `287`
- prototype: `__int64 __fastcall(void **, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18002d3b4`
- `0x18005c2e0`
- `0x1800720a0`

## callees

- `0x1800074c0`
- `0x18001ed10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ee08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ee08`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001ed4e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001ed4e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001ed35`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001ed35`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001edb6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001edb6`
- `RPCRT4!RpcImpersonateClient` at `0x18001edc0`
- `RPCRT4!RpcImpersonateClient` at `0x18001edc0`
- `RPCRT4!RpcRevertToSelf` at `0x18001ed84`
- `RPCRT4!RpcRevertToSelf` at `0x18001ed84`

## string_xrefs

- `0x18001ee26`: `OpenThreadToken failed: 0x%x in %s`
- `0x18001edd4`: `RpcImpersonateClient failed: 0x%x in %s`
- `0x18001eddb`: `CRpcUtils::GetClientToken`

## pseudocode

```c
__int64 __fastcall CRpcUtils::GetClientToken(void **a1, int a2)
{
  HANDLE CurrentThread; // rax
  unsigned int v5; // ebx
  void *v6; // rax
  int v8; // eax
  bool v9; // sf
  RPC_STATUS v10; // eax
  signed int LastError; // eax
  void *TokenHandle; // [rsp+40h] [rbp+18h] BYREF

  TokenHandle = 0;
  if ( a2 )
    goto LABEL_2;
  v10 = RpcImpersonateClient(0);
  v5 = v10;
  if ( v10 > 0 )
    v5 = (unsigned __int16)v10 | 0x80070000;
  if ( (v5 & 0x80000000) == 0 )
  {
LABEL_2:
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0xEu, 1, &TokenHandle) )
    {
      v5 = 0;
    }
    else
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
    }
    if ( a2 )
      goto LABEL_5;
    v8 = RpcRevertToSelf();
    v9 = v8 < 0;
    if ( v8 > 0 )
    {
      v8 = (unsigned __int16)v8 | 0x80070000;
      v9 = v8 < 0;
    }
    if ( !v9 )
    {
LABEL_5:
      if ( (v5 & 0x80000000) == 0 )
      {
        v6 = TokenHandle;
        goto LABEL_7;
      }
      _DbgPrintMessage(8, "OpenThreadToken failed: 0x%x in %s", v5, "CRpcUtils::GetClientToken");
    }
    else
    {
      _DbgPrintMessage(8, "RpcRevertToSelf failed: 0x%x", v8);
      v5 = -2147024891;
    }
  }
  else
  {
    _DbgPrintMessage(8, "RpcImpersonateClient failed: 0x%x in %s", v5, "CRpcUtils::GetClientToken");
  }
  v6 = TokenHandle;
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    return v5;
  }
LABEL_7:
  *a1 = v6;
  return v5;
}

```

## disassembly

```asm
0x18001ed10  mov     [rsp+arg_0], rbx
0x18001ed15  mov     [rsp+arg_8], rsi
0x18001ed1a  push    rdi
0x18001ed1b  sub     rsp, 20h
0x18001ed1f  mov     [rsp+28h+TokenHandle], 0
0x18001ed28  mov     edi, edx
0x18001ed2a  mov     rsi, rcx
0x18001ed2d  test    edx, edx
0x18001ed2f  jz      loc_18001EDBE
0x18001ed35  call    cs:__imp_GetCurrentThread
0x18001ed3b  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18001ed40  mov     edx, 0Eh; DesiredAccess
0x18001ed45  mov     rcx, rax; ThreadHandle
0x18001ed48  mov     r8d, 1; OpenAsSelf
0x18001ed4e  call    cs:__imp_OpenThreadToken
0x18001ed54  test    eax, eax
0x18001ed56  jz      loc_18001EE08
0x18001ed5c  xor     ebx, ebx
0x18001ed5e  test    edi, edi
0x18001ed60  jz      short loc_18001ED84
0x18001ed62  test    ebx, ebx
0x18001ed64  js      loc_18001EE26
0x18001ed6a  mov     rax, [rsp+28h+TokenHandle]
0x18001ed6f  mov     [rsi], rax
0x18001ed72  mov     rsi, [rsp+28h+arg_8]
0x18001ed77  mov     eax, ebx
0x18001ed79  mov     rbx, [rsp+28h+arg_0]
0x18001ed7e  add     rsp, 20h
0x18001ed82  pop     rdi
0x18001ed83  retn
0x18001ed84  call    cs:__imp_RpcRevertToSelf
0x18001ed8a  test    eax, eax
0x18001ed8c  jg      short loc_18001EDF1
0x18001ed8e  jns     short loc_18001ED62
0x18001ed90  mov     r8d, eax
0x18001ed93  lea     rdx, aRpcreverttosel; "RpcRevertToSelf failed: 0x%x"
0x18001ed9a  mov     ecx, 8; int
0x18001ed9f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001eda4  mov     ebx, 80070005h
0x18001eda9  mov     rax, [rsp+28h+TokenHandle]
0x18001edae  test    rax, rax
0x18001edb1  jz      short loc_18001ED6F
0x18001edb3  mov     rcx, rax; hObject
0x18001edb6  call    cs:__imp_CloseHandle
0x18001edbc  jmp     short loc_18001ED72
0x18001edbe  xor     ecx, ecx; BindingHandle
0x18001edc0  call    cs:__imp_RpcImpersonateClient
0x18001edc6  mov     ebx, eax
0x18001edc8  test    eax, eax
0x18001edca  jg      short loc_18001EDFD
0x18001edcc  test    ebx, ebx
0x18001edce  jns     loc_18001ED35
0x18001edd4  lea     rdx, aRpcimpersonate; "RpcImpersonateClient failed: 0x%x in %s"
0x18001eddb  lea     r9, aCrpcutilsGetcl; "CRpcUtils::GetClientToken"
0x18001ede2  mov     r8d, ebx
0x18001ede5  mov     ecx, 8; int
0x18001edea  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001edef  jmp     short loc_18001EDA9
0x18001edf1  movzx   eax, ax
0x18001edf4  or      eax, 80070000h
0x18001edf9  test    eax, eax
0x18001edfb  jmp     short loc_18001ED8E
0x18001edfd  movzx   ebx, ax
0x18001ee00  or      ebx, 80070000h
0x18001ee06  jmp     short loc_18001EDCC
0x18001ee08  call    cs:__imp_GetLastError
0x18001ee0e  mov     ebx, eax
0x18001ee10  test    eax, eax
0x18001ee12  jle     loc_18001ED5E
0x18001ee18  movzx   ebx, ax
0x18001ee1b  or      ebx, 80070000h
0x18001ee21  jmp     loc_18001ED5E
0x18001ee26  lea     rdx, aOpenthreadtoke_0; "OpenThreadToken failed: 0x%x in %s"
0x18001ee2d  jmp     short loc_18001EDDB
```
