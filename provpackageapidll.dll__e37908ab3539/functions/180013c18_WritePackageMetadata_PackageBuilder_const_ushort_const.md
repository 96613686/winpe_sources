# WritePackageMetadata(PackageBuilder const &,ushort const *)

- ea: `0x180013c18`
- end: `0x1800145b9`
- name: `?WritePackageMetadata@@YAJAEBVPackageBuilder@@PEBG@Z`
- size: `2465`
- prototype: `__int64 __fastcall(const unsigned __int16 **, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x1800068b8`

## callees

- `0x180006014`
- `0x1800131ac`
- `0x180013c18`
- `0x1800145c0`
- `0x180019010`

## string_xrefs

- `0x180013ecc`: `    Failed to write whitespace`
- `0x180013c59`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x180013cec`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x180013d7c`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x180013e16`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x180013eab`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x180013f3a`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x180013fd0`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x180014066`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x1800140fc`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x180014192`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x180014228`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x1800142be`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x180014354`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x1800143e6`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x180014478`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x18001450d`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x180013d9d`: `    Failed to write start document`
- `0x18001452e`: `    Failed to flush writer`
- `0x180013c60`: `WritePackageMetadata`
- `0x180013cf3`: `WritePackageMetadata`
- `0x180013d83`: `WritePackageMetadata`
- `0x180013e1d`: `WritePackageMetadata`
- `0x180013eb2`: `WritePackageMetadata`
- `0x180013f41`: `WritePackageMetadata`
- `0x180013fd7`: `WritePackageMetadata`
- `0x18001406d`: `WritePackageMetadata`
- `0x180014103`: `WritePackageMetadata`
- `0x180014199`: `WritePackageMetadata`
- `0x18001422f`: `WritePackageMetadata`
- `0x1800142c5`: `WritePackageMetadata`
- `0x18001435b`: `WritePackageMetadata`
- `0x1800143ed`: `WritePackageMetadata`
- `0x18001447f`: `WritePackageMetadata`
- `0x180014514`: `WritePackageMetadata`
- `0x180013e37`: `    Failed to write image start element`
- `0x180013f62`: `    Failed to write package metadata %s block`
- `0x180013ff8`: `    Failed to write package metadata %s block`
- `0x18001408e`: `    Failed to write package metadata %s block`
- `0x180014124`: `    Failed to write package metadata %s block`
- `0x1800141ba`: `    Failed to write package metadata %s block`
- `0x180014250`: `    Failed to write package metadata %s block`
- `0x1800142e6`: `    Failed to write package metadata %s block`
- `0x18001437c`: `    Failed to write package metadata %s block`
- `0x18001440e`: `    Failed to write %s`
- `0x1800144a0`: `    Failed to write %s`

## pseudocode

