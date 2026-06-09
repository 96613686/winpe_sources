# TryGetTypeInfoFromIIDViaRegistry(_GUID const &,ITypeInfo * *,long *)

- ea: `0x180013f54`
- end: `0x180014af9`
- name: `?TryGetTypeInfoFromIIDViaRegistry@@YAJAEBU_GUID@@PEAPEAUITypeInfo@@PEAJ@Z`
- size: `2981`
- prototype: `HRESULT __fastcall(const _GUID *iidIntercepted, ITypeInfo **pptypeinfo, HRESULT *reasonForNoTypeInfo)`
- caller_count: `2`
- callee_count: `20`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180013d68`
- `0x180013f54`

## callees

- `0x180010fac`
- `0x18001217c`
- `0x180013f54`
- `0x18001a630`
- `0x18002091c`
- `0x180020a3c`
- `0x180020b10`
- `0x18002a618`
- `0x180033bb0`
- `0x18003f19c`
- `0x180042ffc`
- `0x180043ba8`
- `0x180043cd4`
- `0x1800444d4`
- `0x180045658`
- `0x1800457d8`
- `0x180046460`
- `0x180047484`
- `0x18004ba84`
- `0x1800d8010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x1800147cd`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x1800147ef`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x1800147cd`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x1800147ef`
- `ntdll!ZwClose` at `0x1800145e2`
- `ntdll!ZwClose` at `0x1800145f3`
- `ntdll!ZwClose` at `0x180014618`
- `ntdll!ZwClose` at `0x180014629`
- `ntdll!ZwClose` at `0x180014639`
- `ntdll!ZwClose` at `0x180014678`
- `ntdll!ZwClose` at `0x180014689`
- `ntdll!ZwClose` at `0x180014699`
- `ntdll!ZwClose` at `0x180014753`
- `ntdll!ZwClose` at `0x1800148d2`
- `ntdll!ZwClose` at `0x18001497a`
- `ntdll!ZwClose` at `0x18001498b`
- `ntdll!ZwClose` at `0x1800149a6`
- `ntdll!ZwClose` at `0x1800149b7`
- `ntdll!ZwClose` at `0x180014a51`
- `ntdll!ZwClose` at `0x180014a95`
- `ntdll!ZwClose` at `0x180014aa6`
- `ntdll!ZwClose` at `0x1800145e2`
- `ntdll!ZwClose` at `0x1800145f3`
- `ntdll!ZwClose` at `0x180014618`
- `ntdll!ZwClose` at `0x180014629`
- `ntdll!ZwClose` at `0x180014639`
- `ntdll!ZwClose` at `0x180014678`
- `ntdll!ZwClose` at `0x180014689`
- `ntdll!ZwClose` at `0x180014699`
- `ntdll!ZwClose` at `0x180014753`
- `ntdll!ZwClose` at `0x1800148d2`
- `ntdll!ZwClose` at `0x18001497a`
- `ntdll!ZwClose` at `0x18001498b`
- `ntdll!ZwClose` at `0x1800149a6`
- `ntdll!ZwClose` at `0x1800149b7`
- `ntdll!ZwClose` at `0x180014a51`
- `ntdll!ZwClose` at `0x180014a95`
- `ntdll!ZwClose` at `0x180014aa6`
- `ntdll!RtlInitUnicodeString` at `0x180014016`
- `ntdll!RtlInitUnicodeString` at `0x1800140b3`
- `ntdll!RtlInitUnicodeString` at `0x180014227`
- `ntdll!RtlInitUnicodeString` at `0x180014316`
- `ntdll!RtlInitUnicodeString` at `0x1800143e6`
- `ntdll!RtlInitUnicodeString` at `0x180014467`
- `ntdll!RtlInitUnicodeString` at `0x180014016`
- `ntdll!RtlInitUnicodeString` at `0x1800140b3`
- `ntdll!RtlInitUnicodeString` at `0x180014227`
- `ntdll!RtlInitUnicodeString` at `0x180014316`
- `ntdll!RtlInitUnicodeString` at `0x1800143e6`
- `ntdll!RtlInitUnicodeString` at `0x180014467`
- `ntdll!ZwOpenKey` at `0x180014053`
- `ntdll!ZwOpenKey` at `0x1800140f0`
- `ntdll!ZwOpenKey` at `0x180014265`
- `ntdll!ZwOpenKey` at `0x180014359`
- `ntdll!ZwOpenKey` at `0x180014424`
- `ntdll!ZwOpenKey` at `0x18001449f`
- `ntdll!ZwOpenKey` at `0x180014053`
- `ntdll!ZwOpenKey` at `0x1800140f0`
- `ntdll!ZwOpenKey` at `0x180014265`
- `ntdll!ZwOpenKey` at `0x180014359`
- `ntdll!ZwOpenKey` at `0x180014424`
- `ntdll!ZwOpenKey` at `0x18001449f`
- `OLEAUT32!__imp_LoadTypeLibEx` at `0x18001453a`
- `OLEAUT32!__imp_LoadTypeLibEx` at `0x18001453a`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180013fa2`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800141cc`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180013fa2`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800141cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014607`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800146ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014a69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014607`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800146ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014a69`

## string_xrefs

