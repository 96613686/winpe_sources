# GetRpcClientToken(void * *)

- ea: `0x18001fabc`
- end: `0x18001fb31`
- name: `?GetRpcClientToken@@YAJPEAPEAX@Z`
- size: `117`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle)`
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18002c05c`
- `0x180055614`
- `0x180055e2c`
- `0x18005a688`

## callees

- `0x18001fabc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fb1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fb1a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001faf0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001faf0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001fade`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001fade`
- `RPCRT4!RpcRevertToSelf` at `0x18001fafa`
- `RPCRT4!RpcRevertToSelf` at `0x18001fafa`
- `RPCRT4!RpcImpersonateClient` at `0x18001fad2`
- `RPCRT4!RpcImpersonateClient` at `0x18001fad2`

## pseudocode

```c
__int64 __fastcall GetRpcClientToken(PHANDLE TokenHandle)
{
  RPC_STATUS v2; // eax
  unsigned int v3; // ebx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax

  *TokenHandle = 0;
  v2 = RpcImpersonateClient(0);
  v3 = v2;
  if ( v2 )
  {
    if ( v2 > 0 )
      return (unsigned __int16)v2 | 0x80070000;
  }
  else
  {
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 0xEu, 0, TokenHandle) )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
    }
    RpcRevertToSelf();
  }
  return v3;
}

```

## disassembly

```asm
0x18001fabc  mov     [rsp+arg_0], rbx
0x18001fac1  push    rdi
0x18001fac2  sub     rsp, 20h
0x18001fac6  mov     rdi, rcx
0x18001fac9  mov     qword ptr [rcx], 0
0x18001fad0  xor     ecx, ecx; BindingHandle
0x18001fad2  call    cs:__imp_RpcImpersonateClient
0x18001fad8  mov     ebx, eax
0x18001fada  test    eax, eax
0x18001fadc  jnz     short loc_18001FB0D
0x18001fade  call    cs:__imp_GetCurrentThread
0x18001fae4  mov     r9, rdi; TokenHandle
0x18001fae7  lea     edx, [rbx+0Eh]; DesiredAccess
0x18001faea  mov     rcx, rax; ThreadHandle
0x18001faed  xor     r8d, r8d; OpenAsSelf
0x18001faf0  call    cs:__imp_OpenThreadToken
0x18001faf6  test    eax, eax
0x18001faf8  jz      short loc_18001FB1A
0x18001fafa  call    cs:__imp_RpcRevertToSelf
0x18001fb00  mov     eax, ebx
0x18001fb02  mov     rbx, [rsp+28h+arg_0]
0x18001fb07  add     rsp, 20h
0x18001fb0b  pop     rdi
0x18001fb0c  retn
0x18001fb0d  jle     short loc_18001FB00
0x18001fb0f  movzx   ebx, ax
0x18001fb12  or      ebx, 80070000h
0x18001fb18  jmp     short loc_18001FB00
0x18001fb1a  call    cs:__imp_GetLastError
0x18001fb20  mov     ebx, eax
0x18001fb22  test    eax, eax
0x18001fb24  jle     short loc_18001FAFA
0x18001fb26  movzx   ebx, ax
0x18001fb29  or      ebx, 80070000h
0x18001fb2f  jmp     short loc_18001FAFA
```
