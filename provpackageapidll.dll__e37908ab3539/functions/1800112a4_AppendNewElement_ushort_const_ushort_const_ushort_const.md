# AppendNewElement(ushort const *,ushort const *,ushort const *)

- ea: `0x1800112a4`
- end: `0x180011766`
- name: `?AppendNewElement@@YAJPEBG00@Z`
- size: `1218`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x180014f8c`

## callees

- `0x180006014`
- `0x1800112a4`
- `0x1800118ac`
- `0x1800130cc`
- `0x1800131ac`
- `0x18001345c`
- `0x180019010`

## string_xrefs

- `0x1800112fb`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x1800113f3`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x1800114bd`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x18001157f`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x18001164c`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x18001166d`: `    Failed to write end node shallow`
- `0x1800115a0`: `    Failed to write index element block`

## pseudocode

```c
__int64 __fastcall AppendNewElement(const unsigned __int16 *a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  int v5; // eax
  unsigned int v6; // edi
  struct IXmlReader *v7; // rcx
  struct IStream *v8; // rcx
  struct IXmlWriter *v9; // rcx
  struct IStream *v10; // rcx
  struct IXmlReader *v12; // rcx
  struct IStream *v13; // rcx
  int v14; // eax
  struct IXmlReader *v15; // rcx
  struct IStream *v16; // rcx
  struct IXmlWriter *v17; // rcx
  struct IStream *v18; // rcx
  int Node; // eax
  struct IXmlReader *v20; // rcx
  struct IStream *v21; // rcx
  struct IXmlWriter *v22; // rcx
  struct IStream *v23; // rcx
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
  struct IXmlReader *v34; // rcx
  struct IStream *v35; // rcx
  struct IXmlWriter *v36; // rcx
  struct IStream *v37; // rcx
  int v38; // [rsp+20h] [rbp-30h]
  int v39; // [rsp+20h] [rbp-30h]
  int v40; // [rsp+20h] [rbp-30h]
  int v41; // [rsp+20h] [rbp-30h]
  int v42; // [rsp+20h] [rbp-30h]
  int v43; // [rsp+28h] [rbp-28h]
  int v44; // [rsp+28h] [rbp-28h]
  int v45; // [rsp+28h] [rbp-28h]
  int v46; // [rsp+28h] [rbp-28h]
  int v47; // [rsp+28h] [rbp-28h]
  struct IXmlWriter *v48; // [rsp+30h] [rbp-20h] BYREF
  struct IStream *v49; // [rsp+38h] [rbp-18h] BYREF
  struct IStream *v50; // [rsp+40h] [rbp-10h] BYREF
  struct IXmlReader *ppvObject; // [rsp+88h] [rbp+38h] BYREF

  v50 = 0;
  v48 = 0;
  v49 = 0;
  ppvObject = 0;
  v5 = SetupOutput(&v50, &v48, a2, 0);
  v6 = v5;
  if ( v5 < 0 )
  {
    v43 = v5;
    v38 = 388;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "AppendNewElement",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
      v38,
      v43);
    ProvPackageLog(3, L"    Failed to setup output");
    v7 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      ((void (__fastcall *)(struct IXmlReader *))v7->lpVtbl->Release)(v7);
    }
    v8 = v49;
    if ( v49 )
    {
      v49 = 0;
      ((void (__fastcall *)(struct IStream *))v8->lpVtbl->Release)(v8);
    }
    v9 = v48;
    if ( v48 )
    {
      v48 = 0;
      ((void (__fastcall *)(struct IXmlWriter *))v9->lpVtbl->Release)(v9);
    }
    v10 = v50;
    if ( v50 )
    {
      v50 = 0;
      ((void (__fastcall *)(struct IStream *))v10->lpVtbl->Release)(v10);
    }
    return v6;
  }
  v12 = ppvObject;
  if ( ppvObject )
  {
    ppvObject = 0;
    ((void (__fastcall *)(struct IXmlReader *))v12->lpVtbl->Release)(v12);
  }
  v13 = v49;
  if ( v49 )
  {
    v49 = 0;
    ((void (__fastcall *)(struct IStream *))v13->lpVtbl->Release)(v13);
  }
  v14 = SetupInput(&v49, &ppvObject, a1);
  v6 = v14;
  if ( v14 < 0 )
  {
    v44 = v14;
    v39 = 392;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "AppendNewElement",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
      v39,
      v44);
    ProvPackageLog(3, L"    Failed to setup input");
    v15 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      ((void (__fastcall *)(struct IXmlReader *))v15->lpVtbl->Release)(v15);
    }
    v16 = v49;
    if ( v49 )
    {
      v49 = 0;
      ((void (__fastcall *)(struct IStream *))v16->lpVtbl->Release)(v16);
    }
    v17 = v48;
    if ( v48 )
    {
      v48 = 0;
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
  Node = FindNode(ppvObject, v48, 0, L"Elements");
  v6 = Node;
  if ( Node < 0 )
  {
    v45 = Node;
    v40 = 396;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "AppendNewElement",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
      v40,
      v45);
    ProvPackageLog(3, L"    Failed to find elements stop node");
    v20 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      ((void (__fastcall *)(struct IXmlReader *))v20->lpVtbl->Release)(v20);
    }
    v21 = v49;
    if ( v49 )
    {
      v49 = 0;
      ((void (__fastcall *)(struct IStream *))v21->lpVtbl->Release)(v21);
    }
    v22 = v48;
    if ( v48 )
    {
      v48 = 0;
      ((void (__fastcall *)(struct IXmlWriter *))v22->lpVtbl->Release)(v22);
    }
    v23 = v50;
    if ( v50 )
    {
      v50 = 0;
      ((void (__fastcall *)(struct IStream *))v23->lpVtbl->Release)(v23);
    }
    return v6;
  }
  v24 = WriteElementBlock(v48, a3, 0);
  v6 = v24;
  if ( v24 < 0 )
  {
    v46 = v24;
    v41 = 400;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "AppendNewElement",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
      v41,
      v46);
    ProvPackageLog(3, L"    Failed to write index element block");
    v25 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      ((void (__fastcall *)(struct IXmlReader *))v25->lpVtbl->Release)(v25);
    }
    v26 = v49;
    if ( v49 )
    {
      v49 = 0;
      ((void (__fastcall *)(struct IStream *))v26->lpVtbl->Release)(v26);
    }
    v27 = v48;
    if ( v48 )
    {
      v48 = 0;
      ((void (__fastcall *)(struct IXmlWriter *))v27->lpVtbl->Release)(v27);
    }
    v28 = v50;
    if ( v50 )
    {
      v50 = 0;
      ((void (__fastcall *)(struct IStream *))v28->lpVtbl->Release)(v28);
    }
    return v6;
  }
  v29 = ((__int64 (__fastcall *)(struct IXmlWriter *, struct IXmlReader *, _QWORD))v48->lpVtbl->WriteNodeShallow)(
          v48,
          ppvObject,
          0);
  v6 = v29;
  if ( v29 < 0 )
  {
    v47 = v29;
    v42 = 404;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "AppendNewElement",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
      v42,
      v47);
    ProvPackageLog(3, L"    Failed to write end node shallow");
    v30 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      ((void (__fastcall *)(struct IXmlReader *))v30->lpVtbl->Release)(v30);
    }
    v31 = v49;
    if ( v49 )
    {
      v49 = 0;
      ((void (__fastcall *)(struct IStream *))v31->lpVtbl->Release)(v31);
    }
    v32 = v48;
    if ( v48 )
    {
      v48 = 0;
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
    ((void (__fastcall *)(struct IXmlReader *))v34->lpVtbl->Release)(v34);
  }
  v35 = v49;
  if ( v49 )
  {
    v49 = 0;
    ((void (__fastcall *)(struct IStream *))v35->lpVtbl->Release)(v35);
  }
  v36 = v48;
  if ( v48 )
  {
    v48 = 0;
    ((void (__fastcall *)(struct IXmlWriter *))v36->lpVtbl->Release)(v36);
  }
  v37 = v50;
  if ( v50 )
  {
    v50 = 0;
    ((void (__fastcall *)(struct IStream *))v37->lpVtbl->Release)(v37);
  }
  return 0;
}

```

