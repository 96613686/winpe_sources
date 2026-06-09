# atexit

- ea: `0x180001d1c`
- end: `0x180001d33`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180001510`
- `0x180001530`
- `0x180001550`
- `0x180001650`
- `0x180001670`
- `0x180001690`

## callees

- `0x180001c80`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (onexit_0((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x180001d1c  sub     rsp, 28h
0x180001d20  call    _onexit_0
0x180001d25  neg     rax
0x180001d28  sbb     eax, eax
0x180001d2a  neg     eax
0x180001d2c  dec     eax
0x180001d2e  add     rsp, 28h
0x180001d32  retn
```
