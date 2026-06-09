# CellState::FromCellularSnapshot(_MVCellularStateHdr *)

- ea: `0x180038b00`
- end: `0x18003958b`
- name: `?FromCellularSnapshot@CellState@@SA?AV1@PEAU_MVCellularStateHdr@@@Z`
- size: `2699`
- prototype: `_QWORD *__fastcall(_QWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002e0a0`

## callees

- `0x180002034`
- `0x18000e1f8`
- `0x18000e308`
- `0x18000f598`
- `0x18000f84c`
- `0x18000fc8c`
- `0x18000fd24`
- `0x1800128a4`
- `0x180012c70`
- `0x180012d04`
- `0x180012d80`
- `0x180034aec`
- `0x180038498`
- `0x180038554`
- `0x1800386fc`
- `0x180038b00`
- `0x180039594`
- `0x1800397ac`
- `0x18003b2d0`
- `0x18003b3b8`
- `0x18003b96a`
- `0x18003b9a0`
- `0x18003f010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180038d10`
- `msvcrt!??3@YAXPEAX@Z` at `0x180038eeb`
- `msvcrt!??3@YAXPEAX@Z` at `0x180039230`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003928e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003932e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180038d10`
- `msvcrt!??3@YAXPEAX@Z` at `0x180038eeb`
- `msvcrt!??3@YAXPEAX@Z` at `0x180039230`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003928e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003932e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003946d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003946d`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180038bd7`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180038bd7`

## string_xrefs

