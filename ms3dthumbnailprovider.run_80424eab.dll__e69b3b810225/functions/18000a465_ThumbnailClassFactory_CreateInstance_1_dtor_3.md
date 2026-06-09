# _ThumbnailClassFactory::CreateInstance_::_1_::dtor$3

- ea: `0x18000a465`
- end: `0x18000a481`
- name: `_ThumbnailClassFactory::CreateInstance_::_1_::dtor$3`
- size: `28`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002c10`

## pseudocode

```c
void ThumbnailClassFactory::CreateInstance_::_1_::dtor_3()
{
  ;
}

```

## disassembly

```asm
0x18000a465  push    rbp
0x18000a467  sub     rsp, 20h
0x18000a46b  mov     rbp, rdx
0x18000a46e  mov     rdx, [rbp+30h]
0x18000a472  mov     rcx, [rbp+38h]
0x18000a476  call    _guard_check_icall_nop
0x18000a47b  add     rsp, 20h
0x18000a47f  pop     rbp
0x18000a480  retn
```
