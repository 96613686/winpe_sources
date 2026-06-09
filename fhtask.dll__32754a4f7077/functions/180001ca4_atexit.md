# atexit

- ea: `0x180001ca4`
- end: `0x180001cbb`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180001010`
- `0x1800010b0`
- `0x1800010f0`
- `0x180001130`

## callees

- `0x180001c08`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (onexit_0((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x180001ca4  sub     rsp, 28h
0x180001ca8  call    _onexit_0
0x180001cad  neg     rax
0x180001cb0  sbb     eax, eax
0x180001cb2  neg     eax
0x180001cb4  dec     eax
0x180001cb6  add     rsp, 28h
0x180001cba  retn
```
