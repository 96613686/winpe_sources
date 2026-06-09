# std::_Tree_val<std::_Tree_simple_types<std::pair<void * const,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext,std::default_delete<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<void * const,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext,std::default_delete<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>>>>>,std::_Iterator_base0>)

- ea: `0x18000ae34`
- end: `0x18000b291`
- name: `?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAXV?$unique_ptr@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@U?$default_delete@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@@std@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@QEAXV?$unique_ptr@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@U?$default_delete@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@@std@@@std@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAXV?$unique_ptr@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@U?$default_delete@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z`
- size: `1117`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000aaa0`

## callees

- `0x18000ae34`

## pseudocode

```c
_QWORD *__fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<void * const,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>>>>::_Extract(
        _QWORD *a1,
        _QWORD *a2)
{
  _QWORD *v2; // r11
  _QWORD *v3; // r9
  _QWORD *v5; // rbx
  _QWORD *v6; // rbp
  _QWORD *v7; // rsi
  char v8; // r8
  _QWORD **v9; // r10
  _QWORD *i; // rax
  __int64 *v11; // rdx
  _QWORD *v12; // r8
  _QWORD *v13; // rdx
  __int64 *v14; // rcx
  _QWORD *v15; // rcx
  __int64 v16; // rax
  _BYTE *v17; // r10
  _QWORD *v18; // rcx
  _QWORD *v19; // rcx
  char v20; // dl
  __int64 *v21; // rcx
  _QWORD *v22; // rcx
  _QWORD *v23; // rax
  __int64 v24; // rdx
  __int64 v25; // rax
  __int64 *v26; // rcx
  __int64 v27; // rax
  _QWORD *v28; // rax
  __int64 v29; // rdx
  _QWORD *v30; // rax
  _QWORD *v31; // rcx
  _QWORD *v32; // rax
  __int64 *v33; // rdx
  __int64 **v34; // rax
  __int64 v35; // rax
  _QWORD *v36; // rax
  __int64 v37; // rcx

  v2 = a2 + 2;
  v3 = (_QWORD *)a2[2];
  v5 = a2;
  v6 = a2;
  v7 = a2;
  v8 = *((_BYTE *)v3 + 25);
  if ( v8 )
  {
    v9 = (_QWORD **)(a2 + 1);
    for ( i = (_QWORD *)a2[1]; !*((_BYTE *)i + 25) && a2 == (_QWORD *)i[2]; i = (_QWORD *)i[1] )
      a2 = i;
  }
  else
  {
    v11 = (__int64 *)*v3;
    if ( *(_BYTE *)(*v3 + 25LL) )
    {
      i = v3;
    }
    else
    {
      do
      {
        i = v11;
        v11 = (__int64 *)*v11;
      }
      while ( !*((_BYTE *)v11 + 25) );
    }
    v9 = (_QWORD **)(v7 + 1);
  }
  if ( *(_BYTE *)(*v5 + 25LL) )
    goto LABEL_16;
  if ( v8 )
  {
    v3 = (_QWORD *)*v5;
LABEL_16:
    v12 = *v9;
    if ( !*((_BYTE *)v3 + 25) )
      v3[1] = v12;
    if ( *(_QWORD **)(*a1 + 8LL) == v6 )
    {
      *(_QWORD *)(*a1 + 8LL) = v3;
    }
    else if ( (_QWORD *)*v12 == v6 )
    {
      *v12 = v3;
    }
    else
    {
      v12[2] = v3;
    }
    if ( *(_QWORD **)*a1 == v6 )
    {
      if ( *((_BYTE *)v3 + 25) )
      {
        v13 = v12;
      }
      else
      {
        v14 = (__int64 *)*v3;
        if ( *(_BYTE *)(*v3 + 25LL) )
        {
          v13 = v3;
        }
        else
        {
          do
          {
            v13 = v14;
            v14 = (__int64 *)*v14;
          }
          while ( !*((_BYTE *)v14 + 25) );
        }
      }
      *(_QWORD *)*a1 = v13;
    }
    if ( *(_QWORD **)(*a1 + 16LL) == v6 )
    {
      if ( *((_BYTE *)v3 + 25) )
      {
        v15 = v12;
      }
      else
      {
        v16 = v3[2];
        v15 = v3;
        while ( !*(_BYTE *)(v16 + 25) )
        {
          v15 = (_QWORD *)v15[2];
          v16 = v15[2];
        }
      }
      *(_QWORD *)(*a1 + 16LL) = v15;
    }
    v17 = v7 + 3;
    goto LABEL_50;
  }
  v3 = (_QWORD *)i[2];
  if ( i == v6 )
    goto LABEL_16;
  *(_QWORD *)(*v5 + 8LL) = i;
  *i = *v5;
  if ( i == (_QWORD *)*v2 )
  {
    v12 = i;
  }
  else
  {
    v12 = (_QWORD *)i[1];
    if ( !*((_BYTE *)v3 + 25) )
      v3[1] = v12;
    *v12 = v3;
    i[2] = *v2;
    *(_QWORD *)(*v2 + 8LL) = i;
  }
  if ( *(_QWORD **)(*a1 + 8LL) == v6 )
  {
    *(_QWORD *)(*a1 + 8LL) = i;
  }
  else
  {
    v18 = *v9;
    if ( (_QWORD *)**v9 == v6 )
      *v18 = i;
    else
      v18[2] = i;
  }
  v19 = *v9;
  v17 = v6 + 3;
  v20 = *((_BYTE *)i + 24);
  i[1] = v19;
  *((_BYTE *)i + 24) = *((_BYTE *)v6 + 24);
  *((_BYTE *)v6 + 24) = v20;
LABEL_50:
  if ( *v17 != 1 )
    goto LABEL_118;
  while ( v3 != *(_QWORD **)(*a1 + 8LL) && *((_BYTE *)v3 + 24) == 1 )
  {
    v21 = (__int64 *)*v12;
    if ( v3 == (_QWORD *)*v12 )
    {
      v21 = (__int64 *)v12[2];
      if ( !*((_BYTE *)v21 + 24) )
      {
        *((_BYTE *)v21 + 24) = 1;
        v22 = (_QWORD *)v12[2];
        *((_BYTE *)v12 + 24) = 0;
        v12[2] = *v22;
        if ( !*(_BYTE *)(*v22 + 25LL) )
          *(_QWORD *)(*v22 + 8LL) = v12;
        v22[1] = v12[1];
        if ( v12 == *(_QWORD **)(*a1 + 8LL) )
        {
          *(_QWORD *)(*a1 + 8LL) = v22;
        }
        else
        {
          v23 = (_QWORD *)v12[1];
          if ( v12 == (_QWORD *)*v23 )
            *v23 = v22;
          else
            v23[2] = v22;
        }
        *v22 = v12;
        v12[1] = v22;
        v21 = (__int64 *)v12[2];
      }
      if ( !*((_BYTE *)v21 + 25) )
      {
        if ( *(_BYTE *)(*v21 + 24) != 1 || *(_BYTE *)(v21[2] + 24) != 1 )
        {
          if ( *(_BYTE *)(v21[2] + 24) == 1 )
          {
            *(_BYTE *)(*v21 + 24) = 1;
            v24 = *v21;
            *((_BYTE *)v21 + 24) = 0;
            *v21 = *(_QWORD *)(v24 + 16);
            v25 = *(_QWORD *)(v24 + 16);
            if ( !*(_BYTE *)(v25 + 25) )
              *(_QWORD *)(v25 + 8) = v21;
            *(_QWORD *)(v24 + 8) = v21[1];
            if ( v21 == *(__int64 **)(*a1 + 8LL) )
            {
              *(_QWORD *)(*a1 + 8LL) = v24;
            }
            else
            {
              v30 = (_QWORD *)v21[1];
              if ( v21 == (__int64 *)v30[2] )
                v30[2] = v24;
              else
                *v30 = v24;
            }
            *(_QWORD *)(v24 + 16) = v21;
            v21[1] = v24;
            v21 = (__int64 *)v12[2];
          }
          *((_BYTE *)v21 + 24) = *((_BYTE *)v12 + 24);
          *((_BYTE *)v12 + 24) = 1;
          *(_BYTE *)(v21[2] + 24) = 1;
          v31 = (_QWORD *)v12[2];
          v12[2] = *v31;
          if ( !*(_BYTE *)(*v31 + 25LL) )
            *(_QWORD *)(*v31 + 8LL) = v12;
          v31[1] = v12[1];
          if ( v12 == *(_QWORD **)(*a1 + 8LL) )
          {
            *(_QWORD *)(*a1 + 8LL) = v31;
          }
          else
          {
            v32 = (_QWORD *)v12[1];
            if ( v12 == (_QWORD *)*v32 )
              *v32 = v31;
            else
              v32[2] = v31;
          }
          *v31 = v12;
LABEL_116:
          v12[1] = v31;
          break;
        }
LABEL_83:
        *((_BYTE *)v21 + 24) = 0;
      }
    }
    else
    {
      if ( !*((_BYTE *)v21 + 24) )
      {
        *((_BYTE *)v21 + 24) = 1;
        v26 = (__int64 *)*v12;
        *((_BYTE *)v12 + 24) = 0;
        *v12 = v26[2];
        v27 = v26[2];
        if ( !*(_BYTE *)(v27 + 25) )
          *(_QWORD *)(v27 + 8) = v12;
        v26[1] = v12[1];
        if ( v12 == *(_QWORD **)(*a1 + 8LL) )
        {
          *(_QWORD *)(*a1 + 8LL) = v26;
        }
        else
        {
          v28 = (_QWORD *)v12[1];
          if ( v12 == (_QWORD *)v28[2] )
            v28[2] = v26;
          else
            *v28 = v26;
        }
        v26[2] = (__int64)v12;
        v12[1] = v26;
        v21 = (__int64 *)*v12;
      }
      if ( !*((_BYTE *)v21 + 25) )
      {
        v29 = v21[2];
        if ( *(_BYTE *)(v29 + 24) != 1 || *(_BYTE *)(*v21 + 24) != 1 )
        {
          if ( *(_BYTE *)(*v21 + 24) == 1 )
          {
            *(_BYTE *)(v29 + 24) = 1;
            v33 = (__int64 *)v21[2];
            *((_BYTE *)v21 + 24) = 0;
            v21[2] = *v33;
            if ( !*(_BYTE *)(*v33 + 25) )
              *(_QWORD *)(*v33 + 8) = v21;
            v33[1] = v21[1];
            if ( v21 == *(__int64 **)(*a1 + 8LL) )
            {
              *(_QWORD *)(*a1 + 8LL) = v33;
            }
            else
            {
              v34 = (__int64 **)v21[1];
              if ( v21 == *v34 )
                *v34 = v33;
              else
                v34[2] = v33;
            }
            *v33 = (__int64)v21;
            v21[1] = (__int64)v33;
            v21 = (__int64 *)*v12;
          }
          *((_BYTE *)v21 + 24) = *((_BYTE *)v12 + 24);
          *((_BYTE *)v12 + 24) = 1;
          *(_BYTE *)(*v21 + 24) = 1;
          v31 = (_QWORD *)*v12;
          *v12 = *(_QWORD *)(*v12 + 16LL);
          v35 = v31[2];
          if ( !*(_BYTE *)(v35 + 25) )
            *(_QWORD *)(v35 + 8) = v12;
          v31[1] = v12[1];
          if ( v12 == *(_QWORD **)(*a1 + 8LL) )
          {
            *(_QWORD *)(*a1 + 8LL) = v31;
          }
          else
          {
            v36 = (_QWORD *)v12[1];
            if ( v12 == (_QWORD *)v36[2] )
              v36[2] = v31;
            else
              *v36 = v31;
          }
          v31[2] = v12;
          goto LABEL_116;
        }
        goto LABEL_83;
      }
    }
    v3 = v12;
    v12 = (_QWORD *)v12[1];
  }
  *((_BYTE *)v3 + 24) = 1;
LABEL_118:
  v37 = a1[1];
  if ( v37 )
    a1[1] = v37 - 1;
  return v6;
}

