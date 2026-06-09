# std::_Tree<std::_Tset_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *>,0>>::emplace<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> * const &>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> * const &)

- ea: `0x14000549c`
- end: `0x14000559f`
- name: `??$emplace@AEBQEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tset_traits@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@AEBQEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z`
- size: `259`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64 *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140005bd0`
- `0x140008590`
- `0x140008a38`

## callees

- `0x140001c74`
- `0x14000549c`
- `0x140009aac`
- `0x140009cdc`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tset_traits<std::wstring *,std::less<std::wstring *>,std::allocator<std::wstring *>,0>>::emplace<std::wstring * const &>(
        __int64 *a1,
        __int64 a2,
        __int64 *a3)
{
  __int64 v6; // rbp
  __int64 v7; // rax
  unsigned int v8; // esi
  __int64 inserted; // r9
  char v10; // di
  __int64 *v11; // r12
  __int64 *v12; // rax
  __int64 *v14; // [rsp+20h] [rbp-38h] BYREF
  __int64 v15; // [rsp+28h] [rbp-30h]

  v6 = *a1;
  v7 = *(_QWORD *)(*a1 + 8);
  v8 = 0;
  inserted = *a1;
  v10 = 1;
  if ( *(_BYTE *)(v7 + 25) )
  {
    v11 = *(__int64 **)(*a1 + 8);
  }
  else
  {
    do
    {
      v11 = (__int64 *)v7;
      if ( *(_QWORD *)(v7 + 32) >= (unsigned __int64)*a3 )
      {
        v8 = 1;
        inserted = v7;
        v7 = *(_QWORD *)v7;
      }
      else
      {
        v8 = 0;
        v7 = *(_QWORD *)(v7 + 16);
      }
    }
    while ( !*(_BYTE *)(v7 + 25) );
  }
  if ( *(_BYTE *)(inserted + 25) || (unsigned __int64)*a3 < *(_QWORD *)(inserted + 32) )
  {
    if ( a1[1] == 0x666666666666666LL )
      std::_Throw_tree_length_error();
    v14 = a1;
    v15 = 0;
    v12 = (__int64 *)operator new(0x28u);
    v12[4] = *a3;
    *v12 = v6;
    v12[1] = v6;
    v12[2] = v6;
    *((_WORD *)v12 + 12) = 0;
    v14 = v11;
    v15 = v8;
    inserted = std::_Tree_val<std::_Tree_simple_types<std::wstring *>>::_Insert_node(a1, &v14);
  }
  else
  {
    v10 = 0;
  }
  *(_QWORD *)a2 = inserted;
  *(_BYTE *)(a2 + 8) = v10;
  return a2;
}

```

## disassembly

```asm
0x14000549c  mov     [rsp+arg_8], rbx
0x1400054a1  mov     [rsp+arg_10], rbp
0x1400054a6  push    rsi
0x1400054a7  push    rdi
0x1400054a8  push    r12
0x1400054aa  push    r14
0x1400054ac  push    r15
0x1400054ae  sub     rsp, 30h
0x1400054b2  mov     r14, r8
0x1400054b5  mov     rbx, rdx
0x1400054b8  mov     r15, rcx
0x1400054bb  mov     rbp, [rcx]
0x1400054be  mov     rax, [rbp+8]
0x1400054c2  xor     esi, esi
0x1400054c4  xor     ecx, ecx
0x1400054c6  mov     [rsp+58h+arg_0], rcx
0x1400054cb  mov     r9, rbp
0x1400054ce  lea     edi, [rsi+1]
0x1400054d1  cmp     [rax+19h], cl
0x1400054d4  jnz     short loc_1400054FA
0x1400054d6  mov     rcx, [r8]
0x1400054d9  mov     r12, rax
0x1400054dc  cmp     [rax+20h], rcx
0x1400054e0  jnb     short loc_1400054EA
0x1400054e2  xor     esi, esi
0x1400054e4  mov     rax, [rax+10h]
0x1400054e8  jmp     short loc_1400054F2
0x1400054ea  mov     esi, edi
0x1400054ec  mov     r9, rax
0x1400054ef  mov     rax, [rax]
0x1400054f2  cmp     byte ptr [rax+19h], 0
0x1400054f6  jz      short loc_1400054D9
0x1400054f8  jmp     short loc_1400054FD
0x1400054fa  mov     r12, rax
0x1400054fd  cmp     byte ptr [r9+19h], 0
0x140005502  jnz     short loc_140005512
0x140005504  mov     rax, [r9+20h]
0x140005508  cmp     [r8], rax
0x14000550b  jb      short loc_140005512
0x14000550d  xor     dil, dil
0x140005510  jmp     short loc_140005578
0x140005512  mov     rax, 666666666666666h
0x14000551c  cmp     [r15+8], rax
0x140005520  jz      short loc_140005599
0x140005522  mov     [rsp+58h+var_38], r15
0x140005527  mov     [rsp+58h+var_30], 0
0x140005530  mov     ecx, 28h ; '('; Size
0x140005535  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000553a  mov     r8, rax
0x14000553d  mov     rax, [r14]
0x140005540  mov     [r8+20h], rax
0x140005544  mov     [r8], rbp
0x140005547  mov     [r8+8], rbp
0x14000554b  mov     [r8+10h], rbp
0x14000554f  mov     word ptr [r8+18h], 0
0x140005556  mov     [rsp+58h+var_38], r12
0x14000555b  mov     dword ptr [rsp+58h+var_30], esi
0x14000555f  mov     rax, [rsp+58h+arg_0]
0x140005564  mov     dword ptr [rsp+58h+var_30+4], eax
0x140005568  lea     rdx, [rsp+58h+var_38]
0x14000556d  mov     rcx, r15
0x140005570  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::wstring *>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::wstring *,void *> *>,std::_Tree_node<std::wstring *,void *> * const)
0x140005575  mov     r9, rax
0x140005578  mov     [rbx], r9
0x14000557b  mov     [rbx+8], dil
0x14000557f  mov     rax, rbx
0x140005582  mov     rbx, [rsp+58h+arg_8]
0x140005587  mov     rbp, [rsp+58h+arg_10]
0x14000558c  add     rsp, 30h
0x140005590  pop     r15
0x140005592  pop     r14
0x140005594  pop     r12
0x140005596  pop     rdi
0x140005597  pop     rsi
0x140005598  retn
0x140005599  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
