# CPropertyParser::ParsePropertyXml(_GUID const &,IStream *,CDIProperties<ID2D1Properties> * *,EffectType::Enum *)

- ea: `0x1800aee68`
- end: `0x1800af490`
- name: `?ParsePropertyXml@CPropertyParser@@QEAAJAEBU_GUID@@PEAUIStream@@PEAPEAV?$CDIProperties@UID2D1Properties@@@@PEAW4Enum@EffectType@@@Z`
- size: `1576`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800b067c`

## callees

- `0x18001fd58`
- `0x1800389c0`
- `0x1800adc28`
- `0x1800ae788`
- `0x1800ae97c`
- `0x1800aebb0`
- `0x1800aee68`
- `0x1800af498`
- `0x1800af5a0`
- `0x1800af5e4`
- `0x1800af700`
- `0x180100670`
- `0x1802d3274`
- `0x180307010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800af324`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800af35d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800af38c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800af324`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800af35d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800af38c`
- `XmlLite!CreateXmlReader` at `0x1800aeeb2`
- `XmlLite!CreateXmlReader` at `0x1800aeeb2`

## string_xrefs

- `0x1800aef49`: `Property XML must begin with an XML declaration of the form <xml...>`
- `0x1800aef7b`: `Property XML must contain an <Effect> declaration as its only top-level element.`
- `0x1800af3b8`: `Property XML's <Effect> tag is empty. The <Effect> tag must include mandatory system property definitions.`
- `0x1800af3ff`: `Property XML must terminate after the </Effect> element.`

## pseudocode

