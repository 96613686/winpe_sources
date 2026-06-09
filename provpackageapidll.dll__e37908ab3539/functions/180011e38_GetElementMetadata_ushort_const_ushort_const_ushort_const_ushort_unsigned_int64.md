# GetElementMetadata(ushort const *,ushort const *,ushort const *,ushort *,unsigned __int64)

- ea: `0x180011e38`
- end: `0x18001243d`
- name: `?GetElementMetadata@@YAJPEBG00PEAG_K@Z`
- size: `1541`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x180014870`
- `0x180016560`

## callees

- `0x180006014`
- `0x1800118ac`
- `0x180011c88`
- `0x180011e38`
- `0x1800130cc`
- `0x180013290`
- `0x180019010`

## string_xrefs

- `0x180011e89`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x180011fdb`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x180012066`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x180012116`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x18001218b`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x180012200`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x18001227d`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x1800122e2`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x180012357`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x1800123c9`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x1800121ac`: `    Failed to move to first attribute`
- `0x180012378`: `    Failed to move to first attribute`
- `0x180011ffc`: `    Failed to move to next attribute`

## pseudocode

```c
__int64 __fastcall GetElementMetadata(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int64 a5)
{
  int v8; // eax
  unsigned int v9; // edi
  struct IXmlReader *v10; // rcx
  struct IStream *v11; // rcx
  int Node; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  const unsigned __int16 *v19; // rdx
  struct IXmlReader *v20; // rcx
  struct IStream *v21; // rcx
  int AttributeValue; // eax
  struct IXmlReader *v23; // rcx
  struct IStream *v24; // rcx
  struct IXmlReader *v25; // rcx
  struct IStream *v26; // rcx
  struct IXmlReader *v28; // rcx
  struct IStream *v29; // rcx
  struct IXmlReader *v30; // rcx
  struct IStream *v31; // rcx
  struct IXmlReader *v32; // rcx
  struct IStream *v33; // rcx
  struct IXmlReader *v34; // rcx
  struct IStream *v35; // rcx
  struct IXmlReader *v36; // rcx
  struct IStream *v37; // rcx
  struct IXmlReader *v38; // rcx
  struct IStream *v39; // rcx
  struct IXmlReader *v40; // rcx
  struct IStream *v41; // rcx
  struct IXmlReader *ppvObject; // [rsp+30h] [rbp-18h] BYREF
  struct IStream *v43; // [rsp+38h] [rbp-10h] BYREF

  if ( a5 )
    *a4 = 0;
  v43 = 0;
  ppvObject = 0;
  v8 = SetupInput(&v43, &ppvObject, a1);
  v9 = v8;
  if ( v8 >= 0 )
  {
    do
    {
      Node = FindNode(ppvObject, 0, L"Element", 0);
      v9 = Node;
      if ( Node < 0 )
      {
        ProvPackageLog(
          3,
          L"%hs (%hs:%d) - 0x%08x:",
          "GetElementMetadata",
          "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
          552,
          Node);
        ProvPackageLog(3, L"    Failed to find element start node");
        v40 = ppvObject;
        if ( ppvObject )
        {
          ppvObject = 0;
          ((void (__fastcall *)(struct IXmlReader *))v40->lpVtbl->Release)(v40);
        }
        v41 = v43;
        if ( v43 )
        {
          v43 = 0;
          ((void (__fastcall *)(struct IStream *))v41->lpVtbl->Release)(v41);
        }
        return v9;
      }
      v13 = ((__int64 (__fastcall *)(struct IXmlReader *))ppvObject->lpVtbl->MoveToFirstAttribute)(ppvObject);
      v9 = v13;
      if ( v13 < 0 )
      {
        ProvPackageLog(
          3,
          L"%hs (%hs:%d) - 0x%08x:",
          "GetElementMetadata",
          "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
          555,
          v13);
        ProvPackageLog(3, L"    Failed to move to first attribute");
        v38 = ppvObject;
        if ( ppvObject )
        {
          ppvObject = 0;
          ((void (__fastcall *)(struct IXmlReader *))v38->lpVtbl->Release)(v38);
        }
        v39 = v43;
        if ( v43 )
        {
          v43 = 0;
          ((void (__fastcall *)(struct IStream *))v39->lpVtbl->Release)(v39);
        }
        return v9;
      }
      v14 = VerifyAttribute(ppvObject, L"Index", a2);
      v9 = v14;
      if ( v14 < 0 )
      {
        ProvPackageLog(
          3,
          L"%hs (%hs:%d) - 0x%08x:",
          "GetElementMetadata",
          "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
          558,
          v14);
        ProvPackageLog(3, L"    Failed to verify index attribute");
        v36 = ppvObject;
        if ( ppvObject )
        {
          ppvObject = 0;
          ((void (__fastcall *)(struct IXmlReader *))v36->lpVtbl->Release)(v36);
        }
        v37 = v43;
        if ( v43 )
        {
          v43 = 0;
          ((void (__fastcall *)(struct IStream *))v37->lpVtbl->Release)(v37);
        }
        return v9;
      }
    }
    while ( v14 );
    do
    {
      v15 = FindNode(ppvObject, 0, L"Metadata", L"Element");
      v9 = v15;
      if ( v15 == -2147023728 )
      {
        ProvPackageLog(
          0,
          L"%hs (%hs:%d): %s",
          "GetElementMetadata",
          "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
          567,
          L"Node not found");
        v34 = ppvObject;
        if ( ppvObject )
        {
          ppvObject = 0;
          ((void (__fastcall *)(struct IXmlReader *))v34->lpVtbl->Release)(v34);
        }
        v35 = v43;
        if ( v43 )
        {
          v43 = 0;
          ((void (__fastcall *)(struct IStream *))v35->lpVtbl->Release)(v35);
        }
        return 2147943568LL;
      }
      if ( v15 < 0 )
      {
        ProvPackageLog(
          3,
          L"%hs (%hs:%d) - 0x%08x:",
          "GetElementMetadata",
          "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
          570,
          v15);
        ProvPackageLog(3, L"    Failed to find metadata start node before element stop node");
        v32 = ppvObject;
        if ( ppvObject )
        {
          ppvObject = 0;
          ((void (__fastcall *)(struct IXmlReader *))v32->lpVtbl->Release)(v32);
        }
        v33 = v43;
        if ( v43 )
        {
          v43 = 0;
          ((void (__fastcall *)(struct IStream *))v33->lpVtbl->Release)(v33);
        }
        return v9;
      }
      v16 = ((__int64 (__fastcall *)(struct IXmlReader *))ppvObject->lpVtbl->MoveToFirstAttribute)(ppvObject);
      v9 = v16;
      if ( v16 < 0 )
      {
        ProvPackageLog(
          3,
          L"%hs (%hs:%d) - 0x%08x:",
          "GetElementMetadata",
          "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
          573,
          v16);
        ProvPackageLog(3, L"    Failed to move to first attribute");
        v30 = ppvObject;
        if ( ppvObject )
        {
          ppvObject = 0;
          ((void (__fastcall *)(struct IXmlReader *))v30->lpVtbl->Release)(v30);
        }
        v31 = v43;
        if ( v43 )
        {
          v43 = 0;
          ((void (__fastcall *)(struct IStream *))v31->lpVtbl->Release)(v31);
        }
        return v9;
      }
      v17 = VerifyAttribute(ppvObject, L"Key", a3);
      v9 = v17;
      if ( v17 < 0 )
      {
        ProvPackageLog(
          3,
          L"%hs (%hs:%d) - 0x%08x:",
          "GetElementMetadata",
          "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
          576,
          v17);
        ProvPackageLog(3, L"    FAiled to verify key attribute");
        v28 = ppvObject;
        if ( ppvObject )
        {
          ppvObject = 0;
          ((void (__fastcall *)(struct IXmlReader *))v28->lpVtbl->Release)(v28);
        }
        v29 = v43;
        if ( v43 )
        {
          v43 = 0;
          ((void (__fastcall *)(struct IStream *))v29->lpVtbl->Release)(v29);
        }
        return v9;
      }
    }
    while ( v17 );
    v18 = ((__int64 (__fastcall *)(struct IXmlReader *))ppvObject->lpVtbl->MoveToNextAttribute)(ppvObject);
    v9 = v18;
    if ( v18 < 0 )
    {
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "GetElementMetadata",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
        581,
        v18);
      ProvPackageLog(3, L"    Failed to move to next attribute");
      v20 = ppvObject;
      if ( ppvObject )
      {
        ppvObject = 0;
        ((void (__fastcall *)(struct IXmlReader *))v20->lpVtbl->Release)(v20);
      }
      v21 = v43;
      if ( v43 )
      {
        v43 = 0;
        ((void (__fastcall *)(struct IStream *))v21->lpVtbl->Release)(v21);
      }
      return v9;
    }
    AttributeValue = GetAttributeValue(ppvObject, v19, a4, a5);
    v9 = AttributeValue;
    if ( AttributeValue < 0 )
    {
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "GetElementMetadata",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
        586,
        AttributeValue);
      ProvPackageLog(3, L"    Failed to get value attribute value");
      v23 = ppvObject;
      if ( ppvObject )
      {
        ppvObject = 0;
        ((void (__fastcall *)(struct IXmlReader *))v23->lpVtbl->Release)(v23);
      }
      v24 = v43;
      if ( v43 )
      {
        v43 = 0;
        ((void (__fastcall *)(struct IStream *))v24->lpVtbl->Release)(v24);
      }
      return v9;
    }
    v25 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      ((void (__fastcall *)(struct IXmlReader *))v25->lpVtbl->Release)(v25);
    }
    v26 = v43;
    if ( v43 )
    {
      v43 = 0;
      ((void (__fastcall *)(struct IStream *))v26->lpVtbl->Release)(v26);
    }
    return 0;
  }
  else
  {
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "GetElementMetadata",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
      546,
      v8);
    ProvPackageLog(3, L"    Failed to setup input");
    v10 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      ((void (__fastcall *)(struct IXmlReader *))v10->lpVtbl->Release)(v10);
    }
    v11 = v43;
    if ( v43 )
    {
      v43 = 0;
      ((void (__fastcall *)(struct IStream *))v11->lpVtbl->Release)(v11);
    }
    return v9;
  }
}

