# atexit

- ea: `0x180002ee8`
- end: `0x180002eff`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180001010`
- `0x180001030`
- `0x180001050`
- `0x180001070`
- `0x1800011c0`
- `0x1800011e0`

## callees

- `0x180002e4c`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (onexit_0((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x180002ee8  sub     rsp, 28h
0x180002eec  call    _onexit_0
0x180002ef1  neg     rax
0x180002ef4  sbb     eax, eax
0x180002ef6  neg     eax
0x180002ef8  dec     eax
0x180002efa  add     rsp, 28h
0x180002efe  retn
```
