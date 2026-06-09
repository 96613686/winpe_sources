# EfsRpcOpenFileRaw

- ea: `0x18000c660`
- end: `0x18000c68d`
- name: `EfsRpcOpenFileRaw`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000c682`
- `RPCRT4!NdrClientCall3` at `0x18000c682`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall EfsRpcOpenFileRaw(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0, 0, a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000c660  sub     rsp, 48h
0x18000c664  mov     [rsp+48h+var_18], r9d
0x18000c669  mov     r9, rcx
0x18000c66c  mov     [rsp+48h+var_20], r8
0x18000c671  lea     rcx, pProxyInfo; pProxyInfo
0x18000c678  mov     [rsp+48h+var_28], rdx
0x18000c67d  xor     r8d, r8d; pReturnValue
0x18000c680  xor     edx, edx; nProcNum
0x18000c682  call    cs:__imp_NdrClientCall3
0x18000c688  add     rsp, 48h
0x18000c68c  retn
```
