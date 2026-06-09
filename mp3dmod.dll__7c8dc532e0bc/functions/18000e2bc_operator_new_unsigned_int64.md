# operator new(unsigned __int64)

- ea: `0x18000e2bc`
- end: `0x18000e2f5`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c490`
- `0x18000c9fc`
- `0x18000cd00`
- `0x18000cd94`
- `0x18000cf58`
- `0x18000cfdc`
- `0x18000e2fc`
- `0x180010208`

## callees

- `0x18000e2bc`
- `0x18000ef36`
- `0x18000efa4`

## pseudocode

```c
void *__fastcall operator new(size_t Size)
{
  size_t i; // rdi
  void *v2; // rbx

  for ( i = Size; ; Size = i )
  {
    v2 = o_malloc_0(Size);
    if ( v2 || !(unsigned int)o__callnewh_0(i) )
      break;
  }
  return v2;
}

```

## disassembly

```asm
0x18000e2bc  mov     [rsp+arg_0], rbx
0x18000e2c1  push    rdi
0x18000e2c2  sub     rsp, 20h
0x18000e2c6  mov     rdi, rcx
0x18000e2c9  jmp     short loc_18000E2DA
0x18000e2cb  mov     rcx, rdi
0x18000e2ce  call    _o__callnewh_0
0x18000e2d3  test    eax, eax
0x18000e2d5  jz      short loc_18000E2E7
0x18000e2d7  mov     rcx, rdi; Size
0x18000e2da  call    _o_malloc_0
0x18000e2df  mov     rbx, rax
0x18000e2e2  test    rax, rax
0x18000e2e5  jz      short loc_18000E2CB
0x18000e2e7  mov     rax, rbx
0x18000e2ea  mov     rbx, [rsp+28h+arg_0]
0x18000e2ef  add     rsp, 20h
0x18000e2f3  pop     rdi
0x18000e2f4  retn
```
