# DOMNode::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x1800f3cb0`
- end: `0x1800f3df3`
- name: `?GetRuntimeClassName@DOMNode@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `323`
- prototype: `HRESULT __fastcall(DOMNode *this, HSTRING__ **runtimeName)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800f3e00`

## callees

- `0x1800f3cb0`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800f3de0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800f3de0`

## string_xrefs

- `0x1800f3dc8`: `Windows.Data.Xml.Dom.XmlDocument`

## pseudocode

```c
HRESULT __fastcall DOMNode::GetRuntimeClassName(DOMNode *this, HSTRING__ **runtimeName)
{
  DOMNode_vtbl *v3; // rax
  HRESULT result; // eax
  UINT32 v5; // edx
  const wchar_t *v6; // rcx
  Windows::Data::Xml::Dom::NodeType nt; // [rsp+30h] [rbp+8h] BYREF

  *runtimeName = 0;
  v3 = this->_dispatchEx<IXMLDOMNode,&LIBID_MSXML2,&IID_IXMLDOMNode,0,1>::_dispatch<IXMLDOMNode,&LIBID_MSXML2,&IID_IXMLDOMNode,1>::IXMLDOMNode::IDispatch::IUnknown::__vftable;
  nt = NodeType_Invalid;
  result = v3->get_nodeValue(this, (tagVARIANT *)&nt);
  if ( result >= 0 )
  {
    if ( nt > NodeType_ProcessingInstructionNode )
    {
      if ( nt != NodeType_CommentNode )
      {
        switch ( nt )
        {
          case NodeType_DocumentNode:
            v5 = 32;
            v6 = L"Windows.Data.Xml.Dom.XmlDocument";
            return WindowsCreateString(v6, v5, runtimeName);
          case NodeType_DocumentTypeNode:
            v5 = 36;
            v6 = RuntimeClass_Windows_Data_Xml_Dom_XmlDocumentType;
            return WindowsCreateString(v6, v5, runtimeName);
          case NodeType_DocumentFragmentNode:
            v5 = 40;
            v6 = RuntimeClass_Windows_Data_Xml_Dom_XmlDocumentFragment;
            return WindowsCreateString(v6, v5, runtimeName);
          case NodeType_NotationNode:
            v5 = 32;
            v6 = RuntimeClass_Windows_Data_Xml_Dom_DtdNotation;
            return WindowsCreateString(v6, v5, runtimeName);
        }
        return -2147467259;
      }
      v6 = RuntimeClass_Windows_Data_Xml_Dom_XmlComment;
    }
    else
    {
      if ( nt == NodeType_ProcessingInstructionNode )
      {
        v5 = 45;
        v6 = RuntimeClass_Windows_Data_Xml_Dom_XmlProcessingInstruction;
        return WindowsCreateString(v6, v5, runtimeName);
      }
      if ( nt != NodeType_ElementNode )
      {
        switch ( nt )
        {
          case NodeType_AttributeNode:
            v5 = 33;
            v6 = RuntimeClass_Windows_Data_Xml_Dom_XmlAttribute;
            return WindowsCreateString(v6, v5, runtimeName);
          case NodeType_TextNode:
            v5 = 28;
            v6 = RuntimeClass_Windows_Data_Xml_Dom_XmlText;
            return WindowsCreateString(v6, v5, runtimeName);
          case NodeType_DataSectionNode:
            v5 = 36;
            v6 = RuntimeClass_Windows_Data_Xml_Dom_XmlCDataSection;
            return WindowsCreateString(v6, v5, runtimeName);
          case NodeType_EntityReferenceNode:
            v5 = 39;
            v6 = RuntimeClass_Windows_Data_Xml_Dom_XmlEntityReference;
            return WindowsCreateString(v6, v5, runtimeName);
          case NodeType_EntityNode:
            v5 = 30;
            v6 = RuntimeClass_Windows_Data_Xml_Dom_DtdEntity;
            return WindowsCreateString(v6, v5, runtimeName);
        }
        return -2147467259;
      }
      v6 = RuntimeClass_Windows_Data_Xml_Dom_XmlElement;
    }
    v5 = 31;
    return WindowsCreateString(v6, v5, runtimeName);
  }
  return result;
}

```

## disassembly

