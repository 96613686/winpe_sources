# IsoFileSystemSupport::ImportImage(SmartClassPtr<CDiscImporter,CDiscReader>)

- ea: `0x180007e80`
- end: `0x180009604`
- name: `?ImportImage@IsoFileSystemSupport@@UEAAXV?$SmartClassPtr@VCDiscImporter@@VCDiscReader@@@@@Z`
- size: `6020`
- prototype: ``
- caller_count: `0`
- callee_count: `60`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x180003580`
- `0x180003a20`
- `0x180003f50`
- `0x1800049d0`
- `0x180004c70`
- `0x180005040`
- `0x180005160`
- `0x1800051a0`
- `0x180005438`
- `0x180005568`
- `0x180005c04`
- `0x180005cb4`
- `0x180007104`
- `0x180007210`
- `0x18000726c`
- `0x180007e80`
- `0x18000960c`
- `0x18000ba24`
- `0x18000c888`
- `0x18000c8d0`
- `0x18000d1c0`
- `0x18000ea14`
- `0x18001230c`
- `0x180017090`
- `0x1800180e8`
- `0x1800186a8`
- `0x180018e20`
- `0x180018e4c`
- `0x18001bee8`
- `0x18001ce58`
- `0x1800218f0`
- `0x1800236cc`
- `0x180023c08`
- `0x180023c44`
- `0x1800251dc`
- `0x1800251f6`
- `0x180028568`
- `0x18002b680`
- `0x18002d064`
- `0x18002d4e4`
- `0x18002dba4`
- `0x18002dc70`
- `0x18002f534`
- `0x1800361ec`
- `0x18003935c`
- `0x18003c4e0`
- `0x18003d73c`
- `0x1800465b4`
- `0x18004a7c4`
- `0x18004a824`

## import_xrefs

- `msvcrt!_wtoi` at `0x180008746`
- `msvcrt!_wtoi` at `0x180008746`
- `msvcrt!memcpy_s` at `0x180008ced`
- `msvcrt!memcpy_s` at `0x180008ced`
- `OLEAUT32!__imp_SysFreeString` at `0x1800089a5`
- `OLEAUT32!__imp_SysFreeString` at `0x180008e30`
- `OLEAUT32!__imp_SysFreeString` at `0x18000920a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800089a5`
- `OLEAUT32!__imp_SysFreeString` at `0x180008e30`
- `OLEAUT32!__imp_SysFreeString` at `0x18000920a`

## pseudocode

```c
// Hidden C++ exception states: #wind=45
void __fastcall IsoFileSystemSupport::ImportImage(_QWORD *a1, CDiscReader ***a2)
{
  signed int v4; // r15d
  CDiscReader **v5; // rax
  __int64 v6; // r13
  __int64 v7; // rbx
  unsigned __int8 v8; // al
  _BYTE **v9; // rax
  __int64 v10; // rsi
  int *v11; // rcx
  int *v12; // rdi
  __int64 v13; // rbx
  void *v14; // rax
  unsigned int v15; // ebx
  void **v16; // rdi
  void *v17; // rdx
  CIMAPIException *v18; // rax
  CIMAPIException *v19; // rax
  CIMAPIException **v20; // rbx
  unsigned int v21; // esi
  char *v22; // r14
  unsigned int v23; // eax
  CIMAPIException **v24; // rax
  CIMAPIException **v25; // rbx
  char **v26; // rbx
  char *v27; // rcx
  __int64 v28; // rsi
  unsigned __int8 v29; // al
  _BYTE **v30; // rax
  __int64 v31; // r8
  char **v32; // r9
  _BYTE *v33; // rdx
  int *v34; // rcx
  int *v35; // r13
  __int64 v36; // rsi
  char ***v37; // rcx
  _QWORD *v38; // rax
  signed __int64 v39; // rsi
  __int64 v40; // rax
  int v41; // ebx
  char *v42; // rdx
  char *v43; // r13
  CIMAPIException *v44; // rax
  CIMAPIException *v45; // rax
  CIMAPIException **v46; // rbx
  unsigned __int8 *v47; // r13
  ImapiFsObjectBase **v48; // rbx
  _QWORD **v49; // r14
  __int64 v50; // rcx
  __int64 v51; // r15
  unsigned int v52; // esi
  void *v53; // rdx
  unsigned int v54; // r15d
  __int64 v55; // rsi
  int v56; // eax
  OLECHAR *v57; // r14
  unsigned int v58; // r8d
  unsigned int v59; // ecx
  unsigned int v60; // edx
  void *v61; // rdx
  __int64 v62; // r15
  unsigned int v63; // esi
  unsigned __int8 v64; // al
  int v65; // r15d
  unsigned int v66; // eax
  unsigned int v67; // esi
  __int64 v68; // rdx
  __int64 v69; // r8
  _BYTE *v70; // r9
  _QWORD *v71; // rcx
  int *v72; // r15
  __int64 v73; // rsi
  __int64 FileDirRecord; // rax
  void *v75; // rsi
  __int64 v76; // rax
  __int64 v77; // rax
  _DWORD *v78; // rsi
  ImapiFsObjectBase *v79; // rcx
  unsigned int v80; // eax
  unsigned int v81; // ecx
  unsigned int v82; // eax
  unsigned int v83; // eax
  OLECHAR *v84; // r15
  __int64 v85; // rsi
  int v86; // eax
  unsigned int v87; // eax
  unsigned int v88; // eax
  unsigned int v89; // ebx
  char *v90; // r15
  char *v91; // rsi
  _QWORD **v92; // r13
  unsigned int v93; // ecx
  __int64 v94; // r8
  _BYTE *v95; // rdx
  _QWORD *v96; // rcx
  int *v97; // r13
  __int64 v98; // rsi
  __int64 Manager; // rax
  int v100; // ebx
  _BYTE *v101; // rdx
  __int64 v102; // r8
  _QWORD *v103; // rcx
  int *v104; // r13
  __int64 v105; // r15
  __int64 v106; // rbx
  __int64 v107; // rax
  __int64 *v108; // rbx
  _BYTE *v109; // rdx
  _QWORD *v110; // rcx
  int *v111; // r13
  __int64 v112; // rsi
  signed int v113; // r8d
  unsigned __int64 v114; // r13
  __int64 v115; // rdx
  __int64 v116; // rax
  ImapiDirectoryInfo *v117; // rax
  __int64 v118; // rax
  __int64 v119; // rcx
  __int64 **v120; // rax
  __int64 v121; // rdx
  CIMAPIException *v122; // rax
  CIMAPIException *v123; // rax
  CIMAPIException **v124; // rbx
  CIMAPIException *v125; // rax
  CIMAPIException *v126; // rax
  CIMAPIException **v127; // rbx
  CIMAPIException *v128; // rax
  CIMAPIException *v129; // rax
  CIMAPIException **v130; // rbx
  CIMAPIException *v131; // rax
  CIMAPIException *v132; // rax
  CIMAPIException **v133; // rbx
  CIMAPIException *v134; // rax
  CIMAPIException *v135; // rax
  CIMAPIException **v136; // rbx
  __int64 v137; // rcx
  CIMAPIException *v138; // rax
  CIMAPIException *v139; // rax
  CIMAPIException **v140; // rbx
  CIMAPIException *v141; // rax
  CIMAPIException *v142; // rax
  CIMAPIException **v143; // rbx
  CIMAPIException *v144; // rax
  CIMAPIException *v145; // rax
  CIMAPIException **v146; // rbx
  CIMAPIException *v147; // rax
  CIMAPIException *v148; // rax
  CIMAPIException **v149; // rbx
  CIMAPIException *v150; // rax
  CIMAPIException *v151; // rax
  CIMAPIException **v152; // rbx
  unsigned int v153; // [rsp+50h] [rbp-B0h]
  unsigned int v154; // [rsp+50h] [rbp-B0h]
  unsigned int v155; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v156; // [rsp+58h] [rbp-A8h]
  unsigned int v157; // [rsp+5Ch] [rbp-A4h]
  char *v158; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v159; // [rsp+68h] [rbp-98h]
  void *Source; // [rsp+70h] [rbp-90h] BYREF
  char *v161; // [rsp+78h] [rbp-88h] BYREF
  int v162; // [rsp+80h] [rbp-80h]
  unsigned int v163; // [rsp+84h] [rbp-7Ch]
  unsigned int v164; // [rsp+88h] [rbp-78h]
  unsigned int v165; // [rsp+8Ch] [rbp-74h]
  _DWORD *v166; // [rsp+90h] [rbp-70h] BYREF
  ImapiFsObjectBase **v167; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v168; // [rsp+A0h] [rbp-60h]
  char **v169; // [rsp+A8h] [rbp-58h] BYREF
  void *v170[2]; // [rsp+B0h] [rbp-50h] BYREF
  void *v171; // [rsp+C0h] [rbp-40h]
  _DWORD *v172; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v173; // [rsp+D0h] [rbp-30h] BYREF
  ImapiFsObjectBase **v174; // [rsp+D8h] [rbp-28h] BYREF
  __int64 *v175; // [rsp+E0h] [rbp-20h] BYREF
  char v176[8]; // [rsp+E8h] [rbp-18h] BYREF
  _DWORD *v177; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v178; // [rsp+F8h] [rbp-8h] BYREF
  void **v179; // [rsp+100h] [rbp+0h] BYREF
  _QWORD *v180; // [rsp+108h] [rbp+8h] BYREF
  BSTR bstrString; // [rsp+110h] [rbp+10h] BYREF
  _DWORD *v182; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v183[88]; // [rsp+120h] [rbp+20h] BYREF
  char v184[8]; // [rsp+178h] [rbp+78h] BYREF
  char v185[8]; // [rsp+180h] [rbp+80h] BYREF
  char v186[8]; // [rsp+188h] [rbp+88h] BYREF
  char v187[8]; // [rsp+190h] [rbp+90h] BYREF
  char v188[8]; // [rsp+198h] [rbp+98h] BYREF
  __int128 v189; // [rsp+1A0h] [rbp+A0h] BYREF
  __int128 v190; // [rsp+1B0h] [rbp+B0h] BYREF
  char v191[8]; // [rsp+1C0h] [rbp+C0h] BYREF
  void *v192; // [rsp+1C8h] [rbp+C8h]
  ImapiDirectoryInfo *v193; // [rsp+1D0h] [rbp+D0h]
  CIMAPIException **v195; // [rsp+230h] [rbp+130h] BYREF
  CIMAPIException **pExceptionObject; // [rsp+238h] [rbp+138h] BYREF

  v4 = 0;
  v163 = 0;
  v168 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 49, &WPP_0f921ac20c883071ccb82ce92dc0d426_Traceguids);
  }
  v155 = 0;
  v5 = *a2;
  v195 = v5;
  if ( v5 )
    ++*((_DWORD *)v5 + 2);
  IsoFileSystemSupport::FindVolumeDescriptor(a1, &v180, &v195);
  if ( !v180 || !*v180 )
  {
    v150 = (CIMAPIException *)operator new(0x58u);
    pExceptionObject = (CIMAPIException **)v150;
    if ( v150 )
      v151 = CIMAPIException::CIMAPIException(v150, -1062555310, a1[1]);
    else
      v151 = 0;
    SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&pExceptionObject, v151);
    v152 = pExceptionObject;
    if ( pExceptionObject && *pExceptionObject )
    {
      CIMAPIException::SetCodeRefInfo(
        *pExceptionObject,
        "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsifs.cpp",
        1107);
      v195 = v152;
      if ( v152 )
        ++*((_DWORD *)v152 + 2);
      throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&v195;
    }
    CIMAPIException::CIMAPIException(
      (CIMAPIException *)v183,
      (const struct CIMAPIException *)&CIMAPIException::badAlloc);
    throw (CIMAPIException *)v183;
  }
  v6 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v180 + 88LL))(*v180);
  v173 = v6;
  v7 = *a1;
  v8 = (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 160LL))(a1);
  v9 = (_BYTE **)(*(__int64 (__fastcall **)(_QWORD *, CIMAPIException ***, __int64, _QWORD))(v7 + 184))(
                   a1,
                   &pExceptionObject,
                   v6 + 40,
                   0x20u / v8);
  v10 = a1[6];
  v11 = (int *)(*v9 - 24);
  v12 = (int *)(*(_QWORD *)(v10 + 336) - 24LL);
  if ( v11 != v12 )
  {
    if ( v12[4] >= 0 && *(_QWORD *)v11 == *(_QWORD *)v12 )
    {
      v13 = ((__int64 (*)(void))ATL::CSimpleStringT<unsigned short,0>::CloneData)();
      ATL::CStringData::Release((ATL::CStringData *)v12);
      *(_QWORD *)(v10 + 336) = v13 + 24;
    }
    else
    {
      ATL::CSimpleStringT<unsigned short,0>::SetString((char **)(v10 + 336), *v9, *((_DWORD *)*v9 - 4));
    }
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&pExceptionObject);
  if ( (*(unsigned int (__fastcall **)(CDiscReader *))(*(_QWORD *)**a2 + 64LL))(**a2) + 16 >= *(_DWORD *)(v6 + 140)
    || !*(_DWORD *)(v6 + 132) )
  {
    v147 = (CIMAPIException *)operator new(0x58u);
    pExceptionObject = (CIMAPIException **)v147;
    if ( v147 )
      v148 = CIMAPIException::CIMAPIException(v147, -1062555310, a1[1]);
    else
      v148 = 0;
    SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&pExceptionObject, v148);
    v149 = pExceptionObject;
    if ( pExceptionObject && *pExceptionObject )
    {
      CIMAPIException::SetCodeRefInfo(
        *pExceptionObject,
        "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsifs.cpp",
        1119);
      v195 = v149;
      if ( v149 )
        ++*((_DWORD *)v149 + 2);
      throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&v195;
    }
    CIMAPIException::CIMAPIException(
      (CIMAPIException *)v183,
      (const struct CIMAPIException *)&CIMAPIException::badAlloc);
    throw (CIMAPIException *)v183;
  }
  v14 = operator new(0x1000u);
  SmartArrayPtr<unsigned char>::SmartArrayPtr<unsigned char>(&v179, v14);
  v15 = *(_DWORD *)(v6 + 140);
  v16 = v179;
  if ( v179 )
    v17 = *v179;
  else
    v17 = 0;
  CDiscReader::BlockRead(**a2, v17, 2u, v15, &v155);
  if ( v155 != 2 )
  {
    v18 = (CIMAPIException *)operator new(0x58u);
    v195 = (CIMAPIException **)v18;
    if ( v18 )
      v19 = CIMAPIException::CIMAPIException(v18, -1062555305, v15);
    else
      v19 = 0;
    SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v195, v19);
    v20 = v195;
    if ( v195 && *v195 )
    {
      CIMAPIException::SetCodeRefInfo(*v195, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsifs.cpp", 1130);
      pExceptionObject = v20;
      if ( v20 )
        ++*((_DWORD *)v20 + 2);
      throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
    }
    CIMAPIException::CIMAPIException(
      (CIMAPIException *)v183,
      (const struct CIMAPIException *)&CIMAPIException::badAlloc);
    throw (CIMAPIException *)v183;
  }
  v21 = v15 + 2;
  v153 = v15 + 2;
  if ( v16 )
    v22 = (char *)*v16;
  else
    v22 = 0;
  *(_OWORD *)v170 = 0;
  v171 = 0;
  v156 = 0;
  v23 = 0;
  LODWORD(v195) = 0;
  while ( v23 < *(_DWORD *)(v6 + 132) )
  {
    v24 = (CIMAPIException **)operator new(0x10u);
    v25 = v24;
    pExceptionObject = v24;
    if ( v24 )
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v24 + 1);
    else
      v25 = 0;
    SmartPtr<IsoPathTable>::SmartPtr<IsoPathTable>(&v169, v25);
    v26 = v169;
    if ( v169 )
      v27 = *v169;
    else
      v27 = 0;
    *(_QWORD *)v27 = *(_QWORD *)v22;
    v28 = *a1;
    v29 = (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 160LL))(a1);
    v30 = (_BYTE **)(*(__int64 (__fastcall **)(_QWORD *, ImapiFsObjectBase ***, _QWORD *, _QWORD))(v28 + 184))(
                      a1,
                      &v174,
                      (_QWORD *)v22 + 1,
                      (unsigned __int8)*v22 / (unsigned int)v29);
    v32 = (char **)(*v26 + 8);
    pExceptionObject = (CIMAPIException **)v32;
    v33 = *v30;
    v34 = (int *)(*v30 - 24);
    v35 = (int *)(*v32 - 24);
    if ( v34 != v35 )
    {
      if ( v35[4] >= 0 && *(_QWORD *)v34 == *(_QWORD *)v35 )
      {
        v36 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v34, v33, v31);
        ATL::CStringData::Release((ATL::CStringData *)v35);
        *pExceptionObject = (CIMAPIException *)(v36 + 24);
      }
      else
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(v32, v33, *((_DWORD *)v33 - 4));
      }
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v174);
    v37 = (char ***)v170[1];
    if ( &v169 >= v170[1] || (v38 = v170[0], v170[0] > &v169) )
    {
      if ( v170[1] == v171 )
      {
        std::vector<SmartPtr<IsoPathTable>>::_Reserve(v170);
        v37 = (char ***)v170[1];
      }
      *v37 = v26;
      if ( v26 )
        ++*((_DWORD *)v26 + 2);
    }
    else
    {
      v39 = ((char *)&v169 - (char *)v170[0]) >> 3;
      if ( v170[1] == v171 )
      {
        std::vector<SmartPtr<IsoPathTable>>::_Reserve(v170);
        v37 = (char ***)v170[1];
        v38 = v170[0];
      }
      v40 = v38[v39];
      *v37 = (char **)v40;
      if ( v40 )
        ++*(_DWORD *)(v40 + 8);
    }
    v170[1] = v37 + 1;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      WPP_SF_dddDdS(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        *((unsigned __int16 *)*v26 + 3),
        (unsigned int)*v26,
        v156,
        **v26,
        (*v26)[1],
        *(_DWORD *)(*v26 + 2),
        *((_WORD *)*v26 + 3),
        *((_QWORD *)*v26 + 1));
    }
    v41 = Utility::RoundUpToEvenByteBoundary((unsigned int)(unsigned __int8)*v22 + 8);
    v4 += v41;
    v42 = (char *)*v16;
    if ( (unsigned int)v4 < 0x800 )
    {
      v22 = &v42[v4];
      v21 = v153;
    }
    else
    {
      memcpy_0(*v16, v42 + 2048, 0x800u);
      v43 = (char *)*v16;
      CDiscReader::BlockRead(**a2, (char *)*v16 + 2048, 1u, v153, &v155);
      if ( v155 != 1 )
      {
        v44 = (CIMAPIException *)operator new(0x58u);
        v195 = (CIMAPIException **)v44;
        if ( v44 )
          v45 = CIMAPIException::CIMAPIException(v44, -1062555305, v153);
        else
          v45 = 0;
        SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v195, v45);
        v46 = v195;
        if ( v195 && *v195 )
        {
          CIMAPIException::SetCodeRefInfo(*v195, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsifs.cpp", 1182);
          pExceptionObject = v46;
          if ( v46 )
            ++*((_DWORD *)v46 + 2);
          throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
        }
        CIMAPIException::CIMAPIException(
          (CIMAPIException *)v183,
          (const struct CIMAPIException *)&CIMAPIException::badAlloc);
        throw (CIMAPIException *)v183;
      }
      v4 -= 2048;
      v22 = &v43[v4];
      v21 = ++v153;
    }
    ++v156;
    LODWORD(v195) = v41 + (_DWORD)v195;
    SmartPtr<IsoPathTable>::~SmartPtr<IsoPathTable>(&v169);
    v6 = v173;
    v23 = (unsigned int)v195;
  }
  v47 = 0;
  if ( !v21 )
    v21 = 0;
  v154 = v21;
  v48 = *(ImapiFsObjectBase ***)(a1[6] + 56LL);
  v167 = v48;
  if ( v48 )
    ++*((_DWORD *)v48 + 2);
  v49 = (_QWORD **)v170[0];
  v50 = **(_QWORD **)v170[0];
  if ( *(_BYTE *)v50 != 1
    || *(_WORD *)(v50 + 6) != 1
    || (unsigned __int16)ATL::CSimpleStringT<unsigned short,0>::GetAt(v50 + 8, 0) )
  {
    v144 = (CIMAPIException *)operator new(0x58u);
    v195 = (CIMAPIException **)v144;
    if ( v144 )
      v145 = CIMAPIException::CIMAPIException(v144, -1062555310, a1[1]);
    else
      v145 = 0;
    SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v195, v145);
    v146 = v195;
    if ( v195 && *v195 )
    {
      CIMAPIException::SetCodeRefInfo(*v195, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsifs.cpp", 1209);
      pExceptionObject = v146;
      if ( v146 )
        ++*((_DWORD *)v146 + 2);
      throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
    }
    CIMAPIException::CIMAPIException(
      (CIMAPIException *)v183,
      (const struct CIMAPIException *)&CIMAPIException::badAlloc);
    throw (CIMAPIException *)v183;
  }
  v165 = -1;
  v51 = 0;
  v157 = 0;
  LOBYTE(v195) = 0;
  v162 = 0;
  while ( (unsigned int)v51 < v156 )
  {
    SmartClassPtr<ImapiFsObjectBase,ImapiImplementation>::SmartClassPtr<ImapiFsObjectBase,ImapiImplementation>(&v166);
    v52 = *(_DWORD *)(*v49[v51] + 2LL);
    if ( v16 )
      v53 = *v16;
    else
      v53 = 0;
    CDiscReader::BlockRead(**a2, v53, 1u, v52, &v155);
    if ( v155 != 1 )
    {
      v141 = (CIMAPIException *)operator new(0x58u);
      v195 = (CIMAPIException **)v141;
      if ( v141 )
        v142 = CIMAPIException::CIMAPIException(v141, -1062555305, v52);
      else
        v142 = 0;
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v195, v142);
      v143 = v195;
      if ( v195 && *v195 )
      {
        CIMAPIException::SetCodeRefInfo(*v195, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsifs.cpp", 1229);
        pExceptionObject = v143;
        if ( v143 )
          ++*((_DWORD *)v143 + 2);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v183,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v183;
    }
    if ( v16 )
      v47 = (unsigned __int8 *)*v16;
    ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, *(const unsigned __int16 **)(*v49[v51] + 8LL));
    if ( ATL::CComBSTR::Append((ATL::CComBSTR *)&bstrString, L"\\", 1) < 0 )
    {
      v138 = (CIMAPIException *)operator new(0x58u);
      v195 = (CIMAPIException **)v138;
      if ( v138 )
        v139 = CIMAPIException::CIMAPIException(v138, -1062555392);
      else
        v139 = 0;
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v195, v139);
      v140 = v195;
      if ( v195 && *v195 )
      {
        CIMAPIException::SetCodeRefInfo(*v195, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsifs.cpp", 1240);
        pExceptionObject = v140;
        if ( v140 )
          ++*((_DWORD *)v140 + 2);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v183,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v183;
    }
    v54 = v52 + 1;
    v159 = v52 + 1;
    v55 = *(_QWORD *)(a1[6] + 664LL);
    v56 = (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 120LL))(a1);
    v57 = bstrString;
    CProxy_DFileSystemImageImportEvents<CMsftFileSystemImage>::Fire_ImportUpdate(
      v55 + 56,
      v56,
      (_DWORD)bstrString,
      v157,
      v156,
      v162,
      -1);
    if ( (_BYTE)v195 == 1 )
    {
      Utility::GetDateTimeIso915(&v189, v47 + 18);
      *(_OWORD *)((char *)*v48 + 184) = v189;
      *(_OWORD *)((char *)*v48 + 200) = v189;
      *(_OWORD *)((char *)*v48 + 216) = v189;
      *((_BYTE *)*v48 + 177) = v47[25] & 1;
    }
    v58 = *(_DWORD *)(v47 + 10);
    LODWORD(v172) = v58;
    v59 = 0;
    v60 = 0;
    while ( 1 )
    {
      LODWORD(v195) = v60;
      v164 = v59;
      if ( v60 >= v58 )
        break;
      if ( v59 >= 0x800 || !*v47 )
      {
        LODWORD(v195) = ((v60 & 0x7FF) != 0 ? 2048 - (v60 & 0x7FF) : 0) + v60;
        if ( (unsigned int)v195 >= v58 )
          break;
        if ( v16 )
          v61 = *v16;
        else
          v61 = 0;
        CDiscReader::BlockRead(**a2, v61, 1u, v54, &v155);
        if ( v155 != 1 )
        {
          v125 = (CIMAPIException *)operator new(0x58u);
          v195 = (CIMAPIException **)v125;
          if ( v125 )
            v126 = CIMAPIException::CIMAPIException(v125, -1062555305, v54);
          else
            v126 = 0;
          SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v195, v126);
          v127 = v195;
          if ( v195 && *v195 )
          {
            CIMAPIException::SetCodeRefInfo(*v195, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsifs.cpp", 1279);
            pExceptionObject = v127;
            if ( v127 )
              ++*((_DWORD *)v127 + 2);
            throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
          }
          CIMAPIException::CIMAPIException(
            (CIMAPIException *)v183,
            (const struct CIMAPIException *)&CIMAPIException::badAlloc);
          throw (CIMAPIException *)v183;
        }
        v159 = ++v54;
        if ( v16 )
          v47 = (unsigned __int8 *)*v16;
        else
          v47 = 0;
        v164 = 0;
      }
      if ( (v47[25] & 2) == 0 )
      {
        v62 = *a1;
        v63 = v47[32];
        v64 = (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 160LL))(a1);
        (*(void (__fastcall **)(_QWORD *, char **, unsigned __int8 *, _QWORD))(v62 + 184))(
          a1,
          &v161,
          v47 + 33,
          v63 / v64);
        v65 = 1;
        v66 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::ReverseFind(
                &v161,
                59);
        v67 = v66;
        if ( v66 != -1 )
        {
          LODWORD(v175) = _wtoi((const wchar_t *)&v161[2 * (v66 + 1)]);
          v70 = *(_BYTE **)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Left(
                             &v161,
                             v188,
                             v67);
          v71 = v70 - 24;
          v72 = (int *)(v161 - 24);
          if ( v70 - 24 != v161 - 24 )
          {
            if ( v72[4] >= 0 && *v71 == *(_QWORD *)v72 )
            {
              v73 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v71, v68, v69);
              ATL::CStringData::Release((ATL::CStringData *)v72);
              v161 = (char *)(v73 + 24);
            }
            else
            {
              ATL::CSimpleStringT<unsigned short,0>::SetString(&v161, v70, *((_DWORD *)v70 - 4));
            }
          }
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v188);
          v65 = (int)v175;
        }
        FileDirRecord = ImapiDirectoryInfo::GetFileDirRecord(*v48, v191, &v161);
        SmartPtr<ImportMetadata>::operator=(&v166, FileDirRecord);
        SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(v191);
        if ( v166 && *(_QWORD *)v166 )
        {
          if ( !*(_DWORD *)(*(_QWORD *)v166 + 56LL) || *(_DWORD *)(*(_QWORD *)v166 + 56LL) == 3 )
          {
            _bstr_t::_bstr_t((_bstr_t *)&v195, L"\\");
            ImapiFsObjectBase::GetFullPathOriginal(*v48);
            v120 = (__int64 **)operator+((struct _bstr_t *)&pExceptionObject);
            if ( *v120 )
              v121 = **v120;
            else
              v121 = 0;
            ATL::operator+(&v178, v121, &v161);
            _bstr_t::~_bstr_t((_bstr_t *)&pExceptionObject);
            _bstr_t::~_bstr_t((_bstr_t *)&v195);
            v122 = (CIMAPIException *)operator new(0x58u);
            v195 = (CIMAPIException **)v122;
            if ( v122 )
              v123 = CIMAPIException::CIMAPIException(v122, -1062555307, v178, a1[1]);
            else
              v123 = 0;
            SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v195, v123);
            v124 = v195;
            if ( v195 && *v195 )
            {
              CIMAPIException::SetCodeRefInfo(
                *v195,
                "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsifs.cpp",
                1331);
              pExceptionObject = v124;
              if ( v124 )
                ++*((_DWORD *)v124 + 2);
              throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
            }
            CIMAPIException::CIMAPIException(
              (CIMAPIException *)v183,
              (const struct CIMAPIException *)&CIMAPIException::badAlloc);
            throw (CIMAPIException *)v183;
          }
        }
        else
        {
          v75 = operator new(0x120u);
          v192 = v75;
          v76 = 0;
          if ( v75 )
          {
            v77 = SmartClassPtr<ImapiDirectoryInfo,ImapiImplementation>::Pointer(&v167);
            v76 = ImapiFileInfo::ImapiFileInfo(v75, a1[6], v77, &v161);
          }
          SmartPtr<ImportMetadata>::SmartPtr<ImportMetadata>(&v182, v76);
          v78 = v182;
          *(_DWORD *)(*(_QWORD *)v182 + 240LL) = v65;
          *(_DWORD *)(*(_QWORD *)v78 + 244LL) = 1;
          *(_DWORD *)(*(_QWORD *)v78 + 248LL) = *(_DWORD *)(v47 + 2);
          *(_QWORD *)(*(_QWORD *)v78 + 256LL) = *(unsigned int *)(v47 + 10);
          Utility::GetDateTimeIso915(&v190, v47 + 18);
          *(_OWORD *)(*(_QWORD *)v78 + 184LL) = v190;
          *(_OWORD *)(*(_QWORD *)v78 + 200LL) = v190;
          *(_OWORD *)(*(_QWORD *)v78 + 216LL) = v190;
          *(_BYTE *)(*(_QWORD *)v78 + 177LL) = v47[25] & 1;
          v79 = *v48;
          v177 = v78;
          if ( v78 )
            ++v78[2];
          ImapiDirectoryInfo::AddImportedFile(v79, &v177);
          v80 = Utility::BytesToRequiredSectors(*(unsigned int *)(v47 + 10));
          v81 = *(_DWORD *)(v47 + 2);
          if ( v154 < v81 + v80 )
          {
            v82 = Utility::BytesToRequiredSectors(*(unsigned int *)(v47 + 10));
            v81 = *(_DWORD *)(v47 + 2);
            v154 = v81 + v82;
          }
          v83 = v165;
          if ( v165 > v81 )
            v83 = v81;
          v165 = v83;
          SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&v182);
        }
        ++v162;
        v84 = (OLECHAR *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AllocSysString(&v161);
        v85 = *(_QWORD *)(a1[6] + 664LL);
        v86 = (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 120LL))(a1);
        CProxy_DFileSystemImageImportEvents<CMsftFileSystemImage>::Fire_ImportUpdate(
          v85 + 56,
          v86,
          (_DWORD)v84,
          v157,
          v156,
          v162,
          -1);
        SysFreeString(v84);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v161);
        v54 = v159;
      }
      v87 = Utility::RoundUpToEvenByteBoundary(*v47);
      v60 = v87 + (_DWORD)v195;
      v59 = v87 + v164;
      v47 += v87;
      v58 = (unsigned int)v172;
    }
    v21 = v154;
    if ( v154 < v54 )
      v21 = v54;
    v154 = v21;
    v88 = v157 + 1;
    v157 = v88;
    if ( v88 >= v156 )
    {
      SysFreeString(v57);
      SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&v166);
      v49 = (_QWORD **)v170[0];
      break;
    }
    v89 = v88;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v158);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v178);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&Source);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
      &v158,
      MultiByteStr);
    v90 = v158;
    v91 = (char *)Source;
    while ( 1 )
    {
      v92 = (_QWORD **)v170[0];
      v93 = *(unsigned __int16 *)(**((_QWORD **)v170[0] + v89) + 6LL);
      if ( (_WORD)v93 == 1 )
        break;
      v94 = 0;
      if ( !(_WORD)v93 || v93 > v156 )
      {
        v128 = (CIMAPIException *)operator new(0x58u);
        v195 = (CIMAPIException **)v128;
        if ( v128 )
          v129 = CIMAPIException::CIMAPIException(v128, -1062555309, a1[1]);
        else
          v129 = 0;
        SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v195, v129);
        v130 = v195;
        if ( v195 && *v195 )
        {
          CIMAPIException::SetCodeRefInfo(*v195, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsifs.cpp", 1386);
          pExceptionObject = v130;
          if ( v130 )
            ++*((_DWORD *)v130 + 2);
          throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
        }
        CIMAPIException::CIMAPIException(
          (CIMAPIException *)v183,
          (const struct CIMAPIException *)&CIMAPIException::badAlloc);
        throw (CIMAPIException *)v183;
      }
      LODWORD(v195) = v93 - 1;
      v95 = *(_BYTE **)(**((_QWORD **)v170[0] + v93 - 1) + 8LL);
      v96 = v95 - 24;
      v97 = (int *)(v91 - 24);
      if ( v95 - 24 != v91 - 24 )
      {
        if ( v97[4] >= 0 && *v96 == *(_QWORD *)v97 )
        {
          v98 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v96, v95, 0);
          ATL::CStringData::Release((ATL::CStringData *)v97);
          v91 = (char *)(v98 + 24);
          Source = v91;
        }
        else
        {
          ATL::CSimpleStringT<unsigned short,0>::SetString((char **)&Source, v95, *((_DWORD *)v95 - 4));
          v91 = (char *)Source;
        }
      }
      Manager = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::GetManager(
                  &Source,
                  v95,
                  v94);
      ATL::CSimpleStringT<unsigned short,0>::CSimpleStringT<unsigned short,0>(v176, Manager);
      v100 = v163 | 1;
      v168 = v163 | 1;
      v163 |= 1u;
      LOWORD(pExceptionObject) = 92;
      ATL::CSimpleStringT<unsigned short,0>::Concatenate(v176, &pExceptionObject, 1, v91, *((_DWORD *)v91 - 4));
      v101 = *(_BYTE **)ATL::operator+(v184, v176, &v158);
      v103 = v101 - 24;
      v104 = (int *)(v90 - 24);
      if ( v101 - 24 != v90 - 24 )
      {
        if ( v104[4] >= 0 && *v103 == *(_QWORD *)v104 )
        {
          v105 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v103, v101, v102);
          ATL::CStringData::Release((ATL::CStringData *)v104);
          v90 = (char *)(v105 + 24);
          v158 = v90;
        }
        else
        {
          ATL::CSimpleStringT<unsigned short,0>::SetString(&v158, v101, *((_DWORD *)v101 - 4));
          v90 = v158;
        }
      }
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v184);
      v163 = v100 & 0xFFFFFFFE;
      v168 = v100 & 0xFFFFFFFE;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v176);
      v89 = (unsigned int)v195;
    }
    if ( !*((_DWORD *)v90 - 4) )
    {
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v158, (char *)L"\\");
      v90 = v158;
    }
    v106 = a1[6];
    v107 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
             v185,
             &v158);
    v108 = *(__int64 **)FileSystemImage::FindDirectoryItem(v106, v186, v107);
    v175 = v108;
    if ( v108 )
      ++*((_DWORD *)v108 + 2);
    SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(v186);
    if ( !v108 || !*v108 )
    {
      v134 = (CIMAPIException *)operator new(0x58u);
      v195 = (CIMAPIException **)v134;
      if ( v134 )
        v135 = CIMAPIException::CIMAPIException(v134, -1062555366, v90);
      else
        v135 = 0;
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v195, v135);
      v136 = v195;
      if ( v195 && *v195 )
      {
        CIMAPIException::SetCodeRefInfo(*v195, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsifs.cpp", 1404);
        pExceptionObject = v136;
        if ( v136 )
          ++*((_DWORD *)v136 + 2);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v183,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v183;
    }
    _mm_lfence();
    v109 = *(_BYTE **)(*v92[v157] + 8LL);
    v110 = v109 - 24;
    v111 = (int *)(v91 - 24);
    if ( v109 - 24 != v91 - 24 )
    {
      if ( v111[4] >= 0 && *v110 == *(_QWORD *)v111 )
      {
        v112 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v110, v109, 0);
        ATL::CStringData::Release((ATL::CStringData *)v111);
        v91 = (char *)(v112 + 24);
        Source = v91;
      }
      else
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString((char **)&Source, v109, *((_DWORD *)v109 - 4));
        v91 = (char *)Source;
      }
    }
    v113 = *((_DWORD *)v91 - 4);
    v159 = v113;
    v114 = (v91 - v90) >> 1;
    LODWORD(v195) = *((_DWORD *)v90 - 4);
    v115 = (unsigned int)(v113 + (_DWORD)v195);
    if ( (int)((*((_DWORD *)v90 - 3) - v115) | (1 - *((_DWORD *)v90 - 2))) < 0 )
    {
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&v158, v115);
      v90 = v158;
      v113 = v159;
    }
    if ( v114 <= (unsigned int)v195 )
      v91 = &v90[2 * v114];
    memcpy_s(&v90[2 * (unsigned int)v195], 2LL * v113, v91, 2LL * v113);
    ATL::CSimpleStringT<unsigned short,0>::SetLength(&v158, (unsigned int)v195 + v159);
    v116 = ImapiDirectoryInfo::GetFileDirRecord(*v108, v187, &Source);
    SmartPtr<ImportMetadata>::operator=(&v166, v116);
    SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(v187);
    v47 = 0;
    if ( v166 && *(_QWORD *)v166 )
    {
      if ( *(_DWORD *)(*(_QWORD *)v166 + 56LL) && *(_DWORD *)(*(_QWORD *)v166 + 56LL) != 3 )
      {
        v131 = (CIMAPIException *)operator new(0x58u);
        v195 = (CIMAPIException **)v131;
        if ( v131 )
          v132 = CIMAPIException::CIMAPIException(v131, -1062555298, v90, a1[1]);
        else
          v132 = 0;
        SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v195, v132);
        v133 = v195;
        if ( v195 && *v195 )
        {
          CIMAPIException::SetCodeRefInfo(*v195, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsifs.cpp", 1427);
          pExceptionObject = v133;
          if ( v133 )
            ++*((_DWORD *)v133 + 2);
          throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
        }
        CIMAPIException::CIMAPIException(
          (CIMAPIException *)v183,
          (const struct CIMAPIException *)&CIMAPIException::badAlloc);
        throw (CIMAPIException *)v183;
      }
      LOBYTE(v195) = 0;
      v172 = v166;
      ++v166[2];
      SmartPtr<ImportMetadata>::operator=(&v167, &v172);
      SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&v172);
      v48 = v167;
    }
    else
    {
      v117 = (ImapiDirectoryInfo *)operator new(0x318u);
      v193 = v117;
      if ( v117 )
        v118 = ImapiDirectoryInfo::ImapiDirectoryInfo(v117);
      else
        v118 = 0;
      SmartPtr<ImportMetadata>::SmartPtr<ImportMetadata>(&v173, v118);
      SmartPtr<ImportMetadata>::operator=(&v167, &v173);
      SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&v173);
      --*(_DWORD *)(a1[6] + 20LL);
      v119 = *v108;
      v48 = v167;
      v174 = v167;
      if ( v167 )
        ++*((_DWORD *)v167 + 2);
      ImapiDirectoryInfo::AddDirectory(v119, &v174);
      LOBYTE(v195) = 1;
    }
    SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&v175);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&Source);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v178);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v158);
    SysFreeString(v57);
    SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&v166);
    v21 = v154;
    v49 = (_QWORD **)v170[0];
    v51 = v157;
  }
  *(_DWORD *)(a1[6] + 612LL) = v165;
  *(_DWORD *)(a1[6] + 616LL) = v21;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 51, &WPP_0f921ac20c883071ccb82ce92dc0d426_Traceguids);
  }
  SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&v167);
  std::vector<SmartPtr<IsoPathTable>>::_Destroy(v137, v49, v170[1]);
  operator delete(v49);
  SmartArrayPtr<unsigned char>::~SmartArrayPtr<unsigned char>(&v179);
  SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&v180);
  SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(a2);
}