- `0x180013fd7`: `\Registry\Machine\Software\Classes\Interface\%ls\Forward`
- `0x180014077`: `\Registry\Machine\Software\Classes\Interface\%ls\TypeLib`
- `0x180014149`: `com\ole32\com\txf\callframe\typeinfo.cpp`
- `0x1800145a0`: `com\ole32\com\txf\callframe\typeinfo.cpp`
- `0x18001479d`: `com\ole32\com\txf\callframe\typeinfo.cpp`
- `0x180014859`: `com\ole32\com\txf\callframe\typeinfo.cpp`
- `0x180014897`: `com\ole32\com\txf\callframe\typeinfo.cpp`
- `0x1800148b4`: `com\ole32\com\txf\callframe\typeinfo.cpp`
- `0x1800149d2`: `com\ole32\com\txf\callframe\typeinfo.cpp`
- `0x180014a05`: `com\ole32\com\txf\callframe\typeinfo.cpp`
- `0x180014a22`: `com\ole32\com\txf\callframe\typeinfo.cpp`
- `0x180014ad4`: `com\ole32\com\txf\callframe\typeinfo.cpp`
- `0x180014651`: `onecore\internal\com\inc\combase\ComGuid.hpp`
- `0x1800146c5`: `onecore\internal\com\inc\combase\ComGuid.hpp`
- `0x1800141ea`: `\Registry\Machine\Software\Classes\TypeLib\%ls`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
__int64 __fastcall TryGetTypeInfoFromIIDViaRegistry(
        const _GUID *iidIntercepted,
        ITypeInfo **pptypeinfo,
        HRESULT *reasonForNoTypeInfo)
{
  unsigned int v3; // r14d
  bool v6; // di
  HRESULT v7; // ebx
  NTSTATUS v8; // eax
  unsigned int v9; // r9d
  NTSTATUS v10; // eax
  unsigned int v12; // edx
  HRESULT v13; // eax
  NTSTATUS v14; // eax
  unsigned __int16 v15; // r15
  unsigned __int16 v16; // r12
  HRESULT v17; // eax
  const wchar_t *v18; // rbx
  wchar_t *h; // rbx
  NTSTATUS v20; // eax
  HRESULT v21; // eax
  unsigned int i; // r14d
  HRESULT v23; // eax
  wchar_t *m_ptr; // rdi
  void *v25; // rbx
  NTSTATUS v26; // eax
  void *v27; // rbx
  NTSTATUS v28; // eax
  HRESULT v29; // eax
  unsigned int v30; // r9d
  const OLECHAR *v31; // rcx
  int v32; // eax
  _KEY_VALUE_FULL_INFORMATION *value; // rcx
  int RegistryValue; // ebx
  const wchar_t *v35; // rcx
  unsigned int v36; // edx
  unsigned __int16 v37; // di
  unsigned __int16 v38; // ax
  unsigned int v39; // edx
  unsigned int v40; // edx
  unsigned int v41; // edx
  HRESULT v42; // eax
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(void *),&CoTaskMemFree,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > fHasVersion; // [rsp+30h] [rbp-D0h] BYREF
  HREG hregTlb; // [rsp+38h] [rbp-C8h] BYREF
  HREG hregVersion; // [rsp+40h] [rbp-C0h] BYREF
  HREG hregLang; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 wMajBest[2]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 wMinBest; // [rsp+54h] [rbp-ACh] BYREF
  _UNICODE_STRING typeLib; // [rsp+58h] [rbp-A8h] OVERLAPPED BYREF
  wistd::unique_ptr<_KEY_VALUE_FULL_INFORMATION,wil::function_deleter<void (__cdecl*)(void *),&CoTaskMemFree> > valueInformation; // [rsp+68h] [rbp-98h] BYREF
  HREG hregPlatform; // [rsp+70h] [rbp-90h] BYREF
  _UNICODE_STRING platform; // [rsp+78h] [rbp-88h] OVERLAPPED BYREF
  _GUID *p_end; // [rsp+88h] [rbp-78h]
  int v54; // [rsp+90h] [rbp-70h]
  int v55; // [rsp+94h] [rbp-6Ch]
  __int128 v56; // [rsp+98h] [rbp-68h]
  HREG hregTlbId; // [rsp+A8h] [rbp-58h] BYREF
  HREG hregForward; // [rsp+B0h] [rbp-50h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B8h] [rbp-48h] BYREF
  const _GUID *v60; // [rsp+E8h] [rbp-18h]
  _GUID end; // [rsp+F0h] [rbp-10h] BYREF
  char v62; // [rsp+100h] [rbp+0h]
  _GUID libId; // [rsp+108h] [rbp+8h] BYREF
  GuidString iidString; // [rsp+120h] [rbp+20h] BYREF
  GuidString libIdString; // [rsp+170h] [rbp+70h] BYREF
  wchar_t keyPath[264]; // [rsp+1C0h] [rbp+C0h] BYREF
  wchar_t bestVersionString[264]; // [rsp+3D0h] [rbp+2D0h] BYREF
  void *retaddr; // [rsp+628h] [rbp+528h]

  v3 = 0;
  v60 = iidIntercepted;
  *pptypeinfo = 0;
  *reasonForNoTypeInfo = 0;
  if ( StringFromGUID2(iidIntercepted, iidString.m_string, 39) != 39 )
    wil::details::in1diag3::_FailFast_Unexpected(retaddr, 0x19u, "onecore\\internal\\com\\inc\\combase\\ComGuid.hpp");
  memset_0(keyPath, 0, 0x208u);
  v6 = 0;
  v7 = StringCchPrintfW(keyPath, 0x104u, L"\\Registry\\Machine\\Software\\Classes\\Interface\\%ls\\Forward", &iidString);
  if ( v7 < 0 )
  {
    v12 = 399;
    goto LABEL_9;
  }
  hregForward.h = 0;
  v55 = 0;
  end = 0;
  RtlInitUnicodeString((PUNICODE_STRING)&end, keyPath);
  *(_QWORD *)&platform.Length = 48;
  p_end = &end;
  platform.Buffer = 0;
  v54 = 64;
  v56 = 0;
  v8 = ZwOpenKey(&hregForward.h, 0x20019u, (POBJECT_ATTRIBUTES)&platform);
  if ( HrNt(v8) >= 0 )
  {
    *(_QWORD *)&end.Data1 = &typeLib;
    *(_QWORD *)&typeLib.Length = 0;
    *(_QWORD *)end.Data4 = 0;
    v62 = 1;
    RegistryValue = GetRegistryValue(hregForward, &::value, (_KEY_VALUE_FULL_INFORMATION **)end.Data4, v9);
    wil::details::out_param_t<wistd::unique_ptr<_KEY_VALUE_FULL_INFORMATION,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_KEY_VALUE_FULL_INFORMATION,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>((wil::details::out_param_t<wistd::unique_ptr<_KEY_VALUE_FULL_INFORMATION,wil::function_deleter<void (__cdecl*)(void *),&CoTaskMemFree> > > *)&end);
    if ( RegistryValue >= 0 )
    {
      v35 = (const wchar_t *)(*(_QWORD *)&typeLib.Length + *(unsigned int *)(*(_QWORD *)&typeLib.Length + 8LL));
      end = 0;
      if ( GuidFromString(v35, &end) >= 0
        && TryGetTypeInfoFromIIDViaRegistry(&end, pptypeinfo, reasonForNoTypeInfo) >= 0 )
      {
        v6 = *pptypeinfo != 0;
      }
    }
    ZwClose(hregForward.h);
    wistd::unique_ptr<_KEY_VALUE_FULL_INFORMATION,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
      (wistd::unique_ptr<_KEY_VALUE_FULL_INFORMATION,wil::function_deleter<void (__cdecl*)(void *),&CoTaskMemFree> > *)&typeLib,
      0);
    if ( v6 )
      return 0;
  }
  v7 = StringCchPrintfW(keyPath, 0x104u, L"\\Registry\\Machine\\Software\\Classes\\Interface\\%ls\\TypeLib", &iidString);
  if ( v7 < 0 )
  {
    v12 = 428;
LABEL_9:
    wil::details::in1diag3::Return_Hr(retaddr, v12, "com\\ole32\\com\\txf\\callframe\\typeinfo.cpp", v7);
    return (unsigned int)v7;
  }
  hregTlbId.h = 0;
  *(_DWORD *)(&platform.MaximumLength + 1) = 0;
  v55 = 0;
  end = 0;
  RtlInitUnicodeString((PUNICODE_STRING)&end, keyPath);
  *(_DWORD *)&platform.Length = 48;
  p_end = &end;
  platform.Buffer = 0;
  v54 = 64;
  v56 = 0;
  v10 = ZwOpenKey(&hregTlbId.h, 0x20019u, (POBJECT_ATTRIBUTES)&platform);
  v7 = HrNt(v10);
  if ( v7 == -2147024894 )
  {
    *reasonForNoTypeInfo = -2147024894;
    return 0;
  }
  if ( v7 < 0 )
  {
    v12 = 437;
    goto LABEL_9;
  }
  wMajBest[0] = 0;
  wMinBest = 0;
  LODWORD(fHasVersion.m_ptr) = 0;
  libId = 0;
  v13 = SzLibIdOfIID(hregTlbId, &libId, wMajBest, &wMinBest, (int *)&fHasVersion);
  v7 = v13;
  if ( v13 == -2147024894 || v13 == -2147221165 )
  {
    *reasonForNoTypeInfo = v13;
    goto LABEL_53;
  }
  if ( v13 < 0 )
  {
    v36 = 453;
LABEL_65:
    wil::details::in1diag3::Return_Hr(retaddr, v36, "com\\ole32\\com\\txf\\callframe\\typeinfo.cpp", v13);
    goto LABEL_49;
  }
  if ( StringFromGUID2(&libId, libIdString.m_string, 39) != 39 )
    wil::details::in1diag3::_FailFast_Unexpected(retaddr, 0x19u, "onecore\\internal\\com\\inc\\combase\\ComGuid.hpp");
  v13 = StringCchPrintfW(keyPath, 0x104u, L"\\Registry\\Machine\\Software\\Classes\\TypeLib\\%ls", &libIdString);
  v7 = v13;
  if ( v13 < 0 )
  {
    v36 = 459;
    goto LABEL_65;
  }
  hregTlb.h = 0;
  *(_DWORD *)(&platform.MaximumLength + 1) = 0;
  v55 = 0;
  end = 0;
  RtlInitUnicodeString((PUNICODE_STRING)&end, keyPath);
  *(_DWORD *)&platform.Length = 48;
  p_end = &end;
  platform.Buffer = 0;
  v54 = 64;
  v56 = 0;
  v14 = ZwOpenKey(&hregTlb.h, 0x20019u, (POBJECT_ATTRIBUTES)&platform);
  v13 = HrNt(v14);
  v7 = v13;
  if ( v13 == -2147024894 )
  {
    *reasonForNoTypeInfo = -2147024894;
    v7 = 0;
    goto LABEL_49;
  }
  if ( v13 < 0 )
  {
    v36 = 468;
    goto LABEL_65;
  }
  memset_0(bestVersionString, 0, 0x208u);
  v15 = wMajBest[0];
  v16 = wMinBest;
  while ( 1 )
  {
    *(_QWORD *)&typeLib.Length = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      (wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(void *),&CoTaskMemFree,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > *)&typeLib,
      0);
    v17 = EnumerateRegistryKeys(hregTlb, v3, (wchar_t **)&typeLib);
    v7 = v17;
    if ( v17 < 0 )
    {
      v39 = 478;
LABEL_101:
      wil::details::in1diag3::Return_Hr(retaddr, v39, "com\\ole32\\com\\txf\\callframe\\typeinfo.cpp", v17);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(void *),&CoTaskMemFree,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > *)&typeLib);
      goto LABEL_48;
    }
    v18 = *(const wchar_t **)&typeLib.Length;
    if ( !*(_QWORD *)&typeLib.Length )
      break;
    *(_QWORD *)&end.Data1 = 0;
    v37 = wcstoul(*(const wchar_t **)&typeLib.Length, (wchar_t **)&end, 16);
    if ( **(_WORD **)&end.Data1 == 46 )
    {
      if ( (v38 = wcstoul((const wchar_t *)(*(_QWORD *)&end.Data1 + 2LL), 0, 16), !LODWORD(fHasVersion.m_ptr))
        && v37 > v15
        || v37 == v15 && v38 >= v16 )
      {
        v15 = v37;
        v16 = v38;
        v17 = StringCchCopyW(bestVersionString, 0x104u, v18);
        v7 = v17;
        if ( v17 < 0 )
        {
          v39 = 500;
          goto LABEL_101;
        }
      }
    }
    ++v3;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(void *),&CoTaskMemFree,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > *)&typeLib);
  }
  h = (wchar_t *)hregTlb.h;
  hregVersion.h = 0;
  *(_DWORD *)(&platform.MaximumLength + 1) = 0;
  typeLib = 0;
  v55 = 0;
  RtlInitUnicodeString(&typeLib, bestVersionString);
  *(_DWORD *)&platform.Length = 48;
  p_end = (_GUID *)&typeLib;
  platform.Buffer = h;
  v54 = 64;
  v56 = 0;
  v20 = ZwOpenKey(&hregVersion.h, 0x20019u, (POBJECT_ATTRIBUTES)&platform);
  v21 = HrNt(v20);
  v7 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, 0x1FCu, "com\\ole32\\com\\txf\\callframe\\typeinfo.cpp", v21);
