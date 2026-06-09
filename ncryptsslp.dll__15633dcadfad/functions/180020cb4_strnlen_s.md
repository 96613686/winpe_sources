# strnlen_s

- ea: `0x180020cb4`
- end: `0x180020cc6`
- name: `strnlen_s`
- size: `18`
- prototype: `static size_t __cdecl(const char *String, size_t MaxCount)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1800037a0`
- `0x180004570`
- `0x180005240`
- `0x18000a120`
- `0x18000e820`

## callees

- `0x180014760`
- `0x180020cb4`

## pseudocode

```c
size_t __cdecl strnlen_s(const char *String, size_t MaxCount)
{
  if ( String )
    return strnlen(String, 0xF9u);
  else
    return 0;
}

```

## disassembly

```asm
0x180020cb4  test    rcx, rcx
0x180020cb7  jnz     short loc_180020CBC
0x180020cb9  xor     eax, eax
0x180020cbb  retn
0x180020cbc  mov     edx, 0F9h; MaxCount
0x180020cc1  jmp     strnlen
```
