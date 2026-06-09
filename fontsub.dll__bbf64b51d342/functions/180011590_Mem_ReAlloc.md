# Mem_ReAlloc

- ea: `0x180011590`
- end: `0x1800115a4`
- name: `Mem_ReAlloc`
- size: `20`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180012154`
- `0x180012640`
- `0x180013b7c`
- `0x180016dd8`

## callees

- `0x180011538`
- `0x180011590`

## import_xrefs

- `msvcrt!realloc` at `0x18001159d`

## pseudocode

```c
void *__fastcall Mem_ReAlloc(void *a1, size_t a2)
{
  if ( a1 )
    return realloc(a1, a2);
  else
    return Mem_Alloc(a2);
}

```

## disassembly

```asm
0x180011590  test    rcx, rcx
0x180011593  jnz     short loc_18001159D
0x180011595  mov     rcx, rdx; Size
0x180011598  jmp     Mem_Alloc
0x18001159d  jmp     cs:__imp_realloc
```
