# __memset_query

- ea: `0x140004700`
- end: `0x140004726`
- name: `__memset_query`
- size: `38`
- prototype: `void()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140004680`

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
0x140004700  push    r9
0x140004702  push    r8
0x140004704  push    rdx
0x140004705  push    rcx
0x140004706  push    rax
0x140004707  sub     rsp, 30h
0x14000470b  movaps  [rsp+58h+var_38], xmm0
0x140004710  call    __cpu_features_init
0x140004715  movaps  xmm0, [rsp+58h+var_38]
0x14000471a  add     rsp, 30h
0x14000471e  pop     rax
0x14000471f  pop     rcx
0x140004720  pop     rdx
0x140004721  pop     r8
0x140004723  pop     r9
0x140004725  retn
```
