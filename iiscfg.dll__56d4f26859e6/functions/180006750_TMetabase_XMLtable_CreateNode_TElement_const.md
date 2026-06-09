# TMetabase_XMLtable::CreateNode(TElement const &)

- ea: `0x180006750`
- end: `0x180009aaa`
- name: `?CreateNode@TMetabase_XMLtable@@UEAAJAEBUTElement@@@Z`
- size: `13146`
- prototype: `__int64 __fastcall(TMetabase_XMLtable *__hidden this, const struct TElement *)`
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001b78`
- `0x180002bc4`
- `0x180005cb8`
- `0x180005fdc`
- `0x180006310`
- `0x180006750`
- `0x180009acc`
- `0x180009dd4`
- `0x18000c844`
- `0x18000c9d4`
- `0x18000e03c`
- `0x18000e248`
- `0x180011b38`
- `0x180012734`
- `0x18002e0b2`
- `0x18002e0ca`
- `0x18002e0e2`
- `0x18002e110`
- `0x18002e1d0`
- `0x180030010`

## import_xrefs

- `msvcrt!swprintf_s` at `0x18000704e`
- `msvcrt!swprintf_s` at `0x1800073f7`
- `msvcrt!swprintf_s` at `0x1800076bd`
- `msvcrt!swprintf_s` at `0x18000704e`
- `msvcrt!swprintf_s` at `0x1800073f7`
- `msvcrt!swprintf_s` at `0x1800076bd`
- `msvcrt!wcsncpy_s` at `0x1800067cc`
- `msvcrt!wcsncpy_s` at `0x180006813`
- `msvcrt!wcsncpy_s` at `0x180006ac2`
- `msvcrt!wcsncpy_s` at `0x180007071`
- `msvcrt!wcsncpy_s` at `0x18000741a`
- `msvcrt!wcsncpy_s` at `0x18000770b`
- `msvcrt!wcsncpy_s` at `0x18000791b`
- `msvcrt!wcsncpy_s` at `0x180007b21`
- `msvcrt!wcsncpy_s` at `0x180007ed5`
- `msvcrt!wcsncpy_s` at `0x180008600`
- `msvcrt!wcsncpy_s` at `0x180008cb0`
- `msvcrt!wcsncpy_s` at `0x180009171`
- `msvcrt!wcsncpy_s` at `0x18000940b`
- `msvcrt!wcsncpy_s` at `0x1800097d8`
- `msvcrt!wcsncpy_s` at `0x1800067cc`
- `msvcrt!wcsncpy_s` at `0x180006813`
- `msvcrt!wcsncpy_s` at `0x180006ac2`
- `msvcrt!wcsncpy_s` at `0x180007071`
- `msvcrt!wcsncpy_s` at `0x18000741a`
- `msvcrt!wcsncpy_s` at `0x18000770b`
- `msvcrt!wcsncpy_s` at `0x18000791b`
- `msvcrt!wcsncpy_s` at `0x180007b21`
- `msvcrt!wcsncpy_s` at `0x180007ed5`
- `msvcrt!wcsncpy_s` at `0x180008600`
- `msvcrt!wcsncpy_s` at `0x180008cb0`
- `msvcrt!wcsncpy_s` at `0x180009171`
- `msvcrt!wcsncpy_s` at `0x18000940b`
- `msvcrt!wcsncpy_s` at `0x1800097d8`
- `msvcrt!wcstoul` at `0x1800073c4`
- `msvcrt!wcstoul` at `0x1800073c4`
- `msvcrt!wcscpy_s` at `0x180006f13`
- `msvcrt!wcscpy_s` at `0x180009626`
- `msvcrt!wcscpy_s` at `0x180006f13`
- `msvcrt!wcscpy_s` at `0x180009626`
- `msvcrt!_wcsicmp` at `0x180008c85`
- `msvcrt!_wcsicmp` at `0x180008c85`

## string_xrefs

- `0x180006923`: `inetsrv\iis\mb\config\src\stores\xmltable\metabase_xmltable.cpp`
- `0x180006a04`: `inetsrv\iis\mb\config\src\stores\xmltable\metabase_xmltable.cpp`
- `0x180006a36`: `inetsrv\iis\mb\config\src\stores\xmltable\metabase_xmltable.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall TMetabase_XMLtable::CreateNode(TMetabase_XMLtable *this, const struct TElement *a2)
{
  unsigned int v4; // r12d
  rsize_t v5; // r9
  unsigned int v6; // ecx
  __int64 v7; // rax
  unsigned __int64 v8; // rax
  rsize_t v9; // r9
  __int64 v10; // rax
  unsigned __int64 v11; // rax
  unsigned int v12; // eax
  __int64 result; // rax
  unsigned int v14; // eax
  __int64 v15; // r8
  unsigned int *v16; // rax
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int m; // ecx
  TMetabase_XMLtable *v20; // rcx
  TMetabase_XMLtable *v21; // rcx
  int v22; // eax
  TMetabase_XMLtable *v23; // rcx
  TMetabase_XMLtable *v24; // rcx
  rsize_t v25; // r9
  unsigned int v26; // eax
  int v27; // eax
  TMetabase_XMLtable *v28; // rcx
  unsigned int v29; // eax
  rsize_t v30; // r9
  unsigned int v31; // eax
  wchar_t *v32; // rcx
  _DWORD *v33; // rax
  rsize_t v34; // r9
  unsigned int v35; // eax
  rsize_t v36; // r9
  __int64 v37; // rax
  unsigned __int64 v38; // rax
  unsigned int v39; // eax
  unsigned __int64 v40; // rcx
  unsigned int *v41; // rax
  unsigned int v42; // eax
  __int64 v43; // rax
  unsigned __int64 v44; // rax
  unsigned int v45; // eax
  TMetabase_XMLtable *v46; // rcx
  int v47; // edx
  rsize_t v48; // r9
  unsigned int v49; // eax
  __int64 n; // r12
  _DWORD *v51; // rax
  bool v52; // zf
  bool v53; // al
  _DWORD *v54; // rax
  bool v55; // al
  unsigned int v56; // eax
  char v57; // dl
  unsigned int *v58; // rax
  unsigned int v59; // eax
  TMetabase_XMLtable *v60; // rcx
  const unsigned __int16 *v61; // rdx
  __int64 v62; // r8
  __int64 j; // rax
  const void *v64; // rdx
  unsigned int v65; // eax
  _WORD *v66; // rax
  unsigned int v67; // eax
  _WORD *v68; // rax
  int v69; // eax
  const wchar_t *v70; // r8
  rsize_t v71; // r9
  unsigned int v72; // eax
  _WORD *v73; // rax
  TMetabase_XMLtable *v74; // rcx
  _WORD *v75; // rcx
  TMetabase_XMLtable *v76; // rcx
  _WORD *v77; // rcx
  __int64 v78; // rcx
  unsigned __int16 *v79; // rax
  __int64 v80; // rcx
  int v81; // edx
  int v82; // r8d
  _WORD *v83; // rax
  _WORD *v84; // rax
  unsigned int k; // eax
  rsize_t v86; // r9
  __int64 v87; // rax
  unsigned __int64 v88; // rax
  unsigned int v89; // eax
  wchar_t *p_Buffer; // rcx
  TMetabase_XMLtable *v91; // rcx
  TMetabase_XMLtable *v92; // rcx
  rsize_t v93; // r9
  unsigned int v94; // ecx
  __int64 v95; // rax
  unsigned __int64 v96; // rax
  unsigned int v97; // eax
  _DWORD *v98; // rcx
  bool v99; // al
  rsize_t v100; // r9
  unsigned int v101; // eax
  _WORD *v102; // rax
  const unsigned __int16 *v103; // rdx
  __int64 v104; // r8
  __int64 i; // rax
  __int64 v106; // [rsp+88h] [rbp-1350h]
  __int64 v107; // [rsp+90h] [rbp-1348h]
  char v108; // [rsp+B0h] [rbp-1328h]
  unsigned int v109; // [rsp+B4h] [rbp-1324h] BYREF
  unsigned int v110[2]; // [rsp+B8h] [rbp-1320h] BYREF
  __int64 v111; // [rsp+C0h] [rbp-1318h]
  unsigned int v112; // [rsp+C8h] [rbp-1310h] BYREF
  unsigned int v113; // [rsp+CCh] [rbp-130Ch] BYREF
  unsigned int v114[2]; // [rsp+D0h] [rbp-1308h] BYREF
  __int64 v115; // [rsp+D8h] [rbp-1300h]
  __int64 v116; // [rsp+E0h] [rbp-12F8h] BYREF
  __int64 v117; // [rsp+E8h] [rbp-12F0h]
  char v118[8]; // [rsp+F8h] [rbp-12E0h] BYREF
  __int64 v119; // [rsp+100h] [rbp-12D8h]
  char v120[8]; // [rsp+108h] [rbp-12D0h] BYREF
  __int64 v121; // [rsp+110h] [rbp-12C8h]
  char v122[8]; // [rsp+118h] [rbp-12C0h] BYREF
  __int64 v123; // [rsp+120h] [rbp-12B8h]
  unsigned int v124; // [rsp+138h] [rbp-12A0h]
  int v125; // [rsp+140h] [rbp-1298h]
  int v126; // [rsp+144h] [rbp-1294h]
  int v127; // [rsp+148h] [rbp-1290h]
  wchar_t Buffer; // [rsp+180h] [rbp-1258h] BYREF
  __int64 v129; // [rsp+188h] [rbp-1250h]
  wchar_t v130[8]; // [rsp+1A0h] [rbp-1238h] BYREF
  wchar_t *Source; // [rsp+1B0h] [rbp-1228h]
  unsigned int *v132; // [rsp+1D0h] [rbp-1208h]
  _DWORD *v133; // [rsp+208h] [rbp-11D0h]
  _DWORD *v134; // [rsp+210h] [rbp-11C8h]
  _DWORD *v135; // [rsp+218h] [rbp-11C0h]
  int v136; // [rsp+398h] [rbp-1040h]
  __int16 v137; // [rsp+39Ch] [rbp-103Ch]
  wchar_t Destination[1024]; // [rsp+3A0h] [rbp-1038h] BYREF
  wchar_t v139[1024]; // [rsp+BA0h] [rbp-838h] BYREF

  if ( (*((_BYTE *)a2 + 16) & 2) != 0 && *(_DWORD *)a2 != 1 )
    return 0;
  if ( *((_DWORD *)a2 + 6) == 13 )
  {
    v4 = 255;
    v5 = 255;
    if ( *((_DWORD *)a2 + 1) < 0xFFu )
      v5 = *((unsigned int *)a2 + 1);
    wcsncpy_s(Destination, 0x100u, *((const wchar_t **)a2 + 1), v5);
    v6 = *((_DWORD *)a2 + 1);
    v7 = 255;
    if ( v6 < 0xFF )
      v7 = v6;
    v8 = v7;
    if ( v8 >= 256 )
      goto LABEL_397;
    Destination[v8] = 0;
    v9 = 255;
    if ( v6 < 0xFF )
      v9 = v6;
    wcsncpy_s(v130, 0x100u, *((const wchar_t **)a2 + 1), v9);
    v10 = 255;
    if ( *((_DWORD *)a2 + 1) < 0xFFu )
      v10 = *((unsigned int *)a2 + 1);
    v11 = v10;
    if ( v11 >= 256 )
LABEL_397:
      _report_rangecheckfailure();
    v130[v11] = 0;
    if ( *((_DWORD *)a2 + 1) > 0xFFu )
    {
      v136 = 3014702;
      v137 = 46;
    }
    v12 = *((_DWORD *)this + 402);
    if ( v12 < 0x32 )
    {
      *((_DWORD *)this + 402) = v12 + 1;
      v115 = 0;
      CErrorInterceptor::Init(
        (CErrorInterceptor *)v114,
        (_QWORD *)this + 222,
        *((_QWORD *)this + 211),
        0x80210523,
        2u,
        -2147348242,
        Destination,
        v130,
        0,
        0,
        14,
        (__int64)L"MBProperty",
        1,
        -1,
        -1,
        (__int64)this + 16,
        2,
        v106,
        v107,
        *((_DWORD *)this + 420),
        -1);
      CErrorInterceptor::WriteToLog(
        (CErrorInterceptor *)v114,
        L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
        1463,
        *((_DWORD *)this + 409));
LABEL_18:
      CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)v114);
      goto LABEL_24;
    }
    if ( v12 == 50 )
    {
      *((_DWORD *)this + 402) = 51;
      v115 = 0;
      CErrorInterceptor::Init(
        (CErrorInterceptor *)v114,
        (_QWORD *)this + 222,
        *((_QWORD *)this + 211),
        0x80210523,
        2u,
        -1073606423,
        (const wchar_t *)this + 8,
        0,
        0,
        0,
        14,
        (__int64)L"MBProperty",
        1,
        -1,
        -1,
        (__int64)this + 16,
        2,
        v106,
        v107,
        *((_DWORD *)this + 420),
        -1);
      CErrorInterceptor::WriteToLog(
        (CErrorInterceptor *)v114,
        L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
        1463,
        *((_DWORD *)this + 409));
      goto LABEL_18;
    }
  }
  else
  {
    if ( *((_DWORD *)a2 + 6) == 18 )
      return 0;
    v4 = 255;
  }
