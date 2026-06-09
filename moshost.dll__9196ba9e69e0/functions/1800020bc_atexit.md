# atexit

- ea: `0x1800020bc`
- end: `0x1800020d3`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x1800017c0`
- `0x1800017e0`
- `0x180001800`
- `0x180001830`
- `0x180001850`
- `0x1800018c0`
- `0x1800018e0`
- `0x1800065ac`
- `0x18000689c`

## callees

- `0x18000207c`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (onexit((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x1800020bc  sub     rsp, 28h
0x1800020c0  call    _onexit
0x1800020c5  neg     rax
0x1800020c8  sbb     eax, eax
0x1800020ca  neg     eax
0x1800020cc  dec     eax
0x1800020ce  add     rsp, 28h
0x1800020d2  retn
```
