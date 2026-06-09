# CMsftIsoImageManager::Validate(void)

- ea: `0x1800072d0`
- end: `0x180007e74`
- name: `?Validate@CMsftIsoImageManager@@UEAAJXZ`
- size: `2980`
- prototype: `__int64 __fastcall(CMsftIsoImageManager *__hidden this)`
- caller_count: `0`
- callee_count: `28`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x180003580`
- `0x180003a20`
- `0x1800040b0`
- `0x1800048e0`
- `0x180005040`
- `0x1800063b8`
- `0x180007198`
- `0x18000726c`
- `0x1800072d0`
- `0x18000960c`
- `0x18000c8d0`
- `0x180011c48`
- `0x180018fdc`
- `0x1800199b8`
- `0x1800251dc`
- `0x180028568`
- `0x180028bb4`
- `0x18002ae5c`
- `0x18002ae9c`
- `0x18002aef0`
- `0x18002d4e4`
- `0x180041f24`
- `0x18004248c`
- `0x18004a8c8`
- `0x18004da48`
- `0x18008170e`
- `0x180081750`
- `0x180088010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180007561`
- `ole32!CoTaskMemFree` at `0x180007561`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CMsftIsoImageManager::Validate(CMsftIsoImageManager *this)
{
  __int64 v2; // rcx
  CIMAPIException *v3; // rax
  CIMAPIException *v4; // rax
  CIMAPIException *v5; // rbx
  int v6; // ebx
  CIMAPISystemException *v7; // rax
  CIMAPISystemException *v8; // rax
  CIMAPIException *v9; // rbx
  void *v10; // rax
  CIMAPIException *v11; // rax
  CIMAPIException *v12; // rax
  CIMAPIException *v13; // rbx
  CIMAPIException *v14; // rax
  CIMAPIException *v15; // rax
  CIMAPIException *v16; // rbx
  CIMAPIException *v17; // rax
  CIMAPIException *v18; // rax
  CIMAPIException *v19; // rbx
  int v20; // ebx
  CIMAPISystemException *v21; // rax
  CIMAPISystemException *v22; // rax
  CIMAPIException *v23; // rbx
  __int64 **v24; // rbx
  CIMAPISystemException *v25; // rax
  CIMAPISystemException *v26; // rax
  CIMAPIException *v27; // rbx
  CDiscReader *v28; // rax
  CDiscReader *v29; // rax
  char *v30; // rax
  char *v31; // r14
  __int64 *v32; // rcx
  __int64 v33; // rax
  int v34; // r14d
  int v35; // ebx
  CIMAPISystemException *v36; // rax
  CIMAPISystemException *v37; // rax
  CIMAPIException **v38; // rbx
  CIMAPIException *v39; // rax
  CIMAPIException *v40; // rax
  CIMAPIException **v41; // rbx
  __int64 *v42; // rcx
  int v43; // edx
  int v44; // edx
  int v45; // edx
  int v46; // edx
  int v47; // edx
  int v48; // edx
  CIMAPIException *v49; // rax
  CIMAPIException *v50; // rax
  CIMAPIException **v51; // rbx
  CIMAPIException *v53; // [rsp+40h] [rbp-848h] BYREF
  CIMAPIException **v54; // [rsp+48h] [rbp-840h] BYREF
  __int64 **v55; // [rsp+50h] [rbp-838h] BYREF
  CIMAPIException *pExceptionObject; // [rsp+58h] [rbp-830h] BYREF
  CIMAPIException *v57; // [rsp+60h] [rbp-828h] BYREF
  CIMAPIException *v58; // [rsp+68h] [rbp-820h] BYREF
  CIMAPIException *v59; // [rsp+70h] [rbp-818h] BYREF
  CIMAPIException *v60; // [rsp+78h] [rbp-810h] BYREF
  CIMAPIException *v61; // [rsp+80h] [rbp-808h] BYREF
  CIMAPIException *v62; // [rsp+88h] [rbp-800h] BYREF
  CIMAPIException **v63; // [rsp+90h] [rbp-7F8h] BYREF
  CIMAPIException **v64; // [rsp+98h] [rbp-7F0h] BYREF
  _QWORD v65[2]; // [rsp+A0h] [rbp-7E8h] BYREF
  char v66[8]; // [rsp+B0h] [rbp-7D8h] BYREF
  _BYTE v67[88]; // [rsp+B8h] [rbp-7D0h] BYREF
  _BYTE v68[88]; // [rsp+110h] [rbp-778h] BYREF
  _BYTE v69[88]; // [rsp+168h] [rbp-720h] BYREF
  _BYTE v70[88]; // [rsp+1C0h] [rbp-6C8h] BYREF
  _BYTE v71[88]; // [rsp+218h] [rbp-670h] BYREF
  _BYTE v72[88]; // [rsp+270h] [rbp-618h] BYREF
  _BYTE v73[88]; // [rsp+2C8h] [rbp-5C0h] BYREF
  _BYTE v74[88]; // [rsp+320h] [rbp-568h] BYREF
  _BYTE v75[88]; // [rsp+378h] [rbp-510h] BYREF
  _BYTE v76[96]; // [rsp+3D0h] [rbp-4B8h] BYREF
  _BYTE v77[144]; // [rsp+430h] [rbp-458h] BYREF
  LPVOID pv[2]; // [rsp+4C0h] [rbp-3C8h] BYREF
  unsigned __int64 v79; // [rsp+4D0h] [rbp-3B8h]
  _BYTE v80[816]; // [rsp+510h] [rbp-378h] BYREF

  memset_0(pv, 0, 0x50u);
  MethodTrace::MethodTrace((MethodTrace *)v66, "CMsftIsoImageManager::Validate");
  ImapiClearErrorInfo();
  v65[1] = (char *)this + 8;
  ImapiComObject::LockCS((CMsftIsoImageManager *)((char *)this + 8));
  try
  {
    v2 = *((_QWORD *)this + 17);
    if ( !v2 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 12, &WPP_d3f050a05e0c3b0048cc767be3a359fd_Traceguids);
      }
      v3 = (CIMAPIException *)operator new(0x58u);
      v53 = v3;
      if ( v3 )
        v4 = CIMAPIException::CIMAPIException(v3, -1062555134);
      else
        v4 = 0;
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v53, v4);
      v5 = v53;
      if ( v53 && *(_QWORD *)v53 )
      {
        CIMAPIException::SetCodeRefInfo(
          *(CIMAPIException **)v53,
          "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\isoimagemanager.cpp",
          147);
        pExceptionObject = v5;
        if ( v5 )
          ++*((_DWORD *)v5 + 2);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v67,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v67;
    }
    v6 = (*(__int64 (__fastcall **)(__int64, LPVOID *, __int64))(*(_QWORD *)v2 + 96LL))(v2, pv, 1);
    if ( v6 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 13, &WPP_d3f050a05e0c3b0048cc767be3a359fd_Traceguids);
      }
      v7 = (CIMAPISystemException *)operator new(0x58u);
      v53 = v7;
      if ( v7 )
        v8 = CIMAPISystemException::CIMAPISystemException(v7, v6);
      else
        v8 = 0;
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v53, v8);
      v9 = v53;
      if ( v53 && *(_QWORD *)v53 )
      {
        CIMAPIException::SetCodeRefInfo(
          *(CIMAPIException **)v53,
          "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\isoimagemanager.cpp",
          158);
        v57 = v9;
        if ( v9 )
          ++*((_DWORD *)v9 + 2);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&v57;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v68,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v68;
    }
    v10 = pv[0];
    if ( pv[0] )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 3u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 14, &WPP_d3f050a05e0c3b0048cc767be3a359fd_Traceguids);
        v10 = pv[0];
      }
      CoTaskMemFree(v10);
      pv[0] = 0;
    }
    if ( (v79 & 0x7FF) != 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
      {
        WPP_SF_iidD(*((_QWORD *)WPP_GLOBAL_Control + 7), v79, 2047, v79, v79, v79 & 0x7FF, v79 & 0x7FF);
      }
      v11 = (CIMAPIException *)operator new(0x58u);
      v53 = v11;
      if ( v11 )
        v12 = CIMAPIException::CIMAPIException(v11, -1062555136);
      else
        v12 = 0;
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v53, v12);
      v13 = v53;
      if ( v53 && *(_QWORD *)v53 )
      {
        CIMAPIException::SetCodeRefInfo(
          *(CIMAPIException **)v53,
          "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\isoimagemanager.cpp",
          181);
        v58 = v13;
        if ( v13 )
          ++*((_DWORD *)v13 + 2);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&v58;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v69,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v69;
    }
    if ( v79 >> 11 > 0x7FFFFFFF )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
      {
        WPP_SF_ii(*((_QWORD *)WPP_GLOBAL_Control + 7));
      }
      v14 = (CIMAPIException *)operator new(0x58u);
      v53 = v14;
      if ( v14 )
        v15 = CIMAPIException::CIMAPIException(v14, -1062555133);
      else
        v15 = 0;
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v53, v15);
      v16 = v53;
      if ( v53 && *(_QWORD *)v53 )
      {
        CIMAPIException::SetCodeRefInfo(
          *(CIMAPIException **)v53,
          "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\isoimagemanager.cpp",
          191);
        v59 = v16;
        if ( v16 )
          ++*((_DWORD *)v16 + 2);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&v59;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v70,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v70;
    }
    if ( !v79 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 17, &WPP_d3f050a05e0c3b0048cc767be3a359fd_Traceguids);
      }
      v17 = (CIMAPIException *)operator new(0x58u);
      v53 = v17;
      if ( v17 )
        v18 = CIMAPIException::CIMAPIException(v17, -1062555135);
      else
        v18 = 0;
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v53, v18);
      v19 = v53;
      if ( v53 && *(_QWORD *)v53 )
      {
        CIMAPIException::SetCodeRefInfo(
          *(CIMAPIException **)v53,
          "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\isoimagemanager.cpp",
          198);
        v60 = v19;
        if ( v19 )
          ++*((_DWORD *)v19 + 2);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&v60;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v71,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v71;
    }
    v55 = 0;
    v20 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64 ***))(**((_QWORD **)this + 17) + 40LL))(
            *((_QWORD *)this + 17),
            0,
            1,
            &v55);
    if ( v20 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 18, &WPP_d3f050a05e0c3b0048cc767be3a359fd_Traceguids);
      }
      v21 = (CIMAPISystemException *)operator new(0x58u);
      v53 = v21;
      if ( v21 )
        v22 = CIMAPISystemException::CIMAPISystemException(v21, v20);
      else
        v22 = 0;
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v53, v22);
      v23 = v53;
      if ( v53 && *(_QWORD *)v53 )
      {
        CIMAPIException::SetCodeRefInfo(
          *(CIMAPIException **)v53,
          "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\isoimagemanager.cpp",
          215);
        v61 = v23;
        if ( v23 )
          ++*((_DWORD *)v23 + 2);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&v61;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v72,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v72;
    }
    v24 = v55;
    if ( (unsigned __int64)v55 > 0x7FFFFFFFFFFFFFFFLL )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
      {
        WPP_SF_i(*((_QWORD *)WPP_GLOBAL_Control + 7), 19, &WPP_d3f050a05e0c3b0048cc767be3a359fd_Traceguids, v55);
      }
      v25 = (CIMAPISystemException *)operator new(0x58u);
      v53 = v25;
      if ( v25 )
        v26 = CIMAPISystemException::CIMAPISystemException(v25, -2147024673);
      else
        v26 = 0;
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v53, v26);
      v27 = v53;
      if ( v53 && *(_QWORD *)v53 )
      {
        CIMAPIException::SetCodeRefInfo(
          *(CIMAPIException **)v53,
          "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\isoimagemanager.cpp",
          223);
        v62 = v27;
        if ( v27 )
          ++*((_DWORD *)v27 + 2);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&v62;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v73,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v73;
    }
    FileSystemImage::FileSystemImage((FileSystemImage *)v80, 0);
    v28 = (CDiscReader *)operator new(0x30u);
    v53 = v28;
    if ( v28 )
      v29 = CDiscReader::CDiscReader(v28, *((struct IStream **)this + 17));
    else
      v29 = 0;
    SmartPtr<ImportMetadata>::SmartPtr<ImportMetadata>(&v53, v29);
    Iso9660FileSystemSupport::Iso9660FileSystemSupport((Iso9660FileSystemSupport *)v77, (struct FileSystemImage *)v80);
    v30 = (char *)operator new(0x810u);
    v31 = v30;
    if ( v30 )
    {
      *((_QWORD *)v30 + 1) = v77;
      *(_QWORD *)v30 = &VolumeRecognitionStructureBase::`vftable';
      v30[16] = 0;
      *(_DWORD *)(v30 + 17) = 0;
      *(_WORD *)(v30 + 21) = 0;
      memset_0(v30 + 23, 0, 0x7F9u);
    }
    else
    {
      v31 = 0;
    }
    SmartPtr<ImportMetadata>::SmartPtr<ImportMetadata>(&v55, v31);
    v32 = *v55;
    v33 = **v55;
    v54 = (CIMAPIException **)v53;
    if ( v53 )
      ++*((_DWORD *)v53 + 2);
    v34 = (*(__int64 (__fastcall **)(__int64 *, CIMAPIException ***, __int64))(v33 + 24))(v32, &v54, 16);
    v35 = (*(__int64 (__fastcall **)(_QWORD, __int64 **, _QWORD, _QWORD))(**((_QWORD **)this + 17) + 40LL))(
            *((_QWORD *)this + 17),
            v24,
            0,
            0);
    if ( v35 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 20, &WPP_d3f050a05e0c3b0048cc767be3a359fd_Traceguids);
      }
      v36 = (CIMAPISystemException *)operator new(0x58u);
      v54 = (CIMAPIException **)v36;
      if ( v36 )
        v37 = CIMAPISystemException::CIMAPISystemException(v36, v35);
      else
        v37 = 0;
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v54, v37);
      v38 = v54;
      if ( v54 && *v54 )
      {
        CIMAPIException::SetCodeRefInfo(
          *v54,
          "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\isoimagemanager.cpp",
          254);
        v63 = v38;
        if ( v38 )
          ++*((_DWORD *)v38 + 2);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&v63;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v74,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v74;
    }
    if ( v34 != 2048 )
    {
      v39 = (CIMAPIException *)operator new(0x58u);
      v54 = (CIMAPIException **)v39;
      if ( v39 )
        v40 = CIMAPIException::CIMAPIException(v39, -1062555305);
      else
        v40 = 0;
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v54, v40);
      v41 = v54;
      if ( v54 && *v54 )
      {
        CIMAPIException::SetCodeRefInfo(
          *v54,
          "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\isoimagemanager.cpp",
          261);
        v64 = v41;
        if ( v41 )
          ++*((_DWORD *)v41 + 2);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&v64;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v75,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v75;
    }
    v42 = *v55;
    v43 = *(_DWORD *)((char *)*v55 + 17) - 809583938;
    if ( *(_DWORD *)((char *)*v55 + 17) == 809583938 )
      v43 = *((unsigned __int8 *)v42 + 21) - 49;
    if ( v43 )
    {
      v44 = *(_DWORD *)((char *)v42 + 17) - 809583956;
      if ( *(_DWORD *)((char *)v42 + 17) == 809583956 )
        v44 = *((unsigned __int8 *)v42 + 21) - 49;
      if ( v44 )
      {
        v45 = *(_DWORD *)((char *)v42 + 17) - 1414483778;
        if ( *(_DWORD *)((char *)v42 + 17) == 1414483778 )
          v45 = *((unsigned __int8 *)v42 + 21) - 50;
        if ( v45 )
        {
          v46 = *(_DWORD *)((char *)v42 + 17) - 808469571;
          if ( *(_DWORD *)((char *)v42 + 17) == 808469571 )
            v46 = *((unsigned __int8 *)v42 + 21) - 49;
          if ( v46 )
          {
            v47 = *(_DWORD *)((char *)v42 + 17) - 811025475;
            if ( *(_DWORD *)((char *)v42 + 17) == 811025475 )
              v47 = *((unsigned __int8 *)v42 + 21) - 50;
            if ( v47 )
            {
              v48 = *(_DWORD *)((char *)v42 + 17) - 810701646;
              if ( *(_DWORD *)((char *)v42 + 17) == 810701646 )
                v48 = *((unsigned __int8 *)v42 + 21) - 50;
              if ( v48 )
              {
                v49 = (CIMAPIException *)operator new(0x58u);
                v54 = (CIMAPIException **)v49;
                if ( v49 )
                  v50 = CIMAPIException::CIMAPIException(v49, -1062555135);
                else
                  v50 = 0;
                SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v54, v50);
                v51 = v54;
                if ( v54 && *v54 )
                {
                  CIMAPIException::SetCodeRefInfo(
                    *v54,
                    "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\isoimagemanager.cpp",
                    278);
                  v65[0] = v51;
                  if ( v51 )
                    ++*((_DWORD *)v51 + 2);
                  throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)v65;
                }
                CIMAPIException::CIMAPIException(
                  (CIMAPIException *)v76,
                  (const struct CIMAPIException *)&CIMAPIException::badAlloc);
                throw (CIMAPIException *)v76;
              }
            }
          }
        }
      }
    }
    SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&v55);
    Iso9660FileSystemSupport::~Iso9660FileSystemSupport((Iso9660FileSystemSupport *)v77);
    SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&v53);
    FileSystemImage::~FileSystemImage((FileSystemImage *)v80);
  }
  catch ( ... )
  {
    ExceptionDispatcher(&CLSID_MsftIsoImageManager);
  }
  ImapiComObject::UnlockCS((CMsftIsoImageManager *)((char *)this + 8));
  MethodTrace::~MethodTrace((MethodTrace *)v66);
  return 0;
}

