# JoinStatusStorage::ReadJoinStatus(int,_CERT_CONTEXT const *,int,struct_join_status *,int)

- ea: `0x180009f10`
- end: `0x18000ab64`
- name: `?ReadJoinStatus@JoinStatusStorage@@SAJHPEBU_CERT_CONTEXT@@HPEAUstruct_join_status@@H@Z`
- size: `3156`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, const struct _CERT_CONTEXT *@<rdx>, int@<r8d>, struct struct_join_status *@<r9>, int)`
- caller_count: `6`
- callee_count: `17`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180009a50`
- `0x18000ce20`
- `0x18000db10`
- `0x1800108e0`
- `0x18001b6a0`
- `0x180052698`

## callees

- `0x1800048cc`
- `0x1800051d4`
- `0x180005bbc`
- `0x180006190`
- `0x1800069a0`
- `0x1800084f4`
- `0x180008d80`
- `0x180009780`
- `0x180009f10`
- `0x18000bac0`
- `0x18000cbd8`
- `0x18000d110`
- `0x18000ddf0`
- `0x1800307c4`
- `0x18003334c`
- `0x180043ef8`
- `0x180044300`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18000aaef`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18000aaef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a089`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a1ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a089`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a1ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a068`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a0bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a18d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a1de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a7d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a83f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a068`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a0bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a18d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a1de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a7d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a83f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a2d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a3ca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a587`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a5a0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a2d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a3ca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a587`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a5a0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a595`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a5ae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a595`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a5ae`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a2e7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a3db`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a2e7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a3db`
- `CRYPT32!CertFindExtension` at `0x180009fe8`
- `CRYPT32!CertFindExtension` at `0x18000a10a`
- `CRYPT32!CertFindExtension` at `0x180009fe8`
- `CRYPT32!CertFindExtension` at `0x18000a10a`
- `CRYPT32!CryptDecodeObjectEx` at `0x18000a028`
- `CRYPT32!CryptDecodeObjectEx` at `0x18000a14a`
- `CRYPT32!CryptDecodeObjectEx` at `0x18000a028`
- `CRYPT32!CryptDecodeObjectEx` at `0x18000a14a`

## string_xrefs

- `0x18000a947`: `JoinStatusStorage::GetExistingDeviceKeyPath`
- `0x18000a68c`: `JoinStatusStorage::ReadDeviceKey`
- `0x18000a196`: `RegistrationCertStatus::GetTenantIdExtensionValue`
- `0x18000a1e4`: `RegistrationCertStatus::GetTenantIdExtensionValue`
- `0x18000a84b`: `RegistrationCertStatus::GetTenantIdExtensionValue`
- `0x180009f96`: `JoinStatusStorage::ReadJoinStatus`
- `0x18000a548`: `JoinStatusStorage::ReadJoinStatus`
- `0x18000a5ca`: `JoinStatusStorage::ReadJoinStatus`
- `0x18000a608`: `JoinStatusStorage::ReadJoinStatus`
- `0x18000a69f`: `JoinStatusStorage::ReadJoinStatus`
- `0x18000a6e0`: `JoinStatusStorage::ReadJoinStatus`
- `0x18000a74b`: `JoinStatusStorage::ReadJoinStatus`
- `0x18000a765`: `JoinStatusStorage::ReadJoinStatus`
- `0x18000a7fd`: `JoinStatusStorage::ReadJoinStatus`
- `0x18000a925`: `JoinStatusStorage::ReadJoinStatus`
- `0x18000a94e`: `JoinStatusStorage::ReadJoinStatus`
- `0x18000a9f4`: `JoinStatusStorage::ReadJoinStatus`
- `0x18000ab37`: `JoinStatusStorage::ReadJoinStatus`
- `0x18000a092`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x18000a1b4`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x18000a77d`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x18000a7b5`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x18000a81f`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x18000a8b5`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x18000a887`: `CopyStringW`
- `0x18000a784`: `%s: Extension was not found in the certificate. OID: %hs.`
- `0x18000a826`: `%s: Extension was not found in the certificate. OID: %hs.`
- `0x18000a5c3`: `RegistryPath::Append`
- `0x18000ab2d`: `JoinStatusStorage::ReadTenantKey`
- `0x18000a726`: `Logger::WriteNullOrEmptyParameterFailureEvent`
- `0x18000a71f`: `EventWriteNullOrEmptyParameterFailureEvent`
- `0x18000a9a0`: `StringCchCopyW`
- `0x18000aa8a`: `StringCchCopyW`

## pseudocode

