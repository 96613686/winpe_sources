# std::_Tree<std::_Tmap_traits<ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,stringCompare,std::allocator<std::pair<ushort const * const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,0>>::~_Tree<std::_Tmap_traits<ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,stringCompare,std::allocator<std::pair<ushort const * const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,0>>(void)

- ea: `0x180006308`
- end: `0x180006373`
- name: `??1?$_Tree@V?$_Tmap_traits@PEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UstringCompare@@V?$allocator@U?$pair@QEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ`
- size: `107`
- prototype: `void __fastcall(void **)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180006454`
- `0x180006518`

## callees

- `0x1800020a8`
- `0x1800060e4`
- `0x180006308`
- `0x18000637c`

## pseudocode

```c
void __fastcall std::_Tree<std::_Tmap_traits<unsigned short const *,std::wstring,stringCompare,std::allocator<std::pair<unsigned short const * const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<unsigned short const *,std::wstring,stringCompare,std::allocator<std::pair<unsigned short const * const,std::wstring>>,0>>(
        void **a1)
{
  _QWORD *v2; // rdi
  _QWORD *v3; // rcx
  void *v4; // rbx

  v2 = (_QWORD *)*((_QWORD *)*a1 + 1);
  while ( !*((_BYTE *)v2 + 25) )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned short const * const,std::wstring>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned short const * const,std::wstring>,void *>>>(
      a1,
      a1,
      v2[2]);
    v3 = v2;
    v4 = v2;
    v2 = (_QWORD *)*v2;
    std::wstring::~wstring(v3 + 5);
    operator delete(v4, (const struct std::nothrow_t *)0x48);
  }
  operator delete(*a1, (const struct std::nothrow_t *)0x48);
}

```

## disassembly

```asm
0x180006308  mov     [rsp+arg_0], rbx
0x18000630d  mov     [rsp+arg_8], rsi
0x180006312  push    rdi
0x180006313  sub     rsp, 20h
0x180006317  mov     rax, [rcx]
0x18000631a  mov     rsi, rcx
0x18000631d  mov     rdi, [rax+8]
0x180006321  jmp     short loc_180006351
0x180006323  mov     r8, [rdi+10h]
0x180006327  mov     rdx, rsi
0x18000632a  mov     rcx, rsi
0x18000632d  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@QEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@QEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@QEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ushort const * const,std::wstring>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<ushort const * const,std::wstring>,void *>>>(std::allocator<std::_Tree_node<std::pair<ushort const * const,std::wstring>,void *>> &,std::_Tree_node<std::pair<ushort const * const,std::wstring>,void *> *)
0x180006332  mov     rcx, rdi
0x180006335  mov     rbx, rdi
0x180006338  mov     rdi, [rdi]
0x18000633b  add     rcx, 28h ; '('
0x18000633f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180006344  mov     edx, 48h ; 'H'; struct std::nothrow_t *
0x180006349  mov     rcx, rbx; void *
0x18000634c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006351  cmp     byte ptr [rdi+19h], 0
0x180006355  jz      short loc_180006323
0x180006357  mov     rcx, [rsi]; void *
0x18000635a  mov     edx, 48h ; 'H'; struct std::nothrow_t *
0x18000635f  mov     rbx, [rsp+28h+arg_0]
0x180006364  mov     rsi, [rsp+28h+arg_8]
0x180006369  add     rsp, 20h
0x18000636d  pop     rdi
0x18000636e  jmp     ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
```
