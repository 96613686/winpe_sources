# sub_CF50C

- ea: `0xcf50c`
- end: `0xcf511`
- name: `sub_CF50C`
- size: `5`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
void __fastcall __noreturn sub_CF50C(__int64 a1, __int64 a2, char a3)
{
  _BYTE *v3; // rbx

  *v3 += a3;
  __halt();
}

```

## disassembly

```asm
0xcf50c  add     [rbx], dl
0xcf50e  or      al, [rax]
0xcf510  hlt
```
