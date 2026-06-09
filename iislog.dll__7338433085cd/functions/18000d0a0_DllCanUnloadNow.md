# DllCanUnloadNow

- ea: `0x18000d0a0`
- end: `0x18000d0ac`
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
  return dword_180017A78 != 0;
}

```

## disassembly

```asm
0x18000d0a0  xor     eax, eax
0x18000d0a2  cmp     cs:dword_180017A78, eax
0x18000d0a8  setnz   al
0x18000d0ab  retn
```
