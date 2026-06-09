# std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Clear_guard::~_Clear_guard(void)

- ea: `0x180018928`
- end: `0x18001897e`
- name: `??1_Clear_guard@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@QEAA@XZ`
- size: `86`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001a3c0`

## callees

- `0x1800182ec`
- `0x18001848c`
- `0x180018928`

## pseudocode

```c
__int64 __fastcall std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::_Clear_guard::~_Clear_guard(
        _QWORD *a1)
{
  _QWORD *v1; // rbx
  __int64 v2; // rdx
  __int64 v3; // rcx
  __int64 result; // rax
  __int64 v5; // [rsp+30h] [rbp+8h] BYREF

  v1 = (_QWORD *)*a1;
  if ( *a1 )
  {
    if ( v1[2] )
    {
      std::_List_node<unsigned short const *,void *>::_Free_non_head<std::allocator<std::_List_node<unsigned short const *,void *>>>(
        a1,
        v1[1]);
      *(_QWORD *)v1[1] = v1[1];
      *(_QWORD *)(v1[1] + 8LL) = v1[1];
      v1[2] = 0;
      v2 = v1[4];
      v3 = v1[3];
      v5 = v1[1];
      return std::fill<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned short const *>>,std::_Iterator_base0> *,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned short const *>>,std::_Iterator_base0>>(
               v3,
               v2,
               &v5);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180018928  push    rbx
0x18001892a  sub     rsp, 20h
0x18001892e  mov     rbx, [rcx]
0x180018931  test    rbx, rbx
0x180018934  jz      short loc_180018978
0x180018936  cmp     qword ptr [rbx+10h], 0
0x18001893b  jz      short loc_180018978
0x18001893d  mov     rdx, [rbx+8]
0x180018941  call    ??$_Free_non_head@V?$allocator@U?$_List_node@PEBGPEAX@std@@@std@@@?$_List_node@PEBGPEAX@std@@SAXAEAV?$allocator@U?$_List_node@PEBGPEAX@std@@@1@PEAU01@@Z; std::_List_node<ushort const *,void *>::_Free_non_head<std::allocator<std::_List_node<ushort const *,void *>>>(std::allocator<std::_List_node<ushort const *,void *>> &,std::_List_node<ushort const *,void *> *)
0x180018946  mov     rax, [rbx+8]
0x18001894a  lea     r8, [rsp+28h+arg_0]
0x18001894f  mov     [rax], rax
0x180018952  mov     rax, [rbx+8]
0x180018956  mov     [rax+8], rax
0x18001895a  mov     qword ptr [rbx+10h], 0
0x180018962  mov     rax, [rbx+8]
0x180018966  mov     rdx, [rbx+20h]
0x18001896a  mov     rcx, [rbx+18h]
0x18001896e  mov     [rsp+28h+arg_0], rax
0x180018973  call    ??$fill@PEAV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEBG@std@@@std@@U_Iterator_base0@2@@std@@V12@@std@@YAXQEAV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEBG@std@@@std@@U_Iterator_base0@2@@0@0AEBV10@@Z; std::fill<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ushort const *>>,std::_Iterator_base0> *,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ushort const *>>,std::_Iterator_base0>>(std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ushort const *>>,std::_Iterator_base0> * const,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ushort const *>>,std::_Iterator_base0> * const,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ushort const *>>,std::_Iterator_base0> const &)
0x180018978  add     rsp, 20h
0x18001897c  pop     rbx
0x18001897d  retn
```
