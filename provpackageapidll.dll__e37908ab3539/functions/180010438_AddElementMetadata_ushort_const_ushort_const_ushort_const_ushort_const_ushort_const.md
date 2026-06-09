# AddElementMetadata(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x180010438`
- end: `0x18001128a`
- name: `?AddElementMetadata@@YAJPEBG0000@Z`
- size: `3666`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180014870`

## callees

- `0x180006014`
- `0x180010438`
- `0x1800118ac`
- `0x1800130cc`
- `0x1800131ac`
- `0x180013290`
- `0x180019010`

## string_xrefs

- `0x180010797`: `    Failed to write whitespace`
- `0x180010ba5`: `    Failed to write whitespace`
- `0x180010c72`: `    Failed to write whitespace`
- `0x18001048d`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x180010583`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x1800106a9`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x180010776`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x180010848`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x18001091c`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x1800109f4`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x180010ab7`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x180010b84`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x180010c51`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x180010d27`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x180010df0`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x180010eb3`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x180010f79`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x180011091`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x18001113a`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x1800111e3`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x180010d48`: `    Failed to write end node shallow`
- `0x180010ad8`: `    Failed to write end element`
- `0x180010ed4`: `    Failed to write end document`
- `0x180010f9a`: `    Failed to flush writer`
- `0x18001115b`: `    Failed to move to first attribute`
- `0x180010869`: `    FAiled to write metadata start element`
- `0x18001093d`: `    Failed to write key attribute`
- `0x180010a15`: `    Failed to write value attribute`
- `0x180010e11`: `    Failed to copy the rest of the file`

## pseudocode

