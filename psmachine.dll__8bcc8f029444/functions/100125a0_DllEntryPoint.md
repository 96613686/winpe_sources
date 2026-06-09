# DllEntryPoint

- ea: `0x100125a0`
- end: `0x100125a5`
- name: `DllEntryPoint`
- size: `5`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
BOOL __stdcall DllEntryPoint(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  char v3; // al
  BOOL result; // eax

  LOBYTE(result) = v3 & 4;
  return result;
}

```

## disassembly

```asm
0x100125a0  and     al, 4
0x100125a2  mov     edi, edx
0x100125a4  retn
```
