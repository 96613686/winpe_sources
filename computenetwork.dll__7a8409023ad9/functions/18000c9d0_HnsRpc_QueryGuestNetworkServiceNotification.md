# HnsRpc_QueryGuestNetworkServiceNotification

- ea: `0x18000c9d0`
- end: `0x18000c9ff`
- name: `HnsRpc_QueryGuestNetworkServiceNotification`
- size: `47`
- prototype: `int(void *, unsigned int *, int *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000c9f4`
- `RPCRT4!NdrClientCall3` at `0x18000c9f4`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall HnsRpc_QueryGuestNetworkServiceNotification(
        void *a1,
        unsigned int *a2,
        int *a3,
        unsigned __int16 **a4)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x33u, 0, a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000c9d0  sub     rsp, 48h
0x18000c9d4  mov     [rsp+48h+var_18], r9
0x18000c9d9  mov     r9, rcx
0x18000c9dc  mov     [rsp+48h+var_20], r8
0x18000c9e1  lea     rcx, pProxyInfo; pProxyInfo
0x18000c9e8  xor     r8d, r8d; pReturnValue
0x18000c9eb  mov     [rsp+48h+var_28], rdx
0x18000c9f0  lea     edx, [r8+33h]; nProcNum
0x18000c9f4  call    cs:__imp_NdrClientCall3
0x18000c9fa  add     rsp, 48h
0x18000c9fe  retn
```
