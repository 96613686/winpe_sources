# DllMain

- ea: `0x180003aec`
- end: `0x180003afe`
- name: `DllMain`
- size: `18`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001314`

## callees

- `0x180003aec`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  if ( fdwReason == 1 )
    g_DllInstance = hinstDLL;
  return 1;
}

```

## disassembly

```asm
0x180003aec  cmp     edx, 1
0x180003aef  jnz     short loc_180003AF8
0x180003af1  mov     cs:?g_DllInstance@@3PEAUHINSTANCE__@@EA, rcx; HINSTANCE__ * g_DllInstance
0x180003af8  mov     eax, 1
0x180003afd  retn
```
