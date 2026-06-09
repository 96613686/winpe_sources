# CRpcUtils::GetClientToken(void * *,int)

- ea: `0x180020290`
- end: `0x1800203d4`
- name: `?GetClientToken@CRpcUtils@@SAJPEAPEAXH@Z`
- size: `324`
- prototype: `__int64 __fastcall(void **, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18002f3c0`
- `0x18005fd30`
- `0x180076200`

## callees

- `0x1800077a0`
- `0x180020290`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800203a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800203a7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800202d4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800202d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800202b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800202b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020349`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020349`
- `RPCRT4!RpcImpersonateClient` at `0x180020359`
- `RPCRT4!RpcImpersonateClient` at `0x180020359`
- `RPCRT4!RpcRevertToSelf` at `0x180020311`
- `RPCRT4!RpcRevertToSelf` at `0x180020311`

## string_xrefs

- `0x1800203cb`: `OpenThreadToken failed: 0x%x in %s`
- `0x180020373`: `RpcImpersonateClient failed: 0x%x in %s`
- `0x18002037a`: `CRpcUtils::GetClientToken`

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
0x180020290  mov     [rsp+arg_0], rbx
0x180020295  mov     [rsp+arg_8], rsi
0x18002029a  push    rdi
0x18002029b  sub     rsp, 20h
0x18002029f  mov     [rsp+28h+TokenHandle], 0
0x1800202a8  mov     edi, edx
0x1800202aa  mov     rsi, rcx
0x1800202ad  test    edx, edx
0x1800202af  jz      loc_180020357
0x1800202b5  call    cs:__imp_GetCurrentThread
0x1800202bc  nop     dword ptr [rax+rax+00h]
0x1800202c1  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x1800202c6  mov     edx, 0Eh; DesiredAccess
0x1800202cb  mov     rcx, rax; ThreadHandle
0x1800202ce  mov     r8d, 1; OpenAsSelf
0x1800202d4  call    cs:__imp_OpenThreadToken
0x1800202db  nop     dword ptr [rax+rax+00h]
0x1800202e0  test    eax, eax
0x1800202e2  jz      loc_1800203A7
0x1800202e8  xor     ebx, ebx
0x1800202ea  test    edi, edi
0x1800202ec  jz      short loc_180020311
0x1800202ee  test    ebx, ebx
0x1800202f0  js      loc_1800203CB
0x1800202f6  mov     rax, [rsp+28h+TokenHandle]
0x1800202fb  mov     [rsi], rax
0x1800202fe  mov     rsi, [rsp+28h+arg_8]
0x180020303  mov     eax, ebx
0x180020305  mov     rbx, [rsp+28h+arg_0]
0x18002030a  add     rsp, 20h
0x18002030e  pop     rdi
0x18002030f  retn
0x180020311  call    cs:__imp_RpcRevertToSelf
0x180020318  nop     dword ptr [rax+rax+00h]
0x18002031d  test    eax, eax
0x18002031f  jg      short loc_180020390
0x180020321  jns     short loc_1800202EE
0x180020323  mov     r8d, eax
0x180020326  lea     rdx, aRpcreverttosel; "RpcRevertToSelf failed: 0x%x"
0x18002032d  mov     ecx, 8; int
0x180020332  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180020337  mov     ebx, 80070005h
0x18002033c  mov     rax, [rsp+28h+TokenHandle]
0x180020341  test    rax, rax
0x180020344  jz      short loc_1800202FB
0x180020346  mov     rcx, rax; hObject
0x180020349  call    cs:__imp_CloseHandle
0x180020350  nop     dword ptr [rax+rax+00h]
0x180020355  jmp     short loc_1800202FE
0x180020357  xor     ecx, ecx; BindingHandle
0x180020359  call    cs:__imp_RpcImpersonateClient
0x180020360  nop     dword ptr [rax+rax+00h]
0x180020365  mov     ebx, eax
0x180020367  test    eax, eax
0x180020369  jg      short loc_18002039C
0x18002036b  test    ebx, ebx
0x18002036d  jns     loc_1800202B5
0x180020373  lea     rdx, aRpcimpersonate; "RpcImpersonateClient failed: 0x%x in %s"
0x18002037a  lea     r9, aCrpcutilsGetcl; "CRpcUtils::GetClientToken"
0x180020381  mov     r8d, ebx
0x180020384  mov     ecx, 8; int
0x180020389  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002038e  jmp     short loc_18002033C
0x180020390  movzx   eax, ax
0x180020393  or      eax, 80070000h
0x180020398  test    eax, eax
0x18002039a  jmp     short loc_180020321
0x18002039c  movzx   ebx, ax
0x18002039f  or      ebx, 80070000h
0x1800203a5  jmp     short loc_18002036B
0x1800203a7  call    cs:__imp_GetLastError
0x1800203ae  nop     dword ptr [rax+rax+00h]
0x1800203b3  mov     ebx, eax
0x1800203b5  test    eax, eax
0x1800203b7  jle     loc_1800202EA
0x1800203bd  movzx   ebx, ax
0x1800203c0  or      ebx, 80070000h
0x1800203c6  jmp     loc_1800202EA
0x1800203cb  lea     rdx, aOpenthreadtoke_0; "OpenThreadToken failed: 0x%x in %s"
0x1800203d2  jmp     short loc_18002037A
```
