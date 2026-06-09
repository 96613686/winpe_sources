# GetElementMetadataKeys(std::list<ushort const *,std::allocator<ushort const *>> *,ushort const *,ushort const *)

- ea: `0x180012444`
- end: `0x180012b8c`
- name: `?GetElementMetadataKeys@@YAJPEAV?$list@PEBGV?$allocator@PEBG@std@@@std@@PEBG1@Z`
- size: `1864`
- prototype: `__int64 __fastcall(unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180015530`

## callees

- `0x1800020a8`
- `0x1800020ec`
- `0x180002110`
- `0x180004a84`
- `0x180005424`
- `0x180006014`
- `0x1800118ac`
- `0x180012444`
- `0x1800130cc`
- `0x180013290`
- `0x180019010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800126de`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800126de`

## string_xrefs

- `0x18001248d`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x1800126f9`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x18001276e`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x1800127c7`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x18001283c`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x1800128b8`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x18001292d`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x1800129b1`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x180012a18`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x180012a94`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x180012b06`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x1800128d9`: `    Failed to move to first attribute`
- `0x180012ab5`: `    Failed to move to first attribute`
- `0x18001271a`: `    Failed to copy key string`

## pseudocode

```c
__int64 __fastcall GetElementMetadataKeys(unsigned __int16 *a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  int v5; // eax
  unsigned int v6; // edi
  struct IXmlReader *v7; // rcx
  struct IStream *v8; // rcx
  int Node; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  __int64 v16; // rax
  unsigned __int64 v17; // rbx
  unsigned __int64 v18; // rax
  unsigned __int64 v19; // kr00_8
  unsigned __int16 *v20; // rax
  unsigned __int16 *v21; // rsi
  const struct std::nothrow_t *v22; // rdx
  __int64 v23; // rbx
  _QWORD *v24; // rax
  _QWORD *v25; // rcx
  struct IXmlReader *v26; // rcx
  struct IStream *v27; // rcx
  struct IXmlReader *v29; // rcx
  struct IStream *v30; // rcx
  struct IXmlReader *v31; // rcx
  struct IStream *v32; // rcx
  struct IXmlReader *v33; // rcx
  struct IStream *v34; // rcx
  struct IXmlReader *v35; // rcx
  struct IStream *v36; // rcx
  struct IXmlReader *v37; // rcx
  struct IStream *v38; // rcx
  struct IXmlReader *v39; // rcx
  struct IStream *v40; // rcx
  struct IXmlReader *v41; // rcx
  struct IStream *v42; // rcx
  struct IXmlReader *v43; // rcx
  struct IStream *v44; // rcx
  struct IXmlReader *v45; // rcx
  struct IStream *v46; // rcx
  struct IXmlReader *v47; // rcx
  struct IStream *v48; // rcx
  int v49; // [rsp+20h] [rbp-40h]
  struct IStream *v50; // [rsp+30h] [rbp-30h] BYREF
  unsigned __int16 *v51; // [rsp+38h] [rbp-28h] BYREF
  unsigned __int16 *v52[2]; // [rsp+40h] [rbp-20h] BYREF
  __int64 v53; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  struct IXmlReader *ppvObject; // [rsp+A8h] [rbp+48h] BYREF

  v50 = 0;
  ppvObject = 0;
  v5 = SetupInput(&v50, &ppvObject, a3);
  v6 = v5;
  if ( v5 >= 0 )
  {
    do
    {
      Node = FindNode(ppvObject, 0, L"Element", 0);
      v6 = Node;
      if ( Node < 0 )
      {
        ProvPackageLog(
          3,
          L"%hs (%hs:%d) - 0x%08x:",
          "GetElementMetadataKeys",
          "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
          732,
          Node);
        ProvPackageLog(3, L"    Failed to find %s node", L"element");
        v47 = ppvObject;
        if ( ppvObject )
        {
          ppvObject = 0;
          ((void (__fastcall *)(struct IXmlReader *))v47->lpVtbl->Release)(v47);
        }
        v48 = v50;
        if ( v50 )
        {
          v50 = 0;
          ((void (__fastcall *)(struct IStream *))v48->lpVtbl->Release)(v48);
        }
        return v6;
      }
      v10 = ((__int64 (__fastcall *)(struct IXmlReader *))ppvObject->lpVtbl->MoveToFirstAttribute)(ppvObject);
      v6 = v10;
      if ( v10 < 0 )
      {
        ProvPackageLog(
          3,
          L"%hs (%hs:%d) - 0x%08x:",
          "GetElementMetadataKeys",
          "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
          735,
          v10);
        ProvPackageLog(3, L"    Failed to move to first attribute");
        v45 = ppvObject;
        if ( ppvObject )
        {
          ppvObject = 0;
          ((void (__fastcall *)(struct IXmlReader *))v45->lpVtbl->Release)(v45);
        }
        v46 = v50;
        if ( v50 )
        {
          v50 = 0;
          ((void (__fastcall *)(struct IStream *))v46->lpVtbl->Release)(v46);
        }
        return v6;
      }
      v11 = VerifyAttribute(ppvObject, L"Index", a2);
      v6 = v11;
      if ( v11 < 0 )
      {
        ProvPackageLog(
          3,
          L"%hs (%hs:%d) - 0x%08x:",
          "GetElementMetadataKeys",
          "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
          738,
          v11);
        ProvPackageLog(3, L"    Failed to verify %s attribute", L"index");
        v43 = ppvObject;
        if ( ppvObject )
        {
          ppvObject = 0;
          ((void (__fastcall *)(struct IXmlReader *))v43->lpVtbl->Release)(v43);
        }
        v44 = v50;
        if ( v50 )
        {
          v50 = 0;
          ((void (__fastcall *)(struct IStream *))v44->lpVtbl->Release)(v44);
        }
        return v6;
      }
    }
    while ( v11 );
    while ( 1 )
    {
      v12 = FindNode(ppvObject, 0, L"Metadata", L"Element");
      v6 = v12;
      if ( v12 == -2147023728 )
        break;
      if ( v12 < 0 )
      {
        ProvPackageLog(
          3,
          L"%hs (%hs:%d) - 0x%08x:",
          "GetElementMetadataKeys",
          "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
          750,
          v12);
        ProvPackageLog(3, L"    Failed to find %s node", L"metadata");
        v39 = ppvObject;
        if ( ppvObject )
        {
          ppvObject = 0;
          ((void (__fastcall *)(struct IXmlReader *))v39->lpVtbl->Release)(v39);
        }
        v40 = v50;
        if ( v50 )
        {
          v50 = 0;
          ((void (__fastcall *)(struct IStream *))v40->lpVtbl->Release)(v40);
        }
        return v6;
      }
      v13 = ((__int64 (__fastcall *)(struct IXmlReader *))ppvObject->lpVtbl->MoveToFirstAttribute)(ppvObject);
      v6 = v13;
      if ( v13 < 0 )
      {
        ProvPackageLog(
          3,
          L"%hs (%hs:%d) - 0x%08x:",
          "GetElementMetadataKeys",
          "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
          753,
          v13);
        ProvPackageLog(3, L"    Failed to move to first attribute");
        v37 = ppvObject;
        if ( ppvObject )
        {
          ppvObject = 0;
          ((void (__fastcall *)(struct IXmlReader *))v37->lpVtbl->Release)(v37);
        }
        v38 = v50;
        if ( v50 )
        {
          v50 = 0;
          ((void (__fastcall *)(struct IStream *))v38->lpVtbl->Release)(v38);
        }
        return v6;
      }
      v52[0] = 0;
      ((void (__fastcall *)(struct IXmlReader *, unsigned __int16 **, _QWORD))ppvObject->lpVtbl->GetLocalName)(
        ppvObject,
        v52,
        0);
      v14 = VerifyAttribute(ppvObject, L"Key", v52[0]);
      v6 = v14;
      if ( v14 < 0 )
      {
        ProvPackageLog(
          3,
          L"%hs (%hs:%d) - 0x%08x:",
          "GetElementMetadataKeys",
          "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
          761,
          v14);
        ProvPackageLog(3, L"    Failed to verify %s attribute", L"key");
        v35 = ppvObject;
        if ( ppvObject )
        {
          ppvObject = 0;
          ((void (__fastcall *)(struct IXmlReader *))v35->lpVtbl->Release)(v35);
        }
        v36 = v50;
        if ( v50 )
        {
          v50 = 0;
          ((void (__fastcall *)(struct IStream *))v36->lpVtbl->Release)(v36);
        }
        return v6;
      }
      v51 = 0;
      v15 = ((__int64 (__fastcall *)(struct IXmlReader *, unsigned __int16 **, _QWORD))ppvObject->lpVtbl->GetValue)(
              ppvObject,
              &v51,
              0);
      v6 = v15;
      if ( v15 < 0 )
      {
        ProvPackageLog(
          3,
          L"%hs (%hs:%d) - 0x%08x:",
          "GetElementMetadataKeys",
          "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
          766,
          v15);
        ProvPackageLog(3, L"    Failed to get key value");
        v33 = ppvObject;
        if ( ppvObject )
        {
          ppvObject = 0;
          ((void (__fastcall *)(struct IXmlReader *))v33->lpVtbl->Release)(v33);
        }
        v34 = v50;
        if ( v50 )
        {
          v50 = 0;
          ((void (__fastcall *)(struct IStream *))v34->lpVtbl->Release)(v34);
        }
        return v6;
      }
      v16 = -1;
      do
        ++v16;
      while ( v51[v16] );
      v17 = v16 + 1;
      v19 = v16 + 1;
      v18 = 2 * (v16 + 1);
      if ( !is_mul_ok(v19, 2u) )
        v18 = -1;
      v20 = (unsigned __int16 *)operator new[](v18, (const struct std::nothrow_t *)&std::nothrow);
      v21 = v20;
      if ( !v20 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x302,
          (unsigned int)"onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
          (const char *)0x8007000ELL,
          v49);
        v31 = ppvObject;
        if ( ppvObject )
        {
          ppvObject = 0;
          ((void (__fastcall *)(struct IXmlReader *))v31->lpVtbl->Release)(v31);
        }
        v32 = v50;
        if ( v50 )
        {
          v50 = 0;
          ((void (__fastcall *)(struct IStream *))v32->lpVtbl->Release)(v32);
        }
        return 2147942414LL;
      }
      v6 = StringCchCopyW(v20, v17, v51);
      if ( (v6 & 0x80000000) != 0 )
      {
        operator delete(v21, v22);
        ProvPackageLog(
          3,
          L"%hs (%hs:%d) - 0x%08x:",
          "GetElementMetadataKeys",
          "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
          775,
          v6);
        ProvPackageLog(3, L"    Failed to copy key string");
        v29 = ppvObject;
        if ( ppvObject )
        {
          ppvObject = 0;
          ((void (__fastcall *)(struct IXmlReader *))v29->lpVtbl->Release)(v29);
        }
        v30 = v50;
        if ( v50 )
        {
          v50 = 0;
          ((void (__fastcall *)(struct IStream *))v30->lpVtbl->Release)(v30);
        }
        return v6;
      }
      if ( *((_QWORD *)a1 + 1) == 0xAAAAAAAAAAAAAAALL )
        std::_Xlength_error("list too long");
      v23 = *(_QWORD *)a1;
      v52[1] = a1;
      v53 = 0;
      v24 = operator new(0x18u);
      v24[2] = v21;
      ++*((_QWORD *)a1 + 1);
      v25 = *(_QWORD **)(v23 + 8);
      *v24 = v23;
      v24[1] = v25;
      v53 = 0;
      *(_QWORD *)(v23 + 8) = v24;
      *v25 = v24;
      if ( v6 )
      {
        v26 = ppvObject;
        if ( ppvObject )
        {
          ppvObject = 0;
          ((void (__fastcall *)(struct IXmlReader *))v26->lpVtbl->Release)(v26);
        }
        v27 = v50;
        if ( v50 )
        {
          v50 = 0;
          ((void (__fastcall *)(struct IStream *))v27->lpVtbl->Release)(v27);
        }
        return 0;
      }
    }
    ProvPackageLog(
      0,
      L"%hs (%hs:%d): %s",
      "GetElementMetadataKeys",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
      747,
      L"Metadata not found");
    v41 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      ((void (__fastcall *)(struct IXmlReader *))v41->lpVtbl->Release)(v41);
    }
    v42 = v50;
    if ( v50 )
    {
      v50 = 0;
      ((void (__fastcall *)(struct IStream *))v42->lpVtbl->Release)(v42);
    }
    return 2147943568LL;
  }
  else
  {
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "GetElementMetadataKeys",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
      726,
      v5);
    ProvPackageLog(3, L"    Failed to setup input");
    v7 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      ((void (__fastcall *)(struct IXmlReader *))v7->lpVtbl->Release)(v7);
    }
    v8 = v50;
    if ( v50 )
    {
      v50 = 0;
      ((void (__fastcall *)(struct IStream *))v8->lpVtbl->Release)(v8);
    }
    return v6;
  }
}

```