```

## disassembly

```asm
0x180007e80  mov     [rsp-8+arg_0], rbx
0x180007e85  mov     [rsp-8+arg_8], rdx
0x180007e8a  push    rbp
0x180007e8b  push    rsi
0x180007e8c  push    rdi
0x180007e8d  push    r12
0x180007e8f  push    r13
0x180007e91  push    r14
0x180007e93  push    r15
0x180007e95  lea     rbp, [rsp-0E0h]
0x180007e9d  sub     rsp, 1E0h
0x180007ea4  mov     r14, rdx
0x180007ea7  mov     r12, rcx
0x180007eaa  xor     r15d, r15d
0x180007ead  mov     eax, r15d
0x180007eb0  mov     [rbp+110h+var_18C], eax
0x180007eb3  mov     [rbp+110h+var_170], eax
0x180007eb6  lea     rax, WPP_GLOBAL_Control
0x180007ebd  mov     rcx, cs:WPP_GLOBAL_Control
0x180007ec4  cmp     rcx, rax
0x180007ec7  jz      short loc_180007EE9
0x180007ec9  test    byte ptr [rcx+44h], 8
0x180007ecd  jz      short loc_180007EE9
0x180007ecf  cmp     byte ptr [rcx+41h], 5
0x180007ed3  jb      short loc_180007EE9
0x180007ed5  lea     edx, [r15+31h]
0x180007ed9  lea     r8, WPP_0f921ac20c883071ccb82ce92dc0d426_Traceguids
0x180007ee0  mov     rcx, [rcx+38h]
0x180007ee4  call    WPP_SF_
0x180007ee9  mov     [rsp+210h+var_1BC], r15d
0x180007eee  mov     rax, [r14]
0x180007ef1  mov     [rbp+110h+arg_10], rax
0x180007ef8  mov     edi, 1
0x180007efd  test    rax, rax
0x180007f00  jz      short loc_180007F05
0x180007f02  add     [rax+8], edi
0x180007f05  lea     r8, [rbp+110h+arg_10]
0x180007f0c  lea     rdx, [rbp+110h+var_108]
0x180007f10  mov     rcx, r12
0x180007f13  call    ?FindVolumeDescriptor@IsoFileSystemSupport@@IEAA?AV?$SmartPtr@VVolumeRecognitionStructureBase@@@@V?$SmartClassPtr@VCDiscReader@@V1@@@@Z; IsoFileSystemSupport::FindVolumeDescriptor(SmartClassPtr<CDiscReader,CDiscReader>)
0x180007f18  nop
0x180007f19  mov     rax, [rbp+110h+var_108]
0x180007f1d  test    rax, rax
0x180007f20  jz      loc_18000955D
0x180007f26  cmp     [rax], r15
0x180007f29  jz      loc_18000955D
0x180007f2f  mov     rcx, [rax]
0x180007f32  mov     rax, [rcx]
0x180007f35  mov     rax, [rax+58h]
0x180007f39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f3e  mov     r13, rax
0x180007f41  mov     [rbp+110h+var_140], rax
0x180007f45  mov     rbx, [r12]
0x180007f49  mov     rcx, r12
0x180007f4c  mov     rax, [rbx+0A0h]
0x180007f53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f58  movzx   ecx, al
0x180007f5b  xor     edx, edx
0x180007f5d  lea     eax, [rdx+20h]
0x180007f60  div     ecx
0x180007f62  mov     r9d, eax
0x180007f65  lea     r8, [r13+28h]
0x180007f69  lea     rdx, [rbp+110h+pExceptionObject]
0x180007f70  mov     rcx, r12
0x180007f73  mov     rax, [rbx+0B8h]
0x180007f7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f7f  nop
0x180007f80  mov     rsi, [r12+30h]
0x180007f85  mov     rdx, [rax]
0x180007f88  lea     rcx, [rdx-18h]
0x180007f8c  mov     rdi, [rsi+150h]
0x180007f93  add     rdi, 0FFFFFFFFFFFFFFE8h
0x180007f97  cmp     rcx, rdi
0x180007f9a  jz      short loc_180007FD8
0x180007f9c  cmp     [rdi+10h], r15d
0x180007fa0  jl      short loc_180007FC7
0x180007fa2  mov     rax, [rdi]
0x180007fa5  cmp     [rcx], rax
0x180007fa8  jnz     short loc_180007FC7
0x180007faa  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180007faf  mov     rbx, rax
0x180007fb2  mov     rcx, rdi; this
0x180007fb5  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180007fba  lea     rax, [rbx+18h]
0x180007fbe  mov     [rsi+150h], rax
0x180007fc5  jmp     short loc_180007FD8
0x180007fc7  mov     r8d, [rdx-10h]
0x180007fcb  lea     rcx, [rsi+150h]
0x180007fd2  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180007fd7  nop
0x180007fd8  lea     rcx, [rbp+110h+pExceptionObject]; void *
0x180007fdf  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180007fe4  mov     rax, [r14]
0x180007fe7  mov     rcx, [rax]
0x180007fea  mov     rax, [rcx]
0x180007fed  mov     rax, [rax+40h]
0x180007ff1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ff6  add     eax, 10h
0x180007ff9  cmp     eax, [r13+8Ch]
0x180008000  jnb     loc_1800094B6
0x180008006  cmp     [r13+84h], r15d
0x18000800d  jbe     loc_1800094B6
0x180008013  mov     ecx, 1000h; unsigned __int64
0x180008018  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000801d  mov     rdx, rax
0x180008020  lea     rcx, [rbp+110h+var_110]
0x180008024  call    ??0?$SmartArrayPtr@E@@QEAA@PEAE@Z; SmartArrayPtr<uchar>::SmartArrayPtr<uchar>(uchar *)
0x180008029  nop
0x18000802a  mov     ebx, [r13+8Ch]
0x180008031  mov     rax, [r14]
0x180008034  mov     rdi, [rbp+110h+var_110]
0x180008038  test    rdi, rdi
0x18000803b  jz      short loc_180008042
0x18000803d  mov     rdx, [rdi]
0x180008040  jmp     short loc_180008045
0x180008042  mov     rdx, r15; void *
0x180008045  lea     rcx, [rsp+210h+var_1BC]
0x18000804a  mov     [rsp+210h+var_1F0], rcx; unsigned int *
0x18000804f  mov     r9d, ebx; unsigned int
0x180008052  mov     r8d, 2; unsigned int
0x180008058  mov     rcx, [rax]; this
0x18000805b  call    ?BlockRead@CDiscReader@@QEAAXPEAXKKPEAK@Z; CDiscReader::BlockRead(void *,ulong,ulong,ulong *)
0x180008060  cmp     [rsp+210h+var_1BC], 2
0x180008065  jz      loc_180008110
0x18000806b  mov     ecx, 58h ; 'X'; unsigned __int64
0x180008070  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008075  mov     [rbp+110h+arg_10], rax
0x18000807c  test    rax, rax
0x18000807f  jz      short loc_180008093
0x180008081  mov     r8d, ebx
0x180008084  mov     edx, 0C0AAB157h; int
0x180008089  mov     rcx, rax; this
0x18000808c  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x180008091  jmp     short loc_180008096
0x180008093  mov     rax, r15
0x180008096  mov     rdx, rax
0x180008099  lea     rcx, [rbp+110h+arg_10]
0x1800080a0  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x1800080a5  nop
0x1800080a6  mov     rbx, [rbp+110h+arg_10]
0x1800080ad  test    rbx, rbx
0x1800080b0  jz      short loc_1800080EF
0x1800080b2  cmp     [rbx], r15
0x1800080b5  jz      short loc_1800080EF
0x1800080b7  mov     r8d, 46Ah; int
0x1800080bd  lea     rdx, aDriversStorage_7; "drivers\\storage\\imapi2\\filesystemima"...
0x1800080c4  mov     rcx, [rbx]; this
0x1800080c7  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x1800080cc  mov     [rbp+110h+pExceptionObject], rbx
0x1800080d3  test    rbx, rbx
0x1800080d6  jz      short loc_1800080DB
0x1800080d8  inc     dword ptr [rbx+8]
0x1800080db  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x1800080e2  lea     rcx, [rbp+110h+pExceptionObject]; pExceptionObject
0x1800080e9  call    _CxxThrowException_0
0x1800080ef  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x1800080f6  lea     rcx, [rbp+110h+var_F0]; this
0x1800080fa  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x1800080ff  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x180008106  lea     rcx, [rbp+110h+var_F0]; pExceptionObject
0x18000810a  call    _CxxThrowException_0
0x180008110  lea     esi, [rbx+2]
0x180008113  mov     [rsp+210h+var_1C0], esi
0x180008117  test    rdi, rdi
0x18000811a  jz      short loc_180008121
0x18000811c  mov     r14, [rdi]
0x18000811f  jmp     short loc_180008124
0x180008121  mov     r14, r15
0x180008124  xorps   xmm0, xmm0
0x180008127  movdqu  xmmword ptr [rbp+110h+var_160], xmm0
0x18000812c  mov     [rbp+110h+var_150], r15
0x180008130  mov     [rsp+210h+var_1B8], r15d
0x180008135  xor     eax, eax
0x180008137  mov     dword ptr [rbp+110h+arg_10], eax
0x18000813d  cmp     eax, [r13+84h]
0x180008144  jnb     loc_180008459
0x18000814a  mov     ecx, 10h; unsigned __int64
0x18000814f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008154  mov     rbx, rax
0x180008157  mov     [rbp+110h+pExceptionObject], rax
0x18000815e  xor     esi, esi
0x180008160  test    rax, rax
0x180008163  jz      short loc_180008170
0x180008165  lea     rcx, [rax+8]; void *
0x180008169  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18000816e  jmp     short loc_180008173
0x180008170  mov     rbx, rsi
0x180008173  mov     rdx, rbx
0x180008176  lea     rcx, [rbp+110h+var_168]
0x18000817a  call    ??0?$SmartPtr@UIsoPathTable@@@@QEAA@PEAUIsoPathTable@@@Z; SmartPtr<IsoPathTable>::SmartPtr<IsoPathTable>(IsoPathTable *)
0x18000817f  nop
0x180008180  mov     rbx, [rbp+110h+var_168]
0x180008184  test    rbx, rbx
0x180008187  jz      short loc_18000818E
0x180008189  mov     rcx, [rbx]
0x18000818c  jmp     short loc_180008191
0x18000818e  mov     rcx, rsi
0x180008191  mov     rax, [r14]
0x180008194  mov     [rcx], rax
0x180008197  mov     rsi, [r12]
0x18000819b  mov     rcx, r12
0x18000819e  mov     rax, [rsi+0A0h]
0x1800081a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800081aa  movzx   ecx, al
0x1800081ad  movzx   eax, byte ptr [r14]
0x1800081b1  xor     edx, edx
0x1800081b3  div     ecx
0x1800081b5  mov     r9d, eax
0x1800081b8  lea     r8, [r14+8]
0x1800081bc  lea     rdx, [rbp+110h+var_138]
0x1800081c0  mov     rcx, r12
0x1800081c3  mov     rax, [rsi+0B8h]
0x1800081ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800081cf  nop
0x1800081d0  mov     r9, [rbx]
0x1800081d3  add     r9, 8
0x1800081d7  mov     [rbp+110h+pExceptionObject], r9
0x1800081de  mov     rdx, [rax]
0x1800081e1  lea     rcx, [rdx-18h]
0x1800081e5  mov     r13, [r9]
0x1800081e8  add     r13, 0FFFFFFFFFFFFFFE8h
0x1800081ec  cmp     rcx, r13
0x1800081ef  jz      short loc_18000822E
0x1800081f1  cmp     dword ptr [r13+10h], 0
0x1800081f6  jl      short loc_180008221
0x1800081f8  mov     rax, [r13+0]
0x1800081fc  cmp     [rcx], rax
0x1800081ff  jnz     short loc_180008221
0x180008201  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180008206  mov     rsi, rax
0x180008209  mov     rcx, r13; this
0x18000820c  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180008211  lea     rax, [rsi+18h]
0x180008215  mov     rcx, [rbp+110h+pExceptionObject]
0x18000821c  mov     [rcx], rax
0x18000821f  jmp     short loc_18000822E
0x180008221  mov     r8d, [rdx-10h]
0x180008225  mov     rcx, r9
0x180008228  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18000822d  nop
0x18000822e  lea     rcx, [rbp+110h+var_138]; void *
0x180008232  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180008237  lea     rax, [rbp+110h+var_168]
0x18000823b  mov     rcx, [rbp+110h+var_160+8]
0x18000823f  cmp     rax, rcx
0x180008242  jnb     short loc_180008284
0x180008244  lea     rdx, [rbp+110h+var_168]
0x180008248  mov     rax, [rbp+110h+var_160]
0x18000824c  cmp     rax, rdx
0x18000824f  ja      short loc_180008284
0x180008251  lea     rsi, [rbp+110h+var_168]
0x180008255  sub     rsi, rax
0x180008258  sar     rsi, 3
0x18000825c  cmp     rcx, [rbp+110h+var_150]
0x180008260  jnz     short loc_180008273
0x180008262  lea     rcx, [rbp+110h+var_160]
0x180008266  call    ?_Reserve@?$vector@V?$SmartPtr@UIsoPathTable@@@@V?$allocator@V?$SmartPtr@UIsoPathTable@@@@@std@@@std@@IEAAX_K@Z; std::vector<SmartPtr<IsoPathTable>>::_Reserve(unsigned __int64)
0x18000826b  mov     rcx, [rbp+110h+var_160+8]
0x18000826f  mov     rax, [rbp+110h+var_160]
0x180008273  mov     rax, [rax+rsi*8]
0x180008277  mov     [rcx], rax
0x18000827a  test    rax, rax
0x18000827d  jz      short loc_1800082A2
0x18000827f  inc     dword ptr [rax+8]
0x180008282  jmp     short loc_1800082A2
0x180008284  cmp     rcx, [rbp+110h+var_150]
0x180008288  jnz     short loc_180008297
0x18000828a  lea     rcx, [rbp+110h+var_160]
0x18000828e  call    ?_Reserve@?$vector@V?$SmartPtr@UIsoPathTable@@@@V?$allocator@V?$SmartPtr@UIsoPathTable@@@@@std@@@std@@IEAAX_K@Z; std::vector<SmartPtr<IsoPathTable>>::_Reserve(unsigned __int64)
0x180008293  mov     rcx, [rbp+110h+var_160+8]
0x180008297  mov     [rcx], rbx
0x18000829a  test    rbx, rbx
0x18000829d  jz      short loc_1800082A2
0x18000829f  inc     dword ptr [rbx+8]
0x1800082a2  add     rcx, 8
0x1800082a6  mov     [rbp+110h+var_160+8], rcx
0x1800082aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800082b1  lea     rax, WPP_GLOBAL_Control
0x1800082b8  cmp     rcx, rax
0x1800082bb  jz      short loc_180008307
0x1800082bd  test    byte ptr [rcx+44h], 4
0x1800082c1  jz      short loc_180008307
0x1800082c3  cmp     byte ptr [rcx+41h], 4
0x1800082c7  jb      short loc_180008307
0x1800082c9  mov     r8, [rbx]
0x1800082cc  movzx   edx, word ptr [r8+6]
0x1800082d1  movzx   r9d, byte ptr [r8+1]
0x1800082d6  movzx   r10d, byte ptr [r8]
0x1800082da  mov     rax, [r8+8]
0x1800082de  mov     [rsp+210h+var_1D0], rax
0x1800082e3  mov     [rsp+210h+var_1D8], edx
0x1800082e7  mov     eax, [r8+2]
0x1800082eb  mov     [rsp+210h+var_1E0], eax
0x1800082ef  mov     [rsp+210h+var_1E8], r9d
0x1800082f4  mov     dword ptr [rsp+210h+var_1F0], r10d
0x1800082f9  mov     r9d, [rsp+210h+var_1B8]
0x1800082fe  mov     rcx, [rcx+38h]
0x180008302  call    WPP_SF_dddDdS
0x180008307  movzx   ecx, byte ptr [r14]
0x18000830b  add     ecx, 8; int
  ... truncated ...
```
