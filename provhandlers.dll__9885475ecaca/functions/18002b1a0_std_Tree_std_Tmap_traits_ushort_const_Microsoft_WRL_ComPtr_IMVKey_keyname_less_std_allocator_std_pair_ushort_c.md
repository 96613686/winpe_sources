# std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::clear(void)

- ea: `0x18002b1a0`
- end: `0x18002b22d`
- name: `?clear@?$_Tree@V?$_Tmap_traits@PEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@Ukeyname_less@@V?$allocator@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@@std@@$0A@@std@@@std@@QEAAXXZ`
- size: `141`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `10`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180026304`
- `0x180026420`
- `0x1800267f4`
- `0x1800269b0`
- `0x180027220`
- `0x180027880`
- `0x18002a190`
- `0x18002eb90`
- `0x1800308d0`
- `0x180032290`

## callees

- `0x18002b108`
- `0x18002b1a0`
- `0x18003f010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18002b1f2`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b1f2`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::clear(
        _QWORD *a1)
{
  _QWORD *v2; // rdi
  _QWORD *i; // rsi
  __int64 v4; // rcx
  __int64 result; // rax

  v2 = *(_QWORD **)(*a1 + 8LL);
  for ( i = v2; !*((_BYTE *)i + 25); v2 = i )
  {
    std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::_Erase(
      (__int64)a1,
      (_QWORD *)i[2]);
    i = (_QWORD *)*i;
    v4 = v2[5];
    if ( v4 )
    {
      v2[5] = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    }
    operator delete(v2);
  }
  *(_QWORD *)(*a1 + 8LL) = *a1;
  *(_QWORD *)*a1 = *a1;
  result = *a1;
  *(_QWORD *)(*a1 + 16LL) = *a1;
  a1[1] = 0;
  return result;
}

```

## disassembly

```asm
0x18002b1a0  mov     [rsp+arg_0], rbx
0x18002b1a5  mov     [rsp+arg_8], rsi
0x18002b1aa  push    rdi
0x18002b1ab  sub     rsp, 20h
0x18002b1af  mov     rbx, rcx
0x18002b1b2  mov     rax, [rcx]
0x18002b1b5  mov     rdi, [rax+8]
0x18002b1b9  mov     rsi, rdi
0x18002b1bc  cmp     byte ptr [rdi+19h], 0
0x18002b1c0  jnz     short loc_18002B201
0x18002b1c2  mov     rdx, [rsi+10h]
0x18002b1c6  mov     rcx, rbx
0x18002b1c9  call    ?_Erase@?$_Tree@V?$_Tmap_traits@PEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@Ukeyname_less@@V?$allocator@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@@std@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::_Erase(std::_Tree_node<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>,void *> *)
0x18002b1ce  mov     rsi, [rsi]
0x18002b1d1  mov     rcx, [rdi+28h]
0x18002b1d5  test    rcx, rcx
0x18002b1d8  jz      short loc_18002B1EF
0x18002b1da  mov     qword ptr [rdi+28h], 0
0x18002b1e2  mov     rax, [rcx]
0x18002b1e5  mov     rax, [rax+10h]
0x18002b1e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b1ee  nop
0x18002b1ef  mov     rcx, rdi
0x18002b1f2  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002b1f8  mov     rdi, rsi
0x18002b1fb  cmp     byte ptr [rsi+19h], 0
0x18002b1ff  jz      short loc_18002B1C2
0x18002b201  mov     rax, [rbx]
0x18002b204  mov     [rax+8], rax
0x18002b208  mov     rax, [rbx]
0x18002b20b  mov     [rax], rax
0x18002b20e  mov     rax, [rbx]
0x18002b211  mov     [rax+10h], rax
0x18002b215  mov     qword ptr [rbx+8], 0
0x18002b21d  mov     rbx, [rsp+28h+arg_0]
0x18002b222  mov     rsi, [rsp+28h+arg_8]
0x18002b227  add     rsp, 20h
0x18002b22b  pop     rdi
0x18002b22c  retn
```
