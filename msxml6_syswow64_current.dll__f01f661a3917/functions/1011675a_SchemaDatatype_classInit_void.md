# SchemaDatatype::classInit(void)

- ea: `0x1011675a`
- end: `0x10117650`
- name: `?classInit@SchemaDatatype@@SGXXZ`
- size: `3830`
- prototype: `void __stdcall()`
- caller_count: `1`
- callee_count: `55`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x1010d5aa`

## callees

- `0x1003f548`
- `0x1003fba3`
- `0x1003fcda`
- `0x1003fd1f`
- `0x1003fd61`
- `0x10040c44`
- `0x10067bc0`
- `0x1006c080`
- `0x100779c5`
- `0x10077a1b`
- `0x1007818b`
- `0x10110b33`
- `0x10110b4f`
- `0x10110b6b`
- `0x10110b87`
- `0x10110bb4`
- `0x10110bdc`
- `0x10110bfd`
- `0x10110c2a`
- `0x10110c4b`
- `0x10110c6c`
- `0x10110c8d`
- `0x10110cae`
- `0x10110ccf`
- `0x10110cf0`
- `0x10110d18`
- `0x10110d40`
- `0x10110d68`
- `0x10110d89`
- `0x10110daa`
- `0x10110dcb`
- `0x10110dec`
- `0x10110e0d`
- `0x10110e2e`
- `0x10110e4f`
- `0x10110e77`
- `0x10110e98`
- `0x10110ec0`
- `0x10110ee8`
- `0x10110f09`
- `0x10110f2a`
- `0x10110f4b`
- `0x10110f78`
- `0x10110f99`
- `0x10110fba`
- `0x10110fe7`
- `0x1011100f`
- `0x1011106b`
- `0x10111085`
- `0x101110a6`

## string_xrefs

- `0x101172ce`: `token`
- `0x10116f4d`: `NMTOKEN`
- `0x101175bf`: `NMTOKENS`
- `0x1011680e`: `anyURI`

## pseudocode

```c
void __stdcall SchemaDatatype::classInit()
{
  Datatype_anyType *v0; // eax
  Datatype_anyType *v1; // edi
  String *v2; // esi
  Datatype_anyURI *v3; // eax
  Datatype_anyURI *v4; // edi
  String *v5; // esi
  Datatype_base64Binary *v6; // eax
  Datatype_base64Binary *v7; // edi
  String *v8; // esi
  Datatype_boolean *v9; // eax
  Datatype_boolean *v10; // edi
  String *v11; // esi
  Datatype_byte *v12; // eax
  Datatype_byte *v13; // edi
  String *v14; // esi
  Datatype_date *v15; // eax
  Datatype_date *v16; // edi
  String *v17; // esi
  Datatype_dateTime *v18; // eax
  Datatype_dateTime *v19; // edi
  String *v20; // esi
  Datatype_day *v21; // eax
  Datatype_day *v22; // edi
  String *v23; // esi
  Datatype_double *v24; // eax
  Datatype_double *v25; // edi
  String *v26; // esi
  Datatype_duration *v27; // eax
  Datatype_duration *v28; // edi
  String *v29; // esi
  Datatype_ENTITY *v30; // eax
  Datatype_ENTITY *v31; // edi
  String *v32; // esi
  Datatype_float *v33; // eax
  Datatype_float *v34; // edi
  String *v35; // esi
  Datatype_hexBinary *v36; // eax
  Datatype_hexBinary *v37; // edi
  String *v38; // esi
  Datatype_ID *v39; // eax
  Datatype_ID *v40; // edi
  String *v41; // esi
  Datatype_IDREF *v42; // eax
  Datatype_IDREF *v43; // edi
  String *v44; // esi
  Datatype_int *v45; // eax
  Datatype_int *v46; // edi
  String *v47; // esi
  Datatype_integer *v48; // eax
  Datatype_integer *v49; // edi
  String *v50; // esi
  Datatype_language *v51; // eax
  Datatype_language *v52; // edi
  String *v53; // esi
  Datatype_long *v54; // eax
  Datatype_long *v55; // edi
  String *v56; // esi
  Datatype_month *v57; // eax
  Datatype_month *v58; // edi
  String *v59; // esi
  Datatype_monthDay *v60; // eax
  Datatype_monthDay *v61; // edi
  String *v62; // esi
  Datatype_Name *v63; // eax
  Datatype_Name *v64; // edi
  String *v65; // esi
  Datatype_NCName *v66; // eax
  Datatype_NCName *v67; // edi
  String *v68; // esi
  Datatype_negativeInteger *v69; // eax
  Datatype_negativeInteger *v70; // edi
  String *v71; // esi
  Datatype_NMTOKEN *v72; // eax
  Datatype_NMTOKEN *v73; // edi
  String *v74; // esi
  Datatype_nonNegativeInteger *v75; // eax
  Datatype_nonNegativeInteger *v76; // edi
  String *v77; // esi
  Datatype_nonPositiveInteger *v78; // eax
  Datatype_nonPositiveInteger *v79; // edi
  String *v80; // esi
  Datatype_normalizedString *v81; // eax
  Datatype_normalizedString *v82; // edi
  String *v83; // esi
  Datatype_NOTATION *v84; // eax
  Datatype_NOTATION *v85; // edi
  String *v86; // esi
  Datatype_decimal *v87; // eax
  Datatype_decimal *v88; // edi
  String *v89; // esi
  Datatype_positiveInteger *v90; // eax
  Datatype_positiveInteger *v91; // edi
  String *v92; // esi
  Datatype_QName *v93; // eax
  Datatype_QName *v94; // edi
  String *v95; // esi
  Datatype_short *v96; // eax
  Datatype_short *v97; // edi
  String *v98; // esi
  Datatype_string *v99; // eax
  Datatype_string *v100; // edi
  String *v101; // esi
  Datatype_time *v102; // eax
  Datatype_time *v103; // edi
  String *v104; // esi
  Datatype_token *v105; // eax
  Datatype_token *v106; // edi
  String *v107; // esi
  Datatype_unsignedByte *v108; // eax
  Datatype_unsignedByte *v109; // edi
  String *v110; // esi
  Datatype_unsignedInt *v111; // eax
  Datatype_unsignedInt *v112; // edi
  String *v113; // esi
  Datatype_unsignedLong *v114; // eax
  Datatype_unsignedLong *v115; // edi
  String *v116; // esi
  Datatype_unsignedShort *v117; // eax
  Datatype_unsignedShort *v118; // edi
  String *v119; // esi
  Datatype_year *v120; // eax
  Datatype_year *v121; // edi
  String *v122; // esi
  Datatype_yearMonth *v123; // eax
  Datatype_yearMonth *v124; // edi
  String *v125; // esi
  SchemaDatatype *v126; // eax
  String *v127; // esi
  SchemaDatatype *v128; // eax
  String *v129; // esi
  SchemaDatatype *v130; // eax
  String *v131; // esi
  MutexLock lock; // [esp+10h] [ebp-20h] BYREF
  _reference<String> s; // [esp+14h] [ebp-1Ch] BYREF
  CPPEH_RECORD ms_exc; // [esp+18h] [ebp-18h]

  if ( !SchemaDatatype::c_NMTOKENS._p )
  {
    MutexLock::MutexLock(&lock, g_pMutex);
    s._p = 0;
    ms_exc.registration.TryLevel = 0;
    if ( !SchemaDatatype::c_NMTOKENS._p )
    {
      v0 = (Datatype_anyType *)_MemAlloc(0x60u, 12);
      v1 = Datatype_anyType::Datatype_anyType(v0);
      assign(&SchemaDatatype::c_anySimpleType._p, v1);
      v2 = String::newConstString(L"anySimpleType");
      release(&s._p);
      s._p = v2;
      assign(&v1->_name._p, v2);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_anyType *))v1->Release)(v1->Release, v1);
      v3 = (Datatype_anyURI *)_MemAlloc(0x60u, 12);
      v4 = Datatype_anyURI::Datatype_anyURI(v3);
      assign(&SchemaDatatype::c_anyURI._p, v4);
      v5 = String::newConstString(L"anyURI");
      release(&s._p);
      s._p = v5;
      assign(&v4->_name._p, v5);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_anyURI *))v4->Release)(v4->Release, v4);
      v6 = (Datatype_base64Binary *)_MemAlloc(0x60u, 12);
      v7 = Datatype_base64Binary::Datatype_base64Binary(v6);
      assign(&SchemaDatatype::c_base64Binary._p, v7);
      v8 = String::newConstString(L"base64Binary");
      release(&s._p);
      s._p = v8;
      assign(&v7->_name._p, v8);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_base64Binary *))v7->Release)(
        v7->Release,
        v7);
      v9 = (Datatype_boolean *)_MemAlloc(0x60u, 12);
      v10 = Datatype_boolean::Datatype_boolean(v9);
      assign(&SchemaDatatype::c_boolean._p, v10);
      v11 = String::newConstString(L"boolean");
      release(&s._p);
      s._p = v11;
      assign(&v10->_name._p, v11);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_boolean *))v10->Release)(v10->Release, v10);
      v12 = (Datatype_byte *)_MemAlloc(0x60u, 12);
      v13 = Datatype_byte::Datatype_byte(v12);
      assign(&SchemaDatatype::c_byte._p, v13);
      v14 = String::newConstString(L"byte");
      release(&s._p);
      s._p = v14;
      assign(&v13->_name._p, v14);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_byte *))v13->Release)(v13->Release, v13);
      v15 = (Datatype_date *)_MemAlloc(0x64u, 12);
      v16 = Datatype_date::Datatype_date(v15);
      assign(&SchemaDatatype::c_date._p, v16);
      v17 = String::newConstString(L"date");
      release(&s._p);
      s._p = v17;
      assign(&v16->_name._p, v17);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_date *))v16->Release)(v16->Release, v16);
      v18 = (Datatype_dateTime *)_MemAlloc(0x64u, 12);
      v19 = Datatype_dateTime::Datatype_dateTime(v18);
      assign(&SchemaDatatype::c_dateTime._p, v19);
      v20 = String::newConstString(L"dateTime");
      release(&s._p);
      s._p = v20;
      assign(&v19->_name._p, v20);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_dateTime *))v19->Release)(
        v19->Release,
        v19);
      v21 = (Datatype_day *)_MemAlloc(0x64u, 12);
      v22 = Datatype_day::Datatype_day(v21);
      assign(&SchemaDatatype::c_day._p, v22);
      v23 = String::newConstString(L"gDay");
      release(&s._p);
      s._p = v23;
      assign(&v22->_name._p, v23);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_day *))v22->Release)(v22->Release, v22);
      v24 = (Datatype_double *)_MemAlloc(0x60u, 12);
      v25 = Datatype_double::Datatype_double(v24);
      assign(&SchemaDatatype::c_double._p, v25);
      v26 = String::newConstString(L"double");
      release(&s._p);
      s._p = v26;
      assign(&v25->_name._p, v26);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_double *))v25->Release)(v25->Release, v25);
      v27 = (Datatype_duration *)_MemAlloc(0x60u, 12);
      v28 = Datatype_duration::Datatype_duration(v27);
      assign(&SchemaDatatype::c_duration._p, v28);
      v29 = String::newConstString(L"duration");
      release(&s._p);
      s._p = v29;
      assign(&v28->_name._p, v29);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_duration *))v28->Release)(
        v28->Release,
        v28);
      v30 = (Datatype_ENTITY *)_MemAlloc(0x64u, 12);
      v31 = Datatype_ENTITY::Datatype_ENTITY(v30);
      assign(&SchemaDatatype::c_ENTITY._p, v31);
      v32 = String::newConstString(L"ENTITY");
      release(&s._p);
      s._p = v32;
      assign(&v31->_name._p, v32);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_ENTITY *))v31->Release)(v31->Release, v31);
      v33 = (Datatype_float *)_MemAlloc(0x60u, 12);
      v34 = Datatype_float::Datatype_float(v33);
      assign(&SchemaDatatype::c_float._p, v34);
      v35 = String::newConstString(L"float");
      release(&s._p);
      s._p = v35;
      assign(&v34->_name._p, v35);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_float *))v34->Release)(v34->Release, v34);
      v36 = (Datatype_hexBinary *)_MemAlloc(0x60u, 12);
      v37 = Datatype_hexBinary::Datatype_hexBinary(v36);
      assign(&SchemaDatatype::c_hexBinary._p, v37);
      v38 = String::newConstString(L"hexBinary");
      release(&s._p);
      s._p = v38;
      assign(&v37->_name._p, v38);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_hexBinary *))v37->Release)(
        v37->Release,
        v37);
      v39 = (Datatype_ID *)_MemAlloc(0x64u, 12);
      v40 = Datatype_ID::Datatype_ID(v39);
      assign(&SchemaDatatype::c_ID._p, v40);
      v41 = String::newConstString(L"ID");
      release(&s._p);
      s._p = v41;
      assign(&v40->_name._p, v41);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_ID *))v40->Release)(v40->Release, v40);
      v42 = (Datatype_IDREF *)_MemAlloc(0x64u, 12);
      v43 = Datatype_IDREF::Datatype_IDREF(v42);
      assign(&SchemaDatatype::c_IDREF._p, v43);
      v44 = String::newConstString(L"IDREF");
      release(&s._p);
      s._p = v44;
      assign(&v43->_name._p, v44);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_IDREF *))v43->Release)(v43->Release, v43);
      v45 = (Datatype_int *)_MemAlloc(0x60u, 12);
      v46 = Datatype_int::Datatype_int(v45);
      assign(&SchemaDatatype::c_int._p, v46);
      v47 = String::newConstString(L"int");
      release(&s._p);
      s._p = v47;
      assign(&v46->_name._p, v47);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_int *))v46->Release)(v46->Release, v46);
      v48 = (Datatype_integer *)_MemAlloc(0x60u, 12);
      v49 = Datatype_integer::Datatype_integer(v48);
      assign(&SchemaDatatype::c_integer._p, v49);
      v50 = String::newConstString(L"integer");
      release(&s._p);
      s._p = v50;
      assign(&v49->_name._p, v50);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_integer *))v49->Release)(v49->Release, v49);
      v51 = (Datatype_language *)_MemAlloc(0x64u, 12);
      v52 = Datatype_language::Datatype_language(v51);
      assign(&SchemaDatatype::c_language._p, v52);
      v53 = String::newConstString(L"language");
      release(&s._p);
      s._p = v53;
      assign(&v52->_name._p, v53);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_language *))v52->Release)(
        v52->Release,
        v52);
      v54 = (Datatype_long *)_MemAlloc(0x60u, 12);
      v55 = Datatype_long::Datatype_long(v54);
      assign(&SchemaDatatype::c_long._p, v55);
      v56 = String::newConstString(L"long");
      release(&s._p);
      s._p = v56;
      assign(&v55->_name._p, v56);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_long *))v55->Release)(v55->Release, v55);
      v57 = (Datatype_month *)_MemAlloc(0x64u, 12);
      v58 = Datatype_month::Datatype_month(v57);
      assign(&SchemaDatatype::c_month._p, v58);
      v59 = String::newConstString(L"gMonth");
      release(&s._p);
      s._p = v59;
      assign(&v58->_name._p, v59);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_month *))v58->Release)(v58->Release, v58);
      v60 = (Datatype_monthDay *)_MemAlloc(0x64u, 12);
      v61 = Datatype_monthDay::Datatype_monthDay(v60);
      assign(&SchemaDatatype::c_monthDay._p, v61);
      v62 = String::newConstString(L"gMonthDay");
      release(&s._p);
      s._p = v62;
      assign(&v61->_name._p, v62);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_monthDay *))v61->Release)(
        v61->Release,
        v61);
      v63 = (Datatype_Name *)_MemAlloc(0x64u, 12);
      v64 = Datatype_Name::Datatype_Name(v63, HT_Name);
      assign(&SchemaDatatype::c_Name._p, v64);
      v65 = String::newConstString(L"Name");
      release(&s._p);
      s._p = v65;
      assign(&v64->_name._p, v65);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_Name *))v64->Release)(v64->Release, v64);
      v66 = (Datatype_NCName *)_MemAlloc(0x64u, 12);
      v67 = Datatype_NCName::Datatype_NCName(v66, HT_NCName);
      assign(&SchemaDatatype::c_NCName._p, v67);
      v68 = String::newConstString(L"NCName");
      release(&s._p);
      s._p = v68;
      assign(&v67->_name._p, v68);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_NCName *))v67->Release)(v67->Release, v67);
      v69 = (Datatype_negativeInteger *)_MemAlloc(0x60u, 12);
      v70 = Datatype_negativeInteger::Datatype_negativeInteger(v69);
      assign(&SchemaDatatype::c_negativeInteger._p, v70);
      v71 = String::newConstString(L"negativeInteger");
      release(&s._p);
      s._p = v71;
      assign(&v70->_name._p, v71);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_negativeInteger *))v70->Release)(
        v70->Release,
        v70);
      v72 = (Datatype_NMTOKEN *)_MemAlloc(0x64u, 12);
      v73 = Datatype_NMTOKEN::Datatype_NMTOKEN(v72);
      assign(&SchemaDatatype::c_NMTOKEN._p, v73);
      v74 = String::newConstString(L"NMTOKEN");
      release(&s._p);
      s._p = v74;
      assign(&v73->_name._p, v74);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_NMTOKEN *))v73->Release)(v73->Release, v73);
      v75 = (Datatype_nonNegativeInteger *)_MemAlloc(0x60u, 12);
      v76 = Datatype_nonNegativeInteger::Datatype_nonNegativeInteger(v75);
      assign(&SchemaDatatype::c_nonNegativeInteger._p, v76);
      v77 = String::newConstString(L"nonNegativeInteger");
      release(&s._p);
      s._p = v77;
      assign(&v76->_name._p, v77);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_nonNegativeInteger *))v76->Release)(
        v76->Release,
        v76);
      v78 = (Datatype_nonPositiveInteger *)_MemAlloc(0x60u, 12);
      v79 = Datatype_nonPositiveInteger::Datatype_nonPositiveInteger(v78);
      assign(&SchemaDatatype::c_nonPositiveInteger._p, v79);
      v80 = String::newConstString(L"nonPositiveInteger");
      release(&s._p);
      s._p = v80;
      assign(&v79->_name._p, v80);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_nonPositiveInteger *))v79->Release)(
        v79->Release,
        v79);
      v81 = (Datatype_normalizedString *)_MemAlloc(0x64u, 12);
      v82 = Datatype_normalizedString::Datatype_normalizedString(v81, HT_normalizedString);
      assign(&SchemaDatatype::c_normalizedString._p, v82);
      v83 = String::newConstString(L"normalizedString");
      release(&s._p);
      s._p = v83;
      assign(&v82->_name._p, v83);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_normalizedString *))v82->Release)(
        v82->Release,
        v82);
      v84 = (Datatype_NOTATION *)_MemAlloc(0x60u, 12);
      v85 = Datatype_NOTATION::Datatype_NOTATION(v84);
      assign(&SchemaDatatype::c_NOTATION._p, v85);
      v86 = String::newConstString(L"NOTATION");
      release(&s._p);
      s._p = v86;
      assign(&v85->_name._p, v86);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_NOTATION *))v85->Release)(
        v85->Release,
        v85);
      v87 = (Datatype_decimal *)_MemAlloc(0x60u, 12);
      v88 = Datatype_decimal::Datatype_decimal(v87);
      assign(&SchemaDatatype::c_decimal._p, v88);
      v89 = String::newConstString(L"decimal");
      release(&s._p);
      s._p = v89;
      assign(&v88->_name._p, v89);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_decimal *))v88->Release)(v88->Release, v88);
      v90 = (Datatype_positiveInteger *)_MemAlloc(0x60u, 12);
      v91 = Datatype_positiveInteger::Datatype_positiveInteger(v90);
      assign(&SchemaDatatype::c_positiveInteger._p, v91);
      v92 = String::newConstString(L"positiveInteger");
      release(&s._p);
      s._p = v92;
      assign(&v91->_name._p, v92);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_positiveInteger *))v91->Release)(
        v91->Release,
        v91);
      v93 = (Datatype_QName *)_MemAlloc(0x60u, 12);
      v94 = Datatype_QName::Datatype_QName(v93);
      assign(&SchemaDatatype::c_QName._p, v94);
      v95 = String::newConstString(L"QName");
      release(&s._p);
      s._p = v95;
      assign(&v94->_name._p, v95);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_QName *))v94->Release)(v94->Release, v94);
      v96 = (Datatype_short *)_MemAlloc(0x60u, 12);
      v97 = Datatype_short::Datatype_short(v96);
      assign(&SchemaDatatype::c_short._p, v97);
      v98 = String::newConstString(L"short");
      release(&s._p);
      s._p = v98;
      assign(&v97->_name._p, v98);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_short *))v97->Release)(v97->Release, v97);
      v99 = (Datatype_string *)_MemAlloc(0x64u, 12);
      v100 = Datatype_string::Datatype_string(v99, HT_string);
      assign(&SchemaDatatype::c_string._p, v100);
      v101 = String::newConstString(L"string");
      release(&s._p);
      s._p = v101;
      assign(&v100->_name._p, v101);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_string *))v100->Release)(
        v100->Release,
        v100);
      v102 = (Datatype_time *)_MemAlloc(0x64u, 12);
      v103 = Datatype_time::Datatype_time(v102);
      assign(&SchemaDatatype::c_time._p, v103);
      v104 = String::newConstString(L"time");
      release(&s._p);
      s._p = v104;
      assign(&v103->_name._p, v104);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_time *))v103->Release)(v103->Release, v103);
      v105 = (Datatype_token *)_MemAlloc(0x64u, 12);
      v106 = Datatype_token::Datatype_token(v105, HT_token);
      assign(&SchemaDatatype::c_token._p, v106);
      v107 = String::newConstString(L"token");
      release(&s._p);
      s._p = v107;
      assign(&v106->_name._p, v107);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_token *))v106->Release)(
        v106->Release,
        v106);
      v108 = (Datatype_unsignedByte *)_MemAlloc(0x60u, 12);
      v109 = Datatype_unsignedByte::Datatype_unsignedByte(v108);
      assign(&SchemaDatatype::c_unsignedByte._p, v109);
      v110 = String::newConstString(L"unsignedByte");
      release(&s._p);
      s._p = v110;
      assign(&v109->_name._p, v110);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_unsignedByte *))v109->Release)(
        v109->Release,
        v109);
      v111 = (Datatype_unsignedInt *)_MemAlloc(0x60u, 12);
      v112 = Datatype_unsignedInt::Datatype_unsignedInt(v111);
      assign(&SchemaDatatype::c_unsignedInt._p, v112);
      v113 = String::newConstString(L"unsignedInt");
      release(&s._p);
      s._p = v113;
      assign(&v112->_name._p, v113);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_unsignedInt *))v112->Release)(
        v112->Release,
        v112);
      v114 = (Datatype_unsignedLong *)_MemAlloc(0x60u, 12);
      v115 = Datatype_unsignedLong::Datatype_unsignedLong(v114);
      assign(&SchemaDatatype::c_unsignedLong._p, v115);
      v116 = String::newConstString(L"unsignedLong");
      release(&s._p);
      s._p = v116;
      assign(&v115->_name._p, v116);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_unsignedLong *))v115->Release)(
        v115->Release,
        v115);
      v117 = (Datatype_unsignedShort *)_MemAlloc(0x60u, 12);
      v118 = Datatype_unsignedShort::Datatype_unsignedShort(v117);
      assign(&SchemaDatatype::c_unsignedShort._p, v118);
      v119 = String::newConstString(L"unsignedShort");
      release(&s._p);
      s._p = v119;
      assign(&v118->_name._p, v119);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_unsignedShort *))v118->Release)(
        v118->Release,
        v118);
      v120 = (Datatype_year *)_MemAlloc(0x64u, 12);
      v121 = Datatype_year::Datatype_year(v120);
      assign(&SchemaDatatype::c_year._p, v121);
      v122 = String::newConstString(L"gYear");
      release(&s._p);
      s._p = v122;
      assign(&v121->_name._p, v122);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_year *))v121->Release)(v121->Release, v121);
      v123 = (Datatype_yearMonth *)_MemAlloc(0x64u, 12);
      v124 = Datatype_yearMonth::Datatype_yearMonth(v123);
      assign(&SchemaDatatype::c_yearMonth._p, v124);
      v125 = String::newConstString(L"gYearMonth");
      release(&s._p);
      s._p = v125;
      assign(&v124->_name._p, v125);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_yearMonth *))v124->Release)(
        v124->Release,
        v124);
      v126 = SchemaDatatype::DeriveByList(SchemaDatatype::c_ENTITY._p, 1, 0);
      assign(&SchemaDatatype::c_ENTITIES._p, v126);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), SchemaDatatype *))SchemaDatatype::c_ENTITIES._p->Release)(
        SchemaDatatype::c_ENTITIES._p->Release,
        SchemaDatatype::c_ENTITIES._p);
      v127 = String::newConstString(L"ENTITIES");
      release(&s._p);
      s._p = v127;
      assign(&SchemaDatatype::c_ENTITIES._p->_name._p, v127);
      v128 = SchemaDatatype::DeriveByList(SchemaDatatype::c_IDREF._p, 1, 0);
      assign(&SchemaDatatype::c_IDREFS._p, v128);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), SchemaDatatype *))SchemaDatatype::c_IDREFS._p->Release)(
        SchemaDatatype::c_IDREFS._p->Release,
        SchemaDatatype::c_IDREFS._p);
      v129 = String::newConstString(L"IDREFS");
      release(&s._p);
      s._p = v129;
      assign(&SchemaDatatype::c_IDREFS._p->_name._p, v129);
      v130 = SchemaDatatype::DeriveByList(SchemaDatatype::c_NMTOKEN._p, 1, 0);
      assign(&SchemaDatatype::c_NMTOKENS._p, v130);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), SchemaDatatype *))SchemaDatatype::c_NMTOKENS._p->Release)(
        SchemaDatatype::c_NMTOKENS._p->Release,
        SchemaDatatype::c_NMTOKENS._p);
      v131 = String::newConstString(L"NMTOKENS");
      release(&s._p);
      s._p = v131;
      assign(&SchemaDatatype::c_NMTOKENS._p->_name._p, v131);
    }
    ms_exc.registration.TryLevel = -2;
    release(&s._p);
    MutexLock::Release(&lock);
  }
}

