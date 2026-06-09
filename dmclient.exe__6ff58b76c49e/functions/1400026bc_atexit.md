# atexit

- ea: `0x1400026bc`
- end: `0x1400026d3`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140001e00`
- `0x140001e20`
- `0x140001e40`
- `0x140001f40`
- `0x140001f60`
- `0x140001f80`

## callees

- `0x140002620`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (onexit_0((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x1400026bc  sub     rsp, 28h
0x1400026c0  call    _onexit_0
0x1400026c5  neg     rax
0x1400026c8  sbb     eax, eax
0x1400026ca  neg     eax
0x1400026cc  dec     eax
0x1400026ce  add     rsp, 28h
0x1400026d2  retn
```