LABEL_24:
  if ( *(_DWORD *)a2 == 1 )
  {
    if ( *((_BYTE *)this + 1578) )
    {
      v103 = (const unsigned __int16 *)**((_QWORD **)this + 193);
      v104 = -1;
      do
        ++v104;
      while ( v103[v104] );
      TMetabase_XMLtable::AddKeyTypeRow((TMetabase_XMLtable *)((char *)this - 24), v103, v104, 1);
      *((_BYTE *)this + 1578) = 0;
    }
    for ( i = 0; i != 9; ++i )
    {
      *((_QWORD *)this + i + 98) = 0;
      *((_DWORD *)this + i + 314) = 0;
    }
    return 0;
  }
  if ( *(_DWORD *)a2 == 2 )
  {
    v60 = (TMetabase_XMLtable *)((char *)this - 24);
    *((_BYTE *)this + 1577) = 1;
    if ( *((_QWORD *)this + 218) && *((_BYTE *)this + 1579) )
      return 2149647639LL;
    if ( *((_DWORD *)a2 + 6) == 16 )
      return TMetabase_XMLtable::SetComment(v60, *((const unsigned __int16 **)a2 + 1), *((_DWORD *)a2 + 1));
    if ( *((_BYTE *)v60 + 1602) )
    {
      v61 = (const unsigned __int16 *)**((_QWORD **)this + 193);
      v62 = -1;
      do
        ++v62;
      while ( v61[v62] );
      TMetabase_XMLtable::AddKeyTypeRow(v60, v61, v62, 1);
      *((_BYTE *)this + 1578) = 0;
    }
    for ( j = 0; j != 9; ++j )
    {
      *((_QWORD *)this + j + 98) = 0;
      *((_DWORD *)this + j + 314) = 0;
    }
    v64 = (const void *)*((_QWORD *)a2 + 1);
    if ( *((_DWORD *)a2 + 1) > 0x3FFu )
    {
      memcpy_0(Destination, v64, 0x7FEu);
      Destination[1023] = 0;
      v65 = *((_DWORD *)this + 402);
      if ( v65 >= 0x32 )
      {
        if ( v65 != 50 )
        {
LABEL_269:
          v66 = (_WORD *)*((_QWORD *)this + 217);
          if ( v66 )
            *v66 = 0;
          *((_BYTE *)this + 1578) = 0;
          return 0;
        }
        *((_DWORD *)this + 402) = 51;
        v115 = 0;
        CErrorInterceptor::Init(
          (CErrorInterceptor *)v114,
          (_QWORD *)this + 222,
          *((_QWORD *)this + 211),
          0x80210523,
          2u,
          -1073606423,
          (const wchar_t *)this + 8,
          0,
          0,
          0,
          14,
          (__int64)L"MBProperty",
          1,
          -1,
          -1,
          (__int64)this + 16,
          2,
          v106,
          v107,
          *((_DWORD *)this + 420),
          -1);
        CErrorInterceptor::WriteToLog(
          (CErrorInterceptor *)v114,
          L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
          1518,
          *((_DWORD *)this + 409));
      }
      else
      {
        *((_DWORD *)this + 402) = v65 + 1;
        v115 = 0;
        CErrorInterceptor::Init(
          (CErrorInterceptor *)v114,
          (_QWORD *)this + 222,
          *((_QWORD *)this + 211),
          0x80210523,
          2u,
          -2147348300,
          Destination,
          0,
          0,
          0,
          14,
          (__int64)L"MBProperty",
          1,
          -1,
          -1,
          (__int64)this + 16,
          2,
          v106,
          v107,
          *((_DWORD *)this + 420),
          -1);
        CErrorInterceptor::WriteToLog(
          (CErrorInterceptor *)v114,
          L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
          1518,
          *((_DWORD *)this + 409));
      }
      CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)v114);
      goto LABEL_269;
    }
    *(_QWORD *)v114 = 2LL * *((unsigned int *)a2 + 1);
    memcpy_0(v139, v64, *(size_t *)v114);
    if ( *(_QWORD *)v114 >= 0x800u )
      _report_rangecheckfailure();
    *(wchar_t *)((char *)v139 + *(_QWORD *)v114) = 0;
    if ( !TPublicRowName::IsEqual(
            (TMetabase_XMLtable *)((char *)this + 1512),
            *((const unsigned __int16 **)a2 + 1),
            *((_DWORD *)a2 + 1)) )
    {
      v67 = *((_DWORD *)this + 402);
      if ( v67 >= 0x32 )
      {
        if ( v67 != 50 )
        {
LABEL_279:
          v68 = (_WORD *)*((_QWORD *)this + 217);
          if ( v68 )
            *v68 = 0;
          *((_BYTE *)this + 1578) = 0;
          return 0;
        }
        *((_DWORD *)this + 402) = 51;
        v115 = 0;
        CErrorInterceptor::Init(
          (CErrorInterceptor *)v114,
          (_QWORD *)this + 222,
          *((_QWORD *)this + 211),
          0x80210523,
          2u,
          -1073606423,
          (const wchar_t *)this + 8,
          0,
          0,
          0,
          14,
          (__int64)L"MBProperty",
          1,
          -1,
          -1,
          (__int64)this + 16,
          2,
          v106,
          v107,
          *((_DWORD *)this + 420),
          -1);
        CErrorInterceptor::WriteToLog(
          (CErrorInterceptor *)v114,
          L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
          1533,
          *((_DWORD *)this + 409));
      }
      else
      {
        *((_DWORD *)this + 402) = v67 + 1;
        v115 = 0;
        CErrorInterceptor::Init(
          (CErrorInterceptor *)v114,
          (_QWORD *)this + 222,
          *((_QWORD *)this + 211),
          0x80210523,
          2u,
          -2147348299,
          v139,
          0,
          0,
          0,
          14,
          (__int64)L"MBProperty",
          1,
          -1,
          -1,
          (__int64)this + 16,
          2,
          v106,
          v107,
          *((_DWORD *)this + 420),
          -1);
        CErrorInterceptor::WriteToLog(
          (CErrorInterceptor *)v114,
          L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
          1533,
          *((_DWORD *)this + 409));
      }
      CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)v114);
      goto LABEL_279;
    }
    v69 = _wcsicmp(L"Custom", *((const wchar_t **)a2 + 1));
    v70 = (const wchar_t *)*((_QWORD *)a2 + 1);
    if ( !v69 )
    {
      v71 = 255;
      if ( *((_DWORD *)a2 + 1) < 0xFFu )
        v71 = *((unsigned int *)a2 + 1);
      wcsncpy_s(Destination, 0x100u, v70, v71);
      if ( *((_DWORD *)a2 + 1) < 0xFFu )
        v4 = *((_DWORD *)a2 + 1);
      if ( 2 * (unsigned __int64)v4 >= 0x200 )
        _report_rangecheckfailure();
      Destination[v4] = 0;
      v72 = *((_DWORD *)this + 402);
      if ( v72 >= 0x32 )
      {
        if ( v72 != 50 )
        {
LABEL_293:
          v73 = (_WORD *)*((_QWORD *)this + 217);
          if ( v73 )
            *v73 = 0;
          *((_BYTE *)this + 1578) = 0;
          return 0;
        }
        *((_DWORD *)this + 402) = 51;
        v115 = 0;
        CErrorInterceptor::Init(
          (CErrorInterceptor *)v114,
          (_QWORD *)this + 222,
          *((_QWORD *)this + 211),
          0x80210523,
          2u,
          -1073606423,
          (const wchar_t *)this + 8,
          0,
          0,
          0,
          14,
          (__int64)L"MBProperty",
          1,
          -1,
          -1,
          (__int64)this + 16,
          2,
          v106,
          v107,
          *((_DWORD *)this + 420),
          -1);
        CErrorInterceptor::WriteToLog(
          (CErrorInterceptor *)v114,
          L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
          1546,
          *((_DWORD *)this + 409));
      }
      else
      {
        *((_DWORD *)this + 402) = v72 + 1;
        v115 = 0;
        CErrorInterceptor::Init(
          (CErrorInterceptor *)v114,
          (_QWORD *)this + 222,
          *((_QWORD *)this + 211),
          0x80210523,
          2u,
          -2147348298,
          Destination,
          0,
          0,
          0,
          14,
          (__int64)L"MBProperty",
          1,
          -1,
          -1,
          (__int64)this + 16,
          2,
          v106,
          v107,
          *((_DWORD *)this + 420),
          -1);
        CErrorInterceptor::WriteToLog(
          (CErrorInterceptor *)v114,
          L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
          1546,
          *((_DWORD *)this + 409));
      }
      CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)v114);
      goto LABEL_293;
    }
    result = TMetabase_XMLtable::FillInColumn(
               (TMetabase_XMLtable *)((char *)this - 24),
               8u,
               v70,
               *((_DWORD *)a2 + 1),
               *((_DWORD *)this + 184),
               *((_DWORD *)this + 186),
               0);
    if ( (_DWORD)result )
    {
      v75 = (_WORD *)*((_QWORD *)this + 217);
      if ( v75 )
        *v75 = 0;
      *((_BYTE *)this + 1578) = 0;
      *((_QWORD *)this + 106) = 0;
      if ( (_DWORD)result == 1 )
        return 0;
      return result;
    }
    v113 = TMetabase_XMLtable::StringCompare(
             v74,
             **((const unsigned __int16 ***)this + 193),
             *((const unsigned __int16 **)a2 + 1));
    LOBYTE(v76) = v113 == 0;
    *((_BYTE *)this + 1578) = v113 == 0;
    v114[0] = 0;
    if ( TMetabase_XMLtable::FindAttribute(
           v76,
           a2,
           *((const unsigned __int16 **)this + 143),
           *((_DWORD *)this + 300),
           v114) )
    {
      result = TMetabase_XMLtable::FillInColumn(
                 (TMetabase_XMLtable *)((char *)this - 24),
                 4u,
                 *((const unsigned __int16 **)a2 + 4 * v114[0] + 7),
                 *((_DWORD *)a2 + 8 * v114[0] + 12),
                 *((_DWORD *)this + 172),
                 *((_DWORD *)this + 174),
                 0);
      if ( (_DWORD)result )
      {
        v77 = (_WORD *)*((_QWORD *)this + 217);
        if ( v77 )
          *v77 = 0;
        *((_BYTE *)this + 1578) = 0;
        if ( (_DWORD)result == 1 )
          return 0;
        return result;
      }
      v78 = *((_QWORD *)this + 218);
      if ( v78 )
      {
        v79 = (unsigned __int16 *)*((_QWORD *)this + 102);
        v80 = v78 - (_QWORD)v79;
        do
        {
          v81 = *(unsigned __int16 *)((char *)v79 + v80);
          v82 = *v79 - v81;
          if ( v82 )
            break;
          ++v79;
        }
        while ( v81 );
        if ( v82 )
        {
          v83 = (_WORD *)*((_QWORD *)this + 217);
          if ( v83 )
            *v83 = 0;
          *((_BYTE *)this + 1578) = 0;
          return 0;
        }
      }
      *((_QWORD *)this + 105) = &TMetabase_XMLtable::m_LocationID;
      *((_DWORD *)this + 321) = 4;
      _InterlockedAdd(&TMetabase_XMLtable::m_LocationID, 1u);
      *((_BYTE *)this + 1579) = 1;
      v84 = (_WORD *)*((_QWORD *)this + 217);
      if ( v84 && *v84 )
      {
        result = TMetabase_XMLtable::AddCommentRow((TMetabase_XMLtable *)((char *)this - 24));
        if ( (int)result < 0 )
          return result;
        *(_WORD *)((char *)this + 1577) = 0;
      }
      if ( v113 )
      {
        TMetabase_XMLtable::AddKeyTypeRow(
          (TMetabase_XMLtable *)((char *)this - 24),
          *((const unsigned __int16 **)a2 + 1),
          *((_DWORD *)a2 + 1),
          0);
        *((_BYTE *)this + 1577) = 0;
      }
      for ( k = 0; ; ++k )
      {
        v109 = k;
        if ( k >= *((_DWORD *)a2 + 5) )
          return 0;
        if ( v114[0] != k )
          break;
LABEL_363:
        ;
      }
      v116 = 32LL * k;
      result = TMetabase_XMLtable::FillInColumn(
                 (TMetabase_XMLtable *)((char *)this - 24),
                 0,
                 *(const unsigned __int16 **)((char *)a2 + v116 + 40),
                 *(_DWORD *)((char *)a2 + v116 + 32),
                 *((_DWORD *)this + 160),
                 *((_DWORD *)this + 162),
                 0);
      if ( (_DWORD)result )
      {
        if ( (_DWORD)result == 1 )
          return 0;
        return result;
      }
      *((_QWORD *)this + 255) = v139;
      *((_QWORD *)this + 257) = *((_QWORD *)this + 98);
      v110[0] = -1;
      if ( (*(int (__fastcall **)(_QWORD, _QWORD, __int64, char *, _QWORD, char *, unsigned int *))(**((_QWORD **)this + 252)
                                                                                                  + 56LL))(
             *((_QWORD *)this + 252),
             0,
             2,
             (char *)this + 2024,
             0,
             (char *)this + 2040,
             v110) >= 0 )
      {
        memset_0(v130, 0, 0x90u);
        result = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)this + 252) + 32LL))(
                   *((_QWORD *)this + 252),
                   v110[0],
                   18);
        if ( (int)result < 0 )
          return result;
        if ( !(unsigned int)TMetabase_XMLtable::StringCompare(v91, Source, *((const unsigned __int16 **)this + 257)) )
        {
          v112 = TMetabase_XMLtable::MetabaseTypeFromColumnMetaType(v92, (struct tCOLUMNMETARow *)v130);
          wcscpy_s(*((wchar_t **)this + 98), *((unsigned int *)this + 314), Source);
          *((_QWORD *)this + 99) = &v112;
          *((_DWORD *)this + 315) = v125;
          v98 = v135;
          *((_QWORD *)this + 100) = v135;
          *((_DWORD *)this + 316) = v124;
          *((_QWORD *)this + 103) = v133;
          *((_DWORD *)this + 319) = v126;
          *((_QWORD *)this + 104) = v134;
          *((_DWORD *)this + 320) = v127;
          if ( !v98 || (v99 = 1, (*v98 & 4) == 0) )
            v99 = 0;
          if ( !(unsigned int)TMetabase_XMLtable::FillInColumn(
                                (TMetabase_XMLtable *)((char *)this - 24),
                                3u,
                                *((const unsigned __int16 **)a2 + 4 * v109 + 7),
                                *((_DWORD *)a2 + 8 * v109 + 12),
                                v112,
                                *v132,
                                v99) )
          {
            if ( *v133 == 9994 )
              *((_DWORD *)this + 420) = **((_DWORD **)this + 101);
            v113 = 0;
            result = (*(__int64 (__fastcall **)(char *, unsigned int *))(*((_QWORD *)this - 3) + 72LL))(
                       (char *)this - 24,
                       &v113);
            if ( (int)result < 0 )
              return result;
            result = (*(__int64 (__fastcall **)(char *, _QWORD, __int64))(*((_QWORD *)this - 3) + 88LL))(
                       (char *)this - 24,
                       v113,
                       9);
            if ( (int)result < 0 )
              return result;
            result = TMetabase_XMLtable::AddPropertyToLocationMapping(
                       (TMetabase_XMLtable *)((char *)this - 24),
                       *((const unsigned __int16 **)this + 102),
                       v113);
            if ( (int)result < 0 )
              return result;
            *((_BYTE *)this + 1577) = 0;
          }
          goto LABEL_362;
        }
        v93 = 255;
        if ( *(_DWORD *)((char *)a2 + v116 + 32) < 0xFFu )
          v93 = *(unsigned int *)((char *)a2 + v116 + 32);
        wcsncpy_s(Destination, 0x100u, *((const wchar_t **)a2 + 4 * v109 + 5), v93);
        v94 = *((_DWORD *)a2 + 8 * v109 + 8);
        v95 = 255;
        if ( v94 < 0xFF )
          v95 = v94;
        v96 = v95;
        if ( v96 >= 256 )
          _report_rangecheckfailure();
        Destination[v96] = 0;
        v97 = *((_DWORD *)this + 402);
        if ( v97 >= 0x32 )
        {
          if ( v97 != 50 )
            goto LABEL_362;
          *((_DWORD *)this + 402) = 51;
          v129 = 0;
          CErrorInterceptor::Init(
            (CErrorInterceptor *)&Buffer,
            (_QWORD *)this + 222,
            *((_QWORD *)this + 211),
            0x80210523,
            2u,
            -1073606423,
            (const wchar_t *)this + 8,
            0,
            0,
            0,
            14,
            (__int64)L"MBProperty",
            1,
            -1,
            -1,
            (__int64)this + 16,
            2,
            v106,
            v107,
            *((_DWORD *)this + 420),
            -1);
          CErrorInterceptor::WriteToLog(
            (CErrorInterceptor *)&Buffer,
            L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
            1666,
            *((_DWORD *)this + 409));
          p_Buffer = &Buffer;
        }
        else
        {
          *((_DWORD *)this + 402) = v97 + 1;
          v123 = 0;
          CErrorInterceptor::Init(
            (CErrorInterceptor *)v122,
            (_QWORD *)this + 222,
            *((_QWORD *)this + 211),
            0x80210523,
            2u,
            -2147348296,
            *((const wchar_t **)this + 98),
            Destination,
            0,
            0,
            14,
            (__int64)L"MBProperty",
            1,
            -1,
            -1,
            (__int64)this + 16,
            2,
            v106,
            v107,
            *((_DWORD *)this + 420),
            -1);
          CErrorInterceptor::WriteToLog(
            (CErrorInterceptor *)v122,
            L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
            1666,
            *((_DWORD *)this + 409));
          p_Buffer = (wchar_t *)v122;
        }
      }
      else
      {
        v86 = 255;
        if ( *(_DWORD *)((char *)a2 + v116 + 32) < 0xFFu )
          v86 = *(unsigned int *)((char *)a2 + v116 + 32);
        wcsncpy_s(Destination, 0x100u, *(const wchar_t **)((char *)a2 + v116 + 40), v86);
        v87 = 255;
        if ( *(_DWORD *)((char *)a2 + v116 + 32) < 0xFFu )
          v87 = *(unsigned int *)((char *)a2 + v116 + 32);
        v88 = v87;
        if ( v88 >= 256 )
          _report_rangecheckfailure();
        Destination[v88] = 0;
        v89 = *((_DWORD *)this + 402);
        if ( v89 >= 0x32 )
        {
          if ( v89 != 50 )
            goto LABEL_362;
          *((_DWORD *)this + 402) = 51;
          v121 = 0;
          CErrorInterceptor::Init(
            (CErrorInterceptor *)v120,
            (_QWORD *)this + 222,
            *((_QWORD *)this + 211),
            0x80210523,
            2u,
            -1073606423,
            (const wchar_t *)this + 8,
            0,
            0,
            0,
            14,
            (__int64)L"MBProperty",
            1,
            -1,
            -1,
            (__int64)this + 16,
            2,
            v106,
            v107,
            *((_DWORD *)this + 420),
            -1);
          CErrorInterceptor::WriteToLog(
            (CErrorInterceptor *)v120,
            L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
            1650,
            *((_DWORD *)this + 409));
          p_Buffer = (wchar_t *)v120;
        }
        else
        {
          *((_DWORD *)this + 402) = v89 + 1;
          v119 = 0;
          CErrorInterceptor::Init(
            (CErrorInterceptor *)v118,
            (_QWORD *)this + 222,
            *((_QWORD *)this + 211),
            0x80210523,
            2u,
            -2147348296,
            *((const wchar_t **)this + 98),
            Destination,
            0,
            0,
            14,
            (__int64)L"MBProperty",
            1,
            -1,
            -1,
            (__int64)this + 16,
            2,
            v106,
            v107,
            *((_DWORD *)this + 420),
            -1);
          CErrorInterceptor::WriteToLog(
            (CErrorInterceptor *)v118,
            L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
            1650,
            *((_DWORD *)this + 409));
          p_Buffer = (wchar_t *)v118;
        }
      }
      CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)p_Buffer);
