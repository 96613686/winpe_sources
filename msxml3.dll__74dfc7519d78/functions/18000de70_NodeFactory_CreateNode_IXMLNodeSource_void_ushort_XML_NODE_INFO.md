# NodeFactory::CreateNode(IXMLNodeSource *,void *,ushort,_XML_NODE_INFO * *)

- ea: `0x18000de70`
- end: `0x18000ee6c`
- name: `?CreateNode@NodeFactory@@UEAAJPEAUIXMLNodeSource@@PEAXGPEAPEAU_XML_NODE_INFO@@@Z`
- size: `4092`
- prototype: `int(NodeFactory *__hidden this, struct IXMLNodeSource *, void *, unsigned __int16, struct _XML_NODE_INFO **)`
- caller_count: `0`
- callee_count: `55`
- tags: `registry_config`

## callees

- `0x18000a5cc`
- `0x18000d5c0`
- `0x18000de70`
- `0x18000ee74`
- `0x18000f368`
- `0x18000f578`
- `0x180012000`
- `0x18001296c`
- `0x180014214`
- `0x180016078`
- `0x180016334`
- `0x1800166a0`
- `0x1800169b0`
- `0x180018940`
- `0x18001b690`
- `0x18001f080`
- `0x1800325d8`
- `0x180034304`
- `0x1800391f4`
- `0x18003b600`
- `0x18003d620`
- `0x18003d970`
- `0x18003e89c`
- `0x18003f734`
- `0x180048554`
- `0x18004882c`
- `0x18004a8fc`
- `0x18004aa34`
- `0x18004aa64`
- `0x18004aa88`
- `0x18004b1c4`
- `0x18004d704`
- `0x18004df38`
- `0x18004e34c`
- `0x180051ea8`
- `0x180064034`
- `0x18006b590`
- `0x18006cf24`
- `0x18006d524`
- `0x18006e03c`
- `0x180070180`
- `0x180078608`
- `0x180079adc`
- `0x18007aac0`
- `0x1800f98ac`
- `0x1800f991c`
- `0x1800f9a70`
- `0x1800fa048`
- `0x1800fb668`
- `0x1800fc66c`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x18000ed16`
- `msvcrt!_resetstkoflw` at `0x18000ed16`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000ed69`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000ed69`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000deeb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000ed04`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000edbe`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000deeb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000ed04`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000edbe`

## pseudocode

```c
__int64 __fastcall NodeFactory::CreateNode(
        NodeFactory *this,
        struct IXMLNodeSource *a2,
        struct Atom *a3,
        unsigned __int16 a4,
        struct _XML_NODE_INFO **a5)
{
  struct Atom *v5; // r12
  signed int LastError; // edi
  struct _XML_NODE_INFO *v8; // rsi
  __int64 v9; // r13
  __int64 v10; // r8
  struct TLSDATA *Value; // r14
  unsigned int v12; // r15d
  int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // r8d
  __int64 v16; // rcx
  NamespaceMgr *v17; // rcx
  unsigned int v18; // eax
  __int64 v19; // rcx
  __int64 v20; // rax
  struct Node *NodeLastChild; // rax
  unsigned int v22; // edx
  struct NameDef *v23; // rdx
  __int64 v24; // rcx
  struct ElementDecl *v25; // rax
  __int64 v26; // rcx
  struct _XML_NODE_INFO **v27; // rdx
  int v28; // r8d
  __int64 v29; // rax
  struct Node *v30; // r9
  Node *v31; // r12
  int v32; // ecx
  struct _XML_NODE_INFO **v33; // rsi
  struct IXMLNodeSource *v34; // r13
  Document *v35; // rcx
  NodeFactory *v36; // rcx
  const unsigned __int16 *v37; // r9
  struct String *AttributeValue; // rax
  struct Atom *InlineSchemaURN; // rsi
  Hashtable *SchemaBackRefTable; // rax
  int v41; // r9d
  __int64 v42; // r11
  unsigned __int64 v43; // r8
  _QWORD **v44; // rsi
  Document *v45; // rdi
  struct DocumentVtbl *lpVtbl; // rsi
  struct DTD *DTD; // rax
  int v48; // eax
  int v49; // eax
  struct Document *v50; // rdx
  unsigned int v51; // ecx
  __int64 v52; // rcx
  int v53; // ecx
  const unsigned __int16 *v54; // r9
  struct Atom *v55; // rax
  __int64 v56; // rdx
  unsigned int v57; // r8d
  const unsigned __int16 *v58; // rdx
  int v59; // edx
  void *v60; // rax
  __int64 v61; // rax
  __int64 v62; // rcx
  struct String *v63; // rax
  struct ArrayString *v64; // rax
  struct __array *v65; // rcx
  __int64 v66; // rax
  NodeFactory *v67; // rcx
  __int64 v68; // rax
  int v69; // r9d
  const unsigned __int16 *v70; // r8
  int v71; // r9d
  NamespaceMgr *v72; // rcx
  struct Atom *Atom; // rax
  struct Name *v74; // rax
  __int64 v75; // rdi
  struct String *v76; // rax
  __int64 v77; // rax
  struct String *NodeText; // rax
  __int64 v79; // rax
  __int64 v80; // rcx
  void *v81; // rax
  struct String *v82; // rax
  _QWORD *v83; // r12
  __int64 v84; // rdx
  __int64 v85; // rcx
  IntegerHashtable *v86; // rax
  struct _XML_NODE_INFO **v88; // [rsp+20h] [rbp-108h]
  struct _XML_NODE_INFO **v89; // [rsp+20h] [rbp-108h]
  struct String *v90; // [rsp+28h] [rbp-100h]
  __int64 v91; // [rsp+30h] [rbp-F8h]
  bool v92; // [rsp+40h] [rbp-E8h]
  unsigned int v93; // [rsp+44h] [rbp-E4h]
  int v94; // [rsp+44h] [rbp-E4h]
  const unsigned __int16 *Src; // [rsp+50h] [rbp-D8h]
  const unsigned __int16 *Srca; // [rsp+50h] [rbp-D8h]
  unsigned int v97; // [rsp+58h] [rbp-D0h]
  struct NameDef *v98; // [rsp+60h] [rbp-C8h]
  NamespaceMgr *v99; // [rsp+70h] [rbp-B8h]
  struct Atom *v100; // [rsp+78h] [rbp-B0h] BYREF
  int v101; // [rsp+80h] [rbp-A8h]
  signed int v102; // [rsp+84h] [rbp-A4h]
  struct IXMLNodeFactory *v103; // [rsp+88h] [rbp-A0h] BYREF
  unsigned int v104; // [rsp+90h] [rbp-98h]
  ElementDecl *v105; // [rsp+98h] [rbp-90h]
  struct Atom *v106; // [rsp+A0h] [rbp-88h]
  int v107; // [rsp+A8h] [rbp-80h]
  int v108[2]; // [rsp+B0h] [rbp-78h]
  struct ElementDecl *v109; // [rsp+B8h] [rbp-70h]
  struct _XML_NODE_INFO *v110; // [rsp+C0h] [rbp-68h]
  struct TLSDATA *v111; // [rsp+C8h] [rbp-60h]
  _QWORD v112[3]; // [rsp+D0h] [rbp-58h] BYREF
  char v113; // [rsp+E8h] [rbp-40h]
  struct Atom *v115; // [rsp+140h] [rbp+18h] BYREF
  unsigned __int16 v116; // [rsp+148h] [rbp+20h]

