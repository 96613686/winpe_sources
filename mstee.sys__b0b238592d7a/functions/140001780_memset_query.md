# __memset_query

- ea: `0x140001780`
- end: `0x1400017a6`
- name: `__memset_query`
- size: `38`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140001700`

## callees

- `0x1400010f0`

## pseudocode

```c
void _memset_query()
{
  _cpu_features_init();
}

```

## disassembly

```asm
0x140001780  push    r9
0x140001782  push    r8
0x140001784  push    rdx
0x140001785  push    rcx
0x140001786  push    rax
0x140001787  sub     rsp, 30h
0x14000178b  movaps  [rsp+58h+var_38], xmm0
0x140001790  call    __cpu_features_init
0x140001795  movaps  xmm0, [rsp+58h+var_38]
0x14000179a  add     rsp, 30h
0x14000179e  pop     rax
0x14000179f  pop     rcx
0x1400017a0  pop     rdx
0x1400017a1  pop     r8
0x1400017a3  pop     r9
0x1400017a5  retn
```
