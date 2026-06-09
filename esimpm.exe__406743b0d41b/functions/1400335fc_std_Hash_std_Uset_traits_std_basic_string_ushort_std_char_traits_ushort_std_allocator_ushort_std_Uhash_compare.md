# std::_Hash<std::_Uset_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,0>>::clear(void)

- ea: `0x1400335fc`
- end: `0x1400336bf`
- name: `?clear@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAAXXZ`
- size: `195`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14002fb4c`

## callees

- `0x140003244`
- `0x140013df8`
- `0x140033424`
- `0x1400335fc`

## pseudocode

```c
void __fastcall std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::clear(
        _QWORD *a1)
{
  __int64 v2; // rcx
  char *v3; // rsi
  char *v4; // rdi
  void *v5; // rdi
  unsigned __int64 v6; // rcx

  if ( a1[2] )
  {
    v2 = a1[1];
    if ( a1[7] >> 3 <= a1[2] )
    {
      **(_QWORD **)(v2 + 8) = 0;
      v3 = *(char **)v2;
      if ( *(_QWORD *)v2 )
      {
        do
        {
          v4 = *(char **)v3;
          std::wstring::_Tidy_deallocate((char **)v3 + 2);
          operator delete(v3);
          v3 = v4;
        }
        while ( v4 );
      }
      *(_QWORD *)a1[1] = a1[1];
      *(_QWORD *)(a1[1] + 8LL) = a1[1];
      a1[2] = 0;
      v5 = (void *)a1[3];
      v6 = (unsigned __int64)(a1[4] - (_QWORD)v5 + 7LL) >> 3;
      if ( (unsigned __int64)v5 > a1[4] )
        v6 = 0;
      if ( v6 )
        memset64(v5, a1[1], v6);
    }
    else
    {
      std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Unchecked_erase(
        a1,
        *(char **)v2,
        (char *)v2);
    }
  }
}

```

## disassembly

```asm
0x1400335fc  mov     [rsp+arg_0], rbx
0x140033601  mov     [rsp+arg_8], rsi
0x140033606  push    rdi
0x140033607  sub     rsp, 20h
0x14003360b  cmp     qword ptr [rcx+10h], 0
0x140033610  mov     rbx, rcx
0x140033613  jz      loc_1400336AF
0x140033619  mov     rax, [rbx+38h]
0x14003361d  mov     rcx, [rcx+8]
0x140033621  shr     rax, 3
0x140033625  cmp     rax, [rbx+10h]
0x140033629  jbe     short loc_14003363B
0x14003362b  mov     rdx, [rcx]
0x14003362e  mov     r8, rcx
0x140033631  mov     rcx, rbx
0x140033634  call    ?_Unchecked_erase@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@AEAAPEAU?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@2@PEAU32@QEAU32@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Unchecked_erase(std::_List_node<std::wstring,void *> *,std::_List_node<std::wstring,void *> * const)
0x140033639  jmp     short loc_1400336AF
0x14003363b  mov     rax, [rcx+8]
0x14003363f  mov     qword ptr [rax], 0
0x140033646  mov     rsi, [rcx]
0x140033649  test    rsi, rsi
0x14003364c  jz      short loc_14003366F
0x14003364e  mov     rdi, [rsi]
0x140033651  lea     rcx, [rsi+10h]
0x140033655  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003365a  mov     edx, 30h ; '0'
0x14003365f  mov     rcx, rsi; Block
0x140033662  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140033667  mov     rsi, rdi
0x14003366a  test    rdi, rdi
0x14003366d  jnz     short loc_14003364E
0x14003366f  mov     rax, [rbx+8]
0x140033673  xor     edx, edx
0x140033675  mov     [rax], rax
0x140033678  mov     rax, [rbx+8]
0x14003367c  mov     [rax+8], rax
0x140033680  mov     qword ptr [rbx+10h], 0
0x140033688  mov     rdi, [rbx+18h]
0x14003368c  mov     rcx, [rbx+20h]
0x140033690  sub     rcx, rdi
0x140033693  add     rcx, 7
0x140033697  shr     rcx, 3
0x14003369b  cmp     rdi, [rbx+20h]
0x14003369f  cmova   rcx, rdx
0x1400336a3  test    rcx, rcx
0x1400336a6  jz      short loc_1400336AF
0x1400336a8  mov     rax, [rbx+8]
0x1400336ac  rep stosq
0x1400336af  mov     rbx, [rsp+28h+arg_0]
0x1400336b4  mov     rsi, [rsp+28h+arg_8]
0x1400336b9  add     rsp, 20h
0x1400336bd  pop     rdi
0x1400336be  retn
```
