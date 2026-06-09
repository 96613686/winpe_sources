# atexit

- ea: `0x140001f3c`
- end: `0x140001f53`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140001460`
- `0x140001480`
- `0x1400014a0`
- `0x1400014c0`

## callees

- `0x140001ea0`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (onexit_0((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x140001f3c  sub     rsp, 28h
0x140001f40  call    _onexit_0
0x140001f45  neg     rax
0x140001f48  sbb     eax, eax
0x140001f4a  neg     eax
0x140001f4c  dec     eax
0x140001f4e  add     rsp, 28h
0x140001f52  retn
```
