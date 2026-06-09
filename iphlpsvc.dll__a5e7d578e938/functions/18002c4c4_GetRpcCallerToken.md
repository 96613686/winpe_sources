# GetRpcCallerToken

- ea: `0x18002c4c4`
- end: `0x18002c5bf`
- name: `GetRpcCallerToken`
- size: `251`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle, PHANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18002c0bc`
- `0x18002c278`

## callees

- `0x1800190f0`
- `0x18002c4c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c543`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c543`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002c51a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002c51a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002c533`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002c533`
- `RPCRT4!RpcImpersonateClient` at `0x18002c4e0`
- `RPCRT4!RpcImpersonateClient` at `0x18002c4e0`
- `RPCRT4!RpcRevertToSelfEx` at `0x18002c575`
- `RPCRT4!RpcRevertToSelfEx` at `0x18002c575`

## string_xrefs

- `0x18002c502`: `RpcImpersonateClient returned 0x%x`
- `0x18002c561`: `OpenThreadToken returned 0x%x`

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
0x18002c4c4  mov     [rsp+arg_0], rbx
0x18002c4c9  mov     [rsp+arg_8], rbp
0x18002c4ce  push    rdi
0x18002c4cf  sub     rsp, 20h
0x18002c4d3  mov     rdi, rdx
0x18002c4d6  mov     qword ptr [rdx], 0
0x18002c4dd  mov     rbp, rcx
0x18002c4e0  call    cs:__imp_RpcImpersonateClient
0x18002c4e7  nop     dword ptr [rax+rax+00h]
0x18002c4ec  test    eax, eax
0x18002c4ee  jz      short loc_18002C518
0x18002c4f0  jg      short loc_18002C4F6
0x18002c4f2  mov     ebx, eax
0x18002c4f4  jmp     short loc_18002C4FF
0x18002c4f6  movzx   ebx, ax
0x18002c4f9  or      ebx, 80070000h
0x18002c4ff  mov     r8d, eax
0x18002c502  lea     rdx, aRpcimpersonate; "RpcImpersonateClient returned 0x%x"
0x18002c509  mov     ecx, 100000h
0x18002c50e  call    EventWriteError0
0x18002c513  jmp     loc_18002C5AC
0x18002c518  xor     ebx, ebx
0x18002c51a  call    cs:__imp_GetCurrentThread
0x18002c521  nop     dword ptr [rax+rax+00h]
0x18002c526  mov     r9, rdi; TokenHandle
0x18002c529  lea     edx, [rbx+8]; DesiredAccess
0x18002c52c  mov     rcx, rax; ThreadHandle
0x18002c52f  lea     r8d, [rbx+1]; OpenAsSelf
0x18002c533  call    cs:__imp_OpenThreadToken
0x18002c53a  nop     dword ptr [rax+rax+00h]
0x18002c53f  test    eax, eax
0x18002c541  jnz     short loc_18002C572
0x18002c543  call    cs:__imp_GetLastError
0x18002c54a  nop     dword ptr [rax+rax+00h]
0x18002c54f  mov     ebx, eax
0x18002c551  test    eax, eax
0x18002c553  jle     short loc_18002C55E
0x18002c555  movzx   ebx, ax
0x18002c558  or      ebx, 80070000h
0x18002c55e  mov     r8d, ebx
0x18002c561  lea     rdx, aOpenthreadtoke; "OpenThreadToken returned 0x%x"
0x18002c568  mov     ecx, 100000h
0x18002c56d  call    EventWriteError0
0x18002c572  mov     rcx, rbp; BindingHandle
0x18002c575  call    cs:__imp_RpcRevertToSelfEx
0x18002c57c  nop     dword ptr [rax+rax+00h]
0x18002c581  mov     edi, eax
0x18002c583  test    eax, eax
0x18002c585  jz      short loc_18002C5AC
0x18002c587  mov     r8d, eax
0x18002c58a  lea     rdx, aRpcreverttosel; "RpcRevertToSelfEx returned 0x%x"
0x18002c591  mov     ecx, 100000h
0x18002c596  call    EventWriteError0
0x18002c59b  test    edi, edi
0x18002c59d  jg      short loc_18002C5A3
0x18002c59f  mov     ebx, edi
0x18002c5a1  jmp     short loc_18002C5AC
0x18002c5a3  movzx   ebx, di
0x18002c5a6  or      ebx, 80070000h
0x18002c5ac  mov     rbp, [rsp+28h+arg_8]
0x18002c5b1  mov     eax, ebx
0x18002c5b3  mov     rbx, [rsp+28h+arg_0]
0x18002c5b8  add     rsp, 20h
0x18002c5bc  pop     rdi
0x18002c5bd  retn
```
