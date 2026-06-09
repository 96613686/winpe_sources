# SchemaDatatype::classInit(void)

- ea: `0x1801493cc`
- end: `0x18014a52e`
- name: `?classInit@SchemaDatatype@@SAXXZ`
- size: `4450`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `54`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180061950`

## callees

- `0x1800101e4`
- `0x180015a80`
- `0x180019e20`
- `0x18002a3a0`
- `0x1800307d4`
- `0x18005ed7c`
- `0x180060074`
- `0x18009fefc`
- `0x1800a3c08`
- `0x1800ab9c4`
- `0x1800c1b70`
- `0x1800c5a14`
- `0x1800c5dc0`
- `0x1800c5e04`
- `0x1800c5e48`
- `0x1800c5e8c`
- `0x1800d82c0`
- `0x180145be4`
- `0x180145c14`
- `0x180145c44`
- `0x180145c84`
- `0x180145cb8`
- `0x180145cec`
- `0x180145d20`
- `0x180145d54`
- `0x180145d88`
- `0x180145dbc`
- `0x180145dfc`
- `0x180145e3c`
- `0x180145e7c`
- `0x180145eb0`
- `0x180145ee4`
- `0x180145f18`
- `0x180145f4c`
- `0x180145f80`
- `0x180145fb4`
- `0x180145ff4`
- `0x180146028`
- `0x180146068`
- `0x1801460a8`
- `0x1801460dc`
- `0x180146110`
- `0x180146144`
- `0x180146178`
- `0x1801461ac`
- `0x180146234`
- `0x18014625c`
- `0x180146290`
- `0x1801462c4`
- `0x1801462f8`

## string_xrefs

- `0x18014a138`: `token`
- `0x180149d1f`: `NMTOKEN`
- `0x18014a4a9`: `NMTOKENS`
- `0x18014949f`: `anyURI`

## pseudocode

```c
void SchemaDatatype::classInit(void)
{
  Datatype_anyType *v0; // rax
  IUnknown **v1; // rax
  IUnknown **v2; // rdi
  String *v3; // rbx
  Datatype_anyURI *v4; // rax
  IUnknown **v5; // rax
  IUnknown **v6; // rdi
  String *v7; // rbx
  Datatype_base64Binary *v8; // rax
  IUnknown **v9; // rax
  IUnknown **v10; // rdi
  String *v11; // rbx
  Datatype_boolean *v12; // rax
  IUnknown **v13; // rax
  IUnknown **v14; // rdi
  String *v15; // rbx
  Datatype_byte *v16; // rax
  IUnknown **v17; // rax
  IUnknown **v18; // rdi
  String *v19; // rbx
  Datatype_date *v20; // rax
  IUnknown **v21; // rax
  IUnknown **v22; // rdi
  String *v23; // rbx
  Datatype_dateTime *v24; // rax
  IUnknown **v25; // rax
  IUnknown **v26; // rdi
  String *v27; // rbx
  Datatype_day *v28; // rax
  IUnknown **v29; // rax
  IUnknown **v30; // rdi
  String *v31; // rbx
  Datatype_double *v32; // rax
  IUnknown **v33; // rax
  IUnknown **v34; // rdi
  String *v35; // rbx
  Datatype_duration *v36; // rax
  IUnknown **v37; // rax
  IUnknown **v38; // rdi
  String *v39; // rbx
  Datatype_ENTITY *v40; // rax
  IUnknown **v41; // rax
  IUnknown **v42; // rdi
  String *v43; // rbx
  Datatype_float *v44; // rax
  IUnknown **v45; // rax
  IUnknown **v46; // rdi
  String *v47; // rbx
  Datatype_hexBinary *v48; // rax
  IUnknown **v49; // rax
  IUnknown **v50; // rdi
  String *v51; // rbx
  Datatype_ID *v52; // rax
  IUnknown **v53; // rax
  IUnknown **v54; // rdi
  String *v55; // rbx
  Datatype_IDREF *v56; // rax
  IUnknown **v57; // rax
  IUnknown **v58; // rdi
  String *v59; // rbx
  Datatype_int *v60; // rax
  IUnknown **v61; // rax
  IUnknown **v62; // rdi
  String *v63; // rbx
  Datatype_integer *v64; // rax
  IUnknown **v65; // rax
  IUnknown **v66; // rdi
  String *v67; // rbx
  Datatype_language *v68; // rax
  IUnknown **v69; // rax
  IUnknown **v70; // rdi
  String *v71; // rbx
  Datatype_long *v72; // rax
  IUnknown **v73; // rax
  IUnknown **v74; // rdi
  String *v75; // rbx
  Datatype_month *v76; // rax
  IUnknown **v77; // rax
  IUnknown **v78; // rdi
  String *v79; // rbx
  Datatype_monthDay *v80; // rax
  IUnknown **v81; // rax
  IUnknown **v82; // rdi
  String *v83; // rbx
  Datatype_Name *v84; // rax
  IUnknown **v85; // rax
  IUnknown **v86; // rdi
  String *v87; // rbx
  Datatype_NCName *v88; // rax
  IUnknown **v89; // rax
  IUnknown **v90; // rdi
  String *v91; // rbx
  Datatype_negativeInteger *v92; // rax
  IUnknown **v93; // rax
  IUnknown **v94; // rdi
  String *v95; // rbx
  Datatype_NMTOKEN *v96; // rax
  IUnknown **v97; // rax
  IUnknown **v98; // rdi
  String *v99; // rbx
  Datatype_nonNegativeInteger *v100; // rax
  IUnknown **v101; // rax
  IUnknown **v102; // rdi
  String *v103; // rbx
  Datatype_nonPositiveInteger *v104; // rax
  IUnknown **v105; // rax
  IUnknown **v106; // rdi
  String *v107; // rbx
  Datatype_normalizedString *v108; // rax
  IUnknown **v109; // rax
  IUnknown **v110; // rdi
  String *v111; // rbx
  Datatype_NOTATION *v112; // rax
  IUnknown **v113; // rax
  IUnknown **v114; // rdi
  String *v115; // rbx
  Datatype_decimal *v116; // rax
  IUnknown **v117; // rax
  IUnknown **v118; // rdi
  String *v119; // rbx
  Datatype_positiveInteger *v120; // rax
  IUnknown **v121; // rax
  IUnknown **v122; // rdi
  String *v123; // rbx
  Datatype_QName *v124; // rax
  IUnknown **v125; // rax
  IUnknown **v126; // rdi
  String *v127; // rbx
  Datatype_short *v128; // rax
  IUnknown **v129; // rax
  IUnknown **v130; // rdi
  String *v131; // rbx
  Datatype_string *v132; // rax
  IUnknown **v133; // rax
  IUnknown **v134; // rdi
  String *v135; // rbx
  Datatype_time *v136; // rax
  IUnknown **v137; // rax
  IUnknown **v138; // rdi
  String *v139; // rbx
  Datatype_token *v140; // rax
  IUnknown **v141; // rax
  IUnknown **v142; // rdi
  String *v143; // rbx
  Datatype_unsignedByte *v144; // rax
  IUnknown **v145; // rax
  IUnknown **v146; // rdi
  String *v147; // rbx
  Datatype_unsignedInt *v148; // rax
  IUnknown **v149; // rax
  IUnknown **v150; // rdi
  String *v151; // rbx
  Datatype_unsignedLong *v152; // rax
  IUnknown **v153; // rax
  IUnknown **v154; // rdi
  String *v155; // rbx
  Datatype_unsignedShort *v156; // rax
  IUnknown **v157; // rax
  IUnknown **v158; // rdi
  String *v159; // rbx
  Datatype_year *v160; // rax
  IUnknown **v161; // rax
  IUnknown **v162; // rdi
  String *v163; // rbx
  Datatype_yearMonth *v164; // rax
  IUnknown **v165; // rax
  IUnknown **v166; // rdi
  String *v167; // rbx
  SchemaDatatype *v168; // rax
  String *v169; // rbx
  SchemaDatatype *v170; // rax
  String *v171; // rbx
  SchemaDatatype *v172; // rax
  String *v173; // rbx
  _reference<String> s; // [rsp+40h] [rbp+8h] BYREF
  MutexLock lock; // [rsp+48h] [rbp+10h] BYREF

  if ( !SchemaDatatype::c_NMTOKENS._p )
  {
    MutexLock::MutexLock(&lock, g_pMutex);
    s._p = 0;
    if ( !SchemaDatatype::c_NMTOKENS._p )
    {
      v0 = (Datatype_anyType *)_MemAlloc(0xB8u, 0xCu);
      Datatype_anyType::Datatype_anyType(v0);
      v2 = v1;
      assign(&SchemaDatatype::c_anySimpleType._p, v1);
      v3 = String::newConstString(L"anySimpleType");
      release(&s._p);
      s._p = v3;
      assign(v2 + 8, v3);
      ((void (__fastcall *)(IUnknown **))(*v2)[2].__vftable)(v2);
      v4 = (Datatype_anyURI *)_MemAlloc(0xB8u, 0xCu);
      Datatype_anyURI::Datatype_anyURI(v4);
      v6 = v5;
      assign(&SchemaDatatype::c_anyURI._p, v5);
      v7 = String::newConstString(L"anyURI");
      release(&s._p);
      s._p = v7;
      assign(v6 + 8, v7);
      ((void (__fastcall *)(IUnknown **))(*v6)[2].__vftable)(v6);
      v8 = (Datatype_base64Binary *)_MemAlloc(0xB8u, 0xCu);
      Datatype_base64Binary::Datatype_base64Binary(v8);
      v10 = v9;
      assign(&SchemaDatatype::c_base64Binary._p, v9);
      v11 = String::newConstString(L"base64Binary");
      release(&s._p);
      s._p = v11;
      assign(v10 + 8, v11);
      ((void (__fastcall *)(IUnknown **))(*v10)[2].__vftable)(v10);
      v12 = (Datatype_boolean *)_MemAlloc(0xB8u, 0xCu);
      Datatype_boolean::Datatype_boolean(v12);
      v14 = v13;
      assign(&SchemaDatatype::c_boolean._p, v13);
      v15 = String::newConstString(L"boolean");
      release(&s._p);
      s._p = v15;
      assign(v14 + 8, v15);
      ((void (__fastcall *)(IUnknown **))(*v14)[2].__vftable)(v14);
      v16 = (Datatype_byte *)_MemAlloc(0xB8u, 0xCu);
      Datatype_byte::Datatype_byte(v16);
      v18 = v17;
      assign(&SchemaDatatype::c_byte._p, v17);
      v19 = String::newConstString(L"byte");
      release(&s._p);
      s._p = v19;
      assign(v18 + 8, v19);
      ((void (__fastcall *)(IUnknown **))(*v18)[2].__vftable)(v18);
      v20 = (Datatype_date *)_MemAlloc(0xC0u, 0xCu);
      Datatype_date::Datatype_date(v20);
      v22 = v21;
      assign(&SchemaDatatype::c_date._p, v21);
      v23 = String::newConstString(L"date");
      release(&s._p);
      s._p = v23;
      assign(v22 + 8, v23);
      ((void (__fastcall *)(IUnknown **))(*v22)[2].__vftable)(v22);
      v24 = (Datatype_dateTime *)_MemAlloc(0xC0u, 0xCu);
      Datatype_dateTime::Datatype_dateTime(v24);
      v26 = v25;
      assign(&SchemaDatatype::c_dateTime._p, v25);
      v27 = String::newConstString(L"dateTime");
      release(&s._p);
      s._p = v27;
      assign(v26 + 8, v27);
      ((void (__fastcall *)(IUnknown **))(*v26)[2].__vftable)(v26);
      v28 = (Datatype_day *)_MemAlloc(0xC0u, 0xCu);
      Datatype_day::Datatype_day(v28);
      v30 = v29;
      assign(&SchemaDatatype::c_day._p, v29);
      v31 = String::newConstString(L"gDay");
      release(&s._p);
      s._p = v31;
      assign(v30 + 8, v31);
      ((void (__fastcall *)(IUnknown **))(*v30)[2].__vftable)(v30);
      v32 = (Datatype_double *)_MemAlloc(0xB8u, 0xCu);
      Datatype_double::Datatype_double(v32);
      v34 = v33;
      assign(&SchemaDatatype::c_double._p, v33);
      v35 = String::newConstString(L"double");
      release(&s._p);
      s._p = v35;
      assign(v34 + 8, v35);
      ((void (__fastcall *)(IUnknown **))(*v34)[2].__vftable)(v34);
      v36 = (Datatype_duration *)_MemAlloc(0xB8u, 0xCu);
      Datatype_duration::Datatype_duration(v36);
      v38 = v37;
      assign(&SchemaDatatype::c_duration._p, v37);
      v39 = String::newConstString(L"duration");
      release(&s._p);
      s._p = v39;
      assign(v38 + 8, v39);
      ((void (__fastcall *)(IUnknown **))(*v38)[2].__vftable)(v38);
      v40 = (Datatype_ENTITY *)_MemAlloc(0xC0u, 0xCu);
      Datatype_ENTITY::Datatype_ENTITY(v40);
      v42 = v41;
      assign(&SchemaDatatype::c_ENTITY._p, v41);
      v43 = String::newConstString(L"ENTITY");
      release(&s._p);
      s._p = v43;
      assign(v42 + 8, v43);
      ((void (__fastcall *)(IUnknown **))(*v42)[2].__vftable)(v42);
      v44 = (Datatype_float *)_MemAlloc(0xB8u, 0xCu);
      Datatype_float::Datatype_float(v44);
      v46 = v45;
      assign(&SchemaDatatype::c_float._p, v45);
      v47 = String::newConstString(L"float");
      release(&s._p);
      s._p = v47;
      assign(v46 + 8, v47);
      ((void (__fastcall *)(IUnknown **))(*v46)[2].__vftable)(v46);
      v48 = (Datatype_hexBinary *)_MemAlloc(0xB8u, 0xCu);
      Datatype_hexBinary::Datatype_hexBinary(v48);
      v50 = v49;
      assign(&SchemaDatatype::c_hexBinary._p, v49);
      v51 = String::newConstString(L"hexBinary");
      release(&s._p);
      s._p = v51;
      assign(v50 + 8, v51);
      ((void (__fastcall *)(IUnknown **))(*v50)[2].__vftable)(v50);
      v52 = (Datatype_ID *)_MemAlloc(0xC0u, 0xCu);
      Datatype_ID::Datatype_ID(v52);
      v54 = v53;
      assign(&SchemaDatatype::c_ID._p, v53);
      v55 = String::newConstString(L"ID");
      release(&s._p);
      s._p = v55;
      assign(v54 + 8, v55);
      ((void (__fastcall *)(IUnknown **))(*v54)[2].__vftable)(v54);
      v56 = (Datatype_IDREF *)_MemAlloc(0xC0u, 0xCu);
      Datatype_IDREF::Datatype_IDREF(v56);
      v58 = v57;
      assign(&SchemaDatatype::c_IDREF._p, v57);
      v59 = String::newConstString(L"IDREF");
      release(&s._p);
      s._p = v59;
      assign(v58 + 8, v59);
      ((void (__fastcall *)(IUnknown **))(*v58)[2].__vftable)(v58);
      v60 = (Datatype_int *)_MemAlloc(0xB8u, 0xCu);
      Datatype_int::Datatype_int(v60);
      v62 = v61;
      assign(&SchemaDatatype::c_int._p, v61);
      v63 = String::newConstString(L"int");
      release(&s._p);
      s._p = v63;
      assign(v62 + 8, v63);
      ((void (__fastcall *)(IUnknown **))(*v62)[2].__vftable)(v62);
      v64 = (Datatype_integer *)_MemAlloc(0xB8u, 0xCu);
      Datatype_integer::Datatype_integer(v64);
      v66 = v65;
      assign(&SchemaDatatype::c_integer._p, v65);
      v67 = String::newConstString(L"integer");
      release(&s._p);
      s._p = v67;
      assign(v66 + 8, v67);
      ((void (__fastcall *)(IUnknown **))(*v66)[2].__vftable)(v66);
      v68 = (Datatype_language *)_MemAlloc(0xC0u, 0xCu);
      Datatype_language::Datatype_language(v68);
      v70 = v69;
      assign(&SchemaDatatype::c_language._p, v69);
      v71 = String::newConstString(L"language");
      release(&s._p);
      s._p = v71;
      assign(v70 + 8, v71);
      ((void (__fastcall *)(IUnknown **))(*v70)[2].__vftable)(v70);
      v72 = (Datatype_long *)_MemAlloc(0xB8u, 0xCu);
      Datatype_long::Datatype_long(v72);
      v74 = v73;
      assign(&SchemaDatatype::c_long._p, v73);
      v75 = String::newConstString(L"long");
      release(&s._p);
      s._p = v75;
      assign(v74 + 8, v75);
      ((void (__fastcall *)(IUnknown **))(*v74)[2].__vftable)(v74);
      v76 = (Datatype_month *)_MemAlloc(0xC0u, 0xCu);
      Datatype_month::Datatype_month(v76);
      v78 = v77;
      assign(&SchemaDatatype::c_month._p, v77);
      v79 = String::newConstString(L"gMonth");
      release(&s._p);
      s._p = v79;
      assign(v78 + 8, v79);
      ((void (__fastcall *)(IUnknown **))(*v78)[2].__vftable)(v78);
      v80 = (Datatype_monthDay *)_MemAlloc(0xC0u, 0xCu);
      Datatype_monthDay::Datatype_monthDay(v80);
      v82 = v81;
      assign(&SchemaDatatype::c_monthDay._p, v81);
      v83 = String::newConstString(L"gMonthDay");
      release(&s._p);
      s._p = v83;
      assign(v82 + 8, v83);
      ((void (__fastcall *)(IUnknown **))(*v82)[2].__vftable)(v82);
      v84 = (Datatype_Name *)_MemAlloc(0xC0u, 0xCu);
      Datatype_Name::Datatype_Name(v84, HT_Name);
      v86 = v85;
      assign(&SchemaDatatype::c_Name._p, v85);
      v87 = String::newConstString(L"Name");
      release(&s._p);
      s._p = v87;
      assign(v86 + 8, v87);
      ((void (__fastcall *)(IUnknown **))(*v86)[2].__vftable)(v86);
      v88 = (Datatype_NCName *)_MemAlloc(0xC0u, 0xCu);
      Datatype_NCName::Datatype_NCName(v88, HT_NCName);
      v90 = v89;
      assign(&SchemaDatatype::c_NCName._p, v89);
      v91 = String::newConstString(L"NCName");
      release(&s._p);
      s._p = v91;
      assign(v90 + 8, v91);
      ((void (__fastcall *)(IUnknown **))(*v90)[2].__vftable)(v90);
      v92 = (Datatype_negativeInteger *)_MemAlloc(0xB8u, 0xCu);
      Datatype_negativeInteger::Datatype_negativeInteger(v92);
      v94 = v93;
      assign(&SchemaDatatype::c_negativeInteger._p, v93);
      v95 = String::newConstString(L"negativeInteger");
      release(&s._p);
      s._p = v95;
      assign(v94 + 8, v95);
      ((void (__fastcall *)(IUnknown **))(*v94)[2].__vftable)(v94);
      v96 = (Datatype_NMTOKEN *)_MemAlloc(0xC0u, 0xCu);
      Datatype_NMTOKEN::Datatype_NMTOKEN(v96);
      v98 = v97;
      assign(&SchemaDatatype::c_NMTOKEN._p, v97);
      v99 = String::newConstString(L"NMTOKEN");
      release(&s._p);
      s._p = v99;
      assign(v98 + 8, v99);
      ((void (__fastcall *)(IUnknown **))(*v98)[2].__vftable)(v98);
      v100 = (Datatype_nonNegativeInteger *)_MemAlloc(0xB8u, 0xCu);
      Datatype_nonNegativeInteger::Datatype_nonNegativeInteger(v100);
      v102 = v101;
      assign(&SchemaDatatype::c_nonNegativeInteger._p, v101);
      v103 = String::newConstString(L"nonNegativeInteger");
      release(&s._p);
      s._p = v103;
      assign(v102 + 8, v103);
      ((void (__fastcall *)(IUnknown **))(*v102)[2].__vftable)(v102);
      v104 = (Datatype_nonPositiveInteger *)_MemAlloc(0xB8u, 0xCu);
      Datatype_nonPositiveInteger::Datatype_nonPositiveInteger(v104);
      v106 = v105;
      assign(&SchemaDatatype::c_nonPositiveInteger._p, v105);
      v107 = String::newConstString(L"nonPositiveInteger");
      release(&s._p);
      s._p = v107;
      assign(v106 + 8, v107);
      ((void (__fastcall *)(IUnknown **))(*v106)[2].__vftable)(v106);
      v108 = (Datatype_normalizedString *)_MemAlloc(0xC0u, 0xCu);
      Datatype_normalizedString::Datatype_normalizedString(v108, HT_normalizedString);
      v110 = v109;
      assign(&SchemaDatatype::c_normalizedString._p, v109);
      v111 = String::newConstString(L"normalizedString");
      release(&s._p);
      s._p = v111;
      assign(v110 + 8, v111);
      ((void (__fastcall *)(IUnknown **))(*v110)[2].__vftable)(v110);
      v112 = (Datatype_NOTATION *)_MemAlloc(0xB8u, 0xCu);
      Datatype_NOTATION::Datatype_NOTATION(v112);
      v114 = v113;
      assign(&SchemaDatatype::c_NOTATION._p, v113);
      v115 = String::newConstString(L"NOTATION");
      release(&s._p);
      s._p = v115;
      assign(v114 + 8, v115);
      ((void (__fastcall *)(IUnknown **))(*v114)[2].__vftable)(v114);
      v116 = (Datatype_decimal *)_MemAlloc(0xB8u, 0xCu);
      Datatype_decimal::Datatype_decimal(v116);
      v118 = v117;
      assign(&SchemaDatatype::c_decimal._p, v117);
      v119 = String::newConstString(L"decimal");
      release(&s._p);
      s._p = v119;
      assign(v118 + 8, v119);
      ((void (__fastcall *)(IUnknown **))(*v118)[2].__vftable)(v118);
      v120 = (Datatype_positiveInteger *)_MemAlloc(0xB8u, 0xCu);
      Datatype_positiveInteger::Datatype_positiveInteger(v120);
      v122 = v121;
      assign(&SchemaDatatype::c_positiveInteger._p, v121);
      v123 = String::newConstString(L"positiveInteger");
      release(&s._p);
      s._p = v123;
      assign(v122 + 8, v123);
      ((void (__fastcall *)(IUnknown **))(*v122)[2].__vftable)(v122);
      v124 = (Datatype_QName *)_MemAlloc(0xB8u, 0xCu);
      Datatype_QName::Datatype_QName(v124);
      v126 = v125;
      assign(&SchemaDatatype::c_QName._p, v125);
      v127 = String::newConstString(L"QName");
      release(&s._p);
      s._p = v127;
      assign(v126 + 8, v127);
      ((void (__fastcall *)(IUnknown **))(*v126)[2].__vftable)(v126);
      v128 = (Datatype_short *)_MemAlloc(0xB8u, 0xCu);
      Datatype_short::Datatype_short(v128);
      v130 = v129;
      assign(&SchemaDatatype::c_short._p, v129);
      v131 = String::newConstString(L"short");
      release(&s._p);
      s._p = v131;
      assign(v130 + 8, v131);
      ((void (__fastcall *)(IUnknown **))(*v130)[2].__vftable)(v130);
      v132 = (Datatype_string *)_MemAlloc(0xC0u, 0xCu);
      Datatype_string::Datatype_string(v132, HT_string);
      v134 = v133;
      assign(&SchemaDatatype::c_string._p, v133);
      v135 = String::newConstString(L"string");
      release(&s._p);
      s._p = v135;
      assign(v134 + 8, v135);
      ((void (__fastcall *)(IUnknown **))(*v134)[2].__vftable)(v134);
      v136 = (Datatype_time *)_MemAlloc(0xC0u, 0xCu);
      Datatype_time::Datatype_time(v136);
      v138 = v137;
      assign(&SchemaDatatype::c_time._p, v137);
      v139 = String::newConstString(L"time");
      release(&s._p);
      s._p = v139;
      assign(v138 + 8, v139);
      ((void (__fastcall *)(IUnknown **))(*v138)[2].__vftable)(v138);
      v140 = (Datatype_token *)_MemAlloc(0xC0u, 0xCu);
      Datatype_token::Datatype_token(v140, HT_token);
      v142 = v141;
      assign(&SchemaDatatype::c_token._p, v141);
      v143 = String::newConstString(L"token");
      release(&s._p);
      s._p = v143;
      assign(v142 + 8, v143);
      ((void (__fastcall *)(IUnknown **))(*v142)[2].__vftable)(v142);
      v144 = (Datatype_unsignedByte *)_MemAlloc(0xB8u, 0xCu);
      Datatype_unsignedByte::Datatype_unsignedByte(v144);
      v146 = v145;
      assign(&SchemaDatatype::c_unsignedByte._p, v145);
      v147 = String::newConstString(L"unsignedByte");
      release(&s._p);
      s._p = v147;
      assign(v146 + 8, v147);
      ((void (__fastcall *)(IUnknown **))(*v146)[2].__vftable)(v146);
      v148 = (Datatype_unsignedInt *)_MemAlloc(0xB8u, 0xCu);
      Datatype_unsignedInt::Datatype_unsignedInt(v148);
      v150 = v149;
      assign(&SchemaDatatype::c_unsignedInt._p, v149);
      v151 = String::newConstString(L"unsignedInt");
      release(&s._p);
      s._p = v151;
      assign(v150 + 8, v151);
      ((void (__fastcall *)(IUnknown **))(*v150)[2].__vftable)(v150);
      v152 = (Datatype_unsignedLong *)_MemAlloc(0xB8u, 0xCu);
      Datatype_unsignedLong::Datatype_unsignedLong(v152);
      v154 = v153;
      assign(&SchemaDatatype::c_unsignedLong._p, v153);
      v155 = String::newConstString(L"unsignedLong");
      release(&s._p);
      s._p = v155;
      assign(v154 + 8, v155);
      ((void (__fastcall *)(IUnknown **))(*v154)[2].__vftable)(v154);
      v156 = (Datatype_unsignedShort *)_MemAlloc(0xB8u, 0xCu);
      Datatype_unsignedShort::Datatype_unsignedShort(v156);
      v158 = v157;
      assign(&SchemaDatatype::c_unsignedShort._p, v157);
      v159 = String::newConstString(L"unsignedShort");
      release(&s._p);
      s._p = v159;
      assign(v158 + 8, v159);
      ((void (__fastcall *)(IUnknown **))(*v158)[2].__vftable)(v158);
      v160 = (Datatype_year *)_MemAlloc(0xC0u, 0xCu);
      Datatype_year::Datatype_year(v160);
      v162 = v161;
      assign(&SchemaDatatype::c_year._p, v161);
      v163 = String::newConstString(L"gYear");
      release(&s._p);
      s._p = v163;
      assign(v162 + 8, v163);
      ((void (__fastcall *)(IUnknown **))(*v162)[2].__vftable)(v162);
      v164 = (Datatype_yearMonth *)_MemAlloc(0xC0u, 0xCu);
      Datatype_yearMonth::Datatype_yearMonth(v164);
      v166 = v165;
      assign(&SchemaDatatype::c_yearMonth._p, v165);
      v167 = String::newConstString(L"gYearMonth");
      release(&s._p);
      s._p = v167;
      assign(v166 + 8, v167);
      ((void (__fastcall *)(IUnknown **))(*v166)[2].__vftable)(v166);
      v168 = SchemaDatatype::DeriveByList(SchemaDatatype::c_ENTITY._p, 1, 0);
      assign(&SchemaDatatype::c_ENTITIES._p, v168);
      SchemaDatatype::c_ENTITIES._p->Release(SchemaDatatype::c_ENTITIES._p);
      v169 = String::newConstString(L"ENTITIES");
      release(&s._p);
      s._p = v169;
      assign(&SchemaDatatype::c_ENTITIES._p->_name._p, v169);
      v170 = SchemaDatatype::DeriveByList(SchemaDatatype::c_IDREF._p, 1, 0);
      assign(&SchemaDatatype::c_IDREFS._p, v170);
      SchemaDatatype::c_IDREFS._p->Release(SchemaDatatype::c_IDREFS._p);
      v171 = String::newConstString(L"IDREFS");
      release(&s._p);
      s._p = v171;
      assign(&SchemaDatatype::c_IDREFS._p->_name._p, v171);
      v172 = SchemaDatatype::DeriveByList(SchemaDatatype::c_NMTOKEN._p, 1, 0);
      assign(&SchemaDatatype::c_NMTOKENS._p, v172);
      SchemaDatatype::c_NMTOKENS._p->Release(SchemaDatatype::c_NMTOKENS._p);
      v173 = String::newConstString(L"NMTOKENS");
      release(&s._p);
      s._p = v173;
      assign(&SchemaDatatype::c_NMTOKENS._p->_name._p, v173);
    }
    release(&s._p);
    MutexLock::Release(&lock);
  }
}

