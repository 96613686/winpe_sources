# std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::_Erase<MapsBackgroundTransferJob *>(MapsBackgroundTransferJob * const &)

- ea: `0x180003cac`
- end: `0x180003d4c`
- name: `??$_Erase@PEAVMapsBackgroundTransferJob@@@?$_Hash@V?$_Umap_traits@PEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@V?$_Uhash_compare@PEAVMapsBackgroundTransferJob@@U?$hash@PEAVMapsBackgroundTransferJob@@@std@@U?$equal_to@PEAVMapsBackgroundTransferJob@@@3@@3@V?$allocator@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@3@$0A@@std@@@std@@AEAA_KAEBQEAVMapsBackgroundTransferJob@@@Z`
- size: `160`
- prototype: `__int64 __fastcall(__int64, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180005000`

## callees

- `0x180003cac`
- `0x180003d54`
- `0x180003df4`
- `0x180004860`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::_Erase<MapsBackgroundTransferJob *>(
        __int64 a1,
        unsigned __int8 *a2)
{
  __int64 v2; // rbx
  __int64 v3; // rcx
  __int64 v4; // r11
  _QWORD *v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // r8
  __int64 v10; // rcx
  _BYTE v12[24]; // [rsp+20h] [rbp-18h] BYREF

  v2 = std::_Conditionally_enabled_hash<MapsBackgroundTransferJob *,1>::operator()(a2);
  v5 = *(_QWORD **)(std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::_Find_last<MapsBackgroundTransferJob *>(
                      v3,
                      v12,
                      v4,
                      v2)
                  + 8);
  if ( !v5 )
    return 0;
  v6 = qword_18001D838;
  v7 = 2 * (v2 & qword_18001D850);
  if ( *(_QWORD **)(qword_18001D838 + 16 * (v2 & qword_18001D850) + 8) == v5 )
  {
    if ( *(_QWORD **)(qword_18001D838 + 16 * (v2 & qword_18001D850)) == v5 )
    {
      v8 = qword_18001D828;
      *(_QWORD *)(qword_18001D838 + 16 * (v2 & qword_18001D850)) = qword_18001D828;
    }
    else
    {
      v8 = v5[1];
    }
    *(_QWORD *)(v6 + 8 * v7 + 8) = v8;
  }
  else if ( *(_QWORD **)(qword_18001D838 + 16 * (v2 & qword_18001D850)) == v5 )
  {
    *(_QWORD *)(qword_18001D838 + 16 * (v2 & qword_18001D850)) = *v5;
  }
  v9 = *v5;
  --qword_18001D830;
  *(_QWORD *)v5[1] = v9;
  v10 = v5[1];
  *(_QWORD *)(v9 + 8) = v10;
  std::_List_node<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>,void *>::_Freenode<std::allocator<std::_List_node<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>,void *>>>(
    v10,
    v5);
  return 1;
}

```

## disassembly

```asm
0x180003cac  push    rbx
0x180003cae  sub     rsp, 30h
0x180003cb2  mov     rcx, rdx; unsigned __int8 *
0x180003cb5  mov     r11, rdx
0x180003cb8  call    ??R?$_Conditionally_enabled_hash@PEAVMapsBackgroundTransferJob@@$00@std@@SA_KAEBQEAVMapsBackgroundTransferJob@@@Z; std::_Conditionally_enabled_hash<MapsBackgroundTransferJob *,1>::operator()(MapsBackgroundTransferJob * const &)
0x180003cbd  mov     r9, rax
0x180003cc0  lea     rdx, [rsp+38h+var_18]
0x180003cc5  mov     r8, r11
0x180003cc8  mov     rbx, rax
0x180003ccb  call    ??$_Find_last@PEAVMapsBackgroundTransferJob@@@?$_Hash@V?$_Umap_traits@PEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@V?$_Uhash_compare@PEAVMapsBackgroundTransferJob@@U?$hash@PEAVMapsBackgroundTransferJob@@@std@@U?$equal_to@PEAVMapsBackgroundTransferJob@@@3@@3@V?$allocator@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@3@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@PEAX@std@@@1@AEBQEAVMapsBackgroundTransferJob@@_K@Z; std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::_Find_last<MapsBackgroundTransferJob *>(MapsBackgroundTransferJob * const &,unsigned __int64)
0x180003cd0  mov     rdx, [rax+8]
0x180003cd4  test    rdx, rdx
0x180003cd7  jz      short loc_180003D44
0x180003cd9  mov     rcx, cs:qword_18001D850
0x180003ce0  mov     r8, cs:qword_18001D838
0x180003ce7  and     rcx, rbx
0x180003cea  add     rcx, rcx
0x180003ced  cmp     [r8+rcx*8+8], rdx
0x180003cf2  jnz     short loc_180003D12
0x180003cf4  cmp     [r8+rcx*8], rdx
0x180003cf8  jnz     short loc_180003D07
0x180003cfa  mov     rax, cs:qword_18001D828
0x180003d01  mov     [r8+rcx*8], rax
0x180003d05  jmp     short loc_180003D0B
0x180003d07  mov     rax, [rdx+8]
0x180003d0b  mov     [r8+rcx*8+8], rax
0x180003d10  jmp     short loc_180003D1F
0x180003d12  cmp     [r8+rcx*8], rdx
0x180003d16  jnz     short loc_180003D1F
0x180003d18  mov     rax, [rdx]
0x180003d1b  mov     [r8+rcx*8], rax
0x180003d1f  mov     r8, [rdx]
0x180003d22  dec     cs:qword_18001D830
0x180003d29  mov     rcx, [rdx+8]
0x180003d2d  mov     [rcx], r8
0x180003d30  mov     rcx, [rdx+8]
0x180003d34  mov     [r8+8], rcx
0x180003d38  call    ??$_Freenode@V?$allocator@U?$_List_node@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@PEAX@std@@@std@@@?$_List_node@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>,void *>::_Freenode<std::allocator<std::_List_node<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>,void *>>>(std::allocator<std::_List_node<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>,void *>> &,std::_List_node<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>,void *> *)
0x180003d3d  mov     eax, 1
0x180003d42  jmp     short loc_180003D46
0x180003d44  xor     eax, eax
0x180003d46  add     rsp, 30h
0x180003d4a  pop     rbx
0x180003d4b  retn
```
