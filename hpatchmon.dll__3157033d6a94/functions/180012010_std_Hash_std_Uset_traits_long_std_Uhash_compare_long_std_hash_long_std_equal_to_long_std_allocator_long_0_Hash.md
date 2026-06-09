# std::_Hash<std::_Uset_traits<long,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<long>,0>>::~_Hash<std::_Uset_traits<long,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<long>,0>>(void)

- ea: `0x180012010`
- end: `0x18001206a`
- name: `??1?$_Hash@V?$_Uset_traits@JV?$_Uhash_compare@JU?$hash@J@std@@U?$equal_to@J@2@@std@@V?$allocator@J@2@$0A@@std@@@std@@QEAA@XZ`
- size: `90`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800143bc`

## callees

- `0x180002c8c`
- `0x180012010`
- `0x180012098`

## pseudocode

```c
void __fastcall std::_Hash<std::_Uset_traits<long,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<long>,0>>::~_Hash<std::_Uset_traits<long,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<long>,0>>(
        __int64 a1)
{
  _QWORD **v2; // rdx
  _QWORD *v3; // rcx
  _QWORD *v4; // rbx

  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>(a1 + 24);
  v2 = *(_QWORD ***)(a1 + 8);
  *v2[1] = 0;
  v3 = *v2;
  if ( *v2 )
  {
    do
    {
      v4 = (_QWORD *)*v3;
      operator delete(v3, 0x18u);
      v3 = v4;
    }
    while ( v4 );
  }
  operator delete(*(void **)(a1 + 8), 0x18u);
}

```

## disassembly

```asm
0x180012010  mov     [rsp+arg_0], rbx
0x180012015  push    rdi
0x180012016  sub     rsp, 20h
0x18001201a  mov     rdi, rcx
0x18001201d  add     rcx, 18h
0x180012021  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>(void)
0x180012026  mov     rdx, [rdi+8]
0x18001202a  mov     rax, [rdx+8]
0x18001202e  mov     qword ptr [rax], 0
0x180012035  mov     rcx, [rdx]; void *
0x180012038  test    rcx, rcx
0x18001203b  jz      short loc_180012052
0x18001203d  mov     rbx, [rcx]
0x180012040  mov     edx, 18h; unsigned __int64
0x180012045  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001204a  mov     rcx, rbx
0x18001204d  test    rbx, rbx
0x180012050  jnz     short loc_18001203D
0x180012052  mov     rcx, [rdi+8]; void *
0x180012056  mov     edx, 18h; unsigned __int64
0x18001205b  mov     rbx, [rsp+28h+arg_0]
0x180012060  add     rsp, 20h
0x180012064  pop     rdi
0x180012065  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