LABEL_362:
      k = v109;
      goto LABEL_363;
    }
    v100 = 255;
    if ( *((_DWORD *)a2 + 1) < 0xFFu )
      v100 = *((unsigned int *)a2 + 1);
    wcsncpy_s(Destination, 0x100u, *((const wchar_t **)a2 + 1), v100);
    if ( *((_DWORD *)a2 + 1) < 0xFFu )
      v4 = *((_DWORD *)a2 + 1);
    if ( 2 * (unsigned __int64)v4 >= 0x200 )
      _report_rangecheckfailure();
    Destination[v4] = 0;
    v101 = *((_DWORD *)this + 402);
    if ( v101 >= 0x32 )
    {
      if ( v101 != 50 )
      {
LABEL_374:
        v102 = (_WORD *)*((_QWORD *)this + 217);
        if ( v102 )
          *v102 = 0;
        *((_BYTE *)this + 1578) = 0;
        return 0;
      }
      *((_DWORD *)this + 402) = 51;
      v129 = 0;
      CErrorInterceptor::Init(
        (CErrorInterceptor *)&Buffer,
        (_QWORD *)this + 222,
        *((_QWORD *)this + 211),
        0x80210523,
        2u,
        -1073606423,
        (const wchar_t *)this + 8,
        0,
        0,
        0,
        14,
        (__int64)L"MBProperty",
        1,
        -1,
        -1,
        (__int64)this + 16,
        2,
        v106,
        v107,
        *((_DWORD *)this + 420),
        -1);
      CErrorInterceptor::WriteToLog(
        (CErrorInterceptor *)&Buffer,
        L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
        1605,
        *((_DWORD *)this + 409));
    }
    else
    {
      *((_DWORD *)this + 402) = v101 + 1;
      v129 = 0;
      CErrorInterceptor::Init(
        (CErrorInterceptor *)&Buffer,
        (_QWORD *)this + 222,
        *((_QWORD *)this + 211),
        0x80210523,
        2u,
        -2147348297,
        v139,
        Destination,
        0,
        0,
        14,
        (__int64)L"MBProperty",
        1,
        -1,
        -1,
        (__int64)this + 16,
        2,
        v106,
        v107,
        *((_DWORD *)this + 420),
        -1);
      CErrorInterceptor::WriteToLog(
        (CErrorInterceptor *)&Buffer,
        L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
        1605,
        *((_DWORD *)this + 409));
    }
    CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)&Buffer);
    goto LABEL_374;
  }
  if ( *(_DWORD *)a2 != 3 )
    return 0;
  if ( *((_DWORD *)a2 + 6) != 1 )
    return 0;
  v14 = *((_DWORD *)a2 + 1);
  if ( v14 != 6 )
  {
    if ( v14 >= 0xFF )
      v14 = 255;
LABEL_243:
    wcsncpy_s(Destination, 0x100u, *((const wchar_t **)a2 + 1), v14);
    if ( *((_DWORD *)a2 + 1) < 0xFFu )
      v4 = *((_DWORD *)a2 + 1);
    if ( 2 * (unsigned __int64)v4 >= 0x200 )
      _report_rangecheckfailure();
    Destination[v4] = 0;
    v59 = *((_DWORD *)this + 402);
    if ( v59 >= 0x32 )
    {
      if ( v59 != 50 )
        return 0;
      *((_DWORD *)this + 402) = 51;
      v111 = 0;
      CErrorInterceptor::Init(
        (CErrorInterceptor *)v110,
        (_QWORD *)this + 222,
        *((_QWORD *)this + 211),
        0x80210523,
        2u,
        -1073606423,
        (const wchar_t *)this + 8,
        0,
        0,
        0,
        14,
        (__int64)L"MBProperty",
        1,
        -1,
        -1,
        (__int64)this + 16,
        2,
        v106,
        v107,
        *((_DWORD *)this + 420),
        -1);
      CErrorInterceptor::WriteToLog(
        (CErrorInterceptor *)v110,
        L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
        1749,
        *((_DWORD *)this + 409));
    }
    else
    {
      *((_DWORD *)this + 402) = v59 + 1;
      v111 = 0;
      CErrorInterceptor::Init(
        (CErrorInterceptor *)v110,
        (_QWORD *)this + 222,
        *((_QWORD *)this + 211),
        0x80210523,
        2u,
        -2147348287,
        Destination,
        0,
        0,
        0,
        14,
        (__int64)L"MBProperty",
        1,
        -1,
        -1,
        (__int64)this + 16,
        2,
        v106,
        v107,
        *((_DWORD *)this + 420),
        -1);
      CErrorInterceptor::WriteToLog(
        (CErrorInterceptor *)v110,
        L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
        1749,
        *((_DWORD *)this + 409));
    }
    CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)v110);
    return 0;
  }
  v15 = *((_QWORD *)a2 + 1);
  if ( *(_QWORD *)v15 != 0x74007300750043LL || *(_DWORD *)(v15 + 8) != 7143535 )
    goto LABEL_243;
  v16 = (unsigned int *)*((_QWORD *)this + 106);
  if ( !v16 )
  {
    wcsncpy_s(Destination, 0x100u, (const wchar_t *)v15, 6u);
    if ( *((_DWORD *)a2 + 1) < 0xFFu )
      v4 = *((_DWORD *)a2 + 1);
    if ( 2 * (unsigned __int64)v4 >= 0x200 )
      _report_rangecheckfailure();
    Destination[v4] = 0;
    v17 = *((_DWORD *)this + 402);
    if ( v17 >= 0x32 )
    {
      if ( v17 != 50 )
        return 0;
      *((_DWORD *)this + 402) = 51;
      v111 = 0;
      CErrorInterceptor::Init(
        (CErrorInterceptor *)v110,
        (_QWORD *)this + 222,
        *((_QWORD *)this + 211),
        0x80210523,
        2u,
        -1073606423,
        (const wchar_t *)this + 8,
        0,
        0,
        0,
        14,
        (__int64)L"MBProperty",
        1,
        -1,
        -1,
        (__int64)this + 16,
        2,
        v106,
        v107,
        *((_DWORD *)this + 420),
        -1);
      CErrorInterceptor::WriteToLog(
        (CErrorInterceptor *)v110,
        L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
        1758,
        *((_DWORD *)this + 409));
    }
    else
    {
      *((_DWORD *)this + 402) = v17 + 1;
      v111 = 0;
      CErrorInterceptor::Init(
        (CErrorInterceptor *)v110,
        (_QWORD *)this + 222,
        *((_QWORD *)this + 211),
        0x80210523,
        2u,
        -2147348286,
        Destination,
        0,
        0,
        0,
        14,
        (__int64)L"MBProperty",
        1,
        -1,
        -1,
        (__int64)this + 16,
        2,
        v106,
        v107,
        *((_DWORD *)this + 420),
        -1);
      CErrorInterceptor::WriteToLog(
        (CErrorInterceptor *)v110,
        L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
        1758,
        *((_DWORD *)this + 409));
    }
    CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)v110);
    return 0;
  }
  if ( *((_QWORD *)this + 218) && !*((_QWORD *)this + 105) )
    return 0;
  v18 = *v16;
  if ( v18 != 66 )
    *((_DWORD *)this + 564) = v18;
  *((_BYTE *)this + 1578) = 0;
  for ( m = 0; m < 9; ++m )
  {
    if ( m == 4 || m == 7 )
    {
      v18 = m;
      if ( !*((_QWORD *)this + m + 98) )
        return 0;
    }
    else
    {
      v18 = m - 8;
      if ( m != 8 )
      {
        v18 = m;
        *((_DWORD *)this + m + 314) = 0;
        *((_QWORD *)this + m + 98) = 0;
      }
    }
  }
  v109 = 0;
  v112 = 0;
  v113 = 0;
  v108 = 0;
  LOBYTE(v18) = 0;
  LODWORD(v116) = v18;
  memset_0(v130, 0, 0x90u);
  if ( TMetabase_XMLtable::FindAttribute(
         v20,
         a2,
         *((const unsigned __int16 **)this + 139),
         *((_DWORD *)this + 296),
         &v109) )
  {
    result = TMetabase_XMLtable::FillInColumn(
               (TMetabase_XMLtable *)((char *)this - 24),
               0,
               *((const unsigned __int16 **)a2 + 4 * v109 + 7),
               *((_DWORD *)a2 + 8 * v109 + 12),
               *((_DWORD *)this + 160),
               *((_DWORD *)this + 162),
               0);
    if ( (_DWORD)result )
    {
      if ( (_DWORD)result == 1 )
        return 0;
      return result;
    }
    *((_QWORD *)this + 255) = *(_QWORD *)(*((_QWORD *)this + 196)
                                        + 48LL * (unsigned int)(*((_DWORD *)this + 339) + *((_DWORD *)this + 564))
                                        + 16);
    *((_QWORD *)this + 257) = *((_QWORD *)this + 98);
    v110[0] = -1;
    if ( (*(int (__fastcall **)(_QWORD, _QWORD, __int64, char *, _QWORD, char *, unsigned int *))(**((_QWORD **)this + 252)
                                                                                                + 56LL))(
           *((_QWORD *)this + 252),
           0,
           2,
           (char *)this + 2024,
           0,
           (char *)this + 2040,
           v110) < 0 )
    {
      *((_QWORD *)this + 255) = **((_QWORD **)this + 193);
      v22 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, char *, _QWORD, char *, unsigned int *))(**((_QWORD **)this + 252) + 56LL))(
              *((_QWORD *)this + 252),
              0,
              2,
              (char *)this + 2024,
              0,
              (char *)this + 2040,
              v110);
      if ( v22 < 0 )
        goto LABEL_67;
      LOBYTE(v22) = 0;
      LODWORD(v116) = v22;
    }
    else
    {
      LOBYTE(v116) = 1;
    }
    v108 = 1;
