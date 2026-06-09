# std::unique_ptr<ProfileSelection,std::default_delete<ProfileSelection>>::~unique_ptr<ProfileSelection,std::default_delete<ProfileSelection>>(void)

- ea: `0x180026420`
- end: `0x180026450`
- name: `??1?$unique_ptr@VProfileSelection@@U?$default_delete@VProfileSelection@@@std@@@std@@QEAA@XZ`
- size: `48`
- prototype: `void __fastcall(void ***)`
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003ce1b`
- `0x18003ce2d`
- `0x18003cec5`
- `0x18003d04b`
- `0x18003d6e1`

## callees

- `0x180026420`
- `0x18002b1a0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180026439`
- `msvcrt!??3@YAXPEAX@Z` at `0x180026443`
- `msvcrt!??3@YAXPEAX@Z` at `0x180026439`
- `msvcrt!??3@YAXPEAX@Z` at `0x180026443`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall std::unique_ptr<ProfileSelection>::~unique_ptr<ProfileSelection>(void ***a1)
{
  void **v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::clear(*a1);
    operator delete(*v1);
    operator delete(v1);
  }
}

```

## disassembly

```asm
0x180026420  push    rbx
0x180026422  sub     rsp, 20h
0x180026426  mov     rbx, [rcx]
0x180026429  test    rbx, rbx
0x18002642c  jz      short loc_18002644A
0x18002642e  mov     rcx, rbx
0x180026431  call    ?clear@?$_Tree@V?$_Tmap_traits@PEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@Ukeyname_less@@V?$allocator@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@@std@@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::clear(void)
0x180026436  mov     rcx, [rbx]
0x180026439  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002643f  nop
0x180026440  mov     rcx, rbx
0x180026443  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180026449  nop
0x18002644a  add     rsp, 20h
0x18002644e  pop     rbx
0x18002644f  retn
```
