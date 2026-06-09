# std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::_Find_last<MapsBackgroundTransferJob *>(MapsBackgroundTransferJob * const &,unsigned __int64)

- ea: `0x180003d54`
- end: `0x180003db4`
- name: `??$_Find_last@PEAVMapsBackgroundTransferJob@@@?$_Hash@V?$_Umap_traits@PEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@V?$_Uhash_compare@PEAVMapsBackgroundTransferJob@@U?$hash@PEAVMapsBackgroundTransferJob@@@std@@U?$equal_to@PEAVMapsBackgroundTransferJob@@@3@@3@V?$allocator@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@3@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@PEAX@std@@@1@AEBQEAVMapsBackgroundTransferJob@@_K@Z`
- size: `96`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, _QWORD *, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003cac`
- `0x180003eac`

## callees

- `0x180003d54`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::_Find_last<MapsBackgroundTransferJob *>(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3,
        __int64 a4)
{
  _QWORD *v4; // rcx

  v4 = *(_QWORD **)(qword_18001D838 + 16 * (a4 & qword_18001D850) + 8);
  if ( v4 == (_QWORD *)qword_18001D828 )
  {
    *a2 = qword_18001D828;
LABEL_3:
    a2[1] = 0;
  }
  else
  {
    while ( *a3 != v4[2] )
    {
      if ( v4 == *(_QWORD **)(qword_18001D838 + 16 * (a4 & qword_18001D850)) )
      {
        *a2 = v4;
        goto LABEL_3;
      }
      v4 = (_QWORD *)v4[1];
    }
    *a2 = *v4;
    a2[1] = v4;
  }
  return a2;
}

```

## disassembly

```asm
0x180003d54  mov     rax, cs:qword_18001D850
0x180003d5b  mov     r10, r8
0x180003d5e  mov     r8, cs:qword_18001D838
0x180003d65  and     rax, r9
0x180003d68  mov     r9, cs:qword_18001D828
0x180003d6f  add     rax, rax
0x180003d72  mov     rcx, [r8+rax*8+8]
0x180003d77  cmp     rcx, r9
0x180003d7a  jnz     short loc_180003D89
0x180003d7c  mov     [rdx], r9
0x180003d7f  mov     qword ptr [rdx+8], 0
0x180003d87  jmp     short loc_180003DB0
0x180003d89  mov     r8, [r8+rax*8]
0x180003d8d  mov     rax, [r10]
0x180003d90  cmp     rax, [rcx+10h]
0x180003d94  jz      short loc_180003DA6
0x180003d96  cmp     rcx, r8
0x180003d99  jz      short loc_180003DA1
0x180003d9b  mov     rcx, [rcx+8]
0x180003d9f  jmp     short loc_180003D90
0x180003da1  mov     [rdx], rcx
0x180003da4  jmp     short loc_180003D7F
0x180003da6  mov     rax, [rcx]
0x180003da9  mov     [rdx], rax
0x180003dac  mov     [rdx+8], rcx
0x180003db0  mov     rax, rdx
0x180003db3  retn
```
