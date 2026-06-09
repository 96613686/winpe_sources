# CImpersonate::ImpersonateRpcClient(void)

- ea: `0x180021bc4`
- end: `0x180021c5f`
- name: `?ImpersonateRpcClient@CImpersonate@@QEAAJXZ`
- size: `155`
- prototype: `__int64 __fastcall(CImpersonate *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180030b90`
- `0x18005b080`
- `0x18005caf0`
- `0x18005d000`

## callees

- `0x1800074c0`
- `0x180021bc4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021c2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021c2f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180021bf1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180021bf1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180021bda`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180021bda`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021c05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021c05`
- `RPCRT4!RpcImpersonateClient` at `0x180021c0d`
- `RPCRT4!RpcImpersonateClient` at `0x180021c0d`

## string_xrefs

- `0x180021c4c`: `RpcImpersonateClient failed: 0x%x in %s`
- `0x180021c42`: `CImpersonate::ImpersonateRpcClient`

## pseudocode

```c
__int64 __fastcall CImpersonate::ImpersonateRpcClient(CImpersonate *this)
{
  HANDLE CurrentThread; // rax
  RPC_STATUS v3; // eax
  signed int v4; // ebx
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xEu, 1, &TokenHandle) )
    GetLastError();
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  v3 = RpcImpersonateClient(0);
  v4 = v3;
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x80070000;
  if ( v4 < 0 )
    _DbgPrintMessage(8, "RpcImpersonateClient failed: 0x%x in %s", v4, "CImpersonate::ImpersonateRpcClient");
  else
    *(_WORD *)this = 257;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180021bc4  mov     [rsp+arg_0], rbx
0x180021bc9  push    rdi
0x180021bca  sub     rsp, 20h
0x180021bce  mov     rdi, rcx
0x180021bd1  mov     [rsp+28h+TokenHandle], 0
0x180021bda  call    cs:__imp_GetCurrentThread
0x180021be0  mov     edx, 0Eh; DesiredAccess
0x180021be5  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x180021bea  mov     rcx, rax; ThreadHandle
0x180021bed  lea     r8d, [rdx-0Dh]; OpenAsSelf
0x180021bf1  call    cs:__imp_OpenThreadToken
0x180021bf7  test    eax, eax
0x180021bf9  jz      short loc_180021C2F
0x180021bfb  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x180021c00  test    rcx, rcx
0x180021c03  jz      short loc_180021C0B
0x180021c05  call    cs:__imp_CloseHandle
0x180021c0b  xor     ecx, ecx; BindingHandle
0x180021c0d  call    cs:__imp_RpcImpersonateClient
0x180021c13  mov     ebx, eax
0x180021c15  test    eax, eax
0x180021c17  jg      short loc_180021C37
0x180021c19  test    ebx, ebx
0x180021c1b  js      short loc_180021C42
0x180021c1d  mov     word ptr [rdi], 101h
0x180021c22  mov     eax, ebx
0x180021c24  mov     rbx, [rsp+28h+arg_0]
0x180021c29  add     rsp, 20h
0x180021c2d  pop     rdi
0x180021c2e  retn
0x180021c2f  call    cs:__imp_GetLastError
0x180021c35  jmp     short loc_180021BFB
0x180021c37  movzx   ebx, ax
0x180021c3a  or      ebx, 80070000h
0x180021c40  jmp     short loc_180021C19
0x180021c42  lea     r9, aCimpersonateIm_0; "CImpersonate::ImpersonateRpcClient"
0x180021c49  mov     r8d, ebx
0x180021c4c  lea     rdx, aRpcimpersonate; "RpcImpersonateClient failed: 0x%x in %s"
0x180021c53  mov     ecx, 8; int
0x180021c58  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180021c5d  jmp     short loc_180021C22
```
