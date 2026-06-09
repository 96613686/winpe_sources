# __memset_query

- ea: `0x140003c80`
- end: `0x140003ca6`
- name: `__memset_query`
- size: `38`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140003c00`

## callees

- `0x140001190`

## pseudocode

```c
void _memset_query()
{
  _cpu_features_init();
}

```

## disassembly

```asm
0x140003c80  push    r9
0x140003c82  push    r8
0x140003c84  push    rdx
0x140003c85  push    rcx
0x140003c86  push    rax
0x140003c87  sub     rsp, 30h
0x140003c8b  movaps  [rsp+58h+var_38], xmm0
0x140003c90  call    __cpu_features_init
0x140003c95  movaps  xmm0, [rsp+58h+var_38]
0x140003c9a  add     rsp, 30h
0x140003c9e  pop     rax
0x140003c9f  pop     rcx
0x140003ca0  pop     rdx
0x140003ca1  pop     r8
0x140003ca3  pop     r9
0x140003ca5  retn
```
