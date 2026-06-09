# std::_Tree<std::_Tmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,0>>::_Copy_nodes<0>(std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,void *> *,std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,void *> *)

- ea: `0x18000c460`
- end: `0x18000c54e`
- name: `??$_Copy_nodes@$0A@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@1@PEAU21@0@Z`
- size: `238`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000c460`
- `0x18000c554`

## callees

- `0x1800034ac`
- `0x180007f40`
- `0x18000c460`
- `0x18000c634`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Copy_nodes<0>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v6; // rbp
  _QWORD *v7; // rsi
  _QWORD *v9; // [rsp+20h] [rbp-48h] BYREF
  _QWORD *v10; // [rsp+28h] [rbp-40h]
  _QWORD *v11; // [rsp+30h] [rbp-38h]

  v6 = *a1;
  if ( *(_BYTE *)(a2 + 25) )
    return (_QWORD *)*a1;
  v9 = a1;
  v7 = operator new(0x60u);
  v10 = v7;
  std::wstring::wstring(v7 + 4, a2 + 32);
  std::wstring::wstring(v7 + 8, a2 + 64);
  *v7 = v6;
  v7[2] = v6;
  *((_WORD *)v7 + 12) = 0;
  v7[1] = a3;
  *((_BYTE *)v7 + 24) = *(_BYTE *)(a2 + 24);
  v9 = a1;
  v10 = a1;
  v11 = v7;
  *v7 = std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Copy_nodes<0>(
          a1,
          *(_QWORD *)a2,
          v7);
  v7[2] = std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Copy_nodes<0>(
            a1,
            *(_QWORD *)(a2 + 16),
            v7);
  v9 = 0;
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_tree_and_orphan_guard<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>::~_Erase_tree_and_orphan_guard<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(&v9);
  return v7;
}

```

## disassembly

```asm
0x18000c460  mov     rax, rsp
0x18000c463  mov     [rax+10h], rbx
0x18000c467  mov     [rax+18h], rbp
0x18000c46b  push    rsi
0x18000c46c  push    rdi
0x18000c46d  push    r12
0x18000c46f  push    r14
0x18000c471  push    r15
0x18000c473  sub     rsp, 40h
0x18000c477  mov     r12, r8
0x18000c47a  mov     r15, rdx
0x18000c47d  mov     r14, rcx
0x18000c480  mov     rbp, [rcx]
0x18000c483  cmp     byte ptr [rdx+19h], 0
0x18000c487  jnz     loc_18000C52F
0x18000c48d  mov     [rax-48h], rcx
0x18000c491  mov     qword ptr [rax-40h], 0
0x18000c499  mov     ecx, 60h ; '`'; Size
0x18000c49e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c4a3  mov     rsi, rax
0x18000c4a6  mov     [rsp+68h+var_40], rax
0x18000c4ab  lea     rbx, [rax+20h]
0x18000c4af  mov     [rsp+68h+arg_0], rbx
0x18000c4b4  lea     rdx, [r15+20h]
0x18000c4b8  mov     rcx, rbx
0x18000c4bb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000c4c0  nop
0x18000c4c1  lea     rdx, [r15+40h]
0x18000c4c5  lea     rcx, [rbx+20h]
0x18000c4c9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000c4ce  nop
0x18000c4cf  mov     [rsi], rbp
0x18000c4d2  mov     [rsi+10h], rbp
0x18000c4d6  mov     word ptr [rsi+18h], 0
0x18000c4dc  mov     [rsi+8], r12
0x18000c4e0  mov     al, [r15+18h]
0x18000c4e4  mov     [rsi+18h], al
0x18000c4e7  mov     [rsp+68h+var_48], r14
0x18000c4ec  mov     [rsp+68h+var_40], r14
0x18000c4f1  mov     [rsp+68h+var_38], rsi
0x18000c4f6  mov     r8, rsi
0x18000c4f9  mov     rdx, [r15]
0x18000c4fc  mov     rcx, r14
0x18000c4ff  call    ??$_Copy_nodes@$0A@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@1@PEAU21@0@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Copy_nodes<0>(std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> *,std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> *)
0x18000c504  mov     [rsi], rax
0x18000c507  mov     r8, rsi
0x18000c50a  mov     rdx, [r15+10h]
0x18000c50e  mov     rcx, r14
0x18000c511  call    ??$_Copy_nodes@$0A@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@1@PEAU21@0@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Copy_nodes<0>(std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> *,std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> *)
0x18000c516  mov     [rsi+10h], rax
0x18000c51a  mov     [rsp+68h+var_48], 0
0x18000c523  lea     rcx, [rsp+68h+var_48]
0x18000c528  call    ??1?$_Erase_tree_and_orphan_guard@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@QEAA@XZ; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_tree_and_orphan_guard<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>::~_Erase_tree_and_orphan_guard<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(void)
0x18000c52d  jmp     short loc_18000C532
0x18000c52f  mov     rsi, rbp
0x18000c532  mov     rax, rsi
0x18000c535  lea     r11, [rsp+68h+var_28]
0x18000c53a  mov     rbx, [r11+38h]
0x18000c53e  mov     rbp, [r11+40h]
0x18000c542  mov     rsp, r11
0x18000c545  pop     r15
0x18000c547  pop     r14
0x18000c549  pop     r12
0x18000c54b  pop     rdi
0x18000c54c  pop     rsi
0x18000c54d  retn
```
