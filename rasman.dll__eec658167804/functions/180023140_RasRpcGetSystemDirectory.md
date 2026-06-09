# RasRpcGetSystemDirectory

- ea: `0x180023140`
- end: `0x18002316a`
- name: `RasRpcGetSystemDirectory`
- size: `42`
- prototype: `CLIENT_CALL_RETURN __fastcall(__int64, __int64, int)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180023968`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18002315f`
- `RPCRT4!NdrClientCall3` at `0x18002315f`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall RasRpcGetSystemDirectory(__int64 a1, __int64 a2, int a3)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0xBu, 0, a1, a2, a3);
}

```

## disassembly

```asm
0x180023140  sub     rsp, 38h
0x180023144  mov     [rsp+38h+var_10], r8d
0x180023149  mov     r9, rcx
0x18002314c  xor     r8d, r8d; pReturnValue
0x18002314f  mov     [rsp+38h+var_18], rdx
0x180023154  lea     rcx, pProxyInfo; pProxyInfo
0x18002315b  lea     edx, [r8+0Bh]; nProcNum
0x18002315f  call    cs:__imp_NdrClientCall3
0x180023165  add     rsp, 38h
0x180023169  retn
```
