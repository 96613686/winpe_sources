# DOMNode::GetIids(ulong *,_GUID * *)

- ea: `0x1800f1510`
- end: `0x1800f1698`
- name: `?GetIids@DOMNode@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `392`
- prototype: `HRESULT __fastcall(DOMNode *this, unsigned int *count, _GUID **iids)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800e2b60`

## callees

- `0x1800f0d94`
- `0x1800f0e04`
- `0x1800f1510`
- `0x180188010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800f15a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800f15a2`

## pseudocode

```c
__int64 __fastcall DOMNode::GetIids(DOMNode *this, unsigned int *count, _GUID **iids)
{
  DOMNode_vtbl *v4; // rax
  __int64 result; // rax
  const _GUID *v7; // rcx
  _GUID *v8; // rax
  const _GUID *v9; // rcx
  Windows::Data::Xml::Dom::NodeType nt; // [rsp+30h] [rbp+8h] BYREF

  *count = 0;
  v4 = this->_dispatchEx<IXMLDOMNode,&LIBID_MSXML2,&IID_IXMLDOMNode,0,1>::_dispatch<IXMLDOMNode,&LIBID_MSXML2,&IID_IXMLDOMNode,1>::IXMLDOMNode::IDispatch::IUnknown::__vftable;
  nt = NodeType_Invalid;
  result = ((__int64 (__fastcall *)(DOMNode *, Windows::Data::Xml::Dom::NodeType *))v4->get_nodeValue)(this, &nt);
  if ( (int)result < 0 )
    return result;
  if ( nt > NodeType_ProcessingInstructionNode )
  {
    if ( nt != NodeType_CommentNode )
    {
      switch ( nt )
      {
        case NodeType_DocumentNode:
          v7 = s_iids_document;
          return CopyIids_4_((const _GUID (*)[4])v7, count, iids);
        case NodeType_DocumentTypeNode:
          v7 = s_iids_documenttype;
          return CopyIids_4_((const _GUID (*)[4])v7, count, iids);
        case NodeType_DocumentFragmentNode:
          v7 = s_iids_documentfragment;
          return CopyIids_4_((const _GUID (*)[4])v7, count, iids);
        case NodeType_NotationNode:
          v7 = s_iids_notation;
          return CopyIids_4_((const _GUID (*)[4])v7, count, iids);
      }
      return 2147500037LL;
    }
    v9 = s_iids_comment;
    return CopyIids_5_((const _GUID (*)[5])v9, count, iids);
  }
  switch ( nt )
  {
    case NodeType_ProcessingInstructionNode:
      v7 = s_iids_pi;
      return CopyIids_4_((const _GUID (*)[4])v7, count, iids);
    case NodeType_ElementNode:
      v7 = s_iids_element;
      return CopyIids_4_((const _GUID (*)[4])v7, count, iids);
    case NodeType_AttributeNode:
      v7 = s_iids_attribute;
      return CopyIids_4_((const _GUID (*)[4])v7, count, iids);
    case NodeType_TextNode:
      v9 = s_iids_text;
      return CopyIids_5_((const _GUID (*)[5])v9, count, iids);
  }
  if ( nt != NodeType_DataSectionNode )
  {
    if ( nt == NodeType_EntityReferenceNode )
    {
      v7 = s_iids_entityref;
      return CopyIids_4_((const _GUID (*)[4])v7, count, iids);
    }
    if ( nt == NodeType_EntityNode )
    {
      v7 = s_iids_entity;
      return CopyIids_4_((const _GUID (*)[4])v7, count, iids);
    }
    return 2147500037LL;
  }
  v8 = (_GUID *)CoTaskMemAlloc(0x60u);
  if ( !v8 )
    return 2147942414LL;
  *v8 = s_iids_cdata[0];
  v8[1] = s_iids_cdata[1];
  v8[2] = s_iids_cdata[2];
  v8[3] = s_iids_cdata[3];
  v8[4] = s_iids_cdata[4];
  v8[5] = s_iids_cdata[5];
  *iids = v8;
  result = 0;
  *count = 6;
  return result;
}

