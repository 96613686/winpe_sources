# TMetabase_XMLtable::GetColumnValue_UI4(ulong,ushort const *,ulong)

- ea: `0x18000a9b4`
- end: `0x18000bae4`
- name: `?GetColumnValue_UI4@TMetabase_XMLtable@@AEAAJKPEBGK@Z`
- size: `4400`
- prototype: `int(TMetabase_XMLtable *__hidden this, unsigned int, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180009acc`

## callees

- `0x180001b78`
- `0x180001e88`
- `0x180002bc4`
- `0x180005870`
- `0x18000a9b4`
- `0x18000c8a0`
- `0x18000ca28`
- `0x180011b38`
- `0x180012734`
- `0x18002e0b2`
- `0x18002e0e2`
- `0x18002e110`
- `0x180030010`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18000ac2e`
- `msvcrt!wcsncpy_s` at `0x18000ae3a`
- `msvcrt!wcsncpy_s` at `0x18000b6c9`
- `msvcrt!wcsncpy_s` at `0x18000b8d4`
- `msvcrt!wcsncpy_s` at `0x18000ac2e`
- `msvcrt!wcsncpy_s` at `0x18000ae3a`
- `msvcrt!wcsncpy_s` at `0x18000b6c9`
- `msvcrt!wcsncpy_s` at `0x18000b8d4`
- `msvcrt!_memicmp` at `0x18000b042`
- `msvcrt!_memicmp` at `0x18000b314`
- `msvcrt!_memicmp` at `0x18000b042`
- `msvcrt!_memicmp` at `0x18000b314`
- `msvcrt!wcstoul` at `0x18000ab77`
- `msvcrt!wcstoul` at `0x18000ab77`
- `msvcrt!_wcsicmp` at `0x18000b07c`
- `msvcrt!_wcsicmp` at `0x18000b357`
- `msvcrt!_wcsicmp` at `0x18000b653`
- `msvcrt!_wcsicmp` at `0x18000b07c`
- `msvcrt!_wcsicmp` at `0x18000b357`
- `msvcrt!_wcsicmp` at `0x18000b653`
- `ole32!CoTaskMemAlloc` at `0x18000aa5c`
- `ole32!CoTaskMemAlloc` at `0x18000b0c1`
- `ole32!CoTaskMemAlloc` at `0x18000b38b`
- `ole32!CoTaskMemAlloc` at `0x18000b5b3`
- `ole32!CoTaskMemAlloc` at `0x18000aa5c`
- `ole32!CoTaskMemAlloc` at `0x18000b0c1`
- `ole32!CoTaskMemAlloc` at `0x18000b38b`
- `ole32!CoTaskMemAlloc` at `0x18000b5b3`

## string_xrefs

- `0x18000ad06`: `inetsrv\iis\mb\config\src\stores\xmltable\metabase_xmltable.cpp`
- `0x18000adcd`: `inetsrv\iis\mb\config\src\stores\xmltable\metabase_xmltable.cpp`
- `0x18000af16`: `inetsrv\iis\mb\config\src\stores\xmltable\metabase_xmltable.cpp`
- `0x18000afe1`: `inetsrv\iis\mb\config\src\stores\xmltable\metabase_xmltable.cpp`
- `0x18000b1b5`: `inetsrv\iis\mb\config\src\stores\xmltable\metabase_xmltable.cpp`
- `0x18000b280`: `inetsrv\iis\mb\config\src\stores\xmltable\metabase_xmltable.cpp`
- `0x18000b496`: `inetsrv\iis\mb\config\src\stores\xmltable\metabase_xmltable.cpp`
- `0x18000b55d`: `inetsrv\iis\mb\config\src\stores\xmltable\metabase_xmltable.cpp`
- `0x18000b7a5`: `inetsrv\iis\mb\config\src\stores\xmltable\metabase_xmltable.cpp`
- `0x18000b870`: `inetsrv\iis\mb\config\src\stores\xmltable\metabase_xmltable.cpp`
- `0x18000b9b0`: `inetsrv\iis\mb\config\src\stores\xmltable\metabase_xmltable.cpp`
- `0x18000ba7b`: `inetsrv\iis\mb\config\src\stores\xmltable\metabase_xmltable.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall TMetabase_XMLtable::GetColumnValue_UI4(
        TMetabase_XMLtable *this,
        unsigned int a2,
        const unsigned __int16 *a3,
        unsigned int a4)
{
  __int64 v4; // r13
  __int64 v7; // r12
  unsigned int v8; // r15d
  wchar_t *v9; // rax
  wchar_t *v10; // rbx
  wchar_t **v11; // r8
  wchar_t *v12; // rbx
  char *v13; // r8
  unsigned int v14; // eax
  wchar_t **v15; // r8
  int v16; // eax
  unsigned int v17; // eax
  void **v18; // rcx
  unsigned int v20; // eax
  unsigned int v21; // eax
  TMetabase_XMLtable *v22; // rcx
  __int64 v23; // rbx
  size_t v24; // rax
  void *v25; // rbx
  unsigned int v26; // eax
  __int64 v27; // rax
  bool i; // zf
  __int64 v29; // rbx
  const void *v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rax
  unsigned int *v33; // rax
  unsigned int *v34; // rcx
  _WORD *v35; // rax
  _WORD *v36; // rbx
  unsigned int v37; // eax
  wchar_t *v38; // rax
  wchar_t *v39; // rbx
  wchar_t **v40; // r8
  wchar_t *v41; // rdi
  __int64 v42; // r8
  unsigned int v43; // ebx
  __int64 v44; // rcx
  __int64 v45; // r13
  wchar_t **v46; // r8
  unsigned int v47; // r13d
  unsigned int v48; // eax
  unsigned int v49; // eax
  unsigned int v50; // [rsp+B0h] [rbp-80h] BYREF
  unsigned int v51; // [rsp+B4h] [rbp-7Ch] BYREF
  __int64 v52; // [rsp+B8h] [rbp-78h] BYREF
  __int64 v53; // [rsp+C0h] [rbp-70h]
  size_t v54; // [rsp+C8h] [rbp-68h] BYREF
  __int64 v55; // [rsp+D0h] [rbp-60h]
  _DWORD *v56; // [rsp+D8h] [rbp-58h] BYREF
  void *Src[2]; // [rsp+E0h] [rbp-50h] BYREF
  wchar_t Destination[256]; // [rsp+F0h] [rbp-40h] BYREF

  v4 = a4;
  v51 = a4;
  Src[0] = (void *)a3;
  v50 = a2;
  v7 = a2;
  *((_QWORD *)this + a2 + 101) = *((_QWORD *)this + 2 * a2 + 174);
  *((_DWORD *)this + a2 + 320) = 4;
  v8 = 1;
  if ( a2 == 3 )
  {
    if ( (unsigned __int16)(*a3 - 48) > 9u && *a3 > 0x2Du )
    {
      v9 = (wchar_t *)CoTaskMemAlloc(saturated_mul(a4 + 1, 2u));
      v10 = v9;
      v54 = (size_t)v9;
      if ( !v9 )
      {
        v8 = -2147024882;
        goto LABEL_28;
      }
      memcpy_0(v9, Src[0], 2 * v4);
      v10[v4] = 0;
      v12 = wcstok_mvcrt_legacy_two_parameter_form(v10, L" ,|\n\t\r", v11);
      v52 = (__int64)v12;
      **((_DWORD **)this + v7 + 101) = 0;
      v13 = (char *)this + 2216;
      *((_QWORD *)this + 277) = **((_QWORD **)this + 196);
      v50 = 0;
      if ( v12 )
      {
        v8 = 1;
        while ( 1 )
        {
          *((_QWORD *)this + 279) = v12;
          if ( (*(int (__fastcall **)(_QWORD, _QWORD, __int64, char *, _QWORD, char *, unsigned int *))(**((_QWORD **)this + 219) + 56LL))(
                 *((_QWORD *)this + 219),
                 0,
                 2,
                 (char *)this + 2208,
                 0,
                 v13,
                 &v50) >= 0 )
          {
            v56 = 0;
            v51 = 4;
            v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, unsigned int *, _QWORD, _DWORD **))(**((_QWORD **)this + 219) + 32LL))(
                    *((_QWORD *)this + 219),
                    v50,
                    1,
                    &v51,
                    0,
                    &v56);
            if ( v16 < 0 )
            {
              v8 = v16;
              goto LABEL_28;
            }
            **((_DWORD **)this + v7 + 101) |= *v56;
          }
          else
          {
            if ( wcsncmp_0(v12, L"FLAG_", 5u)
              || (unsigned __int16)(v12[5] - 48) > 3u
              || (unsigned __int16)(v12[6] - 48) > 9u
              || v12[7]
              || (v14 = wcstoul(v12 + 5, 0, 10), v14 >= 0x20) )
            {
              if ( (unsigned int)v4 >= 0xFF )
                LODWORD(v4) = 255;
              wcsncpy_s(Destination, 0x100u, (const wchar_t *)Src[0], (unsigned int)v4);
              if ( 2 * (unsigned __int64)(unsigned int)v4 >= 0x200 )
                _report_rangecheckfailure();
              Destination[(unsigned int)v4] = 0;
              v17 = *((_DWORD *)this + 408);
              if ( v17 >= 0x32 )
              {
                if ( v17 != 50 )
                  goto LABEL_28;
                *((_DWORD *)this + 408) = 51;
                v53 = 0;
                CErrorInterceptor::Init(
                  &v52,
                  (char *)this + 1800,
                  *((_QWORD *)this + 214),
                  2149647651LL,
                  2,
                  -1073606423,
                  (char *)this + 40,
                  0,
                  0,
                  0,
                  14,
                  L"MBProperty",
                  1,
                  -1,
                  -1,
                  (char *)this + 40,
                  2);
                CErrorInterceptor::WriteToLog(
                  (CErrorInterceptor *)&v52,
                  L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
                  579,
                  *((_DWORD *)this + 415));
                v18 = (void **)&v52;
              }
              else
              {
                *((_DWORD *)this + 408) = v17 + 1;
                Src[1] = 0;
                CErrorInterceptor::Init(
                  Src,
                  (char *)this + 1800,
                  *((_QWORD *)this + 214),
                  2149647651LL,
                  2,
                  -2147348294,
                  v52,
                  Destination,
                  0,
                  0,
                  14,
                  L"MBProperty",
                  1,
                  -1,
                  -1,
                  (char *)this + 40,
                  2);
                CErrorInterceptor::WriteToLog(
                  (CErrorInterceptor *)Src,
                  L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
                  579,
                  *((_DWORD *)this + 415));
                v18 = Src;
              }
              CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)v18);
              goto LABEL_28;
            }
            **((_DWORD **)this + v7 + 101) |= 1 << v14;
          }
          v12 = wcstok_mvcrt_legacy_two_parameter_form(0, L" ,|\n\t\r", v15);
          v52 = (__int64)v12;
          if ( !v12 )
            goto LABEL_105;
          v13 = (char *)this + 2216;
        }
      }
      goto LABEL_105;
    }
    v50 = 0;
    if ( !TMetabase_XMLtable::NumberFromString(this, a3, a4, &v50) )
    {
      if ( (unsigned int)v4 >= 0xFF )
        LODWORD(v4) = 255;
      wcsncpy_s(Destination, 0x100u, a3, (unsigned int)v4);
      if ( 2 * (unsigned __int64)(unsigned int)v4 >= 0x200 )
        _report_rangecheckfailure();
      Destination[(unsigned int)v4] = 0;
      v20 = *((_DWORD *)this + 408);
      if ( v20 < 0x32 )
      {
        *((_DWORD *)this + 408) = v20 + 1;
        v55 = 0;
        CErrorInterceptor::Init(
          &v54,
          (char *)this + 1800,
          *((_QWORD *)this + 214),
          2149647651LL,
          2,
          -1073606422,
          Destination,
          0,
          0,
          0,
          14,
          L"MBProperty",
          1,
          -1,
          -1,
          (char *)this + 40,
          2);
        CErrorInterceptor::WriteToLog(
          (CErrorInterceptor *)&v54,
          L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
          537,
          *((_DWORD *)this + 415));
LABEL_114:
        CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)&v54);
        return v8;
      }
      if ( v20 == 50 )
      {
        *((_DWORD *)this + 408) = 51;
        v55 = 0;
        CErrorInterceptor::Init(
          &v54,
          (char *)this + 1800,
          *((_QWORD *)this + 214),
          2149647651LL,
          2,
          -1073606423,
          (char *)this + 40,
          0,
          0,
          0,
          14,
          L"MBProperty",
          1,
          -1,
          -1,
          (char *)this + 40,
          2);
        CErrorInterceptor::WriteToLog(
          (CErrorInterceptor *)&v54,
          L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
          537,
          *((_DWORD *)this + 415));
        goto LABEL_114;
      }
      return v8;
    }
    v21 = v50;
    goto LABEL_116;
  }
  v22 = (TMetabase_XMLtable *)*((unsigned int *)this + 3 * a2 + 168);
  if ( ((unsigned __int8)v22 & 0x20) == 0 )
  {
    if ( (char)v22 >= 0 || a2 != 1 && TMetabase_XMLtable::IsNumber(v22, a3, a4) )
    {
      if ( ((unsigned __int8)v22 & 0x40) == 0 || TMetabase_XMLtable::IsNumber(v22, a3, v4) )
      {
        v51 = 0;
        if ( !TMetabase_XMLtable::NumberFromString(v22, a3, v4, &v51) )
        {
          if ( (unsigned int)v4 >= 0xFF )
            LODWORD(v4) = 255;
          wcsncpy_s(Destination, 0x100u, a3, (unsigned int)v4);
          if ( 2 * (unsigned __int64)(unsigned int)v4 >= 0x200 )
            _report_rangecheckfailure();
          Destination[(unsigned int)v4] = 0;
          v49 = *((_DWORD *)this + 408);
          if ( v49 < 0x32 )
          {
            *((_DWORD *)this + 408) = v49 + 1;
            v55 = 0;
            CErrorInterceptor::Init(
              &v54,
              (char *)this + 1800,
              *((_QWORD *)this + 214),
              2149647651LL,
              2,
              -1073606422,
              Destination,
              0,
              0,
              0,
              14,
              L"MBProperty",
              1,
              -1,
              -1,
              (char *)this + 40,
              2);
            CErrorInterceptor::WriteToLog(
              (CErrorInterceptor *)&v54,
              L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
              710,
              *((_DWORD *)this + 415));
            goto LABEL_114;
          }
          if ( v49 == 50 )
          {
            *((_DWORD *)this + 408) = 51;
            v55 = 0;
            CErrorInterceptor::Init(
              &v54,
              (char *)this + 1800,
              *((_QWORD *)this + 214),
              2149647651LL,
              2,
              -1073606423,
              (char *)this + 40,
              0,
              0,
              0,
              14,
              L"MBProperty",
              1,
              -1,
              -1,
              (char *)this + 40,
              2);
            CErrorInterceptor::WriteToLog(
              (CErrorInterceptor *)&v54,
              L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
              710,
              *((_DWORD *)this + 415));
            goto LABEL_114;
          }
          return v8;
        }
        v21 = v51;
LABEL_116:
        v34 = (unsigned int *)*((_QWORD *)this + v7 + 101);
LABEL_117:
        *v34 = v21;
        return 0;
      }
      v38 = (wchar_t *)CoTaskMemAlloc(saturated_mul((unsigned int)(v4 + 1), 2u));
      v39 = v38;
      v54 = (size_t)v38;
      if ( !v38 )
      {
        v8 = -2147024882;
        goto LABEL_28;
      }
      memcpy_0(v38, Src[0], 2 * v4);
      v39[v4] = 0;
      v41 = wcstok_mvcrt_legacy_two_parameter_form(v39, L" ,|\n\t\r", v40);
      v42 = v50;
      **((_DWORD **)this + v50 + 101) = 0;
      v43 = *((_DWORD *)this + 2 * v42 + 329);
      if ( !v41 )
        goto LABEL_105;
      v44 = (unsigned int)v42;
      v45 = (unsigned int)v42;
      do
      {
        if ( v43 >= *((_DWORD *)this + 2 * v44 + 330) + *((_DWORD *)this + 2 * v45 + 329) )
          break;
        v52 = 48LL * v43;
        if ( _wcsicmp(*(const wchar_t **)(*((_QWORD *)this + 199) + v52 + 24), v41) )
        {
          ++v43;
        }
        else
        {
          **((_DWORD **)this + v7 + 101) |= **(_DWORD **)(*((_QWORD *)this + 199) + v52 + 32);
          v41 = wcstok_mvcrt_legacy_two_parameter_form(0, L" ,|\n\t\r", v46);
          v43 = *((_DWORD *)this + 2 * v45 + 329);
        }
        v44 = v45;
      }
      while ( v41 );
      v47 = v51;
      if ( !v41 )
      {
LABEL_105:
        TSmartPointerArray<bool>::~TSmartPointerArray<bool>(&v54);
        return 0;
      }
      if ( v51 >= 0xFF )
        v47 = 255;
      wcsncpy_s(Destination, 0x100u, (const wchar_t *)Src[0], v47);
      if ( 2 * (unsigned __int64)v47 >= 0x200 )
        _report_rangecheckfailure();
      Destination[v47] = 0;
      v48 = *((_DWORD *)this + 408);
      if ( v48 >= 0x32 )
      {
        if ( v48 != 50 )
          goto LABEL_28;
        *((_DWORD *)this + 408) = 51;
        v53 = 0;
        CErrorInterceptor::Init(
          &v52,
          (char *)this + 1800,
          *((_QWORD *)this + 214),
          2149647651LL,
          2,
          -1073606423,
          (char *)this + 40,
          0,
          0,
          0,
          14,
          L"MBProperty",
          1,
          -1,
          -1,
          (char *)this + 40,
          2);
        CErrorInterceptor::WriteToLog(
          (CErrorInterceptor *)&v52,
          L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
          697,
          *((_DWORD *)this + 415));
      }
      else
      {
        *((_DWORD *)this + 408) = v48 + 1;
        v53 = 0;
        CErrorInterceptor::Init(
          &v52,
          (char *)this + 1800,
          *((_QWORD *)this + 214),
          2149647651LL,
          2,
          -2147348294,
          v41,
          Destination,
          0,
          0,
          14,
          L"MBProperty",
          1,
          -1,
          -1,
          (char *)this + 40,
          2);
        CErrorInterceptor::WriteToLog(
          (CErrorInterceptor *)&v52,
          L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
          697,
          *((_DWORD *)this + 415));
      }
      CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)&v52);
    }
    else
    {
      v27 = *((unsigned int *)this + 2 * v7 + 329);
      v51 = *((_DWORD *)this + 2 * v7 + 330);
      for ( i = v51 == 0; ; i = v51-- == 1 )
      {
        LODWORD(v56) = v27;
        if ( i )
          break;
        v29 = 6 * v27;
        v30 = *(const void **)(*((_QWORD *)this + 199) + 48 * v27 + 24);
        if ( (_DWORD)v4 )
        {
          if ( !_memicmp(v30, a3, 2 * v4) )
          {
            v31 = *((_QWORD *)this + 199);
            v32 = -1;
            do
              ++v32;
            while ( *(_WORD *)(*(_QWORD *)(v31 + 8 * v29 + 24) + 2 * v32) );
            if ( v4 == v32 )
            {
              v33 = *(unsigned int **)(v31 + 8 * v29 + 32);
LABEL_71:
              v34 = (unsigned int *)*((_QWORD *)this + v50 + 101);
              v21 = *v33;
              goto LABEL_117;
            }
          }
        }
        else if ( !_wcsicmp((const wchar_t *)v30, a3) )
        {
          v33 = *(unsigned int **)(*((_QWORD *)this + 199) + 8 * v29 + 32);
          goto LABEL_71;
        }
        v27 = (unsigned int)((_DWORD)v56 + 1);
      }
      v35 = CoTaskMemAlloc(saturated_mul((unsigned int)(v4 + 1), 2u));
      v36 = v35;
      v54 = (size_t)v35;
      if ( !v35 )
      {
        v8 = -2147024882;
        goto LABEL_28;
      }
      memcpy_0(v35, Src[0], 2 * v4);
      v36[v4] = 0;
      v37 = *((_DWORD *)this + 408);
      if ( v37 >= 0x32 )
      {
        if ( v37 != 50 )
          goto LABEL_28;
        *((_DWORD *)this + 408) = 51;
        v53 = 0;
        CErrorInterceptor::Init(
          &v52,
          (char *)this + 1800,
          *((_QWORD *)this + 214),
          2149647651LL,
          2,
          -1073606423,
          (char *)this + 40,
          0,
          0,
          0,
          14,
          L"MBProperty",
          1,
          -1,
          -1,
          (char *)this + 40,
          2);
        CErrorInterceptor::WriteToLog(
          (CErrorInterceptor *)&v52,
          L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
          659,
          *((_DWORD *)this + 415));
      }
      else
      {
        *((_DWORD *)this + 408) = v37 + 1;
        v53 = 0;
        CErrorInterceptor::Init(
          &v52,
          (char *)this + 1800,
          *((_QWORD *)this + 214),
          2149647651LL,
          2,
          -2147348281,
          *((_QWORD *)this + v50 + 142),
          v36,
          0,
          0,
          14,
          L"MBProperty",
          1,
          -1,
          -1,
          (char *)this + 40,
          2);
        CErrorInterceptor::WriteToLog(
          (CErrorInterceptor *)&v52,
          L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
          659,
          *((_DWORD *)this + 415));
      }
      CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)&v52);
    }
