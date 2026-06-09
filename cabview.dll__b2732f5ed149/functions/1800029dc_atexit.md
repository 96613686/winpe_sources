# atexit

- ea: `0x1800029dc`
- end: `0x1800029f3`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180002030`
- `0x180002050`
- `0x1800021b0`
- `0x1800021d0`
- `0x180002210`
- `0x180011ac4`
- `0x180011ba0`

## callees

- `0x18000299c`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (onexit((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x1800029dc  sub     rsp, 28h
0x1800029e0  call    _onexit
0x1800029e5  neg     rax
0x1800029e8  sbb     eax, eax
0x1800029ea  neg     eax
0x1800029ec  dec     eax
0x1800029ee  add     rsp, 28h
0x1800029f2  retn
```
