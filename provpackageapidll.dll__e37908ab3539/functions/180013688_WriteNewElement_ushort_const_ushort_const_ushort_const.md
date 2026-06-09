# WriteNewElement(ushort const *,ushort const *,ushort const *)

- ea: `0x180013688`
- end: `0x180013c11`
- name: `?WriteNewElement@@YAJPEBG00@Z`
- size: `1417`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x180014f8c`

## callees

- `0x180006014`
- `0x1800131ac`
- `0x18001345c`
- `0x180013688`
- `0x180019010`

## string_xrefs

- `0x1800136d4`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x180013768`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x1800137f8`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x180013892`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x18001392e`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x1800139bb`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x180013a46`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x180013ad1`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x180013b5f`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x1800138b3`: `    Failed to write element start element`
- `0x1800136db`: `WriteNewElement`
- `0x18001376f`: `WriteNewElement`
- `0x1800137ff`: `WriteNewElement`
- `0x180013899`: `WriteNewElement`
- `0x180013935`: `WriteNewElement`
- `0x1800139c2`: `WriteNewElement`
- `0x180013a4d`: `WriteNewElement`
- `0x180013ad8`: `WriteNewElement`
- `0x180013b66`: `WriteNewElement`
- `0x180013819`: `    Failed to write start document`
- `0x18001394f`: `    Failed to write element type attribute`
- `0x1800139dc`: `    Failed to write index element block`
- `0x180013a67`: `    Failed to write end element`
- `0x180013af2`: `    Failed to write end document`
- `0x180013b80`: `    Failed to flush writer`

## pseudocode

