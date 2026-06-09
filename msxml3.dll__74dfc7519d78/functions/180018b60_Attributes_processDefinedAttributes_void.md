# Attributes::processDefinedAttributes(void)

- ea: `0x180018b60`
- end: `0x180019d58`
- name: `?processDefinedAttributes@Attributes@@AEAAXXZ`
- size: `4600`
- prototype: `void __fastcall(Attributes *__hidden this)`
- caller_count: `1`
- callee_count: `33`
- tags: `registry_config`

## callers

- `0x180016a80`

## callees

- `0x18000a5cc`
- `0x1800108cc`
- `0x180014214`
- `0x180015c8c`
- `0x180016078`
- `0x180016334`
- `0x18001690c`
- `0x1800169b0`
- `0x180018940`
- `0x180018b60`
- `0x18001a440`
- `0x18001aa40`
- `0x18001adb0`
- `0x18001b690`
- `0x18001c310`
- `0x18001f080`
- `0x180034304`
- `0x18003e4e0`
- `0x18003f1e4`
- `0x18004a8fc`
- `0x18004aa88`
- `0x18004abb8`
- `0x18004b488`
- `0x18004b4dc`
- `0x18004f5f4`
- `0x18004f6b8`
- `0x18006489c`
- `0x1800da0c8`
- `0x1800da2f8`
- `0x1800da358`
- `0x180102cba`
- `0x180102cc6`
- `0x180107010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800197c9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800198f4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800197c9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800198f4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180018e1c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001921b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180018e1c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001921b`

## string_xrefs

- `0x1800193a4`: `xmlns:`

## pseudocode

