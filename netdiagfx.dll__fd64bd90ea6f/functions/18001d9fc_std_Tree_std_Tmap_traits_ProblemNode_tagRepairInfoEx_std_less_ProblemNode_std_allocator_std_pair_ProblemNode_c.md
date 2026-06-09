# std::_Tree<std::_Tmap_traits<ProblemNode *,tagRepairInfoEx,std::less<ProblemNode *>,std::allocator<std::pair<ProblemNode * const,tagRepairInfoEx>>,1>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ProblemNode * const,tagRepairInfoEx>>>>)

- ea: `0x18001d9fc`
- end: `0x18001dcbe`
- name: `?erase@?$_Tree@V?$_Tmap_traits@PEAVProblemNode@@UtagRepairInfoEx@@U?$less@PEAVProblemNode@@@std@@V?$allocator@U?$pair@QEAVProblemNode@@UtagRepairInfoEx@@@std@@@4@$00@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAVProblemNode@@UtagRepairInfoEx@@@std@@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAVProblemNode@@UtagRepairInfoEx@@@std@@@std@@@std@@@2@@Z`
- size: `706`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, _QWORD *)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x18001d968`
- `0x180021db8`
- `0x180022014`

## callees

- `0x18000192c`
- `0x180005048`
- `0x18000fea8`
- `0x180010018`
- `0x18001d9fc`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001dc93`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001dc93`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tmap_traits<ProblemNode *,tagRepairInfoEx,std::less<ProblemNode *>,std::allocator<std::pair<ProblemNode * const,tagRepairInfoEx>>,1>>::erase(
        _QWORD *a1,
        _QWORD *a2,
        _QWORD *a3)
{
  _QWORD *v5; // rsi
  _BYTE *v6; // r14
  _QWORD *v7; // r10
  _QWORD **v8; // r11
  _QWORD *v9; // rbp
  char v10; // r9
  _QWORD *i; // rbx
  _QWORD *v12; // r9
  _QWORD *v13; // r8
  _QWORD *v14; // rax
  _QWORD *v15; // rcx
  __int64 v16; // rax
  _BYTE *v17; // rdx
  _QWORD *v18; // rax
  char v19; // cl
  char v20; // r11
  _BYTE *v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // rax

  if ( *((_BYTE *)a3 + 25) )
    std::_Xout_of_range("invalid map/set<T> iterator");
  v5 = a3 + 2;
  v6 = a3;
  v7 = (_QWORD *)a3[2];
  v8 = (_QWORD **)(a3 + 1);
  v9 = a3;
  v10 = *((_BYTE *)v7 + 25);
  if ( v10 )
  {
    for ( i = *v8; !*((_BYTE *)i + 25) && a3 == (_QWORD *)i[2]; i = (_QWORD *)i[1] )
      a3 = i;
  }
  else
  {
    i = std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,CExtensionHelperInfoContainer *>>>::_Min((_QWORD *)a3[2]);
  }
  if ( *(_BYTE *)(*(_QWORD *)v6 + 25LL) )
    goto LABEL_13;
  if ( v10 )
  {
    v7 = *(_QWORD **)v6;
LABEL_13:
    v12 = *v8;
    if ( !*((_BYTE *)v7 + 25) )
      v7[1] = v12;
    if ( *(_BYTE **)(*a1 + 8LL) == v6 )
    {
      *(_QWORD *)(*a1 + 8LL) = v7;
    }
    else if ( (_BYTE *)*v12 == v6 )
    {
      *v12 = v7;
    }
    else
    {
      v12[2] = v7;
    }
    v13 = (_QWORD *)*a1;
    if ( *(_BYTE **)*a1 == v6 )
    {
      if ( *((_BYTE *)v7 + 25) )
        v14 = v12;
      else
        v14 = std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,CExtensionHelperInfoContainer *>>>::_Min(v7);
      *v13 = v14;
    }
    if ( *(_BYTE **)(*a1 + 16LL) == v6 )
    {
      if ( *((_BYTE *)v7 + 25) )
      {
        v15 = v12;
      }
      else
      {
        v16 = v7[2];
        v15 = v7;
        while ( !*(_BYTE *)(v16 + 25) )
        {
          v15 = (_QWORD *)v15[2];
          v16 = v15[2];
        }
      }
      *(_QWORD *)(*a1 + 16LL) = v15;
    }
    v17 = v9 + 3;
    goto LABEL_44;
  }
  v7 = (_QWORD *)i[2];
  if ( i == (_QWORD *)v6 )
    goto LABEL_13;
  *(_QWORD *)(*(_QWORD *)v6 + 8LL) = i;
  *i = *(_QWORD *)v6;
  if ( i == (_QWORD *)*v5 )
  {
    v12 = i;
  }
  else
  {
    v12 = (_QWORD *)i[1];
    if ( !*((_BYTE *)v7 + 25) )
      v7[1] = v12;
    *v12 = v7;
    i[2] = *v5;
    *(_QWORD *)(*v5 + 8LL) = i;
  }
  if ( *(_BYTE **)(*a1 + 8LL) == v6 )
  {
    *(_QWORD *)(*a1 + 8LL) = i;
  }
  else
  {
    v18 = *v8;
    if ( (_BYTE *)**v8 == v6 )
      *v18 = i;
    else
      v18[2] = i;
  }
  v17 = v6 + 24;
  i[1] = *v8;
  v19 = *((_BYTE *)i + 24);
  *((_BYTE *)i + 24) = v6[24];
  v6[24] = v19;
LABEL_44:
  v20 = 1;
  if ( *v17 != 1 )
    goto LABEL_67;
  while ( v7 != *(_QWORD **)(*a1 + 8LL) && *((_BYTE *)v7 + 24) == v20 )
  {
    v21 = (_BYTE *)*v12;
    if ( v7 == (_QWORD *)*v12 )
    {
      v21 = (_BYTE *)v12[2];
      if ( !v21[24] )
      {
        v21[24] = v20;
        *((_BYTE *)v12 + 24) = 0;
        std::_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CHelperAttribute *,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,CHelperAttribute *>>,0>>::_Lrotate(
          a1,
          v12);
        v21 = (_BYTE *)v12[2];
      }
      if ( !v21[25] )
      {
        if ( *(_BYTE *)(*(_QWORD *)v21 + 24LL) != v20 || *(_BYTE *)(*((_QWORD *)v21 + 2) + 24LL) != v20 )
        {
          if ( *(_BYTE *)(*((_QWORD *)v21 + 2) + 24LL) == v20 )
          {
            *(_BYTE *)(*(_QWORD *)v21 + 24LL) = v20;
            v21[24] = 0;
            std::_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CExtensionHelperInfo *,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,CExtensionHelperInfo *>>,0>>::_Rrotate(
              (__int64)a1,
              v21);
            v21 = (_BYTE *)v12[2];
          }
          v21[24] = *((_BYTE *)v12 + 24);
          *((_BYTE *)v12 + 24) = v20;
          *(_BYTE *)(*((_QWORD *)v21 + 2) + 24LL) = v20;
          std::_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CHelperAttribute *,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,CHelperAttribute *>>,0>>::_Lrotate(
            a1,
            v12);
          break;
        }
LABEL_61:
        v21[24] = 0;
      }
    }
    else
    {
      if ( !v21[24] )
      {
        v21[24] = v20;
        *((_BYTE *)v12 + 24) = 0;
        std::_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CExtensionHelperInfo *,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,CExtensionHelperInfo *>>,0>>::_Rrotate(
          (__int64)a1,
          v12);
        v21 = (_BYTE *)*v12;
      }
      if ( !v21[25] )
      {
        v22 = *((_QWORD *)v21 + 2);
        if ( *(_BYTE *)(v22 + 24) != v20 || *(_BYTE *)(*(_QWORD *)v21 + 24LL) != v20 )
        {
          if ( *(_BYTE *)(*(_QWORD *)v21 + 24LL) == v20 )
          {
            *(_BYTE *)(v22 + 24) = v20;
            v21[24] = 0;
            std::_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CHelperAttribute *,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,CHelperAttribute *>>,0>>::_Lrotate(
              a1,
              v21);
            v21 = (_BYTE *)*v12;
          }
          v21[24] = *((_BYTE *)v12 + 24);
          *((_BYTE *)v12 + 24) = v20;
          *(_BYTE *)(*(_QWORD *)v21 + 24LL) = v20;
          std::_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CExtensionHelperInfo *,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,CExtensionHelperInfo *>>,0>>::_Rrotate(
            (__int64)a1,
            v12);
          break;
        }
        goto LABEL_61;
      }
    }
    v7 = v12;
    v12 = (_QWORD *)v12[1];
  }
  *((_BYTE *)v7 + 24) = v20;
LABEL_67:
  operator delete(v6);
  v23 = a1[1];
  if ( v23 )
    a1[1] = v23 - 1;
  *a2 = i;
  return a2;
}

```