```c
__int64 __fastcall AddElementMetadata(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5)
{
  int v8; // eax
  unsigned int v9; // edi
  struct IXmlReader *v10; // rcx
  struct IStream *v11; // rcx
  struct IXmlWriter *v12; // rcx
  struct IStream *v13; // rcx
  struct IXmlReader *v14; // rcx
  struct IStream *v15; // rcx
  int v16; // eax
  struct IXmlReader *v17; // rcx
  struct IStream *v18; // rcx
  struct IXmlWriter *v19; // rcx
  struct IStream *v20; // rcx
  int Node; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  struct IXmlReader *v25; // rcx
  struct IStream *v26; // rcx
  struct IXmlWriter *v27; // rcx
  struct IStream *v28; // rcx
  int v29; // eax
  struct IXmlReader *v30; // rcx
  struct IStream *v31; // rcx
  struct IXmlWriter *v32; // rcx
  struct IStream *v33; // rcx
  int v34; // eax
  struct IXmlReader *v35; // rcx
  struct IStream *v36; // rcx
  struct IXmlWriter *v37; // rcx
  struct IStream *v38; // rcx
  int v39; // eax
  struct IXmlReader *v40; // rcx
  struct IStream *v41; // rcx
  struct IXmlWriter *v42; // rcx
  struct IStream *v43; // rcx
  int v44; // eax
  struct IXmlReader *v45; // rcx
  struct IStream *v46; // rcx
  struct IXmlWriter *v47; // rcx
  struct IStream *v48; // rcx
  int v49; // eax
  struct IXmlReader *v50; // rcx
  struct IStream *v51; // rcx
  struct IXmlWriter *v52; // rcx
  struct IStream *v53; // rcx
  int v54; // eax
  struct IXmlReader *v55; // rcx
  struct IStream *v56; // rcx
  struct IXmlWriter *v57; // rcx
  struct IStream *v58; // rcx
  int v59; // eax
  struct IXmlReader *v60; // rcx
  struct IStream *v61; // rcx
  struct IXmlWriter *v62; // rcx
  struct IStream *v63; // rcx
  struct IXmlWriter *v64; // rcx
  int v65; // eax
  struct IXmlReader *v66; // rcx
  struct IStream *v67; // rcx
  struct IXmlWriter *v68; // rcx
  struct IStream *v69; // rcx
  int v70; // eax
  struct IXmlReader *v71; // rcx
  struct IStream *v72; // rcx
  struct IXmlWriter *v73; // rcx
  struct IStream *v74; // rcx
  int v75; // eax
  struct IXmlReader *v76; // rcx
  struct IStream *v77; // rcx
  struct IXmlWriter *v78; // rcx
  struct IStream *v79; // rcx
  int v80; // eax
  struct IXmlReader *v81; // rcx
  struct IStream *v82; // rcx
  struct IXmlWriter *v83; // rcx
  struct IStream *v84; // rcx
  struct IXmlReader *v85; // rcx
  struct IStream *v86; // rcx
  struct IXmlWriter *v87; // rcx
  struct IStream *v88; // rcx
  struct IXmlReader *v90; // rcx
  struct IStream *v91; // rcx
  struct IXmlWriter *v92; // rcx
  struct IStream *v93; // rcx
  struct IXmlReader *v94; // rcx
  struct IStream *v95; // rcx
  struct IXmlWriter *v96; // rcx
  struct IStream *v97; // rcx
  struct IXmlReader *v98; // rcx
  struct IStream *v99; // rcx
  struct IXmlWriter *v100; // rcx
  struct IStream *v101; // rcx
  int v102; // [rsp+20h] [rbp-38h]
  int v103; // [rsp+20h] [rbp-38h]
  int v104; // [rsp+20h] [rbp-38h]
  int v105; // [rsp+20h] [rbp-38h]
  int v106; // [rsp+20h] [rbp-38h]
  __int64 v107; // [rsp+20h] [rbp-38h]
  __int64 v108; // [rsp+20h] [rbp-38h]
  int v109; // [rsp+20h] [rbp-38h]
  int v110; // [rsp+20h] [rbp-38h]
  int v111; // [rsp+20h] [rbp-38h]
  int v112; // [rsp+28h] [rbp-30h]
  int v113; // [rsp+28h] [rbp-30h]
  int v114; // [rsp+28h] [rbp-30h]
  int v115; // [rsp+28h] [rbp-30h]
  int v116; // [rsp+28h] [rbp-30h]
  int v117; // [rsp+28h] [rbp-30h]
  int v118; // [rsp+28h] [rbp-30h]
  int v119; // [rsp+28h] [rbp-30h]
  int v120; // [rsp+28h] [rbp-30h]
  int v121; // [rsp+28h] [rbp-30h]
  int v122; // [rsp+28h] [rbp-30h]
  int v123; // [rsp+28h] [rbp-30h]
  int v124; // [rsp+28h] [rbp-30h]
  int v125; // [rsp+28h] [rbp-30h]
  int v126; // [rsp+28h] [rbp-30h]
  int v127; // [rsp+28h] [rbp-30h]
  int v128; // [rsp+28h] [rbp-30h]
  struct IXmlWriter *v129; // [rsp+30h] [rbp-28h] BYREF
  struct IXmlReader *ppvObject; // [rsp+38h] [rbp-20h] BYREF
  struct IStream *v131; // [rsp+40h] [rbp-18h] BYREF
  struct IStream *v132; // [rsp+48h] [rbp-10h] BYREF

  v132 = 0;
  v129 = 0;
  v131 = 0;
  ppvObject = 0;
  v8 = SetupOutput(&v132, &v129, a2, 0);
  v9 = v8;
  if ( v8 < 0 )
  {
    v112 = v8;
    v102 = 459;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "AddElementMetadata",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
      v102,
      v112);
    ProvPackageLog(3, L"    Failed to setup output");
    v10 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      ((void (__fastcall *)(struct IXmlReader *))v10->lpVtbl->Release)(v10);
    }
    v11 = v131;
    if ( v131 )
    {
      v131 = 0;
      ((void (__fastcall *)(struct IStream *))v11->lpVtbl->Release)(v11);
    }
    v12 = v129;
    if ( v129 )
    {
      v129 = 0;
      ((void (__fastcall *)(struct IXmlWriter *))v12->lpVtbl->Release)(v12);
    }
    v13 = v132;
    if ( v132 )
    {
      v132 = 0;
      ((void (__fastcall *)(struct IStream *))v13->lpVtbl->Release)(v13);
    }
    return v9;
  }
  v14 = ppvObject;
  if ( ppvObject )
  {
    ppvObject = 0;
    ((void (__fastcall *)(struct IXmlReader *))v14->lpVtbl->Release)(v14);
  }
  v15 = v131;
  if ( v131 )
  {
    v131 = 0;
    ((void (__fastcall *)(struct IStream *))v15->lpVtbl->Release)(v15);
  }
  v16 = SetupInput(&v131, &ppvObject, a1);
  v9 = v16;
  if ( v16 < 0 )
  {
    v113 = v16;
    v103 = 463;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "AddElementMetadata",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
      v103,
      v113);
    ProvPackageLog(3, L"    Failed to setup input");
    v17 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      ((void (__fastcall *)(struct IXmlReader *))v17->lpVtbl->Release)(v17);
    }
    v18 = v131;
    if ( v131 )
    {
      v131 = 0;
      ((void (__fastcall *)(struct IStream *))v18->lpVtbl->Release)(v18);
    }
    v19 = v129;
    if ( v129 )
    {
      v129 = 0;
      ((void (__fastcall *)(struct IXmlWriter *))v19->lpVtbl->Release)(v19);
    }
    v20 = v132;
    if ( v132 )
    {
      v132 = 0;
      ((void (__fastcall *)(struct IStream *))v20->lpVtbl->Release)(v20);
    }
    return v9;
  }
  do
  {
    Node = FindNode(ppvObject, v129, L"Element", 0);
    v9 = Node;
    if ( Node < 0 )
    {
      v128 = Node;
      v111 = 469;
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "AddElementMetadata",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
        v111,
        v128);
      ProvPackageLog(3, L"    Failed to find element start node");
      v98 = ppvObject;
      if ( ppvObject )
      {
        ppvObject = 0;
        ((void (__fastcall *)(struct IXmlReader *))v98->lpVtbl->Release)(v98);
      }
      v99 = v131;
      if ( v131 )
      {
        v131 = 0;
        ((void (__fastcall *)(struct IStream *))v99->lpVtbl->Release)(v99);
      }
      v100 = v129;
      if ( v129 )
      {
        v129 = 0;
        ((void (__fastcall *)(struct IXmlWriter *))v100->lpVtbl->Release)(v100);
      }
      v101 = v132;
      if ( v132 )
      {
        v132 = 0;
        ((void (__fastcall *)(struct IStream *))v101->lpVtbl->Release)(v101);
      }
      return v9;
    }
    v22 = ((__int64 (__fastcall *)(struct IXmlReader *))ppvObject->lpVtbl->MoveToFirstAttribute)(ppvObject);
    v9 = v22;
    if ( v22 < 0 )
    {
      v127 = v22;
      v110 = 472;
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "AddElementMetadata",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
        v110,
        v127);
      ProvPackageLog(3, L"    Failed to move to first attribute");
      v94 = ppvObject;
      if ( ppvObject )
      {
        ppvObject = 0;
        ((void (__fastcall *)(struct IXmlReader *))v94->lpVtbl->Release)(v94);
      }
      v95 = v131;
      if ( v131 )
      {
        v131 = 0;
        ((void (__fastcall *)(struct IStream *))v95->lpVtbl->Release)(v95);
      }
      v96 = v129;
      if ( v129 )
      {
        v129 = 0;
        ((void (__fastcall *)(struct IXmlWriter *))v96->lpVtbl->Release)(v96);
      }
      v97 = v132;
      if ( v132 )
      {
        v132 = 0;
        ((void (__fastcall *)(struct IStream *))v97->lpVtbl->Release)(v97);
      }
      return v9;
    }
    v23 = VerifyAttribute(ppvObject, L"Index", a3);
    v9 = v23;
    if ( v23 < 0 )
    {
      v126 = v23;
      v109 = 475;
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "AddElementMetadata",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
        v109,
        v126);
      ProvPackageLog(3, L"    Failed to verify index attribute");
      v90 = ppvObject;
      if ( ppvObject )
      {
        ppvObject = 0;
        ((void (__fastcall *)(struct IXmlReader *))v90->lpVtbl->Release)(v90);
      }
      v91 = v131;
      if ( v131 )
      {
        v131 = 0;
        ((void (__fastcall *)(struct IStream *))v91->lpVtbl->Release)(v91);
      }
      v92 = v129;
      if ( v129 )
      {
        v129 = 0;
        ((void (__fastcall *)(struct IXmlWriter *))v92->lpVtbl->Release)(v92);
      }
      v93 = v132;
      if ( v132 )
      {
        v132 = 0;
        ((void (__fastcall *)(struct IStream *))v93->lpVtbl->Release)(v93);
      }
      return v9;
    }
  }
  while ( v23 );
  v24 = FindNode(ppvObject, v129, 0, L"Element");
  v9 = v24;
  if ( v24 < 0 )
  {
    v114 = v24;
    v104 = 480;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "AddElementMetadata",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
      v104,
      v114);
    ProvPackageLog(3, L"    Failed to find element stop node");
    v25 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      ((void (__fastcall *)(struct IXmlReader *))v25->lpVtbl->Release)(v25);
    }
    v26 = v131;
    if ( v131 )
    {
      v131 = 0;
      ((void (__fastcall *)(struct IStream *))v26->lpVtbl->Release)(v26);
    }
    v27 = v129;
    if ( v129 )
    {
      v129 = 0;
      ((void (__fastcall *)(struct IXmlWriter *))v27->lpVtbl->Release)(v27);
    }
    v28 = v132;
    if ( v132 )
    {
      v132 = 0;
      ((void (__fastcall *)(struct IStream *))v28->lpVtbl->Release)(v28);
    }
    return v9;
  }
  v29 = ((__int64 (__fastcall *)(struct IXmlWriter *, const wchar_t *))v129->lpVtbl->WriteWhitespace)(v129, L"  ");
  v9 = v29;
  if ( v29 < 0 )
  {
    v115 = v29;
    v105 = 484;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "AddElementMetadata",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
      v105,
      v115);
    ProvPackageLog(3, L"    Failed to write whitespace");
    v30 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      ((void (__fastcall *)(struct IXmlReader *))v30->lpVtbl->Release)(v30);
    }
    v31 = v131;
    if ( v131 )
    {
      v131 = 0;
      ((void (__fastcall *)(struct IStream *))v31->lpVtbl->Release)(v31);
    }
    v32 = v129;
    if ( v129 )
    {
      v129 = 0;
      ((void (__fastcall *)(struct IXmlWriter *))v32->lpVtbl->Release)(v32);
    }
    v33 = v132;
    if ( v132 )
    {
      v132 = 0;
      ((void (__fastcall *)(struct IStream *))v33->lpVtbl->Release)(v33);
    }
    return v9;
  }
  v34 = ((__int64 (__fastcall *)(struct IXmlWriter *, _QWORD, const unsigned __int16 *, _QWORD))v129->lpVtbl->WriteStartElement)(
          v129,
          0,
          L"Metadata",
          0);
  v9 = v34;
  if ( v34 < 0 )
  {
    v116 = v34;
    v106 = 487;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "AddElementMetadata",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
      v106,
      v116);
    ProvPackageLog(3, L"    FAiled to write metadata start element");
    v35 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      ((void (__fastcall *)(struct IXmlReader *))v35->lpVtbl->Release)(v35);
    }
    v36 = v131;
    if ( v131 )
    {
      v131 = 0;
      ((void (__fastcall *)(struct IStream *))v36->lpVtbl->Release)(v36);
    }
    v37 = v129;
    if ( v129 )
    {
      v129 = 0;
      ((void (__fastcall *)(struct IXmlWriter *))v37->lpVtbl->Release)(v37);
    }
    v38 = v132;
    if ( v132 )
    {
      v132 = 0;
      ((void (__fastcall *)(struct IStream *))v38->lpVtbl->Release)(v38);
    }
    return v9;
  }
  v39 = ((__int64 (__fastcall *)(struct IXmlWriter *, _QWORD, const unsigned __int16 *, _QWORD, const unsigned __int16 *))v129->lpVtbl->WriteAttributeString)(
          v129,
          0,
          L"Key",
          0,
          a4);
  v9 = v39;
  if ( v39 < 0 )
  {
    v117 = v39;
    LODWORD(v107) = 491;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "AddElementMetadata",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
      v107,
      v117);
    ProvPackageLog(3, L"    Failed to write key attribute");
    v40 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      ((void (__fastcall *)(struct IXmlReader *))v40->lpVtbl->Release)(v40);
    }
    v41 = v131;
    if ( v131 )
    {
      v131 = 0;
      ((void (__fastcall *)(struct IStream *))v41->lpVtbl->Release)(v41);
    }
    v42 = v129;
    if ( v129 )
    {
      v129 = 0;
      ((void (__fastcall *)(struct IXmlWriter *))v42->lpVtbl->Release)(v42);
    }
    v43 = v132;
    if ( v132 )
    {
      v132 = 0;
      ((void (__fastcall *)(struct IStream *))v43->lpVtbl->Release)(v43);
    }
    return v9;
  }
  v44 = ((__int64 (__fastcall *)(struct IXmlWriter *, _QWORD, const wchar_t *, _QWORD, const unsigned __int16 *))v129->lpVtbl->WriteAttributeString)(
          v129,
          0,
          L"Value",
          0,
          a5);
  v9 = v44;
  if ( v44 < 0 )
  {
    v118 = v44;
    LODWORD(v108) = 495;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "AddElementMetadata",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
      v108,
      v118);
    ProvPackageLog(3, L"    Failed to write value attribute");
    v45 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      ((void (__fastcall *)(struct IXmlReader *))v45->lpVtbl->Release)(v45);
    }
    v46 = v131;
    if ( v131 )
    {
      v131 = 0;
      ((void (__fastcall *)(struct IStream *))v46->lpVtbl->Release)(v46);
    }
    v47 = v129;
    if ( v129 )
    {
      v129 = 0;
      ((void (__fastcall *)(struct IXmlWriter *))v47->lpVtbl->Release)(v47);
    }
    v48 = v132;
    if ( v132 )
    {
      v132 = 0;
      ((void (__fastcall *)(struct IStream *))v48->lpVtbl->Release)(v48);
    }
    return v9;
  }
  v49 = ((__int64 (__fastcall *)(struct IXmlWriter *))v129->lpVtbl->WriteEndElement)(v129);
  v9 = v49;
  if ( v49 < 0 )
  {
    v119 = v49;
    LODWORD(v108) = 498;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "AddElementMetadata",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
      v108,
      v119);
    ProvPackageLog(3, L"    Failed to write end element");
    v50 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      ((void (__fastcall *)(struct IXmlReader *))v50->lpVtbl->Release)(v50);
    }
    v51 = v131;
    if ( v131 )
    {
      v131 = 0;
      ((void (__fastcall *)(struct IStream *))v51->lpVtbl->Release)(v51);
    }
    v52 = v129;
    if ( v129 )
    {
      v129 = 0;
      ((void (__fastcall *)(struct IXmlWriter *))v52->lpVtbl->Release)(v52);
    }
    v53 = v132;
    if ( v132 )
    {
      v132 = 0;
      ((void (__fastcall *)(struct IStream *))v53->lpVtbl->Release)(v53);
    }
    return v9;
  }
  v54 = ((__int64 (__fastcall *)(struct IXmlWriter *, const unsigned __int16 *))v129->lpVtbl->WriteWhitespace)(
          v129,
          L"\n");
  v9 = v54;
  if ( v54 < 0 )
  {
    v120 = v54;
    LODWORD(v108) = 501;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "AddElementMetadata",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
      v108,
      v120);
    ProvPackageLog(3, L"    Failed to write whitespace");
    v55 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      ((void (__fastcall *)(struct IXmlReader *))v55->lpVtbl->Release)(v55);
    }
    v56 = v131;
    if ( v131 )
    {
      v131 = 0;
      ((void (__fastcall *)(struct IStream *))v56->lpVtbl->Release)(v56);
    }
    v57 = v129;
    if ( v129 )
    {
      v129 = 0;
      ((void (__fastcall *)(struct IXmlWriter *))v57->lpVtbl->Release)(v57);
    }
    v58 = v132;
    if ( v132 )
    {
      v132 = 0;
      ((void (__fastcall *)(struct IStream *))v58->lpVtbl->Release)(v58);
    }
    return v9;
  }
  v59 = ((__int64 (__fastcall *)(struct IXmlWriter *, const wchar_t *))v129->lpVtbl->WriteWhitespace)(v129, L"  ");
  v9 = v59;
  if ( v59 < 0 )
  {
    v121 = v59;
    LODWORD(v108) = 504;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "AddElementMetadata",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
      v108,
      v121);
    ProvPackageLog(3, L"    Failed to write whitespace");
    v60 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      ((void (__fastcall *)(struct IXmlReader *))v60->lpVtbl->Release)(v60);
    }
    v61 = v131;
    if ( v131 )
    {
      v131 = 0;
      ((void (__fastcall *)(struct IStream *))v61->lpVtbl->Release)(v61);
    }
    v62 = v129;
    if ( v129 )
    {
      v129 = 0;
      ((void (__fastcall *)(struct IXmlWriter *))v62->lpVtbl->Release)(v62);
    }
    v63 = v132;
    if ( v132 )
    {
      v132 = 0;
      ((void (__fastcall *)(struct IStream *))v63->lpVtbl->Release)(v63);
    }
    return v9;
  }
  v64 = v129;
  if ( v129 )
  {
    v65 = ((__int64 (__fastcall *)(struct IXmlWriter *, struct IXmlReader *, _QWORD))v129->lpVtbl->WriteNodeShallow)(
            v129,
            ppvObject,
            0);
    v9 = v65;
    if ( v65 < 0 )
    {
      v122 = v65;
      LODWORD(v108) = 510;
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "AddElementMetadata",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
        v108,
        v122);
      ProvPackageLog(3, L"    Failed to write end node shallow");
      v66 = ppvObject;
      if ( ppvObject )
      {
        ppvObject = 0;
        ((void (__fastcall *)(struct IXmlReader *))v66->lpVtbl->Release)(v66);
      }
      v67 = v131;
      if ( v131 )
      {
        v131 = 0;
        ((void (__fastcall *)(struct IStream *))v67->lpVtbl->Release)(v67);
      }
      v68 = v129;
      if ( v129 )
      {
        v129 = 0;
        ((void (__fastcall *)(struct IXmlWriter *))v68->lpVtbl->Release)(v68);
      }
      v69 = v132;
      if ( v132 )
      {
        v132 = 0;
        ((void (__fastcall *)(struct IStream *))v69->lpVtbl->Release)(v69);
      }
      return v9;
    }
    v64 = v129;
  }
  v70 = FindNode(ppvObject, v64, 0, 0);
  v9 = v70;
  if ( v70 < 0 )
  {
    v123 = v70;
    LODWORD(v108) = 515;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "AddElementMetadata",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
      v108,
      v123);
    ProvPackageLog(3, L"    Failed to copy the rest of the file");
    v71 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      ((void (__fastcall *)(struct IXmlReader *))v71->lpVtbl->Release)(v71);
    }
    v72 = v131;
    if ( v131 )
    {
      v131 = 0;
      ((void (__fastcall *)(struct IStream *))v72->lpVtbl->Release)(v72);
    }
    v73 = v129;
    if ( v129 )
    {
      v129 = 0;
      ((void (__fastcall *)(struct IXmlWriter *))v73->lpVtbl->Release)(v73);
    }
    v74 = v132;
    if ( v132 )
    {
      v132 = 0;
      ((void (__fastcall *)(struct IStream *))v74->lpVtbl->Release)(v74);
    }
    return v9;
  }
  v75 = ((__int64 (__fastcall *)(struct IXmlWriter *))v129->lpVtbl->WriteEndDocument)(v129);
  v9 = v75;
  if ( v75 < 0 )
  {
    v124 = v75;
    LODWORD(v108) = 518;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "AddElementMetadata",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
      v108,
      v124);
    ProvPackageLog(3, L"    Failed to write end document");
    v76 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      ((void (__fastcall *)(struct IXmlReader *))v76->lpVtbl->Release)(v76);
    }
    v77 = v131;
    if ( v131 )
    {
      v131 = 0;
      ((void (__fastcall *)(struct IStream *))v77->lpVtbl->Release)(v77);
    }
    v78 = v129;
    if ( v129 )
    {
      v129 = 0;
      ((void (__fastcall *)(struct IXmlWriter *))v78->lpVtbl->Release)(v78);
    }
    v79 = v132;
    if ( v132 )
    {
      v132 = 0;
      ((void (__fastcall *)(struct IStream *))v79->lpVtbl->Release)(v79);
    }
    return v9;
  }
  v80 = ((__int64 (__fastcall *)(struct IXmlWriter *))v129->lpVtbl->Flush)(v129);
  v9 = v80;
  if ( v80 < 0 )
  {
    v125 = v80;
    LODWORD(v108) = 521;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "AddElementMetadata",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
      v108,
      v125);
    ProvPackageLog(3, L"    Failed to flush writer");
    v81 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      ((void (__fastcall *)(struct IXmlReader *))v81->lpVtbl->Release)(v81);
    }
    v82 = v131;
    if ( v131 )
    {
      v131 = 0;
      ((void (__fastcall *)(struct IStream *))v82->lpVtbl->Release)(v82);
    }
    v83 = v129;
    if ( v129 )
    {
      v129 = 0;
      ((void (__fastcall *)(struct IXmlWriter *))v83->lpVtbl->Release)(v83);
    }
    v84 = v132;
    if ( v132 )
    {
      v132 = 0;
      ((void (__fastcall *)(struct IStream *))v84->lpVtbl->Release)(v84);
    }
    return v9;
  }
  v85 = ppvObject;
  if ( ppvObject )
  {
    ppvObject = 0;
    ((void (__fastcall *)(struct IXmlReader *))v85->lpVtbl->Release)(v85);
  }
  v86 = v131;
  if ( v131 )
  {
    v131 = 0;
    ((void (__fastcall *)(struct IStream *))v86->lpVtbl->Release)(v86);
  }
  v87 = v129;
  if ( v129 )
  {
    v129 = 0;
    ((void (__fastcall *)(struct IXmlWriter *))v87->lpVtbl->Release)(v87);
  }
  v88 = v132;
  if ( v132 )
  {
    v132 = 0;
    ((void (__fastcall *)(struct IStream *))v88->lpVtbl->Release)(v88);
  }
  return 0;
}

```

