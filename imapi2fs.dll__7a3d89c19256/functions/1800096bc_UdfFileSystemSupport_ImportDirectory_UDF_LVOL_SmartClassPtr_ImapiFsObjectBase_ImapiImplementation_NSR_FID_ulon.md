# UdfFileSystemSupport::ImportDirectory(UDF_LVOL *,SmartClassPtr<ImapiFsObjectBase,ImapiImplementation>,NSR_FID *,ulong,int)

- ea: `0x1800096bc`
- end: `0x18000a344`
- name: `?ImportDirectory@UdfFileSystemSupport@@IEAAXPEAVUDF_LVOL@@V?$SmartClassPtr@VImapiFsObjectBase@@VImapiImplementation@@@@PEAUNSR_FID@@KH@Z`
- size: `3208`
- prototype: ``
- caller_count: `3`
- callee_count: `32`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x1800096bc`
- `0x180022b74`
- `0x1800379a0`

## callees

- `0x180003580`
- `0x180003a20`
- `0x180005040`
- `0x18000726c`
- `0x18000960c`
- `0x1800096bc`
- `0x18000ba24`
- `0x18000c888`
- `0x18000c8d0`
- `0x18000d1c0`
- `0x180017090`
- `0x180018e20`
- `0x18001b974`
- `0x1800218f0`
- `0x1800223c0`
- `0x180022b74`
- `0x1800236cc`
- `0x180023724`
- `0x180023c08`
- `0x180023c44`
- `0x1800251dc`
- `0x180028568`
- `0x18002ade4`
- `0x18002b680`
- `0x18002d4e4`
- `0x18002f228`
- `0x180036dc8`
- `0x180038c94`
- `0x180051904`
- `0x18005ff7c`
- `0x180061098`
- `0x180061620`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
void UdfFileSystemSupport::ImportDirectory(struct UdfFileSystemSupport *a1, ...)
{
  struct NSR_FID *v1; // rdi
  _QWORD **v2; // rbx
  struct UDF_LVOL *v3; // rsi
  UdfFileSystemSupport *v4; // r12
  struct UDF_LVOL *v5; // rax
  CIMAPIException *v6; // rax
  struct UDF_LVOL *v7; // rbx
  _QWORD *v8; // rax
  int v9; // ebx
  struct UDF_LVOL *v10; // rcx
  struct ICB_ENTRY *IcbEntry; // rax
  __int64 v12; // rcx
  struct ICB_ENTRY *v13; // r15
  struct UDF_LVOL *v14; // rax
  CIMAPIException *v15; // rax
  struct UDF_LVOL *v16; // rbx
  __int64 v17; // r13
  struct UDF_LVOL *v18; // rax
  struct UDF_LVOL *v19; // rbx
  struct UDF_LVOL *v20; // rax
  struct UDF_LVOL *v21; // rbx
  __int64 v22; // rax
  const wchar_t *v23; // r9
  struct UDF_LVOL *v24; // rax
  CIMAPIException *v25; // rax
  struct UDF_LVOL *v26; // rbx
  const wchar_t *v27; // r9
  struct UDF_LVOL *v28; // rax
  CIMAPIException *v29; // rax
  struct UDF_LVOL *v30; // rbx
  ImapiFsObjectBase ***v31; // r15
  struct UDF_LVOL *v32; // rcx
  struct UDF_LVOL *v33; // rbx
  ImapiFsObjectBase *v34; // rcx
  _QWORD *v35; // rdx
  struct UDF_LVOL *v36; // rax
  struct UDF_LVOL *v37; // rbx
  const struct ATL::CComBSTR *FullPathOriginal; // rax
  struct UDF_LVOL *v39; // rbx
  const struct ATL::CComBSTR *v40; // rax
  ImapiDirectoryInfo *v41; // rax
  struct UDF_LVOL *v42; // rax
  __int64 v43; // rcx
  __int64 v44; // rax
  struct UDF_LVOL **v45; // r15
  struct ICB_ENTRY *v46; // rax
  unsigned int v47; // edx
  int v48; // r9d
  char v49; // al
  struct UDF_LVOL *v50; // rax
  struct UDF_LVOL *v51; // rax
  struct UDF_LVOL *v52; // rbx
  struct UDF_LVOL *v53; // rax
  struct UDF_LVOL *v54; // rbx
  struct UDF_LVOL *pExceptionObject; // [rsp+38h] [rbp-99h] BYREF
  struct UDF_LVOL *v56; // [rsp+40h] [rbp-91h] BYREF
  struct UDF_LVOL *v57; // [rsp+48h] [rbp-89h] BYREF
  const wchar_t *v58; // [rsp+50h] [rbp-81h] BYREF
  unsigned __int8 v59; // [rsp+58h] [rbp-79h] BYREF
  unsigned __int8 v60[7]; // [rsp+59h] [rbp-78h] BYREF
  struct UDF_LVOL *v61; // [rsp+60h] [rbp-71h] BYREF
  ICB_INFO *v62; // [rsp+68h] [rbp-69h] BYREF
  char v63[8]; // [rsp+70h] [rbp-61h] BYREF
  _BYTE v64[160]; // [rsp+78h] [rbp-59h] BYREF
  struct UDF_LVOL *v66; // [rsp+130h] [rbp+5Fh] BYREF
  va_list va; // [rsp+130h] [rbp+5Fh]
  void *v68; // [rsp+138h] [rbp+67h]
  struct NSR_FID *v69; // [rsp+140h] [rbp+6Fh] BYREF
  va_list va1; // [rsp+140h] [rbp+6Fh]
  __int64 v71; // [rsp+148h] [rbp+77h]
  __int64 v72; // [rsp+150h] [rbp+7Fh]
  va_list va2; // [rsp+158h] [rbp+87h] BYREF

  va_start(va2, a1);
  va_start(va1, a1);
  va_start(va, a1);
  v66 = va_arg(va1, struct UDF_LVOL *);
  v68 = va_arg(va1, void *);
  va_copy(va2, va1);
  v69 = va_arg(va2, struct NSR_FID *);
  v71 = va_arg(va2, _QWORD);
  v72 = va_arg(va2, _QWORD);
  v1 = v69;
  v2 = (_QWORD **)v68;
  v3 = v66;
  v4 = a1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 87, &WPP_cfb9f38fb45937fd90037ddd4a0f05da_Traceguids);
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v58);
  SmartPtr<ImportMetadata>::SmartPtr<ImportMetadata>(&v61, 0);
  v62 = (struct UDF_LVOL *)((char *)v3 + 552);
  if ( v3 == (struct UDF_LVOL *)-552LL )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && ((unsigned __int8)((_BYTE)v3 + 44) & *((_BYTE *)WPP_GLOBAL_Control + 68)) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      WPP_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        (unsigned int)((_DWORD)v3 + 640),
        &WPP_cfb9f38fb45937fd90037ddd4a0f05da_Traceguids);
    }
    v5 = (struct UDF_LVOL *)operator new(0x58u);
    v66 = v5;
    if ( v5 )
      v6 = CIMAPIException::CIMAPIException(v5, -1062555392);
    else
      v6 = 0;
    SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>((struct UDF_LVOL **)va, v6);
    v7 = v66;
    if ( v66 && *(_QWORD *)v66 )
    {
      CIMAPIException::SetCodeRefInfo(
        *(CIMAPIException **)v66,
        "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiudf.cpp",
        2117);
      pExceptionObject = v7;
      if ( v7 )
        ++*((_DWORD *)v7 + 2);
      throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
    }
    CIMAPIException::CIMAPIException((CIMAPIException *)v64, (const struct CIMAPIException *)&CIMAPIException::badAlloc);
    throw (CIMAPIException *)v64;
  }
  v8 = *v2;
  if ( !*v2 || (v9 = 0, !*v8) )
  {
    v9 = 1;
    v10 = *(struct UDF_LVOL **)(*((_QWORD *)v4 + 6) + 56LL);
    v56 = v10;
    if ( v10 )
      ++*((_DWORD *)v10 + 2);
    SmartPtr<ImportMetadata>::operator=(&v61, &v56);
    SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&v56);
  }
  IcbEntry = ICB_INFO::GetIcbEntry((struct UDF_LVOL *)((char *)v3 + 552), v71);
  v13 = IcbEntry;
  if ( !IcbEntry )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 89, &WPP_cfb9f38fb45937fd90037ddd4a0f05da_Traceguids);
    }
    v14 = (struct UDF_LVOL *)operator new(0x58u);
    v66 = v14;
    if ( v14 )
      v15 = CIMAPIException::CIMAPIException(v14, -1062555392);
    else
      v15 = 0;
    SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>((struct UDF_LVOL **)va, v15);
    v16 = v66;
    if ( v66 && *(_QWORD *)v66 )
    {
      CIMAPIException::SetCodeRefInfo(
        *(CIMAPIException **)v66,
        "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiudf.cpp",
        2135);
      pExceptionObject = v16;
      if ( v16 )
        ++*((_DWORD *)v16 + 2);
      throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
    }
    CIMAPIException::CIMAPIException((CIMAPIException *)v64, (const struct CIMAPIException *)&CIMAPIException::badAlloc);
    throw (CIMAPIException *)v64;
  }
  v17 = *((_QWORD *)IcbEntry + 5);
  if ( !v17 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 90, &WPP_cfb9f38fb45937fd90037ddd4a0f05da_Traceguids);
    }
    v18 = (struct UDF_LVOL *)operator new(0x58u);
    v66 = v18;
    if ( v18 )
      v18 = CIMAPIException::CIMAPIException(v18, -1062555392);
    SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>((struct UDF_LVOL **)va, v18);
    v19 = v66;
    if ( v66 && *(_QWORD *)v66 )
    {
      CIMAPIException::SetCodeRefInfo(
        *(CIMAPIException **)v66,
        "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiudf.cpp",
        2145);
      pExceptionObject = v19;
      if ( v19 )
        ++*((_DWORD *)v19 + 2);
      throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
    }
    CIMAPIException::CIMAPIException((CIMAPIException *)v64, (const struct CIMAPIException *)&CIMAPIException::badAlloc);
    throw (CIMAPIException *)v64;
  }
  if ( !v9 && !(unsigned __int8)UdfFileSystemSupport::GetObjectName(v12, v1, &v58) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 91, &WPP_cfb9f38fb45937fd90037ddd4a0f05da_Traceguids);
    }
    v20 = (struct UDF_LVOL *)operator new(0x58u);
    v66 = v20;
    if ( v20 )
      v20 = CIMAPIException::CIMAPIException(v20, -1062555309, *((_QWORD *)v4 + 1));
    SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>((struct UDF_LVOL **)va, v20);
    v21 = v66;
    if ( v66 && *(_QWORD *)v66 )
    {
      CIMAPIException::SetCodeRefInfo(
        *(CIMAPIException **)v66,
        "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiudf.cpp",
        2156);
      pExceptionObject = v21;
      if ( v21 )
        ++*((_DWORD *)v21 + 2);
      throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
    }
    CIMAPIException::CIMAPIException((CIMAPIException *)v64, (const struct CIMAPIException *)&CIMAPIException::badAlloc);
    throw (CIMAPIException *)v64;
  }
  if ( *((_BYTE *)v13 + 34) != 2 || (_DWORD)v72 )
    goto LABEL_141;
  v22 = *(_QWORD *)(v17 + 16);
  if ( *(_WORD *)(v22 + 20) != 4 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      v23 = L"(root)";
      if ( !v9 )
        LODWORD(v23) = (_DWORD)v58;
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        92,
        (unsigned int)&WPP_cfb9f38fb45937fd90037ddd4a0f05da_Traceguids,
        (_DWORD)v23,
        *(_WORD *)(v22 + 20));
    }
    v24 = (struct UDF_LVOL *)operator new(0x58u);
    v66 = v24;
    if ( v24 )
      v25 = CIMAPIException::CIMAPIException(v24, -1062555308, *((_QWORD *)v4 + 1));
    else
      v25 = 0;
    SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>((struct UDF_LVOL **)va, v25);
    v26 = v66;
    if ( v66 && *(_QWORD *)v66 )
    {
      CIMAPIException::SetCodeRefInfo(
        *(CIMAPIException **)v66,
        "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiudf.cpp",
        2171);
      pExceptionObject = v26;
      if ( v26 )
        ++*((_DWORD *)v26 + 2);
      throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
    }
    CIMAPIException::CIMAPIException((CIMAPIException *)v64, (const struct CIMAPIException *)&CIMAPIException::badAlloc);
    throw (CIMAPIException *)v64;
  }
  if ( !UdfFileSystemSupport::IsDataContiguous(v4, v66, (struct FILE_ICB_DESCRIPTOR *)v17) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      v27 = L"(root)";
      if ( !v9 )
        v27 = v58;
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 93, &WPP_cfb9f38fb45937fd90037ddd4a0f05da_Traceguids, v27);
    }
    v28 = (struct UDF_LVOL *)operator new(0x58u);
    v66 = v28;
    if ( v28 )
      v29 = CIMAPIException::CIMAPIException(v28, -1062555308, *((_QWORD *)v4 + 1));
    else
      v29 = 0;
    SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>((struct UDF_LVOL **)va, v29);
    v30 = v66;
    if ( v66 && *(_QWORD *)v66 )
    {
      CIMAPIException::SetCodeRefInfo(
        *(CIMAPIException **)v66,
        "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiudf.cpp",
        2178);
      pExceptionObject = v30;
      if ( v30 )
        ++*((_DWORD *)v30 + 2);
      throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
    }
    CIMAPIException::CIMAPIException((CIMAPIException *)v64, (const struct CIMAPIException *)&CIMAPIException::badAlloc);
    throw (CIMAPIException *)v64;
  }
  if ( v9 )
  {
LABEL_141:
    v39 = v61;
  }
  else
  {
    v31 = (ImapiFsObjectBase ***)v68;
    v32 = *(struct UDF_LVOL **)v68;
    v56 = v32;
    if ( v32 )
      ++*((_DWORD *)v32 + 2);
    v33 = *(struct UDF_LVOL **)ImapiDirectoryInfo::GetFileDirRecord(*(_QWORD *)v32, v63, &v58);
    pExceptionObject = v33;
    if ( v33 )
      ++*((_DWORD *)v33 + 2);
    SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(v63);
    SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&v56);
    if ( v33 && *(_QWORD *)v33 )
    {
      v34 = *(ImapiFsObjectBase **)v33;
      if ( *(_DWORD *)(*(_QWORD *)v33 + 56LL) && *((_DWORD *)v34 + 14) != 3 )
      {
        _bstr_t::_bstr_t((_bstr_t *)va, L"\\");
        ImapiFsObjectBase::GetFullPathOriginal(**v31);
        v35 = *(_QWORD **)operator+((struct _bstr_t *)&v57);
        if ( v35 )
          v35 = (_QWORD *)*v35;
        ATL::operator+(&v56, v35, &v58);
        _bstr_t::~_bstr_t((_bstr_t *)&v57);
        _bstr_t::~_bstr_t((_bstr_t *)va);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 96, &WPP_cfb9f38fb45937fd90037ddd4a0f05da_Traceguids, v56);
        }
        v36 = (struct UDF_LVOL *)operator new(0x58u);
        v66 = v36;
        if ( v36 )
          v36 = CIMAPIException::CIMAPIException(v36, -1062555298, v56, *((_QWORD *)v4 + 1));
        SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>((struct UDF_LVOL **)va, v36);
        v37 = v66;
        if ( v66 && *(_QWORD *)v66 )
        {
          CIMAPIException::SetCodeRefInfo(
            *(CIMAPIException **)v66,
            "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiudf.cpp",
            2223);
          v57 = v37;
          if ( v37 )
            ++*((_DWORD *)v37 + 2);
          throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&v57;
        }
        CIMAPIException::CIMAPIException(
          (CIMAPIException *)v64,
          (const struct CIMAPIException *)&CIMAPIException::badAlloc);
        throw (CIMAPIException *)v64;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
      {
        FullPathOriginal = ImapiFsObjectBase::GetFullPathOriginal(v34);
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          95,
          &WPP_cfb9f38fb45937fd90037ddd4a0f05da_Traceguids,
          *(_QWORD *)FullPathOriginal);
      }
      SmartPtr<ImportMetadata>::operator=(&v61, &pExceptionObject);
      v39 = v61;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
      {
        v40 = ImapiFsObjectBase::GetFullPathOriginal(**v31);
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          94,
          (unsigned int)&WPP_cfb9f38fb45937fd90037ddd4a0f05da_Traceguids,
          *(_QWORD *)v40,
          (__int64)v58);
      }
      v41 = (ImapiDirectoryInfo *)operator new(0x318u);
      v57 = v41;
      if ( v41 )
        v41 = (ImapiDirectoryInfo *)ImapiDirectoryInfo::ImapiDirectoryInfo(v41);
      SmartPtr<ImportMetadata>::SmartPtr<ImportMetadata>(&v56, v41);
      SmartPtr<ImportMetadata>::operator=(&v61, &v56);
      SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&v56);
      v39 = v61;
      v56 = v61;
      if ( v61 )
        ++*((_DWORD *)v61 + 2);
      UdfFileSystemSupport::SetObjectAttributes(a1);
      --*(_DWORD *)(*((_QWORD *)v4 + 6) + 20LL);
      v42 = *(struct UDF_LVOL **)v68;
      v57 = v42;
      if ( v42 )
        ++*((_DWORD *)v42 + 2);
      v43 = *(_QWORD *)v42;
      v56 = v39;
      if ( v39 )
        ++*((_DWORD *)v39 + 2);
      ImapiDirectoryInfo::AddDirectory(v43, &v56);
      SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&v57);
      v4 = a1;
    }
    SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&pExceptionObject);
  }
  if ( *(_BYTE *)(v17 + 177) )
  {
    DIR_ICB_DESCRIPTOR::InitializeFidIterator((DIR_ICB_DESCRIPTOR *)v17, 0, v66);
  }
  else
  {
    v44 = *(_QWORD *)(v17 + 16);
    if ( (*(_BYTE *)(v44 + 27) == 4 || *(_BYTE *)(v44 + 27) == 13) && *(_QWORD *)(v17 + 144) )
    {
      *(_DWORD *)(v17 + 140) += *(_DWORD *)(v17 + 132);
      *(_DWORD *)(v17 + 132) = 0;
      *(_BYTE *)(v17 + 176) = 0;
    }
  }
  v45 = (struct UDF_LVOL **)v68;
  while ( DIR_ICB_DESCRIPTOR::NextFid((DIR_ICB_DESCRIPTOR *)v17, (struct NSR_FID **)va1, v60, &v59) )
  {
    if ( (*((_BYTE *)v69 + 18) & 0xC) == 0 )
    {
      v46 = ICB_INFO::GetIcbEntry(v62, *((_DWORD *)v69 + 6));
      if ( !v46 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 97, &WPP_cfb9f38fb45937fd90037ddd4a0f05da_Traceguids);
        }
        v53 = (struct UDF_LVOL *)operator new(0x58u);
        v66 = v53;
        if ( v53 )
          v53 = CIMAPIException::CIMAPIException(v53, -1062555392);
        SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>((struct UDF_LVOL **)va, v53);
        v54 = v66;
        if ( v66 && *(_QWORD *)v66 )
        {
          CIMAPIException::SetCodeRefInfo(
            *(CIMAPIException **)v66,
            "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiudf.cpp",
            2260);
          v62 = v54;
          if ( v54 )
            ++*((_DWORD *)v54 + 2);
          throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&v62;
        }
        CIMAPIException::CIMAPIException(
          (CIMAPIException *)v64,
          (const struct CIMAPIException *)&CIMAPIException::badAlloc);
        throw (CIMAPIException *)v64;
      }
      v49 = *((_BYTE *)v46 + 34);
      if ( v49 == 2 )
      {
        pExceptionObject = v39;
        if ( v39 )
          ++*((_DWORD *)v39 + 2);
        UdfFileSystemSupport::ImportDirectory((_DWORD)v4, (_DWORD)v66, (unsigned int)&pExceptionObject, v48, v47, 0);
      }
      else if ( v49 == 1 )
      {
        pExceptionObject = v39;
        if ( v39 )
          ++*((_DWORD *)v39 + 2);
        UdfFileSystemSupport::ImportFile(v4);
      }
      else
      {
        if ( v49 != 3 || (_DWORD)v72 != 1 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 98, &WPP_cfb9f38fb45937fd90037ddd4a0f05da_Traceguids);
          }
          v51 = (struct UDF_LVOL *)operator new(0x58u);
          v66 = v51;
          if ( v51 )
            v51 = CIMAPIException::CIMAPIException(v51, -1062555309, *((_QWORD *)v4 + 1));
          SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>((struct UDF_LVOL **)va, v51);
          v52 = v66;
          if ( v66 && *(_QWORD *)v66 )
          {
            CIMAPIException::SetCodeRefInfo(
              *(CIMAPIException **)v66,
              "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiudf.cpp",
              2282);
            v62 = v52;
            if ( v52 )
              ++*((_DWORD *)v52 + 2);
            throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&v62;
          }
          CIMAPIException::CIMAPIException(
            (CIMAPIException *)v64,
            (const struct CIMAPIException *)&CIMAPIException::badAlloc);
          throw (CIMAPIException *)v64;
        }
        v50 = *v45;
        pExceptionObject = v50;
        if ( v50 )
          ++*((_DWORD *)v50 + 2);
        UdfFileSystemSupport::ImportStream(v4);
      }
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 99, &WPP_cfb9f38fb45937fd90037ddd4a0f05da_Traceguids);
  }
  SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&v61);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v58);
  SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(v45);
}

```

