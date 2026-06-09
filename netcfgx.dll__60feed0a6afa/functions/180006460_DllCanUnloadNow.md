# DllCanUnloadNow

- ea: `0x180006460`
- end: `0x18000646c`
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
  return dword_18001A5EC != 0;
}

```

## disassembly

```asm
0x180006460  xor     eax, eax
0x180006462  cmp     cs:dword_18001A5EC, eax
0x180006468  setnz   al
0x18000646b  retn
```
