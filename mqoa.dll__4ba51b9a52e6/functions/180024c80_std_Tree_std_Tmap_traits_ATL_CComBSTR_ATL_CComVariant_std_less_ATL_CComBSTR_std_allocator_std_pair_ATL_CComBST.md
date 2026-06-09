# std::_Tree<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::_Insert(bool,std::_Tree_nod<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::_Node *,std::pair<ATL::CComBSTR const,ATL::CComVariant> const &)

- ea: `0x180024c80`
- end: `0x180024e57`
- name: `?_Insert@?$_Tree@V?$_Tmap_traits@VCComBSTR@ATL@@VCComVariant@2@U?$less@VCComBSTR@ATL@@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@VCComVariant@2@@std@@@5@$0A@@std@@@std@@IEAA?AViterator@12@_NPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@VCComBSTR@ATL@@VCComVariant@2@U?$less@VCComBSTR@ATL@@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@VCComVariant@2@@std@@@5@$0A@@std@@@2@AEBU?$pair@$$CBVCComBSTR@ATL@@VCComVariant@2@@2@@Z`
- size: `471`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800253f4`

## callees

- `0x1800023bb`
- `0x180023fc0`
- `0x180024024`
- `0x180024a04`
- `0x180024c80`
- `0x180024e9c`
- `0x1800250b0`
- `0x1800273b0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 *__fastcall std::_Tree<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::_Insert(
        __int64 a1,
        __int64 *a2,
        char a3,
        __int64 *a4,
        ATL::CComBSTR *a5)
{
  __int64 v9; // r10
  __int64 *v10; // rax
  char v11; // r11
  __int64 v12; // rax
  __int64 *v13; // rax
  __int64 v14; // r9
  __int64 v15; // rdx
  __int64 *v16; // rcx
  __int64 v17; // rax
  _BYTE v19[48]; // [rsp+30h] [rbp-98h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+60h] [rbp-68h] BYREF

  if ( *(_QWORD *)(a1 + 16) >= 0x7FFFFFFFFFFFFFEuLL )
  {
    std::string::string(v19, "map/set<T> too long");
    std::length_error::length_error(pExceptionObject, v19);
    throw (std::length_error *)pExceptionObject;
  }
  v9 = std::_Tree<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::_Buynode(
         -2,
         *(_QWORD *)(a1 + 8),
         (int)a4,
         *(_QWORD *)(a1 + 8),
         a5);
  ++*(_QWORD *)(a1 + 16);
  v10 = *(__int64 **)(a1 + 8);
  v11 = 0;
  if ( a4 == v10 )
  {
    v10[1] = v9;
    **(_QWORD **)(a1 + 8) = v9;
    v12 = *(_QWORD *)(a1 + 8);
LABEL_9:
    *(_QWORD *)(v12 + 16) = v9;
    goto LABEL_10;
  }
  if ( !a3 )
  {
    a4[2] = v9;
    v12 = *(_QWORD *)(a1 + 8);
    if ( a4 != *(__int64 **)(v12 + 16) )
      goto LABEL_10;
    goto LABEL_9;
  }
  *a4 = v9;
  v13 = *(__int64 **)(a1 + 8);
  if ( a4 == (__int64 *)*v13 )
    *v13 = v9;
LABEL_10:
  v14 = v9;
  if ( !*(_BYTE *)(*(_QWORD *)(v9 + 8) + 56LL) )
  {
    do
    {
      v15 = *(_QWORD *)(v14 + 8);
      v16 = *(__int64 **)(v15 + 8);
      v17 = *v16;
      if ( v15 == *v16 )
      {
        v17 = v16[2];
        if ( *(_BYTE *)(v17 + 56) != v11 )
        {
          if ( v14 == *(_QWORD *)(v15 + 16) )
            std::_Tree<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::_Lrotate(a1);
          *(_BYTE *)(*(_QWORD *)(v14 + 8) + 56LL) = 1;
          *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v14 + 8) + 8LL) + 56LL) = v11;
          std::_Tree<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::_Rrotate(
            a1,
            *(_QWORD *)(*(_QWORD *)(v14 + 8) + 8LL));
          continue;
        }
      }
      else if ( *(_BYTE *)(v17 + 56) != v11 )
      {
        if ( v14 == *(_QWORD *)v15 )
          std::_Tree<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::_Rrotate(
            a1,
            v15);
        *(_BYTE *)(*(_QWORD *)(v14 + 8) + 56LL) = 1;
        *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v14 + 8) + 8LL) + 56LL) = v11;
        std::_Tree<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::_Lrotate(a1);
        continue;
      }
      *(_BYTE *)(v15 + 56) = 1;
      *(_BYTE *)(v17 + 56) = 1;
      *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v14 + 8) + 8LL) + 56LL) = v11;
      v14 = *(_QWORD *)(*(_QWORD *)(v14 + 8) + 8LL);
    }
    while ( *(_BYTE *)(*(_QWORD *)(v14 + 8) + 56LL) == v11 );
  }
  *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) + 56LL) = 1;
  *a2 = v9;
  return a2;
}