## disassembly

```asm
0x180012444  mov     [rsp-28h+arg_0], rbx
0x180012449  mov     [rsp-28h+arg_8], rsi
0x18001244e  push    rbp
0x18001244f  push    rdi
0x180012450  push    r13
0x180012452  push    r14
0x180012454  push    r15
0x180012456  mov     rbp, rsp
0x180012459  sub     rsp, 60h
0x18001245d  mov     rbx, rdx
0x180012460  mov     r14, rcx
0x180012463  xor     r15d, r15d
0x180012466  mov     [rbp+var_30], r15
0x18001246a  mov     [rbp+ppvObject], r15
0x18001246e  lea     rdx, [rbp+ppvObject]; ppvObject
0x180012472  lea     rcx, [rbp+var_30]; struct IStream **
0x180012476  call    ?SetupInput@@YAJPEAPEAUIStream@@PEAPEAUIXmlReader@@PEBG@Z; SetupInput(IStream * *,IXmlReader * *,ushort const *)
0x18001247b  mov     edi, eax
0x18001247d  test    eax, eax
0x18001247f  jns     short loc_1800124F5
0x180012481  mov     dword ptr [rsp+60h+var_38], eax
0x180012485  mov     [rsp+60h+var_40], 2D6h
0x18001248d  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x180012494  lea     r8, aGetelementmeta_0; "GetElementMetadataKeys"
0x18001249b  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x1800124a2  lea     ebx, [r15+3]
0x1800124a6  mov     ecx, ebx
0x1800124a8  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800124ad  lea     rdx, aFailedToSetupI; "    Failed to setup input"
0x1800124b4  mov     ecx, ebx
0x1800124b6  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800124bb  nop
0x1800124bc  mov     rcx, [rbp+ppvObject]
0x1800124c0  test    rcx, rcx
0x1800124c3  jz      short loc_1800124D6
0x1800124c5  mov     [rbp+ppvObject], r15
0x1800124c9  mov     rax, [rcx]
0x1800124cc  mov     rax, [rax+10h]
0x1800124d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800124d5  nop
0x1800124d6  mov     rcx, [rbp+var_30]
0x1800124da  test    rcx, rcx
0x1800124dd  jz      short loc_1800124F0
0x1800124df  mov     [rbp+var_30], r15
0x1800124e3  mov     rax, [rcx]
0x1800124e6  mov     rax, [rax+10h]
0x1800124ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800124ef  nop
0x1800124f0  jmp     loc_180012B71
0x1800124f5  xor     r9d, r9d; unsigned __int16 *
0x1800124f8  lea     r8, aElement_0; "Element"
0x1800124ff  xor     edx, edx; struct IXmlWriter *
0x180012501  mov     rcx, [rbp+ppvObject]; struct IXmlReader *
0x180012505  call    ?FindNode@@YAJPEAUIXmlReader@@PEAUIXmlWriter@@PEBG2@Z; FindNode(IXmlReader *,IXmlWriter *,ushort const *,ushort const *)
0x18001250a  mov     edi, eax
0x18001250c  test    eax, eax
0x18001250e  js      loc_180012AFA
0x180012514  mov     rcx, [rbp+ppvObject]
0x180012518  mov     rax, [rcx]
0x18001251b  mov     rax, [rax+40h]
0x18001251f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012524  mov     edi, eax
0x180012526  test    eax, eax
0x180012528  js      loc_180012A88
0x18001252e  mov     r8, rbx; unsigned __int16 *
0x180012531  lea     rdx, aIndex_0; "Index"
0x180012538  mov     rcx, [rbp+ppvObject]; struct IXmlReader *
0x18001253c  call    ?VerifyAttribute@@YAJPEAUIXmlReader@@PEBG1@Z; VerifyAttribute(IXmlReader *,ushort const *,ushort const *)
0x180012541  mov     edi, eax
0x180012543  test    eax, eax
0x180012545  js      loc_180012A0C
0x18001254b  test    eax, eax
0x18001254d  jnz     short loc_1800124F5
0x18001254f  or      r13, 0FFFFFFFFFFFFFFFFh
0x180012553  lea     r9, aElement_0; "Element"
0x18001255a  lea     r8, aMetadata; "Metadata"
0x180012561  xor     edx, edx; struct IXmlWriter *
0x180012563  mov     rcx, [rbp+ppvObject]; struct IXmlReader *
0x180012567  call    ?FindNode@@YAJPEAUIXmlReader@@PEAUIXmlWriter@@PEBG2@Z; FindNode(IXmlReader *,IXmlWriter *,ushort const *,ushort const *)
0x18001256c  mov     edi, eax
0x18001256e  cmp     eax, 80070490h
0x180012573  jz      loc_18001299D
0x180012579  test    eax, eax
0x18001257b  js      loc_180012921
0x180012581  mov     rcx, [rbp+ppvObject]
0x180012585  mov     rax, [rcx]
0x180012588  mov     rax, [rax+40h]
0x18001258c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012591  mov     edi, eax
0x180012593  test    eax, eax
0x180012595  js      loc_1800128AC
0x18001259b  mov     [rbp+var_20], r15
0x18001259f  mov     rcx, [rbp+ppvObject]
0x1800125a3  mov     rax, [rcx]
0x1800125a6  xor     r8d, r8d
0x1800125a9  lea     rdx, [rbp+var_20]
0x1800125ad  mov     rax, [rax+70h]
0x1800125b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125b6  mov     r8, [rbp+var_20]; unsigned __int16 *
0x1800125ba  lea     rdx, aKey; "Key"
0x1800125c1  mov     rcx, [rbp+ppvObject]; struct IXmlReader *
0x1800125c5  call    ?VerifyAttribute@@YAJPEAUIXmlReader@@PEBG1@Z; VerifyAttribute(IXmlReader *,ushort const *,ushort const *)
0x1800125ca  mov     edi, eax
0x1800125cc  test    eax, eax
0x1800125ce  js      loc_180012830
0x1800125d4  mov     [rbp+var_28], r15
0x1800125d8  mov     rcx, [rbp+ppvObject]
0x1800125dc  mov     rax, [rcx]
0x1800125df  xor     r8d, r8d
0x1800125e2  lea     rdx, [rbp+var_28]
0x1800125e6  mov     rax, [rax+80h]
0x1800125ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125f2  mov     edi, eax
0x1800125f4  test    eax, eax
0x1800125f6  js      loc_1800127BB
0x1800125fc  mov     rcx, [rbp+var_28]
0x180012600  mov     rax, r13
0x180012603  inc     rax
0x180012606  cmp     [rcx+rax*2], r15w
0x18001260b  jnz     short loc_180012603
0x18001260d  lea     rbx, [rax+1]
0x180012611  mov     eax, 2
0x180012616  mul     rbx
0x180012619  cmovb   rax, r13
0x18001261d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180012624  mov     rcx, rax; unsigned __int64
0x180012627  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001262c  mov     rsi, rax
0x18001262f  test    rax, rax
0x180012632  jz      loc_180012762
0x180012638  mov     r8, [rbp+var_28]; unsigned __int16 *
0x18001263c  mov     rdx, rbx; unsigned __int64
0x18001263f  mov     rcx, rax; unsigned __int16 *
0x180012642  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180012647  mov     edi, eax
0x180012649  test    eax, eax
0x18001264b  js      loc_1800126E5
0x180012651  mov     rax, 0AAAAAAAAAAAAAAAh
0x18001265b  cmp     [r14+8], rax
0x18001265f  jz      short loc_1800126D7
0x180012661  mov     rbx, [r14]
0x180012664  mov     [rbp+var_18], r14
0x180012668  mov     [rbp+var_10], r15
0x18001266c  mov     ecx, 18h; Size
0x180012671  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012676  mov     [rax+10h], rsi
0x18001267a  inc     qword ptr [r14+8]
0x18001267e  mov     rcx, [rbx+8]
0x180012682  mov     [rax], rbx
0x180012685  mov     [rax+8], rcx
0x180012689  mov     [rbp+var_10], r15
0x18001268d  mov     [rbx+8], rax
0x180012691  mov     [rcx], rax
0x180012694  test    edi, edi
0x180012696  jz      loc_180012553
0x18001269c  mov     rcx, [rbp+ppvObject]
0x1800126a0  test    rcx, rcx
0x1800126a3  jz      short loc_1800126B6
0x1800126a5  mov     [rbp+ppvObject], r15
0x1800126a9  mov     rax, [rcx]
0x1800126ac  mov     rax, [rax+10h]
0x1800126b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800126b5  nop
0x1800126b6  mov     rcx, [rbp+var_30]
0x1800126ba  test    rcx, rcx
0x1800126bd  jz      short loc_1800126D0
0x1800126bf  mov     [rbp+var_30], r15
0x1800126c3  mov     rax, [rcx]
0x1800126c6  mov     rax, [rax+10h]
0x1800126ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800126cf  nop
0x1800126d0  xor     eax, eax
0x1800126d2  jmp     loc_180012B73
0x1800126d7  lea     rcx, aListTooLong; "list too long"
0x1800126de  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800126e5  mov     rcx, rsi; void *
0x1800126e8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800126ed  mov     dword ptr [rsp+60h+var_38], edi
0x1800126f1  mov     [rsp+60h+var_40], 307h
0x1800126f9  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x180012700  lea     r8, aGetelementmeta_0; "GetElementMetadataKeys"
0x180012707  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18001270e  mov     ebx, 3
0x180012713  mov     ecx, ebx
0x180012715  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18001271a  lea     rdx, aFailedToCopyKe; "    Failed to copy key string"
0x180012721  mov     ecx, ebx
0x180012723  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180012728  nop
0x180012729  mov     rcx, [rbp+ppvObject]
0x18001272d  test    rcx, rcx
0x180012730  jz      short loc_180012743
0x180012732  mov     [rbp+ppvObject], r15
0x180012736  mov     rax, [rcx]
0x180012739  mov     rax, [rax+10h]
0x18001273d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012742  nop
0x180012743  mov     rcx, [rbp+var_30]
0x180012747  test    rcx, rcx
0x18001274a  jz      short loc_18001275D
0x18001274c  mov     [rbp+var_30], r15
0x180012750  mov     rax, [rcx]
0x180012753  mov     rax, [rax+10h]
0x180012757  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001275c  nop
0x18001275d  jmp     loc_180012B71
0x180012762  mov     rcx, [rbp+28h]; this
0x180012766  mov     ebx, 8007000Eh
0x18001276b  mov     r9d, ebx; char *
0x18001276e  lea     r8, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x180012775  mov     edx, 302h; void *
0x18001277a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001277f  nop
0x180012780  mov     rcx, [rbp+ppvObject]
0x180012784  test    rcx, rcx
0x180012787  jz      short loc_18001279A
0x180012789  mov     [rbp+ppvObject], r15
0x18001278d  mov     rax, [rcx]
0x180012790  mov     rax, [rax+10h]
0x180012794  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012799  nop
0x18001279a  mov     rcx, [rbp+var_30]
0x18001279e  test    rcx, rcx
0x1800127a1  jz      short loc_1800127B4
0x1800127a3  mov     [rbp+var_30], r15
0x1800127a7  mov     rdx, [rcx]
0x1800127aa  mov     rax, [rdx+10h]
0x1800127ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127b3  nop
0x1800127b4  mov     eax, ebx
0x1800127b6  jmp     loc_180012B73
0x1800127bb  mov     dword ptr [rsp+60h+var_38], edi
0x1800127bf  mov     [rsp+60h+var_40], 2FEh
0x1800127c7  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x1800127ce  lea     r8, aGetelementmeta_0; "GetElementMetadataKeys"
0x1800127d5  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x1800127dc  mov     ebx, 3
0x1800127e1  mov     ecx, ebx
0x1800127e3  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800127e8  lea     rdx, aFailedToGetKey; "    Failed to get key value"
0x1800127ef  mov     ecx, ebx
0x1800127f1  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800127f6  nop
0x1800127f7  mov     rcx, [rbp+ppvObject]
0x1800127fb  test    rcx, rcx
0x1800127fe  jz      short loc_180012811
0x180012800  mov     [rbp+ppvObject], r15
0x180012804  mov     rax, [rcx]
0x180012807  mov     rax, [rax+10h]
0x18001280b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012810  nop
0x180012811  mov     rcx, [rbp+var_30]
0x180012815  test    rcx, rcx
0x180012818  jz      short loc_18001282B
0x18001281a  mov     [rbp+var_30], r15
0x18001281e  mov     rax, [rcx]
0x180012821  mov     rax, [rax+10h]
0x180012825  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001282a  nop
0x18001282b  jmp     loc_180012B71
0x180012830  mov     dword ptr [rsp+60h+var_38], edi
0x180012834  mov     [rsp+60h+var_40], 2F9h
0x18001283c  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x180012843  lea     r8, aGetelementmeta_0; "GetElementMetadataKeys"
0x18001284a  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180012851  mov     ebx, 3
0x180012856  mov     ecx, ebx
0x180012858  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18001285d  lea     r8, aKey_0; "key"
0x180012864  lea     rdx, aFailedToVerify_0; "    Failed to verify %s attribute"
0x18001286b  mov     ecx, ebx
0x18001286d  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180012872  nop
0x180012873  mov     rcx, [rbp+ppvObject]
0x180012877  test    rcx, rcx
0x18001287a  jz      short loc_18001288D
0x18001287c  mov     [rbp+ppvObject], r15
0x180012880  mov     rax, [rcx]
0x180012883  mov     rax, [rax+10h]
0x180012887  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001288c  nop
0x18001288d  mov     rcx, [rbp+var_30]
0x180012891  test    rcx, rcx
0x180012894  jz      short loc_1800128A7
0x180012896  mov     [rbp+var_30], r15
0x18001289a  mov     rax, [rcx]
0x18001289d  mov     rax, [rax+10h]
0x1800128a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800128a6  nop
0x1800128a7  jmp     loc_180012B71
0x1800128ac  mov     dword ptr [rsp+60h+var_38], edi
0x1800128b0  mov     [rsp+60h+var_40], 2F1h
0x1800128b8  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x1800128bf  lea     r8, aGetelementmeta_0; "GetElementMetadataKeys"
0x1800128c6  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x1800128cd  mov     ebx, 3
0x1800128d2  mov     ecx, ebx
0x1800128d4  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800128d9  lea     rdx, aFailedToMoveTo_0; "    Failed to move to first attribute"
0x1800128e0  mov     ecx, ebx
  ... truncated ...
```