LABEL_67:
    if ( v110[0] != -1 )
    {
      result = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)this + 252) + 32LL))(
                 *((_QWORD *)this + 252),
                 v110[0],
                 18);
      if ( (int)result < 0 )
        return result;
      v113 = TMetabase_XMLtable::MetabaseTypeFromColumnMetaType(v23, (struct tCOLUMNMETARow *)v130);
      wcscpy_s(*((wchar_t **)this + 98), *((unsigned int *)this + 314), Source);
      *((_QWORD *)this + 99) = &v113;
      *((_DWORD *)this + 315) = v125;
      *((_QWORD *)this + 100) = v135;
      *((_DWORD *)this + 316) = v124;
      *((_QWORD *)this + 103) = v133;
      *((_DWORD *)this + 319) = v126;
      *((_QWORD *)this + 104) = v134;
      *((_DWORD *)this + 320) = v127;
      v112 = *v132;
    }
  }
  if ( !TMetabase_XMLtable::FindAttribute(
          v21,
          a2,
          *((const unsigned __int16 **)this + 144),
          *((_DWORD *)this + 301),
          &v109) )
    goto LABEL_111;
  result = TMetabase_XMLtable::FillInColumn(
             (TMetabase_XMLtable *)((char *)this - 24),
             5u,
             *((const unsigned __int16 **)a2 + 4 * v109 + 7),
             *((_DWORD *)a2 + 8 * v109 + 12),
             *((_DWORD *)this + 175),
             *((_DWORD *)this + 177),
             0);
  if ( (_DWORD)result )
  {
    if ( (_DWORD)result == 1 )
      return 0;
    return result;
  }
  if ( !v108 )
  {
    *((_QWORD *)this + 255) = *(_QWORD *)(*((_QWORD *)this + 196)
                                        + 48LL * (unsigned int)(*((_DWORD *)this + 339) + *((_DWORD *)this + 564))
                                        + 16);
    *((_QWORD *)this + 268) = *((_QWORD *)this + 103);
    v110[0] = -1;
    if ( (*(int (__fastcall **)(_QWORD, _QWORD, __int64, char *, _QWORD, char *, unsigned int *))(**((_QWORD **)this + 252)
                                                                                                + 56LL))(
           *((_QWORD *)this + 252),
           0,
           2,
           (char *)this + 2032,
           0,
           (char *)this + 2040,
           v110) < 0 )
    {
      *((_QWORD *)this + 255) = **((_QWORD **)this + 193);
      v27 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, char *, _QWORD, char *, unsigned int *))(**((_QWORD **)this + 252) + 56LL))(
              *((_QWORD *)this + 252),
              0,
              2,
              (char *)this + 2032,
              0,
              (char *)this + 2040,
              v110);
      if ( v27 < 0 )
        goto LABEL_93;
      LOBYTE(v27) = 0;
      LODWORD(v116) = v27;
    }
    else
    {
      LOBYTE(v116) = 1;
    }
    v108 = 1;
