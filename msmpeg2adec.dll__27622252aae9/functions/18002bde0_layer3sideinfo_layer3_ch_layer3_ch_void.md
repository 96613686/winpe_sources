# layer3sideinfo::_layer3_ch::_layer3_ch(void)

- ea: `0x18002bde0`
- end: `0x18002be0e`
- name: `??0_layer3_ch@layer3sideinfo@@QEAA@XZ`
- size: `46`
- prototype: `__int64 __fastcall(layer3sideinfo::_layer3_ch *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18002b6d0`

## callees

- `0x18002be20`

## pseudocode

```c
layer3sideinfo::_layer3_ch *__fastcall layer3sideinfo::_layer3_ch::_layer3_ch(layer3sideinfo::_layer3_ch *this)
{
  layer3grinfo::layer3grinfo((layer3sideinfo::_layer3_ch *)((char *)this + 16));
  layer3grinfo::layer3grinfo((layer3sideinfo::_layer3_ch *)((char *)this + 92));
  return this;
}

```

## disassembly

```asm
0x18002bde0  mov     [rsp+arg_0], rbx
0x18002bde5  push    rdi
0x18002bde6  sub     rsp, 20h
0x18002bdea  mov     rdi, rcx
0x18002bded  add     rcx, 10h; this
0x18002bdf1  call    ??0layer3grinfo@@QEAA@XZ; layer3grinfo::layer3grinfo(void)
0x18002bdf6  lea     rcx, [rdi+5Ch]; this
0x18002bdfa  call    ??0layer3grinfo@@QEAA@XZ; layer3grinfo::layer3grinfo(void)
0x18002bdff  mov     rbx, [rsp+28h+arg_0]
0x18002be04  mov     rax, rdi
0x18002be07  add     rsp, 20h
0x18002be0b  pop     rdi
0x18002be0c  retn
```
