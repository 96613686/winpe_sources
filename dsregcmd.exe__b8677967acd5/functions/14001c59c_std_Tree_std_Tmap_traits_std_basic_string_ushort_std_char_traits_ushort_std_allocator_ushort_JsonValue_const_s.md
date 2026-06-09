# std::_Tree<std::_Tmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,JsonValue const *,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,JsonValue const *>>,0>>::_Find_lower_bound<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x14001c59c`
- end: `0x14001c63d`
- name: `??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBVJsonValue@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBVJsonValue@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBVJsonValue@@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z`
- size: `161`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14001cac4`
- `0x14001d36c`

## callees

- `0x140011024`
- `0x14001c59c`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tmap_traits<std::wstring,JsonValue const *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,JsonValue const *>>,0>>::_Find_lower_bound<std::wstring>(
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
0x14001c59c  push    rbx
0x14001c59e  push    rbp
0x14001c59f  push    rsi
0x14001c5a0  push    rdi
0x14001c5a1  push    r14
0x14001c5a3  sub     rsp, 20h
0x14001c5a7  mov     rax, [rcx]
0x14001c5aa  mov     rsi, r8
0x14001c5ad  mov     rdi, rdx
0x14001c5b0  mov     r9, [rax+8]
0x14001c5b4  mov     [rdx], r9
0x14001c5b7  mov     rbx, r9
0x14001c5ba  mov     qword ptr [rdx+8], 0
0x14001c5c2  mov     rax, [rcx]
0x14001c5c5  mov     [rdx+10h], rax
0x14001c5c9  cmp     byte ptr [r9+19h], 0
0x14001c5ce  jnz     short loc_14001C622
0x14001c5d0  mov     [rdi], rbx
0x14001c5d3  lea     rcx, [rbx+20h]
0x14001c5d7  cmp     qword ptr [rsi+18h], 7
0x14001c5dc  mov     r14, [rsi+10h]
0x14001c5e0  jbe     short loc_14001C5E7
0x14001c5e2  mov     rdx, [rsi]
0x14001c5e5  jmp     short loc_14001C5EA
0x14001c5e7  mov     rdx, rsi; S2
0x14001c5ea  cmp     qword ptr [rcx+18h], 7
0x14001c5ef  mov     rbp, [rbx+30h]
0x14001c5f3  jbe     short loc_14001C5F8
0x14001c5f5  mov     rcx, [rcx]; S1
0x14001c5f8  cmp     r14, rbp
0x14001c5fb  mov     r8, r14
0x14001c5fe  cmovnb  r8, rbp; N
0x14001c602  call    wmemcmp
0x14001c607  test    eax, eax
0x14001c609  jz      short loc_14001C630
0x14001c60b  js      short loc_14001C635
0x14001c60d  mov     [rdi+10h], rbx
0x14001c611  mov     eax, 1
0x14001c616  mov     [rdi+8], eax
0x14001c619  mov     rbx, [rbx]
0x14001c61c  cmp     byte ptr [rbx+19h], 0
0x14001c620  jz      short loc_14001C5D0
0x14001c622  mov     rax, rdi
0x14001c625  add     rsp, 20h
0x14001c629  pop     r14
0x14001c62b  pop     rdi
0x14001c62c  pop     rsi
0x14001c62d  pop     rbp
0x14001c62e  pop     rbx
0x14001c62f  retn
0x14001c630  cmp     rbp, r14
0x14001c633  jnb     short loc_14001C60D
0x14001c635  add     rbx, 10h
0x14001c639  xor     eax, eax
0x14001c63b  jmp     short loc_14001C616
```