```c
__int64 __fastcall WritePackageMetadata(const unsigned __int16 **a1, const unsigned __int16 *a2)
{
  int v3; // eax
  unsigned int v4; // edi
  struct IXmlWriter *v5; // rcx
  struct IStream *v6; // rcx
  int v8; // eax
  struct IXmlWriter *v9; // rcx
  struct IStream *v10; // rcx
  int v11; // eax
  struct IXmlWriter *v12; // rcx
  struct IStream *v13; // rcx
  int v14; // eax
  struct IXmlWriter *v15; // rcx
  struct IStream *v16; // rcx
  int v17; // eax
  struct IXmlWriter *v18; // rcx
  struct IStream *v19; // rcx
  int v20; // eax
  struct IXmlWriter *v21; // rcx
  struct IStream *v22; // rcx
  int v23; // eax
  struct IXmlWriter *v24; // rcx
  struct IStream *v25; // rcx
  int v26; // eax
  struct IXmlWriter *v27; // rcx
  struct IStream *v28; // rcx
  int v29; // eax
  struct IXmlWriter *v30; // rcx
  struct IStream *v31; // rcx
  int v32; // eax
  struct IXmlWriter *v33; // rcx
  struct IStream *v34; // rcx
  int v35; // eax
  struct IXmlWriter *v36; // rcx
  struct IStream *v37; // rcx
  int v38; // eax
  struct IXmlWriter *v39; // rcx
  struct IStream *v40; // rcx
  int v41; // eax
  struct IXmlWriter *v42; // rcx
  struct IStream *v43; // rcx
  int v44; // eax
  struct IXmlWriter *v45; // rcx
  struct IStream *v46; // rcx
  int v47; // eax
  struct IXmlWriter *v48; // rcx
  struct IStream *v49; // rcx
  int v50; // eax
  struct IXmlWriter *v51; // rcx
  struct IStream *v52; // rcx
  struct IXmlWriter *v53; // rcx
  struct IStream *v54; // rcx
  int v55; // [rsp+20h] [rbp-10h]
  int v56; // [rsp+20h] [rbp-10h]
  int v57; // [rsp+20h] [rbp-10h]
  int v58; // [rsp+20h] [rbp-10h]
  int v59; // [rsp+20h] [rbp-10h]
  int v60; // [rsp+20h] [rbp-10h]
  int v61; // [rsp+20h] [rbp-10h]
  int v62; // [rsp+20h] [rbp-10h]
  int v63; // [rsp+20h] [rbp-10h]
  int v64; // [rsp+20h] [rbp-10h]
  int v65; // [rsp+20h] [rbp-10h]
  int v66; // [rsp+20h] [rbp-10h]
  int v67; // [rsp+20h] [rbp-10h]
  int v68; // [rsp+20h] [rbp-10h]
  int v69; // [rsp+20h] [rbp-10h]
  int v70; // [rsp+20h] [rbp-10h]
  int v71; // [rsp+28h] [rbp-8h]
  int v72; // [rsp+28h] [rbp-8h]
  int v73; // [rsp+28h] [rbp-8h]
  int v74; // [rsp+28h] [rbp-8h]
  int v75; // [rsp+28h] [rbp-8h]
  int v76; // [rsp+28h] [rbp-8h]
  int v77; // [rsp+28h] [rbp-8h]
  int v78; // [rsp+28h] [rbp-8h]
  int v79; // [rsp+28h] [rbp-8h]
  int v80; // [rsp+28h] [rbp-8h]
  int v81; // [rsp+28h] [rbp-8h]
  int v82; // [rsp+28h] [rbp-8h]
  int v83; // [rsp+28h] [rbp-8h]
  int v84; // [rsp+28h] [rbp-8h]
  int v85; // [rsp+28h] [rbp-8h]
  int v86; // [rsp+28h] [rbp-8h]
  struct IXmlWriter *ppvObject; // [rsp+60h] [rbp+30h] BYREF
  struct IStream *v88; // [rsp+68h] [rbp+38h] BYREF

  v88 = 0;
  ppvObject = 0;
  v3 = SetupOutput(&v88, &ppvObject, a2, 0);
  v4 = v3;
  if ( v3 < 0 )
  {
    v71 = v3;
    v55 = 603;
    ProvPackageLog(
      3u,
      L"%hs (%hs:%d) - 0x%08x:",
      "WritePackageMetadata",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
      v55,
      v71);
    ProvPackageLog(3u, L"    Failed to setup output");
    v5 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      ((void (__fastcall *)(struct IXmlWriter *))v5->lpVtbl->Release)(v5);
    }
    v6 = v88;
    if ( v88 )
    {
      v88 = 0;
      ((void (__fastcall *)(struct IStream *))v6->lpVtbl->Release)(v6);
    }
    return v4;
  }
  v8 = ((__int64 (__fastcall *)(struct IXmlWriter *, __int64, __int64))ppvObject->lpVtbl->SetProperty)(ppvObject, 1, 1);
  v4 = v8;
  if ( v8 < 0 )
  {
    v72 = v8;
    v56 = 607;
    ProvPackageLog(
      3u,
      L"%hs (%hs:%d) - 0x%08x:",
      "WritePackageMetadata",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
      v56,
      v72);
    ProvPackageLog(3u, L"    Failed to set indent property");
    v9 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      ((void (__fastcall *)(struct IXmlWriter *))v9->lpVtbl->Release)(v9);
    }
    v10 = v88;
    if ( v88 )
    {
      v88 = 0;
      ((void (__fastcall *)(struct IStream *))v10->lpVtbl->Release)(v10);
    }
    return v4;
  }
  v11 = ((__int64 (__fastcall *)(struct IXmlWriter *, _QWORD))ppvObject->lpVtbl->WriteStartDocument)(ppvObject, 0);
  v4 = v11;
  if ( v11 < 0 )
  {
    v73 = v11;
    v57 = 610;
    ProvPackageLog(
      3u,
      L"%hs (%hs:%d) - 0x%08x:",
      "WritePackageMetadata",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
      v57,
      v73);
    ProvPackageLog(3u, L"    Failed to write start document");
    v12 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      ((void (__fastcall *)(struct IXmlWriter *))v12->lpVtbl->Release)(v12);
    }
    v13 = v88;
    if ( v88 )
    {
      v88 = 0;
      ((void (__fastcall *)(struct IStream *))v13->lpVtbl->Release)(v13);
    }
    return v4;
  }
  v14 = ((__int64 (__fastcall *)(struct IXmlWriter *, _QWORD, const wchar_t *, _QWORD))ppvObject->lpVtbl->WriteStartElement)(
          ppvObject,
          0,
          L"IMAGE",
          0);
  v4 = v14;
  if ( v14 < 0 )
  {
    v74 = v14;
    v58 = 614;
    ProvPackageLog(
      3u,
      L"%hs (%hs:%d) - 0x%08x:",
      "WritePackageMetadata",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
      v58,
      v74);
    ProvPackageLog(3u, L"    Failed to write image start element");
    v15 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      ((void (__fastcall *)(struct IXmlWriter *))v15->lpVtbl->Release)(v15);
    }
    v16 = v88;
    if ( v88 )
    {
      v88 = 0;
      ((void (__fastcall *)(struct IStream *))v16->lpVtbl->Release)(v16);
    }
    return v4;
  }
  v17 = ((__int64 (__fastcall *)(struct IXmlWriter *, const unsigned __int16 *))ppvObject->lpVtbl->WriteWhitespace)(
          ppvObject,
          L"\n");
  v4 = v17;
  if ( v17 < 0 )
  {
    v75 = v17;
    v59 = 617;
    ProvPackageLog(
      3u,
      L"%hs (%hs:%d) - 0x%08x:",
      "WritePackageMetadata",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
      v59,
      v75);
    ProvPackageLog(3u, L"    Failed to write whitespace");
    v18 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      ((void (__fastcall *)(struct IXmlWriter *))v18->lpVtbl->Release)(v18);
    }
    v19 = v88;
    if ( v88 )
    {
      v88 = 0;
      ((void (__fastcall *)(struct IStream *))v19->lpVtbl->Release)(v19);
    }
    return v4;
  }
  v20 = WritePackageMetadataBlock(ppvObject, L"NAME", a1[2]);
  v4 = v20;
  if ( v20 < 0 )
  {
    v76 = v20;
    v60 = 622;
    ProvPackageLog(
      3u,
      L"%hs (%hs:%d) - 0x%08x:",
      "WritePackageMetadata",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
      v60,
      v76);
    ProvPackageLog(3u, L"    Failed to write package metadata %s block", L"name");
    v21 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      ((void (__fastcall *)(struct IXmlWriter *))v21->lpVtbl->Release)(v21);
    }
    v22 = v88;
    if ( v88 )
    {
      v88 = 0;
      ((void (__fastcall *)(struct IStream *))v22->lpVtbl->Release)(v22);
    }
    return v4;
  }
  v23 = WritePackageMetadataBlock(ppvObject, L"DESCRIPTION", a1[3]);
  v4 = v23;
  if ( v23 < 0 )
  {
    v77 = v23;
    v61 = 626;
    ProvPackageLog(
      3u,
      L"%hs (%hs:%d) - 0x%08x:",
      "WritePackageMetadata",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
      v61,
      v77);
    ProvPackageLog(3u, L"    Failed to write package metadata %s block", L"description");
    v24 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      ((void (__fastcall *)(struct IXmlWriter *))v24->lpVtbl->Release)(v24);
    }
    v25 = v88;
    if ( v88 )
    {
      v88 = 0;
      ((void (__fastcall *)(struct IStream *))v25->lpVtbl->Release)(v25);
    }
    return v4;
  }
  v26 = WritePackageMetadataBlock(ppvObject, L"NOTES", a1[4]);
  v4 = v26;
  if ( v26 < 0 )
  {
    v78 = v26;
    v62 = 630;
    ProvPackageLog(
      3u,
      L"%hs (%hs:%d) - 0x%08x:",
      "WritePackageMetadata",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
      v62,
      v78);
    ProvPackageLog(3u, L"    Failed to write package metadata %s block", L"notes");
    v27 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      ((void (__fastcall *)(struct IXmlWriter *))v27->lpVtbl->Release)(v27);
    }
    v28 = v88;
    if ( v88 )
    {
      v88 = 0;
      ((void (__fastcall *)(struct IStream *))v28->lpVtbl->Release)(v28);
    }
    return v4;
  }
  v29 = WritePackageMetadataBlock(ppvObject, L"AUTHOR", a1[5]);
  v4 = v29;
  if ( v29 < 0 )
  {
    v79 = v29;
    v63 = 634;
    ProvPackageLog(
      3u,
      L"%hs (%hs:%d) - 0x%08x:",
      "WritePackageMetadata",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
      v63,
      v79);
    ProvPackageLog(3u, L"    Failed to write package metadata %s block", L"author");
    v30 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      ((void (__fastcall *)(struct IXmlWriter *))v30->lpVtbl->Release)(v30);
    }
    v31 = v88;
    if ( v88 )
    {
      v88 = 0;
      ((void (__fastcall *)(struct IStream *))v31->lpVtbl->Release)(v31);
    }
    return v4;
  }
  v32 = WritePackageMetadataBlock(ppvObject, L"VERSION", a1[6]);
  v4 = v32;
  if ( v32 < 0 )
  {
    v80 = v32;
    v64 = 638;
    ProvPackageLog(
      3u,
      L"%hs (%hs:%d) - 0x%08x:",
      "WritePackageMetadata",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
      v64,
      v80);
    ProvPackageLog(3u, L"    Failed to write package metadata %s block", L"version");
    v33 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      ((void (__fastcall *)(struct IXmlWriter *))v33->lpVtbl->Release)(v33);
    }
    v34 = v88;
    if ( v88 )
    {
      v88 = 0;
      ((void (__fastcall *)(struct IStream *))v34->lpVtbl->Release)(v34);
    }
    return v4;
  }
  v35 = WritePackageMetadataBlock(ppvObject, L"ALTITUDE", a1[7]);
  v4 = v35;
  if ( v35 < 0 )
  {
    v81 = v35;
    v65 = 642;
    ProvPackageLog(
      3u,
      L"%hs (%hs:%d) - 0x%08x:",
      "WritePackageMetadata",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
      v65,
      v81);
    ProvPackageLog(3u, L"    Failed to write package metadata %s block", L"altitude");
    v36 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      ((void (__fastcall *)(struct IXmlWriter *))v36->lpVtbl->Release)(v36);
    }
    v37 = v88;
    if ( v88 )
    {
      v88 = 0;
      ((void (__fastcall *)(struct IStream *))v37->lpVtbl->Release)(v37);
    }
    return v4;
  }
  v38 = WritePackageMetadataBlock(ppvObject, L"RESETCLEAR", a1[8]);
  v4 = v38;
  if ( v38 < 0 )
  {
    v82 = v38;
    v66 = 646;
    ProvPackageLog(
      3u,
      L"%hs (%hs:%d) - 0x%08x:",
      "WritePackageMetadata",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
      v66,
      v82);
    ProvPackageLog(3u, L"    Failed to write package metadata %s block", L"rest clear");
    v39 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      ((void (__fastcall *)(struct IXmlWriter *))v39->lpVtbl->Release)(v39);
    }
    v40 = v88;
    if ( v88 )
    {
      v88 = 0;
      ((void (__fastcall *)(struct IStream *))v40->lpVtbl->Release)(v40);
    }
    return v4;
  }
  v41 = WritePackageMetadataBlock(ppvObject, L"PACKAGEID", a1[9]);
  v4 = v41;
  if ( v41 < 0 )
  {
    v83 = v41;
    v67 = 650;
    ProvPackageLog(
      3u,
      L"%hs (%hs:%d) - 0x%08x:",
      "WritePackageMetadata",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
      v67,
      v83);
    ProvPackageLog(3u, L"    Failed to write package metadata %s block", L"package ID");
    v42 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      ((void (__fastcall *)(struct IXmlWriter *))v42->lpVtbl->Release)(v42);
    }
    v43 = v88;
    if ( v88 )
    {
      v88 = 0;
      ((void (__fastcall *)(struct IStream *))v43->lpVtbl->Release)(v43);
    }
    return v4;
  }
  v44 = ((__int64 (__fastcall *)(struct IXmlWriter *))ppvObject->lpVtbl->WriteEndElement)(ppvObject);
  v4 = v44;
  if ( v44 < 0 )
  {
    v84 = v44;
    v68 = 653;
    ProvPackageLog(
      3u,
      L"%hs (%hs:%d) - 0x%08x:",
      "WritePackageMetadata",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
      v68,
      v84);
    ProvPackageLog(3u, L"    Failed to write %s", L"end element");
    v45 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      ((void (__fastcall *)(struct IXmlWriter *))v45->lpVtbl->Release)(v45);
    }
    v46 = v88;
    if ( v88 )
    {
      v88 = 0;
      ((void (__fastcall *)(struct IStream *))v46->lpVtbl->Release)(v46);
    }
    return v4;
  }
  v47 = ((__int64 (__fastcall *)(struct IXmlWriter *))ppvObject->lpVtbl->WriteEndDocument)(ppvObject);
  v4 = v47;
  if ( v47 < 0 )
  {
    v85 = v47;
    v69 = 656;
    ProvPackageLog(
      3u,
      L"%hs (%hs:%d) - 0x%08x:",
      "WritePackageMetadata",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
      v69,
      v85);
    ProvPackageLog(3u, L"    Failed to write %s", L"end document");
    v48 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      ((void (__fastcall *)(struct IXmlWriter *))v48->lpVtbl->Release)(v48);
    }
    v49 = v88;
    if ( v88 )
    {
      v88 = 0;
      ((void (__fastcall *)(struct IStream *))v49->lpVtbl->Release)(v49);
    }
    return v4;
  }
  v50 = ((__int64 (__fastcall *)(struct IXmlWriter *))ppvObject->lpVtbl->Flush)(ppvObject);
  v4 = v50;
  if ( v50 < 0 )
  {
    v86 = v50;
    v70 = 659;
    ProvPackageLog(
      3u,
      L"%hs (%hs:%d) - 0x%08x:",
      "WritePackageMetadata",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
      v70,
      v86);
    ProvPackageLog(3u, L"    Failed to flush writer");
    v51 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      ((void (__fastcall *)(struct IXmlWriter *))v51->lpVtbl->Release)(v51);
    }
    v52 = v88;
    if ( v88 )
    {
      v88 = 0;
      ((void (__fastcall *)(struct IStream *))v52->lpVtbl->Release)(v52);
    }
    return v4;
  }
  v53 = ppvObject;
  if ( ppvObject )
  {
    ppvObject = 0;
    ((void (__fastcall *)(struct IXmlWriter *))v53->lpVtbl->Release)(v53);
  }
  v54 = v88;
  if ( v88 )
  {
    v88 = 0;
    ((void (__fastcall *)(struct IStream *))v54->lpVtbl->Release)(v54);
  }
  return 0;
}

```

