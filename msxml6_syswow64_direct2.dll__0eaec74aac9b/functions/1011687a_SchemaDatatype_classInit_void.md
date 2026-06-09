# SchemaDatatype::classInit(void)

- ea: `0x1011687a`
- end: `0x10117770`
- name: `?classInit@SchemaDatatype@@SGXXZ`
- size: `3830`
- prototype: `void __stdcall()`
- caller_count: `1`
- callee_count: `55`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x1010d6ca`

## callees

- `0x1003f4b8`
- `0x1003fb13`
- `0x1003fc4a`
- `0x1003fc8f`
- `0x1003fcd1`
- `0x10040bb4`
- `0x10067b20`
- `0x1006bff0`
- `0x100779f5`
- `0x10077a4b`
- `0x100781cb`
- `0x10110c53`
- `0x10110c6f`
- `0x10110c8b`
- `0x10110ca7`
- `0x10110cd4`
- `0x10110cfc`
- `0x10110d1d`
- `0x10110d4a`
- `0x10110d6b`
- `0x10110d8c`
- `0x10110dad`
- `0x10110dce`
- `0x10110def`
- `0x10110e10`
- `0x10110e38`
- `0x10110e60`
- `0x10110e88`
- `0x10110ea9`
- `0x10110eca`
- `0x10110eeb`
- `0x10110f0c`
- `0x10110f2d`
- `0x10110f4e`
- `0x10110f6f`
- `0x10110f97`
- `0x10110fb8`
- `0x10110fe0`
- `0x10111008`
- `0x10111029`
- `0x1011104a`
- `0x1011106b`
- `0x10111098`
- `0x101110b9`
- `0x101110da`
- `0x10111107`
- `0x1011112f`
- `0x1011118b`
- `0x101111a5`
- `0x101111c6`

## string_xrefs

- `0x101173ee`: `token`
- `0x1011706d`: `NMTOKEN`
- `0x101176df`: `NMTOKENS`
- `0x1011692e`: `anyURI`

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
      v0 = (Datatype_anyType *)_MemAlloc(0x60u, 0xCu);
      v1 = Datatype_anyType::Datatype_anyType(v0);
      assign(&SchemaDatatype::c_anySimpleType._p, v1);
      v2 = String::newConstString(L"anySimpleType");
      release(&s._p);
      s._p = v2;
      assign(&v1->_name._p, v2);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_anyType *))v1->Release)(v1->Release, v1);
      v3 = (Datatype_anyURI *)_MemAlloc(0x60u, 0xCu);
      v4 = Datatype_anyURI::Datatype_anyURI(v3);
      assign(&SchemaDatatype::c_anyURI._p, v4);
      v5 = String::newConstString(L"anyURI");
      release(&s._p);
      s._p = v5;
      assign(&v4->_name._p, v5);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_anyURI *))v4->Release)(v4->Release, v4);
      v6 = (Datatype_base64Binary *)_MemAlloc(0x60u, 0xCu);
      v7 = Datatype_base64Binary::Datatype_base64Binary(v6);
      assign(&SchemaDatatype::c_base64Binary._p, v7);
      v8 = String::newConstString(L"base64Binary");
      release(&s._p);
      s._p = v8;
      assign(&v7->_name._p, v8);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_base64Binary *))v7->Release)(
        v7->Release,
        v7);
      v9 = (Datatype_boolean *)_MemAlloc(0x60u, 0xCu);
      v10 = Datatype_boolean::Datatype_boolean(v9);
      assign(&SchemaDatatype::c_boolean._p, v10);
      v11 = String::newConstString(L"boolean");
      release(&s._p);
      s._p = v11;
      assign(&v10->_name._p, v11);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_boolean *))v10->Release)(v10->Release, v10);
      v12 = (Datatype_byte *)_MemAlloc(0x60u, 0xCu);
      v13 = Datatype_byte::Datatype_byte(v12);
      assign(&SchemaDatatype::c_byte._p, v13);
      v14 = String::newConstString(L"byte");
      release(&s._p);
      s._p = v14;
      assign(&v13->_name._p, v14);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_byte *))v13->Release)(v13->Release, v13);
      v15 = (Datatype_date *)_MemAlloc(0x64u, 0xCu);
      v16 = Datatype_date::Datatype_date(v15);
      assign(&SchemaDatatype::c_date._p, v16);
      v17 = String::newConstString(L"date");
      release(&s._p);
      s._p = v17;
      assign(&v16->_name._p, v17);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_date *))v16->Release)(v16->Release, v16);
      v18 = (Datatype_dateTime *)_MemAlloc(0x64u, 0xCu);
      v19 = Datatype_dateTime::Datatype_dateTime(v18);
      assign(&SchemaDatatype::c_dateTime._p, v19);
      v20 = String::newConstString(L"dateTime");
      release(&s._p);
      s._p = v20;
      assign(&v19->_name._p, v20);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_dateTime *))v19->Release)(
        v19->Release,
        v19);
      v21 = (Datatype_day *)_MemAlloc(0x64u, 0xCu);
      v22 = Datatype_day::Datatype_day(v21);
      assign(&SchemaDatatype::c_day._p, v22);
      v23 = String::newConstString(L"gDay");
      release(&s._p);
      s._p = v23;
      assign(&v22->_name._p, v23);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_day *))v22->Release)(v22->Release, v22);
      v24 = (Datatype_double *)_MemAlloc(0x60u, 0xCu);
      v25 = Datatype_double::Datatype_double(v24);
      assign(&SchemaDatatype::c_double._p, v25);
      v26 = String::newConstString(L"double");
      release(&s._p);
      s._p = v26;
      assign(&v25->_name._p, v26);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_double *))v25->Release)(v25->Release, v25);
      v27 = (Datatype_duration *)_MemAlloc(0x60u, 0xCu);
      v28 = Datatype_duration::Datatype_duration(v27);
      assign(&SchemaDatatype::c_duration._p, v28);
      v29 = String::newConstString(L"duration");
      release(&s._p);
      s._p = v29;
      assign(&v28->_name._p, v29);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_duration *))v28->Release)(
        v28->Release,
        v28);
      v30 = (Datatype_ENTITY *)_MemAlloc(0x64u, 0xCu);
      v31 = Datatype_ENTITY::Datatype_ENTITY(v30);
      assign(&SchemaDatatype::c_ENTITY._p, v31);
      v32 = String::newConstString(L"ENTITY");
      release(&s._p);
      s._p = v32;
      assign(&v31->_name._p, v32);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_ENTITY *))v31->Release)(v31->Release, v31);
      v33 = (Datatype_float *)_MemAlloc(0x60u, 0xCu);
      v34 = Datatype_float::Datatype_float(v33);
      assign(&SchemaDatatype::c_float._p, v34);
      v35 = String::newConstString(L"float");
      release(&s._p);
      s._p = v35;
      assign(&v34->_name._p, v35);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_float *))v34->Release)(v34->Release, v34);
      v36 = (Datatype_hexBinary *)_MemAlloc(0x60u, 0xCu);
      v37 = Datatype_hexBinary::Datatype_hexBinary(v36);
      assign(&SchemaDatatype::c_hexBinary._p, v37);
      v38 = String::newConstString(L"hexBinary");
      release(&s._p);
      s._p = v38;
      assign(&v37->_name._p, v38);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_hexBinary *))v37->Release)(
        v37->Release,
        v37);
      v39 = (Datatype_ID *)_MemAlloc(0x64u, 0xCu);
      v40 = Datatype_ID::Datatype_ID(v39);
      assign(&SchemaDatatype::c_ID._p, v40);
      v41 = String::newConstString(L"ID");
      release(&s._p);
      s._p = v41;
      assign(&v40->_name._p, v41);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_ID *))v40->Release)(v40->Release, v40);
      v42 = (Datatype_IDREF *)_MemAlloc(0x64u, 0xCu);
      v43 = Datatype_IDREF::Datatype_IDREF(v42);
      assign(&SchemaDatatype::c_IDREF._p, v43);
      v44 = String::newConstString(L"IDREF");
      release(&s._p);
      s._p = v44;
      assign(&v43->_name._p, v44);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_IDREF *))v43->Release)(v43->Release, v43);
      v45 = (Datatype_int *)_MemAlloc(0x60u, 0xCu);
      v46 = Datatype_int::Datatype_int(v45);
      assign(&SchemaDatatype::c_int._p, v46);
      v47 = String::newConstString(L"int");
      release(&s._p);
      s._p = v47;
      assign(&v46->_name._p, v47);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_int *))v46->Release)(v46->Release, v46);
      v48 = (Datatype_integer *)_MemAlloc(0x60u, 0xCu);
      v49 = Datatype_integer::Datatype_integer(v48);
      assign(&SchemaDatatype::c_integer._p, v49);
      v50 = String::newConstString(L"integer");
      release(&s._p);
      s._p = v50;
      assign(&v49->_name._p, v50);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_integer *))v49->Release)(v49->Release, v49);
      v51 = (Datatype_language *)_MemAlloc(0x64u, 0xCu);
      v52 = Datatype_language::Datatype_language(v51);
      assign(&SchemaDatatype::c_language._p, v52);
      v53 = String::newConstString(L"language");
      release(&s._p);
      s._p = v53;
      assign(&v52->_name._p, v53);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_language *))v52->Release)(
        v52->Release,
        v52);
      v54 = (Datatype_long *)_MemAlloc(0x60u, 0xCu);
      v55 = Datatype_long::Datatype_long(v54);
      assign(&SchemaDatatype::c_long._p, v55);
      v56 = String::newConstString(L"long");
      release(&s._p);
      s._p = v56;
      assign(&v55->_name._p, v56);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_long *))v55->Release)(v55->Release, v55);
      v57 = (Datatype_month *)_MemAlloc(0x64u, 0xCu);
      v58 = Datatype_month::Datatype_month(v57);
      assign(&SchemaDatatype::c_month._p, v58);
      v59 = String::newConstString(L"gMonth");
      release(&s._p);
      s._p = v59;
      assign(&v58->_name._p, v59);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_month *))v58->Release)(v58->Release, v58);
      v60 = (Datatype_monthDay *)_MemAlloc(0x64u, 0xCu);
      v61 = Datatype_monthDay::Datatype_monthDay(v60);
      assign(&SchemaDatatype::c_monthDay._p, v61);
      v62 = String::newConstString(L"gMonthDay");
      release(&s._p);
      s._p = v62;
      assign(&v61->_name._p, v62);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_monthDay *))v61->Release)(
        v61->Release,
        v61);
      v63 = (Datatype_Name *)_MemAlloc(0x64u, 0xCu);
      v64 = Datatype_Name::Datatype_Name(v63, HT_Name);
      assign(&SchemaDatatype::c_Name._p, v64);
      v65 = String::newConstString(L"Name");
      release(&s._p);
      s._p = v65;
      assign(&v64->_name._p, v65);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_Name *))v64->Release)(v64->Release, v64);
      v66 = (Datatype_NCName *)_MemAlloc(0x64u, 0xCu);
      v67 = Datatype_NCName::Datatype_NCName(v66, HT_NCName);
      assign(&SchemaDatatype::c_NCName._p, v67);
      v68 = String::newConstString(L"NCName");
      release(&s._p);
      s._p = v68;
      assign(&v67->_name._p, v68);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_NCName *))v67->Release)(v67->Release, v67);
      v69 = (Datatype_negativeInteger *)_MemAlloc(0x60u, 0xCu);
      v70 = Datatype_negativeInteger::Datatype_negativeInteger(v69);
      assign(&SchemaDatatype::c_negativeInteger._p, v70);
      v71 = String::newConstString(L"negativeInteger");
      release(&s._p);
      s._p = v71;
      assign(&v70->_name._p, v71);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_negativeInteger *))v70->Release)(
        v70->Release,
        v70);
      v72 = (Datatype_NMTOKEN *)_MemAlloc(0x64u, 0xCu);
      v73 = Datatype_NMTOKEN::Datatype_NMTOKEN(v72);
      assign(&SchemaDatatype::c_NMTOKEN._p, v73);
      v74 = String::newConstString(L"NMTOKEN");
      release(&s._p);
      s._p = v74;
      assign(&v73->_name._p, v74);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_NMTOKEN *))v73->Release)(v73->Release, v73);
      v75 = (Datatype_nonNegativeInteger *)_MemAlloc(0x60u, 0xCu);
      v76 = Datatype_nonNegativeInteger::Datatype_nonNegativeInteger(v75);
      assign(&SchemaDatatype::c_nonNegativeInteger._p, v76);
      v77 = String::newConstString(L"nonNegativeInteger");
      release(&s._p);
      s._p = v77;
      assign(&v76->_name._p, v77);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_nonNegativeInteger *))v76->Release)(
        v76->Release,
        v76);
      v78 = (Datatype_nonPositiveInteger *)_MemAlloc(0x60u, 0xCu);
      v79 = Datatype_nonPositiveInteger::Datatype_nonPositiveInteger(v78);
      assign(&SchemaDatatype::c_nonPositiveInteger._p, v79);
      v80 = String::newConstString(L"nonPositiveInteger");
      release(&s._p);
      s._p = v80;
      assign(&v79->_name._p, v80);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_nonPositiveInteger *))v79->Release)(
        v79->Release,
        v79);
      v81 = (Datatype_normalizedString *)_MemAlloc(0x64u, 0xCu);
      v82 = Datatype_normalizedString::Datatype_normalizedString(v81, HT_normalizedString);
      assign(&SchemaDatatype::c_normalizedString._p, v82);
      v83 = String::newConstString(L"normalizedString");
      release(&s._p);
      s._p = v83;
      assign(&v82->_name._p, v83);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_normalizedString *))v82->Release)(
        v82->Release,
        v82);
      v84 = (Datatype_NOTATION *)_MemAlloc(0x60u, 0xCu);
      v85 = Datatype_NOTATION::Datatype_NOTATION(v84);
      assign(&SchemaDatatype::c_NOTATION._p, v85);
      v86 = String::newConstString(L"NOTATION");
      release(&s._p);
      s._p = v86;
      assign(&v85->_name._p, v86);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_NOTATION *))v85->Release)(
        v85->Release,
        v85);
      v87 = (Datatype_decimal *)_MemAlloc(0x60u, 0xCu);
      v88 = Datatype_decimal::Datatype_decimal(v87);
      assign(&SchemaDatatype::c_decimal._p, v88);
      v89 = String::newConstString(L"decimal");
      release(&s._p);
      s._p = v89;
      assign(&v88->_name._p, v89);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_decimal *))v88->Release)(v88->Release, v88);
      v90 = (Datatype_positiveInteger *)_MemAlloc(0x60u, 0xCu);
      v91 = Datatype_positiveInteger::Datatype_positiveInteger(v90);
      assign(&SchemaDatatype::c_positiveInteger._p, v91);
      v92 = String::newConstString(L"positiveInteger");
      release(&s._p);
      s._p = v92;
      assign(&v91->_name._p, v92);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_positiveInteger *))v91->Release)(
        v91->Release,
        v91);
      v93 = (Datatype_QName *)_MemAlloc(0x60u, 0xCu);
      v94 = Datatype_QName::Datatype_QName(v93);
      assign(&SchemaDatatype::c_QName._p, v94);
      v95 = String::newConstString(L"QName");
      release(&s._p);
      s._p = v95;
      assign(&v94->_name._p, v95);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_QName *))v94->Release)(v94->Release, v94);
      v96 = (Datatype_short *)_MemAlloc(0x60u, 0xCu);
      v97 = Datatype_short::Datatype_short(v96);
      assign(&SchemaDatatype::c_short._p, v97);
      v98 = String::newConstString(L"short");
      release(&s._p);
      s._p = v98;
      assign(&v97->_name._p, v98);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_short *))v97->Release)(v97->Release, v97);
      v99 = (Datatype_string *)_MemAlloc(0x64u, 0xCu);
      v100 = Datatype_string::Datatype_string(v99, HT_string);
      assign(&SchemaDatatype::c_string._p, v100);
      v101 = String::newConstString(L"string");
      release(&s._p);
      s._p = v101;
      assign(&v100->_name._p, v101);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_string *))v100->Release)(
        v100->Release,
        v100);
      v102 = (Datatype_time *)_MemAlloc(0x64u, 0xCu);
      v103 = Datatype_time::Datatype_time(v102);
      assign(&SchemaDatatype::c_time._p, v103);
      v104 = String::newConstString(L"time");
      release(&s._p);
      s._p = v104;
      assign(&v103->_name._p, v104);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_time *))v103->Release)(v103->Release, v103);
      v105 = (Datatype_token *)_MemAlloc(0x64u, 0xCu);
      v106 = Datatype_token::Datatype_token(v105, HT_token);
      assign(&SchemaDatatype::c_token._p, v106);
      v107 = String::newConstString(L"token");
      release(&s._p);
      s._p = v107;
      assign(&v106->_name._p, v107);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_token *))v106->Release)(
        v106->Release,
        v106);
      v108 = (Datatype_unsignedByte *)_MemAlloc(0x60u, 0xCu);
      v109 = Datatype_unsignedByte::Datatype_unsignedByte(v108);
      assign(&SchemaDatatype::c_unsignedByte._p, v109);
      v110 = String::newConstString(L"unsignedByte");
      release(&s._p);
      s._p = v110;
      assign(&v109->_name._p, v110);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_unsignedByte *))v109->Release)(
        v109->Release,
        v109);
      v111 = (Datatype_unsignedInt *)_MemAlloc(0x60u, 0xCu);
      v112 = Datatype_unsignedInt::Datatype_unsignedInt(v111);
      assign(&SchemaDatatype::c_unsignedInt._p, v112);
      v113 = String::newConstString(L"unsignedInt");
      release(&s._p);
      s._p = v113;
      assign(&v112->_name._p, v113);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_unsignedInt *))v112->Release)(
        v112->Release,
        v112);
      v114 = (Datatype_unsignedLong *)_MemAlloc(0x60u, 0xCu);
      v115 = Datatype_unsignedLong::Datatype_unsignedLong(v114);
      assign(&SchemaDatatype::c_unsignedLong._p, v115);
      v116 = String::newConstString(L"unsignedLong");
      release(&s._p);
      s._p = v116;
      assign(&v115->_name._p, v116);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_unsignedLong *))v115->Release)(
        v115->Release,
        v115);
      v117 = (Datatype_unsignedShort *)_MemAlloc(0x60u, 0xCu);
      v118 = Datatype_unsignedShort::Datatype_unsignedShort(v117);
      assign(&SchemaDatatype::c_unsignedShort._p, v118);
      v119 = String::newConstString(L"unsignedShort");
      release(&s._p);
      s._p = v119;
      assign(&v118->_name._p, v119);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_unsignedShort *))v118->Release)(
        v118->Release,
        v118);
      v120 = (Datatype_year *)_MemAlloc(0x64u, 0xCu);
      v121 = Datatype_year::Datatype_year(v120);
      assign(&SchemaDatatype::c_year._p, v121);
      v122 = String::newConstString(L"gYear");
      release(&s._p);
      s._p = v122;
      assign(&v121->_name._p, v122);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Datatype_year *))v121->Release)(v121->Release, v121);
      v123 = (Datatype_yearMonth *)_MemAlloc(0x64u, 0xCu);
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
0x1011687a  push    10h
0x1011687c  push    offset stru_1017B9A8
0x10116881  call    __SEH_prolog4
0x10116886  cmp     ?c_NMTOKENS@SchemaDatatype@@2V?$_reference@VSchemaDatatype@@@@A._p, 0; _reference<SchemaDatatype> SchemaDatatype::c_NMTOKENS ...
0x1011688d  jnz     loc_1011771D
0x10116893  push    ?g_pMutex@@3PAVCSMutex@@A; pMutex
0x10116899  lea     ecx, [ebp+lock]; this
0x1011689c  call    ??0MutexLock@@QAE@PAVMutex@@@Z; MutexLock::MutexLock(Mutex *)
0x101168a1  mov     [ebp+s._p], 0
0x101168a8  mov     [ebp+ms_exc.registration.TryLevel], 0
0x101168af  cmp     ?c_NMTOKENS@SchemaDatatype@@2V?$_reference@VSchemaDatatype@@@@A._p, 0; _reference<SchemaDatatype> SchemaDatatype::c_NMTOKENS ...
0x101168b6  jnz     loc_10117706
0x101168bc  push    0Ch
0x101168be  pop     edx; dwFlags
0x101168bf  push    60h ; '`'
0x101168c1  pop     ebx
0x101168c2  mov     ecx, ebx; cb
0x101168c4  call    ?_MemAlloc@@YGPAXIK@Z; _MemAlloc(uint,ulong)
0x101168c9  mov     ecx, eax; this
0x101168cb  call    ??0Datatype_anyType@@QAE@XZ; Datatype_anyType::Datatype_anyType(void)
0x101168d0  mov     edi, eax
0x101168d2  mov     edx, edi; pref
0x101168d4  mov     ecx, offset ?c_anySimpleType@SchemaDatatype@@2V?$_reference@VSchemaDatatype@@@@A; ppref
0x101168d9  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x101168de  mov     ecx, offset aAnysimpletype; "anySimpleType"
0x101168e3  call    ?newConstString@String@@SGPAV1@PBG@Z; String::newConstString(ushort const *)
0x101168e8  mov     esi, eax
0x101168ea  lea     ecx, [ebp+s]; ppref
0x101168ed  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x101168f2  mov     [ebp+s._p], esi
0x101168f5  lea     ecx, [edi+20h]; ppref
0x101168f8  mov     edx, esi; pref
0x101168fa  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x101168ff  mov     eax, [edi]
0x10116901  push    edi
0x10116902  mov     esi, [eax+8]
0x10116905  mov     ecx, esi; this
0x10116907  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1011690d  call    esi
0x1011690f  push    0Ch
0x10116911  pop     edx; dwFlags
0x10116912  mov     ecx, ebx; cb
0x10116914  call    ?_MemAlloc@@YGPAXIK@Z; _MemAlloc(uint,ulong)
0x10116919  mov     ecx, eax; this
0x1011691b  call    ??0Datatype_anyURI@@QAE@XZ; Datatype_anyURI::Datatype_anyURI(void)
0x10116920  mov     edi, eax
0x10116922  mov     edx, edi; pref
0x10116924  mov     ecx, offset ?c_anyURI@SchemaDatatype@@2V?$_reference@VSchemaDatatype@@@@A; ppref
0x10116929  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x1011692e  mov     ecx, offset aAnyuri; "anyURI"
0x10116933  call    ?newConstString@String@@SGPAV1@PBG@Z; String::newConstString(ushort const *)
0x10116938  mov     esi, eax
0x1011693a  lea     ecx, [ebp+s]; ppref
0x1011693d  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x10116942  mov     [ebp+s._p], esi
0x10116945  lea     ecx, [edi+20h]; ppref
0x10116948  mov     edx, esi; pref
0x1011694a  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x1011694f  mov     eax, [edi]
0x10116951  push    edi
0x10116952  mov     esi, [eax+8]
0x10116955  mov     ecx, esi; this
0x10116957  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1011695d  call    esi
0x1011695f  push    0Ch
0x10116961  pop     edx; dwFlags
0x10116962  mov     ecx, ebx; cb
0x10116964  call    ?_MemAlloc@@YGPAXIK@Z; _MemAlloc(uint,ulong)
0x10116969  mov     ecx, eax; this
0x1011696b  call    ??0Datatype_base64Binary@@QAE@XZ; Datatype_base64Binary::Datatype_base64Binary(void)
0x10116970  mov     edi, eax
0x10116972  mov     edx, edi; pref
0x10116974  mov     ecx, offset ?c_base64Binary@SchemaDatatype@@2V?$_reference@VSchemaDatatype@@@@A; ppref
0x10116979  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x1011697e  mov     ecx, offset aBase64binary; "base64Binary"
0x10116983  call    ?newConstString@String@@SGPAV1@PBG@Z; String::newConstString(ushort const *)
0x10116988  mov     esi, eax
0x1011698a  lea     ecx, [ebp+s]; ppref
0x1011698d  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x10116992  mov     [ebp+s._p], esi
0x10116995  lea     ecx, [edi+20h]; ppref
0x10116998  mov     edx, esi; pref
0x1011699a  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x1011699f  mov     eax, [edi]
0x101169a1  push    edi
0x101169a2  mov     esi, [eax+8]
0x101169a5  mov     ecx, esi; this
0x101169a7  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x101169ad  call    esi
0x101169af  push    0Ch
0x101169b1  pop     edx; dwFlags
0x101169b2  mov     ecx, ebx; cb
0x101169b4  call    ?_MemAlloc@@YGPAXIK@Z; _MemAlloc(uint,ulong)
0x101169b9  mov     ecx, eax; this
0x101169bb  call    ??0Datatype_boolean@@QAE@XZ; Datatype_boolean::Datatype_boolean(void)
0x101169c0  mov     edi, eax
0x101169c2  mov     edx, edi; pref
0x101169c4  mov     ecx, offset ?c_boolean@SchemaDatatype@@2V?$_reference@VSchemaDatatype@@@@A; ppref
0x101169c9  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x101169ce  mov     ecx, offset aBoolean; "boolean"
0x101169d3  call    ?newConstString@String@@SGPAV1@PBG@Z; String::newConstString(ushort const *)
0x101169d8  mov     esi, eax
0x101169da  lea     ecx, [ebp+s]; ppref
0x101169dd  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x101169e2  mov     [ebp+s._p], esi
0x101169e5  lea     ecx, [edi+20h]; ppref
0x101169e8  mov     edx, esi; pref
0x101169ea  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x101169ef  mov     eax, [edi]
0x101169f1  push    edi
0x101169f2  mov     esi, [eax+8]
0x101169f5  mov     ecx, esi; this
0x101169f7  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x101169fd  call    esi
0x101169ff  push    0Ch
0x10116a01  pop     edx; dwFlags
0x10116a02  mov     ecx, ebx; cb
0x10116a04  call    ?_MemAlloc@@YGPAXIK@Z; _MemAlloc(uint,ulong)
0x10116a09  mov     ecx, eax; this
0x10116a0b  call    ??0Datatype_byte@@QAE@XZ; Datatype_byte::Datatype_byte(void)
0x10116a10  mov     edi, eax
0x10116a12  mov     edx, edi; pref
0x10116a14  mov     ecx, offset ?c_byte@SchemaDatatype@@2V?$_reference@VSchemaDatatype@@@@A; ppref
0x10116a19  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x10116a1e  mov     ecx, offset aByte; "byte"
0x10116a23  call    ?newConstString@String@@SGPAV1@PBG@Z; String::newConstString(ushort const *)
0x10116a28  mov     esi, eax
0x10116a2a  lea     ecx, [ebp+s]; ppref
0x10116a2d  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x10116a32  mov     [ebp+s._p], esi
0x10116a35  lea     ecx, [edi+20h]; ppref
0x10116a38  mov     edx, esi; pref
0x10116a3a  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x10116a3f  mov     eax, [edi]
0x10116a41  push    edi
0x10116a42  mov     esi, [eax+8]
0x10116a45  mov     ecx, esi; this
0x10116a47  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10116a4d  call    esi
0x10116a4f  push    0Ch
0x10116a51  pop     edx; dwFlags
0x10116a52  push    64h ; 'd'
0x10116a54  pop     ebx
0x10116a55  mov     ecx, ebx; cb
0x10116a57  call    ?_MemAlloc@@YGPAXIK@Z; _MemAlloc(uint,ulong)
0x10116a5c  mov     ecx, eax; this
0x10116a5e  call    ??0Datatype_date@@QAE@XZ; Datatype_date::Datatype_date(void)
0x10116a63  mov     edi, eax
0x10116a65  mov     edx, edi; pref
0x10116a67  mov     ecx, offset ?c_date@SchemaDatatype@@2V?$_reference@VSchemaDatatype@@@@A; ppref
0x10116a6c  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x10116a71  mov     ecx, offset aDate; "date"
0x10116a76  call    ?newConstString@String@@SGPAV1@PBG@Z; String::newConstString(ushort const *)
0x10116a7b  mov     esi, eax
0x10116a7d  lea     ecx, [ebp+s]; ppref
0x10116a80  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x10116a85  mov     [ebp+s._p], esi
0x10116a88  lea     ecx, [edi+20h]; ppref
0x10116a8b  mov     edx, esi; pref
0x10116a8d  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x10116a92  mov     eax, [edi]
0x10116a94  push    edi
0x10116a95  mov     esi, [eax+8]
0x10116a98  mov     ecx, esi; this
0x10116a9a  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10116aa0  call    esi
0x10116aa2  push    0Ch
0x10116aa4  pop     edx; dwFlags
0x10116aa5  mov     ecx, ebx; cb
0x10116aa7  call    ?_MemAlloc@@YGPAXIK@Z; _MemAlloc(uint,ulong)
0x10116aac  mov     ecx, eax; this
0x10116aae  call    ??0Datatype_dateTime@@QAE@XZ; Datatype_dateTime::Datatype_dateTime(void)
0x10116ab3  mov     edi, eax
0x10116ab5  mov     edx, edi; pref
0x10116ab7  mov     ecx, offset ?c_dateTime@SchemaDatatype@@2V?$_reference@VSchemaDatatype@@@@A; ppref
0x10116abc  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x10116ac1  mov     ecx, offset aDatetime; "dateTime"
0x10116ac6  call    ?newConstString@String@@SGPAV1@PBG@Z; String::newConstString(ushort const *)
0x10116acb  mov     esi, eax
0x10116acd  lea     ecx, [ebp+s]; ppref
0x10116ad0  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x10116ad5  mov     [ebp+s._p], esi
0x10116ad8  lea     ecx, [edi+20h]; ppref
0x10116adb  mov     edx, esi; pref
0x10116add  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x10116ae2  mov     eax, [edi]
0x10116ae4  push    edi
0x10116ae5  mov     esi, [eax+8]
0x10116ae8  mov     ecx, esi; this
0x10116aea  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10116af0  call    esi
0x10116af2  push    0Ch
0x10116af4  pop     edx; dwFlags
0x10116af5  mov     ecx, ebx; cb
0x10116af7  call    ?_MemAlloc@@YGPAXIK@Z; _MemAlloc(uint,ulong)
0x10116afc  mov     ecx, eax; this
0x10116afe  call    ??0Datatype_day@@QAE@XZ; Datatype_day::Datatype_day(void)
0x10116b03  mov     edi, eax
0x10116b05  mov     edx, edi; pref
0x10116b07  mov     ecx, offset ?c_day@SchemaDatatype@@2V?$_reference@VSchemaDatatype@@@@A; ppref
0x10116b0c  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x10116b11  mov     ecx, offset aGday; "gDay"
0x10116b16  call    ?newConstString@String@@SGPAV1@PBG@Z; String::newConstString(ushort const *)
0x10116b1b  mov     esi, eax
0x10116b1d  lea     ecx, [ebp+s]; ppref
0x10116b20  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x10116b25  mov     [ebp+s._p], esi
0x10116b28  lea     ecx, [edi+20h]; ppref
0x10116b2b  mov     edx, esi; pref
0x10116b2d  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x10116b32  mov     eax, [edi]
0x10116b34  push    edi
0x10116b35  mov     esi, [eax+8]
0x10116b38  mov     ecx, esi; this
0x10116b3a  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10116b40  call    esi
0x10116b42  push    0Ch
0x10116b44  pop     edx; dwFlags
0x10116b45  push    60h ; '`'
0x10116b47  pop     ecx; cb
0x10116b48  call    ?_MemAlloc@@YGPAXIK@Z; _MemAlloc(uint,ulong)
0x10116b4d  mov     ecx, eax; this
0x10116b4f  call    ??0Datatype_double@@QAE@XZ; Datatype_double::Datatype_double(void)
0x10116b54  mov     edi, eax
0x10116b56  mov     edx, edi; pref
0x10116b58  mov     ecx, offset ?c_double@SchemaDatatype@@2V?$_reference@VSchemaDatatype@@@@A; ppref
0x10116b5d  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x10116b62  mov     ecx, offset aDouble; "double"
0x10116b67  call    ?newConstString@String@@SGPAV1@PBG@Z; String::newConstString(ushort const *)
0x10116b6c  mov     esi, eax
0x10116b6e  lea     ecx, [ebp+s]; ppref
0x10116b71  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x10116b76  mov     [ebp+s._p], esi
0x10116b79  lea     ecx, [edi+20h]; ppref
0x10116b7c  mov     edx, esi; pref
0x10116b7e  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x10116b83  mov     eax, [edi]
0x10116b85  push    edi
0x10116b86  mov     esi, [eax+8]
0x10116b89  mov     ecx, esi; this
0x10116b8b  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10116b91  call    esi
0x10116b93  push    0Ch
0x10116b95  pop     edx; dwFlags
0x10116b96  push    60h ; '`'
0x10116b98  pop     ecx; cb
0x10116b99  call    ?_MemAlloc@@YGPAXIK@Z; _MemAlloc(uint,ulong)
0x10116b9e  mov     ecx, eax; this
0x10116ba0  call    ??0Datatype_duration@@QAE@XZ; Datatype_duration::Datatype_duration(void)
0x10116ba5  mov     edi, eax
0x10116ba7  mov     edx, edi; pref
0x10116ba9  mov     ecx, offset ?c_duration@SchemaDatatype@@2V?$_reference@VSchemaDatatype@@@@A; ppref
0x10116bae  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x10116bb3  mov     ecx, offset aDuration; "duration"
0x10116bb8  call    ?newConstString@String@@SGPAV1@PBG@Z; String::newConstString(ushort const *)
0x10116bbd  mov     esi, eax
0x10116bbf  lea     ecx, [ebp+s]; ppref
0x10116bc2  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x10116bc7  mov     [ebp+s._p], esi
0x10116bca  lea     ecx, [edi+20h]; ppref
0x10116bcd  mov     edx, esi; pref
0x10116bcf  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x10116bd4  mov     eax, [edi]
0x10116bd6  push    edi
0x10116bd7  mov     esi, [eax+8]
0x10116bda  mov     ecx, esi; this
0x10116bdc  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10116be2  call    esi
0x10116be4  push    0Ch
0x10116be6  pop     edx; dwFlags
0x10116be7  mov     ecx, ebx; cb
0x10116be9  call    ?_MemAlloc@@YGPAXIK@Z; _MemAlloc(uint,ulong)
0x10116bee  mov     ecx, eax; this
0x10116bf0  call    ??0Datatype_ENTITY@@QAE@XZ; Datatype_ENTITY::Datatype_ENTITY(void)
0x10116bf5  mov     edi, eax
0x10116bf7  mov     edx, edi; pref
0x10116bf9  mov     ecx, offset ?c_ENTITY@SchemaDatatype@@2V?$_reference@VSchemaDatatype@@@@A; ppref
0x10116bfe  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x10116c03  mov     ecx, offset aEntity; "ENTITY"
0x10116c08  call    ?newConstString@String@@SGPAV1@PBG@Z; String::newConstString(ushort const *)
0x10116c0d  mov     esi, eax
0x10116c0f  lea     ecx, [ebp+s]; ppref
0x10116c12  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x10116c17  mov     [ebp+s._p], esi
0x10116c1a  lea     ecx, [edi+20h]; ppref
0x10116c1d  mov     edx, esi; pref
0x10116c1f  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x10116c24  mov     eax, [edi]
0x10116c26  push    edi
0x10116c27  mov     esi, [eax+8]
0x10116c2a  mov     ecx, esi; this
0x10116c2c  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10116c32  call    esi
0x10116c34  push    0Ch
0x10116c36  pop     edx; dwFlags
0x10116c37  push    60h ; '`'
0x10116c39  pop     ecx; cb
0x10116c3a  call    ?_MemAlloc@@YGPAXIK@Z; _MemAlloc(uint,ulong)
0x10116c3f  mov     ecx, eax; this
0x10116c41  call    ??0Datatype_float@@QAE@XZ; Datatype_float::Datatype_float(void)
  ... truncated ...
```