```

## disassembly

```asm
0x1800072d0  push    rbx
0x1800072d2  push    rdi
0x1800072d3  push    r12
0x1800072d5  push    r13
0x1800072d7  push    r14
0x1800072d9  push    r15
0x1800072db  sub     rsp, 858h
0x1800072e2  mov     rax, cs:__security_cookie
0x1800072e9  xor     rax, rsp
0x1800072ec  mov     [rsp+888h+var_48], rax
0x1800072f4  mov     r15, rcx
0x1800072f7  xor     edx, edx; Val
0x1800072f9  lea     r8d, [rdx+50h]; Size
0x1800072fd  lea     rcx, [rsp+888h+pv]; void *
0x180007305  call    memset_0
0x18000730a  lea     rdx, aCmsftisoimagem_1; "CMsftIsoImageManager::Validate"
0x180007311  lea     rcx, [rsp+888h+var_7D8]; this
0x180007319  call    ??0MethodTrace@@QEAA@PEBD@Z; MethodTrace::MethodTrace(char const *)
0x18000731e  nop
0x18000731f  call    ?ImapiClearErrorInfo@@YAXXZ; ImapiClearErrorInfo(void)
0x180007324  nop
0x180007325  lea     r12, [r15+8]
0x180007329  mov     [rsp+888h+var_7E0], r12
0x180007331  mov     rcx, r12; this
0x180007334  call    ?LockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::LockCS(void)
0x180007339  mov     rcx, [r15+88h]
0x180007340  xor     r13d, r13d
0x180007343  test    rcx, rcx
0x180007346  jnz     loc_18000741E
0x18000734c  lea     rdi, WPP_GLOBAL_Control
0x180007353  mov     rcx, cs:WPP_GLOBAL_Control
0x18000735a  cmp     rcx, rdi
0x18000735d  jz      short loc_18000737F
0x18000735f  test    byte ptr [rcx+44h], 4
0x180007363  jz      short loc_18000737F
0x180007365  cmp     byte ptr [rcx+41h], 2
0x180007369  jb      short loc_18000737F
0x18000736b  lea     edx, [r13+0Ch]
0x18000736f  lea     r8, WPP_d3f050a05e0c3b0048cc767be3a359fd_Traceguids
0x180007376  mov     rcx, [rcx+38h]
0x18000737a  call    WPP_SF_
0x18000737f  mov     ecx, 58h ; 'X'; unsigned __int64
0x180007384  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007389  mov     [rsp+888h+var_848], rax
0x18000738e  test    rax, rax
0x180007391  jz      short loc_1800073A2
0x180007393  mov     edx, 0C0AAB202h; int
0x180007398  mov     rcx, rax; this
0x18000739b  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x1800073a0  jmp     short loc_1800073A5
0x1800073a2  mov     rax, r13
0x1800073a5  mov     rdx, rax
0x1800073a8  lea     rcx, [rsp+888h+var_848]
0x1800073ad  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x1800073b2  nop
0x1800073b3  mov     rbx, [rsp+888h+var_848]
0x1800073b8  test    rbx, rbx
0x1800073bb  jz      short loc_1800073F5
0x1800073bd  cmp     [rbx], r13
0x1800073c0  jz      short loc_1800073F5
0x1800073c2  mov     r8d, 93h; int
0x1800073c8  lea     rdx, aDriversStorage_8; "drivers\\storage\\imapi2\\filesystemima"...
0x1800073cf  mov     rcx, [rbx]; this
0x1800073d2  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x1800073d7  mov     [rsp+888h+pExceptionObject], rbx
0x1800073dc  test    rbx, rbx
0x1800073df  jz      short loc_1800073E4
0x1800073e1  inc     dword ptr [rbx+8]
0x1800073e4  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x1800073eb  lea     rcx, [rsp+888h+pExceptionObject]; pExceptionObject
0x1800073f0  call    _CxxThrowException_0
0x1800073f5  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x1800073fc  lea     rcx, [rsp+888h+var_7D0]; this
0x180007404  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x180007409  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x180007410  lea     rcx, [rsp+888h+var_7D0]; pExceptionObject
0x180007418  call    _CxxThrowException_0
0x18000741e  mov     rax, [rcx]
0x180007421  mov     r8d, 1
0x180007427  lea     rdx, [rsp+888h+pv]
0x18000742f  mov     rax, [rax+60h]
0x180007433  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007438  mov     ebx, eax
0x18000743a  test    eax, eax
0x18000743c  jns     loc_180007515
0x180007442  lea     rdi, WPP_GLOBAL_Control
0x180007449  mov     rcx, cs:WPP_GLOBAL_Control
0x180007450  cmp     rcx, rdi
0x180007453  jz      short loc_180007479
0x180007455  test    byte ptr [rcx+44h], 4
0x180007459  jz      short loc_180007479
0x18000745b  cmp     byte ptr [rcx+41h], 2
0x18000745f  jb      short loc_180007479
0x180007461  mov     edx, 0Dh
0x180007466  mov     r9d, eax
0x180007469  lea     r8, WPP_d3f050a05e0c3b0048cc767be3a359fd_Traceguids
0x180007470  mov     rcx, [rcx+38h]
0x180007474  call    WPP_SF_d
0x180007479  mov     ecx, 58h ; 'X'; unsigned __int64
0x18000747e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007483  mov     [rsp+888h+var_848], rax
0x180007488  test    rax, rax
0x18000748b  jz      short loc_180007499
0x18000748d  mov     edx, ebx; int
0x18000748f  mov     rcx, rax; this
0x180007492  call    ??0CIMAPISystemException@@QEAA@JZZ; CIMAPISystemException::CIMAPISystemException(long,...)
0x180007497  jmp     short loc_18000749C
0x180007499  mov     rax, r13
0x18000749c  mov     rdx, rax
0x18000749f  lea     rcx, [rsp+888h+var_848]
0x1800074a4  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x1800074a9  nop
0x1800074aa  mov     rbx, [rsp+888h+var_848]
0x1800074af  test    rbx, rbx
0x1800074b2  jz      short loc_1800074EC
0x1800074b4  cmp     [rbx], r13
0x1800074b7  jz      short loc_1800074EC
0x1800074b9  mov     r8d, 9Eh; int
0x1800074bf  lea     rdx, aDriversStorage_8; "drivers\\storage\\imapi2\\filesystemima"...
0x1800074c6  mov     rcx, [rbx]; this
0x1800074c9  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x1800074ce  mov     [rsp+888h+var_828], rbx
0x1800074d3  test    rbx, rbx
0x1800074d6  jz      short loc_1800074DB
0x1800074d8  inc     dword ptr [rbx+8]
0x1800074db  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x1800074e2  lea     rcx, [rsp+888h+var_828]; pExceptionObject
0x1800074e7  call    _CxxThrowException_0
0x1800074ec  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x1800074f3  lea     rcx, [rsp+888h+var_778]; this
0x1800074fb  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x180007500  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x180007507  lea     rcx, [rsp+888h+var_778]; pExceptionObject
0x18000750f  call    _CxxThrowException_0
0x180007515  mov     rax, [rsp+888h+pv]
0x18000751d  test    rax, rax
0x180007520  jz      short loc_180007571
0x180007522  lea     rdi, WPP_GLOBAL_Control
0x180007529  mov     rcx, cs:WPP_GLOBAL_Control
0x180007530  cmp     rcx, rdi
0x180007533  jz      short loc_18000755E
0x180007535  test    byte ptr [rcx+44h], 4
0x180007539  jz      short loc_18000755E
0x18000753b  cmp     byte ptr [rcx+41h], 3
0x18000753f  jb      short loc_18000755E
0x180007541  mov     edx, 0Eh
0x180007546  lea     r8, WPP_d3f050a05e0c3b0048cc767be3a359fd_Traceguids
0x18000754d  mov     rcx, [rcx+38h]
0x180007551  call    WPP_SF_
0x180007556  mov     rax, [rsp+888h+pv]
0x18000755e  mov     rcx, rax; pv
0x180007561  call    cs:__imp_CoTaskMemFree
0x180007567  mov     [rsp+888h+pv], r13
0x18000756f  jmp     short loc_180007578
0x180007571  lea     rdi, WPP_GLOBAL_Control
0x180007578  mov     rdx, [rsp+888h+var_3B8]
0x180007580  mov     r8d, 7FFh
0x180007586  test    r8, rdx
0x180007589  jz      loc_180007664
0x18000758f  mov     rcx, cs:WPP_GLOBAL_Control
0x180007596  cmp     rcx, rdi
0x180007599  jz      short loc_1800075C5
0x18000759b  test    byte ptr [rcx+44h], 4
0x18000759f  jz      short loc_1800075C5
0x1800075a1  cmp     byte ptr [rcx+41h], 2
0x1800075a5  jb      short loc_1800075C5
0x1800075a7  mov     eax, edx
0x1800075a9  and     eax, r8d
0x1800075ac  mov     [rsp+888h+var_858], eax
0x1800075b0  mov     [rsp+888h+var_860], eax
0x1800075b4  mov     [rsp+888h+var_868], rdx
0x1800075b9  mov     r9, rdx
0x1800075bc  mov     rcx, [rcx+38h]
0x1800075c0  call    WPP_SF_iidD
0x1800075c5  mov     ecx, 58h ; 'X'; unsigned __int64
0x1800075ca  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800075cf  mov     [rsp+888h+var_848], rax
0x1800075d4  test    rax, rax
0x1800075d7  jz      short loc_1800075E8
0x1800075d9  mov     edx, 0C0AAB200h; int
0x1800075de  mov     rcx, rax; this
0x1800075e1  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x1800075e6  jmp     short loc_1800075EB
0x1800075e8  mov     rax, r13
0x1800075eb  mov     rdx, rax
0x1800075ee  lea     rcx, [rsp+888h+var_848]
0x1800075f3  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x1800075f8  nop
0x1800075f9  mov     rbx, [rsp+888h+var_848]
0x1800075fe  test    rbx, rbx
0x180007601  jz      short loc_18000763B
0x180007603  cmp     [rbx], r13
0x180007606  jz      short loc_18000763B
0x180007608  mov     r8d, 0B5h; int
0x18000760e  lea     rdx, aDriversStorage_8; "drivers\\storage\\imapi2\\filesystemima"...
0x180007615  mov     rcx, [rbx]; this
0x180007618  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18000761d  mov     [rsp+888h+var_820], rbx
0x180007622  test    rbx, rbx
0x180007625  jz      short loc_18000762A
0x180007627  inc     dword ptr [rbx+8]
0x18000762a  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x180007631  lea     rcx, [rsp+888h+var_820]; pExceptionObject
0x180007636  call    _CxxThrowException_0
0x18000763b  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x180007642  lea     rcx, [rsp+888h+var_720]; this
0x18000764a  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18000764f  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x180007656  lea     rcx, [rsp+888h+var_720]; pExceptionObject
0x18000765e  call    _CxxThrowException_0
0x180007664  mov     r9, rdx
0x180007667  shr     r9, 0Bh
0x18000766b  cmp     r9, 7FFFFFFFh
0x180007672  jbe     loc_18000773D
0x180007678  mov     rcx, cs:WPP_GLOBAL_Control
0x18000767f  cmp     rcx, rdi
0x180007682  jz      short loc_18000769E
0x180007684  test    byte ptr [rcx+44h], 4
0x180007688  jz      short loc_18000769E
0x18000768a  cmp     byte ptr [rcx+41h], 2
0x18000768e  jb      short loc_18000769E
0x180007690  mov     [rsp+888h+var_868], r9
0x180007695  mov     rcx, [rcx+38h]
0x180007699  call    WPP_SF_ii
0x18000769e  mov     ecx, 58h ; 'X'; unsigned __int64
0x1800076a3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800076a8  mov     [rsp+888h+var_848], rax
0x1800076ad  test    rax, rax
0x1800076b0  jz      short loc_1800076C1
0x1800076b2  mov     edx, 0C0AAB203h; int
0x1800076b7  mov     rcx, rax; this
0x1800076ba  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x1800076bf  jmp     short loc_1800076C4
0x1800076c1  mov     rax, r13
0x1800076c4  mov     rdx, rax
0x1800076c7  lea     rcx, [rsp+888h+var_848]
0x1800076cc  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x1800076d1  nop
0x1800076d2  mov     rbx, [rsp+888h+var_848]
0x1800076d7  test    rbx, rbx
0x1800076da  jz      short loc_180007714
0x1800076dc  cmp     [rbx], r13
0x1800076df  jz      short loc_180007714
0x1800076e1  mov     r8d, 0BFh; int
0x1800076e7  lea     rdx, aDriversStorage_8; "drivers\\storage\\imapi2\\filesystemima"...
0x1800076ee  mov     rcx, [rbx]; this
0x1800076f1  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x1800076f6  mov     [rsp+888h+var_818], rbx
0x1800076fb  test    rbx, rbx
0x1800076fe  jz      short loc_180007703
0x180007700  inc     dword ptr [rbx+8]
0x180007703  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18000770a  lea     rcx, [rsp+888h+var_818]; pExceptionObject
0x18000770f  call    _CxxThrowException_0
0x180007714  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18000771b  lea     rcx, [rsp+888h+var_6C8]; this
0x180007723  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x180007728  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18000772f  lea     rcx, [rsp+888h+var_6C8]; pExceptionObject
0x180007737  call    _CxxThrowException_0
0x18000773d  test    rdx, rdx
0x180007740  jnz     loc_180007812
0x180007746  mov     rcx, cs:WPP_GLOBAL_Control
0x18000774d  cmp     rcx, rdi
0x180007750  jz      short loc_180007773
0x180007752  test    byte ptr [rcx+44h], 4
0x180007756  jz      short loc_180007773
0x180007758  cmp     byte ptr [rcx+41h], 2
0x18000775c  jb      short loc_180007773
0x18000775e  mov     edx, 11h
0x180007763  lea     r8, WPP_d3f050a05e0c3b0048cc767be3a359fd_Traceguids
0x18000776a  mov     rcx, [rcx+38h]
0x18000776e  call    WPP_SF_
0x180007773  mov     ecx, 58h ; 'X'; unsigned __int64
0x180007778  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000777d  mov     [rsp+888h+var_848], rax
0x180007782  test    rax, rax
0x180007785  jz      short loc_180007796
0x180007787  mov     edx, 0C0AAB201h; int
0x18000778c  mov     rcx, rax; this
0x18000778f  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x180007794  jmp     short loc_180007799
0x180007796  mov     rax, r13
0x180007799  mov     rdx, rax
0x18000779c  lea     rcx, [rsp+888h+var_848]
0x1800077a1  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x1800077a6  nop
0x1800077a7  mov     rbx, [rsp+888h+var_848]
0x1800077ac  test    rbx, rbx
0x1800077af  jz      short loc_1800077E9
0x1800077b1  cmp     [rbx], r13
0x1800077b4  jz      short loc_1800077E9
0x1800077b6  mov     r8d, 0C6h; int
0x1800077bc  lea     rdx, aDriversStorage_8; "drivers\\storage\\imapi2\\filesystemima"...
0x1800077c3  mov     rcx, [rbx]; this
0x1800077c6  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x1800077cb  mov     [rsp+888h+var_810], rbx
0x1800077d0  test    rbx, rbx
0x1800077d3  jz      short loc_1800077D8
0x1800077d5  inc     dword ptr [rbx+8]
  ... truncated ...
```