```

## disassembly

```asm
0x1800f1510  mov     [rsp+arg_8], rbx
0x1800f1515  push    rdi
0x1800f1516  sub     rsp, 20h
0x1800f151a  mov     dword ptr [count], 0
0x1800f1520  mov     rbx, count
0x1800f1523  mov     rax, [this]
0x1800f1526  lea     count, [rsp+28h+nt]
0x1800f152b  mov     rdi, iids
0x1800f152e  mov     [rsp+28h+nt], 0
0x1800f1536  mov     rax, [rax+40h]
0x1800f153a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f153f  test    eax, eax
0x1800f1541  js      loc_1800F168D
0x1800f1547  mov     ecx, [rsp+28h+nt]
0x1800f154b  cmp     ecx, 7
0x1800f154e  jg      loc_1800F1637
0x1800f1554  jz      loc_1800F162E
0x1800f155a  sub     ecx, 1
0x1800f155d  jz      loc_1800F1625
0x1800f1563  sub     ecx, 1
0x1800f1566  jz      loc_1800F1611
0x1800f156c  sub     ecx, 1
0x1800f156f  jz      loc_1800F1608
0x1800f1575  sub     ecx, 1
0x1800f1578  jz      short loc_1800F159D
0x1800f157a  sub     ecx, 1
0x1800f157d  jz      short loc_1800F1594
0x1800f157f  cmp     ecx, 1
0x1800f1582  jnz     loc_1800F1650
0x1800f1588  lea     this, s_iids_entity
0x1800f158f  jmp     loc_1800F1618
0x1800f1594  lea     this, s_iids_entityref
0x1800f159b  jmp     short loc_1800F1618
0x1800f159d  mov     ecx, 60h ; '`'; cb
0x1800f15a2  call    cs:__imp_CoTaskMemAlloc
0x1800f15a8  test    rax, rax
0x1800f15ab  jnz     short loc_1800F15B7
0x1800f15ad  mov     eax, 8007000Eh
0x1800f15b2  jmp     loc_1800F168D
0x1800f15b7  movaps  xmm0, xmmword ptr cs:s_iids_cdata.Data1
0x1800f15be  movups  xmmword ptr [rax], xmm0
0x1800f15c1  movaps  xmm1, xmmword ptr cs:s_iids_cdata.Data1+10h
0x1800f15c8  movups  xmmword ptr [rax+10h], xmm1
0x1800f15cc  movaps  xmm0, xmmword ptr cs:s_iids_cdata.Data1+20h
0x1800f15d3  movups  xmmword ptr [rax+20h], xmm0
0x1800f15d7  movaps  xmm1, xmmword ptr cs:s_iids_cdata.Data1+30h
0x1800f15de  movups  xmmword ptr [rax+30h], xmm1
0x1800f15e2  movaps  xmm0, xmmword ptr cs:s_iids_cdata.Data1+40h
0x1800f15e9  movups  xmmword ptr [rax+40h], xmm0
0x1800f15ed  movaps  xmm1, xmmword ptr cs:s_iids_cdata.Data1+50h
0x1800f15f4  movups  xmmword ptr [rax+50h], xmm1
0x1800f15f8  mov     [rdi], rax
0x1800f15fb  xor     eax, eax
0x1800f15fd  mov     dword ptr [rbx], 6
0x1800f1603  jmp     loc_1800F168D
0x1800f1608  lea     this, s_iids_text
0x1800f160f  jmp     short loc_1800F1682
0x1800f1611  lea     this, s_iids_attribute; ar
0x1800f1618  mov     iids, rdi; iids
0x1800f161b  mov     count, rbx; count
0x1800f161e  call    CopyIids_4_
0x1800f1623  jmp     short loc_1800F168D
0x1800f1625  lea     this, s_iids_element
0x1800f162c  jmp     short loc_1800F1618
0x1800f162e  lea     this, s_iids_pi
0x1800f1635  jmp     short loc_1800F1618
0x1800f1637  sub     ecx, 8
0x1800f163a  jz      short loc_1800F167B
0x1800f163c  sub     ecx, 1
0x1800f163f  jz      short loc_1800F1672
0x1800f1641  sub     ecx, 1
0x1800f1644  jz      short loc_1800F1669
0x1800f1646  sub     ecx, 1
0x1800f1649  jz      short loc_1800F1660
0x1800f164b  cmp     ecx, 1
0x1800f164e  jz      short loc_1800F1657
0x1800f1650  mov     eax, 80004005h
0x1800f1655  jmp     short loc_1800F168D
0x1800f1657  lea     this, s_iids_notation
0x1800f165e  jmp     short loc_1800F1618
0x1800f1660  lea     this, s_iids_documentfragment
0x1800f1667  jmp     short loc_1800F1618
0x1800f1669  lea     this, s_iids_documenttype
0x1800f1670  jmp     short loc_1800F1618
0x1800f1672  lea     this, s_iids_document
0x1800f1679  jmp     short loc_1800F1618
0x1800f167b  lea     this, s_iids_comment; ar
0x1800f1682  mov     iids, rdi; iids
0x1800f1685  mov     count, rbx; count
0x1800f1688  call    CopyIids_5_
0x1800f168d  mov     rbx, [rsp+28h+arg_8]
0x1800f1692  add     rsp, 20h
0x1800f1696  pop     rdi
0x1800f1697  retn
```
