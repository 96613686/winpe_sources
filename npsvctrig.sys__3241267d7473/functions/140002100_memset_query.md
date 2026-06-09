# __memset_query

- ea: `0x140002100`
- end: `0x140002126`
- name: `__memset_query`
- size: `38`
- prototype: `void()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140002080`

## callees

- `0x140001a90`

## pseudocode

```c
void _memset_query()
{
  _cpu_features_init();
}

```

## disassembly

```asm
0x140002100  push    r9
0x140002102  push    r8
0x140002104  push    rdx
0x140002105  push    rcx
0x140002106  push    rax
0x140002107  sub     rsp, 30h
0x14000210b  movaps  [rsp+58h+var_38], xmm0
0x140002110  call    __cpu_features_init
0x140002115  movaps  xmm0, [rsp+58h+var_38]
0x14000211a  add     rsp, 30h
0x14000211e  pop     rax
0x14000211f  pop     rcx
0x140002120  pop     rdx
0x140002121  pop     r8
0x140002123  pop     r9
0x140002125  retn
```
