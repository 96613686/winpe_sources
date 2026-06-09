# PropVariantToWinRTPropertyValue

- ea: `0x180028760`
- end: `0x18002999c`
- name: `PropVariantToWinRTPropertyValue`
- size: `4668`
- prototype: `HRESULT __stdcall(const PROPVARIANT *const propvar, const IID *const riid, void **ppv)`
- caller_count: `1`
- callee_count: `31`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180028760`

## callees

- `0x180003f94`
- `0x18001bff8`
- `0x180023708`
- `0x180028760`
- `0x1800299a4`
- `0x18002a68c`
- `0x18002a7d4`
- `0x18002ab10`
- `0x18002d370`
- `0x180048760`
- `0x18004d488`
- `0x18005abac`
- `0x18005cdd8`
- `0x18005d2a0`
- `0x180064258`
- `0x18006af24`
- `0x18006b2fc`
- `0x18006ed20`
- `0x1800899c0`
- `0x180089b24`
- `0x180089c88`
- `0x180089de8`
- `0x180089f4c`
- `0x18008a0b0`
- `0x18008a1f8`
- `0x18008a35c`
- `0x18008a4c0`
- `0x18008a624`
- `0x18008a780`
- `0x18008c444`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800289e7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800290bc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800290dd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800289e7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800290bc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800290dd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180028ff2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180028ff2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028bcb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028bcb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800287bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180028883`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800287bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180028883`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028bb0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800297d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028bb0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800297d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180028b90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180029099`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180028b90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180029099`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800287da`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800287da`

## pseudocode

```c
HRESULT __stdcall PropVariantToWinRTPropertyValue(const PROPVARIANT *const propvar, const IID *const riid, void **ppv)
{
  void **v3; // rbx
  const IID *v4; // r14
  HRESULT v6; // eax
  const WCHAR *v7; // rdi
  unsigned int v8; // edx
  int v9; // ebx
  unsigned int v10; // edx
  unsigned int v11; // edx
  const WCHAR *v12; // r14
  __int64 v13; // r15
  unsigned __int64 v14; // rsi
  unsigned int v15; // eax
  UINT32 v16; // edx
  HRESULT v17; // eax
  PWSTR *v18; // r15
  struct IInspectable *v19; // rsi
  int v20; // r12d
  WCHAR *v21; // r14
  PWSTR v22; // rcx
  int v23; // eax
  __int64 v24; // rcx
  __int64 v25; // rcx
  const WCHAR *v26; // rcx
  unsigned int v28; // edx
  unsigned int v29; // edx
  unsigned int v30; // edx
  __int64 v31; // rax
  void *v32; // rcx
  __int64 v33; // r8
  __int64 v34; // r9
  __int64 v35; // r14
  HSTRING *v36; // rbx
  PWSTR *v37; // r12
  unsigned int v38; // r15d
  const WCHAR *v39; // rcx
  __int64 v40; // rdx
  unsigned int i; // esi
  unsigned int v42; // edx
  unsigned int v43; // edx
  unsigned int v44; // edx
  unsigned int v45; // edx
  unsigned int v46; // edx
  __int64 v47; // rax
  __int64 v48; // rax
  unsigned __int64 v49; // rdx
  __int64 v50; // rax
  unsigned int (__fastcall ***v51)(_QWORD, GUID *, struct IInspectable **); // rcx
  unsigned int (__fastcall **v52)(_QWORD, GUID *, struct IInspectable **); // rax
  unsigned int v53; // ebx
  __int16 v54; // ax
  bool v55; // al
  __int64 v56; // rax
  __int64 v57; // rax
  __int64 v58; // rax
  __int64 *v59; // rdx
  __int64 v60; // rax
  __int64 v61; // rax
  __int64 v62; // rax
  unsigned int v63; // edx
  unsigned int v64; // edx
  unsigned int v65; // edx
  __int64 (__fastcall *v66)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 v67; // rax
  HSTRING_HEADER *p_hstringHeader; // rcx
  __int64 v69; // r14
  HSTRING *v70; // rbx
  void *v71; // rcx
  __int64 v72; // r8
  PWSTR *v73; // r12
  __int64 v74; // r9
  unsigned int v75; // r15d
  const WCHAR *v76; // rcx
  __int64 v77; // rdx
  __int64 v78; // rax
  __int64 v79; // rax
  __int64 v80; // rax
  __int64 v81; // rax
  __int64 *v82; // rdx
  unsigned int v83; // edx
  unsigned int v84; // edx
  unsigned int v85; // edx
  unsigned int v86; // edx
  unsigned int v87; // edx
  unsigned int v88; // edx
  unsigned int v89; // edx
  unsigned int v90; // edx
  __int64 v91; // rax
  __int64 v92; // rax
  __int64 v93; // rax
  unsigned int v94; // edx
  unsigned int v95; // edx
  unsigned int v96; // edx
  unsigned int v97; // edx
  unsigned int v98; // edx
  unsigned int v99; // edx
  unsigned int v100; // edx
  unsigned int v101; // edx
  __int64 v102; // rax
  __int64 v103; // r14
  unsigned int v104; // ebx
  void **Reserved1; // r15
  __int64 v106; // rax
  __int64 v107; // rax
  __int64 v108; // rax
  __int64 v109; // rax
  __int64 v110; // rax
  ULONG v111; // ebx
  void *v112; // rcx
  PWSTR *v113; // r10
  __int64 v114; // rax
  __int64 v115; // rax
  __int64 v116; // rax
  unsigned int j; // esi
  __int64 v118; // rax
  __int64 v119; // rax
  __int64 v120; // rax
  __int64 v121; // rax
  PWSTR *pprgsz; // [rsp+30h] [rbp-79h] BYREF
  struct IInspectable *v123; // [rsp+38h] [rbp-71h] BYREF
  PWSTR *v124; // [rsp+40h] [rbp-69h] BYREF
  void **v125; // [rsp+48h] [rbp-61h]
  const IID *v126; // [rsp+50h] [rbp-59h]
  ULONG pcElem[2]; // [rsp+58h] [rbp-51h] BYREF
  const WCHAR *v128; // [rsp+60h] [rbp-49h] BYREF
  __int64 v129; // [rsp+68h] [rbp-41h] BYREF
  int v130; // [rsp+70h] [rbp-39h]
  PROPVARIANT pvar[4]; // [rsp+80h] [rbp-29h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-9h] BYREF
  HSTRING string; // [rsp+B8h] [rbp+Fh] BYREF

  v3 = ppv;
  v125 = ppv;
  v4 = riid;
  v126 = riid;
  *ppv = 0;
  v128 = 0;
  string = 0;
  v6 = WindowsCreateStringReference(L"Windows.Foundation.PropertyValue", 0x20u, &hstringHeader, &string);
  if ( v6 < 0 )
  {
    RaiseException(v6, 1u, 0, 0);
    __debugbreak();
  }
  LODWORD(v7) = RoGetActivationFactory(string, &GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858, &v128);
  if ( (int)v7 >= 0 )
  {
    v129 = 0;
    v130 = 0;
    v8 = *(unsigned __int16 *)propvar;
    if ( v8 <= 0x40 )
    {
      if ( v8 == 64 )
      {
        v48 = HIDWORD(*((_QWORD *)propvar + 1));
        if ( (int)v48 < 0 )
        {
          LODWORD(v7) = -2147483637;
        }
        else
        {
          v49 = *((unsigned int *)propvar + 2) | (unsigned __int64)(v48 << 32);
          v50 = *(_QWORD *)v128;
          pprgsz = (PWSTR *)&v129;
          v123 = 0;
          LODWORD(v7) = (*(__int64 (__fastcall **)(const WCHAR *, unsigned __int64, struct IInspectable **))(v50 + 168))(
                          v128,
                          v49,
                          &v123);
          RoVariant::Attach((RoVariant *)&v129, v123);
        }
        goto LABEL_20;
      }
      if ( v8 <= 0xD )
      {
        if ( v8 == 13 )
        {
          v51 = (unsigned int (__fastcall ***)(_QWORD, GUID *, struct IInspectable **))*((_QWORD *)propvar + 1);
          v52 = *v51;
          pprgsz = (PWSTR *)&v129;
          v123 = 0;
          v53 = (*v52)(v51, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, &v123) >> 31;
          RoVariant::Attach((RoVariant *)&v129, v123);
          if ( (unsigned __int8)v53 != 1 )
          {
LABEL_22:
            v3 = v125;
            goto LABEL_23;
          }
          goto LABEL_95;
        }
        if ( v8 > 5 )
        {
          v9 = 7;
          v10 = v8 - 7;
          if ( !v10 )
          {
            *(_QWORD *)pcElem = 0;
            LODWORD(v7) = ConvertTimeHelper((FILETIME *)propvar + 1);
            if ( (int)v7 < 0 )
              goto LABEL_30;
            v61 = *(_QWORD *)v128;
            pprgsz = (PWSTR *)&v129;
            v123 = 0;
            LODWORD(v7) = (*(__int64 (__fastcall **)(const WCHAR *, _QWORD, struct IInspectable **))(v61 + 168))(
                            v128,
                            *(_QWORD *)pcElem,
                            &v123);
            RoVariant::Attach((RoVariant *)&v129, v123);
            goto LABEL_20;
          }
          v11 = v10 - 1;
          if ( !v11 )
            goto LABEL_10;
          if ( v11 == 3 )
          {
            v54 = *((_WORD *)propvar + 4);
            if ( v54 == -1 )
            {
              v58 = *(_QWORD *)v128;
              v59 = &v129;
              pprgsz = (PWSTR *)&v129;
              v123 = 0;
              LOBYTE(v59) = 1;
              LODWORD(v7) = (*(__int64 (__fastcall **)(const WCHAR *, __int64 *, struct IInspectable **))(v58 + 136))(
                              v128,
                              v59,
                              &v123);
              RoVariant::Attach((RoVariant *)&v129, v123);
            }
            else if ( v54 )
            {
              LODWORD(v7) = -2147024809;
            }
            else
            {
              v60 = *(_QWORD *)v128;
              pprgsz = (PWSTR *)&v129;
              v123 = 0;
              LODWORD(v7) = (*(__int64 (__fastcall **)(const WCHAR *, _QWORD, struct IInspectable **))(v60 + 136))(
                              v128,
                              0,
                              &v123);
              RoVariant::Attach((RoVariant *)&v129, v123);
            }
            goto LABEL_20;
          }
LABEL_95:
          v55 = IsAgile(*((struct IUnknown **)propvar + 1));
          v123 = 0;
          pprgsz = (PWSTR *)&v129;
          if ( v55 )
            LODWORD(v7) = Microsoft::WRL::Details::MakeAndInitialize<AgileWinRTPropVariantWrapper,IInspectable,tagPROPVARIANT const &>(
                            &v123,
                            propvar);
          else
            LODWORD(v7) = Microsoft::WRL::Details::MakeAndInitialize<WinRTPropVariantWrapper,IInspectable,tagPROPVARIANT const &>(
                            &v123,
                            propvar);
          RoVariant::Attach((RoVariant *)pprgsz, v123);
          goto LABEL_20;
        }
        if ( v8 == 5 )
        {
          v57 = *(_QWORD *)v128;
          pprgsz = (PWSTR *)&v129;
          v123 = 0;
          LODWORD(v7) = (*(__int64 (__fastcall **)(const WCHAR *, __int64 *, struct IInspectable **))(v57 + 120))(
                          v128,
                          &v129,
                          &v123);
          RoVariant::Attach((RoVariant *)&v129, v123);
          goto LABEL_20;
        }
        if ( !*(_WORD *)propvar || (v28 = v8 - 1) == 0 )
        {
LABEL_23:
          *(_QWORD *)pcElem = 0;
          Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(pcElem);
          LODWORD(v7) = v130;
          if ( v130 >= 0 )
          {
            v24 = v129;
            *(_QWORD *)pcElem = v129;
            if ( !v129
              || ((*(void (__fastcall **)(__int64))(*(_QWORD *)v129 + 8LL))(v129), (v24 = *(_QWORD *)pcElem) == 0) )
            {
              LODWORD(v7) = 0;
LABEL_28:
              if ( v24 )
              {
                *(_QWORD *)pcElem = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
              }
LABEL_30:
              v25 = v129;
              if ( !v129 )
                goto LABEL_31;
              goto LABEL_36;
            }
            LODWORD(v7) = (***(__int64 (__fastcall ****)(_QWORD, const IID *, void **))pcElem)(
                            *(_QWORD *)pcElem,
                            v4,
                            v3);
          }
          v24 = *(_QWORD *)pcElem;
          goto LABEL_28;
        }
        v29 = v28 - 1;
        if ( !v29 )
        {
          v56 = *(_QWORD *)v128;
          pprgsz = (PWSTR *)&v129;
          v123 = 0;
          LODWORD(v7) = (*(__int64 (__fastcall **)(const WCHAR *, _QWORD, struct IInspectable **))(v56 + 64))(
                          v128,
                          *((unsigned __int16 *)propvar + 4),
                          &v123);
          RoVariant::Attach((RoVariant *)&v129, v123);
          goto LABEL_20;
        }
        v30 = v29 - 1;
        if ( v30 )
        {
          if ( v30 != 1 )
            goto LABEL_95;
          v31 = *(_QWORD *)v128;
          pprgsz = (PWSTR *)&v129;
          v123 = 0;
          LODWORD(v7) = (*(__int64 (__fastcall **)(const WCHAR *, __int64 *, struct IInspectable **))(v31 + 112))(
                          v128,
                          &v129,
                          &v123);
          RoVariant::Attach((RoVariant *)&v129, v123);
LABEL_20:
          if ( (int)v7 < 0 )
            goto LABEL_30;
          v4 = v126;
          goto LABEL_22;
        }
        goto LABEL_128;
      }
      v42 = v8 - 17;
      if ( !v42 )
      {
        v81 = *(_QWORD *)v128;
        v82 = &v129;
        pprgsz = (PWSTR *)&v129;
        v123 = 0;
        LOBYTE(v82) = *((_BYTE *)propvar + 8);
        LODWORD(v7) = (*(__int64 (__fastcall **)(const WCHAR *, __int64 *, struct IInspectable **))(v81 + 56))(
                        v128,
                        v82,
                        &v123);
        RoVariant::Attach((RoVariant *)&v129, v123);
        goto LABEL_20;
      }
      v43 = v42 - 1;
      if ( !v43 )
      {
        v80 = *(_QWORD *)v128;
        pprgsz = (PWSTR *)&v129;
        v123 = 0;
        LODWORD(v7) = (*(__int64 (__fastcall **)(const WCHAR *, _QWORD, struct IInspectable **))(v80 + 72))(
                        v128,
                        *((unsigned __int16 *)propvar + 4),
                        &v123);
        RoVariant::Attach((RoVariant *)&v129, v123);
        goto LABEL_20;
      }
      v44 = v43 - 1;
      if ( !v44 )
        goto LABEL_105;
      v45 = v44 - 1;
      if ( !v45 )
      {
        v79 = *(_QWORD *)v128;
        pprgsz = (PWSTR *)&v129;
        v123 = 0;
        LODWORD(v7) = (*(__int64 (__fastcall **)(const WCHAR *, _QWORD, struct IInspectable **))(v79 + 96))(
                        v128,
                        *((_QWORD *)propvar + 1),
                        &v123);
        RoVariant::Attach((RoVariant *)&v129, v123);
        goto LABEL_20;
      }
      v46 = v45 - 1;
      if ( !v46 )
      {
        v47 = *(_QWORD *)v128;
        pprgsz = (PWSTR *)&v129;
        v123 = 0;
        LODWORD(v7) = (*(__int64 (__fastcall **)(const WCHAR *, _QWORD, struct IInspectable **))(v47 + 104))(
                        v128,
                        *((_QWORD *)propvar + 1),
                        &v123);
        RoVariant::Attach((RoVariant *)&v129, v123);
        goto LABEL_20;
      }
      v63 = v46 - 1;
      if ( !v63 )
      {
LABEL_128:
        v78 = *(_QWORD *)v128;
        pprgsz = (PWSTR *)&v129;
        v123 = 0;
        LODWORD(v7) = (*(__int64 (__fastcall **)(const WCHAR *, _QWORD, struct IInspectable **))(v78 + 80))(
                        v128,
                        *((unsigned int *)propvar + 2),
                        &v123);
        RoVariant::Attach((RoVariant *)&v129, v123);
        goto LABEL_20;
      }
      v64 = v63 - 1;
      if ( !v64 )
      {
LABEL_105:
        v62 = *(_QWORD *)v128;
        pprgsz = (PWSTR *)&v129;
        v123 = 0;
        LODWORD(v7) = (*(__int64 (__fastcall **)(const WCHAR *, _QWORD, struct IInspectable **))(v62 + 88))(
                        v128,
                        *((unsigned int *)propvar + 2),
                        &v123);
        RoVariant::Attach((RoVariant *)&v129, v123);
        goto LABEL_20;
      }
      v9 = 7;
      v65 = v64 - 7;
      if ( v65 )
      {
        if ( v65 == 1 )
        {
LABEL_10:
          v12 = v128;
          v13 = *(_QWORD *)v128;
          pprgsz = (PWSTR *)&v129;
          v123 = 0;
          string = 0;
          v7 = (const WCHAR *)*((_QWORD *)propvar + 1);
          v14 = -1;
          do
            ++v14;
          while ( v7[v14] );
          if ( v14 > 0xFFFFFFFF )
          {
            RaiseException(0x80070216, 1u, 0, 0);
LABEL_36:
            if ( ((v130 - 3) & 0xFFFFFFFB) == 0 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
            goto LABEL_31;
          }
          v15 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v14);
          v16 = v15 - 1;
          if ( (unsigned int)v14 < v15 )
            v16 = v14;
          v17 = WindowsCreateStringReference(v7, v16, &hstringHeader, &string);
          if ( v17 < 0 )
          {
            RaiseException(v17, 1u, 0, 0);
            __debugbreak();
          }
          LODWORD(v7) = (*(__int64 (__fastcall **)(const WCHAR *, HSTRING, struct IInspectable **))(v13 + 144))(
                          v12,
                          string,
                          &v123);
          string = 0;
          v18 = pprgsz;
          v19 = v123;
          if ( v123 )
          {
            pvar[0] = 0;
            v20 = ((__int64 (__fastcall *)(struct IInspectable *, GUID *, PROPVARIANT *))v123->lpVtbl->QueryInterface)(
                    v123,
                    &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62,
                    pvar);
            if ( v20 < 0 )
            {
              if ( v20 == -2147467262 )
              {
                v21 = (WCHAR *)v19;
                v9 = 3;
              }
              else
              {
                ((void (__fastcall *)(struct IInspectable *))v19->lpVtbl->Release)(v19);
                v21 = 0;
                v9 = v20;
              }
            }
            else
            {
              v21 = (WCHAR *)pvar[0];
              ((void (__fastcall *)(struct IInspectable *))v19->lpVtbl->Release)(v19);
            }
          }
          else
          {
            v21 = 0;
            v9 = 0;
          }
          v22 = *pprgsz;
          *pprgsz = v21;
          v23 = *((_DWORD *)v18 + 2);
          *((_DWORD *)v18 + 2) = v9;
          if ( v22 && ((v23 - 3) & 0xFFFFFFFB) == 0 )
            (*(void (__fastcall **)(PWSTR))(*(_QWORD *)v22 + 16LL))(v22);
          goto LABEL_20;
        }
        goto LABEL_95;
      }
      LOWORD(pvar[0]) = 0;
      LODWORD(v7) = CPropVariant::ChangeType(pvar, 0x1Fu, (const struct tagPROPVARIANT *)propvar);
      if ( (int)v7 >= 0 )
      {
        v7 = v128;
        v66 = *(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)v128 + 144LL);
        pprgsz = (PWSTR *)&v129;
        v123 = 0;
        v67 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &pvar[1]);
        LODWORD(v7) = v66(v7, *(_QWORD *)(v67 + 24), &v123);
        string = 0;
        RoVariant::Attach((RoVariant *)&v129, v123);
      }
      p_hstringHeader = (HSTRING_HEADER *)pvar;
LABEL_112:
      PropVariantClear(&p_hstringHeader->Reserved.Reserved1);
      goto LABEL_20;
    }
    if ( v8 <= 0x1017 )
    {
      if ( v8 == 4119 )
        goto LABEL_204;
      if ( v8 <= 0x1005 )
      {
        if ( v8 == 4101 )
          goto LABEL_173;
        v83 = v8 - 65;
        if ( !v83 )
        {
          v93 = *(_QWORD *)v128;
          pprgsz = (PWSTR *)&v129;
          v123 = 0;
          LODWORD(v7) = (*(__int64 (__fastcall **)(const WCHAR *, _QWORD, _QWORD, struct IInspectable **))(v93 + 208))(
                          v128,
                          *((unsigned int *)propvar + 2),
                          *((_QWORD *)propvar + 2),
                          &v123);
          RoVariant::Attach((RoVariant *)&v129, v123);
          goto LABEL_20;
        }
        v84 = v83 - 1;
        if ( !v84 )
          goto LABEL_95;
        v85 = v84 - 1;
        if ( !v85 )
          goto LABEL_95;
        v86 = v85 - 1;
        if ( !v86 )
          goto LABEL_95;
        v87 = v86 - 1;
        if ( !v87 )
          goto LABEL_95;
        v88 = v87 - 3;
        if ( !v88 )
        {
          v92 = *(_QWORD *)v128;
          pprgsz = (PWSTR *)&v129;
          v123 = 0;
          *(_OWORD *)pvar = *(_OWORD *)*((_QWORD *)propvar + 1);
          LODWORD(v7) = (*(__int64 (__fastcall **)(const WCHAR *, PROPVARIANT *, struct IInspectable **))(v92 + 160))(
                          v128,
                          pvar,
                          &v123);
          RoVariant::Attach((RoVariant *)&v129, v123);
          goto LABEL_20;
        }
        v89 = v88 - 4026;
        if ( v89 )
        {
          v90 = v89 - 1;
          if ( v90 )
          {
            if ( v90 != 1 )
              goto LABEL_95;
            goto LABEL_145;
          }
          goto LABEL_159;
        }
        goto LABEL_176;
      }
      v94 = v8 - 4104;
      if ( !v94 )
        goto LABEL_58;
      v95 = v94 - 3;
      if ( !v95 )
      {
LABEL_170:
        pcElem[0] = 0;
        v124 = 0;
        LODWORD(v7) = PropVariantToVectorAlloc<11,short,int>((PROPVARIANT *)propvar);
        if ( (int)v7 >= 0 )
        {
          v107 = *(_QWORD *)v128;
          pprgsz = (PWSTR *)&v129;
          v123 = 0;
          LODWORD(v7) = (*(__int64 (__fastcall **)(const WCHAR *, _QWORD, PWSTR *, struct IInspectable **))(v107 + 288))(
                          v128,
                          pcElem[0],
                          v124,
                          &v123);
          RoVariant::Attach((RoVariant *)&v129, v123);
        }
LABEL_181:
        CCoTaskMemPtr<HSTRING__ *>::~CCoTaskMemPtr<HSTRING__ *>(&v124);
        goto LABEL_20;
      }
      v96 = v95 - 1;
      if ( !v96 )
      {
        v103 = *((unsigned int *)propvar + 2);
        memset(&hstringHeader, 0, sizeof(hstringHeader));
        string = 0;
        LODWORD(v7) = CTSimpleArray<ATL::CComPtr<ParsedPropertyDescription>,4294967294,CTPolicyCoTaskMem<ATL::CComPtr<ParsedPropertyDescription>>,CSimpleArrayStandardCompareHelper<ATL::CComPtr<ParsedPropertyDescription>>,CSimpleArrayStandardMergeHelper<ATL::CComPtr<ParsedPropertyDescription>>>::_EnsureCapacity(
                        &hstringHeader,
                        (unsigned int)v103);
        if ( (int)v7 >= 0 )
        {
          *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = v103;
          v104 = 0;
          Reserved1 = (void **)hstringHeader.Reserved.Reserved1;
          while ( v104 < (unsigned int)v103 )
          {
            LODWORD(v7) = PropVariantToWinRTPropertyValue(
                            (const PROPVARIANT *const)(*((_QWORD *)propvar + 2) + 24LL * v104),
                            &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
                            &Reserved1[v104]);
            ++v104;
            if ( (int)v7 < 0 )
              goto LABEL_168;
          }
          v106 = *(_QWORD *)v128;
          pprgsz = (PWSTR *)&v129;
          v123 = 0;
          LODWORD(v7) = (*(__int64 (__fastcall **)(const WCHAR *, _QWORD, void **, struct IInspectable **))(v106 + 304))(
                          v128,
                          (unsigned int)v103,
                          Reserved1,
                          &v123);
          RoVariant::Attach((RoVariant *)&v129, v123);
        }
LABEL_168:
        CSimplePointerArray<IInspectable,CTContainer_PolicyRelease<IInspectable>,CSimpleArrayStandardCompareHelper<IInspectable *>>::~CSimplePointerArray<IInspectable,CTContainer_PolicyRelease<IInspectable>,CSimpleArrayStandardCompareHelper<IInspectable *>>(&hstringHeader);
        goto LABEL_20;
      }
      v97 = v96 - 5;
      if ( !v97 )
        goto LABEL_179;
      v98 = v97 - 1;
      if ( v98 )
      {
        v99 = v98 - 1;
        if ( !v99 )
          goto LABEL_204;
        v100 = v99 - 1;
        if ( v100 )
        {
          v101 = v100 - 1;
          if ( v101 )
          {
            if ( v101 != 1 )
              goto LABEL_95;
            goto LABEL_159;
          }
LABEL_198:
          pcElem[0] = 0;
          pvar[0] = 0;
          LODWORD(v7) = PropVariantToVectorAlloc<21,unsigned __int64,unsigned __int64>((PROPVARIANT *)propvar);
          if ( (int)v7 >= 0 )
          {
            v118 = *(_QWORD *)v128;
            pprgsz = (PWSTR *)&v129;
            v123 = 0;
            LODWORD(v7) = (*(__int64 (__fastcall **)(const WCHAR *, _QWORD, PROPVARIANT, struct IInspectable **))(v118 + 256))(
                            v128,
                            pcElem[0],
                            pvar[0],
                            &v123);
            RoVariant::Attach((RoVariant *)&v129, v123);
          }
          goto LABEL_209;
        }
LABEL_201:
        pcElem[0] = 0;
        pvar[0] = 0;
        LODWORD(v7) = PropVariantToVectorAlloc<20,__int64,__int64>((PROPVARIANT *)propvar);
        if ( (int)v7 >= 0 )
        {
          v119 = *(_QWORD *)v128;
          pprgsz = (PWSTR *)&v129;
          v123 = 0;
          LODWORD(v7) = (*(__int64 (__fastcall **)(const WCHAR *, _QWORD, PROPVARIANT, struct IInspectable **))(v119 + 248))(
                          v128,
                          pcElem[0],
                          pvar[0],
                          &v123);
          RoVariant::Attach((RoVariant *)&v129, v123);
        }
        goto LABEL_209;
      }
    }
    else
    {
      if ( (unsigned __int16)v8 <= 0x2011u )
      {
        if ( (_WORD)v8 != 8209 )
        {
          if ( v8 != 4126 )
          {
            if ( v8 == 4127 )
            {
LABEL_58:
              pcElem[0] = 0;
              pprgsz = 0;
              LODWORD(v7) = PropVariantToStringVectorAlloc(propvar, &pprgsz, pcElem);
              if ( (int)v7 < 0 )
                goto LABEL_30;
              v35 = pcElem[0];
              v36 = 0;
              pvar[0] = 0;
              v37 = pprgsz;
              if ( is_mul_ok(pcElem[0], 8u) )
              {
                LODWORD(v7) = CTCoAllocPolicy::Alloc(v32, 1u, 8LL * pcElem[0], pvar);
                v34 = 0;
                v36 = (HSTRING *)pvar[0];
                if ( (int)v7 >= 0 )
                {
                  v38 = 0;
                  while ( v38 < (unsigned int)v35 )
                  {
                    v39 = v37[v38];
                    v40 = -1;
                    do
                      ++v40;
                    while ( v39[v40] );
                    LODWORD(v7) = WindowsCreateString(v39, v40, &v36[v38++]);
                    v34 = 0;
                    if ( (int)v7 < 0 )
                      goto LABEL_67;
                  }
                  v115 = *(_QWORD *)v128;
                  pprgsz = (PWSTR *)&v129;
                  v123 = 0;
                  LODWORD(v7) = (*(__int64 (__fastcall **)(const WCHAR *, _QWORD, HSTRING *, struct IInspectable **))(v115 + 296))(
                                  v128,
                                  (unsigned int)v35,
                                  v36,
                                  &v123);
                  RoVariant::Attach((RoVariant *)pprgsz, v123);
                  v34 = 0;
LABEL_67:
                  for ( i = 0; i < (unsigned int)v35; ++i )
                    WindowsDeleteString(v36[i]);
                }
              }
              else
              {
                LODWORD(v7) = -2147024362;
              }
              SHCoFreeArray<unsigned short>(v37, v35, v33, v34);
              CoTaskMemFree(v36);
              goto LABEL_20;
            }
            if ( v8 != 4160 )
            {
              if ( v8 != 8194 )
              {
                if ( v8 != 8195 )
                {
                  if ( v8 != 8196 )
                  {
                    if ( v8 != 8197 )
                    {
                      if ( v8 == 8200 )
                        goto LABEL_58;
                      if ( v8 != 8203 )
                        goto LABEL_95;
                      goto LABEL_170;
                    }
LABEL_173:
                    pcElem[0] = 0;
                    v124 = 0;
                    LODWORD(v7) = PropVariantToVectorAlloc<5,double,double>((PROPVARIANT *)propvar);
                    if ( (int)v7 >= 0 )
                    {
                      v108 = *(_QWORD *)v128;
                      pprgsz = (PWSTR *)&v129;
                      v123 = 0;
                      LODWORD(v7) = (*(__int64 (__fastcall **)(const WCHAR *, _QWORD, PWSTR *, struct IInspectable **))(v108 + 272))(
                                      v128,
                                      pcElem[0],
                                      v124,
                                      &v123);
                      RoVariant::Attach((RoVariant *)&v129, v123);
                    }
                    goto LABEL_181;
                  }
LABEL_145:
                  pcElem[0] = 0;
                  v124 = 0;
                  LODWORD(v7) = PropVariantToVectorAlloc<4,float,float>((PROPVARIANT *)propvar);
                  if ( (int)v7 >= 0 )
                  {
                    v91 = *(_QWORD *)v128;
                    pprgsz = (PWSTR *)&v129;
                    v123 = 0;
                    LODWORD(v7) = (*(__int64 (__fastcall **)(const WCHAR *, _QWORD, PWSTR *, struct IInspectable **))(v91 + 264))(
                                    v128,
                                    pcElem[0],
                                    v124,
                                    &v123);
                    RoVariant::Attach((RoVariant *)&v129, v123);
                  }
                  goto LABEL_181;
                }
                goto LABEL_159;
              }
LABEL_176:
              pcElem[0] = 0;
              v124 = 0;
              LODWORD(v7) = PropVariantToVectorAlloc<2,short,short>((PROPVARIANT *)propvar);
              if ( (int)v7 >= 0 )
              {
                v109 = *(_QWORD *)v128;
                pprgsz = (PWSTR *)&v129;
                v123 = 0;
                LODWORD(v7) = (*(__int64 (__fastcall **)(const WCHAR *, _QWORD, PWSTR *, struct IInspectable **))(v109 + 216))(
                                v128,
                                pcElem[0],
                                v124,
                                &v123);
                RoVariant::Attach((RoVariant *)&v129, v123);
              }
              goto LABEL_181;
            }
LABEL_182:
            pcElem[0] = 0;
            pvar[0] = 0;
            LODWORD(v7) = PropVariantToVectorAlloc<64,_FILETIME,_FILETIME>((PROPVARIANT *)propvar);
            if ( (int)v7 >= 0 )
            {
              v124 = 0;
              pprgsz = 0;
              v111 = pcElem[0];
              LODWORD(v7) = ULongLongMult(pcElem[0], 8u, (unsigned __int64 *)&pprgsz);
              if ( (int)v7 >= 0 )
              {
                LODWORD(v7) = CTCoAllocPolicy::Alloc(v112, 1u, (unsigned __int64)pprgsz, (void **)&v124);
                v113 = v124;
              }
              if ( (int)v7 >= 0 )
              {
                v114 = *(_QWORD *)v128;
                pprgsz = (PWSTR *)&v129;
                v123 = 0;
                LODWORD(v7) = (*(__int64 (__fastcall **)(const WCHAR *, _QWORD, PWSTR *, struct IInspectable **))(v114 + 320))(
                                v128,
                                v111,
                                v113,
                                &v123);
                RoVariant::Attach((RoVariant *)pprgsz, v123);
              }
              CCoTaskMemPtr<HSTRING__ *>::~CCoTaskMemPtr<HSTRING__ *>(&v124);
            }
            CCoTaskMemPtr<HSTRING__ *>::~CCoTaskMemPtr<HSTRING__ *>(pvar);
            goto LABEL_20;
          }
          goto LABEL_190;
        }
LABEL_179:
        pcElem[0] = 0;
        v124 = 0;
        LODWORD(v7) = PropVariantToVectorAlloc<17,unsigned char,unsigned char>((PROPVARIANT *)propvar);
        if ( (int)v7 >= 0 )
        {
          v110 = *(_QWORD *)v128;
          pprgsz = (PWSTR *)&v129;
          v123 = 0;
          LODWORD(v7) = (*(__int64 (__fastcall **)(const WCHAR *, _QWORD, PWSTR *, struct IInspectable **))(v110 + 208))(
                          v128,
                          pcElem[0],
                          v124,
                          &v123);
          RoVariant::Attach((RoVariant *)&v129, v123);
        }
        goto LABEL_181;
      }
      if ( v8 != 8210 )
      {
        if ( v8 == 8211 )
          goto LABEL_204;
        if ( v8 != 8212 )
        {
          if ( v8 != 8213 )
          {
            if ( v8 != 8214 )
            {
              if ( v8 != 8215 )
              {
                if ( v8 != 8222 )
                {
                  if ( v8 == 8223 )
                    goto LABEL_58;
                  if ( v8 != 8256 )
                    goto LABEL_95;
                  goto LABEL_182;
                }
LABEL_190:
                LOWORD(hstringHeader.Reserved.Reserved1) = 0;
                LODWORD(v7) = CPropVariant::ChangeType(
                                &hstringHeader.Reserved.Reserved1,
                                v8 & 0x3000 | 0x1F,
                                (const struct tagPROPVARIANT *)propvar);
                if ( (int)v7 >= 0 )
                {
                  pcElem[0] = 0;
                  v124 = 0;
                  LODWORD(v7) = PropVariantToStringVectorAlloc(&hstringHeader.Reserved.Reserved1, &v124, pcElem);
                  if ( (int)v7 >= 0 )
                  {
                    v69 = pcElem[0];
                    v70 = 0;
                    pvar[0] = 0;
                    pprgsz = 0;
                    LODWORD(v7) = ULongLongMult(pcElem[0], 8u, (unsigned __int64 *)&pprgsz);
                    if ( (int)v7 >= 0 )
                    {
                      LODWORD(v7) = CTCoAllocPolicy::Alloc(v71, 1u, (unsigned __int64)pprgsz, pvar);
                      v70 = (HSTRING *)pvar[0];
                    }
                    v73 = v124;
                    v74 = 0;
                    if ( (int)v7 >= 0 )
                    {
                      v75 = 0;
                      while ( v75 < (unsigned int)v69 )
                      {
                        v76 = v73[v75];
                        v77 = -1;
                        do
                          ++v77;
                        while ( v76[v77] );
                        LODWORD(v7) = WindowsCreateString(v76, v77, &v70[v75++]);
                        v74 = 0;
                        if ( (int)v7 < 0 )
                          goto LABEL_194;
                      }
                      v116 = *(_QWORD *)v128;
                      pprgsz = (PWSTR *)&v129;
                      v123 = 0;
                      LODWORD(v7) = (*(__int64 (__fastcall **)(const WCHAR *, _QWORD, HSTRING *, struct IInspectable **))(v116 + 296))(
                                      v128,
                                      (unsigned int)v69,
                                      v70,
                                      &v123);
                      RoVariant::Attach((RoVariant *)pprgsz, v123);
                      v74 = 0;
LABEL_194:
                      for ( j = 0; j < (unsigned int)v69; ++j )
                        WindowsDeleteString(v70[j]);
                    }
                    SHCoFreeArray<unsigned short>(v73, v69, v72, v74);
                    CCoTaskMemPtr<HSTRING__ *>::~CCoTaskMemPtr<HSTRING__ *>(pvar);
                  }
                }
                p_hstringHeader = &hstringHeader;
                goto LABEL_112;
              }
LABEL_204:
              pcElem[0] = 0;
              pvar[0] = 0;
              LODWORD(v7) = PropVariantToVectorAlloc<19,unsigned long,unsigned long>((PROPVARIANT *)propvar);
              if ( (int)v7 >= 0 )
              {
                v120 = *(_QWORD *)v128;
                pprgsz = (PWSTR *)&v129;
                v123 = 0;
                LODWORD(v7) = (*(__int64 (__fastcall **)(const WCHAR *, _QWORD, PROPVARIANT, struct IInspectable **))(v120 + 240))(
                                v128,
                                pcElem[0],
                                pvar[0],
                                &v123);
                RoVariant::Attach((RoVariant *)&v129, v123);
              }
              goto LABEL_209;
            }
LABEL_159:
            pcElem[0] = 0;
            pvar[0] = 0;
            LODWORD(v7) = PropVariantToVectorAlloc<3,long,long>((PROPVARIANT *)propvar);
            if ( (int)v7 >= 0 )
            {
              v102 = *(_QWORD *)v128;
              pprgsz = (PWSTR *)&v129;
              v123 = 0;
              LODWORD(v7) = (*(__int64 (__fastcall **)(const WCHAR *, _QWORD, PROPVARIANT, struct IInspectable **))(v102 + 232))(
                              v128,
                              pcElem[0],
                              pvar[0],
                              &v123);
              RoVariant::Attach((RoVariant *)&v129, v123);
            }
LABEL_209:
            CCoTaskMemPtr<HSTRING__ *>::~CCoTaskMemPtr<HSTRING__ *>(pvar);
            goto LABEL_20;
          }
          goto LABEL_198;
        }
        goto LABEL_201;
      }
    }
    pcElem[0] = 0;
    pvar[0] = 0;
    LODWORD(v7) = PropVariantToVectorAlloc<18,unsigned short,unsigned short>((PROPVARIANT *)propvar);
    if ( (int)v7 >= 0 )
    {
      v121 = *(_QWORD *)v128;
      pprgsz = (PWSTR *)&v129;
      v123 = 0;
      LODWORD(v7) = (*(__int64 (__fastcall **)(const WCHAR *, _QWORD, PROPVARIANT, struct IInspectable **))(v121 + 224))(
                      v128,
                      pcElem[0],
                      pvar[0],
                      &v123);
      RoVariant::Attach((RoVariant *)&v129, v123);
    }
    goto LABEL_209;
  }
