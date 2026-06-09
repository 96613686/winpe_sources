# std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::_Range_eraser::_Bump_erased(void)

- ea: `0x180005ab0`
- end: `0x180005ad6`
- name: `?_Bump_erased@_Range_eraser@?$_Hash@V?$_Umap_traits@PEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@V?$_Uhash_compare@PEAVMapsBackgroundTransferJob@@U?$hash@PEAVMapsBackgroundTransferJob@@@std@@U?$equal_to@PEAVMapsBackgroundTransferJob@@@3@@3@V?$allocator@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@3@$0A@@std@@@std@@QEAAXXZ`
- size: `38`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000617c`

## callees

- `0x180003df4`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::_Range_eraser::_Bump_erased(
        _QWORD *a1)
{
  _QWORD *v1; // rdx
  __int64 result; // rax

  v1 = (_QWORD *)a1[2];
  a1[2] = *v1;
  std::_List_node<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>,void *>::_Freenode<std::allocator<std::_List_node<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>,void *>>>(
    (__int64)a1,
    v1);
  result = *a1;
  --*(_QWORD *)(*a1 + 8LL);
  return result;
}

```

## disassembly

```asm
0x180005ab0  push    rbx
0x180005ab2  sub     rsp, 20h
0x180005ab6  mov     rdx, [rcx+10h]
0x180005aba  mov     rbx, rcx
0x180005abd  mov     rax, [rdx]
0x180005ac0  mov     [rcx+10h], rax
0x180005ac4  call    ??$_Freenode@V?$allocator@U?$_List_node@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@PEAX@std@@@std@@@?$_List_node@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>,void *>::_Freenode<std::allocator<std::_List_node<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>,void *>>>(std::allocator<std::_List_node<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>,void *>> &,std::_List_node<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>,void *> *)
0x180005ac9  mov     rax, [rbx]
0x180005acc  dec     qword ptr [rax+8]
0x180005ad0  add     rsp, 20h
0x180005ad4  pop     rbx
0x180005ad5  retn
```