## disassembly

```asm
0x1800112a4  mov     [rsp-18h+arg_0], rbx
0x1800112a9  mov     [rsp-18h+arg_8], rsi
0x1800112ae  push    rbp
0x1800112af  push    rdi
0x1800112b0  push    r14
0x1800112b2  mov     rbp, rsp
0x1800112b5  sub     rsp, 50h
0x1800112b9  mov     rsi, r8
0x1800112bc  mov     rbx, rcx
0x1800112bf  xor     r14d, r14d
0x1800112c2  mov     [rbp+var_10], r14
0x1800112c6  mov     [rbp+var_20], r14
0x1800112ca  mov     [rbp+var_18], r14
0x1800112ce  mov     [rbp+ppvObject], r14
0x1800112d2  xor     r9d, r9d; int
0x1800112d5  mov     r8, rdx; unsigned __int16 *
0x1800112d8  lea     rdx, [rbp+var_20]; ppvObject
0x1800112dc  lea     rcx, [rbp+var_10]; struct IStream **
0x1800112e0  call    ?SetupOutput@@YAJPEAPEAUIStream@@PEAPEAUIXmlWriter@@PEBGH@Z; SetupOutput(IStream * *,IXmlWriter * *,ushort const *,int)
0x1800112e5  mov     edi, eax
0x1800112e7  test    eax, eax
0x1800112e9  jns     loc_180011399
0x1800112ef  mov     [rsp+50h+var_28], eax
0x1800112f3  mov     [rsp+50h+var_30], 184h
0x1800112fb  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x180011302  lea     r8, aAppendneweleme; "AppendNewElement"
0x180011309  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180011310  lea     ebx, [r14+3]
0x180011314  mov     ecx, ebx
0x180011316  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18001131b  lea     rdx, aFailedToSetupO; "    Failed to setup output"
0x180011322  mov     ecx, ebx
0x180011324  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180011329  nop
0x18001132a  mov     rcx, [rbp+ppvObject]
0x18001132e  test    rcx, rcx
0x180011331  jz      short loc_180011344
0x180011333  mov     [rbp+ppvObject], r14
0x180011337  mov     rax, [rcx]
0x18001133a  mov     rax, [rax+10h]
0x18001133e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011343  nop
0x180011344  mov     rcx, [rbp+var_18]
0x180011348  test    rcx, rcx
0x18001134b  jz      short loc_18001135E
0x18001134d  mov     [rbp+var_18], r14
0x180011351  mov     rax, [rcx]
0x180011354  mov     rax, [rax+10h]
0x180011358  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001135d  nop
0x18001135e  mov     rcx, [rbp+var_20]
0x180011362  test    rcx, rcx
0x180011365  jz      short loc_180011378
0x180011367  mov     [rbp+var_20], r14
0x18001136b  mov     rax, [rcx]
0x18001136e  mov     rax, [rax+10h]
0x180011372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011377  nop
0x180011378  mov     rcx, [rbp+var_10]
0x18001137c  test    rcx, rcx
0x18001137f  jz      short loc_180011392
0x180011381  mov     [rbp+var_10], r14
0x180011385  mov     rax, [rcx]
0x180011388  mov     rax, [rax+10h]
0x18001138c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011391  nop
0x180011392  mov     eax, edi
0x180011394  jmp     loc_180011753
0x180011399  mov     rcx, [rbp+ppvObject]
0x18001139d  test    rcx, rcx
0x1800113a0  jz      short loc_1800113B3
0x1800113a2  mov     [rbp+ppvObject], r14
0x1800113a6  mov     rax, [rcx]
0x1800113a9  mov     rax, [rax+10h]
0x1800113ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113b2  nop
0x1800113b3  mov     rcx, [rbp+var_18]
0x1800113b7  test    rcx, rcx
0x1800113ba  jz      short loc_1800113CD
0x1800113bc  mov     [rbp+var_18], r14
0x1800113c0  mov     rax, [rcx]
0x1800113c3  mov     rax, [rax+10h]
0x1800113c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113cc  nop
0x1800113cd  mov     r8, rbx; unsigned __int16 *
0x1800113d0  lea     rdx, [rbp+ppvObject]; ppvObject
0x1800113d4  lea     rcx, [rbp+var_18]; struct IStream **
0x1800113d8  call    ?SetupInput@@YAJPEAPEAUIStream@@PEAPEAUIXmlReader@@PEBG@Z; SetupInput(IStream * *,IXmlReader * *,ushort const *)
0x1800113dd  mov     edi, eax
0x1800113df  test    eax, eax
0x1800113e1  jns     loc_180011490
0x1800113e7  mov     [rsp+50h+var_28], eax
0x1800113eb  mov     [rsp+50h+var_30], 188h
0x1800113f3  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x1800113fa  lea     r8, aAppendneweleme; "AppendNewElement"
0x180011401  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180011408  mov     ebx, 3
0x18001140d  mov     ecx, ebx
0x18001140f  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180011414  lea     rdx, aFailedToSetupI; "    Failed to setup input"
0x18001141b  mov     ecx, ebx
0x18001141d  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180011422  nop
0x180011423  mov     rcx, [rbp+ppvObject]
0x180011427  test    rcx, rcx
0x18001142a  jz      short loc_18001143D
0x18001142c  mov     [rbp+ppvObject], r14
0x180011430  mov     rax, [rcx]
0x180011433  mov     rax, [rax+10h]
0x180011437  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001143c  nop
0x18001143d  mov     rcx, [rbp+var_18]
0x180011441  test    rcx, rcx
0x180011444  jz      short loc_180011457
0x180011446  mov     [rbp+var_18], r14
0x18001144a  mov     rax, [rcx]
0x18001144d  mov     rax, [rax+10h]
0x180011451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011456  nop
0x180011457  mov     rcx, [rbp+var_20]
0x18001145b  test    rcx, rcx
0x18001145e  jz      short loc_180011471
0x180011460  mov     [rbp+var_20], r14
0x180011464  mov     rax, [rcx]
0x180011467  mov     rax, [rax+10h]
0x18001146b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011470  nop
0x180011471  mov     rcx, [rbp+var_10]
0x180011475  test    rcx, rcx
0x180011478  jz      short loc_18001148B
0x18001147a  mov     [rbp+var_10], r14
0x18001147e  mov     rax, [rcx]
0x180011481  mov     rax, [rax+10h]
0x180011485  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001148a  nop
0x18001148b  jmp     loc_180011392
0x180011490  lea     r9, aElements; "Elements"
0x180011497  xor     r8d, r8d; unsigned __int16 *
0x18001149a  mov     rdx, [rbp+var_20]; struct IXmlWriter *
0x18001149e  mov     rcx, [rbp+ppvObject]; struct IXmlReader *
0x1800114a2  call    ?FindNode@@YAJPEAUIXmlReader@@PEAUIXmlWriter@@PEBG2@Z; FindNode(IXmlReader *,IXmlWriter *,ushort const *,ushort const *)
0x1800114a7  mov     edi, eax
0x1800114a9  test    eax, eax
0x1800114ab  jns     loc_18001155A
0x1800114b1  mov     [rsp+50h+var_28], eax
0x1800114b5  mov     [rsp+50h+var_30], 18Ch
0x1800114bd  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x1800114c4  lea     r8, aAppendneweleme; "AppendNewElement"
0x1800114cb  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x1800114d2  mov     ebx, 3
0x1800114d7  mov     ecx, ebx
0x1800114d9  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800114de  lea     rdx, aFailedToFindEl_1; "    Failed to find elements stop node"
0x1800114e5  mov     ecx, ebx
0x1800114e7  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800114ec  nop
0x1800114ed  mov     rcx, [rbp+ppvObject]
0x1800114f1  test    rcx, rcx
0x1800114f4  jz      short loc_180011507
0x1800114f6  mov     [rbp+ppvObject], r14
0x1800114fa  mov     rax, [rcx]
0x1800114fd  mov     rax, [rax+10h]
0x180011501  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011506  nop
0x180011507  mov     rcx, [rbp+var_18]
0x18001150b  test    rcx, rcx
0x18001150e  jz      short loc_180011521
0x180011510  mov     [rbp+var_18], r14
0x180011514  mov     rax, [rcx]
0x180011517  mov     rax, [rax+10h]
0x18001151b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011520  nop
0x180011521  mov     rcx, [rbp+var_20]
0x180011525  test    rcx, rcx
0x180011528  jz      short loc_18001153B
0x18001152a  mov     [rbp+var_20], r14
0x18001152e  mov     rax, [rcx]
0x180011531  mov     rax, [rax+10h]
0x180011535  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001153a  nop
0x18001153b  mov     rcx, [rbp+var_10]
0x18001153f  test    rcx, rcx
0x180011542  jz      short loc_180011555
0x180011544  mov     [rbp+var_10], r14
0x180011548  mov     rax, [rcx]
0x18001154b  mov     rax, [rax+10h]
0x18001154f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011554  nop
0x180011555  jmp     loc_180011392
0x18001155a  xor     r8d, r8d; int
0x18001155d  mov     rdx, rsi; unsigned __int16 *
0x180011560  mov     rcx, [rbp+var_20]; struct IXmlWriter *
0x180011564  call    ?WriteElementBlock@@YAJPEAUIXmlWriter@@PEBGH@Z; WriteElementBlock(IXmlWriter *,ushort const *,int)
0x180011569  mov     edi, eax
0x18001156b  test    eax, eax
0x18001156d  jns     loc_18001161C
0x180011573  mov     [rsp+50h+var_28], eax
0x180011577  mov     [rsp+50h+var_30], 190h
0x18001157f  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x180011586  lea     r8, aAppendneweleme; "AppendNewElement"
0x18001158d  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180011594  mov     ebx, 3
0x180011599  mov     ecx, ebx
0x18001159b  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800115a0  lea     rdx, aFailedToWriteI_0; "    Failed to write index element block"
0x1800115a7  mov     ecx, ebx
0x1800115a9  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800115ae  nop
0x1800115af  mov     rcx, [rbp+ppvObject]
0x1800115b3  test    rcx, rcx
0x1800115b6  jz      short loc_1800115C9
0x1800115b8  mov     [rbp+ppvObject], r14
0x1800115bc  mov     rax, [rcx]
0x1800115bf  mov     rax, [rax+10h]
0x1800115c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800115c8  nop
0x1800115c9  mov     rcx, [rbp+var_18]
0x1800115cd  test    rcx, rcx
0x1800115d0  jz      short loc_1800115E3
0x1800115d2  mov     [rbp+var_18], r14
0x1800115d6  mov     rax, [rcx]
0x1800115d9  mov     rax, [rax+10h]
0x1800115dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800115e2  nop
0x1800115e3  mov     rcx, [rbp+var_20]
0x1800115e7  test    rcx, rcx
0x1800115ea  jz      short loc_1800115FD
0x1800115ec  mov     [rbp+var_20], r14
0x1800115f0  mov     rax, [rcx]
0x1800115f3  mov     rax, [rax+10h]
0x1800115f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800115fc  nop
0x1800115fd  mov     rcx, [rbp+var_10]
0x180011601  test    rcx, rcx
0x180011604  jz      short loc_180011617
0x180011606  mov     [rbp+var_10], r14
0x18001160a  mov     rax, [rcx]
0x18001160d  mov     rax, [rax+10h]
0x180011611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011616  nop
0x180011617  jmp     loc_180011392
0x18001161c  mov     rcx, [rbp+var_20]
0x180011620  mov     rax, [rcx]
0x180011623  xor     r8d, r8d
0x180011626  mov     rdx, [rbp+ppvObject]
0x18001162a  mov     rax, [rax+0A8h]
0x180011631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011636  mov     edi, eax
0x180011638  test    eax, eax
0x18001163a  jns     loc_1800116E9
0x180011640  mov     [rsp+50h+var_28], eax
0x180011644  mov     [rsp+50h+var_30], 194h
0x18001164c  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x180011653  lea     r8, aAppendneweleme; "AppendNewElement"
0x18001165a  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180011661  mov     ebx, 3
0x180011666  mov     ecx, ebx
0x180011668  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18001166d  lea     rdx, aFailedToWriteE; "    Failed to write end node shallow"
0x180011674  mov     ecx, ebx
0x180011676  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18001167b  nop
0x18001167c  mov     rcx, [rbp+ppvObject]
0x180011680  test    rcx, rcx
0x180011683  jz      short loc_180011696
0x180011685  mov     [rbp+ppvObject], r14
0x180011689  mov     rax, [rcx]
0x18001168c  mov     rax, [rax+10h]
0x180011690  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011695  nop
0x180011696  mov     rcx, [rbp+var_18]
0x18001169a  test    rcx, rcx
0x18001169d  jz      short loc_1800116B0
0x18001169f  mov     [rbp+var_18], r14
0x1800116a3  mov     rax, [rcx]
0x1800116a6  mov     rax, [rax+10h]
0x1800116aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800116af  nop
0x1800116b0  mov     rcx, [rbp+var_20]
0x1800116b4  test    rcx, rcx
0x1800116b7  jz      short loc_1800116CA
0x1800116b9  mov     [rbp+var_20], r14
0x1800116bd  mov     rax, [rcx]
0x1800116c0  mov     rax, [rax+10h]
0x1800116c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800116c9  nop
0x1800116ca  mov     rcx, [rbp+var_10]
0x1800116ce  test    rcx, rcx
0x1800116d1  jz      short loc_1800116E4
0x1800116d3  mov     [rbp+var_10], r14
0x1800116d7  mov     rax, [rcx]
0x1800116da  mov     rax, [rax+10h]
0x1800116de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800116e3  nop
0x1800116e4  jmp     loc_180011392
0x1800116e9  mov     rcx, [rbp+ppvObject]
0x1800116ed  test    rcx, rcx
0x1800116f0  jz      short loc_180011703
0x1800116f2  mov     [rbp+ppvObject], r14
0x1800116f6  mov     rax, [rcx]
  ... truncated ...
```
