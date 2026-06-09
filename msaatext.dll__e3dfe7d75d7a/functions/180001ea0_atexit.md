# atexit

- ea: `0x180001ea0`
- end: `0x180001eb7`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180001010`
- `0x180001030`
- `0x180001050`

## callees

- `0x180001e04`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (onexit_0((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x180001ea0  sub     rsp, 28h
0x180001ea4  call    _onexit_0
0x180001ea9  neg     rax
0x180001eac  sbb     eax, eax
0x180001eae  neg     eax
0x180001eb0  dec     eax
0x180001eb2  add     rsp, 28h
0x180001eb6  retn
```
