# ActivateFileAssociationW

- ea: `0x180005400`
- end: `0x1800060ce`
- name: `ActivateFileAssociationW`
- size: `3278`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180005230`

## callees

- `0x1800019f8`
- `0x180001a64`
- `0x180001ad0`
- `0x180001e84`
- `0x180002238`
- `0x180002604`
- `0x1800037a0`
- `0x180003e88`
- `0x18000444c`
- `0x180005400`
- `0x180007928`
- `0x180012b30`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1800058c0`
- `ADVAPI32!RegOpenKeyExW` at `0x1800058c0`
- `ADVAPI32!RegCloseKey` at `0x1800058f1`
- `ADVAPI32!RegCloseKey` at `0x1800059d4`
- `ADVAPI32!RegCloseKey` at `0x180005a47`
- `ADVAPI32!RegCloseKey` at `0x180005bb9`
- `ADVAPI32!RegCloseKey` at `0x180005d6c`
- `ADVAPI32!RegCloseKey` at `0x180005ec6`
- `ADVAPI32!RegCloseKey` at `0x1800058f1`
- `ADVAPI32!RegCloseKey` at `0x1800059d4`
- `ADVAPI32!RegCloseKey` at `0x180005a47`
- `ADVAPI32!RegCloseKey` at `0x180005bb9`
- `ADVAPI32!RegCloseKey` at `0x180005d6c`
- `ADVAPI32!RegCloseKey` at `0x180005ec6`
- `OLEAUT32!__imp_VariantInit` at `0x180005cd6`
- `OLEAUT32!__imp_VariantInit` at `0x180005cd6`
- `OLEAUT32!__imp_VariantClear` at `0x180005cfd`
- `OLEAUT32!__imp_VariantClear` at `0x180005e57`
- `OLEAUT32!__imp_VariantClear` at `0x180005fad`
- `OLEAUT32!__imp_VariantClear` at `0x18000603d`
- `OLEAUT32!__imp_VariantClear` at `0x180006057`
- `OLEAUT32!__imp_VariantClear` at `0x180005cfd`
- `OLEAUT32!__imp_VariantClear` at `0x180005e57`
- `OLEAUT32!__imp_VariantClear` at `0x180005fad`
- `OLEAUT32!__imp_VariantClear` at `0x18000603d`
- `OLEAUT32!__imp_VariantClear` at `0x180006057`

## string_xrefs

- `0x180006023`: `ActivateApplicationExtension`

## pseudocode

