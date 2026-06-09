# std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::_Unchecked_erase(std::_List_node<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>,void *> *,std::_List_node<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>,void *> * const)

- ea: `0x18000617c`
- end: `0x1800062a6`
- name: `?_Unchecked_erase@?$_Hash@V?$_Umap_traits@PEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@V?$_Uhash_compare@PEAVMapsBackgroundTransferJob@@U?$hash@PEAVMapsBackgroundTransferJob@@@std@@U?$equal_to@PEAVMapsBackgroundTransferJob@@@3@@3@V?$allocator@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@3@$0A@@std@@@std@@AEAAPEAU?$_List_node@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@PEAX@2@PEAU32@QEAU32@@Z`
- size: `298`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180004730`

## callees

- `0x180004860`
- `0x180005ab0`
- `0x18000617c`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::_Unchecked_erase(
        _QWORD *a1,
        __int64 a2,
        __int64 a3)
{
  _QWORD *v6; // r12
  __int64 v7; // rsi
  _QWORD *v8; // r15
  __int64 v9; // rax
  __int64 v10; // r11
  __int64 v11; // r14
  __int64 v12; // rax
  __int64 v13; // r13
  bool v14; // bl
  _QWORD *v15; // rax
  __int64 v17; // rax
  __int64 v18; // r12
  bool v19; // bl
  _QWORD *v20; // [rsp+20h] [rbp-58h] BYREF
  _QWORD *v21; // [rsp+28h] [rbp-50h]
  __int64 v22; // [rsp+30h] [rbp-48h]
  __int64 v24; // [rsp+88h] [rbp+10h]

  if ( a2 != a3 )
  {
    v6 = *(_QWORD **)(a2 + 8);
    v7 = a1[3];
    v8 = (_QWORD *)a1[1];
    v20 = a1 + 1;
    v21 = v6;
    v22 = a2;
    v9 = std::_Conditionally_enabled_hash<MapsBackgroundTransferJob *,1>::operator()((unsigned __int8 *)(a2 + 16));
    v11 = 2 * (a1[6] & v9);
    v12 = *(_QWORD *)(v7 + 16 * (a1[6] & v9) + 8);
    v13 = *(_QWORD *)(v7 + 8 * v11);
    v24 = *(_QWORD *)(v7 + 8 * v11 + 8);
    while ( 1 )
    {
      v14 = v10 == v12;
      std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::_Range_eraser::_Bump_erased(&v20);
      if ( v14 )
        break;
      v10 = v22;
      v12 = v24;
      if ( v22 == a3 )
      {
        if ( v13 == a2 )
LABEL_6:
          *(_QWORD *)(v7 + 8 * v11) = v10;
        goto LABEL_7;
      }
    }
    if ( v13 == a2 )
    {
      *(_QWORD *)(v7 + 8 * v11) = v8;
      v6 = v8;
    }
    for ( *(_QWORD *)(v7 + 8 * v11 + 8) = v6; ; *(_QWORD *)(v7 + 8 * v11 + 8) = v8 )
    {
      v10 = v22;
      if ( v22 == a3 )
        break;
      v17 = std::_Conditionally_enabled_hash<MapsBackgroundTransferJob *,1>::operator()((unsigned __int8 *)(v22 + 16));
      v11 = 2 * (a1[6] & v17);
      v18 = *(_QWORD *)(v7 + 16 * (a1[6] & v17) + 8);
      while ( 1 )
      {
        v19 = v10 == v18;
        std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::_Range_eraser::_Bump_erased(&v20);
        if ( v19 )
          break;
        v10 = v22;
        if ( v22 == a3 )
          goto LABEL_6;
      }
      *(_QWORD *)(v7 + 8 * v11) = v8;
    }
LABEL_7:
    v15 = v21;
    *v21 = v10;
    *(_QWORD *)(v10 + 8) = v15;
  }
  return a3;
}

```

## disassembly

