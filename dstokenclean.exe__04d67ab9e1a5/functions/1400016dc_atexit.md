# atexit

- ea: `0x1400016dc`
- end: `0x1400016f3`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140001010`

## callees

- `0x140001640`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (onexit_0((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x1400016dc  sub     rsp, 28h
0x1400016e0  call    _onexit_0
0x1400016e5  neg     rax
0x1400016e8  sbb     eax, eax
0x1400016ea  neg     eax
0x1400016ec  dec     eax
0x1400016ee  add     rsp, 28h
0x1400016f2  retn
```
