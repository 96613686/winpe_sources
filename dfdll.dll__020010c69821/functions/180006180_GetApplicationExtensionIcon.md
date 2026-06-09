# GetApplicationExtensionIcon

- ea: `0x180006180`
- end: `0x180006e5e`
- name: `GetApplicationExtensionIcon`
- size: `3294`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned int, char *, unsigned int)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800019f8`
- `0x180001a64`
- `0x180002238`
- `0x180002604`
- `0x180002988`
- `0x180002af8`
- `0x180002ff8`
- `0x1800037a0`
- `0x180006180`
- `0x180008a14`
- `0x180008d34`
- `0x18000aa14`
- `0x180010ea8`
- `0x180012b30`
- `0x180012bd0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18000647c`
- `ADVAPI32!RegOpenKeyExW` at `0x18000647c`
- `ADVAPI32!RegCloseKey` at `0x1800064b2`
- `ADVAPI32!RegCloseKey` at `0x180006527`
- `ADVAPI32!RegCloseKey` at `0x1800065c0`
- `ADVAPI32!RegCloseKey` at `0x1800066c9`
- `ADVAPI32!RegCloseKey` at `0x1800067c4`
- `ADVAPI32!RegCloseKey` at `0x18000692f`
- `ADVAPI32!RegCloseKey` at `0x180006a4d`
- `ADVAPI32!RegCloseKey` at `0x180006b92`
- `ADVAPI32!RegCloseKey` at `0x1800064b2`
- `ADVAPI32!RegCloseKey` at `0x180006527`
- `ADVAPI32!RegCloseKey` at `0x1800065c0`
- `ADVAPI32!RegCloseKey` at `0x1800066c9`
- `ADVAPI32!RegCloseKey` at `0x1800067c4`
- `ADVAPI32!RegCloseKey` at `0x18000692f`
- `ADVAPI32!RegCloseKey` at `0x180006a4d`
- `ADVAPI32!RegCloseKey` at `0x180006b92`
- `KERNEL32!GetLastError` at `0x180006d92`
- `KERNEL32!GetLastError` at `0x180006d92`
- `KERNEL32!GetFileAttributesW` at `0x180006d87`
- `KERNEL32!GetFileAttributesW` at `0x180006d87`

## pseudocode

```c
// Hidden C++ exception states: #wind=28
__int64 __fastcall GetApplicationExtensionIcon(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned int a3,
        char *a4,
        unsigned int a5)
{
  const struct std::nothrow_t *v8; // rdx
  signed int Value; // edi
  char v10; // si
  __int64 v11; // rdx
  unsigned __int16 *v12; // rax
  __int64 v13; // rdx
  unsigned __int16 *v14; // rax
  __int64 v15; // rdx
  unsigned __int16 *v16; // rax
  __int64 v17; // rdx
  unsigned __int16 *v18; // rax
  LSTATUS v19; // eax
  const struct std::nothrow_t *v20; // rdx
  const struct std::nothrow_t *v21; // rdx
  const struct std::nothrow_t *v22; // rdx
  const struct std::nothrow_t *v23; // rdx
  const struct std::nothrow_t *v24; // rdx
  const struct std::nothrow_t *v25; // rdx
  const struct std::nothrow_t *v26; // rdx
  unsigned __int16 *v27; // r14
  WCHAR *v28; // rdx
  const struct std::nothrow_t *v29; // rdx
  __int64 v31; // r8
  unsigned __int16 *v32; // rax
  __int64 v33; // r9
  __int64 v34; // r8
  const unsigned __int16 *v35; // rax
  __int64 v36; // rcx
  unsigned __int16 *v37; // rax
  signed int LastError; // eax
  void **v39; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h]
  void **v41; // [rsp+40h] [rbp-C0h]
  void **v42; // [rsp+48h] [rbp-B8h]
  void *v43; // [rsp+50h] [rbp-B0h]
  int v44; // [rsp+58h] [rbp-A8h]
  int v45; // [rsp+60h] [rbp-A0h]
  void **v46; // [rsp+68h] [rbp-98h] BYREF
  void **v47; // [rsp+70h] [rbp-90h]
  void *v48; // [rsp+78h] [rbp-88h]
  int v49; // [rsp+80h] [rbp-80h]
  int v50; // [rsp+88h] [rbp-78h]
  void **v51; // [rsp+90h] [rbp-70h] BYREF
  void **v52; // [rsp+98h] [rbp-68h]
  LPCWSTR lpSubKey; // [rsp+A0h] [rbp-60h]
  int v54; // [rsp+A8h] [rbp-58h]
  int v55; // [rsp+B0h] [rbp-50h]
  void **v56; // [rsp+B8h] [rbp-48h] BYREF
  void **v57; // [rsp+C0h] [rbp-40h]
  unsigned __int16 *v58; // [rsp+C8h] [rbp-38h]
  int v59; // [rsp+D0h] [rbp-30h]
  int v60; // [rsp+D8h] [rbp-28h]
  void **v61; // [rsp+E0h] [rbp-20h] BYREF
  void **v62; // [rsp+E8h] [rbp-18h]
  LPCWSTR lpFileName; // [rsp+F0h] [rbp-10h]
  int v64; // [rsp+F8h] [rbp-8h]
  int v65; // [rsp+100h] [rbp+0h]
  void **v66; // [rsp+108h] [rbp+8h] BYREF
  void **v67; // [rsp+110h] [rbp+10h]
  unsigned __int16 *v68; // [rsp+118h] [rbp+18h]
  int v69; // [rsp+120h] [rbp+20h]
  int v70; // [rsp+128h] [rbp+28h]
  unsigned int v71; // [rsp+130h] [rbp+30h] BYREF
  HKEY phkResult; // [rsp+138h] [rbp+38h] BYREF
  _BYTE v73[240]; // [rsp+140h] [rbp+40h] BYREF

  v71 = a3;
  v51 = &Dfdll::CString::`vftable';
  lpSubKey = 0;
  v54 = 0;
  v52 = &Dfdll::CBuffer<unsigned short>::`vftable';
  v55 = 0;
  Value = Dfdll::CString::Assign((Dfdll::CString *)&v51, Dfdll::Constants::Strings::ClassesCLSID);
  if ( Value < 0 )
  {
    v51 = &Dfdll::CString::`vftable';
    v52 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( lpSubKey )
      operator delete((void *)lpSubKey, v8);
    return (unsigned int)Value;
  }
  v10 = 1;
  if ( Dfdll::Constants::Strings::BackSlash )
  {
    v11 = 0x7FFFFFFF;
    v12 = Dfdll::Constants::Strings::BackSlash;
    do
    {
      if ( !*v12 )
        break;
      ++v12;
      --v11;
    }
    while ( v11 );
    Value = v11 == 0 ? 0x80070057 : 0;
    if ( !v11
      || (Value = Dfdll::CString::Append(
                    (Dfdll::CString *)&v51,
                    Dfdll::Constants::Strings::BackSlash,
                    v11 != 0 ? 0x7FFFFFFF - v11 : 0),
          Value < 0) )
    {
      v51 = &Dfdll::CString::`vftable';
      v52 = &Dfdll::CBuffer<unsigned short>::`vftable';
      if ( lpSubKey )
        operator delete((void *)lpSubKey, (const struct std::nothrow_t *)v11);
      return (unsigned int)Value;
    }
  }
  if ( Dfdll::Constants::Strings::OpenBracket )
  {
    v13 = 0x7FFFFFFF;
    v14 = Dfdll::Constants::Strings::OpenBracket;
    do
    {
      if ( !*v14 )
        break;
      ++v14;
      --v13;
    }
    while ( v13 );
    Value = v13 == 0 ? 0x80070057 : 0;
    if ( !v13
      || (Value = Dfdll::CString::Append(
                    (Dfdll::CString *)&v51,
                    Dfdll::Constants::Strings::OpenBracket,
                    v13 != 0 ? 0x7FFFFFFF - v13 : 0),
          Value < 0) )
    {
      v51 = &Dfdll::CString::`vftable';
      v52 = &Dfdll::CBuffer<unsigned short>::`vftable';
      if ( lpSubKey )
        operator delete((void *)lpSubKey, (const struct std::nothrow_t *)v13);
      return (unsigned int)Value;
    }
  }
  if ( a1 )
  {
    v15 = 0x7FFFFFFF;
    v16 = a1;
    do
    {
      if ( !*v16 )
        break;
      ++v16;
      --v15;
    }
    while ( v15 );
    Value = v15 == 0 ? 0x80070057 : 0;
    if ( !v15
      || (Value = Dfdll::CString::Append((Dfdll::CString *)&v51, a1, v15 != 0 ? 0x7FFFFFFF - v15 : 0), Value < 0) )
    {
      v51 = &Dfdll::CString::`vftable';
      v52 = &Dfdll::CBuffer<unsigned short>::`vftable';
      if ( lpSubKey )
        operator delete((void *)lpSubKey, (const struct std::nothrow_t *)v15);
      return (unsigned int)Value;
    }
  }
  if ( Dfdll::Constants::Strings::CloseBracket )
  {
    v17 = 0x7FFFFFFF;
    v18 = Dfdll::Constants::Strings::CloseBracket;
    do
    {
      if ( !*v18 )
        break;
      ++v18;
      --v17;
    }
    while ( v17 );
    Value = v17 == 0 ? 0x80070057 : 0;
    if ( !v17
      || (Value = Dfdll::CString::Append(
                    (Dfdll::CString *)&v51,
                    Dfdll::Constants::Strings::CloseBracket,
                    v17 != 0 ? 0x7FFFFFFF - v17 : 0),
          Value < 0) )
    {
      v51 = &Dfdll::CString::`vftable';
      v52 = &Dfdll::CBuffer<unsigned short>::`vftable';
      if ( lpSubKey )
        operator delete((void *)lpSubKey, (const struct std::nothrow_t *)v17);
      return (unsigned int)Value;
    }
  }
  v39 = &Dfdll::CRegKey::`vftable';
  hKey = 0;
  v41 = &Dfdll::CString::`vftable';
  v43 = 0;
  v44 = 0;
  v42 = &Dfdll::CBuffer<unsigned short>::`vftable';
  v45 = 0;
  phkResult = 0;
  v19 = RegOpenKeyExW(HKEY_CURRENT_USER, lpSubKey, 0, 0x2001Fu, &phkResult);
  if ( v19 )
  {
    Value = (unsigned __int16)v19 | 0x80070000;
    if ( v19 <= 0 )
      Value = v19;
    hKey = 0;
    v43 = 0;
    v44 = 0;
    v42 = &Dfdll::CObject::`vftable';
    v41 = &Dfdll::CObject::`vftable';
    v39 = &Dfdll::CObject::`vftable';
    v51 = &Dfdll::CString::`vftable';
    v52 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( lpSubKey )
      operator delete((void *)lpSubKey, v20);
    return (unsigned int)Value;
  }
  hKey = phkResult;
  v46 = &Dfdll::CString::`vftable';
  v48 = 0;
  v49 = 0;
  v47 = &Dfdll::CBuffer<unsigned short>::`vftable';
  v50 = 0;
  Value = Dfdll::CRegKey::QueryValue(
            (Dfdll::CRegKey *)&v39,
            Dfdll::Constants::Strings::AppId,
            (struct Dfdll::CString *)&v46);
  if ( Value < 0 )
  {
    v46 = &Dfdll::CString::`vftable';
    v47 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v48 )
      operator delete(v48, v21);
    v48 = 0;
    v49 = 0;
    v47 = &Dfdll::CObject::`vftable';
    v46 = &Dfdll::CObject::`vftable';
    v39 = &Dfdll::CRegKey::`vftable';
    if ( hKey )
      RegCloseKey(hKey);
    hKey = 0;
    v41 = &Dfdll::CString::`vftable';
    v42 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v43 )
      operator delete(v43, v21);
    v43 = 0;
    v44 = 0;
    v42 = &Dfdll::CObject::`vftable';
    v41 = &Dfdll::CObject::`vftable';
    v39 = &Dfdll::CObject::`vftable';
    v51 = &Dfdll::CString::`vftable';
    v52 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( lpSubKey )
      operator delete((void *)lpSubKey, v21);
    return (unsigned int)Value;
  }
  v56 = &Dfdll::CString::`vftable';
  v58 = 0;
  v59 = 0;
  v57 = &Dfdll::CBuffer<unsigned short>::`vftable';
  v60 = 0;
  Value = Dfdll::CRegKey::QueryValue(
            (Dfdll::CRegKey *)&v39,
            Dfdll::Constants::Strings::IconFile,
            (struct Dfdll::CString *)&v56);
  if ( Value < 0 )
  {
    v56 = &Dfdll::CString::`vftable';
    v57 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v58 )
      operator delete(v58, v22);
    v58 = 0;
    v59 = 0;
    v57 = &Dfdll::CObject::`vftable';
    v56 = &Dfdll::CObject::`vftable';
    v46 = &Dfdll::CString::`vftable';
    v47 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v48 )
      operator delete(v48, v22);
    v48 = 0;
    v49 = 0;
    v47 = &Dfdll::CObject::`vftable';
    v46 = &Dfdll::CObject::`vftable';
    v39 = &Dfdll::CRegKey::`vftable';
    if ( hKey )
      RegCloseKey(hKey);
    hKey = 0;
    v41 = &Dfdll::CString::`vftable';
    v42 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v43 )
      operator delete(v43, v22);
    v43 = 0;
    v44 = 0;
    v42 = &Dfdll::CObject::`vftable';
    v41 = &Dfdll::CObject::`vftable';
    v39 = &Dfdll::CObject::`vftable';
    v51 = &Dfdll::CString::`vftable';
    v52 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( lpSubKey )
      operator delete((void *)lpSubKey, v22);
    return (unsigned int)Value;
  }
  Dfdll::CSubscription::CSubscription((Dfdll::CSubscription *)v73);
  Value = Dfdll::CSubscription::LoadFromSubscriptionId((Dfdll::CSubscription *)v73, (struct Dfdll::CString *)&v46);
  if ( Value < 0 )
  {
    Dfdll::CSubscription::~CSubscription((Dfdll::CSubscription *)v73);
    v56 = &Dfdll::CString::`vftable';
    v57 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v58 )
      operator delete(v58, v23);
    v58 = 0;
    v59 = 0;
    v57 = &Dfdll::CObject::`vftable';
    v56 = &Dfdll::CObject::`vftable';
    v46 = &Dfdll::CString::`vftable';
    v47 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v48 )
      operator delete(v48, v23);
    v48 = 0;
    v49 = 0;
    v47 = &Dfdll::CObject::`vftable';
    v46 = &Dfdll::CObject::`vftable';
    v39 = &Dfdll::CRegKey::`vftable';
    if ( hKey )
      RegCloseKey(hKey);
    hKey = 0;
    v41 = &Dfdll::CString::`vftable';
    v42 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v43 )
      operator delete(v43, v23);
    v43 = 0;
    v44 = 0;
    v42 = &Dfdll::CObject::`vftable';
    v41 = &Dfdll::CObject::`vftable';
    v39 = &Dfdll::CObject::`vftable';
    v51 = &Dfdll::CString::`vftable';
    v52 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( lpSubKey )
      operator delete((void *)lpSubKey, v23);
    return (unsigned int)Value;
  }
  v61 = &Dfdll::CString::`vftable';
  lpFileName = 0;
  v64 = 0;
  v62 = &Dfdll::CBuffer<unsigned short>::`vftable';
  v65 = 0;
  v66 = &Dfdll::CString::`vftable';
  v68 = 0;
  v69 = 0;
  v67 = &Dfdll::CBuffer<unsigned short>::`vftable';
  v70 = 0;
  Value = Dfdll::CSubscription::GetApplicationBasePath((Dfdll::CSubscription *)v73, (struct Dfdll::CString *)&v66);
  if ( Value < 0 )
  {
    v66 = &Dfdll::CString::`vftable';
    v67 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v68 )
      operator delete(v68, v24);
    v68 = 0;
    v69 = 0;
    v67 = &Dfdll::CObject::`vftable';
    v66 = &Dfdll::CObject::`vftable';
    v61 = &Dfdll::CString::`vftable';
    v62 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( lpFileName )
      operator delete((void *)lpFileName, v24);
    lpFileName = 0;
    v64 = 0;
    v62 = &Dfdll::CObject::`vftable';
    v61 = &Dfdll::CObject::`vftable';
    Dfdll::CSubscription::~CSubscription((Dfdll::CSubscription *)v73);
    v56 = &Dfdll::CString::`vftable';
    v57 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v58 )
      operator delete(v58, v25);
    v58 = 0;
    v59 = 0;
    v57 = &Dfdll::CObject::`vftable';
    v56 = &Dfdll::CObject::`vftable';
    v46 = &Dfdll::CString::`vftable';
    v47 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v48 )
      operator delete(v48, v25);
    v48 = 0;
    v49 = 0;
    v47 = &Dfdll::CObject::`vftable';
    v46 = &Dfdll::CObject::`vftable';
    v39 = &Dfdll::CRegKey::`vftable';
    if ( hKey )
      RegCloseKey(hKey);
    hKey = 0;
    v41 = &Dfdll::CString::`vftable';
    v42 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v43 )
      operator delete(v43, v25);
    v43 = 0;
    v44 = 0;
    v42 = &Dfdll::CObject::`vftable';
    v41 = &Dfdll::CObject::`vftable';
    v39 = &Dfdll::CObject::`vftable';
    v51 = &Dfdll::CString::`vftable';
    v52 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( lpSubKey )
      operator delete((void *)lpSubKey, v25);
    return (unsigned int)Value;
  }
  if ( !v68 )
  {
    Value = -2147024809;
    v68 = 0;
    v69 = 0;
    v67 = &Dfdll::CObject::`vftable';
    v66 = &Dfdll::CObject::`vftable';
    v61 = &Dfdll::CString::`vftable';
    v62 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( lpFileName )
      operator delete((void *)lpFileName, v24);
    lpFileName = 0;
    v64 = 0;
    v62 = &Dfdll::CObject::`vftable';
    v61 = &Dfdll::CObject::`vftable';
    Dfdll::CSubscription::~CSubscription((Dfdll::CSubscription *)v73);
    v56 = &Dfdll::CString::`vftable';
    v57 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v58 )
      operator delete(v58, v26);
    v58 = 0;
    v59 = 0;
    v57 = &Dfdll::CObject::`vftable';
    v56 = &Dfdll::CObject::`vftable';
    v46 = &Dfdll::CString::`vftable';
    v47 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v48 )
      operator delete(v48, v26);
    v48 = 0;
    v49 = 0;
    v47 = &Dfdll::CObject::`vftable';
    v46 = &Dfdll::CObject::`vftable';
    v39 = &Dfdll::CRegKey::`vftable';
    if ( hKey )
      RegCloseKey(hKey);
    hKey = 0;
    v41 = &Dfdll::CString::`vftable';
    v42 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v43 )
      operator delete(v43, v26);
    v43 = 0;
    v44 = 0;
    v42 = &Dfdll::CObject::`vftable';
    v41 = &Dfdll::CObject::`vftable';
    v39 = &Dfdll::CObject::`vftable';
    v51 = &Dfdll::CString::`vftable';
    v52 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( lpSubKey )
      operator delete((void *)lpSubKey, v26);
    return (unsigned int)Value;
  }
  v27 = v58;
  if ( v58 )
  {
    Value = Dfdll::CString::Assign((Dfdll::CString *)&v61, v68);
    if ( Value < 0 )
      goto LABEL_113;
    v28 = (WCHAR *)lpFileName;
    if ( !lpFileName )
    {
      Value = -2147024809;
      goto LABEL_114;
    }
    v31 = 0x7FFFFFFF;
    v32 = v27;
    do
    {
      if ( !*v32 )
        break;
      ++v32;
      --v31;
    }
    while ( v31 );
    Value = v31 == 0 ? 0x80070057 : 0;
    v33 = (0x7FFFFFFF - v31) & -(__int64)(v31 != 0);
    if ( !v31 )
      goto LABEL_114;
    if ( (_DWORD)v33 )
    {
      if ( *v27 != 92 || (++v27, (_DWORD)v33 != 1) )
      {
        if ( v65 && lpFileName[v65 - 1] != 92 )
        {
          v34 = 0x7FFFFFFF;
          v35 = L"\\";
          do
          {
            if ( !*v35 )
              break;
            ++v35;
            --v34;
          }
          while ( v34 );
          Value = v34 == 0 ? 0x80070057 : 0;
          if ( !v34 )
            goto LABEL_114;
          Value = Dfdll::CString::Append((Dfdll::CString *)&v61, L"\\", v34 != 0 ? 0x7FFFFFFF - v34 : 0);
          if ( Value < 0 )
            goto LABEL_113;
          v28 = (WCHAR *)lpFileName;
        }
        if ( v27 )
        {
          v36 = 0x7FFFFFFF;
          v37 = v27;
          do
          {
            if ( !*v37 )
              break;
            ++v37;
            --v36;
          }
          while ( v36 );
          Value = v36 == 0 ? 0x80070057 : 0;
          if ( !v36 )
            goto LABEL_114;
          Value = Dfdll::CString::Append((Dfdll::CString *)&v61, v27, v36 != 0 ? 0x7FFFFFFF - v36 : 0);
          if ( Value < 0 )
            goto LABEL_113;
          v28 = (WCHAR *)lpFileName;
        }
      }
    }
    if ( !v28 )
    {
      Value = -2147024809;
LABEL_161:
      Dfdll::CString::~CString((Dfdll::CString *)&v66);
      Dfdll::CString::~CString((Dfdll::CString *)&v61);
      Dfdll::CSubscription::~CSubscription((Dfdll::CSubscription *)v73);
      Dfdll::CString::~CString((Dfdll::CString *)&v56);
      Dfdll::CString::~CString((Dfdll::CString *)&v46);
      Dfdll::CRegKey::~CRegKey((Dfdll::CRegKey *)&v39);
      Dfdll::CString::~CString((Dfdll::CString *)&v51);
      return (unsigned int)Value;
    }
    if ( GetFileAttributesW(v28) == -1 )
    {
      LastError = GetLastError();
      Value = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        Value = LastError;
      if ( Value < 0 )
      {
        if ( (unsigned int)(Value + 2147024894) > 1 )
          goto LABEL_161;
        v10 = 0;
      }
    }
    if ( v10 || (Value = Dfdll::CSystem::GetModuleFileNameW(g_hModule, (struct Dfdll::CString *)&v61), Value >= 0) )
    {
      Value = Dfdll::CString::CopyTo((Dfdll::CString *)&v61, a4, &a5);
      if ( Value >= 0 )
      {
        Value = Dfdll::CString::CopyTo((Dfdll::CString *)&v61, a2, &v71);
        if ( Value >= 0 )
          Value = 0;
      }
    }
    goto LABEL_161;
  }
  Value = -2147024809;
