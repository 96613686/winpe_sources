# CryptSvcSecurityCallback

- ea: `0x18000b3e0`
- end: `0x18000b416`
- name: `CryptSvcSecurityCallback`
- size: `54`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000b3e0`

## import_xrefs

- `RPCRT4!I_RpcBindingIsClientLocal` at `0x18000b3f3`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x18000b3f3`

## pseudocode

```c
__int64 CryptSvcSecurityCallback()
{
  unsigned int ClientLocalFlag; // [rsp+40h] [rbp+18h] BYREF

  ClientLocalFlag = 0;
  if ( I_RpcBindingIsClientLocal(0, &ClientLocalFlag) )
    return 5;
  else
    return ClientLocalFlag == 0 ? 5 : 0;
}

```

## disassembly

```asm
0x18000b3e0  sub     rsp, 28h
0x18000b3e4  lea     rdx, [rsp+28h+ClientLocalFlag]; ClientLocalFlag
0x18000b3e9  mov     [rsp+28h+ClientLocalFlag], 0
0x18000b3f1  xor     ecx, ecx; BindingHandle
0x18000b3f3  call    cs:__imp_I_RpcBindingIsClientLocal
0x18000b3f9  test    eax, eax
0x18000b3fb  jz      short loc_18000B407
0x18000b3fd  mov     eax, 5
0x18000b402  add     rsp, 28h
0x18000b406  retn
0x18000b407  mov     eax, [rsp+28h+ClientLocalFlag]
0x18000b40b  neg     eax
0x18000b40d  sbb     eax, eax
0x18000b40f  not     eax
0x18000b411  and     eax, 5
0x18000b414  jmp     short loc_18000B402
```