```c
// Hidden C++ exception states: #wind=28
__int64 __fastcall ActivateFileAssociationW(unsigned __int16 *a1)
{
  const struct std::nothrow_t *v1; // rdx
  signed int Value; // edi
  const struct std::nothrow_t *v3; // rdx
  const struct std::nothrow_t *v4; // rdx
  __int64 v5; // rdx
  unsigned __int16 *v6; // rax
  unsigned __int16 *v7; // rcx
  __int64 v8; // rdx
  unsigned __int16 *v9; // rax
  LSTATUS v10; // eax
  const struct std::nothrow_t *v11; // rdx
  HKEY v12; // rbx
  const struct std::nothrow_t *v13; // rdx
  const struct std::nothrow_t *v14; // rdx
  const struct std::nothrow_t *v15; // rdx
  const struct std::nothrow_t *v16; // rdx
  const struct std::nothrow_t *v17; // rdx
  void **v19; // [rsp+30h] [rbp-D0h] BYREF
  void **v20; // [rsp+38h] [rbp-C8h]
  unsigned __int16 *v21; // [rsp+40h] [rbp-C0h]
  int v22; // [rsp+48h] [rbp-B8h]
  int v23; // [rsp+50h] [rbp-B0h]
  void **v24; // [rsp+58h] [rbp-A8h] BYREF
  void **v25; // [rsp+60h] [rbp-A0h]
  OLECHAR *psz; // [rsp+68h] [rbp-98h]
  int v27; // [rsp+70h] [rbp-90h]
  int v28; // [rsp+78h] [rbp-88h]
  void **v29; // [rsp+80h] [rbp-80h] BYREF
  void **v30; // [rsp+88h] [rbp-78h]
  LPCWSTR lpSubKey; // [rsp+90h] [rbp-70h]
  int v32; // [rsp+98h] [rbp-68h]
  int v33; // [rsp+A0h] [rbp-60h]
  void **v34; // [rsp+A8h] [rbp-58h] BYREF
  HKEY hKey; // [rsp+B0h] [rbp-50h]
  void **v36; // [rsp+B8h] [rbp-48h]
  void **v37; // [rsp+C0h] [rbp-40h]
  void *v38; // [rsp+C8h] [rbp-38h]
  int v39; // [rsp+D0h] [rbp-30h]
  int v40; // [rsp+D8h] [rbp-28h]
  void **v41; // [rsp+E0h] [rbp-20h] BYREF
  void **v42; // [rsp+E8h] [rbp-18h]
  OLECHAR *v43; // [rsp+F0h] [rbp-10h]
  int v44; // [rsp+F8h] [rbp-8h]
  int v45; // [rsp+100h] [rbp+0h]
  void **v46; // [rsp+108h] [rbp+8h] BYREF
  void **v47; // [rsp+110h] [rbp+10h]
  void *v48; // [rsp+118h] [rbp+18h]
  int v49; // [rsp+120h] [rbp+20h]
  int v50; // [rsp+128h] [rbp+28h]
  void **v51; // [rsp+130h] [rbp+30h] BYREF
  void **v52; // [rsp+138h] [rbp+38h]
  OLECHAR *v53; // [rsp+140h] [rbp+40h]
  int v54; // [rsp+148h] [rbp+48h]
  int v55; // [rsp+150h] [rbp+50h]
  void **v56; // [rsp+158h] [rbp+58h] BYREF
  VARIANTARG pvarg; // [rsp+160h] [rbp+60h] BYREF
  _QWORD v58[2]; // [rsp+178h] [rbp+78h] BYREF
  struct tagVARIANT *v59; // [rsp+188h] [rbp+88h]
  int v60; // [rsp+190h] [rbp+90h]
  unsigned int v61; // [rsp+198h] [rbp+98h]
  HKEY phkResult; // [rsp+1D8h] [rbp+D8h] BYREF

  v46 = &Dfdll::CString::`vftable';
  v48 = 0;
  v49 = 0;
  v47 = &Dfdll::CBuffer<unsigned short>::`vftable';
  v50 = 0;
  v19 = &Dfdll::CString::`vftable';
  v21 = 0;
  v22 = 0;
  v20 = &Dfdll::CBuffer<unsigned short>::`vftable';
  v23 = 0;
  v24 = &Dfdll::CString::`vftable';
  psz = 0;
  v27 = 0;
  v25 = &Dfdll::CBuffer<unsigned short>::`vftable';
  v28 = 0;
  Value = Dfdll::CString::Assign((Dfdll::CString *)&v46, a1);
  if ( Value < 0 )
  {
    psz = 0;
    v27 = 0;
    v25 = &Dfdll::CObject::`vftable';
    v24 = &Dfdll::CObject::`vftable';
    v21 = 0;
    v22 = 0;
    v20 = &Dfdll::CObject::`vftable';
    v19 = &Dfdll::CObject::`vftable';
    v46 = &Dfdll::CString::`vftable';
    v47 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v48 )
      operator delete(v48, v1);
    return (unsigned int)Value;
  }
  Value = Dfdll::CString::Split(
            (Dfdll::CString *)&v46,
            Dfdll::Constants::Strings::BlankSpace,
            (struct Dfdll::CString *)&v19,
            (struct Dfdll::CString *)&v24);
  if ( Value < 0 )
  {
    v24 = &Dfdll::CString::`vftable';
    v25 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( psz )
      operator delete(psz, v3);
    psz = 0;
    v27 = 0;
    v25 = &Dfdll::CObject::`vftable';
    v24 = &Dfdll::CObject::`vftable';
    v19 = &Dfdll::CString::`vftable';
    v20 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v21 )
      operator delete(v21, v3);
    v21 = 0;
    v22 = 0;
    v20 = &Dfdll::CObject::`vftable';
    v19 = &Dfdll::CObject::`vftable';
    v46 = &Dfdll::CString::`vftable';
    v47 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v48 )
      operator delete(v48, v3);
    return (unsigned int)Value;
  }
  v29 = &Dfdll::CString::`vftable';
  lpSubKey = 0;
  v32 = 0;
  v30 = &Dfdll::CBuffer<unsigned short>::`vftable';
  v33 = 0;
  Value = Dfdll::CString::Assign((Dfdll::CString *)&v29, Dfdll::Constants::Strings::ClassesCLSID);
  if ( Value < 0 )
  {
    v29 = &Dfdll::CString::`vftable';
    v30 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( lpSubKey )
      operator delete((void *)lpSubKey, v4);
    lpSubKey = 0;
    v32 = 0;
    v30 = &Dfdll::CObject::`vftable';
    v29 = &Dfdll::CObject::`vftable';
    v24 = &Dfdll::CString::`vftable';
    v25 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( psz )
      operator delete(psz, v4);
    psz = 0;
    v27 = 0;
    v25 = &Dfdll::CObject::`vftable';
    v24 = &Dfdll::CObject::`vftable';
    v19 = &Dfdll::CString::`vftable';
    v20 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v21 )
      operator delete(v21, v4);
    v21 = 0;
    v22 = 0;
    v20 = &Dfdll::CObject::`vftable';
    v19 = &Dfdll::CObject::`vftable';
    v46 = &Dfdll::CString::`vftable';
    v47 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v48 )
      operator delete(v48, v4);
    return (unsigned int)Value;
  }
  if ( Dfdll::Constants::Strings::BackSlash )
  {
    v5 = 0x7FFFFFFF;
    v6 = Dfdll::Constants::Strings::BackSlash;
    do
    {
      if ( !*v6 )
        break;
      ++v6;
      --v5;
    }
    while ( v5 );
    Value = v5 == 0 ? 0x80070057 : 0;
    if ( !v5
      || (Value = Dfdll::CString::Append(
                    (Dfdll::CString *)&v29,
                    Dfdll::Constants::Strings::BackSlash,
                    v5 != 0 ? 0x7FFFFFFF - v5 : 0),
          Value < 0) )
    {
      v29 = &Dfdll::CString::`vftable';
      v30 = &Dfdll::CBuffer<unsigned short>::`vftable';
      if ( lpSubKey )
        operator delete((void *)lpSubKey, (const struct std::nothrow_t *)v5);
      lpSubKey = 0;
      v32 = 0;
      v30 = &Dfdll::CObject::`vftable';
      v29 = &Dfdll::CObject::`vftable';
      v24 = &Dfdll::CString::`vftable';
      v25 = &Dfdll::CBuffer<unsigned short>::`vftable';
      if ( psz )
        operator delete(psz, (const struct std::nothrow_t *)v5);
      psz = 0;
      v27 = 0;
      v25 = &Dfdll::CObject::`vftable';
      v24 = &Dfdll::CObject::`vftable';
      v19 = &Dfdll::CString::`vftable';
      v20 = &Dfdll::CBuffer<unsigned short>::`vftable';
      if ( v21 )
        operator delete(v21, (const struct std::nothrow_t *)v5);
      v21 = 0;
      v22 = 0;
      v20 = &Dfdll::CObject::`vftable';
      v19 = &Dfdll::CObject::`vftable';
      v46 = &Dfdll::CString::`vftable';
      v47 = &Dfdll::CBuffer<unsigned short>::`vftable';
      if ( v48 )
        operator delete(v48, (const struct std::nothrow_t *)v5);
      return (unsigned int)Value;
    }
  }
  v7 = v21;
  if ( v21 )
  {
    v8 = 0x7FFFFFFF;
    v9 = v21;
    do
    {
      if ( !*v9 )
        break;
      ++v9;
      --v8;
    }
    while ( v8 );
    Value = v8 == 0 ? 0x80070057 : 0;
    if ( !v8 )
      goto LABEL_45;
    Value = Dfdll::CString::Append((Dfdll::CString *)&v29, v21, v8 != 0 ? 0x7FFFFFFF - v8 : 0);
    if ( Value < 0 )
    {
      v7 = v21;
LABEL_45:
      v29 = &Dfdll::CString::`vftable';
      v30 = &Dfdll::CBuffer<unsigned short>::`vftable';
      if ( lpSubKey )
      {
        operator delete((void *)lpSubKey, (const struct std::nothrow_t *)v8);
        v7 = v21;
      }
      lpSubKey = 0;
      v32 = 0;
      v30 = &Dfdll::CObject::`vftable';
      v29 = &Dfdll::CObject::`vftable';
      v24 = &Dfdll::CString::`vftable';
      v25 = &Dfdll::CBuffer<unsigned short>::`vftable';
      if ( psz )
      {
        operator delete(psz, (const struct std::nothrow_t *)v8);
        v7 = v21;
      }
      psz = 0;
      v27 = 0;
      v25 = &Dfdll::CObject::`vftable';
      v24 = &Dfdll::CObject::`vftable';
      v19 = &Dfdll::CString::`vftable';
      v20 = &Dfdll::CBuffer<unsigned short>::`vftable';
      if ( v7 )
        operator delete(v7, (const struct std::nothrow_t *)v8);
      v21 = 0;
      v22 = 0;
      v20 = &Dfdll::CObject::`vftable';
      v19 = &Dfdll::CObject::`vftable';
      v46 = &Dfdll::CString::`vftable';
      v47 = &Dfdll::CBuffer<unsigned short>::`vftable';
      if ( v48 )
        operator delete(v48, (const struct std::nothrow_t *)v8);
      return (unsigned int)Value;
    }
  }
  v34 = &Dfdll::CRegKey::`vftable';
  hKey = 0;
  v36 = &Dfdll::CString::`vftable';
  v38 = 0;
  v39 = 0;
  v37 = &Dfdll::CBuffer<unsigned short>::`vftable';
  v40 = 0;
  phkResult = 0;
  v10 = RegOpenKeyExW(HKEY_CURRENT_USER, lpSubKey, 0, 0x2011Fu, &phkResult);
  if ( v10 )
  {
    Value = (unsigned __int16)v10 | 0x80070000;
    if ( v10 <= 0 )
      Value = v10;
    v34 = &Dfdll::CRegKey::`vftable';
    if ( hKey )
      RegCloseKey(hKey);
    hKey = 0;
    v36 = &Dfdll::CString::`vftable';
    v37 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v38 )
      operator delete(v38, v11);
    v38 = 0;
    v39 = 0;
    v37 = &Dfdll::CObject::`vftable';
    v36 = &Dfdll::CObject::`vftable';
    v34 = &Dfdll::CObject::`vftable';
    v29 = &Dfdll::CString::`vftable';
    v30 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( lpSubKey )
      operator delete((void *)lpSubKey, v11);
    lpSubKey = 0;
    v32 = 0;
    v30 = &Dfdll::CObject::`vftable';
    v29 = &Dfdll::CObject::`vftable';
    v24 = &Dfdll::CString::`vftable';
    v25 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( psz )
      operator delete(psz, v11);
    psz = 0;
    v27 = 0;
    v25 = &Dfdll::CObject::`vftable';
    v24 = &Dfdll::CObject::`vftable';
    v19 = &Dfdll::CString::`vftable';
    v20 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v21 )
      operator delete(v21, v11);
    v21 = 0;
    v22 = 0;
    v20 = &Dfdll::CObject::`vftable';
    v19 = &Dfdll::CObject::`vftable';
    v46 = &Dfdll::CString::`vftable';
    v47 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v48 )
      operator delete(v48, v11);
    return (unsigned int)Value;
  }
  v12 = phkResult;
  if ( hKey )
    RegCloseKey(hKey);
  hKey = v12;
  v41 = &Dfdll::CString::`vftable';
  v43 = 0;
  v44 = 0;
  v42 = &Dfdll::CBuffer<unsigned short>::`vftable';
  v45 = 0;
  Value = Dfdll::CRegKey::QueryValue(
            (Dfdll::CRegKey *)&v34,
            Dfdll::Constants::Strings::AppId,
            (struct Dfdll::CString *)&v41);
  if ( Value < 0 )
  {
    v41 = &Dfdll::CString::`vftable';
    v42 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v43 )
      operator delete(v43, v13);
    v43 = 0;
    v44 = 0;
    v42 = &Dfdll::CObject::`vftable';
    v41 = &Dfdll::CObject::`vftable';
    v34 = &Dfdll::CRegKey::`vftable';
    if ( hKey )
      RegCloseKey(hKey);
    hKey = 0;
    v36 = &Dfdll::CString::`vftable';
    v37 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v38 )
      operator delete(v38, v13);
    v38 = 0;
    v39 = 0;
    v37 = &Dfdll::CObject::`vftable';
    v36 = &Dfdll::CObject::`vftable';
    v34 = &Dfdll::CObject::`vftable';
    v29 = &Dfdll::CString::`vftable';
    v30 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( lpSubKey )
      operator delete((void *)lpSubKey, v13);
    lpSubKey = 0;
    v32 = 0;
    v30 = &Dfdll::CObject::`vftable';
    v29 = &Dfdll::CObject::`vftable';
    v24 = &Dfdll::CString::`vftable';
    v25 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( psz )
      operator delete(psz, v13);
    psz = 0;
    v27 = 0;
    v25 = &Dfdll::CObject::`vftable';
    v24 = &Dfdll::CObject::`vftable';
    v19 = &Dfdll::CString::`vftable';
    v20 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v21 )
      operator delete(v21, v13);
    v21 = 0;
    v22 = 0;
    v20 = &Dfdll::CObject::`vftable';
    v19 = &Dfdll::CObject::`vftable';
    v46 = &Dfdll::CString::`vftable';
    v47 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v48 )
      operator delete(v48, v13);
    return (unsigned int)Value;
  }
  v51 = &Dfdll::CString::`vftable';
  v53 = 0;
  v54 = 0;
  v52 = &Dfdll::CBuffer<unsigned short>::`vftable';
  v55 = 0;
  if ( Dfdll::CRegKey::QueryValue(
         (Dfdll::CRegKey *)&v34,
         Dfdll::Constants::Strings::DeploymentProviderUrl,
         (struct Dfdll::CString *)&v51) < 0 )
  {
    Value = Dfdll::CString::Assign((Dfdll::CString *)&v51, Dfdll::Constants::Strings::BlankString);
    if ( Value < 0 )
    {
      v51 = &Dfdll::CString::`vftable';
      v52 = &Dfdll::CBuffer<unsigned short>::`vftable';
      if ( v53 )
        operator delete(v53, v14);
      v53 = 0;
      v54 = 0;
      v52 = &Dfdll::CObject::`vftable';
      v51 = &Dfdll::CObject::`vftable';
      v41 = &Dfdll::CString::`vftable';
      v42 = &Dfdll::CBuffer<unsigned short>::`vftable';
      if ( v43 )
        operator delete(v43, v14);
      v43 = 0;
      v44 = 0;
      v42 = &Dfdll::CObject::`vftable';
      v41 = &Dfdll::CObject::`vftable';
      v34 = &Dfdll::CRegKey::`vftable';
      if ( hKey )
        RegCloseKey(hKey);
      hKey = 0;
      v36 = &Dfdll::CString::`vftable';
      v37 = &Dfdll::CBuffer<unsigned short>::`vftable';
      if ( v38 )
        operator delete(v38, v14);
      v38 = 0;
      v39 = 0;
      v37 = &Dfdll::CObject::`vftable';
      v36 = &Dfdll::CObject::`vftable';
      v34 = &Dfdll::CObject::`vftable';
      v29 = &Dfdll::CString::`vftable';
      v30 = &Dfdll::CBuffer<unsigned short>::`vftable';
      if ( lpSubKey )
        operator delete((void *)lpSubKey, v14);
      lpSubKey = 0;
      v32 = 0;
      v30 = &Dfdll::CObject::`vftable';
      v29 = &Dfdll::CObject::`vftable';
      v24 = &Dfdll::CString::`vftable';
      v25 = &Dfdll::CBuffer<unsigned short>::`vftable';
      if ( psz )
        operator delete(psz, v14);
      psz = 0;
      v27 = 0;
      v25 = &Dfdll::CObject::`vftable';
      v24 = &Dfdll::CObject::`vftable';
      v19 = &Dfdll::CString::`vftable';
      v20 = &Dfdll::CBuffer<unsigned short>::`vftable';
      if ( v21 )
        operator delete(v21, v14);
      v21 = 0;
      v22 = 0;
      v20 = &Dfdll::CObject::`vftable';
      v19 = &Dfdll::CObject::`vftable';
      v46 = &Dfdll::CString::`vftable';
      v47 = &Dfdll::CBuffer<unsigned short>::`vftable';
      if ( v48 )
        operator delete(v48, v14);
      return (unsigned int)Value;
    }
  }
  if ( (int)TryActivatingFromFileAssociation((struct Dfdll::CString *)&v41, (struct Dfdll::CString *)&v24) >= 0 )
    goto LABEL_153;
  v58[0] = &Dfdll::CVariantArray::`vftable';
  v59 = 0;
  v60 = 0;
  v58[1] = &Dfdll::CVariantBufferBase::`vftable';
  v61 = 0;
  v56 = &Dfdll::CVariant::`vftable';
  VariantInit(&pvarg);
  Value = Dfdll::CVariantArray::Add((Dfdll::CVariantArray *)v58, psz);
  if ( Value < 0 )
  {
    v56 = &Dfdll::CVariant::`vftable';
    VariantClear(&pvarg);
    Dfdll::CVariantArray::~CVariantArray((Dfdll::CVariantArray *)v58);
    v51 = &Dfdll::CString::`vftable';
    v52 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v53 )
      operator delete(v53, v15);
    v53 = 0;
    v54 = 0;
    v52 = &Dfdll::CObject::`vftable';
    v51 = &Dfdll::CObject::`vftable';
    v41 = &Dfdll::CString::`vftable';
    v42 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v43 )
      operator delete(v43, v15);
    v43 = 0;
    v44 = 0;
    v42 = &Dfdll::CObject::`vftable';
    v41 = &Dfdll::CObject::`vftable';
    v34 = &Dfdll::CRegKey::`vftable';
    if ( hKey )
      RegCloseKey(hKey);
    hKey = 0;
    v36 = &Dfdll::CString::`vftable';
    v37 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v38 )
      operator delete(v38, v15);
    v38 = 0;
    v39 = 0;
    v37 = &Dfdll::CObject::`vftable';
    v36 = &Dfdll::CObject::`vftable';
    v34 = &Dfdll::CObject::`vftable';
    v29 = &Dfdll::CString::`vftable';
    v30 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( lpSubKey )
      operator delete((void *)lpSubKey, v15);
    lpSubKey = 0;
    v32 = 0;
    v30 = &Dfdll::CObject::`vftable';
    v29 = &Dfdll::CObject::`vftable';
    v24 = &Dfdll::CString::`vftable';
    v25 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( psz )
      operator delete(psz, v15);
    psz = 0;
    v27 = 0;
    v25 = &Dfdll::CObject::`vftable';
    v24 = &Dfdll::CObject::`vftable';
    v19 = &Dfdll::CString::`vftable';
    v20 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v21 )
      operator delete(v21, v15);
    v21 = 0;
    v22 = 0;
    v20 = &Dfdll::CObject::`vftable';
    v19 = &Dfdll::CObject::`vftable';
    v46 = &Dfdll::CString::`vftable';
    v47 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v48 )
      operator delete(v48, v15);
    return (unsigned int)Value;
  }
  Value = Dfdll::CVariantArray::Add((Dfdll::CVariantArray *)v58, v53);
  if ( Value >= 0 )
  {
    Value = Dfdll::CVariantArray::Add((Dfdll::CVariantArray *)v58, v43);
    if ( Value < 0 )
    {
      v56 = &Dfdll::CVariant::`vftable';
      VariantClear(&pvarg);
      Dfdll::CVariantArray::~CVariantArray((Dfdll::CVariantArray *)v58);
      v51 = &Dfdll::CString::`vftable';
      v52 = &Dfdll::CBuffer<unsigned short>::`vftable';
      if ( v53 )
        operator delete(v53, v17);
      v53 = 0;
      v54 = 0;
      v52 = &Dfdll::CObject::`vftable';
      v51 = &Dfdll::CObject::`vftable';
      v41 = &Dfdll::CString::`vftable';
      v42 = &Dfdll::CBuffer<unsigned short>::`vftable';
      if ( v43 )
        operator delete(v43, v17);
      v43 = 0;
      v44 = 0;
      v42 = &Dfdll::CObject::`vftable';
      v41 = &Dfdll::CObject::`vftable';
      goto LABEL_155;
    }
    Value = InvokeServer(L"ActivateApplicationExtension", v59, v61, (struct Dfdll::CVariant *)&v56);
    if ( Value < 0 )
    {
      v56 = &Dfdll::CVariant::`vftable';
      VariantClear(&pvarg);
      Dfdll::CVariantArray::~CVariantArray((Dfdll::CVariantArray *)v58);
LABEL_154:
      Dfdll::CString::~CString((Dfdll::CString *)&v51);
      Dfdll::CString::~CString((Dfdll::CString *)&v41);
LABEL_155:
      Dfdll::CRegKey::~CRegKey((Dfdll::CRegKey *)&v34);
      Dfdll::CString::~CString((Dfdll::CString *)&v29);
      Dfdll::CString::~CString((Dfdll::CString *)&v24);
      Dfdll::CString::~CString((Dfdll::CString *)&v19);
      Dfdll::CString::~CString((Dfdll::CString *)&v46);
      return (unsigned int)Value;
    }
    v56 = &Dfdll::CVariant::`vftable';
    VariantClear(&pvarg);
    Dfdll::CVariantArray::~CVariantArray((Dfdll::CVariantArray *)v58);
LABEL_153:
    Value = 0;
    goto LABEL_154;
  }
  v56 = &Dfdll::CVariant::`vftable';
  VariantClear(&pvarg);
  Dfdll::CVariantArray::~CVariantArray((Dfdll::CVariantArray *)v58);
  v51 = &Dfdll::CString::`vftable';
  v52 = &Dfdll::CBuffer<unsigned short>::`vftable';
  if ( v53 )
    operator delete(v53, v16);
  v53 = 0;
  v54 = 0;
  v52 = &Dfdll::CObject::`vftable';
  v51 = &Dfdll::CObject::`vftable';
  v41 = &Dfdll::CString::`vftable';
  v42 = &Dfdll::CBuffer<unsigned short>::`vftable';
  if ( v43 )
    operator delete(v43, v16);
  v43 = 0;
  v44 = 0;
  v42 = &Dfdll::CObject::`vftable';
  v41 = &Dfdll::CObject::`vftable';
  v34 = &Dfdll::CRegKey::`vftable';
  if ( hKey )
    RegCloseKey(hKey);
  hKey = 0;
  v36 = &Dfdll::CString::`vftable';
  v37 = &Dfdll::CBuffer<unsigned short>::`vftable';
  if ( v38 )
    operator delete(v38, v16);
  v38 = 0;
  v39 = 0;
  v37 = &Dfdll::CObject::`vftable';
  v36 = &Dfdll::CObject::`vftable';
  v34 = &Dfdll::CObject::`vftable';
  v29 = &Dfdll::CString::`vftable';
  v30 = &Dfdll::CBuffer<unsigned short>::`vftable';
  if ( lpSubKey )
    operator delete((void *)lpSubKey, v16);
  lpSubKey = 0;
  v32 = 0;
  v30 = &Dfdll::CObject::`vftable';
  v29 = &Dfdll::CObject::`vftable';
  v24 = &Dfdll::CString::`vftable';
  v25 = &Dfdll::CBuffer<unsigned short>::`vftable';
  if ( psz )
    operator delete(psz, v16);
  psz = 0;
  v27 = 0;
  v25 = &Dfdll::CObject::`vftable';
  v24 = &Dfdll::CObject::`vftable';
  v19 = &Dfdll::CString::`vftable';
  v20 = &Dfdll::CBuffer<unsigned short>::`vftable';
  if ( v21 )
    operator delete(v21, v16);
  v21 = 0;
  v22 = 0;
  v20 = &Dfdll::CObject::`vftable';
  v19 = &Dfdll::CObject::`vftable';
  v46 = &Dfdll::CString::`vftable';
  v47 = &Dfdll::CBuffer<unsigned short>::`vftable';
  if ( v48 )
    operator delete(v48, v16);
  return (unsigned int)Value;
}

