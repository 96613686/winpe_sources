# DllCanUnloadNow

- ea: `0x180010780`
- end: `0x18001078c`
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
  return g_cLockCount != 0;
}

```

## disassembly

```asm
0x180010780  xor     eax, eax
0x180010782  cmp     cs:?g_cLockCount@@3KA, eax; ulong g_cLockCount
0x180010788  setnz   al
0x18001078b  retn
```
