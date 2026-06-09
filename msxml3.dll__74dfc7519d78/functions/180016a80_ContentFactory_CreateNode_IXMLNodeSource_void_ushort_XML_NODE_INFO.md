# ContentFactory::CreateNode(IXMLNodeSource *,void *,ushort,_XML_NODE_INFO * *)

- ea: `0x180016a80`
- end: `0x180018198`
- name: `?CreateNode@ContentFactory@@UEAAJPEAUIXMLNodeSource@@PEAXGPEAPEAU_XML_NODE_INFO@@@Z`
- size: `5912`
- prototype: `__int64 __fastcall(ContentFactory *__hidden this, struct IXMLNodeSource *, void *, unsigned __int16, struct _XML_NODE_INFO **)`
- caller_count: `0`
- callee_count: `41`
- tags: `registry_config`

## callees

- `0x18000a5cc`
- `0x180014214`
- `0x18001428c`
- `0x180014370`
- `0x180014670`
- `0x180014d38`
- `0x180015c8c`
- `0x180016254`
- `0x180016334`
- `0x18001690c`
- `0x1800169b0`
- `0x180016a80`
- `0x180018940`
- `0x180018b60`
- `0x18001adb0`
- `0x18001b690`
- `0x18001c310`
- `0x18001f080`
- `0x18002d610`
- `0x18003739c`
- `0x18003cf30`
- `0x1800472e4`
- `0x18004a8fc`
- `0x18004aa64`
- `0x18004aa88`
- `0x18004abb8`
- `0x18004b488`
- `0x18004e34c`
- `0x18004ee94`
- `0x18004f5f4`
- `0x18004f6b8`
- `0x180050560`
- `0x180050ae0`
- `0x180051a50`
- `0x180064034`
- `0x1800d5854`
- `0x1800d58ec`
- `0x1800da358`
- `0x180102cba`
- `0x180102cc6`
- `0x180107010`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x180018074`
- `msvcrt!_resetstkoflw` at `0x180018074`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800179ee`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800179ee`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800180cb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800180cb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800170ee`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180018062`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800180d7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800170ee`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180018062`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800180d7`

## pseudocode