```

## disassembly

```asm
0x1011675a  push    10h
0x1011675c  push    offset stru_1017B8B8
0x10116761  call    __SEH_prolog4
0x10116766  cmp     ?c_NMTOKENS@SchemaDatatype@@2V?$_reference@VSchemaDatatype@@@@A._p, 0; _reference<SchemaDatatype> SchemaDatatype::c_NMTOKENS ...
0x1011676d  jnz     loc_101175FD
0x10116773  push    ?g_pMutex@@3PAVCSMutex@@A; pMutex
0x10116779  lea     ecx, [ebp+lock]; this
0x1011677c  call    ??0MutexLock@@QAE@PAVMutex@@@Z; MutexLock::MutexLock(Mutex *)
0x10116781  mov     [ebp+s._p], 0
0x10116788  mov     [ebp+ms_exc.registration.TryLevel], 0
0x1011678f  cmp     ?c_NMTOKENS@SchemaDatatype@@2V?$_reference@VSchemaDatatype@@@@A._p, 0; _reference<SchemaDatatype> SchemaDatatype::c_NMTOKENS ...
0x10116796  jnz     loc_101175E6
0x1011679c  push    0Ch
0x1011679e  pop     edx; dwFlags
0x1011679f  push    60h ; '`'
0x101167a1  pop     ebx
0x101167a2  mov     ecx, ebx; cb
0x101167a4  call    ?_MemAlloc@@YGPAXIK@Z; _MemAlloc(uint,ulong)
0x101167a9  mov     ecx, eax; this
0x101167ab  call    ??0Datatype_anyType@@QAE@XZ; Datatype_anyType::Datatype_anyType(void)
0x101167b0  mov     edi, eax
0x101167b2  mov     edx, edi; pref
0x101167b4  mov     ecx, offset ?c_anySimpleType@SchemaDatatype@@2V?$_reference@VSchemaDatatype@@@@A; ppref
0x101167b9  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x101167be  mov     ecx, offset aAnysimpletype; "anySimpleType"
0x101167c3  call    ?newConstString@String@@SGPAV1@PBG@Z; String::newConstString(ushort const *)
0x101167c8  mov     esi, eax
0x101167ca  lea     ecx, [ebp+s]; ppref
0x101167cd  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x101167d2  mov     [ebp+s._p], esi
0x101167d5  lea     ecx, [edi+20h]; ppref
0x101167d8  mov     edx, esi; pref
0x101167da  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x101167df  mov     eax, [edi]
0x101167e1  push    edi
0x101167e2  mov     esi, [eax+8]
0x101167e5  mov     ecx, esi; this
0x101167e7  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x101167ed  call    esi
0x101167ef  push    0Ch
0x101167f1  pop     edx; dwFlags
0x101167f2  mov     ecx, ebx; cb
0x101167f4  call    ?_MemAlloc@@YGPAXIK@Z; _MemAlloc(uint,ulong)
0x101167f9  mov     ecx, eax; this
0x101167fb  call    ??0Datatype_anyURI@@QAE@XZ; Datatype_anyURI::Datatype_anyURI(void)
0x10116800  mov     edi, eax
0x10116802  mov     edx, edi; pref
0x10116804  mov     ecx, offset ?c_anyURI@SchemaDatatype@@2V?$_reference@VSchemaDatatype@@@@A; ppref
0x10116809  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x1011680e  mov     ecx, offset aAnyuri; "anyURI"
0x10116813  call    ?newConstString@String@@SGPAV1@PBG@Z; String::newConstString(ushort const *)
0x10116818  mov     esi, eax
0x1011681a  lea     ecx, [ebp+s]; ppref
0x1011681d  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x10116822  mov     [ebp+s._p], esi
0x10116825  lea     ecx, [edi+20h]; ppref
0x10116828  mov     edx, esi; pref
0x1011682a  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x1011682f  mov     eax, [edi]
0x10116831  push    edi
0x10116832  mov     esi, [eax+8]
0x10116835  mov     ecx, esi; this
0x10116837  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1011683d  call    esi
0x1011683f  push    0Ch
0x10116841  pop     edx; dwFlags
0x10116842  mov     ecx, ebx; cb
0x10116844  call    ?_MemAlloc@@YGPAXIK@Z; _MemAlloc(uint,ulong)
0x10116849  mov     ecx, eax; this
0x1011684b  call    ??0Datatype_base64Binary@@QAE@XZ; Datatype_base64Binary::Datatype_base64Binary(void)
0x10116850  mov     edi, eax
0x10116852  mov     edx, edi; pref
0x10116854  mov     ecx, offset ?c_base64Binary@SchemaDatatype@@2V?$_reference@VSchemaDatatype@@@@A; ppref
0x10116859  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x1011685e  mov     ecx, offset aBase64binary; "base64Binary"
0x10116863  call    ?newConstString@String@@SGPAV1@PBG@Z; String::newConstString(ushort const *)
0x10116868  mov     esi, eax
0x1011686a  lea     ecx, [ebp+s]; ppref
0x1011686d  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x10116872  mov     [ebp+s._p], esi
0x10116875  lea     ecx, [edi+20h]; ppref
0x10116878  mov     edx, esi; pref
0x1011687a  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x1011687f  mov     eax, [edi]
0x10116881  push    edi
0x10116882  mov     esi, [eax+8]
0x10116885  mov     ecx, esi; this
0x10116887  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1011688d  call    esi
0x1011688f  push    0Ch
0x10116891  pop     edx; dwFlags
0x10116892  mov     ecx, ebx; cb
0x10116894  call    ?_MemAlloc@@YGPAXIK@Z; _MemAlloc(uint,ulong)
0x10116899  mov     ecx, eax; this
0x1011689b  call    ??0Datatype_boolean@@QAE@XZ; Datatype_boolean::Datatype_boolean(void)
0x101168a0  mov     edi, eax
0x101168a2  mov     edx, edi; pref
0x101168a4  mov     ecx, offset ?c_boolean@SchemaDatatype@@2V?$_reference@VSchemaDatatype@@@@A; ppref
0x101168a9  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x101168ae  mov     ecx, offset aBoolean; "boolean"
0x101168b3  call    ?newConstString@String@@SGPAV1@PBG@Z; String::newConstString(ushort const *)
0x101168b8  mov     esi, eax
0x101168ba  lea     ecx, [ebp+s]; ppref
0x101168bd  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x101168c2  mov     [ebp+s._p], esi
0x101168c5  lea     ecx, [edi+20h]; ppref
0x101168c8  mov     edx, esi; pref
0x101168ca  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x101168cf  mov     eax, [edi]
0x101168d1  push    edi
0x101168d2  mov     esi, [eax+8]
0x101168d5  mov     ecx, esi; this
0x101168d7  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x101168dd  call    esi
0x101168df  push    0Ch
0x101168e1  pop     edx; dwFlags
0x101168e2  mov     ecx, ebx; cb
0x101168e4  call    ?_MemAlloc@@YGPAXIK@Z; _MemAlloc(uint,ulong)
0x101168e9  mov     ecx, eax; this
0x101168eb  call    ??0Datatype_byte@@QAE@XZ; Datatype_byte::Datatype_byte(void)
0x101168f0  mov     edi, eax
0x101168f2  mov     edx, edi; pref
0x101168f4  mov     ecx, offset ?c_byte@SchemaDatatype@@2V?$_reference@VSchemaDatatype@@@@A; ppref
0x101168f9  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x101168fe  mov     ecx, offset aByte; "byte"
0x10116903  call    ?newConstString@String@@SGPAV1@PBG@Z; String::newConstString(ushort const *)
0x10116908  mov     esi, eax
0x1011690a  lea     ecx, [ebp+s]; ppref
0x1011690d  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x10116912  mov     [ebp+s._p], esi
0x10116915  lea     ecx, [edi+20h]; ppref
0x10116918  mov     edx, esi; pref
0x1011691a  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x1011691f  mov     eax, [edi]
0x10116921  push    edi
0x10116922  mov     esi, [eax+8]
0x10116925  mov     ecx, esi; this
0x10116927  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1011692d  call    esi
0x1011692f  push    0Ch
0x10116931  pop     edx; dwFlags
0x10116932  push    64h ; 'd'
0x10116934  pop     ebx
0x10116935  mov     ecx, ebx; cb
0x10116937  call    ?_MemAlloc@@YGPAXIK@Z; _MemAlloc(uint,ulong)
0x1011693c  mov     ecx, eax; this
0x1011693e  call    ??0Datatype_date@@QAE@XZ; Datatype_date::Datatype_date(void)
0x10116943  mov     edi, eax
0x10116945  mov     edx, edi; pref
0x10116947  mov     ecx, offset ?c_date@SchemaDatatype@@2V?$_reference@VSchemaDatatype@@@@A; ppref
0x1011694c  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x10116951  mov     ecx, offset aDate; "date"
0x10116956  call    ?newConstString@String@@SGPAV1@PBG@Z; String::newConstString(ushort const *)
0x1011695b  mov     esi, eax
0x1011695d  lea     ecx, [ebp+s]; ppref
0x10116960  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x10116965  mov     [ebp+s._p], esi
0x10116968  lea     ecx, [edi+20h]; ppref
0x1011696b  mov     edx, esi; pref
0x1011696d  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x10116972  mov     eax, [edi]
0x10116974  push    edi
0x10116975  mov     esi, [eax+8]
0x10116978  mov     ecx, esi; this
0x1011697a  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10116980  call    esi
0x10116982  push    0Ch
0x10116984  pop     edx; dwFlags
0x10116985  mov     ecx, ebx; cb
0x10116987  call    ?_MemAlloc@@YGPAXIK@Z; _MemAlloc(uint,ulong)
0x1011698c  mov     ecx, eax; this
0x1011698e  call    ??0Datatype_dateTime@@QAE@XZ; Datatype_dateTime::Datatype_dateTime(void)
0x10116993  mov     edi, eax
0x10116995  mov     edx, edi; pref
0x10116997  mov     ecx, offset ?c_dateTime@SchemaDatatype@@2V?$_reference@VSchemaDatatype@@@@A; ppref
0x1011699c  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x101169a1  mov     ecx, offset aDatetime; "dateTime"
0x101169a6  call    ?newConstString@String@@SGPAV1@PBG@Z; String::newConstString(ushort const *)
0x101169ab  mov     esi, eax
0x101169ad  lea     ecx, [ebp+s]; ppref
0x101169b0  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x101169b5  mov     [ebp+s._p], esi
0x101169b8  lea     ecx, [edi+20h]; ppref
0x101169bb  mov     edx, esi; pref
0x101169bd  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x101169c2  mov     eax, [edi]
0x101169c4  push    edi
0x101169c5  mov     esi, [eax+8]
0x101169c8  mov     ecx, esi; this
0x101169ca  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x101169d0  call    esi
0x101169d2  push    0Ch
0x101169d4  pop     edx; dwFlags
0x101169d5  mov     ecx, ebx; cb
0x101169d7  call    ?_MemAlloc@@YGPAXIK@Z; _MemAlloc(uint,ulong)
0x101169dc  mov     ecx, eax; this
0x101169de  call    ??0Datatype_day@@QAE@XZ; Datatype_day::Datatype_day(void)
0x101169e3  mov     edi, eax
0x101169e5  mov     edx, edi; pref
0x101169e7  mov     ecx, offset ?c_day@SchemaDatatype@@2V?$_reference@VSchemaDatatype@@@@A; ppref
0x101169ec  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x101169f1  mov     ecx, offset aGday; "gDay"
0x101169f6  call    ?newConstString@String@@SGPAV1@PBG@Z; String::newConstString(ushort const *)
0x101169fb  mov     esi, eax
0x101169fd  lea     ecx, [ebp+s]; ppref
0x10116a00  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x10116a05  mov     [ebp+s._p], esi
0x10116a08  lea     ecx, [edi+20h]; ppref
0x10116a0b  mov     edx, esi; pref
0x10116a0d  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x10116a12  mov     eax, [edi]
0x10116a14  push    edi
0x10116a15  mov     esi, [eax+8]
0x10116a18  mov     ecx, esi; this
0x10116a1a  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10116a20  call    esi
0x10116a22  push    0Ch
0x10116a24  pop     edx; dwFlags
0x10116a25  push    60h ; '`'
0x10116a27  pop     ecx; cb
0x10116a28  call    ?_MemAlloc@@YGPAXIK@Z; _MemAlloc(uint,ulong)
0x10116a2d  mov     ecx, eax; this
0x10116a2f  call    ??0Datatype_double@@QAE@XZ; Datatype_double::Datatype_double(void)
0x10116a34  mov     edi, eax
0x10116a36  mov     edx, edi; pref
0x10116a38  mov     ecx, offset ?c_double@SchemaDatatype@@2V?$_reference@VSchemaDatatype@@@@A; ppref
0x10116a3d  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x10116a42  mov     ecx, offset aDouble; "double"
0x10116a47  call    ?newConstString@String@@SGPAV1@PBG@Z; String::newConstString(ushort const *)
0x10116a4c  mov     esi, eax
0x10116a4e  lea     ecx, [ebp+s]; ppref
0x10116a51  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x10116a56  mov     [ebp+s._p], esi
0x10116a59  lea     ecx, [edi+20h]; ppref
0x10116a5c  mov     edx, esi; pref
0x10116a5e  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x10116a63  mov     eax, [edi]
0x10116a65  push    edi
0x10116a66  mov     esi, [eax+8]
0x10116a69  mov     ecx, esi; this
0x10116a6b  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10116a71  call    esi
0x10116a73  push    0Ch
0x10116a75  pop     edx; dwFlags
0x10116a76  push    60h ; '`'
0x10116a78  pop     ecx; cb
0x10116a79  call    ?_MemAlloc@@YGPAXIK@Z; _MemAlloc(uint,ulong)
0x10116a7e  mov     ecx, eax; this
0x10116a80  call    ??0Datatype_duration@@QAE@XZ; Datatype_duration::Datatype_duration(void)
0x10116a85  mov     edi, eax
0x10116a87  mov     edx, edi; pref
0x10116a89  mov     ecx, offset ?c_duration@SchemaDatatype@@2V?$_reference@VSchemaDatatype@@@@A; ppref
0x10116a8e  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x10116a93  mov     ecx, offset aDuration; "duration"
0x10116a98  call    ?newConstString@String@@SGPAV1@PBG@Z; String::newConstString(ushort const *)
0x10116a9d  mov     esi, eax
0x10116a9f  lea     ecx, [ebp+s]; ppref
0x10116aa2  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x10116aa7  mov     [ebp+s._p], esi
0x10116aaa  lea     ecx, [edi+20h]; ppref
0x10116aad  mov     edx, esi; pref
0x10116aaf  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x10116ab4  mov     eax, [edi]
0x10116ab6  push    edi
0x10116ab7  mov     esi, [eax+8]
0x10116aba  mov     ecx, esi; this
0x10116abc  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10116ac2  call    esi
0x10116ac4  push    0Ch
0x10116ac6  pop     edx; dwFlags
0x10116ac7  mov     ecx, ebx; cb
0x10116ac9  call    ?_MemAlloc@@YGPAXIK@Z; _MemAlloc(uint,ulong)
0x10116ace  mov     ecx, eax; this
0x10116ad0  call    ??0Datatype_ENTITY@@QAE@XZ; Datatype_ENTITY::Datatype_ENTITY(void)
0x10116ad5  mov     edi, eax
0x10116ad7  mov     edx, edi; pref
0x10116ad9  mov     ecx, offset ?c_ENTITY@SchemaDatatype@@2V?$_reference@VSchemaDatatype@@@@A; ppref
0x10116ade  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x10116ae3  mov     ecx, offset aEntity; "ENTITY"
0x10116ae8  call    ?newConstString@String@@SGPAV1@PBG@Z; String::newConstString(ushort const *)
0x10116aed  mov     esi, eax
0x10116aef  lea     ecx, [ebp+s]; ppref
0x10116af2  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x10116af7  mov     [ebp+s._p], esi
0x10116afa  lea     ecx, [edi+20h]; ppref
0x10116afd  mov     edx, esi; pref
0x10116aff  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x10116b04  mov     eax, [edi]
0x10116b06  push    edi
0x10116b07  mov     esi, [eax+8]
0x10116b0a  mov     ecx, esi; this
0x10116b0c  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10116b12  call    esi
0x10116b14  push    0Ch
0x10116b16  pop     edx; dwFlags
0x10116b17  push    60h ; '`'
0x10116b19  pop     ecx; cb
0x10116b1a  call    ?_MemAlloc@@YGPAXIK@Z; _MemAlloc(uint,ulong)
0x10116b1f  mov     ecx, eax; this
0x10116b21  call    ??0Datatype_float@@QAE@XZ; Datatype_float::Datatype_float(void)
  ... truncated ...
```
