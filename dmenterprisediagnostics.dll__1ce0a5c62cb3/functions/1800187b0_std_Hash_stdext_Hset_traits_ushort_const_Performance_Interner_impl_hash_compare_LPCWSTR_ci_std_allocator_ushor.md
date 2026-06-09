# std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::~_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>(void)

- ea: `0x1800187b0`
- end: `0x180018806`
- name: `??1?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@QEAA@XZ`
- size: `86`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001874c`

## callees

- `0x1800035c4`
- `0x1800182ec`
- `0x1800187b0`

## pseudocode

```c
void __fastcall std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::~_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>(
        __int64 a1)
{
  void *v2; // rcx

  v2 = *(void **)(a1 + 24);
  if ( v2 )
  {
    std::_Deallocate<16>(v2, (*(_QWORD *)(a1 + 40) - (_QWORD)v2) & 0xFFFFFFFFFFFFFFF8uLL);
    *(_QWORD *)(a1 + 24) = 0;
    *(_QWORD *)(a1 + 32) = 0;
    *(_QWORD *)(a1 + 40) = 0;
  }
  std::_List_node<unsigned short const *,void *>::_Free_non_head<std::allocator<std::_List_node<unsigned short const *,void *>>>(
    v2,
    *(_QWORD *)(a1 + 8));
  std::_Deallocate<16>(*(void **)(a1 + 8), 0x18u);
}

```

## disassembly

```asm
0x1800187b0  push    rbx
0x1800187b2  sub     rsp, 20h
0x1800187b6  mov     rbx, rcx
0x1800187b9  mov     rcx, [rcx+18h]
0x1800187bd  test    rcx, rcx
0x1800187c0  jz      short loc_1800187EA
0x1800187c2  mov     rdx, [rbx+28h]
0x1800187c6  sub     rdx, rcx
0x1800187c9  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1800187cd  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800187d2  mov     qword ptr [rbx+18h], 0
0x1800187da  mov     qword ptr [rbx+20h], 0
0x1800187e2  mov     qword ptr [rbx+28h], 0
0x1800187ea  mov     rdx, [rbx+8]
0x1800187ee  call    ??$_Free_non_head@V?$allocator@U?$_List_node@PEBGPEAX@std@@@std@@@?$_List_node@PEBGPEAX@std@@SAXAEAV?$allocator@U?$_List_node@PEBGPEAX@std@@@1@PEAU01@@Z; std::_List_node<ushort const *,void *>::_Free_non_head<std::allocator<std::_List_node<ushort const *,void *>>>(std::allocator<std::_List_node<ushort const *,void *>> &,std::_List_node<ushort const *,void *> *)
0x1800187f3  mov     rcx, [rbx+8]
0x1800187f7  mov     edx, 18h
0x1800187fc  add     rsp, 20h
0x180018800  pop     rbx
0x180018801  jmp     ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
```
