# std::_Hash<std::_Umap_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::tuple<std::vector<uchar,std::allocator<uchar>>,std::vector<uchar,std::allocator<uchar>>,std::vector<uchar,std::allocator<uchar>>,std::vector<uchar,std::allocator<uchar>>,std::vector<uchar,std::allocator<uchar>>>,std::_Uhash_compare<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::hash<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,std::equal_to<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,std::tuple<std::vector<uchar,std::allocator<uchar>>,std::vector<uchar,std::allocator<uchar>>,std::vector<uchar,std::allocator<uchar>>,std::vector<uchar,std::allocator<uchar>>,std::vector<uchar,std::allocator<uchar>>>>>,0>>::_Find_last<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,unsigned __int64)

- ea: `0x180010f68`
- end: `0x180010fff`
- name: `??$_Find_last@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V12@V12@V12@V12@@2@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V12@V12@V12@V12@@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V12@V12@V12@V12@@2@@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@_K@Z`
- size: `151`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180011008`
- `0x180011600`

## callees

- `0x180010d20`
- `0x180010f68`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<std::_Umap_traits<std::wstring,std::tuple<std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::tuple<std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>>>>,0>>::_Find_last<std::wstring>(
        _QWORD *a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v5; // r8
  _QWORD *v7; // rdx
  _QWORD *v8; // rdi
  _QWORD *v9; // rbp
  const wchar_t *v10; // rdx
  size_t v11; // r8
  const wchar_t *v12; // rcx

  v5 = a1[3];
  v7 = (_QWORD *)a1[1];
  v8 = *(_QWORD **)(v5 + 16 * (a4 & a1[6]) + 8);
  if ( v8 == v7 )
  {
    *a2 = v7;
  }
  else
  {
    v9 = *(_QWORD **)(v5 + 16 * (a4 & a1[6]));
    while ( 1 )
    {
      v10 = (const wchar_t *)(v8 + 2);
      if ( v8[5] > 7u )
        v10 = *(const wchar_t **)v10;
      v11 = *(_QWORD *)(a3 + 16);
      if ( *(_QWORD *)(a3 + 24) <= 7u )
        v12 = (const wchar_t *)a3;
      else
        v12 = *(const wchar_t **)a3;
      if ( v11 == v8[4] && (!v11 || !wmemcmp(v12, v10, v11)) )
      {
        *a2 = *v8;
        a2[1] = v8;
        return a2;
      }
      if ( v8 == v9 )
        break;
      v8 = (_QWORD *)v8[1];
    }
    *a2 = v8;
  }
  a2[1] = 0;
  return a2;
}

```

## disassembly

```asm
0x180010f68  push    rbx
0x180010f6a  push    rbp
0x180010f6b  push    rsi
0x180010f6c  push    rdi
0x180010f6d  sub     rsp, 28h
0x180010f71  mov     rax, [rcx+30h]
0x180010f75  mov     rsi, r8
0x180010f78  mov     r8, [rcx+18h]
0x180010f7c  and     rax, r9
0x180010f7f  add     rax, rax
0x180010f82  mov     rbx, rdx
0x180010f85  mov     rdx, [rcx+8]
0x180010f89  mov     rdi, [r8+rax*8+8]
0x180010f8e  cmp     rdi, rdx
0x180010f91  jnz     short loc_180010F98
0x180010f93  mov     [rbx], rdx
0x180010f96  jmp     short loc_180010FEB
0x180010f98  mov     rbp, [r8+rax*8]
0x180010f9c  cmp     qword ptr [rdi+28h], 7
0x180010fa1  lea     rdx, [rdi+10h]
0x180010fa5  jbe     short loc_180010FAA
0x180010fa7  mov     rdx, [rdx]; S2
0x180010faa  cmp     qword ptr [rsi+18h], 7
0x180010faf  mov     r8, [rsi+10h]; N
0x180010fb3  jbe     short loc_180010FBA
0x180010fb5  mov     rcx, [rsi]
0x180010fb8  jmp     short loc_180010FBD
0x180010fba  mov     rcx, rsi; S1
0x180010fbd  cmp     r8, [rdi+20h]
0x180010fc1  jnz     short loc_180010FD1
0x180010fc3  test    r8, r8
0x180010fc6  jz      short loc_180010FDC
0x180010fc8  call    wmemcmp
0x180010fcd  test    eax, eax
0x180010fcf  jz      short loc_180010FDC
0x180010fd1  cmp     rdi, rbp
0x180010fd4  jz      short loc_180010FE8
0x180010fd6  mov     rdi, [rdi+8]
0x180010fda  jmp     short loc_180010F9C
0x180010fdc  mov     rax, [rdi]
0x180010fdf  mov     [rbx], rax
0x180010fe2  mov     [rbx+8], rdi
0x180010fe6  jmp     short loc_180010FF3
0x180010fe8  mov     [rbx], rdi
0x180010feb  mov     qword ptr [rbx+8], 0
0x180010ff3  mov     rax, rbx
0x180010ff6  add     rsp, 28h
0x180010ffa  pop     rdi
0x180010ffb  pop     rsi
0x180010ffc  pop     rbp
0x180010ffd  pop     rbx
0x180010ffe  retn
```
