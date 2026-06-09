# std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::_Insert_at<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>> &,std::_Tree_node<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>,void *> *>(bool,std::_Tree_node<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>,void *> *,std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>> &,std::_Tree_node<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>,void *> *)

- ea: `0x180025c68`
- end: `0x180025ee1`
- name: `??$_Insert_at@AEAU?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@PEAU?$_Tree_node@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@PEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@Ukeyname_less@@V?$allocator@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@@std@@$0A@@std@@@std@@IEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@@std@@@std@@@1@_NPEAU?$_Tree_node@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@PEAX@1@AEAU?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@1@1@Z`
- size: `633`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, char, _QWORD *, int, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180025ee8`

## callees

- `0x180025c68`
- `0x18002b0cc`

## import_xrefs

- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180025c9f`
- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180025c9f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::_Insert_at<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>> &,std::_Tree_node<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>,void *> *>(
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
    std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::_Destroy_if_not_nil(
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
0x180025c68  mov     [rsp+arg_0], rbx
0x180025c6d  push    rdi
0x180025c6e  sub     rsp, 20h
0x180025c72  mov     rax, [rcx+8]
0x180025c76  mov     r11, rcx
0x180025c79  mov     rcx, 555555555555554h
0x180025c83  mov     r10, r9
0x180025c86  mov     rbx, rdx
0x180025c89  cmp     rax, rcx
0x180025c8c  jb      short loc_180025CA6
0x180025c8e  mov     rdx, [rsp+28h+arg_28]
0x180025c93  call    ?_Destroy_if_not_nil@?$_Tree@V?$_Tmap_traits@PEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@Ukeyname_less@@V?$allocator@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@@std@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::_Destroy_if_not_nil(std::_Tree_node<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>,void *> *)
0x180025c98  lea     rcx, aMapSetTTooLong; "map/set<T> too long"
0x180025c9f  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180025ca6  mov     r9, [rsp+28h+arg_28]
0x180025cab  inc     rax
0x180025cae  mov     [r11+8], rax
0x180025cb2  xor     edi, edi
0x180025cb4  mov     [r9+8], r10
0x180025cb8  mov     rax, [r11]
0x180025cbb  cmp     r10, rax
0x180025cbe  jnz     short loc_180025CCF
0x180025cc0  mov     [rax+8], r9
0x180025cc4  mov     rax, [r11]
0x180025cc7  mov     [rax], r9
0x180025cca  mov     rax, [r11]
0x180025ccd  jmp     short loc_180025CF1
0x180025ccf  test    r8b, r8b
0x180025cd2  jz      short loc_180025CE4
0x180025cd4  mov     [r10], r9
0x180025cd7  mov     rax, [r11]
0x180025cda  cmp     r10, [rax]
0x180025cdd  jnz     short loc_180025CF5
0x180025cdf  mov     [rax], r9
0x180025ce2  jmp     short loc_180025CF5
0x180025ce4  mov     [r10+10h], r9
0x180025ce8  mov     rax, [r11]
0x180025ceb  cmp     r10, [rax+10h]
0x180025cef  jnz     short loc_180025CF5
0x180025cf1  mov     [rax+10h], r9
0x180025cf5  mov     rax, [r9+8]
0x180025cf9  mov     rdx, r9
0x180025cfc  jmp     loc_180025EBB
0x180025d01  mov     rcx, [rdx+8]
0x180025d05  mov     r8, [rcx+8]
0x180025d09  mov     rax, [r8]
0x180025d0c  cmp     rcx, rax
0x180025d0f  jnz     loc_180025DDA
0x180025d15  mov     rax, [r8+10h]
0x180025d19  cmp     [rax+18h], dil
0x180025d1d  jz      loc_180025DE0
0x180025d23  mov     r8, [rcx+10h]
0x180025d27  cmp     rdx, r8
0x180025d2a  jnz     short loc_180025D73
0x180025d2c  mov     rax, [r8]
0x180025d2f  mov     rdx, rcx
0x180025d32  mov     [rcx+10h], rax
0x180025d36  mov     rax, [r8]
0x180025d39  cmp     [rax+19h], dil
0x180025d3d  jnz     short loc_180025D43
0x180025d3f  mov     [rax+8], rcx
0x180025d43  mov     rax, [rcx+8]
0x180025d47  mov     [r8+8], rax
0x180025d4b  mov     rax, [r11]
0x180025d4e  cmp     rcx, [rax+8]
0x180025d52  jnz     short loc_180025D5A
0x180025d54  mov     [rax+8], r8
0x180025d58  jmp     short loc_180025D6C
0x180025d5a  mov     rax, [rcx+8]
0x180025d5e  cmp     rcx, [rax]
0x180025d61  jnz     short loc_180025D68
0x180025d63  mov     [rax], r8
0x180025d66  jmp     short loc_180025D6C
0x180025d68  mov     [rax+10h], r8
0x180025d6c  mov     [r8], rcx
0x180025d6f  mov     [rcx+8], r8
0x180025d73  mov     rax, [rdx+8]
0x180025d77  mov     byte ptr [rax+18h], 1
0x180025d7b  mov     rax, [rdx+8]
0x180025d7f  mov     rcx, [rax+8]
0x180025d83  mov     [rcx+18h], dil
0x180025d87  mov     rax, [rdx+8]
0x180025d8b  mov     rcx, [rax+8]
0x180025d8f  mov     r8, [rcx]
0x180025d92  mov     rax, [r8+10h]
0x180025d96  mov     [rcx], rax
0x180025d99  mov     rax, [r8+10h]
0x180025d9d  cmp     [rax+19h], dil
0x180025da1  jnz     short loc_180025DA7
0x180025da3  mov     [rax+8], rcx
0x180025da7  mov     rax, [rcx+8]
0x180025dab  mov     [r8+8], rax
0x180025daf  mov     rax, [r11]
0x180025db2  cmp     rcx, [rax+8]
0x180025db6  jnz     short loc_180025DBE
0x180025db8  mov     [rax+8], r8
0x180025dbc  jmp     short loc_180025DD1
0x180025dbe  mov     rax, [rcx+8]
0x180025dc2  cmp     rcx, [rax+10h]
0x180025dc6  jnz     short loc_180025DCE
0x180025dc8  mov     [rax+10h], r8
0x180025dcc  jmp     short loc_180025DD1
0x180025dce  mov     [rax], r8
0x180025dd1  mov     [r8+10h], rcx
0x180025dd5  jmp     loc_180025EB3
0x180025dda  cmp     [rax+18h], dil
0x180025dde  jnz     short loc_180025E01
0x180025de0  mov     byte ptr [rcx+18h], 1
0x180025de4  mov     byte ptr [rax+18h], 1
0x180025de8  mov     rax, [rdx+8]
0x180025dec  mov     rcx, [rax+8]
0x180025df0  mov     [rcx+18h], dil
0x180025df4  mov     rax, [rdx+8]
0x180025df8  mov     rdx, [rax+8]
0x180025dfc  jmp     loc_180025EB7
0x180025e01  mov     r8, [rcx]
0x180025e04  cmp     rdx, r8
0x180025e07  jnz     short loc_180025E53
0x180025e09  mov     rax, [r8+10h]
0x180025e0d  mov     rdx, rcx
0x180025e10  mov     [rcx], rax
0x180025e13  mov     rax, [r8+10h]
0x180025e17  cmp     [rax+19h], dil
0x180025e1b  jnz     short loc_180025E21
0x180025e1d  mov     [rax+8], rcx
0x180025e21  mov     rax, [rcx+8]
0x180025e25  mov     [r8+8], rax
0x180025e29  mov     rax, [r11]
0x180025e2c  cmp     rcx, [rax+8]
0x180025e30  jnz     short loc_180025E38
0x180025e32  mov     [rax+8], r8
0x180025e36  jmp     short loc_180025E4B
0x180025e38  mov     rax, [rcx+8]
0x180025e3c  cmp     rcx, [rax+10h]
0x180025e40  jnz     short loc_180025E48
0x180025e42  mov     [rax+10h], r8
0x180025e46  jmp     short loc_180025E4B
0x180025e48  mov     [rax], r8
0x180025e4b  mov     [r8+10h], rcx
0x180025e4f  mov     [rcx+8], r8
0x180025e53  mov     rax, [rdx+8]
0x180025e57  mov     byte ptr [rax+18h], 1
0x180025e5b  mov     rax, [rdx+8]
0x180025e5f  mov     rcx, [rax+8]
0x180025e63  mov     [rcx+18h], dil
0x180025e67  mov     rax, [rdx+8]
0x180025e6b  mov     rcx, [rax+8]
0x180025e6f  mov     r8, [rcx+10h]
0x180025e73  mov     rax, [r8]
0x180025e76  mov     [rcx+10h], rax
0x180025e7a  mov     rax, [r8]
0x180025e7d  cmp     [rax+19h], dil
0x180025e81  jnz     short loc_180025E87
0x180025e83  mov     [rax+8], rcx
0x180025e87  mov     rax, [rcx+8]
0x180025e8b  mov     [r8+8], rax
0x180025e8f  mov     rax, [r11]
0x180025e92  cmp     rcx, [rax+8]
0x180025e96  jnz     short loc_180025E9E
0x180025e98  mov     [rax+8], r8
0x180025e9c  jmp     short loc_180025EB0
0x180025e9e  mov     rax, [rcx+8]
0x180025ea2  cmp     rcx, [rax]
0x180025ea5  jnz     short loc_180025EAC
0x180025ea7  mov     [rax], r8
0x180025eaa  jmp     short loc_180025EB0
0x180025eac  mov     [rax+10h], r8
0x180025eb0  mov     [r8], rcx
0x180025eb3  mov     [rcx+8], r8
0x180025eb7  mov     rax, [rdx+8]
0x180025ebb  cmp     [rax+18h], dil
0x180025ebf  jz      loc_180025D01
0x180025ec5  mov     rax, [r11]
0x180025ec8  mov     [rbx], r9
0x180025ecb  mov     rcx, [rax+8]
0x180025ecf  mov     rax, rbx
0x180025ed2  mov     rbx, [rsp+28h+arg_0]
0x180025ed7  mov     byte ptr [rcx+18h], 1
0x180025edb  add     rsp, 20h
0x180025edf  pop     rdi
0x180025ee0  retn
```
