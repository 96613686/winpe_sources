# atexit

- ea: `0x180002aec`
- end: `0x180002b03`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x180001e50`
- `0x180001e70`
- `0x180001e90`
- `0x1800020e0`
- `0x180002100`
- `0x180002120`
- `0x180002160`
- `0x180002180`
- `0x1800021a0`
- `0x18000f144`

## callees

- `0x180002aac`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (onexit((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x180002aec  sub     rsp, 28h
0x180002af0  call    _onexit
0x180002af5  neg     rax
0x180002af8  sbb     eax, eax
0x180002afa  neg     eax
0x180002afc  dec     eax
0x180002afe  add     rsp, 28h
0x180002b02  retn
```
