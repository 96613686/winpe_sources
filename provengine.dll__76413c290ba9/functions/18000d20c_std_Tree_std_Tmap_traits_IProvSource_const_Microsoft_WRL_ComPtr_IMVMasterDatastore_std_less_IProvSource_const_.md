# std::_Tree<std::_Tmap_traits<IProvSource const *,Microsoft::WRL::ComPtr<IMVMasterDatastore>,std::less<IProvSource const *>,std::allocator<std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>>>,0>>::_Insert_at<std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>> &,std::_Tree_node<std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>>,void *> *>(bool,std::_Tree_node<std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>>,void *> *,std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>> &,std::_Tree_node<std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>>,void *> *)

- ea: `0x18000d20c`
- end: `0x18000d485`
- name: `??$_Insert_at@AEAU?$pair@QEBUIProvSource@@V?$ComPtr@UIMVMasterDatastore@@@WRL@Microsoft@@@std@@PEAU?$_Tree_node@U?$pair@QEBUIProvSource@@V?$ComPtr@UIMVMasterDatastore@@@WRL@Microsoft@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@PEBUIProvSource@@V?$ComPtr@UIMVMasterDatastore@@@WRL@Microsoft@@U?$less@PEBUIProvSource@@@std@@V?$allocator@U?$pair@QEBUIProvSource@@V?$ComPtr@UIMVMasterDatastore@@@WRL@Microsoft@@@std@@@6@$0A@@std@@@std@@IEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBUIProvSource@@V?$ComPtr@UIMVMasterDatastore@@@WRL@Microsoft@@@std@@@std@@@std@@@1@_NPEAU?$_Tree_node@U?$pair@QEBUIProvSource@@V?$ComPtr@UIMVMasterDatastore@@@WRL@Microsoft@@@std@@PEAX@1@AEAU?$pair@QEBUIProvSource@@V?$ComPtr@UIMVMasterDatastore@@@WRL@Microsoft@@@1@1@Z`
- size: `633`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, char, _QWORD *, int, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000e04c`
- `0x18000ea84`

## callees

- `0x18000d20c`
- `0x180020f40`

## import_xrefs

- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000d243`
- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000d243`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall std::_Tree<std::_Tmap_traits<IProvSource const *,Microsoft::WRL::ComPtr<IMVMasterDatastore>,std::less<IProvSource const *>,std::allocator<std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>>>,0>>::_Insert_at<std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>> &,std::_Tree_node<std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>>,void *> *>(
        _QWORD *a1,
        _QWORD *a2,
        char a3,
        _QWORD *a4,
        int a5,
        __int64 a6)
{
  unsigned __int64 v6; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 *v12; // rcx
  __int64 *v13; // r8
  __int64 *v14; // rax
  __int64 *v15; // r8
  __int64 **v16; // rax
  _QWORD *v17; // rcx
  _QWORD *v18; // r8
  __int64 v19; // rax
  _QWORD *v20; // rax
  __int64 v21; // r8
  __int64 v22; // rax
  _QWORD *v23; // rax
  _QWORD *v24; // rax
  __int64 v25; // rax
  __int64 v26; // rcx
  _QWORD *result; // rax

  v6 = a1[1];
  if ( v6 >= 0x555555555555554LL )
  {
    std::_Tree<std::_Tmap_traits<IProvSource const *,Microsoft::WRL::ComPtr<IMVMasterDatastore>,std::less<IProvSource const *>,std::allocator<std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>>>,0>>::_Destroy_if_not_nil(
      0x555555555555554LL,
      a6);
    std::_Xlength_error("map/set<T> too long");
  }
  a1[1] = v6 + 1;
  *(_QWORD *)(a6 + 8) = a4;
  if ( a4 == (_QWORD *)*a1 )
  {
    *(_QWORD *)(*a1 + 8LL) = a6;
    *(_QWORD *)*a1 = a6;
    v9 = *a1;
LABEL_9:
    *(_QWORD *)(v9 + 16) = a6;
    goto LABEL_10;
  }
  if ( a3 )
  {
    *a4 = a6;
    if ( a4 == *(_QWORD **)*a1 )
      *(_QWORD *)*a1 = a6;
    goto LABEL_10;
  }
  a4[2] = a6;
  v9 = *a1;
  if ( a4 == *(_QWORD **)(*a1 + 16LL) )
    goto LABEL_9;
LABEL_10:
  v10 = *(_QWORD *)(a6 + 8);
  v11 = a6;
  while ( !*(_BYTE *)(v10 + 24) )
  {
    v12 = *(__int64 **)(v11 + 8);
    v13 = (__int64 *)v12[1];
    v14 = (__int64 *)*v13;
    if ( v12 == (__int64 *)*v13 )
    {
      v14 = (__int64 *)v13[2];
      if ( !*((_BYTE *)v14 + 24) )
        goto LABEL_31;
      v15 = (__int64 *)v12[2];
      if ( (__int64 *)v11 == v15 )
      {
        v11 = *(_QWORD *)(v11 + 8);
        v12[2] = *v15;
        if ( !*(_BYTE *)(*v15 + 25) )
          *(_QWORD *)(*v15 + 8) = v12;
        v15[1] = v12[1];
        if ( v12 == *(__int64 **)(*a1 + 8LL) )
        {
          *(_QWORD *)(*a1 + 8LL) = v15;
        }
        else
        {
          v16 = (__int64 **)v12[1];
          if ( v12 == *v16 )
            *v16 = v15;
          else
            v16[2] = v15;
        }
        *v15 = (__int64)v12;
        v12[1] = (__int64)v15;
      }
      *(_BYTE *)(*(_QWORD *)(v11 + 8) + 24LL) = 1;
      *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v11 + 8) + 8LL) + 24LL) = 0;
      v17 = *(_QWORD **)(*(_QWORD *)(v11 + 8) + 8LL);
      v18 = (_QWORD *)*v17;
      *v17 = *(_QWORD *)(*v17 + 16LL);
      v19 = v18[2];
      if ( !*(_BYTE *)(v19 + 25) )
        *(_QWORD *)(v19 + 8) = v17;
      v18[1] = v17[1];
      if ( v17 == *(_QWORD **)(*a1 + 8LL) )
      {
        *(_QWORD *)(*a1 + 8LL) = v18;
      }
      else
      {
        v20 = (_QWORD *)v17[1];
        if ( v17 == (_QWORD *)v20[2] )
          v20[2] = v18;
        else
          *v20 = v18;
      }
      v18[2] = v17;
    }
    else
    {
      if ( !*((_BYTE *)v14 + 24) )
      {
LABEL_31:
        *((_BYTE *)v12 + 24) = 1;
        *((_BYTE *)v14 + 24) = 1;
        *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v11 + 8) + 8LL) + 24LL) = 0;
        v11 = *(_QWORD *)(*(_QWORD *)(v11 + 8) + 8LL);
        goto LABEL_50;
      }
      v21 = *v12;
      if ( v11 == *v12 )
      {
        v11 = *(_QWORD *)(v11 + 8);
        *v12 = *(_QWORD *)(v21 + 16);
        v22 = *(_QWORD *)(v21 + 16);
        if ( !*(_BYTE *)(v22 + 25) )
          *(_QWORD *)(v22 + 8) = v12;
        *(_QWORD *)(v21 + 8) = v12[1];
        if ( v12 == *(__int64 **)(*a1 + 8LL) )
        {
          *(_QWORD *)(*a1 + 8LL) = v21;
        }
        else
        {
          v23 = (_QWORD *)v12[1];
          if ( v12 == (__int64 *)v23[2] )
            v23[2] = v21;
          else
            *v23 = v21;
        }
        *(_QWORD *)(v21 + 16) = v12;
        v12[1] = v21;
      }
      *(_BYTE *)(*(_QWORD *)(v11 + 8) + 24LL) = 1;
      *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v11 + 8) + 8LL) + 24LL) = 0;
      v17 = *(_QWORD **)(*(_QWORD *)(v11 + 8) + 8LL);
      v18 = (_QWORD *)v17[2];
      v17[2] = *v18;
      if ( !*(_BYTE *)(*v18 + 25LL) )
        *(_QWORD *)(*v18 + 8LL) = v17;
      v18[1] = v17[1];
      if ( v17 == *(_QWORD **)(*a1 + 8LL) )
      {
        *(_QWORD *)(*a1 + 8LL) = v18;
      }
      else
      {
        v24 = (_QWORD *)v17[1];
        if ( v17 == (_QWORD *)*v24 )
          *v24 = v18;
        else
          v24[2] = v18;
      }
      *v18 = v17;
    }
    v17[1] = v18;
LABEL_50:
    v10 = *(_QWORD *)(v11 + 8);
  }
  v25 = *a1;
  *a2 = a6;
  v26 = *(_QWORD *)(v25 + 8);
  result = a2;
  *(_BYTE *)(v26 + 24) = 1;
  return result;
}

```

