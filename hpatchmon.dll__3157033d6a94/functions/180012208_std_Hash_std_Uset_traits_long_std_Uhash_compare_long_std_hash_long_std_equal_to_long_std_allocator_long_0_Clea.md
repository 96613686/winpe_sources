# std::_Hash<std::_Uset_traits<long,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<long>,0>>::_Clear_guard::~_Clear_guard(void)

- ea: `0x180012208`
- end: `0x1800122be`
- name: `??1_Clear_guard@?$_Hash@V?$_Uset_traits@JV?$_Uhash_compare@JU?$hash@J@std@@U?$equal_to@J@2@@std@@V?$allocator@J@2@$0A@@std@@@std@@QEAA@XZ`
- size: `182`
- prototype: `void __fastcall(unsigned __int64 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001346c`

## callees

- `0x180002c8c`
- `0x180012208`
- `0x1800136bc`

## pseudocode

```c
void __fastcall std::_Hash<std::_Uset_traits<long,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<long>,0>>::_Clear_guard::~_Clear_guard(
        unsigned __int64 **a1)
{
  unsigned __int64 *v1; // rbx
  unsigned __int64 v2; // rcx
  _QWORD *v3; // rcx
  _QWORD *v4; // rdi
  void *v5; // rdi
  unsigned __int64 v6; // rcx

  v1 = *a1;
  if ( *a1 && v1[2] )
  {
    v2 = v1[1];
    if ( v1[7] >> 3 <= v1[2] )
    {
      **(_QWORD **)(v2 + 8) = 0;
      v3 = *(_QWORD **)v2;
      if ( v3 )
      {
        do
        {
          v4 = (_QWORD *)*v3;
          operator delete(v3, 0x18u);
          v3 = v4;
        }
        while ( v4 );
      }
      *(_QWORD *)v1[1] = v1[1];
      *(_QWORD *)(v1[1] + 8) = v1[1];
      v1[2] = 0;
      v5 = (void *)v1[3];
      v6 = (v1[4] - (unsigned __int64)v5 + 7) >> 3;
      if ( (unsigned __int64)v5 > v1[4] )
        v6 = 0;
      if ( v6 )
        memset64(v5, v1[1], v6);
    }
    else
    {
      std::_Hash<std::_Uset_traits<long,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<long>,0>>::_Unchecked_erase(
        v1,
        *(_QWORD *)v2,
        v1[1]);
    }
  }
}

```

## disassembly

```asm
0x180012208  mov     [rsp+arg_0], rbx
0x18001220d  push    rdi
0x18001220e  sub     rsp, 20h
0x180012212  mov     rbx, [rcx]
0x180012215  test    rbx, rbx
0x180012218  jz      loc_1800122B3
0x18001221e  cmp     qword ptr [rbx+10h], 0
0x180012223  jz      loc_1800122B3
0x180012229  mov     rax, [rbx+38h]
0x18001222d  mov     rcx, [rbx+8]
0x180012231  shr     rax, 3
0x180012235  cmp     rax, [rbx+10h]
0x180012239  jbe     short loc_18001224B
0x18001223b  mov     rdx, [rcx]
0x18001223e  mov     r8, rcx
0x180012241  mov     rcx, rbx
0x180012244  call    ?_Unchecked_erase@?$_Hash@V?$_Uset_traits@JV?$_Uhash_compare@JU?$hash@J@std@@U?$equal_to@J@2@@std@@V?$allocator@J@2@$0A@@std@@@std@@AEAAPEAU?$_List_node@JPEAX@2@PEAU32@QEAU32@@Z; std::_Hash<std::_Uset_traits<long,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<long>,0>>::_Unchecked_erase(std::_List_node<long,void *> *,std::_List_node<long,void *> * const)
0x180012249  jmp     short loc_1800122B3
0x18001224b  mov     rax, [rcx+8]
0x18001224f  mov     qword ptr [rax], 0
0x180012256  mov     rcx, [rcx]; void *
0x180012259  test    rcx, rcx
0x18001225c  jz      short loc_180012273
0x18001225e  mov     rdi, [rcx]
0x180012261  mov     edx, 18h; unsigned __int64
0x180012266  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001226b  mov     rcx, rdi
0x18001226e  test    rdi, rdi
0x180012271  jnz     short loc_18001225E
0x180012273  mov     rax, [rbx+8]
0x180012277  xor     edx, edx
0x180012279  mov     [rax], rax
0x18001227c  mov     rax, [rbx+8]
0x180012280  mov     [rax+8], rax
0x180012284  mov     qword ptr [rbx+10h], 0
0x18001228c  mov     rdi, [rbx+18h]
0x180012290  mov     rcx, [rbx+20h]
0x180012294  sub     rcx, rdi
0x180012297  add     rcx, 7
0x18001229b  shr     rcx, 3
0x18001229f  cmp     rdi, [rbx+20h]
0x1800122a3  cmova   rcx, rdx
0x1800122a7  test    rcx, rcx
0x1800122aa  jz      short loc_1800122B3
0x1800122ac  mov     rax, [rbx+8]
0x1800122b0  rep stosq
0x1800122b3  mov     rbx, [rsp+28h+arg_0]
0x1800122b8  add     rsp, 20h
0x1800122bc  pop     rdi
0x1800122bd  retn
```
