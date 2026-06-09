# CASFReader::LoadInternal(void)

- ea: `0x18000ab04`
- end: `0x18000b923`
- name: `?LoadInternal@CASFReader@@QEAAJXZ`
- size: `3615`
- prototype: `__int64 __fastcall(CASFReader *this, unsigned __int64)`
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops, registry_config, loader_planting, service_task`

## callers

- `0x18000a8a0`
- `0x18000aa50`

## callees

- `0x180001008`
- `0x180001014`
- `0x180001020`
- `0x180001460`
- `0x1800026d4`
- `0x180006f48`
- `0x180007004`
- `0x1800074d8`
- `0x18000784c`
- `0x1800087d8`
- `0x180008b9c`
- `0x18000a508`
- `0x18000ab04`
- `0x18000c9e4`
- `0x18000cc78`
- `0x18001be68`
- `0x18001f010`

## import_xrefs

- `WMVCore!WMCreateReader` at `0x18000ac20`
- `WMVCore!WMCreateReader` at `0x18000ac20`
- `KERNEL32!WaitForSingleObject` at `0x18000ad15`
- `KERNEL32!WaitForSingleObject` at `0x18000ad15`

## string_xrefs

- `0x18000b81d`: `DedicatedDeliveryThread`

## pseudocode

```c
__int64 __fastcall CASFReader::LoadInternal(CASFReader *this, unsigned __int64 a2)
{
  HRESULT StreamNumberFromOutputNumber; // ebx
  IWMReader **v4; // r12
  int v5; // ebx
  void *v6; // rcx
  void *v7; // rax
  unsigned int v8; // r13d
  int v9; // eax
  unsigned __int64 v10; // rdx
  int v11; // r14d
  struct _WMMediaType *v12; // r15
  int v13; // eax
  int v14; // r12d
  CASFOutput *v15; // r13
  CASFReader *v16; // rcx
  __int64 v17; // rax
  const unsigned __int16 *v18; // r8
  CASFOutput *v19; // rax
  struct __POSITION *v20; // rax
  unsigned int i; // r15d
  CASFOutput *v22; // r14
  unsigned __int64 v23; // rdx
  unsigned int v24; // eax
  struct _WMMediaType *v25; // r13
  CASFReader *v26; // rcx
  __int64 v27; // rax
  const unsigned __int16 *v28; // r8
  CASFOutput *v29; // rax
  _DWORD *v30; // r12
  struct __POSITION *v31; // r12
  int v32; // eax
  int v34; // [rsp+28h] [rbp-180h]
  int v35; // [rsp+28h] [rbp-180h]
  int v36; // [rsp+40h] [rbp-168h] BYREF
  int v37; // [rsp+44h] [rbp-164h] BYREF
  int v38; // [rsp+48h] [rbp-160h] BYREF
  IWMReader **v39; // [rsp+50h] [rbp-158h]
  struct IWMStreamConfig *v40; // [rsp+58h] [rbp-150h] BYREF
  int v41[2]; // [rsp+60h] [rbp-148h] BYREF
  unsigned int v42; // [rsp+68h] [rbp-140h] BYREF
  unsigned __int16 v43[2]; // [rsp+6Ch] [rbp-13Ch] BYREF
  unsigned __int16 v44[2]; // [rsp+70h] [rbp-138h] BYREF
  unsigned int v45; // [rsp+74h] [rbp-134h] BYREF
  unsigned int v46; // [rsp+78h] [rbp-130h] BYREF
  int v47[2]; // [rsp+80h] [rbp-128h] BYREF
  struct IWMStreamConfig *v48; // [rsp+88h] [rbp-120h] BYREF
  unsigned int v49; // [rsp+90h] [rbp-118h] BYREF
  __int64 v50; // [rsp+98h] [rbp-110h] BYREF
  unsigned __int16 v51[104]; // [rsp+A0h] [rbp-108h] BYREF

  *(_QWORD *)v47 = this;
  StreamNumberFromOutputNumber = 0;
  v36 = 0;
  v4 = (IWMReader **)((char *)this + 344);
  v39 = (IWMReader **)((char *)this + 344);
  if ( !*((_QWORD *)this + 43) )
  {
    if ( !*((_DWORD *)this + 84) )
    {
      v48 = 0;
      if ( (***((int (__fastcall ****)(_QWORD, GUID *, struct IWMStreamConfig **))this + 12))(
             *((_QWORD *)this + 12),
             &IID_IObjectWithSite,
             &v48) >= 0 )
      {
        v40 = 0;
        v5 = ((__int64 (__fastcall *)(struct IWMStreamConfig *, GUID *, struct IWMStreamConfig **))v48->lpVtbl->GetStreamNumber)(
               v48,
               &IID_IServiceProvider,
               &v40);
        ((void (__fastcall *)(struct IWMStreamConfig *))v48->lpVtbl->Release)(v48);
        if ( v5 >= 0 )
        {
          ((void (__fastcall *)(struct IWMStreamConfig *, GUID *, GUID *, char *))v40->lpVtbl->GetStreamType)(
            v40,
            &IID_IWMReader,
            &IID_IUnknown,
            (char *)this + 328);
          ((void (__fastcall *)(struct IWMStreamConfig *))v40->lpVtbl->Release)(v40);
        }
      }
      *((_DWORD *)this + 84) = 1;
    }
    StreamNumberFromOutputNumber = WMCreateReader(*((IUnknown **)this + 41), 1u, v4);
    v36 = StreamNumberFromOutputNumber;
  }
  if ( !*((_QWORD *)this + 44) && StreamNumberFromOutputNumber >= 0 )
  {
    StreamNumberFromOutputNumber = ((__int64 (__fastcall *)(IWMReader *, GUID *, char *))(*v4)->lpVtbl->QueryInterface)(
                                     *v4,
                                     &IID_IWMReaderAdvanced,
                                     (char *)this + 352);
    v36 = StreamNumberFromOutputNumber;
  }
  if ( !*((_QWORD *)this + 45) && StreamNumberFromOutputNumber >= 0 )
    ((void (__fastcall *)(IWMReader *, GUID *))(*v4)->lpVtbl->QueryInterface)(*v4, &IID_IWMReaderAdvanced2);
  if ( !*((_QWORD *)this + 46) )
  {
    if ( StreamNumberFromOutputNumber < 0 )
      goto LABEL_19;
    ((void (__fastcall *)(IWMReader *, GUID *))(*v4)->lpVtbl->QueryInterface)(*v4, &IID_IWMHeaderInfo);
  }
  if ( StreamNumberFromOutputNumber < 0 )
  {
LABEL_19:
    if ( *v4 )
    {
      ((void (__fastcall *)(IWMReader *))(*v4)->lpVtbl->Release)(*v4);
      *v4 = 0;
    }
    goto LABEL_21;
  }
  StreamNumberFromOutputNumber = ((__int64 (__fastcall *)(IWMReader *, _QWORD, _QWORD, _QWORD))(*v4)->lpVtbl->Open)(
                                   *v4,
                                   *((_QWORD *)this + 30),
                                   *((_QWORD *)this + 47),
                                   0);
  v36 = StreamNumberFromOutputNumber;
LABEL_21:
  if ( StreamNumberFromOutputNumber >= 0 )
  {
    WaitForSingleObject(*((HANDLE *)this + 51), 0xFFFFFFFF);
    StreamNumberFromOutputNumber = *((_DWORD *)this + 104);
    v36 = StreamNumberFromOutputNumber;
  }
  *((_DWORD *)this + 112) = 0;
  if ( StreamNumberFromOutputNumber >= 0 )
  {
    *(_QWORD *)v41 = 0;
    if ( ((__int64 (__fastcall *)(IWMReader *, GUID *, int *))(*v4)->lpVtbl->QueryInterface)(
           *v4,
           &IID_IWMHeaderInfo,
           v41) >= 0 )
    {
      v44[0] = -1;
      v45 = 0;
      v43[0] = 8;
      if ( (*(int (__fastcall **)(_QWORD, unsigned __int16 *, const wchar_t *, unsigned int *, char *, unsigned __int16 *))(**(_QWORD **)v41 + 40LL))(
             *(_QWORD *)v41,
             v44,
             L"Duration",
             &v45,
             (char *)this + 384,
             v43) >= 0 )
      {
        *((_QWORD *)this + 33) = *((_QWORD *)this + 48);
        *((_QWORD *)this + 32) = 0;
      }
      v46 = 0;
      v44[0] = -1;
      v43[0] = 4;
      if ( (*(int (__fastcall **)(_QWORD, unsigned __int16 *, const wchar_t *, unsigned int *, unsigned int *, unsigned __int16 *))(**(_QWORD **)v41 + 40LL))(
             *(_QWORD *)v41,
             v44,
             L"Is_Protected",
             &v45,
             &v46,
             v43) >= 0
        && v46 )
      {
        *((_DWORD *)this + 112) = 1;
      }
      v44[0] = 0;
      v47[0] = 0;
      v43[0] = 4;
      (*(void (__fastcall **)(_QWORD, unsigned __int16 *, const wchar_t *, int *, char *, unsigned __int16 *))(**(_QWORD **)v41 + 40LL))(
        *(_QWORD *)v41,
        v44,
        L"Seekable",
        v47,
        (char *)this + 392,
        v43);
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v41 + 16LL))(*(_QWORD *)v41);
    }
    (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 44) + 80LL))(*((_QWORD *)this + 44), 1);
  }
  v50 = 0;
  v42 = 0;
  if ( StreamNumberFromOutputNumber >= 0 )
  {
    StreamNumberFromOutputNumber = ((__int64 (__fastcall *)(IWMReader *, GUID *, __int64 *))(*v4)->lpVtbl->QueryInterface)(
                                     *v4,
                                     &IID_IWMProfile,
                                     &v50);
    v36 = StreamNumberFromOutputNumber;
    if ( StreamNumberFromOutputNumber >= 0 )
    {
      StreamNumberFromOutputNumber = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v50 + 64LL))(
                                       v50,
                                       &v42);
      v36 = StreamNumberFromOutputNumber;
      if ( StreamNumberFromOutputNumber >= 0 )
      {
        v6 = (void *)*((_QWORD *)this + 50);
        if ( v6 )
          operator delete(v6, a2);
        v7 = operator new[](saturated_mul(v42, 2u));
        *((_QWORD *)this + 50) = v7;
        if ( !v7 )
          StreamNumberFromOutputNumber = -2147024882;
        v36 = StreamNumberFromOutputNumber;
      }
    }
  }
  v8 = 0;
  v46 = 0;
  if ( StreamNumberFromOutputNumber >= 0 )
  {
    while ( 1 )
    {
      if ( v8 >= v42 )
      {
LABEL_112:
        v4 = v39;
        goto LABEL_113;
      }
      v40 = 0;
      v43[0] = 0;
      v45 = 0;
      v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IWMStreamConfig **))(*(_QWORD *)v50 + 72LL))(
             v50,
             v8,
             &v40);
      StreamNumberFromOutputNumber = v9;
      v36 = v9;
      if ( v9 >= 0 )
      {
        v9 = ((__int64 (__fastcall *)(struct IWMStreamConfig *, unsigned __int16 *))v40->lpVtbl->GetStreamNumber)(
               v40,
               v43);
        StreamNumberFromOutputNumber = v9;
        v36 = v9;
      }
      v11 = v9;
      v48 = 0;
      if ( v9 < 0
        || (*(_WORD *)(*((_QWORD *)this + 50) + 2LL * v8) = v43[0],
            StreamNumberFromOutputNumber = ((__int64 (__fastcall *)(struct IWMStreamConfig *, GUID *, struct IWMStreamConfig **))v40->lpVtbl->QueryInterface)(
                                             v40,
                                             &IID_IWMMediaProps,
                                             &v48),
            v36 = StreamNumberFromOutputNumber,
            v11 = StreamNumberFromOutputNumber,
            StreamNumberFromOutputNumber < 0)
        || (StreamNumberFromOutputNumber = ((__int64 (__fastcall *)(struct IWMStreamConfig *, _QWORD, unsigned int *))v48->lpVtbl->GetStreamNumber)(
                                             v48,
                                             0,
                                             &v45),
            v36 = StreamNumberFromOutputNumber,
            v11 = StreamNumberFromOutputNumber,
            StreamNumberFromOutputNumber < 0) )
      {
        v12 = 0;
      }
      else
      {
        v12 = (struct _WMMediaType *)operator new[](v45);
        if ( !v12 )
        {
          StreamNumberFromOutputNumber = -2147024882;
          v36 = -2147024882;
          v11 = -2147024882;
        }
      }
      if ( v11 >= 0 )
      {
        StreamNumberFromOutputNumber = ((__int64 (__fastcall *)(struct IWMStreamConfig *, struct _WMMediaType *, unsigned int *))v48->lpVtbl->GetStreamNumber)(
                                         v48,
                                         v12,
                                         &v45);
        v36 = StreamNumberFromOutputNumber;
        v11 = StreamNumberFromOutputNumber;
        if ( StreamNumberFromOutputNumber >= 0 )
        {
          *(_DWORD *)v44 = 0;
          v13 = ValidateMediaType(v12, v44);
          StreamNumberFromOutputNumber = v13;
          v36 = v13;
          if ( *(_DWORD *)v44 )
          {
            v11 = v13;
          }
          else
          {
            StreamNumberFromOutputNumber = 0;
            v36 = 0;
            v11 = 0;
          }
          if ( v11 < 0 && !v12->pbFormat && !v12->cbFormat )
          {
            StreamNumberFromOutputNumber = 0;
            v36 = 0;
            v11 = 0;
          }
        }
      }
      if ( !*((_DWORD *)this + 112) )
        break;
