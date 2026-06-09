# __imp_load_I_RpcMapWin32Status

- ea: `0x1800028a3`
- end: `0x1800028af`
- name: `__imp_load_I_RpcMapWin32Status`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002824`

## import_xrefs

- `RPCRT4!I_RpcMapWin32Status` at `0x1800028a3`

## pseudocode

```c
__int64 __fastcall load_I_RpcMapWin32Status(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_rpcrt4_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800028a3  lea     rax, __imp_I_RpcMapWin32Status
0x1800028aa  jmp     __tailMerge_rpcrt4_dll
```
