# std::_Tree<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::erase(std::_Tree<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::iterator)

- ea: `0x180026450`
- end: `0x180026785`
- name: `?erase@?$_Tree@V?$_Tmap_traits@VCComBSTR@ATL@@VCComVariant@2@U?$less@VCComBSTR@ATL@@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@VCComVariant@2@@std@@@5@$0A@@std@@@std@@QEAA?AViterator@12@V312@@Z`
- size: `821`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180026368`

## callees

- `0x18000178c`
- `0x1800023bb`
- `0x180023fc0`
- `0x180024170`
- `0x180024e9c`
- `0x180024eec`
- `0x1800250b0`
- `0x1800255f8`
- `0x180026450`
- `0x1800273b0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 **__fastcall std::_Tree<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::erase(
        __int64 a1,
        __int64 **a2,
        __int64 *a3)
{
  __int64 *v5; // r14
  __int64 *v6; // rbp
  _QWORD *v7; // rsi
  _QWORD *v8; // r10
  char v9; // r9
  __int64 **v10; // r11
  __int64 *i; // rbx
  __int64 *v12; // r9
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 *v16; // rcx
  __int64 j; // rax
  _BYTE *v18; // rdx
  __int64 v19; // rax
  _QWORD *v20; // rax
  char v21; // cl
  char v22; // r11
  __int64 v23; // rcx
  __int64 v24; // rcx
  _BYTE v26[48]; // [rsp+20h] [rbp-A8h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+50h] [rbp-78h] BYREF

  if ( *((_BYTE *)a3 + 57) )
  {
    std::string::string(v26, "invalid map/set<T> iterator");
    std::out_of_range::out_of_range(pExceptionObject, v26, 0);
    throw (std::out_of_range *)pExceptionObject;
  }
  v5 = a3;
  v6 = a3;
  v7 = a3 + 2;
  v8 = (_QWORD *)a3[2];
  v9 = *((_BYTE *)v8 + 57);
  v10 = (__int64 **)(a3 + 1);
  if ( v9 )
  {
    for ( i = *v10; !*((_BYTE *)i + 57) && a3 == (__int64 *)i[2]; i = (__int64 *)i[1] )
      a3 = i;
  }
  else
  {
    i = (__int64 *)std::_Tree<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::_Min(a3[2]);
  }
  if ( *(_BYTE *)(*v5 + 57) )
    goto LABEL_13;
  if ( v9 )
  {
    v8 = (_QWORD *)*v5;
LABEL_13:
    v12 = *v10;
    if ( !*((_BYTE *)v8 + 57) )
      v8[1] = v12;
    v13 = *(_QWORD *)(a1 + 8);
    if ( *(__int64 **)(v13 + 8) == v5 )
    {
      *(_QWORD *)(v13 + 8) = v8;
    }
    else if ( (__int64 *)*v12 == v5 )
    {
      *v12 = (__int64)v8;
    }
    else
    {
      v12[2] = (__int64)v8;
    }
    a3 = *(__int64 **)(a1 + 8);
    if ( (__int64 *)*a3 == v5 )
    {
      if ( *((_BYTE *)v8 + 57) )
        v14 = (__int64)v12;
      else
        v14 = std::_Tree<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::_Min(v8);
      *a3 = v14;
    }
    v15 = *(_QWORD *)(a1 + 8);
    if ( *(__int64 **)(v15 + 16) == v5 )
    {
      if ( *((_BYTE *)v8 + 57) )
      {
        v16 = v12;
      }
      else
      {
        v16 = v8;
        for ( j = v8[2]; !*(_BYTE *)(j + 57); j = v16[2] )
          v16 = (__int64 *)v16[2];
      }
      *(_QWORD *)(v15 + 16) = v16;
    }
    v18 = v6 + 7;
    goto LABEL_44;
  }
  v8 = (_QWORD *)i[2];
  if ( i == v5 )
    goto LABEL_13;
  *(_QWORD *)(*v5 + 8) = i;
  *i = *v5;
  if ( i == (__int64 *)*v7 )
  {
    v12 = i;
  }
  else
  {
    v12 = (__int64 *)i[1];
    if ( !*((_BYTE *)v8 + 57) )
      v8[1] = v12;
    *v12 = (__int64)v8;
    i[2] = *v7;
    *(_QWORD *)(*v7 + 8LL) = i;
  }
  v19 = *(_QWORD *)(a1 + 8);
  if ( *(__int64 **)(v19 + 8) == v5 )
  {
    *(_QWORD *)(v19 + 8) = i;
  }
  else
  {
    v20 = *v10;
    if ( (__int64 *)**v10 == v5 )
      *v20 = i;
    else
      v20[2] = i;
  }
  i[1] = (__int64)*v10;
  v18 = v5 + 7;
  v21 = *((_BYTE *)i + 56);
  *((_BYTE *)i + 56) = *((_BYTE *)v5 + 56);
  *((_BYTE *)v5 + 56) = v21;
LABEL_44:
  v22 = 1;
  if ( *v18 != 1 )
    goto LABEL_67;
  while ( v8 != *(_QWORD **)(*(_QWORD *)(a1 + 8) + 8LL) && *((_BYTE *)v8 + 56) == v22 )
  {
    v18 = (_BYTE *)*v12;
    if ( v8 == (_QWORD *)*v12 )
    {
      v18 = (_BYTE *)v12[2];
      if ( !v18[56] )
      {
        v18[56] = v22;
        *((_BYTE *)v12 + 56) = 0;
        std::_Tree<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::_Lrotate(a1);
        v18 = (_BYTE *)v12[2];
      }
      if ( !v18[57] )
      {
        a3 = *(__int64 **)v18;
        if ( *(_BYTE *)(*(_QWORD *)v18 + 56LL) != v22 || *(_BYTE *)(*((_QWORD *)v18 + 2) + 56LL) != v22 )
        {
          if ( *(_BYTE *)(*((_QWORD *)v18 + 2) + 56LL) == v22 )
          {
            *((_BYTE *)a3 + 56) = v22;
            v18[56] = 0;
            std::_Tree<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::_Rrotate(
              a1,
              v18);
            v18 = (_BYTE *)v12[2];
          }
          v18[56] = *((_BYTE *)v12 + 56);
          *((_BYTE *)v12 + 56) = v22;
          *(_BYTE *)(*((_QWORD *)v18 + 2) + 56LL) = v22;
          std::_Tree<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::_Lrotate(a1);
          break;
        }
LABEL_61:
        v18[56] = 0;
      }
    }
    else
    {
      if ( !v18[56] )
      {
        v18[56] = v22;
        *((_BYTE *)v12 + 56) = 0;
        std::_Tree<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::_Rrotate(
          a1,
          v12);
        v18 = (_BYTE *)*v12;
      }
      if ( !v18[57] )
      {
        v23 = *((_QWORD *)v18 + 2);
        if ( *(_BYTE *)(v23 + 56) != v22 || *(_BYTE *)(*(_QWORD *)v18 + 56LL) != v22 )
        {
          if ( *(_BYTE *)(*(_QWORD *)v18 + 56LL) == v22 )
          {
            *(_BYTE *)(v23 + 56) = v22;
            v18[56] = 0;
            std::_Tree<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::_Lrotate(a1);
            v18 = (_BYTE *)*v12;
          }
          v18[56] = *((_BYTE *)v12 + 56);
          *((_BYTE *)v12 + 56) = v22;
          *(_BYTE *)(*(_QWORD *)v18 + 56LL) = v22;
          std::_Tree<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::_Rrotate(
            a1,
            v12);
          break;
        }
        goto LABEL_61;
      }
    }
    v8 = v12;
    v12 = (__int64 *)v12[1];
  }
  *((_BYTE *)v8 + 56) = v22;
LABEL_67:
  std::pair<ATL::CComBSTR const,ATL::CComVariant>::~pair<ATL::CComBSTR const,ATL::CComVariant>(v5 + 3, v18, a3, v12);
  operator delete(v5);
  v24 = *(_QWORD *)(a1 + 16);
  if ( v24 )
    *(_QWORD *)(a1 + 16) = v24 - 1;
  *a2 = i;
  return a2;
}