LABEL_48:
    ZwClose(hregTlb.h);
LABEL_49:
    ZwClose(hregTlbId.h);
    return (unsigned int)v7;
  }
  for ( i = 0; ; ++i )
  {
    fHasVersion.m_ptr = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &fHasVersion,
      0);
    v23 = EnumerateRegistryKeys(hregVersion, i, &fHasVersion.m_ptr);
    v7 = v23;
    if ( v23 < 0 )
    {
      v40 = 517;
      goto LABEL_79;
    }
    m_ptr = fHasVersion.m_ptr;
    if ( !fHasVersion.m_ptr )
    {
      *reasonForNoTypeInfo = -2147319779;
      goto LABEL_52;
    }
    if ( FIsLCID(fHasVersion.m_ptr) )
      break;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&fHasVersion);
  }
  v25 = hregVersion.h;
  hregLang.h = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  platform = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  RtlInitUnicodeString(&platform, m_ptr);
  ObjectAttributes.RootDirectory = v25;
  ObjectAttributes.ObjectName = &platform;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.Length = 48;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v26 = ZwOpenKey(&hregLang.h, 0x20019u, &ObjectAttributes);
  v23 = HrNt(v26);
  v7 = v23;
  if ( v23 < 0 )
  {
    v40 = 528;
LABEL_79:
    wil::details::in1diag3::Return_Hr(retaddr, v40, "com\\ole32\\com\\txf\\callframe\\typeinfo.cpp", v23);
    goto LABEL_83;
  }
  v27 = hregLang.h;
  hregPlatform.h = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  platform = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  RtlInitUnicodeString(&platform, Com::Catalog::Constants::win64);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &platform;
  ObjectAttributes.RootDirectory = v27;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v28 = ZwOpenKey(&hregPlatform.h, 0x20019u, &ObjectAttributes);
  v29 = HrNt(v28);
  v7 = v29;
  if ( v29 != -2147024894 )
  {
    if ( v29 >= 0 )
      goto LABEL_31;
    wil::details::in1diag3::Return_Hr(retaddr, 0x22Cu, "com\\ole32\\com\\txf\\callframe\\typeinfo.cpp", v29);
LABEL_82:
    ZwClose(hregLang.h);
LABEL_83:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&fHasVersion);
LABEL_47:
    ZwClose(hregVersion.h);
    goto LABEL_48;
  }
  *(_QWORD *)&platform.Length = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    (wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(void *),&CoTaskMemFree,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > *)&platform,
    0);
  v42 = EnumerateRegistryKeys(hregLang, 0, (wchar_t **)&platform);
  v7 = v42;
  if ( v42 < 0 )
  {
    v41 = 545;
LABEL_81:
    wil::details::in1diag3::Return_Hr(retaddr, v41, "com\\ole32\\com\\txf\\callframe\\typeinfo.cpp", v42);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(void *),&CoTaskMemFree,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > *)&platform);
    goto LABEL_82;
  }
  if ( !*(_QWORD *)&platform.Length )
  {
    *reasonForNoTypeInfo = -2147319779;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(void *),&CoTaskMemFree,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > *)&platform);
