# SchemaDatatype::classInit(void)

- ea: `0x18014611c`
- end: `0x18014727d`
- name: `?classInit@SchemaDatatype@@SAXXZ`
- size: `4449`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `54`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x18004cf70`

## callees

- `0x180009490`
- `0x18000d7d0`
- `0x18003617c`
- `0x18003d0b0`
- `0x18005f3dc`
- `0x18005fbe0`
- `0x18009f718`
- `0x1800a3e04`
- `0x1800aa2a0`
- `0x1800aa93c`
- `0x1800c049c`
- `0x1800c41e0`
- `0x1800c4600`
- `0x1800c4644`
- `0x1800c4688`
- `0x1800c46cc`
- `0x1800d65dc`
- `0x18014298c`
- `0x1801429b8`
- `0x1801429e4`
- `0x180142a20`
- `0x180142a54`
- `0x180142a88`
- `0x180142abc`
- `0x180142af0`
- `0x180142b24`
- `0x180142b58`
- `0x180142b94`
- `0x180142bd0`
- `0x180142c0c`
- `0x180142c40`
- `0x180142c74`
- `0x180142ca8`
- `0x180142cdc`
- `0x180142d10`
- `0x180142d44`
- `0x180142d80`
- `0x180142db4`
- `0x180142df0`
- `0x180142e2c`
- `0x180142e60`
- `0x180142e94`
- `0x180142ec8`
- `0x180142efc`
- `0x180142f30`
- `0x180142fb4`
- `0x180142fdc`
- `0x180143010`
- `0x180143044`
- `0x180143078`

## string_xrefs

- `0x180146e88`: `token`
- `0x180146a6f`: `NMTOKEN`
- `0x1801471f9`: `NMTOKENS`
- `0x1801461ef`: `anyURI`

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
      v0 = (Datatype_anyType *)_MemAlloc(0xB8u, 12);
      Datatype_anyType::Datatype_anyType(v0);
      v2 = v1;
      assign(&SchemaDatatype::c_anySimpleType._p, v1);
      v3 = String::newConstString(L"anySimpleType");
      release(&s._p);
      s._p = v3;
      assign(v2 + 8, v3);
      ((void (__fastcall *)(IUnknown **))(*v2)[2].__vftable)(v2);
      v4 = (Datatype_anyURI *)_MemAlloc(0xB8u, 12);
      Datatype_anyURI::Datatype_anyURI(v4);
      v6 = v5;
      assign(&SchemaDatatype::c_anyURI._p, v5);
      v7 = String::newConstString(L"anyURI");
      release(&s._p);
      s._p = v7;
      assign(v6 + 8, v7);
      ((void (__fastcall *)(IUnknown **))(*v6)[2].__vftable)(v6);
      v8 = (Datatype_base64Binary *)_MemAlloc(0xB8u, 12);
      Datatype_base64Binary::Datatype_base64Binary(v8);
      v10 = v9;
      assign(&SchemaDatatype::c_base64Binary._p, v9);
      v11 = String::newConstString(L"base64Binary");
      release(&s._p);
      s._p = v11;
      assign(v10 + 8, v11);
      ((void (__fastcall *)(IUnknown **))(*v10)[2].__vftable)(v10);
      v12 = (Datatype_boolean *)_MemAlloc(0xB8u, 12);
      Datatype_boolean::Datatype_boolean(v12);
      v14 = v13;
      assign(&SchemaDatatype::c_boolean._p, v13);
      v15 = String::newConstString(L"boolean");
      release(&s._p);
      s._p = v15;
      assign(v14 + 8, v15);
      ((void (__fastcall *)(IUnknown **))(*v14)[2].__vftable)(v14);
      v16 = (Datatype_byte *)_MemAlloc(0xB8u, 12);
      Datatype_byte::Datatype_byte(v16);
      v18 = v17;
      assign(&SchemaDatatype::c_byte._p, v17);
      v19 = String::newConstString(L"byte");
      release(&s._p);
      s._p = v19;
      assign(v18 + 8, v19);
      ((void (__fastcall *)(IUnknown **))(*v18)[2].__vftable)(v18);
      v20 = (Datatype_date *)_MemAlloc(0xC0u, 12);
      Datatype_date::Datatype_date(v20);
      v22 = v21;
      assign(&SchemaDatatype::c_date._p, v21);
      v23 = String::newConstString(L"date");
      release(&s._p);
      s._p = v23;
      assign(v22 + 8, v23);
      ((void (__fastcall *)(IUnknown **))(*v22)[2].__vftable)(v22);
      v24 = (Datatype_dateTime *)_MemAlloc(0xC0u, 12);
      Datatype_dateTime::Datatype_dateTime(v24);
      v26 = v25;
      assign(&SchemaDatatype::c_dateTime._p, v25);
      v27 = String::newConstString(L"dateTime");
      release(&s._p);
      s._p = v27;
      assign(v26 + 8, v27);
      ((void (__fastcall *)(IUnknown **))(*v26)[2].__vftable)(v26);
      v28 = (Datatype_day *)_MemAlloc(0xC0u, 12);
      Datatype_day::Datatype_day(v28);
      v30 = v29;
      assign(&SchemaDatatype::c_day._p, v29);
      v31 = String::newConstString(L"gDay");
      release(&s._p);
      s._p = v31;
      assign(v30 + 8, v31);
      ((void (__fastcall *)(IUnknown **))(*v30)[2].__vftable)(v30);
      v32 = (Datatype_double *)_MemAlloc(0xB8u, 12);
      Datatype_double::Datatype_double(v32);
      v34 = v33;
      assign(&SchemaDatatype::c_double._p, v33);
      v35 = String::newConstString(L"double");
      release(&s._p);
      s._p = v35;
      assign(v34 + 8, v35);
      ((void (__fastcall *)(IUnknown **))(*v34)[2].__vftable)(v34);
      v36 = (Datatype_duration *)_MemAlloc(0xB8u, 12);
      Datatype_duration::Datatype_duration(v36);
      v38 = v37;
      assign(&SchemaDatatype::c_duration._p, v37);
      v39 = String::newConstString(L"duration");
      release(&s._p);
      s._p = v39;
      assign(v38 + 8, v39);
      ((void (__fastcall *)(IUnknown **))(*v38)[2].__vftable)(v38);
      v40 = (Datatype_ENTITY *)_MemAlloc(0xC0u, 12);
      Datatype_ENTITY::Datatype_ENTITY(v40);
      v42 = v41;
      assign(&SchemaDatatype::c_ENTITY._p, v41);
      v43 = String::newConstString(L"ENTITY");
      release(&s._p);
      s._p = v43;
      assign(v42 + 8, v43);
      ((void (__fastcall *)(IUnknown **))(*v42)[2].__vftable)(v42);
      v44 = (Datatype_float *)_MemAlloc(0xB8u, 12);
      Datatype_float::Datatype_float(v44);
      v46 = v45;
      assign(&SchemaDatatype::c_float._p, v45);
      v47 = String::newConstString(L"float");
      release(&s._p);
      s._p = v47;
      assign(v46 + 8, v47);
      ((void (__fastcall *)(IUnknown **))(*v46)[2].__vftable)(v46);
      v48 = (Datatype_hexBinary *)_MemAlloc(0xB8u, 12);
      Datatype_hexBinary::Datatype_hexBinary(v48);
      v50 = v49;
      assign(&SchemaDatatype::c_hexBinary._p, v49);
      v51 = String::newConstString(L"hexBinary");
      release(&s._p);
      s._p = v51;
      assign(v50 + 8, v51);
      ((void (__fastcall *)(IUnknown **))(*v50)[2].__vftable)(v50);
      v52 = (Datatype_ID *)_MemAlloc(0xC0u, 12);
      Datatype_ID::Datatype_ID(v52);
      v54 = v53;
      assign(&SchemaDatatype::c_ID._p, v53);
      v55 = String::newConstString(L"ID");
      release(&s._p);
      s._p = v55;
      assign(v54 + 8, v55);
      ((void (__fastcall *)(IUnknown **))(*v54)[2].__vftable)(v54);
      v56 = (Datatype_IDREF *)_MemAlloc(0xC0u, 12);
      Datatype_IDREF::Datatype_IDREF(v56);
      v58 = v57;
      assign(&SchemaDatatype::c_IDREF._p, v57);
      v59 = String::newConstString(L"IDREF");
      release(&s._p);
      s._p = v59;
      assign(v58 + 8, v59);
      ((void (__fastcall *)(IUnknown **))(*v58)[2].__vftable)(v58);
      v60 = (Datatype_int *)_MemAlloc(0xB8u, 12);
      Datatype_int::Datatype_int(v60);
      v62 = v61;
      assign(&SchemaDatatype::c_int._p, v61);
      v63 = String::newConstString(L"int");
      release(&s._p);
      s._p = v63;
      assign(v62 + 8, v63);
      ((void (__fastcall *)(IUnknown **))(*v62)[2].__vftable)(v62);
      v64 = (Datatype_integer *)_MemAlloc(0xB8u, 12);
      Datatype_integer::Datatype_integer(v64);
      v66 = v65;
      assign(&SchemaDatatype::c_integer._p, v65);
      v67 = String::newConstString(L"integer");
      release(&s._p);
      s._p = v67;
      assign(v66 + 8, v67);
      ((void (__fastcall *)(IUnknown **))(*v66)[2].__vftable)(v66);
      v68 = (Datatype_language *)_MemAlloc(0xC0u, 12);
      Datatype_language::Datatype_language(v68);
      v70 = v69;
      assign(&SchemaDatatype::c_language._p, v69);
      v71 = String::newConstString(L"language");
      release(&s._p);
      s._p = v71;
      assign(v70 + 8, v71);
      ((void (__fastcall *)(IUnknown **))(*v70)[2].__vftable)(v70);
      v72 = (Datatype_long *)_MemAlloc(0xB8u, 12);
      Datatype_long::Datatype_long(v72);
      v74 = v73;
      assign(&SchemaDatatype::c_long._p, v73);
      v75 = String::newConstString(L"long");
      release(&s._p);
      s._p = v75;
      assign(v74 + 8, v75);
      ((void (__fastcall *)(IUnknown **))(*v74)[2].__vftable)(v74);
      v76 = (Datatype_month *)_MemAlloc(0xC0u, 12);
      Datatype_month::Datatype_month(v76);
      v78 = v77;
      assign(&SchemaDatatype::c_month._p, v77);
      v79 = String::newConstString(L"gMonth");
      release(&s._p);
      s._p = v79;
      assign(v78 + 8, v79);
      ((void (__fastcall *)(IUnknown **))(*v78)[2].__vftable)(v78);
      v80 = (Datatype_monthDay *)_MemAlloc(0xC0u, 12);
      Datatype_monthDay::Datatype_monthDay(v80);
      v82 = v81;
      assign(&SchemaDatatype::c_monthDay._p, v81);
      v83 = String::newConstString(L"gMonthDay");
      release(&s._p);
      s._p = v83;
      assign(v82 + 8, v83);
      ((void (__fastcall *)(IUnknown **))(*v82)[2].__vftable)(v82);
      v84 = (Datatype_Name *)_MemAlloc(0xC0u, 12);
      Datatype_Name::Datatype_Name(v84, HT_Name);
      v86 = v85;
      assign(&SchemaDatatype::c_Name._p, v85);
      v87 = String::newConstString(L"Name");
      release(&s._p);
      s._p = v87;
      assign(v86 + 8, v87);
      ((void (__fastcall *)(IUnknown **))(*v86)[2].__vftable)(v86);
      v88 = (Datatype_NCName *)_MemAlloc(0xC0u, 12);
      Datatype_NCName::Datatype_NCName(v88, HT_NCName);
      v90 = v89;
      assign(&SchemaDatatype::c_NCName._p, v89);
      v91 = String::newConstString(L"NCName");
      release(&s._p);
      s._p = v91;
      assign(v90 + 8, v91);
      ((void (__fastcall *)(IUnknown **))(*v90)[2].__vftable)(v90);
      v92 = (Datatype_negativeInteger *)_MemAlloc(0xB8u, 12);
      Datatype_negativeInteger::Datatype_negativeInteger(v92);
      v94 = v93;
      assign(&SchemaDatatype::c_negativeInteger._p, v93);
      v95 = String::newConstString(L"negativeInteger");
      release(&s._p);
      s._p = v95;
      assign(v94 + 8, v95);
      ((void (__fastcall *)(IUnknown **))(*v94)[2].__vftable)(v94);
      v96 = (Datatype_NMTOKEN *)_MemAlloc(0xC0u, 12);
      Datatype_NMTOKEN::Datatype_NMTOKEN(v96);
      v98 = v97;
      assign(&SchemaDatatype::c_NMTOKEN._p, v97);
      v99 = String::newConstString(L"NMTOKEN");
      release(&s._p);
      s._p = v99;
      assign(v98 + 8, v99);
      ((void (__fastcall *)(IUnknown **))(*v98)[2].__vftable)(v98);
      v100 = (Datatype_nonNegativeInteger *)_MemAlloc(0xB8u, 12);
      Datatype_nonNegativeInteger::Datatype_nonNegativeInteger(v100);
      v102 = v101;
      assign(&SchemaDatatype::c_nonNegativeInteger._p, v101);
      v103 = String::newConstString(L"nonNegativeInteger");
      release(&s._p);
      s._p = v103;
      assign(v102 + 8, v103);
      ((void (__fastcall *)(IUnknown **))(*v102)[2].__vftable)(v102);
      v104 = (Datatype_nonPositiveInteger *)_MemAlloc(0xB8u, 12);
      Datatype_nonPositiveInteger::Datatype_nonPositiveInteger(v104);
      v106 = v105;
      assign(&SchemaDatatype::c_nonPositiveInteger._p, v105);
      v107 = String::newConstString(L"nonPositiveInteger");
      release(&s._p);
      s._p = v107;
      assign(v106 + 8, v107);
      ((void (__fastcall *)(IUnknown **))(*v106)[2].__vftable)(v106);
      v108 = (Datatype_normalizedString *)_MemAlloc(0xC0u, 12);
      Datatype_normalizedString::Datatype_normalizedString(v108, HT_normalizedString);
      v110 = v109;
      assign(&SchemaDatatype::c_normalizedString._p, v109);
      v111 = String::newConstString(L"normalizedString");
      release(&s._p);
      s._p = v111;
      assign(v110 + 8, v111);
      ((void (__fastcall *)(IUnknown **))(*v110)[2].__vftable)(v110);
      v112 = (Datatype_NOTATION *)_MemAlloc(0xB8u, 12);
      Datatype_NOTATION::Datatype_NOTATION(v112);
      v114 = v113;
      assign(&SchemaDatatype::c_NOTATION._p, v113);
      v115 = String::newConstString(L"NOTATION");
      release(&s._p);
      s._p = v115;
      assign(v114 + 8, v115);
      ((void (__fastcall *)(IUnknown **))(*v114)[2].__vftable)(v114);
      v116 = (Datatype_decimal *)_MemAlloc(0xB8u, 12);
      Datatype_decimal::Datatype_decimal(v116);
      v118 = v117;
      assign(&SchemaDatatype::c_decimal._p, v117);
      v119 = String::newConstString(L"decimal");
      release(&s._p);
      s._p = v119;
      assign(v118 + 8, v119);
      ((void (__fastcall *)(IUnknown **))(*v118)[2].__vftable)(v118);
      v120 = (Datatype_positiveInteger *)_MemAlloc(0xB8u, 12);
      Datatype_positiveInteger::Datatype_positiveInteger(v120);
      v122 = v121;
      assign(&SchemaDatatype::c_positiveInteger._p, v121);
      v123 = String::newConstString(L"positiveInteger");
      release(&s._p);
      s._p = v123;
      assign(v122 + 8, v123);
      ((void (__fastcall *)(IUnknown **))(*v122)[2].__vftable)(v122);
      v124 = (Datatype_QName *)_MemAlloc(0xB8u, 12);
      Datatype_QName::Datatype_QName(v124);
      v126 = v125;
      assign(&SchemaDatatype::c_QName._p, v125);
      v127 = String::newConstString(L"QName");
      release(&s._p);
      s._p = v127;
      assign(v126 + 8, v127);
      ((void (__fastcall *)(IUnknown **))(*v126)[2].__vftable)(v126);
      v128 = (Datatype_short *)_MemAlloc(0xB8u, 12);
      Datatype_short::Datatype_short(v128);
      v130 = v129;
      assign(&SchemaDatatype::c_short._p, v129);
      v131 = String::newConstString(L"short");
      release(&s._p);
      s._p = v131;
      assign(v130 + 8, v131);
      ((void (__fastcall *)(IUnknown **))(*v130)[2].__vftable)(v130);
      v132 = (Datatype_string *)_MemAlloc(0xC0u, 12);
      Datatype_string::Datatype_string(v132, HT_string);
      v134 = v133;
      assign(&SchemaDatatype::c_string._p, v133);
      v135 = String::newConstString(L"string");
      release(&s._p);
      s._p = v135;
      assign(v134 + 8, v135);
      ((void (__fastcall *)(IUnknown **))(*v134)[2].__vftable)(v134);
      v136 = (Datatype_time *)_MemAlloc(0xC0u, 12);
      Datatype_time::Datatype_time(v136);
      v138 = v137;
      assign(&SchemaDatatype::c_time._p, v137);
      v139 = String::newConstString(L"time");
      release(&s._p);
      s._p = v139;
      assign(v138 + 8, v139);
      ((void (__fastcall *)(IUnknown **))(*v138)[2].__vftable)(v138);
      v140 = (Datatype_token *)_MemAlloc(0xC0u, 12);
      Datatype_token::Datatype_token(v140, HT_token);
      v142 = v141;
      assign(&SchemaDatatype::c_token._p, v141);
      v143 = String::newConstString(L"token");
      release(&s._p);
      s._p = v143;
      assign(v142 + 8, v143);
      ((void (__fastcall *)(IUnknown **))(*v142)[2].__vftable)(v142);
      v144 = (Datatype_unsignedByte *)_MemAlloc(0xB8u, 12);
      Datatype_unsignedByte::Datatype_unsignedByte(v144);
      v146 = v145;
      assign(&SchemaDatatype::c_unsignedByte._p, v145);
      v147 = String::newConstString(L"unsignedByte");
      release(&s._p);
      s._p = v147;
      assign(v146 + 8, v147);
      ((void (__fastcall *)(IUnknown **))(*v146)[2].__vftable)(v146);
      v148 = (Datatype_unsignedInt *)_MemAlloc(0xB8u, 12);
      Datatype_unsignedInt::Datatype_unsignedInt(v148);
      v150 = v149;
      assign(&SchemaDatatype::c_unsignedInt._p, v149);
      v151 = String::newConstString(L"unsignedInt");
      release(&s._p);
      s._p = v151;
      assign(v150 + 8, v151);
      ((void (__fastcall *)(IUnknown **))(*v150)[2].__vftable)(v150);
      v152 = (Datatype_unsignedLong *)_MemAlloc(0xB8u, 12);
      Datatype_unsignedLong::Datatype_unsignedLong(v152);
      v154 = v153;
      assign(&SchemaDatatype::c_unsignedLong._p, v153);
      v155 = String::newConstString(L"unsignedLong");
      release(&s._p);
      s._p = v155;
      assign(v154 + 8, v155);
      ((void (__fastcall *)(IUnknown **))(*v154)[2].__vftable)(v154);
      v156 = (Datatype_unsignedShort *)_MemAlloc(0xB8u, 12);
      Datatype_unsignedShort::Datatype_unsignedShort(v156);
      v158 = v157;
      assign(&SchemaDatatype::c_unsignedShort._p, v157);
      v159 = String::newConstString(L"unsignedShort");
      release(&s._p);
      s._p = v159;
      assign(v158 + 8, v159);
      ((void (__fastcall *)(IUnknown **))(*v158)[2].__vftable)(v158);
      v160 = (Datatype_year *)_MemAlloc(0xC0u, 12);
      Datatype_year::Datatype_year(v160);
      v162 = v161;
      assign(&SchemaDatatype::c_year._p, v161);
      v163 = String::newConstString(L"gYear");
      release(&s._p);
      s._p = v163;
      assign(v162 + 8, v163);
      ((void (__fastcall *)(IUnknown **))(*v162)[2].__vftable)(v162);
      v164 = (Datatype_yearMonth *)_MemAlloc(0xC0u, 12);
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
0x18014611c  mov     [rsp+arg_10], rbx
0x180146121  mov     [rsp+arg_18], rdi
0x180146126  push    r12
0x180146128  push    r14
0x18014612a  push    r15
0x18014612c  sub     rsp, 20h
0x180146130  xor     ebx, ebx
0x180146132  cmp     cs:?c_NMTOKENS@SchemaDatatype@@2V?$_reference@VSchemaDatatype@@@@A._p, rbx; _reference<SchemaDatatype> SchemaDatatype::c_NMTOKENS ...
0x180146139  jnz     loc_18014723F
0x18014613f  mov     rdx, cs:?g_pMutex@@3PEAVCSMutex@@EA; pMutex
0x180146146  lea     rcx, [rsp+38h+lock]; this
0x18014614b  call    ??0MutexLock@@QEAA@PEAVMutex@@@Z; MutexLock::MutexLock(Mutex *)
0x180146150  mov     [rsp+38h+s._p], rbx
0x180146155  cmp     cs:?c_NMTOKENS@SchemaDatatype@@2V?$_reference@VSchemaDatatype@@@@A._p, rbx; _reference<SchemaDatatype> SchemaDatatype::c_NMTOKENS ...
0x18014615c  jnz     loc_18014722B
0x180146162  lea     r12d, [rbx+0Ch]
0x180146166  mov     edx, r12d; dwFlags
0x180146169  mov     r15d, 0B8h
0x18014616f  mov     ecx, r15d; cb
0x180146172  call    ?_MemAlloc@@YAPEAX_KK@Z; _MemAlloc(unsigned __int64,ulong)
0x180146177  mov     rcx, rax; this
0x18014617a  call    ??0Datatype_anyType@@QEAA@XZ; Datatype_anyType::Datatype_anyType(void)
0x18014617f  mov     rdi, rax
0x180146182  mov     rdx, rax; pref
0x180146185  lea     rcx, ?c_anySimpleType@SchemaDatatype@@2V?$_reference@VSchemaDatatype@@@@A; ppref
0x18014618c  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x180146191  lea     rcx, aAnysimpletype; "anySimpleType"
0x180146198  call    ?newConstString@String@@SAPEAV1@PEBG@Z; String::newConstString(ushort const *)
0x18014619d  mov     rbx, rax
0x1801461a0  lea     rcx, [rsp+38h+s]; ppref
0x1801461a5  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1801461aa  mov     [rsp+38h+s._p], rbx
0x1801461af  lea     rcx, [rdi+40h]; ppref
0x1801461b3  mov     rdx, rbx; pref
0x1801461b6  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1801461bb  mov     rcx, [rdi]
0x1801461be  mov     rax, [rcx+10h]
0x1801461c2  mov     rcx, rdi
0x1801461c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801461ca  mov     edx, r12d; dwFlags
0x1801461cd  mov     ecx, r15d; cb
0x1801461d0  call    ?_MemAlloc@@YAPEAX_KK@Z; _MemAlloc(unsigned __int64,ulong)
0x1801461d5  mov     rcx, rax; this
0x1801461d8  call    ??0Datatype_anyURI@@QEAA@XZ; Datatype_anyURI::Datatype_anyURI(void)
0x1801461dd  mov     rdi, rax
0x1801461e0  mov     rdx, rax; pref
0x1801461e3  lea     rcx, ?c_anyURI@SchemaDatatype@@2V?$_reference@VSchemaDatatype@@@@A; ppref
0x1801461ea  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1801461ef  lea     rcx, aAnyuri; "anyURI"
0x1801461f6  call    ?newConstString@String@@SAPEAV1@PEBG@Z; String::newConstString(ushort const *)
0x1801461fb  mov     rbx, rax
0x1801461fe  lea     rcx, [rsp+38h+s]; ppref
0x180146203  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x180146208  mov     [rsp+38h+s._p], rbx
0x18014620d  lea     rcx, [rdi+40h]; ppref
0x180146211  mov     rdx, rbx; pref
0x180146214  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x180146219  mov     rcx, [rdi]
0x18014621c  mov     rax, [rcx+10h]
0x180146220  mov     rcx, rdi
0x180146223  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180146228  mov     edx, r12d; dwFlags
0x18014622b  mov     ecx, r15d; cb
0x18014622e  call    ?_MemAlloc@@YAPEAX_KK@Z; _MemAlloc(unsigned __int64,ulong)
0x180146233  mov     rcx, rax; this
0x180146236  call    ??0Datatype_base64Binary@@QEAA@XZ; Datatype_base64Binary::Datatype_base64Binary(void)
0x18014623b  mov     rdi, rax
0x18014623e  mov     rdx, rax; pref
0x180146241  lea     rcx, ?c_base64Binary@SchemaDatatype@@2V?$_reference@VSchemaDatatype@@@@A; ppref
0x180146248  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x18014624d  lea     rcx, aBase64binary; "base64Binary"
0x180146254  call    ?newConstString@String@@SAPEAV1@PEBG@Z; String::newConstString(ushort const *)
0x180146259  mov     rbx, rax
0x18014625c  lea     rcx, [rsp+38h+s]; ppref
0x180146261  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x180146266  mov     [rsp+38h+s._p], rbx
0x18014626b  lea     rcx, [rdi+40h]; ppref
0x18014626f  mov     rdx, rbx; pref
0x180146272  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x180146277  mov     rcx, [rdi]
0x18014627a  mov     rax, [rcx+10h]
0x18014627e  mov     rcx, rdi
0x180146281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180146286  mov     edx, r12d; dwFlags
0x180146289  mov     ecx, r15d; cb
0x18014628c  call    ?_MemAlloc@@YAPEAX_KK@Z; _MemAlloc(unsigned __int64,ulong)
0x180146291  mov     rcx, rax; this
0x180146294  call    ??0Datatype_boolean@@QEAA@XZ; Datatype_boolean::Datatype_boolean(void)
0x180146299  mov     rdi, rax
0x18014629c  mov     rdx, rax; pref
0x18014629f  lea     rcx, ?c_boolean@SchemaDatatype@@2V?$_reference@VSchemaDatatype@@@@A; ppref
0x1801462a6  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1801462ab  lea     rcx, aBoolean; "boolean"
0x1801462b2  call    ?newConstString@String@@SAPEAV1@PEBG@Z; String::newConstString(ushort const *)
0x1801462b7  mov     rbx, rax
0x1801462ba  lea     rcx, [rsp+38h+s]; ppref
0x1801462bf  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1801462c4  mov     [rsp+38h+s._p], rbx
0x1801462c9  lea     rcx, [rdi+40h]; ppref
0x1801462cd  mov     rdx, rbx; pref
0x1801462d0  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1801462d5  mov     rcx, [rdi]
0x1801462d8  mov     rax, [rcx+10h]
0x1801462dc  mov     rcx, rdi
0x1801462df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801462e4  mov     edx, r12d; dwFlags
0x1801462e7  mov     ecx, r15d; cb
0x1801462ea  call    ?_MemAlloc@@YAPEAX_KK@Z; _MemAlloc(unsigned __int64,ulong)
0x1801462ef  mov     rcx, rax; this
0x1801462f2  call    ??0Datatype_byte@@QEAA@XZ; Datatype_byte::Datatype_byte(void)
0x1801462f7  mov     rdi, rax
0x1801462fa  mov     rdx, rax; pref
0x1801462fd  lea     rcx, ?c_byte@SchemaDatatype@@2V?$_reference@VSchemaDatatype@@@@A; ppref
0x180146304  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x180146309  lea     rcx, aByte; "byte"
0x180146310  call    ?newConstString@String@@SAPEAV1@PEBG@Z; String::newConstString(ushort const *)
0x180146315  mov     rbx, rax
0x180146318  lea     rcx, [rsp+38h+s]; ppref
0x18014631d  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x180146322  mov     [rsp+38h+s._p], rbx
0x180146327  lea     rcx, [rdi+40h]; ppref
0x18014632b  mov     rdx, rbx; pref
0x18014632e  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x180146333  mov     rcx, [rdi]
0x180146336  mov     rax, [rcx+10h]
0x18014633a  mov     rcx, rdi
0x18014633d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180146342  mov     edx, r12d; dwFlags
0x180146345  lea     r14d, [r15+8]
0x180146349  mov     ecx, r14d; cb
0x18014634c  call    ?_MemAlloc@@YAPEAX_KK@Z; _MemAlloc(unsigned __int64,ulong)
0x180146351  mov     rcx, rax; this
0x180146354  call    ??0Datatype_date@@QEAA@XZ; Datatype_date::Datatype_date(void)
0x180146359  mov     rdi, rax
0x18014635c  mov     rdx, rax; pref
0x18014635f  lea     rcx, ?c_date@SchemaDatatype@@2V?$_reference@VSchemaDatatype@@@@A; ppref
0x180146366  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x18014636b  lea     rcx, aDate; "date"
0x180146372  call    ?newConstString@String@@SAPEAV1@PEBG@Z; String::newConstString(ushort const *)
0x180146377  mov     rbx, rax
0x18014637a  lea     rcx, [rsp+38h+s]; ppref
0x18014637f  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x180146384  mov     [rsp+38h+s._p], rbx
0x180146389  lea     rcx, [rdi+40h]; ppref
0x18014638d  mov     rdx, rbx; pref
0x180146390  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x180146395  mov     rcx, [rdi]
0x180146398  mov     rax, [rcx+10h]
0x18014639c  mov     rcx, rdi
0x18014639f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801463a4  mov     edx, r12d; dwFlags
0x1801463a7  mov     ecx, r14d; cb
0x1801463aa  call    ?_MemAlloc@@YAPEAX_KK@Z; _MemAlloc(unsigned __int64,ulong)
0x1801463af  mov     rcx, rax; this
0x1801463b2  call    ??0Datatype_dateTime@@QEAA@XZ; Datatype_dateTime::Datatype_dateTime(void)
0x1801463b7  mov     rdi, rax
0x1801463ba  mov     rdx, rax; pref
0x1801463bd  lea     rcx, ?c_dateTime@SchemaDatatype@@2V?$_reference@VSchemaDatatype@@@@A; ppref
0x1801463c4  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1801463c9  lea     rcx, aDatetime; "dateTime"
0x1801463d0  call    ?newConstString@String@@SAPEAV1@PEBG@Z; String::newConstString(ushort const *)
0x1801463d5  mov     rbx, rax
0x1801463d8  lea     rcx, [rsp+38h+s]; ppref
0x1801463dd  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1801463e2  mov     [rsp+38h+s._p], rbx
0x1801463e7  lea     rcx, [rdi+40h]; ppref
0x1801463eb  mov     rdx, rbx; pref
0x1801463ee  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1801463f3  mov     rcx, [rdi]
0x1801463f6  mov     rax, [rcx+10h]
0x1801463fa  mov     rcx, rdi
0x1801463fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180146402  mov     edx, r12d; dwFlags
0x180146405  mov     ecx, r14d; cb
0x180146408  call    ?_MemAlloc@@YAPEAX_KK@Z; _MemAlloc(unsigned __int64,ulong)
0x18014640d  mov     rcx, rax; this
0x180146410  call    ??0Datatype_day@@QEAA@XZ; Datatype_day::Datatype_day(void)
0x180146415  mov     rdi, rax
0x180146418  mov     rdx, rax; pref
0x18014641b  lea     rcx, ?c_day@SchemaDatatype@@2V?$_reference@VSchemaDatatype@@@@A; ppref
0x180146422  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x180146427  lea     rcx, aGday; "gDay"
0x18014642e  call    ?newConstString@String@@SAPEAV1@PEBG@Z; String::newConstString(ushort const *)
0x180146433  mov     rbx, rax
0x180146436  lea     rcx, [rsp+38h+s]; ppref
0x18014643b  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x180146440  mov     [rsp+38h+s._p], rbx
0x180146445  lea     rcx, [rdi+40h]; ppref
0x180146449  mov     rdx, rbx; pref
0x18014644c  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x180146451  mov     rcx, [rdi]
0x180146454  mov     rax, [rcx+10h]
0x180146458  mov     rcx, rdi
0x18014645b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180146460  mov     edx, r12d; dwFlags
0x180146463  mov     ecx, r15d; cb
0x180146466  call    ?_MemAlloc@@YAPEAX_KK@Z; _MemAlloc(unsigned __int64,ulong)
0x18014646b  mov     rcx, rax; this
0x18014646e  call    ??0Datatype_double@@QEAA@XZ; Datatype_double::Datatype_double(void)
0x180146473  mov     rdi, rax
0x180146476  mov     rdx, rax; pref
0x180146479  lea     rcx, ?c_double@SchemaDatatype@@2V?$_reference@VSchemaDatatype@@@@A; ppref
0x180146480  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x180146485  lea     rcx, aDouble; "double"
0x18014648c  call    ?newConstString@String@@SAPEAV1@PEBG@Z; String::newConstString(ushort const *)
0x180146491  mov     rbx, rax
0x180146494  lea     rcx, [rsp+38h+s]; ppref
0x180146499  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x18014649e  mov     [rsp+38h+s._p], rbx
0x1801464a3  lea     rcx, [rdi+40h]; ppref
0x1801464a7  mov     rdx, rbx; pref
0x1801464aa  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1801464af  mov     rcx, [rdi]
0x1801464b2  mov     rax, [rcx+10h]
0x1801464b6  mov     rcx, rdi
0x1801464b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801464be  mov     edx, r12d; dwFlags
0x1801464c1  mov     ecx, r15d; cb
0x1801464c4  call    ?_MemAlloc@@YAPEAX_KK@Z; _MemAlloc(unsigned __int64,ulong)
0x1801464c9  mov     rcx, rax; this
0x1801464cc  call    ??0Datatype_duration@@QEAA@XZ; Datatype_duration::Datatype_duration(void)
0x1801464d1  mov     rdi, rax
0x1801464d4  mov     rdx, rax; pref
0x1801464d7  lea     rcx, ?c_duration@SchemaDatatype@@2V?$_reference@VSchemaDatatype@@@@A; ppref
0x1801464de  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1801464e3  lea     rcx, aDuration; "duration"
0x1801464ea  call    ?newConstString@String@@SAPEAV1@PEBG@Z; String::newConstString(ushort const *)
0x1801464ef  mov     rbx, rax
0x1801464f2  lea     rcx, [rsp+38h+s]; ppref
0x1801464f7  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1801464fc  mov     [rsp+38h+s._p], rbx
0x180146501  lea     rcx, [rdi+40h]; ppref
0x180146505  mov     rdx, rbx; pref
0x180146508  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x18014650d  mov     rcx, [rdi]
0x180146510  mov     rax, [rcx+10h]
0x180146514  mov     rcx, rdi
0x180146517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014651c  mov     edx, r12d; dwFlags
0x18014651f  mov     ecx, r14d; cb
0x180146522  call    ?_MemAlloc@@YAPEAX_KK@Z; _MemAlloc(unsigned __int64,ulong)
0x180146527  mov     rcx, rax; this
0x18014652a  call    ??0Datatype_ENTITY@@QEAA@XZ; Datatype_ENTITY::Datatype_ENTITY(void)
0x18014652f  mov     rdi, rax
0x180146532  mov     rdx, rax; pref
0x180146535  lea     rcx, ?c_ENTITY@SchemaDatatype@@2V?$_reference@VSchemaDatatype@@@@A; ppref
0x18014653c  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x180146541  lea     rcx, aEntity; "ENTITY"
0x180146548  call    ?newConstString@String@@SAPEAV1@PEBG@Z; String::newConstString(ushort const *)
0x18014654d  mov     rbx, rax
0x180146550  lea     rcx, [rsp+38h+s]; ppref
0x180146555  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x18014655a  mov     [rsp+38h+s._p], rbx
0x18014655f  lea     rcx, [rdi+40h]; ppref
0x180146563  mov     rdx, rbx; pref
0x180146566  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x18014656b  mov     rcx, [rdi]
0x18014656e  mov     rax, [rcx+10h]
0x180146572  mov     rcx, rdi
0x180146575  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014657a  mov     edx, r12d; dwFlags
0x18014657d  mov     ecx, r15d; cb
0x180146580  call    ?_MemAlloc@@YAPEAX_KK@Z; _MemAlloc(unsigned __int64,ulong)
0x180146585  mov     rcx, rax; this
0x180146588  call    ??0Datatype_float@@QEAA@XZ; Datatype_float::Datatype_float(void)
0x18014658d  mov     rdi, rax
0x180146590  mov     rdx, rax; pref
0x180146593  lea     rcx, ?c_float@SchemaDatatype@@2V?$_reference@VSchemaDatatype@@@@A; ppref
0x18014659a  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x18014659f  lea     rcx, aFloat; "float"
0x1801465a6  call    ?newConstString@String@@SAPEAV1@PEBG@Z; String::newConstString(ushort const *)
0x1801465ab  mov     rbx, rax
0x1801465ae  lea     rcx, [rsp+38h+s]; ppref
0x1801465b3  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1801465b8  mov     [rsp+38h+s._p], rbx
0x1801465bd  lea     rcx, [rdi+40h]; ppref
0x1801465c1  mov     rdx, rbx; pref
0x1801465c4  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1801465c9  mov     rcx, [rdi]
0x1801465cc  mov     rax, [rcx+10h]
0x1801465d0  mov     rcx, rdi
0x1801465d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801465d8  mov     edx, r12d; dwFlags
0x1801465db  mov     ecx, r15d; cb
0x1801465de  call    ?_MemAlloc@@YAPEAX_KK@Z; _MemAlloc(unsigned __int64,ulong)
0x1801465e3  mov     rcx, rax; this
0x1801465e6  call    ??0Datatype_hexBinary@@QEAA@XZ; Datatype_hexBinary::Datatype_hexBinary(void)
0x1801465eb  mov     rdi, rax
0x1801465ee  mov     rdx, rax; pref
0x1801465f1  lea     rcx, ?c_hexBinary@SchemaDatatype@@2V?$_reference@VSchemaDatatype@@@@A; ppref
0x1801465f8  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1801465fd  lea     rcx, aHexbinary; "hexBinary"
0x180146604  call    ?newConstString@String@@SAPEAV1@PEBG@Z; String::newConstString(ushort const *)
0x180146609  mov     rbx, rax
0x18014660c  lea     rcx, [rsp+38h+s]; ppref
0x180146611  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x180146616  mov     [rsp+38h+s._p], rbx
0x18014661b  lea     rcx, [rdi+40h]; ppref
0x18014661f  mov     rdx, rbx; pref
0x180146622  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
  ... truncated ...
```
