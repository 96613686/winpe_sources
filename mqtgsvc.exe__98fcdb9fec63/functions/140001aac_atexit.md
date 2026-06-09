# atexit

- ea: `0x140001aac`
- end: `0x140001ac3`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `18`
- callee_count: `1`
- tags: ``

## callers

- `0x140001010`
- `0x140001040`
- `0x140001070`
- `0x140001090`
- `0x1400010b0`
- `0x1400010e0`
- `0x140001110`
- `0x140001140`
- `0x140001170`
- `0x1400011a0`
- `0x1400011d0`
- `0x140001210`
- `0x140001250`
- `0x1400012f0`
- `0x140001340`
- `0x140001360`
- `0x1400014a0`
- `0x1400014c0`

## callees

- `0x140001a10`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (onexit_0((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x140001aac  sub     rsp, 28h
0x140001ab0  call    _onexit_0
0x140001ab5  neg     rax
0x140001ab8  sbb     eax, eax
0x140001aba  neg     eax
0x140001abc  dec     eax
0x140001abe  add     rsp, 28h
0x140001ac2  retn
```
