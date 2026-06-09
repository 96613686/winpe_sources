# DOMNode::GetIids(ulong *,_GUID * *)

- ea: `0x100a9fd0`
- end: `0x100aa0ec`
- name: `?GetIids@DOMNode@@UAGJPAKPAPAU_GUID@@@Z`
- size: `284`
- prototype: `HRESULT __stdcall(DOMNode *this, unsigned int *count, _GUID **iids)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x100922a0`

## callees

- `0x10067b20`
- `0x100a95c9`
- `0x100a960b`
- `0x100a9fd0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x100aa050`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x100aa050`

## pseudocode

```c
HRESULT __stdcall DOMNode::GetIids(DOMNode *this, unsigned int *count, _GUID **iids)
{
  HRESULT result; // eax
  const _GUID *v4; // ecx
  const _GUID *v5; // ecx
  _GUID *v6; // edx
  Windows::Data::Xml::Dom::NodeType nt; // [esp+8h] [ebp-4h] BYREF

  *count = 0;
  result = ((int (__thiscall *)(HRESULT (__stdcall *)(IXMLDOMNode *, tagVARIANT *), DOMNode *, Windows::Data::Xml::Dom::NodeType *))this->get_nodeValue)(
             this->get_nodeValue,
             this,
             &nt);
  if ( result >= 0 )
  {
    switch ( nt )
    {
      case NodeType_ElementNode:
        v4 = s_iids_element;
        goto LABEL_4;
      case NodeType_AttributeNode:
        v4 = s_iids_attribute;
        goto LABEL_4;
      case NodeType_TextNode:
        v5 = s_iids_text;
        return CopyIids_5_((const _GUID (*)[5])v5, count, iids);
      case NodeType_DataSectionNode:
        v6 = (_GUID *)CoTaskMemAlloc(0x60u);
        if ( !v6 )
          return -2147024882;
        qmemcpy(v6, s_iids_cdata, 0x60u);
        *iids = v6;
        result = 0;
        *count = 6;
        return result;
      case NodeType_EntityReferenceNode:
        v4 = s_iids_entityref;
        goto LABEL_4;
      case NodeType_EntityNode:
        v4 = s_iids_entity;
        goto LABEL_4;
      case NodeType_ProcessingInstructionNode:
        v4 = s_iids_pi;
        goto LABEL_4;
      case NodeType_CommentNode:
        v5 = s_iids_comment;
        return CopyIids_5_((const _GUID (*)[5])v5, count, iids);
      case NodeType_DocumentNode:
        v4 = s_iids_document;
        goto LABEL_4;
      case NodeType_DocumentTypeNode:
        v4 = s_iids_documenttype;
        goto LABEL_4;
      case NodeType_DocumentFragmentNode:
        v4 = s_iids_documentfragment;
        goto LABEL_4;
      case NodeType_NotationNode:
        v4 = s_iids_notation;
LABEL_4:
        result = CopyIids_4_((const _GUID (*)[4])v4, count, iids);
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
0x100a9fd0  mov     edi, edi
0x100a9fd2  push    ebp
0x100a9fd3  mov     ebp, esp
0x100a9fd5  push    ecx
0x100a9fd6  mov     ecx, [ebp+this]
0x100a9fd9  push    ebx
0x100a9fda  mov     ebx, [ebp+count]
0x100a9fdd  push    esi
0x100a9fde  mov     dword ptr [ebx], 0
0x100a9fe4  mov     eax, [ecx]
0x100a9fe6  mov     esi, [eax+20h]
0x100a9fe9  lea     eax, [ebp+nt]
0x100a9fec  push    eax
0x100a9fed  push    ecx
0x100a9fee  mov     ecx, esi; this
0x100a9ff0  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100a9ff6  call    esi
0x100a9ff8  test    eax, eax
0x100a9ffa  js      loc_100AA0B5
0x100aa000  mov     eax, [ebp+nt]
0x100aa003  dec     eax; switch 12 cases
0x100aa004  cmp     eax, 0Bh
0x100aa007  ja      def_100AA00D; jumptable 100AA00D default case
0x100aa00d  jmp     ds:jpt_100AA00D[eax*4]; switch jump
0x100aa014  mov     ecx, offset s_iids_attribute; jumptable 100AA00D case 2
0x100aa019  push    [ebp+iids]; iids
0x100aa01c  mov     edx, ebx; count
0x100aa01e  call    CopyIids_4_
0x100aa023  jmp     loc_100AA0B5
0x100aa028  mov     ecx, offset s_iids_element; jumptable 100AA00D case 1
0x100aa02d  jmp     short loc_100AA019
0x100aa02f  mov     ecx, offset s_iids_entity; jumptable 100AA00D case 6
0x100aa034  jmp     short loc_100AA019
0x100aa036  mov     ecx, offset s_iids_entityref; jumptable 100AA00D case 5
0x100aa03b  jmp     short loc_100AA019
0x100aa03d  mov     ecx, offset s_iids_comment; jumptable 100AA00D case 8
0x100aa042  push    [ebp+iids]; iids
0x100aa045  mov     edx, ebx; count
0x100aa047  call    CopyIids_5_
0x100aa04c  jmp     short loc_100AA0B5
0x100aa04e  push    60h ; '`'; jumptable 100AA00D case 4
0x100aa050  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x100aa056  mov     edx, eax
0x100aa058  test    edx, edx
0x100aa05a  jnz     short loc_100AA063
0x100aa05c  mov     eax, 8007000Eh
0x100aa061  jmp     short loc_100AA0B5
0x100aa063  mov     eax, [ebp+iids]
0x100aa066  mov     esi, offset s_iids_cdata
0x100aa06b  push    edi
0x100aa06c  push    18h
0x100aa06e  pop     ecx
0x100aa06f  mov     edi, edx
0x100aa071  rep movsd
0x100aa073  mov     [eax], edx
0x100aa075  xor     eax, eax
0x100aa077  mov     dword ptr [ebx], 6
0x100aa07d  pop     edi
0x100aa07e  jmp     short loc_100AA0B5
0x100aa080  mov     ecx, offset s_iids_documentfragment; jumptable 100AA00D case 11
0x100aa085  jmp     short loc_100AA019
0x100aa087  mov     ecx, offset s_iids_document; jumptable 100AA00D case 9
0x100aa08c  jmp     short loc_100AA019
0x100aa08e  mov     ecx, offset s_iids_documenttype; jumptable 100AA00D case 10
0x100aa093  jmp     short loc_100AA019
0x100aa095  mov     ecx, offset s_iids_pi; jumptable 100AA00D case 7
0x100aa09a  jmp     loc_100AA019
0x100aa09f  mov     ecx, offset s_iids_notation; jumptable 100AA00D case 12
0x100aa0a4  jmp     loc_100AA019
0x100aa0a9  mov     ecx, offset s_iids_text; jumptable 100AA00D case 3
0x100aa0ae  jmp     short loc_100AA042
0x100aa0b0  mov     eax, 80004005h; jumptable 100AA00D default case
0x100aa0b5  pop     esi
0x100aa0b6  pop     ebx
0x100aa0b7  leave
0x100aa0b8  retn    0Ch
```
