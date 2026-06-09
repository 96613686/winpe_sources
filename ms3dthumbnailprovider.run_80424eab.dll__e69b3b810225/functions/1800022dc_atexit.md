# atexit

- ea: `0x1800022dc`
- end: `0x1800022f3`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180001980`
- `0x180001ac0`
- `0x180001ae0`
- `0x180007c04`

## callees

- `0x18000229c`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (onexit((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x1800022dc  sub     rsp, 28h
0x1800022e0  call    _onexit
0x1800022e5  neg     rax
0x1800022e8  sbb     eax, eax
0x1800022ea  neg     eax
0x1800022ec  dec     eax
0x1800022ee  add     rsp, 28h
0x1800022f2  retn
```