LABEL_31:
  v26 = v128;
  if ( v128 )
  {
    v128 = 0;
    (*(void (__fastcall **)(const WCHAR *))(*(_QWORD *)v26 + 16LL))(v26);
  }
  return (int)v7;
}

```

## disassembly

```asm
0x180028760  mov     [rsp-8+arg_18], rbx
0x180028765  push    rbp
0x180028766  push    rsi
0x180028767  push    rdi
0x180028768  push    r12
0x18002876a  push    r13
0x18002876c  push    r14
0x18002876e  push    r15
0x180028770  lea     rbp, [rsp-27h]
0x180028775  sub     rsp, 0D0h
0x18002877c  mov     rax, cs:__security_cookie
0x180028783  xor     rax, rsp
0x180028786  mov     [rbp+57h+var_40], rax
0x18002878a  mov     rbx, r8
0x18002878d  mov     [rbp+57h+var_B8], rbx
0x180028791  mov     r14, rdx
0x180028794  mov     [rbp+57h+var_B0], rdx
0x180028798  mov     rsi, rcx
0x18002879b  xor     r12d, r12d
0x18002879e  mov     [r8], r12
0x1800287a1  mov     [rbp+57h+var_A0], r12
0x1800287a5  mov     [rbp+57h+string], r12
0x1800287a9  lea     r9, [rbp+57h+string]; string
0x1800287ad  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800287b1  lea     edx, [r12+20h]; length
0x1800287b6  lea     rcx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x1800287bd  call    cs:__imp_WindowsCreateStringReference
0x1800287c3  test    eax, eax
0x1800287c5  js      loc_1800290B0
0x1800287cb  lea     r8, [rbp+57h+var_A0]
0x1800287cf  lea     rdx, _GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858
0x1800287d6  mov     rcx, [rbp+57h+string]
0x1800287da  call    cs:__imp_RoGetActivationFactory
0x1800287e0  mov     edi, eax
0x1800287e2  test    eax, eax
0x1800287e4  js      loc_180028990
0x1800287ea  mov     [rbp+57h+var_98], r12
0x1800287ee  mov     [rbp+57h+var_90], r12d
0x1800287f2  movzx   edx, word ptr [rsi]
0x1800287f5  cmp     edx, 40h ; '@'
0x1800287f8  ja      loc_180028A94
0x1800287fe  jz      loc_180028C3F
0x180028804  cmp     edx, 0Dh
0x180028807  ja      loc_180028BD9
0x18002880d  jz      loc_180028C94
0x180028813  cmp     edx, 5
0x180028816  jbe     loc_180028A28
0x18002881c  lea     ebx, [r12+7]
0x180028821  sub     edx, ebx
0x180028823  jz      loc_180028EBE
0x180028829  sub     edx, 1
0x18002882c  jnz     loc_180028CDB
0x180028832  mov     r14, [rbp+57h+var_A0]
0x180028836  mov     r15, [r14]
0x180028839  lea     rax, [rbp+57h+var_98]
0x18002883d  mov     [rbp+57h+pprgsz], rax
0x180028841  mov     [rbp+57h+var_C8], r12
0x180028845  mov     [rbp+57h+string], r12
0x180028849  mov     rdi, [rsi+8]
0x18002884d  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180028851  inc     rsi
0x180028854  cmp     [rdi+rsi*2], r12w
0x180028859  jnz     short loc_180028851
0x18002885b  mov     eax, 0FFFFFFFFh
0x180028860  cmp     rsi, rax
0x180028863  ja      loc_1800289D8
0x180028869  mov     ecx, esi; unsigned int
0x18002886b  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180028870  lea     edx, [rax-1]
0x180028873  cmp     esi, eax
0x180028875  cmovb   edx, esi; length
0x180028878  lea     r9, [rbp+57h+string]; string
0x18002887c  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180028880  mov     rcx, rdi; sourceString
0x180028883  call    cs:__imp_WindowsCreateStringReference
0x180028889  test    eax, eax
0x18002888b  js      loc_1800290D1
0x180028891  lea     r8, [rbp+57h+var_C8]
0x180028895  mov     rdx, [rbp+57h+string]
0x180028899  mov     rcx, r14
0x18002889c  mov     rax, [r15+90h]
0x1800288a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800288a8  mov     edi, eax
0x1800288aa  mov     [rbp+57h+string], r12
0x1800288ae  mov     r15, [rbp+57h+pprgsz]
0x1800288b2  mov     rsi, [rbp+57h+var_C8]
0x1800288b6  test    rsi, rsi
0x1800288b9  jz      loc_180028DCC
0x1800288bf  mov     [rbp+57h+pvar], r12
0x1800288c3  mov     rax, [rsi]
0x1800288c6  lea     r8, [rbp+57h+pvar]
0x1800288ca  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x1800288d1  mov     rcx, rsi
0x1800288d4  mov     rax, [rax]
0x1800288d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800288dc  mov     r12d, eax
0x1800288df  test    eax, eax
0x1800288e1  js      loc_180028D11
0x1800288e7  mov     r14, [rbp+57h+pvar]
0x1800288eb  mov     rax, [rsi]
0x1800288ee  mov     rcx, rsi
0x1800288f1  mov     rax, [rax+10h]
0x1800288f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800288fa  xor     r12d, r12d
0x1800288fd  mov     rcx, [r15]
0x180028900  mov     [r15], r14
0x180028903  mov     eax, [r15+8]
0x180028907  mov     [r15+8], ebx
0x18002890b  test    rcx, rcx
0x18002890e  jnz     loc_180028A09
0x180028914  test    edi, edi
0x180028916  js      short loc_180028987
0x180028918  mov     r14, [rbp+57h+var_B0]
0x18002891c  mov     rbx, [rbp+57h+var_B8]
0x180028920  mov     qword ptr [rbp+57h+pcElem], r12
0x180028924  lea     rcx, [rbp+57h+pcElem]
0x180028928  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18002892d  mov     edi, [rbp+57h+var_90]
0x180028930  test    edi, edi
0x180028932  js      short loc_18002896D
0x180028934  mov     rcx, [rbp+57h+var_98]
0x180028938  mov     qword ptr [rbp+57h+pcElem], rcx
0x18002893c  test    rcx, rcx
0x18002893f  jz      loc_1800289D3
0x180028945  mov     rax, [rcx]
0x180028948  mov     rax, [rax+8]
0x18002894c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028951  mov     rcx, qword ptr [rbp+57h+pcElem]
0x180028955  test    rcx, rcx
0x180028958  jz      short loc_1800289D3
0x18002895a  mov     rax, [rcx]
0x18002895d  mov     r8, rbx
0x180028960  mov     rdx, r14
0x180028963  mov     rax, [rax]
0x180028966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002896b  mov     edi, eax
0x18002896d  mov     rcx, qword ptr [rbp+57h+pcElem]
0x180028971  test    rcx, rcx
0x180028974  jz      short loc_180028987
0x180028976  mov     qword ptr [rbp+57h+pcElem], r12
0x18002897a  mov     rax, [rcx]
0x18002897d  mov     rax, [rax+10h]
0x180028981  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028986  nop
0x180028987  mov     rcx, [rbp+57h+var_98]
0x18002898b  test    rcx, rcx
0x18002898e  jnz     short loc_1800289EE
0x180028990  mov     rcx, [rbp+57h+var_A0]
0x180028994  test    rcx, rcx
0x180028997  jz      short loc_1800289AA
0x180028999  mov     [rbp+57h+var_A0], r12
0x18002899d  mov     rax, [rcx]
0x1800289a0  mov     rax, [rax+10h]
0x1800289a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800289a9  nop
0x1800289aa  mov     eax, edi
0x1800289ac  mov     rcx, [rbp+57h+var_40]
0x1800289b0  xor     rcx, rsp; StackCookie
0x1800289b3  call    __security_check_cookie
0x1800289b8  mov     rbx, [rsp+100h+arg_18]
0x1800289c0  add     rsp, 0D0h
0x1800289c7  pop     r15
0x1800289c9  pop     r14
0x1800289cb  pop     r13
0x1800289cd  pop     r12
0x1800289cf  pop     rdi
0x1800289d0  pop     rsi
0x1800289d1  pop     rbp
0x1800289d2  retn
0x1800289d3  mov     edi, r12d
0x1800289d6  jmp     short loc_180028971
0x1800289d8  xor     r9d, r9d; lpArguments
0x1800289db  xor     r8d, r8d; nNumberOfArguments
0x1800289de  lea     edx, [r9+1]; dwExceptionFlags
0x1800289e2  mov     ecx, 80070216h; dwExceptionCode
0x1800289e7  call    cs:__imp_RaiseException
0x1800289ed  nop
0x1800289ee  mov     eax, [rbp+57h+var_90]
0x1800289f1  add     eax, 0FFFFFFFDh
0x1800289f4  test    eax, 0FFFFFFFBh
0x1800289f9  jnz     short loc_180028990
0x1800289fb  mov     rax, [rcx]
0x1800289fe  mov     rax, [rax+10h]
0x180028a02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028a07  jmp     short loc_180028990
0x180028a09  add     eax, 0FFFFFFFDh
0x180028a0c  test    eax, 0FFFFFFFBh
0x180028a11  jnz     loc_180028914
0x180028a17  mov     rax, [rcx]
0x180028a1a  mov     rax, [rax+10h]
0x180028a1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028a23  jmp     loc_180028914
0x180028a28  jz      loc_180028E10
0x180028a2e  test    edx, edx
0x180028a30  jz      loc_180028920
0x180028a36  sub     edx, 1
0x180028a39  jz      loc_180028920
0x180028a3f  sub     edx, 1
0x180028a42  jz      loc_180028DD7
0x180028a48  sub     edx, 1
0x180028a4b  jz      loc_1800290E4
0x180028a51  cmp     edx, 1
0x180028a54  jnz     loc_180028D8E
0x180028a5a  mov     rcx, [rbp+57h+var_A0]
0x180028a5e  mov     rax, [rcx]
0x180028a61  lea     rdx, [rbp+57h+var_98]
0x180028a65  mov     [rbp+57h+pprgsz], rdx
0x180028a69  mov     [rbp+57h+var_C8], r12
0x180028a6d  lea     r8, [rbp+57h+var_C8]
0x180028a71  movss   xmm1, dword ptr [rsi+8]
0x180028a76  mov     rax, [rax+70h]
0x180028a7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028a7f  mov     edi, eax
0x180028a81  mov     rdx, [rbp+57h+var_C8]; struct IInspectable *
0x180028a85  mov     rcx, [rbp+57h+pprgsz]; this
0x180028a89  call    ?Attach@RoVariant@@QEAAXPEAUIInspectable@@@Z; RoVariant::Attach(IInspectable *)
0x180028a8e  nop
0x180028a8f  jmp     loc_180028914
0x180028a94  mov     eax, 1017h
0x180028a99  cmp     edx, eax
0x180028a9b  jbe     loc_1800291D0
0x180028aa1  mov     eax, 2011h
0x180028aa6  cmp     dx, ax
0x180028aa9  ja      loc_180028D38
0x180028aaf  jz      loc_1800295C3
0x180028ab5  mov     ecx, edx
0x180028ab7  sub     ecx, 101Eh
0x180028abd  jz      loc_180029742
0x180028ac3  sub     ecx, 1
0x180028ac6  jz      short loc_180028B05
0x180028ac8  sub     ecx, 21h ; '!'
0x180028acb  jz      loc_180029629
0x180028ad1  sub     ecx, 0FC2h
0x180028ad7  jz      loc_18002955D
0x180028add  sub     ecx, 1
0x180028ae0  jz      loc_18002937E
0x180028ae6  sub     ecx, 1
0x180028ae9  jz      loc_18002923D
0x180028aef  sub     ecx, 1
0x180028af2  jz      loc_1800294F7
0x180028af8  mov     ebx, 3
0x180028afd  sub     ecx, ebx
0x180028aff  jnz     loc_180029489
0x180028b05  mov     [rbp+57h+pcElem], r12d
0x180028b09  mov     [rbp+57h+pprgsz], r12
0x180028b0d  lea     r8, [rbp+57h+pcElem]; pcElem
0x180028b11  lea     rdx, [rbp+57h+pprgsz]; pprgsz
0x180028b15  mov     rcx, rsi; propvar
0x180028b18  call    PropVariantToStringVectorAlloc
0x180028b1d  mov     edi, eax
0x180028b1f  test    eax, eax
0x180028b21  js      loc_180028987
0x180028b27  mov     r14d, [rbp+57h+pcElem]
0x180028b2b  mov     rbx, r12
0x180028b2e  mov     [rbp+57h+pvar], rbx
0x180028b32  mov     eax, 8
0x180028b37  mul     r14
0x180028b3a  mov     r12, [rbp+57h+pprgsz]
0x180028b3e  test    rdx, rdx
0x180028b41  jz      short loc_180028B4A
0x180028b43  mov     edi, 80070216h
0x180028b48  jmp     short loc_180028BBD
0x180028b4a  lea     r9, [rbp+57h+pvar]; void **
0x180028b4e  mov     r8, rax; unsigned __int64
0x180028b51  mov     edx, 1; unsigned int
0x180028b56  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180028b5b  mov     edi, eax
0x180028b5d  xor     r9d, r9d
0x180028b60  mov     rbx, [rbp+57h+pvar]
0x180028b64  test    eax, eax
0x180028b66  js      short loc_180028BBD
0x180028b68  mov     r15d, r9d
0x180028b6b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180028b6f  cmp     r15d, r14d
0x180028b72  jnb     loc_180029701
0x180028b78  mov     eax, r15d
0x180028b7b  lea     r8, [rbx+rax*8]; string
0x180028b7f  mov     rcx, [r12+rax*8]; sourceString
0x180028b83  mov     rdx, rsi
0x180028b86  inc     rdx; length
0x180028b89  cmp     [rcx+rdx*2], r9w
0x180028b8e  jnz     short loc_180028B86
0x180028b90  call    cs:__imp_WindowsCreateString
0x180028b96  mov     edi, eax
0x180028b98  inc     r15d
0x180028b9b  xor     r9d, r9d
0x180028b9e  test    eax, eax
0x180028ba0  jns     short loc_180028B6F
0x180028ba2  mov     esi, r9d
0x180028ba5  test    r14d, r14d
0x180028ba8  jz      short loc_180028BBD
0x180028baa  mov     ecx, esi
0x180028bac  mov     rcx, [rbx+rcx*8]; string
0x180028bb0  call    cs:__imp_WindowsDeleteString
0x180028bb6  inc     esi
0x180028bb8  cmp     esi, r14d
0x180028bbb  jb      short loc_180028BAA
0x180028bbd  mov     rdx, r14
0x180028bc0  mov     rcx, r12
0x180028bc3  call    ??$SHCoFreeArray@G@@YAXPEAPEAG_K@Z; SHCoFreeArray<ushort>(ushort * *,unsigned __int64)
  ... truncated ...
```
