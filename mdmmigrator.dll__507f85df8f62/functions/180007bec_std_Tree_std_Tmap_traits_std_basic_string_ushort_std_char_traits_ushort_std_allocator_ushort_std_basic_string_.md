# std::_Tree<std::_Tmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,0>>::_Find_lower_bound<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180007bec`
- end: `0x180007c8d`
- name: `??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z`
- size: `161`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180007dd4`
- `0x1800082ac`
- `0x18000be00`
- `0x18000de8c`
- `0x18000eae0`
- `0x18000f5c4`

## callees

- `0x180007bec`
- `0x180009850`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_lower_bound<std::wstring>(
        __int64 a1,
        _QWORD *a2,
        __int64 a3)
{
  __int64 *v5; // r9
  __int64 *v6; // rbx
  const wchar_t *v7; // rcx
  unsigned __int64 v8; // r14
  const wchar_t *v9; // rdx
  unsigned __int64 v10; // rbp
  size_t v11; // r8
  int v12; // eax
  int v13; // eax

  v5 = *(__int64 **)(*(_QWORD *)a1 + 8LL);
  *a2 = v5;
  v6 = v5;
  a2[1] = 0;
  for ( a2[2] = *(_QWORD *)a1; !*((_BYTE *)v6 + 25); v6 = (__int64 *)*v6 )
  {
    *a2 = v6;
    v7 = (const wchar_t *)(v6 + 4);
    v8 = *(_QWORD *)(a3 + 16);
    if ( *(_QWORD *)(a3 + 24) <= 7u )
      v9 = (const wchar_t *)a3;
    else
      v9 = *(const wchar_t **)a3;
    v10 = v6[6];
    if ( (unsigned __int64)v6[7] > 7 )
      v7 = *(const wchar_t **)v7;
    v11 = *(_QWORD *)(a3 + 16);
    if ( v8 >= v10 )
      v11 = v6[6];
    v12 = wmemcmp(v7, v9, v11);
    if ( v12 )
    {
      if ( v12 < 0 )
        goto LABEL_15;
    }
    else if ( v10 < v8 )
    {
LABEL_15:
      v6 += 2;
      v13 = 0;
      goto LABEL_12;
    }
    a2[2] = v6;
    v13 = 1;
LABEL_12:
    *((_DWORD *)a2 + 2) = v13;
  }
  return a2;
}

```

## disassembly

```asm
0x180007bec  push    rbx
0x180007bee  push    rbp
0x180007bef  push    rsi
0x180007bf0  push    rdi
0x180007bf1  push    r14
0x180007bf3  sub     rsp, 20h
0x180007bf7  mov     rax, [rcx]
0x180007bfa  mov     rsi, r8
0x180007bfd  mov     rdi, rdx
0x180007c00  mov     r9, [rax+8]
0x180007c04  mov     [rdx], r9
0x180007c07  mov     rbx, r9
0x180007c0a  mov     qword ptr [rdx+8], 0
0x180007c12  mov     rax, [rcx]
0x180007c15  mov     [rdx+10h], rax
0x180007c19  cmp     byte ptr [r9+19h], 0
0x180007c1e  jnz     short loc_180007C72
0x180007c20  mov     [rdi], rbx
0x180007c23  lea     rcx, [rbx+20h]
0x180007c27  cmp     qword ptr [rsi+18h], 7
0x180007c2c  mov     r14, [rsi+10h]
0x180007c30  jbe     short loc_180007C37
0x180007c32  mov     rdx, [rsi]
0x180007c35  jmp     short loc_180007C3A
0x180007c37  mov     rdx, rsi; S2
0x180007c3a  cmp     qword ptr [rcx+18h], 7
0x180007c3f  mov     rbp, [rbx+30h]
0x180007c43  jbe     short loc_180007C48
0x180007c45  mov     rcx, [rcx]; S1
0x180007c48  cmp     r14, rbp
0x180007c4b  mov     r8, r14
0x180007c4e  cmovnb  r8, rbp; N
0x180007c52  call    wmemcmp
0x180007c57  test    eax, eax
0x180007c59  jz      short loc_180007C80
0x180007c5b  js      short loc_180007C85
0x180007c5d  mov     [rdi+10h], rbx
0x180007c61  mov     eax, 1
0x180007c66  mov     [rdi+8], eax
0x180007c69  mov     rbx, [rbx]
0x180007c6c  cmp     byte ptr [rbx+19h], 0
0x180007c70  jz      short loc_180007C20
0x180007c72  mov     rax, rdi
0x180007c75  add     rsp, 20h
0x180007c79  pop     r14
0x180007c7b  pop     rdi
0x180007c7c  pop     rsi
0x180007c7d  pop     rbp
0x180007c7e  pop     rbx
0x180007c7f  retn
0x180007c80  cmp     rbp, r14
0x180007c83  jnb     short loc_180007C5D
0x180007c85  add     rbx, 10h
0x180007c89  xor     eax, eax
0x180007c8b  jmp     short loc_180007C66
```