LABEL_107:
      operator delete(v12, v10);
      if ( v48 )
        ((void (__fastcall *)(struct IWMStreamConfig *))v48->lpVtbl->Release)(v48);
      if ( v40 )
        ((void (__fastcall *)(struct IWMStreamConfig *))v40->lpVtbl->Release)(v40);
      v46 = ++v8;
      if ( StreamNumberFromOutputNumber < 0 )
        goto LABEL_112;
    }
    v14 = 0;
    v38 = 0;
    v41[0] = 0;
    v47[0] = 0;
    v37 = 0;
    *(_DWORD *)v44 = 0;
    v15 = 0;
    if ( v11 >= 0 )
    {
      StreamNumberFromOutputNumber = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)this + 44) + 96LL))(
                                       *((_QWORD *)this + 44),
                                       v43[0],
                                       1);
      v36 = StreamNumberFromOutputNumber;
      if ( StreamNumberFromOutputNumber >= 0 )
      {
        if ( *(_QWORD *)&v12->majortype.Data1 == DVR_MEDIATYPE_Video
          && *(_QWORD *)v12->majortype.Data4 == 0xFDA2C08E7EBC99A7uLL )
        {
          v12->majortype = MEDIATYPE_Video;
          *(_DWORD *)v44 = 1;
        }
        if ( *(_QWORD *)&v12->majortype.Data1 == DVR_MEDIATYPE_Audio
          && *(_QWORD *)v12->majortype.Data4 == 0x3F522DBF93D82B5LL )
        {
          v12->majortype = MEDIATYPE_Audio;
          *(_DWORD *)v44 = 1;
        }
        if ( *(_QWORD *)&v12->majortype.Data1 == *(_QWORD *)&MEDIATYPE_Video.Data1
          && *(_QWORD *)v12->majortype.Data4 == *(_QWORD *)MEDIATYPE_Video.Data4 )
        {
          StringCchPrintfW(v51, 0x64u, L"Raw Video %d", v46);
        }
        else if ( *(_QWORD *)&v12->majortype.Data1 == *(_QWORD *)&MEDIATYPE_Audio.Data1
               && *(_QWORD *)v12->majortype.Data4 == *(_QWORD *)MEDIATYPE_Audio.Data4 )
        {
          StringCchPrintfW(v51, 0x64u, L"Raw Audio %d", v46);
        }
        else
        {
          v17 = *(_QWORD *)&v12->majortype.Data1 - *(_QWORD *)&WMMEDIATYPE_FileTransfer.Data1;
          if ( *(_QWORD *)&v12->majortype.Data1 == *(_QWORD *)&WMMEDIATYPE_FileTransfer.Data1 )
            v17 = *(_QWORD *)v12->majortype.Data4 - *(_QWORD *)WMMEDIATYPE_FileTransfer.Data4;
          v18 = L"Raw File Transfer %d";
          if ( v17 )
            v18 = L"Raw Stream %d";
          StringCchPrintfW(v51, 0x64u, v18, v46);
        }
        CASFReader::CheckDataUnitExtensionsForVIH2Props(v16, v40, &v38, &v37, (int *)v44);
        v19 = (CASFOutput *)operator new(0x1A8u);
        if ( v19 )
        {
          v15 = CASFOutput::CASFOutput(v19, this, v43[0], v12, &v36, v51);
          StreamNumberFromOutputNumber = v36;
        }
        if ( !v15 )
        {
          StreamNumberFromOutputNumber = -2147024882;
          v36 = -2147024882;
LABEL_96:
          v20 = 0;
          if ( StreamNumberFromOutputNumber < 0 )
            goto LABEL_100;
          v20 = CBaseList::AddTailI((CASFReader *)((char *)this + 280), v15);
          if ( !v20 )
            StreamNumberFromOutputNumber = -2147024882;
          v36 = StreamNumberFromOutputNumber;
          if ( StreamNumberFromOutputNumber >= 0 )
          {
            StreamNumberFromOutputNumber = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)this + 44)
                                                                                              + 128LL))(
                                             *((_QWORD *)this + 44),
                                             v43[0],
                                             1);
            v36 = StreamNumberFromOutputNumber;
          }
          else
          {
LABEL_100:
            if ( v20 )
              CBaseList::RemoveI((CASFReader *)((char *)this + 280), v20);
            if ( v15 )
              (*(void (__fastcall **)(__int64))(*((_QWORD *)v15 + 3) + 16LL))((__int64)v15 + 24);
          }
          v8 = v46;
          goto LABEL_107;
        }
        (*(void (__fastcall **)(__int64))(*((_QWORD *)v15 + 3) + 8LL))((__int64)v15 + 24);
        v14 = v38;
      }
    }
    if ( StreamNumberFromOutputNumber >= 0 )
    {
      StreamNumberFromOutputNumber = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)this + 44)
                                                                                        + 168LL))(
                                       *((_QWORD *)this + 44),
                                       v43[0],
                                       (__int64)v15 + 312);
      v36 = StreamNumberFromOutputNumber;
      if ( *((_DWORD *)v15 + 78) <= 0x20u )
        *((_DWORD *)v15 + 78) = 0x10000;
      if ( StreamNumberFromOutputNumber >= 0 )
      {
        *((_DWORD *)v15 + 82) = *(_DWORD *)v44;
        *((_DWORD *)v15 + 102) = v37;
        *((_DWORD *)v15 + 103) = v14;
        if ( !v14 )
          CASFReader::CheckMetadataForVIH2Props(this, v15, v43[0], v41, v47);
        if ( *((_DWORD *)v15 + 103) || (StreamNumberFromOutputNumber = 0, *((_DWORD *)v15 + 102)) )
        {
          StreamNumberFromOutputNumber = ConvertVideoInfoToVideoInfo2((char *)v15 + 104);
          if ( StreamNumberFromOutputNumber >= 0 )
          {
            v10 = (unsigned int)v41[0];
            if ( v41[0] )
              CASFOutput::SetImageAspectRatio(v15, v41[0], v47[0]);
          }
        }
        v36 = StreamNumberFromOutputNumber;
      }
    }
    goto LABEL_96;
  }
