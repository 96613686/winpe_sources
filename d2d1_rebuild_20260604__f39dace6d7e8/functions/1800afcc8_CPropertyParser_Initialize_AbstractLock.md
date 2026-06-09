# CPropertyParser::Initialize(AbstractLock *)

- ea: `0x1800afcc8`
- end: `0x1800b024c`
- name: `?Initialize@CPropertyParser@@QEAAJPEAVAbstractLock@@@Z`
- size: `1412`
- prototype: `__int64 __fastcall(CPropertyParser *__hidden this, struct AbstractLock *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800b0c04`

## callees

- `0x18001fd58`
- `0x1800389c0`
- `0x1800ad84c`
- `0x1800ae788`
- `0x1800ae97c`
- `0x1800aebb0`
- `0x1800afcc8`
- `0x180100670`
- `0x1801a043c`
- `0x1801b352c`
- `0x1801d3c04`
- `0x1802f5370`
- `0x180307010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800b0206`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800b0206`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x1800afd0b`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x1800afd0b`
- `XmlLite!CreateXmlReader` at `0x1800afd78`
- `XmlLite!CreateXmlReader` at `0x1800afd78`

## string_xrefs

- `0x1800afcf2`: `SYSTEMPROPERTIES.XML`
- `0x1800afdc1`: `SystemPropertyNames`
- `0x1800afe73`: `Unexpected end of property XML while looking for "%S".`
- `0x1800affd0`: `Unexpected end of property XML while looking for "%S".`
- `0x1800b00e8`: `Unexpected end of property XML while looking for "%S".`

## pseudocode

```c
__int64 __fastcall CPropertyParser::Initialize(CPropertyParser *this, struct AbstractLock *a2)
{
  struct IStream *v3; // rbx
  HRSRC Resource; // rax
  int LastErrorAsFailHr; // eax
  int v6; // edi
  HRESULT v8; // eax
  int v9; // eax
  void *v10; // rcx
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // rcx
  int v14; // ecx
  int v15; // ecx
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rcx
  int v19; // eax
  __int64 v20; // rcx
  int v21; // ecx
  __int64 v22; // rcx
  int v23; // eax
  __int64 v24; // rcx
  int v25; // eax
  __int64 v26; // rcx
  int v27; // ecx
  char *v28; // rcx
  unsigned int j; // ebx
  int v30; // eax
  int v31; // eax
  int v32; // ecx
  __int64 v33; // rcx
  unsigned int k; // ebx
  unsigned int i; // ebx
  void *Block; // [rsp+30h] [rbp-20h] BYREF
  __int64 v37; // [rsp+38h] [rbp-18h]
  void *ppvObject; // [rsp+90h] [rbp+40h] BYREF
  struct AbstractLock *v39; // [rsp+98h] [rbp+48h] BYREF
  struct IStream *v40; // [rsp+A0h] [rbp+50h] BYREF
  wchar_t *String2; // [rsp+A8h] [rbp+58h] BYREF

  v39 = a2;
  *((_QWORD *)this + 3) = &CEffectRegistry::s_registryCritSec;
  v3 = 0;
  v40 = 0;
  Resource = FindResourceExW(&_ImageBase, (LPCWSTR)0x17, L"SYSTEMPROPERTIES.XML", 0);
  if ( Resource )
  {
    LastErrorAsFailHr = CreateStreamFromResourceHandle(&_ImageBase, Resource, &v40);
    v6 = LastErrorAsFailHr;
    if ( LastErrorAsFailHr < 0 )
      goto LABEL_3;
    v3 = v40;
  }
  else
  {
    LastErrorAsFailHr = GetLastErrorAsFailHr();
    v6 = LastErrorAsFailHr;
    if ( LastErrorAsFailHr < 0 )
    {
LABEL_3:
      DoStackCapture(LastErrorAsFailHr);
      DoStackCapture(v6);
      goto LABEL_4;
    }
  }
  ppvObject = 0;
  v8 = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
  v6 = v8;
  if ( v8 < 0 )
  {
    DoStackCapture(v8);
    goto LABEL_70;
  }
  v9 = (*(__int64 (__fastcall **)(void *, struct IStream *))(*(_QWORD *)ppvObject + 24LL))(ppvObject, v3);
  v6 = v9;
  if ( v9 < 0 )
  {
    DoStackCapture(v9);
    goto LABEL_88;
  }
  v10 = ppvObject;
  *((_QWORD *)this + 7) = ppvObject;
  if ( v10 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v10 + 8LL))(v10);
  v6 = 0;
  while ( 1 )
  {
    if ( v6 == 1 )
      goto LABEL_26;
    v11 = *((_QWORD *)this + 7);
    LODWORD(v39) = 0;
    v12 = (*(__int64 (__fastcall **)(__int64, struct AbstractLock **))(*(_QWORD *)v11 + 56LL))(v11, &v39);
    v6 = v12;
    if ( v12 < 0 )
      goto LABEL_19;
    if ( (_DWORD)v39 == 1 )
      break;
LABEL_18:
    v12 = CPropertyParser::AdvanceDirectlyToAnyNode(this);
    v6 = v12;
    if ( v12 < 0 )
      goto LABEL_19;
  }
  v13 = *((_QWORD *)this + 7);
  String2 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, wchar_t **, _QWORD))(*(_QWORD *)v13 + 112LL))(v13, &String2, 0);
  if ( v6 < 0 )
  {
    v14 = v6;
    goto LABEL_20;
  }
  if ( wcscmp_0(L"SystemPropertyNames", String2) )
    goto LABEL_18;
  if ( v6 != 1 )
    goto LABEL_27;
