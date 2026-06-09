# std::_Tree<std::_Tmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,0>>::~_Tree<std::_Tmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,0>>(void)

- ea: `0x1800076a4`
- end: `0x18000770b`
- name: `??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ`
- size: `103`
- prototype: `void __fastcall(void **)`
- caller_count: `10`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000778c`
- `0x180007840`
- `0x180007890`
- `0x1800081e0`
- `0x180008940`
- `0x18000c718`
- `0x18000c740`
- `0x18000ca90`
- `0x18000cb50`
- `0x180010864`

## callees

- `0x1800026b0`
- `0x18000763c`
- `0x1800076a4`
- `0x180007720`

## pseudocode

```c
void __fastcall std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(
        void **a1)
{
  __int64 *v2; // r14
  __int64 *v3; // rdi

  v2 = (__int64 *)*((_QWORD *)*a1 + 1);
  while ( !*((_BYTE *)v2 + 25) )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
      (__int64)a1,
      (__int64)a1,
      (__int64 *)v2[2]);
    v3 = v2;
    v2 = (__int64 *)*v2;
    std::wstring::~wstring(v3 + 8);
    std::wstring::~wstring(v3 + 4);
    operator delete(v3, (const struct std::nothrow_t *)0x60);
  }
  operator delete(*a1, (const struct std::nothrow_t *)0x60);
}

```

## disassembly

```asm
0x1800076a4  push    rbx
0x1800076a6  push    rsi
0x1800076a7  push    rdi
0x1800076a8  push    r14
0x1800076aa  sub     rsp, 28h
0x1800076ae  mov     rax, [rcx]
0x1800076b1  mov     rsi, rcx
0x1800076b4  mov     r14, [rax+8]
0x1800076b8  jmp     short loc_1800076EE
0x1800076ba  mov     r8, [r14+10h]
0x1800076be  mov     rdx, rsi
0x1800076c1  mov     rcx, rsi
0x1800076c4  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>> &,std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> *)
0x1800076c9  mov     rdi, r14
0x1800076cc  mov     r14, [r14]
0x1800076cf  lea     rcx, [rdi+40h]; void *
0x1800076d3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800076d8  lea     rcx, [rdi+20h]; void *
0x1800076dc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800076e1  mov     edx, 60h ; '`'; struct std::nothrow_t *
0x1800076e6  mov     rcx, rdi; void *
0x1800076e9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800076ee  cmp     byte ptr [r14+19h], 0
0x1800076f3  jz      short loc_1800076BA
0x1800076f5  mov     rcx, [rsi]; void *
0x1800076f8  mov     edx, 60h ; '`'; struct std::nothrow_t *
0x1800076fd  add     rsp, 28h
0x180007701  pop     r14
0x180007703  pop     rdi
0x180007704  pop     rsi
0x180007705  pop     rbx
0x180007706  jmp     ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
```