```asm
0x18000617c  mov     r11, rsp
0x18000617f  mov     [r11+18h], rbx
0x180006183  mov     [r11+8], rcx
0x180006187  push    rbp
0x180006188  push    rsi
0x180006189  push    rdi
0x18000618a  push    r12
0x18000618c  push    r13
0x18000618e  push    r14
0x180006190  push    r15
0x180006192  sub     rsp, 40h
0x180006196  mov     rdi, r8
0x180006199  mov     rbp, rdx
0x18000619c  mov     rbx, rcx
0x18000619f  cmp     rdx, r8
0x1800061a2  jz      short loc_180006222
0x1800061a4  mov     r12, [rdx+8]
0x1800061a8  lea     rax, [rcx+8]
0x1800061ac  mov     rsi, [rcx+18h]
0x1800061b0  lea     rcx, [rdx+10h]; unsigned __int8 *
0x1800061b4  mov     r15, [rax]
0x1800061b7  mov     [r11-58h], rax
0x1800061bb  mov     [r11-50h], r12
0x1800061bf  mov     r11, rdx
0x1800061c2  mov     [rsp+78h+var_48], rdx
0x1800061c7  call    ??R?$_Conditionally_enabled_hash@PEAVMapsBackgroundTransferJob@@$00@std@@SA_KAEBQEAVMapsBackgroundTransferJob@@@Z; std::_Conditionally_enabled_hash<MapsBackgroundTransferJob *,1>::operator()(MapsBackgroundTransferJob * const &)
0x1800061cc  mov     r14, rax
0x1800061cf  and     r14, [rbx+30h]
0x1800061d3  add     r14, r14
0x1800061d6  mov     rax, [rsi+r14*8+8]
0x1800061db  mov     r13, [rsi+r14*8]
0x1800061df  mov     [rsp+78h+arg_8], rax
0x1800061e7  cmp     r11, rax
0x1800061ea  lea     rcx, [rsp+78h+var_58]
0x1800061ef  setz    bl
0x1800061f2  call    ?_Bump_erased@_Range_eraser@?$_Hash@V?$_Umap_traits@PEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@V?$_Uhash_compare@PEAVMapsBackgroundTransferJob@@U?$hash@PEAVMapsBackgroundTransferJob@@@std@@U?$equal_to@PEAVMapsBackgroundTransferJob@@@3@@3@V?$allocator@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@3@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::_Range_eraser::_Bump_erased(void)
0x1800061f7  test    bl, bl
0x1800061f9  jnz     short loc_18000623D
0x1800061fb  mov     r11, [rsp+78h+var_48]
0x180006200  mov     rax, [rsp+78h+arg_8]
0x180006208  cmp     r11, rdi
0x18000620b  jnz     short loc_1800061E7
0x18000620d  cmp     r13, rbp
0x180006210  jnz     short loc_180006216
0x180006212  mov     [rsi+r14*8], r11
0x180006216  mov     rax, [rsp+78h+var_50]
0x18000621b  mov     [rax], r11
0x18000621e  mov     [r11+8], rax
0x180006222  mov     rbx, [rsp+78h+arg_10]
0x18000622a  mov     rax, rdi
0x18000622d  add     rsp, 40h
0x180006231  pop     r15
0x180006233  pop     r14
0x180006235  pop     r13
0x180006237  pop     r12
0x180006239  pop     rdi
0x18000623a  pop     rsi
0x18000623b  pop     rbp
0x18000623c  retn
0x18000623d  cmp     r13, rbp
0x180006240  jnz     short loc_180006249
0x180006242  mov     [rsi+r14*8], r15
0x180006246  mov     r12, r15
0x180006249  mov     [rsi+r14*8+8], r12
0x18000624e  mov     rbp, [rsp+78h+arg_0]
0x180006256  mov     r11, [rsp+78h+var_48]
0x18000625b  cmp     r11, rdi
0x18000625e  jz      short loc_180006216
0x180006260  lea     rcx, [r11+10h]; unsigned __int8 *
0x180006264  call    ??R?$_Conditionally_enabled_hash@PEAVMapsBackgroundTransferJob@@$00@std@@SA_KAEBQEAVMapsBackgroundTransferJob@@@Z; std::_Conditionally_enabled_hash<MapsBackgroundTransferJob *,1>::operator()(MapsBackgroundTransferJob * const &)
0x180006269  mov     r14, rax
0x18000626c  and     r14, [rbp+30h]
0x180006270  add     r14, r14
0x180006273  mov     r12, [rsi+r14*8+8]
0x180006278  cmp     r11, r12
0x18000627b  lea     rcx, [rsp+78h+var_58]
0x180006280  setz    bl
0x180006283  call    ?_Bump_erased@_Range_eraser@?$_Hash@V?$_Umap_traits@PEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@V?$_Uhash_compare@PEAVMapsBackgroundTransferJob@@U?$hash@PEAVMapsBackgroundTransferJob@@@std@@U?$equal_to@PEAVMapsBackgroundTransferJob@@@3@@3@V?$allocator@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@3@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::_Range_eraser::_Bump_erased(void)
0x180006288  test    bl, bl
0x18000628a  jnz     short loc_18000629B
0x18000628c  mov     r11, [rsp+78h+var_48]
0x180006291  cmp     r11, rdi
0x180006294  jnz     short loc_180006278
0x180006296  jmp     loc_180006212
0x18000629b  mov     [rsi+r14*8], r15
0x18000629f  mov     [rsi+r14*8+8], r15
0x1800062a4  jmp     short loc_180006256
```
