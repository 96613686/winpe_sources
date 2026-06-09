# atexit

- ea: `0x180001d2c`
- end: `0x180001d43`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180001520`
- `0x180001540`
- `0x180001560`
- `0x180001660`
- `0x180001680`
- `0x1800016a0`

## callees

- `0x180001c90`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (onexit_0((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x180001d2c  sub     rsp, 28h
0x180001d30  call    _onexit_0
0x180001d35  neg     rax
0x180001d38  sbb     eax, eax
0x180001d3a  neg     eax
0x180001d3c  dec     eax
0x180001d3e  add     rsp, 28h
0x180001d42  retn
```