```c
__int64 __fastcall ContentFactory::CreateNode(
        ContentFactory *this,
        struct IXMLNodeSource *a2,
        void *a3,
        unsigned __int16 a4,
        struct _XML_NODE_INFO **a5)
{
  DTD *v5; // rbx
  __int64 v10; // r13
  int v11; // eax
  _DWORD *v12; // r14
  int v13; // eax
  unsigned int v14; // eax
  __int64 v15; // rsi
  int v16; // ecx
  struct _XML_NODE_INFO **v17; // r12
  _DWORD *v18; // rdi
  unsigned int i; // ebx
  int v20; // esi
  struct _XML_NODE_INFO **j; // rbx
  int v22; // eax
  struct _XML_NODE_INFO *v23; // rdi
  StringHashtable **v24; // rdx
  const unsigned __int16 *v25; // r9
  int v26; // r12d
  StringHashtable *v27; // rcx
  struct Atom *v28; // rcx
  struct Atom *v29; // r12
  struct _XML_NODE_INFO *v30; // rdx
  void *v31; // r10
  struct _XML_NODE_INFO *v32; // rax
  int *v33; // rax
  void *v34; // r12
  __int64 v35; // rsi
  __int64 v36; // rbx
  unsigned __int16 *v37; // r9
  __int64 v38; // rax
  int v39; // edx
  __int64 v40; // r12
  unsigned int v41; // eax
  unsigned int v42; // edi
  unsigned int v43; // eax
  struct NamespaceMgr::Entry *Entry; // rax
  struct Atom *v45; // rcx
  struct Atom *v46; // rdx
  char v47; // al
  struct IUnknown *v48; // rdi
  unsigned int v49; // ecx
  __int64 v50; // r12
  struct IUnknownVtbl *lpVtbl; // rbx
  int v52; // eax
  int v53; // edi
  struct Atom *v54; // rsi
  int v55; // r13d
  struct Atom *v56; // rax
  const unsigned __int16 near *const *v57; // rdx
  int v58; // esi
  __int64 v59; // rbx
  __int64 v60; // rcx
  __int64 v61; // rax
  const unsigned __int16 *v62; // rdi
  int v63; // edi
  StringHashtable *v64; // rcx
  struct IUnknown *v65; // rcx
  void *v66; // rcx
  struct Name *v67; // rsi
  NameDef *v68; // rax
  NameDef *v69; // rdi
  _DWORD *Value; // rax
  __int64 v71; // rcx
  __int64 v72; // rsi
  const unsigned __int16 *v73; // rcx
  struct ArrayString *v74; // rdx
  unsigned int *v75; // rcx
  int v76; // edx
  int v77; // eax
  int v78; // eax
  __int64 v79; // r8
  __int64 v80; // rdx
  __int64 v81; // r8
  unsigned int v82; // r9d
  __int64 v83; // rdx
  __int64 v84; // rax
  __int64 v85; // rax
  unsigned int v86; // ebx
  int v87; // eax
  __int64 v88; // r10
  unsigned int v89; // r8d
  unsigned __int64 v90; // rdx
  unsigned __int64 v91; // rax
  __int64 *v92; // r9
  __int64 v93; // rsi
  __int64 v94; // r12
  const unsigned __int16 near *const *v95; // rax
  unsigned int v96; // r12d
  const unsigned __int16 near *const *v97; // rdx
  int v98; // edx
  _WORD *v99; // rcx
  unsigned __int64 v100; // rax
  struct Atom *Atom; // rdi
  struct Atom *v102; // rax
  int v103; // edx
  StringHashtable *v104; // rcx
  int v105; // edx
  const unsigned __int16 *v106; // rdi
  StringHashtable *v107; // rcx
  struct Atom *v108; // rax
  __int64 v109; // rdi
  struct Atom *v110; // rax
  __int64 v111; // r12
  __int64 v112; // rax
  __int64 v113; // r9
  int v114; // eax
  __int64 v115; // rax
  const unsigned __int16 *v116; // rcx
  unsigned __int64 k; // rax
  __int64 v118; // rax
  __int64 v119; // r9
  char *v120; // rcx
  const unsigned __int16 *v121; // rcx
  unsigned __int64 m; // rax
  struct Atom *v123; // rcx
  __int64 v124; // rax
  __int64 v125; // r9
  const unsigned __int16 *v126; // rcx
  unsigned __int64 v127; // rax
  struct Atom *v128; // rax
  int v129; // eax
  struct String *v130; // rax
  __int64 v131; // rcx
  struct _XML_NODE_INFO **v132; // rdx
  struct NameDef *v133; // rax
  __int64 v134; // rbx
  struct ArrayString *v135; // rax
  __int64 v136; // r9
  int v137; // eax
  __int64 v138; // r9
  struct _XML_NODE_INFO *v139; // rax
  int v140; // edx
  __int64 v141; // r9
  int v142; // eax
  __int64 v143; // rcx
  int v144; // edx
  __int64 v145; // rcx
  _BYTE *v146; // rbx
  __int64 v147; // rcx
  __int64 v148; // rcx
  unsigned int v149; // eax
  struct String *v150; // rax
  struct NameDef *v151; // rsi
  struct Entity *Entity; // rbx
  __int64 v153; // r9
  __int64 v154; // rcx
  struct NameDef *v155; // rax
  struct ElementDecl *ElementDecl; // rax
  int v157; // eax
  __int64 v158; // r8
  unsigned int v159; // r8d
  int v160; // r8d
  struct String *v161; // rax
  struct String *v162; // rax
  struct String *v164; // [rsp+20h] [rbp-138h]
  struct String *v165; // [rsp+28h] [rbp-130h]
  int v166; // [rsp+50h] [rbp-108h]
  void *Src; // [rsp+58h] [rbp-100h]
  const unsigned __int16 *Srca; // [rsp+58h] [rbp-100h]
  struct Atom *v169; // [rsp+60h] [rbp-F8h]
  struct Atom *v170; // [rsp+60h] [rbp-F8h]
  struct Atom *v171; // [rsp+60h] [rbp-F8h]
  struct Atom *v172; // [rsp+60h] [rbp-F8h]
  struct Atom *v173; // [rsp+60h] [rbp-F8h]
  struct Atom *v174; // [rsp+60h] [rbp-F8h]
  struct Atom *v175; // [rsp+60h] [rbp-F8h]
  struct Atom *v176; // [rsp+68h] [rbp-F0h] BYREF
  struct Atom *v177; // [rsp+70h] [rbp-E8h]
  struct Atom *v178; // [rsp+78h] [rbp-E0h]
  int v179; // [rsp+80h] [rbp-D8h]
  int v180; // [rsp+84h] [rbp-D4h]
  __int64 (__fastcall *v181)(__int64, const unsigned __int16 near *const *, _QWORD, struct Atom *, int, struct Atom *, int, struct Atom *); // [rsp+88h] [rbp-D0h]
  unsigned int v182; // [rsp+90h] [rbp-C8h]
  int v183; // [rsp+94h] [rbp-C4h]
  int v184; // [rsp+98h] [rbp-C0h]
  unsigned int v185; // [rsp+9Ch] [rbp-BCh]
  int v186; // [rsp+A0h] [rbp-B8h]
  __int64 (__fastcall *v187)(__int64 (__fastcall *)(__int64, const unsigned __int16 near *const *, _QWORD, struct Atom *, int, struct Atom *, int, struct Atom *), const unsigned __int16 near *const *, _QWORD, struct Atom *, int); // [rsp+A8h] [rbp-B0h]
  _DWORD *v188; // [rsp+B0h] [rbp-A8h] BYREF
  struct _XML_NODE_INFO **v189; // [rsp+B8h] [rbp-A0h]
  struct Atom *v190; // [rsp+C0h] [rbp-98h]
  void *v191; // [rsp+C8h] [rbp-90h]
  void *v192; // [rsp+D0h] [rbp-88h]
  _WORD *v193; // [rsp+D8h] [rbp-80h]
  struct Atom *v194; // [rsp+E0h] [rbp-78h]
  const unsigned __int16 *v195; // [rsp+E8h] [rbp-70h]
  const unsigned __int16 *v196; // [rsp+F0h] [rbp-68h]
  const unsigned __int16 *v197; // [rsp+F8h] [rbp-60h]
  __int64 v198; // [rsp+100h] [rbp-58h]
  unsigned __int64 v199; // [rsp+108h] [rbp-50h]
  _DWORD *v200; // [rsp+110h] [rbp-48h]
  __int64 v201; // [rsp+118h] [rbp-40h]
  __int64 v202; // [rsp+120h] [rbp-38h]
  int v204; // [rsp+180h] [rbp+28h]
  struct _XML_NODE_INFO **v205; // [rsp+180h] [rbp+28h]
  char v206; // [rsp+180h] [rbp+28h]
  char v207; // [rsp+180h] [rbp+28h]
  unsigned int v208; // [rsp+180h] [rbp+28h]
  int v209; // [rsp+180h] [rbp+28h]
  int v210; // [rsp+180h] [rbp+28h]
  int v211; // [rsp+180h] [rbp+28h]
  struct _XML_NODE_INFO **v212; // [rsp+180h] [rbp+28h]
  struct _XML_NODE_INFO **v213; // [rsp+180h] [rbp+28h]

  LODWORD(v5) = a4;
  v166 = 0;
  v10 = (__int64)*a5;
  v169 = 0;
  v188 = 0;
  v11 = (**(__int64 (__fastcall ***)(struct IXMLNodeSource *, __int64 *, _DWORD **))a2)(a2, qword_18012A028, &v188);
  if ( v11 < 0 )
    Exception::throwHR(v11);
  v12 = v188;
  v200 = v188;
  v13 = *(_DWORD *)(v10 + 4);
  if ( v13 != 1 )
  {
    if ( v13 == 13 )
    {
      v131 = *((_QWORD *)this + 10);
      if ( v131 && (*((_DWORD *)this + 27) || *((_BYTE *)this + 122)) )
LABEL_201:
        v58 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v131 + 80LL))(
                v131,
                *(_QWORD *)(v10 + 16),
                *(unsigned int *)(v10 + 24));
      else
LABEL_208:
        v58 = 0;
    }
    else
    {
      switch ( v13 )
      {
        case 3:
          v133 = ContentFactory::processName(this, (struct _XML_NODE_INFO *)v10, 0);
          if ( !*((_QWORD *)this + 10) )
            goto LABEL_208;
          v134 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)v133 + 2) + 40LL) + 88LL))(*(_QWORD *)(*((_QWORD *)v133 + 2) + 40LL));
          if ( *((_BYTE *)this + 106) )
          {
            v135 = ArrayString::newString(*((const unsigned __int16 **)a5[1] + 2), *((_DWORD *)a5[1] + 6));
            v136 = (*(__int64 (__fastcall **)(struct ArrayString *, _QWORD))(*(_QWORD *)v135 + 128LL))(v135, 0);
            v137 = *(_DWORD *)(v136 + 16);
            if ( v137 )
              v138 = *(_QWORD *)(v136 + 24);
            else
              v138 = 0;
            v58 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, int))(**((_QWORD **)this + 10) + 96LL))(
                    *((_QWORD *)this + 10),
                    *(_QWORD *)(v134 + 24),
                    *(unsigned int *)(v134 + 16),
                    v138,
                    v137);
          }
          else
          {
            v139 = a5[1];
            v140 = *((_DWORD *)v139 + 6);
            if ( v140 )
              v141 = *((_QWORD *)v139 + 2);
            else
              v141 = 0;
            v58 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, int))(**((_QWORD **)this + 10) + 96LL))(
                    *((_QWORD *)this + 10),
                    *(_QWORD *)(v134 + 24),
                    *(unsigned int *)(v134 + 16),
                    v141,
                    v140);
          }
          goto LABEL_282;
        case 4:
          v132 = a5 + 1;
          if ( (int)v5 - 1 <= 0 )
            v132 = 0;
          ContentFactory::processXmlDecl(this, v132, (_DWORD)v5 - 1);
          v58 = 0;
          goto LABEL_282;
        case 5:
          v142 = (*(__int64 (__fastcall **)(struct IXMLNodeSource *, _QWORD))(*(_QWORD *)a2 + 24LL))(
                   a2,
                   *((_QWORD *)this + 6));
          if ( v142 >= 0 )
            v58 = (*(__int64 (__fastcall **)(_QWORD, struct IXMLNodeSource *, void *, _QWORD, struct _XML_NODE_INFO **))(**((_QWORD **)this + 6) + 56LL))(
                    *((_QWORD *)this + 6),
                    a2,
                    a3,
                    (unsigned __int16)v5,
                    a5);
          else
            v58 = v142;
          goto LABEL_282;
        case 14:
          v143 = *((_QWORD *)this + 12);
          if ( !v143 || (v144 = *((_DWORD *)this + 28), *((_DWORD *)this + 28) = v144 + 1, v144) )
          {
            v58 = 0;
          }
          else
          {
            v58 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v143 + 56LL))(v143);
            if ( v58 < 0 )
              goto LABEL_282;
          }
          v145 = *((_QWORD *)this + 10);
          v146 = (char *)this + 107;
          if ( !v145
            || !*v146
            || *(_DWORD *)(v10 + 40) == 2
            || (v58 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v145 + 80LL))(
                        v145,
                        *(_QWORD *)(v10 + 16),
                        *(unsigned int *)(v10 + 24)),
                v58 >= 0) )
          {
            v147 = *((_QWORD *)this + 12);
            if ( v147 )
            {
              if ( *v146 && *(_DWORD *)(v10 + 40) != 1 )
              {
                *((_DWORD *)this + 28) = 0;
                v58 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v147 + 64LL))(v147);
              }
            }
          }
          goto LABEL_282;
        case 16:
          v148 = *((_QWORD *)this + 12);
          if ( !v148 )
            goto LABEL_208;
          v58 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v148 + 72LL))(
                  v148,
                  *(_QWORD *)(v10 + 16),
                  *(unsigned int *)(v10 + 24));
          goto LABEL_282;
        case 17:
          ++*((_DWORD *)this + 29);
          v149 = v12[83];
          if ( v149 && *((_DWORD *)this + 29) > v149 )
          {
            v150 = String::newConstString(L"MaxElementDepth");
            Exception::throwHR(-2147467260, -1072897270, v150, 0, v164, v165);
          }
          v151 = ContentFactory::processName(this, (struct _XML_NODE_INFO *)v10, 0);
          Entity = DTD::findEntity(*((DTD **)this + 5), *((struct Name **)v151 + 2), 0);
          ContentFactory::checkGeneralEntity(this, Entity, *((struct Name **)v151 + 2), 0, 0);
          if ( ContentFactory::parseEntity(this, a2, Entity)
            || (v153 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)v151 + 2) + 40LL) + 88LL))(*(_QWORD *)(*((_QWORD *)v151 + 2) + 40LL)),
                (v154 = *((_QWORD *)this + 10)) == 0) )
          {
            v58 = 0;
          }
          else
          {
            v58 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v154 + 104LL))(
                    v154,
                    *(_QWORD *)(v153 + 24),
                    *(unsigned int *)(v153 + 16));
            if ( v58 < 0 )
              goto LABEL_282;
          }
          --*((_DWORD *)this + 29);
          break;
        case 18:
          v131 = *((_QWORD *)this + 10);
          if ( v131 && (*((_DWORD *)this + 27) || *((_BYTE *)this + 122)) )
            goto LABEL_201;
          goto LABEL_208;
        default:
          goto LABEL_208;
      }
    }
    goto LABEL_282;
  }
  ++*((_DWORD *)this + 29);
  v14 = v12[83];
  if ( v14 && *((_DWORD *)this + 29) > v14 )
  {
    v130 = String::newConstString(L"MaxElementDepth");
    Exception::throwHR(-2147467260, -1072897270, v130, 0, v164, v165);
  }
  ++*((_DWORD *)this + 27);
  *(_DWORD *)v10 = *(_DWORD *)(*((_QWORD *)this + 19) + 20LL);
  if ( *((_BYTE *)this + 121) )
  {
    v5 = (DTD *)*((_QWORD *)this + 5);
    v155 = ContentFactory::processName(this, (struct _XML_NODE_INFO *)v10, 1);
    ElementDecl = DTD::findElementDecl(v5, *((struct Name **)v155 + 2));
    LOWORD(v5) = a4;
    if ( ElementDecl )
      v169 = (struct Atom *)*((_QWORD *)ElementDecl + 11);
  }
  v15 = *((_QWORD *)this + 8);
  v16 = (unsigned __int16)v5 - 1;
  v204 = v16;
  v17 = a5 + 1;
  if ( v16 <= 0 )
    v17 = 0;
  if ( *(_QWORD *)(v15 + 80) )
  {
    Vector::setSize(*(Vector **)(v15 + 88), 0);
    Vector::setSize(*(Vector **)(v15 + 96), 0);
    Vector::setSize(*(Vector **)(v15 + 104), 0);
    v16 = v204;
  }
  if ( v17 )
  {
    v18 = *(_DWORD **)(v15 + 112);
    if ( (int)v18[5] < 0 )
    {
      Vector::ensureCapacity(*(Vector **)(v15 + 112), 0);
      v18[5] = 0;
    }
    else
    {
      for ( i = 0; ; ++i )
      {
        v182 = i;
        if ( (signed int)i >= v18[5] )
          break;
        (*(void (__fastcall **)(_DWORD *, _QWORD, _QWORD))(*(_QWORD *)v18 + 128LL))(v18, i, 0);
      }
      v18[5] = 0;
      LOWORD(v5) = a4;
    }
    v16 = v204;
  }
  *(_BYTE *)(v15 + 121) = 0;
  *(_DWORD *)(v15 + 76) = 0;
  *(_QWORD *)(v15 + 64) = v17;
  *(_DWORD *)(v15 + 72) = v16;
  *(_QWORD *)(v15 + 80) = v169;
  v34 = (void *)*((_QWORD *)this + 8);
  Src = v34;
  if ( *((_QWORD *)v34 + 10) )
  {
    Attributes::preprocessAttDefs((Attributes *)v34);
    Attributes::processDefinedNamespaces((Attributes *)v34, (unsigned __int16)v5 > 1u);
    Attributes::processPromotedNamespaces((Attributes *)v34);
    Attributes::processPromotedAttributes((Attributes *)v34);
    goto LABEL_41;
  }
  v189 = 0;
  v179 = 0;
  if ( (unsigned __int16)v5 > 1u )
  {
    v20 = *((_DWORD *)v34 + 18);
    v179 = v20;
    for ( j = (struct _XML_NODE_INFO **)*((_QWORD *)v34 + 8); ; ++j )
    {
      v189 = j;
      v22 = v20--;
      v179 = v20;
      if ( v22 <= 0 )
        goto LABEL_41;
      v23 = *j;
      if ( *((_DWORD *)*j + 1) == 2 && *((_DWORD *)v23 + 2) == 31 )
        break;
LABEL_17:
      ;
    }
    if ( !*((_DWORD *)v23 + 7) )
    {
      v29 = 0;
      goto LABEL_25;
    }
    v24 = (StringHashtable **)*((_QWORD *)v34 + 4);
    v170 = (struct Atom *)v24;
    v25 = (const unsigned __int16 *)(*((_QWORD *)v23 + 2) + 12LL);
    v205 = (struct _XML_NODE_INFO **)v25;
    v26 = *((_DWORD *)v23 + 6) - 6;
    if ( v26 < 0 )
    {
      v99 = (_WORD *)(*((_QWORD *)v23 + 2) + 12LL);
      v193 = v99;
      v177 = 0;
      v100 = 0;
      v26 = 0;
      if ( v25 )
      {
        while ( 1 )
        {
          v26 = v100;
          if ( v100 >= 0x7FFFFFFF || !*v99 )
            break;
          v193 = ++v99;
          v177 = (struct Atom *)++v100;
        }
      }
    }
    v178 = 0;
    v27 = v24[2];
    if ( v27 )
    {
      v28 = (struct Atom *)StringHashtable::get(v27, v25, v26);
      v178 = v28;
      if ( v28 )
      {
LABEL_23:
        if ( v28 )
        {
          v98 = *(unsigned __int16 *)(*((_QWORD *)v23 + 2) + 12LL);
          if ( (*((_BYTE *)(&g_apCharTables)[(unsigned __int64)*(unsigned __int16 *)(*((_QWORD *)v23 + 2) + 12LL) >> 8]
                + (unsigned __int8)v98)
              & 2) == 0
            && v98 != 95 )
          {
            goto LABEL_270;
          }
        }
        v29 = v178;
LABEL_25:
        v206 = 1;
        v30 = *j;
        v171 = v30;
        *((_QWORD *)v30 + 5) = 0;
        v31 = Src;
        if ( *((_QWORD *)Src + 10) )
        {
          v157 = 0;
          while ( 1 )
          {
            v180 = v157;
            v158 = *((_QWORD *)v31 + 10);
            if ( v157 >= *(_DWORD *)(v158 + 20) )
              break;
            v177 = *(struct Atom **)(*(_QWORD *)(v158 + 32) + 8LL * v157);
            if ( Attributes::equalNames((Attributes *)v157, v30, v177) )
            {
              v30 = v171;
              *((_QWORD *)v171 + 5) = v177;
              v31 = Src;
              break;
            }
            v157 = v180 + 1;
            v30 = v171;
            v31 = Src;
          }
        }
        if ( v20 <= 0 || *((_DWORD *)j[1] + 1) == 2 )
        {
          *((_DWORD *)v30 + 3) = 1;
        }
        else
        {
          *((_DWORD *)v30 + 3) = 0;
          *((_QWORD *)j[1] + 5) = -1;
        }
        v176 = 0;
        if ( *((_DWORD *)*j + 3) )
        {
          Attributes::getDefinedAttributeValue((Attributes *)v31, j + 1, v20, &v176);
          v31 = Src;
        }
        else
        {
          v32 = j[1];
          if ( *((int *)v32 + 10) >= 0 )
          {
            v33 = *(int **)(*(_QWORD *)(*((_QWORD *)v31 + 14) + 32LL) + 8LL * *((int *)v32 + 10));
            v176 = (struct Atom *)v33;
LABEL_32:
            if ( v33[4] > 0 )
            {
              v206 = 0;
              Atom = NamespaceMgr::createAtom(*((NamespaceMgr **)v31 + 4), (struct String *)v33, 0, 0);
              v102 = NamespaceMgr::CanonicalURN(*((NamespaceMgr **)Src + 4), Atom);
              NamespaceMgr::pushScope(*((NamespaceMgr **)Src + 4), v29, v102, Atom, 0);
            }
            if ( v206 )
            {
              if ( v29 )
                Exception::throwHR(-1072898009);
              v34 = Src;
              NamespaceMgr::pushScope(*((NamespaceMgr **)Src + 4), 0, 0, 0, 0);
            }
            else
            {
              v34 = Src;
            }
            *((_BYTE *)v34 + 121) = 1;
            goto LABEL_17;
          }
          Attributes::getDefinedAttributeValue((Attributes *)v31, j + 1, v20, &v176);
          v75 = (unsigned int *)*((_QWORD *)Src + 14);
          v174 = (struct Atom *)v75;
          v76 = v75[5] + 1;
          v77 = v75[6];
          if ( v76 > v77 )
          {
            v159 = v75[4];
            if ( v159 )
              v160 = v77 + v159;
            else
              v160 = 2 * v77 + 2;
            if ( v76 > v160 )
              v160 = v75[5] + 1;
            (*(void (__fastcall **)(unsigned int *, _QWORD))(*(_QWORD *)v75 + 136LL))(v75, (unsigned int)v160);
            v75 = (unsigned int *)v174;
          }
          (*(void (__fastcall **)(unsigned int *, _QWORD, struct Atom *))(*(_QWORD *)v75 + 128LL))(v75, v75[5], v176);
          ++*((_DWORD *)v174 + 5);
          v31 = Src;
          *((_QWORD *)j[1] + 5) = *(_DWORD *)(*((_QWORD *)Src + 14) + 20LL) - 1;
        }
        v33 = (int *)v176;
        goto LABEL_32;
      }
      v25 = (const unsigned __int16 *)v205;
    }
    v110 = Atom::create(0, v25, v26);
    v28 = v110;
    v178 = v110;
    v111 = *((_QWORD *)v170 + 2);
    if ( v111 )
    {
      v112 = (*(__int64 (__fastcall **)(struct Atom *))(*(_QWORD *)v110 + 88LL))(v110);
      LOBYTE(v113) = 1;
      (*(void (__fastcall **)(__int64, __int64, struct Atom *, __int64))(*(_QWORD *)v111 + 128LL))(
        v111,
        v112,
        v178,
        v113);
      v28 = v178;
    }
    goto LABEL_23;
  }
LABEL_41:
  Attributes::processDefinedAttributes((Attributes *)v34);
  v35 = *(unsigned int *)(v10 + 28);
  v36 = *(unsigned int *)(v10 + 24);
  v37 = *(unsigned __int16 **)(v10 + 16);
  Srca = v37;
  if ( (_DWORD)v35 )
  {
    v38 = (unsigned int)(v35 + 1);
    if ( (unsigned int)v36 > (unsigned int)v38 )
    {
      v39 = v37[v38];
      if ( (_WORD)v39 )
      {
        if ( (*((_BYTE *)(&g_apCharTables)[(unsigned __int64)v37[v38] >> 8] + (unsigned __int8)v37[v38]) & 2) == 0
          && v39 != 95 )
        {
LABEL_270:
          Exception::throwHR(-1072896763);
        }
      }
    }
  }
  v40 = *((_QWORD *)this + 4);
  v176 = 0;
  v194 = 0;
  v41 = v36 + 8;
  v42 = -1;
  if ( (int)v36 + 8 >= (unsigned int)v36 )
    v42 = v36 + 8;
  if ( v41 < (unsigned int)v36 )
    Exception::throwHR(v41 < (unsigned int)v36 ? 0x80070216 : 0);
  v43 = *(_DWORD *)(v40 + 104);
  if ( v42 > v43 )
  {
    if ( v43 )
    {
      MemFreeObject(*(void **)(v40 + 96));
      *(_QWORD *)(v40 + 96) = 0;
    }
    *(_DWORD *)(v40 + 104) = 0;
    *(_QWORD *)(v40 + 96) = new_array<unsigned short>(v42);
    *(_DWORD *)(v40 + 104) = v42;
    v37 = (unsigned __int16 *)Srca;
  }
  v207 = 0;
  if ( ((*v37 - 88) & 0xFFDF) == 0 && (unsigned int)v35 > 2 )
  {
    if ( (_DWORD)v35 == 3 )
    {
      v129 = (_DWORD)XMLNames::s_cstrXML_pwz - *(_DWORD *)v37;
      if ( (_DWORD)XMLNames::s_cstrXML_pwz == *(_DWORD *)v37 )
        v129 = WORD2(XMLNames::s_cstrXML_pwz) - v37[2];
      if ( !v129 )
      {
        v45 = (struct Atom *)XMLNames::atomURNXML;
LABEL_273:
        v176 = v45;
        v47 = 1;
        v46 = v45;
        v172 = v45;
        goto LABEL_54;
      }
    }
    if ( (_DWORD)v35 == 5 )
    {
      v120 = (char *)XMLNames::s_cstrXMLNS_pwz - *(_QWORD *)v37;
      if ( XMLNames::s_cstrXMLNS_pwz == *(const unsigned __int16 near *const *)v37 )
        v120 = (char *)(115LL - v37[4]);
      if ( !v120 )
      {
        v45 = (struct Atom *)XMLNames::atomURNXMLNS;
        goto LABEL_273;
      }
    }
    if ( NamespaceMgr::isReservedNameSpace(v37, v35) )
      v207 = 1;
  }
  Entry = 0;
  if ( *(_QWORD *)(v40 + 40) )
  {
    if ( (_DWORD)v35 )
    {
      v60 = *(_QWORD *)(v40 + 72);
      if ( v60 )
      {
        v61 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v60 + 88LL))(v60);
        v62 = Srca;
        if ( *(_DWORD *)(v61 + 16) == (_DWORD)v35 && !memcmp_0(Srca, *(const void **)(v61 + 24), 2 * v35) )
        {
          Entry = (struct NamespaceMgr::Entry *)(*(_QWORD *)(v40 + 48) + 40LL
                                                                       * (unsigned int)(*(_DWORD *)(v40 + 80) - 1));
          goto LABEL_52;
        }
      }
      else
      {
        v62 = Srca;
      }
      v128 = NamespaceMgr::createAtom((NamespaceMgr *)v40, 0, v62, v35);
    }
    else
    {
      v78 = *(_DWORD *)(v40 + 84);
      if ( v78 )
      {
        Entry = (struct NamespaceMgr::Entry *)(*(_QWORD *)(v40 + 48) + 40LL * (unsigned int)(v78 - 1));
        goto LABEL_52;
      }
      v128 = 0;
    }
    Entry = NamespaceMgr::findEntry((NamespaceMgr *)v40, v128);
  }
  if ( !Entry )
  {
    v46 = 0;
    v45 = v176;
    goto LABEL_53;
  }
LABEL_52:
  v45 = (struct Atom *)*((_QWORD *)Entry + 2);
  v176 = v45;
  v46 = (struct Atom *)*((_QWORD *)Entry + 1);
LABEL_53:
  v47 = v207;
  v37 = (unsigned __int16 *)Srca;
  v172 = v46;
LABEL_54:
  if ( !v46 && (_DWORD)v35 )
  {
    v161 = String::newString(v37, v35);
    Exception::throwError(-1072898019, v161, 0, 0, v164);
  }
  v194 = v46;
  if ( v47 )
  {
    v162 = String::newString(v37, v35);
    Exception::throwError(-1072896664, v162, 0, 0, v164);
  }
  **(_QWORD **)(v40 + 96) = v45;
  memcpy_0((void *)(*(_QWORD *)(v40 + 96) + 8LL), v37, 2 * v36);
  v48 = StringHashtable::get(*(StringHashtable **)(v40 + 88), *(const unsigned __int16 **)(v40 + 96), (int)v36 + 4);
  if ( v48 )
    goto LABEL_57;
  if ( !(_DWORD)v35 )
  {
    v177 = 0;
    if ( (int)v36 < 0 )
    {
      v116 = Srca;
      v197 = Srca;
      v181 = 0;
      for ( k = 0;
            ;
            v181 = (__int64 (__fastcall *)(__int64, const unsigned __int16 near *const *, _QWORD, struct Atom *, int, struct Atom *, int, struct Atom *))k )
      {
        v63 = k;
        if ( k >= 0x7FFFFFFF || !*v116 )
          break;
        v197 = ++v116;
        ++k;
      }
    }
    else
    {
      v63 = v36;
    }
    v192 = 0;
    v64 = *(StringHashtable **)(v40 + 16);
    if ( v64 )
    {
      v65 = StringHashtable::get(v64, Srca, v63);
      v192 = v65;
      if ( v65 )
        goto LABEL_85;
    }
    v108 = Atom::create(0, Srca, v63);
    v65 = (struct IUnknown *)v108;
    v212 = (struct _XML_NODE_INFO **)v108;
    v192 = v108;
    v109 = *(_QWORD *)(v40 + 16);
    if ( !v109 )
      goto LABEL_85;
    goto LABEL_166;
  }
  if ( (int)v35 < 0 )
  {
    v121 = Srca;
    v195 = Srca;
    for ( m = 0; ; ++m )
    {
      v103 = m;
      v210 = m;
      if ( m >= 0x7FFFFFFF )
        break;
      v210 = m;
      if ( !*v121 )
        break;
      v195 = ++v121;
    }
  }
  else
  {
    v103 = v35;
    v210 = v35;
  }
  v190 = 0;
  v104 = *(StringHashtable **)(v40 + 16);
  if ( !v104 )
    goto LABEL_181;
  v177 = (struct Atom *)StringHashtable::get(v104, Srca, v103);
  v190 = v177;
  if ( !v177 )
  {
    v103 = v210;
LABEL_181:
    v123 = Atom::create(0, Srca, v103);
    v177 = v123;
    v190 = v123;
    v213 = *(struct _XML_NODE_INFO ***)(v40 + 16);
    if ( v213 )
    {
      v124 = (*(__int64 (__fastcall **)(struct Atom *))(*(_QWORD *)v123 + 88LL))(v123);
      LOBYTE(v125) = 1;
      (*((void (__fastcall **)(struct _XML_NODE_INFO **, __int64, struct Atom *, __int64))*v213 + 16))(
        v213,
        v124,
        v177,
        v125);
    }
  }
  if ( (unsigned int)v36 <= (unsigned int)v35 )
  {
    v65 = (struct IUnknown *)Atom::s_emptyAtom;
    goto LABEL_85;
  }
  v105 = v36 - v35 - 1;
  v211 = v105;
  v106 = &Srca[v35 + 1];
  if ( v105 < 0 )
  {
    v126 = &Srca[v35 + 1];
    v196 = v126;
    v187 = 0;
    v127 = 0;
    v105 = 0;
    v211 = 0;
    if ( &Srca[v35] != (const unsigned __int16 *)-2LL )
    {
      while ( 1 )
      {
        v105 = v127;
        v211 = v127;
        if ( v127 >= 0x7FFFFFFF )
          break;
        v211 = v127;
        if ( !*v126 )
          break;
        v196 = ++v126;
        v187 = (__int64 (__fastcall *)(__int64 (__fastcall *)(__int64, const unsigned __int16 near *const *, _QWORD, struct Atom *, int, struct Atom *, int, struct Atom *), const unsigned __int16 near *const *, _QWORD, struct Atom *, int))++v127;
      }
    }
  }
  v191 = 0;
  v107 = *(StringHashtable **)(v40 + 16);
  if ( v107 )
  {
    v65 = StringHashtable::get(v107, v106, v105);
    v191 = v65;
    if ( v65 )
      goto LABEL_85;
  }
  v108 = Atom::create(0, v106, v211);
  v65 = (struct IUnknown *)v108;
  v212 = (struct _XML_NODE_INFO **)v108;
  v191 = v108;
  v109 = *(_QWORD *)(v40 + 16);
  if ( !v109 )
    goto LABEL_85;
LABEL_166:
  v118 = (*(__int64 (__fastcall **)(struct IUnknown *))(*(_QWORD *)v108 + 88LL))(v65);
  LOBYTE(v119) = 1;
  (*(void (__fastcall **)(__int64, __int64, struct _XML_NODE_INFO **, __int64))(*(_QWORD *)v109 + 128LL))(
    v109,
    v118,
    v212,
    v119);
  v65 = (struct IUnknown *)v212;
LABEL_85:
  v67 = Name::create((struct Atom *)v65, v172);
  if ( g_fUseMpHeap )
    v68 = (NameDef *)MpHeapAlloc(v66, 0x2000000Cu, 0x28u);
  else
    v68 = (NameDef *)HeapAlloc(g_hProcessHeap, 0x2000000Cu, 0x28u);
  v69 = v68;
  if ( !v68 )
  {
    failure_tracing::record();
    Exception::raiseException((struct Exception *)&Exception::s_cexpOutOfMem);
    __debugbreak();
  }
  Value = TlsGetValue(g_dwTlsIndex);
  v71 = 4;
  if ( Value[19] )
    v71 = -1;
  *((_QWORD *)v69 + 1) = v71;
  v48 = (struct IUnknown *)NameDef::NameDef(v69, v67, v176, v177);
  v72 = *(_QWORD *)(v40 + 88);
  v73 = *(const unsigned __int16 **)(v40 + 96);
  if ( !v73 || (_DWORD)v36 == -4 )
    v74 = (struct ArrayString *)&String::s_cstrEmpty;
  else
    v74 = ArrayString::newString(v73, (int)v36 + 4);
  (*(void (__fastcall **)(__int64, struct ArrayString *, struct IUnknown *, _QWORD))(*(_QWORD *)v72 + 128LL))(
    v72,
    v74,
    v48,
    0);
LABEL_57:
  *(_QWORD *)(v10 + 32) = v48;
  if ( *(_BYTE *)(*((_QWORD *)this + 8) + 121LL) )
  {
    v79 = *((_QWORD *)this + 4);
    v80 = *(_QWORD *)(v79 + 40);
    if ( v80 )
    {
      v183 = *(_QWORD *)(v79 + 40);
      while ( 1 )
      {
        v114 = v80;
        v80 = (unsigned int)(v80 - 1);
        v183 = v80;
        if ( !v114 )
          break;
        v115 = *(_QWORD *)(v79 + 48);
        if ( *(_QWORD *)(v115 + 40 * v80 + 24) )
          break;
        *(_QWORD *)(v115 + 40 * v80 + 24) = v10;
      }
    }
    v81 = *((_QWORD *)this + 4);
    v82 = 0;
    v184 = 0;
    v83 = *(_QWORD *)(v81 + 40);
    v198 = v83;
    while ( 1 )
    {
      v84 = v83;
      v198 = --v83;
      if ( !v84 )
        break;
      v85 = *(_QWORD *)(v81 + 48);
      if ( *(_QWORD *)(v85 + 40 * v83 + 24) != v10 )
        break;
      if ( *(_QWORD *)(v85 + 40 * v83) != -1 )
        v184 = ++v82;
    }
    v86 = v82;
    *(_QWORD *)(v10 + 40) = (int)v82;
    if ( *((_QWORD *)this + 10) )
    {
      v185 = v82;
LABEL_111:
      while ( 1 )
      {
        v87 = v86--;
        v185 = v86;
        if ( !v87 )
          break;
        v88 = *((_QWORD *)this + 4);
        v89 = v86;
        v186 = v86;
        v90 = *(_QWORD *)(v88 + 40);
        if ( v86 <= v90 )
        {
          v199 = *(_QWORD *)(v88 + 40);
          while ( 1 )
          {
            v91 = v90--;
            v199 = v90;
            if ( !v91 )
              break;
            v92 = (__int64 *)(*(_QWORD *)(v88 + 48) + 40 * v90);
            v93 = *v92;
            if ( *v92 != -1 )
            {
              if ( !v89 )
              {
                v201 = *v92;
                v94 = v92[1];
                v202 = v94;
                v181 = (__int64 (__fastcall *)(__int64, const unsigned __int16 near *const *, _QWORD, struct Atom *, int, struct Atom *, int, struct Atom *))*((_QWORD *)this + 10);
                v187 = *(__int64 (__fastcall **)(__int64 (__fastcall *)(__int64, const unsigned __int16 near *const *, _QWORD, struct Atom *, int, struct Atom *, int, struct Atom *), const unsigned __int16 near *const *, _QWORD, struct Atom *, int))(*(_QWORD *)v181 + 48LL);
                if ( v94 )
                  v209 = *(_DWORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v94 + 88LL))(v94) + 16);
                else
                  v209 = 0;
                if ( v94 )
                  v95 = *(const unsigned __int16 near *const **)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v94 + 88LL))(v94)
                                                               + 24);
                else
                  v95 = off_1801457D8;
                v175 = (struct Atom *)v95;
                if ( v93 )
                  v96 = *(_DWORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v93 + 88LL))(v93) + 16);
                else
                  v96 = 0;
                if ( v93 )
                  v97 = *(const unsigned __int16 near *const **)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v93 + 88LL))(v93)
                                                               + 24);
                else
                  v97 = off_1801457D8;
                v58 = v187(v181, v97, v96, v175, v209);
                v166 = v58;
                if ( v58 < 0 )
                  goto LABEL_282;
                goto LABEL_111;
              }
              v186 = --v89;
            }
          }
        }
      }
    }
    v49 = 0;
  }
  else
  {
    v49 = 0;
    *(_QWORD *)(v10 + 40) = 0;
  }
  v50 = *((_QWORD *)this + 10);
  if ( !v50 || !*((_BYTE *)this + 107) )
  {
    v58 = v166;
LABEL_68:
    v59 = *((_QWORD *)this + 8);
    if ( *(_QWORD *)(v59 + 80) )
    {
      Vector::setSize(*(Vector **)(v59 + 88), 0);
      Vector::setSize(*(Vector **)(v59 + 96), 0);
      Vector::setSize(*(Vector **)(v59 + 104), 0);
    }
    *(_BYTE *)(v59 + 121) = 0;
    *(_QWORD *)(v59 + 72) = 0;
    *(_QWORD *)(v59 + 64) = 0;
    *(_QWORD *)(v59 + 80) = 0;
    goto LABEL_282;
  }
  lpVtbl = v48[4].lpVtbl;
  v52 = *(_DWORD *)(v10 + 28);
  v53 = *(_DWORD *)(v10 + 24);
  v54 = *(struct Atom **)(v10 + 16);
  v55 = v53;
  if ( v52 )
  {
    v55 = v53 - v52 - 1;
    v177 = (struct Atom *)((char *)v54 + 2 * (unsigned int)(v52 + 1));
    v49 = 0;
  }
  else
  {
    v177 = v54;
  }
  v181 = *(__int64 (__fastcall **)(__int64, const unsigned __int16 near *const *, _QWORD, struct Atom *, int, struct Atom *, int, struct Atom *))(*(_QWORD *)v50 + 64LL);
  v56 = (struct Atom *)*((_QWORD *)this + 8);
  v173 = v56;
  if ( lpVtbl )
  {
    v49 = *(_DWORD *)((*((__int64 (__fastcall **)(struct IUnknownVtbl *))lpVtbl->QueryInterface + 11))(lpVtbl) + 16);
    v56 = v173;
  }
  v208 = v49;
  if ( lpVtbl )
  {
    v57 = *(const unsigned __int16 near *const **)((*((__int64 (__fastcall **)(struct IUnknownVtbl *))lpVtbl->QueryInterface
                                                    + 11))(lpVtbl)
                                                 + 24);
    v56 = v173;
    v49 = v208;
  }
  else
  {
    v57 = off_1801457D8;
  }
  v58 = v181(v50, v57, v49, v177, v55, v54, v53, v56);
  if ( v58 >= 0 )
    goto LABEL_68;
LABEL_282:
  if ( v12 )
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v12 + 16LL))(v12);
  return (unsigned int)v58;
}

```

