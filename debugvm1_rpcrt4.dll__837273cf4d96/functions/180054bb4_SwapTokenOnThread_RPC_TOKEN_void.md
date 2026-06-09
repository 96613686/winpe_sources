# SwapTokenOnThread(RPC_TOKEN *,void * *)

- ea: `0x180054bb4`
- end: `0x180054c2c`
- name: `?SwapTokenOnThread@@YAHPEAVRPC_TOKEN@@PEAPEAX@Z`
- size: `120`
- prototype: `__int64 __fastcall(struct RPC_TOKEN *, void **)`
- caller_count: `6`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800548c0`
- `0x1800550b0`
- `0x180055ce4`
- `0x1800595ac`
- `0x18009a5f4`
- `0x1800a48a0`

## callees

- `0x180054bb4`
- `0x180054c34`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054c24`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054c24`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180054be9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180054be9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180054bd2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180054bd2`

## pseudocode

```c
__int64 __fastcall SwapTokenOnThread(void **a1, void **a2)
{
  void *v3; // rbx
  HANDLE CurrentThread; // rax
  void *TokenHandle; // [rsp+30h] [rbp+8h] BYREF

  TokenHandle = 0;
  if ( a1 )
    v3 = *a1;
  else
    v3 = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
  {
    if ( (unsigned int)ReplaceToken(v3) )
    {
      *a2 = TokenHandle;
      return 1;
    }
    if ( TokenHandle )
      CloseHandle(TokenHandle);
  }
  return 0;
}

```

## disassembly

```asm
0x180054bb4  mov     [rsp+arg_8], rbx
0x180054bb9  push    rdi
0x180054bba  sub     rsp, 20h
0x180054bbe  mov     [rsp+28h+TokenHandle], 0
0x180054bc7  mov     rdi, rdx
0x180054bca  test    rcx, rcx
0x180054bcd  jz      short loc_180054C20
0x180054bcf  mov     rbx, [rcx]
0x180054bd2  call    cs:__imp_GetCurrentThread
0x180054bd8  mov     edx, 0Ch; DesiredAccess
0x180054bdd  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x180054be2  mov     rcx, rax; ThreadHandle
0x180054be5  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x180054be9  call    cs:__imp_OpenThreadToken
0x180054bef  test    eax, eax
0x180054bf1  jz      short loc_180054C1C
0x180054bf3  mov     rcx, rbx; void *
0x180054bf6  call    ?ReplaceToken@@YAHPEAX@Z; ReplaceToken(void *)
0x180054bfb  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x180054c00  test    eax, eax
0x180054c02  jz      short loc_180054C17
0x180054c04  mov     [rdi], rcx
0x180054c07  mov     eax, 1
0x180054c0c  mov     rbx, [rsp+28h+arg_8]
0x180054c11  add     rsp, 20h
0x180054c15  pop     rdi
0x180054c16  retn
0x180054c17  test    rcx, rcx
0x180054c1a  jnz     short loc_180054C24
0x180054c1c  xor     eax, eax
0x180054c1e  jmp     short loc_180054C0C
0x180054c20  xor     ebx, ebx
0x180054c22  jmp     short loc_180054BD2
0x180054c24  call    cs:__imp_CloseHandle
0x180054c2a  jmp     short loc_180054C1C
```
