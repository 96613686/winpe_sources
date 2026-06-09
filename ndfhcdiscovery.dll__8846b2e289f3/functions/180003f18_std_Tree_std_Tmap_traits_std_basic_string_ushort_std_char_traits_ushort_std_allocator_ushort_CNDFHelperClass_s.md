# std::_Tree<std::_Tmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,CNDFHelperClass *,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,CNDFHelperClass *>>,0>>::_Copy_nodes<std::integral_constant<bool,0>>(std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,CNDFHelperClass *>,void *> *,std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,CNDFHelperClass *>,void *> *,std::integral_constant<bool,0>)

- ea: `0x180003f18`
- end: `0x180003fa7`
- name: `??$_Copy_nodes@U?$integral_constant@_N$0A@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@@2@$0A@@std@@@std@@IEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@PEAX@1@PEAU21@0U?$integral_constant@_N$0A@@1@@Z`
- size: `143`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003f18`
- `0x1800053a8`

## callees

- `0x180003dfc`
- `0x180003f18`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tmap_traits<std::wstring,CNDFHelperClass *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CNDFHelperClass *>>,0>>::_Copy_nodes<std::integral_constant<bool,0>>(
        __int64 *a1,
        __int64 a2,
        __int64 a3,
        char a4)
{
  __int64 v8; // rsi
  __int64 v9; // rdi
  __int64 v10; // r9

  v8 = *a1;
  if ( !*(_BYTE *)(a2 + 25) )
  {
    v9 = std::_Tree_buy<std::pair<std::wstring const,CNDFHelperClass *>>::_Buynode<std::pair<std::wstring const,CNDFHelperClass *> &>(
           a1,
           a2 + 32);
    *(_QWORD *)(v9 + 8) = a3;
    *(_BYTE *)(v9 + 24) = *(_BYTE *)(a2 + 24);
    if ( *(_BYTE *)(v8 + 25) )
      v8 = v9;
    try
    {
      *(_QWORD *)v9 = ((__int64 (*)(void))std::_Tree<std::_Tmap_traits<std::wstring,CNDFHelperClass *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CNDFHelperClass *>>,0>>::_Copy_nodes<std::integral_constant<bool,0>>)();
      LOBYTE(v10) = a4;
      *(_QWORD *)(v9 + 16) = std::_Tree<std::_Tmap_traits<std::wstring,CNDFHelperClass *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CNDFHelperClass *>>,0>>::_Copy_nodes<std::integral_constant<bool,0>>(
                               a1,
                               *(_QWORD *)(a2 + 16),
                               v9,
                               v10);
    }
    catch ( ... )
    {
      std::_Tree<std::_Tmap_traits<std::wstring,CNDFHelperClass *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CNDFHelperClass *>>,0>>::_Erase(
        a1,
        v8);
      throw;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180003f18  mov     [rsp+arg_10], rbx
0x180003f1d  mov     [rsp+arg_0], rcx
0x180003f22  push    rsi
0x180003f23  push    rdi
0x180003f24  push    r12
0x180003f26  push    r14
0x180003f28  push    r15
0x180003f2a  sub     rsp, 20h
0x180003f2e  mov     bl, r9b
0x180003f31  mov     r12, r8
0x180003f34  mov     r15, rdx
0x180003f37  mov     r14, rcx
0x180003f3a  mov     rsi, [rcx]
0x180003f3d  cmp     byte ptr [rdx+19h], 0
0x180003f41  jnz     short loc_180003F91
0x180003f43  add     rdx, 20h ; ' '
0x180003f47  call    ??$_Buynode@AEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@@?$_Tree_buy@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@@2@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@PEAX@1@AEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@1@@Z; std::_Tree_buy<std::pair<std::wstring const,CNDFHelperClass *>>::_Buynode<std::pair<std::wstring const,CNDFHelperClass *> &>(std::pair<std::wstring const,CNDFHelperClass *> &)
0x180003f4c  mov     rdi, rax
0x180003f4f  mov     [rax+8], r12
0x180003f53  mov     al, [r15+18h]
0x180003f57  mov     [rdi+18h], al
0x180003f5a  cmp     byte ptr [rsi+19h], 0
0x180003f5e  cmovnz  rsi, rdi
0x180003f62  mov     [rsp+48h+arg_8], rsi
0x180003f67  mov     r9b, bl
0x180003f6a  mov     r8, rdi
0x180003f6d  mov     rdx, [r15]
0x180003f70  mov     rcx, r14
0x180003f73  call    ??$_Copy_nodes@U?$integral_constant@_N$0A@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@@2@$0A@@std@@@std@@IEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@PEAX@1@PEAU21@0U?$integral_constant@_N$0A@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,CNDFHelperClass *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CNDFHelperClass *>>,0>>::_Copy_nodes<std::integral_constant<bool,0>>(std::_Tree_node<std::pair<std::wstring const,CNDFHelperClass *>,void *> *,std::_Tree_node<std::pair<std::wstring const,CNDFHelperClass *>,void *> *,std::integral_constant<bool,0>)
0x180003f78  mov     [rdi], rax
0x180003f7b  mov     r9b, bl
0x180003f7e  mov     r8, rdi
0x180003f81  mov     rdx, [r15+10h]
0x180003f85  mov     rcx, r14
0x180003f88  call    ??$_Copy_nodes@U?$integral_constant@_N$0A@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@@2@$0A@@std@@@std@@IEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@PEAX@1@PEAU21@0U?$integral_constant@_N$0A@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,CNDFHelperClass *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CNDFHelperClass *>>,0>>::_Copy_nodes<std::integral_constant<bool,0>>(std::_Tree_node<std::pair<std::wstring const,CNDFHelperClass *>,void *> *,std::_Tree_node<std::pair<std::wstring const,CNDFHelperClass *>,void *> *,std::integral_constant<bool,0>)
0x180003f8d  mov     [rdi+10h], rax
0x180003f91  mov     rax, rsi
0x180003f94  mov     rbx, [rsp+48h+arg_10]
0x180003f99  add     rsp, 20h
0x180003f9d  pop     r15
0x180003f9f  pop     r14
0x180003fa1  pop     r12
0x180003fa3  pop     rdi
0x180003fa4  pop     rsi
0x180003fa5  retn
```