```c
__int64 __fastcall WriteNewElement(const unsigned __int16 *a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  int v5; // eax
  unsigned int v6; // edi
  struct IXmlWriter *v7; // rcx
  struct IStream *v8; // rcx
  int v10; // eax
  struct IXmlWriter *v11; // rcx
  struct IStream *v12; // rcx
  int v13; // eax
  struct IXmlWriter *v14; // rcx
  struct IStream *v15; // rcx
  int v16; // eax
  struct IXmlWriter *v17; // rcx
  struct IStream *v18; // rcx
  int v19; // eax
  struct IXmlWriter *v20; // rcx
  struct IStream *v21; // rcx
  int v22; // eax
  struct IXmlWriter *v23; // rcx
  struct IStream *v24; // rcx
  int v25; // eax
  struct IXmlWriter *v26; // rcx
  struct IStream *v27; // rcx
  int v28; // eax
  struct IXmlWriter *v29; // rcx
  struct IStream *v30; // rcx
  int v31; // eax
  struct IXmlWriter *v32; // rcx
  struct IStream *v33; // rcx
  struct IXmlWriter *v34; // rcx
  struct IStream *v35; // rcx
  int v36; // [rsp+20h] [rbp-20h]
  int v37; // [rsp+20h] [rbp-20h]
  int v38; // [rsp+20h] [rbp-20h]
  int v39; // [rsp+20h] [rbp-20h]
  __int64 v40; // [rsp+20h] [rbp-20h]
  int v41; // [rsp+28h] [rbp-18h]
  int v42; // [rsp+28h] [rbp-18h]
  int v43; // [rsp+28h] [rbp-18h]
  int v44; // [rsp+28h] [rbp-18h]
  int v45; // [rsp+28h] [rbp-18h]
  int v46; // [rsp+28h] [rbp-18h]
  int v47; // [rsp+28h] [rbp-18h]
  int v48; // [rsp+28h] [rbp-18h]
  int v49; // [rsp+28h] [rbp-18h]
  struct IStream *v50; // [rsp+30h] [rbp-10h] BYREF
  struct IXmlWriter *ppvObject; // [rsp+78h] [rbp+38h] BYREF

  v50 = 0;
  ppvObject = 0;
  v5 = SetupOutput(&v50, &ppvObject, a1, 1);
  v6 = v5;
  if ( v5 < 0 )
  {
    v41 = v5;
    v36 = 340;
    ProvPackageLog(
      3u,
      L"%hs (%hs:%d) - 0x%08x:",
      "WriteNewElement",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
      v36,
      v41);
    ProvPackageLog(3u, L"    Failed to setup output");
    v7 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      ((void (__fastcall *)(struct IXmlWriter *))v7->lpVtbl->Release)(v7);
    }
    v8 = v50;
    if ( v50 )
    {
      v50 = 0;
      ((void (__fastcall *)(struct IStream *))v8->lpVtbl->Release)(v8);
    }
    return v6;
  }
  v10 = ((__int64 (__fastcall *)(struct IXmlWriter *, __int64, __int64))ppvObject->lpVtbl->SetProperty)(ppvObject, 1, 1);
  v6 = v10;
  if ( v10 < 0 )
  {
    v42 = v10;
    v37 = 344;
    ProvPackageLog(
      3u,
      L"%hs (%hs:%d) - 0x%08x:",
      "WriteNewElement",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
      v37,
      v42);
    ProvPackageLog(3u, L"    Failed to set indent property");
    v11 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      ((void (__fastcall *)(struct IXmlWriter *))v11->lpVtbl->Release)(v11);
    }
    v12 = v50;
    if ( v50 )
    {
      v50 = 0;
      ((void (__fastcall *)(struct IStream *))v12->lpVtbl->Release)(v12);
    }
    return v6;
  }
  v13 = ((__int64 (__fastcall *)(struct IXmlWriter *, _QWORD))ppvObject->lpVtbl->WriteStartDocument)(ppvObject, 0);
  v6 = v13;
  if ( v13 < 0 )
  {
    v43 = v13;
    v38 = 347;
    ProvPackageLog(
      3u,
      L"%hs (%hs:%d) - 0x%08x:",
      "WriteNewElement",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
      v38,
      v43);
    ProvPackageLog(3u, L"    Failed to write start document");
    v14 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      ((void (__fastcall *)(struct IXmlWriter *))v14->lpVtbl->Release)(v14);
    }
    v15 = v50;
    if ( v50 )
    {
      v50 = 0;
      ((void (__fastcall *)(struct IStream *))v15->lpVtbl->Release)(v15);
    }
    return v6;
  }
  v16 = ((__int64 (__fastcall *)(struct IXmlWriter *, _QWORD, const unsigned __int16 *, _QWORD))ppvObject->lpVtbl->WriteStartElement)(
          ppvObject,
          0,
          L"Elements",
          0);
  v6 = v16;
  if ( v16 < 0 )
  {
    v44 = v16;
    v39 = 351;
    ProvPackageLog(
      3u,
      L"%hs (%hs:%d) - 0x%08x:",
      "WriteNewElement",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
      v39,
      v44);
    ProvPackageLog(3u, L"    Failed to write element start element");
    v17 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      ((void (__fastcall *)(struct IXmlWriter *))v17->lpVtbl->Release)(v17);
    }
    v18 = v50;
    if ( v50 )
    {
      v50 = 0;
      ((void (__fastcall *)(struct IStream *))v18->lpVtbl->Release)(v18);
    }
    return v6;
  }
  v19 = ((__int64 (__fastcall *)(struct IXmlWriter *, _QWORD, const wchar_t *, _QWORD, const unsigned __int16 *))ppvObject->lpVtbl->WriteAttributeString)(
          ppvObject,
          0,
          L"Type",
          0,
          a2);
  v6 = v19;
  if ( v19 < 0 )
  {
    v45 = v19;
    LODWORD(v40) = 354;
    ProvPackageLog(
      3u,
      L"%hs (%hs:%d) - 0x%08x:",
      "WriteNewElement",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
      v40,
      v45);
    ProvPackageLog(3u, L"    Failed to write element type attribute");
    v20 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      ((void (__fastcall *)(struct IXmlWriter *))v20->lpVtbl->Release)(v20);
    }
    v21 = v50;
    if ( v50 )
    {
      v50 = 0;
      ((void (__fastcall *)(struct IStream *))v21->lpVtbl->Release)(v21);
    }
    return v6;
  }
  v22 = WriteElementBlock(ppvObject, a3, 1);
  v6 = v22;
  if ( v22 < 0 )
  {
    v46 = v22;
    LODWORD(v40) = 358;
    ProvPackageLog(
      3u,
      L"%hs (%hs:%d) - 0x%08x:",
      "WriteNewElement",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
      v40,
      v46);
    ProvPackageLog(3u, L"    Failed to write index element block");
    v23 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      ((void (__fastcall *)(struct IXmlWriter *))v23->lpVtbl->Release)(v23);
    }
    v24 = v50;
    if ( v50 )
    {
      v50 = 0;
      ((void (__fastcall *)(struct IStream *))v24->lpVtbl->Release)(v24);
    }
    return v6;
  }
  v25 = ((__int64 (__fastcall *)(struct IXmlWriter *))ppvObject->lpVtbl->WriteEndElement)(ppvObject);
  v6 = v25;
  if ( v25 < 0 )
  {
    v47 = v25;
    LODWORD(v40) = 362;
    ProvPackageLog(
      3u,
      L"%hs (%hs:%d) - 0x%08x:",
      "WriteNewElement",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
      v40,
      v47);
    ProvPackageLog(3u, L"    Failed to write end element");
    v26 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      ((void (__fastcall *)(struct IXmlWriter *))v26->lpVtbl->Release)(v26);
    }
    v27 = v50;
    if ( v50 )
    {
      v50 = 0;
      ((void (__fastcall *)(struct IStream *))v27->lpVtbl->Release)(v27);
    }
    return v6;
  }
  v28 = ((__int64 (__fastcall *)(struct IXmlWriter *))ppvObject->lpVtbl->WriteEndDocument)(ppvObject);
  v6 = v28;
  if ( v28 < 0 )
  {
    v48 = v28;
    LODWORD(v40) = 365;
    ProvPackageLog(
      3u,
      L"%hs (%hs:%d) - 0x%08x:",
      "WriteNewElement",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
      v40,
      v48);
    ProvPackageLog(3u, L"    Failed to write end document");
    v29 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      ((void (__fastcall *)(struct IXmlWriter *))v29->lpVtbl->Release)(v29);
    }
    v30 = v50;
    if ( v50 )
    {
      v50 = 0;
      ((void (__fastcall *)(struct IStream *))v30->lpVtbl->Release)(v30);
    }
    return v6;
  }
  v31 = ((__int64 (__fastcall *)(struct IXmlWriter *))ppvObject->lpVtbl->Flush)(ppvObject);
  v6 = v31;
  if ( v31 < 0 )
  {
    v49 = v31;
    LODWORD(v40) = 368;
    ProvPackageLog(
      3u,
      L"%hs (%hs:%d) - 0x%08x:",
      "WriteNewElement",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
      v40,
      v49);
    ProvPackageLog(3u, L"    Failed to flush writer");
    v32 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      ((void (__fastcall *)(struct IXmlWriter *))v32->lpVtbl->Release)(v32);
    }
    v33 = v50;
    if ( v50 )
    {
      v50 = 0;
      ((void (__fastcall *)(struct IStream *))v33->lpVtbl->Release)(v33);
    }
    return v6;
  }
  v34 = ppvObject;
  if ( ppvObject )
  {
    ppvObject = 0;
    ((void (__fastcall *)(struct IXmlWriter *))v34->lpVtbl->Release)(v34);
  }
  v35 = v50;
  if ( v50 )
  {
    v50 = 0;
    ((void (__fastcall *)(struct IStream *))v35->lpVtbl->Release)(v35);
  }
  return 0;
}

```