## disassembly

```asm
0x18001d9fc  push    rbx
0x18001d9fe  push    rbp
0x18001d9ff  push    rsi
0x18001da00  push    rdi
0x18001da01  push    r12
0x18001da03  push    r14
0x18001da05  push    r15
0x18001da07  sub     rsp, 20h
0x18001da0b  xor     r12d, r12d
0x18001da0e  mov     r15, rdx
0x18001da11  mov     rdi, rcx
0x18001da14  cmp     [r8+19h], r12b
0x18001da18  jz      short loc_18001DA27
0x18001da1a  lea     rcx, aInvalidMapSetT; "invalid map/set<T> iterator"
0x18001da21  call    ?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x18001da27  lea     rsi, [r8+10h]
0x18001da2b  mov     r14, r8
0x18001da2e  mov     r10, [rsi]
0x18001da31  lea     r11, [r8+8]
0x18001da35  mov     rbp, r8
0x18001da38  mov     r9b, [r10+19h]
0x18001da3c  test    r9b, r9b
0x18001da3f  jnz     short loc_18001DA4E
0x18001da41  mov     rcx, r10
0x18001da44  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCExtensionHelperInfoContainer@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCExtensionHelperInfoContainer@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,CExtensionHelperInfoContainer *>>>::_Min(std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,CExtensionHelperInfoContainer *>,void *> *)
0x18001da49  mov     rbx, rax
0x18001da4c  jmp     short loc_18001DA66
0x18001da4e  mov     rbx, [r11]
0x18001da51  jmp     short loc_18001DA60
0x18001da53  cmp     r8, [rbx+10h]
0x18001da57  jnz     short loc_18001DA66
0x18001da59  mov     r8, rbx
0x18001da5c  mov     rbx, [rbx+8]
0x18001da60  cmp     [rbx+19h], r12b
0x18001da64  jz      short loc_18001DA53
0x18001da66  mov     rax, [r14]
0x18001da69  cmp     [rax+19h], r12b
0x18001da6d  jnz     short loc_18001DA82
0x18001da6f  test    r9b, r9b
0x18001da72  jz      short loc_18001DA79
0x18001da74  mov     r10, rax
0x18001da77  jmp     short loc_18001DA82
0x18001da79  mov     r10, [rbx+10h]
0x18001da7d  cmp     rbx, r14
0x18001da80  jnz     short loc_18001DAFF
0x18001da82  mov     r9, [r11]
0x18001da85  cmp     [r10+19h], r12b
0x18001da89  jnz     short loc_18001DA8F
0x18001da8b  mov     [r10+8], r9
0x18001da8f  mov     rax, [rdi]
0x18001da92  cmp     [rax+8], r14
0x18001da96  jnz     short loc_18001DA9E
0x18001da98  mov     [rax+8], r10
0x18001da9c  jmp     short loc_18001DAAC
0x18001da9e  cmp     [r9], r14
0x18001daa1  jnz     short loc_18001DAA8
0x18001daa3  mov     [r9], r10
0x18001daa6  jmp     short loc_18001DAAC
0x18001daa8  mov     [r9+10h], r10
0x18001daac  mov     r8, [rdi]
0x18001daaf  cmp     [r8], r14
0x18001dab2  jnz     short loc_18001DACA
0x18001dab4  cmp     [r10+19h], r12b
0x18001dab8  jz      short loc_18001DABF
0x18001daba  mov     rax, r9
0x18001dabd  jmp     short loc_18001DAC7
0x18001dabf  mov     rcx, r10
0x18001dac2  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCExtensionHelperInfoContainer@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCExtensionHelperInfoContainer@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,CExtensionHelperInfoContainer *>>>::_Min(std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,CExtensionHelperInfoContainer *>,void *> *)
0x18001dac7  mov     [r8], rax
0x18001daca  mov     rdx, [rdi]
0x18001dacd  cmp     [rdx+10h], r14
0x18001dad1  jnz     short loc_18001DAF9
0x18001dad3  cmp     [r10+19h], r12b
0x18001dad7  jz      short loc_18001DADE
0x18001dad9  mov     rcx, r9
0x18001dadc  jmp     short loc_18001DAF5
0x18001dade  mov     rax, [r10+10h]
0x18001dae2  mov     rcx, r10
0x18001dae5  jmp     short loc_18001DAEF
0x18001dae7  mov     rcx, [rcx+10h]
0x18001daeb  mov     rax, [rcx+10h]
0x18001daef  cmp     [rax+19h], r12b
0x18001daf3  jz      short loc_18001DAE7
0x18001daf5  mov     [rdx+10h], rcx
0x18001daf9  lea     rdx, [rbp+18h]
0x18001dafd  jmp     short loc_18001DB67
0x18001daff  mov     [rax+8], rbx
0x18001db03  mov     rax, [r14]
0x18001db06  mov     [rbx], rax
0x18001db09  cmp     rbx, [rsi]
0x18001db0c  jnz     short loc_18001DB13
0x18001db0e  mov     r9, rbx
0x18001db11  jmp     short loc_18001DB32
0x18001db13  mov     r9, [rbx+8]
0x18001db17  cmp     [r10+19h], r12b
0x18001db1b  jnz     short loc_18001DB21
0x18001db1d  mov     [r10+8], r9
0x18001db21  mov     [r9], r10
0x18001db24  mov     rax, [rsi]
0x18001db27  mov     [rbx+10h], rax
0x18001db2b  mov     rax, [rsi]
0x18001db2e  mov     [rax+8], rbx
0x18001db32  mov     rax, [rdi]
0x18001db35  cmp     [rax+8], r14
0x18001db39  jnz     short loc_18001DB41
0x18001db3b  mov     [rax+8], rbx
0x18001db3f  jmp     short loc_18001DB52
0x18001db41  mov     rax, [r11]
0x18001db44  cmp     [rax], r14
0x18001db47  jnz     short loc_18001DB4E
0x18001db49  mov     [rax], rbx
0x18001db4c  jmp     short loc_18001DB52
0x18001db4e  mov     [rax+10h], rbx
0x18001db52  mov     rax, [r11]
0x18001db55  lea     rdx, [r14+18h]
0x18001db59  mov     [rbx+8], rax
0x18001db5d  mov     al, [rdx]
0x18001db5f  mov     cl, [rbx+18h]
0x18001db62  mov     [rbx+18h], al
0x18001db65  mov     [rdx], cl
0x18001db67  mov     r11b, 1
0x18001db6a  cmp     [rdx], r11b
0x18001db6d  jnz     loc_18001DC90
0x18001db73  mov     rax, [rdi]
0x18001db76  cmp     r10, [rax+8]
0x18001db7a  jz      loc_18001DC8C
0x18001db80  cmp     [r10+18h], r11b
0x18001db84  jnz     loc_18001DC8C
0x18001db8a  mov     rdx, [r9]
0x18001db8d  cmp     r10, rdx
0x18001db90  jnz     short loc_18001DC0E
0x18001db92  mov     rdx, [r9+10h]
0x18001db96  cmp     [rdx+18h], r12b
0x18001db9a  jnz     short loc_18001DBB3
0x18001db9c  mov     [rdx+18h], r11b
0x18001dba0  mov     rcx, rdi
0x18001dba3  mov     rdx, r9
0x18001dba6  mov     [r9+18h], r12b
0x18001dbaa  call    ?_Lrotate@?$_Tree@V?$_Tmap_traits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCHelperAttribute@@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCHelperAttribute@@@std@@@5@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCHelperAttribute@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CHelperAttribute *,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,CHelperAttribute *>>,0>>::_Lrotate(std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,CHelperAttribute *>,void *> *)
0x18001dbaf  mov     rdx, [r9+10h]
0x18001dbb3  cmp     [rdx+19h], r12b
0x18001dbb7  jnz     loc_18001DC47
0x18001dbbd  mov     r8, [rdx]
0x18001dbc0  cmp     [r8+18h], r11b
0x18001dbc4  jnz     short loc_18001DBD0
0x18001dbc6  mov     rax, [rdx+10h]
0x18001dbca  cmp     [rax+18h], r11b
0x18001dbce  jz      short loc_18001DC43
0x18001dbd0  mov     rax, [rdx+10h]
0x18001dbd4  cmp     [rax+18h], r11b
0x18001dbd8  jnz     short loc_18001DBEE
0x18001dbda  mov     [r8+18h], r11b
0x18001dbde  mov     rcx, rdi
0x18001dbe1  mov     [rdx+18h], r12b
0x18001dbe5  call    ?_Rrotate@?$_Tree@V?$_Tmap_traits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCExtensionHelperInfo@@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCExtensionHelperInfo@@@std@@@5@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCExtensionHelperInfo@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CExtensionHelperInfo *,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,CExtensionHelperInfo *>>,0>>::_Rrotate(std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,CExtensionHelperInfo *>,void *> *)
0x18001dbea  mov     rdx, [r9+10h]
0x18001dbee  mov     al, [r9+18h]
0x18001dbf2  mov     rcx, rdi
0x18001dbf5  mov     [rdx+18h], al
0x18001dbf8  mov     [r9+18h], r11b
0x18001dbfc  mov     rax, [rdx+10h]
0x18001dc00  mov     rdx, r9
0x18001dc03  mov     [rax+18h], r11b
0x18001dc07  call    ?_Lrotate@?$_Tree@V?$_Tmap_traits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCHelperAttribute@@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCHelperAttribute@@@std@@@5@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCHelperAttribute@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CHelperAttribute *,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,CHelperAttribute *>>,0>>::_Lrotate(std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,CHelperAttribute *>,void *> *)
0x18001dc0c  jmp     short loc_18001DC8C
0x18001dc0e  cmp     [rdx+18h], r12b
0x18001dc12  jnz     short loc_18001DC2A
0x18001dc14  mov     [rdx+18h], r11b
0x18001dc18  mov     rcx, rdi
0x18001dc1b  mov     rdx, r9
0x18001dc1e  mov     [r9+18h], r12b
0x18001dc22  call    ?_Rrotate@?$_Tree@V?$_Tmap_traits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCExtensionHelperInfo@@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCExtensionHelperInfo@@@std@@@5@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCExtensionHelperInfo@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CExtensionHelperInfo *,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,CExtensionHelperInfo *>>,0>>::_Rrotate(std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,CExtensionHelperInfo *>,void *> *)
0x18001dc27  mov     rdx, [r9]
0x18001dc2a  cmp     [rdx+19h], r12b
0x18001dc2e  jnz     short loc_18001DC47
0x18001dc30  mov     rcx, [rdx+10h]
0x18001dc34  cmp     [rcx+18h], r11b
0x18001dc38  jnz     short loc_18001DC53
0x18001dc3a  mov     rax, [rdx]
0x18001dc3d  cmp     [rax+18h], r11b
0x18001dc41  jnz     short loc_18001DC53
0x18001dc43  mov     [rdx+18h], r12b
0x18001dc47  mov     r10, r9
0x18001dc4a  mov     r9, [r9+8]
0x18001dc4e  jmp     loc_18001DB73
0x18001dc53  mov     rax, [rdx]
0x18001dc56  cmp     [rax+18h], r11b
0x18001dc5a  jnz     short loc_18001DC6F
0x18001dc5c  mov     [rcx+18h], r11b
0x18001dc60  mov     rcx, rdi
0x18001dc63  mov     [rdx+18h], r12b
0x18001dc67  call    ?_Lrotate@?$_Tree@V?$_Tmap_traits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCHelperAttribute@@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCHelperAttribute@@@std@@@5@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCHelperAttribute@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CHelperAttribute *,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,CHelperAttribute *>>,0>>::_Lrotate(std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,CHelperAttribute *>,void *> *)
0x18001dc6c  mov     rdx, [r9]
0x18001dc6f  mov     al, [r9+18h]
0x18001dc73  mov     rcx, rdi
0x18001dc76  mov     [rdx+18h], al
0x18001dc79  mov     [r9+18h], r11b
0x18001dc7d  mov     rax, [rdx]
0x18001dc80  mov     rdx, r9
0x18001dc83  mov     [rax+18h], r11b
0x18001dc87  call    ?_Rrotate@?$_Tree@V?$_Tmap_traits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCExtensionHelperInfo@@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCExtensionHelperInfo@@@std@@@5@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCExtensionHelperInfo@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CExtensionHelperInfo *,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,CExtensionHelperInfo *>>,0>>::_Rrotate(std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,CExtensionHelperInfo *>,void *> *)
0x18001dc8c  mov     [r10+18h], r11b
0x18001dc90  mov     rcx, r14
0x18001dc93  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001dc99  mov     rax, [rdi+8]
0x18001dc9d  test    rax, rax
0x18001dca0  jz      short loc_18001DCA9
0x18001dca2  dec     rax
0x18001dca5  mov     [rdi+8], rax
0x18001dca9  mov     [r15], rbx
0x18001dcac  mov     rax, r15
0x18001dcaf  add     rsp, 20h
0x18001dcb3  pop     r15
0x18001dcb5  pop     r14
0x18001dcb7  pop     r12
0x18001dcb9  pop     rdi
0x18001dcba  pop     rsi
0x18001dcbb  pop     rbp
0x18001dcbc  pop     rbx
0x18001dcbd  retn
```