  v116 = a4;
  v115 = a3;
  v5 = a3;
  LastError = 0;
  v102 = 0;
  v101 = 0;
  v92 = 0;
  ++*((_DWORD *)this + 57);
  v8 = *a5;
  v110 = v8;
  v9 = *((unsigned int *)v8 + 1);
  v98 = 0;
  v105 = 0;
  v103 = 0;
  Value = (struct TLSDATA *)TlsGetValue(g_dwTlsIndex);
  v111 = Value;
  v12 = *((_DWORD *)Value + 18);
  v104 = v12;
  v13 = *((_DWORD *)this + 54);
  if ( !v13 )
  {
    if ( *((_DWORD *)this + 55) )
    {
      v5 = (struct Atom *)*((_QWORD *)this + 23);
    }
    else if ( (_DWORD)v9 == 1 )
    {
      *((_BYTE *)this + 241) = 1;
    }
  }
  if ( !*((_DWORD *)v8 + 3) )
    *((_DWORD *)this + 54) = v13 + 1;
  if ( *((_DWORD *)this + 20) && (_DWORD)v9 != 13 )
  {
    if ( (_DWORD)v9 == 18 )
    {
LABEL_11:
      v19 = *((_QWORD *)this + 25);
      if ( v19 )
      {
        *((_QWORD *)this + 12) = v8;
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v19 + 144LL))(v19, 2);
      }
      if ( v5 == *((struct Atom **)this + 18) )
      {
        v66 = (*(__int64 (__fastcall **)(struct Atom *))(*(_QWORD *)v5 + 608LL))(v5);
        if ( v66 )
          *(_DWORD *)(v66 + 16) |= 0x1000u;
        goto LABEL_156;
      }
      if ( !*((_BYTE *)this + 86) && !*((_BYTE *)this + 84) )
      {
        v20 = (*(__int64 (__fastcall **)(struct Atom *))(*(_QWORD *)v5 + 608LL))(v5);
        if ( !v20 || v20 != *((_QWORD *)this + 8) )
        {
          NodeLastChild = Node::getNodeLastChild((Node *)v5);
          if ( NodeLastChild )
            LODWORD(NodeLastChild[2].lpVtbl) |= 0x1000u;
          else
            *((_DWORD *)v5 + 4) |= 0x800u;
          goto LABEL_156;
        }
      }
      if ( _NDNodeFactory::bufferAppend(
             this,
             (struct Node *)v5,
             *((const unsigned __int16 **)v8 + 2),
             *((_DWORD *)v8 + 6)) )
      {
        goto LABEL_156;
      }
LABEL_27:
      v26 = *((_DWORD *)&nodeProperties + v9) & 0x1F;
      v94 = *((_DWORD *)&nodeProperties + v9) & 0x1F;
      LODWORD(v115) = *((_DWORD *)v8 + 3);
      if ( v98 )
      {
        v27 = 0;
        v28 = 0;
      }
      else
      {
        v27 = (struct _XML_NODE_INFO **)*((_QWORD *)v8 + 2);
        v28 = *((_DWORD *)v8 + 6);
      }
      v91 = *((_QWORD *)this + 4);
      LODWORD(v90) = v28;
      v89 = v27;
      v29 = Node::newNode(v26, v98, v5);
      v31 = (Node *)v29;
      *(_DWORD *)(v29 + 16) &= ~0x10000u;
      v32 = 0;
      if ( (_DWORD)v115 == 1 )
        v32 = 0x10000;
      *(_DWORD *)(v29 + 16) |= v32;
      *((_QWORD *)v8 + 4) = v29;
      if ( (_DWORD)v115 != 1 )
      {
        v65 = (struct __array *)*((_QWORD *)this + 6);
        if ( v65 )
        {
          v59 = *((_DWORD *)v65 + 4);
          if ( ++*((_DWORD *)this + 14) >= v59 )
          {
            v60 = (void *)_array<_reference<Node>>::resize(v65, 2 * v59);
            assign((struct IUnknown **)this + 6, v60);
          }
          v61 = *((int *)this + 14);
          if ( (int)v61 < 0 || (v62 = *((_QWORD *)this + 6), (int)v61 >= *(_DWORD *)(v62 + 16)) )
            Exception::throw_E_INVALIDARG();
          assign((struct IUnknown **)(v62 + 8 * v61 + 24), v31);
        }
      }
      *((_BYTE *)this + 84) = 0;
      switch ( (_DWORD)v9 )
      {
        case 1:
          v50 = (struct Document *)(unsigned int)++*((_DWORD *)this + 56);
          v51 = *(_DWORD *)(*((_QWORD *)this + 4) + 424LL);
          if ( v51 && (unsigned int)v50 > v51 )
          {
            v63 = String::newConstString(L"MaxElementDepth");
            Exception::throwHR(-2147467260, -1072897270, v63, 0, (struct String *)v89, v90);
          }
          if ( v101 > 0 )
          {
            if ( v92 )
              *((_QWORD *)this + 29) = v31;
            NamespaceMgr::changeContext(*((NamespaceMgr **)this + 17), v50, v31);
          }
          if ( v105 && *((_BYTE *)this + 242) && *((_QWORD *)v105 + 3) )
            ElementDecl::fixupNames(v105, v50, *((struct NamespaceMgr **)this + 17), v30);
          break;
        case 0xD:
LABEL_149:
          assign((struct IUnknown **)this + 8, v31);
          break;
        case 0x11:
          if ( !*((_DWORD *)this + 55) )
            Node::_expandEntityRef(v31, *((_DWORD *)this + 56) + 1, 1);
          v84 = *((_QWORD *)this + 25);
          v85 = *((_QWORD *)this + 16);
          v112[0] = *((_QWORD *)this + 4);
          v112[1] = v85;
          v112[2] = v84;
          v113 = 0;
          RuntimeValidator::validateEntity((RuntimeValidator *)v112, v31, *((_BYTE *)this + 241));
          break;
        case 0x12:
          goto LABEL_149;
        default:
          break;
      }
      v33 = a5;
      if ( v116 > 1u )
      {
        if ( (_DWORD)v9 != 3 )
        {
          v34 = a2;
          NodeFactory::HandleAttributes(this, a2, v31, v116 - 1, a5 + 1);
LABEL_38:
          if ( !v94 )
          {
            if ( *((_BYTE *)this + 243) )
            {
              if ( SchemaNames::isSchemaRootName(*((struct Name **)v98 + 2)) )
              {
                AttributeValue = NodeFactory::FindAttributeValue(
                                   v36,
                                   v116,
                                   v33,
                                   v37,
                                   (unsigned int)v89,
                                   *((struct DTD **)this + 16));
                if ( AttributeValue )
                {
                  InlineSchemaURN = MakeInlineSchemaURN(*((struct Document **)this + 4), AttributeValue);
                  v115 = InlineSchemaURN;
                  if ( !InlineSchemaInfo::schemaNode(
                          (InlineSchemaInfo *)(*((_QWORD *)this + 16) + 48LL),
                          InlineSchemaURN) )
                  {
                    *((_BYTE *)this + 243) = 0;
                    SchemaBackRefTable = NodeFactory::getSchemaBackRefTable(this);
                    a5 = 0;
                    Hashtable::_get(SchemaBackRefTable, InlineSchemaURN, (struct IUnknown **)&a5);
                    if ( !a5
                      && !_SetArray::_scanField(
                            (_SetArray *)(*((_QWORD *)this + 16) + 48LL),
                            16,
                            (unsigned __int64)InlineSchemaURN,
                            0) )
                    {
                      v43 = Atom::s_emptyAtom;
                      if ( InlineSchemaURN )
                        v43 = (unsigned __int64)InlineSchemaURN;
                      if ( _SetArray::_scanField((_SetArray *)(v42 + 24), 24, v43, v41) )
                      {
                        v44 = (_QWORD **)*((_QWORD *)this + 22);
                        LODWORD(a5) = (*(_QWORD *)(((__int64 (__fastcall *)(Node *))v31->lpVtbl[1].GetTypeInfo)(v31) + 32) != XMLNames::atomXSDSCHEMA)
                                    + 10;
                        if ( !v44 )
                        {
                          v45 = (Document *)*((_QWORD *)this + 4);
                          lpVtbl = v45[31].lpVtbl;
                          DTD = Document::getDTD(v45);
                          LODWORD(v91) = 0;
                          SchemaNodeFactory::newFactory(this, DTD, lpVtbl, lpVtbl, v115, v45, v91, (char *)this + 176);
                          v44 = (_QWORD **)*((_QWORD *)this + 22);
                          *(_BYTE *)(*((_QWORD *)this + 16) + 75LL) = 1;
                          LastError = v102;
                        }
                        (*(void (__fastcall **)(struct IXMLNodeSource *, char *))(*(_QWORD *)v34 + 32LL))(
                          v34,
                          (char *)this + 208);
                        DTD::addSchemaURN(*((DTD **)this + 16), v115, v115);
                        v48 = ((__int64 (__fastcall *)(_QWORD **, struct IXMLNodeSource *, _QWORD))(*v44)[3])(
                                v44,
                                v34,
                                (unsigned int)a5);
                        if ( v48 )
                          Exception::throwHR(v48);
                        v49 = (*(__int64 (__fastcall **)(struct IXMLNodeSource *, _QWORD **))(*(_QWORD *)v34 + 24LL))(
                                v34,
                                v44);
                        if ( v49 )
                          Exception::throwHR(v49);
                        (*(void (__fastcall **)(_QWORD *, Node *))(*v44[5] + 80LL))(v44[5], v31);
                      }
                      else
                      {
                        v86 = NodeFactory::getSchemaBackRefTable(this);
                        IntegerHashtable::put(v86, InlineSchemaURN, (unsigned __int64)v31);
                      }
                    }
                  }
                }
              }
            }
          }
          if ( v92 && Document::hasPendingChildDocs(*((Document **)this + 4)) )
          {
            LastError = Document::startNextPending(v35) ? 0x8000000A : 0;
            if ( (unsigned int)Document::GetLastError(*((Document **)this + 4)) )
              LastError = Document::GetLastError(*((Document **)this + 4));
          }
          goto LABEL_156;
        }
        Node::_appendText(v31, *((const unsigned __int16 **)a5[1] + 2), *((_DWORD *)a5[1] + 6));
      }
      v34 = a2;
      goto LABEL_38;
    }
    _NDNodeFactory::bufferAttach(this);
  }
  if ( (_DWORD)v9 == 18 )
    goto LABEL_11;
  switch ( (int)v9 )
  {
    case 1:
      if ( v116 > 1u )
      {
        if ( *((_QWORD *)v8 + 5) )
        {
          v101 = NodeFactory::ProcessXMLNSAttributes(this, a2, (unsigned int)v116 - 1, a5 + 1);
          v107 = v101;
          v92 = v101 == 7;
          if ( v101 >= 3 && !*((_QWORD *)this + 25) && *((_BYTE *)this + 85) )
          {
            v81 = (void *)NewValidator(*((_QWORD *)this + 4), 2);
            assign((struct IUnknown **)this + 25, v81);
          }
        }
      }
      v14 = *((_DWORD *)v8 + 7);
      v97 = v14;
      v15 = *((_DWORD *)v8 + 6);
      v93 = v15;
      Src = (const unsigned __int16 *)*((_QWORD *)v8 + 2);
      if ( v14 )
      {
        v68 = v14 + 1;
        if ( v15 > (unsigned int)v68 )
        {
          v16 = *((_QWORD *)v8 + 2);
          v69 = *(unsigned __int16 *)(v16 + 2 * v68);
          if ( (_WORD)v69 )
          {
            if ( (*((_BYTE *)(&g_apCharTables)[(unsigned __int64)*(unsigned __int16 *)(v16 + 2 * v68) >> 8]
                  + (unsigned __int8)*(_WORD *)(v16 + 2 * v68))
                & 2) == 0
              && v69 != 95 )
            {
              Exception::throwHR(-1072896763);
            }
          }
        }
      }
      v17 = (NamespaceMgr *)*((_QWORD *)this + 17);
      v99 = v17;
      v100 = 0;
      v106 = 0;
      v18 = v15 + 8;
      LODWORD(v115) = v15 + 8;
      if ( v15 + 8 < v15 )
        Exception::throwHR(-2147024362);
      v22 = *((_DWORD *)v17 + 26);
      if ( v18 > v22 )
      {
        if ( v22 )
        {
          MemFreeObject(*((void **)v17 + 12));
          v17 = v99;
          *((_QWORD *)v99 + 12) = 0;
          v18 = (unsigned int)v115;
        }
        *((_DWORD *)v17 + 26) = 0;
        v77 = new_array<unsigned short>(v18);
        v17 = v99;
        *((_QWORD *)v99 + 12) = v77;
        *((_DWORD *)v99 + 26) = (_DWORD)v115;
      }
      LOBYTE(v115) = 0;
      v106 = NamespaceMgr::ensureURNExists(v17, Src, v97, (bool *)&v115, &v100);
      if ( (_BYTE)v115 )
      {
        v82 = String::newString(Src, v97);
        Exception::throwError(-1072896664, v82, 0, 0, (struct String *)v88);
      }
      **((_QWORD **)v99 + 12) = v100;
      memcpy_0((void *)(*((_QWORD *)v99 + 12) + 8LL), Src, 2LL * v93);
      *(_QWORD *)v108 = v93 + 4;
      v23 = (struct NameDef *)StringHashtable::get(
                                *((StringHashtable **)v99 + 11),
                                *((const unsigned __int16 **)v99 + 12),
                                v93 + 4);
      v98 = v23;
      if ( v23 )
        goto LABEL_22;
      v70 = Src;
      if ( !v97 )
      {
        v115 = 0;
        v71 = v93;
        v72 = v99;
LABEL_105:
        Atom = NamespaceMgr::createAtom(v72, 0, v70, v71);
        goto LABEL_106;
      }
      v115 = NamespaceMgr::createAtom(v99, 0, Src, v97);
      if ( v93 > v97 )
      {
        v71 = v93 - v97 - 1;
        v70 = &Src[v97 + 1];
        v72 = v99;
        goto LABEL_105;
      }
      Atom = (struct Atom *)Atom::s_emptyAtom;
LABEL_106:
      v74 = Name::create(Atom, v106);
      v98 = NameDef::newNameDef(v74, v100, v115);
      v75 = *((_QWORD *)v99 + 11);
      v76 = String::newString(*((const unsigned __int16 **)v99 + 12), v108[0]);
      (*(void (__fastcall **)(__int64, struct String *, struct NameDef *, _QWORD))(*(_QWORD *)v75 + 128LL))(
        v75,
        v76,
        v98,
        0);
      LastError = v102;
      v23 = v98;
LABEL_22:
      *((_QWORD *)v8 + 5) = *((_BYTE *)this + 86) != 0 ? 2 : 0;
      if ( !v92 )
      {
        v24 = *((_QWORD *)this + 25);
        v25 = v24
            ? (struct ElementDecl *)(*(__int64 (__fastcall **)(__int64, struct NameDef *))(*(_QWORD *)v24 + 152LL))(
                                      v24,
                                      v23)
            : DTD::findElement(*((DTD **)this + 16), v23);
        v109 = v25;
        v105 = v25;
        if ( v25 )
        {
          if ( !*((_BYTE *)this + 87) && *((_BYTE *)this + 85) && *((_DWORD *)v25 + 25) )
            *((_BYTE *)this + 86) = (*((_DWORD *)v25 + 25) & 8) != 0;
        }
      }
      goto LABEL_27;
    case 3:
    case 17:
      v98 = NodeFactory::ProcessName(this, 1, v8);
      goto LABEL_27;
    case 4:
      v98 = NodeFactory::ProcessName(this, 1, v8);
      *((_BYTE *)this + 240) = NodeFactory::ProcessStandaloneAttribute(v67, a5, v116);
      goto LABEL_27;
    case 5:
      if ( *(_BYTE *)(*((_QWORD *)this + 16) + 75LL) )
      {
        if ( !*((_QWORD *)this + 19) )
        {
          LastError = -1072897755;
          break;
        }
      }
      else
      {
        *((_BYTE *)this + 242) = 1;
        *((_DWORD *)this + 48) = 1;
      }
      --*((_DWORD *)this + 54);
      (*(void (__fastcall **)(struct IXMLNodeSource *, struct IXMLNodeFactory **))(*(_QWORD *)a2 + 32LL))(a2, &v103);
      v83 = (_QWORD *)((char *)this + 168);
      DTDFactory::New(
        v103,
        this,
        *((struct Document **)this + 4),
        *((_DWORD *)this + 48) != 1,
        (struct DTDFactory **)this + 21);
      (*(void (__fastcall **)(struct IXMLNodeFactory *))(*(_QWORD *)v103 + 16LL))(v103);
      v103 = 0;
      LastError = (*(__int64 (__fastcall **)(_QWORD, struct IXMLNodeSource *, struct Atom *, _QWORD, struct _XML_NODE_INFO **))(*(_QWORD *)*v83 + 56LL))(
                    *v83,
                    a2,
                    v115,
                    v116,
                    a5);
      if ( LastError >= 0 )
        LastError = (*(__int64 (__fastcall **)(struct IXMLNodeSource *, _QWORD))(*(_QWORD *)a2 + 24LL))(a2, *v83);
      break;
    case 13:
      v52 = *((_QWORD *)this + 25);
      if ( v52 )
      {
        *((_QWORD *)this + 12) = v8;
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v52 + 144LL))(v52, 0);
      }
      v53 = *((_DWORD *)v8 + 6);
      LODWORD(v115) = v53;
      v54 = (const unsigned __int16 *)*((_QWORD *)v8 + 2);
      Srca = v54;
      if ( v5 )
      {
        v55 = (struct Atom *)(*(__int64 (__fastcall **)(struct Atom *))(*(_QWORD *)v5 + 608LL))(v5);
        v53 = (int)v115;
        v54 = Srca;
      }
      else
      {
        v55 = 0;
      }
      v100 = v55;
      v56 = *((unsigned __int8 *)this + 84);
      if ( v55 )
      {
        if ( (_BYTE)v56 )
        {
          v79 = (*(__int64 (__fastcall **)(struct Atom *, __int64, __int64, const unsigned __int16 *))(*(_QWORD *)v5 + 624LL))(
                  v5,
                  v56,
                  v10,
                  v54);
          if ( !v79 )
            Exception::throw_E_INTERNAL();
          _NDNodeFactory::bufferAppend(this, *(const unsigned __int16 **)(v79 + 24), *(_DWORD *)(v79 + 16));
          (*(void (__fastcall **)(struct Atom *, _QWORD))(*(_QWORD *)v5 + 632LL))(v5, 0);
          v55 = v100;
          v53 = (int)v115;
          v54 = Srca;
        }
        if ( *((_DWORD *)this + 20) )
          goto LABEL_73;
        if ( v55 == *((struct Atom **)this + 8) )
        {
          NodeText = Node::getNodeText((Node *)v55);
          _NDNodeFactory::bufferAppend(this, *((const unsigned __int16 **)NodeText + 3), *((_DWORD *)NodeText + 4));
          v57 = (unsigned int)v115;
          v58 = Srca;
          goto LABEL_74;
        }
        *((_BYTE *)this + 84) = 0;
        goto LABEL_27;
      }
      if ( (_BYTE)v56 )
      {
LABEL_73:
        v57 = v53;
        v58 = v54;
LABEL_74:
        _NDNodeFactory::bufferAppend(this, v58, v57);
        break;
      }
      v64 = ArrayString::newString(v54, v53);
      (*(void (__fastcall **)(struct Atom *, struct ArrayString *))(*(_QWORD *)v5 + 632LL))(v5, v64);
      *((_BYTE *)this + 84) = 1;
      assign((struct IUnknown **)this + 8, v5);
      *((_DWORD *)this + 20) = 0;
      break;
    case 14:
      v80 = *((_QWORD *)this + 25);
      if ( v80 )
      {
        *((_QWORD *)this + 12) = v8;
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v80 + 144LL))(v80, 1);
      }
      goto LABEL_27;
    default:
      goto LABEL_27;
  }
