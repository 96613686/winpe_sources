# IE4NodeFactory::CreateNode(IXMLNodeSource *,void *,ushort,_XML_NODE_INFO * *)

- ea: `0x180057b70`
- end: `0x180058077`
- name: `?CreateNode@IE4NodeFactory@@UEAAJPEAUIXMLNodeSource@@PEAXGPEAPEAU_XML_NODE_INFO@@@Z`
- size: `1287`
- prototype: `__int64 __usercall@<rax>(IE4NodeFactory *__hidden this@<rcx>, struct IXMLNodeSource *@<rdx>, void *@<r8>, unsigned __int16@<r9w>, struct _XML_NODE_INFO **)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config`

## callees

- `0x18000f368`
- `0x18000f578`
- `0x180012000`
- `0x1800325d8`
- `0x18003e89c`
- `0x18004df38`
- `0x180057b70`
- `0x180064034`
- `0x1800647d8`
- `0x180077614`
- `0x18007aac0`
- `0x1800f9778`
- `0x1800f9fc4`
- `0x1800fa048`
- `0x180107010`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x180057faf`
- `msvcrt!_resetstkoflw` at `0x180057faf`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180058002`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180058002`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180057f9d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18005803a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180057f9d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18005803a`

## string_xrefs

- `0x180057e40`: `XML-SPACE`

## pseudocode