```

## disassembly

```asm
0x180011e38  push    rbp
0x180011e3a  push    rbx
0x180011e3b  push    rdi
0x180011e3c  push    r12
0x180011e3e  push    r14
0x180011e40  push    r15
0x180011e42  mov     rbp, rsp
0x180011e45  sub     rsp, 48h
0x180011e49  mov     rbx, r9
0x180011e4c  mov     r15, r8
0x180011e4f  mov     r14, rdx
0x180011e52  xor     r12d, r12d
0x180011e55  cmp     [rbp+arg_20], r12
0x180011e59  jbe     short loc_180011E5F
0x180011e5b  mov     [r9], r12w
0x180011e5f  mov     [rbp+var_10], r12
0x180011e63  mov     [rbp+ppvObject], r12
0x180011e67  mov     r8, rcx; unsigned __int16 *
0x180011e6a  lea     rdx, [rbp+ppvObject]; ppvObject
0x180011e6e  lea     rcx, [rbp+var_10]; struct IStream **
0x180011e72  call    ?SetupInput@@YAJPEAPEAUIStream@@PEAPEAUIXmlReader@@PEBG@Z; SetupInput(IStream * *,IXmlReader * *,ushort const *)
0x180011e77  mov     edi, eax
0x180011e79  test    eax, eax
0x180011e7b  jns     short loc_180011EF2
0x180011e7d  mov     dword ptr [rsp+48h+var_20], eax
0x180011e81  mov     [rsp+48h+var_28], 222h
0x180011e89  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x180011e90  lea     r8, aGetelementmeta; "GetElementMetadata"
0x180011e97  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180011e9e  mov     ebx, 3
0x180011ea3  mov     ecx, ebx
0x180011ea5  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180011eaa  lea     rdx, aFailedToSetupI; "    Failed to setup input"
0x180011eb1  mov     ecx, ebx
0x180011eb3  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180011eb8  nop
0x180011eb9  mov     rcx, [rbp+ppvObject]
0x180011ebd  test    rcx, rcx
0x180011ec0  jz      short loc_180011ED3
0x180011ec2  mov     [rbp+ppvObject], r12
0x180011ec6  mov     rax, [rcx]
0x180011ec9  mov     rax, [rax+10h]
0x180011ecd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ed2  nop
0x180011ed3  mov     rcx, [rbp+var_10]
0x180011ed7  test    rcx, rcx
0x180011eda  jz      short loc_180011EED
0x180011edc  mov     [rbp+var_10], r12
0x180011ee0  mov     rax, [rcx]
0x180011ee3  mov     rax, [rax+10h]
0x180011ee7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011eec  nop
0x180011eed  jmp     loc_18001242D
0x180011ef2  xor     r9d, r9d; unsigned __int16 *
0x180011ef5  lea     r8, aElement_0; "Element"
0x180011efc  xor     edx, edx; struct IXmlWriter *
0x180011efe  mov     rcx, [rbp+ppvObject]; struct IXmlReader *
0x180011f02  call    ?FindNode@@YAJPEAUIXmlReader@@PEAUIXmlWriter@@PEBG2@Z; FindNode(IXmlReader *,IXmlWriter *,ushort const *,ushort const *)
0x180011f07  mov     edi, eax
0x180011f09  test    eax, eax
0x180011f0b  js      loc_1800123BD
0x180011f11  mov     rcx, [rbp+ppvObject]
0x180011f15  mov     rax, [rcx]
0x180011f18  mov     rax, [rax+40h]
0x180011f1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f21  mov     edi, eax
0x180011f23  test    eax, eax
0x180011f25  js      loc_18001234B
0x180011f2b  mov     r8, r14; unsigned __int16 *
0x180011f2e  lea     rdx, aIndex_0; "Index"
0x180011f35  mov     rcx, [rbp+ppvObject]; struct IXmlReader *
0x180011f39  call    ?VerifyAttribute@@YAJPEAUIXmlReader@@PEBG1@Z; VerifyAttribute(IXmlReader *,ushort const *,ushort const *)
0x180011f3e  mov     edi, eax
0x180011f40  test    eax, eax
0x180011f42  js      loc_1800122D6
0x180011f48  test    eax, eax
0x180011f4a  jnz     short loc_180011EF2
0x180011f4c  mov     r14d, 80070490h
0x180011f52  lea     r9, aElement_0; "Element"
0x180011f59  lea     r8, aMetadata; "Metadata"
0x180011f60  xor     edx, edx; struct IXmlWriter *
0x180011f62  mov     rcx, [rbp+ppvObject]; struct IXmlReader *
0x180011f66  call    ?FindNode@@YAJPEAUIXmlReader@@PEAUIXmlWriter@@PEBG2@Z; FindNode(IXmlReader *,IXmlWriter *,ushort const *,ushort const *)
0x180011f6b  mov     edi, eax
0x180011f6d  cmp     eax, r14d
0x180011f70  jz      loc_180012269
0x180011f76  test    eax, eax
0x180011f78  js      loc_1800121F4
0x180011f7e  mov     rcx, [rbp+ppvObject]
0x180011f82  mov     rax, [rcx]
0x180011f85  mov     rax, [rax+40h]
0x180011f89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f8e  mov     edi, eax
0x180011f90  test    eax, eax
0x180011f92  js      loc_18001217F
0x180011f98  mov     r8, r15; unsigned __int16 *
0x180011f9b  lea     rdx, aKey; "Key"
0x180011fa2  mov     rcx, [rbp+ppvObject]; struct IXmlReader *
0x180011fa6  call    ?VerifyAttribute@@YAJPEAUIXmlReader@@PEBG1@Z; VerifyAttribute(IXmlReader *,ushort const *,ushort const *)
0x180011fab  mov     edi, eax
0x180011fad  test    eax, eax
0x180011faf  js      loc_18001210A
0x180011fb5  test    eax, eax
0x180011fb7  jnz     short loc_180011F52
0x180011fb9  mov     rcx, [rbp+ppvObject]
0x180011fbd  mov     rax, [rcx]
0x180011fc0  mov     rax, [rax+48h]
0x180011fc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011fc9  mov     edi, eax
0x180011fcb  test    eax, eax
0x180011fcd  jns     short loc_180012044
0x180011fcf  mov     dword ptr [rsp+48h+var_20], eax
0x180011fd3  mov     [rsp+48h+var_28], 245h
0x180011fdb  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x180011fe2  lea     r8, aGetelementmeta; "GetElementMetadata"
0x180011fe9  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180011ff0  mov     ebx, 3
0x180011ff5  mov     ecx, ebx
0x180011ff7  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180011ffc  lea     rdx, aFailedToMoveTo; "    Failed to move to next attribute"
0x180012003  mov     ecx, ebx
0x180012005  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18001200a  nop
0x18001200b  mov     rcx, [rbp+ppvObject]
0x18001200f  test    rcx, rcx
0x180012012  jz      short loc_180012025
0x180012014  mov     [rbp+ppvObject], r12
0x180012018  mov     rax, [rcx]
0x18001201b  mov     rax, [rax+10h]
0x18001201f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012024  nop
0x180012025  mov     rcx, [rbp+var_10]
0x180012029  test    rcx, rcx
0x18001202c  jz      short loc_18001203F
0x18001202e  mov     [rbp+var_10], r12
0x180012032  mov     rax, [rcx]
0x180012035  mov     rax, [rax+10h]
0x180012039  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001203e  nop
0x18001203f  jmp     loc_18001242D
0x180012044  mov     r9, [rbp+arg_20]; unsigned __int64
0x180012048  mov     r8, rbx; unsigned __int16 *
0x18001204b  mov     rcx, [rbp+ppvObject]; struct IXmlReader *
0x18001204f  call    ?GetAttributeValue@@YAJPEAUIXmlReader@@PEBGPEAG_K@Z; GetAttributeValue(IXmlReader *,ushort const *,ushort *,unsigned __int64)
0x180012054  mov     edi, eax
0x180012056  test    eax, eax
0x180012058  jns     short loc_1800120CF
0x18001205a  mov     dword ptr [rsp+48h+var_20], eax
0x18001205e  mov     [rsp+48h+var_28], 24Ah
0x180012066  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x18001206d  lea     r8, aGetelementmeta; "GetElementMetadata"
0x180012074  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18001207b  mov     ebx, 3
0x180012080  mov     ecx, ebx
0x180012082  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180012087  lea     rdx, aFailedToGetVal; "    Failed to get value attribute value"
0x18001208e  mov     ecx, ebx
0x180012090  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180012095  nop
0x180012096  mov     rcx, [rbp+ppvObject]
0x18001209a  test    rcx, rcx
0x18001209d  jz      short loc_1800120B0
0x18001209f  mov     [rbp+ppvObject], r12
0x1800120a3  mov     rax, [rcx]
0x1800120a6  mov     rax, [rax+10h]
0x1800120aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120af  nop
0x1800120b0  mov     rcx, [rbp+var_10]
0x1800120b4  test    rcx, rcx
0x1800120b7  jz      short loc_1800120CA
0x1800120b9  mov     [rbp+var_10], r12
0x1800120bd  mov     rax, [rcx]
0x1800120c0  mov     rax, [rax+10h]
0x1800120c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120c9  nop
0x1800120ca  jmp     loc_18001242D
0x1800120cf  mov     rcx, [rbp+ppvObject]
0x1800120d3  test    rcx, rcx
0x1800120d6  jz      short loc_1800120E9
0x1800120d8  mov     [rbp+ppvObject], r12
0x1800120dc  mov     rax, [rcx]
0x1800120df  mov     rax, [rax+10h]
0x1800120e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120e8  nop
0x1800120e9  mov     rcx, [rbp+var_10]
0x1800120ed  test    rcx, rcx
0x1800120f0  jz      short loc_180012103
0x1800120f2  mov     [rbp+var_10], r12
0x1800120f6  mov     rax, [rcx]
0x1800120f9  mov     rax, [rax+10h]
0x1800120fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012102  nop
0x180012103  xor     eax, eax
0x180012105  jmp     loc_18001242F
0x18001210a  mov     dword ptr [rsp+48h+var_20], edi
0x18001210e  mov     [rsp+48h+var_28], 240h
0x180012116  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x18001211d  lea     r8, aGetelementmeta; "GetElementMetadata"
0x180012124  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18001212b  mov     ebx, 3
0x180012130  mov     ecx, ebx
0x180012132  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180012137  lea     rdx, aFailedToVerify_1; "    FAiled to verify key attribute"
0x18001213e  mov     ecx, ebx
0x180012140  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180012145  nop
0x180012146  mov     rcx, [rbp+ppvObject]
0x18001214a  test    rcx, rcx
0x18001214d  jz      short loc_180012160
0x18001214f  mov     [rbp+ppvObject], r12
0x180012153  mov     rax, [rcx]
0x180012156  mov     rax, [rax+10h]
0x18001215a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001215f  nop
0x180012160  mov     rcx, [rbp+var_10]
0x180012164  test    rcx, rcx
0x180012167  jz      short loc_18001217A
0x180012169  mov     [rbp+var_10], r12
0x18001216d  mov     rax, [rcx]
0x180012170  mov     rax, [rax+10h]
0x180012174  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012179  nop
0x18001217a  jmp     loc_18001242D
0x18001217f  mov     dword ptr [rsp+48h+var_20], edi
0x180012183  mov     [rsp+48h+var_28], 23Dh
0x18001218b  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x180012192  lea     r8, aGetelementmeta; "GetElementMetadata"
0x180012199  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x1800121a0  mov     ebx, 3
0x1800121a5  mov     ecx, ebx
0x1800121a7  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800121ac  lea     rdx, aFailedToMoveTo_0; "    Failed to move to first attribute"
0x1800121b3  mov     ecx, ebx
0x1800121b5  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800121ba  nop
0x1800121bb  mov     rcx, [rbp+ppvObject]
0x1800121bf  test    rcx, rcx
0x1800121c2  jz      short loc_1800121D5
0x1800121c4  mov     [rbp+ppvObject], r12
0x1800121c8  mov     rax, [rcx]
0x1800121cb  mov     rax, [rax+10h]
0x1800121cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800121d4  nop
0x1800121d5  mov     rcx, [rbp+var_10]
0x1800121d9  test    rcx, rcx
0x1800121dc  jz      short loc_1800121EF
0x1800121de  mov     [rbp+var_10], r12
0x1800121e2  mov     rax, [rcx]
0x1800121e5  mov     rax, [rax+10h]
0x1800121e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800121ee  nop
0x1800121ef  jmp     loc_18001242D
0x1800121f4  mov     dword ptr [rsp+48h+var_20], edi
0x1800121f8  mov     [rsp+48h+var_28], 23Ah
0x180012200  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x180012207  lea     r8, aGetelementmeta; "GetElementMetadata"
0x18001220e  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180012215  mov     ebx, 3
0x18001221a  mov     ecx, ebx
0x18001221c  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180012221  lea     rdx, aFailedToFindMe; "    Failed to find metadata start node "...
0x180012228  mov     ecx, ebx
0x18001222a  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18001222f  nop
0x180012230  mov     rcx, [rbp+ppvObject]
0x180012234  test    rcx, rcx
0x180012237  jz      short loc_18001224A
0x180012239  mov     [rbp+ppvObject], r12
0x18001223d  mov     rax, [rcx]
0x180012240  mov     rax, [rax+10h]
0x180012244  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012249  nop
0x18001224a  mov     rcx, [rbp+var_10]
0x18001224e  test    rcx, rcx
0x180012251  jz      short loc_180012264
0x180012253  mov     [rbp+var_10], r12
0x180012257  mov     rax, [rcx]
0x18001225a  mov     rax, [rax+10h]
0x18001225e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012263  nop
0x180012264  jmp     loc_18001242D
0x180012269  lea     rax, aNodeNotFound; "Node not found"
0x180012270  mov     [rsp+48h+var_20], rax
0x180012275  mov     [rsp+48h+var_28], 237h
0x18001227d  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x180012284  lea     r8, aGetelementmeta; "GetElementMetadata"
0x18001228b  lea     rdx, aHsHsDS; "%hs (%hs:%d): %s"
0x180012292  xor     ecx, ecx
0x180012294  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180012299  nop
0x18001229a  mov     rcx, [rbp+ppvObject]
0x18001229e  test    rcx, rcx
0x1800122a1  jz      short loc_1800122B4
0x1800122a3  mov     [rbp+ppvObject], r12
0x1800122a7  mov     rax, [rcx]
0x1800122aa  mov     rax, [rax+10h]
0x1800122ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800122b3  nop
0x1800122b4  mov     rcx, [rbp+var_10]
0x1800122b8  test    rcx, rcx
  ... truncated ...
```
