# std::_Hash<std::_Uset_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,0>>::_Find_last<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,unsigned __int64)

- ea: `0x14000fa10`
- end: `0x14000fab0`
- name: `??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z`
- size: `160`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000fab8`
- `0x14001088c`

## callees

- `0x14000fa10`
- `0x140011024`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4)
{
  _QWORD *v6; // rdi
  _QWORD *v7; // rbp
  const wchar_t *v8; // rdx
  size_t v9; // r8
  const wchar_t *v10; // rcx

  v6 = *(_QWORD **)(qword_1400460B8 + 16 * (a4 & qword_1400460D0) + 8);
  if ( v6 == (_QWORD *)qword_1400460A8 )
  {
    *a2 = qword_1400460A8;
  }
  else
  {
    v7 = *(_QWORD **)(qword_1400460B8 + 16 * (a4 & qword_1400460D0));
    while ( 1 )
    {
      v8 = (const wchar_t *)(v6 + 2);
      if ( v6[5] > 7u )
        v8 = *(const wchar_t **)v8;
      v9 = *(_QWORD *)(a3 + 16);
      if ( *(_QWORD *)(a3 + 24) <= 7u )
        v10 = (const wchar_t *)a3;
      else
        v10 = *(const wchar_t **)a3;
      if ( v9 == v6[4] && (!v9 || !wmemcmp(v10, v8, v9)) )
      {
        *a2 = *v6;
        a2[1] = v6;
        return a2;
      }
      if ( v6 == v7 )
        break;
      v6 = (_QWORD *)v6[1];
    }
    *a2 = v6;
  }
  a2[1] = 0;
  return a2;
}

```

## disassembly

```asm
0x14000fa10  push    rbx
0x14000fa12  push    rbp
0x14000fa13  push    rsi
0x14000fa14  push    rdi
0x14000fa15  sub     rsp, 28h
0x14000fa19  mov     rax, cs:qword_1400460D0
0x14000fa20  mov     rbx, rdx
0x14000fa23  mov     rdx, cs:qword_1400460B8
0x14000fa2a  and     rax, r9
0x14000fa2d  mov     rcx, cs:qword_1400460A8
0x14000fa34  add     rax, rax
0x14000fa37  mov     rsi, r8
0x14000fa3a  mov     rdi, [rdx+rax*8+8]
0x14000fa3f  cmp     rdi, rcx
0x14000fa42  jnz     short loc_14000FA49
0x14000fa44  mov     [rbx], rcx
0x14000fa47  jmp     short loc_14000FA9C
0x14000fa49  mov     rbp, [rdx+rax*8]
0x14000fa4d  cmp     qword ptr [rdi+28h], 7
0x14000fa52  lea     rdx, [rdi+10h]
0x14000fa56  jbe     short loc_14000FA5B
0x14000fa58  mov     rdx, [rdx]; S2
0x14000fa5b  cmp     qword ptr [rsi+18h], 7
0x14000fa60  mov     r8, [rsi+10h]; N
0x14000fa64  jbe     short loc_14000FA6B
0x14000fa66  mov     rcx, [rsi]
0x14000fa69  jmp     short loc_14000FA6E
0x14000fa6b  mov     rcx, rsi; S1
0x14000fa6e  cmp     r8, [rdi+20h]
0x14000fa72  jnz     short loc_14000FA82
0x14000fa74  test    r8, r8
0x14000fa77  jz      short loc_14000FA8D
0x14000fa79  call    wmemcmp
0x14000fa7e  test    eax, eax
0x14000fa80  jz      short loc_14000FA8D
0x14000fa82  cmp     rdi, rbp
0x14000fa85  jz      short loc_14000FA99
0x14000fa87  mov     rdi, [rdi+8]
0x14000fa8b  jmp     short loc_14000FA4D
0x14000fa8d  mov     rax, [rdi]
0x14000fa90  mov     [rbx], rax
0x14000fa93  mov     [rbx+8], rdi
0x14000fa97  jmp     short loc_14000FAA4
0x14000fa99  mov     [rbx], rdi
0x14000fa9c  mov     qword ptr [rbx+8], 0
0x14000faa4  mov     rax, rbx
0x14000faa7  add     rsp, 28h
0x14000faab  pop     rdi
0x14000faac  pop     rsi
0x14000faad  pop     rbp
0x14000faae  pop     rbx
0x14000faaf  retn
```