```c
__int64 __fastcall IE4NodeFactory::CreateNode(
        IE4NodeFactory *this,
        struct IXMLNodeSource *a2,
        Node *a3,
        unsigned __int16 a4,
        struct _XML_NODE_INFO **a5)
{
  struct _XML_NODE_INFO *v7; // rbx
  char v8; // dl
  char v9; // r13
  struct _XML_NODE_INFO **v10; // rax
  int i; // edi
  struct _XML_NODE_INFO *v12; // r15
  Node *v13; // r12
  __int64 v14; // rax
  int v15; // ebx
  struct NameDef *NameDef; // rax
  __int64 v17; // rax
  struct Node *NodeLastChild; // rax
  Node *v19; // rax
  int v20; // ecx
  Node *v21; // r15
  __int64 v22; // rax
  String *v23; // rax
  struct _XML_NODE_INFO *v24; // rdi
  __int64 v25; // rbx
  __int64 v26; // rbx
  bool v27; // di
  char v29; // [rsp+40h] [rbp-78h]
  bool v30; // [rsp+41h] [rbp-77h]
  char v31; // [rsp+43h] [rbp-75h]
  int v32; // [rsp+44h] [rbp-74h]
  Node *v33; // [rsp+48h] [rbp-70h]
  struct _XML_NODE_INFO *v34; // [rsp+50h] [rbp-68h]
  struct _XML_NODE_INFO *v35; // [rsp+78h] [rbp-40h]
  struct _XML_NODE_INFO **v36; // [rsp+E0h] [rbp+28h]

  v33 = 0;
  v7 = 0;
  v34 = 0;
  v8 = 0;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  v9 = 0;
  v10 = a5;
  v35 = *a5;
  for ( i = a4; ; --i )
  {
    v32 = i;
    if ( i <= 0 )
      break;
    v12 = *v10;
    v36 = v10 + 1;
    v13 = 0;
    v14 = *((unsigned int *)*v10 + 1);
    v15 = *((_DWORD *)&nodeProperties + v14);
    if ( *((_DWORD *)this + 20) )
    {
      if ( (v15 & 0x20) == 0 && ((_DWORD)v14 == 13 || (_DWORD)v14 == 18) )
      {
        _NDNodeFactory::bufferAppend(this, *((const unsigned __int16 **)v12 + 2), *((_DWORD *)v12 + 6));
        goto LABEL_33;
      }
      _NDNodeFactory::bufferAttach(this);
      v8 = v29;
    }
    if ( (v15 & 0x20) == 0 )
    {
      if ( (v15 & 0x100) != 0 )
      {
        switch ( *((_DWORD *)v12 + 1) )
        {
          case 0xD:
            goto LABEL_25;
          case 0xE:
            if ( ((unsigned int (__fastcall *)(Node *))a3->lpVtbl[1].get_Name)(a3) == 5 )
            {
              Node::_appendText(a3, *((const unsigned __int16 **)v12 + 2), *((_DWORD *)v12 + 6));
              goto LABEL_33;
            }
            break;
          case 0x12:
            if ( !*((_BYTE *)this + 84) && (!*((_BYTE *)this + 86) || v8) )
            {
              v17 = ((__int64 (__fastcall *)(Node *))a3->lpVtbl[6].GetTypeInfo)(a3);
              if ( !v17 || v17 != *((_QWORD *)this + 8) )
              {
                NodeLastChild = Node::getNodeLastChild(a3);
                if ( NodeLastChild )
                  LODWORD(NodeLastChild[2].lpVtbl) |= 0x1000u;
                else
                  LODWORD(a3[2].lpVtbl) |= 0x800u;
                goto LABEL_33;
              }
            }
LABEL_25:
            if ( _NDNodeFactory::bufferAppend(this, a3, *((const unsigned __int16 **)v12 + 2), *((_DWORD *)v12 + 6)) )
              goto LABEL_33;
            break;
        }
      }
      else if ( (v15 & 0x1Fu) > 0x12 )
      {
        goto LABEL_33;
      }
      v19 = (Node *)Node::newNode(v15 & 0x1F, 0, a3);
      v13 = v19;
      if ( (v15 & 0x1F) == 1 )
        assign((struct IUnknown **)this + 8, v19);
      goto LABEL_30;
    }
    NameDef = NamespaceMgr::createNameDef(
                *((NamespaceMgr **)this + 11),
                *((const unsigned __int16 **)v12 + 2),
                *((_DWORD *)v12 + 6));
    v13 = (Node *)Node::newNode(v15 & 0x1F, NameDef, a3);
LABEL_30:
    *((_BYTE *)this + 84) = 0;
    v20 = 0;
    if ( *((_DWORD *)v12 + 3) == 1 )
      v20 = 0x10000;
    LODWORD(v13[2].lpVtbl) = (__int64)v13[2].lpVtbl & 0xFFFEFFFF | v20;
    *((_QWORD *)v12 + 4) = v13;
LABEL_33:
    if ( i <= 1 )
    {
      v8 = v29;
      v7 = v34;
      v10 = v36;
    }
    else
    {
      if ( (v15 & 0x80u) == 0 )
      {
        if ( *((_DWORD *)v12 + 1) == 2 )
        {
          if ( !v13 )
            Exception::throw_E_INTERNAL();
          a3 = v13;
          v22 = ((__int64 (__fastcall *)(Node *))v13->lpVtbl[1].GetTypeInfo)(v13);
          v23 = (String *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v22 + 88LL))(v22);
          if ( String::equalsIgnoreCase(v23, L"XML-SPACE") )
          {
            v31 = 1;
            v9 = 1;
          }
        }
        v21 = v33;
      }
      else
      {
        if ( !v13 )
          Exception::throw_E_INTERNAL();
        a3 = v13;
        v21 = v13;
        v33 = v13;
      }
      v10 = v36;
      v24 = *v36;
      if ( *((_DWORD *)*v36 + 1) == 2 )
      {
        if ( *((_DWORD *)this + 20) )
          _NDNodeFactory::bufferAttach(this);
        assign((struct IUnknown **)this + 8, 0);
        *((_BYTE *)this + 84) = 0;
        if ( v29 )
        {
          if ( !v34 )
            Exception::throw_E_INTERNAL();
          v25 = *((_QWORD *)v34 + 4);
          if ( v9 )
            v30 = ProcessXmlSpace((struct Node *)v25, 1);
          *(_DWORD *)(v25 + 16) |= 0x10000u;
        }
        v9 = 0;
        v7 = v24;
        v34 = v24;
        v8 = 1;
        v29 = 1;
        a3 = v21;
        v10 = v36;
      }
      else
      {
        v8 = v29;
        v7 = v34;
      }
      i = v32;
    }
  }
  if ( v8 )
  {
    if ( *((_DWORD *)this + 20) )
      _NDNodeFactory::bufferAttach(this);
    v26 = *((_QWORD *)v7 + 4);
    if ( v9 )
      v27 = ProcessXmlSpace((struct Node *)v26, 1);
    else
      v27 = v30;
    *(_DWORD *)(v26 + 16) |= 0x10000u;
    assign((struct IUnknown **)this + 8, 0);
    *((_BYTE *)this + 84) = 0;
  }
  else
  {
    v27 = v30;
  }
  *((_QWORD *)v35 + 5) = *((_BYTE *)this + 86) != 0 ? 2 : 0;
  if ( v31 )
    *((_BYTE *)this + 86) = v27;
  return 0;
}

```