## disassembly

```asm
0x180013688  mov     [rsp-18h+arg_0], rbx
0x18001368d  mov     [rsp-18h+arg_8], rsi
0x180013692  push    rbp
0x180013693  push    rdi
0x180013694  push    r14
0x180013696  mov     rbp, rsp
0x180013699  sub     rsp, 40h
0x18001369d  mov     rbx, r8
0x1800136a0  mov     rsi, rdx
0x1800136a3  xor     r14d, r14d
0x1800136a6  mov     [rbp+var_10], r14
0x1800136aa  mov     [rbp+ppvObject], r14
0x1800136ae  lea     r9d, [r14+1]; int
0x1800136b2  mov     r8, rcx; unsigned __int16 *
0x1800136b5  lea     rdx, [rbp+ppvObject]; ppvObject
0x1800136b9  lea     rcx, [rbp+var_10]; struct IStream **
0x1800136bd  call    ?SetupOutput@@YAJPEAPEAUIStream@@PEAPEAUIXmlWriter@@PEBGH@Z; SetupOutput(IStream * *,IXmlWriter * *,ushort const *,int)
0x1800136c2  mov     edi, eax
0x1800136c4  test    eax, eax
0x1800136c6  jns     short loc_18001373E
0x1800136c8  mov     [rsp+40h+var_18], eax
0x1800136cc  mov     dword ptr [rsp+40h+var_20], 154h
0x1800136d4  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x1800136db  lea     r8, aWritenewelemen; "WriteNewElement"
0x1800136e2  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x1800136e9  lea     ebx, [r14+3]
0x1800136ed  mov     ecx, ebx
0x1800136ef  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800136f4  lea     rdx, aFailedToSetupO; "    Failed to setup output"
0x1800136fb  mov     ecx, ebx
0x1800136fd  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180013702  nop
0x180013703  mov     rcx, [rbp+ppvObject]
0x180013707  test    rcx, rcx
0x18001370a  jz      short loc_18001371D
0x18001370c  mov     [rbp+ppvObject], r14
0x180013710  mov     rax, [rcx]
0x180013713  mov     rax, [rax+10h]
0x180013717  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001371c  nop
0x18001371d  mov     rcx, [rbp+var_10]
0x180013721  test    rcx, rcx
0x180013724  jz      short loc_180013737
0x180013726  mov     [rbp+var_10], r14
0x18001372a  mov     rax, [rcx]
0x18001372d  mov     rax, [rax+10h]
0x180013731  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013736  nop
0x180013737  mov     eax, edi
0x180013739  jmp     loc_180013BFE
0x18001373e  mov     rcx, [rbp+ppvObject]
0x180013742  mov     rax, [rcx]
0x180013745  mov     edx, 1
0x18001374a  mov     r8d, edx
0x18001374d  mov     rax, [rax+28h]
0x180013751  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013756  mov     edi, eax
0x180013758  test    eax, eax
0x18001375a  jns     short loc_1800137D1
0x18001375c  mov     [rsp+40h+var_18], eax
0x180013760  mov     dword ptr [rsp+40h+var_20], 158h
0x180013768  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x18001376f  lea     r8, aWritenewelemen; "WriteNewElement"
0x180013776  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18001377d  mov     ebx, 3
0x180013782  mov     ecx, ebx
0x180013784  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180013789  lea     rdx, aFailedToSetInd; "    Failed to set indent property"
0x180013790  mov     ecx, ebx
0x180013792  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180013797  nop
0x180013798  mov     rcx, [rbp+ppvObject]
0x18001379c  test    rcx, rcx
0x18001379f  jz      short loc_1800137B2
0x1800137a1  mov     [rbp+ppvObject], r14
0x1800137a5  mov     rax, [rcx]
0x1800137a8  mov     rax, [rax+10h]
0x1800137ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800137b1  nop
0x1800137b2  mov     rcx, [rbp+var_10]
0x1800137b6  test    rcx, rcx
0x1800137b9  jz      short loc_1800137CC
0x1800137bb  mov     [rbp+var_10], r14
0x1800137bf  mov     rax, [rcx]
0x1800137c2  mov     rax, [rax+10h]
0x1800137c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800137cb  nop
0x1800137cc  jmp     loc_180013737
0x1800137d1  mov     rcx, [rbp+ppvObject]
0x1800137d5  mov     rax, [rcx]
0x1800137d8  xor     edx, edx
0x1800137da  mov     rax, [rax+0D0h]
0x1800137e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800137e6  mov     edi, eax
0x1800137e8  test    eax, eax
0x1800137ea  jns     short loc_180013861
0x1800137ec  mov     [rsp+40h+var_18], eax
0x1800137f0  mov     dword ptr [rsp+40h+var_20], 15Bh
0x1800137f8  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x1800137ff  lea     r8, aWritenewelemen; "WriteNewElement"
0x180013806  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18001380d  mov     ebx, 3
0x180013812  mov     ecx, ebx
0x180013814  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180013819  lea     rdx, aFailedToWriteS_1; "    Failed to write start document"
0x180013820  mov     ecx, ebx
0x180013822  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180013827  nop
0x180013828  mov     rcx, [rbp+ppvObject]
0x18001382c  test    rcx, rcx
0x18001382f  jz      short loc_180013842
0x180013831  mov     [rbp+ppvObject], r14
0x180013835  mov     rax, [rcx]
0x180013838  mov     rax, [rax+10h]
0x18001383c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013841  nop
0x180013842  mov     rcx, [rbp+var_10]
0x180013846  test    rcx, rcx
0x180013849  jz      short loc_18001385C
0x18001384b  mov     [rbp+var_10], r14
0x18001384f  mov     rax, [rcx]
0x180013852  mov     rax, [rax+10h]
0x180013856  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001385b  nop
0x18001385c  jmp     loc_180013737
0x180013861  mov     rcx, [rbp+ppvObject]
0x180013865  mov     rax, [rcx]
0x180013868  xor     r9d, r9d
0x18001386b  lea     r8, aElements; "Elements"
0x180013872  xor     edx, edx
0x180013874  mov     rax, [rax+0D8h]
0x18001387b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013880  mov     edi, eax
0x180013882  test    eax, eax
0x180013884  jns     short loc_1800138FB
0x180013886  mov     [rsp+40h+var_18], eax
0x18001388a  mov     dword ptr [rsp+40h+var_20], 15Fh
0x180013892  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x180013899  lea     r8, aWritenewelemen; "WriteNewElement"
0x1800138a0  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x1800138a7  mov     ebx, 3
0x1800138ac  mov     ecx, ebx
0x1800138ae  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800138b3  lea     rdx, aFailedToWriteE_4; "    Failed to write element start eleme"...
0x1800138ba  mov     ecx, ebx
0x1800138bc  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800138c1  nop
0x1800138c2  mov     rcx, [rbp+ppvObject]
0x1800138c6  test    rcx, rcx
0x1800138c9  jz      short loc_1800138DC
0x1800138cb  mov     [rbp+ppvObject], r14
0x1800138cf  mov     rax, [rcx]
0x1800138d2  mov     rax, [rax+10h]
0x1800138d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138db  nop
0x1800138dc  mov     rcx, [rbp+var_10]
0x1800138e0  test    rcx, rcx
0x1800138e3  jz      short loc_1800138F6
0x1800138e5  mov     [rbp+var_10], r14
0x1800138e9  mov     rax, [rcx]
0x1800138ec  mov     rax, [rax+10h]
0x1800138f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138f5  nop
0x1800138f6  jmp     loc_180013737
0x1800138fb  mov     rcx, [rbp+ppvObject]
0x1800138ff  mov     rax, [rcx]
0x180013902  mov     [rsp+40h+var_20], rsi
0x180013907  xor     r9d, r9d
0x18001390a  lea     r8, aType; "Type"
0x180013911  xor     edx, edx
0x180013913  mov     rax, [rax+38h]
0x180013917  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001391c  mov     edi, eax
0x18001391e  test    eax, eax
0x180013920  jns     short loc_180013997
0x180013922  mov     [rsp+40h+var_18], eax
0x180013926  mov     dword ptr [rsp+40h+var_20], 162h
0x18001392e  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x180013935  lea     r8, aWritenewelemen; "WriteNewElement"
0x18001393c  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180013943  mov     ebx, 3
0x180013948  mov     ecx, ebx
0x18001394a  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18001394f  lea     rdx, aFailedToWriteE_5; "    Failed to write element type attrib"...
0x180013956  mov     ecx, ebx
0x180013958  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18001395d  nop
0x18001395e  mov     rcx, [rbp+ppvObject]
0x180013962  test    rcx, rcx
0x180013965  jz      short loc_180013978
0x180013967  mov     [rbp+ppvObject], r14
0x18001396b  mov     rax, [rcx]
0x18001396e  mov     rax, [rax+10h]
0x180013972  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013977  nop
0x180013978  mov     rcx, [rbp+var_10]
0x18001397c  test    rcx, rcx
0x18001397f  jz      short loc_180013992
0x180013981  mov     [rbp+var_10], r14
0x180013985  mov     rax, [rcx]
0x180013988  mov     rax, [rax+10h]
0x18001398c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013991  nop
0x180013992  jmp     loc_180013737
0x180013997  mov     r8d, 1; int
0x18001399d  mov     rdx, rbx; unsigned __int16 *
0x1800139a0  mov     rcx, [rbp+ppvObject]; struct IXmlWriter *
0x1800139a4  call    ?WriteElementBlock@@YAJPEAUIXmlWriter@@PEBGH@Z; WriteElementBlock(IXmlWriter *,ushort const *,int)
0x1800139a9  mov     edi, eax
0x1800139ab  test    eax, eax
0x1800139ad  jns     short loc_180013A24
0x1800139af  mov     [rsp+40h+var_18], eax
0x1800139b3  mov     dword ptr [rsp+40h+var_20], 166h
0x1800139bb  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x1800139c2  lea     r8, aWritenewelemen; "WriteNewElement"
0x1800139c9  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x1800139d0  mov     ebx, 3
0x1800139d5  mov     ecx, ebx
0x1800139d7  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800139dc  lea     rdx, aFailedToWriteI_0; "    Failed to write index element block"
0x1800139e3  mov     ecx, ebx
0x1800139e5  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800139ea  nop
0x1800139eb  mov     rcx, [rbp+ppvObject]
0x1800139ef  test    rcx, rcx
0x1800139f2  jz      short loc_180013A05
0x1800139f4  mov     [rbp+ppvObject], r14
0x1800139f8  mov     rax, [rcx]
0x1800139fb  mov     rax, [rax+10h]
0x1800139ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a04  nop
0x180013a05  mov     rcx, [rbp+var_10]
0x180013a09  test    rcx, rcx
0x180013a0c  jz      short loc_180013A1F
0x180013a0e  mov     [rbp+var_10], r14
0x180013a12  mov     rax, [rcx]
0x180013a15  mov     rax, [rax+10h]
0x180013a19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a1e  nop
0x180013a1f  jmp     loc_180013737
0x180013a24  mov     rcx, [rbp+ppvObject]
0x180013a28  mov     rax, [rcx]
0x180013a2b  mov     rax, [rax+78h]
0x180013a2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a34  mov     edi, eax
0x180013a36  test    eax, eax
0x180013a38  jns     short loc_180013AAF
0x180013a3a  mov     [rsp+40h+var_18], eax
0x180013a3e  mov     dword ptr [rsp+40h+var_20], 16Ah
0x180013a46  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x180013a4d  lea     r8, aWritenewelemen; "WriteNewElement"
0x180013a54  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180013a5b  mov     ebx, 3
0x180013a60  mov     ecx, ebx
0x180013a62  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180013a67  lea     rdx, aFailedToWriteE_1; "    Failed to write end element"
0x180013a6e  mov     ecx, ebx
0x180013a70  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180013a75  nop
0x180013a76  mov     rcx, [rbp+ppvObject]
0x180013a7a  test    rcx, rcx
0x180013a7d  jz      short loc_180013A90
0x180013a7f  mov     [rbp+ppvObject], r14
0x180013a83  mov     rax, [rcx]
0x180013a86  mov     rax, [rax+10h]
0x180013a8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a8f  nop
0x180013a90  mov     rcx, [rbp+var_10]
0x180013a94  test    rcx, rcx
0x180013a97  jz      short loc_180013AAA
0x180013a99  mov     [rbp+var_10], r14
0x180013a9d  mov     rax, [rcx]
0x180013aa0  mov     rax, [rax+10h]
0x180013aa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013aa9  nop
0x180013aaa  jmp     loc_180013737
0x180013aaf  mov     rcx, [rbp+ppvObject]
0x180013ab3  mov     rax, [rcx]
0x180013ab6  mov     rax, [rax+70h]
0x180013aba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013abf  mov     edi, eax
0x180013ac1  test    eax, eax
0x180013ac3  jns     short loc_180013B3A
0x180013ac5  mov     [rsp+40h+var_18], eax
0x180013ac9  mov     dword ptr [rsp+40h+var_20], 16Dh
0x180013ad1  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x180013ad8  lea     r8, aWritenewelemen; "WriteNewElement"
0x180013adf  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180013ae6  mov     ebx, 3
0x180013aeb  mov     ecx, ebx
0x180013aed  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180013af2  lea     rdx, aFailedToWriteE_6; "    Failed to write end document"
0x180013af9  mov     ecx, ebx
0x180013afb  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180013b00  nop
0x180013b01  mov     rcx, [rbp+ppvObject]
0x180013b05  test    rcx, rcx
0x180013b08  jz      short loc_180013B1B
0x180013b0a  mov     [rbp+ppvObject], r14
0x180013b0e  mov     rax, [rcx]
  ... truncated ...
```