- `0x1800394b9`: `onecoreuap\admin\prov\multivariant\handlers\common\cellstate.cpp`
- `0x1800394d1`: `onecoreuap\admin\prov\multivariant\handlers\common\cellstate.cpp`
- `0x1800394e6`: `onecoreuap\admin\prov\multivariant\handlers\common\cellstate.cpp`
- `0x1800394fe`: `onecoreuap\admin\prov\multivariant\handlers\common\cellstate.cpp`
- `0x180039516`: `onecoreuap\admin\prov\multivariant\handlers\common\cellstate.cpp`
- `0x18003952e`: `onecoreuap\admin\prov\multivariant\handlers\common\cellstate.cpp`
- `0x180039549`: `onecoreuap\admin\prov\multivariant\handlers\common\cellstate.cpp`
- `0x180039561`: `onecoreuap\admin\prov\multivariant\handlers\common\cellstate.cpp`
- `0x180039579`: `onecoreuap\admin\prov\multivariant\handlers\common\cellstate.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall CellState::FromCellularSnapshot(_QWORD *a1, _DWORD *a2)
{
  _DWORD *v2; // r13
  _QWORD *v3; // r12
  _DWORD *v4; // r14
  int v5; // edi
  unsigned int v6; // eax
  HRESULT v7; // eax
  _QWORD *v8; // rax
  _QWORD *v9; // rbx
  char *v10; // rdx
  unsigned __int64 v11; // r8
  char *v12; // rdx
  unsigned __int64 v13; // r8
  __int64 v14; // rbx
  unsigned int *v15; // r12
  unsigned int v16; // eax
  _DWORD *v17; // r12
  __int64 v18; // rdx
  __int64 v19; // r8
  Uicc **v20; // r13
  char *v21; // rdx
  unsigned __int64 v22; // r8
  Uicc *v23; // rax
  Uicc *v24; // rbx
  Uicc *v25; // rdi
  Uicc *v26; // rbx
  __int64 *v27; // rax
  __int64 v28; // rdx
  __int64 v29; // rdx
  volatile signed __int32 *v30; // rbx
  unsigned int v31; // r12d
  unsigned __int16 v32; // cx
  unsigned __int16 v33; // di
  Uicc *v34; // rbx
  _QWORD *v35; // rcx
  unsigned __int64 v36; // r8
  Uicc *v37; // rbx
  _QWORD *v38; // rcx
  unsigned __int64 v39; // r8
  unsigned int j; // r12d
  _DWORD *v41; // r15
  Uicc *v42; // rdi
  _QWORD *v43; // rbx
  char *v44; // rdx
  unsigned __int64 v45; // r8
  char *v46; // rdx
  unsigned __int64 v47; // r8
  const char *v48; // r9
  _DWORD *v49; // rbx
  __int64 v50; // rax
  _DWORD *v51; // rdi
  __int64 v52; // rax
  volatile signed __int32 *v53; // rbx
  int v55; // [rsp+20h] [rbp-198h]
  unsigned int i; // [rsp+20h] [rbp-198h]
  int v57; // [rsp+24h] [rbp-194h]
  int v58; // [rsp+28h] [rbp-190h]
  unsigned int v59; // [rsp+2Ch] [rbp-18Ch]
  unsigned int v60; // [rsp+30h] [rbp-188h]
  _QWORD *v61; // [rsp+38h] [rbp-180h]
  LPOLESTR lpsz; // [rsp+40h] [rbp-178h] BYREF
  _DWORD *v63; // [rsp+48h] [rbp-170h]
  _DWORD *v64; // [rsp+50h] [rbp-168h]
  __int128 v65; // [rsp+58h] [rbp-160h] BYREF
  _DWORD *v66; // [rsp+68h] [rbp-150h]
  Uicc **v67; // [rsp+70h] [rbp-148h]
  _DWORD *v68; // [rsp+78h] [rbp-140h]
  _QWORD *v69; // [rsp+80h] [rbp-138h]
  _DWORD *v70; // [rsp+88h] [rbp-130h]
  _DWORD *v71; // [rsp+90h] [rbp-128h]
  _DWORD *v72; // [rsp+98h] [rbp-120h]
  _DWORD *v73; // [rsp+A0h] [rbp-118h]
  _DWORD *v74; // [rsp+A8h] [rbp-110h]
  _DWORD *v75; // [rsp+B0h] [rbp-108h]
  unsigned int *v76; // [rsp+B8h] [rbp-100h]
  _DWORD *v77; // [rsp+C0h] [rbp-F8h]
  _QWORD *v78; // [rsp+C8h] [rbp-F0h]
  Uicc *v79; // [rsp+D0h] [rbp-E8h]
  __int64 v80; // [rsp+D8h] [rbp-E0h] BYREF
  volatile signed __int32 *v81; // [rsp+E0h] [rbp-D8h]
  void *Src[2]; // [rsp+E8h] [rbp-D0h] BYREF
  __int64 v83; // [rsp+F8h] [rbp-C0h]
  unsigned __int64 v84; // [rsp+100h] [rbp-B8h]
  void *v85[4]; // [rsp+110h] [rbp-A8h] BYREF
  _OWORD v86[3]; // [rsp+130h] [rbp-88h] BYREF
  __int128 v87; // [rsp+160h] [rbp-58h] BYREF
  __int128 v88; // [rsp+170h] [rbp-48h]
  int v89; // [rsp+180h] [rbp-38h] BYREF
  __int16 v90; // [rsp+184h] [rbp-34h]
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+0h]

  v2 = a2;
  v63 = a2;
  v3 = a1;
  v61 = a1;
  v69 = a1;
  v70 = a2;
  if ( *a2 != 2 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF3,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\cellstate.cpp",
      (const char *)0x80070057LL,
      v55);
  v4 = a2 + 4;
  v5 = a2[2];
  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  a1[3] = 0;
  a1[4] = 0;
  a1[3] = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,std::shared_ptr<Modem>>>>::_Buyheadnode(retaddr);
  *((_DWORD *)v3 + 10) = v5;
  v58 = 1;
  v57 = 1;
  v6 = 0;
  while ( 1 )
  {
    v60 = v6;
    if ( v6 >= v2[3] )
      break;
    if ( *v4 != 3 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xFC,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\cellstate.cpp",
        (const char *)0x80070057LL,
        v55);
    lpsz = 0;
    v7 = StringFromCLSID((const IID *const)(v4 + 2), &lpsz);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x100,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\cellstate.cpp",
        (const char *)(unsigned int)v7,
        v55);
    v77 = v4;
    v72 = v4;
    v8 = operator new(0x78u);
    v9 = v8;
    v78 = v8;
    if ( v8 )
    {
      v10 = (char *)lpsz;
      v8[3] = 7;
      v8[2] = 0;
      *(_WORD *)v8 = 0;
      if ( *(_WORD *)v10 )
      {
        v11 = -1;
        do
          ++v11;
        while ( *(_WORD *)&v10[2 * v11] );
      }
      else
      {
        v11 = 0;
      }
      std::wstring::assign(v8, v10, v11);
      v9[14] = 0;
      v9[7] = 7;
      v9[6] = 0;
      *((_WORD *)v9 + 16) = 0;
      v9[8] = 0;
      v9[9] = 0;
      v9[10] = 0;
      v9[11] = 0;
      v9[12] = 0;
      v9[13] = 0;
      v58 |= 0x1Eu;
      v57 = v58;
      *(_DWORD *)((char *)v9 + 114) = 0;
      *((_WORD *)v9 + 59) = 0;
    }
    else
    {
      v9 = 0;
    }
    v65 = 0;
    std::shared_ptr<Modem>::_Resetp<Modem>(&v65, v9);
    v12 = (char *)(v4 + 6);
    v84 = 7;
    v83 = 0;
    LOWORD(Src[0]) = 0;
    if ( *((_WORD *)v4 + 12) )
    {
      v13 = -1;
      do
        ++v13;
      while ( *(_WORD *)&v12[2 * v13] );
    }
    else
    {
      v13 = 0;
    }
    std::wstring::assign(Src, v12, v13);
    v14 = v65;
    std::wstring::operator=((void *)(v65 + 32), Src);
    if ( v84 >= 8 )
      operator delete(Src[0]);
    *(_BYTE *)(v14 + 112) = v4[16] != 0;
    *(_BYTE *)(v14 + 113) = v4[15] != 0;
    v15 = v4 + 17;
    v76 = v4 + 17;
    std::vector<nullable_any<Uicc>>::resize(v14 + 64, (unsigned int)v4[17]);
    std::vector<unsigned __int64>::resize(v14 + 88, (unsigned int)v4[17]);
    v4 += 18;
    v16 = 0;
    while ( 1 )
    {
      v59 = v16;
      if ( v16 >= *v15 )
        break;
      if ( *v4 != 2 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x10D,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\cellstate.cpp",
          (const char *)0x80070057LL,
          v55);
      v17 = v4;
      v73 = v4;
      v4 += 19;
      v18 = (unsigned int)v17[2];
      v19 = *(_QWORD *)(v14 + 64);
      *(_QWORD *)(*(_QWORD *)(v14 + 88) + 8LL * (unsigned int)v17[3]) = v18;
      if ( v17[4] )
      {
        v20 = (Uicc **)(v19 + 8 * v18);
        v67 = v20;
        v21 = (char *)(v17 + 5);
        v85[3] = (void *)7;
        v85[2] = 0;
        LOWORD(v85[0]) = 0;
        if ( *((_WORD *)v17 + 10) )
        {
          v22 = -1;
          do
            ++v22;
          while ( *(_WORD *)&v21[2 * v22] );
        }
        else
        {
          v22 = 0;
        }
        std::wstring::assign(v85, v21, v22);
        v88 = 0;
        memset(v86, 0, sizeof(v86));
        v87 = 0;
        *(_DWORD *)((char *)&v88 + 10) = 0;
        HIWORD(v88) = 0;
        v23 = (Uicc *)operator new(0x70u);
        v24 = v23;
        v79 = v23;
        if ( v23 )
        {
          *((_QWORD *)v23 + 3) = 7;
          *((_QWORD *)v23 + 2) = 0;
          *(_WORD *)v23 = 0;
          std::wstring::assign((void **)v23, v85, 0, 0xFFFFFFFFFFFFFFFFuLL);
          std::vector<std::wstring>::vector<std::wstring>((char *)v24 + 32, v86);
          std::vector<Line>::vector<Line>((char *)v24 + 56, (char *)&v86[1] + 8);
          std::shared_ptr<CMvExtensionKey const>::shared_ptr<CMvExtensionKey const>((_QWORD *)v24 + 10, (__int64 *)&v87);
          *((_QWORD *)v24 + 12) = v88;
          *((_WORD *)v24 + 52) = WORD4(v88);
        }
        else
        {
          v24 = 0;
        }
        v25 = *v20;
        if ( v24 != *v20 )
        {
          if ( v25 )
          {
            Uicc::~Uicc(*v20);
            operator delete(v25);
          }
          *v20 = v24;
        }
        Uicc::~Uicc((Uicc *)v85);
        v26 = *v20;
        v27 = std::shared_ptr<CMvExtensionKey const>::shared_ptr<CMvExtensionKey const>(&v80, (__int64 *)&v65);
        v28 = v27[1];
        v27[1] = *((_QWORD *)v26 + 11);
        *((_QWORD *)v26 + 11) = v28;
        v29 = *v27;
        *v27 = *((_QWORD *)v26 + 10);
        *((_QWORD *)v26 + 10) = v29;
        v30 = v81;
        if ( v81 )
        {
          if ( _InterlockedExchangeAdd(v81 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v30)(v30);
            if ( _InterlockedExchangeAdd(v30 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v30 + 8LL))(v30);
          }
        }
        *((_DWORD *)*v20 + 24) = v17[2];
        *((_DWORD *)*v20 + 25) = v17[4];
        *((_BYTE *)*v20 + 105) = v17[16] == 1;
        v31 = (unsigned int)(v17[17] + 1) >> 1;
        for ( i = 0; i < v31; ++v4 )
        {
          v89 = 0;
          v90 = 0;
          v32 = *(_WORD *)v4;
          if ( *(_WORD *)v4 == 0xFFFF )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x128,
              (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\cellstate.cpp",
              (const char *)0x80070057LL,
              i);
          v33 = *((_WORD *)v4 + 1);
          LOWORD(v89) = (unsigned __int8)v32;
          HIWORD(v89) = HIBYTE(v32);
          v34 = *v20;
          if ( *((_QWORD *)*v20 + 5) == *((_QWORD *)*v20 + 6) )
            std::vector<std::wstring>::_Reserve((char *)v34 + 32);
          v35 = (_QWORD *)*((_QWORD *)v34 + 5);
          v35[3] = 7;
          v35[2] = 0;
          *(_WORD *)v35 = 0;
          if ( (_WORD)v89 )
          {
            v36 = -1;
            do
              ++v36;
            while ( *((_WORD *)&v89 + v36) );
          }
          else
          {
            v36 = 0;
          }
          std::wstring::assign(v35, (char *)&v89, v36);
          *((_QWORD *)v34 + 5) += 32LL;
          if ( v33 != 0xFFFF )
          {
            LOWORD(v89) = (unsigned __int8)v33;
            HIWORD(v89) = HIBYTE(v33);
            v37 = *v20;
            if ( *((_QWORD *)*v20 + 5) == *((_QWORD *)*v20 + 6) )
              std::vector<std::wstring>::_Reserve((char *)v37 + 32);
            v38 = (_QWORD *)*((_QWORD *)v37 + 5);
            v38[3] = 7;
            v38[2] = 0;
            *(_WORD *)v38 = 0;
            if ( (_WORD)v89 )
            {
              v39 = -1;
              do
                ++v39;
              while ( *((_WORD *)&v89 + v39) );
            }
            else
            {
              v39 = 0;
            }
            std::wstring::assign(v38, (char *)&v89, v39);
            *((_QWORD *)v37 + 5) += 32LL;
          }
          ++i;
        }
        for ( j = 0; ; ++j )
        {
          v55 = j;
          if ( j >= v73[18] )
            break;
          if ( *v4 != 1 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x138,
              (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\cellstate.cpp",
              (const char *)0x80070057LL,
              j);
          v75 = v4;
          v41 = v4;
          v68 = v4;
          v64 = v4 + 24;
          v74 = v4 + 24;
          v42 = *v20;
          if ( *((_QWORD *)*v20 + 8) == *((_QWORD *)*v20 + 9) )
            std::vector<Line>::_Reserve((char *)v42 + 56);
          v43 = (_QWORD *)*((_QWORD *)v42 + 8);
          memset_0(v43, 0, 0x60u);
          v43[3] = 7;
          v43[7] = 7;
          *((_QWORD *)v42 + 8) += 96LL;
          v44 = (char *)(v4 + 2);
          if ( *((_WORD *)v4 + 4) )
          {
            v45 = -1;
            do
              ++v45;
            while ( *(_WORD *)&v44[2 * v45] );
          }
          else
          {
            v45 = 0;
          }
          std::wstring::assign((_QWORD *)(*((_QWORD *)*v20 + 8) - 64LL), v44, v45);
          *(_QWORD *)(*((_QWORD *)*v20 + 8) - 8LL) = (unsigned int)v4[10];
          v46 = (char *)(v4 + 11);
          v84 = 7;
          v83 = 0;
          LOWORD(Src[0]) = 0;
          if ( *((_WORD *)v4 + 22) )
          {
            v47 = -1;
            do
              ++v47;
            while ( *(_WORD *)&v46[2 * v47] );
          }
          else
          {
            v47 = 0;
          }
          std::wstring::assign(Src, v46, v47);
          nullable_any<std::wstring>::operator=(*((_QWORD *)*v20 + 8) - 32LL, Src);
          if ( v84 >= 8 )
            operator delete(Src[0]);
          v49 = v4 + 22;
          v71 = v4 + 22;
          v66 = v4 + 22;
          if ( v4[22] )
          {
            try
            {
              v50 = CellState::Gid1FromBytes(Src);
              nullable_any<std::wstring>::operator=(*((_QWORD *)*v20 + 8) - 16LL, v50);
              if ( v84 >= 8 )
                operator delete(Src[0]);
            }
            catch ( ... )
            {
              wil::details::in1diag3::Log_CaughtException(
                retaddr,
                (void *)0x147,
                (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\cellstate.cpp",
                v48);
              v20 = v67;
              v41 = v68;
              v58 = v57;
              v61 = v69;
              v63 = v70;
              v49 = v71;
            }
          }
          try
          {
            v51 = v41 + 23;
            v64 = v41 + 23;
            if ( v41[23] )
            {
              v52 = CellState::PnnFromBytes(Src);
              nullable_any<std::wstring>::operator=(*((_QWORD *)*v20 + 8) - 24LL, v52);
              if ( v84 >= 8 )
                operator delete(Src[0]);
            }
          }
          catch ( ... )
          {
            wil::details::in1diag3::Log_CaughtException(
              retaddr,
              (void *)0x151,
              (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\cellstate.cpp",
              v48);
            v20 = v67;
            v41 = v68;
            v58 = v57;
            v61 = v69;
            v63 = v70;
            v49 = v71;
            v51 = v64;
          }
          v4 = &v74[(unsigned __int64)(unsigned int)(*v49 + 3 + *v51) >> 2];
          if ( v75[1] != (unsigned int)(v4 - v41) )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x155,
              (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\cellstate.cpp",
              (const char *)0x80070057LL,
              j);
        }
        if ( v73[1] != (unsigned int)(v4 - v73) )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x158,
            (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\cellstate.cpp",
            (const char *)0x80070057LL,
            j);
        v14 = v65;
      }
      v16 = v59 + 1;
      v15 = v76;
    }
    if ( v72[1] != (unsigned int)(v4 - v77) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x15B,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\cellstate.cpp",
        (const char *)0x80070057LL,
        v55);
    v3 = v61;
    CellState::operator+=(v61, &v65);
    v53 = (volatile signed __int32 *)*((_QWORD *)&v65 + 1);
    if ( *((_QWORD *)&v65 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v65 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v53)(v53);
        if ( _InterlockedExchangeAdd(v53 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v53 + 8LL))(v53);
      }
    }
    if ( lpsz )
      CoTaskMemFree(lpsz);
    v6 = v60 + 1;
    v2 = v63;
  }
  return v3;
}

```