## disassembly

```asm
0x180057b70  mov     rax, rsp
0x180057b73  mov     [rax+18h], rbx
0x180057b77  mov     [rax+20h], rsi
0x180057b7b  mov     [rax+10h], rdx
0x180057b7f  mov     [rax+8], rcx
0x180057b83  push    rdi
0x180057b84  push    r12
0x180057b86  push    r13
0x180057b88  push    r14
0x180057b8a  push    r15
0x180057b8c  sub     rsp, 90h
0x180057b93  mov     r14, r8
0x180057b96  mov     rsi, rcx
0x180057b99  xor     r8d, r8d
0x180057b9c  mov     [rsp+0B8h+var_60], r8d
0x180057ba1  mov     [rax-70h], r8
0x180057ba5  xor     ebx, ebx
0x180057ba7  mov     [rax-68h], rbx
0x180057bab  mov     [rax-58h], r14
0x180057baf  xor     dl, dl
0x180057bb1  mov     [rax-78h], dl
0x180057bb4  xor     dil, dil
0x180057bb7  mov     [rax-77h], dil
0x180057bbb  mov     [rax-75h], dl
0x180057bbe  xor     r13b, r13b
0x180057bc1  mov     [rax-76h], r13b
0x180057bc5  mov     rax, [rax+28h]
0x180057bc9  mov     r15, [rax]
0x180057bcc  mov     [rsp+0B8h+var_40], r15
0x180057bd1  movzx   edi, r9w
0x180057bd5  mov     [rsp+0B8h+var_74], edi
0x180057bd9  test    edi, edi
0x180057bdb  jle     loc_180057F20
0x180057be1  mov     r15, [rax]
0x180057be4  add     rax, 8
0x180057be8  mov     [rsp+0B8h+arg_20], rax
0x180057bf0  xor     r12d, r12d
0x180057bf3  mov     [rsp+0B8h+var_50], r12
0x180057bf8  mov     eax, [r15+4]
0x180057bfc  lea     rbx, ?nodeProperties@@3QBUNDProperties@@B; NDProperties const near * const nodeProperties
0x180057c03  mov     ebx, [rbx+rax*4]
0x180057c06  mov     [rsp+0B8h+var_48], ebx
0x180057c0a  cmp     [rsi+50h], r12d
0x180057c0e  jbe     short loc_180057C40
0x180057c10  test    bl, 20h
0x180057c13  jnz     short loc_180057C34
0x180057c15  cmp     eax, 0Dh
0x180057c18  jz      short loc_180057C1F
0x180057c1a  cmp     eax, 12h
0x180057c1d  jnz     short loc_180057C34
0x180057c1f  mov     r8d, [r15+18h]; unsigned int
0x180057c23  mov     rdx, [r15+10h]; unsigned __int16 *
0x180057c27  mov     rcx, rsi; this
0x180057c2a  call    ?bufferAppend@_NDNodeFactory@@IEAAXPEBGK@Z; _NDNodeFactory::bufferAppend(ushort const *,ulong)
0x180057c2f  jmp     loc_180057DD4
0x180057c34  mov     rcx, rsi; this
0x180057c37  call    ?bufferAttach@_NDNodeFactory@@IEAAXXZ; _NDNodeFactory::bufferAttach(void)
0x180057c3c  mov     dl, [rsp+0B8h+var_78]
0x180057c40  test    bl, 20h
0x180057c43  jz      short loc_180057C92
0x180057c45  mov     r8d, [r15+18h]; unsigned int
0x180057c49  mov     rdx, [r15+10h]; unsigned __int16 *
0x180057c4d  mov     rcx, [rsi+58h]; this
0x180057c51  call    ?createNameDef@NamespaceMgr@@QEAAPEAVNameDef@@PEBGK@Z; NamespaceMgr::createNameDef(ushort const *,ulong)
0x180057c56  mov     rdx, rax
0x180057c59  mov     ecx, ebx
0x180057c5b  and     ecx, 1Fh
0x180057c5e  mov     rax, [rsi+28h]
0x180057c62  mov     [rsp+0B8h+var_80], rax
0x180057c67  mov     rax, [rsi+20h]
0x180057c6b  mov     [rsp+0B8h+var_88], rax
0x180057c70  mov     [rsp+0B8h+var_90], r12d
0x180057c75  mov     [rsp+0B8h+var_98], r12
0x180057c7a  xor     r9d, r9d
0x180057c7d  mov     r8, r14
0x180057c80  call    ?newNode@Node@@SAPEAV1@W4NodeType@Element@@PEAVNameDef@@PEAV1@PEAVString@@PEBGKPEAVDocument@@PEAVNodeManager@@@Z; Node::newNode(Element::NodeType,NameDef *,Node *,String *,ushort const *,ulong,Document *,NodeManager *)
0x180057c85  mov     r12, rax
0x180057c88  mov     [rsp+0B8h+var_50], rax
0x180057c8d  jmp     loc_180057DAD
0x180057c92  bt      bx, 8
0x180057c97  jnb     loc_180057D50
0x180057c9d  mov     ecx, [r15+4]
0x180057ca1  sub     ecx, 0Dh
0x180057ca4  jz      loc_180057D33
0x180057caa  sub     ecx, 1
0x180057cad  jz      short loc_180057D07
0x180057caf  cmp     ecx, 4
0x180057cb2  jnz     loc_180057D59
0x180057cb8  cmp     [rsi+54h], r12b
0x180057cbc  jnz     short loc_180057D33
0x180057cbe  cmp     [rsi+56h], r12b
0x180057cc2  jz      short loc_180057CC8
0x180057cc4  test    dl, dl
0x180057cc6  jz      short loc_180057D33
0x180057cc8  mov     rax, [r14]
0x180057ccb  mov     rcx, r14
0x180057cce  mov     rax, [rax+260h]
0x180057cd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057cda  test    rax, rax
0x180057cdd  jz      short loc_180057CE5
0x180057cdf  cmp     rax, [rsi+40h]
0x180057ce3  jz      short loc_180057D33
0x180057ce5  mov     rcx, r14; this
0x180057ce8  call    ?getNodeLastChild@Node@@QEAAPEAV1@XZ; Node::getNodeLastChild(void)
0x180057ced  test    rax, rax
0x180057cf0  jz      short loc_180057CFC
0x180057cf2  bts     dword ptr [rax+10h], 0Ch
0x180057cf7  jmp     loc_180057DD4
0x180057cfc  bts     dword ptr [r14+10h], 0Bh
0x180057d02  jmp     loc_180057DD4
0x180057d07  mov     rax, [r14]
0x180057d0a  mov     rcx, r14
0x180057d0d  mov     rax, [rax+98h]
0x180057d14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057d19  cmp     eax, 5
0x180057d1c  jnz     short loc_180057D59
0x180057d1e  mov     r8d, [r15+18h]; int
0x180057d22  mov     rdx, [r15+10h]; unsigned __int16 *
0x180057d26  mov     rcx, r14; this
0x180057d29  call    ?_appendText@Node@@QEAAXPEBGH@Z; Node::_appendText(ushort const *,int)
0x180057d2e  jmp     loc_180057DD4
0x180057d33  mov     r9d, [r15+18h]; unsigned int
0x180057d37  mov     r8, [r15+10h]; unsigned __int16 *
0x180057d3b  mov     rdx, r14; struct Node *
0x180057d3e  mov     rcx, rsi; this
0x180057d41  call    ?bufferAppend@_NDNodeFactory@@IEAA_NPEAVNode@@PEBGK@Z; _NDNodeFactory::bufferAppend(Node *,ushort const *,ulong)
0x180057d46  test    al, al
0x180057d48  jnz     loc_180057DD4
0x180057d4e  jmp     short loc_180057D59
0x180057d50  mov     eax, ebx
0x180057d52  and     eax, 1Fh
0x180057d55  cmp     al, 12h
0x180057d57  ja      short loc_180057DD4
0x180057d59  mov     edi, ebx
0x180057d5b  and     edi, 1Fh
0x180057d5e  mov     rax, [rsi+28h]
0x180057d62  mov     [rsp+0B8h+var_80], rax
0x180057d67  mov     rax, [rsi+20h]
0x180057d6b  mov     [rsp+0B8h+var_88], rax
0x180057d70  mov     eax, [r15+18h]
0x180057d74  mov     [rsp+0B8h+var_90], eax
0x180057d78  mov     rax, [r15+10h]
0x180057d7c  mov     [rsp+0B8h+var_98], rax
0x180057d81  xor     r9d, r9d
0x180057d84  mov     r8, r14
0x180057d87  xor     edx, edx
0x180057d89  mov     ecx, edi
0x180057d8b  call    ?newNode@Node@@SAPEAV1@W4NodeType@Element@@PEAVNameDef@@PEAV1@PEAVString@@PEBGKPEAVDocument@@PEAVNodeManager@@@Z; Node::newNode(Element::NodeType,NameDef *,Node *,String *,ushort const *,ulong,Document *,NodeManager *)
0x180057d90  mov     r12, rax
0x180057d93  mov     [rsp+0B8h+var_50], rax
0x180057d98  cmp     edi, 1
0x180057d9b  jnz     short loc_180057DA9
0x180057d9d  lea     rcx, [rsi+40h]; struct IUnknown **
0x180057da1  mov     rdx, rax; void *
0x180057da4  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x180057da9  mov     edi, [rsp+0B8h+var_74]
0x180057dad  mov     byte ptr [rsi+54h], 0
0x180057db1  xor     ecx, ecx
0x180057db3  cmp     dword ptr [r15+0Ch], 1
0x180057db8  mov     eax, 10000h
0x180057dbd  cmovz   ecx, eax
0x180057dc0  mov     eax, [r12+10h]
0x180057dc5  btr     eax, 10h
0x180057dc9  or      ecx, eax
0x180057dcb  mov     [r12+10h], ecx
0x180057dd0  mov     [r15+20h], r12
0x180057dd4  cmp     edi, 1
0x180057dd7  jle     loc_180057EF9
0x180057ddd  test    bl, bl
0x180057ddf  jns     short loc_180057E05
0x180057de1  test    r12, r12
0x180057de4  jnz     short loc_180057DEB
0x180057de6  call    ?throw_E_INTERNAL@Exception@@SAXXZ; Exception::throw_E_INTERNAL(void)
0x180057deb  mov     r14, r12
0x180057dee  mov     [rsp+0B8h+var_58], r12
0x180057df3  mov     r15, r12
0x180057df6  mov     [rsp+0B8h+var_70], r12
0x180057dfb  mov     [rsp+0B8h+var_38], r12
0x180057e03  jmp     short loc_180057E65
0x180057e05  cmp     dword ptr [r15+4], 2
0x180057e0a  jnz     short loc_180057E60
0x180057e0c  test    r12, r12
0x180057e0f  jnz     short loc_180057E16
0x180057e11  call    ?throw_E_INTERNAL@Exception@@SAXXZ; Exception::throw_E_INTERNAL(void)
0x180057e16  mov     r14, r12
0x180057e19  mov     [rsp+0B8h+var_58], r12
0x180057e1e  mov     rax, [r12]
0x180057e22  mov     rcx, r12
0x180057e25  mov     rax, [rax+80h]
0x180057e2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057e31  mov     rcx, rax
0x180057e34  mov     rax, [rax]
0x180057e37  mov     rax, [rax+58h]
0x180057e3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057e40  lea     rdx, ?s_cstrXMLSpace_pwz@XMLNames@@2QBGB; "XML-SPACE"
0x180057e47  mov     rcx, rax; this
0x180057e4a  call    ?equalsIgnoreCase@String@@QEAA_NPEBG@Z; String::equalsIgnoreCase(ushort const *)
0x180057e4f  test    al, al
0x180057e51  jz      short loc_180057E60
0x180057e53  mov     [rsp+0B8h+var_75], 1
0x180057e58  mov     r13b, 1
0x180057e5b  mov     [rsp+0B8h+var_76], r13b
0x180057e60  mov     r15, [rsp+0B8h+var_70]
0x180057e65  mov     rax, [rsp+0B8h+arg_20]
0x180057e6d  mov     rdi, [rax]
0x180057e70  cmp     dword ptr [rdi+4], 2
0x180057e74  jnz     loc_180057F0C
0x180057e7a  cmp     dword ptr [rsi+50h], 0
0x180057e7e  jbe     short loc_180057E88
0x180057e80  mov     rcx, rsi; this
0x180057e83  call    ?bufferAttach@_NDNodeFactory@@IEAAXXZ; _NDNodeFactory::bufferAttach(void)
0x180057e88  lea     rcx, [rsi+40h]; struct IUnknown **
0x180057e8c  xor     edx, edx; void *
0x180057e8e  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x180057e93  mov     byte ptr [rsi+54h], 0
0x180057e97  cmp     [rsp+0B8h+var_78], 0
0x180057e9c  jz      short loc_180057EC9
0x180057e9e  mov     rbx, [rsp+0B8h+var_68]
0x180057ea3  test    rbx, rbx
0x180057ea6  jnz     short loc_180057EAD
0x180057ea8  call    ?throw_E_INTERNAL@Exception@@SAXXZ; Exception::throw_E_INTERNAL(void)
0x180057ead  mov     rbx, [rbx+20h]
0x180057eb1  test    r13b, r13b
0x180057eb4  jz      short loc_180057EC4
0x180057eb6  mov     dl, 1; bool
0x180057eb8  mov     rcx, rbx; struct Node *
0x180057ebb  call    ?ProcessXmlSpace@@YA_NPEAVNode@@_N@Z; ProcessXmlSpace(Node *,bool)
0x180057ec0  mov     [rsp+0B8h+var_77], al
0x180057ec4  bts     dword ptr [rbx+10h], 10h
0x180057ec9  xor     r13b, r13b
0x180057ecc  mov     [rsp+0B8h+var_76], r13b
0x180057ed1  mov     rbx, rdi
0x180057ed4  mov     [rsp+0B8h+var_68], rbx
0x180057ed9  mov     [rsp+0B8h+var_30], rbx
0x180057ee1  mov     dl, 1
0x180057ee3  mov     [rsp+0B8h+var_78], dl
0x180057ee7  mov     r14, r15
0x180057eea  mov     [rsp+0B8h+var_58], r15
0x180057eef  mov     rax, [rsp+0B8h+arg_20]
0x180057ef7  jmp     short loc_180057F15
0x180057ef9  mov     dl, [rsp+0B8h+var_78]
0x180057efd  mov     rbx, [rsp+0B8h+var_68]
0x180057f02  mov     rax, [rsp+0B8h+arg_20]
0x180057f0a  jmp     short loc_180057F19
0x180057f0c  mov     dl, [rsp+0B8h+var_78]
0x180057f10  mov     rbx, [rsp+0B8h+var_68]
0x180057f15  mov     edi, [rsp+0B8h+var_74]
0x180057f19  dec     edi
0x180057f1b  jmp     loc_180057BD5
0x180057f20  test    dl, dl
0x180057f22  jz      short loc_180057F69
0x180057f24  cmp     dword ptr [rsi+50h], 0
0x180057f28  jbe     short loc_180057F32
0x180057f2a  mov     rcx, rsi; this
0x180057f2d  call    ?bufferAttach@_NDNodeFactory@@IEAAXXZ; _NDNodeFactory::bufferAttach(void)
0x180057f32  mov     rbx, [rbx+20h]
0x180057f36  test    r13b, r13b
0x180057f39  jz      short loc_180057F4E
0x180057f3b  mov     dl, 1; bool
0x180057f3d  mov     rcx, rbx; struct Node *
0x180057f40  call    ?ProcessXmlSpace@@YA_NPEAVNode@@_N@Z; ProcessXmlSpace(Node *,bool)
0x180057f45  mov     dil, al
0x180057f48  mov     [rsp+0B8h+var_77], al
0x180057f4c  jmp     short loc_180057F53
0x180057f4e  mov     dil, [rsp+0B8h+var_77]
0x180057f53  bts     dword ptr [rbx+10h], 10h
0x180057f58  lea     rcx, [rsi+40h]; struct IUnknown **
0x180057f5c  xor     edx, edx; void *
0x180057f5e  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x180057f63  mov     byte ptr [rsi+54h], 0
0x180057f67  jmp     short loc_180057F6E
0x180057f69  mov     dil, [rsp+0B8h+var_77]
0x180057f6e  mov     al, [rsi+56h]
0x180057f71  neg     al
0x180057f73  sbb     rcx, rcx
0x180057f76  and     ecx, 2
0x180057f79  mov     rax, [rsp+0B8h+var_40]
0x180057f7e  mov     [rax+28h], rcx
0x180057f82  cmp     [rsp+0B8h+var_75], 0
0x180057f87  jz      short loc_180057F8D
0x180057f89  mov     [rsi+56h], dil
0x180057f8d  mov     r8d, [rsp+0B8h+var_60]
0x180057f92  jmp     loc_180058057
0x180057f97  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x180057f9d  call    cs:__imp_TlsGetValue
0x180057fa3  mov     rbx, rax
0x180057fa6  cmp     dword ptr [rax+54h], 0C00000FDh
0x180057fad  jnz     short loc_180058028
0x180057faf  call    cs:__imp__resetstkoflw
0x180057fb5  test    eax, eax
0x180057fb7  jnz     short loc_18005800A
0x180057fb9  mov     rcx, cs:?g_pMutexGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexGC
0x180057fc0  test    rcx, rcx
0x180057fc3  jz      short loc_180057FD7
0x180057fc5  cmp     [rcx+50h], rbx
0x180057fc9  jnz     short loc_180057FD7
0x180057fcb  mov     rax, [rcx]
0x180057fce  mov     rax, [rax+20h]
0x180057fd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057fd7  mov     rcx, cs:?g_pMutexFullGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexFullGC
  ... truncated ...
```
