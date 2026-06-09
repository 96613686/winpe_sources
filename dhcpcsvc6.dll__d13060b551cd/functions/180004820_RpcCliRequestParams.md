# RpcCliRequestParams

- ea: `0x180004820`
- end: `0x180004867`
- name: `RpcCliRequestParams`
- size: `71`
- prototype: `CLIENT_CALL_RETURN()`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180004e10`
- `0x1800062f0`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000485c`
- `RPCRT4!NdrClientCall3` at `0x18000485c`

## pseudocode

```c
CLIENT_CALL_RETURN RpcCliRequestParams()
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 4u, 0);
}

```

## disassembly

```asm
0x180004820  mov     r11, rsp
0x180004823  sub     rsp, 58h
0x180004827  mov     rax, [rsp+58h+arg_28]
0x18000482f  lea     rcx, pProxyInfo; pProxyInfo
0x180004836  mov     [r11-18h], rax
0x18000483a  mov     rax, [rsp+58h+arg_20]
0x180004842  mov     [r11-20h], rax
0x180004846  mov     [r11-28h], r9d
0x18000484a  xor     r9d, r9d
0x18000484d  mov     [r11-30h], r8
0x180004851  xor     r8d, r8d; pReturnValue
0x180004854  mov     [r11-38h], rdx
0x180004858  lea     edx, [r9+4]; nProcNum
0x18000485c  call    cs:__imp_NdrClientCall3
0x180004862  add     rsp, 58h
0x180004866  retn
```
