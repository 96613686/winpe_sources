# DllCanUnloadNow

- ea: `0x1800011a0`
- end: `0x1800011ac`
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
  return g_cLocks != 0;
}

```

## disassembly

```asm
0x1800011a0  xor     eax, eax
0x1800011a2  cmp     cs:?g_cLocks@@3JA, eax; long g_cLocks
0x1800011a8  setnz   al
0x1800011ab  retn
```