LABEL_93:
    if ( v110[0] == -1 )
    {
      v32 = (wchar_t *)*((_QWORD *)this + 171);
      *((_QWORD *)this + 98) = v32;
      *((_DWORD *)this + 314) = 2
                              * swprintf_s(
                                  v32,
                                  *((_QWORD *)this + 172) >> 1,
                                  L"UnknownName_%u",
                                  **((unsigned int **)this + 103))
                              + 2;
      goto LABEL_111;
    }
    result = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)this + 252) + 32LL))(
               *((_QWORD *)this + 252),
               v110[0],
               18);
    if ( (int)result < 0 )
      return result;
    if ( !*((_QWORD *)this + 98)
      || !wcsncmp_0(*((const wchar_t **)this + 98), L"UnknownName_", 0xCu)
      && (v29 = wcstoul((const wchar_t *)(*((_QWORD *)this + 98) + 24LL), 0, 10),
          v28 = (TMetabase_XMLtable *)*((_QWORD *)this + 103),
          *(_DWORD *)v28 == v29) )
    {
      v113 = TMetabase_XMLtable::MetabaseTypeFromColumnMetaType(v28, (struct tCOLUMNMETARow *)v130);
      *((_QWORD *)this + 98) = Source;
      v24 = (TMetabase_XMLtable *)v124;
      *((_DWORD *)this + 314) = v124;
      *((_QWORD *)this + 99) = &v113;
      *((_DWORD *)this + 315) = v125;
      *((_QWORD *)this + 100) = v135;
      *((_DWORD *)this + 316) = (_DWORD)v24;
      *((_QWORD *)this + 104) = v134;
      *((_DWORD *)this + 320) = v127;
      v112 = *v132;
      goto LABEL_111;
    }
    swprintf_s(&Buffer, 0xCu, L"%d", **((unsigned int **)this + 103));
    v30 = 255;
    if ( *((_DWORD *)a2 + 8) < 0xFFu )
      v30 = *((unsigned int *)a2 + 8);
    wcsncpy_s(Destination, 0x100u, *((const wchar_t **)a2 + 5), v30);
    if ( *((_DWORD *)a2 + 8) < 0xFFu )
      v4 = *((_DWORD *)a2 + 8);
    if ( 2 * (unsigned __int64)v4 >= 0x200 )
      _report_rangecheckfailure();
    Destination[v4] = 0;
    v31 = *((_DWORD *)this + 402);
    if ( v31 >= 0x32 )
    {
      if ( v31 != 50 )
        return 0;
      *((_DWORD *)this + 402) = 51;
      v117 = 0;
      CErrorInterceptor::Init(
        (CErrorInterceptor *)&v116,
        (_QWORD *)this + 222,
        *((_QWORD *)this + 211),
        0x80210523,
        2u,
        -1073606423,
        (const wchar_t *)this + 8,
        0,
        0,
        0,
        14,
        (__int64)L"MBProperty",
        1,
        -1,
        -1,
        (__int64)this + 16,
        2,
        v106,
        v107,
        *((_DWORD *)this + 420),
        -1);
      CErrorInterceptor::WriteToLog(
        (CErrorInterceptor *)&v116,
        L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
        1938,
        *((_DWORD *)this + 409));
    }
    else
    {
      *((_DWORD *)this + 402) = v31 + 1;
      v117 = 0;
      CErrorInterceptor::Init(
        (CErrorInterceptor *)&v116,
        (_QWORD *)this + 222,
        *((_QWORD *)this + 211),
        0x80210523,
        2u,
        -2147348285,
        *((const wchar_t **)this + 98),
        &Buffer,
        Destination,
        0,
        14,
        (__int64)L"MBProperty",
        1,
        -1,
        -1,
        (__int64)this + 16,
        2,
        v106,
        v107,
        *((_DWORD *)this + 420),
        -1);
      CErrorInterceptor::WriteToLog(
        (CErrorInterceptor *)&v116,
        L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
        1938,
        *((_DWORD *)this + 409));
    }
    CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)&v116);
    return 0;
  }
  if ( *v133 != **((_DWORD **)this + 103) )
  {
    swprintf_s(&Buffer, 0xCu, L"%d");
    v25 = 255;
    if ( *((_DWORD *)a2 + 8) < 0xFFu )
      v25 = *((unsigned int *)a2 + 8);
    wcsncpy_s(Destination, 0x100u, *((const wchar_t **)a2 + 5), v25);
    if ( *((_DWORD *)a2 + 8) < 0xFFu )
      v4 = *((_DWORD *)a2 + 8);
    if ( 2 * (unsigned __int64)v4 >= 0x200 )
      _report_rangecheckfailure();
    Destination[v4] = 0;
    v26 = *((_DWORD *)this + 402);
    if ( v26 >= 0x32 )
    {
      if ( v26 != 50 )
        return 0;
      *((_DWORD *)this + 402) = 51;
      v111 = 0;
      CErrorInterceptor::Init(
        (CErrorInterceptor *)v110,
        (_QWORD *)this + 222,
        *((_QWORD *)this + 211),
        0x80210523,
        2u,
        -1073606423,
        (const wchar_t *)this + 8,
        0,
        0,
        0,
        14,
        (__int64)L"MBProperty",
        1,
        -1,
        -1,
        (__int64)this + 16,
        2,
        v106,
        v107,
        *((_DWORD *)this + 420),
        -1);
      CErrorInterceptor::WriteToLog(
        (CErrorInterceptor *)v110,
        L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
        1889,
        *((_DWORD *)this + 409));
    }
    else
    {
      *((_DWORD *)this + 402) = v26 + 1;
      v111 = 0;
      CErrorInterceptor::Init(
        (CErrorInterceptor *)v110,
        (_QWORD *)this + 222,
        *((_QWORD *)this + 211),
        0x80210523,
        2u,
        -2147348285,
        *((const wchar_t **)this + 98),
        &Buffer,
        Destination,
        0,
        14,
        (__int64)L"MBProperty",
        1,
        -1,
        -1,
        (__int64)this + 16,
        2,
        v106,
        v107,
        *((_DWORD *)this + 420),
        -1);
      CErrorInterceptor::WriteToLog(
        (CErrorInterceptor *)v110,
        L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
        1889,
        *((_DWORD *)this + 409));
    }
    CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)v110);
    return 0;
  }
LABEL_111:
  v33 = (_DWORD *)*((_QWORD *)this + 103);
  if ( !v33 )
  {
    Destination[0] = 0;
    if ( *((_DWORD *)a2 + 5) )
    {
      v34 = 255;
      if ( *((_DWORD *)a2 + 8) < 0xFFu )
        v34 = *((unsigned int *)a2 + 8);
      wcsncpy_s(Destination, 0x100u, *((const wchar_t **)a2 + 5), v34);
      if ( *((_DWORD *)a2 + 8) < 0xFFu )
        v4 = *((_DWORD *)a2 + 8);
      if ( 2 * (unsigned __int64)v4 >= 0x200 )
        _report_rangecheckfailure();
      Destination[v4] = 0;
    }
    v35 = *((_DWORD *)this + 402);
    if ( v35 >= 0x32 )
    {
      if ( v35 != 50 )
        return 0;
      *((_DWORD *)this + 402) = 51;
      v111 = 0;
      CErrorInterceptor::Init(
        (CErrorInterceptor *)v110,
        (_QWORD *)this + 222,
        *((_QWORD *)this + 211),
        0x80210523,
        2u,
        -1073606423,
        (const wchar_t *)this + 8,
        0,
        0,
        0,
        14,
        (__int64)L"MBProperty",
        1,
        -1,
        -1,
        (__int64)this + 16,
        2,
        v106,
        v107,
        *((_DWORD *)this + 420),
        -1);
      CErrorInterceptor::WriteToLog(
        (CErrorInterceptor *)v110,
        L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
        1977,
        *((_DWORD *)this + 409));
    }
    else
    {
      *((_DWORD *)this + 402) = v35 + 1;
      v111 = 0;
      CErrorInterceptor::Init(
        (CErrorInterceptor *)v110,
        (_QWORD *)this + 222,
        *((_QWORD *)this + 211),
        0x80210523,
        2u,
        -2147348284,
        Destination,
        0,
        0,
        0,
        14,
        (__int64)L"MBProperty",
        1,
        -1,
        -1,
        (__int64)this + 16,
        2,
        v106,
        v107,
        *((_DWORD *)this + 420),
        -1);
      CErrorInterceptor::WriteToLog(
        (CErrorInterceptor *)v110,
        L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
        1977,
        *((_DWORD *)this + 409));
    }
    CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)v110);
    return 0;
  }
  if ( *v33 == 1002 && *((_DWORD *)this + 564) )
  {
    v36 = 255;
    if ( *((_DWORD *)a2 + 8) < 0xFFu )
      v36 = *((unsigned int *)a2 + 8);
    wcsncpy_s(Destination, 0x100u, *((const wchar_t **)a2 + 5), v36);
    v37 = 255;
    if ( *((_DWORD *)a2 + 8) < 0xFFu )
      v37 = *((unsigned int *)a2 + 8);
    v38 = v37;
    if ( v38 >= 256 )
      _report_rangecheckfailure();
    Destination[v38] = 0;
    v39 = *((_DWORD *)this + 402);
    if ( v39 >= 0x32 )
    {
      if ( v39 != 50 )
        goto LABEL_135;
      *((_DWORD *)this + 402) = 51;
      v111 = 0;
      CErrorInterceptor::Init(
        (CErrorInterceptor *)v110,
        (_QWORD *)this + 222,
        *((_QWORD *)this + 211),
        0x80210523,
        2u,
        -1073606423,
        (const wchar_t *)this + 8,
        0,
        0,
        0,
        14,
        (__int64)L"MBProperty",
        1,
        -1,
        -1,
        (__int64)this + 16,
        2,
        v106,
        v107,
        *((_DWORD *)this + 420),
        -1);
      CErrorInterceptor::WriteToLog(
        (CErrorInterceptor *)v110,
        L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
        1988,
        *((_DWORD *)this + 409));
    }
    else
    {
      *((_DWORD *)this + 402) = v39 + 1;
      v111 = 0;
      CErrorInterceptor::Init(
        (CErrorInterceptor *)v110,
        (_QWORD *)this + 222,
        *((_QWORD *)this + 211),
        0x80210523,
        2u,
        -2147348292,
        **((const wchar_t ***)this + 193),
        Destination,
        0,
        0,
        14,
        (__int64)L"MBProperty",
        1,
        -1,
        -1,
        (__int64)this + 16,
        2,
        v106,
        v107,
        *((_DWORD *)this + 420),
        -1);
      CErrorInterceptor::WriteToLog(
        (CErrorInterceptor *)v110,
        L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
        1988,
        *((_DWORD *)this + 409));
    }
    CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)v110);
  }
