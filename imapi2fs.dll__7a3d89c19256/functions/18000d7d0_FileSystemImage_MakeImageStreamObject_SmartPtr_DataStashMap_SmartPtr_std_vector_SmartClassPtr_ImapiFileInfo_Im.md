# FileSystemImage::MakeImageStreamObject(SmartPtr<DataStashMap>,SmartPtr<std::vector<SmartClassPtr<ImapiFileInfo,ImapiImplementation>,std::allocator<SmartClassPtr<ImapiFileInfo,ImapiImplementation>>>>)

- ea: `0x18000d7d0`
- end: `0x18000e5d1`
- name: `?MakeImageStreamObject@FileSystemImage@@AEAA?AV?$SmartClassPtr@VCStreamROBase@@VImapiImplementation@@@@V?$SmartPtr@VDataStashMap@@@@V?$SmartPtr@V?$vector@V?$SmartClassPtr@VImapiFileInfo@@VImapiImplementation@@@@V?$allocator@V?$SmartClassPtr@VImapiFileInfo@@VImapiImplementation@@@@@std@@@std@@@@@Z`
- size: `3585`
- prototype: ``
- caller_count: `1`
- callee_count: `49`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180043c04`

## callees

- `0x180003580`
- `0x180003a20`
- `0x180004c70`
- `0x180005040`
- `0x1800051a0`
- `0x180005568`
- `0x1800063b8`
- `0x18000726c`
- `0x18000960c`
- `0x18000c888`
- `0x18000c8d0`
- `0x18000d1c0`
- `0x18000d7d0`
- `0x18000e5d8`
- `0x18000f4b0`
- `0x18000f4cc`
- `0x18000f58c`
- `0x18000f5b4`
- `0x18000f5d0`
- `0x18000f5ec`
- `0x1800180e8`
- `0x1800187ac`
- `0x18001f27c`
- `0x18002502c`
- `0x1800251dc`
- `0x1800251f6`
- `0x180028568`
- `0x18002b0e4`
- `0x18002d4e4`
- `0x18002dba4`
- `0x18002dc70`
- `0x18002f6a4`
- `0x180030d18`
- `0x180030d88`
- `0x18003239c`
- `0x180032754`
- `0x180041eac`
- `0x1800426fc`
- `0x1800427b4`
- `0x180042b18`
- `0x180049eec`
- `0x18004a0a8`
- `0x18004d438`
- `0x18004f8bc`
- `0x18005b04c`
- `0x18005b16c`
- `0x18005c2c8`
- `0x1800816e6`
- `0x180088010`

## import_xrefs

- `ole32!CreateStreamOnHGlobal` at `0x18000ddb6`
- `ole32!CreateStreamOnHGlobal` at `0x18000ddb6`
- `KERNEL32!GlobalFree` at `0x18000ddc9`
- `KERNEL32!GlobalFree` at `0x18000ddc9`
- `KERNEL32!GlobalAlloc` at `0x18000dcb3`
- `KERNEL32!GlobalAlloc` at `0x18000dcb3`

## pseudocode

```c
// Hidden C++ exception states: #wind=25
struct _FILETIME ***__fastcall FileSystemImage::MakeImageStreamObject(
        CIMAPIException **a1,
        struct _FILETIME ***a2,
        DataStashMap **a3,
        _QWORD **a4)
{
  _QWORD **v4; // r14
  CIMAPIException **v5; // rsi
  int v6; // r15d
  unsigned int v7; // r12d
  CIMAPIException *v8; // rax
  bool v9; // bl
  CIMAPIException *v10; // rcx
  char v11; // bl
  __int64 v12; // rax
  bool v13; // cf
  unsigned __int64 v14; // rax
  _QWORD *v15; // rax
  _QWORD *v16; // rbx
  unsigned int v17; // r13d
  DataStashMap *v18; // rcx
  char v19; // bl
  CIMAPIException **v20; // rdi
  DataStashMap *v21; // rax
  DataStashMap *v22; // rax
  DataStashMap *v23; // rax
  IStream *v24; // rax
  IStream *v25; // rbx
  __int64 v26; // rcx
  StashFileDescr *v27; // rax
  StashFileDescr *v28; // r9
  __int64 v29; // rax
  CIMAPIException *v30; // rax
  __int64 Stream; // rax
  CIMAPIException *v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  unsigned int v35; // ebx
  HGLOBAL v36; // r14
  CIMAPIException *v37; // rax
  CIMAPIException *v38; // rax
  CIMAPIException **v39; // rbx
  const void *v40; // rdx
  HRESULT v41; // ebx
  CIMAPIException *v42; // rax
  CIMAPIException *v43; // rax
  CIMAPIException **v44; // rbx
  CStreamEmbeddedIStreamRO *v45; // rbx
  __int64 v46; // rax
  CIMAPIException *v47; // rax
  __int64 v48; // rax
  CIMAPIException *v49; // rax
  __int64 v50; // rax
  StashFileDescr *v51; // rax
  StashFileDescr *v52; // rbx
  DataStashMap *v53; // rcx
  __int64 v54; // rbx
  StashFileDescr *v55; // rax
  StashFileDescr *v56; // r9
  DataStashMap *v57; // rcx
  __int64 v58; // rax
  signed int v59; // r13d
  _QWORD *v60; // rcx
  int v61; // r12d
  __int64 v62; // rdx
  _QWORD **v63; // rsi
  IStream *v64; // rbx
  CStreamEmbeddedIStreamRO *v65; // rax
  CStreamEmbeddedIStreamRO *v66; // r14
  __int64 v67; // rcx
  CIMAPIException *v68; // rax
  bool v69; // bl
  StashFileDescr *v70; // rax
  StashFileDescr *v71; // rbx
  CIMAPIException *v72; // rax
  __int64 v73; // rcx
  CStreamEmbeddedIStreamRO *v74; // rax
  __int64 v75; // rax
  _QWORD *v76; // rax
  struct _FILETIME **v77; // rbx
  struct _FILETIME *v78; // r12
  int *v79; // rcx
  int *v80; // r14
  __int64 v81; // rdi
  CIMAPIException **v82; // rcx
  char v83; // di
  unsigned int v84; // r15d
  __int64 v85; // rcx
  CIMAPIException **v86; // r14
  unsigned int v87; // ecx
  int v88; // r8d
  ImapiBlockRangeList **v89; // rdi
  struct _FILETIME ***v90; // rdi
  DataStashMap *pExceptionObject; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v93; // [rsp+40h] [rbp-C8h] BYREF
  IStream *v94; // [rsp+48h] [rbp-C0h] BYREF
  CStreamEmbeddedIStreamRO *v95; // [rsp+50h] [rbp-B8h]
  LPSTREAM ppstm; // [rsp+58h] [rbp-B0h] BYREF
  int v97; // [rsp+60h] [rbp-A8h]
  int v98; // [rsp+64h] [rbp-A4h]
  CIMAPIException **v99; // [rsp+68h] [rbp-A0h] BYREF
  ImapiBlockRangeList **v100; // [rsp+70h] [rbp-98h] BYREF
  IStream *v101; // [rsp+78h] [rbp-90h] BYREF
  struct _FILETIME **v102; // [rsp+80h] [rbp-88h] BYREF
  const void **v103; // [rsp+88h] [rbp-80h] BYREF
  int v104; // [rsp+90h] [rbp-78h]
  int v105; // [rsp+94h] [rbp-74h]
  unsigned int v106; // [rsp+98h] [rbp-70h]
  char v107[8]; // [rsp+A0h] [rbp-68h] BYREF
  SIZE_T dwBytes; // [rsp+A8h] [rbp-60h]
  _BYTE v109[160]; // [rsp+B8h] [rbp-50h] BYREF
  CIMAPIException **v110; // [rsp+168h] [rbp+60h] BYREF
  struct _FILETIME ***v111; // [rsp+170h] [rbp+68h]
  DataStashMap **v112; // [rsp+178h] [rbp+70h]
  _QWORD **v113; // [rsp+180h] [rbp+78h]

  v113 = a4;
  v112 = a3;
  v111 = a2;
  v110 = a1;
  v4 = a4;
  v5 = a1;
  v6 = 0;
  v98 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 52, &WPP_a4ce3c455c623a57c7cb4594e9846ff6_Traceguids);
  }
  SmartPtr<ImportMetadata>::SmartPtr<ImportMetadata>(&v102, 0);
  SmartPtr<ImportMetadata>::SmartPtr<ImportMetadata>(&v100, 0);
  v7 = ((__int64)(*(_QWORD *)(**v4 + 8LL) - *(_QWORD *)**v4) >> 3) + 2;
  v97 = v7;
  v8 = v5[89];
  v99 = (CIMAPIException **)v8;
  v9 = 0;
  if ( v8 )
  {
    ++*((_DWORD *)v8 + 2);
    if ( *(_QWORD *)v8 )
      v9 = 1;
  }
  SmartPtr<CFsiStashFile>::~SmartPtr<CFsiStashFile>(&v99);
  if ( v9 )
    v97 = ++v7;
  if ( *((_BYTE *)v5 + 792) )
  {
    v10 = v5[98];
    v99 = (CIMAPIException **)v10;
    if ( v10 )
      ++*((_DWORD *)v10 + 2);
    v11 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v10 + 56LL))(*(_QWORD *)v10);
    SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&v99);
    if ( v11 )
    {
      v7 += 4;
      v97 = v7;
      if ( ((_BYTE)v5[3] & 4) != 0 )
      {
        v7 += 2;
        v97 = v7;
      }
    }
  }
  v12 = 8LL * (int)v7;
  if ( !is_mul_ok((int)v7, 8u) )
    v12 = -1;
  v13 = __CFADD__(v12, 8);
  v14 = v12 + 8;
  if ( v13 )
    v14 = -1;
  v15 = operator new(v14);
  v99 = (CIMAPIException **)v15;
  if ( v15 )
  {
    *v15 = (int)v7;
    v16 = v15 + 1;
    `eh vector constructor iterator'(
      v15 + 1,
      8u,
      (int)v7,
      SmartClassPtr<CStreamROBase,ImapiImplementation>::`default constructor closure',
      SmartClassPtr<RollbackBase,RollbackBase>::~SmartClassPtr<RollbackBase,RollbackBase>);
  }
  else
  {
    v16 = 0;
  }
  SmartArrayPtr<SmartClassPtr<ImapiDirectoryInfo,ImapiImplementation>>::SmartArrayPtr<SmartClassPtr<ImapiDirectoryInfo,ImapiImplementation>>(
    &v99,
    v16);
  v17 = 0;
  *(CIMAPIException **)((char *)v5 + 620) = (CIMAPIException *)-1LL;
  if ( !*((_BYTE *)v5 + 792) )
    goto LABEL_29;
  v18 = v5[98];
  pExceptionObject = v18;
  if ( v18 )
    ++*((_DWORD *)v18 + 2);
  v6 = 1;
  v98 = 1;
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(**(_QWORD **)v18 + 56LL))(*(_QWORD *)v18) )
    v19 = 1;
  else
