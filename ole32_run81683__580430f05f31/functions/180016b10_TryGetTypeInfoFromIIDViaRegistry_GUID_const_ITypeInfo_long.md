# TryGetTypeInfoFromIIDViaRegistry(_GUID const &,ITypeInfo * *,long *)

- ea: `0x180016b10`
- end: `0x180017753`
- name: `?TryGetTypeInfoFromIIDViaRegistry@@YAJAEBU_GUID@@PEAPEAUITypeInfo@@PEAJ@Z`
- size: `3139`
- prototype: `HRESULT __fastcall(const _GUID *iidIntercepted, ITypeInfo **pptypeinfo, HRESULT *reasonForNoTypeInfo)`
- caller_count: `2`
- callee_count: `17`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800168f8`
- `0x180016b10`

## callees

- `0x180016b10`
- `0x18001775c`
- `0x1800177e4`
- `0x180017894`
- `0x1800185ec`
- `0x180018a34`
- `0x18001b0e4`
- `0x18001b810`
- `0x18003aecc`
- `0x18003ffb4`
- `0x18004197c`
- `0x1800420d0`
- `0x1800477a4`
- `0x180052390`
- `0x180053014`
- `0x1800573ec`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180016da7`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180016dc5`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18001754e`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18001756a`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180016da7`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180016dc5`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18001754e`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18001756a`
- `ntdll!ZwClose` at `0x180016ff3`
- `ntdll!ZwClose` at `0x180016ffe`
- `ntdll!ZwClose` at `0x180017012`
- `ntdll!ZwClose` at `0x18001701d`
- `ntdll!ZwClose` at `0x180017029`
- `ntdll!ZwClose` at `0x180017241`
- `ntdll!ZwClose` at `0x18001724c`
- `ntdll!ZwClose` at `0x180017256`
- `ntdll!ZwClose` at `0x180017279`
- `ntdll!ZwClose` at `0x180017284`
- `ntdll!ZwClose` at `0x180017298`
- `ntdll!ZwClose` at `0x1800172a3`
- `ntdll!ZwClose` at `0x1800172df`
- `ntdll!ZwClose` at `0x180017361`
- `ntdll!ZwClose` at `0x180017373`
- `ntdll!ZwClose` at `0x180017418`
- `ntdll!ZwClose` at `0x180017423`
- `ntdll!ZwClose` at `0x180016ff3`
- `ntdll!ZwClose` at `0x180016ffe`
- `ntdll!ZwClose` at `0x180017012`
- `ntdll!ZwClose` at `0x18001701d`
- `ntdll!ZwClose` at `0x180017029`
- `ntdll!ZwClose` at `0x180017241`
- `ntdll!ZwClose` at `0x18001724c`
- `ntdll!ZwClose` at `0x180017256`
- `ntdll!ZwClose` at `0x180017279`
- `ntdll!ZwClose` at `0x180017284`
- `ntdll!ZwClose` at `0x180017298`
- `ntdll!ZwClose` at `0x1800172a3`
- `ntdll!ZwClose` at `0x1800172df`
- `ntdll!ZwClose` at `0x180017361`
- `ntdll!ZwClose` at `0x180017373`
- `ntdll!ZwClose` at `0x180017418`
- `ntdll!ZwClose` at `0x180017423`
- `ntdll!RtlInitUnicodeString` at `0x180016bd0`
- `ntdll!RtlInitUnicodeString` at `0x180016c6a`
- `ntdll!RtlInitUnicodeString` at `0x180016e18`
- `ntdll!RtlInitUnicodeString` at `0x180016e88`
- `ntdll!RtlInitUnicodeString` at `0x1800170e4`
- `ntdll!RtlInitUnicodeString` at `0x1800171af`
- `ntdll!RtlInitUnicodeString` at `0x180016bd0`
- `ntdll!RtlInitUnicodeString` at `0x180016c6a`
- `ntdll!RtlInitUnicodeString` at `0x180016e18`
- `ntdll!RtlInitUnicodeString` at `0x180016e88`
- `ntdll!RtlInitUnicodeString` at `0x1800170e4`
- `ntdll!RtlInitUnicodeString` at `0x1800171af`
- `ntdll!ZwOpenKey` at `0x180016c0a`
- `ntdll!ZwOpenKey` at `0x180016ca4`
- `ntdll!ZwOpenKey` at `0x180016e47`
- `ntdll!ZwOpenKey` at `0x180016eb7`
- `ntdll!ZwOpenKey` at `0x18001711f`
- `ntdll!ZwOpenKey` at `0x1800171ee`
- `ntdll!ZwOpenKey` at `0x180016c0a`
- `ntdll!ZwOpenKey` at `0x180016ca4`
- `ntdll!ZwOpenKey` at `0x180016e47`
- `ntdll!ZwOpenKey` at `0x180016eb7`
- `ntdll!ZwOpenKey` at `0x18001711f`
- `ntdll!ZwOpenKey` at `0x1800171ee`
- `OLEAUT32!__imp_LoadTypeLibEx` at `0x180016f50`
- `OLEAUT32!__imp_LoadTypeLibEx` at `0x180016f50`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180016b5f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001708a`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180016b5f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001708a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016dd7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017007`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001704b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001728d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017313`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017388`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800173c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800173eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001742c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800175b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800175e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017612`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001768c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800176d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017713`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017736`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017741`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016dd7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017007`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001704b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001728d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017313`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017388`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800173c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800173eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001742c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800175b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800175e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017612`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001768c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800176d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017713`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017736`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017741`

## string_xrefs

