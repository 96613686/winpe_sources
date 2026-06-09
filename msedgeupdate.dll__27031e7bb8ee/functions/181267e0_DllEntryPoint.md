# DllEntryPoint

- ea: `0x181267e0`
- end: `0x181267e7`
- name: `DllEntryPoint`
- size: `7`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
BOOL __stdcall DllEntryPoint(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  BOOL result; // eax

  return result;
}

```

## disassembly

```asm
0x181267e0  sar     dh, 0C0h
0x181267e3  pop     edi
0x181267e4  pop     esi
0x181267e5  pop     ebp
0x181267e6  retn
```