LABEL_26:
  v12 = CPropertyParser::HrFailTraceXml(
          this,
          2147943568LL,
          512,
          "Unexpected end of property XML while looking for \"%S\".",
          L"SystemPropertyNames");
  v6 = v12;
  if ( v12 < 0 )
  {
LABEL_19:
    v14 = v12;
LABEL_20:
    DoStackCapture(v14);
    goto LABEL_21;
  }
LABEL_27:
  v17 = CPropertyParser::ParseProperties(this, (__int64)CPropertyParser::ParsePropertyByType<1>);
  v6 = v17;
  if ( v17 < 0 )
  {
    v15 = v17;
    goto LABEL_22;
  }
  if ( *((_DWORD *)this + 10) != 10 )
  {
    v6 = -2147024809;
LABEL_21:
    v15 = v6;
LABEL_22:
    DoStackCapture(v15);
LABEL_23:
    v16 = *((_QWORD *)this + 7);
    if ( v16 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      *((_QWORD *)this + 7) = 0;
    }
LABEL_88:
    ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(&ppvObject);
LABEL_4:
    ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(&v40);
    return (unsigned int)v6;
  }
  Block = 0;
  v37 = 0;
  v6 = CArray<ATL::CComPtr<CDIProperties<ID2D1Properties>>,CPropertyNodePtrTraits,CDefaultAllocator>::Resize(&Block, 2);
  if ( v6 < 0 )
  {
    v32 = v6;
    goto LABEL_67;
  }
  v6 = 0;
  while ( 2 )
  {
    if ( v6 == 1 )
      goto LABEL_47;
    v18 = *((_QWORD *)this + 7);
    LODWORD(v39) = 0;
    v19 = (*(__int64 (__fastcall **)(__int64, struct AbstractLock **))(*(_QWORD *)v18 + 56LL))(v18, &v39);
    v6 = v19;
    if ( v19 < 0 )
      goto LABEL_39;
    if ( (_DWORD)v39 != 1 )
    {
LABEL_38:
      v19 = CPropertyParser::AdvanceDirectlyToAnyNode(this);
      v6 = v19;
      if ( v19 < 0 )
        goto LABEL_39;
      continue;
    }
    break;
  }
  v20 = *((_QWORD *)this + 7);
  String2 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, wchar_t **, _QWORD))(*(_QWORD *)v20 + 112LL))(v20, &String2, 0);
  if ( v6 < 0 )
  {
    v21 = v6;
    goto LABEL_40;
  }
  if ( wcscmp_0(L"PrecisionAutoProperties", String2) )
    goto LABEL_38;
  if ( v6 != 1 )
    goto LABEL_48;