```c
__int64 __fastcall JoinStatusStorage::ReadJoinStatus(
        int a1,
        const struct _CERT_CONTEXT *a2,
        int a3,
        struct struct_join_status *a4,
        int a5)
{
  const wchar_t *v8; // r15
  PCERT_INFO pCertInfo; // rdx
  unsigned int v10; // ebx
  PCERT_EXTENSION Extension; // rax
  int v12; // eax
  unsigned int DeviceKey; // r13d
  __int64 LastError; // rdi
  PCERT_INFO v15; // rdx
  unsigned __int16 *v16; // rdi
  PCERT_EXTENSION v17; // rax
  int v18; // eax
  __int64 v19; // rsi
  const wchar_t *v20; // rsi
  int ExistingDeviceKeyPath; // eax
  struct struct_join_status *v22; // r14
  int v23; // r15d
  void *v24; // rbx
  unsigned __int16 *v25; // rax
  __int64 v26; // rsi
  int v27; // r12d
  __int64 v28; // rcx
  int v29; // ebx
  __int64 v30; // rdi
  SIZE_T v31; // rbx
  HANDLE v32; // rax
  _WORD *v33; // rax
  _WORD *v34; // r9
  unsigned __int64 v35; // r8
  unsigned __int16 *v36; // rdx
  __int64 v37; // rcx
  _WORD *v38; // rcx
  void *v39; // rbx
  void **v40; // r14
  unsigned __int16 *v41; // rax
  __int64 v42; // rcx
  __int64 v43; // rdi
  SIZE_T v44; // rbx
  HANDLE v45; // rax
  _WORD *v46; // rax
  _WORD *v47; // r8
  const unsigned __int16 *v48; // rbx
  unsigned __int64 v49; // rdx
  unsigned __int16 *v50; // rcx
  _WORD *v51; // rcx
  const wchar_t *v52; // rdi
  wchar_t *v53; // rax
  size_t v54; // r8
  size_t v55; // r9
  size_t v56; // r11
  int v57; // ecx
  char v58; // r10
  wchar_t *v59; // rdx
  int TenantKey; // eax
  unsigned __int16 *v61; // rcx
  HANDLE ProcessHeap; // rax
  HANDLE v64; // rax
  __int64 v65; // r8
  unsigned int v66; // eax
  const wchar_t *v67; // rax
  const wchar_t *v68; // rax
  unsigned __int16 *v69; // rcx
  int v70; // eax
  __int64 v71; // r9
  __int64 v72; // r9
  const wchar_t *v73; // r8
  const wchar_t *v74; // rax
  DWORD dwFlags[2]; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *Block; // [rsp+40h] [rbp-C0h]
  unsigned __int16 *v77; // [rsp+48h] [rbp-B8h]
  HLOCAL hMem; // [rsp+50h] [rbp-B0h] BYREF
  int v79; // [rsp+58h] [rbp-A8h]
  DWORD pcbStructInfo; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned __int16 *v81; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v82; // [rsp+68h] [rbp-98h] BYREF
  struct struct_join_status *v83; // [rsp+70h] [rbp-90h]
  wchar_t *Source; // [rsp+80h] [rbp-80h] BYREF
  size_t MaxCount; // [rsp+88h] [rbp-78h]
  __int64 v86; // [rsp+90h] [rbp-70h]
  size_t v87; // [rsp+98h] [rbp-68h]
  __int128 v88; // [rsp+A0h] [rbp-60h]
  __int64 v89; // [rsp+B0h] [rbp-50h]
  __int64 v90; // [rsp+B8h] [rbp-48h]
  char v91[16]; // [rsp+C0h] [rbp-40h] BYREF
  const unsigned __int16 *v92; // [rsp+D0h] [rbp-30h]
  __int64 v93; // [rsp+D8h] [rbp-28h]
  const unsigned __int16 *v94; // [rsp+E0h] [rbp-20h]
  __int64 v95; // [rsp+E8h] [rbp-18h]

  v79 = a3;
  Source = 0;
  v77 = 0;
  v82 = 0;
  v83 = a4;
  MaxCount = 0;
  v86 = 0;
  v87 = 0;
  v8 = L"TRUE";
  v88 = 0;
  if ( !a1 )
    v8 = L"FALSE";
  v89 = 0;
  v90 = 0;
  Logger::TraceVerbose((wchar_t *)L"%s started. %s: %s.", L"JoinStatusStorage::ReadJoinStatus", L"isDevice", v8);
  if ( !a2 )
  {
    DeviceKey = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"JoinStatusStorage::ReadJoinStatus", L"pCert");
    if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) != 0 )
    {
      v92 = L"JoinStatusStorage::ReadJoinStatus";
      v93 = 68;
      v94 = L"pCert";
      v95 = 12;
      v66 = McGenEventWrite_EventWriteTransfer(
              &UserDeviceRegistrationEventProvider_Context,
              NullOrEmptyParameterFailureEvent,
              v65,
              3,
              v91);
      if ( v66 )
        Logger::TraceError(
          L"%s: %s failed with win32 error code: 0x%08x.",
          L"Logger::WriteNullOrEmptyParameterFailureEvent",
          L"EventWriteNullOrEmptyParameterFailureEvent",
          v66);
    }
    goto LABEL_84;
  }
  if ( !a4 )
  {
    DeviceKey = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"JoinStatusStorage::ReadJoinStatus", L"pJoinStatus");
    Logger::WriteNullOrEmptyParameterFailureEvent(L"JoinStatusStorage::ReadJoinStatus", L"pJoinStatus");
LABEL_84:
    v61 = 0;
    goto LABEL_74;
  }
  pCertInfo = a2->pCertInfo;
  hMem = 0;
  v10 = 0;
  pcbStructInfo = 0;
  v81 = 0;
  Block = 0;
  Extension = CertFindExtension("1.2.840.113556.1.5.284.2", pCertInfo->cExtension, pCertInfo->rgExtension);
  if ( !Extension )
  {
    Logger::TraceVerbose(
      (wchar_t *)L"%s: Extension was not found in the certificate. OID: %hs.",
      L"CertificateUtil::FindExtensionGuidValueByOid",
      "1.2.840.113556.1.5.284.2");
    v69 = 0;
    DeviceKey = -2146885628;
LABEL_101:
    operator delete(v69);
    LocalFree(hMem);
    Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"RegistrationCertStatus::GetDeviceId", DeviceKey);
LABEL_102:
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"JoinStatusStorage::ReadJoinStatus",
      L"RegistrationCertStatus::GetDeviceId",
      DeviceKey);
    v61 = 0;
    goto LABEL_74;
  }
  if ( CryptDecodeObjectEx(
         a2->dwCertEncodingType,
         (LPCSTR)0x19,
         Extension->Value.pbData,
         Extension->Value.cbData,
         0x8000u,
         0,
         &hMem,
         &pcbStructInfo) )
  {
    v12 = CertificateUtil::GuidStringFromByteArray(*((const unsigned __int8 **)hMem + 1), *(_DWORD *)hMem, &v81);
    DeviceKey = v12;
    if ( v12 >= 0 )
    {
      Block = v81;
      operator delete(0);
      LocalFree(hMem);
      Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"RegistrationCertStatus::GetDeviceId", DeviceKey);
      goto LABEL_11;
    }
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"CertificateUtil::FindExtensionGuidValueByOid",
      L"CertificateUtil::GuidStringFromByteArray",
      (unsigned int)v12);
    v69 = v81;
    goto LABEL_101;
  }
  DeviceKey = 0;
  LastError = GetLastError();
  Logger::TraceError(
    L"%s: CryptDecodeObjectEx failed with error code: 0x%08x",
    L"CertificateUtil::FindExtensionGuidValueByOid",
    LastError);
  if ( (_DWORD)LastError )
  {
    if ( (int)LastError > 0 )
      DeviceKey = (unsigned __int16)LastError | 0x80070000;
    else
      DeviceKey = LastError;
  }
  operator delete(0);
  LocalFree(hMem);
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"RegistrationCertStatus::GetDeviceId", DeviceKey);
  if ( (DeviceKey & 0x80000000) != 0 )
    goto LABEL_102;
LABEL_11:
  v15 = a2->pCertInfo;
  hMem = 0;
  v16 = 0;
  pcbStructInfo = 0;
  v81 = 0;
  v17 = CertFindExtension("1.2.840.113556.1.5.284.5", v15->cExtension, v15->rgExtension);
  if ( v17 )
  {
    if ( CryptDecodeObjectEx(
           a2->dwCertEncodingType,
           (LPCSTR)0x19,
           v17->Value.pbData,
           v17->Value.cbData,
           0x8000u,
           0,
           &hMem,
           &pcbStructInfo) )
    {
      v18 = CertificateUtil::GuidStringFromByteArray(*((const unsigned __int8 **)hMem + 1), *(_DWORD *)hMem, &v81);
      v10 = v18;
      if ( v18 >= 0 )
      {
        DeviceKey = v18;
        v77 = v81;
        operator delete(0);
        LocalFree(hMem);
        Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"RegistrationCertStatus::GetTenantIdExtensionValue", v10);
        goto LABEL_18;
      }
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"CertificateUtil::FindExtensionGuidValueByOid",
        L"CertificateUtil::GuidStringFromByteArray",
        (unsigned int)v18);
      v16 = v81;
    }
    else
    {
      v19 = GetLastError();
      Logger::TraceError(
        L"%s: CryptDecodeObjectEx failed with error code: 0x%08x",
        L"CertificateUtil::FindExtensionGuidValueByOid",
        v19);
      if ( (_DWORD)v19 )
      {
        if ( (int)v19 > 0 )
          v10 = (unsigned __int16)v19 | 0x80070000;
        else
          v10 = v19;
      }
    }
    operator delete(v16);
    LocalFree(hMem);
    v20 = L"RegistrationCertStatus::GetTenantIdExtensionValue";
    Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"RegistrationCertStatus::GetTenantIdExtensionValue", v10);
    if ( v10 != -2146885628 )
    {
      DeviceKey = v10;
      if ( (v10 & 0x80000000) == 0 )
        goto LABEL_18;
      v71 = v10;
LABEL_110:
      Logger::TraceError(L"%s: %s failed with error code: 0x%08x.", L"RegistrationCertStatus::GetTenantId", v20, v71);
      operator delete(v77);
      v77 = 0;
      Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"RegistrationCertStatus::GetTenantId", v10);
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"JoinStatusStorage::ReadJoinStatus",
        L"RegistrationCertStatus::GetTenantId",
        DeviceKey);
      goto LABEL_73;
    }
  }
  else
  {
    Logger::TraceVerbose(
      (wchar_t *)L"%s: Extension was not found in the certificate. OID: %hs.",
      L"CertificateUtil::FindExtensionGuidValueByOid",
      "1.2.840.113556.1.5.284.5");
    operator delete(0);
    LocalFree(hMem);
    Logger::TraceVerbose(
      (wchar_t *)L"%s - hr: 0x%08x",
      L"RegistrationCertStatus::GetTenantIdExtensionValue",
      2148081668LL);
  }
  operator delete(0);
  v70 = CopyStringW(L"383a3889-5bc9-47a3-846c-2b70f0b7fe0e", 0x24u, &v82);
  DeviceKey = v70;
  if ( v70 < 0 )
  {
    v10 = v70;
    v20 = L"CopyStringW";
    v71 = (unsigned int)v70;
    v77 = v82;
    goto LABEL_110;
  }
  v77 = v82;
LABEL_18:
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"RegistrationCertStatus::GetTenantId", DeviceKey);
  ExistingDeviceKeyPath = JoinStatusStorage::GetExistingDeviceKeyPath(a1, a2, (HKEY *)&Source);
  DeviceKey = ExistingDeviceKeyPath;
  if ( ExistingDeviceKeyPath < 0 )
  {
    dwFlags[0] = ExistingDeviceKeyPath;
    Logger::TraceError(
      L"%s: %s(%s) failed with error code: 0x%08x.",
      L"JoinStatusStorage::ReadJoinStatus",
      L"JoinStatusStorage::GetExistingDeviceKeyPath",
      v8,
      *(_QWORD *)dwFlags);
    v61 = Block;
    goto LABEL_74;
  }
  v22 = v83;
  v23 = v79;
  DeviceKey = JoinStatusStorage::ReadDeviceKey(v83, (struct RegistryPath *)&Source, v79);
  if ( (DeviceKey & 0x80000000) != 0 )
  {
    v67 = L"TRUE";
    if ( !v23 )
      v67 = L"FALSE";
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
      L"JoinStatusStorage::ReadJoinStatus",
      L"JoinStatusStorage::ReadDeviceKey",
      DeviceKey,
      v67);
    if ( !v23 )
      goto LABEL_73;
  }
  v24 = *(void **)v22;
  if ( *(_QWORD *)v22 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v24);
  }
  v25 = Block;
  v26 = 2147483646;
  *(_QWORD *)v22 = 0;
  DeviceKey = -2147024809;
  v27 = -2147024882;
  if ( Block )
  {
    v28 = 0x7FFFFFFF;
    do
    {
      if ( !*v25 )
        break;
      ++v25;
      --v28;
    }
    while ( v28 );
    v29 = -2147024809;
    if ( !v28 )
    {
      v72 = 2147942487LL;
      v73 = L"StringCchLengthW";
      goto LABEL_118;
    }
    v30 = 0x7FFFFFFF - v28;
    v31 = 2 * (0x7FFFFFFF - v28) + 2;
    v32 = GetProcessHeap();
    v33 = HeapAlloc(v32, 8u, v31);
    *(_QWORD *)v22 = v33;
    v34 = v33;
    if ( !v33 )
    {
      v29 = -2147024882;
      Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"StringDup");
      goto LABEL_119;
    }
    v35 = v30 + 1;
    if ( v30 == -1 )
    {
      v29 = -2147024809;
    }
    else
    {
      if ( v35 > 0x7FFFFFFF )
      {
        v29 = -2147024809;
        *v33 = 0;
        v72 = 2147942487LL;
LABEL_116:
        v73 = L"StringCchCopyW";
LABEL_118:
        Logger::TraceError(L"%s: %s failed with error code: 0x%08x.", L"StringDup", v73, v72);
LABEL_119:
        SafeFree(*(void **)v22);
        *(_QWORD *)v22 = 0;
        v74 = L"TRUE";
        if ( !v23 )
          v74 = L"FALSE";
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
          L"JoinStatusStorage::ReadJoinStatus",
          L"StringDup",
          (unsigned int)v29,
          v74);
        if ( !v23 )
        {
          v61 = Block;
          DeviceKey = v29;
          goto LABEL_74;
        }
        goto LABEL_38;
      }
      v36 = Block;
      v37 = 2147483646;
      do
      {
        if ( !v37 )
          break;
        if ( !*v36 )
          break;
        *v34++ = *v36++;
        --v37;
        --v35;
      }
      while ( v35 );
      v38 = v34 - 1;
      v29 = -2147024774;
      if ( v35 )
      {
        v38 = v34;
        v29 = 0;
      }
      *v38 = 0;
    }
    if ( v29 >= 0 )
      goto LABEL_38;
    v72 = (unsigned int)v29;
    goto LABEL_116;
  }
LABEL_38:
  v39 = (void *)*((_QWORD *)v22 + 2);
  v40 = (void **)((char *)v22 + 16);
  if ( v39 )
  {
    v64 = GetProcessHeap();
    HeapFree(v64, 0, v39);
    *v40 = 0;
  }
  else
  {
    *v40 = 0;
    if ( !v40 )
    {
      v27 = -2147024809;
      Logger::TraceError(L"%s: \"%s\" should not be null.", L"StringDup", L"dest");
      Logger::WriteNullOrEmptyParameterFailureEvent(L"StringDup", L"dest");
      v48 = v77;
      goto LABEL_89;
    }
  }
  v41 = v77;
  if ( !v77 )
  {
    v48 = 0;
    goto LABEL_56;
  }
  v42 = 0x7FFFFFFF;
  do
  {
    if ( !*v41 )
      break;
    ++v41;
    --v42;
  }
  while ( v42 );
  if ( !v42 )
  {
    v27 = -2147024809;
    Logger::TraceError(L"%s: %s failed with error code: 0x%08x.", L"StringDup", L"StringCchLengthW");
    goto LABEL_130;
  }
  v43 = 0x7FFFFFFF - v42;
  v44 = 2 * (0x7FFFFFFF - v42) + 2;
  v45 = GetProcessHeap();
  v46 = HeapAlloc(v45, 8u, v44);
  *v40 = v46;
  v47 = v46;
  if ( !v46 )
  {
    Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"StringDup");
LABEL_130:
    v48 = v77;
    goto LABEL_131;
  }
  v48 = v77;
  v49 = v43 + 1;
  if ( v43 == -1 )
  {
    v27 = -2147024809;
  }
  else
  {
    if ( v49 > 0x7FFFFFFF )
    {
      v27 = -2147024809;
      *v46 = 0;
LABEL_128:
      Logger::TraceError(L"%s: %s failed with error code: 0x%08x.", L"StringDup", L"StringCchCopyW", DeviceKey);
LABEL_131:
      SafeFree(*v40);
      *v40 = 0;
      DeviceKey = v27;
      v23 = v79;
LABEL_89:
      v52 = L"TRUE";
      v68 = L"TRUE";
      if ( !v23 )
        v68 = L"FALSE";
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
        L"JoinStatusStorage::ReadJoinStatus",
        L"StringDup",
        (unsigned int)v27,
        v68);
      if ( !v23 )
        goto LABEL_73;
      goto LABEL_57;
    }
    v50 = v77;
    do
    {
      if ( !v26 )
        break;
      if ( !*v50 )
        break;
      *v47++ = *v50++;
      --v26;
      --v49;
    }
    while ( v49 );
    v51 = v47 - 1;
    v27 = -2147024774;
    if ( v49 )
    {
      v51 = v47;
      v27 = 0;
    }
    *v51 = 0;
  }
  if ( v27 < 0 )
  {
    DeviceKey = v27;
    goto LABEL_128;
  }
LABEL_56:
  v23 = v79;
  v52 = L"TRUE";
LABEL_57:
  v53 = Source;
  v54 = 0;
  if ( Source && MaxCount )
  {
    v54 = wcsnlen(Source, MaxCount);
    v53 = Source;
  }
  v55 = v87;
  v56 = v54;
  v57 = 0;
  v58 = 1;
  while ( v54 && v54 >= v55 )
  {
    v59 = &v53[v54];
    if ( *(v59 - 1) != 92 )
    {
      v58 = 0;
LABEL_80:
      --v54;
      goto LABEL_66;
    }
    if ( v58 )
      goto LABEL_80;
    v58 = 1;
    --v54;
    *(v59 - 1) = 0;
    v55 = v87;
    v56 = v54;
    v53 = Source;
    ++v57;
LABEL_66:
    if ( v57 >= 2 )
      break;
  }
  if ( v57 )
  {
    if ( v55 > v56 )
      v55 = v56;
    v87 = v55;
    RegistryPath::CloseSubKey((RegistryPath *)&Source);
  }
  DeviceKey = RegistryPath::Append((const wchar_t **)&Source, L"TenantInfo");
  if ( !DeviceKey )
    DeviceKey = RegistryPath::Append((const wchar_t **)&Source, v48);
  if ( DeviceKey )
  {
    Logger::TraceError(
      L"%s: %s failed with win32 error code: 0x%08x.",
      L"JoinStatusStorage::ReadJoinStatus",
      L"RegistryPath::Append",
      DeviceKey);
    if ( (int)DeviceKey > 0 )
      DeviceKey = (unsigned __int16)DeviceKey | 0x80070000;
    v61 = Block;
  }
  else
  {
    TenantKey = JoinStatusStorage::ReadTenantKey((void **)v83, (struct RegistryPath *)&Source, a5);
    DeviceKey = TenantKey;
    if ( TenantKey < 0 )
    {
      if ( !v23 )
        v52 = L"FALSE";
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
        L"JoinStatusStorage::ReadJoinStatus",
        L"JoinStatusStorage::ReadTenantKey",
        (unsigned int)TenantKey,
        v52);
      if ( v23 )
        goto LABEL_139;
    }
    else
    {
      if ( !v23 )
        goto LABEL_73;
LABEL_139:
      DeviceKey = 0;
    }
LABEL_73:
    v61 = Block;
  }
LABEL_74:
  operator delete(v61);
  operator delete(v77);
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"JoinStatusStorage::ReadJoinStatus", DeviceKey);
  RegistryPath::Reset((RegistryPath *)&Source);
  return DeviceKey;
}

```