LABEL_113:
  v49 = 0;
  if ( StreamNumberFromOutputNumber >= 0 )
  {
    StreamNumberFromOutputNumber = ((__int64 (__fastcall *)(IWMReader *, unsigned int *))(*v4)->lpVtbl->GetOutputCount)(
                                     *v4,
                                     &v49);
    v36 = StreamNumberFromOutputNumber;
  }
  for ( i = 0; StreamNumberFromOutputNumber >= 0 && i < v49; ++i )
  {
    if ( !*((_DWORD *)this + 112) )
    {
      StreamNumberFromOutputNumber = ((__int64 (__fastcall *)(IWMReader *, _QWORD, _QWORD))(*v4)->lpVtbl->SetOutputProps)(
                                       *v4,
                                       i,
                                       0);
      v36 = StreamNumberFromOutputNumber;
      continue;
    }
    v40 = 0;
    v22 = 0;
    StreamNumberFromOutputNumber = ((__int64 (__fastcall *)(IWMReader *, _QWORD, struct IWMStreamConfig **))(*v4)->lpVtbl->GetOutputProps)(
                                     *v4,
                                     i,
                                     &v40);
    v36 = StreamNumberFromOutputNumber;
    v24 = 0;
    v45 = 0;
    if ( StreamNumberFromOutputNumber >= 0 )
    {
      ((void (__fastcall *)(IWMReader *, _QWORD, struct IWMStreamConfig *))(*v4)->lpVtbl->SetOutputProps)(*v4, i, v40);
      StreamNumberFromOutputNumber = ((__int64 (__fastcall *)(struct IWMStreamConfig *, _QWORD, unsigned int *))v40->lpVtbl->GetStreamNumber)(
                                       v40,
                                       0,
                                       &v45);
      v36 = StreamNumberFromOutputNumber;
      v24 = v45;
    }
    v25 = 0;
    if ( StreamNumberFromOutputNumber >= 0 )
    {
      v25 = (struct _WMMediaType *)operator new[](v24);
      if ( !v25 )
        StreamNumberFromOutputNumber = -2147024882;
      v36 = StreamNumberFromOutputNumber;
    }
    if ( StreamNumberFromOutputNumber >= 0 )
    {
      StreamNumberFromOutputNumber = ((__int64 (__fastcall *)(struct IWMStreamConfig *, struct _WMMediaType *, unsigned int *))v40->lpVtbl->GetStreamNumber)(
                                       v40,
                                       v25,
                                       &v45);
      v36 = StreamNumberFromOutputNumber;
    }
    v41[0] = 0;
    v46 = 0;
    v38 = 0;
    v47[0] = 0;
    v37 = 0;
    v44[0] = 0;
    if ( StreamNumberFromOutputNumber < 0 )
      goto LABEL_145;
    v48 = 0;
    if ( (*(int (__fastcall **)(__int64, _QWORD, struct IWMStreamConfig **))(*(_QWORD *)v50 + 72LL))(
           v50,
           (unsigned __int16)i,
           &v48) >= 0 )
      CASFReader::CheckDataUnitExtensionsForVIH2Props(v26, v48, v41, v47, &v37);
    if ( v48 )
      ((void (__fastcall *)(struct IWMStreamConfig *))v48->lpVtbl->Release)(v48);
    if ( *(_QWORD *)&v25->majortype.Data1 == *(_QWORD *)&MEDIATYPE_Video.Data1
      && *(_QWORD *)v25->majortype.Data4 == *(_QWORD *)MEDIATYPE_Video.Data4 )
    {
      StringCchPrintfW(v51, 0x64u, L"Video %d", i);
    }
    else
    {
      v27 = *(_QWORD *)&v25->majortype.Data1 - *(_QWORD *)&MEDIATYPE_Audio.Data1;
      if ( *(_QWORD *)&v25->majortype.Data1 == *(_QWORD *)&MEDIATYPE_Audio.Data1 )
        v27 = *(_QWORD *)v25->majortype.Data4 - *(_QWORD *)MEDIATYPE_Audio.Data4;
      v28 = L"Audio %d";
      if ( v27 )
        v28 = L"Stream %d";
      StringCchPrintfW(v51, 0x64u, v28, i);
    }
    v29 = (CASFOutput *)operator new(0x1A8u);
    if ( v29 )
    {
      v22 = CASFOutput::CASFOutput(v29, this, i, v25, &v36, v51);
      StreamNumberFromOutputNumber = v36;
    }
    if ( v22 )
    {
      (*(void (__fastcall **)(__int64))(*((_QWORD *)v22 + 3) + 8LL))((__int64)v22 + 24);
LABEL_145:
      v30 = (_DWORD *)((char *)v22 + 312);
      if ( StreamNumberFromOutputNumber >= 0 )
      {
        StreamNumberFromOutputNumber = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)this + 44)
                                                                                          + 160LL))(
                                         *((_QWORD *)this + 44),
                                         i,
                                         (__int64)v22 + 312);
        v36 = StreamNumberFromOutputNumber;
        if ( StreamNumberFromOutputNumber >= 0 )
        {
          if ( *v30 <= 0x20u )
            *v30 = 0x10000;
          StreamNumberFromOutputNumber = CASFReader::GetStreamNumberFromOutputNumber(this, i, v44);
          v36 = StreamNumberFromOutputNumber;
        }
      }
      goto LABEL_150;
    }
    StreamNumberFromOutputNumber = -2147024882;
    v36 = -2147024882;
