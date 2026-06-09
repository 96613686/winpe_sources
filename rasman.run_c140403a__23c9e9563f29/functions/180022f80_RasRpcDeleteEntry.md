# RasRpcDeleteEntry

- ea: `0x180022f80`
- end: `0x180022faa`
- name: `RasRpcDeleteEntry`
- size: `42`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180023a7c`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180022f9f`
- `RPCRT4!NdrClientCall3` at `0x180022f9f`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall RasRpcDeleteEntry(__int64 a1, __int64 a2, __int64 a3)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 5u, 0, a1, a2, a3);
}

```

## disassembly

```asm
0x180022f80  sub     rsp, 38h
0x180022f84  mov     [rsp+38h+var_10], r8
0x180022f89  mov     r9, rcx
0x180022f8c  xor     r8d, r8d; pReturnValue
0x180022f8f  mov     [rsp+38h+var_18], rdx
0x180022f94  lea     rcx, pProxyInfo; pProxyInfo
0x180022f9b  lea     edx, [r8+5]; nProcNum
0x180022f9f  call    cs:__imp_NdrClientCall3
0x180022fa5  add     rsp, 38h
0x180022fa9  retn
```
