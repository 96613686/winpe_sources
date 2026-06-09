# std::_Uninit_copy<std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar *,std::allocator<uchar>>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar *,std::_Wrap_alloc<std::allocator<uchar>> &,std::_Nonscalar_ptr_iterator_tag)

- ea: `0x18000c28c`
- end: `0x18000c2ab`
- name: `??$_Uninit_copy@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@std@@PEAEV?$allocator@E@2@@std@@YAPEAEV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@0@0PEAEAEAU?$_Wrap_alloc@V?$allocator@E@std@@@0@U_Nonscalar_ptr_iterator_tag@0@@Z`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c5d0`

## callees

- `0x18000c28c`

## pseudocode

```c
_BYTE *__fastcall std::_Uninit_copy<std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<unsigned char>>>,unsigned char *,std::allocator<unsigned char>>(
        _BYTE *a1,
        _BYTE *a2,
        _BYTE *a3)
{
  while ( a1 != a2 )
    *a3++ = *a1++;
  return a3;
}

```

## disassembly

```asm
0x18000c28c  sub     rsp, 28h
0x18000c290  cmp     rcx, rdx
0x18000c293  jz      short loc_18000C2A2
0x18000c295  mov     al, [rcx]
0x18000c297  mov     [r8], al
0x18000c29a  inc     r8
0x18000c29d  inc     rcx
0x18000c2a0  jmp     short loc_18000C290
0x18000c2a2  mov     rax, r8
0x18000c2a5  add     rsp, 28h
0x18000c2a9  retn
```
