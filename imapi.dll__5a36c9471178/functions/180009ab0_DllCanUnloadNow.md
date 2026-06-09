# DllCanUnloadNow

- ea: `0x180009ab0`
- end: `0x180009abc`
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
  return dword_180022B0C != 0;
}

```

## disassembly

```asm
0x180009ab0  xor     eax, eax
0x180009ab2  cmp     cs:dword_180022B0C, eax
0x180009ab8  setnz   al
0x180009abb  retn
```
