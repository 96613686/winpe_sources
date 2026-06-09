# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ulong,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,ulong>>,0>>::_Range_eraser::_Bump_erased(void)

- ea: `0x18000fbac`
- end: `0x18000fbd2`
- name: `?_Bump_erased@_Range_eraser@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@QEAAXXZ`
- size: `38`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180010994`

## callees

- `0x18000a060`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::_Range_eraser::_Bump_erased(
        _QWORD *a1)
{
  __int64 result; // rax

  a1[2] = *(_QWORD *)a1[2];
  std::_List_node<std::pair<std::wstring const,unsigned long>,void *>::_Freenode<std::allocator<std::_List_node<std::pair<std::wstring const,unsigned long>,void *>>>();
  result = *a1;
  --*(_QWORD *)(*a1 + 8LL);
  return result;
}

```

## disassembly

```asm
0x18000fbac  push    rbx
0x18000fbae  sub     rsp, 20h
0x18000fbb2  mov     rdx, [rcx+10h]
0x18000fbb6  mov     rbx, rcx
0x18000fbb9  mov     rax, [rdx]
0x18000fbbc  mov     [rcx+10h], rax
0x18000fbc0  call    ??$_Freenode@V?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@PEAX@std@@@std@@@?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::pair<std::wstring const,ulong>,void *>::_Freenode<std::allocator<std::_List_node<std::pair<std::wstring const,ulong>,void *>>>(std::allocator<std::_List_node<std::pair<std::wstring const,ulong>,void *>> &,std::_List_node<std::pair<std::wstring const,ulong>,void *> *)
0x18000fbc5  mov     rax, [rbx]
0x18000fbc8  dec     qword ptr [rax+8]
0x18000fbcc  add     rsp, 20h
0x18000fbd0  pop     rbx
0x18000fbd1  retn
```
