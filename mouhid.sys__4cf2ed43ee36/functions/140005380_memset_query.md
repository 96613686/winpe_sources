# __memset_query

- ea: `0x140005380`
- end: `0x1400053a6`
- name: `__memset_query`
- size: `38`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140005300`

## callees

- `0x140004d20`

## pseudocode

```c
void _memset_query()
{
  _cpu_features_init();
}

```

## disassembly

```asm
0x140005380  push    r9
0x140005382  push    r8
0x140005384  push    rdx
0x140005385  push    rcx
0x140005386  push    rax
0x140005387  sub     rsp, 30h
0x14000538b  movaps  [rsp+58h+var_38], xmm0
0x140005390  call    __cpu_features_init
0x140005395  movaps  xmm0, [rsp+58h+var_38]
0x14000539a  add     rsp, 30h
0x14000539e  pop     rax
0x14000539f  pop     rcx
0x1400053a0  pop     rdx
0x1400053a1  pop     r8
0x1400053a3  pop     r9
0x1400053a5  retn
```