LABEL_156:
  --*((_DWORD *)this + 57);
  if ( *((_DWORD *)Value + 18) > v12 )
    Base::freeRentalObjects(Value, 1, v12);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18000de70  mov     [rsp+arg_18], r9w
0x18000de76  mov     [rsp+arg_10], r8
0x18000de7b  mov     [rsp+arg_8], rdx
0x18000de80  mov     [rsp+arg_0], rcx
0x18000de85  push    rbx
0x18000de86  push    rsi
0x18000de87  push    rdi
0x18000de88  push    r12
0x18000de8a  push    r13
0x18000de8c  push    r14
0x18000de8e  push    r15
0x18000de90  sub     rsp, 0F0h
0x18000de97  mov     r12, r8
0x18000de9a  mov     rbx, rcx
0x18000de9d  xor     ecx, ecx
0x18000de9f  mov     edi, ecx
0x18000dea1  mov     [rsp+128h+var_A4], ecx
0x18000dea8  mov     [rsp+128h+var_A8], ecx
0x18000deaf  mov     [rsp+128h+var_E8], cl
0x18000deb3  inc     dword ptr [rbx+0E4h]
0x18000deb9  mov     rax, [rsp+128h+arg_20]
0x18000dec1  mov     rsi, [rax]
0x18000dec4  mov     [rsp+128h+var_68], rsi
0x18000decc  mov     r13d, [rsi+4]
0x18000ded0  mov     [rsp+128h+var_C8], rcx
0x18000ded5  mov     [rsp+128h+var_90], rcx
0x18000dedd  mov     [rsp+128h+var_A0], rcx
0x18000dee5  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x18000deeb  call    cs:__imp_TlsGetValue
0x18000def1  mov     r14, rax
0x18000def4  mov     [rsp+128h+var_60], rax
0x18000defc  mov     r15d, [rax+48h]
0x18000df00  mov     [rsp+128h+var_98], r15d
0x18000df08  mov     eax, [rbx+0D8h]
0x18000df0e  test    eax, eax
0x18000df10  jz      loc_18000E937
0x18000df16  cmp     dword ptr [rsi+0Ch], 0
0x18000df1a  jnz     short loc_18000DF24
0x18000df1c  inc     eax
0x18000df1e  mov     [rbx+0D8h], eax
0x18000df24  cmp     dword ptr [rbx+50h], 0
0x18000df28  ja      loc_18000E962
0x18000df2e  cmp     r13d, 12h
0x18000df32  jz      loc_18000DFD5
0x18000df38  lea     ecx, [r13-1]; switch 17 cases
0x18000df3c  cmp     ecx, 10h
0x18000df3f  ja      def_18000DF5D; jumptable 000000018000DF5D default case, cases 2,6-12,15,16
0x18000df45  lea     rax, __ImageBase
0x18000df4c  mov     eax, ds:(jpt_18000DF5D - 180000000h)[rax+rcx*4]
0x18000df53  lea     rdx, __ImageBase
0x18000df5a  add     rax, rdx
0x18000df5d  jmp     rax; switch jump
0x18000df5f  mov     r9d, 1; jumptable 000000018000DF5D case 1
0x18000df65  movzx   r10d, [rsp+128h+arg_18]
0x18000df6e  cmp     r9w, r10w
0x18000df72  jb      loc_18000E6E5
0x18000df78  mov     eax, [rsi+1Ch]
0x18000df7b  mov     [rsp+128h+var_D0], eax
0x18000df7f  mov     r8d, [rsi+18h]
0x18000df83  mov     [rsp+128h+var_E4], r8d
0x18000df88  mov     rcx, [rsi+10h]
0x18000df8c  mov     [rsp+128h+Src], rcx
0x18000df91  test    eax, eax
0x18000df93  jnz     loc_18000E797
0x18000df99  mov     rcx, [rbx+88h]; this
0x18000dfa0  mov     [rsp+128h+var_B8], rcx
0x18000dfa5  mov     [rsp+128h+var_B0], 0
0x18000dfae  mov     [rsp+128h+var_88], 0
0x18000dfba  lea     eax, [r8+8]
0x18000dfbe  mov     dword ptr [rsp+128h+arg_10], eax
0x18000dfc5  cmp     eax, r8d
0x18000dfc8  jnb     short loc_18000E03F
0x18000dfca  mov     ecx, 80070216h; int
0x18000dfcf  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x18000dfd5  mov     rcx, [rbx+0C8h]
0x18000dfdc  test    rcx, rcx
0x18000dfdf  jnz     loc_18000EBFD
0x18000dfe5  cmp     r12, [rbx+90h]
0x18000dfec  jz      loc_18000E743
0x18000dff2  cmp     byte ptr [rbx+56h], 0
0x18000dff6  jnz     loc_18000E5D2
0x18000dffc  cmp     byte ptr [rbx+54h], 0
0x18000e000  jnz     loc_18000E5D2
0x18000e006  mov     rax, [r12]
0x18000e00a  mov     rcx, r12
0x18000e00d  mov     rax, [rax+260h]
0x18000e014  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e019  test    rax, rax
0x18000e01c  jnz     loc_18000E5C8
0x18000e022  mov     rcx, r12; this
0x18000e025  call    ?getNodeLastChild@Node@@QEAAPEAV1@XZ; Node::getNodeLastChild(void)
0x18000e02a  test    rax, rax
0x18000e02d  jz      loc_18000E286
0x18000e033  or      dword ptr [rax+10h], 1000h
0x18000e03a  jmp     loc_18000EDFA
0x18000e03f  mov     edx, [rcx+68h]
0x18000e042  cmp     eax, edx
0x18000e044  ja      loc_18000E8BF
0x18000e04a  mov     byte ptr [rsp+128h+arg_10], 0
0x18000e052  lea     rax, [rsp+128h+var_B0]
0x18000e057  mov     [rsp+128h+var_108], rax; struct String *
0x18000e05c  lea     r9, [rsp+128h+arg_10]; bool *
0x18000e064  mov     r8d, [rsp+128h+var_D0]; unsigned int
0x18000e069  mov     rdx, [rsp+128h+Src]; Src
0x18000e06e  call    ?ensureURNExists@NamespaceMgr@@QEAAPEAVAtom@@PEBGKPEA_NPEAPEAV2@@Z; NamespaceMgr::ensureURNExists(ushort const *,ulong,bool *,Atom * *)
0x18000e073  mov     [rsp+128h+var_88], rax
0x18000e07b  cmp     byte ptr [rsp+128h+arg_10], 0
0x18000e083  jnz     loc_18000EA9D
0x18000e089  mov     rcx, [rsp+128h+var_B8]
0x18000e08e  mov     rax, [rcx+60h]
0x18000e092  mov     rdx, [rsp+128h+var_B0]
0x18000e097  mov     [rax], rdx
0x18000e09a  mov     r8d, [rsp+128h+var_E4]
0x18000e09f  add     r8, r8; Size
0x18000e0a2  mov     rcx, [rcx+60h]
0x18000e0a6  add     rcx, 8; void *
0x18000e0aa  mov     rdx, [rsp+128h+Src]; Src
0x18000e0af  call    memcpy_0
0x18000e0b4  mov     eax, [rsp+128h+var_E4]
0x18000e0b8  add     eax, 4
0x18000e0bb  mov     qword ptr [rsp+128h+var_78], rax
0x18000e0c3  mov     r8d, eax; int
0x18000e0c6  mov     rax, [rsp+128h+var_B8]
0x18000e0cb  mov     rdx, [rax+60h]; unsigned __int16 *
0x18000e0cf  mov     rcx, [rax+58h]; this
0x18000e0d3  call    ?get@StringHashtable@@QEAAPEAUIUnknown@@PEBGH@Z; StringHashtable::get(ushort const *,int)
0x18000e0d8  mov     rdx, rax; struct NameDef *
0x18000e0db  mov     [rsp+128h+var_C8], rax
0x18000e0e0  test    rax, rax
0x18000e0e3  jz      loc_18000E7E3
0x18000e0e9  movzx   eax, byte ptr [rbx+56h]
0x18000e0ed  neg     al
0x18000e0ef  sbb     rcx, rcx
0x18000e0f2  and     ecx, 2
0x18000e0f5  mov     [rsi+28h], rcx
0x18000e0f9  cmp     [rsp+128h+var_E8], 0
0x18000e0fe  jnz     short def_18000DF5D; jumptable 000000018000DF5D default case, cases 2,6-12,15,16
0x18000e100  mov     rcx, [rbx+0C8h]
0x18000e107  test    rcx, rcx
0x18000e10a  jz      loc_18000E645
0x18000e110  mov     rax, [rcx]
0x18000e113  mov     rax, [rax+98h]
0x18000e11a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e11f  mov     [rsp+128h+var_70], rax
0x18000e127  mov     [rsp+128h+var_90], rax
0x18000e12f  test    rax, rax
0x18000e132  jz      short def_18000DF5D; jumptable 000000018000DF5D default case, cases 2,6-12,15,16
0x18000e134  cmp     byte ptr [rbx+57h], 0
0x18000e138  jz      loc_18000EABF
0x18000e13e  lea     rcx, __ImageBase; jumptable 000000018000DF5D default case, cases 2,6-12,15,16
0x18000e145  mov     ecx, ds:rva ?nodeProperties@@3QBUNDProperties@@B[rcx+r13*4]; NDProperties const near * const nodeProperties ...
0x18000e14d  and     ecx, 1Fh
0x18000e150  mov     [rsp+128h+var_E4], ecx
0x18000e154  mov     eax, [rsi+0Ch]
0x18000e157  mov     dword ptr [rsp+128h+arg_10], eax
0x18000e15e  mov     r10, [rsp+128h+var_C8]
0x18000e163  test    r10, r10
0x18000e166  jz      loc_18000E279
0x18000e16c  xor     edx, edx
0x18000e16e  xor     r8d, r8d
0x18000e171  mov     rax, [rbx+28h]
0x18000e175  mov     [rsp+128h+var_F0], rax
0x18000e17a  mov     rax, [rbx+20h]
0x18000e17e  mov     [rsp+128h+var_F8], rax
0x18000e183  mov     dword ptr [rsp+128h+var_100], r8d; struct String *
0x18000e188  mov     [rsp+128h+var_108], rdx; struct String *
0x18000e18d  xor     r9d, r9d
0x18000e190  mov     r8, r12
0x18000e193  mov     rdx, r10
0x18000e196  call    ?newNode@Node@@SAPEAV1@W4NodeType@Element@@PEAVNameDef@@PEAV1@PEAVString@@PEBGKPEAVDocument@@PEAVNodeManager@@@Z; Node::newNode(Element::NodeType,NameDef *,Node *,String *,ushort const *,ulong,Document *,NodeManager *)
0x18000e19b  mov     r12, rax
0x18000e19e  and     dword ptr [rax+10h], 0FFFEFFFFh
0x18000e1a5  xor     ecx, ecx
0x18000e1a7  mov     edx, 10000h
0x18000e1ac  cmp     dword ptr [rsp+128h+arg_10], 1
0x18000e1b4  cmovz   ecx, edx
0x18000e1b7  or      [rax+10h], ecx
0x18000e1ba  mov     [rsi+20h], rax
0x18000e1be  cmp     dword ptr [rsp+128h+arg_10], 1
0x18000e1c6  jnz     loc_18000E6D3
0x18000e1cc  mov     byte ptr [rbx+54h], 0
0x18000e1d0  cmp     r13d, 1
0x18000e1d4  jz      loc_18000E4E5
0x18000e1da  mov     eax, r13d
0x18000e1dd  sub     eax, 0Dh
0x18000e1e0  jz      loc_18000EC9B
0x18000e1e6  sub     eax, 4
0x18000e1e9  jz      loc_18000EC30
0x18000e1ef  cmp     eax, 1
0x18000e1f2  jz      loc_18000EC9B
0x18000e1f8  movzx   eax, [rsp+128h+arg_18]
0x18000e200  mov     rsi, [rsp+128h+arg_20]
0x18000e208  cmp     ax, 1
0x18000e20c  ja      loc_18000E294
0x18000e212  mov     r13, [rsp+128h+arg_8]
0x18000e21a  cmp     [rsp+128h+var_E4], 0
0x18000e21f  jz      loc_18000E2C6
0x18000e225  cmp     [rsp+128h+var_E8], 0
0x18000e22a  jz      loc_18000ECF9
0x18000e230  mov     rcx, [rbx+20h]; this
0x18000e234  call    ?hasPendingChildDocs@Document@@QEBA_NXZ; Document::hasPendingChildDocs(void)
0x18000e239  test    al, al
0x18000e23b  jz      loc_18000ECF9
0x18000e241  call    ?startNextPending@Document@@QEAA_NXZ; Document::startNextPending(void)
0x18000e246  neg     al
0x18000e248  sbb     edi, edi
0x18000e24a  and     edi, 8000000Ah
0x18000e250  mov     [rsp+128h+var_E0], edi
0x18000e254  mov     rcx, [rbx+20h]; this
0x18000e258  call    ?GetLastError@Document@@QEAAJXZ; Document::GetLastError(void)
0x18000e25d  test    eax, eax
0x18000e25f  jz      loc_18000ECF9
0x18000e265  mov     rcx, [rbx+20h]; this
0x18000e269  call    ?GetLastError@Document@@QEAAJXZ; Document::GetLastError(void)
0x18000e26e  mov     edi, eax
0x18000e270  mov     [rsp+128h+var_E0], eax
0x18000e274  jmp     loc_18000ECF9
0x18000e279  mov     rdx, [rsi+10h]
0x18000e27d  mov     r8d, [rsi+18h]
0x18000e281  jmp     loc_18000E171
0x18000e286  or      dword ptr [r12+10h], 800h
0x18000e28f  jmp     loc_18000E03A
0x18000e294  lea     rcx, [rsi+8]
0x18000e298  cmp     r13d, 3
0x18000e29c  jz      loc_18000E67F
0x18000e2a2  lea     r9d, [rax-1]; unsigned __int16
0x18000e2a6  mov     [rsp+128h+var_108], rcx; struct _XML_NODE_INFO **
0x18000e2ab  mov     r8, r12; struct Node *
0x18000e2ae  mov     r13, [rsp+128h+arg_8]
0x18000e2b6  mov     rdx, r13; struct IXMLNodeSource *
0x18000e2b9  mov     rcx, rbx; this
0x18000e2bc  call    ?HandleAttributes@NodeFactory@@IEAAXPEAUIXMLNodeSource@@PEAVNode@@GPEAPEAU_XML_NODE_INFO@@@Z; NodeFactory::HandleAttributes(IXMLNodeSource *,Node *,ushort,_XML_NODE_INFO * *)
0x18000e2c1  jmp     loc_18000E21A
0x18000e2c6  cmp     byte ptr [rbx+0F3h], 0
0x18000e2cd  jz      loc_18000E225
0x18000e2d3  mov     rcx, [rsp+128h+var_C8]
0x18000e2d8  mov     rcx, [rcx+10h]; struct Name *
0x18000e2dc  call    ?isSchemaRootName@SchemaNames@@SA_NPEAVName@@@Z; SchemaNames::isSchemaRootName(Name *)
0x18000e2e1  test    al, al
0x18000e2e3  jz      loc_18000E225
0x18000e2e9  mov     rax, [rbx+80h]
0x18000e2f0  mov     [rsp+128h+var_100], rax; struct DTD *
0x18000e2f5  mov     r8, rsi; struct _XML_NODE_INFO **
0x18000e2f8  movzx   edx, [rsp+128h+arg_18]; unsigned __int16
0x18000e300  call    ?FindAttributeValue@NodeFactory@@IEAAPEAVString@@GPEAPEAU_XML_NODE_INFO@@PEBGKPEAVDTD@@@Z; NodeFactory::FindAttributeValue(ushort,_XML_NODE_INFO * *,ushort const *,ulong,DTD *)
0x18000e305  test    rax, rax
0x18000e308  jz      loc_18000E225
0x18000e30e  mov     rdx, rax; struct String *
0x18000e311  mov     rcx, [rbx+20h]; struct Document *
0x18000e315  call    ?MakeInlineSchemaURN@@YAPEAVAtom@@PEAVDocument@@PEAVString@@@Z; MakeInlineSchemaURN(Document *,String *)
0x18000e31a  mov     rsi, rax
0x18000e31d  mov     [rsp+128h+arg_10], rax
0x18000e325  mov     rcx, [rbx+80h]
0x18000e32c  add     rcx, 30h ; '0'; this
0x18000e330  mov     rdx, rax; struct Atom *
0x18000e333  call    ?schemaNode@InlineSchemaInfo@@QEAAPEAVNode@@PEAVAtom@@@Z; InlineSchemaInfo::schemaNode(Atom *)
0x18000e338  test    rax, rax
0x18000e33b  jnz     loc_18000E225
0x18000e341  mov     [rbx+0F3h], al
0x18000e347  mov     rcx, rbx; this
0x18000e34a  call    ?getSchemaBackRefTable@NodeFactory@@IEAAPEAVHashtable@@XZ; NodeFactory::getSchemaBackRefTable(void)
0x18000e34f  mov     [rsp+128h+arg_20], 0
0x18000e35b  lea     r8, [rsp+128h+arg_20]; struct IUnknown **
0x18000e363  mov     rdx, rsi; struct Object *
0x18000e366  mov     rcx, rax; this
0x18000e369  call    ?_get@Hashtable@@IEAA_NPEAVObject@@PEAPEAUIUnknown@@@Z; Hashtable::_get(Object *,IUnknown * *)
0x18000e36e  cmp     [rsp+128h+arg_20], 0
0x18000e377  jnz     loc_18000E225
0x18000e37d  mov     r11, [rbx+80h]
0x18000e384  lea     rcx, [r11+30h]; this
0x18000e388  xor     r9d, r9d; int
0x18000e38b  mov     r8, rsi; unsigned __int64
0x18000e38e  mov     edx, 10h; int
0x18000e393  call    ?_scanField@_SetArray@@IEBAPEAXH_KH@Z; _SetArray::_scanField(int,unsigned __int64,int)
0x18000e398  test    rax, rax
0x18000e39b  jnz     loc_18000E225
0x18000e3a1  mov     r8, cs:?s_emptyAtom@Atom@@0V?$_staticreference@VAtom@@@@A; _staticreference<Atom> Atom::s_emptyAtom
0x18000e3a8  test    rsi, rsi
0x18000e3ab  cmovnz  r8, rsi; unsigned __int64
0x18000e3af  lea     rcx, [r11+18h]; this
0x18000e3b3  mov     edx, 18h; int
0x18000e3b8  call    ?_scanField@_SetArray@@IEBAPEAXH_KH@Z; _SetArray::_scanField(int,unsigned __int64,int)
0x18000e3bd  test    rax, rax
0x18000e3c0  jz      loc_18000ECDE
0x18000e3c6  mov     rsi, [rbx+0B0h]
0x18000e3cd  mov     rax, [r12]
0x18000e3d1  mov     rcx, r12
0x18000e3d4  mov     rax, [rax+80h]
0x18000e3db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e3e0  xor     edx, edx
0x18000e3e2  mov     rcx, cs:?atomXSDSCHEMA@XMLNames@@2V?$_staticreference@VAtom@@@@A; _staticreference<Atom> XMLNames::atomXSDSCHEMA
0x18000e3e9  cmp     [rax+20h], rcx
0x18000e3ed  setnz   dl
0x18000e3f0  add     edx, 0Ah
0x18000e3f3  mov     dword ptr [rsp+128h+arg_20], edx
0x18000e3fa  test    rsi, rsi
0x18000e3fd  jnz     short loc_18000E462
0x18000e3ff  mov     rdi, [rbx+20h]
0x18000e403  mov     rsi, [rdi+0F8h]
0x18000e40a  mov     rcx, rdi; this
  ... truncated ...
```
