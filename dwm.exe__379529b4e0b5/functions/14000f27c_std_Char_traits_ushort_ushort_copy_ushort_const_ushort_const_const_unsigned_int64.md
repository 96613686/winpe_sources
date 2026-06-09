# std::_Char_traits<ushort,ushort>::copy(ushort * const,ushort const * const,unsigned __int64)

- ea: `0x14000f27c`
- end: `0x14000f296`
- name: `?copy@?$_Char_traits@GG@std@@SAPEAGQEAGQEBG_K@Z`
- size: `26`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x14000f5c8`

## callees

- `0x140006965`

## pseudocode

```c
void *__fastcall std::_Char_traits<unsigned short,unsigned short>::copy(void *a1, const void *a2, __int64 a3)
{
  memcpy_0(a1, a2, 2 * a3);
  return a1;
}

```

## disassembly

```asm
0x14000f27c  push    rbx
0x14000f27e  sub     rsp, 20h
0x14000f282  add     r8, r8; Size
0x14000f285  mov     rbx, rcx
0x14000f288  call    memcpy_0
0x14000f28d  mov     rax, rbx
0x14000f290  add     rsp, 20h
0x14000f294  pop     rbx
0x14000f295  retn
```
