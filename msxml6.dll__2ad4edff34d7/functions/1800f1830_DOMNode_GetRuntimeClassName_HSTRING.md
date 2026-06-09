# DOMNode::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x1800f1830`
- end: `0x1800f196c`
- name: `?GetRuntimeClassName@DOMNode@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `316`
- prototype: `HRESULT __fastcall(DOMNode *this, HSTRING__ **runtimeName)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800f1980`

## callees

- `0x1800f1830`
- `0x180188010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800f1960`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800f1960`

## string_xrefs

- `0x1800f1948`: `Windows.Data.Xml.Dom.XmlDocument`

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
0x1800f1830  push    rbx
0x1800f1832  sub     rsp, 20h
0x1800f1836  mov     qword ptr [runtimeName], 0
0x1800f183d  mov     rbx, runtimeName
0x1800f1840  mov     rax, [this]
0x1800f1843  lea     runtimeName, [rsp+28h+nt]
0x1800f1848  mov     [rsp+28h+nt], 0
0x1800f1850  mov     rax, [rax+40h]
0x1800f1854  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1859  test    eax, eax
0x1800f185b  js      loc_1800F1966
0x1800f1861  mov     ecx, [rsp+28h+nt]
0x1800f1865  cmp     ecx, 7
0x1800f1868  jg      loc_1800F18F9
0x1800f186e  jz      short loc_1800F18EB
0x1800f1870  sub     ecx, 1
0x1800f1873  jz      short loc_1800F18E2
0x1800f1875  sub     ecx, 1
0x1800f1878  jz      short loc_1800F18D4
0x1800f187a  sub     ecx, 1
0x1800f187d  jz      short loc_1800F18C3
0x1800f187f  sub     ecx, 1
0x1800f1882  jz      short loc_1800F18B2
0x1800f1884  sub     ecx, 1
0x1800f1887  jz      short loc_1800F18A1
0x1800f1889  cmp     ecx, 1
0x1800f188c  jnz     loc_1800F1912
0x1800f1892  lea     edx, [this+1Dh]
0x1800f1895  lea     this, ?RuntimeClass_Windows_Data_Xml_Dom_DtdEntity@@3QBGB; ushort const near * const RuntimeClass_Windows_Data_Xml_Dom_DtdEntity
0x1800f189c  jmp     loc_1800F195D
0x1800f18a1  mov     edx, 27h ; '''
0x1800f18a6  lea     this, ?RuntimeClass_Windows_Data_Xml_Dom_XmlEntityReference@@3QBGB; ushort const near * const RuntimeClass_Windows_Data_Xml_Dom_XmlEntityReference
0x1800f18ad  jmp     loc_1800F195D
0x1800f18b2  mov     edx, 24h ; '$'
0x1800f18b7  lea     this, ?RuntimeClass_Windows_Data_Xml_Dom_XmlCDataSection@@3QBGB; ushort const near * const RuntimeClass_Windows_Data_Xml_Dom_XmlCDataSection
0x1800f18be  jmp     loc_1800F195D
0x1800f18c3  mov     edx, 1Ch
0x1800f18c8  lea     this, ?RuntimeClass_Windows_Data_Xml_Dom_XmlText@@3QBGB; ushort const near * const RuntimeClass_Windows_Data_Xml_Dom_XmlText
0x1800f18cf  jmp     loc_1800F195D
0x1800f18d4  mov     edx, 21h ; '!'
0x1800f18d9  lea     this, ?RuntimeClass_Windows_Data_Xml_Dom_XmlAttribute@@3QBGB; ushort const near * const RuntimeClass_Windows_Data_Xml_Dom_XmlAttribute
0x1800f18e0  jmp     short loc_1800F195D
0x1800f18e2  lea     this, ?RuntimeClass_Windows_Data_Xml_Dom_XmlElement@@3QBGB; ushort const near * const RuntimeClass_Windows_Data_Xml_Dom_XmlElement
0x1800f18e9  jmp     short loc_1800F1958
0x1800f18eb  mov     edx, 2Dh ; '-'
0x1800f18f0  lea     this, ?RuntimeClass_Windows_Data_Xml_Dom_XmlProcessingInstruction@@3QBGB; ushort const near * const RuntimeClass_Windows_Data_Xml_Dom_XmlProcessingInstruction
0x1800f18f7  jmp     short loc_1800F195D
0x1800f18f9  sub     ecx, 8
0x1800f18fc  jz      short loc_1800F1951
0x1800f18fe  sub     ecx, 1
0x1800f1901  jz      short loc_1800F1943
0x1800f1903  sub     ecx, 1
0x1800f1906  jz      short loc_1800F1935
0x1800f1908  sub     ecx, 1
0x1800f190b  jz      short loc_1800F1927
0x1800f190d  cmp     ecx, 1
0x1800f1910  jz      short loc_1800F1919
0x1800f1912  mov     eax, 80004005h
0x1800f1917  jmp     short loc_1800F1966
0x1800f1919  mov     edx, 20h ; ' '
0x1800f191e  lea     this, ?RuntimeClass_Windows_Data_Xml_Dom_DtdNotation@@3QBGB; ushort const near * const RuntimeClass_Windows_Data_Xml_Dom_DtdNotation
0x1800f1925  jmp     short loc_1800F195D
0x1800f1927  mov     edx, 28h ; '('
0x1800f192c  lea     this, ?RuntimeClass_Windows_Data_Xml_Dom_XmlDocumentFragment@@3QBGB; ushort const near * const RuntimeClass_Windows_Data_Xml_Dom_XmlDocumentFragment
0x1800f1933  jmp     short loc_1800F195D
0x1800f1935  mov     edx, 24h ; '$'
0x1800f193a  lea     this, ?RuntimeClass_Windows_Data_Xml_Dom_XmlDocumentType@@3QBGB; ushort const near * const RuntimeClass_Windows_Data_Xml_Dom_XmlDocumentType
0x1800f1941  jmp     short loc_1800F195D
0x1800f1943  mov     edx, 20h ; ' '
0x1800f1948  lea     this, ?RuntimeClass_Windows_Data_Xml_Dom_XmlDocument@@3QBGB; "Windows.Data.Xml.Dom.XmlDocument"
0x1800f194f  jmp     short loc_1800F195D
0x1800f1951  lea     this, ?RuntimeClass_Windows_Data_Xml_Dom_XmlComment@@3QBGB; sourceString
0x1800f1958  mov     edx, 1Fh; length
0x1800f195d  mov     r8, rbx; string
0x1800f1960  call    cs:__imp_WindowsCreateString
0x1800f1966  add     rsp, 20h
0x1800f196a  pop     rbx
0x1800f196b  retn
```