## disassembly

```asm
0x1800096bc  mov     rax, rsp
0x1800096bf  mov     [rax+20h], r9
0x1800096c3  mov     [rax+18h], r8
0x1800096c7  mov     [rax+10h], rdx
0x1800096cb  mov     [rax+8], rcx
0x1800096cf  push    rbp
0x1800096d0  push    rbx
0x1800096d1  push    rsi
0x1800096d2  push    rdi
0x1800096d3  push    r12
0x1800096d5  push    r13
0x1800096d7  push    r14
0x1800096d9  push    r15
0x1800096db  lea     rbp, [rax-4Fh]
0x1800096df  sub     rsp, 0D8h
0x1800096e6  mov     rdi, r9
0x1800096e9  mov     rbx, r8
0x1800096ec  mov     rsi, rdx
0x1800096ef  mov     r12, rcx
0x1800096f2  lea     r15, WPP_GLOBAL_Control
0x1800096f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180009700  cmp     rcx, r15
0x180009703  jz      short loc_180009726
0x180009705  test    byte ptr [rcx+44h], 8
0x180009709  jz      short loc_180009726
0x18000970b  cmp     byte ptr [rcx+41h], 5
0x18000970f  jb      short loc_180009726
0x180009711  mov     edx, 57h ; 'W'
0x180009716  lea     r8, WPP_cfb9f38fb45937fd90037ddd4a0f05da_Traceguids
0x18000971d  mov     rcx, [rcx+38h]
0x180009721  call    WPP_SF_
0x180009726  lea     rcx, [rsp+110h+var_C8]; void *
0x18000972b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180009730  nop
0x180009731  xor     edx, edx
0x180009733  lea     rcx, [rbp+47h+var_B8]
0x180009737  call    ??0?$SmartPtr@VImportMetadata@@@@QEAA@PEAVImportMetadata@@@Z; SmartPtr<ImportMetadata>::SmartPtr<ImportMetadata>(ImportMetadata *)
0x18000973c  nop
0x18000973d  lea     r14, [rsi+228h]
0x180009744  mov     [rbp+47h+var_B0], r14
0x180009748  xor     r13d, r13d
0x18000974b  test    r14, r14
0x18000974e  jnz     loc_180009820
0x180009754  mov     rcx, cs:WPP_GLOBAL_Control
0x18000975b  cmp     rcx, r15
0x18000975e  jz      short loc_180009786
0x180009760  lea     edi, [r14+4]
0x180009764  test    [rcx+44h], dil
0x180009768  jz      short loc_180009786
0x18000976a  mov     r14b, 2
0x18000976d  cmp     [rcx+41h], r14b
0x180009771  jb      short loc_180009786
0x180009773  lea     edx, [rdi+54h]
0x180009776  lea     r8, WPP_cfb9f38fb45937fd90037ddd4a0f05da_Traceguids
0x18000977d  mov     rcx, [rcx+38h]
0x180009781  call    WPP_SF_
0x180009786  mov     ecx, 58h ; 'X'; unsigned __int64
0x18000978b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009790  mov     [rbp+47h+arg_8], rax
0x180009794  test    rax, rax
0x180009797  jz      short loc_1800097A8
0x180009799  mov     edx, 0C0AAB100h; int
0x18000979e  mov     rcx, rax; this
0x1800097a1  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x1800097a6  jmp     short loc_1800097AB
0x1800097a8  mov     rax, r13
0x1800097ab  mov     rdx, rax
0x1800097ae  lea     rcx, [rbp+47h+arg_8]
0x1800097b2  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x1800097b7  nop
0x1800097b8  mov     rbx, [rbp+47h+arg_8]
0x1800097bc  test    rbx, rbx
0x1800097bf  jz      short loc_1800097FF
0x1800097c1  cmp     [rbx], r13
0x1800097c4  jz      short loc_1800097FF
0x1800097c6  mov     r8d, 845h; int
0x1800097cc  lea     rdx, aDriversStorage_15; "drivers\\storage\\imapi2\\filesystemima"...
0x1800097d3  mov     rcx, [rbx]; this
0x1800097d6  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x1800097db  mov     [rsp+110h+pExceptionObject], rbx
0x1800097e0  test    rbx, rbx
0x1800097e3  jz      short loc_1800097ED
0x1800097e5  mov     esi, 1
0x1800097ea  add     [rbx+8], esi
0x1800097ed  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x1800097f4  lea     rcx, [rsp+110h+pExceptionObject]; pExceptionObject
0x1800097f9  call    _CxxThrowException_0
0x1800097ff  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x180009806  lea     rcx, [rbp+47h+var_A0]; this
0x18000980a  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18000980f  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x180009816  lea     rcx, [rbp+47h+var_A0]; pExceptionObject
0x18000981a  call    _CxxThrowException_0
0x180009820  mov     rax, [rbx]
0x180009823  mov     esi, 1
0x180009828  test    rax, rax
0x18000982b  jz      short loc_180009835
0x18000982d  mov     ebx, r13d
0x180009830  cmp     [rax], r13
0x180009833  jnz     short loc_180009865
0x180009835  mov     ebx, esi
0x180009837  mov     rax, [r12+30h]
0x18000983c  mov     rcx, [rax+38h]
0x180009840  mov     [rsp+110h+var_D8], rcx
0x180009845  test    rcx, rcx
0x180009848  jz      short loc_18000984D
0x18000984a  add     [rcx+8], esi
0x18000984d  lea     rdx, [rsp+110h+var_D8]
0x180009852  lea     rcx, [rbp+47h+var_B8]
0x180009856  call    ??4?$SmartPtr@VImportMetadata@@@@QEAAAEAV0@AEBV0@@Z; SmartPtr<ImportMetadata>::operator=(SmartPtr<ImportMetadata> const &)
0x18000985b  lea     rcx, [rsp+110h+var_D8]; void *
0x180009860  call    ??1?$SmartPtr@VVolumeRecognitionStructureBase@@@@QEAA@XZ; SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(void)
0x180009865  mov     edx, dword ptr [rbp+47h+arg_20]; unsigned int
0x180009868  mov     rcx, r14; this
0x18000986b  call    ?GetIcbEntry@ICB_INFO@@QEAAPEAUICB_ENTRY@@K@Z; ICB_INFO::GetIcbEntry(ulong)
0x180009870  mov     r15, rax
0x180009873  test    rax, rax
0x180009876  jnz     loc_180009949
0x18000987c  mov     rcx, cs:WPP_GLOBAL_Control
0x180009883  lea     rdx, WPP_GLOBAL_Control
0x18000988a  cmp     rcx, rdx
0x18000988d  jz      short loc_1800098B4
0x18000988f  lea     edi, [rax+4]
0x180009892  test    [rcx+44h], dil
0x180009896  jz      short loc_1800098B4
0x180009898  mov     r14b, 2
0x18000989b  cmp     [rcx+41h], r14b
0x18000989f  jb      short loc_1800098B4
0x1800098a1  lea     edx, [rax+59h]
0x1800098a4  lea     r8, WPP_cfb9f38fb45937fd90037ddd4a0f05da_Traceguids
0x1800098ab  mov     rcx, [rcx+38h]
0x1800098af  call    WPP_SF_
0x1800098b4  mov     ecx, 58h ; 'X'; unsigned __int64
0x1800098b9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800098be  mov     [rbp+47h+arg_8], rax
0x1800098c2  test    rax, rax
0x1800098c5  jz      short loc_1800098D6
0x1800098c7  mov     edx, 0C0AAB100h; int
0x1800098cc  mov     rcx, rax; this
0x1800098cf  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x1800098d4  jmp     short loc_1800098D9
0x1800098d6  mov     rax, r13
0x1800098d9  mov     rdx, rax
0x1800098dc  lea     rcx, [rbp+47h+arg_8]
0x1800098e0  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x1800098e5  nop
0x1800098e6  mov     rbx, [rbp+47h+arg_8]
0x1800098ea  test    rbx, rbx
0x1800098ed  jz      short loc_180009928
0x1800098ef  cmp     [rbx], r13
0x1800098f2  jz      short loc_180009928
0x1800098f4  mov     r8d, 857h; int
0x1800098fa  lea     rdx, aDriversStorage_15; "drivers\\storage\\imapi2\\filesystemima"...
0x180009901  mov     rcx, [rbx]; this
0x180009904  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x180009909  mov     [rsp+110h+pExceptionObject], rbx
0x18000990e  test    rbx, rbx
0x180009911  jz      short loc_180009916
0x180009913  add     [rbx+8], esi
0x180009916  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18000991d  lea     rcx, [rsp+110h+pExceptionObject]; pExceptionObject
0x180009922  call    _CxxThrowException_0
0x180009928  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18000992f  lea     rcx, [rbp+47h+var_A0]; this
0x180009933  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x180009938  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18000993f  lea     rcx, [rbp+47h+var_A0]; pExceptionObject
0x180009943  call    _CxxThrowException_0
0x180009949  mov     r13, [rax+28h]
0x18000994d  test    r13, r13
0x180009950  jnz     loc_180009A21
0x180009956  mov     rcx, cs:WPP_GLOBAL_Control
0x18000995d  lea     rdx, WPP_GLOBAL_Control
0x180009964  cmp     rcx, rdx
0x180009967  jz      short loc_18000998F
0x180009969  lea     edi, [r13+4]
0x18000996d  test    [rcx+44h], dil
0x180009971  jz      short loc_18000998F
0x180009973  mov     r14b, 2
0x180009976  cmp     [rcx+41h], r14b
0x18000997a  jb      short loc_18000998F
0x18000997c  lea     edx, [rdi+56h]
0x18000997f  lea     r8, WPP_cfb9f38fb45937fd90037ddd4a0f05da_Traceguids
0x180009986  mov     rcx, [rcx+38h]
0x18000998a  call    WPP_SF_
0x18000998f  mov     ecx, 58h ; 'X'; unsigned __int64
0x180009994  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009999  mov     [rbp+47h+arg_8], rax
0x18000999d  test    rax, rax
0x1800099a0  jz      short loc_1800099B0
0x1800099a2  mov     edx, 0C0AAB100h; int
0x1800099a7  mov     rcx, rax; this
0x1800099aa  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x1800099af  nop
0x1800099b0  mov     rdx, rax
0x1800099b3  lea     rcx, [rbp+47h+arg_8]
0x1800099b7  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x1800099bc  nop
0x1800099bd  mov     rbx, [rbp+47h+arg_8]
0x1800099c1  test    rbx, rbx
0x1800099c4  jz      short loc_180009A00
0x1800099c6  cmp     qword ptr [rbx], 0
0x1800099ca  jz      short loc_180009A00
0x1800099cc  mov     r8d, 861h; int
0x1800099d2  lea     rdx, aDriversStorage_15; "drivers\\storage\\imapi2\\filesystemima"...
0x1800099d9  mov     rcx, [rbx]; this
0x1800099dc  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x1800099e1  mov     [rsp+110h+pExceptionObject], rbx
0x1800099e6  test    rbx, rbx
0x1800099e9  jz      short loc_1800099EE
0x1800099eb  add     [rbx+8], esi
0x1800099ee  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x1800099f5  lea     rcx, [rsp+110h+pExceptionObject]; pExceptionObject
0x1800099fa  call    _CxxThrowException_0
0x180009a00  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x180009a07  lea     rcx, [rbp+47h+var_A0]; this
0x180009a0b  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x180009a10  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x180009a17  lea     rcx, [rbp+47h+var_A0]; pExceptionObject
0x180009a1b  call    _CxxThrowException_0
0x180009a21  test    ebx, ebx
0x180009a23  jnz     loc_180009B0D
0x180009a29  lea     r8, [rsp+110h+var_C8]
0x180009a2e  mov     rdx, rdi
0x180009a31  call    ?GetObjectName@UdfFileSystemSupport@@IEAA_NPEAUNSR_FID@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; UdfFileSystemSupport::GetObjectName(NSR_FID *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180009a36  test    al, al
0x180009a38  jnz     loc_180009B0D
0x180009a3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180009a45  lea     rdx, WPP_GLOBAL_Control
0x180009a4c  cmp     rcx, rdx
0x180009a4f  jz      short loc_180009A76
0x180009a51  lea     edi, [rbx+4]
0x180009a54  test    [rcx+44h], dil
0x180009a58  jz      short loc_180009A76
0x180009a5a  mov     r14b, 2
0x180009a5d  cmp     [rcx+41h], r14b
0x180009a61  jb      short loc_180009A76
0x180009a63  lea     edx, [rbx+5Bh]
0x180009a66  lea     r8, WPP_cfb9f38fb45937fd90037ddd4a0f05da_Traceguids
0x180009a6d  mov     rcx, [rcx+38h]
0x180009a71  call    WPP_SF_
0x180009a76  mov     ecx, 58h ; 'X'; unsigned __int64
0x180009a7b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009a80  mov     [rbp+47h+arg_8], rax
0x180009a84  test    rax, rax
0x180009a87  jz      short loc_180009A9C
0x180009a89  mov     r8, [r12+8]
0x180009a8e  mov     edx, 0C0AAB153h; int
0x180009a93  mov     rcx, rax; this
0x180009a96  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x180009a9b  nop
0x180009a9c  mov     rdx, rax
0x180009a9f  lea     rcx, [rbp+47h+arg_8]
0x180009aa3  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x180009aa8  nop
0x180009aa9  mov     rbx, [rbp+47h+arg_8]
0x180009aad  test    rbx, rbx
0x180009ab0  jz      short loc_180009AEC
0x180009ab2  cmp     qword ptr [rbx], 0
0x180009ab6  jz      short loc_180009AEC
0x180009ab8  mov     r8d, 86Ch; int
0x180009abe  lea     rdx, aDriversStorage_15; "drivers\\storage\\imapi2\\filesystemima"...
0x180009ac5  mov     rcx, [rbx]; this
0x180009ac8  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x180009acd  mov     [rsp+110h+pExceptionObject], rbx
0x180009ad2  test    rbx, rbx
0x180009ad5  jz      short loc_180009ADA
0x180009ad7  add     [rbx+8], esi
0x180009ada  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x180009ae1  lea     rcx, [rsp+110h+pExceptionObject]; pExceptionObject
0x180009ae6  call    _CxxThrowException_0
0x180009aec  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x180009af3  lea     rcx, [rbp+47h+var_A0]; this
0x180009af7  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x180009afc  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x180009b03  lea     rcx, [rbp+47h+var_A0]; pExceptionObject
0x180009b07  call    _CxxThrowException_0
0x180009b0d  mov     edi, 4
0x180009b12  mov     r14b, 2
0x180009b15  cmp     [r15+22h], r14b
0x180009b19  jnz     loc_18000A032
0x180009b1f  xor     r15d, r15d
0x180009b22  cmp     dword ptr [rbp+47h+arg_28], r15d
0x180009b26  jnz     loc_18000A032
0x180009b2c  mov     rax, [r13+10h]
0x180009b30  cmp     di, [rax+14h]
0x180009b34  jz      loc_180009C1D
0x180009b3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b41  lea     rdx, WPP_GLOBAL_Control
0x180009b48  cmp     rcx, rdx
0x180009b4b  jz      short loc_180009B83
0x180009b4d  test    [rcx+44h], dil
0x180009b51  jz      short loc_180009B83
0x180009b53  cmp     [rcx+41h], r14b
0x180009b57  jb      short loc_180009B83
0x180009b59  lea     r9, aRoot; "(root)"
0x180009b60  test    ebx, ebx
0x180009b62  cmovz   r9, [rsp+110h+var_C8]
0x180009b68  movzx   eax, word ptr [rax+14h]
0x180009b6c  lea     edx, [rdi+58h]
  ... truncated ...
```
