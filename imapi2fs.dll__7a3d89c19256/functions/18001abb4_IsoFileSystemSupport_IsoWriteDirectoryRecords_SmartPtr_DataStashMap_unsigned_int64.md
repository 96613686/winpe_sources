# IsoFileSystemSupport::IsoWriteDirectoryRecords(SmartPtr<DataStashMap>,unsigned __int64)

- ea: `0x18001abb4`
- end: `0x18001b646`
- name: `?IsoWriteDirectoryRecords@IsoFileSystemSupport@@IEAAXV?$SmartPtr@VDataStashMap@@@@_K@Z`
- size: `2706`
- prototype: `__int64 __fastcall(FileSystemSupport *this)`
- caller_count: `1`
- callee_count: `38`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18004cfd0`

## callees

- `0x180003580`
- `0x180003a20`
- `0x180003f50`
- `0x180005040`
- `0x180007104`
- `0x18000960c`
- `0x18000c888`
- `0x18000c8d0`
- `0x18000d1c0`
- `0x18000f4b0`
- `0x18000f5b4`
- `0x180016fa4`
- `0x180017090`
- `0x1800170c8`
- `0x1800180e8`
- `0x18001abb4`
- `0x18001b7bc`
- `0x18001ce58`
- `0x1800251dc`
- `0x180028568`
- `0x18002d4e4`
- `0x18002dba4`
- `0x18002dc70`
- `0x18002dec8`
- `0x18002eeec`
- `0x1800304c0`
- `0x180030828`
- `0x18003239c`
- `0x180039210`
- `0x18003935c`
- `0x180049f40`
- `0x18004af6c`
- `0x18004d438`
- `0x18004d584`
- `0x18005266c`
- `0x1800816e6`
- `0x18008170e`
- `0x180088010`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall IsoFileSystemSupport::IsoWriteDirectoryRecords(
        CIMAPIException **this,
        DataStashMap ***a2,
        __int64 a3)
{
  FileSystemSupport *v3; // r13
  PVOID *v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // r14
  void *v7; // rax
  unsigned int v8; // r12d
  unsigned __int8 **v9; // rbx
  unsigned __int8 *v10; // rcx
  _DWORD *v11; // rdi
  __int64 v12; // rsi
  unsigned int v13; // eax
  unsigned __int8 *v14; // r9
  unsigned __int8 *v15; // r8
  unsigned int v16; // eax
  unsigned __int8 *v17; // r9
  unsigned __int8 *v18; // r8
  __int64 i; // rcx
  int v20; // r15d
  __int64 v21; // rax
  char *j; // rsi
  void (__fastcall **v23)(FileSystemSupport *, unsigned __int8 *, __int64, __int64); // rdi
  __int64 v24; // rcx
  __int64 v25; // r12
  unsigned __int64 v26; // rax
  unsigned __int64 v27; // rdx
  int v28; // eax
  unsigned int v29; // r9d
  unsigned __int8 *v30; // r8
  unsigned __int64 v31; // rcx
  unsigned __int64 v32; // rax
  unsigned int v33; // edx
  __int64 v34; // rcx
  unsigned __int64 v35; // r14
  unsigned __int64 v36; // rcx
  int v37; // r9d
  unsigned __int8 *v38; // r8
  __int64 v39; // r13
  int v40; // r14d
  CIMAPIException **v41; // r15
  void (__fastcall *v42)(FileSystemSupport *, unsigned __int8 *, _QWORD, __int64); // r12
  __int64 v43; // r15
  int v44; // r14d
  unsigned __int8 v45; // al
  unsigned int v46; // eax
  unsigned __int8 *v47; // r9
  unsigned __int8 *v48; // r8
  int v49; // r14d
  __int64 v50; // r14
  __int64 v51; // rdx
  __int64 v52; // r15
  int v53; // r14d
  __int64 v54; // r8
  __int64 v55; // r15
  int v56; // r14d
  __int64 v57; // r8
  int v58; // r15d
  __int64 v59; // rcx
  CIMAPIException *v60; // rax
  CIMAPIException **v61; // rbx
  __int64 v62; // rcx
  void *v63; // rbx
  unsigned int v65; // [rsp+30h] [rbp-D0h]
  int v66; // [rsp+34h] [rbp-CCh]
  __int64 v67; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v68; // [rsp+40h] [rbp-C0h]
  __int64 v69; // [rsp+48h] [rbp-B8h]
  void (__fastcall **v70)(FileSystemSupport *, unsigned __int8 *, __int64, __int64); // [rsp+50h] [rbp-B0h] BYREF
  _DWORD *v71; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v72[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v73; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int8 **v74; // [rsp+80h] [rbp-80h] BYREF
  char *v75; // [rsp+88h] [rbp-78h] BYREF
  void *v76[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v77; // [rsp+A0h] [rbp-60h]
  char v78[8]; // [rsp+A8h] [rbp-58h] BYREF
  char v79[8]; // [rsp+B0h] [rbp-50h] BYREF
  char v80[8]; // [rsp+B8h] [rbp-48h] BYREF
  char v81[8]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v82; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v83; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v84; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v85[160]; // [rsp+100h] [rbp+0h] BYREF
  CIMAPIException **v86; // [rsp+1B0h] [rbp+B0h] BYREF
  DataStashMap ***v87; // [rsp+1B8h] [rbp+B8h]
  __int64 v88; // [rsp+1C0h] [rbp+C0h]
  CIMAPIException **pExceptionObject; // [rsp+1C8h] [rbp+C8h] BYREF

  v88 = a3;
  v87 = a2;
  v86 = this;
  v3 = (FileSystemSupport *)this;
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 41, &WPP_0f921ac20c883071ccb82ce92dc0d426_Traceguids);
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 68) & 4) != 0 && *((_BYTE *)v4 + 65) >= 4u )
      WPP_SF_SD((unsigned int)v4[7], 42, a3, *((_QWORD *)v3 + 1), *((_DWORD *)v3 + 21));
  }
  v5 = *(_QWORD *)(*((_QWORD *)v3 + 6) + 704LL);
  pExceptionObject = (CIMAPIException **)v5;
  if ( v5 )
    ++*(_DWORD *)(v5 + 8);
  CFsiStashFile::BlockSeek(*(CFsiStashFile **)v5, *((_DWORD *)v3 + 21));
  SmartPtr<CFsiStashFile>::~SmartPtr<CFsiStashFile>(&pExceptionObject);
  SmartClassPtr<ImapiFsObjectBase,ImapiImplementation>::SmartClassPtr<ImapiFsObjectBase,ImapiImplementation>(v72);
  LODWORD(v6) = (*(__int64 (__fastcall **)(FileSystemSupport *))(*(_QWORD *)v3 + 128LL))(v3);
  v66 = v6;
  *(_OWORD *)v76 = 0;
  v77 = 0;
  v7 = operator new(0x800u);
  SmartArrayPtr<unsigned char>::SmartArrayPtr<unsigned char>(&v74, v7);
  v8 = 0;
  v9 = v74;
  while ( 2 )
  {
    v65 = v8;
    if ( v8 >= *(_DWORD *)(*((_QWORD *)v3 + 6) + 368LL) )
      goto LABEL_71;
    if ( v9 )
      v10 = *v9;
    else
      v10 = 0;
    memset_0(v10, 0, 0x800u);
    v11 = *(_DWORD **)(**(_QWORD **)IsoFileSystemSupport::GetPathTable(v3, v78) + 8LL * (int)v8);
    v71 = v11;
    if ( v11 )
      ++v11[2];
    SmartArrayPtr<SmartClassPtr<CStreamROBase,ImapiImplementation>>::~SmartArrayPtr<SmartClassPtr<CStreamROBase,ImapiImplementation>>(v78);
    v12 = _RTDynamicCast_0(
            *(_QWORD *)(*(_QWORD *)v11 + 72LL),
            0,
            &ImapiFsObjectBase `RTTI Type Descriptor',
            &ImapiDirectoryInfo `RTTI Type Descriptor',
            0);
    **v9 = 34;
    v6 = (int)v6;
    v68 = v6;
    v13 = FileSystemSupport::DiscRelativeBlock(v3, *(_DWORD *)(*(_QWORD *)v11 + 4LL * (int)v6 + 780));
    v14 = *v9;
    *(_DWORD *)(v14 + 2) = v13;
    v14[6] = HIBYTE(v13);
    v14[7] = BYTE2(v13);
    v14[8] = BYTE1(v13);
    v14[9] = v13;
    LODWORD(v14) = *(_DWORD *)(*(_QWORD *)v11 + 4LL * (int)v6 + 140);
    v15 = *v9;
    *((_WORD *)v15 + 5) = (_WORD)v14;
    v15[12] = BYTE2(v14);
    v15[13] = BYTE3(v14);
    v15[14] = BYTE3(v14);
    v15[15] = BYTE2(v14);
    v15[16] = BYTE1(v14);
    v15[17] = (unsigned __int8)v14;
    ImapiFsObjectBase::ExportLastModifiedTime(*(_QWORD *)v11, &v82);
    v73 = v82;
    Utility::SetDateTimeIso915(*v9 + 18, &v73);
    (*v9)[25] = 2;
    if ( *(_BYTE *)(*(_QWORD *)v11 + 177LL) == 1 )
      (*v9)[25] |= 1u;
    Utility::Set16BitDualFormatNumber(*v9 + 28, 1u);
    (*v9)[32] = 1;
    (*v9)[34] = 34;
    v16 = FileSystemSupport::DiscRelativeBlock(v3, *(_DWORD *)(v12 + 4LL * (int)v6 + 780));
    v17 = *v9;
    *((_DWORD *)v17 + 9) = v16;
    v17[40] = HIBYTE(v16);
    v17[41] = BYTE2(v16);
    v17[42] = BYTE1(v16);
    v17[43] = v16;
    LODWORD(v17) = *(_DWORD *)(v12 + 4LL * (int)v6 + 140);
    v18 = *v9;
    *((_WORD *)v18 + 22) = (_WORD)v17;
    v18[46] = BYTE2(v17);
    v18[47] = BYTE3(v17);
    v18[48] = BYTE3(v17);
    v18[49] = BYTE2(v17);
    v18[50] = BYTE1(v17);
    v18[51] = (unsigned __int8)v17;
    ImapiFsObjectBase::ExportLastModifiedTime(v12, &v83);
    v73 = v83;
    Utility::SetDateTimeIso915(*v9 + 52, &v73);
    (*v9)[59] = 2;
    if ( *(_BYTE *)(*(_QWORD *)v11 + 177LL) == 1 )
      (*v9)[59] |= 1u;
    Utility::Set16BitDualFormatNumber(*v9 + 62, 1u);
    for ( i = 0; i != 2; ++i )
      (*v9)[i + 66] = 1;
    if ( !FileSystemSupport::include(v3) )
    {
LABEL_57:
      v59 = *(_QWORD *)(*((_QWORD *)v3 + 6) + 704LL);
      pExceptionObject = (CIMAPIException **)v59;
      if ( v59 )
        ++*(_DWORD *)(v59 + 8);
      CFsiStashFile::Write(*(CFsiStashFile **)v59, *v9, 0x800u, 0xFFFFFFFFFFFFFFFFuLL);
      SmartPtr<CFsiStashFile>::~SmartPtr<CFsiStashFile>(&pExceptionObject);
      goto LABEL_60;
    }
    v20 = 68;
    LODWORD(pExceptionObject) = 68;
    v21 = SmartClassPtr<ImapiDirectoryInfo,ImapiImplementation>::Pointer(&v71);
    IsoFileSystemSupport::SortDirectoryChildren(v3, v21, v76);
    for ( j = (char *)v76[0]; j != v76[1]; j += 8 )
    {
      SmartPtr<ImportMetadata>::operator=(v72, j);
      v23 = (void (__fastcall **)(FileSystemSupport *, unsigned __int8 *, __int64, __int64))v72[0];
      if ( (unsigned int)(v20 + *(_DWORD *)(*(_QWORD *)v72[0] + 4 * v6 + 128)) >= 0x800 )
      {
        v24 = *(_QWORD *)(*((_QWORD *)v3 + 6) + 704LL);
        pExceptionObject = (CIMAPIException **)v24;
        if ( v24 )
          ++*(_DWORD *)(v24 + 8);
        CFsiStashFile::Write(*(CFsiStashFile **)v24, *v9, 0x800u, 0xFFFFFFFFFFFFFFFFuLL);
        SmartPtr<CFsiStashFile>::~SmartPtr<CFsiStashFile>(&pExceptionObject);
        memset_0(*v9, 0, 0x800u);
        v20 = 0;
        LODWORD(pExceptionObject) = 0;
      }
      v25 = v20;
      v69 = v20;
      (*v9)[v20] = *((_BYTE *)*v23 + 4 * v6 + 128);
      v26 = (unsigned __int64)*v23;
      if ( *((_DWORD *)*v23 + 14) && *(_DWORD *)(v26 + 56) != 3 )
      {
        v70 = v23;
        if ( v23 )
          ++*((_DWORD *)v23 + 2);
        v27 = v26;
        v28 = *(_DWORD *)(v26 + 244);
        if ( v28 == 1 )
        {
          v29 = *(_DWORD *)(v27 + 248);
          v30 = *v9;
          *(_DWORD *)&v30[v20 + 2] = v29;
          LODWORD(v27) = v29 >> 8;
          LODWORD(v31) = HIWORD(v29);
          LODWORD(v32) = HIBYTE(v29);
          v30[v20 + 9] = v29;
LABEL_46:
          v30[v20 + 8] = v27;
          v30[v20 + 7] = v31;
          v30[v20 + 6] = v32;
          v37 = *((_DWORD *)*v23 + 64);
          v38 = *v9;
          *(_DWORD *)&v38[v20 + 10] = v37;
          v38[v20 + 14] = HIBYTE(v37);
          v38[v20 + 15] = BYTE2(v37);
          v38[v20 + 16] = BYTE1(v37);
          v38[v20 + 17] = v37;
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v67);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
            &v67,
            L"%s;%u",
            *((_QWORD *)*v23 + v6 + 13),
            *((unsigned int *)*v23 + 60));
          v39 = v67;
          v40 = *(_DWORD *)(v67 - 16);
          v41 = v86;
          (*v9)[v25 + 32] = v40 * (*((__int64 (__fastcall **)(CIMAPIException **))*v86 + 20))(v86);
          v42 = (void (__fastcall *)(FileSystemSupport *, unsigned __int8 *, _QWORD, __int64))*((_QWORD *)*v41 + 21);
          v75 = v79;
          v43 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                  v79,
                  &v67);
          v44 = *(_DWORD *)(v39 - 16);
          v3 = (FileSystemSupport *)v86;
          v45 = (*((__int64 (__fastcall **)(CIMAPIException **))*v86 + 20))(v86);
          v42(v3, &(*v9)[(int)pExceptionObject + 33], v44 * (unsigned int)v45, v43);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v67);
          SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&v70);
          v25 = v69;
          goto LABEL_53;
        }
        if ( v28 == 2 )
        {
          v33 = DataStashMap::LogicalBlockAddress(**v87, *(_DWORD *)(v27 + 248));
          goto LABEL_41;
        }
        v34 = 0;
        if ( v28 == 3 )
        {
          v33 = *(_DWORD *)(*((_QWORD *)v3 + 6) + 696LL) + *(_DWORD *)(v27 + 248);
LABEL_41:
          v34 = FileSystemSupport::DiscRelativeBlock(v3, v33);
        }
        v35 = v34 + v88;
        if ( (unsigned __int64)(v34 + v88) > 0xFFFFFFFF
          || (v36 = *((_QWORD *)*v23 + 32), v36 > 0x80000000)
          || v35 + Utility::BytesToRequiredSectors(v36) > 0xFFFFFFFF )
        {
          v60 = (CIMAPIException *)operator new(0x58u);
          v86 = (CIMAPIException **)v60;
          if ( v60 )
            v60 = CIMAPIException::CIMAPIException(v60, -1062555342, L"ISO9660/Joliet");
          SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v86, v60);
          v61 = v86;
          if ( v86 && *v86 )
          {
            CIMAPIException::SetCodeRefInfo(*v86, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsifs.cpp", 986);
            pExceptionObject = v61;
            if ( v61 )
              ++*((_DWORD *)v61 + 2);
            throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
          }
          CIMAPIException::CIMAPIException(
            (CIMAPIException *)v85,
            (const struct CIMAPIException *)&CIMAPIException::badAlloc);
          throw (CIMAPIException *)v85;
        }
        v30 = *v9;
        v30[v20 + 2] = v35;
        v27 = v35 >> 8;
        v30[v20 + 3] = BYTE1(v35);
        v31 = v35 >> 16;
        v30[v20 + 4] = BYTE2(v35);
        v32 = v35 >> 24;
        v30[v20 + 5] = BYTE3(v35);
        v30[v20 + 9] = v35;
        v6 = v68;
        goto LABEL_46;
      }
      (*v9)[v20 + 25] |= 2u;
      v75 = (char *)v23;
      if ( v23 )
        ++*((_DWORD *)v23 + 2);
      v46 = FileSystemSupport::DiscRelativeBlock(v3, *((_DWORD *)*v23 + v6 + 195));
      v47 = *v9;
      *(_DWORD *)&v47[v20 + 2] = v46;
      v47[v20 + 6] = HIBYTE(v46);
      v47[v20 + 7] = BYTE2(v46);
      v47[v20 + 8] = BYTE1(v46);
      v47[v20 + 9] = v46;
      LODWORD(v47) = *((_DWORD *)*v23 + v6 + 35);
      v48 = *v9;
      *(_WORD *)&v48[v20 + 10] = (_WORD)v47;
      v48[v20 + 12] = BYTE2(v47);
      v48[v20 + 13] = BYTE3(v47);
      v48[v20 + 14] = BYTE3(v47);
      v48[v20 + 15] = BYTE2(v47);
      v48[v20 + 16] = BYTE1(v47);
      v48[v20 + 17] = (unsigned __int8)v47;
      v49 = *(_DWORD *)(*((_QWORD *)*v23 + v6 + 13) - 16LL);
      (*v9)[v20 + 32] = v49 * (*(__int64 (__fastcall **)(FileSystemSupport *))(*(_QWORD *)v3 + 160LL))(v3);
      v70 = *(void (__fastcall ***)(FileSystemSupport *, unsigned __int8 *, __int64, __int64))v3;
      v69 = v20 + 33;
      v50 = v68;
      v51 = v68 + 13;
      if ( v66 )
      {
        *(_QWORD *)&v73 = v81;
        v55 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                v81,
                (char *)*v23 + 8 * v51);
        v56 = *(_DWORD *)(*((_QWORD *)*v23 + v50 + 13) - 16LL);
        v57 = v56 * (unsigned int)(*(unsigned __int8 (__fastcall **)(FileSystemSupport *))(*(_QWORD *)v3 + 160LL))(v3);
        v70[21](v3, &(*v9)[v69], v57, v55);
      }
      else
      {
        *(_QWORD *)&v73 = v80;
        v52 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                v80,
                (char *)*v23 + 8 * v51);
        v53 = *(_DWORD *)(*((_QWORD *)*v23 + v50 + 13) - 16LL);
        v54 = v53 * (unsigned int)(*(unsigned __int8 (__fastcall **)(FileSystemSupport *))(*(_QWORD *)v3 + 160LL))(v3);
        v70[22](v3, &(*v9)[v69], v54, v52);
      }
      SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&v75);
LABEL_53:
      ImapiFsObjectBase::ExportLastModifiedTime(*v23, &v84);
      v73 = v84;
      v58 = (int)pExceptionObject;
      Utility::SetDateTimeIso915(&(*v9)[(int)pExceptionObject + 18], &v73);
      if ( *((_BYTE *)*v23 + 177) == 1 )
        (*v9)[v25 + 25] |= 1u;
      Utility::Set16BitDualFormatNumber(&(*v9)[v58 + 28], 1u);
      v6 = v68;
      v20 = *((_DWORD *)*v23 + v68 + 32) + v58;
      LODWORD(pExceptionObject) = v20;
    }
    v8 = v65;
    if ( v20 )
      goto LABEL_57;
LABEL_60:
    if ( FileSystemSupport::include(v3) )
    {
      SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&v71);
      ++v8;
      LODWORD(v6) = v66;
      continue;
    }
    break;
  }
  SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&v71);
LABEL_71:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 43, &WPP_0f921ac20c883071ccb82ce92dc0d426_Traceguids);
  }
  SmartArrayPtr<unsigned char>::~SmartArrayPtr<unsigned char>(&v74);
  v63 = v76[0];
  if ( v76[0] )
  {
    std::vector<SmartClassPtr<ProgressItem,ImapiImplementation>>::_Destroy(v62, v76[0], v76[1]);
    operator delete(v63);
  }
  SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(v72);
  return SmartPtr<DataStashMap>::~SmartPtr<DataStashMap>(v87);
}

```

