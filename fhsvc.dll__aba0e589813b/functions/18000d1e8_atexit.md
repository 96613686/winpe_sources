# atexit

- ea: `0x18000d1e8`
- end: `0x18000d1ff`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1800010d0`
- `0x180001110`
- `0x180001150`
- `0x180001170`
- `0x180001190`

## callees

- `0x18000d14c`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (onexit_0((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x18000d1e8  sub     rsp, 28h
0x18000d1ec  call    _onexit_0
0x18000d1f1  neg     rax
0x18000d1f4  sbb     eax, eax
0x18000d1f6  neg     eax
0x18000d1f8  dec     eax
0x18000d1fa  add     rsp, 28h
0x18000d1fe  retn
```