LABEL_92:
    ZwClose(hregLang.h);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&fHasVersion);
    ZwClose(hregVersion.h);
    ZwClose(hregTlb.h);
    v7 = 0;
    goto LABEL_49;
  }
  v42 = OpenRegistryKey(&hregPlatform, hregLang, *(const wchar_t **)&platform.Length, 0x20019u, 0);
  v7 = v42;
  if ( v42 < 0 )
  {
    v41 = 552;
    goto LABEL_81;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(void *),&CoTaskMemFree,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > *)&platform);
LABEL_31:
  *(_QWORD *)&platform.Length = &valueInformation;
  valueInformation.__ptr_.__value_ = 0;
  platform.Buffer = 0;
  LOBYTE(p_end) = 1;
  v7 = GetRegistryValue(hregPlatform, &::value, (_KEY_VALUE_FULL_INFORMATION **)&platform.Buffer, v30);
  if ( (_BYTE)p_end )
    wistd::unique_ptr<_KEY_VALUE_FULL_INFORMATION,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
      *(wistd::unique_ptr<_KEY_VALUE_FULL_INFORMATION,wil::function_deleter<void (__cdecl*)(void *),&CoTaskMemFree> > **)&platform.Length,
      (_KEY_VALUE_FULL_INFORMATION *)platform.Buffer);
  if ( v7 == -2147024894 || v7 == -2147221165 )
  {
    *reasonForNoTypeInfo = v7;
LABEL_91:
    wistd::unique_ptr<_KEY_VALUE_FULL_INFORMATION,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
      &valueInformation,
      0);
    ZwClose(hregPlatform.h);
    goto LABEL_92;
  }
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, 0x23Au, "com\\ole32\\com\\txf\\callframe\\typeinfo.cpp", v7);
LABEL_96:
    wistd::unique_ptr<_KEY_VALUE_FULL_INFORMATION,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
      &valueInformation,
      0);
    ZwClose(hregPlatform.h);
    goto LABEL_82;
  }
  v31 = (const OLECHAR *)((char *)valueInformation.__ptr_.__value_ + valueInformation.__ptr_.__value_->DataOffset);
  *(_QWORD *)&typeLib.Length = 0;
  v32 = LoadTypeLibEx(v31, REGKIND_NONE, (ITypeLib **)&typeLib);
  v7 = v32;
  if ( v32 == -2147312566 || (unsigned int)(v32 + 2147287038) <= 1 )
  {
    *reasonForNoTypeInfo = v32;
    wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>((wil::com_ptr_t<IProxyServerIdentity,wil::err_returncode_policy> *)&typeLib);
    goto LABEL_91;
  }
  if ( v32 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, 0x246u, "com\\ole32\\com\\txf\\callframe\\typeinfo.cpp", v32);
    wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>((wil::com_ptr_t<IProxyServerIdentity,wil::err_returncode_policy> *)&typeLib);
    goto LABEL_96;
  }
  v7 = (*(__int64 (__fastcall **)(_QWORD, const _GUID *, ITypeInfo **))(**(_QWORD **)&typeLib.Length + 48LL))(
         *(_QWORD *)&typeLib.Length,
         v60,
         pptypeinfo);
  if ( v7 == -2147319765 )
  {
    *reasonForNoTypeInfo = -2147319765;
    goto LABEL_41;
  }
  if ( v7 < 0 )
  {
LABEL_41:
    wil::details::in1diag3::Return_Hr(retaddr, 0x24Du, "com\\ole32\\com\\txf\\callframe\\typeinfo.cpp", v7);
    if ( *(_QWORD *)&typeLib.Length )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&typeLib.Length + 16LL))(*(_QWORD *)&typeLib.Length);
    value = valueInformation.__ptr_.__value_;
    valueInformation.__ptr_.__value_ = 0;
    if ( value )
      CoTaskMemFree(value);
    ZwClose(hregPlatform.h);
    ZwClose(hregLang.h);
    if ( m_ptr )
      CoTaskMemFree(m_ptr);
    goto LABEL_47;
  }
  wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>((wil::com_ptr_t<IProxyServerIdentity,wil::err_returncode_policy> *)&typeLib);
  wistd::unique_ptr<_KEY_VALUE_FULL_INFORMATION,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
    &valueInformation,
    0);
  ZwClose(hregPlatform.h);
  ZwClose(hregLang.h);
