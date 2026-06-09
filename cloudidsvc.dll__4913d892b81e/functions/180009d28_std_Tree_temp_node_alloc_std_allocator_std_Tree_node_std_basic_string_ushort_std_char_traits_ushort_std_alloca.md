# std::_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,void *>>>::_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,void *>>>(std::allocator<std::_Tree_node<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,void *>> &)

- ea: `0x180009d28`
- end: `0x180009d57`
- name: `??0?$_Tree_temp_node_alloc@V?$allocator@U?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@std@@QEAA@AEAV?$allocator@U?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@@Z`
- size: `47`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000873c`
- `0x180009048`

## callees

- `0x180008b7c`

## pseudocode

```c
_QWORD *__fastcall std::_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::wstring,void *>>>::_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::wstring,void *>>>(
        _QWORD *a1,
        __int64 a2)
{
  *a1 = a2;
  a1[1] = 0;
  a1[1] = std::_Allocate<16,std::_Default_allocate_traits>(0x40u);
  return a1;
}

```

## disassembly

```asm
0x180009d28  mov     [rsp+arg_0], rcx
0x180009d2d  push    rbx
0x180009d2e  sub     rsp, 20h
0x180009d32  mov     rbx, rcx
0x180009d35  mov     [rcx], rdx
0x180009d38  mov     qword ptr [rcx+8], 0
0x180009d40  mov     ecx, 40h ; '@'
0x180009d45  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180009d4a  mov     [rbx+8], rax
0x180009d4e  mov     rax, rbx
0x180009d51  add     rsp, 20h
0x180009d55  pop     rbx
0x180009d56  retn
```
