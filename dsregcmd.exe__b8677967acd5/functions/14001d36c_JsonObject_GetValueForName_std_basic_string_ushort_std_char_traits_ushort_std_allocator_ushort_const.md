# JsonObject::GetValueForName(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x14001d36c`
- end: `0x14001d3ee`
- name: `?GetValueForName@JsonObject@@QEBAPEBVJsonValue@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `130`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14000baf8`
- `0x14001cf60`

## callees

- `0x140011024`
- `0x14001c59c`
- `0x14001d36c`

## pseudocode

```c
__int64 __fastcall JsonObject::GetValueForName(__int64 a1, __int64 a2)
{
  _QWORD *v2; // r14
  __int64 v3; // rbx
  __int64 v4; // rdi
  const wchar_t *v5; // rdx
  size_t v6; // rbp
  size_t v7; // rsi
  size_t v8; // r8
  int v9; // eax
  __int64 v11; // [rsp+20h] [rbp-48h] BYREF
  __int64 v12; // [rsp+30h] [rbp-38h]

  v2 = (_QWORD *)(a1 + 16);
  v3 = a2;
  std::_Tree<std::_Tmap_traits<std::wstring,JsonValue const *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,JsonValue const *>>,0>>::_Find_lower_bound<std::wstring>(
    a1 + 16,
    &v11,
    a2);
  v4 = v12;
  if ( *(_BYTE *)(v12 + 25) )
    return 0;
  v5 = (const wchar_t *)(v12 + 32);
  v6 = *(_QWORD *)(v12 + 48);
  if ( *(_QWORD *)(v12 + 56) > 7u )
    v5 = *(const wchar_t **)v5;
  v7 = *(_QWORD *)(v3 + 16);
  if ( *(_QWORD *)(v3 + 24) > 7u )
    v3 = *(_QWORD *)v3;
  v8 = *(_QWORD *)(v12 + 48);
  if ( v6 >= v7 )
    v8 = v7;
  v9 = wmemcmp((const wchar_t *)v3, v5, v8);
  if ( v9 )
  {
    if ( v9 < 0 )
      return 0;
  }
  else if ( v7 < v6 )
  {
    return 0;
  }
  if ( v4 == *v2 )
    return 0;
  return *(_QWORD *)(v4 + 64);
}

```

## disassembly

```asm
0x14001d36c  push    rbx
0x14001d36e  push    rbp
0x14001d36f  push    rsi
0x14001d370  push    rdi
0x14001d371  push    r14
0x14001d373  sub     rsp, 40h
0x14001d377  lea     r14, [rcx+10h]
0x14001d37b  mov     rbx, rdx
0x14001d37e  mov     r8, rdx
0x14001d381  mov     rcx, r14
0x14001d384  lea     rdx, [rsp+68h+var_48]
0x14001d389  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBVJsonValue@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBVJsonValue@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBVJsonValue@@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,JsonValue const *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,JsonValue const *>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x14001d38e  mov     rdi, [rsp+68h+var_38]
0x14001d393  cmp     byte ptr [rdi+19h], 0
0x14001d397  jnz     short loc_14001D3D4
0x14001d399  lea     rdx, [rdi+20h]
0x14001d39d  cmp     qword ptr [rdx+18h], 7
0x14001d3a2  mov     rbp, [rdx+10h]
0x14001d3a6  jbe     short loc_14001D3AB
0x14001d3a8  mov     rdx, [rdx]; S2
0x14001d3ab  cmp     qword ptr [rbx+18h], 7
0x14001d3b0  mov     rsi, [rbx+10h]
0x14001d3b4  jbe     short loc_14001D3B9
0x14001d3b6  mov     rbx, [rbx]
0x14001d3b9  cmp     rbp, rsi
0x14001d3bc  mov     r8, rbp
0x14001d3bf  mov     rcx, rbx; S1
0x14001d3c2  cmovnb  r8, rsi; N
0x14001d3c6  call    wmemcmp
0x14001d3cb  test    eax, eax
0x14001d3cd  jnz     short loc_14001D3E1
0x14001d3cf  cmp     rsi, rbp
0x14001d3d2  jnb     short loc_14001D3E3
0x14001d3d4  xor     eax, eax
0x14001d3d6  add     rsp, 40h
0x14001d3da  pop     r14
0x14001d3dc  pop     rdi
0x14001d3dd  pop     rsi
0x14001d3de  pop     rbp
0x14001d3df  pop     rbx
0x14001d3e0  retn
0x14001d3e1  js      short loc_14001D3D4
0x14001d3e3  cmp     rdi, [r14]
0x14001d3e6  jz      short loc_14001D3D4
0x14001d3e8  mov     rax, [rdi+40h]
0x14001d3ec  jmp     short loc_14001D3D6
```