```

## disassembly

```asm
0x180024c80  mov     [rsp+arg_10], rbx
0x180024c85  push    rsi
0x180024c86  push    rdi
0x180024c87  push    r14
0x180024c89  sub     rsp, 0B0h
0x180024c90  mov     rax, cs:__security_cookie
0x180024c97  xor     rax, rsp
0x180024c9a  mov     [rsp+0C8h+var_28], rax
0x180024ca2  mov     rdi, r9
0x180024ca5  mov     sil, r8b
0x180024ca8  mov     r14, rdx
0x180024cab  mov     rbx, rcx
0x180024cae  mov     rax, [rsp+0C8h+arg_20]
0x180024cb6  mov     rcx, 7FFFFFFFFFFFFFEh; int
0x180024cc0  cmp     [rbx+10h], rcx
0x180024cc4  jb      short loc_180024CF9
0x180024cc6  lea     rdx, aMapSetTTooLong; "map/set<T> too long"
0x180024ccd  lea     rcx, [rsp+0C8h+var_98]
0x180024cd2  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAA@PEBD@Z; std::string::string(char const *)
0x180024cd7  nop
0x180024cd8  lea     rdx, [rsp+0C8h+var_98]
0x180024cdd  lea     rcx, [rsp+0C8h+pExceptionObject]
0x180024ce2  call    ??0length_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@1@@Z; std::length_error::length_error(std::string const &)
0x180024ce7  lea     rdx, _TI3?AVlength_error@std@@; pThrowInfo
0x180024cee  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x180024cf3  call    _CxxThrowException_0
0x180024cf9  mov     rdx, [rbx+8]; int
0x180024cfd  mov     [rsp+0C8h+var_A8], rax; ATL::CComBSTR *
0x180024d02  mov     r9, rdx; int
0x180024d05  mov     r8, rdi; int
0x180024d08  call    ?_Buynode@?$_Tree@V?$_Tmap_traits@VCComBSTR@ATL@@VCComVariant@2@U?$less@VCComBSTR@ATL@@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@VCComVariant@2@@std@@@5@$0A@@std@@@std@@IEAAPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@VCComBSTR@ATL@@VCComVariant@2@U?$less@VCComBSTR@ATL@@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@VCComVariant@2@@std@@@5@$0A@@std@@@2@PEAU342@00AEBU?$pair@$$CBVCComBSTR@ATL@@VCComVariant@2@@2@D@Z; std::_Tree<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::_Buynode(std::_Tree_nod<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::_Node *,std::_Tree_nod<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::_Node *,std::_Tree_nod<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::_Node *,std::pair<ATL::CComBSTR const,ATL::CComVariant> const &,char)
0x180024d0d  mov     r10, rax
0x180024d10  inc     qword ptr [rbx+10h]
0x180024d14  mov     rax, [rbx+8]
0x180024d18  xor     r11d, r11d
0x180024d1b  cmp     rdi, rax
0x180024d1e  jnz     short loc_180024D31
0x180024d20  mov     [rax+8], r10
0x180024d24  mov     rax, [rbx+8]
0x180024d28  mov     [rax], r10
0x180024d2b  mov     rax, [rbx+8]
0x180024d2f  jmp     short loc_180024D55
0x180024d31  test    sil, sil
0x180024d34  jz      short loc_180024D47
0x180024d36  mov     [rdi], r10
0x180024d39  mov     rax, [rbx+8]
0x180024d3d  cmp     rdi, [rax]
0x180024d40  jnz     short loc_180024D59
0x180024d42  mov     [rax], r10
0x180024d45  jmp     short loc_180024D59
0x180024d47  mov     [rdi+10h], r10
0x180024d4b  mov     rax, [rbx+8]
0x180024d4f  cmp     rdi, [rax+10h]
0x180024d53  jnz     short loc_180024D59
0x180024d55  mov     [rax+10h], r10
0x180024d59  mov     r9, r10
0x180024d5c  mov     rax, [r10+8]
0x180024d60  cmp     [rax+38h], r11b
0x180024d64  jnz     loc_180024E21
0x180024d6a  mov     rdx, [r9+8]
0x180024d6e  mov     rcx, [rdx+8]
0x180024d72  mov     rax, [rcx]
0x180024d75  cmp     rdx, rax
0x180024d78  jnz     short loc_180024DBB
0x180024d7a  mov     rax, [rcx+10h]
0x180024d7e  cmp     [rax+38h], r11b
0x180024d82  jz      short loc_180024DC1
0x180024d84  cmp     r9, [rdx+10h]
0x180024d88  jnz     short loc_180024D95
0x180024d8a  mov     r9, rdx
0x180024d8d  mov     rcx, rbx
0x180024d90  call    ?_Lrotate@?$_Tree@V?$_Tmap_traits@VCComBSTR@ATL@@VCComVariant@2@U?$less@VCComBSTR@ATL@@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@VCComVariant@2@@std@@@5@$0A@@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@VCComBSTR@ATL@@VCComVariant@2@U?$less@VCComBSTR@ATL@@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@VCComVariant@2@@std@@@5@$0A@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::_Lrotate(std::_Tree_nod<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::_Node *)
0x180024d95  mov     rax, [r9+8]
0x180024d99  mov     byte ptr [rax+38h], 1
0x180024d9d  mov     rax, [r9+8]
0x180024da1  mov     rcx, [rax+8]
0x180024da5  mov     [rcx+38h], r11b
0x180024da9  mov     rdx, [r9+8]
0x180024dad  mov     rdx, [rdx+8]
0x180024db1  mov     rcx, rbx
0x180024db4  call    ?_Rrotate@?$_Tree@V?$_Tmap_traits@VCComBSTR@ATL@@VCComVariant@2@U?$less@VCComBSTR@ATL@@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@VCComVariant@2@@std@@@5@$0A@@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@VCComBSTR@ATL@@VCComVariant@2@U?$less@VCComBSTR@ATL@@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@VCComVariant@2@@std@@@5@$0A@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::_Rrotate(std::_Tree_nod<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::_Node *)
0x180024db9  jmp     short loc_180024E13
0x180024dbb  cmp     [rax+38h], r11b
0x180024dbf  jnz     short loc_180024DDF
0x180024dc1  mov     byte ptr [rdx+38h], 1
0x180024dc5  mov     byte ptr [rax+38h], 1
0x180024dc9  mov     rax, [r9+8]
0x180024dcd  mov     rcx, [rax+8]
0x180024dd1  mov     [rcx+38h], r11b
0x180024dd5  mov     rax, [r9+8]
0x180024dd9  mov     r9, [rax+8]
0x180024ddd  jmp     short loc_180024E13
0x180024ddf  cmp     r9, [rdx]
0x180024de2  jnz     short loc_180024DEF
0x180024de4  mov     r9, rdx
0x180024de7  mov     rcx, rbx
0x180024dea  call    ?_Rrotate@?$_Tree@V?$_Tmap_traits@VCComBSTR@ATL@@VCComVariant@2@U?$less@VCComBSTR@ATL@@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@VCComVariant@2@@std@@@5@$0A@@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@VCComBSTR@ATL@@VCComVariant@2@U?$less@VCComBSTR@ATL@@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@VCComVariant@2@@std@@@5@$0A@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::_Rrotate(std::_Tree_nod<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::_Node *)
0x180024def  mov     rax, [r9+8]
0x180024df3  mov     byte ptr [rax+38h], 1
0x180024df7  mov     rax, [r9+8]
0x180024dfb  mov     rcx, [rax+8]
0x180024dff  mov     [rcx+38h], r11b
0x180024e03  mov     rdx, [r9+8]
0x180024e07  mov     rdx, [rdx+8]
0x180024e0b  mov     rcx, rbx
0x180024e0e  call    ?_Lrotate@?$_Tree@V?$_Tmap_traits@VCComBSTR@ATL@@VCComVariant@2@U?$less@VCComBSTR@ATL@@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@VCComVariant@2@@std@@@5@$0A@@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@VCComBSTR@ATL@@VCComVariant@2@U?$less@VCComBSTR@ATL@@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@VCComVariant@2@@std@@@5@$0A@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::_Lrotate(std::_Tree_nod<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::_Node *)
0x180024e13  mov     rcx, [r9+8]
0x180024e17  cmp     [rcx+38h], r11b
0x180024e1b  jz      loc_180024D6A
0x180024e21  mov     rcx, [rbx+8]
0x180024e25  mov     rdx, [rcx+8]
0x180024e29  mov     byte ptr [rdx+38h], 1
0x180024e2d  mov     [r14], r10
0x180024e30  mov     rax, r14
0x180024e33  mov     rcx, [rsp+0C8h+var_28]
0x180024e3b  xor     rcx, rsp; StackCookie
0x180024e3e  call    __security_check_cookie
0x180024e43  mov     rbx, [rsp+0C8h+arg_10]
0x180024e4b  add     rsp, 0B0h
0x180024e52  pop     r14
0x180024e54  pop     rdi
0x180024e55  pop     rsi
0x180024e56  retn
```
