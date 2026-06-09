# std::_Tree_val<std::_Tree_simple_types<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *>>::_Erase_tree<std::allocator<std::_Tree_node<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,void *>>>(std::allocator<std::_Tree_node<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,void *>> &,std::_Tree_node<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,void *> *)

- ea: `0x140004f34`
- end: `0x140004f88`
- name: `??$_Erase_tree@V?$allocator@U?$_Tree_node@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU?$_Tree_node@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@1@@Z`
- size: `84`
- prototype: `void __fastcall(__int64, __int64, __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140004f34`
- `0x1400059b4`
- `0x140005bd0`
- `0x1400082d0`
- `0x140008a38`
- `0x14000b144`

## callees

- `0x140001cb8`
- `0x140004f34`

## pseudocode

```c
void __fastcall std::_Tree_val<std::_Tree_simple_types<std::wstring *>>::_Erase_tree<std::allocator<std::_Tree_node<std::wstring *,void *>>>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  _QWORD *v3; // rbx
  void *v6; // rcx

  v3 = (_QWORD *)a3;
  if ( !*(_BYTE *)(a3 + 25) )
  {
    do
    {
      std::_Tree_val<std::_Tree_simple_types<std::wstring *>>::_Erase_tree<std::allocator<std::_Tree_node<std::wstring *,void *>>>(
        a1,
        a2,
        v3[2]);
      v6 = v3;
      v3 = (_QWORD *)*v3;
      operator delete(v6, (const struct std::nothrow_t *)0x28);
    }
    while ( !*((_BYTE *)v3 + 25) );
  }
}

```

## disassembly

```asm
0x140004f34  mov     [rsp+arg_0], rbx
0x140004f39  mov     [rsp+arg_8], rsi
0x140004f3e  push    rdi
0x140004f3f  sub     rsp, 20h
0x140004f43  cmp     byte ptr [r8+19h], 0
0x140004f48  mov     rbx, r8
0x140004f4b  mov     rdi, rdx
0x140004f4e  mov     rsi, rcx
0x140004f51  jnz     short loc_140004F78
0x140004f53  mov     r8, [rbx+10h]
0x140004f57  mov     rdx, rdi
0x140004f5a  mov     rcx, rsi
0x140004f5d  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU?$_Tree_node@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::wstring *>>::_Erase_tree<std::allocator<std::_Tree_node<std::wstring *,void *>>>(std::allocator<std::_Tree_node<std::wstring *,void *>> &,std::_Tree_node<std::wstring *,void *> *)
0x140004f62  mov     rcx, rbx; void *
0x140004f65  mov     edx, 28h ; '('; struct std::nothrow_t *
0x140004f6a  mov     rbx, [rbx]
0x140004f6d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140004f72  cmp     byte ptr [rbx+19h], 0
0x140004f76  jz      short loc_140004F53
0x140004f78  mov     rbx, [rsp+28h+arg_0]
0x140004f7d  mov     rsi, [rsp+28h+arg_8]
0x140004f82  add     rsp, 20h
0x140004f86  pop     rdi
0x140004f87  retn
```
