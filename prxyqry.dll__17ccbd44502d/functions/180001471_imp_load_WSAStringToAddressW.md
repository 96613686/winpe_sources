# __imp_load_WSAStringToAddressW

- ea: `0x180001471`
- end: `0x18000147d`
- name: `__imp_load_WSAStringToAddressW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800013e0`

## import_xrefs

- `WS2_32!WSAStringToAddressW` at `0x180001471`

## pseudocode

```c
__int64 __fastcall load_WSAStringToAddressW(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_ws2_32_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001471  lea     rax, __imp_WSAStringToAddressW
0x180001478  jmp     __tailMerge_ws2_32_dll
```