LABEL_47:
  v19 = CPropertyParser::HrFailTraceXml(
          this,
          2147943568LL,
          512,
          "Unexpected end of property XML while looking for \"%S\".",
          L"PrecisionAutoProperties");
  v6 = v19;
  if ( v19 < 0 )
  {
LABEL_39:
    v21 = v19;
LABEL_40:
    DoStackCapture(v21);
    DoStackCapture(v6);
    CArray<ATL::CComPtr<CMultistepScaler>,CDefaultTraits<ATL::CComPtr<CMultistepScaler>>,CDefaultAllocator>::RemoveAll(&Block);
    v22 = *((_QWORD *)this + 7);
    if ( v22 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      *((_QWORD *)this + 7) = 0;
    }
    if ( ppvObject )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    if ( v3 )
      (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v3 + 16LL))(v3);
    return (unsigned int)v6;
  }
LABEL_48:
  v23 = CPropertyParser::ParseProperties(this, 0);
  v6 = v23;
  if ( v23 < 0 )
  {
    DoStackCapture(v23);
    v28 = (char *)Block;
    if ( !Block )
    {
LABEL_84:
      LODWORD(v37) = 0;
      goto LABEL_23;
    }
    for ( i = 0; i < (unsigned int)v37; ++i )
    {
      ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(&v28[8 * i]);
      v28 = (char *)Block;
    }
LABEL_83:
    free(v28);
    Block = 0;
    HIDWORD(v37) = 0;
    goto LABEL_84;
  }
  v6 = 0;
  while ( 1 )
  {
    if ( v6 == 1 )
      goto LABEL_63;
    v24 = *((_QWORD *)this + 7);
    LODWORD(v39) = 0;
    v25 = (*(__int64 (__fastcall **)(__int64, struct AbstractLock **))(*(_QWORD *)v24 + 56LL))(v24, &v39);
    v6 = v25;
    if ( v25 < 0 )
      goto LABEL_56;
    if ( (_DWORD)v39 == 1 )
      break;
LABEL_55:
    v25 = CPropertyParser::AdvanceDirectlyToAnyNode(this);
    v6 = v25;
    if ( v25 < 0 )
      goto LABEL_56;
  }
  v26 = *((_QWORD *)this + 7);
  String2 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, wchar_t **, _QWORD))(*(_QWORD *)v26 + 112LL))(v26, &String2, 0);
  if ( v6 < 0 )
  {
    v27 = v6;
    goto LABEL_57;
  }
  if ( wcscmp_0(L"GlobalAutoProperties", String2) )
    goto LABEL_55;
  if ( v6 != 1 )
    goto LABEL_64;
LABEL_63:
  v25 = CPropertyParser::HrFailTraceXml(
          this,
          2147943568LL,
          512,
          "Unexpected end of property XML while looking for \"%S\".",
          L"GlobalAutoProperties");
  v6 = v25;
  if ( v25 < 0 )
  {
LABEL_56:
    v27 = v25;
LABEL_57:
    DoStackCapture(v27);
    DoStackCapture(v6);
    v28 = (char *)Block;
    if ( !Block )
      goto LABEL_84;
    for ( j = 0; j < (unsigned int)v37; ++j )
    {
      ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(&v28[8 * j]);
      v28 = (char *)Block;
    }
    goto LABEL_83;
  }
