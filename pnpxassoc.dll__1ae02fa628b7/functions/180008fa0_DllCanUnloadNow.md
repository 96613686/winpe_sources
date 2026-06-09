# DllCanUnloadNow

- ea: `0x180008fa0`
- end: `0x180008fac`
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
  return dword_18001AC2C != 0;
}

```

## disassembly

```asm
0x180008fa0  xor     eax, eax
0x180008fa2  cmp     cs:dword_18001AC2C, eax
0x180008fa8  setnz   al
0x180008fab  retn
```
