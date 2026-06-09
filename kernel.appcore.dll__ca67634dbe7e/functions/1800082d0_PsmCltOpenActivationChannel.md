# PsmCltOpenActivationChannel

- ea: `0x1800082d0`
- end: `0x1800082f5`
- name: `PsmCltOpenActivationChannel`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x1800082ea`
- `RPCRT4!NdrClientCall3` at `0x1800082ea`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall PsmCltOpenActivationChannel(__int64 a1, __int64 a2)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 2u, 0, a1, a2);
}

```

## disassembly

```asm
0x1800082d0  sub     rsp, 38h
0x1800082d4  xor     r8d, r8d; pReturnValue
0x1800082d7  mov     [rsp+38h+var_18], rdx
0x1800082dc  mov     r9, rcx
0x1800082df  lea     rcx, pProxyInfo; pProxyInfo
0x1800082e6  lea     edx, [r8+2]; nProcNum
0x1800082ea  call    cs:__imp_NdrClientCall3
0x1800082f0  add     rsp, 38h
0x1800082f4  retn
```
