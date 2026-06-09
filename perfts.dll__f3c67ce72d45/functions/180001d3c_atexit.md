# atexit

- ea: `0x180001d3c`
- end: `0x180001d53`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180001290`
- `0x1800012b0`
- `0x1800012d0`
- `0x1800012f0`
- `0x180001320`
- `0x180001350`

## callees

- `0x180001ca0`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (onexit_0((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x180001d3c  sub     rsp, 28h
0x180001d40  call    _onexit_0
0x180001d45  neg     rax
0x180001d48  sbb     eax, eax
0x180001d4a  neg     eax
0x180001d4c  dec     eax
0x180001d4e  add     rsp, 28h
0x180001d52  retn
```
