# std::_Tree<std::_Tmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,CachedAdapterInformation,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,CachedAdapterInformation>>,0>>::_Find_lower_bound<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x140004810`
- end: `0x1400048b1`
- name: `??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCachedAdapterInformation@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCachedAdapterInformation@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCachedAdapterInformation@@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z`
- size: `161`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140004d34`
- `0x14000893c`

## callees

- `0x140004810`
- `0x14001113c`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tmap_traits<std::wstring,CachedAdapterInformation,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CachedAdapterInformation>>,0>>::_Find_lower_bound<std::wstring>(
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
0x140004810  push    rbx
0x140004812  push    rbp
0x140004813  push    rsi
0x140004814  push    rdi
0x140004815  push    r14
0x140004817  sub     rsp, 20h
0x14000481b  mov     rax, [rcx]
0x14000481e  mov     rsi, r8
0x140004821  mov     rdi, rdx
0x140004824  mov     r9, [rax+8]
0x140004828  mov     [rdx], r9
0x14000482b  mov     rbx, r9
0x14000482e  mov     qword ptr [rdx+8], 0
0x140004836  mov     rax, [rcx]
0x140004839  mov     [rdx+10h], rax
0x14000483d  cmp     byte ptr [r9+19h], 0
0x140004842  jnz     short loc_140004896
0x140004844  mov     [rdi], rbx
0x140004847  lea     rcx, [rbx+20h]
0x14000484b  cmp     qword ptr [rsi+18h], 7
0x140004850  mov     r14, [rsi+10h]
0x140004854  jbe     short loc_14000485B
0x140004856  mov     rdx, [rsi]
0x140004859  jmp     short loc_14000485E
0x14000485b  mov     rdx, rsi; S2
0x14000485e  cmp     qword ptr [rcx+18h], 7
0x140004863  mov     rbp, [rbx+30h]
0x140004867  jbe     short loc_14000486C
0x140004869  mov     rcx, [rcx]; S1
0x14000486c  cmp     r14, rbp
0x14000486f  mov     r8, r14
0x140004872  cmovnb  r8, rbp; N
0x140004876  call    wmemcmp
0x14000487b  test    eax, eax
0x14000487d  jz      short loc_1400048A4
0x14000487f  js      short loc_1400048A9
0x140004881  mov     [rdi+10h], rbx
0x140004885  mov     eax, 1
0x14000488a  mov     [rdi+8], eax
0x14000488d  mov     rbx, [rbx]
0x140004890  cmp     byte ptr [rbx+19h], 0
0x140004894  jz      short loc_140004844
0x140004896  mov     rax, rdi
0x140004899  add     rsp, 20h
0x14000489d  pop     r14
0x14000489f  pop     rdi
0x1400048a0  pop     rsi
0x1400048a1  pop     rbp
0x1400048a2  pop     rbx
0x1400048a3  retn
0x1400048a4  cmp     rbp, r14
0x1400048a7  jnb     short loc_140004881
0x1400048a9  add     rbx, 10h
0x1400048ad  xor     eax, eax
0x1400048af  jmp     short loc_14000488A
```
