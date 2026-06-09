# DOMNode::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x100aa3f0`
- end: `0x100aa4f0`
- name: `?GetRuntimeClassName@DOMNode@@UAGJPAPAUHSTRING__@@@Z`
- size: `256`
- prototype: `HRESULT __stdcall(DOMNode *this, HSTRING__ **runtimeName)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x100aa500`

## callees

- `0x10067b20`
- `0x100aa3f0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x100aa43c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x100aa43c`

## string_xrefs

- `0x100aa4ab`: `Windows.Data.Xml.Dom.XmlText`
- `0x100aa4a1`: `Windows.Data.Xml.Dom.DtdNotation`
- `0x100aa45b`: `Windows.Data.Xml.Dom.XmlEntityReference`
- `0x100aa483`: `Windows.Data.Xml.Dom.XmlDocument`
- `0x100aa48d`: `Windows.Data.Xml.Dom.XmlDocumentType`
- `0x100aa437`: `Windows.Data.Xml.Dom.XmlAttribute`
- `0x100aa465`: `Windows.Data.Xml.Dom.XmlComment`
- `0x100aa479`: `Windows.Data.Xml.Dom.XmlDocumentFragment`
- `0x100aa46f`: `Windows.Data.Xml.Dom.XmlCDataSection`
- `0x100aa451`: `Windows.Data.Xml.Dom.DtdEntity`
- `0x100aa447`: `Windows.Data.Xml.Dom.XmlElement`
- `0x100aa497`: `Windows.Data.Xml.Dom.XmlProcessingInstruction`

## pseudocode

```c
HRESULT __stdcall DOMNode::GetRuntimeClassName(DOMNode *this, HSTRING__ **runtimeName)
{
  HRESULT result; // eax
  Windows::Data::Xml::Dom::NodeType nt; // [esp+8h] [ebp-4h] BYREF

  *runtimeName = 0;
  result = ((int (__thiscall *)(HRESULT (__stdcall *)(IXMLDOMNode *, tagVARIANT *), DOMNode *, Windows::Data::Xml::Dom::NodeType *))this->get_nodeValue)(
             this->get_nodeValue,
             this,
             &nt);
  if ( result >= 0 )
  {
    switch ( nt )
    {
      case NodeType_ElementNode:
        result = WindowsCreateString(L"Windows.Data.Xml.Dom.XmlElement", 0x1Fu, runtimeName);
        break;
      case NodeType_AttributeNode:
        result = WindowsCreateString(L"Windows.Data.Xml.Dom.XmlAttribute", 0x21u, runtimeName);
        break;
      case NodeType_TextNode:
        result = WindowsCreateString(L"Windows.Data.Xml.Dom.XmlText", 0x1Cu, runtimeName);
        break;
      case NodeType_DataSectionNode:
        result = WindowsCreateString(L"Windows.Data.Xml.Dom.XmlCDataSection", 0x24u, runtimeName);
        break;
      case NodeType_EntityReferenceNode:
        result = WindowsCreateString(L"Windows.Data.Xml.Dom.XmlEntityReference", 0x27u, runtimeName);
        break;
      case NodeType_EntityNode:
        result = WindowsCreateString(L"Windows.Data.Xml.Dom.DtdEntity", 0x1Eu, runtimeName);
        break;
      case NodeType_ProcessingInstructionNode:
        result = WindowsCreateString(L"Windows.Data.Xml.Dom.XmlProcessingInstruction", 0x2Du, runtimeName);
        break;
      case NodeType_CommentNode:
        result = WindowsCreateString(L"Windows.Data.Xml.Dom.XmlComment", 0x1Fu, runtimeName);
        break;
      case NodeType_DocumentNode:
        result = WindowsCreateString(L"Windows.Data.Xml.Dom.XmlDocument", 0x20u, runtimeName);
        break;
      case NodeType_DocumentTypeNode:
        result = WindowsCreateString(L"Windows.Data.Xml.Dom.XmlDocumentType", 0x24u, runtimeName);
        break;
      case NodeType_DocumentFragmentNode:
        result = WindowsCreateString(L"Windows.Data.Xml.Dom.XmlDocumentFragment", 0x28u, runtimeName);
        break;
      case NodeType_NotationNode:
        result = WindowsCreateString(L"Windows.Data.Xml.Dom.DtdNotation", 0x20u, runtimeName);
        break;
      default:
        result = -2147467259;
        break;
    }
  }
  return result;
}

```

## disassembly

