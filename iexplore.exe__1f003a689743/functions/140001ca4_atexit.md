# atexit

- ea: `0x140001ca4`
- end: `0x140001cbb`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400014b0`
- `0x1400014d0`

## callees

- `0x140001c08`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (onexit_0((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x140001ca4  sub     rsp, 28h
0x140001ca8  call    _onexit_0
0x140001cad  neg     rax
0x140001cb0  sbb     eax, eax
0x140001cb2  neg     eax
0x140001cb4  dec     eax
0x140001cb6  add     rsp, 28h
0x140001cba  retn
```
