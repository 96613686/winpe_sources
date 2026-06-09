# HnsRpc_QueryServiceNotification

- ea: `0x18000cbd0`
- end: `0x18000cbff`
- name: `HnsRpc_QueryServiceNotification`
- size: `47`
- prototype: `int(void *, unsigned int *, int *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000cbf4`
- `RPCRT4!NdrClientCall3` at `0x18000cbf4`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall HnsRpc_QueryServiceNotification(
        void *a1,
        unsigned int *a2,
        int *a3,
        unsigned __int16 **a4)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x29u, 0, a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000cbd0  sub     rsp, 48h
0x18000cbd4  mov     [rsp+48h+var_18], r9
0x18000cbd9  mov     r9, rcx
0x18000cbdc  mov     [rsp+48h+var_20], r8
0x18000cbe1  lea     rcx, pProxyInfo; pProxyInfo
0x18000cbe8  xor     r8d, r8d; pReturnValue
0x18000cbeb  mov     [rsp+48h+var_28], rdx
0x18000cbf0  lea     edx, [r8+29h]; nProcNum
0x18000cbf4  call    cs:__imp_NdrClientCall3
0x18000cbfa  add     rsp, 48h
0x18000cbfe  retn
```