LABEL_135:
  if ( TMetabase_XMLtable::FindAttribute(
         v24,
         a2,
         *((const unsigned __int16 **)this + 140),
         *((_DWORD *)this + 297),
         &v109) )
  {
    *(_QWORD *)v110 = 32LL * v109;
    result = TMetabase_XMLtable::FillInColumn(
               (TMetabase_XMLtable *)((char *)this - 24),
               1u,
               *(const unsigned __int16 **)((char *)a2 + *(_QWORD *)v110 + 56),
               *(_DWORD *)((char *)a2 + *(_QWORD *)v110 + 48),
               *((_DWORD *)this + 163),
               *((_DWORD *)this + 165),
               0);
    if ( (_DWORD)result )
    {
      if ( (_DWORD)result == 1 )
        return 0;
      return result;
    }
    v41 = (unsigned int *)*((_QWORD *)this + 99);
    v40 = *v41;
    if ( v113 != (_DWORD)v40 )
    {
      LOBYTE(v41) = 0;
      LODWORD(v116) = (_DWORD)v41;
      v40 = (unsigned int)(v40 - 1);
      if ( (_DWORD)v40 )
      {
        v40 = (unsigned int)(v40 - 1);
        if ( (_DWORD)v40 && (v40 = (unsigned int)(v40 - 1), (_DWORD)v40) )
        {
          v40 = (unsigned int)(v40 - 1);
          if ( (_DWORD)v40 )
          {
            if ( (_DWORD)v40 != 1 )
            {
              v42 = *(_DWORD *)((char *)a2 + *(_QWORD *)v110 + 48);
              if ( v42 > 0xFF )
                v42 = 255;
              wcsncpy_s(Destination, 0x100u, *(const wchar_t **)((char *)a2 + *(_QWORD *)v110 + 56), v42);
              v43 = *(unsigned int *)((char *)a2 + *(_QWORD *)v110 + 48);
              if ( (unsigned int)v43 > 0xFE )
                v43 = 254;
              v44 = v43;
              if ( v44 >= 256 )
                _report_rangecheckfailure();
              Destination[v44] = 0;
              v45 = *((_DWORD *)this + 402);
              if ( v45 >= 0x32 )
              {
                if ( v45 != 50 )
                  return 1;
                *((_DWORD *)this + 402) = 51;
                v111 = 0;
                CErrorInterceptor::Init(
                  (CErrorInterceptor *)v110,
                  (_QWORD *)this + 222,
                  *((_QWORD *)this + 211),
                  0x80210523,
                  2u,
                  -1073606423,
                  (const wchar_t *)this + 8,
                  0,
                  0,
                  0,
                  14,
                  (__int64)L"MBProperty",
                  1,
                  -1,
                  -1,
                  (__int64)this + 16,
                  2,
                  v106,
                  v107,
                  *((_DWORD *)this + 420),
                  -1);
                CErrorInterceptor::WriteToLog(
                  (CErrorInterceptor *)v110,
                  L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
                  2025,
                  *((_DWORD *)this + 409));
              }
              else
              {
                *((_DWORD *)this + 402) = v45 + 1;
                v111 = 0;
                CErrorInterceptor::Init(
                  (CErrorInterceptor *)v110,
                  (_QWORD *)this + 222,
                  *((_QWORD *)this + 211),
                  0x80210523,
                  2u,
                  -2147348281,
                  *((const wchar_t **)this + 140),
                  Destination,
                  0,
                  0,
                  14,
                  (__int64)L"MBProperty",
                  1,
                  -1,
                  -1,
                  (__int64)this + 16,
                  2,
                  v106,
                  v107,
                  *((_DWORD *)this + 420),
                  -1);
                CErrorInterceptor::WriteToLog(
                  (CErrorInterceptor *)v110,
                  L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
                  2025,
                  *((_DWORD *)this + 409));
              }
              CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)v110);
              return 1;
            }
            v112 = 0x2000000;
          }
          else
          {
            v112 = 0x4000000;
          }
        }
        else
        {
          v112 = 0;
        }
      }
      else
      {
        v112 = 0x100000;
      }
    }
  }
  if ( TMetabase_XMLtable::FindAttribute(
         (TMetabase_XMLtable *)v40,
         a2,
         *((const unsigned __int16 **)this + 141),
         *((_DWORD *)this + 298),
         &v109) )
  {
    result = TMetabase_XMLtable::FillInColumn(
               (TMetabase_XMLtable *)((char *)this - 24),
               2u,
               *((const unsigned __int16 **)a2 + 4 * v109 + 7),
               *((_DWORD *)a2 + 8 * v109 + 12),
               *((_DWORD *)this + 166),
               *((_DWORD *)this + 168),
               0);
    if ( (_DWORD)result )
    {
      if ( (_DWORD)result == 1 )
        return 0;
      return result;
    }
    if ( v108 )
    {
      v47 = (unsigned __int8)v116;
      v46 = (TMetabase_XMLtable *)**((unsigned int **)this + 100);
      if ( *v135 != (_DWORD)v46 )
        v47 = 0;
      LODWORD(v116) = v47;
    }
  }
  if ( *((_QWORD *)this + 99) )
    goto LABEL_184;
  v48 = 255;
  if ( *((_DWORD *)a2 + 8) < 0xFFu )
    v48 = *((unsigned int *)a2 + 8);
  wcsncpy_s(Destination, 0x100u, *((const wchar_t **)a2 + 5), v48);
  if ( *((_DWORD *)a2 + 8) < 0xFFu )
    v4 = *((_DWORD *)a2 + 8);
  if ( 2 * (unsigned __int64)v4 >= 0x200 )
    _report_rangecheckfailure();
  Destination[v4] = 0;
  v49 = *((_DWORD *)this + 402);
  if ( v49 < 0x32 )
  {
    *((_DWORD *)this + 402) = v49 + 1;
    v111 = 0;
    CErrorInterceptor::Init(
      (CErrorInterceptor *)v110,
      (_QWORD *)this + 222,
      *((_QWORD *)this + 211),
      0x80210523,
      2u,
      -2147348283,
      *((const wchar_t **)this + 98),
      Destination,
      0,
      0,
      14,
      (__int64)L"MBProperty",
      1,
      -1,
      -1,
      (__int64)this + 16,
      2,
      v106,
      v107,
      *((_DWORD *)this + 420),
      -1);
    CErrorInterceptor::WriteToLog(
      (CErrorInterceptor *)v110,
      L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
      2045,
      *((_DWORD *)this + 409));
LABEL_182:
    CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)v110);
    goto LABEL_183;
  }
  if ( v49 == 50 )
  {
    *((_DWORD *)this + 402) = 51;
    v111 = 0;
    CErrorInterceptor::Init(
      (CErrorInterceptor *)v110,
      (_QWORD *)this + 222,
      *((_QWORD *)this + 211),
      0x80210523,
      2u,
      -1073606423,
      (const wchar_t *)this + 8,
      0,
      0,
      0,
      14,
      (__int64)L"MBProperty",
      1,
      -1,
      -1,
      (__int64)this + 16,
      2,
      v106,
      v107,
      *((_DWORD *)this + 420),
      -1);
    CErrorInterceptor::WriteToLog(
      (CErrorInterceptor *)v110,
      L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
      2045,
      *((_DWORD *)this + 409));
    goto LABEL_182;
  }
LABEL_183:
  *((_QWORD *)this + 99) = &dword_180041544;
  *((_DWORD *)this + 315) = 4;