- `0x180016b8f`: `\Registry\Machine\Software\Classes\Interface\%ls\Forward`
- `0x180016c29`: `\Registry\Machine\Software\Classes\Interface\%ls\TypeLib`
- `0x180016cf9`: `com\ole32\com\txf\callframe\typeinfo.cpp`
- `0x180016fb1`: `com\ole32\com\txf\callframe\typeinfo.cpp`
- `0x1800172b8`: `com\ole32\com\txf\callframe\typeinfo.cpp`
- `0x1800172f1`: `com\ole32\com\txf\callframe\typeinfo.cpp`
- `0x18001733a`: `com\ole32\com\txf\callframe\typeinfo.cpp`
- `0x180017522`: `com\ole32\com\txf\callframe\typeinfo.cpp`
- `0x1800175cb`: `com\ole32\com\txf\callframe\typeinfo.cpp`
- `0x1800175f4`: `com\ole32\com\txf\callframe\typeinfo.cpp`
- `0x180017624`: `com\ole32\com\txf\callframe\typeinfo.cpp`
- `0x180017675`: `com\ole32\com\txf\callframe\typeinfo.cpp`
- `0x18001769e`: `com\ole32\com\txf\callframe\typeinfo.cpp`
- `0x1800176be`: `com\ole32\com\txf\callframe\typeinfo.cpp`
- `0x1800176e9`: `com\ole32\com\txf\callframe\typeinfo.cpp`
- `0x1800170a2`: `\Registry\Machine\Software\Classes\TypeLib\%ls`
- `0x18001743e`: `onecore\internal\com\inc\combase\ComGuid.hpp`
- `0x1800174fa`: `onecore\internal\com\inc\combase\ComGuid.hpp`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
__int64 __fastcall TryGetTypeInfoFromIIDViaRegistry(
        const _GUID *iidIntercepted,
        ITypeInfo **pptypeinfo,
        HRESULT *reasonForNoTypeInfo)
{
  HRESULT v5; // ebx
  NTSTATUS v6; // eax
  unsigned int v7; // r9d
  ITypeLib *fCreate; // r14
  NTSTATUS v9; // eax
  unsigned int v10; // r9d
  unsigned int v12; // edx
  void *h; // rbx
  unsigned __int16 v14; // r13
  int RegistryValue; // edi
  unsigned int v16; // r9d
  ITypeLib *v17; // rbx
  const wchar_t *v18; // rcx
  int v19; // r12d
  unsigned __int16 v20; // ax
  void *v21; // rbx
  NTSTATUS v22; // eax
  HRESULT v23; // eax
  HRESULT v24; // ebx
  void *v25; // rbx
  NTSTATUS v26; // eax
  HRESULT v27; // eax
  unsigned int v28; // r9d
  const OLECHAR *v29; // rcx
  int v30; // eax
  _KEY_VALUE_FULL_INFORMATION *v31; // rcx
  int v32; // eax
  NTSTATUS v33; // eax
  unsigned int i; // r15d
  HRESULT v35; // eax
  wchar_t *v36; // rbx
  void *v37; // rbx
  NTSTATUS v38; // eax
  HRESULT v39; // eax
  unsigned int j; // ebx
  HRESULT v41; // eax
  void *v42; // rdi
  _KEY_VALUE_FULL_INFORMATION *value; // rcx
  wchar_t *v44; // rcx
  void *v45; // rbx
  ITypeLib *m_ptr; // rcx
  HRESULT v47; // eax
  void *v48; // rcx
  _KEY_VALUE_FULL_INFORMATION *v49; // rcx
  bool v50; // di
  unsigned int v51; // ebx
  const wchar_t *v52; // rcx
  HRESULT v53; // r9d
  unsigned int v54; // edx
  unsigned __int16 v55; // r14
  unsigned __int16 v56; // r10
  HRESULT v57; // eax
  __int16 v58; // r10
  HRESULT v59; // eax
  wistd::unique_ptr<_KEY_VALUE_FULL_INFORMATION,wil::function_deleter<void (__cdecl*)(void *),&CoTaskMemFree> > valueInformation; // [rsp+30h] [rbp-D0h] BYREF
  HREG hregTlb; // [rsp+38h] [rbp-C8h] BYREF
  wil::com_ptr_t<ITypeLib,wil::err_returncode_policy> typeLib; // [rsp+40h] [rbp-C0h] BYREF
  HREG hregVersion; // [rsp+48h] [rbp-B8h] BYREF
  HREG hregLang; // [rsp+50h] [rbp-B0h] BYREF
  HREG hregPlatform; // [rsp+58h] [rbp-A8h] BYREF
  _UNICODE_STRING platform; // [rsp+60h] [rbp-A0h] OVERLAPPED BYREF
  __int128 v67; // [rsp+70h] [rbp-90h]
  __int128 v68; // [rsp+80h] [rbp-80h]
  HREG hregTlbId; // [rsp+90h] [rbp-70h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp-68h] BYREF
  HREG hregForward; // [rsp+C8h] [rbp-38h] BYREF
  ITypeInfo **v72; // [rsp+D0h] [rbp-30h]
  const _GUID *v73; // [rsp+D8h] [rbp-28h]
  _GUID end; // [rsp+E0h] [rbp-20h] BYREF
  char v75; // [rsp+F0h] [rbp-10h]
  _GUID libId; // [rsp+F8h] [rbp-8h] BYREF
  GuidString iidString; // [rsp+110h] [rbp+10h] BYREF
  GuidString libIdString; // [rsp+160h] [rbp+60h] BYREF
  wchar_t keyPath[264]; // [rsp+1B0h] [rbp+B0h] BYREF
  wchar_t bestVersionString[264]; // [rsp+3C0h] [rbp+2C0h] BYREF
  void *retaddr; // [rsp+618h] [rbp+518h]

  v72 = pptypeinfo;
  *pptypeinfo = 0;
  *reasonForNoTypeInfo = 0;
  v73 = iidIntercepted;
  if ( StringFromGUID2(iidIntercepted, iidString.m_string, 39) != 39 )
    wil::details::in1diag3::_FailFast_Unexpected(retaddr, 0x19u, "onecore\\internal\\com\\inc\\combase\\ComGuid.hpp");
  memset_0(keyPath, 0, 0x208u);
  v5 = StringCchPrintfW(keyPath, 0x104u, L"\\Registry\\Machine\\Software\\Classes\\Interface\\%ls\\Forward", &iidString);
  if ( v5 < 0 )
  {
    v12 = 399;
    goto LABEL_10;
  }
  hregForward.h = 0;
  *(_DWORD *)(&platform.MaximumLength + 1) = 0;
  v67 = 0;
  end = 0;
  RtlInitUnicodeString((PUNICODE_STRING)&end, keyPath);
  *(_DWORD *)&platform.Length = 48;
  *(_QWORD *)&v67 = &end;
  platform.Buffer = 0;
  DWORD2(v67) = 64;
  v68 = 0;
  v6 = ZwOpenKey(&hregForward.h, 0x20019u, (POBJECT_ATTRIBUTES)&platform);
  if ( HrNt(v6) >= 0 )
  {
    *(_QWORD *)&end.Data1 = &typeLib;
    typeLib.m_ptr = 0;
    v50 = 0;
    *(_QWORD *)end.Data4 = 0;
    v75 = 1;
    v51 = (unsigned int)GetRegistryValue(hregForward, &::value, (_KEY_VALUE_FULL_INFORMATION **)end.Data4, v7) >> 31;
    wil::details::out_param_t<wistd::unique_ptr<_KEY_VALUE_FULL_INFORMATION,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_KEY_VALUE_FULL_INFORMATION,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>((wil::details::out_param_t<wistd::unique_ptr<_KEY_VALUE_FULL_INFORMATION,wil::function_deleter<void (__cdecl*)(void *),&CoTaskMemFree> > > *)&end);
    if ( (unsigned __int8)v51 != 1 )
    {
      v52 = (const wchar_t *)((char *)typeLib.m_ptr + LODWORD(typeLib.m_ptr[1].lpVtbl));
      end = 0;
      if ( GuidFromString(v52, &end) >= 0
        && TryGetTypeInfoFromIIDViaRegistry(&end, pptypeinfo, reasonForNoTypeInfo) >= 0 )
      {
        v50 = *pptypeinfo != 0;
      }
    }
    fCreate = 0;
    ZwClose(hregForward.h);
    m_ptr = typeLib.m_ptr;
    typeLib.m_ptr = 0;
    if ( m_ptr )
      CoTaskMemFree(m_ptr);
    if ( v50 )
      return 0;
  }
  else
  {
    fCreate = 0;
  }
  v5 = StringCchPrintfW(keyPath, 0x104u, L"\\Registry\\Machine\\Software\\Classes\\Interface\\%ls\\TypeLib", &iidString);
  if ( v5 < 0 )
  {
    v12 = 428;
LABEL_10:
    wil::details::in1diag3::Return_Hr(retaddr, v12, "com\\ole32\\com\\txf\\callframe\\typeinfo.cpp", v5);
    return (unsigned int)v5;
  }
  hregTlbId.h = 0;
  platform = 0;
  v67 = 0;
  v68 = 0;
  end = 0;
  RtlInitUnicodeString((PUNICODE_STRING)&end, keyPath);
  *(_DWORD *)&platform.Length = 48;
  *(_QWORD *)&v67 = &end;
  platform.Buffer = 0;
  DWORD2(v67) = 64;
  v68 = 0;
  v9 = ZwOpenKey(&hregTlbId.h, 0x20019u, (POBJECT_ATTRIBUTES)&platform);
  v5 = HrNt(v9);
  if ( v5 == -2147024894 )
  {
    *reasonForNoTypeInfo = -2147024894;
    return 0;
  }
  if ( v5 < 0 )
  {
    v12 = 437;
    goto LABEL_10;
  }
  h = hregTlbId.h;
  LODWORD(valueInformation.__ptr_.__value_) = 0;
  typeLib.m_ptr = 0;
  v14 = 0;
  libId = 0;
  RegistryValue = GetRegistryValue(hregTlbId, &::value, (_KEY_VALUE_FULL_INFORMATION **)&typeLib, v10);
  if ( RegistryValue
    || (fCreate = typeLib.m_ptr) != 0
    && (RegistryValue = GuidFromString(
                          (const wchar_t *)((char *)typeLib.m_ptr + LODWORD(typeLib.m_ptr[1].lpVtbl)),
                          &libId),
        CoTaskMemFree(fCreate),
        fCreate = 0,
        RegistryValue) )
  {
    if ( RegistryValue == -2147024894 || RegistryValue == -2147221165 )
    {
      *reasonForNoTypeInfo = RegistryValue;
      goto LABEL_59;
    }
    if ( RegistryValue < 0 )
    {
      v53 = RegistryValue;
      v54 = 453;
LABEL_96:
      wil::details::in1diag3::Return_Hr(retaddr, v54, "com\\ole32\\com\\txf\\callframe\\typeinfo.cpp", v53);
      goto LABEL_40;
    }
    goto LABEL_45;
  }
  typeLib.m_ptr = fCreate;
  if ( GetRegistryValue((HREG)h, L"Version", (_KEY_VALUE_FULL_INFORMATION **)&typeLib, v16)
    || (v17 = typeLib.m_ptr) == 0 )
  {
LABEL_45:
    v19 = (int)fCreate;
    goto LABEL_46;
  }
  v18 = (const wchar_t *)((char *)typeLib.m_ptr + LODWORD(typeLib.m_ptr[1].lpVtbl));
  *(_QWORD *)&platform.Length = fCreate;
  v19 = (int)fCreate;
  v20 = wcstoul(v18, (wchar_t **)&platform, 16);
  if ( **(_WORD **)&platform.Length == 46 )
  {
    v14 = v20;
    LOWORD(valueInformation.__ptr_.__value_) = wcstoul((const wchar_t *)(*(_QWORD *)&platform.Length + 2LL), 0, 16);
    v19 = 1;
  }
  CoTaskMemFree(v17);
LABEL_46:
  if ( StringFromGUID2(&libId, libIdString.m_string, 39) != 39 )
    wil::details::in1diag3::_FailFast_Unexpected(retaddr, 0x19u, "onecore\\internal\\com\\inc\\combase\\ComGuid.hpp");
  v32 = StringCchPrintfW(keyPath, 0x104u, L"\\Registry\\Machine\\Software\\Classes\\TypeLib\\%ls", &libIdString);
  RegistryValue = v32;
  if ( v32 < 0 )
  {
    v54 = 459;
LABEL_95:
    v53 = v32;
    goto LABEL_96;
  }
  hregTlb.h = fCreate;
  platform = 0;
  v67 = 0;
  v68 = 0;
  end = 0;
  RtlInitUnicodeString((PUNICODE_STRING)&end, keyPath);
  *(_DWORD *)&platform.Length = 48;
  *(_QWORD *)&v67 = &end;
  platform.Buffer = (wchar_t *)fCreate;
  DWORD2(v67) = 64;
  v68 = 0;
  v33 = ZwOpenKey(&hregTlb.h, 0x20019u, (POBJECT_ATTRIBUTES)&platform);
  v32 = HrNt(v33);
  RegistryValue = v32;
  if ( v32 == -2147024894 )
  {
    *reasonForNoTypeInfo = -2147024894;
LABEL_64:
    RegistryValue = (int)fCreate;
    goto LABEL_40;
  }
  if ( v32 < 0 )
  {
    v54 = 468;
    goto LABEL_95;
  }
  memset_0(bestVersionString, 0, 0x208u);
  for ( i = (unsigned int)fCreate; ; ++i )
  {
    *(_QWORD *)&platform.Length = fCreate;
    v35 = EnumerateRegistryKeys(hregTlb, i, (wchar_t **)&platform);
    RegistryValue = v35;
    if ( v35 < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, 0x1DEu, "com\\ole32\\com\\txf\\callframe\\typeinfo.cpp", v35);
      v44 = *(wchar_t **)&platform.Length;
      if ( *(_QWORD *)&platform.Length )
        goto LABEL_107;
      goto LABEL_66;
    }
    v36 = *(wchar_t **)&platform.Length;
    if ( !*(_QWORD *)&platform.Length )
      break;
    *(_QWORD *)&end.Data1 = fCreate;
    v55 = wcstoul(*(const wchar_t **)&platform.Length, (wchar_t **)&end, 16);
    if ( **(_WORD **)&end.Data1 == 46 )
    {
      if ( (v56 = wcstoul((const wchar_t *)(*(_QWORD *)&end.Data1 + 2LL), 0, 16), !v19) && v55 > v14
        || v55 == v14 && v56 >= LOWORD(valueInformation.__ptr_.__value_) )
      {
        v57 = StringCchCopyW(bestVersionString, 0x104u, v36);
        RegistryValue = v57;
        if ( v57 < 0 )
        {
          wil::details::in1diag3::Return_Hr(retaddr, 0x1F4u, "com\\ole32\\com\\txf\\callframe\\typeinfo.cpp", v57);
          v44 = v36;
LABEL_107:
          CoTaskMemFree(v44);
LABEL_66:
          ZwClose(hregTlb.h);
LABEL_40:
          ZwClose(hregTlbId.h);
          return (unsigned int)RegistryValue;
        }
        LOWORD(valueInformation.__ptr_.__value_) = v58;
        v14 = v55;
      }
    }
    CoTaskMemFree(v36);
    fCreate = 0;
  }
  v37 = hregTlb.h;
  hregVersion.h = fCreate;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  platform = 0;
  RtlInitUnicodeString(&platform, bestVersionString);
  ObjectAttributes.RootDirectory = v37;
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &platform;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v38 = ZwOpenKey(&hregVersion.h, 0x20019u, &ObjectAttributes);
  v39 = HrNt(v38);
  RegistryValue = v39;
  if ( v39 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, 0x1FCu, "com\\ole32\\com\\txf\\callframe\\typeinfo.cpp", v39);
    goto LABEL_66;
  }
  for ( j = (unsigned int)fCreate; ; ++j )
  {
    *(_QWORD *)&platform.Length = fCreate;
    v41 = EnumerateRegistryKeys(hregVersion, j, (wchar_t **)&platform);
    RegistryValue = v41;
    if ( v41 < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, 0x205u, "com\\ole32\\com\\txf\\callframe\\typeinfo.cpp", v41);
      if ( *(_QWORD *)&platform.Length )
        CoTaskMemFree(*(LPVOID *)&platform.Length);
      ZwClose(hregVersion.h);
      goto LABEL_66;
    }
    v42 = *(void **)&platform.Length;
    if ( !*(_QWORD *)&platform.Length )
    {
      *reasonForNoTypeInfo = -2147319779;
      goto LABEL_58;
    }
    if ( FIsLCID(*(wchar_t **)&platform.Length) )
      break;
    CoTaskMemFree(v42);
  }
  v21 = hregVersion.h;
  hregLang.h = fCreate;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  platform = 0;
  RtlInitUnicodeString(&platform, (PCWSTR)v42);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &platform;
  ObjectAttributes.RootDirectory = v21;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v22 = ZwOpenKey(&hregLang.h, 0x20019u, &ObjectAttributes);
  v23 = HrNt(v22);
  v24 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, 0x210u, "com\\ole32\\com\\txf\\callframe\\typeinfo.cpp", v23);
    goto LABEL_39;
  }
  v25 = hregLang.h;
  hregPlatform.h = fCreate;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  platform = 0;
  RtlInitUnicodeString(&platform, Com::Catalog::Constants::win64);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &platform;
  ObjectAttributes.RootDirectory = v25;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v26 = ZwOpenKey(&hregPlatform.h, 0x20019u, &ObjectAttributes);
  v27 = HrNt(v26);
  v24 = v27;
  if ( v27 == -2147024894 )
  {
    *(_QWORD *)&platform.Length = fCreate;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      (wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(void *),&CoTaskMemFree,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > *)&platform,
      0);
    v59 = EnumerateRegistryKeys(hregLang, 0, (wchar_t **)&platform);
    v24 = v59;
    if ( v59 < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, 0x221u, "com\\ole32\\com\\txf\\callframe\\typeinfo.cpp", v59);
      if ( *(_QWORD *)&platform.Length )
        CoTaskMemFree(*(LPVOID *)&platform.Length);
      goto LABEL_38;
    }
    v45 = *(void **)&platform.Length;
    if ( *(_QWORD *)&platform.Length )
    {
      v47 = OpenRegistryKey(&hregPlatform, hregLang, *(const wchar_t **)&platform.Length, 0x20019u, (int)fCreate);
      LODWORD(fCreate) = v47;
      if ( v47 >= 0 )
      {
        CoTaskMemFree(v45);
        fCreate = 0;
        goto LABEL_24;
      }
      wil::details::in1diag3::Return_Hr(retaddr, 0x228u, "com\\ole32\\com\\txf\\callframe\\typeinfo.cpp", v47);
      CoTaskMemFree(v45);
    }
    else
    {
      *reasonForNoTypeInfo = -2147319779;
    }
    goto LABEL_63;
  }
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, 0x22Cu, "com\\ole32\\com\\txf\\callframe\\typeinfo.cpp", v27);
    goto LABEL_38;
  }
