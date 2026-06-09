# std::_Tree<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::_Erase(std::_Tree_nod<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::_Node *)

- ea: `0x180026308`
- end: `0x18002635f`
- name: `?_Erase@?$_Tree@V?$_Tmap_traits@VCComBSTR@ATL@@VCComVariant@2@U?$less@VCComBSTR@ATL@@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@VCComVariant@2@@std@@@5@$0A@@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@VCComBSTR@ATL@@VCComVariant@2@U?$less@VCComBSTR@ATL@@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@VCComVariant@2@@std@@@5@$0A@@std@@@2@@Z`
- size: `87`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180026308`
- `0x180026368`

## callees

- `0x18000178c`
- `0x180024170`
- `0x180026308`

## pseudocode

```c
void __fastcall std::_Tree<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::_Erase(
        __int64 a1,
        BSTR *a2)
{
  BSTR *v2; // rbx
  BSTR v4; // rdi

  v2 = a2;
  v4 = (BSTR)a2;
  if ( !*((_BYTE *)a2 + 57) )
  {
    do
    {
      std::_Tree<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::_Erase(
        a1,
        *((_QWORD *)v4 + 2));
      v4 = *(BSTR *)v4;
      std::pair<ATL::CComBSTR const,ATL::CComVariant>::~pair<ATL::CComBSTR const,ATL::CComVariant>(v2 + 3);
      operator delete(v2);
      v2 = (BSTR *)v4;
    }
    while ( !*((_BYTE *)v4 + 57) );
  }
}

```

## disassembly

```asm
0x180026308  mov     [rsp+arg_0], rbx
0x18002630d  mov     [rsp+arg_8], rsi
0x180026312  push    rdi
0x180026313  sub     rsp, 20h
0x180026317  cmp     byte ptr [rdx+39h], 0
0x18002631b  mov     rbx, rdx
0x18002631e  mov     rsi, rcx
0x180026321  mov     rdi, rdx
0x180026324  jnz     short loc_18002634F
0x180026326  mov     rdx, [rdi+10h]
0x18002632a  mov     rcx, rsi
0x18002632d  call    ?_Erase@?$_Tree@V?$_Tmap_traits@VCComBSTR@ATL@@VCComVariant@2@U?$less@VCComBSTR@ATL@@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@VCComVariant@2@@std@@@5@$0A@@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@VCComBSTR@ATL@@VCComVariant@2@U?$less@VCComBSTR@ATL@@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@VCComVariant@2@@std@@@5@$0A@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::_Erase(std::_Tree_nod<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::_Node *)
0x180026332  mov     rdi, [rdi]
0x180026335  lea     rcx, [rbx+18h]
0x180026339  call    ??1?$pair@$$CBVCComBSTR@ATL@@VCComVariant@2@@std@@QEAA@XZ; std::pair<ATL::CComBSTR const,ATL::CComVariant>::~pair<ATL::CComBSTR const,ATL::CComVariant>(void)
0x18002633e  mov     rcx, rbx; Block
0x180026341  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180026346  cmp     byte ptr [rdi+39h], 0
0x18002634a  mov     rbx, rdi
0x18002634d  jz      short loc_180026326
0x18002634f  mov     rbx, [rsp+28h+arg_0]
0x180026354  mov     rsi, [rsp+28h+arg_8]
0x180026359  add     rsp, 20h
0x18002635d  pop     rdi
0x18002635e  retn
```
