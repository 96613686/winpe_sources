# std::_Tree_temp_node<std::allocator<std::_Tree_node<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,void *>>>(void)

- ea: `0x18000a700`
- end: `0x18000a728`
- name: `??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `40`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180009048`
- `0x180009514`
- `0x18000d218`

## callees

- `0x18000a594`
- `0x18000a700`
- `0x18000c498`

## pseudocode

```c
__int64 __fastcall std::_Tree_temp_node<std::allocator<std::_Tree_node<std::wstring,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::wstring,void *>>>(
        __int64 a1)
{
  __int64 v2; // rcx

  v2 = *(_QWORD *)(a1 + 8);
  if ( v2 )
    std::wstring::_Tidy_deallocate(v2 + 32);
  return std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::wstring,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::wstring,void *>>>(a1);
}

```

## disassembly

```asm
0x18000a700  push    rbx
0x18000a702  sub     rsp, 20h
0x18000a706  mov     rbx, rcx
0x18000a709  mov     rcx, [rcx+8]
0x18000a70d  test    rcx, rcx
0x18000a710  jz      short loc_18000A71B
0x18000a712  add     rcx, 20h ; ' '
0x18000a716  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000a71b  mov     rcx, rbx
0x18000a71e  add     rsp, 20h
0x18000a722  pop     rbx
0x18000a723  jmp     ??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::wstring,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::wstring,void *>>>(void)
```
