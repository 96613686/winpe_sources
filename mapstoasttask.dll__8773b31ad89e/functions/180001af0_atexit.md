# atexit

- ea: `0x180001af0`
- end: `0x180001b07`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800010f0`
- `0x180001110`

## callees

- `0x180001ab0`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (onexit((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x180001af0  sub     rsp, 28h
0x180001af4  call    _onexit
0x180001af9  neg     rax
0x180001afc  sbb     eax, eax
0x180001afe  neg     eax
0x180001b00  dec     eax
0x180001b02  add     rsp, 28h
0x180001b06  retn
```