## disassembly

```asm
0x180009f10  push    rbp
0x180009f12  push    rbx
0x180009f13  push    rsi
0x180009f14  push    rdi
0x180009f15  push    r12
0x180009f17  push    r13
0x180009f19  push    r14
0x180009f1b  push    r15
0x180009f1d  lea     rbp, [rsp-8]
0x180009f22  sub     rsp, 108h
0x180009f29  mov     rax, cs:__security_cookie
0x180009f30  xor     rax, rsp
0x180009f33  mov     [rbp+40h+var_50], rax
0x180009f37  xor     esi, esi
0x180009f39  mov     [rsp+140h+var_E8], r8d
0x180009f3e  mov     eax, esi
0x180009f40  mov     [rbp+40h+Source], rsi
0x180009f44  test    ecx, ecx
0x180009f46  mov     [rsp+140h+var_F8], rax
0x180009f4b  mov     rbx, r9
0x180009f4e  mov     [rsp+140h+var_D8], rax
0x180009f53  lea     rax, aFalse_0; "FALSE"
0x180009f5a  mov     [rsp+140h+var_D0], rbx
0x180009f5f  mov     r14, rdx
0x180009f62  mov     [rbp+40h+MaxCount], rsi
0x180009f66  mov     r12d, ecx
0x180009f69  mov     [rbp+40h+var_B0], rsi
0x180009f6d  xorps   xmm0, xmm0
0x180009f70  mov     [rbp+40h+var_A8], rsi
0x180009f74  lea     r15, aTrue_0; "TRUE"
0x180009f7b  movdqa  [rbp+40h+var_A0], xmm0
0x180009f80  cmovz   r15, rax
0x180009f84  mov     [rbp+40h+var_90], rsi
0x180009f88  mov     r9, r15
0x180009f8b  mov     [rbp+40h+var_88], rsi
0x180009f8f  lea     r8, aIsdevice; "isDevice"
0x180009f96  lea     rdx, aJoinstatusstor_8; "JoinStatusStorage::ReadJoinStatus"
0x180009f9d  lea     rcx, aSStartedSS; "%s started. %s: %s."
0x180009fa4  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180009fa9  test    r14, r14
0x180009fac  jz      loc_18000A5FB
0x180009fb2  test    rbx, rbx
0x180009fb5  jz      loc_18000A73E
0x180009fbb  mov     rdx, [r14+18h]
0x180009fbf  lea     rcx, pszObjId; "1.2.840.113556.1.5.284.2"
0x180009fc6  mov     [rsp+140h+hMem], rsi
0x180009fcb  mov     ebx, esi
0x180009fcd  mov     [rsp+140h+var_E4], esi
0x180009fd1  mov     [rsp+140h+var_E0], rbx
0x180009fd6  mov     r8, [rdx+0C8h]; rgExtensions
0x180009fdd  mov     edx, [rdx+0C0h]; cExtensions
0x180009fe3  mov     [rsp+140h+Block], rsi
0x180009fe8  call    cs:__imp_CertFindExtension
0x180009fee  test    rax, rax
0x180009ff1  jz      loc_18000A776
0x180009ff7  mov     r9d, [rax+10h]; cbEncoded
0x180009ffb  lea     rcx, [rsp+140h+var_E4]
0x18000a000  mov     r8, [rax+18h]; pbEncoded
0x18000a004  mov     edx, 19h; lpszStructType
0x18000a009  mov     [rsp+140h+pcbStructInfo], rcx; pcbStructInfo
0x18000a00e  lea     rcx, [rsp+140h+hMem]
0x18000a013  mov     [rsp+140h+pvStructInfo], rcx; pvStructInfo
0x18000a018  mov     ecx, [r14]; dwCertEncodingType
0x18000a01b  mov     [rsp+140h+pDecodePara], rsi; pDecodePara
0x18000a020  mov     [rsp+140h+dwFlags], 8000h; dwFlags
0x18000a028  call    cs:__imp_CryptDecodeObjectEx
0x18000a02e  test    eax, eax
0x18000a030  jz      short loc_18000A086
0x18000a032  mov     rcx, [rsp+140h+hMem]
0x18000a037  lea     r8, [rsp+140h+var_E0]; unsigned __int16 **
0x18000a03c  mov     edx, [rcx]; unsigned int
0x18000a03e  mov     rcx, [rcx+8]; unsigned __int8 *
0x18000a042  call    ?GuidStringFromByteArray@CertificateUtil@@CAJPEBEKPEAPEAG@Z; CertificateUtil::GuidStringFromByteArray(uchar const *,ulong,ushort * *)
0x18000a047  mov     r13d, eax
0x18000a04a  test    eax, eax
0x18000a04c  js      loc_18000A7AB
0x18000a052  mov     rax, [rsp+140h+var_E0]
0x18000a057  mov     ecx, esi; Block
0x18000a059  mov     [rsp+140h+Block], rax
0x18000a05e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a063  mov     rcx, [rsp+140h+hMem]; hMem
0x18000a068  call    cs:__imp_LocalFree
0x18000a06e  mov     r8d, r13d
0x18000a071  lea     rdx, aRegistrationce_24; "RegistrationCertStatus::GetDeviceId"
0x18000a078  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x18000a07f  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18000a084  jmp     short loc_18000A0E1
0x18000a086  mov     r13d, esi
0x18000a089  call    cs:__imp_GetLastError
0x18000a08f  mov     r8d, eax
0x18000a092  lea     rdx, aCertificateuti_5; "CertificateUtil::FindExtensionGuidValue"...
0x18000a099  lea     rcx, aSCryptdecodeob_0; "%s: CryptDecodeObjectEx failed with err"...
0x18000a0a0  mov     edi, eax
0x18000a0a2  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000a0a7  test    edi, edi
0x18000a0a9  jnz     loc_18000A701
0x18000a0af  mov     rcx, rbx; Block
0x18000a0b2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a0b7  mov     rcx, [rsp+140h+hMem]; hMem
0x18000a0bc  call    cs:__imp_LocalFree
0x18000a0c2  mov     r8d, r13d
0x18000a0c5  lea     rdx, aRegistrationce_24; "RegistrationCertStatus::GetDeviceId"
0x18000a0cc  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x18000a0d3  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18000a0d8  test    r13d, r13d
0x18000a0db  js      loc_18000A7F3
0x18000a0e1  mov     rdx, [r14+18h]
0x18000a0e5  lea     rcx, a12840113556152; "1.2.840.113556.1.5.284.5"
0x18000a0ec  mov     [rsp+140h+hMem], rsi
0x18000a0f1  mov     rdi, rsi
0x18000a0f4  mov     [rsp+140h+var_E4], esi
0x18000a0f8  mov     [rsp+140h+var_E0], rsi
0x18000a0fd  mov     r8, [rdx+0C8h]; rgExtensions
0x18000a104  mov     edx, [rdx+0C0h]; cExtensions
0x18000a10a  call    cs:__imp_CertFindExtension
0x18000a110  test    rax, rax
0x18000a113  jz      loc_18000A818
0x18000a119  mov     r9d, [rax+10h]; cbEncoded
0x18000a11d  lea     rcx, [rsp+140h+var_E4]
0x18000a122  mov     r8, [rax+18h]; pbEncoded
0x18000a126  mov     edx, 19h; lpszStructType
0x18000a12b  mov     [rsp+140h+pcbStructInfo], rcx; pcbStructInfo
0x18000a130  lea     rcx, [rsp+140h+hMem]
0x18000a135  mov     [rsp+140h+pvStructInfo], rcx; pvStructInfo
0x18000a13a  mov     ecx, [r14]; dwCertEncodingType
0x18000a13d  mov     [rsp+140h+pDecodePara], rsi; pDecodePara
0x18000a142  mov     [rsp+140h+dwFlags], 8000h; dwFlags
0x18000a14a  call    cs:__imp_CryptDecodeObjectEx
0x18000a150  test    eax, eax
0x18000a152  jz      short loc_18000A1AB
0x18000a154  mov     rcx, [rsp+140h+hMem]
0x18000a159  lea     r8, [rsp+140h+var_E0]; unsigned __int16 **
0x18000a15e  mov     edx, [rcx]; unsigned int
0x18000a160  mov     rcx, [rcx+8]; unsigned __int8 *
0x18000a164  call    ?GuidStringFromByteArray@CertificateUtil@@CAJPEBEKPEAPEAG@Z; CertificateUtil::GuidStringFromByteArray(uchar const *,ulong,ushort * *)
0x18000a169  mov     ebx, eax
0x18000a16b  test    eax, eax
0x18000a16d  js      loc_18000A8AB
0x18000a173  mov     r13d, eax
0x18000a176  mov     rcx, rsi; Block
0x18000a179  mov     rax, [rsp+140h+var_E0]
0x18000a17e  mov     [rsp+140h+var_F8], rax
0x18000a183  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a188  mov     rcx, [rsp+140h+hMem]; hMem
0x18000a18d  call    cs:__imp_LocalFree
0x18000a193  mov     r8d, ebx
0x18000a196  lea     rdx, aRegistrationce_5; "RegistrationCertStatus::GetTenantIdExte"...
0x18000a19d  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x18000a1a4  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18000a1a9  jmp     short loc_18000A217
0x18000a1ab  call    cs:__imp_GetLastError
0x18000a1b1  mov     r8d, eax
0x18000a1b4  lea     rdx, aCertificateuti_5; "CertificateUtil::FindExtensionGuidValue"...
0x18000a1bb  lea     rcx, aSCryptdecodeob_0; "%s: CryptDecodeObjectEx failed with err"...
0x18000a1c2  mov     esi, eax
0x18000a1c4  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000a1c9  test    esi, esi
0x18000a1cb  jnz     loc_18000A70F
0x18000a1d1  mov     rcx, rdi; Block
0x18000a1d4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a1d9  mov     rcx, [rsp+140h+hMem]; hMem
0x18000a1de  call    cs:__imp_LocalFree
0x18000a1e4  lea     rsi, aRegistrationce_5; "RegistrationCertStatus::GetTenantIdExte"...
0x18000a1eb  mov     r8d, ebx
0x18000a1ee  mov     rdx, rsi
0x18000a1f1  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x18000a1f8  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18000a1fd  mov     r13d, 80092004h
0x18000a203  cmp     ebx, r13d
0x18000a206  jz      loc_18000A85E
0x18000a20c  mov     r13d, ebx
0x18000a20f  test    ebx, ebx
0x18000a211  js      loc_18000A8E1
0x18000a217  lea     rdi, aRegistrationce_21; "RegistrationCertStatus::GetTenantId"
0x18000a21e  mov     r8d, r13d
0x18000a221  mov     rdx, rdi
0x18000a224  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x18000a22b  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18000a230  lea     r8, [rbp+40h+Source]; struct RegistryPath *
0x18000a234  mov     rdx, r14; struct _CERT_CONTEXT *
0x18000a237  mov     ecx, r12d; int
0x18000a23a  call    ?GetExistingDeviceKeyPath@JoinStatusStorage@@CAJHPEBU_CERT_CONTEXT@@AEAVRegistryPath@@@Z; JoinStatusStorage::GetExistingDeviceKeyPath(int,_CERT_CONTEXT const *,RegistryPath &)
0x18000a23f  mov     r13d, eax
0x18000a242  test    eax, eax
0x18000a244  js      loc_18000A940
0x18000a24a  mov     r14, [rsp+140h+var_D0]
0x18000a24f  lea     rdx, [rbp+40h+Source]; struct RegistryPath *
0x18000a253  mov     r15d, [rsp+140h+var_E8]
0x18000a258  mov     rcx, r14; struct struct_join_status *
0x18000a25b  mov     r8d, r15d; int
0x18000a25e  call    ?ReadDeviceKey@JoinStatusStorage@@CAJPEAUstruct_join_status@@AEAVRegistryPath@@H@Z; JoinStatusStorage::ReadDeviceKey(struct_join_status *,RegistryPath &,int)
0x18000a263  mov     r13d, eax
0x18000a266  test    eax, eax
0x18000a268  js      loc_18000A674
0x18000a26e  mov     rbx, [r14]
0x18000a271  test    rbx, rbx
0x18000a274  jnz     loc_18000A587
0x18000a27a  mov     rax, [rsp+140h+Block]
0x18000a27f  mov     esi, 7FFFFFFEh
0x18000a284  mov     qword ptr [r14], 0
0x18000a28b  mov     r13d, 80070057h
0x18000a291  mov     r12d, 8007000Eh
0x18000a297  test    rax, rax
0x18000a29a  jz      loc_18000A365
0x18000a2a0  mov     ecx, 7FFFFFFFh
0x18000a2a5  cmp     word ptr [rax], 0
0x18000a2a9  jz      short loc_18000A2B5
0x18000a2ab  add     rax, 2
0x18000a2af  sub     rcx, 1
0x18000a2b3  jnz     short loc_18000A2A5
0x18000a2b5  xor     eax, eax
0x18000a2b7  mov     ebx, r13d
0x18000a2ba  test    rcx, rcx
0x18000a2bd  cmovnz  ebx, eax
0x18000a2c0  jz      loc_18000A9A9
0x18000a2c6  mov     edi, 7FFFFFFFh
0x18000a2cb  sub     rdi, rcx
0x18000a2ce  lea     rbx, ds:2[rdi*2]
0x18000a2d6  call    cs:__imp_GetProcessHeap
0x18000a2dc  mov     r8, rbx; dwBytes
0x18000a2df  mov     edx, 8; dwFlags
0x18000a2e4  mov     rcx, rax; hHeap
0x18000a2e7  call    cs:__imp_HeapAlloc
0x18000a2ed  mov     [r14], rax
0x18000a2f0  mov     r9, rax
0x18000a2f3  test    rax, rax
0x18000a2f6  jz      loc_18000A96B
0x18000a2fc  lea     r8, [rdi+1]
0x18000a300  test    r8, r8
0x18000a303  jz      loc_18000A983
0x18000a309  cmp     r8, 7FFFFFFFh
0x18000a310  ja      loc_18000A98F
0x18000a316  mov     rdx, [rsp+140h+Block]
0x18000a31b  mov     rcx, rsi
0x18000a31e  xchg    ax, ax
0x18000a320  test    rcx, rcx
0x18000a323  jz      short loc_18000A342
0x18000a325  movzx   eax, word ptr [rdx]
0x18000a328  test    ax, ax
0x18000a32b  jz      short loc_18000A342
0x18000a32d  mov     [r9], ax
0x18000a331  add     rdx, 2
0x18000a335  add     r9, 2
0x18000a339  dec     rcx
0x18000a33c  sub     r8, 1
0x18000a340  jnz     short loc_18000A320
0x18000a342  test    r8, r8
0x18000a345  lea     rcx, [r9-2]
0x18000a349  mov     ebx, 8007007Ah
0x18000a34e  cmovnz  rcx, r9
0x18000a352  xor     eax, eax
0x18000a354  test    r8, r8
0x18000a357  cmovnz  ebx, eax
0x18000a35a  mov     [rcx], ax
0x18000a35d  test    ebx, ebx
0x18000a35f  js      loc_18000A99D
0x18000a365  mov     rbx, [r14+10h]
0x18000a369  add     r14, 10h
0x18000a36d  test    rbx, rbx
0x18000a370  jnz     loc_18000A5A0
0x18000a376  mov     [r14], rbx
0x18000a379  test    r14, r14
0x18000a37c  jz      loc_18000AA22
0x18000a382  mov     rax, [rsp+140h+var_F8]
0x18000a387  mov     r15, r14
0x18000a38a  test    rax, rax
0x18000a38d  jz      loc_18000AAE4
0x18000a393  mov     ecx, 7FFFFFFFh
0x18000a398  cmp     word ptr [rax], 0
0x18000a39c  jz      short loc_18000A3A8
0x18000a39e  add     rax, 2
0x18000a3a2  sub     rcx, 1
0x18000a3a6  jnz     short loc_18000A398
0x18000a3a8  xor     eax, eax
0x18000a3aa  mov     r9d, r13d
0x18000a3ad  test    rcx, rcx
0x18000a3b0  cmovnz  r9d, eax
0x18000a3b4  jz      loc_18000AAA6
0x18000a3ba  mov     edi, 7FFFFFFFh
0x18000a3bf  sub     rdi, rcx
0x18000a3c2  lea     rbx, ds:2[rdi*2]
0x18000a3ca  call    cs:__imp_GetProcessHeap
0x18000a3d0  mov     r8, rbx; dwBytes
0x18000a3d3  mov     edx, 8; dwFlags
0x18000a3d8  mov     rcx, rax; hHeap
0x18000a3db  call    cs:__imp_HeapAlloc
0x18000a3e1  mov     [r14], rax
0x18000a3e4  mov     r8, rax
0x18000a3e7  test    rax, rax
0x18000a3ea  jz      loc_18000AA5C
0x18000a3f0  mov     rbx, [rsp+140h+var_F8]
0x18000a3f5  lea     rdx, [rdi+1]
0x18000a3f9  test    rdx, rdx
0x18000a3fc  jz      loc_18000AA7C
0x18000a402  cmp     rdx, 7FFFFFFFh
0x18000a409  ja      loc_18000AA71
0x18000a40f  mov     rcx, rbx
0x18000a412  test    rsi, rsi
0x18000a415  jz      short loc_18000A434
0x18000a417  movzx   eax, word ptr [rcx]
  ... truncated ...
```
