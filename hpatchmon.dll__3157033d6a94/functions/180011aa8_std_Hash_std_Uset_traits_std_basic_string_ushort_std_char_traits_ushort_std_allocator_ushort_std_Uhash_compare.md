# std::_Hash<std::_Uset_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,0>>::_Find_last<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,unsigned __int64)

- ea: `0x180011aa8`
- end: `0x180011b48`
- name: `??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z`
- size: `160`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180011d60`
- `0x180013d34`

## callees

- `0x180011aa8`
- `0x180013dc4`

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

  v6 = *(_QWORD **)(qword_180022ED8 + 16 * (a4 & qword_180022EF0) + 8);
  if ( v6 == (_QWORD *)qword_180022EC8 )
  {
    *a2 = qword_180022EC8;
  }
  else
  {
    v7 = *(_QWORD **)(qword_180022ED8 + 16 * (a4 & qword_180022EF0));
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
0x180011aa8  push    rbx
0x180011aaa  push    rbp
0x180011aab  push    rsi
0x180011aac  push    rdi
0x180011aad  sub     rsp, 28h
0x180011ab1  mov     rax, cs:qword_180022EF0
0x180011ab8  mov     rbx, rdx
0x180011abb  mov     rdx, cs:qword_180022ED8
0x180011ac2  and     rax, r9
0x180011ac5  mov     rcx, cs:qword_180022EC8
0x180011acc  add     rax, rax
0x180011acf  mov     rsi, r8
0x180011ad2  mov     rdi, [rdx+rax*8+8]
0x180011ad7  cmp     rdi, rcx
0x180011ada  jnz     short loc_180011AE1
0x180011adc  mov     [rbx], rcx
0x180011adf  jmp     short loc_180011B34
0x180011ae1  mov     rbp, [rdx+rax*8]
0x180011ae5  cmp     qword ptr [rdi+28h], 7
0x180011aea  lea     rdx, [rdi+10h]
0x180011aee  jbe     short loc_180011AF3
0x180011af0  mov     rdx, [rdx]; S2
0x180011af3  cmp     qword ptr [rsi+18h], 7
0x180011af8  mov     r8, [rsi+10h]; N
0x180011afc  jbe     short loc_180011B03
0x180011afe  mov     rcx, [rsi]
0x180011b01  jmp     short loc_180011B06
0x180011b03  mov     rcx, rsi; S1
0x180011b06  cmp     r8, [rdi+20h]
0x180011b0a  jnz     short loc_180011B1A
0x180011b0c  test    r8, r8
0x180011b0f  jz      short loc_180011B25
0x180011b11  call    wmemcmp
0x180011b16  test    eax, eax
0x180011b18  jz      short loc_180011B25
0x180011b1a  cmp     rdi, rbp
0x180011b1d  jz      short loc_180011B31
0x180011b1f  mov     rdi, [rdi+8]
0x180011b23  jmp     short loc_180011AE5
0x180011b25  mov     rax, [rdi]
0x180011b28  mov     [rbx], rax
0x180011b2b  mov     [rbx+8], rdi
0x180011b2f  jmp     short loc_180011B3C
0x180011b31  mov     [rbx], rdi
0x180011b34  mov     qword ptr [rbx+8], 0
0x180011b3c  mov     rax, rbx
0x180011b3f  add     rsp, 28h
0x180011b43  pop     rdi
0x180011b44  pop     rsi
0x180011b45  pop     rbp
0x180011b46  pop     rbx
0x180011b47  retn
```