## disassembly

```asm
0x180016a80  mov     [rsp+arg_0], rbx
0x180016a85  mov     [rsp+arg_10], rsi
0x180016a8a  mov     [rsp+arg_18], r9w
0x180016a90  mov     [rsp+arg_8], rdx
0x180016a95  push    rdi
0x180016a96  push    r12
0x180016a98  push    r13
0x180016a9a  push    r14
0x180016a9c  push    r15
0x180016a9e  sub     rsp, 130h
0x180016aa5  movzx   ebx, r9w
0x180016aa9  mov     rsi, r8
0x180016aac  mov     rdi, rdx
0x180016aaf  mov     r15, rcx
0x180016ab2  mov     r12, [rsp+158h+arg_20]
0x180016aba  xor     ecx, ecx
0x180016abc  mov     [rsp+158h+var_108], ecx
0x180016ac0  mov     r13, [r12]
0x180016ac4  mov     [rsp+158h+var_F8], rcx
0x180016ac9  mov     [rsp+158h+var_A8], rcx
0x180016ad1  mov     rax, [rdx]
0x180016ad4  lea     r8, [rsp+158h+var_A8]
0x180016adc  lea     rdx, qword_18012A028
0x180016ae3  mov     rcx, rdi
0x180016ae6  mov     rax, [rax]
0x180016ae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016aee  test    eax, eax
0x180016af0  js      loc_18001814F
0x180016af6  mov     r14, [rsp+158h+var_A8]
0x180016afe  mov     [rsp+158h+var_48], r14
0x180016b06  mov     eax, [r13+4]
0x180016b0a  cmp     eax, 1
0x180016b0d  jnz     loc_180017A22
0x180016b13  inc     dword ptr [r15+74h]
0x180016b17  mov     ecx, [r15+74h]
0x180016b1b  mov     eax, [r14+14Ch]
0x180016b22  test    eax, eax
0x180016b24  jnz     loc_1800179F9
0x180016b2a  inc     dword ptr [r15+6Ch]
0x180016b2e  mov     rax, [r15+98h]
0x180016b35  mov     ecx, [rax+14h]
0x180016b38  mov     [r13+0], ecx
0x180016b3c  cmp     byte ptr [r15+79h], 0
0x180016b41  jnz     loc_180017DFD
0x180016b47  mov     rsi, [r15+40h]
0x180016b4b  movzx   ecx, bx
0x180016b4e  dec     ecx
0x180016b50  mov     dword ptr [rsp+158h+arg_20], ecx
0x180016b57  add     r12, 8
0x180016b5b  xor     r8d, r8d
0x180016b5e  test    ecx, ecx
0x180016b60  cmovle  r12, r8
0x180016b64  cmp     [rsi+50h], r8
0x180016b68  jnz     loc_180017E3A
0x180016b6e  test    r12, r12
0x180016b71  jz      loc_180016D2E
0x180016b77  mov     rdi, [rsi+70h]
0x180016b7b  cmp     dword ptr [rdi+14h], 0
0x180016b7f  jl      loc_180017E6A
0x180016b85  mov     ebx, r8d
0x180016b88  mov     [rsp+158h+var_C8], ebx
0x180016b8f  xor     r8d, r8d
0x180016b92  cmp     ebx, [rdi+14h]
0x180016b95  jge     loc_180016D1B
0x180016b9b  mov     rax, [rdi]
0x180016b9e  mov     edx, ebx
0x180016ba0  mov     rcx, rdi
0x180016ba3  mov     rax, [rax+80h]
0x180016baa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016baf  inc     ebx
0x180016bb1  jmp     short loc_180016B88
0x180016bb3  mov     esi, [r12+48h]
0x180016bb8  mov     [rsp+158h+var_D8], esi
0x180016bbf  mov     rbx, [r12+40h]
0x180016bc4  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180016bcb  mov     [rsp+158h+var_A0], rbx
0x180016bd3  mov     eax, esi
0x180016bd5  dec     esi
0x180016bd7  mov     [rsp+158h+var_D8], esi
0x180016bde  test    eax, eax
0x180016be0  jle     loc_180016D7D
0x180016be6  mov     rdi, [rbx]
0x180016be9  cmp     dword ptr [rdi+4], 2
0x180016bed  jz      short loc_180016BF5
0x180016bef  add     rbx, 8
0x180016bf3  jmp     short loc_180016BCB
0x180016bf5  cmp     dword ptr [rdi+8], 1Fh
0x180016bf9  jnz     short loc_180016BEF
0x180016bfb  cmp     dword ptr [rdi+1Ch], 0
0x180016bff  jz      loc_180016FF4
0x180016c05  mov     rdx, [r12+20h]
0x180016c0a  mov     [rsp+158h+var_F8], rdx
0x180016c0f  mov     r12d, [rdi+18h]
0x180016c13  mov     r9, [rdi+10h]
0x180016c17  add     r9, 0Ch
0x180016c1b  mov     [rsp+158h+arg_20], r9
0x180016c23  add     r12d, 0FFFFFFFAh
0x180016c27  js      loc_180017433
0x180016c2d  mov     [rsp+158h+var_E0], r8
0x180016c32  mov     rcx, [rdx+10h]; this
0x180016c36  test    rcx, rcx
0x180016c39  jz      loc_1800175F3
0x180016c3f  mov     r8d, r12d; int
0x180016c42  mov     rdx, r9; unsigned __int16 *
0x180016c45  call    ?get@StringHashtable@@QEAAPEAUIUnknown@@PEBGH@Z; StringHashtable::get(ushort const *,int)
0x180016c4a  mov     rcx, rax
0x180016c4d  mov     [rsp+158h+var_E0], rax
0x180016c52  test    rax, rax
0x180016c55  jz      loc_180017E80
0x180016c5b  test    rcx, rcx
0x180016c5e  jnz     loc_1800173FB
0x180016c64  mov     r12, [rsp+158h+var_E0]
0x180016c69  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180016c70  xor     r8d, r8d
0x180016c73  mov     byte ptr [rsp+158h+arg_20], 1
0x180016c7b  mov     rdx, [rbx]; struct _XML_NODE_INFO *
0x180016c7e  mov     [rsp+158h+var_F8], rdx
0x180016c83  mov     [rdx+28h], r8
0x180016c87  mov     r10, [rsp+158h+Src]
0x180016c8c  cmp     qword ptr [r10+50h], 0
0x180016c91  jnz     loc_180017E8D
0x180016c97  test    esi, esi
0x180016c99  jle     loc_180017EF4
0x180016c9f  mov     rax, [rbx+8]
0x180016ca3  cmp     dword ptr [rax+4], 2
0x180016ca7  jz      loc_180017EF4
0x180016cad  mov     [rdx+0Ch], r8d
0x180016cb1  mov     rax, [rbx+8]
0x180016cb5  mov     [rax+28h], rcx
0x180016cb9  mov     [rsp+158h+var_F0], r8
0x180016cbe  mov     rax, [rbx]
0x180016cc1  cmp     dword ptr [rax+0Ch], 0
0x180016cc5  jnz     loc_1800179C9
0x180016ccb  mov     rax, [rbx+8]
0x180016ccf  movsxd  rcx, dword ptr [rax+28h]
0x180016cd3  test    ecx, ecx
0x180016cd5  js      loc_180017167
0x180016cdb  mov     rdx, rcx
0x180016cde  mov     rax, [r10+70h]
0x180016ce2  mov     rcx, [rax+20h]
0x180016ce6  mov     rax, [rcx+rdx*8]
0x180016cea  mov     [rsp+158h+var_F0], rax
0x180016cef  cmp     dword ptr [rax+10h], 0
0x180016cf3  jg      loc_1800174A6
0x180016cf9  cmp     byte ptr [rsp+158h+arg_20], 0
0x180016d01  jz      loc_1800171FC
0x180016d07  test    r12, r12
0x180016d0a  jz      loc_180017F39
0x180016d10  mov     ecx, 0C00CE027h; int
0x180016d15  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x180016d1b  mov     [rdi+14h], r8d
0x180016d1f  movzx   ebx, [rsp+158h+arg_18]
0x180016d27  mov     ecx, dword ptr [rsp+158h+arg_20]
0x180016d2e  mov     byte ptr [rsi+79h], 0
0x180016d32  mov     [rsi+4Ch], r8d
0x180016d36  mov     [rsi+40h], r12
0x180016d3a  mov     [rsi+48h], ecx
0x180016d3d  mov     rax, [rsp+158h+var_F8]
0x180016d42  mov     [rsi+50h], rax
0x180016d46  mov     r12, [r15+40h]
0x180016d4a  mov     [rsp+158h+Src], r12
0x180016d4f  cmp     bx, 1
0x180016d53  setnbe  dil
0x180016d57  cmp     qword ptr [r12+50h], 0
0x180016d5d  jnz     loc_180017821
0x180016d63  mov     [rsp+158h+var_A0], r8
0x180016d6b  mov     [rsp+158h+var_D8], r8d
0x180016d73  cmp     bx, 1
0x180016d77  ja      loc_180016BB3
0x180016d7d  lea     rdi, __ImageBase
0x180016d84  mov     rcx, r12; this
0x180016d87  call    ?processDefinedAttributes@Attributes@@AEAAXXZ; Attributes::processDefinedAttributes(void)
0x180016d8c  mov     esi, [r13+1Ch]
0x180016d90  mov     ebx, [r13+18h]
0x180016d94  mov     r9, [r13+10h]
0x180016d98  mov     [rsp+158h+Src], r9
0x180016d9d  test    esi, esi
0x180016d9f  jz      short loc_180016DCD
0x180016da1  lea     eax, [rsi+1]
0x180016da4  cmp     ebx, eax
0x180016da6  jbe     short loc_180016DCD
0x180016da8  movzx   edx, word ptr [r9+rax*2]
0x180016dad  test    dx, dx
0x180016db0  jz      short loc_180016DCD
0x180016db2  mov     eax, edx
0x180016db4  shr     rax, 8
0x180016db8  movzx   ecx, dl
0x180016dbb  mov     rax, ds:rva ?g_apCharTables@@3QBQEBEB[rdi+rax*8]; uchar const * const near * const g_apCharTables ...
0x180016dc3  test    byte ptr [rcx+rax], 2
0x180016dc7  jz      loc_180017F5E
0x180016dcd  mov     r12, [r15+20h]
0x180016dd1  xor     eax, eax
0x180016dd3  mov     [rsp+158h+var_F0], rax
0x180016dd8  mov     [rsp+158h+var_F8], rax
0x180016ddd  mov     [rsp+158h+var_78], rax
0x180016de5  lea     eax, [rbx+8]
0x180016de8  mov     edi, 0FFFFFFFFh
0x180016ded  cmp     eax, ebx
0x180016def  cmovnb  edi, eax
0x180016df2  sbb     ecx, ecx
0x180016df4  and     ecx, 80070216h; int
0x180016dfa  cmp     eax, ebx
0x180016dfc  jb      loc_180017F72
0x180016e02  mov     eax, [r12+68h]
0x180016e07  cmp     edi, eax
0x180016e09  ja      loc_180017720
0x180016e0f  mov     byte ptr [rsp+158h+arg_20], 0
0x180016e17  movzx   eax, word ptr [r9]
0x180016e1b  sub     ax, 58h ; 'X'
0x180016e1f  mov     ecx, 0FFDFh
0x180016e24  test    cx, ax
0x180016e27  jz      loc_1800177C7
0x180016e2d  xor     eax, eax
0x180016e2f  cmp     [r12+28h], rax
0x180016e34  jnz     loc_180016FFC
0x180016e3a  test    rax, rax
0x180016e3d  jz      loc_1800179BD
0x180016e43  mov     rcx, [rax+10h]
0x180016e47  mov     [rsp+158h+var_F0], rcx
0x180016e4c  mov     [rsp+158h+var_F8], rcx
0x180016e51  mov     rdx, [rax+8]
0x180016e55  movzx   eax, byte ptr [rsp+158h+arg_20]
0x180016e5d  mov     r9, [rsp+158h+Src]
0x180016e62  mov     [rsp+158h+var_F8], rdx
0x180016e67  test    rdx, rdx
0x180016e6a  jz      loc_180017FC8
0x180016e70  mov     [rsp+158h+var_78], rdx
0x180016e78  test    al, al
0x180016e7a  jnz     loc_180017FEE
0x180016e80  mov     rax, [r12+60h]
0x180016e85  mov     [rax], rcx
0x180016e88  mov     r8, rbx
0x180016e8b  add     r8, r8; Size
0x180016e8e  mov     rcx, [r12+60h]
0x180016e93  add     rcx, 8; void *
0x180016e97  mov     rdx, r9; Src
0x180016e9a  call    memcpy_0
0x180016e9f  lea     r8d, [rbx+4]; int
0x180016ea3  mov     rdx, [r12+60h]; unsigned __int16 *
0x180016ea8  mov     rcx, [r12+58h]; this
0x180016ead  call    ?get@StringHashtable@@QEAAPEAUIUnknown@@PEBGH@Z; StringHashtable::get(ushort const *,int)
0x180016eb2  mov     rdi, rax
0x180016eb5  test    rax, rax
0x180016eb8  jz      loc_18001705F
0x180016ebe  mov     [r13+20h], rdi
0x180016ec2  mov     rax, [r15+40h]
0x180016ec6  cmp     byte ptr [rax+79h], 0
0x180016eca  jnz     loc_180017222
0x180016ed0  xor     ecx, ecx
0x180016ed2  mov     [r13+28h], rcx
0x180016ed6  mov     r12, [r15+50h]
0x180016eda  test    r12, r12
0x180016edd  jz      loc_180016FD1
0x180016ee3  cmp     byte ptr [r15+6Bh], 0
0x180016ee8  jz      loc_180016FD1
0x180016eee  mov     rbx, [rdi+20h]
0x180016ef2  mov     eax, [r13+1Ch]
0x180016ef6  mov     edi, [r13+18h]
0x180016efa  mov     rsi, [r13+10h]
0x180016efe  mov     r13d, edi
0x180016f01  test    eax, eax
0x180016f03  jnz     loc_180016FDC
0x180016f09  mov     [rsp+158h+var_E8], rsi
0x180016f0e  mov     rax, [r12]
0x180016f12  mov     rax, [rax+40h]
0x180016f16  mov     [rsp+158h+var_D0], rax
0x180016f1e  mov     rax, [r15+40h]
0x180016f22  mov     [rsp+158h+var_F8], rax
0x180016f27  test    rbx, rbx
0x180016f2a  jz      short loc_180016F43
0x180016f2c  mov     rax, [rbx]
0x180016f2f  mov     rcx, rbx
0x180016f32  mov     rax, [rax+58h]
0x180016f36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f3b  mov     ecx, [rax+10h]
0x180016f3e  mov     rax, [rsp+158h+var_F8]
0x180016f43  mov     dword ptr [rsp+158h+arg_20], ecx
0x180016f4a  test    rbx, rbx
0x180016f4d  jz      loc_180017216
0x180016f53  mov     rax, [rbx]
0x180016f56  mov     rcx, rbx
0x180016f59  mov     rax, [rax+58h]
0x180016f5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f62  mov     rdx, [rax+18h]
0x180016f66  mov     rax, [rsp+158h+var_F8]
0x180016f6b  mov     ecx, dword ptr [rsp+158h+arg_20]
0x180016f72  mov     [rsp+158h+var_120], rax
0x180016f77  mov     [rsp+158h+var_128], edi
0x180016f7b  mov     [rsp+158h+var_130], rsi
0x180016f80  mov     dword ptr [rsp+158h+var_138], r13d
0x180016f85  mov     r9, [rsp+158h+var_E8]
0x180016f8a  mov     r8d, ecx
0x180016f8d  mov     rcx, r12
0x180016f90  mov     rax, [rsp+158h+var_D0]
0x180016f98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f9d  mov     esi, eax
0x180016f9f  mov     [rsp+158h+var_104], eax
0x180016fa3  test    eax, eax
0x180016fa5  js      short loc_180016FD7
0x180016fa7  xor     ecx, ecx
  ... truncated ...
```
