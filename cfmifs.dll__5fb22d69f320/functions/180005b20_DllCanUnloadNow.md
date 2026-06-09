# DllCanUnloadNow

- ea: `0x180005b20`
- end: `0x180005b2c`
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
  return dword_18000B7CC != 0;
}

```

## disassembly

```asm
0x180005b20  xor     eax, eax
0x180005b22  cmp     cs:dword_18000B7CC, eax
0x180005b28  setnz   al
0x180005b2b  retn
```