LABEL_28:
    TSmartPointerArray<bool>::~TSmartPointerArray<bool>(&v54);
    return v8;
  }
  LODWORD(v23) = 0;
  if ( a4 )
  {
    if ( TMetabase_XMLtable::m_kwszBoolStrings )
    {
      v24 = 2LL * a4;
      v54 = v24;
      do
      {
        if ( !_memicmp((&TMetabase_XMLtable::m_kwszBoolStrings)[(unsigned int)v23], a3, v24) )
          break;
        v23 = (unsigned int)(v23 + 1);
        v24 = v54;
      }
      while ( (&TMetabase_XMLtable::m_kwszBoolStrings)[v23] );
    }
  }
  else if ( TMetabase_XMLtable::m_kwszBoolStrings )
  {
    do
    {
      if ( !_wcsicmp((const wchar_t *)(&TMetabase_XMLtable::m_kwszBoolStrings)[(unsigned int)v23], a3) )
        break;
      v23 = (unsigned int)(v23 + 1);
    }
    while ( (&TMetabase_XMLtable::m_kwszBoolStrings)[v23] );
    LODWORD(v4) = v51;
  }
  if ( !(&TMetabase_XMLtable::m_kwszBoolStrings)[(unsigned int)v23] )
  {
    v25 = CoTaskMemAlloc(saturated_mul((unsigned int)(v4 + 1), 2u));
    v54 = (size_t)v25;
    if ( !v25 )
    {
      v8 = -2147024882;
      goto LABEL_28;
    }
    memcpy_0(v25, Src[0], 2LL * (unsigned int)v4);
    *((_WORD *)v25 + (unsigned int)v4) = 0;
    v26 = *((_DWORD *)this + 408);
    if ( v26 >= 0x32 )
    {
      if ( v26 != 50 )
        goto LABEL_28;
      *((_DWORD *)this + 408) = 51;
      v53 = 0;
      CErrorInterceptor::Init(
        &v52,
        (char *)this + 1800,
        *((_QWORD *)this + 214),
        2149647651LL,
        2,
        -1073606423,
        (char *)this + 40,
        0,
        0,
        0,
        14,
        L"MBProperty",
        1,
        -1,
        -1,
        (char *)this + 40,
        2);
      CErrorInterceptor::WriteToLog(
        (CErrorInterceptor *)&v52,
        L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
        619,
        *((_DWORD *)this + 415));
    }
    else
    {
      *((_DWORD *)this + 408) = v26 + 1;
      v53 = 0;
      CErrorInterceptor::Init(
        &v52,
        (char *)this + 1800,
        *((_QWORD *)this + 214),
        2149647651LL,
        2,
        -2147348282,
        v25,
        0,
        0,
        0,
        14,
        L"MBProperty",
        1,
        -1,
        -1,
        (char *)this + 40,
        2);
      CErrorInterceptor::WriteToLog(
        (CErrorInterceptor *)&v52,
        L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
        619,
        *((_DWORD *)this + 415));
    }
    CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)&v52);
    goto LABEL_28;
  }
  **((_DWORD **)this + v7 + 101) = v23 & 1;
  return 0;
}