```

## disassembly

```asm
0x180005400  mov     [rsp-8+arg_0], rbx
0x180005405  mov     [rsp-8+arg_10], rsi
0x18000540a  push    rbp
0x18000540b  push    rdi
0x18000540c  push    r12
0x18000540e  push    r14
0x180005410  push    r15
0x180005412  lea     rbp, [rsp-0A0h]
0x18000541a  sub     rsp, 1A0h
0x180005421  lea     r14, ??_7CString@Dfdll@@6B@; const Dfdll::CString::`vftable'
0x180005428  mov     [rbp+0C0h+var_B8], r14
0x18000542c  xor     esi, esi
0x18000542e  mov     [rbp+0C0h+var_A8], rsi
0x180005432  mov     [rbp+0C0h+var_A0], esi
0x180005435  lea     r15, ??_7?$CBuffer@G@Dfdll@@6B@; const Dfdll::CBuffer<ushort>::`vftable'
0x18000543c  mov     [rbp+0C0h+var_B0], r15
0x180005440  mov     [rbp+0C0h+var_98], esi
0x180005443  mov     [rsp+1C0h+var_190], r14
0x180005448  mov     [rsp+1C0h+var_180], rsi
0x18000544d  mov     [rsp+1C0h+var_178], esi
0x180005451  mov     [rsp+1C0h+var_188], r15
0x180005456  mov     [rsp+1C0h+var_170], esi
0x18000545a  mov     [rsp+1C0h+var_168], r14
0x18000545f  mov     [rsp+1C0h+psz], rsi
0x180005464  mov     [rsp+1C0h+var_150], esi
0x180005468  mov     [rsp+1C0h+var_160], r15
0x18000546d  mov     [rsp+1C0h+var_148], esi
0x180005471  mov     rdx, rcx; unsigned __int16 *
0x180005474  lea     rcx, [rbp+0C0h+var_B8]; this
0x180005478  call    ?Assign@CString@Dfdll@@QEAAJPEBG@Z; Dfdll::CString::Assign(ushort const *)
0x18000547d  mov     edi, eax
0x18000547f  test    eax, eax
0x180005481  jns     short loc_1800054FE
0x180005483  mov     [rsp+1C0h+var_168], r14
0x180005488  mov     [rsp+1C0h+var_160], r15
0x18000548d  mov     rcx, [rsp+1C0h+psz]; void *
0x180005492  test    rcx, rcx
0x180005495  jz      short loc_18000549C
0x180005497  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000549c  mov     [rsp+1C0h+psz], rsi
0x1800054a1  mov     [rsp+1C0h+var_150], esi
0x1800054a5  lea     rbx, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x1800054ac  mov     [rsp+1C0h+var_160], rbx
0x1800054b1  mov     [rsp+1C0h+var_168], rbx
0x1800054b6  mov     [rsp+1C0h+var_190], r14
0x1800054bb  mov     [rsp+1C0h+var_188], r15
0x1800054c0  mov     rcx, [rsp+1C0h+var_180]; void *
0x1800054c5  test    rcx, rcx
0x1800054c8  jz      short loc_1800054CF
0x1800054ca  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800054cf  mov     [rsp+1C0h+var_180], rsi
0x1800054d4  mov     [rsp+1C0h+var_178], esi
0x1800054d8  mov     [rsp+1C0h+var_188], rbx
0x1800054dd  mov     [rsp+1C0h+var_190], rbx
0x1800054e2  mov     [rbp+0C0h+var_B8], r14
0x1800054e6  mov     [rbp+0C0h+var_B0], r15
0x1800054ea  mov     rcx, [rbp+0C0h+var_A8]; void *
0x1800054ee  test    rcx, rcx
0x1800054f1  jz      short loc_1800054F9
0x1800054f3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800054f8  nop
0x1800054f9  jmp     loc_1800060B0
0x1800054fe  lea     r9, [rsp+1C0h+var_168]; struct Dfdll::CString *
0x180005503  lea     r8, [rsp+1C0h+var_190]; struct Dfdll::CString *
0x180005508  mov     rdx, cs:?BlankSpace@Strings@Constants@Dfdll@@3QEAGEA; unsigned __int16 *
0x18000550f  lea     rcx, [rbp+0C0h+var_B8]; this
0x180005513  call    ?Split@CString@Dfdll@@QEAAJPEBGAEAV12@1@Z; Dfdll::CString::Split(ushort const *,Dfdll::CString &,Dfdll::CString &)
0x180005518  mov     edi, eax
0x18000551a  test    eax, eax
0x18000551c  jns     short loc_180005599
0x18000551e  mov     [rsp+1C0h+var_168], r14
0x180005523  mov     [rsp+1C0h+var_160], r15
0x180005528  mov     rcx, [rsp+1C0h+psz]; void *
0x18000552d  test    rcx, rcx
0x180005530  jz      short loc_180005537
0x180005532  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180005537  mov     [rsp+1C0h+psz], rsi
0x18000553c  mov     [rsp+1C0h+var_150], esi
0x180005540  lea     rbx, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x180005547  mov     [rsp+1C0h+var_160], rbx
0x18000554c  mov     [rsp+1C0h+var_168], rbx
0x180005551  mov     [rsp+1C0h+var_190], r14
0x180005556  mov     [rsp+1C0h+var_188], r15
0x18000555b  mov     rcx, [rsp+1C0h+var_180]; void *
0x180005560  test    rcx, rcx
0x180005563  jz      short loc_18000556A
0x180005565  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000556a  mov     [rsp+1C0h+var_180], rsi
0x18000556f  mov     [rsp+1C0h+var_178], esi
0x180005573  mov     [rsp+1C0h+var_188], rbx
0x180005578  mov     [rsp+1C0h+var_190], rbx
0x18000557d  mov     [rbp+0C0h+var_B8], r14
0x180005581  mov     [rbp+0C0h+var_B0], r15
0x180005585  mov     rcx, [rbp+0C0h+var_A8]; void *
0x180005589  test    rcx, rcx
0x18000558c  jz      short loc_180005594
0x18000558e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180005593  nop
0x180005594  jmp     loc_1800060B0
0x180005599  mov     [rbp+0C0h+var_140], r14
0x18000559d  mov     [rbp+0C0h+lpSubKey], rsi
0x1800055a1  mov     [rbp+0C0h+var_128], esi
0x1800055a4  mov     [rbp+0C0h+var_138], r15
0x1800055a8  mov     [rbp+0C0h+var_120], esi
0x1800055ab  mov     rdx, cs:?ClassesCLSID@Strings@Constants@Dfdll@@3QEAGEA; unsigned __int16 *
0x1800055b2  lea     rcx, [rbp+0C0h+var_140]; this
0x1800055b6  call    ?Assign@CString@Dfdll@@QEAAJPEBG@Z; Dfdll::CString::Assign(ushort const *)
0x1800055bb  mov     edi, eax
0x1800055bd  test    eax, eax
0x1800055bf  jns     loc_180005665
0x1800055c5  mov     [rbp+0C0h+var_140], r14
0x1800055c9  mov     [rbp+0C0h+var_138], r15
0x1800055cd  mov     rcx, [rbp+0C0h+lpSubKey]; void *
0x1800055d1  test    rcx, rcx
0x1800055d4  jz      short loc_1800055DB
0x1800055d6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800055db  mov     [rbp+0C0h+lpSubKey], rsi
0x1800055df  mov     [rbp+0C0h+var_128], esi
0x1800055e2  lea     rbx, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x1800055e9  mov     [rbp+0C0h+var_138], rbx
0x1800055ed  mov     [rbp+0C0h+var_140], rbx
0x1800055f1  mov     [rsp+1C0h+var_168], r14
0x1800055f6  mov     [rsp+1C0h+var_160], r15
0x1800055fb  mov     rcx, [rsp+1C0h+psz]; void *
0x180005600  test    rcx, rcx
0x180005603  jz      short loc_18000560A
0x180005605  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000560a  mov     [rsp+1C0h+psz], rsi
0x18000560f  mov     [rsp+1C0h+var_150], esi
0x180005613  mov     [rsp+1C0h+var_160], rbx
0x180005618  mov     [rsp+1C0h+var_168], rbx
0x18000561d  mov     [rsp+1C0h+var_190], r14
0x180005622  mov     [rsp+1C0h+var_188], r15
0x180005627  mov     rcx, [rsp+1C0h+var_180]; void *
0x18000562c  test    rcx, rcx
0x18000562f  jz      short loc_180005636
0x180005631  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180005636  mov     [rsp+1C0h+var_180], rsi
0x18000563b  mov     [rsp+1C0h+var_178], esi
0x18000563f  mov     [rsp+1C0h+var_188], rbx
0x180005644  mov     [rsp+1C0h+var_190], rbx
0x180005649  mov     [rbp+0C0h+var_B8], r14
0x18000564d  mov     [rbp+0C0h+var_B0], r15
0x180005651  mov     rcx, [rbp+0C0h+var_A8]; void *
0x180005655  test    rcx, rcx
0x180005658  jz      short loc_180005660
0x18000565a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000565f  nop
0x180005660  jmp     loc_1800060B0
0x180005665  mov     r9, cs:?BackSlash@Strings@Constants@Dfdll@@3QEAGEA; ushort * Dfdll::Constants::Strings::BackSlash
0x18000566c  mov     ebx, 7FFFFFFFh
0x180005671  mov     r12d, 80070057h
0x180005677  test    r9, r9
0x18000567a  jz      loc_18000576E
0x180005680  mov     edx, ebx
0x180005682  mov     rax, r9
0x180005685  cmp     [rax], si
0x180005688  jz      short loc_180005694
0x18000568a  add     rax, 2
0x18000568e  sub     rdx, 1
0x180005692  jnz     short loc_180005685
0x180005694  mov     rax, rdx
0x180005697  neg     rax
0x18000569a  sbb     edi, edi
0x18000569c  not     edi
0x18000569e  and     edi, r12d
0x1800056a1  mov     rax, rdx
0x1800056a4  mov     rcx, rbx
0x1800056a7  sub     rcx, rdx
0x1800056aa  neg     rax
0x1800056ad  sbb     r8, r8
0x1800056b0  and     r8, rcx; unsigned int
0x1800056b3  test    rdx, rdx
0x1800056b6  jz      short loc_1800056CE
0x1800056b8  mov     rdx, r9; unsigned __int16 *
0x1800056bb  lea     rcx, [rbp+0C0h+var_140]; this
0x1800056bf  call    ?Append@CString@Dfdll@@QEAAJPEBGI@Z; Dfdll::CString::Append(ushort const *,uint)
0x1800056c4  mov     edi, eax
0x1800056c6  test    eax, eax
0x1800056c8  jns     loc_18000576E
0x1800056ce  mov     [rbp+0C0h+var_140], r14
0x1800056d2  mov     [rbp+0C0h+var_138], r15
0x1800056d6  mov     rcx, [rbp+0C0h+lpSubKey]; void *
0x1800056da  test    rcx, rcx
0x1800056dd  jz      short loc_1800056E4
0x1800056df  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800056e4  mov     [rbp+0C0h+lpSubKey], rsi
0x1800056e8  mov     [rbp+0C0h+var_128], esi
0x1800056eb  lea     rbx, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x1800056f2  mov     [rbp+0C0h+var_138], rbx
0x1800056f6  mov     [rbp+0C0h+var_140], rbx
0x1800056fa  mov     [rsp+1C0h+var_168], r14
0x1800056ff  mov     [rsp+1C0h+var_160], r15
0x180005704  mov     rcx, [rsp+1C0h+psz]; void *
0x180005709  test    rcx, rcx
0x18000570c  jz      short loc_180005713
0x18000570e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180005713  mov     [rsp+1C0h+psz], rsi
0x180005718  mov     [rsp+1C0h+var_150], esi
0x18000571c  mov     [rsp+1C0h+var_160], rbx
0x180005721  mov     [rsp+1C0h+var_168], rbx
0x180005726  mov     [rsp+1C0h+var_190], r14
0x18000572b  mov     [rsp+1C0h+var_188], r15
0x180005730  mov     rcx, [rsp+1C0h+var_180]; void *
0x180005735  test    rcx, rcx
0x180005738  jz      short loc_18000573F
0x18000573a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000573f  mov     [rsp+1C0h+var_180], rsi
0x180005744  mov     [rsp+1C0h+var_178], esi
0x180005748  mov     [rsp+1C0h+var_188], rbx
0x18000574d  mov     [rsp+1C0h+var_190], rbx
0x180005752  mov     [rbp+0C0h+var_B8], r14
0x180005756  mov     [rbp+0C0h+var_B0], r15
0x18000575a  mov     rcx, [rbp+0C0h+var_A8]; void *
0x18000575e  test    rcx, rcx
0x180005761  jz      short loc_180005769
0x180005763  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180005768  nop
0x180005769  jmp     loc_1800060B0
0x18000576e  mov     rcx, [rsp+1C0h+var_180]
0x180005773  test    rcx, rcx
0x180005776  jz      loc_180005878
0x18000577c  mov     rdx, rbx
0x18000577f  mov     rax, rcx
0x180005782  cmp     [rax], si
0x180005785  jz      short loc_180005791
0x180005787  add     rax, 2
0x18000578b  sub     rdx, 1
0x18000578f  jnz     short loc_180005782
0x180005791  mov     rax, rdx
0x180005794  neg     rax
0x180005797  sbb     edi, edi
0x180005799  not     edi
0x18000579b  and     edi, r12d
0x18000579e  mov     rax, rdx
0x1800057a1  sub     rbx, rdx
0x1800057a4  neg     rax
0x1800057a7  sbb     r8, r8
0x1800057aa  and     r8, rbx; unsigned int
0x1800057ad  test    rdx, rdx
0x1800057b0  jz      short loc_1800057CD
0x1800057b2  mov     rdx, rcx; unsigned __int16 *
0x1800057b5  lea     rcx, [rbp+0C0h+var_140]; this
0x1800057b9  call    ?Append@CString@Dfdll@@QEAAJPEBGI@Z; Dfdll::CString::Append(ushort const *,uint)
0x1800057be  mov     edi, eax
0x1800057c0  test    eax, eax
0x1800057c2  jns     loc_180005878
0x1800057c8  mov     rcx, [rsp+1C0h+var_180]
0x1800057cd  mov     [rbp+0C0h+var_140], r14
0x1800057d1  mov     [rbp+0C0h+var_138], r15
0x1800057d5  mov     rax, [rbp+0C0h+lpSubKey]
0x1800057d9  test    rax, rax
0x1800057dc  jz      short loc_1800057EB
0x1800057de  mov     rcx, rax; void *
0x1800057e1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800057e6  mov     rcx, [rsp+1C0h+var_180]
0x1800057eb  mov     [rbp+0C0h+lpSubKey], rsi
0x1800057ef  mov     [rbp+0C0h+var_128], esi
0x1800057f2  lea     rbx, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x1800057f9  mov     [rbp+0C0h+var_138], rbx
0x1800057fd  mov     [rbp+0C0h+var_140], rbx
0x180005801  mov     [rsp+1C0h+var_168], r14
0x180005806  mov     [rsp+1C0h+var_160], r15
0x18000580b  mov     rax, [rsp+1C0h+psz]
0x180005810  test    rax, rax
0x180005813  jz      short loc_180005822
0x180005815  mov     rcx, rax; void *
0x180005818  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000581d  mov     rcx, [rsp+1C0h+var_180]; void *
0x180005822  mov     [rsp+1C0h+psz], rsi
0x180005827  mov     [rsp+1C0h+var_150], esi
0x18000582b  mov     [rsp+1C0h+var_160], rbx
0x180005830  mov     [rsp+1C0h+var_168], rbx
0x180005835  mov     [rsp+1C0h+var_190], r14
0x18000583a  mov     [rsp+1C0h+var_188], r15
0x18000583f  test    rcx, rcx
0x180005842  jz      short loc_180005849
0x180005844  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180005849  mov     [rsp+1C0h+var_180], rsi
0x18000584e  mov     [rsp+1C0h+var_178], esi
0x180005852  mov     [rsp+1C0h+var_188], rbx
0x180005857  mov     [rsp+1C0h+var_190], rbx
0x18000585c  mov     [rbp+0C0h+var_B8], r14
0x180005860  mov     [rbp+0C0h+var_B0], r15
0x180005864  mov     rcx, [rbp+0C0h+var_A8]; void *
0x180005868  test    rcx, rcx
0x18000586b  jz      short loc_180005873
0x18000586d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180005872  nop
0x180005873  jmp     loc_1800060B0
0x180005878  lea     r12, ??_7CRegKey@Dfdll@@6B@; const Dfdll::CRegKey::`vftable'
0x18000587f  mov     [rbp+0C0h+var_118], r12
0x180005883  mov     [rbp+0C0h+hKey], rsi
0x180005887  mov     [rbp+0C0h+var_108], r14
0x18000588b  mov     [rbp+0C0h+var_F8], rsi
0x18000588f  mov     [rbp+0C0h+var_F0], esi
0x180005892  mov     [rbp+0C0h+var_100], r15
0x180005896  mov     [rbp+0C0h+var_E8], esi
0x180005899  mov     [rbp+0C0h+arg_8], rsi
0x1800058a0  lea     rax, [rbp+0C0h+arg_8]
  ... truncated ...
```
