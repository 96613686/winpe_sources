# std::_Tree<std::_Tmap_traits<IProvSource const *,Microsoft::WRL::ComPtr<IMVMasterDatastore>,std::less<IProvSource const *>,std::allocator<std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>>>,0>>::~_Tree<std::_Tmap_traits<IProvSource const *,Microsoft::WRL::ComPtr<IMVMasterDatastore>,std::less<IProvSource const *>,std::allocator<std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>>>,0>>(void)

- ea: `0x180010088`
- end: `0x18001011e`
- name: `??1?$_Tree@V?$_Tmap_traits@PEBUIProvSource@@V?$ComPtr@UIMVMasterDatastore@@@WRL@Microsoft@@U?$less@PEBUIProvSource@@@std@@V?$allocator@U?$pair@QEBUIProvSource@@V?$ComPtr@UIMVMasterDatastore@@@WRL@Microsoft@@@std@@@6@$0A@@std@@@std@@QEAA@XZ`
- size: `150`
- prototype: `void __fastcall(void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001051c`
- `0x180010d34`

## callees

- `0x180010088`
- `0x180021100`
- `0x180047010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800100da`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800100da`
- `msvcrt!??3@YAXPEAX@Z` at `0x180010117`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall std::_Tree<std::_Tmap_traits<IProvSource const *,Microsoft::WRL::ComPtr<IMVMasterDatastore>,std::less<IProvSource const *>,std::allocator<std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>>>,0>>::~_Tree<std::_Tmap_traits<IProvSource const *,Microsoft::WRL::ComPtr<IMVMasterDatastore>,std::less<IProvSource const *>,std::allocator<std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>>>,0>>(
        void **a1)
{
  _QWORD *v2; // rdi
  _QWORD *i; // rsi
  __int64 v4; // rcx

  v2 = (_QWORD *)*((_QWORD *)*a1 + 1);
  for ( i = v2; !*((_BYTE *)i + 25); v2 = i )
  {
    std::_Tree<std::_Tmap_traits<IProvSource const *,Microsoft::WRL::ComPtr<IMVMasterDatastore>,std::less<IProvSource const *>,std::allocator<std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>>>,0>>::_Erase(
      a1,
      i[2]);
    i = (_QWORD *)*i;
    v4 = v2[5];
    if ( v4 )
    {
      v2[5] = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    }
    operator delete(v2);
  }
  *((_QWORD *)*a1 + 1) = *a1;
  *(_QWORD *)*a1 = *a1;
  *((_QWORD *)*a1 + 2) = *a1;
  a1[1] = 0;
  operator delete(*a1);
}

```

## disassembly

```asm
0x180010088  mov     [rsp+arg_0], rbx
0x18001008d  mov     [rsp+arg_8], rsi
0x180010092  push    rdi
0x180010093  sub     rsp, 20h
0x180010097  mov     rbx, rcx
0x18001009a  mov     rax, [rcx]
0x18001009d  mov     rdi, [rax+8]
0x1800100a1  mov     rsi, rdi
0x1800100a4  cmp     byte ptr [rdi+19h], 0
0x1800100a8  jnz     short loc_1800100E9
0x1800100aa  mov     rdx, [rsi+10h]
0x1800100ae  mov     rcx, rbx
0x1800100b1  call    ?_Erase@?$_Tree@V?$_Tmap_traits@PEBUIProvSource@@V?$ComPtr@UIMVMasterDatastore@@@WRL@Microsoft@@U?$less@PEBUIProvSource@@@std@@V?$allocator@U?$pair@QEBUIProvSource@@V?$ComPtr@UIMVMasterDatastore@@@WRL@Microsoft@@@std@@@6@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@QEBUIProvSource@@V?$ComPtr@UIMVMasterDatastore@@@WRL@Microsoft@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<IProvSource const *,Microsoft::WRL::ComPtr<IMVMasterDatastore>,std::less<IProvSource const *>,std::allocator<std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>>>,0>>::_Erase(std::_Tree_node<std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>>,void *> *)
0x1800100b6  mov     rsi, [rsi]
0x1800100b9  mov     rcx, [rdi+28h]
0x1800100bd  test    rcx, rcx
0x1800100c0  jz      short loc_1800100D7
0x1800100c2  mov     qword ptr [rdi+28h], 0
0x1800100ca  mov     rax, [rcx]
0x1800100cd  mov     rax, [rax+10h]
0x1800100d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100d6  nop
0x1800100d7  mov     rcx, rdi
0x1800100da  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800100e0  mov     rdi, rsi
0x1800100e3  cmp     byte ptr [rsi+19h], 0
0x1800100e7  jz      short loc_1800100AA
0x1800100e9  mov     rax, [rbx]
0x1800100ec  mov     [rax+8], rax
0x1800100f0  mov     rax, [rbx]
0x1800100f3  mov     [rax], rax
0x1800100f6  mov     rax, [rbx]
0x1800100f9  mov     [rax+10h], rax
0x1800100fd  mov     qword ptr [rbx+8], 0
0x180010105  mov     rcx, [rbx]
0x180010108  mov     rbx, [rsp+28h+arg_0]
0x18001010d  mov     rsi, [rsp+28h+arg_8]
0x180010112  add     rsp, 20h
0x180010116  pop     rdi
0x180010117  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
