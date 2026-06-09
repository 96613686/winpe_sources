# std::_Tree<std::_Tmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,CNDFHelperClass *,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,CNDFHelperClass *>>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,CNDFHelperClass *>>>>,std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,CNDFHelperClass *>>>>)

- ea: `0x18000a6c0`
- end: `0x18000a783`
- name: `?erase@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@@std@@@std@@@2@0@Z`
- size: `195`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x1800056b8`
- `0x180005790`
- `0x180007a20`
- `0x180007d5c`
- `0x18000a388`
- `0x18000ac44`

## callees

- `0x18000a27c`
- `0x18000a6c0`
- `0x18000a78c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 **__fastcall std::_Tree<std::_Tmap_traits<std::wstring,CNDFHelperClass *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CNDFHelperClass *>>,0>>::erase(
        __int64 ***a1,
        __int64 **a2,
        __int64 *a3,
        __int64 *a4)
{
  __int64 *v5; // rbx
  __int64 **v8; // rdx
  __int64 *v9; // r8
  __int64 *i; // rax
  __int64 *v11; // rcx
  char v13; // [rsp+50h] [rbp+8h] BYREF

  v5 = a3;
  v8 = *a1;
  if ( a3 != **a1 || a4 != (__int64 *)v8 )
  {
    while ( 1 )
    {
      if ( v5 == a4 )
      {
        *a2 = v5;
        return a2;
      }
      v9 = v5;
      if ( !*((_BYTE *)v5 + 25) )
      {
        i = (__int64 *)v5[2];
        if ( *((_BYTE *)i + 25) )
        {
          for ( i = (__int64 *)v5[1]; !*((_BYTE *)i + 25) && v5 == (__int64 *)i[2]; i = (__int64 *)i[1] )
            v5 = i;
LABEL_14:
          v5 = i;
          goto LABEL_15;
        }
        v11 = (__int64 *)*i;
        if ( *(_BYTE *)(*i + 25) )
          goto LABEL_14;
        do
        {
          v5 = v11;
          v11 = (__int64 *)*v11;
        }
        while ( !*((_BYTE *)v11 + 25) );
      }
LABEL_15:
      std::_Tree<std::_Tmap_traits<std::wstring,CNDFHelperClass *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CNDFHelperClass *>>,0>>::erase(
        a1,
        &v13,
        v9);
    }
  }
  std::_Tree<std::_Tmap_traits<std::wstring,CNDFHelperClass *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CNDFHelperClass *>>,0>>::_Erase(
    a1,
    v8[1]);
  (*a1)[1] = (__int64 *)*a1;
  **a1 = (__int64 *)*a1;
  (*a1)[2] = (__int64 *)*a1;
  a1[1] = 0;
  *a2 = **a1;
  return a2;
}

```

## disassembly

```asm
0x18000a6c0  push    rbx
0x18000a6c2  push    rdi
0x18000a6c3  push    r14
0x18000a6c5  push    r15
0x18000a6c7  sub     rsp, 28h
0x18000a6cb  mov     rdi, r9
0x18000a6ce  mov     rbx, r8
0x18000a6d1  mov     r15, rdx
0x18000a6d4  mov     r14, rcx
0x18000a6d7  mov     rdx, [rcx]
0x18000a6da  cmp     r8, [rdx]
0x18000a6dd  jnz     short loc_18000A714
0x18000a6df  cmp     r9, rdx
0x18000a6e2  jnz     short loc_18000A714
0x18000a6e4  mov     rdx, [rdx+8]
0x18000a6e8  call    ?_Erase@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@@2@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,CNDFHelperClass *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CNDFHelperClass *>>,0>>::_Erase(std::_Tree_node<std::pair<std::wstring const,CNDFHelperClass *>,void *> *)
0x18000a6ed  mov     rax, [r14]
0x18000a6f0  mov     [rax+8], rax
0x18000a6f4  mov     rax, [r14]
0x18000a6f7  mov     [rax], rax
0x18000a6fa  mov     rax, [r14]
0x18000a6fd  mov     [rax+10h], rax
0x18000a701  mov     qword ptr [r14+8], 0
0x18000a709  mov     rax, [r14]
0x18000a70c  mov     rcx, [rax]
0x18000a70f  mov     [r15], rcx
0x18000a712  jmp     short loc_18000A774
0x18000a714  cmp     rbx, rdi
0x18000a717  jz      short loc_18000A771
0x18000a719  mov     r8, rbx
0x18000a71c  cmp     byte ptr [rbx+19h], 0
0x18000a720  jnz     short loc_18000A762
0x18000a722  mov     rax, [rbx+10h]
0x18000a726  cmp     byte ptr [rax+19h], 0
0x18000a72a  jnz     short loc_18000A746
0x18000a72c  mov     rcx, [rax]
0x18000a72f  cmp     byte ptr [rcx+19h], 0
0x18000a733  jnz     short loc_18000A75F
0x18000a735  mov     rbx, rcx
0x18000a738  mov     rax, [rcx]
0x18000a73b  mov     rcx, rax
0x18000a73e  cmp     byte ptr [rax+19h], 0
0x18000a742  jz      short loc_18000A735
0x18000a744  jmp     short loc_18000A762
0x18000a746  mov     rax, [rbx+8]
0x18000a74a  jmp     short loc_18000A759
0x18000a74c  cmp     rbx, [rax+10h]
0x18000a750  jnz     short loc_18000A75F
0x18000a752  mov     rbx, rax
0x18000a755  mov     rax, [rax+8]
0x18000a759  cmp     byte ptr [rax+19h], 0
0x18000a75d  jz      short loc_18000A74C
0x18000a75f  mov     rbx, rax
0x18000a762  lea     rdx, [rsp+48h+arg_0]
0x18000a767  mov     rcx, r14
0x18000a76a  call    ?erase@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@@std@@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,CNDFHelperClass *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CNDFHelperClass *>>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CNDFHelperClass *>>>>)
0x18000a76f  jmp     short loc_18000A714
0x18000a771  mov     [r15], rbx
0x18000a774  mov     rax, r15
0x18000a777  add     rsp, 28h
0x18000a77b  pop     r15
0x18000a77d  pop     r14
0x18000a77f  pop     rdi
0x18000a780  pop     rbx
0x18000a781  retn
```
