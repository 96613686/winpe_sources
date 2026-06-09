# DllCanUnloadNow

- ea: `0x180007930`
- end: `0x18000793c`
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
  return dword_18000F8D8 != 0;
}

```

## disassembly

```asm
0x180007930  xor     eax, eax
0x180007932  cmp     cs:dword_18000F8D8, eax
0x180007938  setnz   al
0x18000793b  retn
```
