# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ulong,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,ulong>>,0>>::~_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ulong,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,ulong>>,0>>(void)

- ea: `0x18000b070`
- end: `0x18000b0c6`
- name: `??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@QEAA@XZ`
- size: `86`
- prototype: `void __fastcall(__int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000b3fc`
- `0x18000dd10`
- `0x18000f49c`

## callees

- `0x180003c34`
- `0x180009fb8`
- `0x18000b070`

## pseudocode

```c
void __fastcall std::_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::~_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>(
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
  std::_List_node<std::pair<std::wstring const,unsigned long>,void *>::_Free_non_head<std::allocator<std::_List_node<std::pair<std::wstring const,unsigned long>,void *>>>(
    v2,
    *(_QWORD *)(a1 + 8));
  std::_Deallocate<16>(*(void **)(a1 + 8), 0x38u);
}

```

## disassembly

```asm
0x18000b070  push    rbx
0x18000b072  sub     rsp, 20h
0x18000b076  mov     rbx, rcx
0x18000b079  mov     rcx, [rcx+18h]
0x18000b07d  test    rcx, rcx
0x18000b080  jz      short loc_18000B0AA
0x18000b082  mov     rdx, [rbx+28h]
0x18000b086  sub     rdx, rcx
0x18000b089  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18000b08d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000b092  mov     qword ptr [rbx+18h], 0
0x18000b09a  mov     qword ptr [rbx+20h], 0
0x18000b0a2  mov     qword ptr [rbx+28h], 0
0x18000b0aa  mov     rdx, [rbx+8]
0x18000b0ae  call    ??$_Free_non_head@V?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@PEAX@std@@@std@@@?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::pair<std::wstring const,ulong>,void *>::_Free_non_head<std::allocator<std::_List_node<std::pair<std::wstring const,ulong>,void *>>>(std::allocator<std::_List_node<std::pair<std::wstring const,ulong>,void *>> &,std::_List_node<std::pair<std::wstring const,ulong>,void *> *)
0x18000b0b3  mov     rcx, [rbx+8]
0x18000b0b7  mov     edx, 38h ; '8'
0x18000b0bc  add     rsp, 20h
0x18000b0c0  pop     rbx
0x18000b0c1  jmp     ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
```