```c
__int64 __fastcall CPropertyParser::ParsePropertyXml(
        __int64 a1,
        const struct _GUID *a2,
        __int64 a3,
        _QWORD *a4,
        enum EffectType::Enum *a5)
{
  CPropertyParser *v5; // rbx
  HRESULT v8; // edi
  void *v9; // rcx
  int v10; // eax
  int v11; // eax
  HRESULT v12; // esi
  unsigned int v13; // eax
  int v14; // eax
  unsigned int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // edx
  int v21; // r9d
  int v22; // eax
  __int64 v23; // rcx
  void (*v24)(void); // rax
  char *v26; // rcx
  __int64 v27; // rcx
  char *v28; // rcx
  __int64 v29; // rcx
  unsigned int k; // edi
  unsigned int m; // edi
  unsigned int n; // edi
  unsigned int jj; // edi
  unsigned int kk; // esi
  unsigned int nn; // esi
  unsigned int i; // esi
  unsigned int j; // edi
  __int64 v38; // rcx
  char *v39; // rcx
  unsigned int ii; // edi
  unsigned int mm; // edi
  int v42; // [rsp+28h] [rbp-E0h]
  void *Block; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v44; // [rsp+60h] [rbp-A8h]
  const wchar_t *v45; // [rsp+78h] [rbp-90h]
  int v46; // [rsp+80h] [rbp-88h]
  __int64 (__fastcall *v47)(); // [rsp+88h] [rbp-80h]
  char v48; // [rsp+90h] [rbp-78h]
  const unsigned __int16 *v49; // [rsp+98h] [rbp-70h]
  int v50; // [rsp+A0h] [rbp-68h]
  __int64 (__fastcall *v51)(); // [rsp+A8h] [rbp-60h]
  char v52; // [rsp+B0h] [rbp-58h]
  const wchar_t *v53; // [rsp+B8h] [rbp-50h]
  int v54; // [rsp+C0h] [rbp-48h]
  __int64 (__fastcall *v55)(); // [rsp+C8h] [rbp-40h]
  char v56; // [rsp+D0h] [rbp-38h]
  const wchar_t *v57; // [rsp+D8h] [rbp-30h]
  int v58; // [rsp+E0h] [rbp-28h]
  __int64 (__fastcall *v59)(); // [rsp+E8h] [rbp-20h]
  char v60; // [rsp+F0h] [rbp-18h]
  const wchar_t *v61; // [rsp+F8h] [rbp-10h]
  int v62; // [rsp+100h] [rbp-8h]
  __int64 (__fastcall *v63)(); // [rsp+108h] [rbp+0h]
  char v64; // [rsp+110h] [rbp+8h]
  const unsigned __int16 *v65; // [rsp+118h] [rbp+10h]
  int v66; // [rsp+120h] [rbp+18h]
  __int64 (__fastcall *v67)(); // [rsp+128h] [rbp+20h]
  char v68; // [rsp+130h] [rbp+28h]
  void *ppvObject; // [rsp+168h] [rbp+60h] BYREF

  v5 = CEffectRegistry::s_pPropertyParser;
  *a4 = 0;
  ppvObject = 0;
  v8 = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
  if ( v8 < 0
    || (v8 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppvObject + 24LL))(ppvObject, a3), v8 < 0) )
  {
    DoStackCapture(v8);
    if ( !ppvObject )
      return (unsigned int)v8;
    v24 = *(void (**)(void))(*(_QWORD *)ppvObject + 16LL);
    goto LABEL_19;
  }
  v9 = ppvObject;
  *((_QWORD *)v5 + 7) = ppvObject;
  if ( v9 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v9 + 8LL))(v9);
  Block = 0;
  v44 = 0;
  v10 = CArray<ATL::CComPtr<CDIProperties<ID2D1Properties>>,CPropertyNodePtrTraits,CDefaultAllocator>::Resize(
          &Block,
          10);
  v8 = v10;
  if ( v10 < 0 )
  {
    DoStackCapture(v10);
    v26 = (char *)Block;
    if ( !Block )
      goto LABEL_24;
    for ( i = 0; i < (unsigned int)v44; ++i )
    {
      ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(&v26[8 * i]);
      v26 = (char *)Block;
    }
    goto LABEL_56;
  }
  v11 = CPropertyParser::AddAutoProperties(v5, a2, (struct CPropertyNodeArray *)&Block);
  v12 = v11;
  if ( v11 < 0 )
  {
    DoStackCapture(v11);
    v28 = (char *)Block;
    if ( Block )
    {
      for ( j = 0; j < (unsigned int)v44; ++j )
      {
        ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(&v28[8 * j]);
        v28 = (char *)Block;
      }
      goto LABEL_60;
    }
    goto LABEL_27;
  }
  v13 = CPropertyParser::AdvanceDirectlyToNode(v5, 0, XmlNodeType_XmlDeclaration);
  v14 = HrFailTrace(v13, 512, "Property XML must begin with an XML declaration of the form <xml...>");
  v12 = v14;
  if ( v14 < 0 )
  {
    DoStackCapture(v14);
    v28 = (char *)Block;
    if ( Block )
    {
      for ( k = 0; k < (unsigned int)v44; ++k )
      {
        ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(&v28[8 * k]);
        v28 = (char *)Block;
      }
      goto LABEL_60;
    }
    goto LABEL_27;
  }
  v15 = CPropertyParser::AdvanceDirectlyToNode(v5, L"Effect", XmlNodeType_Element);
  v16 = HrFailTrace(v15, 512, "Property XML must contain an <Effect> declaration as its only top-level element.");
  v12 = v16;
  if ( v16 < 0 )
  {
    DoStackCapture(v16);
    v28 = (char *)Block;
    if ( Block )
    {
      for ( m = 0; m < (unsigned int)v44; ++m )
      {
        ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(&v28[8 * m]);
        v28 = (char *)Block;
      }
      goto LABEL_60;
    }
    goto LABEL_27;
  }
  v17 = CPropertyParser::ParseEffectType(v5, a5);
  v12 = v17;
  if ( v17 < 0 )
  {
    DoStackCapture(v17);
    v28 = (char *)Block;
    if ( Block )
    {
      for ( n = 0; n < (unsigned int)v44; ++n )
      {
        ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(&v28[8 * n]);
        v28 = (char *)Block;
      }
      goto LABEL_60;
    }
LABEL_27:
    v29 = *((_QWORD *)v5 + 7);
    LODWORD(v44) = 0;
    if ( v29 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
      *((_QWORD *)v5 + 7) = 0;
    }
    v8 = v12;
    goto LABEL_30;
  }
  if ( (*(unsigned int (__fastcall **)(void *))(*(_QWORD *)ppvObject + 160LL))(ppvObject) )
  {
    DImageTraceMessage(
      512,
      "Property XML's <Effect> tag is empty. The <Effect> tag must include mandatory system property definitions.");
    DoStackCapture(-2147024809);
    v39 = (char *)Block;
    if ( !Block )
      goto LABEL_64;
    for ( ii = 0; ii < (unsigned int)v44; ++ii )
    {
      ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(&v39[8 * ii]);
      v39 = (char *)Block;
    }
LABEL_63:
    free(v39);
    Block = 0;
    HIDWORD(v44) = 0;
LABEL_64:
    v38 = *((_QWORD *)v5 + 7);
    LODWORD(v44) = 0;
    if ( v38 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
      *((_QWORD *)v5 + 7) = 0;
    }
    v8 = -2147024809;
    goto LABEL_30;
  }
  v46 = 0x7FFFFFFF;
  v51 = CPropertyParser::ExecuteCallback<&private: long CPropertyParser::ParsePropertyByType<1,1>(CPropertyNodeArray *,unsigned int)>;
  v45 = L"_locDefinition";
  v55 = CPropertyParser::ExecuteCallback<&private: long CPropertyParser::ParsePropertyByType<1,1>(CPropertyNodeArray *,unsigned int)>;
  v47 = CPropertyParser::ExecuteCallback<&private: long CPropertyParser::DiscardLocalization(CPropertyNodeArray *,unsigned int)>;
  v59 = CPropertyParser::ExecuteCallback<&private: long CPropertyParser::ParsePropertyByType<1,1>(CPropertyNodeArray *,unsigned int)>;
  v49 = L"DisplayName";
  v63 = CPropertyParser::ExecuteCallback<&private: long CPropertyParser::ParsePropertyByType<1,1>(CPropertyNodeArray *,unsigned int)>;
  v53 = L"Author";
  v48 = 0;
  v57 = L"Category";
  v61 = L"Description";
  v65 = L"Inputs";
  v67 = CPropertyParser::ExecuteCallback<&private: long CPropertyParser::ParseInputs(CPropertyNodeArray *,unsigned int)>;
  v50 = 1;
  v52 = 1;
  v54 = 2;
  v56 = 1;
  v58 = 3;
  v60 = 1;
  v62 = 4;
  v64 = 1;
  v66 = 5;
  v68 = 1;
  v18 = CPropertyParser::ParseProperties(v5, (__int64)CPropertyParser::ParseProperty);
  v12 = v18;
  if ( v18 < 0 )
  {
    DoStackCapture(v18);
    v28 = (char *)Block;
    if ( Block )
    {
      for ( jj = 0; jj < (unsigned int)v44; ++jj )
      {
        ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(&v28[8 * jj]);
        v28 = (char *)Block;
      }
LABEL_60:
      free(v28);
      Block = 0;
      HIDWORD(v44) = 0;
      goto LABEL_27;
    }
    goto LABEL_27;
  }
  v19 = CPropertyParser::AdvanceDirectlyToAnyNode(v5);
  v8 = v19;
  if ( v19 < 0 )
  {
    DoStackCapture(v19);
    v26 = (char *)Block;
    if ( !Block )
      goto LABEL_24;
    for ( kk = 0; kk < (unsigned int)v44; ++kk )
    {
      ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(&v26[8 * kk]);
      v26 = (char *)Block;
    }
    goto LABEL_56;
  }
  if ( v19 != 1 )
  {
    DImageTraceMessage(512, "Property XML must terminate after the </Effect> element.");
    DoStackCapture(-2147024809);
    v39 = (char *)Block;
    if ( !Block )
      goto LABEL_64;
    for ( mm = 0; mm < (unsigned int)v44; ++mm )
    {
      ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(&v39[8 * mm]);
      v39 = (char *)Block;
    }
    goto LABEL_63;
  }
  v22 = CreateComObjectInit<LockingRequired,CDIProperties<ID2D1Properties>,AbstractLock *,RefCountedObject<CPropertyDescription,LockingRequired,DeleteOnZeroReference> *,CPropertyNodeArray *,unsigned int,bool,IUnknown *,IUnknown *,bool>(
          *((_QWORD *)v5 + 3),
          v20,
          (unsigned int)&Block,
          v21,
          v42);
  v8 = v22;
  if ( v22 < 0 )
  {
    DoStackCapture(v22);
    v26 = (char *)Block;
    if ( !Block )
      goto LABEL_24;
    for ( nn = 0; nn < (unsigned int)v44; ++nn )
    {
      ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(&v26[8 * nn]);
      v26 = (char *)Block;
    }
LABEL_56:
    free(v26);
    Block = 0;
    HIDWORD(v44) = 0;
LABEL_24:
    v27 = *((_QWORD *)v5 + 7);
    LODWORD(v44) = 0;
    if ( v27 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
      *((_QWORD *)v5 + 7) = 0;
    }
LABEL_30:
    ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(&ppvObject);
    return (unsigned int)v8;
  }
  CArray<ATL::CComPtr<CMultistepScaler>,CDefaultTraits<ATL::CComPtr<CMultistepScaler>>,CDefaultAllocator>::RemoveAll(&Block);
  v23 = *((_QWORD *)v5 + 7);
  if ( v23 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    *((_QWORD *)v5 + 7) = 0;
  }
  if ( ppvObject )
  {
    v24 = *(void (**)(void))(*(_QWORD *)ppvObject + 16LL);
LABEL_19:
    v24();
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800aee68  mov     rax, rsp
0x1800aee6b  mov     [rax+10h], rbx
0x1800aee6f  mov     [rax+18h], rsi
0x1800aee73  mov     [rax+8], rcx
0x1800aee77  push    rbp
0x1800aee78  push    rdi
0x1800aee79  push    r12
0x1800aee7b  push    r14
0x1800aee7d  push    r15
0x1800aee7f  lea     rbp, [rax-58h]
0x1800aee83  sub     rsp, 130h
0x1800aee8a  mov     rbx, cs:?s_pPropertyParser@CEffectRegistry@@0PEAVCPropertyParser@@EA; CPropertyParser * CEffectRegistry::s_pPropertyParser
0x1800aee91  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x1800aee98  mov     rsi, r8
0x1800aee9b  mov     r15, rdx
0x1800aee9e  xor     r12d, r12d
0x1800aeea1  lea     rdx, [rbp+50h+ppvObject]; ppvObject
0x1800aeea5  xor     r8d, r8d; pMalloc
0x1800aeea8  mov     [r9], r12
0x1800aeeab  mov     [rbp+50h+ppvObject], r12
0x1800aeeaf  mov     r14, r9
0x1800aeeb2  call    cs:__imp_CreateXmlReader
0x1800aeeb8  mov     edi, eax
0x1800aeeba  test    eax, eax
0x1800aeebc  js      loc_1800AF12B
0x1800aeec2  mov     rcx, [rbp+50h+ppvObject]
0x1800aeec6  mov     rdx, rsi
0x1800aeec9  mov     rax, [rcx]
0x1800aeecc  mov     rax, [rax+18h]
0x1800aeed0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aeed5  mov     edi, eax
0x1800aeed7  test    eax, eax
0x1800aeed9  js      loc_1800AF12B
0x1800aeedf  mov     rcx, [rbp+50h+ppvObject]
0x1800aeee3  mov     [rbx+38h], rcx
0x1800aeee7  test    rcx, rcx
0x1800aeeea  jz      short loc_1800AEEF8
0x1800aeeec  mov     rax, [rcx]
0x1800aeeef  mov     rax, [rax+8]
0x1800aeef3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aeef8  mov     edx, 0Ah
0x1800aeefd  mov     [rsp+150h+Block], r12
0x1800aef02  lea     rcx, [rsp+150h+Block]
0x1800aef07  mov     [rsp+150h+var_F8], r12
0x1800aef0c  call    ?Resize@?$CArray@V?$CComPtr@V?$CDIProperties@UID2D1Properties@@@@@ATL@@VCPropertyNodePtrTraits@@VCDefaultAllocator@@@@QEAAJI@Z; CArray<ATL::CComPtr<CDIProperties<ID2D1Properties>>,CPropertyNodePtrTraits,CDefaultAllocator>::Resize(uint)
0x1800aef11  mov     edi, eax
0x1800aef13  test    eax, eax
0x1800aef15  js      loc_1800AF144
0x1800aef1b  lea     r8, [rsp+150h+Block]; struct CPropertyNodeArray *
0x1800aef20  mov     rdx, r15; struct _GUID *
0x1800aef23  mov     rcx, rbx; this
0x1800aef26  call    ?AddAutoProperties@CPropertyParser@@AEAAJAEBU_GUID@@PEAVCPropertyNodeArray@@@Z; CPropertyParser::AddAutoProperties(_GUID const &,CPropertyNodeArray *)
0x1800aef2b  mov     esi, eax
0x1800aef2d  test    eax, eax
0x1800aef2f  js      loc_1800AF179
0x1800aef35  xor     edx, edx; unsigned __int16 *
0x1800aef37  mov     rcx, rbx; this
0x1800aef3a  lea     r8d, [rdx+11h]; enum XmlNodeType
0x1800aef3e  call    ?AdvanceDirectlyToNode@CPropertyParser@@AEAAJPEBGW4XmlNodeType@@@Z; CPropertyParser::AdvanceDirectlyToNode(ushort const *,XmlNodeType)
0x1800aef43  mov     r15d, 200h
0x1800aef49  lea     r8, aPropertyXmlMus_1; "Property XML must begin with an XML dec"...
0x1800aef50  mov     edx, r15d
0x1800aef53  mov     ecx, eax
0x1800aef55  call    ?HrFailTrace@@YAJJW4VRL_D2D1@@PEBDZZ; HrFailTrace(long,VRL_D2D1,char const *,...)
0x1800aef5a  mov     esi, eax
0x1800aef5c  test    eax, eax
0x1800aef5e  js      loc_1800AF1B0
0x1800aef64  mov     r8d, 1; enum XmlNodeType
0x1800aef6a  lea     rdx, aEffect; "Effect"
0x1800aef71  mov     rcx, rbx; this
0x1800aef74  call    ?AdvanceDirectlyToNode@CPropertyParser@@AEAAJPEBGW4XmlNodeType@@@Z; CPropertyParser::AdvanceDirectlyToNode(ushort const *,XmlNodeType)
0x1800aef79  mov     ecx, eax
0x1800aef7b  lea     r8, aPropertyXmlMus_0; "Property XML must contain an <Effect> d"...
0x1800aef82  mov     edx, r15d
0x1800aef85  call    ?HrFailTrace@@YAJJW4VRL_D2D1@@PEBDZZ; HrFailTrace(long,VRL_D2D1,char const *,...)
0x1800aef8a  mov     esi, eax
0x1800aef8c  test    eax, eax
0x1800aef8e  js      loc_1800AF1EC
0x1800aef94  mov     rdx, [rbp+50h+arg_20]; enum EffectType::Enum *
0x1800aef9b  mov     rcx, rbx; this
0x1800aef9e  call    ?ParseEffectType@CPropertyParser@@AEAAJPEAW4Enum@EffectType@@@Z; CPropertyParser::ParseEffectType(EffectType::Enum *)
0x1800aefa3  mov     esi, eax
0x1800aefa5  test    eax, eax
0x1800aefa7  js      loc_1800AF228
0x1800aefad  mov     rcx, [rbp+50h+ppvObject]
0x1800aefb1  mov     rax, [rcx]
0x1800aefb4  mov     rax, [rax+0A0h]
0x1800aefbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aefc0  test    eax, eax
0x1800aefc2  jnz     loc_1800AF3B8
0x1800aefc8  lea     rcx, ??$ExecuteCallback@$1??$ParsePropertyByType@$00$00@CPropertyParser@@AEAAJPEAVCPropertyNodeArray@@I@Z@CPropertyParser@@CAJPEAV0@PEAVCPropertyNodeArray@@I@Z; CPropertyParser::ExecuteCallback<&CPropertyParser::ParsePropertyByType<1,1>(CPropertyNodeArray *,uint)>(CPropertyParser *,CPropertyNodeArray *,uint)
0x1800aefcf  mov     [rsp+150h+var_D8], 7FFFFFFFh
0x1800aefd7  lea     rax, aLocdefinition; "_locDefinition"
0x1800aefde  mov     [rbp+50h+var_B0], rcx
0x1800aefe2  mov     [rsp+150h+var_E0], rax
0x1800aefe7  lea     r8, [rsp+150h+var_E0]
0x1800aefec  lea     rax, ??$ExecuteCallback@$1?DiscardLocalization@CPropertyParser@@AEAAJPEAVCPropertyNodeArray@@I@Z@CPropertyParser@@CAJPEAV0@PEAVCPropertyNodeArray@@I@Z; CPropertyParser::ExecuteCallback<&CPropertyParser::DiscardLocalization(CPropertyNodeArray *,uint)>(CPropertyParser *,CPropertyNodeArray *,uint)
0x1800aeff3  mov     [rbp+50h+var_90], rcx
0x1800aeff7  mov     [rbp+50h+var_D0], rax
0x1800aeffb  lea     rdx, [rsp+150h+Block]
0x1800af000  lea     rax, aDisplayname_0; "DisplayName"
0x1800af007  mov     [rbp+50h+var_70], rcx
0x1800af00b  mov     [rbp+50h+var_C0], rax
0x1800af00f  mov     r9d, 6
0x1800af015  lea     rax, aAuthor; "Author"
0x1800af01c  mov     [rbp+50h+var_50], rcx
0x1800af020  mov     [rbp+50h+var_A0], rax
0x1800af024  mov     rcx, rbx; this
0x1800af027  lea     rax, aCategory; "Category"
0x1800af02e  mov     [rbp+50h+var_C8], r12b
0x1800af032  mov     [rbp+50h+var_80], rax
0x1800af036  lea     rax, aDescription; "Description"
0x1800af03d  mov     [rbp+50h+var_60], rax
0x1800af041  lea     rax, aInputs; "Inputs"
0x1800af048  mov     [rbp+50h+var_40], rax
0x1800af04c  lea     rax, ??$ExecuteCallback@$1?ParseInputs@CPropertyParser@@AEAAJPEAVCPropertyNodeArray@@I@Z@CPropertyParser@@CAJPEAV0@PEAVCPropertyNodeArray@@I@Z; CPropertyParser::ExecuteCallback<&CPropertyParser::ParseInputs(CPropertyNodeArray *,uint)>(CPropertyParser *,CPropertyNodeArray *,uint)
0x1800af053  mov     [rbp+50h+var_30], rax
0x1800af057  lea     rax, ?ParseProperty@CPropertyParser@@AEAAJPEAVCPropertyNodeArray@@I@Z; CPropertyParser::ParseProperty(CPropertyNodeArray *,uint)
0x1800af05e  mov     qword ptr [rsp+150h+var_130], rax; __int64
0x1800af063  mov     [rbp+50h+var_B8], 1
0x1800af06a  mov     [rbp+50h+var_A8], 1
0x1800af06e  mov     [rbp+50h+var_98], 2
0x1800af075  mov     [rbp+50h+var_88], 1
0x1800af079  mov     [rbp+50h+var_78], 3
0x1800af080  mov     [rbp+50h+var_68], 1
0x1800af084  mov     [rbp+50h+var_58], 4
0x1800af08b  mov     [rbp+50h+var_48], 1
0x1800af08f  mov     [rbp+50h+var_38], 5
0x1800af096  mov     [rbp+50h+var_28], 1
0x1800af09a  call    ?ParseProperties@CPropertyParser@@AEAAJPEAVCPropertyNodeArray@@PEBUELEMENT_INFO@1@IP81@EAAJ0I@Z@Z; CPropertyParser::ParseProperties(CPropertyNodeArray *,CPropertyParser::ELEMENT_INFO const *,uint,long (CPropertyParser::*)(CPropertyNodeArray *,uint))
0x1800af09f  mov     esi, eax
0x1800af0a1  test    eax, eax
0x1800af0a3  js      loc_1800AF268
0x1800af0a9  mov     rcx, rbx; this
0x1800af0ac  call    ?AdvanceDirectlyToAnyNode@CPropertyParser@@AEAAJXZ; CPropertyParser::AdvanceDirectlyToAnyNode(void)
0x1800af0b1  mov     edi, eax
0x1800af0b3  test    eax, eax
0x1800af0b5  js      loc_1800AF2A8
0x1800af0bb  cmp     eax, 1
0x1800af0be  jnz     loc_1800AF3FF
0x1800af0c4  mov     rcx, [rbx+18h]
0x1800af0c8  lea     r8, [rsp+150h+Block]
0x1800af0cd  mov     [rsp+150h+var_110], r14
0x1800af0d2  call    ??$CreateComObjectInit@ULockingRequired@@V?$CDIProperties@UID2D1Properties@@@@PEAVAbstractLock@@PEAV?$RefCountedObject@VCPropertyDescription@@ULockingRequired@@UDeleteOnZeroReference@@@@PEAVCPropertyNodeArray@@I_NPEAUIUnknown@@PEAU6@_N@@YAJPEAVAbstractLock@@PEAV?$RefCountedObject@VCPropertyDescription@@ULockingRequired@@UDeleteOnZeroReference@@@@PEAVCPropertyNodeArray@@I_NPEAUIUnknown@@43PEAPEAV?$CDIProperties@UID2D1Properties@@@@@Z; CreateComObjectInit<LockingRequired,CDIProperties<ID2D1Properties>,AbstractLock *,RefCountedObject<CPropertyDescription,LockingRequired,DeleteOnZeroReference> *,CPropertyNodeArray *,uint,bool,IUnknown *,IUnknown *,bool>(AbstractLock *,RefCountedObject<CPropertyDescription,LockingRequired,DeleteOnZeroReference> *,CPropertyNodeArray *,uint,bool,IUnknown *,IUnknown *,bool,CDIProperties<ID2D1Properties> * *)
0x1800af0d7  mov     edi, eax
0x1800af0d9  test    eax, eax
0x1800af0db  js      loc_1800AF2E1
0x1800af0e1  lea     rcx, [rsp+150h+Block]
0x1800af0e6  call    ?RemoveAll@?$CArray@V?$CComPtr@VCMultistepScaler@@@ATL@@V?$CDefaultTraits@V?$CComPtr@VCMultistepScaler@@@ATL@@@@VCDefaultAllocator@@@@QEAAX_N@Z; CArray<ATL::CComPtr<CMultistepScaler>,CDefaultTraits<ATL::CComPtr<CMultistepScaler>>,CDefaultAllocator>::RemoveAll(bool)
0x1800af0eb  mov     rcx, [rbx+38h]
0x1800af0ef  test    rcx, rcx
0x1800af0f2  jnz     loc_1800AF47B
0x1800af0f8  mov     rcx, [rbp+50h+ppvObject]
0x1800af0fc  test    rcx, rcx
0x1800af0ff  jz      short loc_1800AF10D
0x1800af101  mov     rax, [rcx]
0x1800af104  mov     rax, [rax+10h]
0x1800af108  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af10d  lea     r11, [rsp+150h+var_20]
0x1800af115  mov     eax, edi
0x1800af117  mov     rbx, [r11+38h]
0x1800af11b  mov     rsi, [r11+40h]
0x1800af11f  mov     rsp, r11
0x1800af122  pop     r15
0x1800af124  pop     r14
0x1800af126  pop     r12
0x1800af128  pop     rdi
0x1800af129  pop     rbp
0x1800af12a  retn
0x1800af12b  mov     ecx, edi; int
0x1800af12d  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800af132  mov     rcx, [rbp+50h+ppvObject]
0x1800af136  test    rcx, rcx
0x1800af139  jz      short loc_1800AF10D
0x1800af13b  mov     rdx, [rcx]
0x1800af13e  mov     rax, [rdx+10h]
0x1800af142  jmp     short loc_1800AF108
0x1800af144  mov     ecx, eax; int
0x1800af146  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800af14b  mov     rcx, [rsp+150h+Block]; Block
0x1800af150  test    rcx, rcx
0x1800af153  jnz     loc_1800AF31A
0x1800af159  mov     rcx, [rbx+38h]
0x1800af15d  mov     dword ptr [rsp+150h+var_F8], r12d
0x1800af162  test    rcx, rcx
0x1800af165  jz      short loc_1800AF1A2
0x1800af167  mov     rax, [rcx]
0x1800af16a  mov     rax, [rax+10h]
0x1800af16e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af173  mov     [rbx+38h], r12
0x1800af177  jmp     short loc_1800AF1A2
0x1800af179  mov     ecx, esi; int
0x1800af17b  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800af180  mov     rcx, [rsp+150h+Block]; Block
0x1800af185  test    rcx, rcx
0x1800af188  jnz     loc_1800AF353
0x1800af18e  mov     rcx, [rbx+38h]
0x1800af192  mov     dword ptr [rsp+150h+var_F8], r12d
0x1800af197  test    rcx, rcx
0x1800af19a  jnz     loc_1800AF451
0x1800af1a0  mov     edi, esi
0x1800af1a2  lea     rcx, [rbp+50h+ppvObject]; void *
0x1800af1a6  call    ??1?$CComPtr@UIWICBitmap@@@ATL@@QEAA@XZ; ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(void)
0x1800af1ab  jmp     loc_1800AF10D
0x1800af1b0  mov     ecx, esi; int
0x1800af1b2  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800af1b7  mov     rcx, [rsp+150h+Block]
0x1800af1bc  test    rcx, rcx
0x1800af1bf  jz      short loc_1800AF18E
0x1800af1c1  mov     edi, r12d
0x1800af1c4  cmp     dword ptr [rsp+150h+var_F8], r12d
0x1800af1c9  jbe     loc_1800AF35D
0x1800af1cf  mov     eax, edi
0x1800af1d1  lea     rcx, [rcx+rax*8]; void *
0x1800af1d5  call    ??1?$CComPtr@UIWICBitmap@@@ATL@@QEAA@XZ; ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(void)
0x1800af1da  mov     rcx, [rsp+150h+Block]
0x1800af1df  inc     edi
0x1800af1e1  cmp     edi, dword ptr [rsp+150h+var_F8]
0x1800af1e5  jb      short loc_1800AF1CF
0x1800af1e7  jmp     loc_1800AF35D
0x1800af1ec  mov     ecx, esi; int
0x1800af1ee  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800af1f3  mov     rcx, [rsp+150h+Block]
0x1800af1f8  test    rcx, rcx
0x1800af1fb  jz      short loc_1800AF18E
0x1800af1fd  mov     edi, r12d
0x1800af200  cmp     dword ptr [rsp+150h+var_F8], r12d
0x1800af205  jbe     loc_1800AF35D
0x1800af20b  mov     eax, edi
0x1800af20d  lea     rcx, [rcx+rax*8]; void *
0x1800af211  call    ??1?$CComPtr@UIWICBitmap@@@ATL@@QEAA@XZ; ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(void)
0x1800af216  mov     rcx, [rsp+150h+Block]
0x1800af21b  inc     edi
0x1800af21d  cmp     edi, dword ptr [rsp+150h+var_F8]
0x1800af221  jb      short loc_1800AF20B
0x1800af223  jmp     loc_1800AF35D
0x1800af228  mov     ecx, esi; int
0x1800af22a  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800af22f  mov     rcx, [rsp+150h+Block]
0x1800af234  test    rcx, rcx
0x1800af237  jz      loc_1800AF18E
0x1800af23d  mov     edi, r12d
0x1800af240  cmp     dword ptr [rsp+150h+var_F8], r12d
0x1800af245  jbe     loc_1800AF35D
0x1800af24b  mov     eax, edi
0x1800af24d  lea     rcx, [rcx+rax*8]; void *
0x1800af251  call    ??1?$CComPtr@UIWICBitmap@@@ATL@@QEAA@XZ; ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(void)
0x1800af256  mov     rcx, [rsp+150h+Block]
0x1800af25b  inc     edi
0x1800af25d  cmp     edi, dword ptr [rsp+150h+var_F8]
0x1800af261  jb      short loc_1800AF24B
0x1800af263  jmp     loc_1800AF35D
0x1800af268  mov     ecx, esi; int
0x1800af26a  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800af26f  mov     rcx, [rsp+150h+Block]
0x1800af274  test    rcx, rcx
0x1800af277  jz      loc_1800AF18E
0x1800af27d  mov     edi, r12d
0x1800af280  cmp     dword ptr [rsp+150h+var_F8], r12d
0x1800af285  jbe     loc_1800AF35D
0x1800af28b  mov     eax, edi
0x1800af28d  lea     rcx, [rcx+rax*8]; void *
0x1800af291  call    ??1?$CComPtr@UIWICBitmap@@@ATL@@QEAA@XZ; ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(void)
0x1800af296  mov     rcx, [rsp+150h+Block]
0x1800af29b  inc     edi
0x1800af29d  cmp     edi, dword ptr [rsp+150h+var_F8]
0x1800af2a1  jb      short loc_1800AF28B
0x1800af2a3  jmp     loc_1800AF35D
0x1800af2a8  mov     ecx, eax; int
0x1800af2aa  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800af2af  mov     rcx, [rsp+150h+Block]
0x1800af2b4  test    rcx, rcx
0x1800af2b7  jz      loc_1800AF159
0x1800af2bd  mov     esi, r12d
0x1800af2c0  cmp     dword ptr [rsp+150h+var_F8], r12d
0x1800af2c5  jbe     short loc_1800AF324
0x1800af2c7  mov     eax, esi
0x1800af2c9  lea     rcx, [rcx+rax*8]; void *
0x1800af2cd  call    ??1?$CComPtr@UIWICBitmap@@@ATL@@QEAA@XZ; ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(void)
0x1800af2d2  mov     rcx, [rsp+150h+Block]
0x1800af2d7  inc     esi
0x1800af2d9  cmp     esi, dword ptr [rsp+150h+var_F8]
0x1800af2dd  jb      short loc_1800AF2C7
0x1800af2df  jmp     short loc_1800AF324
0x1800af2e1  mov     ecx, edi; int
0x1800af2e3  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800af2e8  mov     rcx, [rsp+150h+Block]
0x1800af2ed  test    rcx, rcx
0x1800af2f0  jz      loc_1800AF159
0x1800af2f6  mov     esi, r12d
0x1800af2f9  cmp     dword ptr [rsp+150h+var_F8], r12d
0x1800af2fe  jbe     short loc_1800AF324
0x1800af300  mov     eax, esi
0x1800af302  lea     rcx, [rcx+rax*8]; void *
0x1800af306  call    ??1?$CComPtr@UIWICBitmap@@@ATL@@QEAA@XZ; ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(void)
0x1800af30b  mov     rcx, [rsp+150h+Block]
0x1800af310  inc     esi
0x1800af312  cmp     esi, dword ptr [rsp+150h+var_F8]
0x1800af316  jb      short loc_1800AF300
0x1800af318  jmp     short loc_1800AF324
  ... truncated ...
```
