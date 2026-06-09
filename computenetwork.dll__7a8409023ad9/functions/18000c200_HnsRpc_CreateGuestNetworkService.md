# HnsRpc_CreateGuestNetworkService

- ea: `0x18000c200`
- end: `0x18000c238`
- name: `HnsRpc_CreateGuestNetworkService`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000c22d`
- `RPCRT4!NdrClientCall3` at `0x18000c22d`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall HnsRpc_CreateGuestNetworkService(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x2Cu, 0, a1, a2, a3, a4, a5);
}

```

## disassembly

```asm
0x18000c200  mov     r11, rsp
0x18000c203  sub     rsp, 48h
0x18000c207  mov     rax, [rsp+48h+arg_20]
0x18000c20c  mov     [r11-10h], rax
0x18000c210  mov     [r11-18h], r9
0x18000c214  mov     r9, rcx
0x18000c217  mov     [r11-20h], r8
0x18000c21b  lea     rcx, pProxyInfo; pProxyInfo
0x18000c222  xor     r8d, r8d; pReturnValue
0x18000c225  mov     [r11-28h], rdx
0x18000c229  lea     edx, [r8+2Ch]; nProcNum
0x18000c22d  call    cs:__imp_NdrClientCall3
0x18000c233  add     rsp, 48h
0x18000c237  retn
```
