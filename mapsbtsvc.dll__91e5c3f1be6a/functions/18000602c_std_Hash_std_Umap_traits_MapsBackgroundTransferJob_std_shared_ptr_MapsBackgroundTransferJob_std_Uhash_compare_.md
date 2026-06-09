# std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::_Insert_new_node_before(unsigned __int64,std::_List_node<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>,void *> * const,std::_List_node<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>,void *> * const)

- ea: `0x18000602c`
- end: `0x180006087`
- name: `?_Insert_new_node_before@?$_Hash@V?$_Umap_traits@PEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@V?$_Uhash_compare@PEAVMapsBackgroundTransferJob@@U?$hash@PEAVMapsBackgroundTransferJob@@@std@@U?$equal_to@PEAVMapsBackgroundTransferJob@@@3@@3@V?$allocator@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@3@$0A@@std@@@std@@IEAAPEAU?$_List_node@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@PEAX@2@_KQEAU32@1@Z`
- size: `91`
- prototype: `_QWORD *__fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003eac`

## callees

- `0x18000602c`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::_Insert_new_node_before(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  _QWORD *v4; // r10
  __int64 v5; // rcx
  __int64 v6; // rax
  __int64 v7; // rdx

  v4 = *(_QWORD **)(a3 + 8);
  ++qword_18001D830;
  *a4 = a3;
  a4[1] = v4;
  *v4 = a4;
  *(_QWORD *)(a3 + 8) = a4;
  v5 = qword_18001D838;
  v6 = 2 * (a2 & qword_18001D850);
  v7 = *(_QWORD *)(qword_18001D838 + 16 * (a2 & qword_18001D850));
  if ( v7 == qword_18001D828 )
  {
    *(_QWORD *)(qword_18001D838 + 8 * v6) = a4;
LABEL_6:
    *(_QWORD *)(v5 + 8 * v6 + 8) = a4;
    return a4;
  }
  if ( v7 == a3 )
  {
    *(_QWORD *)(qword_18001D838 + 8 * v6) = a4;
  }
  else if ( *(_QWORD **)(qword_18001D838 + 8 * v6 + 8) == v4 )
  {
    goto LABEL_6;
  }
  return a4;
}

```

## disassembly

```asm
0x18000602c  mov     r10, [r8+8]
0x180006030  inc     cs:qword_18001D830
0x180006037  mov     [r9], r8
0x18000603a  mov     [r9+8], r10
0x18000603e  mov     [r10], r9
0x180006041  mov     [r8+8], r9
0x180006045  mov     rax, cs:qword_18001D850
0x18000604c  mov     rcx, cs:qword_18001D838
0x180006053  and     rax, rdx
0x180006056  add     rax, rax
0x180006059  mov     rdx, [rcx+rax*8]
0x18000605d  cmp     rdx, cs:qword_18001D828
0x180006064  jnz     short loc_18000606C
0x180006066  mov     [rcx+rax*8], r9
0x18000606a  jmp     short loc_18000607E
0x18000606c  cmp     rdx, r8
0x18000606f  jnz     short loc_180006077
0x180006071  mov     [rcx+rax*8], r9
0x180006075  jmp     short loc_180006083
0x180006077  cmp     [rcx+rax*8+8], r10
0x18000607c  jnz     short loc_180006083
0x18000607e  mov     [rcx+rax*8+8], r9
0x180006083  mov     rax, r9
0x180006086  retn
```
