# DllMain

- ea: `0x1800040dc`
- end: `0x1800040ff`
- name: `DllMain`
- size: `35`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001314`

## callees

- `0x1800040dc`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  if ( fdwReason )
  {
    if ( fdwReason == 1 )
      g_hModule = hinstDLL;
  }
  else
  {
    g_hModule = 0;
  }
  return 1;
}

```

## disassembly

```asm
0x1800040dc  test    edx, edx
0x1800040de  jz      short loc_1800040EE
0x1800040e0  cmp     edx, 1
0x1800040e3  jnz     short loc_1800040F9
0x1800040e5  mov     cs:?g_hModule@@3PEAUHINSTANCE__@@EA, rcx; HINSTANCE__ * g_hModule
0x1800040ec  jmp     short loc_1800040F9
0x1800040ee  mov     cs:?g_hModule@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * g_hModule
0x1800040f9  mov     eax, 1
0x1800040fe  retn
```
