# __memset_query

- ea: `0x140003ac0`
- end: `0x140003ae6`
- name: `__memset_query`
- size: `38`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140003a40`

## callees

- `0x140003460`

## pseudocode

```c
void _memset_query()
{
  _cpu_features_init();
}

```

## disassembly

```asm
0x140003ac0  push    r9
0x140003ac2  push    r8
0x140003ac4  push    rdx
0x140003ac5  push    rcx
0x140003ac6  push    rax
0x140003ac7  sub     rsp, 30h
0x140003acb  movaps  [rsp+58h+var_38], xmm0
0x140003ad0  call    __cpu_features_init
0x140003ad5  movaps  xmm0, [rsp+58h+var_38]
0x140003ada  add     rsp, 30h
0x140003ade  pop     rax
0x140003adf  pop     rcx
0x140003ae0  pop     rdx
0x140003ae1  pop     r8
0x140003ae3  pop     r9
0x140003ae5  retn
```