LABEL_113:
  v28 = (WCHAR *)lpFileName;
LABEL_114:
  v66 = &Dfdll::CString::`vftable';
  v67 = &Dfdll::CBuffer<unsigned short>::`vftable';
  if ( v68 )
  {
    operator delete(v68, (const struct std::nothrow_t *)v28);
    v28 = (WCHAR *)lpFileName;
  }
  v68 = 0;
  v69 = 0;
  v67 = &Dfdll::CObject::`vftable';
  v66 = &Dfdll::CObject::`vftable';
  v61 = &Dfdll::CString::`vftable';
  v62 = &Dfdll::CBuffer<unsigned short>::`vftable';
  if ( v28 )
    operator delete(v28, (const struct std::nothrow_t *)v28);
  lpFileName = 0;
  v64 = 0;
  v62 = &Dfdll::CObject::`vftable';
  v61 = &Dfdll::CObject::`vftable';
  Dfdll::CSubscription::~CSubscription((Dfdll::CSubscription *)v73);
  v56 = &Dfdll::CString::`vftable';
  v57 = &Dfdll::CBuffer<unsigned short>::`vftable';
  if ( v58 )
    operator delete(v58, v29);
  v58 = 0;
  v59 = 0;
  v57 = &Dfdll::CObject::`vftable';
  v56 = &Dfdll::CObject::`vftable';
  v46 = &Dfdll::CString::`vftable';
  v47 = &Dfdll::CBuffer<unsigned short>::`vftable';
  if ( v48 )
    operator delete(v48, v29);
  v48 = 0;
  v49 = 0;
  v47 = &Dfdll::CObject::`vftable';
  v46 = &Dfdll::CObject::`vftable';
  v39 = &Dfdll::CRegKey::`vftable';
  if ( hKey )
    RegCloseKey(hKey);
  hKey = 0;
  v41 = &Dfdll::CString::`vftable';
  v42 = &Dfdll::CBuffer<unsigned short>::`vftable';
  if ( v43 )
    operator delete(v43, v29);
  v43 = 0;
  v44 = 0;
  v42 = &Dfdll::CObject::`vftable';
  v41 = &Dfdll::CObject::`vftable';
  v39 = &Dfdll::CObject::`vftable';
  v51 = &Dfdll::CString::`vftable';
  v52 = &Dfdll::CBuffer<unsigned short>::`vftable';
  if ( lpSubKey )
    operator delete((void *)lpSubKey, v29);
  return (unsigned int)Value;
}