LABEL_29:
    v19 = 0;
  if ( (v6 & 1) != 0 )
  {
    v6 &= ~1u;
    v98 = v6;
    SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&pExceptionObject);
  }
  v20 = v99;
  if ( v19 )
  {
    SmartPtr<DataStashMap>::SmartPtr<DataStashMap>(&v94, 0);
    SmartArrayPtr<unsigned char>::SmartArrayPtr<unsigned char>(&v101, 0);
    *((_DWORD *)v5 + 155) = 20;
    v17 = 3;
    if ( FileSystemSupport::include(v5[81]) )
      *((_DWORD *)v5 + 155) += 3;
    v21 = (DataStashMap *)operator new(0x18u);
    pExceptionObject = v21;
    if ( v21 )
      v22 = DataStashMap::DataStashMap(v21);
    else
      v22 = 0;
    SmartPtr<DataStashMap>::operator=(&v94, v22);
    v23 = (DataStashMap *)operator new(0x18u);
    pExceptionObject = v23;
    if ( v23 )
    {
      *(_QWORD *)v23 = 0;
      *((_DWORD *)v23 + 2) = 0;
      *((_QWORD *)v23 + 2) = 0;
    }
    else
    {
      v23 = 0;
    }
    SmartPtr<DataStashMapEntry>::operator=(&v101, v23);
    v24 = v101;
    **(_DWORD **)v101 = 0;
    *(_DWORD *)(*(_QWORD *)v24 + 8LL) = 0;
    *(_DWORD *)(*(_QWORD *)v24 + 4LL) = *((_DWORD *)v5 + 155);
    *(_QWORD *)(*(_QWORD *)v24 + 16LL) = (unsigned __int64)*(unsigned int *)(*(_QWORD *)v24 + 4LL) << 11;
    v25 = v94;
    v26 = *(_QWORD *)v94;
    ppstm = v24;
    if ( v24 )
      ++*((_DWORD *)v24 + 2);
    DataStashMap::Add(v26, &ppstm);
    v27 = (StashFileDescr *)operator new(0x78u);
    v28 = v27;
    pExceptionObject = v27;
    if ( v27 )
    {
      ppstm = v25;
      if ( v25 )
        ++*((_DWORD *)v25 + 2);
      v29 = **(_QWORD **)v5[88];
      v93 = v29;
      if ( v29 )
        ++*(_DWORD *)(v29 + 8);
      v27 = (StashFileDescr *)StashFileDescr::StashFileDescr(v28);
    }
    SmartPtr<ImportMetadata>::SmartPtr<ImportMetadata>(&pExceptionObject, v27);
    SmartPtr<ImportMetadata>::operator=(*v20, &pExceptionObject);
    SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&pExceptionObject);
    v30 = v5[98];
    pExceptionObject = v30;
    if ( v30 )
      ++*((_DWORD *)v30 + 2);
    Stream = GetStream(&pExceptionObject);
    SmartPtr<ImportMetadata>::SmartPtr<ImportMetadata>(&v93, Stream);
    SmartPtr<ImportMetadata>::operator=((char *)*v20 + 8, &v93);
    SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&v93);
    FileSystemSupport::include(v5[81]);
    v32 = v5[98];
    pExceptionObject = v32;
    if ( v32 )
      ++*((_DWORD *)v32 + 2);
    v33 = GetStream(&pExceptionObject);
    SmartPtr<ImportMetadata>::SmartPtr<ImportMetadata>(&v93, v33);
    SmartPtr<ImportMetadata>::operator=((char *)*v20 + 16, &v93);
    SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&v93);
    if ( FileSystemSupport::include(v5[81]) )
    {
      BufferDescr::BufferDescr((BufferDescr *)&v103);
      ppstm = 0;
      v34 = _RTDynamicCast_0(
              v5[81],
              0,
              &FileSystemSupport `RTTI Type Descriptor',
              &UdfFileSystemSupport `RTTI Type Descriptor',
              0);
      BufferDescr::BufferDescr((BufferDescr *)v107, (const struct BufferDescr *)(v34 + 128));
      SmartArrayPtr<unsigned char>::operator=(&v103, v107);
      v35 = dwBytes;
      v104 = dwBytes;
      SmartArrayPtr<unsigned char>::~SmartArrayPtr<unsigned char>(v107);
      v105 = 0;
      v106 = v35;
      v36 = GlobalAlloc(0x40u, v35);
      if ( !v36 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 53, &WPP_a4ce3c455c623a57c7cb4594e9846ff6_Traceguids);
        }
        v37 = (CIMAPIException *)operator new(0x58u);
        v110 = (CIMAPIException **)v37;
        if ( v37 )
          v38 = CIMAPIException::CIMAPIException(v37, -2147024882);
        else
          v38 = 0;
        SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v110, v38);
        v39 = v110;
        if ( v110 && *v110 )
        {
          CIMAPIException::SetCodeRefInfo(*v110, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsifsi.cpp", 1750);
          pExceptionObject = (DataStashMap *)v39;
          if ( v39 )
            ++*((_DWORD *)v39 + 2);
          throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
        }
        CIMAPIException::CIMAPIException(
          (CIMAPIException *)v109,
          (const struct CIMAPIException *)&CIMAPIException::badAlloc);
        throw (CIMAPIException *)v109;
      }
      if ( v103 )
        v40 = *v103;
      else
        v40 = 0;
      memcpy_0(v36, v40, v35);
      v41 = CreateStreamOnHGlobal(v36, 1, &ppstm);
      if ( v41 < 0 )
      {
        GlobalFree(v36);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 54, &WPP_a4ce3c455c623a57c7cb4594e9846ff6_Traceguids);
        }
        v42 = (CIMAPIException *)operator new(0x58u);
        v110 = (CIMAPIException **)v42;
        if ( v42 )
          v43 = CIMAPIException::CIMAPIException(v42, v41);
        else
          v43 = 0;
        SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v110, v43);
        v44 = v110;
        if ( v110 && *v110 )
        {
          CIMAPIException::SetCodeRefInfo(*v110, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsifsi.cpp", 1764);
          pExceptionObject = (DataStashMap *)v44;
          if ( v44 )
            ++*((_DWORD *)v44 + 2);
          throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
        }
        CIMAPIException::CIMAPIException(
          (CIMAPIException *)v109,
          (const struct CIMAPIException *)&CIMAPIException::badAlloc);
        throw (CIMAPIException *)v109;
      }
      v45 = (CStreamEmbeddedIStreamRO *)operator new(0x58u);
      v95 = v45;
      if ( v45 )
      {
        ATL::CComPtrBase<IStream>::CComPtrBase<IStream>(&pExceptionObject, ppstm);
        v46 = CStreamEmbeddedIStreamRO::CStreamEmbeddedIStreamRO(v45);
      }
      else
      {
        v46 = 0;
      }
      SmartPtr<ImportMetadata>::SmartPtr<ImportMetadata>(&v93, v46);
      SmartPtr<ImportMetadata>::operator=((char *)*v20 + 24, &v93);
      SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&v93);
      *((_DWORD *)v5 + 156) = 1;
      v47 = v5[98];
      pExceptionObject = v47;
      if ( v47 )
        ++*((_DWORD *)v47 + 2);
      v48 = GetStream(&pExceptionObject);
      SmartPtr<ImportMetadata>::SmartPtr<ImportMetadata>(&v93, v48);
      SmartPtr<ImportMetadata>::operator=((char *)*v20 + 32, &v93);
      SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&v93);
      v49 = v5[98];
      pExceptionObject = v49;
      if ( v49 )
        ++*((_DWORD *)v49 + 2);
      v50 = GetStream(&pExceptionObject);
      SmartPtr<ImportMetadata>::SmartPtr<ImportMetadata>(&v93, v50);
      v17 = 6;
      SmartPtr<ImportMetadata>::operator=((char *)*v20 + 40, &v93);
      SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&v93);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppstm);
      SmartArrayPtr<unsigned char>::~SmartArrayPtr<unsigned char>(&v103);
    }
    SmartArrayPtr<unsigned char>::~SmartArrayPtr<unsigned char>(&v101);
    SmartPtr<DataStashMap>::~SmartPtr<DataStashMap>(&v94);
    v4 = v113;
  }
  v51 = (StashFileDescr *)operator new(0x78u);
  v52 = v51;
  v95 = v51;
  if ( v51 )
  {
    SmartPtr<DataStashMap>::SmartPtr<DataStashMap>(&v94, 0);
    v53 = **(DataStashMap ***)v5[88];
    pExceptionObject = v53;
    if ( v53 )
      ++*((_DWORD *)v53 + 2);
    v51 = (StashFileDescr *)StashFileDescr::StashFileDescr(v52);
  }
  SmartPtr<ImportMetadata>::SmartPtr<ImportMetadata>(&v93, v51);
  v54 = v17 + 1;
  SmartPtr<ImportMetadata>::operator=((char *)*v20 + 8 * v17, &v93);
  SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&v93);
  v55 = (StashFileDescr *)operator new(0x78u);
  v56 = v55;
  v95 = v55;
  if ( v55 )
  {
    v57 = *v112;
    pExceptionObject = v57;
    if ( v57 )
      ++*((_DWORD *)v57 + 2);
    v58 = **(_QWORD **)v5[85];
    v93 = v58;
    if ( v58 )
      ++*(_DWORD *)(v58 + 8);
    v55 = (StashFileDescr *)StashFileDescr::StashFileDescr(v56);
  }
  SmartPtr<ImportMetadata>::SmartPtr<ImportMetadata>(&v94, v55);
  v59 = v17 + 2;
  SmartPtr<ImportMetadata>::operator=((char *)*v20 + 8 * v54, &v94);
  SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&v94);
  v60 = (_QWORD *)**v4;
  if ( (__int64)(v60[1] - *v60) >> 3 )
  {
    v61 = 0;
    v62 = 0;
    v63 = v113;
    do
    {
      v64 = *(IStream **)std::vector<SmartClassPtr<ImapiFileInfo,ImapiImplementation>>::at(v60, v62);
      v94 = v64;
      if ( v64 )
        ++*((_DWORD *)v64 + 2);
      v65 = (CStreamEmbeddedIStreamRO *)operator new(0x58u);
      v66 = v65;
      v95 = v65;
      if ( v65 )
      {
        ATL::CComPtrBase<IStream>::CComPtrBase<IStream>(&pExceptionObject, *(_QWORD *)(*(_QWORD *)v64 + 264LL));
        v65 = (CStreamEmbeddedIStreamRO *)CStreamEmbeddedIStreamRO::CStreamEmbeddedIStreamRO(v66);
      }
      SmartPtr<ImportMetadata>::SmartPtr<ImportMetadata>(&v93, v65);
      v67 = (__int64)*v20 + 8 * v59++;
      SmartPtr<ImportMetadata>::operator=(v67, &v93);
      SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&v93);
      SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&v94);
      ++v61;
      v60 = (_QWORD *)**v63;
      v62 = v61;
    }
    while ( v61 < (unsigned __int64)((__int64)(v60[1] - *v60) >> 3) );
    v5 = v110;
    v7 = v97;
  }
  v68 = v5[89];
  v110 = (CIMAPIException **)v68;
  v69 = 0;
  if ( v68 )
  {
    ++*((_DWORD *)v68 + 2);
    if ( *(_QWORD *)v68 )
      v69 = 1;
  }
  SmartPtr<CFsiStashFile>::~SmartPtr<CFsiStashFile>(&v110);
  if ( v69 )
  {
    v70 = (StashFileDescr *)operator new(0x78u);
    v71 = v70;
    v95 = v70;
    if ( v70 )
    {
      SmartPtr<DataStashMap>::SmartPtr<DataStashMap>(&v93, 0);
      v72 = v5[89];
      v94 = v72;
      if ( v72 )
        ++*((_DWORD *)v72 + 2);
      v6 |= 2u;
      v98 = v6;
      v73 = **(_QWORD **)v72;
      v110 = (CIMAPIException **)v73;
      if ( v73 )
        ++*(_DWORD *)(v73 + 8);
      v70 = (StashFileDescr *)StashFileDescr::StashFileDescr(v71);
    }
    SmartPtr<ImportMetadata>::SmartPtr<ImportMetadata>(&pExceptionObject, v70);
    SmartPtr<ImportMetadata>::operator=((char *)*v20 + 8 * v59, &pExceptionObject);
    SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&pExceptionObject);
    if ( (v6 & 2) != 0 )
    {
      v6 &= ~2u;
      SmartPtr<CFsiStashFile>::~SmartPtr<CFsiStashFile>(&v94);
    }
  }
  v74 = (CStreamEmbeddedIStreamRO *)operator new(0x58u);
  v95 = v74;
  if ( v74 )
  {
    v110 = v20;
    if ( v20 )
      ++*((_DWORD *)v20 + 2);
    v75 = CStreamMultiStreamRO::CStreamMultiStreamRO(v74, v7, &v110);
  }
  else
  {
    v75 = 0;
  }
  SmartPtr<ImportMetadata>::SmartPtr<ImportMetadata>(&pExceptionObject, v75);
  SmartPtr<ImportMetadata>::operator=(&v102, &pExceptionObject);
  SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&pExceptionObject);
  v76 = (_QWORD *)FileSystemImage::VolumeName(v5, &v110);
  v77 = v102;
  v78 = *v102;
  v79 = (int *)(*v76 - 24LL);
  v80 = (int *)(*(_QWORD *)&(*v102)[3] - 24LL);
  if ( v79 != v80 )
  {
    if ( v80[4] >= 0 && *(_QWORD *)v79 == *(_QWORD *)v80 )
    {
      v81 = ATL::CSimpleStringT<unsigned short,0>::CloneData();
      ATL::CStringData::Release((ATL::CStringData *)v80);
      v78[3] = (struct _FILETIME)(v81 + 24);
    }
    else
    {
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v78[3], *v76, *(unsigned int *)(*v76 - 16LL));
    }
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v110);
  (*v77)[4] = Utility::DATEToFileTime((struct ATL::COleDateTime *)(v5 + 44));
  (*v77)[5] = Utility::DATEToFileTime((struct ATL::COleDateTime *)(v5 + 44));
  (*v77)[6] = Utility::DATEToFileTime((struct ATL::COleDateTime *)(v5 + 44));
  if ( !*((_BYTE *)v5 + 792) )
    goto LABEL_139;
  v82 = (CIMAPIException **)v5[98];
  v110 = v82;
  if ( v82 )
    ++*((_DWORD *)v82 + 2);
  v6 |= 4u;
  v98 = v6;
  v83 = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(CIMAPIException *))(*(_QWORD *)*v82 + 56LL))(*v82) )
