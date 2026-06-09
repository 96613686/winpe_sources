# CryptSvcSecurityCallback

- ea: `0x180005a80`
- end: `0x180005ab2`
- name: `CryptSvcSecurityCallback`
- size: `50`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005a80`

## import_xrefs

- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180005a93`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180005a93`

## pseudocode

```c
__int64 CryptSvcSecurityCallback()
{
  bool v0; // zf
  __int64 result; // rax
  unsigned int v2; // ecx
  unsigned int ClientLocalFlag; // [rsp+40h] [rbp+18h] BYREF

  ClientLocalFlag = 0;
  v0 = I_RpcBindingIsClientLocal(0, &ClientLocalFlag) == 0;
  result = 5;
  if ( v0 )
  {
    v2 = 0;
    if ( !ClientLocalFlag )
      return 5;
    return v2;
  }
  return result;
}

```

## disassembly

```asm
0x180005a80  sub     rsp, 28h
0x180005a84  lea     rdx, [rsp+28h+ClientLocalFlag]; ClientLocalFlag
0x180005a89  mov     [rsp+28h+ClientLocalFlag], 0
0x180005a91  xor     ecx, ecx; BindingHandle
0x180005a93  call    cs:__imp_I_RpcBindingIsClientLocal
0x180005a99  test    eax, eax
0x180005a9b  mov     eax, 5
0x180005aa0  jnz     short loc_180005AAD
0x180005aa2  xor     ecx, ecx
0x180005aa4  cmp     [rsp+28h+ClientLocalFlag], ecx
0x180005aa8  cmovz   ecx, eax
0x180005aab  mov     eax, ecx
0x180005aad  add     rsp, 28h
0x180005ab1  retn
```
