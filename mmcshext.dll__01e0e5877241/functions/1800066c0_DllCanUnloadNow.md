# DllCanUnloadNow

- ea: `0x1800066c0`
- end: `0x1800066cc`
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
  return dword_180012EE8 != 0;
}

```

## disassembly

```asm
0x1800066c0  xor     eax, eax
0x1800066c2  cmp     cs:dword_180012EE8, eax
0x1800066c8  setnz   al
0x1800066cb  retn
```