LABEL_184:
  for ( n = 0; ; n = (unsigned int)(n + 1) )
  {
    v110[0] = n;
    if ( (unsigned int)n >= 9 )
      break;
    if ( (unsigned int)n < 2 )
      continue;
    if ( (_DWORD)n == 2 )
    {
      if ( TMetabase_XMLtable::FindAttribute(
             v46,
             a2,
             *((const unsigned __int16 **)this + 141),
             *((_DWORD *)this + 298),
             &v109) )
      {
        result = TMetabase_XMLtable::FillInColumn(
                   (TMetabase_XMLtable *)((char *)this - 24),
                   2u,
                   *((const unsigned __int16 **)a2 + 4 * v109 + 7),
                   *((_DWORD *)a2 + 8 * v109 + 12),
                   *((_DWORD *)this + 166),
                   *((_DWORD *)this + 168),
                   0);
        if ( (_DWORD)result )
        {
          if ( (_DWORD)result == 1 )
            return 0;
          return result;
        }
        **((_DWORD **)this + 100) &= 0xFFFFFFDD;
      }
LABEL_222:
      if ( TMetabase_XMLtable::FindAttribute(
             v46,
             a2,
             *((const unsigned __int16 **)this + n + 139),
             *((_DWORD *)this + n + 296),
             &v109) )
      {
        result = TMetabase_XMLtable::FillInColumn(
                   (TMetabase_XMLtable *)((char *)this - 24),
                   v110[0],
                   *((const unsigned __int16 **)a2 + 4 * v109 + 7),
                   *((_DWORD *)a2 + 8 * v109 + 12),
                   *((_DWORD *)this + 3 * n + 160),
                   *((_DWORD *)this + 3 * n + 162),
                   0);
        if ( (_DWORD)result )
        {
          if ( (_DWORD)result == 1 )
            return 0;
          return result;
        }
        if ( v108 && v110[0] == 6 && (_BYTE)v116 )
        {
          v57 = v116;
          v46 = (TMetabase_XMLtable *)**((unsigned int **)this + n + 98);
          if ( *v134 != (_DWORD)v46 )
            v57 = 0;
          LOBYTE(v116) = v57;
        }
      }
      LODWORD(n) = v110[0];
      continue;
    }
    if ( (_DWORD)n != 3 )
    {
      if ( (_DWORD)n == 4 || (_DWORD)n == 5 || (_DWORD)n != 6 && (unsigned int)(n - 7) < 2 )
        continue;
      goto LABEL_222;
    }
    if ( TMetabase_XMLtable::FindAttribute(
           v46,
           a2,
           *((const unsigned __int16 **)this + 142),
           *((_DWORD *)this + 299),
           &v109) )
    {
      v51 = (_DWORD *)*((_QWORD *)this + 100);
      if ( !v51 || (v52 = (*v51 & 4) == 0, v53 = 1, v52) )
        v53 = 0;
      result = TMetabase_XMLtable::FillInColumn(
                 (TMetabase_XMLtable *)((char *)this - 24),
                 3u,
                 *((const unsigned __int16 **)a2 + 4 * v109 + 7),
                 *((_DWORD *)a2 + 8 * v109 + 12),
                 *((_DWORD *)this + 169),
                 v112,
                 v53);
      if ( (_DWORD)result )
      {
        if ( (_DWORD)result == 1 )
          return 0;
        return result;
      }
    }
    else
    {
      if ( !v108 )
      {
        v56 = *((_DWORD *)this + 402);
        if ( v56 < 0x32 )
        {
          *((_DWORD *)this + 402) = v56 + 1;
          v111 = 0;
          CErrorInterceptor::Init(
            (CErrorInterceptor *)v110,
            (_QWORD *)this + 222,
            *((_QWORD *)this + 211),
            0x80210523,
            2u,
            -2147348241,
            *((const wchar_t **)this + 98),
            0,
            0,
            0,
            14,
            (__int64)L"MBProperty",
            1,
            -1,
            -1,
            (__int64)this + 16,
            2,
            v106,
            v107,
            *((_DWORD *)this + 420),
            -1);
          CErrorInterceptor::WriteToLog(
            (CErrorInterceptor *)v110,
            L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
            2083,
            *((_DWORD *)this + 409));
          goto LABEL_214;
        }
        if ( v56 == 50 )
        {
          *((_DWORD *)this + 402) = 51;
          v111 = 0;
          CErrorInterceptor::Init(
            (CErrorInterceptor *)v110,
            (_QWORD *)this + 222,
            *((_QWORD *)this + 211),
            0x80210523,
            2u,
            -1073606423,
            (const wchar_t *)this + 8,
            0,
            0,
            0,
            14,
            (__int64)L"MBProperty",
            1,
            -1,
            -1,
            (__int64)this + 16,
            2,
            v106,
            v107,
            *((_DWORD *)this + 420),
            -1);
          CErrorInterceptor::WriteToLog(
            (CErrorInterceptor *)v110,
            L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
            2083,
            *((_DWORD *)this + 409));
LABEL_214:
          CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)v110);
        }
        return 0;
      }
      v54 = (_DWORD *)*((_QWORD *)this + 100);
      if ( !v54 || (v52 = (*v54 & 4) == 0, v55 = 1, v52) )
        v55 = 0;
      result = TMetabase_XMLtable::FillInColumn(
                 (TMetabase_XMLtable *)((char *)this - 24),
                 3u,
                 &word_180034198,
                 0,
                 *((_DWORD *)this + 169),
                 v112,
                 v55);
      if ( (_DWORD)result )
      {
        if ( (_DWORD)result == 1 )
          return 0;
        return result;
      }
    }
  }
  v58 = (unsigned int *)((char *)this + 2256);
  if ( !(_BYTE)v116 )
    v58 = &TMetabase_XMLtable::m_kMBProperty_Custom;
  *((_QWORD *)this + 106) = v58;
  *((_DWORD *)this + 322) = 4;
  v114[0] = 0;
  result = (*(__int64 (__fastcall **)(char *, unsigned int *))(*((_QWORD *)this - 3) + 72LL))((char *)this - 24, v114);
  if ( (int)result >= 0 )
  {
    result = (*(__int64 (__fastcall **)(char *, _QWORD, __int64))(*((_QWORD *)this - 3) + 88LL))(
               (char *)this - 24,
               v114[0],
               9);
    if ( (int)result >= 0 )
    {
      result = TMetabase_XMLtable::AddPropertyToLocationMapping(
                 (TMetabase_XMLtable *)((char *)this - 24),
                 *((const unsigned __int16 **)this + 102),
                 v114[0]);
      if ( (int)result >= 0 )
      {
        *((_BYTE *)this + 1577) = 0;
        return 0;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180006750  mov     [rsp+arg_10], rbx
0x180006755  mov     [rsp+arg_18], rsi
0x18000675a  push    rdi
0x18000675b  push    r12
0x18000675d  push    r13
0x18000675f  push    r14
0x180006761  push    r15
0x180006763  mov     eax, 13B0h
0x180006768  call    _alloca_probe
0x18000676d  sub     rsp, rax
0x180006770  mov     rax, cs:__security_cookie
0x180006777  xor     rax, rsp
0x18000677a  mov     [rsp+13D8h+var_38], rax
0x180006782  mov     r15, rdx
0x180006785  mov     rbx, rcx
0x180006788  mov     r14d, 1
0x18000678e  test    byte ptr [rdx+10h], 2
0x180006792  jz      short loc_18000679D
0x180006794  cmp     [rdx], r14d
0x180006797  jnz     loc_180006A27
0x18000679d  cmp     dword ptr [rdx+18h], 0Dh
0x1800067a1  jnz     loc_180006A21
0x1800067a7  mov     r12d, 0FFh
0x1800067ad  mov     r9d, r12d
0x1800067b0  cmp     [rdx+4], r12d
0x1800067b4  cmovb   r9d, [rdx+4]; MaxCount
0x1800067b9  mov     r8, [rdx+8]; Source
0x1800067bd  lea     esi, [r12+1]
0x1800067c2  mov     edx, esi; SizeInWords
0x1800067c4  lea     rcx, [rsp+13D8h+Destination]; Destination
0x1800067cc  call    cs:__imp_wcsncpy_s
0x1800067d2  mov     ecx, [r15+4]
0x1800067d6  mov     eax, r12d
0x1800067d9  cmp     ecx, r12d
0x1800067dc  cmovb   eax, ecx
0x1800067df  add     rax, rax
0x1800067e2  mov     r13d, 200h
0x1800067e8  cmp     rax, r13
0x1800067eb  jnb     loc_180009A55
0x1800067f1  xor     edi, edi
0x1800067f3  mov     [rsp+rax+13D8h+Destination], di
0x1800067fb  mov     r9d, r12d
0x1800067fe  cmp     ecx, r12d
0x180006801  cmovb   r9d, ecx; MaxCount
0x180006805  mov     r8, [r15+8]; Source
0x180006809  mov     edx, esi; SizeInWords
0x18000680b  lea     rcx, [rsp+13D8h+var_1238]; Destination
0x180006813  call    cs:__imp_wcsncpy_s
0x180006819  mov     eax, r12d
0x18000681c  cmp     [r15+4], r12d
0x180006820  cmovb   eax, [r15+4]
0x180006825  add     rax, rax
0x180006828  cmp     rax, r13
0x18000682b  jnb     loc_180009A55
0x180006831  mov     [rsp+rax+13D8h+var_1238], di
0x180006839  cmp     [r15+4], r12d
0x18000683d  jbe     short loc_180006855
0x18000683f  lea     eax, [rdi+2Eh]
0x180006842  mov     [rsp+13D8h+var_1040], 2E002Eh
0x18000684d  mov     [rsp+13D8h+var_103C], ax
0x180006855  mov     eax, [rbx+648h]
0x18000685b  cmp     eax, 32h ; '2'
0x18000685e  jnb     loc_18000694D
0x180006864  inc     eax
0x180006866  mov     [rbx+648h], eax
0x18000686c  mov     [rsp+13D8h+var_1300], rdi
0x180006874  lea     rcx, [rbx+10h]
0x180006878  lea     rdx, [rbx+6F0h]
0x18000687f  or      esi, 0FFFFFFFFh
0x180006882  mov     [rsp+13D8h+var_1338], esi
0x180006889  mov     eax, [rbx+690h]
0x18000688f  mov     [rsp+13D8h+var_1340], eax
0x180006896  mov     [rsp+13D8h+var_1358], 2
0x1800068a1  mov     [rsp+13D8h+var_1360], rcx
0x1800068a6  mov     [rsp+13D8h+var_1368], esi
0x1800068aa  mov     [rsp+13D8h+var_1370], esi
0x1800068ae  mov     [rsp+13D8h+var_1378], r14d
0x1800068b3  lea     rax, aMbproperty; "MBProperty"
0x1800068ba  mov     [rsp+13D8h+var_1380], rax
0x1800068bf  mov     [rsp+13D8h+var_1388], 0Eh
0x1800068c7  mov     [rsp+13D8h+var_1390], rdi
0x1800068cc  mov     [rsp+13D8h+var_1398], rdi
0x1800068d1  lea     rax, [rsp+13D8h+var_1238]
0x1800068d9  mov     [rsp+13D8h+var_13A0], rax
0x1800068de  lea     rax, [rsp+13D8h+Destination]
0x1800068e6  mov     qword ptr [rsp+13D8h+var_13A8], rax
0x1800068eb  mov     [rsp+13D8h+var_13B0], 800210EEh
0x1800068f3  mov     dword ptr [rsp+13D8h+var_13B8], 2
0x1800068fb  mov     r9d, 80210523h
0x180006901  mov     r8, [rbx+698h]
0x180006908  lea     rcx, [rsp+13D8h+var_1308]
0x180006910  call    ?Init@CErrorInterceptor@@AEAAXPEAPEAUISimpleTableWrite2@@PEAUIAdvancedTableDispenser@@JKKPEBG222K2W4eDETAILEDERRORS_OperationType@@KK2W4eDETAILEDERRORS_Type@@PEAEKKK@Z; CErrorInterceptor::Init(ISimpleTableWrite2 * *,IAdvancedTableDispenser *,long,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,eDETAILEDERRORS_OperationType,ulong,ulong,ushort const *,eDETAILEDERRORS_Type,uchar *,ulong,ulong,ulong)
0x180006915  nop
0x180006916  mov     r9d, [rbx+664h]; unsigned int
0x18000691d  mov     r8d, 5B7h; unsigned int
0x180006923  lea     r13, aInetsrvIisMbCo_4; "inetsrv\\iis\\mb\\config\\src\\stores\\"...
0x18000692a  mov     rdx, r13; unsigned __int16 *
0x18000692d  lea     rcx, [rsp+13D8h+var_1308]; this
0x180006935  call    ?WriteToLog@CErrorInterceptor@@QEAAJPEBGKK@Z; CErrorInterceptor::WriteToLog(ushort const *,ulong,ulong)
0x18000693a  nop
0x18000693b  lea     rcx, [rsp+13D8h+var_1308]; this
0x180006943  call    ??1CErrorInterceptor@@QEAA@XZ; CErrorInterceptor::~CErrorInterceptor(void)
0x180006948  jmp     loc_180006A40
0x18000694d  jnz     loc_180006A36
0x180006953  mov     dword ptr [rbx+648h], 33h ; '3'
0x18000695d  mov     [rsp+13D8h+var_1300], rdi
0x180006965  lea     rcx, [rbx+10h]
0x180006969  lea     rdx, [rbx+6F0h]
0x180006970  or      esi, 0FFFFFFFFh
0x180006973  mov     [rsp+13D8h+var_1338], esi
0x18000697a  mov     eax, [rbx+690h]
0x180006980  mov     [rsp+13D8h+var_1340], eax
0x180006987  mov     [rsp+13D8h+var_1358], 2
0x180006992  mov     [rsp+13D8h+var_1360], rcx
0x180006997  mov     [rsp+13D8h+var_1368], esi
0x18000699b  mov     [rsp+13D8h+var_1370], esi
0x18000699f  mov     [rsp+13D8h+var_1378], r14d
0x1800069a4  lea     rax, aMbproperty; "MBProperty"
0x1800069ab  mov     [rsp+13D8h+var_1380], rax
0x1800069b0  mov     [rsp+13D8h+var_1388], 0Eh
0x1800069b8  mov     [rsp+13D8h+var_1390], rdi
0x1800069bd  mov     [rsp+13D8h+var_1398], rdi
0x1800069c2  mov     [rsp+13D8h+var_13A0], rdi
0x1800069c7  mov     qword ptr [rsp+13D8h+var_13A8], rcx
0x1800069cc  mov     [rsp+13D8h+var_13B0], 0C00210E9h
0x1800069d4  mov     dword ptr [rsp+13D8h+var_13B8], 2
0x1800069dc  mov     r9d, 80210523h
0x1800069e2  mov     r8, [rbx+698h]
0x1800069e9  lea     rcx, [rsp+13D8h+var_1308]
0x1800069f1  call    ?Init@CErrorInterceptor@@AEAAXPEAPEAUISimpleTableWrite2@@PEAUIAdvancedTableDispenser@@JKKPEBG222K2W4eDETAILEDERRORS_OperationType@@KK2W4eDETAILEDERRORS_Type@@PEAEKKK@Z; CErrorInterceptor::Init(ISimpleTableWrite2 * *,IAdvancedTableDispenser *,long,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,eDETAILEDERRORS_OperationType,ulong,ulong,ushort const *,eDETAILEDERRORS_Type,uchar *,ulong,ulong,ulong)
0x1800069f6  nop
0x1800069f7  mov     r9d, [rbx+664h]; unsigned int
0x1800069fe  mov     r8d, 5B7h; unsigned int
0x180006a04  lea     r13, aInetsrvIisMbCo_4; "inetsrv\\iis\\mb\\config\\src\\stores\\"...
0x180006a0b  mov     rdx, r13; unsigned __int16 *
0x180006a0e  lea     rcx, [rsp+13D8h+var_1308]; this
0x180006a16  call    ?WriteToLog@CErrorInterceptor@@QEAAJPEBGKK@Z; CErrorInterceptor::WriteToLog(ushort const *,ulong,ulong)
0x180006a1b  nop
0x180006a1c  jmp     loc_18000693B
0x180006a21  cmp     dword ptr [rdx+18h], 12h
0x180006a25  jnz     short loc_180006A2E
0x180006a27  xor     eax, eax
0x180006a29  jmp     loc_180009A28
0x180006a2e  xor     edi, edi
0x180006a30  mov     r12d, 0FFh
0x180006a36  lea     r13, aInetsrvIisMbCo_4; "inetsrv\\iis\\mb\\config\\src\\stores\\"...
0x180006a3d  or      esi, 0FFFFFFFFh
0x180006a40  mov     ecx, [r15]
0x180006a43  sub     ecx, 1
0x180006a46  jz      loc_1800099CE
0x180006a4c  sub     ecx, 1
0x180006a4f  jz      loc_1800087DB
0x180006a55  cmp     ecx, 1
0x180006a58  jz      short loc_180006A61
0x180006a5a  xor     eax, eax
0x180006a5c  jmp     loc_180009A28
0x180006a61  cmp     [r15+18h], r14d
0x180006a65  jz      short loc_180006A6E
0x180006a67  xor     eax, eax
0x180006a69  jmp     loc_180009A28
0x180006a6e  mov     eax, [r15+4]
0x180006a72  cmp     eax, 6
0x180006a75  jnz     loc_1800085E4
0x180006a7b  mov     r8, [r15+8]; Source
0x180006a7f  mov     rcx, 74007300750043h
0x180006a89  cmp     rcx, [r8]
0x180006a8c  jnz     loc_1800085EC
0x180006a92  mov     ecx, 6D006Fh
0x180006a97  cmp     ecx, [r8+8]
0x180006a9b  jnz     loc_1800085EC
0x180006aa1  mov     rax, [rbx+350h]
0x180006aa8  test    rax, rax
0x180006aab  jnz     loc_180006C9D
0x180006ab1  mov     edx, 100h; SizeInWords
0x180006ab6  lea     r9d, [rax+6]; MaxCount
0x180006aba  lea     rcx, [rsp+13D8h+Destination]; Destination
0x180006ac2  call    cs:__imp_wcsncpy_s
0x180006ac8  cmp     [r15+4], r12d
0x180006acc  cmovb   r12d, [r15+4]
0x180006ad1  mov     eax, r12d
0x180006ad4  add     rax, rax
0x180006ad7  cmp     rax, 200h
0x180006add  jnb     loc_180009A5B
0x180006ae3  mov     [rsp+rax+13D8h+Destination], di
0x180006aeb  mov     eax, [rbx+648h]
0x180006af1  cmp     eax, 32h ; '2'
0x180006af4  jnb     loc_180006BC4
0x180006afa  inc     eax
0x180006afc  mov     [rbx+648h], eax
0x180006b02  mov     [rsp+13D8h+var_1318], rdi
0x180006b0a  lea     rcx, [rbx+10h]
0x180006b0e  lea     rdx, [rbx+6F0h]
0x180006b15  mov     [rsp+13D8h+var_1338], esi
0x180006b1c  mov     eax, [rbx+690h]
0x180006b22  mov     [rsp+13D8h+var_1340], eax
0x180006b29  mov     [rsp+13D8h+var_1358], 2
0x180006b34  mov     [rsp+13D8h+var_1360], rcx
0x180006b39  mov     [rsp+13D8h+var_1368], esi
0x180006b3d  mov     [rsp+13D8h+var_1370], esi
0x180006b41  mov     [rsp+13D8h+var_1378], r14d
0x180006b46  lea     rax, aMbproperty; "MBProperty"
0x180006b4d  mov     [rsp+13D8h+var_1380], rax
0x180006b52  mov     [rsp+13D8h+var_1388], 0Eh
0x180006b5a  mov     [rsp+13D8h+var_1390], rdi
0x180006b5f  mov     [rsp+13D8h+var_1398], rdi
0x180006b64  mov     [rsp+13D8h+var_13A0], rdi
0x180006b69  lea     rax, [rsp+13D8h+Destination]
0x180006b71  mov     qword ptr [rsp+13D8h+var_13A8], rax
0x180006b76  mov     [rsp+13D8h+var_13B0], 800210C2h
0x180006b7e  mov     dword ptr [rsp+13D8h+var_13B8], 2
0x180006b86  mov     r9d, 80210523h
0x180006b8c  mov     r8, [rbx+698h]
0x180006b93  lea     rcx, [rsp+13D8h+var_1320]
0x180006b9b  call    ?Init@CErrorInterceptor@@AEAAXPEAPEAUISimpleTableWrite2@@PEAUIAdvancedTableDispenser@@JKKPEBG222K2W4eDETAILEDERRORS_OperationType@@KK2W4eDETAILEDERRORS_Type@@PEAEKKK@Z; CErrorInterceptor::Init(ISimpleTableWrite2 * *,IAdvancedTableDispenser *,long,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,eDETAILEDERRORS_OperationType,ulong,ulong,ushort const *,eDETAILEDERRORS_Type,uchar *,ulong,ulong,ulong)
0x180006ba0  nop
0x180006ba1  mov     r9d, [rbx+664h]; unsigned int
0x180006ba8  mov     r8d, 6DEh; unsigned int
0x180006bae  mov     rdx, r13; unsigned __int16 *
0x180006bb1  lea     rcx, [rsp+13D8h+var_1320]; this
0x180006bb9  call    ?WriteToLog@CErrorInterceptor@@QEAAJPEBGKK@Z; CErrorInterceptor::WriteToLog(ushort const *,ulong,ulong)
0x180006bbe  nop
0x180006bbf  jmp     loc_180006C89
0x180006bc4  jnz     loc_180006C96
0x180006bca  mov     dword ptr [rbx+648h], 33h ; '3'
0x180006bd4  mov     [rsp+13D8h+var_1318], rdi
0x180006bdc  lea     rcx, [rbx+10h]
0x180006be0  lea     rdx, [rbx+6F0h]
0x180006be7  mov     [rsp+13D8h+var_1338], esi
0x180006bee  mov     eax, [rbx+690h]
0x180006bf4  mov     [rsp+13D8h+var_1340], eax
0x180006bfb  mov     [rsp+13D8h+var_1358], 2
0x180006c06  mov     [rsp+13D8h+var_1360], rcx
0x180006c0b  mov     [rsp+13D8h+var_1368], esi
0x180006c0f  mov     [rsp+13D8h+var_1370], esi
0x180006c13  mov     [rsp+13D8h+var_1378], r14d
0x180006c18  lea     rax, aMbproperty; "MBProperty"
0x180006c1f  mov     [rsp+13D8h+var_1380], rax
0x180006c24  mov     [rsp+13D8h+var_1388], 0Eh
0x180006c2c  mov     [rsp+13D8h+var_1390], rdi
0x180006c31  mov     [rsp+13D8h+var_1398], rdi
0x180006c36  mov     [rsp+13D8h+var_13A0], rdi
0x180006c3b  mov     qword ptr [rsp+13D8h+var_13A8], rcx
0x180006c40  mov     [rsp+13D8h+var_13B0], 0C00210E9h
0x180006c48  mov     dword ptr [rsp+13D8h+var_13B8], 2
0x180006c50  mov     r9d, 80210523h
0x180006c56  mov     r8, [rbx+698h]
0x180006c5d  lea     rcx, [rsp+13D8h+var_1320]
0x180006c65  call    ?Init@CErrorInterceptor@@AEAAXPEAPEAUISimpleTableWrite2@@PEAUIAdvancedTableDispenser@@JKKPEBG222K2W4eDETAILEDERRORS_OperationType@@KK2W4eDETAILEDERRORS_Type@@PEAEKKK@Z; CErrorInterceptor::Init(ISimpleTableWrite2 * *,IAdvancedTableDispenser *,long,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,eDETAILEDERRORS_OperationType,ulong,ulong,ushort const *,eDETAILEDERRORS_Type,uchar *,ulong,ulong,ulong)
0x180006c6a  nop
0x180006c6b  mov     r9d, [rbx+664h]; unsigned int
0x180006c72  mov     r8d, 6DEh; unsigned int
0x180006c78  mov     rdx, r13; unsigned __int16 *
0x180006c7b  lea     rcx, [rsp+13D8h+var_1320]; this
0x180006c83  call    ?WriteToLog@CErrorInterceptor@@QEAAJPEBGKK@Z; CErrorInterceptor::WriteToLog(ushort const *,ulong,ulong)
0x180006c88  nop
0x180006c89  lea     rcx, [rsp+13D8h+var_1320]; this
0x180006c91  call    ??1CErrorInterceptor@@QEAA@XZ; CErrorInterceptor::~CErrorInterceptor(void)
0x180006c96  xor     eax, eax
0x180006c98  jmp     loc_180009A28
0x180006c9d  cmp     [rbx+6D0h], rdi
0x180006ca4  jz      short loc_180006CB6
0x180006ca6  cmp     [rbx+348h], rdi
0x180006cad  jnz     short loc_180006CB6
0x180006caf  xor     eax, eax
0x180006cb1  jmp     loc_180009A28
0x180006cb6  mov     eax, [rax]
0x180006cb8  cmp     eax, 42h ; 'B'
0x180006cbb  jz      short loc_180006CC3
0x180006cbd  mov     [rbx+8D0h], eax
0x180006cc3  mov     [rbx+62Ah], dil
0x180006cca  mov     ecx, edi
0x180006ccc  cmp     ecx, 9
0x180006ccf  jnb     short loc_180006D0B
0x180006cd1  mov     eax, ecx
0x180006cd3  sub     eax, 4
0x180006cd6  jz      short loc_180006CF8
0x180006cd8  sub     eax, 3
0x180006cdb  jz      short loc_180006CF8
0x180006cdd  sub     eax, 1
0x180006ce0  jz      short loc_180006CF3
0x180006ce2  mov     eax, ecx
0x180006ce4  mov     [rbx+rax*4+4E8h], edi
0x180006ceb  mov     [rbx+rax*8+310h], rdi
0x180006cf3  add     ecx, r14d
0x180006cf6  jmp     short loc_180006CCC
0x180006cf8  mov     eax, ecx
0x180006cfa  cmp     [rbx+rax*8+310h], rdi
0x180006d02  jnz     short loc_180006CF3
0x180006d04  xor     eax, eax
0x180006d06  jmp     loc_180009A28
0x180006d0b  mov     [rsp+13D8h+var_1324], edi
0x180006d12  mov     [rsp+13D8h+var_1310], edi
0x180006d19  mov     [rsp+13D8h+var_130C], edi
0x180006d20  mov     [rsp+13D8h+var_1328], dil
0x180006d28  mov     al, dil
0x180006d2b  mov     dword ptr [rsp+13D8h+var_12F8], eax
0x180006d32  xor     edx, edx; Val
0x180006d34  mov     r8d, 90h; Size
0x180006d3a  lea     rcx, [rsp+13D8h+var_1238]; void *
0x180006d42  call    memset_0
  ... truncated ...
```