```

## disassembly

```asm
0x1801493cc  mov     [rsp+arg_10], rbx
0x1801493d1  mov     [rsp+arg_18], rdi
0x1801493d6  push    r12
0x1801493d8  push    r14
0x1801493da  push    r15
0x1801493dc  sub     rsp, 20h
0x1801493e0  xor     ebx, ebx
0x1801493e2  cmp     cs:?c_NMTOKENS@SchemaDatatype@@2V?$_reference@VSchemaDatatype@@@@A._p, rbx; _reference<SchemaDatatype> SchemaDatatype::c_NMTOKENS ...
0x1801493e9  jnz     loc_18014A4EF
0x1801493ef  mov     rdx, cs:?g_pMutex@@3PEAVCSMutex@@EA; pMutex
0x1801493f6  lea     rcx, [rsp+38h+lock]; this
0x1801493fb  call    ??0MutexLock@@QEAA@PEAVMutex@@@Z; MutexLock::MutexLock(Mutex *)
0x180149400  mov     [rsp+38h+s._p], rbx
0x180149405  cmp     cs:?c_NMTOKENS@SchemaDatatype@@2V?$_reference@VSchemaDatatype@@@@A._p, rbx; _reference<SchemaDatatype> SchemaDatatype::c_NMTOKENS ...
0x18014940c  jnz     loc_18014A4DB
0x180149412  lea     r12d, [rbx+0Ch]
0x180149416  mov     edx, r12d; dwFlags
0x180149419  mov     r15d, 0B8h
0x18014941f  mov     ecx, r15d; cb
0x180149422  call    ?_MemAlloc@@YAPEAX_KK@Z; _MemAlloc(unsigned __int64,ulong)
0x180149427  mov     rcx, rax; this
0x18014942a  call    ??0Datatype_anyType@@QEAA@XZ; Datatype_anyType::Datatype_anyType(void)
0x18014942f  mov     rdi, rax
0x180149432  mov     rdx, rax; pref
0x180149435  lea     rcx, ?c_anySimpleType@SchemaDatatype@@2V?$_reference@VSchemaDatatype@@@@A; ppref
0x18014943c  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x180149441  lea     rcx, aAnysimpletype; "anySimpleType"
0x180149448  call    ?newConstString@String@@SAPEAV1@PEBG@Z; String::newConstString(ushort const *)
0x18014944d  mov     rbx, rax
0x180149450  lea     rcx, [rsp+38h+s]; ppref
0x180149455  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x18014945a  mov     [rsp+38h+s._p], rbx
0x18014945f  lea     rcx, [rdi+40h]; ppref
0x180149463  mov     rdx, rbx; pref
0x180149466  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x18014946b  mov     rcx, [rdi]
0x18014946e  mov     rax, [rcx+10h]
0x180149472  mov     rcx, rdi
0x180149475  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014947a  mov     edx, r12d; dwFlags
0x18014947d  mov     ecx, r15d; cb
0x180149480  call    ?_MemAlloc@@YAPEAX_KK@Z; _MemAlloc(unsigned __int64,ulong)
0x180149485  mov     rcx, rax; this
0x180149488  call    ??0Datatype_anyURI@@QEAA@XZ; Datatype_anyURI::Datatype_anyURI(void)
0x18014948d  mov     rdi, rax
0x180149490  mov     rdx, rax; pref
0x180149493  lea     rcx, ?c_anyURI@SchemaDatatype@@2V?$_reference@VSchemaDatatype@@@@A; ppref
0x18014949a  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x18014949f  lea     rcx, aAnyuri; "anyURI"
0x1801494a6  call    ?newConstString@String@@SAPEAV1@PEBG@Z; String::newConstString(ushort const *)
0x1801494ab  mov     rbx, rax
0x1801494ae  lea     rcx, [rsp+38h+s]; ppref
0x1801494b3  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1801494b8  mov     [rsp+38h+s._p], rbx
0x1801494bd  lea     rcx, [rdi+40h]; ppref
0x1801494c1  mov     rdx, rbx; pref
0x1801494c4  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1801494c9  mov     rcx, [rdi]
0x1801494cc  mov     rax, [rcx+10h]
0x1801494d0  mov     rcx, rdi
0x1801494d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801494d8  mov     edx, r12d; dwFlags
0x1801494db  mov     ecx, r15d; cb
0x1801494de  call    ?_MemAlloc@@YAPEAX_KK@Z; _MemAlloc(unsigned __int64,ulong)
0x1801494e3  mov     rcx, rax; this
0x1801494e6  call    ??0Datatype_base64Binary@@QEAA@XZ; Datatype_base64Binary::Datatype_base64Binary(void)
0x1801494eb  mov     rdi, rax
0x1801494ee  mov     rdx, rax; pref
0x1801494f1  lea     rcx, ?c_base64Binary@SchemaDatatype@@2V?$_reference@VSchemaDatatype@@@@A; ppref
0x1801494f8  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1801494fd  lea     rcx, aBase64binary; "base64Binary"
0x180149504  call    ?newConstString@String@@SAPEAV1@PEBG@Z; String::newConstString(ushort const *)
0x180149509  mov     rbx, rax
0x18014950c  lea     rcx, [rsp+38h+s]; ppref
0x180149511  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x180149516  mov     [rsp+38h+s._p], rbx
0x18014951b  lea     rcx, [rdi+40h]; ppref
0x18014951f  mov     rdx, rbx; pref
0x180149522  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x180149527  mov     rcx, [rdi]
0x18014952a  mov     rax, [rcx+10h]
0x18014952e  mov     rcx, rdi
0x180149531  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180149536  mov     edx, r12d; dwFlags
0x180149539  mov     ecx, r15d; cb
0x18014953c  call    ?_MemAlloc@@YAPEAX_KK@Z; _MemAlloc(unsigned __int64,ulong)
0x180149541  mov     rcx, rax; this
0x180149544  call    ??0Datatype_boolean@@QEAA@XZ; Datatype_boolean::Datatype_boolean(void)
0x180149549  mov     rdi, rax
0x18014954c  mov     rdx, rax; pref
0x18014954f  lea     rcx, ?c_boolean@SchemaDatatype@@2V?$_reference@VSchemaDatatype@@@@A; ppref
0x180149556  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x18014955b  lea     rcx, aBoolean; "boolean"
0x180149562  call    ?newConstString@String@@SAPEAV1@PEBG@Z; String::newConstString(ushort const *)
0x180149567  mov     rbx, rax
0x18014956a  lea     rcx, [rsp+38h+s]; ppref
0x18014956f  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x180149574  mov     [rsp+38h+s._p], rbx
0x180149579  lea     rcx, [rdi+40h]; ppref
0x18014957d  mov     rdx, rbx; pref
0x180149580  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x180149585  mov     rcx, [rdi]
0x180149588  mov     rax, [rcx+10h]
0x18014958c  mov     rcx, rdi
0x18014958f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180149594  mov     edx, r12d; dwFlags
0x180149597  mov     ecx, r15d; cb
0x18014959a  call    ?_MemAlloc@@YAPEAX_KK@Z; _MemAlloc(unsigned __int64,ulong)
0x18014959f  mov     rcx, rax; this
0x1801495a2  call    ??0Datatype_byte@@QEAA@XZ; Datatype_byte::Datatype_byte(void)
0x1801495a7  mov     rdi, rax
0x1801495aa  mov     rdx, rax; pref
0x1801495ad  lea     rcx, ?c_byte@SchemaDatatype@@2V?$_reference@VSchemaDatatype@@@@A; ppref
0x1801495b4  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1801495b9  lea     rcx, aByte; "byte"
0x1801495c0  call    ?newConstString@String@@SAPEAV1@PEBG@Z; String::newConstString(ushort const *)
0x1801495c5  mov     rbx, rax
0x1801495c8  lea     rcx, [rsp+38h+s]; ppref
0x1801495cd  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1801495d2  mov     [rsp+38h+s._p], rbx
0x1801495d7  lea     rcx, [rdi+40h]; ppref
0x1801495db  mov     rdx, rbx; pref
0x1801495de  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1801495e3  mov     rcx, [rdi]
0x1801495e6  mov     rax, [rcx+10h]
0x1801495ea  mov     rcx, rdi
0x1801495ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801495f2  mov     edx, r12d; dwFlags
0x1801495f5  lea     r14d, [r15+8]
0x1801495f9  mov     ecx, r14d; cb
0x1801495fc  call    ?_MemAlloc@@YAPEAX_KK@Z; _MemAlloc(unsigned __int64,ulong)
0x180149601  mov     rcx, rax; this
0x180149604  call    ??0Datatype_date@@QEAA@XZ; Datatype_date::Datatype_date(void)
0x180149609  mov     rdi, rax
0x18014960c  mov     rdx, rax; pref
0x18014960f  lea     rcx, ?c_date@SchemaDatatype@@2V?$_reference@VSchemaDatatype@@@@A; ppref
0x180149616  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x18014961b  lea     rcx, aDate; "date"
0x180149622  call    ?newConstString@String@@SAPEAV1@PEBG@Z; String::newConstString(ushort const *)
0x180149627  mov     rbx, rax
0x18014962a  lea     rcx, [rsp+38h+s]; ppref
0x18014962f  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x180149634  mov     [rsp+38h+s._p], rbx
0x180149639  lea     rcx, [rdi+40h]; ppref
0x18014963d  mov     rdx, rbx; pref
0x180149640  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x180149645  mov     rcx, [rdi]
0x180149648  mov     rax, [rcx+10h]
0x18014964c  mov     rcx, rdi
0x18014964f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180149654  mov     edx, r12d; dwFlags
0x180149657  mov     ecx, r14d; cb
0x18014965a  call    ?_MemAlloc@@YAPEAX_KK@Z; _MemAlloc(unsigned __int64,ulong)
0x18014965f  mov     rcx, rax; this
0x180149662  call    ??0Datatype_dateTime@@QEAA@XZ; Datatype_dateTime::Datatype_dateTime(void)
0x180149667  mov     rdi, rax
0x18014966a  mov     rdx, rax; pref
0x18014966d  lea     rcx, ?c_dateTime@SchemaDatatype@@2V?$_reference@VSchemaDatatype@@@@A; ppref
0x180149674  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x180149679  lea     rcx, aDatetime; "dateTime"
0x180149680  call    ?newConstString@String@@SAPEAV1@PEBG@Z; String::newConstString(ushort const *)
0x180149685  mov     rbx, rax
0x180149688  lea     rcx, [rsp+38h+s]; ppref
0x18014968d  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x180149692  mov     [rsp+38h+s._p], rbx
0x180149697  lea     rcx, [rdi+40h]; ppref
0x18014969b  mov     rdx, rbx; pref
0x18014969e  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1801496a3  mov     rcx, [rdi]
0x1801496a6  mov     rax, [rcx+10h]
0x1801496aa  mov     rcx, rdi
0x1801496ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801496b2  mov     edx, r12d; dwFlags
0x1801496b5  mov     ecx, r14d; cb
0x1801496b8  call    ?_MemAlloc@@YAPEAX_KK@Z; _MemAlloc(unsigned __int64,ulong)
0x1801496bd  mov     rcx, rax; this
0x1801496c0  call    ??0Datatype_day@@QEAA@XZ; Datatype_day::Datatype_day(void)
0x1801496c5  mov     rdi, rax
0x1801496c8  mov     rdx, rax; pref
0x1801496cb  lea     rcx, ?c_day@SchemaDatatype@@2V?$_reference@VSchemaDatatype@@@@A; ppref
0x1801496d2  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1801496d7  lea     rcx, aGday; "gDay"
0x1801496de  call    ?newConstString@String@@SAPEAV1@PEBG@Z; String::newConstString(ushort const *)
0x1801496e3  mov     rbx, rax
0x1801496e6  lea     rcx, [rsp+38h+s]; ppref
0x1801496eb  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1801496f0  mov     [rsp+38h+s._p], rbx
0x1801496f5  lea     rcx, [rdi+40h]; ppref
0x1801496f9  mov     rdx, rbx; pref
0x1801496fc  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x180149701  mov     rcx, [rdi]
0x180149704  mov     rax, [rcx+10h]
0x180149708  mov     rcx, rdi
0x18014970b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180149710  mov     edx, r12d; dwFlags
0x180149713  mov     ecx, r15d; cb
0x180149716  call    ?_MemAlloc@@YAPEAX_KK@Z; _MemAlloc(unsigned __int64,ulong)
0x18014971b  mov     rcx, rax; this
0x18014971e  call    ??0Datatype_double@@QEAA@XZ; Datatype_double::Datatype_double(void)
0x180149723  mov     rdi, rax
0x180149726  mov     rdx, rax; pref
0x180149729  lea     rcx, ?c_double@SchemaDatatype@@2V?$_reference@VSchemaDatatype@@@@A; ppref
0x180149730  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x180149735  lea     rcx, aDouble; "double"
0x18014973c  call    ?newConstString@String@@SAPEAV1@PEBG@Z; String::newConstString(ushort const *)
0x180149741  mov     rbx, rax
0x180149744  lea     rcx, [rsp+38h+s]; ppref
0x180149749  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x18014974e  mov     [rsp+38h+s._p], rbx
0x180149753  lea     rcx, [rdi+40h]; ppref
0x180149757  mov     rdx, rbx; pref
0x18014975a  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x18014975f  mov     rcx, [rdi]
0x180149762  mov     rax, [rcx+10h]
0x180149766  mov     rcx, rdi
0x180149769  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014976e  mov     edx, r12d; dwFlags
0x180149771  mov     ecx, r15d; cb
0x180149774  call    ?_MemAlloc@@YAPEAX_KK@Z; _MemAlloc(unsigned __int64,ulong)
0x180149779  mov     rcx, rax; this
0x18014977c  call    ??0Datatype_duration@@QEAA@XZ; Datatype_duration::Datatype_duration(void)
0x180149781  mov     rdi, rax
0x180149784  mov     rdx, rax; pref
0x180149787  lea     rcx, ?c_duration@SchemaDatatype@@2V?$_reference@VSchemaDatatype@@@@A; ppref
0x18014978e  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x180149793  lea     rcx, aDuration; "duration"
0x18014979a  call    ?newConstString@String@@SAPEAV1@PEBG@Z; String::newConstString(ushort const *)
0x18014979f  mov     rbx, rax
0x1801497a2  lea     rcx, [rsp+38h+s]; ppref
0x1801497a7  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1801497ac  mov     [rsp+38h+s._p], rbx
0x1801497b1  lea     rcx, [rdi+40h]; ppref
0x1801497b5  mov     rdx, rbx; pref
0x1801497b8  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1801497bd  mov     rcx, [rdi]
0x1801497c0  mov     rax, [rcx+10h]
0x1801497c4  mov     rcx, rdi
0x1801497c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801497cc  mov     edx, r12d; dwFlags
0x1801497cf  mov     ecx, r14d; cb
0x1801497d2  call    ?_MemAlloc@@YAPEAX_KK@Z; _MemAlloc(unsigned __int64,ulong)
0x1801497d7  mov     rcx, rax; this
0x1801497da  call    ??0Datatype_ENTITY@@QEAA@XZ; Datatype_ENTITY::Datatype_ENTITY(void)
0x1801497df  mov     rdi, rax
0x1801497e2  mov     rdx, rax; pref
0x1801497e5  lea     rcx, ?c_ENTITY@SchemaDatatype@@2V?$_reference@VSchemaDatatype@@@@A; ppref
0x1801497ec  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1801497f1  lea     rcx, aEntity; "ENTITY"
0x1801497f8  call    ?newConstString@String@@SAPEAV1@PEBG@Z; String::newConstString(ushort const *)
0x1801497fd  mov     rbx, rax
0x180149800  lea     rcx, [rsp+38h+s]; ppref
0x180149805  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x18014980a  mov     [rsp+38h+s._p], rbx
0x18014980f  lea     rcx, [rdi+40h]; ppref
0x180149813  mov     rdx, rbx; pref
0x180149816  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x18014981b  mov     rcx, [rdi]
0x18014981e  mov     rax, [rcx+10h]
0x180149822  mov     rcx, rdi
0x180149825  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014982a  mov     edx, r12d; dwFlags
0x18014982d  mov     ecx, r15d; cb
0x180149830  call    ?_MemAlloc@@YAPEAX_KK@Z; _MemAlloc(unsigned __int64,ulong)
0x180149835  mov     rcx, rax; this
0x180149838  call    ??0Datatype_float@@QEAA@XZ; Datatype_float::Datatype_float(void)
0x18014983d  mov     rdi, rax
0x180149840  mov     rdx, rax; pref
0x180149843  lea     rcx, ?c_float@SchemaDatatype@@2V?$_reference@VSchemaDatatype@@@@A; ppref
0x18014984a  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x18014984f  lea     rcx, aFloat; "float"
0x180149856  call    ?newConstString@String@@SAPEAV1@PEBG@Z; String::newConstString(ushort const *)
0x18014985b  mov     rbx, rax
0x18014985e  lea     rcx, [rsp+38h+s]; ppref
0x180149863  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x180149868  mov     [rsp+38h+s._p], rbx
0x18014986d  lea     rcx, [rdi+40h]; ppref
0x180149871  mov     rdx, rbx; pref
0x180149874  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x180149879  mov     rcx, [rdi]
0x18014987c  mov     rax, [rcx+10h]
0x180149880  mov     rcx, rdi
0x180149883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180149888  mov     edx, r12d; dwFlags
0x18014988b  mov     ecx, r15d; cb
0x18014988e  call    ?_MemAlloc@@YAPEAX_KK@Z; _MemAlloc(unsigned __int64,ulong)
0x180149893  mov     rcx, rax; this
0x180149896  call    ??0Datatype_hexBinary@@QEAA@XZ; Datatype_hexBinary::Datatype_hexBinary(void)
0x18014989b  mov     rdi, rax
0x18014989e  mov     rdx, rax; pref
0x1801498a1  lea     rcx, ?c_hexBinary@SchemaDatatype@@2V?$_reference@VSchemaDatatype@@@@A; ppref
0x1801498a8  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1801498ad  lea     rcx, aHexbinary; "hexBinary"
0x1801498b4  call    ?newConstString@String@@SAPEAV1@PEBG@Z; String::newConstString(ushort const *)
0x1801498b9  mov     rbx, rax
0x1801498bc  lea     rcx, [rsp+38h+s]; ppref
0x1801498c1  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1801498c6  mov     [rsp+38h+s._p], rbx
0x1801498cb  lea     rcx, [rdi+40h]; ppref
0x1801498cf  mov     rdx, rbx; pref
0x1801498d2  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
  ... truncated ...
```