## disassembly

```asm
0x180010438  push    rbp
0x18001043a  push    rbx
0x18001043b  push    rsi
0x18001043c  push    rdi
0x18001043d  push    r14
0x18001043f  push    r15
0x180010441  mov     rbp, rsp
0x180010444  sub     rsp, 58h
0x180010448  mov     r14, r9
0x18001044b  mov     rsi, r8
0x18001044e  mov     rbx, rcx
0x180010451  xor     r15d, r15d
0x180010454  mov     [rbp+var_10], r15
0x180010458  mov     [rbp+var_28], r15
0x18001045c  mov     [rbp+var_18], r15
0x180010460  mov     [rbp+ppvObject], r15
0x180010464  xor     r9d, r9d; int
0x180010467  mov     r8, rdx; unsigned __int16 *
0x18001046a  lea     rdx, [rbp+var_28]; ppvObject
0x18001046e  lea     rcx, [rbp+var_10]; struct IStream **
0x180010472  call    ?SetupOutput@@YAJPEAPEAUIStream@@PEAPEAUIXmlWriter@@PEBGH@Z; SetupOutput(IStream * *,IXmlWriter * *,ushort const *,int)
0x180010477  mov     edi, eax
0x180010479  test    eax, eax
0x18001047b  jns     loc_180010529
0x180010481  mov     [rsp+58h+var_30], eax
0x180010485  mov     dword ptr [rsp+58h+var_38], 1CBh
0x18001048d  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x180010494  lea     r8, aAddelementmeta; "AddElementMetadata"
0x18001049b  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x1800104a2  lea     ebx, [r15+3]
0x1800104a6  mov     ecx, ebx
0x1800104a8  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800104ad  lea     rdx, aFailedToSetupO; "    Failed to setup output"
0x1800104b4  mov     ecx, ebx
0x1800104b6  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800104bb  nop
0x1800104bc  mov     rcx, [rbp+ppvObject]
0x1800104c0  test    rcx, rcx
0x1800104c3  jz      short loc_1800104D6
0x1800104c5  mov     [rbp+ppvObject], r15
0x1800104c9  mov     rax, [rcx]
0x1800104cc  mov     rax, [rax+10h]
0x1800104d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800104d5  nop
0x1800104d6  mov     rcx, [rbp+var_18]
0x1800104da  test    rcx, rcx
0x1800104dd  jz      short loc_1800104F0
0x1800104df  mov     [rbp+var_18], r15
0x1800104e3  mov     rax, [rcx]
0x1800104e6  mov     rax, [rax+10h]
0x1800104ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800104ef  nop
0x1800104f0  mov     rcx, [rbp+var_28]
0x1800104f4  test    rcx, rcx
0x1800104f7  jz      short loc_18001050A
0x1800104f9  mov     [rbp+var_28], r15
0x1800104fd  mov     rax, [rcx]
0x180010500  mov     rax, [rax+10h]
0x180010504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010509  nop
0x18001050a  mov     rcx, [rbp+var_10]
0x18001050e  test    rcx, rcx
0x180010511  jz      short loc_180010524
0x180010513  mov     [rbp+var_10], r15
0x180010517  mov     rax, [rcx]
0x18001051a  mov     rax, [rax+10h]
0x18001051e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010523  nop
0x180010524  jmp     loc_18001127B
0x180010529  mov     rcx, [rbp+ppvObject]
0x18001052d  test    rcx, rcx
0x180010530  jz      short loc_180010543
0x180010532  mov     [rbp+ppvObject], r15
0x180010536  mov     rax, [rcx]
0x180010539  mov     rax, [rax+10h]
0x18001053d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010542  nop
0x180010543  mov     rcx, [rbp+var_18]
0x180010547  test    rcx, rcx
0x18001054a  jz      short loc_18001055D
0x18001054c  mov     [rbp+var_18], r15
0x180010550  mov     rax, [rcx]
0x180010553  mov     rax, [rax+10h]
0x180010557  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001055c  nop
0x18001055d  mov     r8, rbx; unsigned __int16 *
0x180010560  lea     rdx, [rbp+ppvObject]; ppvObject
0x180010564  lea     rcx, [rbp+var_18]; struct IStream **
0x180010568  call    ?SetupInput@@YAJPEAPEAUIStream@@PEAPEAUIXmlReader@@PEBG@Z; SetupInput(IStream * *,IXmlReader * *,ushort const *)
0x18001056d  mov     edi, eax
0x18001056f  test    eax, eax
0x180010571  jns     loc_180010620
0x180010577  mov     [rsp+58h+var_30], eax
0x18001057b  mov     dword ptr [rsp+58h+var_38], 1CFh
0x180010583  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x18001058a  lea     r8, aAddelementmeta; "AddElementMetadata"
0x180010591  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180010598  mov     ebx, 3
0x18001059d  mov     ecx, ebx
0x18001059f  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800105a4  lea     rdx, aFailedToSetupI; "    Failed to setup input"
0x1800105ab  mov     ecx, ebx
0x1800105ad  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800105b2  nop
0x1800105b3  mov     rcx, [rbp+ppvObject]
0x1800105b7  test    rcx, rcx
0x1800105ba  jz      short loc_1800105CD
0x1800105bc  mov     [rbp+ppvObject], r15
0x1800105c0  mov     rax, [rcx]
0x1800105c3  mov     rax, [rax+10h]
0x1800105c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105cc  nop
0x1800105cd  mov     rcx, [rbp+var_18]
0x1800105d1  test    rcx, rcx
0x1800105d4  jz      short loc_1800105E7
0x1800105d6  mov     [rbp+var_18], r15
0x1800105da  mov     rax, [rcx]
0x1800105dd  mov     rax, [rax+10h]
0x1800105e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105e6  nop
0x1800105e7  mov     rcx, [rbp+var_28]
0x1800105eb  test    rcx, rcx
0x1800105ee  jz      short loc_180010601
0x1800105f0  mov     [rbp+var_28], r15
0x1800105f4  mov     rax, [rcx]
0x1800105f7  mov     rax, [rax+10h]
0x1800105fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010600  nop
0x180010601  mov     rcx, [rbp+var_10]
0x180010605  test    rcx, rcx
0x180010608  jz      short loc_18001061B
0x18001060a  mov     [rbp+var_10], r15
0x18001060e  mov     rax, [rcx]
0x180010611  mov     rax, [rax+10h]
0x180010615  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001061a  nop
0x18001061b  jmp     loc_18001127B
0x180010620  xor     r9d, r9d; unsigned __int16 *
0x180010623  lea     r8, aElement_0; "Element"
0x18001062a  mov     rdx, [rbp+var_28]; struct IXmlWriter *
0x18001062e  mov     rcx, [rbp+ppvObject]; struct IXmlReader *
0x180010632  call    ?FindNode@@YAJPEAUIXmlReader@@PEAUIXmlWriter@@PEBG2@Z; FindNode(IXmlReader *,IXmlWriter *,ushort const *,ushort const *)
0x180010637  mov     edi, eax
0x180010639  test    eax, eax
0x18001063b  js      loc_1800111D7
0x180010641  mov     rcx, [rbp+ppvObject]
0x180010645  mov     rax, [rcx]
0x180010648  mov     rax, [rax+40h]
0x18001064c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010651  mov     edi, eax
0x180010653  test    eax, eax
0x180010655  js      loc_18001112E
0x18001065b  mov     r8, rsi; unsigned __int16 *
0x18001065e  lea     rdx, aIndex_0; "Index"
0x180010665  mov     rcx, [rbp+ppvObject]; struct IXmlReader *
0x180010669  call    ?VerifyAttribute@@YAJPEAUIXmlReader@@PEBG1@Z; VerifyAttribute(IXmlReader *,ushort const *,ushort const *)
0x18001066e  mov     edi, eax
0x180010670  test    eax, eax
0x180010672  js      loc_180011085
0x180010678  test    eax, eax
0x18001067a  jnz     short loc_180010620
0x18001067c  lea     r9, aElement_0; "Element"
0x180010683  xor     r8d, r8d; unsigned __int16 *
0x180010686  mov     rdx, [rbp+var_28]; struct IXmlWriter *
0x18001068a  mov     rcx, [rbp+ppvObject]; struct IXmlReader *
0x18001068e  call    ?FindNode@@YAJPEAUIXmlReader@@PEAUIXmlWriter@@PEBG2@Z; FindNode(IXmlReader *,IXmlWriter *,ushort const *,ushort const *)
0x180010693  mov     edi, eax
0x180010695  test    eax, eax
0x180010697  jns     loc_180010746
0x18001069d  mov     [rsp+58h+var_30], eax
0x1800106a1  mov     dword ptr [rsp+58h+var_38], 1E0h
0x1800106a9  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x1800106b0  lea     r8, aAddelementmeta; "AddElementMetadata"
0x1800106b7  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x1800106be  mov     ebx, 3
0x1800106c3  mov     ecx, ebx
0x1800106c5  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800106ca  lea     rdx, aFailedToFindEl; "    Failed to find element stop node"
0x1800106d1  mov     ecx, ebx
0x1800106d3  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800106d8  nop
0x1800106d9  mov     rcx, [rbp+ppvObject]
0x1800106dd  test    rcx, rcx
0x1800106e0  jz      short loc_1800106F3
0x1800106e2  mov     [rbp+ppvObject], r15
0x1800106e6  mov     rax, [rcx]
0x1800106e9  mov     rax, [rax+10h]
0x1800106ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800106f2  nop
0x1800106f3  mov     rcx, [rbp+var_18]
0x1800106f7  test    rcx, rcx
0x1800106fa  jz      short loc_18001070D
0x1800106fc  mov     [rbp+var_18], r15
0x180010700  mov     rax, [rcx]
0x180010703  mov     rax, [rax+10h]
0x180010707  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001070c  nop
0x18001070d  mov     rcx, [rbp+var_28]
0x180010711  test    rcx, rcx
0x180010714  jz      short loc_180010727
0x180010716  mov     [rbp+var_28], r15
0x18001071a  mov     rax, [rcx]
0x18001071d  mov     rax, [rax+10h]
0x180010721  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010726  nop
0x180010727  mov     rcx, [rbp+var_10]
0x18001072b  test    rcx, rcx
0x18001072e  jz      short loc_180010741
0x180010730  mov     [rbp+var_10], r15
0x180010734  mov     rax, [rcx]
0x180010737  mov     rax, [rax+10h]
0x18001073b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010740  nop
0x180010741  jmp     loc_18001127B
0x180010746  mov     rcx, [rbp+var_28]
0x18001074a  mov     rax, [rcx]
0x18001074d  lea     rdx, asc_18001F298; "  "
0x180010754  mov     rax, [rax+0F0h]
0x18001075b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010760  mov     edi, eax
0x180010762  test    eax, eax
0x180010764  jns     loc_180010813
0x18001076a  mov     [rsp+58h+var_30], eax
0x18001076e  mov     dword ptr [rsp+58h+var_38], 1E4h
0x180010776  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x18001077d  lea     r8, aAddelementmeta; "AddElementMetadata"
0x180010784  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18001078b  mov     ebx, 3
0x180010790  mov     ecx, ebx
0x180010792  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180010797  lea     rdx, aFailedToWriteW; "    Failed to write whitespace"
0x18001079e  mov     ecx, ebx
0x1800107a0  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800107a5  nop
0x1800107a6  mov     rcx, [rbp+ppvObject]
0x1800107aa  test    rcx, rcx
0x1800107ad  jz      short loc_1800107C0
0x1800107af  mov     [rbp+ppvObject], r15
0x1800107b3  mov     rax, [rcx]
0x1800107b6  mov     rax, [rax+10h]
0x1800107ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107bf  nop
0x1800107c0  mov     rcx, [rbp+var_18]
0x1800107c4  test    rcx, rcx
0x1800107c7  jz      short loc_1800107DA
0x1800107c9  mov     [rbp+var_18], r15
0x1800107cd  mov     rax, [rcx]
0x1800107d0  mov     rax, [rax+10h]
0x1800107d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107d9  nop
0x1800107da  mov     rcx, [rbp+var_28]
0x1800107de  test    rcx, rcx
0x1800107e1  jz      short loc_1800107F4
0x1800107e3  mov     [rbp+var_28], r15
0x1800107e7  mov     rax, [rcx]
0x1800107ea  mov     rax, [rax+10h]
0x1800107ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107f3  nop
0x1800107f4  mov     rcx, [rbp+var_10]
0x1800107f8  test    rcx, rcx
0x1800107fb  jz      short loc_18001080E
0x1800107fd  mov     [rbp+var_10], r15
0x180010801  mov     rax, [rcx]
0x180010804  mov     rax, [rax+10h]
0x180010808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001080d  nop
0x18001080e  jmp     loc_18001127B
0x180010813  mov     rcx, [rbp+var_28]
0x180010817  mov     rax, [rcx]
0x18001081a  xor     r9d, r9d
0x18001081d  lea     r8, aMetadata; "Metadata"
0x180010824  xor     edx, edx
0x180010826  mov     rax, [rax+0D8h]
0x18001082d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010832  mov     edi, eax
0x180010834  test    eax, eax
0x180010836  jns     loc_1800108E5
0x18001083c  mov     [rsp+58h+var_30], eax
0x180010840  mov     dword ptr [rsp+58h+var_38], 1E7h
0x180010848  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x18001084f  lea     r8, aAddelementmeta; "AddElementMetadata"
0x180010856  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18001085d  mov     ebx, 3
0x180010862  mov     ecx, ebx
0x180010864  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180010869  lea     rdx, aFailedToWriteM; "    FAiled to write metadata start elem"...
0x180010870  mov     ecx, ebx
0x180010872  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180010877  nop
0x180010878  mov     rcx, [rbp+ppvObject]
0x18001087c  test    rcx, rcx
0x18001087f  jz      short loc_180010892
0x180010881  mov     [rbp+ppvObject], r15
0x180010885  mov     rax, [rcx]
0x180010888  mov     rax, [rax+10h]
0x18001088c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010891  nop
0x180010892  mov     rcx, [rbp+var_18]
0x180010896  test    rcx, rcx
0x180010899  jz      short loc_1800108AC
  ... truncated ...
```
