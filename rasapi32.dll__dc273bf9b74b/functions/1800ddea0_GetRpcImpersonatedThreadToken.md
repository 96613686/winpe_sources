# GetRpcImpersonatedThreadToken

- ea: `0x1800ddea0`
- end: `0x1800ddf1b`
- name: `GetRpcImpersonatedThreadToken`
- size: `123`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800ddb70`

## callees

- `0x1800ddea0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800dded9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800dded9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ddec4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ddec4`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800ddef0`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800ddef0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ddf04`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ddf04`
- `RPCRT4!RpcRevertToSelf` at `0x1800ddf0a`
- `RPCRT4!RpcRevertToSelf` at `0x1800ddf0a`
- `RPCRT4!RpcImpersonateClient` at `0x1800ddeba`
- `RPCRT4!RpcImpersonateClient` at `0x1800ddeba`

## pseudocode

```c
void *GetRpcImpersonatedThreadToken()
{
  HANDLE CurrentThread; // rax
  void *TokenHandle; // [rsp+30h] [rbp+8h] BYREF
  void *DuplicateTokenHandle; // [rsp+38h] [rbp+10h] BYREF

  TokenHandle = (void *)-1LL;
  DuplicateTokenHandle = (void *)-1LL;
  if ( !RpcImpersonateClient(0) )
  {
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0xEu, 1, &TokenHandle) )
    {
      if ( !DuplicateToken(TokenHandle, SecurityImpersonation, &DuplicateTokenHandle) )
        DuplicateTokenHandle = (void *)-1LL;
      CloseHandle(TokenHandle);
    }
    RpcRevertToSelf();
  }
  return DuplicateTokenHandle;
}

```

## disassembly

```asm
0x1800ddea0  mov     [rsp+TokenHandle], rcx
0x1800ddea5  push    rbx
0x1800ddea6  sub     rsp, 20h
0x1800ddeaa  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800ddeae  xor     ecx, ecx; BindingHandle
0x1800ddeb0  mov     [rsp+28h+TokenHandle], rbx
0x1800ddeb5  mov     [rsp+28h+DuplicateTokenHandle], rbx
0x1800ddeba  call    cs:__imp_RpcImpersonateClient
0x1800ddec0  test    eax, eax
0x1800ddec2  jnz     short loc_1800DDF10
0x1800ddec4  call    cs:__imp_GetCurrentThread
0x1800ddeca  mov     rcx, rax; ThreadHandle
0x1800ddecd  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x1800dded2  lea     edx, [rbx+0Fh]; DesiredAccess
0x1800dded5  lea     r8d, [rbx+2]; OpenAsSelf
0x1800dded9  call    cs:__imp_OpenThreadToken
0x1800ddedf  test    eax, eax
0x1800ddee1  jz      short loc_1800DDF0A
0x1800ddee3  mov     rcx, [rsp+28h+TokenHandle]; ExistingTokenHandle
0x1800ddee8  lea     r8, [rsp+28h+DuplicateTokenHandle]; DuplicateTokenHandle
0x1800ddeed  lea     edx, [rbx+3]; ImpersonationLevel
0x1800ddef0  call    cs:__imp_DuplicateToken
0x1800ddef6  test    eax, eax
0x1800ddef8  jnz     short loc_1800DDEFF
0x1800ddefa  mov     [rsp+28h+DuplicateTokenHandle], rbx
0x1800ddeff  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x1800ddf04  call    cs:__imp_CloseHandle
0x1800ddf0a  call    cs:__imp_RpcRevertToSelf
0x1800ddf10  mov     rax, [rsp+28h+DuplicateTokenHandle]
0x1800ddf15  add     rsp, 20h
0x1800ddf19  pop     rbx
0x1800ddf1a  retn
```
