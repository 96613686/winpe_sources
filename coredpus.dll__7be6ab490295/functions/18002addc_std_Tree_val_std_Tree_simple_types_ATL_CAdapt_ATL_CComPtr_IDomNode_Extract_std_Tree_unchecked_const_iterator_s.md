# std::_Tree_val<std::_Tree_simple_types<ATL::CAdapt<ATL::CComPtr<IDomNode>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<ATL::CAdapt<ATL::CComPtr<IDomNode>>>>,std::_Iterator_base0>)

- ea: `0x18002addc`
- end: `0x18002b061`
- name: `?_Extract@?$_Tree_val@U?$_Tree_simple_types@V?$CAdapt@V?$CComPtr@UIDomNode@@@ATL@@@ATL@@@std@@@std@@QEAAPEAU?$_Tree_node@V?$CAdapt@V?$CComPtr@UIDomNode@@@ATL@@@ATL@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$CAdapt@V?$CComPtr@UIDomNode@@@ATL@@@ATL@@@std@@@std@@U_Iterator_base0@2@@2@@Z`
- size: `645`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18002ad1c`

## callees

- `0x180028978`
- `0x18002addc`
- `0x18002b198`
- `0x18002b1e8`
- `0x18002b20c`

## pseudocode

```c
__int64 *__fastcall std::_Tree_val<std::_Tree_simple_types<ATL::CAdapt<ATL::CComPtr<IDomNode>>>>::_Extract(
        __int64 **a1,
        __int64 *a2)
{
  __int64 *v3; // rdx
  __int64 *v4; // r11
  __int64 v5; // r10
  __int64 v6; // r9
  __int64 *v7; // r8
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 *v11; // rax
  __int64 **v12; // rcx
  char v13; // cl
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 *v16; // rcx
  __int64 *v18; // [rsp+38h] [rbp+10h] BYREF

  v18 = a2;
  std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<ATL::CAdapt<ATL::CComPtr<IDomNode>>>>,std::_Iterator_base0>::operator++(&v18);
  v5 = v4[2];
  if ( *(_BYTE *)(*v4 + 25) )
    goto LABEL_5;
  if ( *(_BYTE *)(v5 + 25) )
  {
    v5 = *v4;
LABEL_5:
    v6 = v4[1];
    if ( !*(_BYTE *)(v5 + 25) )
      *(_QWORD *)(v5 + 8) = v6;
    if ( (__int64 *)(*a1)[1] == v4 )
    {
      (*a1)[1] = v5;
    }
    else if ( *(__int64 **)v6 == v4 )
    {
      *(_QWORD *)v6 = v5;
    }
    else
    {
      *(_QWORD *)(v6 + 16) = v5;
    }
    v7 = *a1;
    if ( (__int64 *)**a1 == v4 )
    {
      if ( *(_BYTE *)(v5 + 25) )
        v8 = v6;
      else
        v8 = std::_Tree_val<std::_Tree_simple_types<ATL::CAdapt<ATL::CComPtr<IDomNode>>>>::_Min(v5, v3, v7, v6);
      *v7 = v8;
    }
    if ( (__int64 *)(*a1)[2] == v4 )
    {
      if ( *(_BYTE *)(v5 + 25) )
      {
        v9 = v6;
      }
      else
      {
        v10 = *(_QWORD *)(v5 + 16);
        v9 = v5;
        while ( !*(_BYTE *)(v10 + 25) )
        {
          v9 = *(_QWORD *)(v9 + 16);
          v10 = *(_QWORD *)(v9 + 16);
        }
      }
      (*a1)[2] = v9;
    }
    goto LABEL_35;
  }
  v3 = v18;
  v5 = v18[2];
  if ( v18 == v4 )
    goto LABEL_5;
  *(_QWORD *)(*v4 + 8) = v18;
  *v3 = *v4;
  if ( v3 == (__int64 *)v4[2] )
  {
    v6 = (__int64)v3;
  }
  else
  {
    v6 = v3[1];
    if ( !*(_BYTE *)(v5 + 25) )
      *(_QWORD *)(v5 + 8) = v6;
    *(_QWORD *)v6 = v5;
    v3[2] = v4[2];
    *(_QWORD *)(v4[2] + 8) = v3;
  }
  if ( (__int64 *)(*a1)[1] == v4 )
  {
    (*a1)[1] = (__int64)v3;
    v11 = v4 + 1;
  }
  else
  {
    v11 = v4 + 1;
    v12 = (__int64 **)v4[1];
    if ( *v12 == v4 )
      *v12 = v3;
    else
      v12[2] = v3;
  }
  v3[1] = *v11;
  v13 = *((_BYTE *)v3 + 24);
  *((_BYTE *)v3 + 24) = *((_BYTE *)v4 + 24);
  *((_BYTE *)v4 + 24) = v13;
LABEL_35:
  if ( *((_BYTE *)v4 + 24) != 1 )
    goto LABEL_58;
  while ( v5 != (*a1)[1] && *(_BYTE *)(v5 + 24) == 1 )
  {
    v14 = *(_QWORD *)v6;
    if ( v5 == *(_QWORD *)v6 )
    {
      v14 = *(_QWORD *)(v6 + 16);
      if ( !*(_BYTE *)(v14 + 24) )
      {
        *(_BYTE *)(v14 + 24) = 1;
        *(_BYTE *)(v6 + 24) = 0;
        std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CDdfInfo *>>>::_Lrotate(a1);
        v14 = *(_QWORD *)(v6 + 16);
      }
      if ( !*(_BYTE *)(v14 + 25) )
      {
        if ( *(_BYTE *)(*(_QWORD *)v14 + 24LL) != 1 || *(_BYTE *)(*(_QWORD *)(v14 + 16) + 24LL) != 1 )
        {
          if ( *(_BYTE *)(*(_QWORD *)(v14 + 16) + 24LL) == 1 )
          {
            *(_BYTE *)(*(_QWORD *)v14 + 24LL) = 1;
            *(_BYTE *)(v14 + 24) = 0;
            std::_Tree_val<std::_Tree_simple_types<ATL::CAdapt<ATL::CComPtr<IDomNode>>>>::_Rrotate(a1, v14);
            v14 = *(_QWORD *)(v6 + 16);
          }
          *(_BYTE *)(v14 + 24) = *(_BYTE *)(v6 + 24);
          *(_BYTE *)(v6 + 24) = 1;
          *(_BYTE *)(*(_QWORD *)(v14 + 16) + 24LL) = 1;
          std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CDdfInfo *>>>::_Lrotate(a1);
          break;
        }
LABEL_52:
        *(_BYTE *)(v14 + 24) = 0;
      }
    }
    else
    {
      if ( !*(_BYTE *)(v14 + 24) )
      {
        *(_BYTE *)(v14 + 24) = 1;
        *(_BYTE *)(v6 + 24) = 0;
        std::_Tree_val<std::_Tree_simple_types<ATL::CAdapt<ATL::CComPtr<IDomNode>>>>::_Rrotate(a1, v6);
        v14 = *(_QWORD *)v6;
      }
      if ( !*(_BYTE *)(v14 + 25) )
      {
        v15 = *(_QWORD *)(v14 + 16);
        if ( *(_BYTE *)(v15 + 24) != 1 || *(_BYTE *)(*(_QWORD *)v14 + 24LL) != 1 )
        {
          if ( *(_BYTE *)(*(_QWORD *)v14 + 24LL) == 1 )
          {
            *(_BYTE *)(v15 + 24) = 1;
            *(_BYTE *)(v14 + 24) = 0;
            std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CDdfInfo *>>>::_Lrotate(a1);
            v14 = *(_QWORD *)v6;
          }
          *(_BYTE *)(v14 + 24) = *(_BYTE *)(v6 + 24);
          *(_BYTE *)(v6 + 24) = 1;
          *(_BYTE *)(*(_QWORD *)v14 + 24LL) = 1;
          std::_Tree_val<std::_Tree_simple_types<ATL::CAdapt<ATL::CComPtr<IDomNode>>>>::_Rrotate(a1, v6);
          break;
        }
        goto LABEL_52;
      }
    }
    v5 = v6;
    v6 = *(_QWORD *)(v6 + 8);
  }
  *(_BYTE *)(v5 + 24) = 1;
LABEL_58:
  v16 = a1[1];
  if ( v16 )
    a1[1] = (__int64 *)((char *)v16 - 1);
  return v4;
}