LABEL_139:
    v83 = 0;
  if ( (v6 & 4) != 0 )
    SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&v110);
  if ( v83 )
  {
    v84 = Utility::BytesToRequiredSectors(*(_QWORD *)&(*v77)[2]);
    v86 = (CIMAPIException **)operator new(0x18u);
    v110 = v86;
    if ( v86 )
    {
      *v86 = (CIMAPIException *)&ImapiBlockRangeList::`vftable';
      v86[1] = 0;
      v86[2] = 0;
      v86[1] = (CIMAPIException *)std::_List_alloc<0,std::_List_base_types<SmartClassPtr<ImapiBlockRange,ImapiImplementation>>>::_Buynode0(
                                    v85,
                                    0,
                                    0);
      std::list<SmartClassPtr<ImapiBlockRange,ImapiImplementation>>::clear(v86 + 1);
    }
    else
    {
      v86 = 0;
    }
    SmartPtr<ImportMetadata>::SmartPtr<ImportMetadata>(&v110, v86);
    SmartPtr<ImportMetadata>::operator=(&v100, &v110);
    SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&v110);
    v87 = *((_DWORD *)v5 + 99);
    if ( *((_DWORD *)v5 + 155) % v87 )
      *((_DWORD *)v5 + 155) += v87 - (v87 + *((_DWORD *)v5 + 155)) % v87;
    v88 = *((_DWORD *)v5 + 156);
    if ( (v88 + 256) % v87 )
      *((_DWORD *)v5 + 156) = v87 + v88 - (v88 + v87 + 256) % v87;
    v89 = v100;
    ImapiBlockRangeList::AddBlockRange(*v100, *((_DWORD *)v5 + 152), v84 - 1);
    ImapiBlockRangeList::AddBlockRange(*v89, 0, *((_DWORD *)v5 + 155) - 1);
    if ( FileSystemSupport::include(v5[81]) )
      ImapiBlockRangeList::AddBlockRange(*v89, 256, *((_DWORD *)v5 + 156) + 255);
  }
  SmartPtr<ImportMetadata>::operator=(&(*v77)[7], &v100);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 55, &WPP_a4ce3c455c623a57c7cb4594e9846ff6_Traceguids);
  }
  v90 = v111;
  *v111 = v77;
  if ( v77 )
    ++*((_DWORD *)v77 + 2);
  SmartArrayPtr<SmartClassPtr<CStreamROBase,ImapiImplementation>>::~SmartArrayPtr<SmartClassPtr<CStreamROBase,ImapiImplementation>>(&v99);
  SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&v100);
  SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&v102);
  SmartPtr<DataStashMap>::~SmartPtr<DataStashMap>(v112);
  SmartPtr<std::vector<SmartClassPtr<ImapiFileInfo,ImapiImplementation>>>::~SmartPtr<std::vector<SmartClassPtr<ImapiFileInfo,ImapiImplementation>>>(v113);
  return v90;
}

```

## disassembly

```asm
0x18000d7d0  mov     rax, rsp
0x18000d7d3  mov     [rax+20h], r9
0x18000d7d7  mov     [rax+18h], r8
0x18000d7db  mov     [rax+10h], rdx
0x18000d7df  mov     [rax+8], rcx
0x18000d7e3  push    rbp
0x18000d7e4  push    rbx
0x18000d7e5  push    rsi
0x18000d7e6  push    rdi
0x18000d7e7  push    r12
0x18000d7e9  push    r13
0x18000d7eb  push    r14
0x18000d7ed  push    r15
0x18000d7ef  lea     rbp, [rax-58h]
0x18000d7f3  sub     rsp, 118h
0x18000d7fa  mov     r14, r9
0x18000d7fd  mov     rsi, rcx
0x18000d800  xor     r15d, r15d
0x18000d803  mov     dword ptr [rsp+150h+var_F8+4], r15d
0x18000d808  lea     rax, WPP_GLOBAL_Control
0x18000d80f  lea     r13d, [r15+8]
0x18000d813  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d81a  cmp     rcx, rax
0x18000d81d  jz      short loc_18000D83F
0x18000d81f  test    [rcx+44h], r13b
0x18000d823  jz      short loc_18000D83F
0x18000d825  cmp     byte ptr [rcx+41h], 5
0x18000d829  jb      short loc_18000D83F
0x18000d82b  lea     edx, [r15+34h]
0x18000d82f  lea     r8, WPP_a4ce3c455c623a57c7cb4594e9846ff6_Traceguids
0x18000d836  mov     rcx, [rcx+38h]
0x18000d83a  call    WPP_SF_
0x18000d83f  xor     edx, edx
0x18000d841  lea     rcx, [rsp+150h+var_D8]
0x18000d846  call    ??0?$SmartPtr@VImportMetadata@@@@QEAA@PEAVImportMetadata@@@Z; SmartPtr<ImportMetadata>::SmartPtr<ImportMetadata>(ImportMetadata *)
0x18000d84b  nop
0x18000d84c  xor     edx, edx
0x18000d84e  lea     rcx, [rsp+150h+var_E8]
0x18000d853  call    ??0?$SmartPtr@VImportMetadata@@@@QEAA@PEAVImportMetadata@@@Z; SmartPtr<ImportMetadata>::SmartPtr<ImportMetadata>(ImportMetadata *)
0x18000d858  nop
0x18000d859  mov     rax, [r14]
0x18000d85c  mov     rcx, [rax]
0x18000d85f  mov     r12, [rcx+8]
0x18000d863  sub     r12, [rcx]
0x18000d866  sar     r12, 3
0x18000d86a  add     r12d, 2
0x18000d86e  mov     dword ptr [rsp+150h+var_F8], r12d
0x18000d873  mov     rax, [rsi+2C8h]
0x18000d87a  mov     [rsp+150h+var_F0], rax
0x18000d87f  test    rax, rax
0x18000d882  jz      short loc_18000D891
0x18000d884  inc     dword ptr [rax+8]
0x18000d887  cmp     qword ptr [rax], 0
0x18000d88b  jz      short loc_18000D891
0x18000d88d  mov     bl, 1
0x18000d88f  jmp     short loc_18000D893
0x18000d891  xor     bl, bl
0x18000d893  lea     rcx, [rsp+150h+var_F0]
0x18000d898  call    ??1?$SmartPtr@VCFsiStashFile@@@@QEAA@XZ; SmartPtr<CFsiStashFile>::~SmartPtr<CFsiStashFile>(void)
0x18000d89d  test    bl, bl
0x18000d89f  jz      short loc_18000D8A9
0x18000d8a1  inc     r12d
0x18000d8a4  mov     dword ptr [rsp+150h+var_F8], r12d
0x18000d8a9  cmp     byte ptr [rsi+318h], 0
0x18000d8b0  jz      short loc_18000D8FD
0x18000d8b2  mov     rcx, [rsi+310h]
0x18000d8b9  mov     [rsp+150h+var_F0], rcx
0x18000d8be  test    rcx, rcx
0x18000d8c1  jz      short loc_18000D8C6
0x18000d8c3  inc     dword ptr [rcx+8]
0x18000d8c6  mov     rcx, [rcx]
0x18000d8c9  mov     rax, [rcx]
0x18000d8cc  mov     rax, [rax+38h]
0x18000d8d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8d5  mov     bl, al
0x18000d8d7  lea     rcx, [rsp+150h+var_F0]; void *
0x18000d8dc  call    ??1?$SmartPtr@VVolumeRecognitionStructureBase@@@@QEAA@XZ; SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(void)
0x18000d8e1  test    bl, bl
0x18000d8e3  jz      short loc_18000D8FD
0x18000d8e5  add     r12d, 4
0x18000d8e9  mov     dword ptr [rsp+150h+var_F8], r12d
0x18000d8ee  test    byte ptr [rsi+18h], 4
0x18000d8f2  jz      short loc_18000D8FD
0x18000d8f4  add     r12d, 2
0x18000d8f8  mov     dword ptr [rsp+150h+var_F8], r12d
0x18000d8fd  movsxd  rdi, r12d
0x18000d900  mov     rax, r13
0x18000d903  mul     rdi
0x18000d906  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000d90d  cmovb   rax, rcx
0x18000d911  add     rax, r13
0x18000d914  cmovb   rax, rcx
0x18000d918  mov     rcx, rax; unsigned __int64
0x18000d91b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d920  mov     [rsp+150h+var_F0], rax
0x18000d925  test    rax, rax
0x18000d928  jz      short loc_18000D954
0x18000d92a  mov     [rax], rdi
0x18000d92d  lea     rbx, [rax+8]
0x18000d931  lea     rax, ??1?$SmartClassPtr@VRollbackBase@@V1@@@QEAA@XZ; SmartClassPtr<RollbackBase,RollbackBase>::~SmartClassPtr<RollbackBase,RollbackBase>(void)
0x18000d938  mov     [rsp+20h], rax; void (*)(void *)
0x18000d93d  lea     r9, ??_F?$SmartClassPtr@VCStreamROBase@@VImapiImplementation@@@@QEAAXXZ; void (*)(void *)
0x18000d944  mov     r8, rdi; unsigned __int64
0x18000d947  mov     rdx, r13; unsigned __int64
0x18000d94a  mov     rcx, rbx; void *
0x18000d94d  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18000d952  jmp     short loc_18000D956
0x18000d954  xor     ebx, ebx
0x18000d956  mov     rdx, rbx
0x18000d959  lea     rcx, [rsp+150h+var_F0]
0x18000d95e  call    ??0?$SmartArrayPtr@V?$SmartClassPtr@VImapiDirectoryInfo@@VImapiImplementation@@@@@@QEAA@PEAV?$SmartClassPtr@VImapiDirectoryInfo@@VImapiImplementation@@@@@Z; SmartArrayPtr<SmartClassPtr<ImapiDirectoryInfo,ImapiImplementation>>::SmartArrayPtr<SmartClassPtr<ImapiDirectoryInfo,ImapiImplementation>>(SmartClassPtr<ImapiDirectoryInfo,ImapiImplementation> *)
0x18000d963  nop
0x18000d964  xor     r13d, r13d
0x18000d967  mov     qword ptr [rsi+26Ch], 0FFFFFFFFFFFFFFFFh
0x18000d972  cmp     [rsi+318h], r13b
0x18000d979  jz      short loc_18000D9B2
0x18000d97b  mov     rcx, [rsi+310h]
0x18000d982  mov     [rsp+150h+pExceptionObject], rcx
0x18000d987  test    rcx, rcx
0x18000d98a  jz      short loc_18000D98F
0x18000d98c  inc     dword ptr [rcx+8]
0x18000d98f  mov     r15d, 1
0x18000d995  mov     dword ptr [rsp+150h+var_F8+4], r15d
0x18000d99a  mov     rcx, [rcx]
0x18000d99d  mov     rax, [rcx]
0x18000d9a0  mov     rax, [rax+38h]
0x18000d9a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d9a9  test    al, al
0x18000d9ab  jz      short loc_18000D9B2
0x18000d9ad  mov     bl, r15b
0x18000d9b0  jmp     short loc_18000D9B4
0x18000d9b2  xor     bl, bl
0x18000d9b4  test    r15b, 1
0x18000d9b8  jz      short loc_18000D9CD
0x18000d9ba  and     r15d, 0FFFFFFFEh
0x18000d9be  mov     dword ptr [rsp+150h+var_F8+4], r15d
0x18000d9c3  lea     rcx, [rsp+150h+pExceptionObject]; void *
0x18000d9c8  call    ??1?$SmartPtr@VVolumeRecognitionStructureBase@@@@QEAA@XZ; SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(void)
0x18000d9cd  mov     rdi, [rsp+150h+var_F0]
0x18000d9d2  test    bl, bl
0x18000d9d4  jz      loc_18000E009
0x18000d9da  xor     edx, edx
0x18000d9dc  lea     rcx, [rsp+150h+var_110]
0x18000d9e1  call    ??0?$SmartPtr@VDataStashMap@@@@QEAA@PEAVDataStashMap@@@Z; SmartPtr<DataStashMap>::SmartPtr<DataStashMap>(DataStashMap *)
0x18000d9e6  nop
0x18000d9e7  xor     edx, edx
0x18000d9e9  lea     rcx, [rsp+150h+var_E0]
0x18000d9ee  call    ??0?$SmartArrayPtr@E@@QEAA@PEAE@Z; SmartArrayPtr<uchar>::SmartArrayPtr<uchar>(uchar *)
0x18000d9f3  nop
0x18000d9f4  xor     ebx, ebx
0x18000d9f6  mov     r14d, ebx
0x18000d9f9  mov     dword ptr [rsi+26Ch], 14h
0x18000da03  mov     rcx, [rsi+288h]; this
0x18000da0a  call    ?include@FileSystemSupport@@QEAA_NXZ; FileSystemSupport::include(void)
0x18000da0f  lea     r13d, [rbx+3]
0x18000da13  test    al, al
0x18000da15  jz      short loc_18000DA1E
0x18000da17  add     [rsi+26Ch], r13d
0x18000da1e  mov     ecx, 18h; unsigned __int64
0x18000da23  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000da28  mov     [rsp+150h+pExceptionObject], rax
0x18000da2d  test    rax, rax
0x18000da30  jz      short loc_18000DA3C
0x18000da32  mov     rcx, rax; this
0x18000da35  call    ??0DataStashMap@@QEAA@XZ; DataStashMap::DataStashMap(void)
0x18000da3a  jmp     short loc_18000DA3F
0x18000da3c  mov     rax, rbx
0x18000da3f  mov     rdx, rax
0x18000da42  lea     rcx, [rsp+150h+var_110]
0x18000da47  call    ??4?$SmartPtr@VDataStashMap@@@@QEAAAEAV0@PEAVDataStashMap@@@Z; SmartPtr<DataStashMap>::operator=(DataStashMap *)
0x18000da4c  mov     ecx, 18h; unsigned __int64
0x18000da51  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000da56  mov     [rsp+150h+pExceptionObject], rax
0x18000da5b  test    rax, rax
0x18000da5e  jz      short loc_18000DA6C
0x18000da60  mov     [rax], rbx
0x18000da63  mov     [rax+8], ebx
0x18000da66  mov     [rax+10h], rbx
0x18000da6a  jmp     short loc_18000DA6F
0x18000da6c  mov     rax, rbx
0x18000da6f  mov     rdx, rax
0x18000da72  lea     rcx, [rsp+150h+var_E0]
0x18000da77  call    ??4?$SmartPtr@UDataStashMapEntry@@@@QEAAAEAV0@PEAUDataStashMapEntry@@@Z; SmartPtr<DataStashMapEntry>::operator=(DataStashMapEntry *)
0x18000da7c  mov     rax, [rsp+150h+var_E0]
0x18000da81  mov     rcx, [rax]
0x18000da84  mov     [rcx], ebx
0x18000da86  mov     rcx, [rax]
0x18000da89  mov     [rcx+8], ebx
0x18000da8c  mov     rdx, [rax]
0x18000da8f  mov     ecx, [rsi+26Ch]
0x18000da95  mov     [rdx+4], ecx
0x18000da98  mov     rdx, [rax]
0x18000da9b  mov     ecx, [rdx+4]
0x18000da9e  shl     rcx, 0Bh
0x18000daa2  mov     [rdx+10h], rcx
0x18000daa6  mov     rbx, [rsp+150h+var_110]
0x18000daab  mov     rcx, [rbx]
0x18000daae  mov     [rsp+150h+ppstm], rax
0x18000dab3  test    rax, rax
0x18000dab6  jz      short loc_18000DABB
0x18000dab8  inc     dword ptr [rax+8]
0x18000dabb  lea     rdx, [rsp+150h+ppstm]
0x18000dac0  call    ?Add@DataStashMap@@QEAAXV?$SmartPtr@UDataStashMapEntry@@@@@Z; DataStashMap::Add(SmartPtr<DataStashMapEntry>)
0x18000dac5  mov     ecx, 78h ; 'x'; unsigned __int64
0x18000daca  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000dacf  mov     r9, rax
0x18000dad2  mov     [rsp+150h+pExceptionObject], rax
0x18000dad7  test    rax, rax
0x18000dada  jz      short loc_18000DB16
0x18000dadc  mov     [rsp+150h+ppstm], rbx
0x18000dae1  test    rbx, rbx
0x18000dae4  jz      short loc_18000DAE9
0x18000dae6  inc     dword ptr [rbx+8]
0x18000dae9  mov     rax, [rsi+2C0h]
0x18000daf0  mov     rcx, [rax]
0x18000daf3  mov     rax, [rcx]
0x18000daf6  mov     [rsp+150h+var_118], rax
0x18000dafb  test    rax, rax
0x18000dafe  jz      short loc_18000DB03
0x18000db00  inc     dword ptr [rax+8]
0x18000db03  lea     r8, [rsp+150h+ppstm]
0x18000db08  lea     rdx, [rsp+150h+var_118]
0x18000db0d  mov     rcx, r9; this
0x18000db10  call    ??0StashFileDescr@@QEAA@V?$SmartPtr@VCAtlFile@ATL@@@@V?$SmartPtr@VDataStashMap@@@@@Z; StashFileDescr::StashFileDescr(SmartPtr<ATL::CAtlFile>,SmartPtr<DataStashMap>)
0x18000db15  nop
0x18000db16  mov     rdx, rax
0x18000db19  lea     rcx, [rsp+150h+pExceptionObject]
0x18000db1e  call    ??0?$SmartPtr@VImportMetadata@@@@QEAA@PEAVImportMetadata@@@Z; SmartPtr<ImportMetadata>::SmartPtr<ImportMetadata>(ImportMetadata *)
0x18000db23  lea     rdx, [rsp+150h+pExceptionObject]
0x18000db28  mov     rcx, [rdi]
0x18000db2b  call    ??4?$SmartPtr@VImportMetadata@@@@QEAAAEAV0@AEBV0@@Z; SmartPtr<ImportMetadata>::operator=(SmartPtr<ImportMetadata> const &)
0x18000db30  lea     rcx, [rsp+150h+pExceptionObject]; void *
0x18000db35  call    ??1?$SmartPtr@VVolumeRecognitionStructureBase@@@@QEAA@XZ; SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(void)
0x18000db3a  mov     ecx, [rsi+18Ch]
0x18000db40  mov     r10d, [rsi+26Ch]
0x18000db47  xor     edx, edx
0x18000db49  mov     eax, r10d
0x18000db4c  div     ecx
0x18000db4e  test    edx, edx
0x18000db50  jz      short loc_18000DB63
0x18000db52  lea     r14d, [rcx+r10]
0x18000db56  xor     edx, edx
0x18000db58  mov     eax, r14d
0x18000db5b  div     ecx
0x18000db5d  sub     r14d, edx
0x18000db60  sub     r14d, r10d
0x18000db63  mov     rax, [rsi+310h]
0x18000db6a  mov     [rsp+150h+pExceptionObject], rax
0x18000db6f  test    rax, rax
0x18000db72  jz      short loc_18000DB77
0x18000db74  inc     dword ptr [rax+8]
0x18000db77  movsxd  r8, r14d
0x18000db7a  shl     r8, 0Bh
0x18000db7e  mov     r9b, 1
0x18000db81  mov     edx, r10d
0x18000db84  lea     rcx, [rsp+150h+pExceptionObject]; void *
0x18000db89  call    ?GetStream@@YAPEAVCStreamROBase@@V?$SmartClassPtr@VCDiscReader@@V1@@@K_K_N@Z; GetStream(SmartClassPtr<CDiscReader,CDiscReader>,ulong,unsigned __int64,bool)
0x18000db8e  mov     rdx, rax
0x18000db91  lea     rcx, [rsp+150h+var_118]
0x18000db96  call    ??0?$SmartPtr@VImportMetadata@@@@QEAA@PEAVImportMetadata@@@Z; SmartPtr<ImportMetadata>::SmartPtr<ImportMetadata>(ImportMetadata *)
0x18000db9b  mov     rcx, [rdi]
0x18000db9e  add     rcx, 8
0x18000dba2  lea     rdx, [rsp+150h+var_118]
0x18000dba7  call    ??4?$SmartPtr@VImportMetadata@@@@QEAAAEAV0@AEBV0@@Z; SmartPtr<ImportMetadata>::operator=(SmartPtr<ImportMetadata> const &)
0x18000dbac  lea     rcx, [rsp+150h+var_118]; void *
0x18000dbb1  call    ??1?$SmartPtr@VVolumeRecognitionStructureBase@@@@QEAA@XZ; SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(void)
0x18000dbb6  mov     rcx, [rsi+288h]; this
0x18000dbbd  call    ?include@FileSystemSupport@@QEAA_NXZ; FileSystemSupport::include(void)
0x18000dbc2  mov     ecx, [rsi+26Ch]
0x18000dbc8  test    al, al
0x18000dbca  mov     eax, 100h
0x18000dbcf  jnz     short loc_18000DBD7
0x18000dbd1  mov     eax, [rsi+260h]
0x18000dbd7  sub     eax, ecx
0x18000dbd9  sub     eax, r14d
0x18000dbdc  mov     r8d, eax
0x18000dbdf  shl     r8, 0Bh
0x18000dbe3  mov     rax, [rsi+310h]
0x18000dbea  mov     [rsp+150h+pExceptionObject], rax
0x18000dbef  test    rax, rax
0x18000dbf2  jz      short loc_18000DBF7
0x18000dbf4  inc     dword ptr [rax+8]
0x18000dbf7  lea     edx, [rcx+r14]
0x18000dbfb  xor     r9d, r9d
0x18000dbfe  lea     rcx, [rsp+150h+pExceptionObject]; void *
0x18000dc03  call    ?GetStream@@YAPEAVCStreamROBase@@V?$SmartClassPtr@VCDiscReader@@V1@@@K_K_N@Z; GetStream(SmartClassPtr<CDiscReader,CDiscReader>,ulong,unsigned __int64,bool)
0x18000dc08  mov     rdx, rax
0x18000dc0b  lea     rcx, [rsp+150h+var_118]
0x18000dc10  call    ??0?$SmartPtr@VImportMetadata@@@@QEAA@PEAVImportMetadata@@@Z; SmartPtr<ImportMetadata>::SmartPtr<ImportMetadata>(ImportMetadata *)
0x18000dc15  mov     rcx, [rdi]
0x18000dc18  add     rcx, 10h
0x18000dc1c  lea     rdx, [rsp+150h+var_118]
0x18000dc21  call    ??4?$SmartPtr@VImportMetadata@@@@QEAAAEAV0@AEBV0@@Z; SmartPtr<ImportMetadata>::operator=(SmartPtr<ImportMetadata> const &)
0x18000dc26  lea     rcx, [rsp+150h+var_118]; void *
0x18000dc2b  call    ??1?$SmartPtr@VVolumeRecognitionStructureBase@@@@QEAA@XZ; SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(void)
0x18000dc30  mov     rcx, [rsi+288h]; this
0x18000dc37  call    ?include@FileSystemSupport@@QEAA_NXZ; FileSystemSupport::include(void)
0x18000dc3c  test    al, al
0x18000dc3e  jz      loc_18000DFF0
0x18000dc44  lea     rcx, [rbp+50h+var_D0]; this
  ... truncated ...
```
