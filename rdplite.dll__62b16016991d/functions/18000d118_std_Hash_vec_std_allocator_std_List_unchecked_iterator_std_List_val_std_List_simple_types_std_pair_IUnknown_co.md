# std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<IUnknown * const,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<IUnknown * const,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>>>>>)

- ea: `0x18000d118`
- end: `0x18000d1a5`
- name: `?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAUIUnknown@@U?$pair@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@PEAX@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAUIUnknown@@U?$pair@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@PEAX@std@@@std@@@std@@@std@@@2@@Z`
- size: `141`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a4d8`
- `0x18000d3a8`
- `0x18001c780`
- `0x18001c914`
- `0x18001f034`
- `0x18001ff30`
- `0x180020004`
- `0x180022b20`
- `0x180022c98`

## callees

- `0x180004958`
- `0x1800049b8`
- `0x180009d6c`
- `0x180009f64`
- `0x18000d118`

## pseudocode

```c
__int64 __fastcall std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<IUnknown * const,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>>>>>>>::_Assign_grow(
        _QWORD *a1,
        unsigned __int64 a2,
        __int64 a3)
{
  __int64 size_of; // rax
  _QWORD *v7; // rdi
  __int64 v8; // rdx
  __int64 result; // rax
  __int64 v10; // [rsp+60h] [rbp+18h] BYREF

  v10 = a3;
  if ( (__int64)(a1[1] - *a1) >> 3 >= a2 )
    return std::fill<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,void *>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,void *>>>>>(
             *a1,
             a1[1],
             &v10);
  size_of = std::_Get_size_of_n<8>(a2);
  v7 = (_QWORD *)std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  v8 = (__int64)(a1[2] - *a1) >> 3;
  if ( v8 )
    std::_Deallocate<16>(*a1, 8 * v8);
  result = (__int64)&v7[a2];
  *a1 = v7;
  a1[1] = result;
  a1[2] = result;
  while ( v7 != (_QWORD *)result )
    *v7++ = a3;
  return result;
}

```

## disassembly

```asm
0x18000d118  mov     [rsp+arg_10], r8
0x18000d11d  push    rbx
0x18000d11e  push    rbp
0x18000d11f  push    rsi
0x18000d120  push    rdi
0x18000d121  sub     rsp, 28h
0x18000d125  mov     rbp, rdx
0x18000d128  mov     rbx, r8
0x18000d12b  mov     rdx, [rcx+8]
0x18000d12f  mov     rsi, rcx
0x18000d132  mov     rax, rdx
0x18000d135  sub     rax, [rcx]
0x18000d138  sar     rax, 3
0x18000d13c  cmp     rax, rbp
0x18000d13f  jnb     short loc_18000D18F
0x18000d141  mov     rcx, rbp
0x18000d144  call    ??$_Get_size_of_n@$07@std@@YA_K_K@Z; std::_Get_size_of_n<8>(unsigned __int64)
0x18000d149  mov     rcx, rax
0x18000d14c  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000d151  mov     rdx, [rsi+10h]
0x18000d155  mov     rdi, rax
0x18000d158  sub     rdx, [rsi]
0x18000d15b  sar     rdx, 3
0x18000d15f  test    rdx, rdx
0x18000d162  jz      short loc_18000D170
0x18000d164  mov     rcx, [rsi]
0x18000d167  shl     rdx, 3
0x18000d16b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000d170  lea     rax, [rdi+rbp*8]
0x18000d174  mov     [rsi], rdi
0x18000d177  mov     [rsi+8], rax
0x18000d17b  mov     [rsi+10h], rax
0x18000d17f  jmp     short loc_18000D188
0x18000d181  mov     [rdi], rbx
0x18000d184  add     rdi, 8
0x18000d188  cmp     rdi, rax
0x18000d18b  jnz     short loc_18000D181
0x18000d18d  jmp     short loc_18000D19C
0x18000d18f  mov     rcx, [rcx]
0x18000d192  lea     r8, [rsp+48h+arg_10]
0x18000d197  call    ??$fill@PEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@PEAX@std@@@std@@@std@@@std@@V12@@std@@YAXQEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@PEAX@std@@@std@@@std@@@0@0AEBV10@@Z; std::fill<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,void *>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,void *>>>>>(std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,void *>>>> * const,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,void *>>>> * const,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,void *>>>> const &)
0x18000d19c  add     rsp, 28h
0x18000d1a0  pop     rdi
0x18000d1a1  pop     rsi
0x18000d1a2  pop     rbp
0x18000d1a3  pop     rbx
0x18000d1a4  retn
```