```c
void __fastcall Attributes::processDefinedAttributes(Attributes *this)
{
  int v1; // r13d
  struct _XML_NODE_INFO **v2; // rbx
  struct _XML_NODE_INFO *v4; // rsi
  int v5; // ecx
  __int64 v6; // r13
  unsigned __int16 *v7; // r9
  __int64 v8; // rdi
  __int64 v9; // rax
  int v10; // edx
  unsigned int v11; // r12d
  struct _XML_NODE_INFO *v12; // rdi
  struct _XML_NODE_INFO *v13; // rdx
  struct _XML_NODE_INFO **v14; // rdi
  String *v15; // r12
  __int64 v16; // rax
  struct Atom *v17; // rcx
  __int64 v18; // r15
  unsigned int v19; // eax
  Attributes *v20; // rcx
  struct IUnknown *v21; // r12
  int v22; // edi
  unsigned __int64 i; // r15
  __int64 v24; // rax
  _QWORD *v25; // rax
  _QWORD *v26; // r15
  __int64 *v27; // r12
  _DWORD *Value; // rax
  __int64 v29; // rcx
  int v30; // edx
  __int64 v31; // r12
  __int64 v32; // rax
  unsigned int *v33; // r15
  int v34; // eax
  int v35; // ecx
  const unsigned __int16 *v36; // r12
  struct String *v37; // rax
  int v38; // r13d
  int v39; // r9d
  int v40; // r15d
  int v41; // eax
  unsigned int v42; // ecx
  unsigned __int16 *v43; // r12
  unsigned int v44; // r8d
  __int16 v45; // r9
  int v46; // r8d
  __int64 v47; // rcx
  __int64 v48; // rax
  struct NamespaceMgr::Entry *Entry; // rax
  unsigned int v50; // r15d
  __int64 v51; // r13
  unsigned int v52; // edi
  __int64 v53; // rax
  const unsigned __int16 *v54; // r12
  int v55; // edx
  unsigned int v56; // eax
  __int64 v57; // r13
  unsigned int v58; // ecx
  const unsigned __int16 *v59; // rdx
  StringHashtable *v60; // rcx
  struct IUnknown *v61; // rax
  const unsigned __int16 *v62; // r12
  unsigned __int64 v63; // r13
  StringHashtable *v64; // rcx
  struct IUnknown *v65; // rax
  struct Atom *v66; // r13
  void *v67; // rcx
  struct Name *v68; // r13
  struct IUnknown *v69; // rax
  _DWORD *v70; // rax
  __int64 v71; // rcx
  __int64 *v72; // rax
  struct Atom *v73; // r13
  struct Atom *Atom; // rax
  struct Atom *v75; // rax
  __int64 v76; // rax
  void *lpVtbl; // rcx
  struct IUnknown *v78; // rcx
  struct IUnknownVtbl *v79; // r13
  const unsigned __int16 *v80; // rcx
  __int64 v81; // r13
  struct ArrayString *v82; // rdx
  unsigned __int64 v83; // rcx
  unsigned __int16 *v84; // rdx
  unsigned __int64 v85; // r12
  StringHashtable *v86; // rcx
  struct Atom *v87; // rax
  __int64 v88; // r12
  __int64 v89; // rax
  __int64 v90; // r9
  void (__fastcall *v91)(__int64, __int64, struct Atom *, __int64); // r10
  unsigned int v92; // eax
  struct ArrayString *v93; // rax
  __int64 v94; // rcx
  _WORD *v95; // rax
  char *v96; // rcx
  struct Atom *v97; // rax
  struct Name *v98; // rax
  struct NameDef *v99; // r15
  __int64 v100; // rdi
  struct String *v101; // rax
  _WORD *v102; // rax
  struct IUnknown *v103; // rcx
  __int64 v104; // rax
  __int64 v105; // r9
  int v106; // r13d
  unsigned __int16 *v107; // rax
  int v108; // eax
  int v109; // r9d
  int v110; // r9d
  unsigned __int16 *v111; // r8
  __int16 v112; // cx
  __int64 v113; // r8
  unsigned __int16 v114; // dx
  struct Object *v115; // r12
  Hashtable *v116; // rcx
  __int64 v117; // rax
  struct IUnknown *v118; // r15
  int j; // r15d
  __int64 v120; // rax
  struct AttDef *v121; // r12
  unsigned __int16 v122; // dx
  unsigned int v123; // edx
  __int64 v124; // rdx
  struct String *v125; // [rsp+20h] [rbp-50h]
  int v126[2]; // [rsp+30h] [rbp-40h]
  int v127; // [rsp+30h] [rbp-40h]
  struct Atom *v128; // [rsp+38h] [rbp-38h]
  struct Atom *v129; // [rsp+38h] [rbp-38h]
  struct ArrayString *v130; // [rsp+40h] [rbp-30h]
  __int64 v131; // [rsp+48h] [rbp-28h] BYREF
  String *v132; // [rsp+50h] [rbp-20h]
  __int16 v133; // [rsp+58h] [rbp-18h]
  void *Buf1; // [rsp+B0h] [rbp+40h] BYREF
  int v135; // [rsp+B8h] [rbp+48h]
  struct Atom *v136; // [rsp+C0h] [rbp+50h]
  struct IUnknown *v137; // [rsp+C8h] [rbp+58h] BYREF

  v1 = *((_DWORD *)this + 18);
  v2 = (struct _XML_NODE_INFO **)*((_QWORD *)this + 8);
  *((_DWORD *)this + 19) = 0;
  while ( v1 > 0 )
  {
    v4 = *v2;
    v135 = --v1;
    if ( *((_DWORD *)v4 + 1) != 2 )
      goto LABEL_20;
    v5 = *((_DWORD *)this + 19);
    *((_DWORD *)this + 19) = v5 + 1;
    if ( *((_DWORD *)v4 + 2) != 31 )
    {
      v6 = *((unsigned int *)v4 + 7);
      v7 = (unsigned __int16 *)*((_QWORD *)v4 + 2);
      v8 = *((unsigned int *)v4 + 6);
      Buf1 = v7;
      if ( (_DWORD)v6 )
      {
        v9 = (unsigned int)(v6 + 1);
        if ( (unsigned int)v8 > (unsigned int)v9 )
        {
          v10 = v7[v9];
          if ( (_WORD)v10 )
          {
            if ( (*((_BYTE *)(&g_apCharTables)[(unsigned __int64)v7[v9] >> 8] + (unsigned __int8)v7[v9]) & 2) == 0
              && v10 != 95 )
            {
              goto LABEL_232;
            }
          }
        }
      }
      v11 = v8 + 8;
      if ( (int)v8 + 8 < (unsigned int)v8 )
        Exception::throwHR(-2147024362);
      v16 = *((_QWORD *)this + 6);
      v17 = 0;
      v136 = 0;
      v128 = 0;
      v18 = *(_QWORD *)(v16 + 32);
      v19 = *(_DWORD *)(v18 + 104);
      if ( v11 > v19 )
      {
        if ( v19 )
        {
          MemFreeObject(*(void **)(v18 + 96));
          *(_QWORD *)(v18 + 96) = 0;
        }
        *(_DWORD *)(v18 + 104) = 0;
        v117 = new_array<unsigned short>(v11);
        v7 = (unsigned __int16 *)Buf1;
        v17 = v136;
        *(_QWORD *)(v18 + 96) = v117;
        *(_DWORD *)(v18 + 104) = v11;
      }
      if ( !(_DWORD)v6 )
      {
LABEL_24:
        **(_QWORD **)(v18 + 96) = v17;
        memcpy_0((void *)(*(_QWORD *)(v18 + 96) + 8LL), v7, 2 * v8);
        v21 = StringHashtable::get(*(StringHashtable **)(v18 + 88), *(const unsigned __int16 **)(v18 + 96), (int)v8 + 4);
        if ( v21 )
        {
LABEL_25:
          *((_QWORD *)v4 + 4) = v21;
          v22 = *((_DWORD *)this + 18);
          for ( i = *((_QWORD *)this + 8); v22 > 0 && i < (unsigned __int64)v2; i += 8LL )
          {
            v24 = *(_QWORD *)i;
            if ( *(_DWORD *)(*(_QWORD *)i + 4LL) == 2
              && *(_DWORD *)(v24 + 8) != 31
              && (*(unsigned __int8 (__fastcall **)(_QWORD, struct IUnknownVtbl *))(**(_QWORD **)(*(_QWORD *)(v24 + 32)
                                                                                                + 16LL)
                                                                                  + 72LL))(
                   *(_QWORD *)(*(_QWORD *)(v24 + 32) + 16LL),
                   v21[2].lpVtbl) )
            {
              goto LABEL_31;
            }
            --v22;
          }
          if ( *((_QWORD *)this + 10)
            && Attributes::containsNameDef(v20, (struct NameDef *)v21, *((struct Vector **)this + 11)) )
          {
LABEL_31:
            Exception::throwHR(-1072896684);
          }
          v12 = *v2;
          *((_QWORD *)*v2 + 5) = 0;
          if ( *((_QWORD *)this + 10) )
          {
            for ( j = 0; ; ++j )
            {
              v120 = *((_QWORD *)this + 10);
              if ( j >= *(_DWORD *)(v120 + 20) )
                break;
              v121 = *(struct AttDef **)(*(_QWORD *)(v120 + 32) + 8LL * j);
              if ( Attributes::equalNames((Attributes *)j, v12, v121) )
              {
                *((_QWORD *)v12 + 5) = v121;
                break;
              }
            }
          }
          v1 = v135;
          if ( v135 <= 0 || *((_DWORD *)v2[1] + 1) == 2 )
          {
            *((_DWORD *)v12 + 3) = 1;
          }
          else
          {
            *((_DWORD *)v12 + 3) = 0;
            *((_QWORD *)v2[1] + 5) = -1;
          }
          v13 = *v2;
          v14 = v2 + 1;
          Buf1 = 0;
          if ( *((_DWORD *)v13 + 3) )
          {
            Attributes::getDefinedAttributeValue(this, v2 + 1, v1, (struct String **)&Buf1);
            v15 = (String *)Buf1;
            goto LABEL_19;
          }
          if ( *((int *)*v14 + 10) >= 0 )
          {
            v15 = *(String **)(*(_QWORD *)(*((_QWORD *)this + 14) + 32LL) + 8LL * *((int *)*v14 + 10));
LABEL_19:
            if ( *((_DWORD *)v4 + 2) == 32
              && !(*(unsigned __int8 (__fastcall **)(String *, void *))(*(_QWORD *)v15 + 72LL))(
                    v15,
                    &XMLNames::s_cstrDefault)
              && !(*(unsigned __int8 (__fastcall **)(String *, void *))(*(_QWORD *)v15 + 72LL))(
                    v15,
                    &XMLNames::s_cstrPreserve) )
            {
              Exception::throwHR(-1072896653);
            }
            goto LABEL_20;
          }
          if ( *((_QWORD *)this + 10) )
            *(_QWORD *)v126 = *((_QWORD *)v13 + 5);
          else
            *(_QWORD *)v126 = 0;
          v131 = 0;
          v133 = 256;
          Buf1 = 0;
          if ( !is_mul_ok(0x21u, 2u) )
            Exception::throwHR(-2147024362);
          if ( g_fUseMpHeap )
            v25 = MpHeapAlloc((void *)0x21, 0x2000000Cu, 0x62u);
          else
            v25 = HeapAlloc(g_hProcessHeap, 0x2000000Cu, 0x62u);
          v26 = v25;
          if ( !v25 )
          {
            failure_tracing::record();
            Exception::raiseException((struct Exception *)&Exception::s_cexpOutOfMem);
            __debugbreak();
          }
          v27 = (__int64 *)(v2 + 1);
          LODWORD(v136) = v1;
          v129 = (struct Atom *)(v2 + 1);
          LOBYTE(Buf1) = 1;
          Value = TlsGetValue(g_dwTlsIndex);
          v29 = 4;
          if ( Value[19] )
            v29 = -1;
          v26[1] = v29;
          *((_DWORD *)v26 + 4) = 32;
          v26[3] = v26 + 4;
          Base::Base((Base *)v26);
          *v26 = &ArrayString::`vftable';
          v132 = (String *)v26;
          if ( v1 <= 0 )
          {
LABEL_48:
            v32 = *((_QWORD *)v132 + 1);
            if ( v32 != -1 && (v32 & 4) != 0 )
              *((_QWORD *)v132 + 1) = v32 & 0xFFFFFFFFFFFFFFFDuLL;
            *((_DWORD *)v132 + 4) = HIDWORD(v131);
            *(_WORD *)(*((_QWORD *)v132 + 3) + 2LL * SHIDWORD(v131)) = 0;
            v15 = v132;
            v132 = 0;
            v131 = 0;
            if ( *(_QWORD *)v126 )
            {
              switch ( (unsigned int)DTDDecl::getDataType(*(_QWORD *)v126) )
              {
                case 1u:
                  break;
                case 2u:
                case 3u:
                case 4u:
                case 5u:
                case 6u:
                case 9u:
                  if ( (int)String::indexOf(v15, 58, 0) >= 0 )
                    Exception::throwHR(-1072898036);
                  goto LABEL_269;
                default:
LABEL_269:
                  WSStringBuffer::init((WSStringBuffer *)&v131, *((_DWORD *)v15 + 4) + 1);
                  WSStringBuffer::append(&v131, v15, 4);
                  *((_DWORD *)v132 + 4) = HIDWORD(v131);
                  *(_WORD *)(*((_QWORD *)v132 + 3) + 2LL * SHIDWORD(v131)) = 0;
                  v15 = v132;
                  break;
              }
            }
            v33 = (unsigned int *)*((_QWORD *)this + 14);
            v34 = v33[6];
            v35 = v33[5] + 1;
            if ( v35 > v34 )
            {
              v123 = v33[4];
              if ( v123 )
                v124 = v34 + v123;
              else
                v124 = (unsigned int)(2 * v34 + 2);
              if ( v35 > (int)v124 )
                v124 = (unsigned int)v35;
              (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v33 + 136LL))(*((_QWORD *)this + 14), v124);
            }
            (*(void (__fastcall **)(unsigned int *, _QWORD, String *))(*(_QWORD *)v33 + 128LL))(v33, v33[5]++, v15);
            v1 = v135;
            *((_QWORD *)*v14 + 5) = *(_DWORD *)(*((_QWORD *)this + 14) + 20LL) - 1;
            goto LABEL_19;
          }
          v30 = v131;
          while ( 2 )
          {
            if ( !(_BYTE)Buf1 )
              goto LABEL_48;
            v31 = *v27;
            if ( *(_DWORD *)(v31 + 4) != 13 )
            {
              if ( *(_DWORD *)(v31 + 4) == 17 )
              {
                v115 = (struct Object *)*((_QWORD *)ContentFactory::processName(
                                                      *((ContentFactory **)this + 6),
                                                      (struct _XML_NODE_INFO *)v31,
                                                      0)
                                        + 2);
                v116 = *(Hashtable **)(*((_QWORD *)this + 5) + 104LL);
                if ( v116 )
                {
                  v137 = 0;
                  Hashtable::_get(v116, v115, &v137);
                  v118 = v137;
                  ContentFactory::checkGeneralEntity(*((ContentFactory **)this + 6), (struct Entity *)v137, v115, 1, 0);
                  if ( v118 && v118[7].lpVtbl )
                    ReplFactory::parseEntity(
                      *((ReplFactory **)this + 7),
                      (struct Entity *)v118,
                      (struct WSStringBuffer *)&v131,
                      0);
                  v30 = v131;
                }
                else
                {
                  ContentFactory::checkGeneralEntity(*((ContentFactory **)this + 6), 0, v115, 1, 0);
                  v30 = v131;
                }
                goto LABEL_47;
              }
              if ( *(_DWORD *)(v31 + 4) != 18 )
              {
                LOBYTE(Buf1) = 0;
LABEL_47:
                v27 = (__int64 *)((char *)v129 + 8);
                LODWORD(v136) = (_DWORD)v136 - 1;
                v129 = (struct Atom *)((char *)v129 + 8);
                if ( (int)v136 <= 0 )
                  goto LABEL_48;
                continue;
              }
            }
            break;
          }
          v38 = *(_DWORD *)(v31 + 8);
          v39 = 0;
          v40 = *(_DWORD *)(v31 + 24);
          if ( !v38 )
            v39 = 3;
          LODWORD(v137) = v39;
          v41 = v30 + v40 + 1;
          if ( v41 < 0 )
            Exception::throwHR(-2147024362);
          if ( (_BYTE)v133 )
          {
            v42 = v41 + 1;
            if ( v41 + 1 < (unsigned int)v41 )
              Exception::throwHR(-2147024362);
          }
          else
          {
            v42 = v30 + v40 + 1;
          }
          v43 = *(unsigned __int16 **)(v31 + 16);
          v44 = *((_DWORD *)v132 + 4);
          if ( v42 > v44 )
          {
            v92 = 2 * v44;
            if ( 2 * v44 < v44 )
              Exception::throwHR(-2147024362);
            if ( v92 + 2 < v92 )
              Exception::throwHR(-2147024362);
            if ( v42 < v92 + 2 )
              v42 = v92 + 2;
            if ( v42 > 0x7FFFFFFF )
              Exception::throwHR(-2147024362);
            v93 = ArrayString::newString(0, v42);
            v130 = v93;
            v94 = *((_QWORD *)v93 + 1);
            if ( v94 != -1 && (v94 & 4) != 0 )
              *((_QWORD *)v93 + 1) = v94 | 2;
            v30 = v131;
            if ( (_DWORD)v131 )
            {
              if ( (unsigned int)v131 > 0x7FFFFFFE || (int)v131 > *((_DWORD *)v93 + 4) )
LABEL_184:
                Exception::throw_E_OVERFLOW();
              memcpy_0(*((void **)v93 + 3), *((const void **)v132 + 3), 2LL * (int)v131);
              v30 = v131;
              v93 = v130;
            }
            v39 = (int)v137;
            v132 = v93;
          }
          if ( !v38 )
          {
            v45 = 0;
            if ( (_BYTE)v133 && !HIBYTE(v133) )
            {
              *(_WORD *)(*((_QWORD *)v132 + 3) + 2LL * v30) = 32;
              v30 = v131 + 1;
              LODWORD(v131) = v131 + 1;
            }
            v133 = 0;
            if ( v40 > 0 )
            {
              while ( 1 )
              {
                v46 = *v43++;
                --v40;
                if ( v46 == 9 )
                  goto LABEL_265;
                if ( v46 == 10 )
                  break;
                if ( v46 == 13 )
                  goto LABEL_265;
                *(_WORD *)(*((_QWORD *)v132 + 3) + 2LL * v30) = v46;
LABEL_72:
                v30 = v131 + 1;
                LODWORD(v131) = v131 + 1;
LABEL_73:
                v45 = v46;
                if ( v40 <= 0 )
                {
                  v14 = v2 + 1;
                  goto LABEL_75;
                }
              }
              if ( v45 == 13 )
                goto LABEL_73;
LABEL_265:
              *(_WORD *)(*((_QWORD *)v132 + 3) + 2LL * v30) = 32;
              goto LABEL_72;
            }
LABEL_75:
            HIDWORD(v131) = v30;
            goto LABEL_47;
          }
          v106 = v40;
          if ( v39 )
          {
            v109 = v39 - 1;
            if ( !v109 )
            {
              if ( !v43 )
                goto LABEL_47;
              if ( v40 > 0 )
              {
                do
                {
                  v114 = *v43++;
                  --v40;
                  WSStringBuffer::_collapsingAppend((WSStringBuffer *)&v131, v114, 0);
                }
                while ( v40 > 0 );
                v30 = v131;
                HIDWORD(v131) = v131;
                goto LABEL_47;
              }
              goto LABEL_75;
            }
            v110 = v109 - 1;
            if ( v110 )
            {
              if ( v110 != 2 || !v43 )
                goto LABEL_47;
              if ( v40 > 0 )
              {
                do
                {
                  v122 = *v43++;
                  --v40;
                  WSStringBuffer::_collapsingAppend((WSStringBuffer *)&v131, v122, 1);
                }
                while ( v40 > 0 );
                v30 = v131;
              }
              goto LABEL_75;
            }
            if ( HIBYTE(v133) )
            {
              if ( !v40 )
                goto LABEL_47;
              while ( (*((_BYTE *)(&g_apCharTables)[(unsigned __int64)*v43 >> 8] + (unsigned __int8)*v43) & 1) != 0 )
              {
                ++v43;
                if ( !--v40 )
                  goto LABEL_47;
              }
            }
            v111 = &v43[v40];
            do
              v112 = *--v111;
            while ( (*((_BYTE *)g_apCharTables + (unsigned __int8)v112) & 1) != 0 );
            v113 = v111 - v43;
            v106 = v113 + 1;
            if ( (_DWORD)v113 == -1 )
            {
              LOBYTE(v133) = 1;
              goto LABEL_47;
            }
          }
          if ( (_BYTE)v133 && !HIBYTE(v133) )
          {
            *(_WORD *)(*((_QWORD *)v132 + 3) + 2LL * v30) = 32;
            v30 = v131 + 1;
            LODWORD(v131) = v131 + 1;
          }
          v133 = 0;
          if ( v40 )
          {
            if ( v30 < 0 || v40 < 0 || (unsigned int)(v30 + v40) >= 0x7FFFFFFF || v30 + v40 > *((_DWORD *)v132 + 4) )
              goto LABEL_184;
            memcpy_0((void *)(*((_QWORD *)v132 + 3) + 2LL * v30), v43, 2LL * v40);
            if ( v106 )
              HIDWORD(v131) = v131 + v106;
            v30 = v40 + v131;
            LODWORD(v131) = v40 + v131;
          }
          goto LABEL_47;
        }
        v62 = (const unsigned __int16 *)Buf1;
        if ( !(_DWORD)v6 )
        {
          v137 = 0;
          if ( (int)v8 < 0 )
          {
            v63 = 0;
            v95 = Buf1;
            if ( Buf1 )
            {
              do
              {
                if ( !*v95 )
                  break;
                ++v95;
                ++v63;
              }
              while ( v63 < 0x7FFFFFFF );
            }
          }
          else
          {
            LODWORD(v63) = v8;
          }
          v64 = *(StringHashtable **)(v18 + 16);
          if ( v64 && (v65 = StringHashtable::get(v64, (const unsigned __int16 *)Buf1, v63)) != 0
            || (v65 = (struct IUnknown *)Atom::create(0, v62, v63), v88 = *(_QWORD *)(v18 + 16), Buf1 = v65, !v88) )
          {
            v66 = (struct Atom *)v65;
          }
          else
          {
            v89 = ((__int64 (__fastcall *)(struct IUnknown *))v65->lpVtbl[3].Release)(v65);
            v66 = (struct Atom *)Buf1;
            v91 = *(void (__fastcall **)(__int64, __int64, struct Atom *, __int64))(*(_QWORD *)v88 + 128LL);
LABEL_158:
            LOBYTE(v90) = 1;
            v91(v88, v89, v66, v90);
          }
          goto LABEL_97;
        }
        if ( (int)v6 >= 0 )
        {
          LODWORD(v83) = v6;
          goto LABEL_127;
        }
        v83 = 0;
        v102 = Buf1;
        v127 = 0;
        if ( Buf1 )
        {
          do
          {
            if ( !*v102 )
              break;
            ++v102;
            ++v83;
          }
          while ( v83 < 0x7FFFFFFF );
LABEL_127:
          v127 = v83;
        }
        if ( !*(_QWORD *)(v18 + 16)
          || (v137 = StringHashtable::get(*(StringHashtable **)(v18 + 16), (const unsigned __int16 *)Buf1, v83)) == 0 )
        {
          v103 = (struct IUnknown *)Atom::create(0, v62, v127);
          v137 = v103;
          Buf1 = *(void **)(v18 + 16);
          if ( Buf1 )
          {
            v104 = ((__int64 (__fastcall *)(struct IUnknown *))v103->lpVtbl[3].Release)(v103);
            LOBYTE(v105) = 1;
            (*(void (__fastcall **)(void *, __int64, struct IUnknown *, __int64))(*(_QWORD *)Buf1 + 128LL))(
              Buf1,
              v104,
              v137,
              v105);
          }
        }
        if ( (unsigned int)v8 <= (unsigned int)v6 )
        {
          v66 = (struct Atom *)Atom::s_emptyAtom;
        }
        else
        {
          v84 = (unsigned __int16 *)&v62[v6 + 1];
          Buf1 = v84;
          if ( (int)v8 - (int)v6 - 1 < 0 )
          {
            v85 = 0;
            v107 = v84;
            if ( v84 )
            {
              do
              {
                if ( !*v107 )
                  break;
                ++v107;
                ++v85;
              }
              while ( v85 < 0x7FFFFFFF );
            }
          }
          else
          {
            LODWORD(v85) = v8 - v6 - 1;
          }
          v86 = *(StringHashtable **)(v18 + 16);
          if ( v86 )
          {
            v66 = (struct Atom *)StringHashtable::get(v86, v84, v85);
            if ( v66 )
              goto LABEL_97;
            v84 = (unsigned __int16 *)Buf1;
          }
          v87 = Atom::create(0, v84, v85);
          v88 = *(_QWORD *)(v18 + 16);
          v66 = v87;
          if ( v88 )
          {
            v89 = (*(__int64 (__fastcall **)(struct Atom *))(*(_QWORD *)v87 + 88LL))(v87);
            v91 = *(void (__fastcall **)(__int64, __int64, struct Atom *, __int64))(*(_QWORD *)v88 + 128LL);
            goto LABEL_158;
          }
        }
