# std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::_Iterator_base0>>>(void)

- ea: `0x180012098`
- end: `0x180012102`
- name: `??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@XZ`
- size: `106`
- prototype: `void __fastcall(char **)`
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180012010`
- `0x180012070`
- `0x1800143e4`
- `0x180014506`
- `0x180014770`
- `0x1800147d0`

## callees

- `0x180002c8c`
- `0x180012098`

## pseudocode

```c
void __fastcall std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>(
        char **a1)
{
  char *v1; // rdx
  unsigned __int64 v3; // rax
  char *v4; // rcx

  v1 = *a1;
  if ( *a1 )
  {
    v3 = (a1[2] - v1) & 0xFFFFFFFFFFFFFFF8uLL;
    if ( v3 < 0x1000 )
    {
      v4 = *a1;
    }
    else
    {
      v4 = (char *)*((_QWORD *)v1 - 1);
      if ( (unsigned __int64)(v1 - v4 - 8) > 0x1F )
        __fastfail(5u);
      v3 += 39LL;
    }
    operator delete(v4, v3);
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
  }
}

```

## disassembly

```asm
0x180012098  push    rbx
0x18001209a  sub     rsp, 20h
0x18001209e  mov     rdx, [rcx]
0x1800120a1  mov     rbx, rcx
0x1800120a4  test    rdx, rdx
0x1800120a7  jz      short loc_1800120FC
0x1800120a9  mov     rax, [rcx+10h]
0x1800120ad  sub     rax, rdx
0x1800120b0  and     rax, 0FFFFFFFFFFFFFFF8h
0x1800120b4  cmp     rax, 1000h
0x1800120ba  jb      short loc_1800120DA
0x1800120bc  mov     rcx, [rdx-8]
0x1800120c0  sub     rdx, rcx
0x1800120c3  sub     rdx, 8
0x1800120c7  cmp     rdx, 1Fh
0x1800120cb  ja      short loc_1800120D3
0x1800120cd  add     rax, 27h ; '''
0x1800120d1  jmp     short loc_1800120DD
0x1800120d3  mov     ecx, 5
0x1800120d8  int     29h; Win8: RtlFailFast(ecx)
0x1800120da  mov     rcx, rdx; void *
0x1800120dd  mov     rdx, rax; unsigned __int64
0x1800120e0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800120e5  mov     qword ptr [rbx], 0
0x1800120ec  mov     qword ptr [rbx+8], 0
0x1800120f4  mov     qword ptr [rbx+10h], 0
0x1800120fc  add     rsp, 20h
0x180012100  pop     rbx
0x180012101  retn
```
