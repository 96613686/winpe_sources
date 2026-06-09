# DllCanUnloadNow

- ea: `0x180011870`
- end: `0x18001187c`
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
  return g_cRefCount != 0;
}

```

## disassembly

```asm
0x180011870  xor     eax, eax
0x180011872  cmp     cs:g_cRefCount, eax
0x180011878  setnz   al
0x18001187b  retn
```