LABEL_97:
        v68 = Name::create(v66, v128);
        if ( g_fUseMpHeap )
          v69 = (struct IUnknown *)MpHeapAlloc(v67, 0x2000000Cu, 0x28u);
        else
          v69 = (struct IUnknown *)HeapAlloc(g_hProcessHeap, 0x2000000Cu, 0x28u);
        v21 = v69;
        if ( !v69 )
        {
          failure_tracing::record();
          Exception::raiseException((struct Exception *)&Exception::s_cexpOutOfMem);
          __debugbreak();
        }
        v70 = TlsGetValue(g_dwTlsIndex);
        v71 = 4;
        if ( v70[19] )
          v71 = -1;
        v21[1].lpVtbl = (struct IUnknownVtbl *)v71;
        Base::Base((Base *)v21);
        v21->lpVtbl = (struct IUnknownVtbl *)&NameDef::`vftable';
        v72 = (__int64 *)&v21[2];
        v21[2].lpVtbl = 0;
        v21[3].lpVtbl = 0;
        v21[4].lpVtbl = 0;
        if ( v68 )
        {
          (*(void (__fastcall **)(struct Name *))(*(_QWORD *)v68 + 8LL))(v68);
          v72 = (__int64 *)&v21[2];
        }
        *v72 = (__int64)v68;
        v73 = v136;
        if ( v136 )
        {
          Buf1 = v21[4].lpVtbl;
          goto LABEL_111;
        }
        v76 = *v72;
        lpVtbl = v21[4].lpVtbl;
        Buf1 = lpVtbl;
        v73 = *(struct Atom **)(v76 + 32);
        if ( v73 )
        {
LABEL_111:
          (*(void (__fastcall **)(struct Atom *))(*(_QWORD *)v73 + 8LL))(v73);
          lpVtbl = Buf1;
        }
        v21[4].lpVtbl = (struct IUnknownVtbl *)v73;
        if ( lpVtbl )
          (*(void (__fastcall **)(void *))(*(_QWORD *)lpVtbl + 16LL))(lpVtbl);
        v78 = v137;
        v79 = v21[3].lpVtbl;
        if ( v137 )
        {
          ((void (__fastcall *)(struct IUnknown *))v137->lpVtbl->AddRef)(v137);
          v78 = v137;
        }
        v21[3].lpVtbl = (struct IUnknownVtbl *)v78;
        if ( v79 )
          (*((void (__fastcall **)(struct IUnknownVtbl *))v79->QueryInterface + 2))(v79);
        v80 = *(const unsigned __int16 **)(v18 + 96);
        v81 = *(_QWORD *)(v18 + 88);
        if ( !v80 || (_DWORD)v8 == -4 )
          v82 = (struct ArrayString *)&String::s_cstrEmpty;
        else
          v82 = ArrayString::newString(v80, (int)v8 + 4);
        (*(void (__fastcall **)(__int64, struct ArrayString *, struct IUnknown *, _QWORD))(*(_QWORD *)v81 + 128LL))(
          v81,
          v82,
          v21,
          0);
        goto LABEL_25;
      }
      if ( ((*v7 - 88) & 0xFFDF) != 0 || (unsigned int)v6 <= 2 )
        goto LABEL_55;
      if ( (_DWORD)v6 == 3 )
      {
        v108 = (_DWORD)XMLNames::s_cstrXML_pwz - *(_DWORD *)v7;
        if ( (_DWORD)XMLNames::s_cstrXML_pwz == *(_DWORD *)v7 )
          v108 = WORD2(XMLNames::s_cstrXML_pwz) - v7[2];
        if ( v108 )
          goto LABEL_55;
        v17 = (struct Atom *)XMLNames::atomURNXML;
LABEL_169:
        v75 = v17;
        v128 = v17;
      }
      else
      {
        if ( (_DWORD)v6 == 5 )
        {
          v96 = (char *)XMLNames::s_cstrXMLNS_pwz - *(_QWORD *)v7;
          if ( XMLNames::s_cstrXMLNS_pwz == *(const unsigned __int16 near *const *)v7 )
            v96 = (char *)(115LL - v7[4]);
          if ( !v96 )
          {
            v17 = (struct Atom *)XMLNames::atomURNXMLNS;
            goto LABEL_169;
          }
        }
LABEL_55:
        if ( !*(_QWORD *)(v18 + 40) )
          goto LABEL_56;
        v47 = *(_QWORD *)(v18 + 72);
        if ( v47 )
        {
          v48 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v47 + 88LL))(v47);
          v36 = (const unsigned __int16 *)Buf1;
          if ( *(_DWORD *)(v48 + 16) == (_DWORD)v6 && !memcmp_0(Buf1, *(const void **)(v48 + 24), 2 * v6) )
          {
            Entry = (struct NamespaceMgr::Entry *)(*(_QWORD *)(v18 + 48)
                                                 + 40LL * (unsigned int)(*(_DWORD *)(v18 + 80) - 1));
            goto LABEL_107;
          }
        }
        else
        {
          v36 = (const unsigned __int16 *)Buf1;
        }
        Atom = NamespaceMgr::createAtom((NamespaceMgr *)v18, 0, v36, v6);
        Entry = NamespaceMgr::findEntry((NamespaceMgr *)v18, Atom);
        if ( !Entry )
          goto LABEL_57;
LABEL_107:
        v17 = (struct Atom *)*((_QWORD *)Entry + 2);
        v75 = (struct Atom *)*((_QWORD *)Entry + 1);
        v7 = (unsigned __int16 *)Buf1;
        v128 = v75;
      }
      v136 = v17;
      if ( !v75 )
      {
LABEL_56:
        v36 = (const unsigned __int16 *)Buf1;
LABEL_57:
        v37 = String::newString(v36, v6);
        Exception::throwError(-1072898019, v37, 0, 0, v125);
      }
      goto LABEL_24;
    }
    if ( !*((_BYTE *)this + 120) )
      *((_DWORD *)this + 19) = v5;
    v50 = *((_DWORD *)v4 + 7);
    v51 = *((_QWORD *)this + 6);
    if ( v50 )
    {
      v52 = *((_DWORD *)v4 + 6);
      v53 = v50 + 1;
      v54 = (const unsigned __int16 *)*((_QWORD *)v4 + 2);
      if ( v52 > (unsigned int)v53 )
      {
        v55 = v54[v53];
        if ( (_WORD)v55 )
        {
          if ( (*((_BYTE *)(&g_apCharTables)[(unsigned __int64)v54[v53] >> 8] + (unsigned __int8)v54[v53]) & 2) == 0
            && v55 != 95 )
          {
LABEL_232:
            Exception::throwHR(-1072896763);
          }
        }
      }
      v56 = v52 + 8;
      LODWORD(Buf1) = v52 + 8;
      if ( v52 + 8 < v52 )
        Exception::throwHR(-2147024362);
    }
    else
    {
      v56 = 14;
      v54 = L"xmlns:";
      LODWORD(Buf1) = 14;
      v52 = 6;
      v50 = 5;
    }
    v57 = *(_QWORD *)(v51 + 32);
    v136 = (struct Atom *)XMLNames::atomURNXMLNS;
    v58 = *(_DWORD *)(v57 + 104);
    if ( v56 > v58 )
    {
      if ( v58 )
      {
        MemFreeObject(*(void **)(v57 + 96));
        v56 = (unsigned int)Buf1;
        *(_QWORD *)(v57 + 96) = 0;
      }
      *(_DWORD *)(v57 + 104) = 0;
      *(_QWORD *)(v57 + 96) = new_array<unsigned short>(v56);
      *(_DWORD *)(v57 + 104) = (_DWORD)Buf1;
    }
    **(_QWORD **)(v57 + 96) = v136;
    memcpy_0((void *)(*(_QWORD *)(v57 + 96) + 8LL), v54, 2LL * v52);
    v59 = *(const unsigned __int16 **)(v57 + 96);
    v60 = *(StringHashtable **)(v57 + 88);
    LODWORD(Buf1) = v52 + 4;
    v61 = StringHashtable::get(v60, v59, v52 + 4);
    if ( !v61 )
    {
      v137 = (struct IUnknown *)NamespaceMgr::createAtom((NamespaceMgr *)v57, 0, v54, v50);
      if ( v52 <= v50 )
        v97 = (struct Atom *)Atom::s_emptyAtom;
      else
        v97 = NamespaceMgr::createAtom((NamespaceMgr *)v57, 0, &v54[v50 + 1], v52 - v50 - 1);
      v98 = Name::create(v97, v136);
      v99 = NameDef::newNameDef(v98, v136, (struct Atom *)v137);
      v100 = *(_QWORD *)(v57 + 88);
      v101 = String::newString(*(const unsigned __int16 **)(v57 + 96), (int)Buf1);
      (*(void (__fastcall **)(__int64, struct String *, struct NameDef *, _QWORD))(*(_QWORD *)v100 + 128LL))(
        v100,
        v101,
        v99,
        0);
      v61 = (struct IUnknown *)v99;
    }
    v1 = v135;
    *((_QWORD *)v4 + 4) = v61;
LABEL_20:
    ++v2;
  }
}

```