```

## disassembly

```asm
0x180006180  push    rbp
0x180006182  push    rbx
0x180006183  push    rsi
0x180006184  push    rdi
0x180006185  push    r12
0x180006187  push    r13
0x180006189  push    r14
0x18000618b  push    r15
0x18000618d  lea     rbp, [rsp-148h]
0x180006195  sub     rsp, 248h
0x18000619c  mov     rax, cs:__security_cookie
0x1800061a3  xor     rax, rsp
0x1800061a6  mov     [rbp+180h+var_50], rax
0x1800061ad  mov     r12, r9
0x1800061b0  mov     r15, rdx
0x1800061b3  mov     r14, rcx
0x1800061b6  mov     [rbp+180h+var_150], r8d
0x1800061ba  lea     rbx, ??_7CString@Dfdll@@6B@
0x1800061c1  mov     [rbp+180h+var_1F0], rbx
0x1800061c5  xor     r13d, r13d
0x1800061c8  mov     [rbp+180h+lpSubKey], r13
0x1800061cc  mov     [rbp+180h+var_1D8], r13d
0x1800061d0  lea     rsi, ??_7?$CBuffer@G@Dfdll@@6B@
0x1800061d7  mov     [rbp+180h+var_1E8], rsi
0x1800061db  mov     [rbp+180h+var_1D0], r13d
0x1800061df  mov     rdx, cs:?ClassesCLSID@Strings@Constants@Dfdll@@3QEAGEA; unsigned __int16 *
0x1800061e6  lea     rcx, [rbp+180h+var_1F0]; this
0x1800061ea  call    ?Assign@CString@Dfdll@@QEAAJPEBG@Z
0x1800061ef  mov     edi, eax
0x1800061f1  test    eax, eax
0x1800061f3  jns     short loc_180006211
0x1800061f5  mov     [rbp+180h+var_1F0], rbx
0x1800061f9  mov     [rbp+180h+var_1E8], rsi
0x1800061fd  mov     rcx, [rbp+180h+lpSubKey]; void *
0x180006201  test    rcx, rcx
0x180006204  jz      short loc_18000620C
0x180006206  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z
0x18000620b  nop
0x18000620c  jmp     loc_180006BE6
0x180006211  mov     r9, cs:?BackSlash@Strings@Constants@Dfdll@@3QEAGEA
0x180006218  mov     ebx, 7FFFFFFFh
0x18000621d  mov     esi, 1
0x180006222  test    r9, r9
0x180006225  jz      short loc_18000629E
0x180006227  mov     edx, ebx
0x180006229  mov     rax, r9
0x18000622c  cmp     [rax], r13w
0x180006230  jz      short loc_18000623B
0x180006232  add     rax, 2
0x180006236  sub     rdx, rsi
0x180006239  jnz     short loc_18000622C
0x18000623b  mov     rax, rdx
0x18000623e  neg     rax
0x180006241  sbb     edi, edi
0x180006243  not     edi
0x180006245  and     edi, 80070057h
0x18000624b  mov     rax, rdx
0x18000624e  mov     rcx, rbx
0x180006251  sub     rcx, rdx
0x180006254  neg     rax
0x180006257  sbb     r8, r8
0x18000625a  and     r8, rcx; unsigned int
0x18000625d  test    rdx, rdx
0x180006260  jz      short loc_180006274
0x180006262  mov     rdx, r9; unsigned __int16 *
0x180006265  lea     rcx, [rbp+180h+var_1F0]; this
0x180006269  call    ?Append@CString@Dfdll@@QEAAJPEBGI@Z
0x18000626e  mov     edi, eax
0x180006270  test    eax, eax
0x180006272  jns     short loc_18000629E
0x180006274  lea     rax, ??_7CString@Dfdll@@6B@
0x18000627b  mov     [rbp+180h+var_1F0], rax
0x18000627f  lea     rax, ??_7?$CBuffer@G@Dfdll@@6B@
0x180006286  mov     [rbp+180h+var_1E8], rax
0x18000628a  mov     rcx, [rbp+180h+lpSubKey]; void *
0x18000628e  test    rcx, rcx
0x180006291  jz      short loc_180006299
0x180006293  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z
0x180006298  nop
0x180006299  jmp     loc_180006BE6
0x18000629e  mov     r9, cs:?OpenBracket@Strings@Constants@Dfdll@@3QEAGEA
0x1800062a5  test    r9, r9
0x1800062a8  jz      short loc_180006322
0x1800062aa  mov     rdx, rbx
0x1800062ad  mov     rax, r9
0x1800062b0  cmp     [rax], r13w
0x1800062b4  jz      short loc_1800062BF
0x1800062b6  add     rax, 2
0x1800062ba  sub     rdx, rsi
0x1800062bd  jnz     short loc_1800062B0
0x1800062bf  mov     rax, rdx
0x1800062c2  neg     rax
0x1800062c5  sbb     edi, edi
0x1800062c7  not     edi
0x1800062c9  and     edi, 80070057h
0x1800062cf  mov     rax, rdx
0x1800062d2  mov     rcx, rbx
0x1800062d5  sub     rcx, rdx
0x1800062d8  neg     rax
0x1800062db  sbb     r8, r8
0x1800062de  and     r8, rcx; unsigned int
0x1800062e1  test    rdx, rdx
0x1800062e4  jz      short loc_1800062F8
0x1800062e6  mov     rdx, r9; unsigned __int16 *
0x1800062e9  lea     rcx, [rbp+180h+var_1F0]; this
0x1800062ed  call    ?Append@CString@Dfdll@@QEAAJPEBGI@Z
0x1800062f2  mov     edi, eax
0x1800062f4  test    eax, eax
0x1800062f6  jns     short loc_180006322
0x1800062f8  lea     rax, ??_7CString@Dfdll@@6B@
0x1800062ff  mov     [rbp+180h+var_1F0], rax
0x180006303  lea     rax, ??_7?$CBuffer@G@Dfdll@@6B@
0x18000630a  mov     [rbp+180h+var_1E8], rax
0x18000630e  mov     rcx, [rbp+180h+lpSubKey]; void *
0x180006312  test    rcx, rcx
0x180006315  jz      short loc_18000631D
0x180006317  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z
0x18000631c  nop
0x18000631d  jmp     loc_180006BE6
0x180006322  test    r14, r14
0x180006325  jz      short loc_18000639F
0x180006327  mov     rdx, rbx
0x18000632a  mov     rax, r14
0x18000632d  cmp     [rax], r13w
0x180006331  jz      short loc_18000633C
0x180006333  add     rax, 2
0x180006337  sub     rdx, rsi
0x18000633a  jnz     short loc_18000632D
0x18000633c  mov     rax, rdx
0x18000633f  neg     rax
0x180006342  sbb     edi, edi
0x180006344  not     edi
0x180006346  and     edi, 80070057h
0x18000634c  mov     rax, rdx
0x18000634f  mov     rcx, rbx
0x180006352  sub     rcx, rdx
0x180006355  neg     rax
0x180006358  sbb     r8, r8
0x18000635b  and     r8, rcx; unsigned int
0x18000635e  test    rdx, rdx
0x180006361  jz      short loc_180006375
0x180006363  mov     rdx, r14; unsigned __int16 *
0x180006366  lea     rcx, [rbp+180h+var_1F0]; this
0x18000636a  call    ?Append@CString@Dfdll@@QEAAJPEBGI@Z
0x18000636f  mov     edi, eax
0x180006371  test    eax, eax
0x180006373  jns     short loc_18000639F
0x180006375  lea     rax, ??_7CString@Dfdll@@6B@
0x18000637c  mov     [rbp+180h+var_1F0], rax
0x180006380  lea     rax, ??_7?$CBuffer@G@Dfdll@@6B@
0x180006387  mov     [rbp+180h+var_1E8], rax
0x18000638b  mov     rcx, [rbp+180h+lpSubKey]; void *
0x18000638f  test    rcx, rcx
0x180006392  jz      short loc_18000639A
0x180006394  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z
0x180006399  nop
0x18000639a  jmp     loc_180006BE6
0x18000639f  mov     r9, cs:?CloseBracket@Strings@Constants@Dfdll@@3QEAGEA
0x1800063a6  test    r9, r9
0x1800063a9  jz      short loc_180006423
0x1800063ab  mov     rdx, rbx
0x1800063ae  mov     rax, r9
0x1800063b1  cmp     [rax], r13w
0x1800063b5  jz      short loc_1800063C0
0x1800063b7  add     rax, 2
0x1800063bb  sub     rdx, rsi
0x1800063be  jnz     short loc_1800063B1
0x1800063c0  mov     rax, rdx
0x1800063c3  neg     rax
0x1800063c6  sbb     edi, edi
0x1800063c8  not     edi
0x1800063ca  and     edi, 80070057h
0x1800063d0  mov     rax, rdx
0x1800063d3  mov     rcx, rbx
0x1800063d6  sub     rcx, rdx
0x1800063d9  neg     rax
0x1800063dc  sbb     r8, r8
0x1800063df  and     r8, rcx; unsigned int
0x1800063e2  test    rdx, rdx
0x1800063e5  jz      short loc_1800063F9
0x1800063e7  mov     rdx, r9; unsigned __int16 *
0x1800063ea  lea     rcx, [rbp+180h+var_1F0]; this
0x1800063ee  call    ?Append@CString@Dfdll@@QEAAJPEBGI@Z
0x1800063f3  mov     edi, eax
0x1800063f5  test    eax, eax
0x1800063f7  jns     short loc_180006423
0x1800063f9  lea     rax, ??_7CString@Dfdll@@6B@
0x180006400  mov     [rbp+180h+var_1F0], rax
0x180006404  lea     rax, ??_7?$CBuffer@G@Dfdll@@6B@
0x18000640b  mov     [rbp+180h+var_1E8], rax
0x18000640f  mov     rcx, [rbp+180h+lpSubKey]; void *
0x180006413  test    rcx, rcx
0x180006416  jz      short loc_18000641E
0x180006418  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z
0x18000641d  nop
0x18000641e  jmp     loc_180006BE6
0x180006423  lea     rax, ??_7CRegKey@Dfdll@@6B@
0x18000642a  mov     [rsp+280h+var_250], rax
0x18000642f  mov     [rsp+280h+hKey], r13
0x180006434  lea     r14, ??_7CString@Dfdll@@6B@
0x18000643b  mov     [rsp+280h+var_240], r14
0x180006440  mov     [rsp+280h+var_230], r13
0x180006445  mov     [rsp+280h+var_228], r13d
0x18000644a  lea     rax, ??_7?$CBuffer@G@Dfdll@@6B@
0x180006451  mov     [rsp+280h+var_238], rax
0x180006456  mov     [rsp+280h+var_220], r13d
0x18000645b  mov     [rbp+180h+var_148], r13
0x18000645f  lea     rax, [rbp+180h+var_148]
0x180006463  mov     [rsp+280h+phkResult], rax; phkResult
0x180006468  mov     r9d, 2001Fh; samDesired
0x18000646e  xor     r8d, r8d; ulOptions
0x180006471  mov     rdx, [rbp+180h+lpSubKey]; lpSubKey
0x180006475  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18000647c  call    cs:__imp_RegOpenKeyExW
0x180006482  test    eax, eax
0x180006484  jz      loc_180006519
0x18000648a  movzx   edi, ax
0x18000648d  or      edi, 80070000h
0x180006493  test    eax, eax
0x180006495  cmovle  edi, eax
0x180006498  test    edi, edi
0x18000649a  jns     short loc_180006519
0x18000649c  lea     rax, ??_7CRegKey@Dfdll@@6B@
0x1800064a3  mov     [rsp+280h+var_250], rax
0x1800064a8  mov     rcx, [rsp+280h+hKey]; hKey
0x1800064ad  test    rcx, rcx
0x1800064b0  jz      short loc_1800064B8
0x1800064b2  call    cs:__imp_RegCloseKey
0x1800064b8  mov     [rsp+280h+hKey], r13
0x1800064bd  mov     [rsp+280h+var_240], r14
0x1800064c2  lea     rsi, ??_7?$CBuffer@G@Dfdll@@6B@
0x1800064c9  mov     [rsp+280h+var_238], rsi
0x1800064ce  mov     rcx, [rsp+280h+var_230]; void *
0x1800064d3  test    rcx, rcx
0x1800064d6  jz      short loc_1800064DD
0x1800064d8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z
0x1800064dd  mov     [rsp+280h+var_230], r13
0x1800064e2  mov     [rsp+280h+var_228], r13d
0x1800064e7  lea     rbx, ??_7CObject@Dfdll@@6B@
0x1800064ee  mov     [rsp+280h+var_238], rbx
0x1800064f3  mov     [rsp+280h+var_240], rbx
0x1800064f8  mov     [rsp+280h+var_250], rbx
0x1800064fd  mov     [rbp+180h+var_1F0], r14
0x180006501  mov     [rbp+180h+var_1E8], rsi
0x180006505  mov     rcx, [rbp+180h+lpSubKey]; void *
0x180006509  test    rcx, rcx
0x18000650c  jz      short loc_180006514
0x18000650e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z
0x180006513  nop
0x180006514  jmp     loc_180006BE6
0x180006519  mov     rdi, [rbp+180h+var_148]
0x18000651d  mov     rcx, [rsp+280h+hKey]; hKey
0x180006522  test    rcx, rcx
0x180006525  jz      short loc_18000652D
0x180006527  call    cs:__imp_RegCloseKey
0x18000652d  mov     [rsp+280h+hKey], rdi
0x180006532  mov     [rsp+280h+var_218], r14
0x180006537  mov     [rsp+280h+var_208], r13
0x18000653c  mov     [rbp+180h+var_200], r13d
0x180006540  lea     rax, ??_7?$CBuffer@G@Dfdll@@6B@
0x180006547  mov     [rsp+280h+var_210], rax
0x18000654c  mov     [rbp+180h+var_1F8], r13d
0x180006550  lea     r8, [rsp+280h+var_218]; struct Dfdll::CString *
0x180006555  mov     rdx, cs:?AppId@Strings@Constants@Dfdll@@3QEAGEA; unsigned __int16 *
0x18000655c  lea     rcx, [rsp+280h+var_250]; this
0x180006561  call    ?QueryValue@CRegKey@Dfdll@@QEAAJPEBGAEAVCString@2@@Z
0x180006566  mov     edi, eax
0x180006568  test    eax, eax
0x18000656a  jns     loc_180006619
0x180006570  mov     [rsp+280h+var_218], r14
0x180006575  lea     rsi, ??_7?$CBuffer@G@Dfdll@@6B@
0x18000657c  mov     [rsp+280h+var_210], rsi
0x180006581  mov     rcx, [rsp+280h+var_208]; void *
0x180006586  test    rcx, rcx
0x180006589  jz      short loc_180006590
0x18000658b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z
0x180006590  mov     [rsp+280h+var_208], r13
0x180006595  mov     [rbp+180h+var_200], r13d
0x180006599  lea     rbx, ??_7CObject@Dfdll@@6B@
0x1800065a0  mov     [rsp+280h+var_210], rbx
0x1800065a5  mov     [rsp+280h+var_218], rbx
0x1800065aa  lea     rax, ??_7CRegKey@Dfdll@@6B@
0x1800065b1  mov     [rsp+280h+var_250], rax
0x1800065b6  mov     rcx, [rsp+280h+hKey]; hKey
0x1800065bb  test    rcx, rcx
0x1800065be  jz      short loc_1800065C6
0x1800065c0  call    cs:__imp_RegCloseKey
0x1800065c6  mov     [rsp+280h+hKey], r13
0x1800065cb  mov     [rsp+280h+var_240], r14
0x1800065d0  mov     [rsp+280h+var_238], rsi
0x1800065d5  mov     rcx, [rsp+280h+var_230]; void *
0x1800065da  test    rcx, rcx
0x1800065dd  jz      short loc_1800065E4
0x1800065df  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z
0x1800065e4  mov     [rsp+280h+var_230], r13
0x1800065e9  mov     [rsp+280h+var_228], r13d
0x1800065ee  mov     [rsp+280h+var_238], rbx
0x1800065f3  mov     [rsp+280h+var_240], rbx
0x1800065f8  mov     [rsp+280h+var_250], rbx
0x1800065fd  mov     [rbp+180h+var_1F0], r14
  ... truncated ...
```
