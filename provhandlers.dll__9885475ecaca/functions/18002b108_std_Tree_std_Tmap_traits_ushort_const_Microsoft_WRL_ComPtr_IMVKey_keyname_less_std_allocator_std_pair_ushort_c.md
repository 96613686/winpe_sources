# std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::_Erase(std::_Tree_node<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>,void *> *)

- ea: `0x18002b108`
- end: `0x18002b175`
- name: `?_Erase@?$_Tree@V?$_Tmap_traits@PEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@Ukeyname_less@@V?$allocator@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@@std@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@PEAX@2@@Z`
- size: `109`
- prototype: `void __fastcall(__int64, _QWORD *)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002b108`
- `0x18002b1a0`
- `0x18003d183`

## callees

- `0x18002b108`
- `0x18003f010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18002b156`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b156`

## pseudocode

```c
void __fastcall std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::_Erase(
        __int64 a1,
        _QWORD *a2)
{
  _QWORD *v2; // rbx
  _QWORD *i; // rdi
  __int64 v5; // rcx

  v2 = a2;
  for ( i = a2; !*((_BYTE *)i + 25); v2 = i )
  {
    std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::_Erase(
      a1,
      i[2]);
    i = (_QWORD *)*i;
    v5 = v2[5];
    if ( v5 )
    {
      v2[5] = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
    operator delete(v2);
  }
}

```

## disassembly

```asm
0x18002b108  mov     [rsp+arg_0], rbx
0x18002b10d  mov     [rsp+arg_8], rsi
0x18002b112  push    rdi
0x18002b113  sub     rsp, 20h
0x18002b117  mov     rbx, rdx
0x18002b11a  mov     rsi, rcx
0x18002b11d  mov     rdi, rdx
0x18002b120  cmp     byte ptr [rdx+19h], 0
0x18002b124  jnz     short loc_18002B165
0x18002b126  mov     rdx, [rdi+10h]
0x18002b12a  mov     rcx, rsi
0x18002b12d  call    ?_Erase@?$_Tree@V?$_Tmap_traits@PEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@Ukeyname_less@@V?$allocator@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@@std@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::_Erase(std::_Tree_node<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>,void *> *)
0x18002b132  mov     rdi, [rdi]
0x18002b135  mov     rcx, [rbx+28h]
0x18002b139  test    rcx, rcx
0x18002b13c  jz      short loc_18002B153
0x18002b13e  mov     qword ptr [rbx+28h], 0
0x18002b146  mov     rax, [rcx]
0x18002b149  mov     rax, [rax+10h]
0x18002b14d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b152  nop
0x18002b153  mov     rcx, rbx
0x18002b156  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002b15c  mov     rbx, rdi
0x18002b15f  cmp     byte ptr [rdi+19h], 0
0x18002b163  jz      short loc_18002B126
0x18002b165  mov     rbx, [rsp+28h+arg_0]
0x18002b16a  mov     rsi, [rsp+28h+arg_8]
0x18002b16f  add     rsp, 20h
0x18002b173  pop     rdi
0x18002b174  retn
```
