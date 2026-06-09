# std::_Uninit_move<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003 *,__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003 *,std::allocator<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003>,__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003>(__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003 *,__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003 *,__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003 *,std::_Wrap_alloc<std::allocator<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003>> &,__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003 *,std::_Nonscalar_ptr_iterator_tag)

- ea: `0x18000c490`
- end: `0x18000c4bc`
- name: `??$_Uninit_move@PEAU__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003@@PEAU1@V?$allocator@U__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003@@@std@@U1@@std@@YAPEAU__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003@@PEAU1@00AEAU?$_Wrap_alloc@V?$allocator@U__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z`
- size: `44`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180010e0c`

## callees

- `0x18000c490`

## pseudocode

```c
_OWORD *__fastcall std::_Uninit_move<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003 *,__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003 *,std::allocator<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003>,__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003>(
        _OWORD *a1,
        _OWORD *a2,
        _OWORD *a3)
{
  while ( a1 != a2 )
  {
    *a3 = *a1;
    a3[1] = a1[1];
    a3 += 2;
    a1 += 2;
  }
  return a3;
}

```

## disassembly

```asm
0x18000c490  sub     rsp, 28h
0x18000c494  jmp     short loc_18000C4AE
0x18000c496  movups  xmm0, xmmword ptr [rcx]
0x18000c499  movups  xmmword ptr [r8], xmm0
0x18000c49d  movups  xmm1, xmmword ptr [rcx+10h]
0x18000c4a1  movups  xmmword ptr [r8+10h], xmm1
0x18000c4a6  add     r8, 20h ; ' '
0x18000c4aa  add     rcx, 20h ; ' '
0x18000c4ae  cmp     rcx, rdx
0x18000c4b1  jnz     short loc_18000C496
0x18000c4b3  mov     rax, r8
0x18000c4b6  add     rsp, 28h
0x18000c4ba  retn
```
