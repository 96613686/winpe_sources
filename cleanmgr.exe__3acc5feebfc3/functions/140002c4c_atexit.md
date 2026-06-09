# atexit

- ea: `0x140002c4c`
- end: `0x140002c63`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x140002570`
- `0x140002590`
- `0x1400025b0`
- `0x1400025d0`
- `0x1400026f0`
- `0x14000ed4c`
- `0x1400128bc`

## callees

- `0x140002c0c`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (onexit((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x140002c4c  sub     rsp, 28h
0x140002c50  call    _onexit
0x140002c55  neg     rax
0x140002c58  sbb     eax, eax
0x140002c5a  neg     eax
0x140002c5c  dec     eax
0x140002c5e  add     rsp, 28h
0x140002c62  retn
```
