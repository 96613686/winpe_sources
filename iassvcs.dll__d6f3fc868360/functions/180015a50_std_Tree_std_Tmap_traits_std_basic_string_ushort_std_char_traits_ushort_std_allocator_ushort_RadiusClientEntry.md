# std::_Tree<std::_Tmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,_RadiusClientEntry *,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,_RadiusClientEntry *>>,0>>::_Insert_at<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,_RadiusClientEntry *> &,std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,_RadiusClientEntry *>,void *> *>(bool,std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,_RadiusClientEntry *>,void *> *,std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,_RadiusClientEntry *> &,std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,_RadiusClientEntry *>,void *> *)

- ea: `0x180015a50`
- end: `0x180015ccc`
- name: `??$_Insert_at@AEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_RadiusClientEntry@@@std@@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_RadiusClientEntry@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_RadiusClientEntry@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_RadiusClientEntry@@@std@@@2@$0A@@std@@@std@@IEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_RadiusClientEntry@@@std@@@std@@@std@@@1@_NPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_RadiusClientEntry@@@std@@PEAX@1@AEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_RadiusClientEntry@@@1@1@Z`
- size: `636`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, char, _QWORD *, int, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180015cd4`
- `0x180016174`

## callees

- `0x180001260`
- `0x180015a50`
- `0x1800166b8`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tmap_traits<std::wstring,_RadiusClientEntry *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,_RadiusClientEntry *>>,0>>::_Insert_at<std::pair<std::wstring const,_RadiusClientEntry *> &,std::_Tree_node<std::pair<std::wstring const,_RadiusClientEntry *>,void *> *>(
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
  if ( v6 >= 0x38E38E38E38E38DLL )
  {
    std::_Tree<std::_Tmap_traits<std::wstring,_RadiusClientEntry *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,_RadiusClientEntry *>>,0>>::_Destroy_if_not_nil(
      0x38E38E38E38E38DLL,
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
LABEL_8:
    *(_QWORD *)(v9 + 16) = a6;
    goto LABEL_9;
  }
  if ( a3 )
  {
    *a4 = a6;
    if ( a4 == *(_QWORD **)*a1 )
      *(_QWORD *)*a1 = a6;
    goto LABEL_9;
  }
  a4[2] = a6;
  v9 = *a1;
  if ( a4 == *(_QWORD **)(*a1 + 16LL) )
    goto LABEL_8;
LABEL_9:
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
        goto LABEL_30;
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
LABEL_30:
        *((_BYTE *)v12 + 24) = 1;
        *((_BYTE *)v14 + 24) = 1;
        *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v11 + 8) + 8LL) + 24LL) = 0;
        v11 = *(_QWORD *)(*(_QWORD *)(v11 + 8) + 8LL);
        goto LABEL_49;
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
LABEL_49:
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
0x180015a50  mov     [rsp+arg_0], rbx
0x180015a55  push    rdi
0x180015a56  sub     rsp, 20h
0x180015a5a  mov     rax, [rcx+8]
0x180015a5e  mov     r11, rcx
0x180015a61  mov     rcx, 38E38E38E38E38Dh
0x180015a6b  mov     r10, r9
0x180015a6e  mov     rbx, rdx
0x180015a71  cmp     rax, rcx
0x180015a74  jnb     loc_180015CB5
0x180015a7a  mov     r9, [rsp+28h+arg_28]
0x180015a7f  inc     rax
0x180015a82  mov     [r11+8], rax
0x180015a86  xor     edi, edi
0x180015a88  mov     [r9+8], r10
0x180015a8c  mov     rax, [r11]
0x180015a8f  cmp     r10, rax
0x180015a92  jnz     short loc_180015AA3
0x180015a94  mov     [rax+8], r9
0x180015a98  mov     rax, [r11]
0x180015a9b  mov     [rax], r9
0x180015a9e  mov     rax, [r11]
0x180015aa1  jmp     short loc_180015AC5
0x180015aa3  test    r8b, r8b
0x180015aa6  jz      short loc_180015AB8
0x180015aa8  mov     [r10], r9
0x180015aab  mov     rax, [r11]
0x180015aae  cmp     r10, [rax]
0x180015ab1  jnz     short loc_180015AC9
0x180015ab3  mov     [rax], r9
0x180015ab6  jmp     short loc_180015AC9
0x180015ab8  mov     [r10+10h], r9
0x180015abc  mov     rax, [r11]
0x180015abf  cmp     r10, [rax+10h]
0x180015ac3  jnz     short loc_180015AC9
0x180015ac5  mov     [rax+10h], r9
0x180015ac9  mov     rax, [r9+8]
0x180015acd  mov     rdx, r9
0x180015ad0  jmp     loc_180015C8F
0x180015ad5  mov     rcx, [rdx+8]
0x180015ad9  mov     r8, [rcx+8]
0x180015add  mov     rax, [r8]
0x180015ae0  cmp     rcx, rax
0x180015ae3  jnz     loc_180015BAE
0x180015ae9  mov     rax, [r8+10h]
0x180015aed  cmp     [rax+18h], dil
0x180015af1  jz      loc_180015BB4
0x180015af7  mov     r8, [rcx+10h]
0x180015afb  cmp     rdx, r8
0x180015afe  jnz     short loc_180015B47
0x180015b00  mov     rax, [r8]
0x180015b03  mov     rdx, rcx
0x180015b06  mov     [rcx+10h], rax
0x180015b0a  mov     rax, [r8]
0x180015b0d  cmp     [rax+19h], dil
0x180015b11  jnz     short loc_180015B17
0x180015b13  mov     [rax+8], rcx
0x180015b17  mov     rax, [rcx+8]
0x180015b1b  mov     [r8+8], rax
0x180015b1f  mov     rax, [r11]
0x180015b22  cmp     rcx, [rax+8]
0x180015b26  jnz     short loc_180015B2E
0x180015b28  mov     [rax+8], r8
0x180015b2c  jmp     short loc_180015B40
0x180015b2e  mov     rax, [rcx+8]
0x180015b32  cmp     rcx, [rax]
0x180015b35  jnz     short loc_180015B3C
0x180015b37  mov     [rax], r8
0x180015b3a  jmp     short loc_180015B40
0x180015b3c  mov     [rax+10h], r8
0x180015b40  mov     [r8], rcx
0x180015b43  mov     [rcx+8], r8
0x180015b47  mov     rax, [rdx+8]
0x180015b4b  mov     byte ptr [rax+18h], 1
0x180015b4f  mov     rax, [rdx+8]
0x180015b53  mov     rcx, [rax+8]
0x180015b57  mov     [rcx+18h], dil
0x180015b5b  mov     rax, [rdx+8]
0x180015b5f  mov     rcx, [rax+8]
0x180015b63  mov     r8, [rcx]
0x180015b66  mov     rax, [r8+10h]
0x180015b6a  mov     [rcx], rax
0x180015b6d  mov     rax, [r8+10h]
0x180015b71  cmp     [rax+19h], dil
0x180015b75  jnz     short loc_180015B7B
0x180015b77  mov     [rax+8], rcx
0x180015b7b  mov     rax, [rcx+8]
0x180015b7f  mov     [r8+8], rax
0x180015b83  mov     rax, [r11]
0x180015b86  cmp     rcx, [rax+8]
0x180015b8a  jnz     short loc_180015B92
0x180015b8c  mov     [rax+8], r8
0x180015b90  jmp     short loc_180015BA5
0x180015b92  mov     rax, [rcx+8]
0x180015b96  cmp     rcx, [rax+10h]
0x180015b9a  jnz     short loc_180015BA2
0x180015b9c  mov     [rax+10h], r8
0x180015ba0  jmp     short loc_180015BA5
0x180015ba2  mov     [rax], r8
0x180015ba5  mov     [r8+10h], rcx
0x180015ba9  jmp     loc_180015C87
0x180015bae  cmp     [rax+18h], dil
0x180015bb2  jnz     short loc_180015BD5
0x180015bb4  mov     byte ptr [rcx+18h], 1
0x180015bb8  mov     byte ptr [rax+18h], 1
0x180015bbc  mov     rax, [rdx+8]
0x180015bc0  mov     rcx, [rax+8]
0x180015bc4  mov     [rcx+18h], dil
0x180015bc8  mov     rax, [rdx+8]
0x180015bcc  mov     rdx, [rax+8]
0x180015bd0  jmp     loc_180015C8B
0x180015bd5  mov     r8, [rcx]
0x180015bd8  cmp     rdx, r8
0x180015bdb  jnz     short loc_180015C27
0x180015bdd  mov     rax, [r8+10h]
0x180015be1  mov     rdx, rcx
0x180015be4  mov     [rcx], rax
0x180015be7  mov     rax, [r8+10h]
0x180015beb  cmp     [rax+19h], dil
0x180015bef  jnz     short loc_180015BF5
0x180015bf1  mov     [rax+8], rcx
0x180015bf5  mov     rax, [rcx+8]
0x180015bf9  mov     [r8+8], rax
0x180015bfd  mov     rax, [r11]
0x180015c00  cmp     rcx, [rax+8]
0x180015c04  jnz     short loc_180015C0C
0x180015c06  mov     [rax+8], r8
0x180015c0a  jmp     short loc_180015C1F
0x180015c0c  mov     rax, [rcx+8]
0x180015c10  cmp     rcx, [rax+10h]
0x180015c14  jnz     short loc_180015C1C
0x180015c16  mov     [rax+10h], r8
0x180015c1a  jmp     short loc_180015C1F
0x180015c1c  mov     [rax], r8
0x180015c1f  mov     [r8+10h], rcx
0x180015c23  mov     [rcx+8], r8
0x180015c27  mov     rax, [rdx+8]
0x180015c2b  mov     byte ptr [rax+18h], 1
0x180015c2f  mov     rax, [rdx+8]
0x180015c33  mov     rcx, [rax+8]
0x180015c37  mov     [rcx+18h], dil
0x180015c3b  mov     rax, [rdx+8]
0x180015c3f  mov     rcx, [rax+8]
0x180015c43  mov     r8, [rcx+10h]
0x180015c47  mov     rax, [r8]
0x180015c4a  mov     [rcx+10h], rax
0x180015c4e  mov     rax, [r8]
0x180015c51  cmp     [rax+19h], dil
0x180015c55  jnz     short loc_180015C5B
0x180015c57  mov     [rax+8], rcx
0x180015c5b  mov     rax, [rcx+8]
0x180015c5f  mov     [r8+8], rax
0x180015c63  mov     rax, [r11]
0x180015c66  cmp     rcx, [rax+8]
0x180015c6a  jnz     short loc_180015C72
0x180015c6c  mov     [rax+8], r8
0x180015c70  jmp     short loc_180015C84
0x180015c72  mov     rax, [rcx+8]
0x180015c76  cmp     rcx, [rax]
0x180015c79  jnz     short loc_180015C80
0x180015c7b  mov     [rax], r8
0x180015c7e  jmp     short loc_180015C84
0x180015c80  mov     [rax+10h], r8
0x180015c84  mov     [r8], rcx
0x180015c87  mov     [rcx+8], r8
0x180015c8b  mov     rax, [rdx+8]
0x180015c8f  cmp     [rax+18h], dil
0x180015c93  jz      loc_180015AD5
0x180015c99  mov     rax, [r11]
0x180015c9c  mov     [rbx], r9
0x180015c9f  mov     rcx, [rax+8]
0x180015ca3  mov     rax, rbx
0x180015ca6  mov     rbx, [rsp+28h+arg_0]
0x180015cab  mov     byte ptr [rcx+18h], 1
0x180015caf  add     rsp, 20h
0x180015cb3  pop     rdi
0x180015cb4  retn
0x180015cb5  mov     rdx, [rsp+28h+arg_28]
0x180015cba  call    ?_Destroy_if_not_nil@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_RadiusClientEntry@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_RadiusClientEntry@@@std@@@2@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_RadiusClientEntry@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,_RadiusClientEntry *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,_RadiusClientEntry *>>,0>>::_Destroy_if_not_nil(std::_Tree_node<std::pair<std::wstring const,_RadiusClientEntry *>,void *> *)
0x180015cbf  lea     rcx, aMapSetTTooLong; "map/set<T> too long"
0x180015cc6  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
