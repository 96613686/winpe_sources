# std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::unique_ptr<ProvResults,std::default_delete<ProvResults>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::unique_ptr<ProvResults,std::default_delete<ProvResults>>>>>::at(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180022088`
- end: `0x180022137`
- name: `?at@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@@std@@@2@@std@@QEAAAEAV?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z`
- size: `175`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180012eb4`
- `0x180018f74`
- `0x18001c7fc`
- `0x18001fab8`

## callees

- `0x180022088`
- `0x180022844`

## import_xrefs

- `msvcp110_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180022130`
- `msvcp110_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180022130`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
_QWORD *__fastcall std::map<std::wstring,std::unique_ptr<ProvResults>>::at(_QWORD *a1, _QWORD *a2)
{
  _QWORD *v2; // rdi
  _WORD *v4; // rdx
  unsigned __int64 v5; // r9
  unsigned __int64 v6; // r8
  unsigned __int64 v7; // rax
  int v8; // eax
  _QWORD *v10; // [rsp+30h] [rbp+8h] BYREF

  v2 = a2;
  std::_Tree<std::_Tmap_traits<std::wstring,PackageContext *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,PackageContext *>>,0>>::lower_bound(
    a1,
    &v10,
    a2);
  if ( v10 == (_QWORD *)*a1 )
    goto LABEL_18;
  if ( v10[7] < 8u )
    v4 = v10 + 4;
  else
    v4 = (_WORD *)v10[4];
  v5 = v10[6];
  v6 = v2[2];
  v7 = v6;
  if ( v6 >= v5 )
    v7 = v10[6];
  if ( v2[3] >= 8u )
    v2 = (_QWORD *)*v2;
  if ( v7 )
  {
    while ( *(_WORD *)v2 == *v4 )
    {
      v2 = (_QWORD *)((char *)v2 + 2);
      ++v4;
      if ( !--v7 )
        goto LABEL_12;
    }
    v8 = *(_WORD *)v2 < *v4 ? -1 : 1;
  }
  else
  {
LABEL_12:
    v8 = v6 >= v5 ? v6 != v5 : -1;
  }
  if ( v8 < 0 )
  {
LABEL_18:
    std::_Xout_of_range("invalid map<K, T> key");
    JUMPOUT(0x180022136LL);
  }
  return v10 + 8;
}

```

## disassembly

```asm
0x180022088  mov     [rsp+arg_8], rbx
0x18002208d  push    rdi
0x18002208e  sub     rsp, 20h
0x180022092  mov     rdi, rdx
0x180022095  mov     rbx, rcx
0x180022098  mov     r8, rdx
0x18002209b  lea     rdx, [rsp+28h+arg_0]
0x1800220a0  call    ?lower_bound@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUPackageContext@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUPackageContext@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUPackageContext@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,PackageContext *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,PackageContext *>>,0>>::lower_bound(std::wstring const &)
0x1800220a5  mov     rax, [rsp+28h+arg_0]
0x1800220aa  cmp     rax, [rbx]
0x1800220ad  jz      short loc_180022129
0x1800220af  lea     rcx, [rax+20h]
0x1800220b3  cmp     qword ptr [rcx+18h], 8
0x1800220b8  jb      short loc_1800220BF
0x1800220ba  mov     rdx, [rcx]
0x1800220bd  jmp     short loc_1800220C2
0x1800220bf  mov     rdx, rcx
0x1800220c2  mov     r9, [rcx+10h]
0x1800220c6  mov     r8, [rdi+10h]
0x1800220ca  mov     rax, r8
0x1800220cd  cmp     r8, r9
0x1800220d0  cmovnb  rax, r9
0x1800220d4  cmp     qword ptr [rdi+18h], 8
0x1800220d9  jb      short loc_1800220DE
0x1800220db  mov     rdi, [rdi]
0x1800220de  test    rax, rax
0x1800220e1  jz      short loc_1800220FB
0x1800220e3  movzx   r10d, word ptr [rdi]
0x1800220e7  cmp     r10w, [rdx]
0x1800220eb  jnz     short loc_180022105
0x1800220ed  add     rdi, 2
0x1800220f1  add     rdx, 2
0x1800220f5  sub     rax, 1
0x1800220f9  jnz     short loc_1800220E3
0x1800220fb  cmp     r8, r9
0x1800220fe  jnb     short loc_18002210E
0x180022100  or      eax, 0FFFFFFFFh
0x180022103  jmp     short loc_180022116
0x180022105  sbb     eax, eax
0x180022107  and     eax, 0FFFFFFFEh
0x18002210a  inc     eax
0x18002210c  jmp     short loc_180022116
0x18002210e  xor     eax, eax
0x180022110  cmp     r8, r9
0x180022113  setnz   al
0x180022116  test    eax, eax
0x180022118  js      short loc_180022129
0x18002211a  lea     rax, [rcx+20h]
0x18002211e  mov     rbx, [rsp+28h+arg_8]
0x180022123  add     rsp, 20h
0x180022127  pop     rdi
0x180022128  retn
0x180022129  lea     rcx, aInvalidMapKTKe; "invalid map<K, T> key"
0x180022130  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
```