## disassembly

```asm
0x18001abb4  mov     [rsp-8+arg_10], r8
0x18001abb9  mov     [rsp-8+arg_8], rdx
0x18001abbe  mov     [rsp-8+arg_0], rcx
0x18001abc3  push    rbp
0x18001abc4  push    rbx
0x18001abc5  push    rsi
0x18001abc6  push    rdi
0x18001abc7  push    r12
0x18001abc9  push    r13
0x18001abcb  push    r14
0x18001abcd  push    r15
0x18001abcf  lea     rbp, [rsp-68h]
0x18001abd4  sub     rsp, 168h
0x18001abdb  mov     r13, rcx
0x18001abde  lea     rbx, WPP_GLOBAL_Control
0x18001abe5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001abec  cmp     rcx, rbx
0x18001abef  jz      short loc_18001AC44
0x18001abf1  test    byte ptr [rcx+44h], 8
0x18001abf5  jz      short loc_18001AC19
0x18001abf7  cmp     byte ptr [rcx+41h], 5
0x18001abfb  jb      short loc_18001AC19
0x18001abfd  mov     edx, 29h ; ')'
0x18001ac02  lea     r8, WPP_0f921ac20c883071ccb82ce92dc0d426_Traceguids
0x18001ac09  mov     rcx, [rcx+38h]
0x18001ac0d  call    WPP_SF_
0x18001ac12  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ac19  cmp     rcx, rbx
0x18001ac1c  jz      short loc_18001AC44
0x18001ac1e  test    byte ptr [rcx+44h], 4
0x18001ac22  jz      short loc_18001AC44
0x18001ac24  cmp     byte ptr [rcx+41h], 4
0x18001ac28  jb      short loc_18001AC44
0x18001ac2a  mov     edx, 2Ah ; '*'
0x18001ac2f  mov     eax, [r13+54h]
0x18001ac33  mov     [rsp+1A0h+var_180], eax
0x18001ac37  mov     r9, [r13+8]
0x18001ac3b  mov     rcx, [rcx+38h]
0x18001ac3f  call    WPP_SF_SD
0x18001ac44  mov     rax, [r13+30h]
0x18001ac48  mov     rcx, [rax+2C0h]
0x18001ac4f  mov     [rbp+0A0h+pExceptionObject], rcx
0x18001ac56  test    rcx, rcx
0x18001ac59  jz      short loc_18001AC5E
0x18001ac5b  inc     dword ptr [rcx+8]
0x18001ac5e  mov     edx, [r13+54h]; unsigned int
0x18001ac62  mov     rcx, [rcx]; this
0x18001ac65  call    ?BlockSeek@CFsiStashFile@@QEAAXK@Z; CFsiStashFile::BlockSeek(ulong)
0x18001ac6a  nop
0x18001ac6b  lea     rcx, [rbp+0A0h+pExceptionObject]
0x18001ac72  call    ??1?$SmartPtr@VCFsiStashFile@@@@QEAA@XZ; SmartPtr<CFsiStashFile>::~SmartPtr<CFsiStashFile>(void)
0x18001ac77  lea     rcx, [rsp+1A0h+var_140]
0x18001ac7c  call    ??0?$SmartClassPtr@VImapiFsObjectBase@@VImapiImplementation@@@@QEAA@PEAVImapiFsObjectBase@@@Z; SmartClassPtr<ImapiFsObjectBase,ImapiImplementation>::SmartClassPtr<ImapiFsObjectBase,ImapiImplementation>(ImapiFsObjectBase *)
0x18001ac81  nop
0x18001ac82  mov     rax, [r13+0]
0x18001ac86  mov     rcx, r13
0x18001ac89  mov     rax, [rax+80h]
0x18001ac90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac95  mov     r14d, eax
0x18001ac98  mov     [rsp+1A0h+var_16C], eax
0x18001ac9c  xorps   xmm0, xmm0
0x18001ac9f  movdqu  xmmword ptr [rbp+0A0h+var_110], xmm0
0x18001aca4  mov     [rbp+0A0h+var_100], 0
0x18001acac  mov     ecx, 800h; unsigned __int64
0x18001acb1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001acb6  mov     rdx, rax
0x18001acb9  lea     rcx, [rbp+0A0h+var_120]
0x18001acbd  call    ??0?$SmartArrayPtr@E@@QEAA@PEAE@Z; SmartArrayPtr<uchar>::SmartArrayPtr<uchar>(uchar *)
0x18001acc2  nop
0x18001acc3  xor     r12d, r12d
0x18001acc6  mov     rbx, [rbp+0A0h+var_120]
0x18001acca  mov     [rsp+1A0h+var_170], r12d
0x18001accf  mov     rax, [r13+30h]
0x18001acd3  cmp     r12d, [rax+170h]
0x18001acda  jnb     loc_18001B5BF
0x18001ace0  test    rbx, rbx
0x18001ace3  jz      short loc_18001ACEA
0x18001ace5  mov     rcx, [rbx]
0x18001ace8  jmp     short loc_18001ACEC
0x18001acea  xor     ecx, ecx; void *
0x18001acec  xor     edx, edx; Val
0x18001acee  mov     r8d, 800h; Size
0x18001acf4  call    memset_0
0x18001acf9  lea     rdx, [rbp+0A0h+var_F8]
0x18001acfd  mov     rcx, r13
0x18001ad00  call    ?GetPathTable@IsoFileSystemSupport@@IEAA?AV?$SmartArrayPtr@V?$SmartClassPtr@VImapiDirectoryInfo@@VImapiImplementation@@@@@@XZ; IsoFileSystemSupport::GetPathTable(void)
0x18001ad05  movsxd  rcx, r12d
0x18001ad08  mov     rax, [rax]
0x18001ad0b  mov     rdi, [rax]
0x18001ad0e  mov     rdi, [rdi+rcx*8]
0x18001ad12  mov     [rsp+1A0h+var_148], rdi
0x18001ad17  test    rdi, rdi
0x18001ad1a  jz      short loc_18001AD1F
0x18001ad1c  inc     dword ptr [rdi+8]
0x18001ad1f  lea     rcx, [rbp+0A0h+var_F8]
0x18001ad23  call    ??1?$SmartArrayPtr@V?$SmartClassPtr@VCStreamROBase@@VImapiImplementation@@@@@@QEAA@XZ; SmartArrayPtr<SmartClassPtr<CStreamROBase,ImapiImplementation>>::~SmartArrayPtr<SmartClassPtr<CStreamROBase,ImapiImplementation>>(void)
0x18001ad28  mov     rcx, [rdi]
0x18001ad2b  mov     [rsp+1A0h+var_180], 0
0x18001ad33  lea     r9, ??_R0?AVImapiDirectoryInfo@@@8; ImapiDirectoryInfo `RTTI Type Descriptor'
0x18001ad3a  lea     r8, ??_R0?AVImapiFsObjectBase@@@8; ImapiFsObjectBase `RTTI Type Descriptor'
0x18001ad41  xor     edx, edx
0x18001ad43  mov     rcx, [rcx+48h]
0x18001ad47  call    __RTDynamicCast_0
0x18001ad4c  mov     rsi, rax
0x18001ad4f  mov     rcx, [rbx]
0x18001ad52  mov     byte ptr [rcx], 22h ; '"'
0x18001ad55  movsxd  r14, r14d
0x18001ad58  mov     [rsp+1A0h+var_160], r14
0x18001ad5d  mov     rdx, [rdi]
0x18001ad60  mov     edx, [rdx+r14*4+30Ch]; unsigned int
0x18001ad68  mov     rcx, r13; this
0x18001ad6b  call    ?DiscRelativeBlock@FileSystemSupport@@QEAAKK@Z; FileSystemSupport::DiscRelativeBlock(ulong)
0x18001ad70  mov     r9, [rbx]
0x18001ad73  mov     [r9+2], al
0x18001ad77  mov     r8d, eax
0x18001ad7a  shr     r8d, 8
0x18001ad7e  mov     [r9+3], r8b
0x18001ad82  mov     edx, eax
0x18001ad84  shr     edx, 10h
0x18001ad87  mov     [r9+4], dl
0x18001ad8b  mov     ecx, eax
0x18001ad8d  shr     ecx, 18h
0x18001ad90  mov     [r9+5], cl
0x18001ad94  mov     [r9+6], cl
0x18001ad98  mov     [r9+7], dl
0x18001ad9c  mov     [r9+8], r8b
0x18001ada0  mov     [r9+9], al
0x18001ada4  mov     rax, [rdi]
0x18001ada7  mov     r9d, [rax+r14*4+8Ch]
0x18001adaf  mov     r8, [rbx]
0x18001adb2  mov     [r8+0Ah], r9b
0x18001adb6  mov     edx, r9d
0x18001adb9  shr     edx, 8
0x18001adbc  mov     [r8+0Bh], dl
0x18001adc0  mov     ecx, r9d
0x18001adc3  shr     ecx, 10h
0x18001adc6  mov     [r8+0Ch], cl
0x18001adca  mov     eax, r9d
0x18001adcd  shr     eax, 18h
0x18001add0  mov     [r8+0Dh], al
0x18001add4  mov     [r8+0Eh], al
0x18001add8  mov     [r8+0Fh], cl
0x18001addc  mov     [r8+10h], dl
0x18001ade0  mov     [r8+11h], r9b
0x18001ade4  lea     rdx, [rbp+0A0h+var_D8]
0x18001ade8  mov     rcx, [rdi]
0x18001adeb  call    ?ExportLastModifiedTime@ImapiFsObjectBase@@QEAA?AVCOleDateTime@ATL@@XZ; ImapiFsObjectBase::ExportLastModifiedTime(void)
0x18001adf0  movups  xmm2, [rbp+0A0h+var_D8]
0x18001adf4  movdqu  [rsp+1A0h+var_130], xmm2
0x18001adfa  mov     rcx, [rbx]
0x18001adfd  add     rcx, 12h
0x18001ae01  lea     rdx, [rsp+1A0h+var_130]
0x18001ae06  call    ?SetDateTimeIso915@Utility@@SAXPEAEVCOleDateTime@ATL@@@Z; Utility::SetDateTimeIso915(uchar *,ATL::COleDateTime)
0x18001ae0b  mov     rax, [rbx]
0x18001ae0e  mov     byte ptr [rax+19h], 2
0x18001ae12  mov     rax, [rdi]
0x18001ae15  cmp     byte ptr [rax+0B1h], 1
0x18001ae1c  jnz     short loc_18001AE25
0x18001ae1e  mov     rax, [rbx]
0x18001ae21  or      byte ptr [rax+19h], 1
0x18001ae25  mov     rcx, [rbx]
0x18001ae28  add     rcx, 1Ch; unsigned __int8 *
0x18001ae2c  mov     edx, 1; unsigned int
0x18001ae31  call    ?Set16BitDualFormatNumber@Utility@@SAXPEAEI@Z; Utility::Set16BitDualFormatNumber(uchar *,uint)
0x18001ae36  mov     rax, [rbx]
0x18001ae39  mov     byte ptr [rax+20h], 1
0x18001ae3d  mov     rax, [rbx]
0x18001ae40  mov     byte ptr [rax+22h], 22h ; '"'
0x18001ae44  mov     edx, [rsi+r14*4+30Ch]; unsigned int
0x18001ae4c  mov     rcx, r13; this
0x18001ae4f  call    ?DiscRelativeBlock@FileSystemSupport@@QEAAKK@Z; FileSystemSupport::DiscRelativeBlock(ulong)
0x18001ae54  mov     r9, [rbx]
0x18001ae57  mov     [r9+24h], al
0x18001ae5b  mov     r8d, eax
0x18001ae5e  shr     r8d, 8
0x18001ae62  mov     [r9+25h], r8b
0x18001ae66  mov     edx, eax
0x18001ae68  shr     edx, 10h
0x18001ae6b  mov     [r9+26h], dl
0x18001ae6f  mov     ecx, eax
0x18001ae71  shr     ecx, 18h
0x18001ae74  mov     [r9+27h], cl
0x18001ae78  mov     [r9+28h], cl
0x18001ae7c  mov     [r9+29h], dl
0x18001ae80  mov     [r9+2Ah], r8b
0x18001ae84  mov     [r9+2Bh], al
0x18001ae88  mov     r9d, [rsi+r14*4+8Ch]
0x18001ae90  mov     r8, [rbx]
0x18001ae93  mov     [r8+2Ch], r9b
0x18001ae97  mov     edx, r9d
0x18001ae9a  shr     edx, 8
0x18001ae9d  mov     [r8+2Dh], dl
0x18001aea1  mov     ecx, r9d
0x18001aea4  shr     ecx, 10h
0x18001aea7  mov     [r8+2Eh], cl
0x18001aeab  mov     eax, r9d
0x18001aeae  shr     eax, 18h
0x18001aeb1  mov     [r8+2Fh], al
0x18001aeb5  mov     [r8+30h], al
0x18001aeb9  mov     [r8+31h], cl
0x18001aebd  mov     [r8+32h], dl
0x18001aec1  mov     [r8+33h], r9b
0x18001aec5  lea     rdx, [rbp+0A0h+var_C8]
0x18001aec9  mov     rcx, rsi
0x18001aecc  call    ?ExportLastModifiedTime@ImapiFsObjectBase@@QEAA?AVCOleDateTime@ATL@@XZ; ImapiFsObjectBase::ExportLastModifiedTime(void)
0x18001aed1  movups  xmm2, [rbp+0A0h+var_C8]
0x18001aed5  movdqu  [rsp+1A0h+var_130], xmm2
0x18001aedb  mov     rcx, [rbx]
0x18001aede  add     rcx, 34h ; '4'
0x18001aee2  lea     rdx, [rsp+1A0h+var_130]
0x18001aee7  call    ?SetDateTimeIso915@Utility@@SAXPEAEVCOleDateTime@ATL@@@Z; Utility::SetDateTimeIso915(uchar *,ATL::COleDateTime)
0x18001aeec  mov     rax, [rbx]
0x18001aeef  mov     byte ptr [rax+3Bh], 2
0x18001aef3  mov     rax, [rdi]
0x18001aef6  cmp     byte ptr [rax+0B1h], 1
0x18001aefd  jnz     short loc_18001AF06
0x18001aeff  mov     rax, [rbx]
0x18001af02  or      byte ptr [rax+3Bh], 1
0x18001af06  mov     rcx, [rbx]
0x18001af09  add     rcx, 3Eh ; '>'; unsigned __int8 *
0x18001af0d  mov     edx, 1; unsigned int
0x18001af12  call    ?Set16BitDualFormatNumber@Utility@@SAXPEAEI@Z; Utility::Set16BitDualFormatNumber(uchar *,uint)
0x18001af17  xor     ecx, ecx
0x18001af19  mov     rax, [rbx]
0x18001af1c  mov     byte ptr [rax+rcx+42h], 1
0x18001af21  inc     rcx
0x18001af24  cmp     rcx, 2
0x18001af28  jnz     short loc_18001AF19
0x18001af2a  mov     rcx, r13; this
0x18001af2d  call    ?include@FileSystemSupport@@QEAA_NXZ; FileSystemSupport::include(void)
0x18001af32  test    al, al
0x18001af34  jz      loc_18001B4B0
0x18001af3a  mov     r15d, 44h ; 'D'
0x18001af40  mov     dword ptr [rbp+0A0h+pExceptionObject], r15d
0x18001af47  lea     rcx, [rsp+1A0h+var_148]
0x18001af4c  call    ?Pointer@?$SmartClassPtr@VImapiDirectoryInfo@@VImapiImplementation@@@@QEBAPEAVImapiDirectoryInfo@@XZ; SmartClassPtr<ImapiDirectoryInfo,ImapiImplementation>::Pointer(void)
0x18001af51  mov     rdx, rax
0x18001af54  lea     r8, [rbp+0A0h+var_110]
0x18001af58  mov     rcx, r13
0x18001af5b  call    ?SortDirectoryChildren@IsoFileSystemSupport@@AEAAXPEAVImapiDirectoryInfo@@PEAV?$vector@V?$SmartClassPtr@VImapiFsObjectBase@@VImapiImplementation@@@@V?$allocator@V?$SmartClassPtr@VImapiFsObjectBase@@VImapiImplementation@@@@@std@@@std@@@Z; IsoFileSystemSupport::SortDirectoryChildren(ImapiDirectoryInfo *,std::vector<SmartClassPtr<ImapiFsObjectBase,ImapiImplementation>> *)
0x18001af60  mov     rsi, [rbp+0A0h+var_110]
0x18001af64  cmp     rsi, [rbp+0A0h+var_110+8]
0x18001af68  jz      loc_18001B4A6
0x18001af6e  mov     rdx, rsi
0x18001af71  lea     rcx, [rsp+1A0h+var_140]
0x18001af76  call    ??4?$SmartPtr@VImportMetadata@@@@QEAAAEAV0@AEBV0@@Z; SmartPtr<ImportMetadata>::operator=(SmartPtr<ImportMetadata> const &)
0x18001af7b  mov     rdi, [rsp+1A0h+var_140]
0x18001af80  mov     rax, [rdi]
0x18001af83  mov     eax, [rax+r14*4+80h]
0x18001af8b  add     eax, r15d
0x18001af8e  mov     r12d, 800h
0x18001af94  cmp     eax, r12d
0x18001af97  jb      short loc_18001AFE9
0x18001af99  mov     rax, [r13+30h]
0x18001af9d  mov     rcx, [rax+2C0h]
0x18001afa4  mov     [rbp+0A0h+pExceptionObject], rcx
0x18001afab  test    rcx, rcx
0x18001afae  jz      short loc_18001AFB3
0x18001afb0  inc     dword ptr [rcx+8]
0x18001afb3  or      r9, 0FFFFFFFFFFFFFFFFh; unsigned __int64
0x18001afb7  mov     r8d, r12d; unsigned int
0x18001afba  mov     rdx, [rbx]; unsigned __int8 *
0x18001afbd  mov     rcx, [rcx]; this
0x18001afc0  call    ?Write@CFsiStashFile@@QEAAKPEAEK_K@Z; CFsiStashFile::Write(uchar *,ulong,unsigned __int64)
0x18001afc5  nop
0x18001afc6  lea     rcx, [rbp+0A0h+pExceptionObject]
0x18001afcd  call    ??1?$SmartPtr@VCFsiStashFile@@@@QEAA@XZ; SmartPtr<CFsiStashFile>::~SmartPtr<CFsiStashFile>(void)
0x18001afd2  mov     r8, r12; Size
0x18001afd5  xor     edx, edx; Val
0x18001afd7  mov     rcx, [rbx]; void *
0x18001afda  call    memset_0
0x18001afdf  xor     r15d, r15d
0x18001afe2  mov     dword ptr [rbp+0A0h+pExceptionObject], r15d
0x18001afe9  movsxd  r12, r15d
0x18001afec  mov     [rsp+1A0h+var_158], r12
0x18001aff1  mov     rax, [rdi]
0x18001aff4  mov     rcx, [rbx]
0x18001aff7  mov     al, [rax+r14*4+80h]
0x18001afff  mov     [r12+rcx], al
0x18001b003  mov     rax, [rdi]
0x18001b006  cmp     dword ptr [rax+38h], 0
0x18001b00a  jz      loc_18001B266
0x18001b010  cmp     dword ptr [rax+38h], 3
0x18001b014  jz      loc_18001B266
0x18001b01a  mov     [rsp+1A0h+var_150], rdi
0x18001b01f  test    rdi, rdi
0x18001b022  jz      short loc_18001B027
0x18001b024  inc     dword ptr [rdi+8]
0x18001b027  mov     rdx, rax
0x18001b02a  mov     eax, [rax+0F4h]
0x18001b030  cmp     eax, 1
0x18001b033  jnz     short loc_18001B06F
0x18001b035  mov     r9d, [rdx+0F8h]
0x18001b03c  mov     r8, [rbx]
0x18001b03f  mov     [r12+r8+2], r9b
0x18001b044  mov     edx, r9d
0x18001b047  shr     edx, 8
0x18001b04a  mov     [r12+r8+3], dl
0x18001b04f  mov     ecx, r9d
0x18001b052  shr     ecx, 10h
  ... truncated ...
```
