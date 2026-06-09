# GetRpcCallerToken

- ea: `0x18002c4b4`
- end: `0x18002c5af`
- name: `GetRpcCallerToken`
- size: `251`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle, PHANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18002c0ac`
- `0x18002c268`

## callees

- `0x1800190e0`
- `0x18002c4b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c533`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c533`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002c50a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002c50a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002c523`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002c523`
- `RPCRT4!RpcImpersonateClient` at `0x18002c4d0`
- `RPCRT4!RpcImpersonateClient` at `0x18002c4d0`
- `RPCRT4!RpcRevertToSelfEx` at `0x18002c565`
- `RPCRT4!RpcRevertToSelfEx` at `0x18002c565`

## string_xrefs

- `0x18002c4f2`: `RpcImpersonateClient returned 0x%x`
- `0x18002c551`: `OpenThreadToken returned 0x%x`

## pseudocode

```c
__int64 __fastcall GetRpcCallerToken(RPC_BINDING_HANDLE BindingHandle, PHANDLE TokenHandle)
{
  RPC_STATUS v4; // eax
  unsigned int v5; // ebx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  unsigned int v8; // eax
  int v9; // edi

  *TokenHandle = 0;
  v4 = RpcImpersonateClient(BindingHandle);
  if ( v4 )
  {
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
    else
      v5 = v4;
    EventWriteError0(0x100000, L"RpcImpersonateClient returned 0x%x", (unsigned int)v4);
  }
  else
  {
    v5 = 0;
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 1, TokenHandle) )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      EventWriteError0(0x100000, L"OpenThreadToken returned 0x%x", v5);
    }
    v8 = RpcRevertToSelfEx(BindingHandle);
    v9 = v8;
    if ( v8 )
    {
      EventWriteError0(0x100000, L"RpcRevertToSelfEx returned 0x%x", v8);
      if ( v9 > 0 )
        return (unsigned __int16)v9 | 0x80070000;
      else
        return (unsigned int)v9;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18002c4b4  mov     [rsp+arg_0], rbx
0x18002c4b9  mov     [rsp+arg_8], rbp
0x18002c4be  push    rdi
0x18002c4bf  sub     rsp, 20h
0x18002c4c3  mov     rdi, rdx
0x18002c4c6  mov     qword ptr [rdx], 0
0x18002c4cd  mov     rbp, rcx
0x18002c4d0  call    cs:__imp_RpcImpersonateClient
0x18002c4d7  nop     dword ptr [rax+rax+00h]
0x18002c4dc  test    eax, eax
0x18002c4de  jz      short loc_18002C508
0x18002c4e0  jg      short loc_18002C4E6
0x18002c4e2  mov     ebx, eax
0x18002c4e4  jmp     short loc_18002C4EF
0x18002c4e6  movzx   ebx, ax
0x18002c4e9  or      ebx, 80070000h
0x18002c4ef  mov     r8d, eax
0x18002c4f2  lea     rdx, aRpcimpersonate; "RpcImpersonateClient returned 0x%x"
0x18002c4f9  mov     ecx, 100000h
0x18002c4fe  call    EventWriteError0
0x18002c503  jmp     loc_18002C59C
0x18002c508  xor     ebx, ebx
0x18002c50a  call    cs:__imp_GetCurrentThread
0x18002c511  nop     dword ptr [rax+rax+00h]
0x18002c516  mov     r9, rdi; TokenHandle
0x18002c519  lea     edx, [rbx+8]; DesiredAccess
0x18002c51c  mov     rcx, rax; ThreadHandle
0x18002c51f  lea     r8d, [rbx+1]; OpenAsSelf
0x18002c523  call    cs:__imp_OpenThreadToken
0x18002c52a  nop     dword ptr [rax+rax+00h]
0x18002c52f  test    eax, eax
0x18002c531  jnz     short loc_18002C562
0x18002c533  call    cs:__imp_GetLastError
0x18002c53a  nop     dword ptr [rax+rax+00h]
0x18002c53f  mov     ebx, eax
0x18002c541  test    eax, eax
0x18002c543  jle     short loc_18002C54E
0x18002c545  movzx   ebx, ax
0x18002c548  or      ebx, 80070000h
0x18002c54e  mov     r8d, ebx
0x18002c551  lea     rdx, aOpenthreadtoke; "OpenThreadToken returned 0x%x"
0x18002c558  mov     ecx, 100000h
0x18002c55d  call    EventWriteError0
0x18002c562  mov     rcx, rbp; BindingHandle
0x18002c565  call    cs:__imp_RpcRevertToSelfEx
0x18002c56c  nop     dword ptr [rax+rax+00h]
0x18002c571  mov     edi, eax
0x18002c573  test    eax, eax
0x18002c575  jz      short loc_18002C59C
0x18002c577  mov     r8d, eax
0x18002c57a  lea     rdx, aRpcreverttosel; "RpcRevertToSelfEx returned 0x%x"
0x18002c581  mov     ecx, 100000h
0x18002c586  call    EventWriteError0
0x18002c58b  test    edi, edi
0x18002c58d  jg      short loc_18002C593
0x18002c58f  mov     ebx, edi
0x18002c591  jmp     short loc_18002C59C
0x18002c593  movzx   ebx, di
0x18002c596  or      ebx, 80070000h
0x18002c59c  mov     rbp, [rsp+28h+arg_8]
0x18002c5a1  mov     eax, ebx
0x18002c5a3  mov     rbx, [rsp+28h+arg_0]
0x18002c5a8  add     rsp, 20h
0x18002c5ac  pop     rdi
0x18002c5ad  retn
```
