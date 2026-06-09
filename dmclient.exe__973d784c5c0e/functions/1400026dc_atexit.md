# atexit

- ea: `0x1400026dc`
- end: `0x1400026f3`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140001e20`
- `0x140001e40`
- `0x140001e60`
- `0x140001f60`
- `0x140001f80`
- `0x140001fa0`

## callees

- `0x140002640`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (onexit_0((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x1400026dc  sub     rsp, 28h
0x1400026e0  call    _onexit_0
0x1400026e5  neg     rax
0x1400026e8  sbb     eax, eax
0x1400026ea  neg     eax
0x1400026ec  dec     eax
0x1400026ee  add     rsp, 28h
0x1400026f2  retn
```