LABEL_52:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&fHasVersion);
  ZwClose(hregVersion.h);
  ZwClose(hregTlb.h);
LABEL_53:
  ZwClose(hregTlbId.h);
  return 0;
}

```

## disassembly

```asm
0x180013f54  mov     [rsp-8+arg_18], rbx
0x180013f59  push    rbp
0x180013f5a  push    rsi
0x180013f5b  push    rdi
0x180013f5c  push    r12
0x180013f5e  push    r13
0x180013f60  push    r14
0x180013f62  push    r15
0x180013f64  lea     rbp, [rsp-4F0h]
0x180013f6c  sub     rsp, 5F0h
0x180013f73  mov     rax, cs:__security_cookie
0x180013f7a  xor     rax, rsp
0x180013f7d  mov     [rbp+520h+var_40], rax
0x180013f84  xor     r14d, r14d
0x180013f87  mov     [rbp+520h+var_538], iidIntercepted
0x180013f8b  mov     [pptypeinfo], r14
0x180013f8e  mov     rsi, reasonForNoTypeInfo
0x180013f91  mov     r13, pptypeinfo
0x180013f94  mov     [reasonForNoTypeInfo], r14d
0x180013f97  lea     pptypeinfo, [rbp+520h+iidString]; lpsz
0x180013f9b  lea     r15d, [r14+27h]
0x180013f9f  mov     r8d, r15d; cchMax
0x180013fa2  call    cs:__imp_StringFromGUID2
0x180013fa9  nop     dword ptr [rax+rax+00h]
0x180013fae  cmp     eax, r15d
0x180013fb1  jnz     loc_1800146BE
0x180013fb7  mov     r12d, 208h
0x180013fbd  lea     iidIntercepted, [rbp+520h+keyPath]; void *
0x180013fc4  mov     r8d, r12d; Size
0x180013fc7  xor     edx, edx; Val
0x180013fc9  call    memset_0
0x180013fce  lea     r9, [rbp+520h+iidString]
0x180013fd2  mov     edx, 104h; cchDest
0x180013fd7  lea     reasonForNoTypeInfo, aRegistryMachin; "\\Registry\\Machine\\Software\\Classes"...
0x180013fde  mov     dil, r14b
0x180013fe1  lea     iidIntercepted, [rbp+520h+keyPath]; pszDest
0x180013fe8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180013fed  mov     ebx, eax
0x180013fef  test    eax, eax
0x180013ff1  js      loc_18001415C
0x180013ff7  xorps   xmm0, xmm0
0x180013ffa  mov     [rbp+520h+hregForward.h], r14
0x180013ffe  lea     pptypeinfo, [rbp+520h+keyPath]; SourceString
0x180014005  mov     dword ptr [rsp+620h+platform.m_ptr+4], r14d
0x18001400a  lea     iidIntercepted, [rbp+520h+end]; DestinationString
0x18001400e  mov     [rbp+520h+var_58C], r14d
0x180014012  movups  [rbp+520h+end], xmm0
0x180014016  call    cs:__imp_RtlInitUnicodeString
0x18001401d  nop     dword ptr [rax+rax+00h]
0x180014022  lea     rax, [rbp+520h+end]
0x180014026  mov     dword ptr [rsp+620h+platform.m_ptr], 30h ; '0'
0x18001402e  xorps   xmm0, xmm0
0x180014031  mov     [rbp+520h+var_598], rax
0x180014035  lea     reasonForNoTypeInfo, [rsp+620h+platform]; ObjectAttributes
0x18001403a  mov     [rbp+520h+ppinfo], r14
0x18001403e  mov     edx, 20019h; DesiredAccess
0x180014043  mov     [rbp+520h+var_590], 40h ; '@'
0x18001404a  lea     iidIntercepted, [rbp+520h+hregForward]; KeyHandle
0x18001404e  movdqu  [rbp+520h+var_588], xmm0
0x180014053  call    cs:__imp_ZwOpenKey
0x18001405a  nop     dword ptr [rax+rax+00h]
0x18001405f  mov     ecx, eax; status
0x180014061  call    HrNt
0x180014066  test    eax, eax
0x180014068  jns     loc_1800146D7
0x18001406e  lea     r9, [rbp+520h+iidString]
0x180014072  mov     edx, 104h; cchDest
0x180014077  lea     reasonForNoTypeInfo, aRegistryMachin_3; "\\Registry\\Machine\\Software\\Classes"...
0x18001407e  lea     iidIntercepted, [rbp+520h+keyPath]; pszDest
0x180014085  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001408a  mov     ebx, eax
0x18001408c  test    eax, eax
0x18001408e  js      loc_18001413D
0x180014094  xorps   xmm0, xmm0
0x180014097  mov     [rbp+520h+hregTlbId.h], r14
0x18001409b  lea     pptypeinfo, [rbp+520h+keyPath]; SourceString
0x1800140a2  mov     dword ptr [rsp+620h+platform.m_ptr+4], r14d
0x1800140a7  lea     iidIntercepted, [rbp+520h+end]; DestinationString
0x1800140ab  mov     [rbp+520h+var_58C], r14d
0x1800140af  movups  [rbp+520h+end], xmm0
0x1800140b3  call    cs:__imp_RtlInitUnicodeString
0x1800140ba  nop     dword ptr [rax+rax+00h]
0x1800140bf  lea     rax, [rbp+520h+end]
0x1800140c3  mov     dword ptr [rsp+620h+platform.m_ptr], 30h ; '0'
0x1800140cb  xorps   xmm0, xmm0
0x1800140ce  mov     [rbp+520h+var_598], rax
0x1800140d2  lea     reasonForNoTypeInfo, [rsp+620h+platform]; ObjectAttributes
0x1800140d7  mov     [rbp+520h+ppinfo], r14
0x1800140db  mov     edx, 20019h; DesiredAccess
0x1800140e0  mov     [rbp+520h+var_590], 40h ; '@'
0x1800140e7  lea     iidIntercepted, [rbp+520h+hregTlbId]; KeyHandle
0x1800140eb  movdqu  [rbp+520h+var_588], xmm0
0x1800140f0  call    cs:__imp_ZwOpenKey
0x1800140f7  nop     dword ptr [rax+rax+00h]
0x1800140fc  mov     ecx, eax; status
0x1800140fe  call    HrNt
0x180014103  mov     edi, 80070002h
0x180014108  mov     ebx, eax
0x18001410a  cmp     eax, edi
0x18001410c  jnz     short loc_180014163
0x18001410e  mov     [rsi], edi
0x180014110  xor     eax, eax
0x180014112  mov     iidIntercepted, [rbp+520h+var_40]
0x180014119  xor     iidIntercepted, rsp; StackCookie
0x18001411c  call    __security_check_cookie
0x180014121  mov     rbx, [rsp+620h+arg_18]
0x180014129  add     rsp, 5F0h
0x180014130  pop     r15
0x180014132  pop     r14
0x180014134  pop     r13
0x180014136  pop     r12
0x180014138  pop     rdi
0x180014139  pop     rsi
0x18001413a  pop     rbp
0x18001413b  retn
0x18001413d  mov     edx, 1ACh; lineNumber
0x180014142  mov     iidIntercepted, [rbp+528h]; callerReturnAddress
0x180014149  lea     reasonForNoTypeInfo, aComOle32ComTxf_3; "com\\ole32\\com\\txf\\callframe\\typein"...
0x180014150  mov     r9d, ebx; hr
0x180014153  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014158  mov     eax, ebx
0x18001415a  jmp     short loc_180014112
0x18001415c  mov     edx, 18Fh
0x180014161  jmp     short loc_180014142
0x180014163  test    ebx, ebx
0x180014165  js      loc_180014779
0x18001416b  mov     iidIntercepted, [rbp+520h+hregTlbId.h]; hregTlb
0x18001416f  lea     rax, [rsp+620h+fHasVersion]
0x180014174  xorps   xmm0, xmm0
0x180014177  mov     [rsp+620h+pfHasVersion], rax; pfHasVersion
0x18001417c  lea     r9, [rsp+620h+wMinBest]; pwMin
0x180014181  mov     [rsp+620h+wMajBest], r14w
0x180014187  lea     reasonForNoTypeInfo, [rsp+620h+wMajBest]; pwMaj
0x18001418c  mov     [rsp+620h+wMinBest], r14w
0x180014192  lea     pptypeinfo, [rbp+520h+libId]; plibid
0x180014196  mov     dword ptr [rsp+620h+fHasVersion], r14d
0x18001419b  movups  xmmword ptr [rbp+520h+libId.Data1], xmm0
0x18001419f  call    ?SzLibIdOfIID@@YAJUHREG@@PEAU_GUID@@PEAG2PEAH@Z; SzLibIdOfIID(HREG,_GUID *,ushort *,ushort *,int *)
0x1800141a4  mov     ebx, eax
0x1800141a6  cmp     eax, edi
0x1800141a8  jz      loc_180014AF2
0x1800141ae  cmp     eax, 80040153h
0x1800141b3  jz      loc_180014AF2
0x1800141b9  test    eax, eax
0x1800141bb  js      loc_180014783
0x1800141c1  mov     r8d, r15d; cchMax
0x1800141c4  lea     pptypeinfo, [rbp+520h+libIdString]; lpsz
0x1800141c8  lea     iidIntercepted, [rbp+520h+libId]; rguid
0x1800141cc  call    cs:__imp_StringFromGUID2
0x1800141d3  nop     dword ptr [rax+rax+00h]
0x1800141d8  cmp     eax, r15d
0x1800141db  jnz     loc_18001464A
0x1800141e1  lea     r9, [rbp+520h+libIdString]
0x1800141e5  mov     edx, 104h; cchDest
0x1800141ea  lea     reasonForNoTypeInfo, aRegistryMachin_0; "\\Registry\\Machine\\Software\\Classes"...
0x1800141f1  lea     iidIntercepted, [rbp+520h+keyPath]; pszDest
0x1800141f8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800141fd  mov     ebx, eax
0x1800141ff  test    eax, eax
0x180014201  js      loc_18001478A
0x180014207  xorps   xmm0, xmm0
0x18001420a  mov     [rsp+620h+hregTlb.h], r14
0x18001420f  lea     pptypeinfo, [rbp+520h+keyPath]; SourceString
0x180014216  mov     dword ptr [rsp+620h+platform.m_ptr+4], r14d
0x18001421b  lea     iidIntercepted, [rbp+520h+end]; DestinationString
0x18001421f  mov     [rbp+520h+var_58C], r14d
0x180014223  movups  [rbp+520h+end], xmm0
0x180014227  call    cs:__imp_RtlInitUnicodeString
0x18001422e  nop     dword ptr [rax+rax+00h]
0x180014233  lea     rax, [rbp+520h+end]
0x180014237  mov     dword ptr [rsp+620h+platform.m_ptr], 30h ; '0'
0x18001423f  xorps   xmm0, xmm0
0x180014242  mov     [rbp+520h+var_598], rax
0x180014246  lea     reasonForNoTypeInfo, [rsp+620h+platform]; ObjectAttributes
0x18001424b  mov     [rbp+520h+ppinfo], r14
0x18001424f  mov     edx, 20019h; DesiredAccess
0x180014254  mov     [rbp+520h+var_590], 40h ; '@'
0x18001425b  lea     iidIntercepted, [rsp+620h+hregTlb]; KeyHandle
0x180014260  movdqu  [rbp+520h+var_588], xmm0
0x180014265  call    cs:__imp_ZwOpenKey
0x18001426c  nop     dword ptr [rax+rax+00h]
0x180014271  mov     ecx, eax; status
0x180014273  call    HrNt
0x180014278  mov     ebx, eax
0x18001427a  cmp     eax, edi
0x18001427c  jz      loc_1800147B1
0x180014282  test    eax, eax
0x180014284  js      loc_180014791
0x18001428a  mov     reasonForNoTypeInfo, r12; Size
0x18001428d  lea     iidIntercepted, [rbp+520h+bestVersionString]; void *
0x180014294  xor     edx, edx; Val
0x180014296  call    memset_0
0x18001429b  movzx   r15d, [rsp+620h+wMajBest]
0x1800142a1  movzx   r12d, [rsp+620h+wMinBest]
0x1800142a7  and     [rsp+620h+typeLib.m_ptr], 0
0x1800142ad  lea     iidIntercepted, [rsp+620h+typeLib]; this
0x1800142b2  xor     edx, edx; ptr
0x1800142b4  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800142b9  mov     iidIntercepted, [rsp+620h+hregTlb.h]; hkey
0x1800142be  lea     reasonForNoTypeInfo, [rsp+620h+typeLib]; pwsz
0x1800142c3  mov     edx, r14d; index
0x1800142c6  call    EnumerateRegistryKeys
0x1800142cb  mov     ebx, eax
0x1800142cd  test    eax, eax
0x1800142cf  js      loc_180014AC8
0x1800142d5  mov     rbx, [rsp+620h+typeLib.m_ptr]
0x1800142da  test    rbx, rbx
0x1800142dd  jnz     loc_1800147BB
0x1800142e3  xor     r15d, r15d
0x1800142e6  test    rbx, rbx
0x1800142e9  jnz     loc_1800146AA
0x1800142ef  mov     rbx, [rsp+620h+hregTlb.h]
0x1800142f4  lea     pptypeinfo, [rbp+520h+bestVersionString]; SourceString
0x1800142fb  xorps   xmm0, xmm0
0x1800142fe  mov     [rsp+620h+hregVersion.h], r15
0x180014303  lea     iidIntercepted, [rsp+620h+typeLib]; DestinationString
0x180014308  mov     dword ptr [rsp+620h+platform.m_ptr+4], r15d
0x18001430d  movups  xmmword ptr [rsp+620h+typeLib.m_ptr], xmm0
0x180014312  mov     [rbp+520h+var_58C], r15d
0x180014316  call    cs:__imp_RtlInitUnicodeString
0x18001431d  nop     dword ptr [rax+rax+00h]
0x180014322  lea     rax, [rsp+620h+typeLib]
0x180014327  mov     dword ptr [rsp+620h+platform.m_ptr], 30h ; '0'
0x18001432f  xorps   xmm0, xmm0
0x180014332  mov     [rbp+520h+var_598], rax
0x180014336  mov     r12d, 20019h
0x18001433c  mov     [rbp+520h+ppinfo], rbx
0x180014340  mov     edx, r12d; DesiredAccess
0x180014343  mov     [rbp+520h+var_590], 40h ; '@'
0x18001434a  lea     reasonForNoTypeInfo, [rsp+620h+platform]; ObjectAttributes
0x18001434f  lea     iidIntercepted, [rsp+620h+hregVersion]; KeyHandle
0x180014354  movdqu  [rbp+520h+var_588], xmm0
0x180014359  call    cs:__imp_ZwOpenKey
0x180014360  nop     dword ptr [rax+rax+00h]
0x180014365  mov     ecx, eax; status
0x180014367  call    HrNt
0x18001436c  mov     ebx, eax
0x18001436e  test    eax, eax
0x180014370  js      loc_180014852
0x180014376  mov     r14d, r15d
0x180014379  xor     edx, edx; ptr
0x18001437b  mov     [rsp+620h+fHasVersion], r15
0x180014380  lea     iidIntercepted, [rsp+620h+fHasVersion]; this
0x180014385  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001438a  mov     iidIntercepted, [rsp+620h+hregVersion.h]; hkey
0x18001438f  lea     reasonForNoTypeInfo, [rsp+620h+fHasVersion]; pwsz
0x180014394  mov     edx, r14d; index
0x180014397  call    EnumerateRegistryKeys
0x18001439c  mov     ebx, eax
0x18001439e  test    eax, eax
0x1800143a0  js      loc_18001488B
0x1800143a6  mov     rdi, [rsp+620h+fHasVersion]
0x1800143ab  test    rdi, rdi
0x1800143ae  jz      loc_180014663
0x1800143b4  mov     iidIntercepted, rdi; wszLcid
0x1800143b7  call    ?FIsLCID@@YAHPEAG@Z; FIsLCID(ushort *)
0x1800143bc  test    eax, eax
0x1800143be  jz      loc_180014872
0x1800143c4  mov     rbx, [rsp+620h+hregVersion.h]
0x1800143c9  lea     iidIntercepted, [rsp+620h+platform]; DestinationString
0x1800143ce  xorps   xmm0, xmm0
0x1800143d1  mov     [rsp+620h+hregLang.h], r15
0x1800143d6  mov     pptypeinfo, rdi; SourceString
0x1800143d9  mov     dword ptr [rbp+520h+ObjectAttributes+4], r15d
0x1800143dd  movups  xmmword ptr [rsp+620h+platform.m_ptr], xmm0
0x1800143e2  mov     dword ptr [rbp+520h+ObjectAttributes+1Ch], r15d
0x1800143e6  call    cs:__imp_RtlInitUnicodeString
0x1800143ed  nop     dword ptr [rax+rax+00h]
0x1800143f2  lea     rax, [rsp+620h+platform]
0x1800143f7  mov     [rbp+520h+ObjectAttributes.RootDirectory], rbx
0x1800143fb  xorps   xmm0, xmm0
0x1800143fe  mov     [rbp+520h+ObjectAttributes.ObjectName], rax
0x180014402  mov     r14d, 30h ; '0'
0x180014408  mov     [rbp+520h+ObjectAttributes.Attributes], 40h ; '@'
0x18001440f  lea     reasonForNoTypeInfo, [rbp+520h+ObjectAttributes]; ObjectAttributes
0x180014413  mov     [rbp+520h+ObjectAttributes.Length], r14d
0x180014417  mov     edx, r12d; DesiredAccess
0x18001441a  lea     iidIntercepted, [rsp+620h+hregLang]; KeyHandle
0x18001441f  movdqu  xmmword ptr [rbp+520h+ObjectAttributes.SecurityDescriptor], xmm0
0x180014424  call    cs:__imp_ZwOpenKey
0x18001442b  nop     dword ptr [rax+rax+00h]
0x180014430  mov     ecx, eax; status
0x180014432  call    HrNt
0x180014437  mov     ebx, eax
0x180014439  test    eax, eax
0x18001443b  js      loc_180014884
0x180014441  mov     rbx, [rsp+620h+hregLang.h]
0x180014446  lea     pptypeinfo, ?win64@Constants@Catalog@Com@@3QBGB; SourceString
0x18001444d  xorps   xmm0, xmm0
0x180014450  mov     [rsp+620h+hregPlatform.h], r15
0x180014455  lea     iidIntercepted, [rsp+620h+platform]; DestinationString
0x18001445a  mov     dword ptr [rbp+520h+ObjectAttributes+4], r15d
0x18001445e  movups  xmmword ptr [rsp+620h+platform.m_ptr], xmm0
0x180014463  mov     dword ptr [rbp+520h+ObjectAttributes+1Ch], r15d
0x180014467  call    cs:__imp_RtlInitUnicodeString
0x18001446e  nop     dword ptr [rax+rax+00h]
0x180014473  lea     rax, [rsp+620h+platform]
0x180014478  mov     [rbp+520h+ObjectAttributes.Length], r14d
0x18001447c  xorps   xmm0, xmm0
0x18001447f  mov     [rbp+520h+ObjectAttributes.ObjectName], rax
  ... truncated ...
```
