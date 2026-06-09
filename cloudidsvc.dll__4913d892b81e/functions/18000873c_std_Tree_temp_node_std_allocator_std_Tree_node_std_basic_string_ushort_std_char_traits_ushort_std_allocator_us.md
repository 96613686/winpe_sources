# std::_Tree_temp_node<std::allocator<std::_Tree_node<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,void *>>>(std::allocator<std::_Tree_node<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,void *>> &,std::_Tree_node<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,void *> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18000873c`
- end: `0x1800087c0`
- name: `??$?0AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree_temp_node@V?$allocator@U?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@std@@QEAA@AEAV?$allocator@U?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z`
- size: `132`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180009514`
- `0x18000d218`

## callees

- `0x18000873c`
- `0x180009004`
- `0x1800099c4`
- `0x180009d28`

## pseudocode

```c
__int64 __fastcall std::_Tree_temp_node<std::allocator<std::_Tree_node<std::wstring,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::wstring,void *>>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v6; // rcx
  __int64 i; // rcx
  __int64 v9; // [rsp+40h] [rbp+18h] BYREF

  v9 = a3;
  std::_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::wstring,void *>>>::_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::wstring,void *>>>();
  std::_Default_allocator_traits<std::allocator<std::_Tree_node<std::wstring,void *>>>::construct<std::wstring,std::wstring const &>(
    v6,
    *(_QWORD *)(a1 + 8) + 32LL,
    a4);
  std::_Construct_in_place<std::_Tree_node<std::wstring,void *> *,std::_Tree_node<std::wstring,void *> * &>(
    *(_QWORD *)(a1 + 8),
    &v9);
  std::_Construct_in_place<std::_Tree_node<std::wstring,void *> *,std::_Tree_node<std::wstring,void *> * &>(
    *(_QWORD *)(a1 + 8) + 8LL,
    &v9);
  std::_Construct_in_place<std::_Tree_node<std::wstring,void *> *,std::_Tree_node<std::wstring,void *> * &>(
    *(_QWORD *)(a1 + 8) + 16LL,
    &v9);
  for ( i = 0; i != 2; ++i )
    *(_BYTE *)(*(_QWORD *)(a1 + 8) + i + 24) = 0;
  return a1;
}

```

## disassembly

```asm
0x18000873c  mov     [rsp+arg_8], rbx
0x180008741  mov     [rsp+arg_10], r8
0x180008746  mov     [rsp+arg_0], rcx
0x18000874b  push    rdi
0x18000874c  sub     rsp, 20h
0x180008750  mov     rbx, r9
0x180008753  mov     rdi, rcx
0x180008756  call    ??0?$_Tree_temp_node_alloc@V?$allocator@U?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@std@@QEAA@AEAV?$allocator@U?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@@Z; std::_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::wstring,void *>>>::_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::wstring,void *>>>(std::allocator<std::_Tree_node<std::wstring,void *>> &)
0x18000875b  nop
0x18000875c  mov     rdx, [rdi+8]
0x180008760  add     rdx, 20h ; ' '
0x180008764  mov     r8, rbx
0x180008767  call    ??$construct@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@@?$_Default_allocator_traits@V?$allocator@U?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@std@@SAXAEAV?$allocator@U?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBV31@@Z; std::_Default_allocator_traits<std::allocator<std::_Tree_node<std::wstring,void *>>>::construct<std::wstring,std::wstring const &>(std::allocator<std::_Tree_node<std::wstring,void *>> &,std::wstring * const,std::wstring const &)
0x18000876c  lea     rdx, [rsp+28h+arg_10]
0x180008771  mov     rcx, [rdi+8]
0x180008775  call    ??$_Construct_in_place@PEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<std::wstring,void *> *,std::_Tree_node<std::wstring,void *> * &>(std::_Tree_node<std::wstring,void *> * &,std::_Tree_node<std::wstring,void *> * &)
0x18000877a  mov     rcx, [rdi+8]
0x18000877e  add     rcx, 8
0x180008782  lea     rdx, [rsp+28h+arg_10]
0x180008787  call    ??$_Construct_in_place@PEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<std::wstring,void *> *,std::_Tree_node<std::wstring,void *> * &>(std::_Tree_node<std::wstring,void *> * &,std::_Tree_node<std::wstring,void *> * &)
0x18000878c  mov     rcx, [rdi+8]
0x180008790  add     rcx, 10h
0x180008794  lea     rdx, [rsp+28h+arg_10]
0x180008799  call    ??$_Construct_in_place@PEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<std::wstring,void *> *,std::_Tree_node<std::wstring,void *> * &>(std::_Tree_node<std::wstring,void *> * &,std::_Tree_node<std::wstring,void *> * &)
0x18000879e  xor     ecx, ecx
0x1800087a0  mov     rax, [rdi+8]
0x1800087a4  mov     byte ptr [rax+rcx+18h], 0
0x1800087a9  inc     rcx
0x1800087ac  cmp     rcx, 2
0x1800087b0  jnz     short loc_1800087A0
0x1800087b2  mov     rax, rdi
0x1800087b5  mov     rbx, [rsp+28h+arg_8]
0x1800087ba  add     rsp, 20h
0x1800087be  pop     rdi
0x1800087bf  retn
```
