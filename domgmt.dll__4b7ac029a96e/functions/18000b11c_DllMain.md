# DllMain

- ea: `0x18000b11c`
- end: `0x18000b12d`
- name: `DllMain`
- size: `17`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001a14`

## callees

- `0x18000b11c`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  BOOL result; // eax

  result = 1;
  if ( fdwReason == 1 )
    g_hModule = hinstDLL;
  return result;
}

```

## disassembly

```asm
0x18000b11c  mov     eax, 1
0x18000b121  cmp     edx, eax
0x18000b123  jnz     short locret_18000B12C
0x18000b125  mov     cs:?g_hModule@@3PEAUHINSTANCE__@@EA, rcx; HINSTANCE__ * g_hModule
0x18000b12c  retn
```