## disassembly

```asm
0x180013c18  mov     [rsp-18h+arg_0], rbx
0x180013c1d  push    rbp
0x180013c1e  push    rsi
0x180013c1f  push    rdi
0x180013c20  mov     rbp, rsp
0x180013c23  sub     rsp, 30h
0x180013c27  mov     rbx, rcx
0x180013c2a  xor     esi, esi
0x180013c2c  mov     [rbp+arg_18], rsi
0x180013c30  mov     [rbp+ppvObject], rsi
0x180013c34  xor     r9d, r9d; int
0x180013c37  mov     r8, rdx; unsigned __int16 *
0x180013c3a  lea     rdx, [rbp+ppvObject]; ppvObject
0x180013c3e  lea     rcx, [rbp+arg_18]; struct IStream **
0x180013c42  call    ?SetupOutput@@YAJPEAPEAUIStream@@PEAPEAUIXmlWriter@@PEBGH@Z; SetupOutput(IStream * *,IXmlWriter * *,ushort const *,int)
0x180013c47  mov     edi, eax
0x180013c49  test    eax, eax
0x180013c4b  jns     short loc_180013CC2
0x180013c4d  mov     [rsp+30h+var_8], eax
0x180013c51  mov     [rsp+30h+var_10], 25Bh
0x180013c59  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x180013c60  lea     r8, aWritepackageme_0; "WritePackageMetadata"
0x180013c67  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180013c6e  lea     ebx, [rsi+3]
0x180013c71  mov     ecx, ebx
0x180013c73  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180013c78  lea     rdx, aFailedToSetupO; "    Failed to setup output"
0x180013c7f  mov     ecx, ebx
0x180013c81  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180013c86  nop
0x180013c87  mov     rcx, [rbp+ppvObject]
0x180013c8b  test    rcx, rcx
0x180013c8e  jz      short loc_180013CA1
0x180013c90  mov     [rbp+ppvObject], rsi
0x180013c94  mov     rax, [rcx]
0x180013c97  mov     rax, [rax+10h]
0x180013c9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ca0  nop
0x180013ca1  mov     rcx, [rbp+arg_18]
0x180013ca5  test    rcx, rcx
0x180013ca8  jz      short loc_180013CBB
0x180013caa  mov     [rbp+arg_18], rsi
0x180013cae  mov     rax, [rcx]
0x180013cb1  mov     rax, [rax+10h]
0x180013cb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013cba  nop
0x180013cbb  mov     eax, edi
0x180013cbd  jmp     loc_1800145AC
0x180013cc2  mov     rcx, [rbp+ppvObject]
0x180013cc6  mov     rax, [rcx]
0x180013cc9  mov     edx, 1
0x180013cce  mov     r8d, edx
0x180013cd1  mov     rax, [rax+28h]
0x180013cd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013cda  mov     edi, eax
0x180013cdc  test    eax, eax
0x180013cde  jns     short loc_180013D55
0x180013ce0  mov     [rsp+30h+var_8], eax
0x180013ce4  mov     [rsp+30h+var_10], 25Fh
0x180013cec  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x180013cf3  lea     r8, aWritepackageme_0; "WritePackageMetadata"
0x180013cfa  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180013d01  mov     ebx, 3
0x180013d06  mov     ecx, ebx
0x180013d08  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180013d0d  lea     rdx, aFailedToSetInd; "    Failed to set indent property"
0x180013d14  mov     ecx, ebx
0x180013d16  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180013d1b  nop
0x180013d1c  mov     rcx, [rbp+ppvObject]
0x180013d20  test    rcx, rcx
0x180013d23  jz      short loc_180013D36
0x180013d25  mov     [rbp+ppvObject], rsi
0x180013d29  mov     rax, [rcx]
0x180013d2c  mov     rax, [rax+10h]
0x180013d30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d35  nop
0x180013d36  mov     rcx, [rbp+arg_18]
0x180013d3a  test    rcx, rcx
0x180013d3d  jz      short loc_180013D50
0x180013d3f  mov     [rbp+arg_18], rsi
0x180013d43  mov     rax, [rcx]
0x180013d46  mov     rax, [rax+10h]
0x180013d4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d4f  nop
0x180013d50  jmp     loc_180013CBB
0x180013d55  mov     rcx, [rbp+ppvObject]
0x180013d59  mov     rax, [rcx]
0x180013d5c  xor     edx, edx
0x180013d5e  mov     rax, [rax+0D0h]
0x180013d65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d6a  mov     edi, eax
0x180013d6c  test    eax, eax
0x180013d6e  jns     short loc_180013DE5
0x180013d70  mov     [rsp+30h+var_8], eax
0x180013d74  mov     [rsp+30h+var_10], 262h
0x180013d7c  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x180013d83  lea     r8, aWritepackageme_0; "WritePackageMetadata"
0x180013d8a  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180013d91  mov     ebx, 3
0x180013d96  mov     ecx, ebx
0x180013d98  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180013d9d  lea     rdx, aFailedToWriteS_1; "    Failed to write start document"
0x180013da4  mov     ecx, ebx
0x180013da6  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180013dab  nop
0x180013dac  mov     rcx, [rbp+ppvObject]
0x180013db0  test    rcx, rcx
0x180013db3  jz      short loc_180013DC6
0x180013db5  mov     [rbp+ppvObject], rsi
0x180013db9  mov     rax, [rcx]
0x180013dbc  mov     rax, [rax+10h]
0x180013dc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013dc5  nop
0x180013dc6  mov     rcx, [rbp+arg_18]
0x180013dca  test    rcx, rcx
0x180013dcd  jz      short loc_180013DE0
0x180013dcf  mov     [rbp+arg_18], rsi
0x180013dd3  mov     rax, [rcx]
0x180013dd6  mov     rax, [rax+10h]
0x180013dda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ddf  nop
0x180013de0  jmp     loc_180013CBB
0x180013de5  mov     rcx, [rbp+ppvObject]
0x180013de9  mov     rax, [rcx]
0x180013dec  xor     r9d, r9d
0x180013def  lea     r8, aImage; "IMAGE"
0x180013df6  xor     edx, edx
0x180013df8  mov     rax, [rax+0D8h]
0x180013dff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e04  mov     edi, eax
0x180013e06  test    eax, eax
0x180013e08  jns     short loc_180013E7F
0x180013e0a  mov     [rsp+30h+var_8], eax
0x180013e0e  mov     [rsp+30h+var_10], 266h
0x180013e16  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x180013e1d  lea     r8, aWritepackageme_0; "WritePackageMetadata"
0x180013e24  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180013e2b  mov     ebx, 3
0x180013e30  mov     ecx, ebx
0x180013e32  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180013e37  lea     rdx, aFailedToWriteI_1; "    Failed to write image start element"
0x180013e3e  mov     ecx, ebx
0x180013e40  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180013e45  nop
0x180013e46  mov     rcx, [rbp+ppvObject]
0x180013e4a  test    rcx, rcx
0x180013e4d  jz      short loc_180013E60
0x180013e4f  mov     [rbp+ppvObject], rsi
0x180013e53  mov     rax, [rcx]
0x180013e56  mov     rax, [rax+10h]
0x180013e5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e5f  nop
0x180013e60  mov     rcx, [rbp+arg_18]
0x180013e64  test    rcx, rcx
0x180013e67  jz      short loc_180013E7A
0x180013e69  mov     [rbp+arg_18], rsi
0x180013e6d  mov     rax, [rcx]
0x180013e70  mov     rax, [rax+10h]
0x180013e74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e79  nop
0x180013e7a  jmp     loc_180013CBB
0x180013e7f  mov     rcx, [rbp+ppvObject]
0x180013e83  mov     rax, [rcx]
0x180013e86  lea     rdx, asc_18001AD68; "\n"
0x180013e8d  mov     rax, [rax+0F0h]
0x180013e94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e99  mov     edi, eax
0x180013e9b  test    eax, eax
0x180013e9d  jns     short loc_180013F14
0x180013e9f  mov     [rsp+30h+var_8], eax
0x180013ea3  mov     [rsp+30h+var_10], 269h
0x180013eab  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x180013eb2  lea     r8, aWritepackageme_0; "WritePackageMetadata"
0x180013eb9  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180013ec0  mov     ebx, 3
0x180013ec5  mov     ecx, ebx
0x180013ec7  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180013ecc  lea     rdx, aFailedToWriteW; "    Failed to write whitespace"
0x180013ed3  mov     ecx, ebx
0x180013ed5  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180013eda  nop
0x180013edb  mov     rcx, [rbp+ppvObject]
0x180013edf  test    rcx, rcx
0x180013ee2  jz      short loc_180013EF5
0x180013ee4  mov     [rbp+ppvObject], rsi
0x180013ee8  mov     rax, [rcx]
0x180013eeb  mov     rax, [rax+10h]
0x180013eef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ef4  nop
0x180013ef5  mov     rcx, [rbp+arg_18]
0x180013ef9  test    rcx, rcx
0x180013efc  jz      short loc_180013F0F
0x180013efe  mov     [rbp+arg_18], rsi
0x180013f02  mov     rax, [rcx]
0x180013f05  mov     rax, [rax+10h]
0x180013f09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f0e  nop
0x180013f0f  jmp     loc_180013CBB
0x180013f14  mov     r8, [rbx+10h]; unsigned __int16 *
0x180013f18  lea     rdx, aName; "NAME"
0x180013f1f  mov     rcx, [rbp+ppvObject]; struct IXmlWriter *
0x180013f23  call    ?WritePackageMetadataBlock@@YAJPEAUIXmlWriter@@PEBG1@Z; WritePackageMetadataBlock(IXmlWriter *,ushort const *,ushort const *)
0x180013f28  mov     edi, eax
0x180013f2a  test    eax, eax
0x180013f2c  jns     short loc_180013FAA
0x180013f2e  mov     [rsp+30h+var_8], eax
0x180013f32  mov     [rsp+30h+var_10], 26Eh
0x180013f3a  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x180013f41  lea     r8, aWritepackageme_0; "WritePackageMetadata"
0x180013f48  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180013f4f  mov     ebx, 3
0x180013f54  mov     ecx, ebx
0x180013f56  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180013f5b  lea     r8, aName_0; "name"
0x180013f62  lea     rdx, aFailedToWriteP_2; "    Failed to write package metadata %s"...
0x180013f69  mov     ecx, ebx
0x180013f6b  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180013f70  nop
0x180013f71  mov     rcx, [rbp+ppvObject]
0x180013f75  test    rcx, rcx
0x180013f78  jz      short loc_180013F8B
0x180013f7a  mov     [rbp+ppvObject], rsi
0x180013f7e  mov     rax, [rcx]
0x180013f81  mov     rax, [rax+10h]
0x180013f85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f8a  nop
0x180013f8b  mov     rcx, [rbp+arg_18]
0x180013f8f  test    rcx, rcx
0x180013f92  jz      short loc_180013FA5
0x180013f94  mov     [rbp+arg_18], rsi
0x180013f98  mov     rax, [rcx]
0x180013f9b  mov     rax, [rax+10h]
0x180013f9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013fa4  nop
0x180013fa5  jmp     loc_180013CBB
0x180013faa  mov     r8, [rbx+18h]; unsigned __int16 *
0x180013fae  lea     rdx, aDescription; "DESCRIPTION"
0x180013fb5  mov     rcx, [rbp+ppvObject]; struct IXmlWriter *
0x180013fb9  call    ?WritePackageMetadataBlock@@YAJPEAUIXmlWriter@@PEBG1@Z; WritePackageMetadataBlock(IXmlWriter *,ushort const *,ushort const *)
0x180013fbe  mov     edi, eax
0x180013fc0  test    eax, eax
0x180013fc2  jns     short loc_180014040
0x180013fc4  mov     [rsp+30h+var_8], eax
0x180013fc8  mov     [rsp+30h+var_10], 272h
0x180013fd0  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x180013fd7  lea     r8, aWritepackageme_0; "WritePackageMetadata"
0x180013fde  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180013fe5  mov     ebx, 3
0x180013fea  mov     ecx, ebx
0x180013fec  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180013ff1  lea     r8, aDescription_0; "description"
0x180013ff8  lea     rdx, aFailedToWriteP_2; "    Failed to write package metadata %s"...
0x180013fff  mov     ecx, ebx
0x180014001  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180014006  nop
0x180014007  mov     rcx, [rbp+ppvObject]
0x18001400b  test    rcx, rcx
0x18001400e  jz      short loc_180014021
0x180014010  mov     [rbp+ppvObject], rsi
0x180014014  mov     rax, [rcx]
0x180014017  mov     rax, [rax+10h]
0x18001401b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014020  nop
0x180014021  mov     rcx, [rbp+arg_18]
0x180014025  test    rcx, rcx
0x180014028  jz      short loc_18001403B
0x18001402a  mov     [rbp+arg_18], rsi
0x18001402e  mov     rax, [rcx]
0x180014031  mov     rax, [rax+10h]
0x180014035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001403a  nop
0x18001403b  jmp     loc_180013CBB
0x180014040  mov     r8, [rbx+20h]; unsigned __int16 *
0x180014044  lea     rdx, aNotes; "NOTES"
0x18001404b  mov     rcx, [rbp+ppvObject]; struct IXmlWriter *
0x18001404f  call    ?WritePackageMetadataBlock@@YAJPEAUIXmlWriter@@PEBG1@Z; WritePackageMetadataBlock(IXmlWriter *,ushort const *,ushort const *)
0x180014054  mov     edi, eax
0x180014056  test    eax, eax
0x180014058  jns     short loc_1800140D6
0x18001405a  mov     [rsp+30h+var_8], eax
0x18001405e  mov     [rsp+30h+var_10], 276h
0x180014066  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x18001406d  lea     r8, aWritepackageme_0; "WritePackageMetadata"
0x180014074  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18001407b  mov     ebx, 3
0x180014080  mov     ecx, ebx
0x180014082  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180014087  lea     r8, aNotes_0; "notes"
0x18001408e  lea     rdx, aFailedToWriteP_2; "    Failed to write package metadata %s"...
0x180014095  mov     ecx, ebx
0x180014097  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18001409c  nop
0x18001409d  mov     rcx, [rbp+ppvObject]
0x1800140a1  test    rcx, rcx
0x1800140a4  jz      short loc_1800140B7
0x1800140a6  mov     [rbp+ppvObject], rsi
0x1800140aa  mov     rax, [rcx]
0x1800140ad  mov     rax, [rax+10h]
0x1800140b1  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