LABEL_150:
    v31 = 0;
    if ( StreamNumberFromOutputNumber < 0 )
      goto LABEL_158;
    *((_DWORD *)v22 + 102) = v47[0];
    v32 = v41[0];
    *((_DWORD *)v22 + 103) = v41[0];
    *((_DWORD *)v22 + 82) = v37;
    if ( !v32 )
      CASFReader::CheckMetadataForVIH2Props(this, v22, v44[0], (int *)&v46, &v38);
    v31 = CBaseList::AddTailI((CASFReader *)((char *)this + 280), v22);
    if ( !v31 )
      StreamNumberFromOutputNumber = -2147024882;
    v36 = StreamNumberFromOutputNumber;
    if ( StreamNumberFromOutputNumber < 0
      || (StreamNumberFromOutputNumber = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)this + 44)
                                                                                            + 112LL))(
                                           *((_QWORD *)this + 44),
                                           (unsigned __int16)i,
                                           1),
          v36 = StreamNumberFromOutputNumber,
          StreamNumberFromOutputNumber < 0) )
    {
LABEL_158:
      if ( v31 )
        CBaseList::RemoveI((CASFReader *)((char *)this + 280), v31);
      if ( v22 )
        (*(void (__fastcall **)(__int64))(*((_QWORD *)v22 + 3) + 16LL))((__int64)v22 + 24);
    }
    else
    {
      v47[0] = 1;
      LOWORD(v34) = 4;
      (*(void (__fastcall **)(_QWORD, _QWORD, const wchar_t *, __int64, int *, int))(**((_QWORD **)this + 45) + 256LL))(
        *((_QWORD *)this + 45),
        i,
        L"JustInTimeDecode",
        3,
        v47,
        v34);
      v47[0] = 1;
      LOWORD(v35) = 4;
      (*(void (__fastcall **)(_QWORD, _QWORD, const wchar_t *, __int64, int *, int))(**((_QWORD **)this + 45) + 256LL))(
        *((_QWORD *)this + 45),
        i,
        L"DedicatedDeliveryThread",
        3,
        v47,
        v35);
    }
    operator delete(v25, v23);
    if ( v40 )
      ((void (__fastcall *)(struct IWMStreamConfig *))v40->lpVtbl->Release)(v40);
    v4 = v39;
  }
  if ( StreamNumberFromOutputNumber >= 0 )
    (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 44) + 24LL))(*((_QWORD *)this + 44), 1);
  if ( StreamNumberFromOutputNumber == -1072886850 || StreamNumberFromOutputNumber == -1072879832 )
  {
    operator delete(*((void **)this + 30), a2);
    *((_QWORD *)this + 30) = 0;
  }
  else if ( StreamNumberFromOutputNumber < 0 )
  {
    CASFReader::RemoveOutputPins(this, a2);
  }
  if ( v50 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
  return (unsigned int)StreamNumberFromOutputNumber;
}

