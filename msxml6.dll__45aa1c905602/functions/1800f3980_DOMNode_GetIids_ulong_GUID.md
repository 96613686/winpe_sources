# DOMNode::GetIids(ulong *,_GUID * *)

- ea: `0x1800f3980`
- end: `0x1800f3b12`
- name: `?GetIids@DOMNode@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `402`
- prototype: `HRESULT __fastcall(DOMNode *this, unsigned int *count, _GUID **iids)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800e4ca0`

## callees

- `0x1800f31f4`
- `0x1800f326c`
- `0x1800f3980`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800f3a15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800f3a15`

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
0x1800f3980  mov     [rsp+arg_8], rbx
0x1800f3985  push    rdi
0x1800f3986  sub     rsp, 20h
0x1800f398a  mov     dword ptr [count], 0
0x1800f3990  mov     rbx, count
0x1800f3993  mov     rax, [this]
0x1800f3996  lea     count, [rsp+28h+nt]
0x1800f399b  mov     rdi, iids
0x1800f399e  mov     [rsp+28h+nt], 0
0x1800f39a6  mov     rax, [rax+40h]
0x1800f39aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f39af  test    eax, eax
0x1800f39b1  js      loc_1800F3B06
0x1800f39b7  mov     ecx, [rsp+28h+nt]
0x1800f39bb  cmp     ecx, 7
0x1800f39be  jg      loc_1800F3AB0
0x1800f39c4  jz      loc_1800F3AA7
0x1800f39ca  sub     ecx, 1
0x1800f39cd  jz      loc_1800F3A9E
0x1800f39d3  sub     ecx, 1
0x1800f39d6  jz      loc_1800F3A8A
0x1800f39dc  sub     ecx, 1
0x1800f39df  jz      loc_1800F3A81
0x1800f39e5  sub     ecx, 1
0x1800f39e8  jz      short loc_1800F3A10
0x1800f39ea  sub     ecx, 1
0x1800f39ed  jz      short loc_1800F3A04
0x1800f39ef  cmp     ecx, 1
0x1800f39f2  jnz     loc_1800F3AC9
0x1800f39f8  lea     this, s_iids_entity
0x1800f39ff  jmp     loc_1800F3A91
0x1800f3a04  lea     this, s_iids_entityref
0x1800f3a0b  jmp     loc_1800F3A91
0x1800f3a10  mov     ecx, 60h ; '`'; cb
0x1800f3a15  call    cs:__imp_CoTaskMemAlloc
0x1800f3a1c  nop     dword ptr [rax+rax+00h]
0x1800f3a21  test    rax, rax
0x1800f3a24  jnz     short loc_1800F3A30
0x1800f3a26  mov     eax, 8007000Eh
0x1800f3a2b  jmp     loc_1800F3B06
0x1800f3a30  movaps  xmm0, xmmword ptr cs:s_iids_cdata.Data1
0x1800f3a37  movups  xmmword ptr [rax], xmm0
0x1800f3a3a  movaps  xmm1, xmmword ptr cs:s_iids_cdata.Data1+10h
0x1800f3a41  movups  xmmword ptr [rax+10h], xmm1
0x1800f3a45  movaps  xmm0, xmmword ptr cs:s_iids_cdata.Data1+20h
0x1800f3a4c  movups  xmmword ptr [rax+20h], xmm0
0x1800f3a50  movaps  xmm1, xmmword ptr cs:s_iids_cdata.Data1+30h
0x1800f3a57  movups  xmmword ptr [rax+30h], xmm1
0x1800f3a5b  movaps  xmm0, xmmword ptr cs:s_iids_cdata.Data1+40h
0x1800f3a62  movups  xmmword ptr [rax+40h], xmm0
0x1800f3a66  movaps  xmm1, xmmword ptr cs:s_iids_cdata.Data1+50h
0x1800f3a6d  movups  xmmword ptr [rax+50h], xmm1
0x1800f3a71  mov     [rdi], rax
0x1800f3a74  xor     eax, eax
0x1800f3a76  mov     dword ptr [rbx], 6
0x1800f3a7c  jmp     loc_1800F3B06
0x1800f3a81  lea     this, s_iids_text
0x1800f3a88  jmp     short loc_1800F3AFB
0x1800f3a8a  lea     this, s_iids_attribute; ar
0x1800f3a91  mov     iids, rdi; iids
0x1800f3a94  mov     count, rbx; count
0x1800f3a97  call    CopyIids_4_
0x1800f3a9c  jmp     short loc_1800F3B06
0x1800f3a9e  lea     this, s_iids_element
0x1800f3aa5  jmp     short loc_1800F3A91
0x1800f3aa7  lea     this, s_iids_pi
0x1800f3aae  jmp     short loc_1800F3A91
0x1800f3ab0  sub     ecx, 8
0x1800f3ab3  jz      short loc_1800F3AF4
0x1800f3ab5  sub     ecx, 1
0x1800f3ab8  jz      short loc_1800F3AEB
0x1800f3aba  sub     ecx, 1
0x1800f3abd  jz      short loc_1800F3AE2
0x1800f3abf  sub     ecx, 1
0x1800f3ac2  jz      short loc_1800F3AD9
0x1800f3ac4  cmp     ecx, 1
0x1800f3ac7  jz      short loc_1800F3AD0
0x1800f3ac9  mov     eax, 80004005h
0x1800f3ace  jmp     short loc_1800F3B06
0x1800f3ad0  lea     this, s_iids_notation
0x1800f3ad7  jmp     short loc_1800F3A91
0x1800f3ad9  lea     this, s_iids_documentfragment
0x1800f3ae0  jmp     short loc_1800F3A91
0x1800f3ae2  lea     this, s_iids_documenttype
0x1800f3ae9  jmp     short loc_1800F3A91
0x1800f3aeb  lea     this, s_iids_document
0x1800f3af2  jmp     short loc_1800F3A91
0x1800f3af4  lea     this, s_iids_comment; ar
0x1800f3afb  mov     iids, rdi; iids
0x1800f3afe  mov     count, rbx; count
0x1800f3b01  call    CopyIids_5_
0x1800f3b06  mov     rbx, [rsp+28h+arg_8]
0x1800f3b0b  add     rsp, 20h
0x1800f3b0f  pop     rdi
0x1800f3b10  retn
```