```asm
0x100aa3f0  mov     edi, edi
0x100aa3f2  push    ebp
0x100aa3f3  mov     ebp, esp
0x100aa3f5  push    ecx
0x100aa3f6  mov     ecx, [ebp+this]
0x100aa3f9  push    esi
0x100aa3fa  push    edi
0x100aa3fb  mov     edi, [ebp+runtimeName]
0x100aa3fe  mov     dword ptr [edi], 0
0x100aa404  mov     eax, [ecx]
0x100aa406  mov     esi, [eax+20h]
0x100aa409  lea     eax, [ebp+nt]
0x100aa40c  push    eax
0x100aa40d  push    ecx
0x100aa40e  mov     ecx, esi; this
0x100aa410  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100aa416  call    esi
0x100aa418  test    eax, eax
0x100aa41a  js      loc_100AA4B7
0x100aa420  mov     eax, [ebp+nt]
0x100aa423  dec     eax; switch 12 cases
0x100aa424  cmp     eax, 0Bh
0x100aa427  ja      def_100AA42D; jumptable 100AA42D default case
0x100aa42d  jmp     ds:jpt_100AA42D[eax*4]; switch jump
0x100aa434  push    edi; jumptable 100AA42D case 2
0x100aa435  push    21h ; '!'; length
0x100aa437  push    offset ?RuntimeClass_Windows_Data_Xml_Dom_XmlAttribute@@3QBGB; "Windows.Data.Xml.Dom.XmlAttribute"
0x100aa43c  call    ds:__imp__WindowsCreateString@12; WindowsCreateString(x,x,x)
0x100aa442  jmp     short loc_100AA4B7
0x100aa444  push    edi; jumptable 100AA42D case 1
0x100aa445  push    1Fh
0x100aa447  push    offset ?RuntimeClass_Windows_Data_Xml_Dom_XmlElement@@3QBGB; "Windows.Data.Xml.Dom.XmlElement"
0x100aa44c  jmp     short loc_100AA43C
0x100aa44e  push    edi; jumptable 100AA42D case 6
0x100aa44f  push    1Eh
0x100aa451  push    offset ?RuntimeClass_Windows_Data_Xml_Dom_DtdEntity@@3QBGB; "Windows.Data.Xml.Dom.DtdEntity"
0x100aa456  jmp     short loc_100AA43C
0x100aa458  push    edi; jumptable 100AA42D case 5
0x100aa459  push    27h ; '''
0x100aa45b  push    offset ?RuntimeClass_Windows_Data_Xml_Dom_XmlEntityReference@@3QBGB; "Windows.Data.Xml.Dom.XmlEntityReference"
0x100aa460  jmp     short loc_100AA43C
0x100aa462  push    edi; jumptable 100AA42D case 8
0x100aa463  push    1Fh
0x100aa465  push    offset ?RuntimeClass_Windows_Data_Xml_Dom_XmlComment@@3QBGB; "Windows.Data.Xml.Dom.XmlComment"
0x100aa46a  jmp     short loc_100AA43C
0x100aa46c  push    edi; jumptable 100AA42D case 4
0x100aa46d  push    24h ; '$'
0x100aa46f  push    offset ?RuntimeClass_Windows_Data_Xml_Dom_XmlCDataSection@@3QBGB; "Windows.Data.Xml.Dom.XmlCDataSection"
0x100aa474  jmp     short loc_100AA43C
0x100aa476  push    edi; jumptable 100AA42D case 11
0x100aa477  push    28h ; '('
0x100aa479  push    offset ?RuntimeClass_Windows_Data_Xml_Dom_XmlDocumentFragment@@3QBGB; "Windows.Data.Xml.Dom.XmlDocumentFragmen"...
0x100aa47e  jmp     short loc_100AA43C
0x100aa480  push    edi; jumptable 100AA42D case 9
0x100aa481  push    20h ; ' '
0x100aa483  push    offset ?RuntimeClass_Windows_Data_Xml_Dom_XmlDocument@@3QBGB; "Windows.Data.Xml.Dom.XmlDocument"
0x100aa488  jmp     short loc_100AA43C
0x100aa48a  push    edi; jumptable 100AA42D case 10
0x100aa48b  push    24h ; '$'
0x100aa48d  push    offset ?RuntimeClass_Windows_Data_Xml_Dom_XmlDocumentType@@3QBGB; "Windows.Data.Xml.Dom.XmlDocumentType"
0x100aa492  jmp     short loc_100AA43C
0x100aa494  push    edi; jumptable 100AA42D case 7
0x100aa495  push    2Dh ; '-'
0x100aa497  push    offset ?RuntimeClass_Windows_Data_Xml_Dom_XmlProcessingInstruction@@3QBGB; "Windows.Data.Xml.Dom.XmlProcessingInstr"...
0x100aa49c  jmp     short loc_100AA43C
0x100aa49e  push    edi; jumptable 100AA42D case 12
0x100aa49f  push    20h ; ' '
0x100aa4a1  push    offset ?RuntimeClass_Windows_Data_Xml_Dom_DtdNotation@@3QBGB; "Windows.Data.Xml.Dom.DtdNotation"
0x100aa4a6  jmp     short loc_100AA43C
0x100aa4a8  push    edi; jumptable 100AA42D case 3
0x100aa4a9  push    1Ch
0x100aa4ab  push    offset ?RuntimeClass_Windows_Data_Xml_Dom_XmlText@@3QBGB; "Windows.Data.Xml.Dom.XmlText"
0x100aa4b0  jmp     short loc_100AA43C
0x100aa4b2  mov     eax, 80004005h; jumptable 100AA42D default case
0x100aa4b7  pop     edi
0x100aa4b8  pop     esi
0x100aa4b9  leave
0x100aa4ba  retn    8
```