```

## disassembly

```asm
0x18002addc  mov     [rsp+arg_0], rbx
0x18002ade1  mov     [rsp+arg_8], rdx
0x18002ade6  push    rsi
0x18002ade7  sub     rsp, 20h
0x18002adeb  mov     rbx, rcx
0x18002adee  mov     r11, rdx
0x18002adf1  lea     rcx, [rsp+28h+arg_8]
0x18002adf6  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$CAdapt@V?$CComPtr@UIDomNode@@@ATL@@@ATL@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<ATL::CAdapt<ATL::CComPtr<IDomNode>>>>,std::_Iterator_base0>::operator++(void)
0x18002adfb  mov     r9, [r11]
0x18002adfe  xor     esi, esi
0x18002ae00  mov     r10, [r11+10h]
0x18002ae04  cmp     [r9+19h], sil
0x18002ae08  jnz     short loc_18002AE23
0x18002ae0a  cmp     [r10+19h], sil
0x18002ae0e  jz      short loc_18002AE15
0x18002ae10  mov     r10, r9
0x18002ae13  jmp     short loc_18002AE23
0x18002ae15  mov     rdx, [rsp+28h+arg_8]
0x18002ae1a  mov     r10, [rdx+10h]
0x18002ae1e  cmp     rdx, r11
0x18002ae21  jnz     short loc_18002AEA1
0x18002ae23  mov     r9, [r11+8]
0x18002ae27  cmp     [r10+19h], sil
0x18002ae2b  jnz     short loc_18002AE31
0x18002ae2d  mov     [r10+8], r9
0x18002ae31  mov     rax, [rbx]
0x18002ae34  cmp     [rax+8], r11
0x18002ae38  jnz     short loc_18002AE40
0x18002ae3a  mov     [rax+8], r10
0x18002ae3e  jmp     short loc_18002AE4E
0x18002ae40  cmp     [r9], r11
0x18002ae43  jnz     short loc_18002AE4A
0x18002ae45  mov     [r9], r10
0x18002ae48  jmp     short loc_18002AE4E
0x18002ae4a  mov     [r9+10h], r10
0x18002ae4e  mov     r8, [rbx]
0x18002ae51  cmp     [r8], r11
0x18002ae54  jnz     short loc_18002AE6C
0x18002ae56  cmp     [r10+19h], sil
0x18002ae5a  jz      short loc_18002AE61
0x18002ae5c  mov     rax, r9
0x18002ae5f  jmp     short loc_18002AE69
0x18002ae61  mov     rcx, r10
0x18002ae64  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@V?$CAdapt@V?$CComPtr@UIDomNode@@@ATL@@@ATL@@@std@@@std@@SAPEAU?$_Tree_node@V?$CAdapt@V?$CComPtr@UIDomNode@@@ATL@@@ATL@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<ATL::CAdapt<ATL::CComPtr<IDomNode>>>>::_Min(std::_Tree_node<ATL::CAdapt<ATL::CComPtr<IDomNode>>,void *> *)
0x18002ae69  mov     [r8], rax
0x18002ae6c  mov     rdx, [rbx]
0x18002ae6f  cmp     [rdx+10h], r11
0x18002ae73  jnz     loc_18002AF14
0x18002ae79  cmp     [r10+19h], sil
0x18002ae7d  jz      short loc_18002AE84
0x18002ae7f  mov     rcx, r9
0x18002ae82  jmp     short loc_18002AE9B
0x18002ae84  mov     rax, [r10+10h]
0x18002ae88  mov     rcx, r10
0x18002ae8b  jmp     short loc_18002AE95
0x18002ae8d  mov     rcx, [rcx+10h]
0x18002ae91  mov     rax, [rcx+10h]
0x18002ae95  cmp     [rax+19h], sil
0x18002ae99  jz      short loc_18002AE8D
0x18002ae9b  mov     [rdx+10h], rcx
0x18002ae9f  jmp     short loc_18002AF14
0x18002aea1  mov     [r9+8], rdx
0x18002aea5  mov     rax, [r11]
0x18002aea8  mov     [rdx], rax
0x18002aeab  cmp     rdx, [r11+10h]
0x18002aeaf  jnz     short loc_18002AEB6
0x18002aeb1  mov     r9, rdx
0x18002aeb4  jmp     short loc_18002AED7
0x18002aeb6  mov     r9, [rdx+8]
0x18002aeba  cmp     [r10+19h], sil
0x18002aebe  jnz     short loc_18002AEC4
0x18002aec0  mov     [r10+8], r9
0x18002aec4  mov     [r9], r10
0x18002aec7  mov     rax, [r11+10h]
0x18002aecb  mov     [rdx+10h], rax
0x18002aecf  mov     rax, [r11+10h]
0x18002aed3  mov     [rax+8], rdx
0x18002aed7  mov     rax, [rbx]
0x18002aeda  cmp     [rax+8], r11
0x18002aede  jnz     short loc_18002AEEA
0x18002aee0  mov     [rax+8], rdx
0x18002aee4  lea     rax, [r11+8]
0x18002aee8  jmp     short loc_18002AEFF
0x18002aeea  lea     rax, [r11+8]
0x18002aeee  mov     rcx, [rax]
0x18002aef1  cmp     [rcx], r11
0x18002aef4  jnz     short loc_18002AEFB
0x18002aef6  mov     [rcx], rdx
0x18002aef9  jmp     short loc_18002AEFF
0x18002aefb  mov     [rcx+10h], rdx
0x18002aeff  mov     rax, [rax]
0x18002af02  mov     [rdx+8], rax
0x18002af06  mov     al, [r11+18h]
0x18002af0a  mov     cl, [rdx+18h]
0x18002af0d  mov     [rdx+18h], al
0x18002af10  mov     [r11+18h], cl
0x18002af14  cmp     byte ptr [r11+18h], 1
0x18002af19  jnz     loc_18002B042
0x18002af1f  mov     rax, [rbx]
0x18002af22  cmp     r10, [rax+8]
0x18002af26  jz      loc_18002B03D
0x18002af2c  cmp     byte ptr [r10+18h], 1
0x18002af31  jnz     loc_18002B03D
0x18002af37  mov     rdx, [r9]
0x18002af3a  cmp     r10, rdx
0x18002af3d  jnz     short loc_18002AFBE
0x18002af3f  mov     rdx, [r9+10h]
0x18002af43  cmp     [rdx+18h], sil
0x18002af47  jnz     short loc_18002AF60
0x18002af49  mov     byte ptr [rdx+18h], 1
0x18002af4d  mov     rcx, rbx
0x18002af50  mov     rdx, r9
0x18002af53  mov     [r9+18h], sil
0x18002af57  call    ?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCDdfInfo@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCDdfInfo@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CDdfInfo *>>>::_Lrotate(std::_Tree_node<std::pair<std::wstring const,CDdfInfo *>,void *> *)
0x18002af5c  mov     rdx, [r9+10h]
0x18002af60  cmp     [rdx+19h], sil
0x18002af64  jnz     loc_18002AFF7
0x18002af6a  mov     r8, [rdx]
0x18002af6d  cmp     byte ptr [r8+18h], 1
0x18002af72  jnz     short loc_18002AF7E
0x18002af74  mov     rax, [rdx+10h]
0x18002af78  cmp     byte ptr [rax+18h], 1
0x18002af7c  jz      short loc_18002AFF3
0x18002af7e  mov     rax, [rdx+10h]
0x18002af82  cmp     byte ptr [rax+18h], 1
0x18002af86  jnz     short loc_18002AF9D
0x18002af88  mov     byte ptr [r8+18h], 1
0x18002af8d  mov     rcx, rbx
0x18002af90  mov     [rdx+18h], sil
0x18002af94  call    ?_Rrotate@?$_Tree_val@U?$_Tree_simple_types@V?$CAdapt@V?$CComPtr@UIDomNode@@@ATL@@@ATL@@@std@@@std@@QEAAXPEAU?$_Tree_node@V?$CAdapt@V?$CComPtr@UIDomNode@@@ATL@@@ATL@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<ATL::CAdapt<ATL::CComPtr<IDomNode>>>>::_Rrotate(std::_Tree_node<ATL::CAdapt<ATL::CComPtr<IDomNode>>,void *> *)
0x18002af99  mov     rdx, [r9+10h]
0x18002af9d  mov     al, [r9+18h]
0x18002afa1  mov     rcx, rbx
0x18002afa4  mov     [rdx+18h], al
0x18002afa7  mov     byte ptr [r9+18h], 1
0x18002afac  mov     rax, [rdx+10h]
0x18002afb0  mov     rdx, r9
0x18002afb3  mov     byte ptr [rax+18h], 1
0x18002afb7  call    ?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCDdfInfo@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCDdfInfo@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CDdfInfo *>>>::_Lrotate(std::_Tree_node<std::pair<std::wstring const,CDdfInfo *>,void *> *)
0x18002afbc  jmp     short loc_18002B03D
0x18002afbe  cmp     [rdx+18h], sil
0x18002afc2  jnz     short loc_18002AFDA
0x18002afc4  mov     byte ptr [rdx+18h], 1
0x18002afc8  mov     rcx, rbx
0x18002afcb  mov     rdx, r9
0x18002afce  mov     [r9+18h], sil
0x18002afd2  call    ?_Rrotate@?$_Tree_val@U?$_Tree_simple_types@V?$CAdapt@V?$CComPtr@UIDomNode@@@ATL@@@ATL@@@std@@@std@@QEAAXPEAU?$_Tree_node@V?$CAdapt@V?$CComPtr@UIDomNode@@@ATL@@@ATL@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<ATL::CAdapt<ATL::CComPtr<IDomNode>>>>::_Rrotate(std::_Tree_node<ATL::CAdapt<ATL::CComPtr<IDomNode>>,void *> *)
0x18002afd7  mov     rdx, [r9]
0x18002afda  cmp     [rdx+19h], sil
0x18002afde  jnz     short loc_18002AFF7
0x18002afe0  mov     rcx, [rdx+10h]
0x18002afe4  cmp     byte ptr [rcx+18h], 1
0x18002afe8  jnz     short loc_18002B003
0x18002afea  mov     rax, [rdx]
0x18002afed  cmp     byte ptr [rax+18h], 1
0x18002aff1  jnz     short loc_18002B003
0x18002aff3  mov     [rdx+18h], sil
0x18002aff7  mov     r10, r9
0x18002affa  mov     r9, [r9+8]
0x18002affe  jmp     loc_18002AF1F
0x18002b003  mov     rax, [rdx]
0x18002b006  cmp     byte ptr [rax+18h], 1
0x18002b00a  jnz     short loc_18002B01F
0x18002b00c  mov     byte ptr [rcx+18h], 1
0x18002b010  mov     rcx, rbx
0x18002b013  mov     [rdx+18h], sil
0x18002b017  call    ?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCDdfInfo@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCDdfInfo@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CDdfInfo *>>>::_Lrotate(std::_Tree_node<std::pair<std::wstring const,CDdfInfo *>,void *> *)
0x18002b01c  mov     rdx, [r9]
0x18002b01f  mov     al, [r9+18h]
0x18002b023  mov     rcx, rbx
0x18002b026  mov     [rdx+18h], al
0x18002b029  mov     byte ptr [r9+18h], 1
0x18002b02e  mov     rax, [rdx]
0x18002b031  mov     rdx, r9
0x18002b034  mov     byte ptr [rax+18h], 1
0x18002b038  call    ?_Rrotate@?$_Tree_val@U?$_Tree_simple_types@V?$CAdapt@V?$CComPtr@UIDomNode@@@ATL@@@ATL@@@std@@@std@@QEAAXPEAU?$_Tree_node@V?$CAdapt@V?$CComPtr@UIDomNode@@@ATL@@@ATL@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<ATL::CAdapt<ATL::CComPtr<IDomNode>>>>::_Rrotate(std::_Tree_node<ATL::CAdapt<ATL::CComPtr<IDomNode>>,void *> *)
0x18002b03d  mov     byte ptr [r10+18h], 1
0x18002b042  mov     rcx, [rbx+8]
0x18002b046  test    rcx, rcx
0x18002b049  jz      short loc_18002B052
0x18002b04b  dec     rcx
0x18002b04e  mov     [rbx+8], rcx
0x18002b052  mov     rbx, [rsp+28h+arg_0]
0x18002b057  mov     rax, r11
0x18002b05a  add     rsp, 20h
0x18002b05e  pop     rsi
0x18002b05f  retn
```
