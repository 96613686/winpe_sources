# atexit

- ea: `0x180001fd4`
- end: `0x180001feb`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800017b0`
- `0x1800017d0`
- `0x180004edc`
- `0x1800055b0`

## callees

- `0x180001f94`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (onexit((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x180001fd4  sub     rsp, 28h
0x180001fd8  call    _onexit
0x180001fdd  neg     rax
0x180001fe0  sbb     eax, eax
0x180001fe2  neg     eax
0x180001fe4  dec     eax
0x180001fe6  add     rsp, 28h
0x180001fea  retn
```