## disassembly

```asm
0x18000d20c  mov     [rsp+arg_0], rbx
0x18000d211  push    rdi
0x18000d212  sub     rsp, 20h
0x18000d216  mov     rax, [rcx+8]
0x18000d21a  mov     r11, rcx
0x18000d21d  mov     rcx, 555555555555554h
0x18000d227  mov     r10, r9
0x18000d22a  mov     rbx, rdx
0x18000d22d  cmp     rax, rcx
0x18000d230  jb      short loc_18000D24A
0x18000d232  mov     rdx, [rsp+28h+arg_28]
0x18000d237  call    ?_Destroy_if_not_nil@?$_Tree@V?$_Tmap_traits@PEBUIProvSource@@V?$ComPtr@UIMVMasterDatastore@@@WRL@Microsoft@@U?$less@PEBUIProvSource@@@std@@V?$allocator@U?$pair@QEBUIProvSource@@V?$ComPtr@UIMVMasterDatastore@@@WRL@Microsoft@@@std@@@6@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@QEBUIProvSource@@V?$ComPtr@UIMVMasterDatastore@@@WRL@Microsoft@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<IProvSource const *,Microsoft::WRL::ComPtr<IMVMasterDatastore>,std::less<IProvSource const *>,std::allocator<std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>>>,0>>::_Destroy_if_not_nil(std::_Tree_node<std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>>,void *> *)
0x18000d23c  lea     rcx, aMapSetTTooLong; "map/set<T> too long"
0x18000d243  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000d24a  mov     r9, [rsp+28h+arg_28]
0x18000d24f  inc     rax
0x18000d252  mov     [r11+8], rax
0x18000d256  xor     edi, edi
0x18000d258  mov     [r9+8], r10
0x18000d25c  mov     rax, [r11]
0x18000d25f  cmp     r10, rax
0x18000d262  jnz     short loc_18000D273
0x18000d264  mov     [rax+8], r9
0x18000d268  mov     rax, [r11]
0x18000d26b  mov     [rax], r9
0x18000d26e  mov     rax, [r11]
0x18000d271  jmp     short loc_18000D295
0x18000d273  test    r8b, r8b
0x18000d276  jz      short loc_18000D288
0x18000d278  mov     [r10], r9
0x18000d27b  mov     rax, [r11]
0x18000d27e  cmp     r10, [rax]
0x18000d281  jnz     short loc_18000D299
0x18000d283  mov     [rax], r9
0x18000d286  jmp     short loc_18000D299
0x18000d288  mov     [r10+10h], r9
0x18000d28c  mov     rax, [r11]
0x18000d28f  cmp     r10, [rax+10h]
0x18000d293  jnz     short loc_18000D299
0x18000d295  mov     [rax+10h], r9
0x18000d299  mov     rax, [r9+8]
0x18000d29d  mov     rdx, r9
0x18000d2a0  jmp     loc_18000D45F
0x18000d2a5  mov     rcx, [rdx+8]
0x18000d2a9  mov     r8, [rcx+8]
0x18000d2ad  mov     rax, [r8]
0x18000d2b0  cmp     rcx, rax
0x18000d2b3  jnz     loc_18000D37E
0x18000d2b9  mov     rax, [r8+10h]
0x18000d2bd  cmp     [rax+18h], dil
0x18000d2c1  jz      loc_18000D384
0x18000d2c7  mov     r8, [rcx+10h]
0x18000d2cb  cmp     rdx, r8
0x18000d2ce  jnz     short loc_18000D317
0x18000d2d0  mov     rax, [r8]
0x18000d2d3  mov     rdx, rcx
0x18000d2d6  mov     [rcx+10h], rax
0x18000d2da  mov     rax, [r8]
0x18000d2dd  cmp     [rax+19h], dil
0x18000d2e1  jnz     short loc_18000D2E7
0x18000d2e3  mov     [rax+8], rcx
0x18000d2e7  mov     rax, [rcx+8]
0x18000d2eb  mov     [r8+8], rax
0x18000d2ef  mov     rax, [r11]
0x18000d2f2  cmp     rcx, [rax+8]
0x18000d2f6  jnz     short loc_18000D2FE
0x18000d2f8  mov     [rax+8], r8
0x18000d2fc  jmp     short loc_18000D310
0x18000d2fe  mov     rax, [rcx+8]
0x18000d302  cmp     rcx, [rax]
0x18000d305  jnz     short loc_18000D30C
0x18000d307  mov     [rax], r8
0x18000d30a  jmp     short loc_18000D310
0x18000d30c  mov     [rax+10h], r8
0x18000d310  mov     [r8], rcx
0x18000d313  mov     [rcx+8], r8
0x18000d317  mov     rax, [rdx+8]
0x18000d31b  mov     byte ptr [rax+18h], 1
0x18000d31f  mov     rax, [rdx+8]
0x18000d323  mov     rcx, [rax+8]
0x18000d327  mov     [rcx+18h], dil
0x18000d32b  mov     rax, [rdx+8]
0x18000d32f  mov     rcx, [rax+8]
0x18000d333  mov     r8, [rcx]
0x18000d336  mov     rax, [r8+10h]
0x18000d33a  mov     [rcx], rax
0x18000d33d  mov     rax, [r8+10h]
0x18000d341  cmp     [rax+19h], dil
0x18000d345  jnz     short loc_18000D34B
0x18000d347  mov     [rax+8], rcx
0x18000d34b  mov     rax, [rcx+8]
0x18000d34f  mov     [r8+8], rax
0x18000d353  mov     rax, [r11]
0x18000d356  cmp     rcx, [rax+8]
0x18000d35a  jnz     short loc_18000D362
0x18000d35c  mov     [rax+8], r8
0x18000d360  jmp     short loc_18000D375
0x18000d362  mov     rax, [rcx+8]
0x18000d366  cmp     rcx, [rax+10h]
0x18000d36a  jnz     short loc_18000D372
0x18000d36c  mov     [rax+10h], r8
0x18000d370  jmp     short loc_18000D375
0x18000d372  mov     [rax], r8
0x18000d375  mov     [r8+10h], rcx
0x18000d379  jmp     loc_18000D457
0x18000d37e  cmp     [rax+18h], dil
0x18000d382  jnz     short loc_18000D3A5
0x18000d384  mov     byte ptr [rcx+18h], 1
0x18000d388  mov     byte ptr [rax+18h], 1
0x18000d38c  mov     rax, [rdx+8]
0x18000d390  mov     rcx, [rax+8]
0x18000d394  mov     [rcx+18h], dil
0x18000d398  mov     rax, [rdx+8]
0x18000d39c  mov     rdx, [rax+8]
0x18000d3a0  jmp     loc_18000D45B
0x18000d3a5  mov     r8, [rcx]
0x18000d3a8  cmp     rdx, r8
0x18000d3ab  jnz     short loc_18000D3F7
0x18000d3ad  mov     rax, [r8+10h]
0x18000d3b1  mov     rdx, rcx
0x18000d3b4  mov     [rcx], rax
0x18000d3b7  mov     rax, [r8+10h]
0x18000d3bb  cmp     [rax+19h], dil
0x18000d3bf  jnz     short loc_18000D3C5
0x18000d3c1  mov     [rax+8], rcx
0x18000d3c5  mov     rax, [rcx+8]
0x18000d3c9  mov     [r8+8], rax
0x18000d3cd  mov     rax, [r11]
0x18000d3d0  cmp     rcx, [rax+8]
0x18000d3d4  jnz     short loc_18000D3DC
0x18000d3d6  mov     [rax+8], r8
0x18000d3da  jmp     short loc_18000D3EF
0x18000d3dc  mov     rax, [rcx+8]
0x18000d3e0  cmp     rcx, [rax+10h]
0x18000d3e4  jnz     short loc_18000D3EC
0x18000d3e6  mov     [rax+10h], r8
0x18000d3ea  jmp     short loc_18000D3EF
0x18000d3ec  mov     [rax], r8
0x18000d3ef  mov     [r8+10h], rcx
0x18000d3f3  mov     [rcx+8], r8
0x18000d3f7  mov     rax, [rdx+8]
0x18000d3fb  mov     byte ptr [rax+18h], 1
0x18000d3ff  mov     rax, [rdx+8]
0x18000d403  mov     rcx, [rax+8]
0x18000d407  mov     [rcx+18h], dil
0x18000d40b  mov     rax, [rdx+8]
0x18000d40f  mov     rcx, [rax+8]
0x18000d413  mov     r8, [rcx+10h]
0x18000d417  mov     rax, [r8]
0x18000d41a  mov     [rcx+10h], rax
0x18000d41e  mov     rax, [r8]
0x18000d421  cmp     [rax+19h], dil
0x18000d425  jnz     short loc_18000D42B
0x18000d427  mov     [rax+8], rcx
0x18000d42b  mov     rax, [rcx+8]
0x18000d42f  mov     [r8+8], rax
0x18000d433  mov     rax, [r11]
0x18000d436  cmp     rcx, [rax+8]
0x18000d43a  jnz     short loc_18000D442
0x18000d43c  mov     [rax+8], r8
0x18000d440  jmp     short loc_18000D454
0x18000d442  mov     rax, [rcx+8]
0x18000d446  cmp     rcx, [rax]
0x18000d449  jnz     short loc_18000D450
0x18000d44b  mov     [rax], r8
0x18000d44e  jmp     short loc_18000D454
0x18000d450  mov     [rax+10h], r8
0x18000d454  mov     [r8], rcx
0x18000d457  mov     [rcx+8], r8
0x18000d45b  mov     rax, [rdx+8]
0x18000d45f  cmp     [rax+18h], dil
0x18000d463  jz      loc_18000D2A5
0x18000d469  mov     rax, [r11]
0x18000d46c  mov     [rbx], r9
0x18000d46f  mov     rcx, [rax+8]
0x18000d473  mov     rax, rbx
0x18000d476  mov     rbx, [rsp+28h+arg_0]
0x18000d47b  mov     byte ptr [rcx+18h], 1
0x18000d47f  add     rsp, 20h
0x18000d483  pop     rdi
0x18000d484  retn
```
