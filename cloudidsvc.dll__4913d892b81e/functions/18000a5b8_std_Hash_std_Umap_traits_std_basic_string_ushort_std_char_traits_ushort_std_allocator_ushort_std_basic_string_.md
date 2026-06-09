# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,0>>::~_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,0>>(void)

- ea: `0x18000a5b8`
- end: `0x18000a60e`
- name: `??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ`
- size: `86`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000a8e0`
- `0x18000a93c`
- `0x18000b67c`

## callees

- `0x180009014`
- `0x180009484`
- `0x18000a5b8`

## pseudocode

```c
void __fastcall std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(
        _QWORD *a1)
{
  _QWORD *v2; // rcx

  v2 = (_QWORD *)a1[3];
  if ( v2 )
  {
    std::_Deallocate<16>(v2, (a1[5] - (_QWORD)v2) & 0xFFFFFFFFFFFFFFF8uLL);
    a1[3] = 0;
    a1[4] = 0;
    a1[5] = 0;
  }
  std::_List_node<std::pair<std::wstring const,std::wstring>,void *>::_Free_non_head<std::allocator<std::_List_node<std::pair<std::wstring const,std::wstring>,void *>>>(
    v2,
    a1[1]);
  std::_Deallocate<16>((_QWORD *)a1[1], 0x50u);
}

```

## disassembly

```asm
0x18000a5b8  push    rbx
0x18000a5ba  sub     rsp, 20h
0x18000a5be  mov     rbx, rcx
0x18000a5c1  mov     rcx, [rcx+18h]
0x18000a5c5  test    rcx, rcx
0x18000a5c8  jz      short loc_18000A5F2
0x18000a5ca  mov     rdx, [rbx+28h]
0x18000a5ce  sub     rdx, rcx
0x18000a5d1  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18000a5d5  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000a5da  mov     qword ptr [rbx+18h], 0
0x18000a5e2  mov     qword ptr [rbx+20h], 0
0x18000a5ea  mov     qword ptr [rbx+28h], 0
0x18000a5f2  mov     rdx, [rbx+8]
0x18000a5f6  call    ??$_Free_non_head@V?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@std@@@?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::pair<std::wstring const,std::wstring>,void *>::_Free_non_head<std::allocator<std::_List_node<std::pair<std::wstring const,std::wstring>,void *>>>(std::allocator<std::_List_node<std::pair<std::wstring const,std::wstring>,void *>> &,std::_List_node<std::pair<std::wstring const,std::wstring>,void *> *)
0x18000a5fb  mov     rcx, [rbx+8]
0x18000a5ff  mov     edx, 50h ; 'P'
0x18000a604  add     rsp, 20h
0x18000a608  pop     rbx
0x18000a609  jmp     ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
```