```

## disassembly

```asm
0x18000a9b4  push    rbp
0x18000a9b6  push    rbx
0x18000a9b7  push    rsi
0x18000a9b8  push    rdi
0x18000a9b9  push    r12
0x18000a9bb  push    r13
0x18000a9bd  push    r14
0x18000a9bf  push    r15
0x18000a9c1  lea     rbp, [rsp-1D8h]
0x18000a9c9  sub     rsp, 308h
0x18000a9d0  mov     rax, cs:__security_cookie
0x18000a9d7  xor     rax, rsp
0x18000a9da  mov     [rbp+210h+var_50], rax
0x18000a9e1  mov     r13d, r9d
0x18000a9e4  mov     [rbp+210h+var_28C], r13d
0x18000a9e8  mov     rdi, r8
0x18000a9eb  mov     [rbp+210h+Src], r8
0x18000a9ef  mov     [rbp+210h+var_290], edx
0x18000a9f2  mov     r14, rcx
0x18000a9f5  mov     r12d, edx
0x18000a9f8  lea     rax, [r12+57h]
0x18000a9fd  add     rax, rax
0x18000aa00  mov     rax, [rcx+rax*8]
0x18000aa04  mov     [rcx+r12*8+328h], rax
0x18000aa0c  mov     dword ptr [rcx+r12*4+500h], 4
0x18000aa18  mov     r15d, 1
0x18000aa1e  cmp     edx, 3
0x18000aa21  jnz     loc_18000AFFF
0x18000aa27  movzx   eax, word ptr [r8]
0x18000aa2b  sub     ax, 30h ; '0'
0x18000aa2f  cmp     ax, 9
0x18000aa33  jbe     loc_18000AE02
0x18000aa39  cmp     word ptr [r8], 2Dh ; '-'
0x18000aa3e  jbe     loc_18000AE02
0x18000aa44  lea     ecx, [r13+1]
0x18000aa48  lea     eax, [rdx-1]
0x18000aa4b  mul     rcx
0x18000aa4e  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000aa55  cmovb   rax, rcx
0x18000aa59  mov     rcx, rax; cb
0x18000aa5c  call    cs:__imp_CoTaskMemAlloc
0x18000aa62  mov     rbx, rax
0x18000aa65  mov     [rbp+210h+var_278], rax
0x18000aa69  xor     esi, esi
0x18000aa6b  test    rax, rax
0x18000aa6e  jnz     short loc_18000AA7B
0x18000aa70  mov     r15d, 8007000Eh
0x18000aa76  jmp     loc_18000ADEC
0x18000aa7b  lea     rdi, ds:0[r13*2]
0x18000aa83  mov     r8, rdi; Size
0x18000aa86  mov     rdx, [rbp+210h+Src]; Src
0x18000aa8a  mov     rcx, rbx; void *
0x18000aa8d  call    memcpy_0
0x18000aa92  mov     [rdi+rbx], si
0x18000aa96  lea     rdx, Delimiter; " ,|\n\t\r"
0x18000aa9d  mov     rcx, rbx; String
0x18000aaa0  call    wcstok_mvcrt_legacy_two_parameter_form
0x18000aaa5  mov     rbx, rax
0x18000aaa8  mov     [rbp+210h+var_288], rax
0x18000aaac  mov     rcx, [r14+r12*8+328h]
0x18000aab4  mov     [rcx], esi
0x18000aab6  lea     r8, [r14+8A8h]
0x18000aabd  mov     rcx, [r14+620h]
0x18000aac4  mov     rdx, [rcx]
0x18000aac7  mov     [r8], rdx
0x18000aaca  mov     [rbp+210h+var_290], esi
0x18000aacd  test    rax, rax
0x18000aad0  jz      loc_18000ADFD
0x18000aad6  mov     edi, 2
0x18000aadb  lea     r15d, [rdi-1]
0x18000aadf  lea     rdx, [r14+8A0h]
0x18000aae6  mov     [r14+8B8h], rbx
0x18000aaed  mov     rcx, [r14+6D8h]
0x18000aaf4  mov     rax, [rcx]
0x18000aaf7  lea     r9, [rbp+210h+var_290]
0x18000aafb  mov     [rsp+340h+var_310], r9
0x18000ab00  mov     [rsp+340h+var_318], r8
0x18000ab05  mov     [rsp+340h+var_320], rsi
0x18000ab0a  mov     r9, rdx
0x18000ab0d  mov     r8d, edi
0x18000ab10  xor     edx, edx
0x18000ab12  mov     rax, [rax+38h]
0x18000ab16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab1b  test    eax, eax
0x18000ab1d  jns     short loc_18000AB99
0x18000ab1f  mov     r8d, 5; MaxCount
0x18000ab25  lea     rdx, aFlag; "FLAG_"
0x18000ab2c  mov     rcx, rbx; String1
0x18000ab2f  call    wcsncmp_0
0x18000ab34  test    eax, eax
0x18000ab36  jnz     loc_18000AC11
0x18000ab3c  lea     rcx, [rbx+0Ah]; String
0x18000ab40  movzx   eax, word ptr [rcx]
0x18000ab43  sub     ax, 30h ; '0'
0x18000ab47  mov     edx, 3
0x18000ab4c  cmp     ax, dx
0x18000ab4f  ja      loc_18000AC11
0x18000ab55  movzx   eax, word ptr [rbx+0Ch]
0x18000ab59  sub     ax, 30h ; '0'
0x18000ab5d  cmp     ax, 9
0x18000ab61  ja      loc_18000AC11
0x18000ab67  cmp     [rbx+0Eh], si
0x18000ab6b  jnz     loc_18000AC11
0x18000ab71  xor     edx, edx; EndPtr
0x18000ab73  lea     r8d, [rdx+0Ah]; Radix
0x18000ab77  call    cs:__imp_wcstoul
0x18000ab7d  cmp     eax, 20h ; ' '
0x18000ab80  jnb     loc_18000AC11
0x18000ab86  mov     rdx, [r14+r12*8+328h]
0x18000ab8e  mov     ecx, eax
0x18000ab90  mov     eax, r15d
0x18000ab93  shl     eax, cl
0x18000ab95  or      [rdx], eax
0x18000ab97  jmp     short loc_18000ABE7
0x18000ab99  mov     [rbp+210h+var_268], rsi
0x18000ab9d  mov     [rbp+210h+var_28C], 4
0x18000aba4  mov     rcx, [r14+6D8h]
0x18000abab  mov     rax, [rcx]
0x18000abae  lea     rdx, [rbp+210h+var_268]
0x18000abb2  mov     [rsp+340h+var_318], rdx
0x18000abb7  mov     [rsp+340h+var_320], rsi
0x18000abbc  lea     r9, [rbp+210h+var_28C]
0x18000abc0  mov     r8d, r15d
0x18000abc3  mov     edx, [rbp+210h+var_290]
0x18000abc6  mov     rax, [rax+20h]
0x18000abca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abcf  test    eax, eax
0x18000abd1  js      loc_18000ADE9
0x18000abd7  mov     rdx, [r14+r12*8+328h]
0x18000abdf  mov     rax, [rbp+210h+var_268]
0x18000abe3  mov     ecx, [rax]
0x18000abe5  or      [rdx], ecx
0x18000abe7  lea     rdx, Delimiter; " ,|\n\t\r"
0x18000abee  xor     ecx, ecx; String
0x18000abf0  call    wcstok_mvcrt_legacy_two_parameter_form
0x18000abf5  mov     rbx, rax
0x18000abf8  mov     [rbp+210h+var_288], rax
0x18000abfc  test    rax, rax
0x18000abff  jz      loc_18000ADFD
0x18000ac05  lea     r8, [r14+8A8h]
0x18000ac0c  jmp     loc_18000AADF
0x18000ac11  mov     eax, 0FFh
0x18000ac16  cmp     r13d, eax
0x18000ac19  cmovnb  r13d, eax
0x18000ac1d  mov     ebx, r13d
0x18000ac20  mov     r9d, r13d; MaxCount
0x18000ac23  mov     r8, [rbp+210h+Src]; Source
0x18000ac27  lea     edx, [rax+1]; SizeInWords
0x18000ac2a  lea     rcx, [rbp+210h+Destination]; Destination
0x18000ac2e  call    cs:__imp_wcsncpy_s
0x18000ac34  add     rbx, rbx
0x18000ac37  cmp     rbx, 200h
0x18000ac3e  jnb     loc_18000BAD2
0x18000ac44  mov     [rbp+rbx+210h+Destination], si
0x18000ac49  mov     eax, [r14+660h]
0x18000ac50  cmp     eax, 32h ; '2'
0x18000ac53  jnb     loc_18000AD20
0x18000ac59  inc     eax
0x18000ac5b  mov     [r14+660h], eax
0x18000ac62  mov     [rbp+210h+var_258], rsi
0x18000ac66  lea     rcx, [r14+28h]
0x18000ac6a  lea     rdx, [r14+708h]
0x18000ac71  or      r12d, 0FFFFFFFFh
0x18000ac75  mov     [rsp+340h+var_2A0], r12d
0x18000ac7d  mov     eax, [r14+6A8h]
0x18000ac84  mov     [rsp+340h+var_2A8], eax
0x18000ac8b  mov     [rsp+340h+var_2C0], edi
0x18000ac92  mov     [rsp+340h+var_2C8], rcx
0x18000ac97  mov     [rsp+340h+var_2D0], r12d
0x18000ac9c  mov     [rsp+340h+var_2D8], r12d
0x18000aca1  mov     [rsp+340h+var_2E0], r15d
0x18000aca6  lea     rax, aMbproperty; "MBProperty"
0x18000acad  mov     [rsp+340h+var_2E8], rax
0x18000acb2  mov     [rsp+340h+var_2F0], 0Eh
0x18000acba  mov     [rsp+340h+var_2F8], rsi
0x18000acbf  mov     [rsp+340h+var_300], rsi
0x18000acc4  lea     rax, [rbp+210h+Destination]
0x18000acc8  mov     [rsp+340h+var_308], rax
0x18000accd  mov     rax, [rbp+210h+var_288]
0x18000acd1  mov     [rsp+340h+var_310], rax
0x18000acd6  mov     dword ptr [rsp+340h+var_318], 800210BAh
0x18000acde  mov     dword ptr [rsp+340h+var_320], edi
0x18000ace2  mov     r9d, 80210523h
0x18000ace8  mov     r8, [r14+6B0h]
0x18000acef  lea     rcx, [rbp+210h+Src]
0x18000acf3  call    ?Init@CErrorInterceptor@@AEAAXPEAPEAUISimpleTableWrite2@@PEAUIAdvancedTableDispenser@@JKKPEBG222K2W4eDETAILEDERRORS_OperationType@@KK2W4eDETAILEDERRORS_Type@@PEAEKKK@Z; CErrorInterceptor::Init(ISimpleTableWrite2 * *,IAdvancedTableDispenser *,long,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,eDETAILEDERRORS_OperationType,ulong,ulong,ushort const *,eDETAILEDERRORS_Type,uchar *,ulong,ulong,ulong)
0x18000acf8  nop
0x18000acf9  mov     r9d, [r14+67Ch]; unsigned int
0x18000ad00  mov     r8d, 243h; unsigned int
0x18000ad06  lea     rdx, aInetsrvIisMbCo_4; "inetsrv\\iis\\mb\\config\\src\\stores\\"...
0x18000ad0d  lea     rcx, [rbp+210h+Src]; this
0x18000ad11  call    ?WriteToLog@CErrorInterceptor@@QEAAJPEBGKK@Z; CErrorInterceptor::WriteToLog(ushort const *,ulong,ulong)
0x18000ad16  nop
0x18000ad17  lea     rcx, [rbp+210h+Src]
0x18000ad1b  jmp     loc_18000ADE2
0x18000ad20  jnz     loc_18000ADEC
0x18000ad26  mov     dword ptr [r14+660h], 33h ; '3'
0x18000ad31  mov     [rbp+210h+var_280], rsi
0x18000ad35  lea     rcx, [r14+28h]
0x18000ad39  lea     rdx, [r14+708h]
0x18000ad40  or      r12d, 0FFFFFFFFh
0x18000ad44  mov     [rsp+340h+var_2A0], r12d
0x18000ad4c  mov     eax, [r14+6A8h]
0x18000ad53  mov     [rsp+340h+var_2A8], eax
0x18000ad5a  mov     [rsp+340h+var_2C0], edi
0x18000ad61  mov     [rsp+340h+var_2C8], rcx
0x18000ad66  mov     [rsp+340h+var_2D0], r12d
0x18000ad6b  mov     [rsp+340h+var_2D8], r12d
0x18000ad70  mov     [rsp+340h+var_2E0], r15d
0x18000ad75  lea     rax, aMbproperty; "MBProperty"
0x18000ad7c  mov     [rsp+340h+var_2E8], rax
0x18000ad81  mov     [rsp+340h+var_2F0], 0Eh
0x18000ad89  mov     [rsp+340h+var_2F8], rsi
0x18000ad8e  mov     [rsp+340h+var_300], rsi
0x18000ad93  mov     [rsp+340h+var_308], rsi
0x18000ad98  mov     [rsp+340h+var_310], rcx
0x18000ad9d  mov     dword ptr [rsp+340h+var_318], 0C00210E9h
0x18000ada5  mov     dword ptr [rsp+340h+var_320], edi
0x18000ada9  mov     r9d, 80210523h
0x18000adaf  mov     r8, [r14+6B0h]
0x18000adb6  lea     rcx, [rbp+210h+var_288]
0x18000adba  call    ?Init@CErrorInterceptor@@AEAAXPEAPEAUISimpleTableWrite2@@PEAUIAdvancedTableDispenser@@JKKPEBG222K2W4eDETAILEDERRORS_OperationType@@KK2W4eDETAILEDERRORS_Type@@PEAEKKK@Z; CErrorInterceptor::Init(ISimpleTableWrite2 * *,IAdvancedTableDispenser *,long,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,eDETAILEDERRORS_OperationType,ulong,ulong,ushort const *,eDETAILEDERRORS_Type,uchar *,ulong,ulong,ulong)
0x18000adbf  nop
0x18000adc0  mov     r9d, [r14+67Ch]; unsigned int
0x18000adc7  mov     r8d, 243h; unsigned int
0x18000adcd  lea     rdx, aInetsrvIisMbCo_4; "inetsrv\\iis\\mb\\config\\src\\stores\\"...
0x18000add4  lea     rcx, [rbp+210h+var_288]; this
0x18000add8  call    ?WriteToLog@CErrorInterceptor@@QEAAJPEBGKK@Z; CErrorInterceptor::WriteToLog(ushort const *,ulong,ulong)
0x18000addd  nop
0x18000adde  lea     rcx, [rbp+210h+var_288]; this
0x18000ade2  call    ??1CErrorInterceptor@@QEAA@XZ; CErrorInterceptor::~CErrorInterceptor(void)
0x18000ade7  jmp     short loc_18000ADEC
0x18000ade9  mov     r15d, eax
0x18000adec  lea     rcx, [rbp+210h+var_278]; void *
0x18000adf0  call    ??1?$TSmartPointerArray@_N@@QEAA@XZ; TSmartPointerArray<bool>::~TSmartPointerArray<bool>(void)
0x18000adf5  mov     eax, r15d
0x18000adf8  jmp     loc_18000BAA9
0x18000adfd  jmp     loc_18000B890
0x18000ae02  xor     esi, esi
0x18000ae04  mov     [rbp+210h+var_290], esi
0x18000ae07  lea     r9, [rbp+210h+var_290]; unsigned int *
0x18000ae0b  mov     r8d, r13d; unsigned int
0x18000ae0e  mov     rdx, rdi; unsigned __int16 *
0x18000ae11  call    ?NumberFromString@TMetabase_XMLtable@@AEBA_NPEBGKAEAK@Z; TMetabase_XMLtable::NumberFromString(ushort const *,ulong,ulong &)
0x18000ae16  test    al, al
0x18000ae18  jnz     loc_18000AFF7
0x18000ae1e  mov     eax, 0FFh
0x18000ae23  cmp     r13d, eax
0x18000ae26  cmovnb  r13d, eax
0x18000ae2a  mov     ebx, r13d
0x18000ae2d  mov     r9d, r13d; MaxCount
0x18000ae30  mov     r8, rdi; Source
0x18000ae33  lea     edx, [rax+1]; SizeInWords
0x18000ae36  lea     rcx, [rbp+210h+Destination]; Destination
0x18000ae3a  call    cs:__imp_wcsncpy_s
0x18000ae40  add     rbx, rbx
0x18000ae43  cmp     rbx, 200h
0x18000ae4a  jnb     loc_18000BAD8
0x18000ae50  mov     [rbp+rbx+210h+Destination], si
0x18000ae55  mov     eax, [r14+660h]
0x18000ae5c  cmp     eax, 32h ; '2'
0x18000ae5f  jnb     loc_18000AF2C
0x18000ae65  inc     eax
0x18000ae67  mov     [r14+660h], eax
0x18000ae6e  mov     [rbp+210h+var_270], rsi
0x18000ae72  lea     rcx, [r14+28h]
0x18000ae76  lea     rdx, [r14+708h]
0x18000ae7d  or      r12d, 0FFFFFFFFh
0x18000ae81  mov     [rsp+340h+var_2A0], r12d
0x18000ae89  mov     eax, [r14+6A8h]
0x18000ae90  mov     [rsp+340h+var_2A8], eax
0x18000ae97  mov     [rsp+340h+var_2C0], 2
0x18000aea2  mov     [rsp+340h+var_2C8], rcx
0x18000aea7  mov     [rsp+340h+var_2D0], r12d
0x18000aeac  mov     [rsp+340h+var_2D8], r12d
0x18000aeb1  mov     [rsp+340h+var_2E0], r15d
0x18000aeb6  lea     rax, aMbproperty; "MBProperty"
0x18000aebd  mov     [rsp+340h+var_2E8], rax
0x18000aec2  mov     [rsp+340h+var_2F0], 0Eh
0x18000aeca  mov     [rsp+340h+var_2F8], rsi
0x18000aecf  mov     [rsp+340h+var_300], rsi
0x18000aed4  mov     [rsp+340h+var_308], rsi
0x18000aed9  lea     rax, [rbp+210h+Destination]
0x18000aedd  mov     [rsp+340h+var_310], rax
0x18000aee2  mov     dword ptr [rsp+340h+var_318], 0C00210EAh
0x18000aeea  mov     dword ptr [rsp+340h+var_320], 2
0x18000aef2  mov     r9d, 80210523h
0x18000aef8  mov     r8, [r14+6B0h]
0x18000aeff  lea     rcx, [rbp+210h+var_278]
0x18000af03  call    ?Init@CErrorInterceptor@@AEAAXPEAPEAUISimpleTableWrite2@@PEAUIAdvancedTableDispenser@@JKKPEBG222K2W4eDETAILEDERRORS_OperationType@@KK2W4eDETAILEDERRORS_Type@@PEAEKKK@Z; CErrorInterceptor::Init(ISimpleTableWrite2 * *,IAdvancedTableDispenser *,long,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,eDETAILEDERRORS_OperationType,ulong,ulong,ushort const *,eDETAILEDERRORS_Type,uchar *,ulong,ulong,ulong)
0x18000af08  nop
0x18000af09  mov     r9d, [r14+67Ch]; unsigned int
0x18000af10  mov     r8d, 219h; unsigned int
0x18000af16  lea     rdx, aInetsrvIisMbCo_4; "inetsrv\\iis\\mb\\config\\src\\stores\\"...
0x18000af1d  lea     rcx, [rbp+210h+var_278]; this
0x18000af21  call    ?WriteToLog@CErrorInterceptor@@QEAAJPEBGKK@Z; CErrorInterceptor::WriteToLog(ushort const *,ulong,ulong)
0x18000af26  nop
0x18000af27  jmp     loc_18000BA8C
0x18000af2c  jnz     loc_18000ADF5
0x18000af32  mov     dword ptr [r14+660h], 33h ; '3'
  ... truncated ...
```
