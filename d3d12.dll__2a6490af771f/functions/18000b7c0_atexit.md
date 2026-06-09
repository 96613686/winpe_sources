# atexit

- ea: `0x18000b7c0`
- end: `0x18000b7d7`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `16`
- callee_count: `1`
- tags: ``

## callers

- `0x180001320`
- `0x180001340`
- `0x180008280`
- `0x180008c20`
- `0x180008c70`
- `0x180008fc0`
- `0x180009130`
- `0x180009160`
- `0x1800092b0`
- `0x180009350`
- `0x180009380`
- `0x1800093d0`
- `0x180009400`
- `0x180009440`
- `0x180009560`
- `0x1800095f0`

## callees

- `0x18000b780`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (onexit((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x18000b7c0  sub     rsp, 28h
0x18000b7c4  call    _onexit
0x18000b7c9  neg     rax
0x18000b7cc  sbb     eax, eax
0x18000b7ce  neg     eax
0x18000b7d0  dec     eax
0x18000b7d2  add     rsp, 28h
0x18000b7d6  retn
```