```asm
0x1800f3cb0  push    rbx
0x1800f3cb2  sub     rsp, 20h
0x1800f3cb6  mov     qword ptr [runtimeName], 0
0x1800f3cbd  mov     rbx, runtimeName
0x1800f3cc0  mov     rax, [this]
0x1800f3cc3  lea     runtimeName, [rsp+28h+nt]
0x1800f3cc8  mov     [rsp+28h+nt], 0
0x1800f3cd0  mov     rax, [rax+40h]
0x1800f3cd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3cd9  test    eax, eax
0x1800f3cdb  js      loc_1800F3DEC
0x1800f3ce1  mov     ecx, [rsp+28h+nt]
0x1800f3ce5  cmp     ecx, 7
0x1800f3ce8  jg      loc_1800F3D79
0x1800f3cee  jz      short loc_1800F3D6B
0x1800f3cf0  sub     ecx, 1
0x1800f3cf3  jz      short loc_1800F3D62
0x1800f3cf5  sub     ecx, 1
0x1800f3cf8  jz      short loc_1800F3D54
0x1800f3cfa  sub     ecx, 1
0x1800f3cfd  jz      short loc_1800F3D43
0x1800f3cff  sub     ecx, 1
0x1800f3d02  jz      short loc_1800F3D32
0x1800f3d04  sub     ecx, 1
0x1800f3d07  jz      short loc_1800F3D21
0x1800f3d09  cmp     ecx, 1
0x1800f3d0c  jnz     loc_1800F3D92
0x1800f3d12  lea     edx, [this+1Dh]
0x1800f3d15  lea     this, ?RuntimeClass_Windows_Data_Xml_Dom_DtdEntity@@3QBGB; ushort const near * const RuntimeClass_Windows_Data_Xml_Dom_DtdEntity
0x1800f3d1c  jmp     loc_1800F3DDD
0x1800f3d21  mov     edx, 27h ; '''
0x1800f3d26  lea     this, ?RuntimeClass_Windows_Data_Xml_Dom_XmlEntityReference@@3QBGB; ushort const near * const RuntimeClass_Windows_Data_Xml_Dom_XmlEntityReference
0x1800f3d2d  jmp     loc_1800F3DDD
0x1800f3d32  mov     edx, 24h ; '$'
0x1800f3d37  lea     this, ?RuntimeClass_Windows_Data_Xml_Dom_XmlCDataSection@@3QBGB; ushort const near * const RuntimeClass_Windows_Data_Xml_Dom_XmlCDataSection
0x1800f3d3e  jmp     loc_1800F3DDD
0x1800f3d43  mov     edx, 1Ch
0x1800f3d48  lea     this, ?RuntimeClass_Windows_Data_Xml_Dom_XmlText@@3QBGB; ushort const near * const RuntimeClass_Windows_Data_Xml_Dom_XmlText
0x1800f3d4f  jmp     loc_1800F3DDD
0x1800f3d54  mov     edx, 21h ; '!'
0x1800f3d59  lea     this, ?RuntimeClass_Windows_Data_Xml_Dom_XmlAttribute@@3QBGB; ushort const near * const RuntimeClass_Windows_Data_Xml_Dom_XmlAttribute
0x1800f3d60  jmp     short loc_1800F3DDD
0x1800f3d62  lea     this, ?RuntimeClass_Windows_Data_Xml_Dom_XmlElement@@3QBGB; ushort const near * const RuntimeClass_Windows_Data_Xml_Dom_XmlElement
0x1800f3d69  jmp     short loc_1800F3DD8
0x1800f3d6b  mov     edx, 2Dh ; '-'
0x1800f3d70  lea     this, ?RuntimeClass_Windows_Data_Xml_Dom_XmlProcessingInstruction@@3QBGB; ushort const near * const RuntimeClass_Windows_Data_Xml_Dom_XmlProcessingInstruction
0x1800f3d77  jmp     short loc_1800F3DDD
0x1800f3d79  sub     ecx, 8
0x1800f3d7c  jz      short loc_1800F3DD1
0x1800f3d7e  sub     ecx, 1
0x1800f3d81  jz      short loc_1800F3DC3
0x1800f3d83  sub     ecx, 1
0x1800f3d86  jz      short loc_1800F3DB5
0x1800f3d88  sub     ecx, 1
0x1800f3d8b  jz      short loc_1800F3DA7
0x1800f3d8d  cmp     ecx, 1
0x1800f3d90  jz      short loc_1800F3D99
0x1800f3d92  mov     eax, 80004005h
0x1800f3d97  jmp     short loc_1800F3DEC
0x1800f3d99  mov     edx, 20h ; ' '
0x1800f3d9e  lea     this, ?RuntimeClass_Windows_Data_Xml_Dom_DtdNotation@@3QBGB; ushort const near * const RuntimeClass_Windows_Data_Xml_Dom_DtdNotation
0x1800f3da5  jmp     short loc_1800F3DDD
0x1800f3da7  mov     edx, 28h ; '('
0x1800f3dac  lea     this, ?RuntimeClass_Windows_Data_Xml_Dom_XmlDocumentFragment@@3QBGB; ushort const near * const RuntimeClass_Windows_Data_Xml_Dom_XmlDocumentFragment
0x1800f3db3  jmp     short loc_1800F3DDD
0x1800f3db5  mov     edx, 24h ; '$'
0x1800f3dba  lea     this, ?RuntimeClass_Windows_Data_Xml_Dom_XmlDocumentType@@3QBGB; ushort const near * const RuntimeClass_Windows_Data_Xml_Dom_XmlDocumentType
0x1800f3dc1  jmp     short loc_1800F3DDD
0x1800f3dc3  mov     edx, 20h ; ' '
0x1800f3dc8  lea     this, ?RuntimeClass_Windows_Data_Xml_Dom_XmlDocument@@3QBGB; "Windows.Data.Xml.Dom.XmlDocument"
0x1800f3dcf  jmp     short loc_1800F3DDD
0x1800f3dd1  lea     this, ?RuntimeClass_Windows_Data_Xml_Dom_XmlComment@@3QBGB; sourceString
0x1800f3dd8  mov     edx, 1Fh; length
0x1800f3ddd  mov     r8, rbx; string
0x1800f3de0  call    cs:__imp_WindowsCreateString
0x1800f3de7  nop     dword ptr [rax+rax+00h]
0x1800f3dec  add     rsp, 20h
0x1800f3df0  pop     rbx
0x1800f3df1  retn
```