```

## disassembly

```asm
0x180026450  mov     [rsp+arg_10], rbx
0x180026455  mov     [rsp+arg_18], rbp
0x18002645a  push    rsi
0x18002645b  push    rdi
0x18002645c  push    r12
0x18002645e  push    r14
0x180026460  push    r15
0x180026462  sub     rsp, 0A0h
0x180026469  mov     rax, cs:__security_cookie
0x180026470  xor     rax, rsp
0x180026473  mov     [rsp+0C8h+var_38], rax
0x18002647b  mov     r15, rdx
0x18002647e  mov     rdi, rcx
0x180026481  xor     r12d, r12d
0x180026484  cmp     [r8+39h], r12b
0x180026488  jz      short loc_1800264C0
0x18002648a  lea     rdx, aInvalidMapSetT; "invalid map/set<T> iterator"
0x180026491  lea     rcx, [rsp+0C8h+var_A8]
0x180026496  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAA@PEBD@Z; std::string::string(char const *)
0x18002649b  nop
0x18002649c  xor     r8d, r8d
0x18002649f  lea     rdx, [rsp+0C8h+var_A8]
0x1800264a4  lea     rcx, [rsp+0C8h+pExceptionObject]
0x1800264a9  call    ??0out_of_range@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@1@PEAV_STL70@@@Z; std::out_of_range::out_of_range(std::string const &,_STL70 *)
0x1800264ae  lea     rdx, _TI3?AVout_of_range@std@@; pThrowInfo
0x1800264b5  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x1800264ba  call    _CxxThrowException_0
0x1800264c0  mov     r14, r8
0x1800264c3  mov     rbp, r8
0x1800264c6  lea     rsi, [r8+10h]
0x1800264ca  mov     r10, [rsi]
0x1800264cd  mov     r9b, [r10+39h]
0x1800264d1  lea     r11, [r8+8]
0x1800264d5  test    r9b, r9b
0x1800264d8  jnz     short loc_1800264E7
0x1800264da  mov     rcx, r10
0x1800264dd  call    ?_Min@?$_Tree@V?$_Tmap_traits@VCComBSTR@ATL@@VCComVariant@2@U?$less@VCComBSTR@ATL@@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@VCComVariant@2@@std@@@5@$0A@@std@@@std@@KAPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@VCComBSTR@ATL@@VCComVariant@2@U?$less@VCComBSTR@ATL@@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@VCComVariant@2@@std@@@5@$0A@@std@@@2@PEAU342@@Z; std::_Tree<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::_Min(std::_Tree_nod<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::_Node *)
0x1800264e2  mov     rbx, rax
0x1800264e5  jmp     short loc_1800264FF
0x1800264e7  mov     rbx, [r11]
0x1800264ea  jmp     short loc_1800264F9
0x1800264ec  cmp     r8, [rbx+10h]
0x1800264f0  jnz     short loc_1800264FF
0x1800264f2  mov     r8, rbx
0x1800264f5  mov     rbx, [rbx+8]
0x1800264f9  cmp     [rbx+39h], r12b
0x1800264fd  jz      short loc_1800264EC
0x1800264ff  mov     rax, [r14]
0x180026502  cmp     [rax+39h], r12b
0x180026506  jnz     short loc_18002651F
0x180026508  test    r9b, r9b
0x18002650b  jz      short loc_180026512
0x18002650d  mov     r10, rax
0x180026510  jmp     short loc_18002651F
0x180026512  mov     r10, [rbx+10h]
0x180026516  cmp     rbx, r14
0x180026519  jnz     loc_18002659F
0x18002651f  mov     r9, [r11]
0x180026522  cmp     [r10+39h], r12b
0x180026526  jnz     short loc_18002652C
0x180026528  mov     [r10+8], r9
0x18002652c  mov     rax, [rdi+8]
0x180026530  cmp     [rax+8], r14
0x180026534  jnz     short loc_18002653C
0x180026536  mov     [rax+8], r10
0x18002653a  jmp     short loc_18002654A
0x18002653c  cmp     [r9], r14
0x18002653f  jnz     short loc_180026546
0x180026541  mov     [r9], r10
0x180026544  jmp     short loc_18002654A
0x180026546  mov     [r9+10h], r10
0x18002654a  mov     r8, [rdi+8]
0x18002654e  cmp     [r8], r14
0x180026551  jnz     short loc_180026569
0x180026553  cmp     [r10+39h], r12b
0x180026557  jz      short loc_18002655E
0x180026559  mov     rax, r9
0x18002655c  jmp     short loc_180026566
0x18002655e  mov     rcx, r10
0x180026561  call    ?_Min@?$_Tree@V?$_Tmap_traits@VCComBSTR@ATL@@VCComVariant@2@U?$less@VCComBSTR@ATL@@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@VCComVariant@2@@std@@@5@$0A@@std@@@std@@KAPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@VCComBSTR@ATL@@VCComVariant@2@U?$less@VCComBSTR@ATL@@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@VCComVariant@2@@std@@@5@$0A@@std@@@2@PEAU342@@Z; std::_Tree<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::_Min(std::_Tree_nod<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::_Node *)
0x180026566  mov     [r8], rax
0x180026569  mov     rdx, [rdi+8]
0x18002656d  cmp     [rdx+10h], r14
0x180026571  jnz     short loc_180026599
0x180026573  cmp     [r10+39h], r12b
0x180026577  jz      short loc_18002657E
0x180026579  mov     rcx, r9
0x18002657c  jmp     short loc_180026595
0x18002657e  mov     rcx, r10
0x180026581  mov     rax, [r10+10h]
0x180026585  jmp     short loc_18002658F
0x180026587  mov     rcx, [rcx+10h]
0x18002658b  mov     rax, [rcx+10h]
0x18002658f  cmp     [rax+39h], r12b
0x180026593  jz      short loc_180026587
0x180026595  mov     [rdx+10h], rcx
0x180026599  lea     rdx, [rbp+38h]
0x18002659d  jmp     short loc_180026608
0x18002659f  mov     [rax+8], rbx
0x1800265a3  mov     rax, [r14]
0x1800265a6  mov     [rbx], rax
0x1800265a9  cmp     rbx, [rsi]
0x1800265ac  jnz     short loc_1800265B3
0x1800265ae  mov     r9, rbx
0x1800265b1  jmp     short loc_1800265D2
0x1800265b3  mov     r9, [rbx+8]
0x1800265b7  cmp     [r10+39h], r12b
0x1800265bb  jnz     short loc_1800265C1
0x1800265bd  mov     [r10+8], r9
0x1800265c1  mov     [r9], r10
0x1800265c4  mov     rax, [rsi]
0x1800265c7  mov     [rbx+10h], rax
0x1800265cb  mov     rax, [rsi]
0x1800265ce  mov     [rax+8], rbx
0x1800265d2  mov     rax, [rdi+8]
0x1800265d6  cmp     [rax+8], r14
0x1800265da  jnz     short loc_1800265E2
0x1800265dc  mov     [rax+8], rbx
0x1800265e0  jmp     short loc_1800265F3
0x1800265e2  mov     rax, [r11]
0x1800265e5  cmp     [rax], r14
0x1800265e8  jnz     short loc_1800265EF
0x1800265ea  mov     [rax], rbx
0x1800265ed  jmp     short loc_1800265F3
0x1800265ef  mov     [rax+10h], rbx
0x1800265f3  mov     rax, [r11]
0x1800265f6  mov     [rbx+8], rax
0x1800265fa  lea     rdx, [r14+38h]
0x1800265fe  mov     cl, [rbx+38h]
0x180026601  mov     al, [rdx]
0x180026603  mov     [rbx+38h], al
0x180026606  mov     [rdx], cl
0x180026608  mov     r11b, 1
0x18002660b  cmp     [rdx], r11b
0x18002660e  jnz     loc_180026732
0x180026614  mov     rax, [rdi+8]
0x180026618  cmp     r10, [rax+8]
0x18002661c  jz      loc_18002672E
0x180026622  cmp     [r10+38h], r11b
0x180026626  jnz     loc_18002672E
0x18002662c  mov     rdx, [r9]
0x18002662f  cmp     r10, rdx
0x180026632  jnz     short loc_1800266B0
0x180026634  mov     rdx, [r9+10h]
0x180026638  cmp     [rdx+38h], r12b
0x18002663c  jnz     short loc_180026655
0x18002663e  mov     [rdx+38h], r11b
0x180026642  mov     [r9+38h], r12b
0x180026646  mov     rdx, r9
0x180026649  mov     rcx, rdi
0x18002664c  call    ?_Lrotate@?$_Tree@V?$_Tmap_traits@VCComBSTR@ATL@@VCComVariant@2@U?$less@VCComBSTR@ATL@@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@VCComVariant@2@@std@@@5@$0A@@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@VCComBSTR@ATL@@VCComVariant@2@U?$less@VCComBSTR@ATL@@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@VCComVariant@2@@std@@@5@$0A@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::_Lrotate(std::_Tree_nod<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::_Node *)
0x180026651  mov     rdx, [r9+10h]
0x180026655  cmp     [rdx+39h], r12b
0x180026659  jnz     loc_1800266E9
0x18002665f  mov     r8, [rdx]
0x180026662  cmp     [r8+38h], r11b
0x180026666  jnz     short loc_180026672
0x180026668  mov     rax, [rdx+10h]
0x18002666c  cmp     [rax+38h], r11b
0x180026670  jz      short loc_1800266E5
0x180026672  mov     rax, [rdx+10h]
0x180026676  cmp     [rax+38h], r11b
0x18002667a  jnz     short loc_180026690
0x18002667c  mov     [r8+38h], r11b
0x180026680  mov     [rdx+38h], r12b
0x180026684  mov     rcx, rdi
0x180026687  call    ?_Rrotate@?$_Tree@V?$_Tmap_traits@VCComBSTR@ATL@@VCComVariant@2@U?$less@VCComBSTR@ATL@@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@VCComVariant@2@@std@@@5@$0A@@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@VCComBSTR@ATL@@VCComVariant@2@U?$less@VCComBSTR@ATL@@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@VCComVariant@2@@std@@@5@$0A@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::_Rrotate(std::_Tree_nod<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::_Node *)
0x18002668c  mov     rdx, [r9+10h]
0x180026690  mov     al, [r9+38h]
0x180026694  mov     [rdx+38h], al
0x180026697  mov     [r9+38h], r11b
0x18002669b  mov     rax, [rdx+10h]
0x18002669f  mov     [rax+38h], r11b
0x1800266a3  mov     rdx, r9
0x1800266a6  mov     rcx, rdi
0x1800266a9  call    ?_Lrotate@?$_Tree@V?$_Tmap_traits@VCComBSTR@ATL@@VCComVariant@2@U?$less@VCComBSTR@ATL@@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@VCComVariant@2@@std@@@5@$0A@@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@VCComBSTR@ATL@@VCComVariant@2@U?$less@VCComBSTR@ATL@@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@VCComVariant@2@@std@@@5@$0A@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::_Lrotate(std::_Tree_nod<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::_Node *)
0x1800266ae  jmp     short loc_18002672E
0x1800266b0  cmp     [rdx+38h], r12b
0x1800266b4  jnz     short loc_1800266CC
0x1800266b6  mov     [rdx+38h], r11b
0x1800266ba  mov     [r9+38h], r12b
0x1800266be  mov     rdx, r9
0x1800266c1  mov     rcx, rdi
0x1800266c4  call    ?_Rrotate@?$_Tree@V?$_Tmap_traits@VCComBSTR@ATL@@VCComVariant@2@U?$less@VCComBSTR@ATL@@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@VCComVariant@2@@std@@@5@$0A@@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@VCComBSTR@ATL@@VCComVariant@2@U?$less@VCComBSTR@ATL@@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@VCComVariant@2@@std@@@5@$0A@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::_Rrotate(std::_Tree_nod<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::_Node *)
0x1800266c9  mov     rdx, [r9]
0x1800266cc  cmp     [rdx+39h], r12b
0x1800266d0  jnz     short loc_1800266E9
0x1800266d2  mov     rcx, [rdx+10h]
0x1800266d6  cmp     [rcx+38h], r11b
0x1800266da  jnz     short loc_1800266F5
0x1800266dc  mov     rax, [rdx]
0x1800266df  cmp     [rax+38h], r11b
0x1800266e3  jnz     short loc_1800266F5
0x1800266e5  mov     [rdx+38h], r12b
0x1800266e9  mov     r10, r9
0x1800266ec  mov     r9, [r9+8]
0x1800266f0  jmp     loc_180026614
0x1800266f5  mov     rax, [rdx]
0x1800266f8  cmp     [rax+38h], r11b
0x1800266fc  jnz     short loc_180026711
0x1800266fe  mov     [rcx+38h], r11b
0x180026702  mov     [rdx+38h], r12b
0x180026706  mov     rcx, rdi
0x180026709  call    ?_Lrotate@?$_Tree@V?$_Tmap_traits@VCComBSTR@ATL@@VCComVariant@2@U?$less@VCComBSTR@ATL@@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@VCComVariant@2@@std@@@5@$0A@@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@VCComBSTR@ATL@@VCComVariant@2@U?$less@VCComBSTR@ATL@@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@VCComVariant@2@@std@@@5@$0A@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::_Lrotate(std::_Tree_nod<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::_Node *)
0x18002670e  mov     rdx, [r9]
0x180026711  mov     al, [r9+38h]
0x180026715  mov     [rdx+38h], al
0x180026718  mov     [r9+38h], r11b
0x18002671c  mov     rax, [rdx]
0x18002671f  mov     [rax+38h], r11b
0x180026723  mov     rdx, r9
0x180026726  mov     rcx, rdi
0x180026729  call    ?_Rrotate@?$_Tree@V?$_Tmap_traits@VCComBSTR@ATL@@VCComVariant@2@U?$less@VCComBSTR@ATL@@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@VCComVariant@2@@std@@@5@$0A@@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@VCComBSTR@ATL@@VCComVariant@2@U?$less@VCComBSTR@ATL@@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@VCComVariant@2@@std@@@5@$0A@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::_Rrotate(std::_Tree_nod<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::_Node *)
0x18002672e  mov     [r10+38h], r11b
0x180026732  lea     rcx, [r14+18h]
0x180026736  call    ??1?$pair@$$CBVCComBSTR@ATL@@VCComVariant@2@@std@@QEAA@XZ; std::pair<ATL::CComBSTR const,ATL::CComVariant>::~pair<ATL::CComBSTR const,ATL::CComVariant>(void)
0x18002673b  mov     rcx, r14; Block
0x18002673e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180026743  mov     rcx, [rdi+10h]
0x180026747  test    rcx, rcx
0x18002674a  jz      short loc_180026753
0x18002674c  dec     rcx
0x18002674f  mov     [rdi+10h], rcx
0x180026753  mov     [r15], rbx
0x180026756  mov     rax, r15
0x180026759  mov     rcx, [rsp+0C8h+var_38]
0x180026761  xor     rcx, rsp; StackCookie
0x180026764  call    __security_check_cookie
0x180026769  lea     r11, [rsp+0C8h+var_28]
0x180026771  mov     rbx, [r11+40h]
0x180026775  mov     rbp, [r11+48h]
0x180026779  mov     rsp, r11
0x18002677c  pop     r15
0x18002677e  pop     r14
0x180026780  pop     r12
0x180026782  pop     rdi
0x180026783  pop     rsi
0x180026784  retn
```
