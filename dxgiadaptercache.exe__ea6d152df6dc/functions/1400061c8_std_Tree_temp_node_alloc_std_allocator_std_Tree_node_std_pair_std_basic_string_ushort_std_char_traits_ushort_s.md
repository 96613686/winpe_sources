# std::_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,CachedAdapterInformation>,void *>>>::~_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,CachedAdapterInformation>,void *>>>(void)

- ea: `0x1400061c8`
- end: `0x1400061e4`
- name: `??1?$_Tree_temp_node_alloc@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCachedAdapterInformation@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `28`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140011558`

## callees

- `0x140002578`
- `0x1400061c8`

## pseudocode

```c
void __fastcall std::_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::pair<std::wstring const,CachedAdapterInformation>,void *>>>::~_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::pair<std::wstring const,CachedAdapterInformation>,void *>>>(
        __int64 a1)
{
  void *v1; // rcx

  v1 = *(void **)(a1 + 8);
  if ( v1 )
    operator delete(v1, 0xA8u);
}

```

## disassembly

```asm
0x1400061c8  sub     rsp, 28h
0x1400061cc  mov     rcx, [rcx+8]; void *
0x1400061d0  test    rcx, rcx
0x1400061d3  jz      short loc_1400061DF
0x1400061d5  mov     edx, 0A8h; unsigned __int64
0x1400061da  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400061df  add     rsp, 28h
0x1400061e3  retn
```