LABEL_64:
  v30 = CPropertyParser::ParseProperties(this, 0);
  v6 = v30;
  if ( v30 < 0 )
  {
    DoStackCapture(v30);
    v28 = (char *)Block;
    if ( !Block )
      goto LABEL_84;
    for ( k = 0; k < (unsigned int)v37; ++k )
    {
      ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(&v28[8 * k]);
      v28 = (char *)Block;
    }
    goto LABEL_83;
  }
  v31 = CArray<ATL::CComPtr<CDIProperties<ID2D1Properties>>,CPropertyNodePtrTraits,CDefaultAllocator>::AddArray<ATL::CComPtr<CDIProperties<ID2D1Properties>>>(
          this,
          Block,
          (unsigned int)v37);
  if ( v31 >= 0 )
    goto LABEL_68;
  v32 = v31;
LABEL_67:
  DoStackCapture(v32);
LABEL_68:
  CArray<ATL::CComPtr<CMultistepScaler>,CDefaultTraits<ATL::CComPtr<CMultistepScaler>>,CDefaultAllocator>::RemoveAll(&Block);
  v33 = *((_QWORD *)this + 7);
  if ( v33 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    *((_QWORD *)this + 7) = 0;
  }
LABEL_70:
  if ( ppvObject )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
  if ( v3 )
    (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v3 + 16LL))(v3);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800afcc8  mov     [rsp-38h+arg_8], rdx
