# std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::_Destroy_if_not_nil(std::_Tree_node<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>,void *> *)

- ea: `0x18002b0cc`
- end: `0x18002b102`
- name: `?_Destroy_if_not_nil@?$_Tree@V?$_Tmap_traits@PEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@Ukeyname_less@@V?$allocator@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@@std@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@PEAX@2@@Z`
- size: `54`
- prototype: `void __fastcall(__int64, _QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180025c68`
- `0x18003cd08`

## callees

- `0x18002b0cc`
- `0x18003f010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18002b0fb`

## pseudocode

```c
void __fastcall std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::_Destroy_if_not_nil(
        __int64 a1,
        _QWORD *a2)
{
  __int64 v3; // rcx

  v3 = a2[5];
  if ( v3 )
  {
    a2[5] = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  operator delete(a2);
}

```

## disassembly

```asm
0x18002b0cc  push    rbx
0x18002b0ce  sub     rsp, 20h
0x18002b0d2  mov     rbx, rdx
0x18002b0d5  mov     rcx, [rdx+28h]
0x18002b0d9  test    rcx, rcx
0x18002b0dc  jz      short loc_18002B0F3
0x18002b0de  mov     qword ptr [rdx+28h], 0
0x18002b0e6  mov     rax, [rcx]
0x18002b0e9  mov     rax, [rax+10h]
0x18002b0ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b0f2  nop
0x18002b0f3  mov     rcx, rbx
0x18002b0f6  add     rsp, 20h
0x18002b0fa  pop     rbx
0x18002b0fb  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