LABEL_24:
  *(_QWORD *)&platform.Length = &valueInformation;
  valueInformation.__ptr_.__value_ = (_KEY_VALUE_FULL_INFORMATION *)fCreate;
  platform.Buffer = (wchar_t *)fCreate;
  LOBYTE(v67) = 1;
  v24 = GetRegistryValue(hregPlatform, &::value, (_KEY_VALUE_FULL_INFORMATION **)&platform.Buffer, v28);
  if ( (_BYTE)v67 != (_BYTE)fCreate )
  {
    v48 = **(void ***)&platform.Length;
    **(_QWORD **)&platform.Length = platform.Buffer;
    if ( v48 )
      CoTaskMemFree(v48);
  }
  if ( v24 == -2147024894 || v24 == -2147221165 )
  {
    *reasonForNoTypeInfo = v24;
    goto LABEL_60;
  }
  if ( v24 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, 0x23Au, "com\\ole32\\com\\txf\\callframe\\typeinfo.cpp", v24);
    goto LABEL_35;
  }
  v29 = (const OLECHAR *)((char *)valueInformation.__ptr_.__value_ + valueInformation.__ptr_.__value_->DataOffset);
  typeLib.m_ptr = fCreate;
  v30 = LoadTypeLibEx(v29, REGKIND_NONE, &typeLib.m_ptr);
  v24 = v30;
  if ( v30 == -2147312566 || (unsigned int)(v30 + 2147287038) <= 1 )
  {
    *reasonForNoTypeInfo = v30;
    wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>((wil::com_ptr_t<IProxyServerIdentity,wil::err_returncode_policy> *)&typeLib);
LABEL_60:
    value = valueInformation.__ptr_.__value_;
    valueInformation.__ptr_.__value_ = (_KEY_VALUE_FULL_INFORMATION *)fCreate;
    if ( value )
      CoTaskMemFree(value);
    ZwClose(hregPlatform.h);
LABEL_63:
    ZwClose(hregLang.h);
    CoTaskMemFree(v42);
    ZwClose(hregVersion.h);
    ZwClose(hregTlb.h);
    goto LABEL_64;
  }
  if ( v30 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, 0x246u, "com\\ole32\\com\\txf\\callframe\\typeinfo.cpp", v30);
    wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>((wil::com_ptr_t<IProxyServerIdentity,wil::err_returncode_policy> *)&typeLib);
    goto LABEL_35;
  }
  v24 = ((__int64 (__fastcall *)(ITypeLib *, const _GUID *, ITypeInfo **))typeLib.m_ptr->lpVtbl[2].QueryInterface)(
          typeLib.m_ptr,
          v73,
          v72);
  if ( v24 == -2147319765 )
  {
    *reasonForNoTypeInfo = -2147319765;
    goto LABEL_33;
  }
  if ( v24 < 0 )
  {
LABEL_33:
    wil::details::in1diag3::Return_Hr(retaddr, 0x24Du, "com\\ole32\\com\\txf\\callframe\\typeinfo.cpp", v24);
    if ( typeLib.m_ptr )
      ((void (__fastcall *)(ITypeLib *))typeLib.m_ptr->lpVtbl->Release)(typeLib.m_ptr);
LABEL_35:
    v31 = valueInformation.__ptr_.__value_;
    valueInformation.__ptr_.__value_ = (_KEY_VALUE_FULL_INFORMATION *)fCreate;
    if ( v31 )
      CoTaskMemFree(v31);
    ZwClose(hregPlatform.h);
LABEL_38:
    ZwClose(hregLang.h);
LABEL_39:
    CoTaskMemFree(v42);
    ZwClose(hregVersion.h);
    ZwClose(hregTlb.h);
    RegistryValue = v24;
    goto LABEL_40;
  }
  wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>((wil::com_ptr_t<IProxyServerIdentity,wil::err_returncode_policy> *)&typeLib);
  v49 = valueInformation.__ptr_.__value_;
  valueInformation.__ptr_.__value_ = (_KEY_VALUE_FULL_INFORMATION *)fCreate;
  if ( v49 )
    CoTaskMemFree(v49);
  ZwClose(hregPlatform.h);
  ZwClose(hregLang.h);
  CoTaskMemFree(v42);
