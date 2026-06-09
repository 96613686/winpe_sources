# std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,JsonValue const *,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,JsonValue const *>>>::operator[](std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x14001cac4`
- end: `0x14001cbbb`
- name: `??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBVJsonValue@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBVJsonValue@@@std@@@2@@std@@QEAAAEAPEBVJsonValue@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z`
- size: `247`
- prototype: `__int64 __fastcall(__int64 *, const wchar_t *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x14001ce88`

## callees

- `0x1400017d4`
- `0x140011024`
- `0x140015ba8`
- `0x140015dd8`
- `0x14001c59c`
- `0x14001c644`
- `0x14001cac4`

## pseudocode

```c
__int64 __fastcall std::map<std::wstring,JsonValue const *>::operator[](__int64 *a1, const wchar_t *a2)
{
  __int64 inserted; // rbx
  const wchar_t *v5; // rdx
  unsigned __int64 v6; // rsi
  unsigned __int64 v7; // rdi
  const wchar_t *v8; // rcx
  size_t v9; // r8
  int v10; // eax
  __int64 v11; // rsi
  _QWORD *v12; // rdi
  __int128 v14; // [rsp+20h] [rbp-58h] BYREF
  __int128 v15; // [rsp+30h] [rbp-48h] BYREF
  __int64 v16; // [rsp+40h] [rbp-38h]

  std::_Tree<std::_Tmap_traits<std::wstring,JsonValue const *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,JsonValue const *>>,0>>::_Find_lower_bound<std::wstring>(
    (__int64)a1,
    &v15,
    (__int64)a2);
  inserted = v16;
  if ( !*(_BYTE *)(v16 + 25) )
  {
    v5 = (const wchar_t *)(v16 + 32);
    v6 = *(_QWORD *)(v16 + 48);
    if ( *(_QWORD *)(v16 + 56) > 7u )
      v5 = *(const wchar_t **)v5;
    v7 = *((_QWORD *)a2 + 2);
    if ( *((_QWORD *)a2 + 3) <= 7u )
      v8 = a2;
    else
      v8 = *(const wchar_t **)a2;
    v9 = *((_QWORD *)a2 + 2);
    if ( v6 < v7 )
      v9 = *(_QWORD *)(v16 + 48);
    v10 = wmemcmp(v8, v5, v9);
    if ( v10 )
    {
      if ( v10 >= 0 )
        return inserted + 64;
    }
    else if ( v7 >= v6 )
    {
      return inserted + 64;
    }
  }
  if ( a1[1] == 0x38E38E38E38E38ELL )
    std::_Throw_tree_length_error();
  v11 = *a1;
  v12 = operator new(0x48u);
  std::wstring::wstring(v12 + 4, a2);
  v12[8] = 0;
  *v12 = v11;
  v12[1] = v11;
  v12[2] = v11;
  *((_WORD *)v12 + 12) = 0;
  v14 = v15;
  inserted = std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,JsonValue const *>>>::_Insert_node(
               a1,
               &v14,
               v12);
  return inserted + 64;
}

```

## disassembly

```asm
0x14001cac4  push    rbx
0x14001cac6  push    rsi
0x14001cac7  push    rdi
0x14001cac8  push    r14
0x14001caca  push    r15
0x14001cacc  sub     rsp, 50h
0x14001cad0  mov     r14, rdx
0x14001cad3  mov     r15, rcx
0x14001cad6  mov     r8, rdx
0x14001cad9  lea     rdx, [rsp+78h+var_48]
0x14001cade  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBVJsonValue@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBVJsonValue@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBVJsonValue@@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,JsonValue const *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,JsonValue const *>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x14001cae3  mov     rbx, [rsp+78h+var_38]
0x14001cae8  cmp     byte ptr [rbx+19h], 0
0x14001caec  jnz     short loc_14001CB2F
0x14001caee  lea     rdx, [rbx+20h]
0x14001caf2  mov     rsi, [rdx+10h]
0x14001caf6  cmp     qword ptr [rdx+18h], 7
0x14001cafb  jbe     short loc_14001CB00
0x14001cafd  mov     rdx, [rdx]; S2
0x14001cb00  mov     rdi, [r14+10h]
0x14001cb04  cmp     qword ptr [r14+18h], 7
0x14001cb09  jbe     short loc_14001CB10
0x14001cb0b  mov     rcx, [r14]
0x14001cb0e  jmp     short loc_14001CB13
0x14001cb10  mov     rcx, r14; S1
0x14001cb13  mov     r8, rdi
0x14001cb16  cmp     rsi, rdi
0x14001cb19  cmovb   r8, rsi; N
0x14001cb1d  call    wmemcmp
0x14001cb22  test    eax, eax
0x14001cb24  jnz     short loc_14001CB2D
0x14001cb26  cmp     rdi, rsi
0x14001cb29  jnb     short loc_14001CBA5
0x14001cb2b  jmp     short loc_14001CB2F
0x14001cb2d  jns     short loc_14001CBA5
0x14001cb2f  mov     rax, 38E38E38E38E38Eh
0x14001cb39  cmp     [r15+8], rax
0x14001cb3d  jz      short loc_14001CBB5
0x14001cb3f  mov     rsi, [r15]
0x14001cb42  mov     qword ptr [rsp+78h+var_58], r15
0x14001cb47  mov     qword ptr [rsp+78h+var_58+8], 0
0x14001cb50  mov     ecx, 48h ; 'H'; Size
0x14001cb55  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001cb5a  mov     rdi, rax
0x14001cb5d  mov     qword ptr [rsp+78h+var_58+8], rax
0x14001cb62  mov     rdx, r14
0x14001cb65  lea     rcx, [rax+20h]
0x14001cb69  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14001cb6e  mov     qword ptr [rdi+40h], 0
0x14001cb76  mov     [rdi], rsi
0x14001cb79  mov     [rdi+8], rsi
0x14001cb7d  mov     [rdi+10h], rsi
0x14001cb81  mov     word ptr [rdi+18h], 0
0x14001cb87  movups  xmm0, [rsp+78h+var_48]
0x14001cb8c  movdqu  [rsp+78h+var_58], xmm0
0x14001cb92  mov     r8, rdi
0x14001cb95  lea     rdx, [rsp+78h+var_58]
0x14001cb9a  mov     rcx, r15
0x14001cb9d  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBVJsonValue@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBVJsonValue@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBVJsonValue@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,JsonValue const *>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<std::wstring const,JsonValue const *>,void *> *>,std::_Tree_node<std::pair<std::wstring const,JsonValue const *>,void *> * const)
0x14001cba2  mov     rbx, rax
0x14001cba5  lea     rax, [rbx+40h]
0x14001cba9  add     rsp, 50h
0x14001cbad  pop     r15
0x14001cbaf  pop     r14
0x14001cbb1  pop     rdi
0x14001cbb2  pop     rsi
0x14001cbb3  pop     rbx
0x14001cbb4  retn
0x14001cbb5  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
