# FwSetupICSPortModify(IWbemServices *,ushort * const,WELL_KNOWN_PORT_ const *,int)

- ea: `0x18007f480`
- end: `0x180080179`
- name: `?FwSetupICSPortModify@@YAJPEAUIWbemServices@@QEAGPEBUWELL_KNOWN_PORT_@@H@Z`
- size: `3321`
- prototype: `__int64 __fastcall(struct IWbemServices *, unsigned __int16 *const, const struct WELL_KNOWN_PORT_ *, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180036db0`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x18004215c`
- `0x18004e0c0`
- `0x18004ed64`
- `0x180071dec`
- `0x18007e6f8`
- `0x18007e734`
- `0x18007f480`
- `0x180090010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18007fce1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18007fce1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18007fd3d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18007fd3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007fd06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007fd47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007fd06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007fd47`
- `OLEAUT32!__imp_SysFreeString` at `0x18007f5a1`
- `OLEAUT32!__imp_SysFreeString` at `0x18007f71b`
- `OLEAUT32!__imp_SysFreeString` at `0x18007f873`
- `OLEAUT32!__imp_SysFreeString` at `0x18007f935`
- `OLEAUT32!__imp_SysFreeString` at `0x18007f9e4`
- `OLEAUT32!__imp_SysFreeString` at `0x18007fc46`
- `OLEAUT32!__imp_SysFreeString` at `0x18007fdfd`
- `OLEAUT32!__imp_SysFreeString` at `0x18007fe96`
- `OLEAUT32!__imp_SysFreeString` at `0x18007ff25`
- `OLEAUT32!__imp_SysFreeString` at `0x18007ffb2`
- `OLEAUT32!__imp_SysFreeString` at `0x18008013a`
- `OLEAUT32!__imp_SysFreeString` at `0x18007f5a1`
- `OLEAUT32!__imp_SysFreeString` at `0x18007f71b`
- `OLEAUT32!__imp_SysFreeString` at `0x18007f873`
- `OLEAUT32!__imp_SysFreeString` at `0x18007f935`
- `OLEAUT32!__imp_SysFreeString` at `0x18007f9e4`
- `OLEAUT32!__imp_SysFreeString` at `0x18007fc46`
- `OLEAUT32!__imp_SysFreeString` at `0x18007fdfd`
- `OLEAUT32!__imp_SysFreeString` at `0x18007fe96`
- `OLEAUT32!__imp_SysFreeString` at `0x18007ff25`
- `OLEAUT32!__imp_SysFreeString` at `0x18007ffb2`
- `OLEAUT32!__imp_SysFreeString` at `0x18008013a`
- `OLEAUT32!__imp_VariantInit` at `0x18007f550`
- `OLEAUT32!__imp_VariantInit` at `0x18007f55b`
- `OLEAUT32!__imp_VariantInit` at `0x18007f550`
- `OLEAUT32!__imp_VariantInit` at `0x18007f55b`
- `OLEAUT32!__imp_VariantClear` at `0x18007f6fc`
- `OLEAUT32!__imp_VariantClear` at `0x18007f8e8`
- `OLEAUT32!__imp_VariantClear` at `0x18007f998`
- `OLEAUT32!__imp_VariantClear` at `0x18007f6fc`
- `OLEAUT32!__imp_VariantClear` at `0x18007f8e8`
- `OLEAUT32!__imp_VariantClear` at `0x18007f998`
- `WS2_32!__imp_htons` at `0x18007f948`
- `WS2_32!__imp_htons` at `0x18007fe47`
- `WS2_32!__imp_htons` at `0x18007f948`
- `WS2_32!__imp_htons` at `0x18007fe47`

## string_xrefs

- `0x18007f56c`: `HNet_PortMappingProtocol`
- `0x18007fc08`: `HNet_PortMappingProtocol`
- `0x18007f838`: `IPProtocol`
- `0x18007feef`: `IPProtocol`
- `0x18007f9aa`: `__Relpath`
- `0x180080101`: `__Relpath`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FwSetupICSPortModify(
        struct IWbemServices *a1,
        unsigned __int16 *const a2,
        const struct WELL_KNOWN_PORT_ *a3,
        __int64 a4)
{
  HRESULT (__stdcall *CreateInstanceEnum)(IWbemServices *, const BSTR, int, IWbemContext *, IEnumWbemClassObject **); // rbx
  ATL::CComBSTR *v7; // rax
  signed int v8; // ebx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  unsigned int v11; // r15d
  PVOID *v12; // rcx
  int v13; // r14d
  int v14; // esi
  __int64 v15; // r9
  PVOID *v16; // rcx
  __int64 (__fastcall *v18)(__int64, _QWORD, _QWORD, VARIANTARG *, _QWORD, _QWORD); // rbx
  ATL::CComBSTR *v19; // rax
  __int64 v20; // r9
  __int64 v21; // rdx
  __int64 (__fastcall *v22)(__int64, _QWORD, _QWORD, VARIANTARG *, _QWORD, _QWORD); // rbx
  ATL::CComBSTR *v23; // rax
  u_short v24; // ax
  __int64 (__fastcall *v25)(__int64, _QWORD, _QWORD, VARIANTARG *, _QWORD, _QWORD); // rbx
  ATL::CComBSTR *v26; // rax
  int v27; // esi
  int v28; // eax
  HRESULT (__stdcall *GetObjectA)(IWbemServices *, const BSTR, int, IWbemContext *, IWbemClassObject **, IWbemCallResult **); // rbx
  ATL::CComBSTR *v30; // rax
  __int64 v31; // r9
  DWORD LastError; // eax
  signed int v33; // eax
  __int64 (__fastcall *v34)(__int64, _QWORD, _QWORD, VARIANTARG *, _DWORD); // rbx
  ATL::CComBSTR *v35; // rax
  __int64 (__fastcall *v36)(__int64, _QWORD, _QWORD, VARIANTARG *, _DWORD); // rbx
  ATL::CComBSTR *v37; // rax
  __int64 (__fastcall *v38)(__int64, _QWORD, _QWORD, VARIANTARG *, _DWORD); // rbx
  ATL::CComBSTR *v39; // rax
  __int64 (__fastcall *v40)(__int64, _QWORD, _QWORD, VARIANTARG *, _DWORD); // rbx
  ATL::CComBSTR *v41; // rax
  __int64 (__fastcall *v42)(__int64, _QWORD, _QWORD, VARIANTARG *, _QWORD, _QWORD); // rbx
  ATL::CComBSTR *v43; // rax
  int v44[2]; // [rsp+20h] [rbp-E0h]
  BSTR v45; // [rsp+40h] [rbp-C0h] BYREF
  int v46; // [rsp+48h] [rbp-B8h]
  __int64 v47; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v48; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v49; // [rsp+60h] [rbp-A0h] BYREF
  VARIANTARG v50; // [rsp+68h] [rbp-98h] BYREF
  __int64 v51; // [rsp+80h] [rbp-80h] BYREF
  BSTR v52; // [rsp+88h] [rbp-78h] BYREF
  __int64 v53; // [rsp+90h] [rbp-70h]
  __int64 v54; // [rsp+98h] [rbp-68h] BYREF
  __int64 v55; // [rsp+A0h] [rbp-60h]
  BSTR bstrString; // [rsp+A8h] [rbp-58h] BYREF
  HMODULE phModule; // [rsp+B0h] [rbp-50h] BYREF
  VARIANTARG pvarg; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 *v59; // [rsp+D0h] [rbp-30h]
  WCHAR Buffer[128]; // [rsp+E0h] [rbp-20h] BYREF

  v46 = a4;
  v59 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    LOBYTE(a4) = (_DWORD)a4 != 0;
    WPP_SF_c(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_3d36977ad8ca33d40382d35fc3f7adf2_Traceguids, a4);
  }
  v52 = 0;
  v49 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  memset(&v50, 0, sizeof(v50));
  phModule = 0;
  memset_0(Buffer, 0, sizeof(Buffer));
  v53 = 0;
  v51 = 0;
  v48 = 0;
  v47 = 0;
  v54 = 0;
  v55 = 0;
  VariantInit(&pvarg);
  VariantInit(&v50);
  CreateInstanceEnum = a1->lpVtbl->CreateInstanceEnum;
  v7 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"HNet_PortMappingProtocol");
  v8 = ((__int64 (__fastcall *)(struct IWbemServices *, _QWORD, __int64))CreateInstanceEnum)(a1, *(_QWORD *)v7, 48);
  SysFreeString(bstrString);
  if ( v8 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_26;
    }
    v10 = 40;
    goto LABEL_124;
  }
  v11 = 0;
  v12 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_3d36977ad8ca33d40382d35fc3f7adf2_Traceguids);
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  v13 = 1;
  while ( 1 )
  {
    while ( 1 )
    {
      ++v11;
      if ( v12 != &WPP_GLOBAL_Control && (*((_DWORD *)v12 + 7) & 0x200) != 0 && *((_BYTE *)v12 + 25) >= 5u )
        WPP_SF_d(v12[2], 42, WPP_3d36977ad8ca33d40382d35fc3f7adf2_Traceguids, v11);
      if ( v48 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
        v48 = 0;
      }
      v14 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *, unsigned int *))(*(_QWORD *)v55 + 32LL))(
              v55,
              0xFFFFFFFFLL,
              1,
              &v48,
              &v49);
      v16 = (PVOID *)WPP_GLOBAL_Control;
      if ( v14 >= 0 )
      {
        if ( v14 == 1 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
          {
            if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_3d36977ad8ca33d40382d35fc3f7adf2_Traceguids, v49);
              v16 = (PVOID *)WPP_GLOBAL_Control;
            }
            v13 = 0;
            goto LABEL_67;
          }
          v27 = v46;
          goto LABEL_95;
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          43,
          WPP_3d36977ad8ca33d40382d35fc3f7adf2_Traceguids,
          (unsigned int)v14);
        v8 = v14;
        goto LABEL_26;
      }
      v8 = v14;
      if ( v14 < 0 )
        goto LABEL_26;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_3d36977ad8ca33d40382d35fc3f7adf2_Traceguids, v49);
      }
      v18 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v48 + 32LL);
      v19 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"IPProtocol");
      v8 = v18(v48, *(_QWORD *)v19, 0, &v50, 0, 0);
      SysFreeString(bstrString);
      if ( v8 < 0 )
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v10 = 46;
          goto LABEL_124;
        }
        goto LABEL_26;
      }
      v20 = *((unsigned int *)a3 + 1);
      if ( (_DWORD)v20 == v50.bVal )
        break;
      v12 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        v21 = 47;
        goto LABEL_55;
      }
    }
    VariantClear(&v50);
    v22 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v48 + 32LL);
    v23 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v45, L"Port");
    v8 = v22(v48, *(_QWORD *)v23, 0, &v50, 0, 0);
    SysFreeString(v45);
    if ( v8 < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v10 = 48;
        goto LABEL_124;
      }
      goto LABEL_26;
    }
    v24 = htons(*(_WORD *)a3);
    if ( v24 == v50.lVal )
      break;
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v21 = 49;
      v20 = *(unsigned int *)a3;
LABEL_55:
      WPP_SF_d(v12[2], v21, WPP_3d36977ad8ca33d40382d35fc3f7adf2_Traceguids, v20);
      v12 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  VariantClear(&v50);
  v25 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v48 + 32LL);
  v26 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v45, L"__Relpath");
  v8 = v25(v48, *(_QWORD *)v26, 0, &pvarg, 0, 0);
  SysFreeString(v45);
  if ( v8 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = 50;
      goto LABEL_124;
    }
    goto LABEL_26;
  }
  v16 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_3d36977ad8ca33d40382d35fc3f7adf2_Traceguids, v11);
    v16 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_67:
  v27 = v46;
  if ( v16 != &WPP_GLOBAL_Control && (*((_DWORD *)v16 + 7) & 0x200) != 0 && *((_BYTE *)v16 + 25) >= 5u )
  {
    LOBYTE(v15) = v46 != 0;
    LOBYTE(v44[0]) = v13;
    WPP_SF_cc(v16[2], 52, WPP_3d36977ad8ca33d40382d35fc3f7adf2_Traceguids, v15, *(_QWORD *)v44);
    v16 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v13 )
  {
LABEL_72:
    v28 = FwSetupICSPortBindingModify(a1, v59, pvarg.bstrVal, a3, v27);
    v8 = v28;
    if ( v28 >= 0 )
      goto LABEL_26;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_26;
    }
    v10 = 66;
    goto LABEL_110;
  }
LABEL_95:
  if ( !v27 )
  {
    if ( v16 != &WPP_GLOBAL_Control && (*((_DWORD *)v16 + 7) & 0x200) != 0 && *((_BYTE *)v16 + 25) >= 5u )
      WPP_SF_(v16[2], 53, WPP_3d36977ad8ca33d40382d35fc3f7adf2_Traceguids);
    goto LABEL_26;
  }
  GetObjectA = a1->lpVtbl->GetObjectA;
  v30 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v45, L"HNet_PortMappingProtocol");
  v8 = ((__int64 (__fastcall *)(struct IWbemServices *, _QWORD, _QWORD, _QWORD, __int64 *, _QWORD))GetObjectA)(
         a1,
         *(_QWORD *)v30,
         0,
         0,
         &v54,
         0);
  SysFreeString(v45);
  if ( v8 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = 54;
      goto LABEL_124;
    }
    goto LABEL_26;
  }
  v28 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v54 + 120LL))(v54, 0, &v47);
  v8 = v28;
  if ( v28 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_26;
    }
    v10 = 55;
    goto LABEL_110;
  }
  if ( !GetModuleHandleExW(6u, (LPCWSTR)FwSetupICSPortModify, &phModule)
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    LastError = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_3d36977ad8ca33d40382d35fc3f7adf2_Traceguids, LastError);
  }
  if ( LoadStringW(phModule, *((_DWORD *)a3 + 2), Buffer, 128) )
  {
    v50.vt = 8;
    v50.llVal = (LONGLONG)Buffer;
    v34 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, VARIANTARG *, _DWORD))(*(_QWORD *)v47 + 40LL);
    v35 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v45, L"Name");
    v8 = v34(v47, *(_QWORD *)v35, 0, &v50, 0);
    SysFreeString(v45);
    if ( v8 >= 0 )
    {
      v50.vt = 3;
      v50.lVal = htons(*(_WORD *)a3);
      v36 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, VARIANTARG *, _DWORD))(*(_QWORD *)v47 + 40LL);
      v37 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v45, L"Port");
      v8 = v36(v47, *(_QWORD *)v37, 0, &v50, 0);
      SysFreeString(v45);
      if ( v8 >= 0 )
      {
        v50.vt = 17;
        v50.bVal = *((_BYTE *)a3 + 4);
        v38 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, VARIANTARG *, _DWORD))(*(_QWORD *)v47 + 40LL);
        v39 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v45, L"IPProtocol");
        v8 = v38(v47, *(_QWORD *)v39, 0, &v50, 0);
        SysFreeString(v45);
        if ( v8 >= 0 )
        {
          v50.vt = 11;
          v50.iVal = 0;
          v40 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, VARIANTARG *, _DWORD))(*(_QWORD *)v47 + 40LL);
          v41 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v45, L"BuiltIn");
          v8 = v40(v47, *(_QWORD *)v41, 0, &v50, 0);
          SysFreeString(v45);
          if ( v8 >= 0 )
          {
            v28 = ((__int64 (__fastcall *)(struct IWbemServices *, __int64, __int64))a1->lpVtbl->PutInstance)(
                    a1,
                    v47,
                    18);
            v8 = v28;
            if ( v28 >= 0 )
            {
              v28 = (*(__int64 (__fastcall **)(__int64, __int64, BSTR *))(*(_QWORD *)v53 + 32LL))(
                      v53,
                      0xFFFFFFFFLL,
                      &v52);
              v8 = v28;
              if ( v28 >= 0 )
              {
                v28 = ((__int64 (__fastcall *)(struct IWbemServices *, BSTR, _QWORD, _QWORD, __int64 *, _QWORD))a1->lpVtbl->GetObjectA)(
                        a1,
                        v52,
                        0,
                        0,
                        &v51,
                        0);
                v8 = v28;
                if ( v28 >= 0 )
                {
                  v42 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v51 + 32LL);
                  v43 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v45, L"__Relpath");
                  v8 = v42(v51, *(_QWORD *)v43, 0, &pvarg, 0, 0);
                  SysFreeString(v45);
                  if ( v8 >= 0 )
                    goto LABEL_72;
                  v9 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                    || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
                    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                  {
                    goto LABEL_26;
                  }
                  v10 = 65;
                  goto LABEL_124;
                }
                v9 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_26;
                }
                v10 = 64;
              }
              else
              {
                v9 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_26;
                }
                v10 = 63;
              }
            }
            else
            {
              v9 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_26;
              }
              v10 = 62;
            }
LABEL_110:
            v31 = (unsigned int)v28;
            goto LABEL_125;
          }
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_26;
          }
          v10 = 61;
        }
        else
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_26;
          }
          v10 = 60;
        }
      }
      else
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_26;
        }
        v10 = 59;
      }
    }
    else
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_26;
      }
      v10 = 58;
    }
  }
  else
  {
    v33 = GetLastError();
    v8 = v33;
    if ( v33 > 0 )
      v8 = (unsigned __int16)v33 | 0x80070000;
    if ( v8 >= 0 )
      goto LABEL_26;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_26;
    }
    v10 = 57;
  }
LABEL_124:
  v31 = (unsigned int)v8;
LABEL_125:
  WPP_SF_d(v9[2], v10, WPP_3d36977ad8ca33d40382d35fc3f7adf2_Traceguids, v31);
LABEL_26:
  VariantClear(&pvarg);
  if ( v51 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
  SysFreeString(v52);
  if ( v53 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
  if ( v47 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
  if ( v54 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
  if ( v48 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
  if ( v55 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, WPP_3d36977ad8ca33d40382d35fc3f7adf2_Traceguids, (unsigned int)v8);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18007f480  push    rbp
0x18007f482  push    rbx
0x18007f483  push    rsi
0x18007f484  push    rdi
0x18007f485  push    r12
0x18007f487  push    r13
0x18007f489  push    r14
0x18007f48b  push    r15
0x18007f48d  lea     rbp, [rsp-0F8h]
0x18007f495  sub     rsp, 1F8h
0x18007f49c  mov     rax, cs:__security_cookie
0x18007f4a3  xor     rax, rsp
0x18007f4a6  mov     [rbp+130h+var_50], rax
0x18007f4ad  mov     eax, r9d
0x18007f4b0  mov     [rsp+230h+var_1E8], eax
0x18007f4b4  mov     r13, r8
0x18007f4b7  mov     [rbp+130h+var_160], rdx
0x18007f4bb  mov     r12, rcx
0x18007f4be  lea     r15, WPP_GLOBAL_Control
0x18007f4c5  xor     ebx, ebx
0x18007f4c7  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f4ce  cmp     rcx, r15
0x18007f4d1  jz      short loc_18007F4FB
0x18007f4d3  test    dword ptr [rcx+1Ch], 200h
0x18007f4da  jz      short loc_18007F4FB
0x18007f4dc  cmp     byte ptr [rcx+19h], 6
0x18007f4e0  jb      short loc_18007F4FB
0x18007f4e2  test    eax, eax
0x18007f4e4  setnz   r9b
0x18007f4e8  lea     edx, [rbx+27h]
0x18007f4eb  lea     r8, WPP_3d36977ad8ca33d40382d35fc3f7adf2_Traceguids
0x18007f4f2  mov     rcx, [rcx+10h]
0x18007f4f6  call    WPP_SF_c
0x18007f4fb  mov     [rbp+130h+var_1A8], rbx
0x18007f4ff  mov     [rsp+230h+var_1D0], ebx
0x18007f503  xorps   xmm0, xmm0
0x18007f506  xor     eax, eax
0x18007f508  movups  xmmword ptr [rbp+130h+pvarg], xmm0
0x18007f50c  mov     qword ptr [rbp+130h+pvarg+10h], rax
0x18007f510  xorps   xmm1, xmm1
0x18007f513  movups  xmmword ptr [rsp+230h+var_1C8], xmm1
0x18007f518  mov     qword ptr [rsp+230h+var_1C8+10h], rax
0x18007f51d  mov     [rbp+130h+phModule], rbx
0x18007f521  xor     edx, edx; Val
0x18007f523  mov     r8d, 100h; Size
0x18007f529  lea     rcx, [rbp+130h+Buffer]; void *
0x18007f52d  call    memset_0
0x18007f532  mov     [rbp+130h+var_1A0], rbx
0x18007f536  mov     [rbp+130h+var_1B0], rbx
0x18007f53a  mov     [rsp+230h+var_1D8], rbx
0x18007f53f  mov     [rsp+230h+var_1E0], rbx
0x18007f544  mov     [rbp+130h+var_198], rbx
0x18007f548  mov     [rbp+130h+var_190], rbx
0x18007f54c  lea     rcx, [rbp+130h+pvarg]; pvarg
0x18007f550  call    cs:__imp_VariantInit
0x18007f556  lea     rcx, [rsp+230h+var_1C8]; pvarg
0x18007f55b  call    cs:__imp_VariantInit
0x18007f561  mov     rax, [r12]
0x18007f565  mov     rbx, [rax+90h]
0x18007f56c  lea     rdx, aHnetPortmappin; "HNet_PortMappingProtocol"
0x18007f573  lea     rcx, [rbp+130h+bstrString]; this
0x18007f577  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18007f57c  nop
0x18007f57d  lea     rcx, [rbp+130h+var_190]
0x18007f581  mov     qword ptr [rsp+230h+var_210], rcx
0x18007f586  xor     r9d, r9d
0x18007f589  lea     r8d, [r9+30h]
0x18007f58d  mov     rdx, [rax]
0x18007f590  mov     rcx, r12
0x18007f593  mov     rax, rbx
0x18007f596  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f59b  mov     ebx, eax
0x18007f59d  mov     rcx, [rbp+130h+bstrString]; bstrString
0x18007f5a1  call    cs:__imp_SysFreeString
0x18007f5a7  xor     esi, esi
0x18007f5a9  test    ebx, ebx
0x18007f5ab  jns     short loc_18007F5DF
0x18007f5ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f5b4  cmp     rcx, r15
0x18007f5b7  jz      loc_18007F6F8
0x18007f5bd  test    dword ptr [rcx+1Ch], 200h
0x18007f5c4  jz      loc_18007F6F8
0x18007f5ca  mov     dil, 2
0x18007f5cd  cmp     [rcx+19h], dil
0x18007f5d1  jb      loc_18007F6F8
0x18007f5d7  lea     edx, [rsi+28h]
0x18007f5da  jmp     loc_18007FD90
0x18007f5df  mov     r15d, esi
0x18007f5e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f5e9  lea     rax, WPP_GLOBAL_Control
0x18007f5f0  cmp     rcx, rax
0x18007f5f3  jz      short loc_18007F627
0x18007f5f5  test    dword ptr [rcx+1Ch], 200h
0x18007f5fc  jz      short loc_18007F627
0x18007f5fe  cmp     byte ptr [rcx+19h], 5
0x18007f602  jb      short loc_18007F627
0x18007f604  mov     edx, 29h ; ')'
0x18007f609  lea     r8, WPP_3d36977ad8ca33d40382d35fc3f7adf2_Traceguids
0x18007f610  mov     rcx, [rcx+10h]
0x18007f614  call    WPP_SF_
0x18007f619  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f620  lea     rax, WPP_GLOBAL_Control
0x18007f627  mov     dil, 2
0x18007f62a  mov     r14d, 1
0x18007f630  add     r15d, r14d
0x18007f633  cmp     rcx, rax
0x18007f636  jz      short loc_18007F65F
0x18007f638  test    dword ptr [rcx+1Ch], 200h
0x18007f63f  jz      short loc_18007F65F
0x18007f641  cmp     byte ptr [rcx+19h], 5
0x18007f645  jb      short loc_18007F65F
0x18007f647  mov     edx, 2Ah ; '*'
0x18007f64c  mov     r9d, r15d
0x18007f64f  lea     r8, WPP_3d36977ad8ca33d40382d35fc3f7adf2_Traceguids
0x18007f656  mov     rcx, [rcx+10h]
0x18007f65a  call    WPP_SF_d
0x18007f65f  mov     rcx, [rsp+230h+var_1D8]
0x18007f664  test    rcx, rcx
0x18007f667  jz      short loc_18007F67A
0x18007f669  mov     rax, [rcx]
0x18007f66c  mov     rax, [rax+10h]
0x18007f670  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f675  mov     [rsp+230h+var_1D8], rsi
0x18007f67a  mov     rcx, [rbp+130h+var_190]
0x18007f67e  mov     rax, [rcx]
0x18007f681  lea     rdx, [rsp+230h+var_1D0]
0x18007f686  mov     qword ptr [rsp+230h+var_210], rdx
0x18007f68b  lea     r9, [rsp+230h+var_1D8]
0x18007f690  mov     r8d, r14d
0x18007f693  or      edx, 0FFFFFFFFh
0x18007f696  mov     rax, [rax+20h]
0x18007f69a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f69f  mov     esi, eax
0x18007f6a1  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f6a8  test    eax, eax
0x18007f6aa  jns     loc_18007F7E4
0x18007f6b0  lea     rax, WPP_GLOBAL_Control
0x18007f6b7  cmp     rcx, rax
0x18007f6ba  jz      loc_18007F7F4
0x18007f6c0  test    dword ptr [rcx+1Ch], 200h
0x18007f6c7  jz      loc_18007F7F4
0x18007f6cd  cmp     [rcx+19h], dil
0x18007f6d1  jb      loc_18007F7F4
0x18007f6d7  mov     edx, 2Bh ; '+'
0x18007f6dc  mov     r9d, esi
0x18007f6df  lea     r8, WPP_3d36977ad8ca33d40382d35fc3f7adf2_Traceguids
0x18007f6e6  mov     rcx, [rcx+10h]
0x18007f6ea  call    WPP_SF_d
0x18007f6ef  mov     ebx, esi
0x18007f6f1  lea     r15, WPP_GLOBAL_Control
0x18007f6f8  lea     rcx, [rbp+130h+pvarg]; pvarg
0x18007f6fc  call    cs:__imp_VariantClear
0x18007f702  mov     rcx, [rbp+130h+var_1B0]
0x18007f706  test    rcx, rcx
0x18007f709  jz      short loc_18007F717
0x18007f70b  mov     rax, [rcx]
0x18007f70e  mov     rax, [rax+10h]
0x18007f712  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f717  mov     rcx, [rbp+130h+var_1A8]; bstrString
0x18007f71b  call    cs:__imp_SysFreeString
0x18007f721  mov     rcx, [rbp+130h+var_1A0]
0x18007f725  test    rcx, rcx
0x18007f728  jz      short loc_18007F736
0x18007f72a  mov     rax, [rcx]
0x18007f72d  mov     rax, [rax+10h]
0x18007f731  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f736  mov     rcx, [rsp+230h+var_1E0]
0x18007f73b  test    rcx, rcx
0x18007f73e  jz      short loc_18007F74C
0x18007f740  mov     rax, [rcx]
0x18007f743  mov     rax, [rax+10h]
0x18007f747  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f74c  mov     rcx, [rbp+130h+var_198]
0x18007f750  test    rcx, rcx
0x18007f753  jz      short loc_18007F761
0x18007f755  mov     rax, [rcx]
0x18007f758  mov     rax, [rax+10h]
0x18007f75c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f761  mov     rcx, [rsp+230h+var_1D8]
0x18007f766  test    rcx, rcx
0x18007f769  jz      short loc_18007F777
0x18007f76b  mov     rax, [rcx]
0x18007f76e  mov     rax, [rax+10h]
0x18007f772  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f777  mov     rcx, [rbp+130h+var_190]
0x18007f77b  test    rcx, rcx
0x18007f77e  jz      short loc_18007F78C
0x18007f780  mov     rax, [rcx]
0x18007f783  mov     rax, [rax+10h]
0x18007f787  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f78c  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f793  cmp     rcx, r15
0x18007f796  jz      short loc_18007F7BF
0x18007f798  test    dword ptr [rcx+1Ch], 200h
0x18007f79f  jz      short loc_18007F7BF
0x18007f7a1  cmp     byte ptr [rcx+19h], 6
0x18007f7a5  jb      short loc_18007F7BF
0x18007f7a7  mov     edx, 43h ; 'C'
0x18007f7ac  mov     r9d, ebx
0x18007f7af  lea     r8, WPP_3d36977ad8ca33d40382d35fc3f7adf2_Traceguids
0x18007f7b6  mov     rcx, [rcx+10h]
0x18007f7ba  call    WPP_SF_d
0x18007f7bf  mov     eax, ebx
0x18007f7c1  mov     rcx, [rbp+130h+var_50]
0x18007f7c8  xor     rcx, rsp; StackCookie
0x18007f7cb  call    __security_check_cookie
0x18007f7d0  add     rsp, 1F8h
0x18007f7d7  pop     r15
0x18007f7d9  pop     r14
0x18007f7db  pop     r13
0x18007f7dd  pop     r12
0x18007f7df  pop     rdi
0x18007f7e0  pop     rsi
0x18007f7e1  pop     rbx
0x18007f7e2  pop     rbp
0x18007f7e3  retn
0x18007f7e4  cmp     esi, r14d
0x18007f7e7  jz      loc_18007FB7C
0x18007f7ed  lea     rax, WPP_GLOBAL_Control
0x18007f7f4  mov     ebx, esi
0x18007f7f6  test    esi, esi
0x18007f7f8  js      loc_18007F6F1
0x18007f7fe  cmp     rcx, rax
0x18007f801  jz      short loc_18007F82C
0x18007f803  test    dword ptr [rcx+1Ch], 200h
0x18007f80a  jz      short loc_18007F82C
0x18007f80c  cmp     byte ptr [rcx+19h], 5
0x18007f810  jb      short loc_18007F82C
0x18007f812  mov     edx, 2Dh ; '-'
0x18007f817  mov     r9d, [rsp+230h+var_1D0]
0x18007f81c  lea     r8, WPP_3d36977ad8ca33d40382d35fc3f7adf2_Traceguids
0x18007f823  mov     rcx, [rcx+10h]
0x18007f827  call    WPP_SF_d
0x18007f82c  mov     rax, [rsp+230h+var_1D8]
0x18007f831  mov     rcx, [rax]
0x18007f834  mov     rbx, [rcx+20h]
0x18007f838  lea     rdx, aIpprotocol; "IPProtocol"
0x18007f83f  lea     rcx, [rbp+130h+bstrString]; this
0x18007f843  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18007f848  nop
0x18007f849  xor     esi, esi
0x18007f84b  mov     [rsp+230h+var_208], rsi
0x18007f850  mov     qword ptr [rsp+230h+var_210], rsi
0x18007f855  lea     r9, [rsp+230h+var_1C8]
0x18007f85a  xor     r8d, r8d
0x18007f85d  mov     rdx, [rax]
0x18007f860  mov     rcx, [rsp+230h+var_1D8]
0x18007f865  mov     rax, rbx
0x18007f868  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f86d  mov     ebx, eax
0x18007f86f  mov     rcx, [rbp+130h+bstrString]; bstrString
0x18007f873  call    cs:__imp_SysFreeString
0x18007f879  test    ebx, ebx
0x18007f87b  js      loc_18007FB44
0x18007f881  mov     r9d, [r13+4]
0x18007f885  movzx   eax, byte ptr [rsp+230h+var_1C8+8]
0x18007f88a  cmp     r9d, eax
0x18007f88d  jz      short loc_18007F8E3
0x18007f88f  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f896  lea     rax, WPP_GLOBAL_Control
0x18007f89d  cmp     rcx, rax
0x18007f8a0  jz      loc_18007F630
0x18007f8a6  test    dword ptr [rcx+1Ch], 200h
0x18007f8ad  jz      loc_18007F630
0x18007f8b3  cmp     byte ptr [rcx+19h], 5
0x18007f8b7  jb      loc_18007F630
0x18007f8bd  lea     edx, [rsi+2Fh]
0x18007f8c0  lea     r8, WPP_3d36977ad8ca33d40382d35fc3f7adf2_Traceguids
0x18007f8c7  mov     rcx, [rcx+10h]
0x18007f8cb  call    WPP_SF_d
0x18007f8d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f8d7  lea     rax, WPP_GLOBAL_Control
0x18007f8de  jmp     loc_18007F630
0x18007f8e3  lea     rcx, [rsp+230h+var_1C8]; pvarg
0x18007f8e8  call    cs:__imp_VariantClear
0x18007f8ee  mov     rax, [rsp+230h+var_1D8]
0x18007f8f3  mov     rcx, [rax]
0x18007f8f6  mov     rbx, [rcx+20h]
0x18007f8fa  lea     rdx, aPort; "Port"
0x18007f901  lea     rcx, [rsp+230h+var_1F0]; this
0x18007f906  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18007f90b  nop
0x18007f90c  mov     [rsp+230h+var_208], rsi
0x18007f911  mov     qword ptr [rsp+230h+var_210], rsi
0x18007f916  lea     r9, [rsp+230h+var_1C8]
0x18007f91b  xor     r8d, r8d
0x18007f91e  mov     rdx, [rax]
0x18007f921  mov     rcx, [rsp+230h+var_1D8]
0x18007f926  mov     rax, rbx
0x18007f929  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f92e  mov     ebx, eax
0x18007f930  mov     rcx, [rsp+230h+var_1F0]; bstrString
0x18007f935  call    cs:__imp_SysFreeString
0x18007f93b  test    ebx, ebx
0x18007f93d  js      loc_18007FB0C
0x18007f943  movzx   ecx, word ptr [r13+0]; hostshort
0x18007f948  call    cs:__imp_htons
0x18007f94e  movzx   eax, ax
0x18007f951  cmp     eax, dword ptr [rsp+230h+var_1C8+8]
0x18007f955  jz      short loc_18007F993
  ... truncated ...
```