## disassembly

```asm
0x180018b60  push    rbp
0x180018b62  push    rbx
0x180018b63  push    rdi
0x180018b64  push    r12
0x180018b66  push    r13
0x180018b68  push    r14
0x180018b6a  push    r15
0x180018b6c  mov     rbp, rsp
0x180018b6f  sub     rsp, 70h
0x180018b73  mov     r13d, [rcx+48h]
0x180018b77  lea     r10, __ImageBase
0x180018b7e  mov     rbx, [rcx+40h]
0x180018b82  xor     r8d, r8d
0x180018b85  mov     [rcx+4Ch], r8d
0x180018b89  mov     r14, rcx
0x180018b8c  mov     r11d, 0FFDFh
0x180018b92  mov     [rsp+70h+var_8], rsi
0x180018b97  test    r13d, r13d
0x180018b9a  jle     loc_180018CBF
0x180018ba0  mov     rsi, [rbx]
0x180018ba3  dec     r13d
0x180018ba6  mov     [rbp+arg_8], r13d
0x180018baa  cmp     dword ptr [rsi+4], 2
0x180018bae  jnz     loc_180018CB6
0x180018bb4  mov     ecx, [r14+4Ch]
0x180018bb8  lea     eax, [rcx+1]
0x180018bbb  mov     [r14+4Ch], eax
0x180018bbf  cmp     dword ptr [rsi+8], 1Fh
0x180018bc3  jz      loc_1800190D0
0x180018bc9  mov     r13d, [rsi+1Ch]
0x180018bcd  mov     r9, [rsi+10h]
0x180018bd1  mov     edi, [rsi+18h]
0x180018bd4  mov     [rbp+Buf1], r9
0x180018bd8  test    r13d, r13d
0x180018bdb  jz      short loc_180018C0A
0x180018bdd  lea     eax, [r13+1]
0x180018be1  cmp     edi, eax
0x180018be3  jbe     short loc_180018C0A
0x180018be5  movzx   edx, word ptr [r9+rax*2]
0x180018bea  test    dx, dx
0x180018bed  jz      short loc_180018C0A
0x180018bef  mov     eax, edx
0x180018bf1  movzx   ecx, dl
0x180018bf4  shr     rax, 8
0x180018bf8  mov     rax, ds:rva ?g_apCharTables@@3QBQEBEB[r10+rax*8]; uchar const * const near * const g_apCharTables ...
0x180018c00  test    byte ptr [rcx+rax], 2
0x180018c04  jz      loc_180019AA5
0x180018c0a  lea     r12d, [rdi+8]
0x180018c0e  cmp     r12d, edi
0x180018c11  jnb     loc_180018CD4
0x180018c17  mov     ecx, 80070216h; int
0x180018c1c  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x180018c22  cmp     qword ptr [r14+50h], 0
0x180018c27  jnz     loc_180019AD8
0x180018c2d  mov     rdi, [rbx]
0x180018c30  xor     r8d, r8d
0x180018c33  mov     [rdi+28h], r8
0x180018c37  cmp     [r14+50h], r8
0x180018c3b  jnz     loc_180019AF1
0x180018c41  mov     r13d, [rbp+arg_8]
0x180018c45  test    r13d, r13d
0x180018c48  jle     loc_180019B29
0x180018c4e  mov     rax, [rbx+8]
0x180018c52  cmp     dword ptr [rax+4], 2
0x180018c56  jz      loc_180019B29
0x180018c5c  mov     [rdi+0Ch], r8d
0x180018c60  mov     rax, [rbx+8]
0x180018c64  mov     qword ptr [rax+28h], 0FFFFFFFFFFFFFFFFh
0x180018c6c  mov     rdx, [rbx]
0x180018c6f  lea     rdi, [rbx+8]
0x180018c73  mov     [rbp+Buf1], r8
0x180018c77  cmp     dword ptr [rdx+0Ch], 0
0x180018c7b  jnz     loc_180019746
0x180018c81  mov     rax, [rdi]
0x180018c84  movsxd  rcx, dword ptr [rax+28h]
0x180018c88  test    ecx, ecx
0x180018c8a  js      loc_180018D97
0x180018c90  mov     rax, [r14+70h]
0x180018c94  mov     rdx, rcx
0x180018c97  mov     rcx, [rax+20h]
0x180018c9b  mov     r12, [rcx+rdx*8]
0x180018c9f  cmp     dword ptr [rsi+8], 20h ; ' '
0x180018ca3  jz      loc_18001948A
0x180018ca9  mov     r11d, 0FFDFh
0x180018caf  lea     r10, __ImageBase
0x180018cb6  add     rbx, 8
0x180018cba  jmp     loc_180018B97
0x180018cbf  mov     rsi, [rsp+70h+var_8]
0x180018cc4  add     rsp, 70h
0x180018cc8  pop     r15
0x180018cca  pop     r14
0x180018ccc  pop     r13
0x180018cce  pop     r12
0x180018cd0  pop     rdi
0x180018cd1  pop     rbx
0x180018cd2  pop     rbp
0x180018cd3  retn
0x180018cd4  mov     rax, [r14+30h]
0x180018cd8  mov     rcx, r8
0x180018cdb  mov     [rbp+arg_10], rcx
0x180018cdf  mov     [rbp+var_38], r8
0x180018ce3  mov     r15, [rax+20h]
0x180018ce7  mov     eax, [r15+68h]
0x180018ceb  cmp     r12d, eax
0x180018cee  ja      loc_180019987
0x180018cf4  test    r13d, r13d
0x180018cf7  jnz     loc_180018F54
0x180018cfd  mov     rax, [r15+60h]
0x180018d01  mov     r8, rdi
0x180018d04  add     r8, r8; Size
0x180018d07  mov     rdx, r9; Src
0x180018d0a  mov     [rax], rcx
0x180018d0d  mov     rcx, [r15+60h]
0x180018d11  add     rcx, 8; void *
0x180018d15  call    memcpy_0
0x180018d1a  mov     rdx, [r15+60h]; unsigned __int16 *
0x180018d1e  lea     r8d, [rdi+4]; int
0x180018d22  mov     rcx, [r15+58h]; this
0x180018d26  call    ?get@StringHashtable@@QEAAPEAUIUnknown@@PEBGH@Z; StringHashtable::get(ushort const *,int)
0x180018d2b  mov     r12, rax
0x180018d2e  test    rax, rax
0x180018d31  jz      loc_180019199
0x180018d37  mov     [rsi+20h], r12
0x180018d3b  mov     edi, [r14+48h]
0x180018d3f  mov     r15, [r14+40h]
0x180018d43  test    edi, edi
0x180018d45  jle     loc_180018C22
0x180018d4b  cmp     r15, rbx
0x180018d4e  jnb     loc_180018C22
0x180018d54  mov     rax, [r15]
0x180018d57  cmp     dword ptr [rax+4], 2
0x180018d5b  jnz     loc_180019ACD
0x180018d61  cmp     dword ptr [rax+8], 1Fh
0x180018d65  jz      loc_180019ACD
0x180018d6b  mov     rax, [rax+20h]
0x180018d6f  mov     rdx, [r12+10h]
0x180018d74  mov     rcx, [rax+10h]
0x180018d78  mov     rax, [rcx]
0x180018d7b  mov     rax, [rax+48h]
0x180018d7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d84  test    al, al
0x180018d86  jz      loc_180019ACD
0x180018d8c  mov     ecx, 0C00CE554h; int
0x180018d91  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x180018d97  cmp     qword ptr [r14+50h], 0
0x180018d9c  jnz     loc_180019B35
0x180018da2  mov     qword ptr [rbp+var_40], r8
0x180018da6  mov     eax, 2
0x180018dab  mov     [rbp+var_28], 0
0x180018db3  mov     ecx, 21h ; '!'; void *
0x180018db8  mov     [rbp+var_18], 100h
0x180018dbe  mul     rcx
0x180018dc1  mov     [rbp+Buf1], r8
0x180018dc5  test    rdx, rdx
0x180018dc8  jnz     loc_180018F94
0x180018dce  lea     r8, [rax+20h]; unsigned __int64
0x180018dd2  cmp     r8, rax
0x180018dd5  jb      loc_180018F9F
0x180018ddb  test    r8, r8
0x180018dde  jz      loc_180019D20
0x180018de4  cmp     cs:g_fUseMpHeap, 0
0x180018deb  mov     edx, 2000000Ch; unsigned int
0x180018df0  jz      loc_1800197C2
0x180018df6  call    ?MpHeapAlloc@@YAPEAXPEAXK_K@Z; MpHeapAlloc(void *,ulong,unsigned __int64)
0x180018dfb  mov     r15, rax
0x180018dfe  test    rax, rax
0x180018e01  jz      loc_180019D20
0x180018e07  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x180018e0d  mov     r12, rdi
0x180018e10  mov     dword ptr [rbp+arg_10], r13d
0x180018e14  mov     [rbp+var_38], rdi
0x180018e18  mov     byte ptr [rbp+Buf1], 1
0x180018e1c  call    cs:__imp_TlsGetValue
0x180018e22  mov     ecx, 4
0x180018e27  cmp     dword ptr [rax+4Ch], 0
0x180018e2b  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180018e32  cmovnz  rcx, rax
0x180018e36  lea     rax, [r15+20h]
0x180018e3a  mov     [r15+8], rcx
0x180018e3e  mov     rcx, r15; this
0x180018e41  mov     dword ptr [r15+10h], 20h ; ' '
0x180018e49  mov     [r15+18h], rax
0x180018e4d  call    ??0Base@@IEAA@XZ; Base::Base(void)
0x180018e52  lea     rax, ??_7ArrayString@@6B@; const ArrayString::`vftable'
0x180018e59  mov     [r15], rax
0x180018e5c  mov     [rbp+var_20], r15
0x180018e60  test    r13d, r13d
0x180018e63  jle     short loc_180018EAE
0x180018e65  mov     edx, dword ptr [rbp+var_28]
0x180018e68  cmp     byte ptr [rbp+Buf1], 0
0x180018e6c  jz      short loc_180018EAE
0x180018e6e  mov     r12, [r12]
0x180018e72  mov     ecx, [r12+4]
0x180018e77  sub     ecx, 0Dh
0x180018e7a  jz      loc_180018FAA
0x180018e80  sub     ecx, 4
0x180018e83  jz      loc_180019946
0x180018e89  cmp     ecx, 1
0x180018e8c  jz      loc_180018FAA
0x180018e92  mov     byte ptr [rbp+Buf1], 0
0x180018e96  mov     eax, dword ptr [rbp+arg_10]
0x180018e99  mov     r12, [rbp+var_38]
0x180018e9d  dec     eax
0x180018e9f  add     r12, 8
0x180018ea3  mov     dword ptr [rbp+arg_10], eax
0x180018ea6  mov     [rbp+var_38], r12
0x180018eaa  test    eax, eax
0x180018eac  jg      short loc_180018E68
0x180018eae  mov     rcx, [rbp+var_20]
0x180018eb2  mov     rax, [rcx+8]
0x180018eb6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180018eba  jz      short loc_180018EC8
0x180018ebc  test    al, 4
0x180018ebe  jz      short loc_180018EC8
0x180018ec0  and     rax, 0FFFFFFFFFFFFFFFDh
0x180018ec4  mov     [rcx+8], rax
0x180018ec8  mov     rax, [rbp+var_20]
0x180018ecc  xor     r15d, r15d
0x180018ecf  mov     edx, dword ptr [rbp+var_28+4]
0x180018ed2  mov     [rax+10h], edx
0x180018ed5  mov     rax, [rbp+var_20]
0x180018ed9  movsxd  r8, dword ptr [rbp+var_28+4]
0x180018edd  mov     rdx, [rax+18h]
0x180018ee1  mov     rax, qword ptr [rbp+var_40]
0x180018ee5  mov     [rdx+r8*2], r15w
0x180018eea  mov     r12, [rbp+var_20]
0x180018eee  mov     [rbp+var_20], r15
0x180018ef2  mov     [rbp+var_28], r15
0x180018ef6  test    rax, rax
0x180018ef9  jnz     loc_180019C56
0x180018eff  mov     r15, [r14+70h]; jumptable 0000000180019C78 case 1
0x180018f03  mov     r13, r12
0x180018f06  mov     ecx, [r15+14h]
0x180018f0a  mov     eax, [r15+18h]
0x180018f0e  inc     ecx
0x180018f10  cmp     ecx, eax
0x180018f12  jg      loc_180019CDF
0x180018f18  mov     rax, [r15]
0x180018f1b  mov     r8, r13
0x180018f1e  mov     edx, [r15+14h]
0x180018f22  mov     rcx, r15
0x180018f25  mov     rax, [rax+80h]
0x180018f2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f31  inc     dword ptr [r15+14h]
0x180018f35  mov     rax, [r14+70h]
0x180018f39  mov     r13d, [rbp+arg_8]
0x180018f3d  mov     ecx, [rax+14h]
0x180018f40  mov     rax, [rdi]
0x180018f43  dec     ecx
0x180018f45  movsxd  rdx, ecx
0x180018f48  mov     [rax+28h], rdx
0x180018f4c  xor     r8d, r8d
0x180018f4f  jmp     loc_180018C9F
0x180018f54  movzx   eax, word ptr [r9]
0x180018f58  sub     ax, 58h ; 'X'
0x180018f5c  test    r11w, ax
0x180018f60  jz      loc_1800195E9
0x180018f66  cmp     qword ptr [r15+28h], 0
0x180018f6b  jnz     loc_180019078
0x180018f71  mov     r12, [rbp+Buf1]
0x180018f75  mov     edx, r13d; int
0x180018f78  mov     rcx, r12; Src
0x180018f7b  call    ?newString@String@@SAPEAV1@PEBGH@Z; String::newString(ushort const *,int)
0x180018f80  mov     rdx, rax; struct String *
0x180018f83  xor     r9d, r9d; struct String *
0x180018f86  xor     r8d, r8d; struct String *
0x180018f89  mov     ecx, 0C00CE01Dh; int
0x180018f8e  call    ?throwError@Exception@@SAXJPEAVString@@000@Z; Exception::throwError(long,String *,String *,String *,String *)
0x180018f94  mov     ecx, 80070216h; int
0x180018f99  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x180018f9f  mov     ecx, 80070216h; int
0x180018fa4  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x180018faa  mov     r13d, [r12+8]
0x180018faf  xor     r9d, r9d
0x180018fb2  mov     r15d, [r12+18h]
0x180018fb7  test    r13d, r13d
0x180018fba  mov     eax, 3
0x180018fbf  cmovz   r9d, eax
0x180018fc3  mov     dword ptr [rbp+arg_18], r9d
0x180018fc7  lea     eax, [r15+1]
0x180018fcb  add     eax, edx
0x180018fcd  js      loc_180019394
0x180018fd3  cmp     byte ptr [rbp+var_18], 0
0x180018fd7  jnz     loc_180019A23
0x180018fdd  mov     ecx, eax
0x180018fdf  mov     rax, [rbp+var_20]
0x180018fe3  mov     r12, [r12+10h]
0x180018fe8  mov     r8d, [rax+10h]
0x180018fec  cmp     ecx, r8d
0x180018fef  ja      loc_1800194D3
0x180018ff5  test    r13d, r13d
0x180018ff8  jnz     loc_180019761
0x180018ffe  xor     r9d, r9d
0x180019001  cmp     byte ptr [rbp+var_18], r9b
0x180019005  jnz     loc_180019C0F
0x18001900b  mov     [rbp+var_18], r9w
0x180019010  test    r15d, r15d
0x180019013  jle     short loc_180019070
0x180019015  mov     edi, 20h ; ' '
0x18001901a  nop     word ptr [rax+rax+00h]
  ... truncated ...
```