```

## disassembly

```asm
0x18000ab04  mov     r11, rsp
0x18000ab07  mov     [r11+10h], rbx
0x18000ab0b  mov     [r11+18h], rsi
0x18000ab0f  push    rdi
0x18000ab10  push    r12
0x18000ab12  push    r13
0x18000ab14  push    r14
0x18000ab16  push    r15
0x18000ab18  sub     rsp, 180h
0x18000ab1f  mov     rax, cs:__security_cookie
0x18000ab26  xor     rax, rsp
0x18000ab29  mov     [rsp+1A8h+var_38], rax
0x18000ab31  mov     rsi, rcx
0x18000ab34  mov     qword ptr [rsp+1A8h+var_128], rcx
0x18000ab3c  xor     edi, edi
0x18000ab3e  mov     ebx, edi
0x18000ab40  mov     [rsp+1A8h+var_168], ebx
0x18000ab44  lea     r12, [rcx+158h]
0x18000ab4b  mov     [rsp+1A8h+var_158], r12
0x18000ab50  cmp     [r12], rdi
0x18000ab54  jnz     loc_18000AC46
0x18000ab5a  cmp     [rcx+150h], edi
0x18000ab60  jnz     loc_18000AC11
0x18000ab66  mov     [r11-120h], rdi
0x18000ab6d  mov     rcx, [rcx+60h]
0x18000ab71  mov     rax, [rcx]
0x18000ab74  lea     r8, [r11-120h]
0x18000ab7b  lea     rdx, IID_IObjectWithSite
0x18000ab82  mov     rax, [rax]
0x18000ab85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab8a  test    eax, eax
0x18000ab8c  js      short loc_18000AC07
0x18000ab8e  mov     [rsp+1A8h+var_150], rdi
0x18000ab93  mov     rcx, [rsp+1A8h+var_120]
0x18000ab9b  mov     rax, [rcx]
0x18000ab9e  lea     r8, [rsp+1A8h+var_150]
0x18000aba3  lea     rdx, IID_IServiceProvider
0x18000abaa  mov     rax, [rax+20h]
0x18000abae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abb3  mov     ebx, eax
0x18000abb5  mov     rdx, [rsp+1A8h+var_120]
0x18000abbd  mov     rcx, [rdx]
0x18000abc0  mov     rax, [rcx+10h]
0x18000abc4  mov     rcx, rdx
0x18000abc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abcc  test    ebx, ebx
0x18000abce  js      short loc_18000AC07
0x18000abd0  mov     rcx, [rsp+1A8h+var_150]
0x18000abd5  mov     rax, [rcx]
0x18000abd8  lea     r9, [rsi+148h]
0x18000abdf  lea     r8, IID_IUnknown
0x18000abe6  lea     rdx, IID_IWMReader
0x18000abed  mov     rax, [rax+18h]
0x18000abf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abf6  mov     rcx, [rsp+1A8h+var_150]
0x18000abfb  mov     rax, [rcx]
0x18000abfe  mov     rax, [rax+10h]
0x18000ac02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac07  mov     dword ptr [rsi+150h], 1
0x18000ac11  mov     r8, r12; ppReader
0x18000ac14  mov     edx, 1; dwRights
0x18000ac19  mov     rcx, [rsi+148h]; pUnkCert
0x18000ac20  call    cs:__imp_WMCreateReader
0x18000ac26  mov     ebx, eax
0x18000ac28  mov     [rsp+1A8h+var_168], eax
0x18000ac2c  jmp     short loc_18000AC46
0x18000ac2e  mov     ebx, 8007007Eh
0x18000ac33  mov     [rsp+1A8h+var_168], ebx
0x18000ac37  xor     edi, edi
0x18000ac39  mov     rsi, qword ptr [rsp+1A8h+var_128]
0x18000ac41  mov     r12, [rsp+1A8h+var_158]
0x18000ac46  lea     r15, [rsi+160h]
0x18000ac4d  cmp     [r15], rdi
0x18000ac50  jnz     short loc_18000AC75
0x18000ac52  test    ebx, ebx
0x18000ac54  js      short loc_18000AC75
0x18000ac56  mov     rcx, [r12]
0x18000ac5a  mov     rax, [rcx]
0x18000ac5d  mov     r8, r15
0x18000ac60  lea     rdx, IID_IWMReaderAdvanced
0x18000ac67  mov     rax, [rax]
0x18000ac6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac6f  mov     ebx, eax
0x18000ac71  mov     [rsp+1A8h+var_168], eax
0x18000ac75  lea     r8, [rsi+168h]
0x18000ac7c  cmp     [r8], rdi
0x18000ac7f  jnz     short loc_18000AC9B
0x18000ac81  test    ebx, ebx
0x18000ac83  js      short loc_18000AC9B
0x18000ac85  mov     rcx, [r12]
0x18000ac89  mov     rax, [rcx]
0x18000ac8c  lea     rdx, IID_IWMReaderAdvanced2
0x18000ac93  mov     rax, [rax]
0x18000ac96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac9b  lea     r8, [rsi+170h]
0x18000aca2  cmp     [r8], rdi
0x18000aca5  jnz     short loc_18000ACC1
0x18000aca7  test    ebx, ebx
0x18000aca9  js      short loc_18000ACEE
0x18000acab  mov     rcx, [r12]
0x18000acaf  mov     rax, [rcx]
0x18000acb2  lea     rdx, IID_IWMHeaderInfo
0x18000acb9  mov     rax, [rax]
0x18000acbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000acc1  test    ebx, ebx
0x18000acc3  js      short loc_18000ACEE
0x18000acc5  mov     rcx, [r12]
0x18000acc9  mov     rax, [rcx]
0x18000accc  xor     r9d, r9d
0x18000accf  mov     r8, [rsi+178h]
0x18000acd6  mov     rdx, [rsi+0F0h]
0x18000acdd  mov     rax, [rax+18h]
0x18000ace1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ace6  mov     ebx, eax
0x18000ace8  mov     [rsp+1A8h+var_168], eax
0x18000acec  jmp     short loc_18000AD07
0x18000acee  mov     rcx, [r12]
0x18000acf2  test    rcx, rcx
0x18000acf5  jz      short loc_18000AD07
0x18000acf7  mov     rax, [rcx]
0x18000acfa  mov     rax, [rax+10h]
0x18000acfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad03  mov     [r12], rdi
0x18000ad07  test    ebx, ebx
0x18000ad09  js      short loc_18000AD25
0x18000ad0b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000ad0e  mov     rcx, [rsi+198h]; hHandle
0x18000ad15  call    cs:__imp_WaitForSingleObject
0x18000ad1b  mov     ebx, [rsi+1A0h]
0x18000ad21  mov     [rsp+1A8h+var_168], ebx
0x18000ad25  mov     [rsi+1C0h], edi
0x18000ad2b  test    ebx, ebx
0x18000ad2d  js      loc_18000AE97
0x18000ad33  mov     qword ptr [rsp+1A8h+var_148], rdi
0x18000ad38  mov     rcx, [r12]
0x18000ad3c  mov     rax, [rcx]
0x18000ad3f  lea     r8, [rsp+1A8h+var_148]
0x18000ad44  lea     rdx, IID_IWMHeaderInfo
0x18000ad4b  mov     rax, [rax]
0x18000ad4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad53  test    eax, eax
0x18000ad55  js      loc_18000AE83
0x18000ad5b  mov     r13d, 0FFFFh
0x18000ad61  mov     [rsp+1A8h+var_138], r13w
0x18000ad67  mov     dword ptr [rsp+1A8h+var_134], edi
0x18000ad6b  mov     eax, 8
0x18000ad70  mov     [rsp+1A8h+var_13C], ax
0x18000ad75  lea     r14, [rsi+180h]
0x18000ad7c  mov     rcx, qword ptr [rsp+1A8h+var_148]
0x18000ad81  mov     rax, [rcx]
0x18000ad84  lea     rdx, [rsp+1A8h+var_13C]
0x18000ad89  mov     qword ptr [rsp+1A8h+var_180], rdx
0x18000ad8e  mov     [rsp+1A8h+var_188], r14
0x18000ad93  lea     r9, [rsp+1A8h+var_134]
0x18000ad98  lea     r8, aDuration; "Duration"
0x18000ad9f  lea     rdx, [rsp+1A8h+var_138]
0x18000ada4  mov     rax, [rax+28h]
0x18000ada8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adad  test    eax, eax
0x18000adaf  js      short loc_18000ADC2
0x18000adb1  mov     rax, [r14]
0x18000adb4  mov     [rsi+108h], rax
0x18000adbb  mov     [rsi+100h], rdi
0x18000adc2  mov     dword ptr [rsp+1A8h+var_134+4], edi
0x18000adc6  mov     [rsp+1A8h+var_138], r13w
0x18000adcc  mov     r14d, 4
0x18000add2  mov     [rsp+1A8h+var_13C], r14w
0x18000add8  mov     rcx, qword ptr [rsp+1A8h+var_148]
0x18000addd  mov     rax, [rcx]
0x18000ade0  lea     rdx, [rsp+1A8h+var_13C]
0x18000ade5  mov     qword ptr [rsp+1A8h+var_180], rdx
0x18000adea  lea     rdx, [rsp+1A8h+var_134+4]
0x18000adef  mov     [rsp+1A8h+var_188], rdx
0x18000adf4  lea     r9, [rsp+1A8h+var_134]
0x18000adf9  lea     r8, aIsProtected; "Is_Protected"
0x18000ae00  lea     rdx, [rsp+1A8h+var_138]
0x18000ae05  mov     rax, [rax+28h]
0x18000ae09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae0e  test    eax, eax
0x18000ae10  js      short loc_18000AE22
0x18000ae12  cmp     dword ptr [rsp+1A8h+var_134+4], edi
0x18000ae16  jz      short loc_18000AE22
0x18000ae18  mov     dword ptr [rsi+1C0h], 1
0x18000ae22  mov     [rsp+1A8h+var_138], di
0x18000ae27  mov     [rsp+1A8h+var_128], edi
0x18000ae2e  mov     [rsp+1A8h+var_13C], r14w
0x18000ae34  mov     r10, qword ptr [rsp+1A8h+var_148]
0x18000ae39  mov     rax, [r10]
0x18000ae3c  lea     rcx, [rsi+188h]
0x18000ae43  lea     rdx, [rsp+1A8h+var_13C]
0x18000ae48  mov     qword ptr [rsp+1A8h+var_180], rdx
0x18000ae4d  mov     [rsp+1A8h+var_188], rcx
0x18000ae52  lea     r9, [rsp+1A8h+var_128]
0x18000ae5a  lea     r8, aSeekable; "Seekable"
0x18000ae61  lea     rdx, [rsp+1A8h+var_138]
0x18000ae66  mov     rcx, r10
0x18000ae69  mov     rax, [rax+28h]
0x18000ae6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae72  mov     rcx, qword ptr [rsp+1A8h+var_148]
0x18000ae77  mov     rax, [rcx]
0x18000ae7a  mov     rax, [rax+10h]
0x18000ae7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae83  mov     rcx, [r15]
0x18000ae86  mov     rax, [rcx]
0x18000ae89  mov     edx, 1
0x18000ae8e  mov     rax, [rax+50h]
0x18000ae92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae97  mov     [rsp+1A8h+var_110], rdi
0x18000ae9f  mov     [rsp+1A8h+var_140], edi
0x18000aea3  test    ebx, ebx
0x18000aea5  js      loc_18000AF3C
0x18000aeab  mov     rcx, [r12]
0x18000aeaf  mov     rax, [rcx]
0x18000aeb2  lea     r8, [rsp+1A8h+var_110]
0x18000aeba  lea     rdx, IID_IWMProfile
0x18000aec1  mov     rax, [rax]
0x18000aec4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aec9  mov     ebx, eax
0x18000aecb  mov     [rsp+1A8h+var_168], eax
0x18000aecf  test    eax, eax
0x18000aed1  js      short loc_18000AF3C
0x18000aed3  mov     rcx, [rsp+1A8h+var_110]
0x18000aedb  mov     rax, [rcx]
0x18000aede  lea     rdx, [rsp+1A8h+var_140]
0x18000aee3  mov     rax, [rax+40h]
0x18000aee7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aeec  mov     ebx, eax
0x18000aeee  mov     [rsp+1A8h+var_168], eax
0x18000aef2  test    eax, eax
0x18000aef4  js      short loc_18000AF3C
0x18000aef6  mov     rcx, [rsi+190h]; void *
0x18000aefd  test    rcx, rcx
0x18000af00  jz      short loc_18000AF07
0x18000af02  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000af07  mov     ecx, [rsp+1A8h+var_140]
0x18000af0b  mov     eax, 2
0x18000af10  mul     rcx
0x18000af13  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000af1a  cmovb   rax, rcx
0x18000af1e  mov     rcx, rax; unsigned __int64
0x18000af21  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000af26  mov     [rsi+190h], rax
0x18000af2d  mov     ecx, 8007000Eh
0x18000af32  test    rax, rax
0x18000af35  cmovz   ebx, ecx
0x18000af38  mov     [rsp+1A8h+var_168], ebx
0x18000af3c  mov     r13d, edi
0x18000af3f  mov     dword ptr [rsp+1A8h+var_134+4], edi
0x18000af43  test    ebx, ebx
0x18000af45  js      loc_18000B424
0x18000af4b  cmp     r13d, [rsp+1A8h+var_140]
0x18000af50  jnb     loc_18000B41F
0x18000af56  mov     [rsp+1A8h+var_150], rdi
0x18000af5b  mov     [rsp+1A8h+var_13C], di
0x18000af60  mov     dword ptr [rsp+1A8h+var_134], edi
0x18000af64  mov     rcx, [rsp+1A8h+var_110]
0x18000af6c  mov     rax, [rcx]
0x18000af6f  lea     r8, [rsp+1A8h+var_150]
0x18000af74  mov     edx, r13d
0x18000af77  mov     rax, [rax+48h]
0x18000af7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af80  mov     ebx, eax
0x18000af82  mov     [rsp+1A8h+var_168], eax
0x18000af86  test    eax, eax
0x18000af88  js      short loc_18000AFA6
0x18000af8a  mov     rcx, [rsp+1A8h+var_150]
0x18000af8f  mov     rax, [rcx]
0x18000af92  lea     rdx, [rsp+1A8h+var_13C]
0x18000af97  mov     rax, [rax+20h]
0x18000af9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afa0  mov     ebx, eax
0x18000afa2  mov     [rsp+1A8h+var_168], eax
0x18000afa6  mov     r14d, eax
0x18000afa9  mov     [rsp+1A8h+var_120], rdi
0x18000afb1  test    eax, eax
0x18000afb3  js      loc_18000B041
0x18000afb9  mov     edx, r13d
0x18000afbc  mov     rcx, [rsi+190h]
0x18000afc3  movzx   eax, [rsp+1A8h+var_13C]
0x18000afc8  mov     [rcx+rdx*2], ax
0x18000afcc  mov     rcx, [rsp+1A8h+var_150]
0x18000afd1  mov     rax, [rcx]
0x18000afd4  lea     r8, [rsp+1A8h+var_120]
0x18000afdc  lea     rdx, IID_IWMMediaProps
0x18000afe3  mov     rax, [rax]
0x18000afe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afeb  mov     ebx, eax
0x18000afed  mov     [rsp+1A8h+var_168], eax
0x18000aff1  mov     r14d, eax
0x18000aff4  test    eax, eax
0x18000aff6  js      short loc_18000B041
0x18000aff8  mov     rcx, [rsp+1A8h+var_120]
0x18000b000  mov     rax, [rcx]
0x18000b003  lea     r8, [rsp+1A8h+var_134]
0x18000b008  xor     edx, edx
0x18000b00a  mov     rax, [rax+20h]
0x18000b00e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b013  mov     ebx, eax
0x18000b015  mov     [rsp+1A8h+var_168], eax
0x18000b019  mov     r14d, eax
  ... truncated ...
```