```

## disassembly

```asm
0x18000ae34  push    rbx
0x18000ae36  push    rbp
0x18000ae37  push    rsi
0x18000ae38  push    rdi
0x18000ae39  push    r14
0x18000ae3b  lea     r11, [rdx+10h]
0x18000ae3f  xor     r14d, r14d
0x18000ae42  mov     r9, [r11]
0x18000ae45  mov     rdi, rcx
0x18000ae48  mov     rbx, rdx
0x18000ae4b  mov     rbp, rdx
0x18000ae4e  mov     rsi, rdx
0x18000ae51  mov     r8b, [r9+19h]
0x18000ae55  test    r8b, r8b
0x18000ae58  jz      short loc_18000AE78
0x18000ae5a  lea     r10, [rdx+8]
0x18000ae5e  mov     rax, [r10]
0x18000ae61  jmp     short loc_18000AE70
0x18000ae63  cmp     rdx, [rax+10h]
0x18000ae67  jnz     short loc_18000AE99
0x18000ae69  mov     rdx, rax
0x18000ae6c  mov     rax, [rax+8]
0x18000ae70  cmp     [rax+19h], r14b
0x18000ae74  jz      short loc_18000AE63
0x18000ae76  jmp     short loc_18000AE99
0x18000ae78  mov     rdx, [r9]
0x18000ae7b  cmp     [rdx+19h], r14b
0x18000ae7f  jnz     short loc_18000AE92
0x18000ae81  mov     rcx, [rdx]
0x18000ae84  mov     rax, rdx
0x18000ae87  mov     rdx, rcx
0x18000ae8a  cmp     [rcx+19h], r14b
0x18000ae8e  jz      short loc_18000AE81
0x18000ae90  jmp     short loc_18000AE95
0x18000ae92  mov     rax, r9
0x18000ae95  lea     r10, [rsi+8]
0x18000ae99  mov     rcx, [rbx]
0x18000ae9c  cmp     [rcx+19h], r14b
0x18000aea0  jnz     short loc_18000AEB9
0x18000aea2  test    r8b, r8b
0x18000aea5  jz      short loc_18000AEAC
0x18000aea7  mov     r9, rcx
0x18000aeaa  jmp     short loc_18000AEB9
0x18000aeac  mov     r9, [rax+10h]
0x18000aeb0  cmp     rax, rbp
0x18000aeb3  jnz     loc_18000AF4B
0x18000aeb9  mov     r8, [r10]
0x18000aebc  cmp     [r9+19h], r14b
0x18000aec0  jnz     short loc_18000AEC6
0x18000aec2  mov     [r9+8], r8
0x18000aec6  mov     rax, [rdi]
0x18000aec9  cmp     [rax+8], rbp
0x18000aecd  jnz     short loc_18000AED5
0x18000aecf  mov     [rax+8], r9
0x18000aed3  jmp     short loc_18000AEE3
0x18000aed5  cmp     [r8], rbp
0x18000aed8  jnz     short loc_18000AEDF
0x18000aeda  mov     [r8], r9
0x18000aedd  jmp     short loc_18000AEE3
0x18000aedf  mov     [r8+10h], r9
0x18000aee3  mov     r10, [rdi]
0x18000aee6  cmp     [r10], rbp
0x18000aee9  jnz     short loc_18000AF16
0x18000aeeb  cmp     [r9+19h], r14b
0x18000aeef  jz      short loc_18000AEF6
0x18000aef1  mov     rdx, r8
0x18000aef4  jmp     short loc_18000AF13
0x18000aef6  mov     rcx, [r9]
0x18000aef9  cmp     [rcx+19h], r14b
0x18000aefd  jnz     short loc_18000AF10
0x18000aeff  mov     rax, [rcx]
0x18000af02  mov     rdx, rcx
0x18000af05  mov     rcx, rax
0x18000af08  cmp     [rax+19h], r14b
0x18000af0c  jz      short loc_18000AEFF
0x18000af0e  jmp     short loc_18000AF13
0x18000af10  mov     rdx, r9
0x18000af13  mov     [r10], rdx
0x18000af16  mov     rdx, [rdi]
0x18000af19  cmp     [rdx+10h], rbp
0x18000af1d  jnz     short loc_18000AF45
0x18000af1f  cmp     [r9+19h], r14b
0x18000af23  jz      short loc_18000AF2A
0x18000af25  mov     rcx, r8
0x18000af28  jmp     short loc_18000AF41
0x18000af2a  mov     rax, [r9+10h]
0x18000af2e  mov     rcx, r9
0x18000af31  jmp     short loc_18000AF3B
0x18000af33  mov     rcx, [rcx+10h]
0x18000af37  mov     rax, [rcx+10h]
0x18000af3b  cmp     [rax+19h], r14b
0x18000af3f  jz      short loc_18000AF33
0x18000af41  mov     [rdx+10h], rcx
0x18000af45  lea     r10, [rsi+18h]
0x18000af49  jmp     short loc_18000AFB5
0x18000af4b  mov     [rcx+8], rax
0x18000af4f  mov     rcx, [rbx]
0x18000af52  mov     [rax], rcx
0x18000af55  cmp     rax, [r11]
0x18000af58  jnz     short loc_18000AF5F
0x18000af5a  mov     r8, rax
0x18000af5d  jmp     short loc_18000AF7E
0x18000af5f  mov     r8, [rax+8]
0x18000af63  cmp     [r9+19h], r14b
0x18000af67  jnz     short loc_18000AF6D
0x18000af69  mov     [r9+8], r8
0x18000af6d  mov     [r8], r9
0x18000af70  mov     rcx, [r11]
0x18000af73  mov     [rax+10h], rcx
0x18000af77  mov     rcx, [r11]
0x18000af7a  mov     [rcx+8], rax
0x18000af7e  mov     rcx, [rdi]
0x18000af81  cmp     [rcx+8], rbp
0x18000af85  jnz     short loc_18000AF8D
0x18000af87  mov     [rcx+8], rax
0x18000af8b  jmp     short loc_18000AF9E
0x18000af8d  mov     rcx, [r10]
0x18000af90  cmp     [rcx], rbp
0x18000af93  jnz     short loc_18000AF9A
0x18000af95  mov     [rcx], rax
0x18000af98  jmp     short loc_18000AF9E
0x18000af9a  mov     [rcx+10h], rax
0x18000af9e  mov     rcx, [r10]
0x18000afa1  lea     r10, [rbp+18h]
0x18000afa5  mov     dl, [rax+18h]
0x18000afa8  mov     [rax+8], rcx
0x18000afac  mov     cl, [r10]
0x18000afaf  mov     [rax+18h], cl
0x18000afb2  mov     [r10], dl
0x18000afb5  mov     r11b, 1
0x18000afb8  cmp     [r10], r11b
0x18000afbb  jnz     loc_18000B277
0x18000afc1  jmp     loc_18000B12E
0x18000afc6  cmp     [r9+18h], r11b
0x18000afca  jnz     loc_18000B273
0x18000afd0  mov     rcx, [r8]
0x18000afd3  cmp     r9, rcx
0x18000afd6  jnz     loc_18000B0A7
0x18000afdc  mov     rcx, [r8+10h]
0x18000afe0  cmp     [rcx+18h], r14b
0x18000afe4  jnz     short loc_18000B03A
0x18000afe6  mov     [rcx+18h], r11b
0x18000afea  mov     rcx, [r8+10h]
0x18000afee  mov     [r8+18h], r14b
0x18000aff2  mov     rax, [rcx]
0x18000aff5  mov     [r8+10h], rax
0x18000aff9  mov     rax, [rcx]
0x18000affc  cmp     [rax+19h], r14b
0x18000b000  jnz     short loc_18000B006
0x18000b002  mov     [rax+8], r8
0x18000b006  mov     rax, [r8+8]
0x18000b00a  mov     [rcx+8], rax
0x18000b00e  mov     rax, [rdi]
0x18000b011  cmp     r8, [rax+8]
0x18000b015  jnz     short loc_18000B01D
0x18000b017  mov     [rax+8], rcx
0x18000b01b  jmp     short loc_18000B02F
0x18000b01d  mov     rax, [r8+8]
0x18000b021  cmp     r8, [rax]
0x18000b024  jnz     short loc_18000B02B
0x18000b026  mov     [rax], rcx
0x18000b029  jmp     short loc_18000B02F
0x18000b02b  mov     [rax+10h], rcx
0x18000b02f  mov     [rcx], r8
0x18000b032  mov     [r8+8], rcx
0x18000b036  mov     rcx, [r8+10h]
0x18000b03a  cmp     [rcx+19h], r14b
0x18000b03e  jnz     loc_18000B127
0x18000b044  mov     r10, [rcx]
0x18000b047  cmp     [r10+18h], r11b
0x18000b04b  jnz     short loc_18000B05B
0x18000b04d  mov     rax, [rcx+10h]
0x18000b051  cmp     [rax+18h], r11b
0x18000b055  jz      loc_18000B123
0x18000b05b  mov     rax, [rcx+10h]
0x18000b05f  cmp     [rax+18h], r11b
0x18000b063  jnz     loc_18000B15F
0x18000b069  mov     [r10+18h], r11b
0x18000b06d  mov     rdx, [rcx]
0x18000b070  mov     [rcx+18h], r14b
0x18000b074  mov     rax, [rdx+10h]
0x18000b078  mov     [rcx], rax
0x18000b07b  mov     rax, [rdx+10h]
0x18000b07f  cmp     [rax+19h], r14b
0x18000b083  jnz     short loc_18000B089
0x18000b085  mov     [rax+8], rcx
0x18000b089  mov     rax, [rcx+8]
0x18000b08d  mov     [rdx+8], rax
0x18000b091  mov     rax, [rdi]
0x18000b094  cmp     rcx, [rax+8]
0x18000b098  jnz     loc_18000B140
0x18000b09e  mov     [rax+8], rdx
0x18000b0a2  jmp     loc_18000B153
0x18000b0a7  cmp     [rcx+18h], r14b
0x18000b0ab  jnz     short loc_18000B102
0x18000b0ad  mov     [rcx+18h], r11b
0x18000b0b1  mov     rcx, [r8]
0x18000b0b4  mov     [r8+18h], r14b
0x18000b0b8  mov     rax, [rcx+10h]
0x18000b0bc  mov     [r8], rax
0x18000b0bf  mov     rax, [rcx+10h]
0x18000b0c3  cmp     [rax+19h], r14b
0x18000b0c7  jnz     short loc_18000B0CD
0x18000b0c9  mov     [rax+8], r8
0x18000b0cd  mov     rax, [r8+8]
0x18000b0d1  mov     [rcx+8], rax
0x18000b0d5  mov     rax, [rdi]
0x18000b0d8  cmp     r8, [rax+8]
0x18000b0dc  jnz     short loc_18000B0E4
0x18000b0de  mov     [rax+8], rcx
0x18000b0e2  jmp     short loc_18000B0F7
0x18000b0e4  mov     rax, [r8+8]
0x18000b0e8  cmp     r8, [rax+10h]
0x18000b0ec  jnz     short loc_18000B0F4
0x18000b0ee  mov     [rax+10h], rcx
0x18000b0f2  jmp     short loc_18000B0F7
0x18000b0f4  mov     [rax], rcx
0x18000b0f7  mov     [rcx+10h], r8
0x18000b0fb  mov     [r8+8], rcx
0x18000b0ff  mov     rcx, [r8]
0x18000b102  cmp     [rcx+19h], r14b
0x18000b106  jnz     short loc_18000B127
0x18000b108  mov     rdx, [rcx+10h]
0x18000b10c  cmp     [rdx+18h], r11b
0x18000b110  jnz     loc_18000B1BB
0x18000b116  mov     rax, [rcx]
0x18000b119  cmp     [rax+18h], r11b
0x18000b11d  jnz     loc_18000B1BB
0x18000b123  mov     [rcx+18h], r14b
0x18000b127  mov     r9, r8
0x18000b12a  mov     r8, [r8+8]
0x18000b12e  mov     rax, [rdi]
0x18000b131  cmp     r9, [rax+8]
0x18000b135  jnz     loc_18000AFC6
0x18000b13b  jmp     loc_18000B273
0x18000b140  mov     rax, [rcx+8]
0x18000b144  cmp     rcx, [rax+10h]
0x18000b148  jnz     short loc_18000B150
0x18000b14a  mov     [rax+10h], rdx
0x18000b14e  jmp     short loc_18000B153
0x18000b150  mov     [rax], rdx
0x18000b153  mov     [rdx+10h], rcx
0x18000b157  mov     [rcx+8], rdx
0x18000b15b  mov     rcx, [r8+10h]
0x18000b15f  mov     al, [r8+18h]
0x18000b163  mov     [rcx+18h], al
0x18000b166  mov     [r8+18h], r11b
0x18000b16a  mov     rax, [rcx+10h]
0x18000b16e  mov     [rax+18h], r11b
0x18000b172  mov     rcx, [r8+10h]
0x18000b176  mov     rax, [rcx]
0x18000b179  mov     [r8+10h], rax
0x18000b17d  mov     rax, [rcx]
0x18000b180  cmp     [rax+19h], r14b
0x18000b184  jnz     short loc_18000B18A
0x18000b186  mov     [rax+8], r8
0x18000b18a  mov     rax, [r8+8]
0x18000b18e  mov     [rcx+8], rax
0x18000b192  mov     rax, [rdi]
0x18000b195  cmp     r8, [rax+8]
0x18000b199  jnz     short loc_18000B1A1
0x18000b19b  mov     [rax+8], rcx
0x18000b19f  jmp     short loc_18000B1B3
0x18000b1a1  mov     rax, [r8+8]
0x18000b1a5  cmp     r8, [rax]
0x18000b1a8  jnz     short loc_18000B1AF
0x18000b1aa  mov     [rax], rcx
0x18000b1ad  jmp     short loc_18000B1B3
0x18000b1af  mov     [rax+10h], rcx
0x18000b1b3  mov     [rcx], r8
0x18000b1b6  jmp     loc_18000B26F
0x18000b1bb  mov     rax, [rcx]
0x18000b1be  cmp     [rax+18h], r11b
0x18000b1c2  jnz     short loc_18000B217
0x18000b1c4  mov     [rdx+18h], r11b
0x18000b1c8  mov     rdx, [rcx+10h]
0x18000b1cc  mov     [rcx+18h], r14b
0x18000b1d0  mov     rax, [rdx]
0x18000b1d3  mov     [rcx+10h], rax
0x18000b1d7  mov     rax, [rdx]
0x18000b1da  cmp     [rax+19h], r14b
0x18000b1de  jnz     short loc_18000B1E4
0x18000b1e0  mov     [rax+8], rcx
0x18000b1e4  mov     rax, [rcx+8]
0x18000b1e8  mov     [rdx+8], rax
0x18000b1ec  mov     rax, [rdi]
0x18000b1ef  cmp     rcx, [rax+8]
0x18000b1f3  jnz     short loc_18000B1FB
0x18000b1f5  mov     [rax+8], rdx
0x18000b1f9  jmp     short loc_18000B20D
0x18000b1fb  mov     rax, [rcx+8]
0x18000b1ff  cmp     rcx, [rax]
0x18000b202  jnz     short loc_18000B209
0x18000b204  mov     [rax], rdx
0x18000b207  jmp     short loc_18000B20D
0x18000b209  mov     [rax+10h], rdx
0x18000b20d  mov     [rdx], rcx
0x18000b210  mov     [rcx+8], rdx
0x18000b214  mov     rcx, [r8]
0x18000b217  mov     al, [r8+18h]
  ... truncated ...
```
