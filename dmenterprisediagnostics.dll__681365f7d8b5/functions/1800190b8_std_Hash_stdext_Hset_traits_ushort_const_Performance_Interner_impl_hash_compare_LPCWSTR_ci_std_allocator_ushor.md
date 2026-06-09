# std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::~_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>(void)

- ea: `0x1800190b8`
- end: `0x18001910e`
- name: `??1?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@QEAA@XZ`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180019054`

## callees

- `0x180003618`
- `0x180018c9c`
- `0x1800190b8`

## pseudocode

```c
__int64 __fastcall std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::~_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>(
        _QWORD *a1)
{
  __int64 v2; // rcx

  v2 = a1[3];
  if ( v2 )
  {
    std::_Deallocate<16>(v2, (a1[5] - v2) & 0xFFFFFFFFFFFFFFF8uLL);
    a1[3] = 0;
    a1[4] = 0;
    a1[5] = 0;
  }
  std::_List_node<unsigned short const *,void *>::_Free_non_head<std::allocator<std::_List_node<unsigned short const *,void *>>>(
    v2,
    a1[1]);
  return std::_Deallocate<16>(a1[1], 24);
}

```

## disassembly

```asm
0x1800190b8  push    rbx
0x1800190ba  sub     rsp, 20h
0x1800190be  mov     rbx, rcx
0x1800190c1  mov     rcx, [rcx+18h]
0x1800190c5  test    rcx, rcx
0x1800190c8  jz      short loc_1800190F2
0x1800190ca  mov     rdx, [rbx+28h]
0x1800190ce  sub     rdx, rcx
0x1800190d1  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1800190d5  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800190da  mov     qword ptr [rbx+18h], 0
0x1800190e2  mov     qword ptr [rbx+20h], 0
0x1800190ea  mov     qword ptr [rbx+28h], 0
0x1800190f2  mov     rdx, [rbx+8]
0x1800190f6  call    ??$_Free_non_head@V?$allocator@U?$_List_node@PEBGPEAX@std@@@std@@@?$_List_node@PEBGPEAX@std@@SAXAEAV?$allocator@U?$_List_node@PEBGPEAX@std@@@1@PEAU01@@Z; std::_List_node<ushort const *,void *>::_Free_non_head<std::allocator<std::_List_node<ushort const *,void *>>>(std::allocator<std::_List_node<ushort const *,void *>> &,std::_List_node<ushort const *,void *> *)
0x1800190fb  mov     rcx, [rbx+8]
0x1800190ff  mov     edx, 18h
0x180019104  add     rsp, 20h
0x180019108  pop     rbx
0x180019109  jmp     ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
```
