# FwSetupICSPortModify(IWbemServices *,ushort * const,WELL_KNOWN_PORT_ const *,int)

- ea: `0x1800859a0`
- end: `0x18008671e`
- name: `?FwSetupICSPortModify@@YAJPEAUIWbemServices@@QEAGPEBUWELL_KNOWN_PORT_@@H@Z`
- size: `3454`
- prototype: `__int64 __fastcall(struct IWbemServices *, unsigned __int16 *const, const struct WELL_KNOWN_PORT_ *, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180039a80`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x18004561c`
- `0x180051f30`
- `0x180052bf4`
- `0x1800778b0`
- `0x180084b88`
- `0x180084bcc`
- `0x1800859a0`
- `0x180097010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18008624a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18008624a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800862b2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800862b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086275`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800862c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086275`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800862c2`
- `OLEAUT32!__imp_SysFreeString` at `0x180085acd`
- `OLEAUT32!__imp_SysFreeString` at `0x180085c53`
- `OLEAUT32!__imp_SysFreeString` at `0x180085db2`
- `OLEAUT32!__imp_SysFreeString` at `0x180085e80`
- `OLEAUT32!__imp_SysFreeString` at `0x180085f41`
- `OLEAUT32!__imp_SysFreeString` at `0x1800861a9`
- `OLEAUT32!__imp_SysFreeString` at `0x18008637e`
- `OLEAUT32!__imp_SysFreeString` at `0x180086423`
- `OLEAUT32!__imp_SysFreeString` at `0x1800864b8`
- `OLEAUT32!__imp_SysFreeString` at `0x18008654b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800866d9`
- `OLEAUT32!__imp_SysFreeString` at `0x180085acd`
- `OLEAUT32!__imp_SysFreeString` at `0x180085c53`
- `OLEAUT32!__imp_SysFreeString` at `0x180085db2`
- `OLEAUT32!__imp_SysFreeString` at `0x180085e80`
- `OLEAUT32!__imp_SysFreeString` at `0x180085f41`
- `OLEAUT32!__imp_SysFreeString` at `0x1800861a9`
- `OLEAUT32!__imp_SysFreeString` at `0x18008637e`
- `OLEAUT32!__imp_SysFreeString` at `0x180086423`
- `OLEAUT32!__imp_SysFreeString` at `0x1800864b8`
- `OLEAUT32!__imp_SysFreeString` at `0x18008654b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800866d9`
- `OLEAUT32!__imp_VariantInit` at `0x180085a70`
- `OLEAUT32!__imp_VariantInit` at `0x180085a81`
- `OLEAUT32!__imp_VariantInit` at `0x180085a70`
- `OLEAUT32!__imp_VariantInit` at `0x180085a81`
- `OLEAUT32!__imp_VariantClear` at `0x180085c2e`
- `OLEAUT32!__imp_VariantClear` at `0x180085e2d`
- `OLEAUT32!__imp_VariantClear` at `0x180085eef`
- `OLEAUT32!__imp_VariantClear` at `0x180085c2e`
- `OLEAUT32!__imp_VariantClear` at `0x180085e2d`
- `OLEAUT32!__imp_VariantClear` at `0x180085eef`
- `WS2_32!__imp_htons` at `0x180085e99`
- `WS2_32!__imp_htons` at `0x1800863ce`
- `WS2_32!__imp_htons` at `0x180085e99`
- `WS2_32!__imp_htons` at `0x1800863ce`

## string_xrefs

- `0x180085a98`: `HNet_PortMappingProtocol`
- `0x18008616b`: `HNet_PortMappingProtocol`
- `0x180085d77`: `IPProtocol`
- `0x180086482`: `IPProtocol`
- `0x180085f07`: `__Relpath`
- `0x1800866a0`: `__Relpath`

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
  _QWORD *v7; // rax
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
  _QWORD *v19; // rax
  __int64 v20; // r9
  __int64 v21; // rdx
  __int64 (__fastcall *v22)(__int64, _QWORD, _QWORD, VARIANTARG *, _QWORD, _QWORD); // rbx
  _QWORD *v23; // rax
  u_short v24; // ax
  __int64 (__fastcall *v25)(__int64, _QWORD, _QWORD, VARIANTARG *, _QWORD, _QWORD); // rbx
  _QWORD *v26; // rax
  int v27; // esi
  int v28; // eax
  HRESULT (__stdcall *GetObjectA)(IWbemServices *, const BSTR, int, IWbemContext *, IWbemClassObject **, IWbemCallResult **); // rbx
  _QWORD *v30; // rax
  __int64 v31; // r9
  DWORD LastError; // eax
  signed int v33; // eax
  __int64 (__fastcall *v34)(__int64, _QWORD, _QWORD, VARIANTARG *, _DWORD); // rbx
  _QWORD *v35; // rax
  __int64 (__fastcall *v36)(__int64, _QWORD, _QWORD, VARIANTARG *, _DWORD); // rbx
  _QWORD *v37; // rax
  __int64 (__fastcall *v38)(__int64, _QWORD, _QWORD, VARIANTARG *, _DWORD); // rbx
  _QWORD *v39; // rax
  __int64 (__fastcall *v40)(__int64, _QWORD, _QWORD, VARIANTARG *, _DWORD); // rbx
  _QWORD *v41; // rax
  __int64 (__fastcall *v42)(__int64, _QWORD, _QWORD, VARIANTARG *, _QWORD, _QWORD); // rbx
  _QWORD *v43; // rax
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
  v7 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"HNet_PortMappingProtocol");
  v8 = ((__int64 (__fastcall *)(struct IWbemServices *, _QWORD, __int64))CreateInstanceEnum)(a1, *v7, 48);
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
      v19 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"IPProtocol");
      v8 = v18(v48, *v19, 0, &v50, 0, 0);
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
    v23 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v45, L"Port");
    v8 = v22(v48, *v23, 0, &v50, 0, 0);
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
  v26 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v45, L"__Relpath");
  v8 = v25(v48, *v26, 0, &pvarg, 0, 0);
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
  v30 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v45, L"HNet_PortMappingProtocol");
  v8 = ((__int64 (__fastcall *)(struct IWbemServices *, _QWORD, _QWORD, _QWORD, __int64 *, _QWORD))GetObjectA)(
         a1,
         *v30,
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
    v35 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v45, L"Name");
    v8 = v34(v47, *v35, 0, &v50, 0);
    SysFreeString(v45);
    if ( v8 >= 0 )
    {
      v50.vt = 3;
      v50.lVal = htons(*(_WORD *)a3);
      v36 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, VARIANTARG *, _DWORD))(*(_QWORD *)v47 + 40LL);
      v37 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v45, L"Port");
      v8 = v36(v47, *v37, 0, &v50, 0);
      SysFreeString(v45);
      if ( v8 >= 0 )
      {
        v50.vt = 17;
        v50.bVal = *((_BYTE *)a3 + 4);
        v38 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, VARIANTARG *, _DWORD))(*(_QWORD *)v47 + 40LL);
        v39 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v45, L"IPProtocol");
        v8 = v38(v47, *v39, 0, &v50, 0);
        SysFreeString(v45);
        if ( v8 >= 0 )
        {
          v50.vt = 11;
          v50.iVal = 0;
          v40 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, VARIANTARG *, _DWORD))(*(_QWORD *)v47 + 40LL);
          v41 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v45, L"BuiltIn");
          v8 = v40(v47, *v41, 0, &v50, 0);
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
                  v43 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v45, L"__Relpath");
                  v8 = v42(v51, *v43, 0, &pvarg, 0, 0);
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
0x1800859a0  push    rbp
0x1800859a2  push    rbx
0x1800859a3  push    rsi
0x1800859a4  push    rdi
0x1800859a5  push    r12
0x1800859a7  push    r13
0x1800859a9  push    r14
0x1800859ab  push    r15
0x1800859ad  lea     rbp, [rsp-0F8h]
0x1800859b5  sub     rsp, 1F8h
0x1800859bc  mov     rax, cs:__security_cookie
0x1800859c3  xor     rax, rsp
0x1800859c6  mov     [rbp+130h+var_50], rax
0x1800859cd  mov     eax, r9d
0x1800859d0  mov     [rsp+230h+var_1E8], eax
0x1800859d4  mov     r13, r8
0x1800859d7  mov     [rbp+130h+var_160], rdx
0x1800859db  mov     r12, rcx
0x1800859de  lea     r15, WPP_GLOBAL_Control
0x1800859e5  xor     ebx, ebx
0x1800859e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800859ee  cmp     rcx, r15
0x1800859f1  jz      short loc_180085A1B
0x1800859f3  test    dword ptr [rcx+1Ch], 200h
0x1800859fa  jz      short loc_180085A1B
0x1800859fc  cmp     byte ptr [rcx+19h], 6
0x180085a00  jb      short loc_180085A1B
0x180085a02  test    eax, eax
0x180085a04  setnz   r9b
0x180085a08  lea     edx, [rbx+27h]
0x180085a0b  lea     r8, WPP_3d36977ad8ca33d40382d35fc3f7adf2_Traceguids
0x180085a12  mov     rcx, [rcx+10h]
0x180085a16  call    WPP_SF_c
0x180085a1b  mov     [rbp+130h+var_1A8], rbx
0x180085a1f  mov     [rsp+230h+var_1D0], ebx
0x180085a23  xorps   xmm0, xmm0
0x180085a26  xor     eax, eax
0x180085a28  movups  xmmword ptr [rbp+130h+pvarg], xmm0
0x180085a2c  mov     qword ptr [rbp+130h+pvarg+10h], rax
0x180085a30  xorps   xmm1, xmm1
0x180085a33  movups  xmmword ptr [rsp+230h+var_1C8], xmm1
0x180085a38  mov     qword ptr [rsp+230h+var_1C8+10h], rax
0x180085a3d  mov     [rbp+130h+phModule], rbx
0x180085a41  xor     edx, edx; Val
0x180085a43  mov     r8d, 100h; Size
0x180085a49  lea     rcx, [rbp+130h+Buffer]; void *
0x180085a4d  call    memset_0
0x180085a52  mov     [rbp+130h+var_1A0], rbx
0x180085a56  mov     [rbp+130h+var_1B0], rbx
0x180085a5a  mov     [rsp+230h+var_1D8], rbx
0x180085a5f  mov     [rsp+230h+var_1E0], rbx
0x180085a64  mov     [rbp+130h+var_198], rbx
0x180085a68  mov     [rbp+130h+var_190], rbx
0x180085a6c  lea     rcx, [rbp+130h+pvarg]; pvarg
0x180085a70  call    cs:__imp_VariantInit
0x180085a77  nop     dword ptr [rax+rax+00h]
0x180085a7c  lea     rcx, [rsp+230h+var_1C8]; pvarg
0x180085a81  call    cs:__imp_VariantInit
0x180085a88  nop     dword ptr [rax+rax+00h]
0x180085a8d  mov     rax, [r12]
0x180085a91  mov     rbx, [rax+90h]
0x180085a98  lea     rdx, aHnetPortmappin; "HNet_PortMappingProtocol"
0x180085a9f  lea     rcx, [rbp+130h+bstrString]; this
0x180085aa3  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180085aa8  nop
0x180085aa9  lea     rcx, [rbp+130h+var_190]
0x180085aad  mov     qword ptr [rsp+230h+var_210], rcx
0x180085ab2  xor     r9d, r9d
0x180085ab5  lea     r8d, [r9+30h]
0x180085ab9  mov     rdx, [rax]
0x180085abc  mov     rcx, r12
0x180085abf  mov     rax, rbx
0x180085ac2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085ac7  mov     ebx, eax
0x180085ac9  mov     rcx, [rbp+130h+bstrString]; bstrString
0x180085acd  call    cs:__imp_SysFreeString
0x180085ad4  nop     dword ptr [rax+rax+00h]
0x180085ad9  xor     esi, esi
0x180085adb  test    ebx, ebx
0x180085add  jns     short loc_180085B11
0x180085adf  mov     rcx, cs:WPP_GLOBAL_Control
0x180085ae6  cmp     rcx, r15
0x180085ae9  jz      loc_180085C2A
0x180085aef  test    dword ptr [rcx+1Ch], 200h
0x180085af6  jz      loc_180085C2A
0x180085afc  mov     dil, 2
0x180085aff  cmp     [rcx+19h], dil
0x180085b03  jb      loc_180085C2A
0x180085b09  lea     edx, [rsi+28h]
0x180085b0c  jmp     loc_180086311
0x180085b11  mov     r15d, esi
0x180085b14  mov     rcx, cs:WPP_GLOBAL_Control
0x180085b1b  lea     rax, WPP_GLOBAL_Control
0x180085b22  cmp     rcx, rax
0x180085b25  jz      short loc_180085B59
0x180085b27  test    dword ptr [rcx+1Ch], 200h
0x180085b2e  jz      short loc_180085B59
0x180085b30  cmp     byte ptr [rcx+19h], 5
0x180085b34  jb      short loc_180085B59
0x180085b36  mov     edx, 29h ; ')'
0x180085b3b  lea     r8, WPP_3d36977ad8ca33d40382d35fc3f7adf2_Traceguids
0x180085b42  mov     rcx, [rcx+10h]
0x180085b46  call    WPP_SF_
0x180085b4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180085b52  lea     rax, WPP_GLOBAL_Control
0x180085b59  mov     dil, 2
0x180085b5c  mov     r14d, 1
0x180085b62  add     r15d, r14d
0x180085b65  cmp     rcx, rax
0x180085b68  jz      short loc_180085B91
0x180085b6a  test    dword ptr [rcx+1Ch], 200h
0x180085b71  jz      short loc_180085B91
0x180085b73  cmp     byte ptr [rcx+19h], 5
0x180085b77  jb      short loc_180085B91
0x180085b79  mov     edx, 2Ah ; '*'
0x180085b7e  mov     r9d, r15d
0x180085b81  lea     r8, WPP_3d36977ad8ca33d40382d35fc3f7adf2_Traceguids
0x180085b88  mov     rcx, [rcx+10h]
0x180085b8c  call    WPP_SF_d
0x180085b91  mov     rcx, [rsp+230h+var_1D8]
0x180085b96  test    rcx, rcx
0x180085b99  jz      short loc_180085BAC
0x180085b9b  mov     rax, [rcx]
0x180085b9e  mov     rax, [rax+10h]
0x180085ba2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085ba7  mov     [rsp+230h+var_1D8], rsi
0x180085bac  mov     rcx, [rbp+130h+var_190]
0x180085bb0  mov     rax, [rcx]
0x180085bb3  lea     rdx, [rsp+230h+var_1D0]
0x180085bb8  mov     qword ptr [rsp+230h+var_210], rdx
0x180085bbd  lea     r9, [rsp+230h+var_1D8]
0x180085bc2  mov     r8d, r14d
0x180085bc5  or      edx, 0FFFFFFFFh
0x180085bc8  mov     rax, [rax+20h]
0x180085bcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085bd1  mov     esi, eax
0x180085bd3  mov     rcx, cs:WPP_GLOBAL_Control
0x180085bda  test    eax, eax
0x180085bdc  jns     loc_180085D23
0x180085be2  lea     rax, WPP_GLOBAL_Control
0x180085be9  cmp     rcx, rax
0x180085bec  jz      loc_180085D33
0x180085bf2  test    dword ptr [rcx+1Ch], 200h
0x180085bf9  jz      loc_180085D33
0x180085bff  cmp     [rcx+19h], dil
0x180085c03  jb      loc_180085D33
0x180085c09  mov     edx, 2Bh ; '+'
0x180085c0e  mov     r9d, esi
0x180085c11  lea     r8, WPP_3d36977ad8ca33d40382d35fc3f7adf2_Traceguids
0x180085c18  mov     rcx, [rcx+10h]
0x180085c1c  call    WPP_SF_d
0x180085c21  mov     ebx, esi
0x180085c23  lea     r15, WPP_GLOBAL_Control
0x180085c2a  lea     rcx, [rbp+130h+pvarg]; pvarg
0x180085c2e  call    cs:__imp_VariantClear
0x180085c35  nop     dword ptr [rax+rax+00h]
0x180085c3a  mov     rcx, [rbp+130h+var_1B0]
0x180085c3e  test    rcx, rcx
0x180085c41  jz      short loc_180085C4F
0x180085c43  mov     rax, [rcx]
0x180085c46  mov     rax, [rax+10h]
0x180085c4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085c4f  mov     rcx, [rbp+130h+var_1A8]; bstrString
0x180085c53  call    cs:__imp_SysFreeString
0x180085c5a  nop     dword ptr [rax+rax+00h]
0x180085c5f  mov     rcx, [rbp+130h+var_1A0]
0x180085c63  test    rcx, rcx
0x180085c66  jz      short loc_180085C74
0x180085c68  mov     rax, [rcx]
0x180085c6b  mov     rax, [rax+10h]
0x180085c6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085c74  mov     rcx, [rsp+230h+var_1E0]
0x180085c79  test    rcx, rcx
0x180085c7c  jz      short loc_180085C8A
0x180085c7e  mov     rax, [rcx]
0x180085c81  mov     rax, [rax+10h]
0x180085c85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085c8a  mov     rcx, [rbp+130h+var_198]
0x180085c8e  test    rcx, rcx
0x180085c91  jz      short loc_180085C9F
0x180085c93  mov     rax, [rcx]
0x180085c96  mov     rax, [rax+10h]
0x180085c9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085c9f  mov     rcx, [rsp+230h+var_1D8]
0x180085ca4  test    rcx, rcx
0x180085ca7  jz      short loc_180085CB5
0x180085ca9  mov     rax, [rcx]
0x180085cac  mov     rax, [rax+10h]
0x180085cb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085cb5  mov     rcx, [rbp+130h+var_190]
0x180085cb9  test    rcx, rcx
0x180085cbc  jz      short loc_180085CCA
0x180085cbe  mov     rax, [rcx]
0x180085cc1  mov     rax, [rax+10h]
0x180085cc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085cca  mov     rcx, cs:WPP_GLOBAL_Control
0x180085cd1  cmp     rcx, r15
0x180085cd4  jz      short loc_180085CFD
0x180085cd6  test    dword ptr [rcx+1Ch], 200h
0x180085cdd  jz      short loc_180085CFD
0x180085cdf  cmp     byte ptr [rcx+19h], 6
0x180085ce3  jb      short loc_180085CFD
0x180085ce5  mov     edx, 43h ; 'C'
0x180085cea  mov     r9d, ebx
0x180085ced  lea     r8, WPP_3d36977ad8ca33d40382d35fc3f7adf2_Traceguids
0x180085cf4  mov     rcx, [rcx+10h]
0x180085cf8  call    WPP_SF_d
0x180085cfd  mov     eax, ebx
0x180085cff  mov     rcx, [rbp+130h+var_50]
0x180085d06  xor     rcx, rsp; StackCookie
0x180085d09  call    __security_check_cookie
0x180085d0e  add     rsp, 1F8h
0x180085d15  pop     r15
0x180085d17  pop     r14
0x180085d19  pop     r13
0x180085d1b  pop     r12
0x180085d1d  pop     rdi
0x180085d1e  pop     rsi
0x180085d1f  pop     rbx
0x180085d20  pop     rbp
0x180085d21  retn
0x180085d23  cmp     esi, r14d
0x180085d26  jz      loc_1800860DF
0x180085d2c  lea     rax, WPP_GLOBAL_Control
0x180085d33  mov     ebx, esi
0x180085d35  test    esi, esi
0x180085d37  js      loc_180085C23
0x180085d3d  cmp     rcx, rax
0x180085d40  jz      short loc_180085D6B
0x180085d42  test    dword ptr [rcx+1Ch], 200h
0x180085d49  jz      short loc_180085D6B
0x180085d4b  cmp     byte ptr [rcx+19h], 5
0x180085d4f  jb      short loc_180085D6B
0x180085d51  mov     edx, 2Dh ; '-'
0x180085d56  mov     r9d, [rsp+230h+var_1D0]
0x180085d5b  lea     r8, WPP_3d36977ad8ca33d40382d35fc3f7adf2_Traceguids
0x180085d62  mov     rcx, [rcx+10h]
0x180085d66  call    WPP_SF_d
0x180085d6b  mov     rax, [rsp+230h+var_1D8]
0x180085d70  mov     rcx, [rax]
0x180085d73  mov     rbx, [rcx+20h]
0x180085d77  lea     rdx, aIpprotocol; "IPProtocol"
0x180085d7e  lea     rcx, [rbp+130h+bstrString]; this
0x180085d82  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180085d87  nop
0x180085d88  xor     esi, esi
0x180085d8a  mov     [rsp+230h+var_208], rsi
0x180085d8f  mov     qword ptr [rsp+230h+var_210], rsi
0x180085d94  lea     r9, [rsp+230h+var_1C8]
0x180085d99  xor     r8d, r8d
0x180085d9c  mov     rdx, [rax]
0x180085d9f  mov     rcx, [rsp+230h+var_1D8]
0x180085da4  mov     rax, rbx
0x180085da7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085dac  mov     ebx, eax
0x180085dae  mov     rcx, [rbp+130h+bstrString]; bstrString
0x180085db2  call    cs:__imp_SysFreeString
0x180085db9  nop     dword ptr [rax+rax+00h]
0x180085dbe  test    ebx, ebx
0x180085dc0  js      loc_1800860A7
0x180085dc6  mov     r9d, [r13+4]
0x180085dca  movzx   eax, byte ptr [rsp+230h+var_1C8+8]
0x180085dcf  cmp     r9d, eax
0x180085dd2  jz      short loc_180085E28
0x180085dd4  mov     rcx, cs:WPP_GLOBAL_Control
0x180085ddb  lea     rax, WPP_GLOBAL_Control
0x180085de2  cmp     rcx, rax
0x180085de5  jz      loc_180085B62
0x180085deb  test    dword ptr [rcx+1Ch], 200h
0x180085df2  jz      loc_180085B62
0x180085df8  cmp     byte ptr [rcx+19h], 5
0x180085dfc  jb      loc_180085B62
0x180085e02  lea     edx, [rsi+2Fh]
0x180085e05  lea     r8, WPP_3d36977ad8ca33d40382d35fc3f7adf2_Traceguids
0x180085e0c  mov     rcx, [rcx+10h]
0x180085e10  call    WPP_SF_d
0x180085e15  mov     rcx, cs:WPP_GLOBAL_Control
0x180085e1c  lea     rax, WPP_GLOBAL_Control
0x180085e23  jmp     loc_180085B62
0x180085e28  lea     rcx, [rsp+230h+var_1C8]; pvarg
0x180085e2d  call    cs:__imp_VariantClear
0x180085e34  nop     dword ptr [rax+rax+00h]
0x180085e39  mov     rax, [rsp+230h+var_1D8]
0x180085e3e  mov     rcx, [rax]
0x180085e41  mov     rbx, [rcx+20h]
0x180085e45  lea     rdx, aPort; "Port"
0x180085e4c  lea     rcx, [rsp+230h+var_1F0]; this
0x180085e51  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180085e56  nop
0x180085e57  mov     [rsp+230h+var_208], rsi
0x180085e5c  mov     qword ptr [rsp+230h+var_210], rsi
0x180085e61  lea     r9, [rsp+230h+var_1C8]
0x180085e66  xor     r8d, r8d
0x180085e69  mov     rdx, [rax]
0x180085e6c  mov     rcx, [rsp+230h+var_1D8]
0x180085e71  mov     rax, rbx
0x180085e74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085e79  mov     ebx, eax
0x180085e7b  mov     rcx, [rsp+230h+var_1F0]; bstrString
0x180085e80  call    cs:__imp_SysFreeString
  ... truncated ...
```
