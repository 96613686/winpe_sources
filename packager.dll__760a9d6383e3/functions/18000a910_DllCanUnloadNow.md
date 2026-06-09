# DllCanUnloadNow

- ea: `0x18000a910`
- end: `0x18000a91c`
- name: `DllCanUnloadNow`
- size: `12`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  return g_cRefThisDll != 0;
}

```

## disassembly

```asm
0x18000a910  xor     eax, eax
0x18000a912  cmp     cs:?g_cRefThisDll@@3JA, eax; long g_cRefThisDll
0x18000a918  setnz   al
0x18000a91b  retn
```