LABEL_58:
  ZwClose(hregVersion.h);
  ZwClose(hregTlb.h);
LABEL_59:
  ZwClose(hregTlbId.h);
  return 0;
}

```

## disassembly

```asm
0x180016b10  mov     [rsp-8+arg_18], rbx
0x180016b15  push    rbp
0x180016b16  push    rsi
0x180016b17  push    rdi
0x180016b18  push    r12
0x180016b1a  push    r13
0x180016b1c  push    r14
0x180016b1e  push    r15
0x180016b20  lea     rbp, [rsp-4E0h]
0x180016b28  sub     rsp, 5E0h
0x180016b2f  mov     rax, cs:__security_cookie
0x180016b36  xor     rax, rsp
0x180016b39  mov     [rbp+510h+var_40], rax
0x180016b40  xor     r15d, r15d
0x180016b43  mov     [rbp+510h+var_540], pptypeinfo
0x180016b47  mov     [pptypeinfo], r15
0x180016b4a  mov     rsi, reasonForNoTypeInfo
0x180016b4d  mov     r14, pptypeinfo
0x180016b50  mov     [reasonForNoTypeInfo], r15d
0x180016b53  lea     pptypeinfo, [rbp+510h+iidString]; lpsz
0x180016b57  mov     [rbp+510h+var_538], iidIntercepted
0x180016b5b  lea     r8d, [r15+27h]; cchMax
0x180016b5f  call    cs:__imp_StringFromGUID2
0x180016b65  cmp     eax, 27h ; '''
0x180016b68  jnz     loc_180017437
0x180016b6e  xor     edx, edx; Val
0x180016b70  lea     iidIntercepted, [rbp+510h+keyPath]; void *
0x180016b77  mov     r8d, 208h; Size
0x180016b7d  call    memset_0
0x180016b82  mov     r12d, 104h
0x180016b88  lea     r9, [rbp+510h+iidString]
0x180016b8c  mov     edx, r12d; cchDest
0x180016b8f  lea     reasonForNoTypeInfo, aRegistryMachin; "\\Registry\\Machine\\Software\\Classes"...
0x180016b96  lea     iidIntercepted, [rbp+510h+keyPath]; pszDest
0x180016b9d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180016ba2  mov     ebx, eax
0x180016ba4  test    eax, eax
0x180016ba6  js      loc_180016D0C
0x180016bac  xorps   xmm0, xmm0
0x180016baf  mov     [rbp+510h+hregForward.h], r15
0x180016bb3  lea     pptypeinfo, [rbp+510h+keyPath]; SourceString
0x180016bba  lea     iidIntercepted, [rbp+510h+end]; DestinationString
0x180016bbe  movups  xmmword ptr [rsp+610h+platform.m_ptr], xmm0
0x180016bc3  movups  [rsp+610h+var_5A0], xmm0
0x180016bc8  movups  [rbp+510h+var_590], xmm0
0x180016bcc  movups  [rbp+510h+end], xmm0
0x180016bd0  call    cs:__imp_RtlInitUnicodeString
0x180016bd6  lea     rax, [rbp+510h+end]
0x180016bda  mov     dword ptr [rsp+610h+platform.m_ptr], 30h ; '0'
0x180016be2  xorps   xmm0, xmm0
0x180016be5  mov     qword ptr [rsp+610h+var_5A0], rax
0x180016bea  lea     reasonForNoTypeInfo, [rsp+610h+platform]; ObjectAttributes
0x180016bef  mov     [rsp+610h+ppinfo], r15
0x180016bf4  mov     edx, 20019h; DesiredAccess
0x180016bf9  mov     dword ptr [rsp+610h+var_5A0+8], 40h ; '@'
0x180016c01  lea     iidIntercepted, [rbp+510h+hregForward]; KeyHandle
0x180016c05  movdqu  [rbp+510h+var_590], xmm0
0x180016c0a  call    cs:__imp_ZwOpenKey
0x180016c10  mov     ecx, eax; status
0x180016c12  call    HrNt
0x180016c17  test    eax, eax
0x180016c19  jns     loc_180017450
0x180016c1f  xor     r14d, r14d
0x180016c22  lea     r9, [rbp+510h+iidString]
0x180016c26  mov     pptypeinfo, r12; cchDest
0x180016c29  lea     reasonForNoTypeInfo, aRegistryMachin_3; "\\Registry\\Machine\\Software\\Classes"...
0x180016c30  lea     iidIntercepted, [rbp+510h+keyPath]; pszDest
0x180016c37  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180016c3c  mov     ebx, eax
0x180016c3e  test    eax, eax
0x180016c40  js      loc_180016CED
0x180016c46  xorps   xmm0, xmm0
0x180016c49  mov     [rbp+510h+hregTlbId.h], r14
0x180016c4d  lea     pptypeinfo, [rbp+510h+keyPath]; SourceString
0x180016c54  lea     iidIntercepted, [rbp+510h+end]; DestinationString
0x180016c58  movups  xmmword ptr [rsp+610h+platform.m_ptr], xmm0
0x180016c5d  movups  [rsp+610h+var_5A0], xmm0
0x180016c62  movups  [rbp+510h+var_590], xmm0
0x180016c66  movups  [rbp+510h+end], xmm0
0x180016c6a  call    cs:__imp_RtlInitUnicodeString
0x180016c70  lea     rax, [rbp+510h+end]
0x180016c74  mov     dword ptr [rsp+610h+platform.m_ptr], 30h ; '0'
0x180016c7c  xorps   xmm0, xmm0
0x180016c7f  mov     qword ptr [rsp+610h+var_5A0], rax
0x180016c84  lea     reasonForNoTypeInfo, [rsp+610h+platform]; ObjectAttributes
0x180016c89  mov     [rsp+610h+ppinfo], r14
0x180016c8e  mov     edx, 20019h; DesiredAccess
0x180016c93  mov     dword ptr [rsp+610h+var_5A0+8], 40h ; '@'
0x180016c9b  lea     iidIntercepted, [rbp+510h+hregTlbId]; KeyHandle
0x180016c9f  movdqu  [rbp+510h+var_590], xmm0
0x180016ca4  call    cs:__imp_ZwOpenKey
0x180016caa  mov     ecx, eax; status
0x180016cac  call    HrNt
0x180016cb1  mov     r15d, 80070002h
0x180016cb7  mov     ebx, eax
0x180016cb9  cmp     eax, r15d
0x180016cbc  jnz     short loc_180016D13
0x180016cbe  mov     [rsi], r15d
0x180016cc1  xor     eax, eax
0x180016cc3  mov     iidIntercepted, [rbp+510h+var_40]
0x180016cca  xor     iidIntercepted, rsp; StackCookie
0x180016ccd  call    __security_check_cookie
0x180016cd2  mov     rbx, [rsp+610h+arg_18]
0x180016cda  add     rsp, 5E0h
0x180016ce1  pop     r15
0x180016ce3  pop     r14
0x180016ce5  pop     r13
0x180016ce7  pop     r12
0x180016ce9  pop     rdi
0x180016cea  pop     rsi
0x180016ceb  pop     rbp
0x180016cec  retn
0x180016ced  mov     edx, 1ACh; lineNumber
0x180016cf2  mov     iidIntercepted, [rbp+518h]; callerReturnAddress
0x180016cf9  lea     reasonForNoTypeInfo, aComOle32ComTxf_3; "com\\ole32\\com\\txf\\callframe\\typein"...
0x180016d00  mov     r9d, ebx; hr
0x180016d03  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016d08  mov     eax, ebx
0x180016d0a  jmp     short loc_180016CC3
0x180016d0c  mov     edx, 18Fh
0x180016d11  jmp     short loc_180016CF2
0x180016d13  test    ebx, ebx
0x180016d15  js      loc_1800174DF
0x180016d1b  mov     rbx, [rbp+510h+hregTlbId.h]
0x180016d1f  lea     reasonForNoTypeInfo, [rsp+610h+typeLib]; ppinfo
0x180016d24  xorps   xmm0, xmm0
0x180016d27  mov     dword ptr [rsp+610h+valueInformation.__ptr_.__value_], r14d
0x180016d2c  mov     iidIntercepted, rbx; hkey
0x180016d2f  mov     [rsp+610h+typeLib.m_ptr], r14
0x180016d34  lea     pptypeinfo, value; wszValue
0x180016d3b  mov     r13d, r14d
0x180016d3e  movups  xmmword ptr [rbp+510h+libId.Data1], xmm0
0x180016d42  call    GetRegistryValue
0x180016d47  mov     edi, eax
0x180016d49  test    eax, eax
0x180016d4b  jnz     loc_18001705C
0x180016d51  mov     r14, [rsp+610h+typeLib.m_ptr]
0x180016d56  test    r14, r14
0x180016d59  jnz     loc_180017036
0x180016d5f  lea     reasonForNoTypeInfo, [rsp+610h+typeLib]; ppinfo
0x180016d64  mov     [rsp+610h+typeLib.m_ptr], r14
0x180016d69  lea     pptypeinfo, aVersion; "Version"
0x180016d70  mov     iidIntercepted, rbx; hkey
0x180016d73  call    GetRegistryValue
0x180016d78  test    eax, eax
0x180016d7a  jnz     loc_180017079
0x180016d80  mov     rbx, [rsp+610h+typeLib.m_ptr]
0x180016d85  test    rbx, rbx
0x180016d88  jz      loc_180017079
0x180016d8e  mov     ecx, [rbx+8]
0x180016d91  lea     edi, [rax+10h]
0x180016d94  add     iidIntercepted, rbx; String
0x180016d97  mov     [rsp+610h+platform.m_ptr], r14
0x180016d9c  mov     r8d, edi; Radix
0x180016d9f  lea     pptypeinfo, [rsp+610h+platform]; EndPtr
0x180016da4  mov     r12d, r14d
0x180016da7  call    cs:__imp_wcstoul
0x180016dad  mov     iidIntercepted, [rsp+610h+platform.m_ptr]
0x180016db2  cmp     word ptr [iidIntercepted], 2Eh ; '.'
0x180016db6  jnz     short loc_180016DD4
0x180016db8  add     iidIntercepted, 2; String
0x180016dbc  mov     r8d, edi; Radix
0x180016dbf  xor     edx, edx; EndPtr
0x180016dc1  movzx   r13d, ax
0x180016dc5  call    cs:__imp_wcstoul
0x180016dcb  mov     word ptr [rsp+610h+valueInformation.__ptr_.__value_], ax
0x180016dd0  lea     r12d, [rdi-0Fh]
0x180016dd4  mov     iidIntercepted, rbx; pv
0x180016dd7  call    cs:__imp_CoTaskMemFree
0x180016ddd  jmp     loc_18001707C
0x180016de2  mov     iidIntercepted, rdi; wszLcid
0x180016de5  call    ?FIsLCID@@YAHPEAG@Z; FIsLCID(ushort *)
0x180016dea  test    eax, eax
0x180016dec  jz      loc_18001760D
0x180016df2  mov     rbx, [rsp+610h+hregVersion.h]
0x180016df7  lea     iidIntercepted, [rsp+610h+platform]; DestinationString
0x180016dfc  xorps   xmm0, xmm0
0x180016dff  mov     [rsp+610h+hregLang.h], r14
0x180016e04  mov     pptypeinfo, rdi; SourceString
0x180016e07  movups  xmmword ptr [rbp+510h+ObjectAttributes.Length], xmm0
0x180016e0b  movups  xmmword ptr [rbp+510h+ObjectAttributes.ObjectName], xmm0
0x180016e0f  movups  xmmword ptr [rbp+510h+ObjectAttributes.SecurityDescriptor], xmm0
0x180016e13  movups  xmmword ptr [rsp+610h+platform.m_ptr], xmm0
0x180016e18  call    cs:__imp_RtlInitUnicodeString
0x180016e1e  lea     rax, [rsp+610h+platform]
0x180016e23  mov     [rbp+510h+ObjectAttributes.Length], r15d
0x180016e27  xorps   xmm0, xmm0
0x180016e2a  mov     [rbp+510h+ObjectAttributes.ObjectName], rax
0x180016e2e  lea     reasonForNoTypeInfo, [rbp+510h+ObjectAttributes]; ObjectAttributes
0x180016e32  mov     [rbp+510h+ObjectAttributes.RootDirectory], rbx
0x180016e36  mov     edx, r12d; DesiredAccess
0x180016e39  mov     [rbp+510h+ObjectAttributes.Attributes], r13d
0x180016e3d  lea     iidIntercepted, [rsp+610h+hregLang]; KeyHandle
0x180016e42  movdqu  xmmword ptr [rbp+510h+ObjectAttributes.SecurityDescriptor], xmm0
0x180016e47  call    cs:__imp_ZwOpenKey
0x180016e4d  mov     ecx, eax; status
0x180016e4f  call    HrNt
0x180016e54  mov     ebx, eax
0x180016e56  test    eax, eax
0x180016e58  js      loc_18001761D
0x180016e5e  mov     rbx, [rsp+610h+hregLang.h]
0x180016e63  lea     pptypeinfo, ?win64@Constants@Catalog@Com@@3QBGB; SourceString
0x180016e6a  xorps   xmm0, xmm0
0x180016e6d  mov     [rsp+610h+hregPlatform.h], r14
0x180016e72  lea     iidIntercepted, [rsp+610h+platform]; DestinationString
0x180016e77  movups  xmmword ptr [rbp+510h+ObjectAttributes.Length], xmm0
0x180016e7b  movups  xmmword ptr [rbp+510h+ObjectAttributes.ObjectName], xmm0
0x180016e7f  movups  xmmword ptr [rbp+510h+ObjectAttributes.SecurityDescriptor], xmm0
0x180016e83  movups  xmmword ptr [rsp+610h+platform.m_ptr], xmm0
0x180016e88  call    cs:__imp_RtlInitUnicodeString
0x180016e8e  lea     rax, [rsp+610h+platform]
0x180016e93  mov     [rbp+510h+ObjectAttributes.Length], r15d
0x180016e97  xorps   xmm0, xmm0
0x180016e9a  mov     [rbp+510h+ObjectAttributes.ObjectName], rax
0x180016e9e  lea     reasonForNoTypeInfo, [rbp+510h+ObjectAttributes]; ObjectAttributes
0x180016ea2  mov     [rbp+510h+ObjectAttributes.RootDirectory], rbx
0x180016ea6  mov     edx, r12d; DesiredAccess
0x180016ea9  mov     [rbp+510h+ObjectAttributes.Attributes], r13d
0x180016ead  lea     iidIntercepted, [rsp+610h+hregPlatform]; KeyHandle
0x180016eb2  movdqu  xmmword ptr [rbp+510h+ObjectAttributes.SecurityDescriptor], xmm0
0x180016eb7  call    cs:__imp_ZwOpenKey
0x180016ebd  mov     ecx, eax; status
0x180016ebf  call    HrNt
0x180016ec4  mov     r15d, 80070002h
0x180016eca  mov     ebx, eax
0x180016ecc  cmp     eax, r15d
0x180016ecf  jz      loc_18001763D
0x180016ed5  test    eax, eax
0x180016ed7  js      loc_180017697
0x180016edd  mov     iidIntercepted, [rsp+610h+hregPlatform.h]; hkey
0x180016ee2  lea     rax, [rsp+610h+valueInformation]
0x180016ee7  lea     reasonForNoTypeInfo, [rsp+610h+ppinfo]; ppinfo
0x180016eec  mov     [rsp+610h+platform.m_ptr], rax
0x180016ef1  lea     pptypeinfo, value; wszValue
0x180016ef8  mov     [rsp+610h+valueInformation.__ptr_.__value_], r14
0x180016efd  mov     [rsp+610h+ppinfo], r14
0x180016f02  mov     byte ptr [rsp+610h+var_5A0], 1
0x180016f07  call    GetRegistryValue
0x180016f0c  mov     ebx, eax
0x180016f0e  cmp     byte ptr [rsp+610h+var_5A0], r14b
0x180016f13  jnz     loc_1800173D2
0x180016f19  cmp     ebx, r15d
0x180016f1c  jz      loc_18001772F
0x180016f22  cmp     ebx, 80040153h
0x180016f28  jz      loc_18001772F
0x180016f2e  test    ebx, ebx
0x180016f30  js      loc_1800176B7
0x180016f36  mov     rax, [rsp+610h+valueInformation.__ptr_.__value_]
0x180016f3b  lea     reasonForNoTypeInfo, [rsp+610h+typeLib]; pptlib
0x180016f40  mov     edx, 2; regkind
0x180016f45  mov     ecx, [rax+8]
0x180016f48  add     iidIntercepted, rax; szFile
0x180016f4b  mov     [rsp+610h+typeLib.m_ptr], r14
0x180016f50  call    cs:__imp_LoadTypeLibEx
0x180016f56  mov     ebx, eax
0x180016f58  cmp     eax, 80029C4Ah
0x180016f5d  jz      loc_18001771E
0x180016f63  lea     ecx, [rax+7FFCFFFEh]
0x180016f69  cmp     ecx, 1
0x180016f6c  jbe     loc_18001771E
0x180016f72  test    eax, eax
0x180016f74  js      loc_1800176E2
0x180016f7a  mov     iidIntercepted, [rsp+610h+typeLib.m_ptr]
0x180016f7f  mov     reasonForNoTypeInfo, [rbp+510h+var_540]
0x180016f83  mov     pptypeinfo, [rbp+510h+var_538]
0x180016f87  mov     rax, [iidIntercepted]
0x180016f8a  mov     rax, [rax+30h]
0x180016f8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f93  mov     ebx, eax
0x180016f95  mov     eax, 8002802Bh
0x180016f9a  cmp     ebx, eax
0x180016f9c  jz      loc_18001770C
0x180016fa2  test    ebx, ebx
0x180016fa4  jns     loc_1800173F6
0x180016faa  mov     iidIntercepted, [rbp+518h]; callerReturnAddress
0x180016fb1  lea     reasonForNoTypeInfo, aComOle32ComTxf_3; "com\\ole32\\com\\txf\\callframe\\typein"...
0x180016fb8  mov     r9d, ebx; hr
0x180016fbb  mov     edx, 24Dh; lineNumber
0x180016fc0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016fc5  mov     iidIntercepted, [rsp+610h+typeLib.m_ptr]
0x180016fca  test    iidIntercepted, iidIntercepted
0x180016fcd  jz      short loc_180016FDB
0x180016fcf  mov     rax, [iidIntercepted]
0x180016fd2  mov     rax, [rax+10h]
0x180016fd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016fdb  mov     iidIntercepted, [rsp+610h+valueInformation.__ptr_.__value_]; pv
0x180016fe0  mov     [rsp+610h+valueInformation.__ptr_.__value_], r14
0x180016fe5  test    iidIntercepted, iidIntercepted
0x180016fe8  jnz     loc_1800176D7
0x180016fee  mov     iidIntercepted, [rsp+610h+hregPlatform.h]; Handle
0x180016ff3  call    cs:__imp_ZwClose
0x180016ff9  mov     iidIntercepted, [rsp+610h+hregLang.h]; Handle
0x180016ffe  call    cs:__imp_ZwClose
0x180017004  mov     iidIntercepted, rdi; pv
0x180017007  call    cs:__imp_CoTaskMemFree
0x18001700d  mov     iidIntercepted, [rsp+610h+hregVersion.h]; Handle
0x180017012  call    cs:__imp_ZwClose
0x180017018  mov     iidIntercepted, [rsp+610h+hregTlb.h]; Handle
0x18001701d  call    cs:__imp_ZwClose
0x180017023  mov     edi, ebx
  ... truncated ...
```
