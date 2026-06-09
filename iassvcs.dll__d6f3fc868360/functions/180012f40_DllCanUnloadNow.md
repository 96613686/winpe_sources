# DllCanUnloadNow

- ea: `0x180012f40`
- end: `0x180012f4c`
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
  return dword_180024F5C != 0;
}

```

## disassembly

```asm
0x180012f40  xor     eax, eax
0x180012f42  cmp     cs:dword_180024F5C, eax
0x180012f48  setnz   al
0x180012f4b  retn
```