## disassembly

```asm
0x180038b00  mov     [rsp+arg_10], rbx
0x180038b05  mov     [rsp+arg_18], rsi
0x180038b0a  push    rdi
0x180038b0b  push    r12
0x180038b0d  push    r13
0x180038b0f  push    r14
0x180038b11  push    r15
0x180038b13  sub     rsp, 190h
0x180038b1a  mov     rax, cs:__security_cookie
0x180038b21  xor     rax, rsp
0x180038b24  mov     [rsp+1B8h+var_30], rax
0x180038b2c  mov     r13, rdx
0x180038b2f  mov     [rsp+1B8h+var_170], rdx
0x180038b34  mov     r12, rcx
0x180038b37  mov     [rsp+1B8h+var_180], rcx
0x180038b3c  mov     [rsp+1B8h+var_138], rcx
0x180038b44  mov     [rsp+1B8h+var_130], rdx
0x180038b4c  mov     [rsp+1B8h+var_194], 1
0x180038b54  mov     rcx, [rsp+1B8h]; this
0x180038b5c  cmp     dword ptr [rdx], 2
0x180038b5f  jnz     loc_1800394B3
0x180038b65  lea     r14, [rdx+10h]
0x180038b69  mov     edi, [rdx+8]
0x180038b6c  xor     esi, esi
0x180038b6e  mov     [r12], rsi
0x180038b72  mov     [r12+8], rsi
0x180038b77  mov     [r12+10h], rsi
0x180038b7c  mov     [r12+18h], rsi
0x180038b81  mov     [r12+20h], rsi
0x180038b86  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UModem@@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UModem@@@2@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UModem@@@2@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,std::shared_ptr<Modem>>>>::_Buyheadnode(void)
0x180038b8b  mov     [r12+18h], rax
0x180038b90  mov     [r12+28h], edi
0x180038b95  lea     eax, [rsi+1]
0x180038b98  mov     [rsp+1B8h+var_190], eax
0x180038b9c  mov     [rsp+1B8h+var_194], eax
0x180038ba0  mov     eax, esi
0x180038ba2  lea     edi, [rsi+7]
0x180038ba5  or      r15, 0FFFFFFFFFFFFFFFFh
0x180038ba9  mov     [rsp+1B8h+var_188], eax
0x180038bad  cmp     eax, [r13+0Ch]
0x180038bb1  jnb     loc_180039483
0x180038bb7  mov     rcx, [rsp+1B8h]; this
0x180038bbf  cmp     dword ptr [r14], 3
0x180038bc3  jnz     loc_1800394CB
0x180038bc9  mov     [rsp+1B8h+lpsz], rsi
0x180038bce  lea     rcx, [r14+8]; rclsid
0x180038bd2  lea     rdx, [rsp+1B8h+lpsz]; lplpsz
0x180038bd7  call    cs:__imp_StringFromCLSID
0x180038bdd  mov     rcx, [rsp+1B8h]; this
0x180038be5  test    eax, eax
0x180038be7  js      loc_1800394E3
0x180038bed  mov     [rsp+1B8h+var_F8], r14
0x180038bf5  mov     [rsp+1B8h+var_120], r14
0x180038bfd  mov     ecx, 78h ; 'x'; Size
0x180038c02  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180038c07  mov     rbx, rax
0x180038c0a  mov     [rsp+1B8h+var_F0], rax
0x180038c12  test    rax, rax
0x180038c15  jz      short loc_180038C8D
0x180038c17  mov     rdx, [rsp+1B8h+lpsz]; Src
0x180038c1c  mov     [rax+18h], rdi
0x180038c20  mov     [rax+10h], rsi
0x180038c24  mov     [rax], si
0x180038c27  cmp     [rdx], si
0x180038c2a  jnz     short loc_180038C31
0x180038c2c  mov     r8, rsi
0x180038c2f  jmp     short loc_180038C3E
0x180038c31  mov     r8, r15
0x180038c34  inc     r8
0x180038c37  cmp     [rdx+r8*2], si
0x180038c3c  jnz     short loc_180038C34
0x180038c3e  mov     rcx, rbx; void *
0x180038c41  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180038c46  mov     eax, [rsp+1B8h+var_190]
0x180038c4a  or      eax, 2
0x180038c4d  xor     ecx, ecx
0x180038c4f  mov     [rbx+70h], rcx
0x180038c53  mov     [rbx+38h], rdi
0x180038c57  mov     [rbx+30h], rsi
0x180038c5b  mov     [rbx+20h], si
0x180038c5f  mov     [rbx+40h], rsi
0x180038c63  mov     [rbx+48h], rsi
0x180038c67  mov     [rbx+50h], rsi
0x180038c6b  mov     [rbx+58h], rsi
0x180038c6f  mov     [rbx+60h], rsi
0x180038c73  mov     [rbx+68h], rsi
0x180038c77  or      eax, 1Ch
0x180038c7a  mov     [rsp+1B8h+var_190], eax
0x180038c7e  mov     [rsp+1B8h+var_194], eax
0x180038c82  xor     eax, eax
0x180038c84  mov     [rbx+72h], eax
0x180038c87  mov     [rbx+76h], ax
0x180038c8b  jmp     short loc_180038C90
0x180038c8d  mov     rbx, rsi
0x180038c90  xorps   xmm0, xmm0
0x180038c93  movdqu  [rsp+1B8h+var_160], xmm0
0x180038c99  mov     rdx, rbx
0x180038c9c  lea     rcx, [rsp+1B8h+var_160]
0x180038ca1  call    ??$_Resetp@UModem@@@?$shared_ptr@UModem@@@std@@AEAAXPEAUModem@@@Z; std::shared_ptr<Modem>::_Resetp<Modem>(Modem *)
0x180038ca6  nop
0x180038ca7  lea     rdx, [r14+18h]; Src
0x180038cab  mov     [rsp+1B8h+var_B8], rdi
0x180038cb3  mov     [rsp+1B8h+var_C0], rsi
0x180038cbb  mov     word ptr [rsp+1B8h+Src], si
0x180038cc3  cmp     [rdx], si
0x180038cc6  jnz     short loc_180038CCD
0x180038cc8  mov     r8, rsi
0x180038ccb  jmp     short loc_180038CDA
0x180038ccd  mov     r8, r15
0x180038cd0  inc     r8
0x180038cd3  cmp     [rdx+r8*2], si
0x180038cd8  jnz     short loc_180038CD0
0x180038cda  lea     rcx, [rsp+1B8h+Src]; void *
0x180038ce2  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180038ce7  mov     rbx, qword ptr [rsp+1B8h+var_160]
0x180038cec  lea     rcx, [rbx+20h]; void *
0x180038cf0  lea     rdx, [rsp+1B8h+Src]; Src
0x180038cf8  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180038cfd  cmp     [rsp+1B8h+var_B8], 8
0x180038d06  jb      short loc_180038D16
0x180038d08  mov     rcx, [rsp+1B8h+Src]
0x180038d10  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180038d16  cmp     [r14+40h], esi
0x180038d1a  setnz   al
0x180038d1d  mov     [rbx+70h], al
0x180038d20  cmp     [r14+3Ch], esi
0x180038d24  setnz   al
0x180038d27  mov     [rbx+71h], al
0x180038d2a  lea     r12, [r14+44h]
0x180038d2e  mov     [rsp+1B8h+var_100], r12
0x180038d36  mov     edx, [r12]
0x180038d3a  lea     rcx, [rbx+40h]
0x180038d3e  call    ?resize@?$vector@V?$nullable_any@UUicc@@@@V?$allocator@V?$nullable_any@UUicc@@@@@std@@@std@@QEAAX_K@Z; std::vector<nullable_any<Uicc>>::resize(unsigned __int64)
0x180038d43  mov     edx, [r12]
0x180038d47  lea     rcx, [rbx+58h]
0x180038d4b  call    ?resize@?$vector@_KV?$allocator@_K@std@@@std@@QEAAX_K@Z; std::vector<unsigned __int64>::resize(unsigned __int64)
0x180038d50  add     r14, 48h ; 'H'
0x180038d54  mov     eax, esi
0x180038d56  mov     [rsp+1B8h+var_18C], eax
0x180038d5a  mov     rcx, [rsp+1B8h]; this
0x180038d62  cmp     eax, [r12]
0x180038d66  jnb     loc_1800393EE
0x180038d6c  cmp     dword ptr [r14], 2
0x180038d70  jnz     loc_1800394F8
0x180038d76  mov     r12, r14
0x180038d79  mov     [rsp+1B8h+var_118], r14
0x180038d81  add     r14, 4Ch ; 'L'
0x180038d85  mov     edx, [r12+8]
0x180038d8a  mov     r8, [rbx+40h]
0x180038d8e  mov     ecx, [r12+0Ch]
0x180038d93  mov     rax, [rbx+58h]
0x180038d97  mov     [rax+rcx*8], rdx
0x180038d9b  cmp     [r12+10h], esi
0x180038da0  jz      loc_1800393DB
0x180038da6  lea     r13, [r8+rdx*8]
0x180038daa  mov     [rsp+1B8h+var_148], r13
0x180038daf  lea     rdx, [r12+14h]; Src
0x180038db4  mov     [rsp+1B8h+var_90], rdi
0x180038dbc  mov     [rsp+1B8h+var_98], rsi
0x180038dc4  mov     [rsp+1B8h+var_A8], si
0x180038dcc  cmp     [rdx], si
0x180038dcf  jnz     short loc_180038DD6
0x180038dd1  mov     r8, rsi
0x180038dd4  jmp     short loc_180038DE3
0x180038dd6  mov     r8, r15
0x180038dd9  inc     r8
0x180038ddc  cmp     [rdx+r8*2], si
0x180038de1  jnz     short loc_180038DD9
0x180038de3  lea     rcx, [rsp+1B8h+var_A8]; void *
0x180038deb  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180038df0  xorps   xmm0, xmm0
0x180038df3  movups  [rsp+1B8h+var_48], xmm0
0x180038dfb  xorps   xmm1, xmm1
0x180038dfe  movdqa  [rsp+1B8h+var_88], xmm1
0x180038e07  movdqa  [rsp+1B8h+var_78], xmm0
0x180038e10  movdqa  [rsp+1B8h+var_68], xmm1
0x180038e19  movdqa  [rsp+1B8h+var_58], xmm0
0x180038e22  xor     eax, eax
0x180038e24  mov     dword ptr [rsp+1B8h+var_48+0Ah], eax
0x180038e2b  mov     word ptr [rsp+1B8h+var_48+0Eh], ax
0x180038e33  lea     ecx, [rax+70h]; Size
0x180038e36  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180038e3b  mov     rbx, rax
0x180038e3e  mov     [rsp+1B8h+var_E8], rax
0x180038e46  test    rax, rax
0x180038e49  jz      loc_180038ECF
0x180038e4f  mov     [rax+18h], rdi
0x180038e53  mov     [rax+10h], rsi
0x180038e57  mov     [rax], si
0x180038e5a  mov     r9, r15
0x180038e5d  xor     r8d, r8d
0x180038e60  lea     rdx, [rsp+1B8h+var_A8]
0x180038e68  mov     rcx, rax; void *
0x180038e6b  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180038e70  nop
0x180038e71  lea     rcx, [rbx+20h]
0x180038e75  lea     rdx, [rsp+1B8h+var_88]
0x180038e7d  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::wstring>::vector<std::wstring>(std::vector<std::wstring> const &)
0x180038e82  nop
0x180038e83  lea     rcx, [rbx+38h]
0x180038e87  lea     rdx, [rsp+1B8h+var_78+8]
0x180038e8f  call    ??0?$vector@ULine@@V?$allocator@ULine@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<Line>::vector<Line>(std::vector<Line> const &)
0x180038e94  lea     rcx, [rbx+50h]
0x180038e98  lea     rdx, [rsp+1B8h+var_58]
0x180038ea0  call    ??$?0VCMvExtensionKey@@@?$shared_ptr@$$CBVCMvExtensionKey@@@std@@QEAA@AEBV?$shared_ptr@VCMvExtensionKey@@@1@PEAPEAX@Z; std::shared_ptr<CMvExtensionKey const>::shared_ptr<CMvExtensionKey const>(std::shared_ptr<CMvExtensionKey> const &,void * *)
0x180038ea5  mov     eax, dword ptr [rsp+1B8h+var_48]
0x180038eac  mov     [rbx+60h], eax
0x180038eaf  mov     eax, dword ptr [rsp+1B8h+var_48+4]
0x180038eb6  mov     [rbx+64h], eax
0x180038eb9  mov     al, byte ptr [rsp+1B8h+var_48+8]
0x180038ec0  mov     [rbx+68h], al
0x180038ec3  mov     al, byte ptr [rsp+1B8h+var_48+9]
0x180038eca  mov     [rbx+69h], al
0x180038ecd  jmp     short loc_180038ED2
0x180038ecf  mov     rbx, rsi
0x180038ed2  mov     rdi, [r13+0]
0x180038ed6  cmp     rbx, rdi
0x180038ed9  jz      short loc_180038EF5
0x180038edb  test    rdi, rdi
0x180038ede  jz      short loc_180038EF1
0x180038ee0  mov     rcx, rdi; this
0x180038ee3  call    ??1Uicc@@QEAA@XZ; Uicc::~Uicc(void)
0x180038ee8  mov     rcx, rdi
0x180038eeb  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180038ef1  mov     [r13+0], rbx
0x180038ef5  lea     rcx, [rsp+1B8h+var_A8]; this
0x180038efd  call    ??1Uicc@@QEAA@XZ; Uicc::~Uicc(void)
0x180038f02  mov     rbx, [r13+0]
0x180038f06  lea     rdx, [rsp+1B8h+var_160]
0x180038f0b  lea     rcx, [rsp+1B8h+var_E0]
0x180038f13  call    ??$?0VCMvExtensionKey@@@?$shared_ptr@$$CBVCMvExtensionKey@@@std@@QEAA@AEBV?$shared_ptr@VCMvExtensionKey@@@1@PEAPEAX@Z; std::shared_ptr<CMvExtensionKey const>::shared_ptr<CMvExtensionKey const>(std::shared_ptr<CMvExtensionKey> const &,void * *)
0x180038f18  mov     rdx, [rax+8]
0x180038f1c  mov     rcx, [rbx+58h]
0x180038f20  mov     [rax+8], rcx
0x180038f24  mov     [rbx+58h], rdx
0x180038f28  mov     rdx, [rax]
0x180038f2b  mov     rcx, [rbx+50h]
0x180038f2f  mov     [rax], rcx
0x180038f32  mov     [rbx+50h], rdx
0x180038f36  mov     rbx, [rsp+1B8h+var_D8]
0x180038f3e  test    rbx, rbx
0x180038f41  jz      short loc_180038F7B
0x180038f43  mov     eax, r15d
0x180038f46  lock xadd [rbx+8], eax
0x180038f4b  add     eax, r15d
0x180038f4e  jnz     short loc_180038F7B
0x180038f50  mov     rax, [rbx]
0x180038f53  mov     rcx, rbx
0x180038f56  mov     rax, [rax]
0x180038f59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038f5e  mov     eax, r15d
0x180038f61  lock xadd [rbx+0Ch], eax
0x180038f66  add     eax, r15d
0x180038f69  jnz     short loc_180038F7B
0x180038f6b  mov     rax, [rbx]
0x180038f6e  mov     rcx, rbx
0x180038f71  mov     rax, [rax+8]
0x180038f75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038f7a  nop
0x180038f7b  mov     rcx, [r13+0]
0x180038f7f  mov     eax, [r12+8]
0x180038f84  mov     [rcx+60h], eax
0x180038f87  mov     rcx, [r13+0]
0x180038f8b  mov     eax, [r12+10h]
0x180038f90  mov     [rcx+64h], eax
0x180038f93  cmp     dword ptr [r12+40h], 1
0x180038f99  setz    cl
0x180038f9c  mov     rax, [r13+0]
0x180038fa0  mov     [rax+69h], cl
0x180038fa3  mov     r12d, [r12+44h]
0x180038fa8  inc     r12d
0x180038fab  shr     r12d, 1
0x180038fae  mov     [rsp+1B8h+var_198], esi; int
0x180038fb2  jz      loc_1800390F8
0x180038fb8  xor     eax, eax
0x180038fba  mov     [rsp+1B8h+var_38], eax
0x180038fc1  mov     [rsp+1B8h+var_34], ax
0x180038fc9  movzx   ecx, word ptr [r14]
0x180038fcd  mov     rax, [rsp+1B8h]
0x180038fd5  mov     edx, 0FFFFh
0x180038fda  cmp     dx, cx
0x180038fdd  jz      loc_180039528
0x180038fe3  movzx   edi, word ptr [r14+2]
0x180038fe8  movzx   eax, cl
0x180038feb  mov     word ptr [rsp+1B8h+var_38], ax
0x180038ff3  shr     cx, 8
0x180038ff7  mov     word ptr [rsp+1B8h+var_38+2], cx
0x180038fff  mov     rbx, [r13+0]
0x180039003  mov     rax, [rbx+30h]
0x180039007  cmp     [rbx+28h], rax
0x18003900b  jnz     short loc_180039016
0x18003900d  lea     rcx, [rbx+20h]
0x180039011  call    ?_Reserve@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::wstring>::_Reserve(unsigned __int64)
0x180039016  mov     rcx, [rbx+28h]; void *
0x18003901a  mov     qword ptr [rcx+18h], 7
0x180039022  mov     [rcx+10h], rsi
0x180039026  mov     [rcx], si
0x180039029  cmp     word ptr [rsp+1B8h+var_38], si
0x180039031  jnz     short loc_180039038
0x180039033  mov     r8, rsi
  ... truncated ...
```