0x1800afccd  push    rbp
0x1800afcce  push    rbx
0x1800afccf  push    rsi
0x1800afcd0  push    rdi
0x1800afcd1  push    r12
0x1800afcd3  push    r14
0x1800afcd5  push    r15
0x1800afcd7  mov     rbp, rsp
0x1800afcda  sub     rsp, 50h
0x1800afcde  xor     r14d, r14d
0x1800afce1  lea     rax, ?s_registryCritSec@CEffectRegistry@@1V?$ComObjectImpl@V?$StackAllocatedRefCount@VCriticalSectionAsAbstractLock@@UNoLockingRequired@@UAssertZeroRefCount@@@@Vnull_type@@@@A; ComObjectImpl<StackAllocatedRefCount<CriticalSectionAsAbstractLock,NoLockingRequired,AssertZeroRefCount>,null_type> CEffectRegistry::s_registryCritSec
0x1800afce8  mov     rsi, rcx
0x1800afceb  mov     [rcx+18h], rax
0x1800afcef  mov     ebx, r14d
0x1800afcf2  lea     r8, Name; "SYSTEMPROPERTIES.XML"
0x1800afcf9  xor     r9d, r9d; wLanguage
0x1800afcfc  mov     [rbp+arg_10], rbx
0x1800afd00  lea     edx, [r14+17h]; lpType
0x1800afd04  lea     rcx, __ImageBase; hModule
0x1800afd0b  call    cs:__imp_FindResourceExW
0x1800afd11  test    rax, rax
0x1800afd14  jnz     short loc_1800AFD49
0x1800afd16  call    ?GetLastErrorAsFailHr@@YAJXZ; GetLastErrorAsFailHr(void)
0x1800afd1b  mov     edi, eax
0x1800afd1d  test    eax, eax
0x1800afd1f  jns     short loc_1800AFD66
0x1800afd21  mov     ecx, eax; int
0x1800afd23  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800afd28  mov     ecx, edi; int
0x1800afd2a  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800afd2f  lea     rcx, [rbp+arg_10]; void *
0x1800afd33  call    ??1?$CComPtr@UIWICBitmap@@@ATL@@QEAA@XZ; ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(void)
0x1800afd38  mov     eax, edi
0x1800afd3a  add     rsp, 50h
0x1800afd3e  pop     r15
0x1800afd40  pop     r14
0x1800afd42  pop     r12
0x1800afd44  pop     rdi
0x1800afd45  pop     rsi
0x1800afd46  pop     rbx
0x1800afd47  pop     rbp
0x1800afd48  retn
0x1800afd49  lea     r8, [rbp+arg_10]; struct IStream **
0x1800afd4d  mov     rdx, rax; hResInfo
0x1800afd50  lea     rcx, __ImageBase; hModule
0x1800afd57  call    ?CreateStreamFromResourceHandle@@YAJPEAUHINSTANCE__@@PEAUHRSRC__@@PEAPEAUIStream@@@Z; CreateStreamFromResourceHandle(HINSTANCE__ *,HRSRC__ *,IStream * *)
0x1800afd5c  mov     edi, eax
0x1800afd5e  test    eax, eax
0x1800afd60  js      short loc_1800AFD21
0x1800afd62  mov     rbx, [rbp+arg_10]
0x1800afd66  xor     r8d, r8d; pMalloc
0x1800afd69  mov     [rbp+ppvObject], r14
0x1800afd6d  lea     rdx, [rbp+ppvObject]; ppvObject
0x1800afd71  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x1800afd78  call    cs:__imp_CreateXmlReader
0x1800afd7e  mov     edi, eax
0x1800afd80  test    eax, eax
0x1800afd82  js      loc_1800B0240
0x1800afd88  mov     rcx, [rbp+ppvObject]
0x1800afd8c  mov     rdx, rbx
0x1800afd8f  mov     rax, [rcx]
0x1800afd92  mov     rax, [rax+18h]
0x1800afd96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800afd9b  mov     edi, eax
0x1800afd9d  test    eax, eax
0x1800afd9f  js      loc_1800B022B
0x1800afda5  mov     rcx, [rbp+ppvObject]
0x1800afda9  mov     [rsi+38h], rcx
0x1800afdad  test    rcx, rcx
0x1800afdb0  jz      short loc_1800AFDBE
0x1800afdb2  mov     rax, [rcx]
0x1800afdb5  mov     rax, [rax+8]
0x1800afdb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800afdbe  mov     edi, r14d
0x1800afdc1  lea     r12, aSystemproperty; "SystemPropertyNames"
0x1800afdc8  mov     r15d, 1
0x1800afdce  cmp     edi, r15d
0x1800afdd1  jz      loc_1800AFE73
0x1800afdd7  mov     rcx, [rsi+38h]
0x1800afddb  lea     rdx, [rbp+arg_8]
0x1800afddf  mov     dword ptr [rbp+arg_8], r14d
0x1800afde3  mov     rax, [rcx]
0x1800afde6  mov     rax, [rax+38h]
0x1800afdea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800afdef  mov     edi, eax
0x1800afdf1  test    eax, eax
0x1800afdf3  js      short loc_1800AFE3E
0x1800afdf5  cmp     dword ptr [rbp+arg_8], r15d
0x1800afdf9  jnz     short loc_1800AFE30
0x1800afdfb  mov     rcx, [rsi+38h]
0x1800afdff  lea     rdx, [rbp+String2]
0x1800afe03  mov     [rbp+String2], r14
0x1800afe07  xor     r8d, r8d
0x1800afe0a  mov     rax, [rcx]
0x1800afe0d  mov     rax, [rax+70h]
0x1800afe11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800afe16  mov     edi, eax
0x1800afe18  test    eax, eax
0x1800afe1a  js      loc_1800AFED0
0x1800afe20  mov     rdx, [rbp+String2]; String2
0x1800afe24  mov     rcx, r12; String1
0x1800afe27  call    wcscmp_0
0x1800afe2c  test    eax, eax
0x1800afe2e  jz      short loc_1800AFE6E
0x1800afe30  mov     rcx, rsi; this
0x1800afe33  call    ?AdvanceDirectlyToAnyNode@CPropertyParser@@AEAAJXZ; CPropertyParser::AdvanceDirectlyToAnyNode(void)
0x1800afe38  mov     edi, eax
0x1800afe3a  test    eax, eax
0x1800afe3c  jns     short loc_1800AFDCE
0x1800afe3e  mov     ecx, eax; int
0x1800afe40  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800afe45  mov     ecx, edi; int
0x1800afe47  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800afe4c  mov     rcx, [rsi+38h]
0x1800afe50  test    rcx, rcx
0x1800afe53  jz      loc_1800B0232
0x1800afe59  mov     rax, [rcx]
0x1800afe5c  mov     rax, [rax+10h]
0x1800afe60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800afe65  mov     [rsi+38h], r14
0x1800afe69  jmp     loc_1800B0232
0x1800afe6e  cmp     edi, r15d
0x1800afe71  jnz     short loc_1800AFE98
0x1800afe73  lea     r9, aUnexpectedEndO_0; "Unexpected end of property XML while lo"...
0x1800afe7a  mov     [rsp+50h+var_30], r12
0x1800afe7f  mov     edx, 80070490h
0x1800afe84  mov     r8d, 200h
0x1800afe8a  mov     rcx, rsi
0x1800afe8d  call    ?HrFailTraceXml@CPropertyParser@@AEAAJJW4VRL_D2D1@@PEBDZZ; CPropertyParser::HrFailTraceXml(long,VRL_D2D1,char const *,...)
0x1800afe92  mov     edi, eax
0x1800afe94  test    eax, eax
0x1800afe96  js      short loc_1800AFE3E
0x1800afe98  lea     rax, ??$ParsePropertyByType@$00@CPropertyParser@@AEAAJPEAVCPropertyNodeArray@@I@Z; CPropertyParser::ParsePropertyByType<1>(CPropertyNodeArray *,uint)
0x1800afe9f  xor     r9d, r9d
0x1800afea2  lea     rdx, [rsi+20h]
0x1800afea6  mov     [rsp+50h+var_30], rax; __int64
0x1800afeab  xor     r8d, r8d
0x1800afeae  mov     rcx, rsi; this
0x1800afeb1  call    ?ParseProperties@CPropertyParser@@AEAAJPEAVCPropertyNodeArray@@PEBUELEMENT_INFO@1@IP81@EAAJ0I@Z@Z; CPropertyParser::ParseProperties(CPropertyNodeArray *,CPropertyParser::ELEMENT_INFO const *,uint,long (CPropertyParser::*)(CPropertyNodeArray *,uint))
0x1800afeb6  mov     edi, eax
0x1800afeb8  test    eax, eax
0x1800afeba  js      loc_1800B0224
0x1800afec0  cmp     dword ptr [rsi+28h], 0Ah
0x1800afec4  jz      short loc_1800AFED7
0x1800afec6  mov     edi, 80070057h
0x1800afecb  jmp     loc_1800AFE45
0x1800afed0  mov     ecx, edi
0x1800afed2  jmp     loc_1800AFE40
0x1800afed7  mov     edx, 2
0x1800afedc  mov     [rbp+Block], r14
0x1800afee0  lea     rcx, [rbp+Block]
0x1800afee4  mov     [rbp+var_18], r14
0x1800afee8  call    ?Resize@?$CArray@V?$CComPtr@V?$CDIProperties@UID2D1Properties@@@@@ATL@@VCPropertyNodePtrTraits@@VCDefaultAllocator@@@@QEAAJI@Z; CArray<ATL::CComPtr<CDIProperties<ID2D1Properties>>,CPropertyNodePtrTraits,CDefaultAllocator>::Resize(uint)
0x1800afeed  mov     edi, eax
0x1800afeef  test    eax, eax
0x1800afef1  js      loc_1800B021D
0x1800afef7  mov     edi, r14d
0x1800afefa  lea     r12, aPrecisionautop; "PrecisionAutoProperties"
0x1800aff01  cmp     edi, r15d
0x1800aff04  jz      loc_1800AFFD0
0x1800aff0a  mov     rcx, [rsi+38h]
0x1800aff0e  lea     rdx, [rbp+arg_8]
0x1800aff12  mov     dword ptr [rbp+arg_8], r14d
0x1800aff16  mov     rax, [rcx]
0x1800aff19  mov     rax, [rax+38h]
0x1800aff1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aff22  mov     edi, eax
0x1800aff24  test    eax, eax
0x1800aff26  js      short loc_1800AFF71
0x1800aff28  cmp     dword ptr [rbp+arg_8], r15d
0x1800aff2c  jnz     short loc_1800AFF63
0x1800aff2e  mov     rcx, [rsi+38h]
0x1800aff32  lea     rdx, [rbp+String2]
0x1800aff36  mov     [rbp+String2], r14
0x1800aff3a  xor     r8d, r8d
0x1800aff3d  mov     rax, [rcx]
0x1800aff40  mov     rax, [rax+70h]
0x1800aff44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aff49  mov     edi, eax
0x1800aff4b  test    eax, eax
0x1800aff4d  js      loc_1800B00DC
0x1800aff53  mov     rdx, [rbp+String2]; String2
0x1800aff57  mov     rcx, r12; String1
0x1800aff5a  call    wcscmp_0
0x1800aff5f  test    eax, eax
0x1800aff61  jz      short loc_1800AFFCB
0x1800aff63  mov     rcx, rsi; this
0x1800aff66  call    ?AdvanceDirectlyToAnyNode@CPropertyParser@@AEAAJXZ; CPropertyParser::AdvanceDirectlyToAnyNode(void)
0x1800aff6b  mov     edi, eax
0x1800aff6d  test    eax, eax
0x1800aff6f  jns     short loc_1800AFF01
0x1800aff71  mov     ecx, eax; int
0x1800aff73  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800aff78  mov     ecx, edi; int
0x1800aff7a  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800aff7f  lea     rcx, [rbp+Block]
0x1800aff83  call    ?RemoveAll@?$CArray@V?$CComPtr@VCMultistepScaler@@@ATL@@V?$CDefaultTraits@V?$CComPtr@VCMultistepScaler@@@ATL@@@@VCDefaultAllocator@@@@QEAAX_N@Z; CArray<ATL::CComPtr<CMultistepScaler>,CDefaultTraits<ATL::CComPtr<CMultistepScaler>>,CDefaultAllocator>::RemoveAll(bool)
0x1800aff88  mov     rcx, [rsi+38h]
0x1800aff8c  test    rcx, rcx
0x1800aff8f  jz      short loc_1800AFFA1
0x1800aff91  mov     rax, [rcx]
0x1800aff94  mov     rax, [rax+10h]
0x1800aff98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aff9d  mov     [rsi+38h], r14
0x1800affa1  mov     rcx, [rbp+ppvObject]
0x1800affa5  test    rcx, rcx
0x1800affa8  jz      short loc_1800AFFB6
0x1800affaa  mov     rax, [rcx]
0x1800affad  mov     rax, [rax+10h]
0x1800affb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800affb6  test    rbx, rbx
0x1800affb9  jz      loc_1800AFD38
0x1800affbf  mov     rcx, [rbx]
0x1800affc2  mov     rax, [rcx+10h]
0x1800affc6  jmp     loc_1800B0190
0x1800affcb  cmp     edi, r15d
0x1800affce  jnz     short loc_1800AFFF9
0x1800affd0  lea     r9, aUnexpectedEndO_0; "Unexpected end of property XML while lo"...
0x1800affd7  mov     [rsp+50h+var_30], r12
0x1800affdc  mov     edx, 80070490h
0x1800affe1  mov     r8d, 200h
0x1800affe7  mov     rcx, rsi
0x1800affea  call    ?HrFailTraceXml@CPropertyParser@@AEAAJJW4VRL_D2D1@@PEBDZZ; CPropertyParser::HrFailTraceXml(long,VRL_D2D1,char const *,...)
0x1800affef  mov     edi, eax
0x1800afff1  test    eax, eax
0x1800afff3  js      loc_1800AFF71
0x1800afff9  mov     r9d, r15d
0x1800afffc  mov     [rsp+50h+var_30], r14; __int64
0x1800b0001  lea     r8, off_18030E578; "Fields"
0x1800b0008  mov     rcx, rsi; this
0x1800b000b  lea     rdx, [rbp+Block]
0x1800b000f  call    ?ParseProperties@CPropertyParser@@AEAAJPEAVCPropertyNodeArray@@PEBUELEMENT_INFO@1@IP81@EAAJ0I@Z@Z; CPropertyParser::ParseProperties(CPropertyNodeArray *,CPropertyParser::ELEMENT_INFO const *,uint,long (CPropertyParser::*)(CPropertyNodeArray *,uint))
0x1800b0014  mov     edi, eax
0x1800b0016  test    eax, eax
0x1800b0018  js      loc_1800B01D6
0x1800b001e  mov     edi, r14d
0x1800b0021  lea     r12, aGlobalautoprop; "GlobalAutoProperties"
0x1800b0028  cmp     edi, r15d
0x1800b002b  jz      loc_1800B00E8
0x1800b0031  mov     rcx, [rsi+38h]
0x1800b0035  lea     rdx, [rbp+arg_8]
0x1800b0039  mov     dword ptr [rbp+arg_8], r14d
0x1800b003d  mov     rax, [rcx]
0x1800b0040  mov     rax, [rax+38h]
0x1800b0044  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0049  mov     edi, eax
0x1800b004b  test    eax, eax
0x1800b004d  js      short loc_1800B0098
0x1800b004f  cmp     dword ptr [rbp+arg_8], r15d
0x1800b0053  jnz     short loc_1800B008A
0x1800b0055  mov     rcx, [rsi+38h]
0x1800b0059  lea     rdx, [rbp+String2]
0x1800b005d  mov     [rbp+String2], r14
0x1800b0061  xor     r8d, r8d
0x1800b0064  mov     rax, [rcx]
0x1800b0067  mov     rax, [rax+70h]
0x1800b006b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0070  mov     edi, eax
0x1800b0072  test    eax, eax
0x1800b0074  js      loc_1800B019D
0x1800b007a  mov     rdx, [rbp+String2]; String2
0x1800b007e  mov     rcx, r12; String1
0x1800b0081  call    wcscmp_0
0x1800b0086  test    eax, eax
0x1800b0088  jz      short loc_1800B00E3
0x1800b008a  mov     rcx, rsi; this
0x1800b008d  call    ?AdvanceDirectlyToAnyNode@CPropertyParser@@AEAAJXZ; CPropertyParser::AdvanceDirectlyToAnyNode(void)
0x1800b0092  mov     edi, eax
0x1800b0094  test    eax, eax
0x1800b0096  jns     short loc_1800B0028
0x1800b0098  mov     ecx, eax; int
0x1800b009a  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800b009f  mov     ecx, edi; int
0x1800b00a1  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800b00a6  mov     rcx, [rbp+Block]
0x1800b00aa  test    rcx, rcx
0x1800b00ad  jz      loc_1800B0214
0x1800b00b3  mov     ebx, r14d
0x1800b00b6  cmp     dword ptr [rbp+var_18], r14d
0x1800b00ba  jbe     loc_1800B0206
0x1800b00c0  mov     eax, ebx
0x1800b00c2  lea     rcx, [rcx+rax*8]; void *
0x1800b00c6  call    ??1?$CComPtr@UIWICBitmap@@@ATL@@QEAA@XZ; ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(void)
0x1800b00cb  mov     rcx, [rbp+Block]
0x1800b00cf  add     ebx, r15d
0x1800b00d2  cmp     ebx, dword ptr [rbp+var_18]
0x1800b00d5  jb      short loc_1800B00C0
0x1800b00d7  jmp     loc_1800B0206
0x1800b00dc  mov     ecx, edi
0x1800b00de  jmp     loc_1800AFF73
0x1800b00e3  cmp     edi, r15d
0x1800b00e6  jnz     short loc_1800B010D
0x1800b00e8  lea     r9, aUnexpectedEndO_0; "Unexpected end of property XML while lo"...
0x1800b00ef  mov     [rsp+50h+var_30], r12
0x1800b00f4  mov     edx, 80070490h
0x1800b00f9  mov     r8d, 200h
0x1800b00ff  mov     rcx, rsi
0x1800b0102  call    ?HrFailTraceXml@CPropertyParser@@AEAAJJW4VRL_D2D1@@PEBDZZ; CPropertyParser::HrFailTraceXml(long,VRL_D2D1,char const *,...)
0x1800b0107  mov     edi, eax
  ... truncated ...
```
