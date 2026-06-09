# atexit

- ea: `0x1800023ac`
- end: `0x1800023c3`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180001980`
- `0x1800019d0`
- `0x180001a00`
- `0x180001a40`
- `0x180001b60`
- `0x180001b80`
- `0x1800023d0`
- `0x18000e970`

## callees

- `0x18000236c`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (onexit((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x1800023ac  sub     rsp, 28h
0x1800023b0  call    _onexit
0x1800023b5  neg     rax
0x1800023b8  sbb     eax, eax
0x1800023ba  neg     eax
0x1800023bc  dec     eax
0x1800023be  add     rsp, 28h
0x1800023c2  retn
```
