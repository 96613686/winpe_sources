# DOMNode::GetIids(ulong *,_GUID * *)

- ea: `0x100a9ec0`
- end: `0x100a9fdc`
- name: `?GetIids@DOMNode@@UAGJPAKPAPAU_GUID@@@Z`
- size: `284`
- prototype: `HRESULT __stdcall(DOMNode *this, unsigned int *count, _GUID **iids)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x100921e0`

## callees

- `0x10067bc0`
- `0x100a94b9`
- `0x100a94fb`
- `0x100a9ec0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x100a9f40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x100a9f40`

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
0x100a9ec0  mov     edi, edi
0x100a9ec2  push    ebp
0x100a9ec3  mov     ebp, esp
0x100a9ec5  push    ecx
0x100a9ec6  mov     ecx, [ebp+this]
0x100a9ec9  push    ebx
0x100a9eca  mov     ebx, [ebp+count]
0x100a9ecd  push    esi
0x100a9ece  mov     dword ptr [ebx], 0
0x100a9ed4  mov     eax, [ecx]
0x100a9ed6  mov     esi, [eax+20h]
0x100a9ed9  lea     eax, [ebp+nt]
0x100a9edc  push    eax
0x100a9edd  push    ecx
0x100a9ede  mov     ecx, esi; this
0x100a9ee0  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100a9ee6  call    esi
0x100a9ee8  test    eax, eax
0x100a9eea  js      loc_100A9FA5
0x100a9ef0  mov     eax, [ebp+nt]
0x100a9ef3  dec     eax; switch 12 cases
0x100a9ef4  cmp     eax, 0Bh
0x100a9ef7  ja      def_100A9EFD; jumptable 100A9EFD default case
0x100a9efd  jmp     ds:jpt_100A9EFD[eax*4]; switch jump
0x100a9f04  mov     ecx, offset s_iids_attribute; jumptable 100A9EFD case 2
0x100a9f09  push    [ebp+iids]; iids
0x100a9f0c  mov     edx, ebx; count
0x100a9f0e  call    CopyIids_4_
0x100a9f13  jmp     loc_100A9FA5
0x100a9f18  mov     ecx, offset s_iids_element; jumptable 100A9EFD case 1
0x100a9f1d  jmp     short loc_100A9F09
0x100a9f1f  mov     ecx, offset s_iids_entity; jumptable 100A9EFD case 6
0x100a9f24  jmp     short loc_100A9F09
0x100a9f26  mov     ecx, offset s_iids_entityref; jumptable 100A9EFD case 5
0x100a9f2b  jmp     short loc_100A9F09
0x100a9f2d  mov     ecx, offset s_iids_comment; jumptable 100A9EFD case 8
0x100a9f32  push    [ebp+iids]; iids
0x100a9f35  mov     edx, ebx; count
0x100a9f37  call    CopyIids_5_
0x100a9f3c  jmp     short loc_100A9FA5
0x100a9f3e  push    60h ; '`'; jumptable 100A9EFD case 4
0x100a9f40  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x100a9f46  mov     edx, eax
0x100a9f48  test    edx, edx
0x100a9f4a  jnz     short loc_100A9F53
0x100a9f4c  mov     eax, 8007000Eh
0x100a9f51  jmp     short loc_100A9FA5
0x100a9f53  mov     eax, [ebp+iids]
0x100a9f56  mov     esi, offset s_iids_cdata
0x100a9f5b  push    edi
0x100a9f5c  push    18h
0x100a9f5e  pop     ecx
0x100a9f5f  mov     edi, edx
0x100a9f61  rep movsd
0x100a9f63  mov     [eax], edx
0x100a9f65  xor     eax, eax
0x100a9f67  mov     dword ptr [ebx], 6
0x100a9f6d  pop     edi
0x100a9f6e  jmp     short loc_100A9FA5
0x100a9f70  mov     ecx, offset s_iids_documentfragment; jumptable 100A9EFD case 11
0x100a9f75  jmp     short loc_100A9F09
0x100a9f77  mov     ecx, offset s_iids_document; jumptable 100A9EFD case 9
0x100a9f7c  jmp     short loc_100A9F09
0x100a9f7e  mov     ecx, offset s_iids_documenttype; jumptable 100A9EFD case 10
0x100a9f83  jmp     short loc_100A9F09
0x100a9f85  mov     ecx, offset s_iids_pi; jumptable 100A9EFD case 7
0x100a9f8a  jmp     loc_100A9F09
0x100a9f8f  mov     ecx, offset s_iids_notation; jumptable 100A9EFD case 12
0x100a9f94  jmp     loc_100A9F09
0x100a9f99  mov     ecx, offset s_iids_text; jumptable 100A9EFD case 3
0x100a9f9e  jmp     short loc_100A9F32
0x100a9fa0  mov     eax, 80004005h; jumptable 100A9EFD default case
0x100a9fa5  pop     esi
0x100a9fa6  pop     ebx
0x100a9fa7  leave
0x100a9fa8  retn    0Ch
```
