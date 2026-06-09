# NgcStatusStorage::Delete(HKEY__ *,ushort const *)

- ea: `0x180094810`
- end: `0x180094d1e`
- name: `?Delete@NgcStatusStorage@@QEAAJPEAUHKEY__@@PEBG@Z`
- size: `1294`
- prototype: `int(NgcStatusStorage *__hidden this, HKEY, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180029e68`
- `0x180094d24`

## callees

- `0x180005ba0`
- `0x1800084f4`
- `0x180009780`
- `0x18000bac0`
- `0x180010640`
- `0x180012948`
- `0x180012cf0`
- `0x1800307c4`
- `0x180030828`
- `0x18003334c`
- `0x18004255c`
- `0x180043e54`
- `0x18008bb70`
- `0x18008cea8`
- `0x18008ddf0`
- `0x180094810`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180094b2c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180094b2c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800949e3`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800949e3`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180094ab4`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180094ab4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180094948`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180094948`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180094ce9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180094ce9`

## string_xrefs

- `0x18009497b`: `RegOpenKeyExW`
- `0x18009485a`: `hUserRegistry`
- `0x180094879`: `hUserRegistry`
- `0x180094cd4`: `%s: There is no valid key registry.`
- `0x180094cb8`: `Logger::WriteNgcDeleteStatusFailureEvent`
- `0x180094cb1`: `EventWriteNgcDeleteStatusFailureEvent`
- `0x180094bb0`: `EventWriteNgcDeleteStatusSuccessEvent`
- `0x180094bb7`: `Logger::WriteNgcDeleteStatusSuccessEvent`
- `0x180094866`: `NgcStatusStorage::Delete`
- `0x180094880`: `NgcStatusStorage::Delete`
- `0x1800948c9`: `NgcStatusStorage::Delete`
- `0x180094911`: `NgcStatusStorage::Delete`
- `0x180094958`: `NgcStatusStorage::Delete`
- `0x180094996`: `NgcStatusStorage::Delete`
- `0x180094a0a`: `NgcStatusStorage::Delete`
- `0x180094a4a`: `NgcStatusStorage::Delete`
- `0x180094af8`: `NgcStatusStorage::Delete`
- `0x180094bd9`: `NgcStatusStorage::Delete`
- `0x180094c10`: `NgcStatusStorage::Delete`
- `0x180094ccd`: `NgcStatusStorage::Delete`
- `0x180094a11`: `%s: Cannot query values of registry key "%s\%s". Win32 error code: 0x%08x.`
- `0x18009495f`: `%s: The registry key "%s" does not exist. Noting to delete.`
- `0x180094aec`: `%s: Cannot enumerate keys under registry key "%s\%s". Index: %u, Win32 error code: 0x%08x.`
- `0x18009498c`: `%s: Cannot open registry key "%s". Win32 error code: 0x%08x.`
- `0x180094b59`: `RegDeleteKeyExW`
- `0x180094be0`: `%s: NGC key status deleted from registry "%s\%s\%s".`
- `0x180094b7c`: `%s: Cannot delete registry key "%s\%s\%s". Win32 error code: 0x%08x.`
- `0x180094c17`: `%s: %u key(s) deleted.`

## pseudocode

```c
__int64 __fastcall NgcStatusStorage::Delete(NgcStatusStorage *this, HKEY a2, unsigned __int16 *a3)
{
  unsigned __int16 *v3; // rsi
  WCHAR *v5; // r12
  unsigned __int16 *v6; // r13
  signed int v7; // edi
  int v8; // ecx
  unsigned __int16 *v9; // rsi
  int v10; // eax
  int v11; // eax
  LSTATUS v12; // eax
  LSTATUS v13; // ebx
  LSTATUS v14; // eax
  unsigned int v15; // eax
  int v16; // r14d
  DWORD v17; // r15d
  int v18; // r13d
  int v19; // edi
  LSTATUS v20; // eax
  __int64 v21; // rcx
  unsigned int v22; // eax
  unsigned int v23; // eax
  int v24; // edi
  unsigned int v25; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-49h]
  PHKEY phkResulta; // [rsp+20h] [rbp-49h]
  LPDWORD lpcbMaxSubKeyLen; // [rsp+28h] [rbp-41h]
  DWORD cbMaxSubKeyLen; // [rsp+60h] [rbp-9h] BYREF
  signed int v31; // [rsp+64h] [rbp-5h]
  HKEY hKey; // [rsp+68h] [rbp-1h] BYREF
  unsigned __int16 *v33; // [rsp+70h] [rbp+7h] BYREF
  void *lpMem; // [rsp+78h] [rbp+Fh] BYREF
  NgcStatusStorage *cchName; // [rsp+D0h] [rbp+67h] BYREF
  DWORD v36; // [rsp+D8h] [rbp+6Fh]
  unsigned __int16 *v37; // [rsp+E0h] [rbp+77h]
  DWORD cSubKeys; // [rsp+E8h] [rbp+7Fh] BYREF

  v37 = a3;
  cchName = this;
  v3 = a3;
  hKey = 0;
  cSubKeys = 0;
  v5 = 0;
  cbMaxSubKeyLen = 0;
  v6 = 0;
  v33 = 0;
  lpMem = 0;
  if ( !a2 )
  {
    v7 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"NgcStatusStorage::Delete", L"hUserRegistry");
    Logger::WriteNullOrEmptyParameterFailureEvent(L"NgcStatusStorage::Delete", L"hUserRegistry");
LABEL_54:
    if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) != 0 )
    {
      v25 = McTemplateU0dzz_EventWriteTransfer(v8, (unsigned int)NgcDeleteStatusFailureEvent, v7, 0, (__int64)v3);
      if ( v25 )
        Logger::TraceError(
          L"%s: %s failed with win32 error code: 0x%08x.",
          L"Logger::WriteNgcDeleteStatusFailureEvent",
          L"EventWriteNgcDeleteStatusFailureEvent",
          v25);
    }
    goto LABEL_58;
  }
  if ( (unsigned int)IsEmptyString(a3) )
  {
    v9 = L"HKEY_CURRENT_USER";
  }
  else
  {
    v10 = StringCat(L"HKEY_USERS\\", v3, &v33);
    v7 = v10;
    if ( v10 < 0 )
    {
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"NgcStatusStorage::Delete",
        L"StringCat",
        (unsigned int)v10);
      v6 = v33;
      goto LABEL_54;
    }
    v6 = v33;
    v9 = v33;
  }
  v11 = StringCat(
          0,
          L"\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC",
          (unsigned __int16 **)&lpMem);
  v31 = v11;
  v7 = v11;
  if ( v11 < 0 )
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"NgcStatusStorage::Delete",
      L"StringCat",
      (unsigned int)v11);
LABEL_53:
    v3 = v37;
    goto LABEL_54;
  }
  v12 = RegOpenKeyExW(a2, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC", 0, 0x20019u, &hKey);
  v13 = v12;
  if ( v12 == 2 )
  {
    Logger::TraceInformation(
      L"%s: The registry key \"%s\" does not exist. Noting to delete.",
      L"NgcStatusStorage::Delete",
      v9);
    goto LABEL_58;
  }
  v36 = 0;
  if ( v12 )
  {
    Logger::WriteRegistryFailureEvent(v12, L"RegOpenKeyExW", v9);
    Logger::TraceError(
      L"%s: Cannot open registry key \"%s\". Win32 error code: 0x%08x.",
      L"NgcStatusStorage::Delete",
      v9,
      (unsigned int)v13);
    goto LABEL_43;
  }
  v14 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  v13 = v14;
  if ( v14 )
  {
    Logger::WriteRegistryFailureEvent(v14, L"RegQueryInfoKeyW", v9);
    LODWORD(phkResult) = v13;
    Logger::TraceError(
      L"%s: Cannot query values of registry key \"%s\\%s\". Win32 error code: 0x%08x.",
      L"NgcStatusStorage::Delete",
      v9,
      L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC",
      phkResult);
    goto LABEL_43;
  }
  if ( !cSubKeys || !cbMaxSubKeyLen )
  {
    Logger::TraceInformation(L"%s: There is no valid key registry.", L"NgcStatusStorage::Delete");
    goto LABEL_58;
  }
  v5 = (WCHAR *)SafeAlloc(2LL * (cbMaxSubKeyLen + 1));
  if ( !v5 )
  {
    v7 = -2147024882;
    Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"NgcStatusStorage::Delete");
    goto LABEL_53;
  }
  v15 = 0;
  v16 = 0;
  v17 = cSubKeys;
  LODWORD(cchName) = 0;
  if ( !cSubKeys )
    goto LABEL_39;
  v18 = 0;
  v19 = 0;
  do
  {
    LODWORD(cchName) = cbMaxSubKeyLen + 1;
    v36 = v17 - 1;
    v20 = RegEnumKeyExW(hKey, v17 - 1, v5, (LPDWORD)&cchName, 0, 0, 0, 0);
    v13 = v20;
    if ( v20 )
    {
      if ( !v19 )
      {
        Logger::WriteRegistryFailureEvent(v20, L"RegEnumKeyExW", v9);
        v19 = 1;
      }
      Logger::WriteNgcDeleteStatusFailureEvent(v13, v5, v37);
      LODWORD(lpcbMaxSubKeyLen) = v13;
      LODWORD(phkResulta) = v17;
      Logger::TraceError(
        L"%s: Cannot enumerate keys under registry key \"%s\\%s\". Index: %u, Win32 error code: 0x%08x.",
        L"NgcStatusStorage::Delete",
        v9,
        L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC",
        phkResulta,
        lpcbMaxSubKeyLen);
LABEL_27:
      if ( !v16 )
        v16 = v13;
      goto LABEL_37;
    }
    v13 = RegDeleteKeyExW(hKey, v5, 0, 0);
    if ( v13 )
    {
      if ( !v19 )
      {
        Logger::WriteRegistryFailureEventEx(
          v13,
          L"RegDeleteKeyExW",
          L"%s\\%s\\%s",
          v9,
          L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC",
          v5);
        v19 = 1;
      }
      Logger::WriteNgcDeleteStatusFailureEvent(v13, v5, v37);
      LODWORD(lpcbMaxSubKeyLen) = v13;
      Logger::TraceError(
        L"%s: Cannot delete registry key \"%s\\%s\\%s\". Win32 error code: 0x%08x.",
        L"NgcStatusStorage::Delete",
        v9,
        L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC",
        v5,
        lpcbMaxSubKeyLen);
      goto LABEL_27;
    }
    if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 1) != 0 )
    {
      v22 = McTemplateU0zz_EventWriteTransfer(v21, NgcDeleteStatusSuccessEvent, v5, v37);
      if ( v22 )
        Logger::TraceError(
          L"%s: %s failed with win32 error code: 0x%08x.",
          L"Logger::WriteNgcDeleteStatusSuccessEvent",
          L"EventWriteNgcDeleteStatusSuccessEvent",
          v22);
    }
    Logger::TraceInformation(
      L"%s: NGC key status deleted from registry \"%s\\%s\\%s\".",
      L"NgcStatusStorage::Delete",
      v9,
      L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC",
      v5);
    ++v18;
LABEL_37:
    v17 = v36;
  }
  while ( v36 );
  LODWORD(cchName) = v18;
  v6 = v33;
  v15 = (unsigned int)cchName;
  v36 = v19;
  v7 = v31;
LABEL_39:
  Logger::TraceVerbose((wchar_t *)L"%s: %u key(s) deleted.", L"NgcStatusStorage::Delete", v15);
  if ( !(_DWORD)cchName )
  {
    if ( !v13 )
      goto LABEL_46;
LABEL_43:
    if ( v13 > 0 )
    {
      v24 = (unsigned __int16)v13;
      goto LABEL_50;
    }
    v7 = v13;
LABEL_51:
    if ( v7 >= 0 || v36 )
      goto LABEL_58;
    goto LABEL_53;
  }
  v23 = RegFlush(hKey, (const unsigned __int16 *)lpMem);
  v13 = v23;
  if ( v23 )
  {
    Logger::TraceError(L"%s: %s failed with win32 error code: 0x%08x.", L"NgcStatusStorage::Delete", L"RegFlush", v23);
    goto LABEL_43;
  }
LABEL_46:
  if ( v16 )
  {
    if ( v16 <= 0 )
    {
      v7 = v16;
      goto LABEL_51;
    }
    v24 = (unsigned __int16)v16;
LABEL_50:
    v7 = v24 | 0x80070000;
    goto LABEL_51;
  }
LABEL_58:
  if ( hKey )
    RegCloseKey(hKey);
  SafeFree(v5);
  SafeFree(v6);
  SafeFree(lpMem);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180094810  mov     [rsp-8+arg_10], r8
0x180094815  mov     [rsp-8+cchName], rcx
0x18009481a  push    rbp
0x18009481b  push    rbx
0x18009481c  push    rsi
0x18009481d  push    rdi
0x18009481e  push    r12
0x180094820  push    r13
0x180094822  push    r14
0x180094824  push    r15
0x180094826  lea     rbp, [rsp-1Fh]
0x18009482b  sub     rsp, 88h
0x180094832  xor     r15d, r15d
0x180094835  mov     rsi, r8
0x180094838  mov     [rbp+57h+hKey], r15
0x18009483c  mov     rbx, rdx
0x18009483f  mov     [rbp+57h+cSubKeys], r15d
0x180094843  mov     r12d, r15d
0x180094846  mov     [rbp+57h+cbMaxSubKeyLen], r15d
0x18009484a  mov     r13d, r15d
0x18009484d  mov     [rbp+57h+var_50], r15
0x180094851  mov     [rbp+57h+lpMem], r15
0x180094855  test    rdx, rdx
0x180094858  jnz     short loc_180094891
0x18009485a  lea     r8, aHuserregistry; "hUserRegistry"
0x180094861  mov     edi, 80070057h
0x180094866  lea     rdx, aNgcstatusstora_4; "NgcStatusStorage::Delete"
0x18009486d  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180094874  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180094879  lea     rdx, aHuserregistry; "hUserRegistry"
0x180094880  lea     rcx, aNgcstatusstora_4; "NgcStatusStorage::Delete"
0x180094887  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18009488c  jmp     loc_180094C8A
0x180094891  mov     rcx, rsi; unsigned __int16 *
0x180094894  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x180094899  test    eax, eax
0x18009489b  jz      short loc_1800948A6
0x18009489d  lea     rsi, aHkeyCurrentUse; "HKEY_CURRENT_USER"
0x1800948a4  jmp     short loc_1800948EC
0x1800948a6  lea     r8, [rbp+57h+var_50]; unsigned __int16 **
0x1800948aa  mov     rdx, rsi; unsigned __int16 *
0x1800948ad  lea     rcx, aHkeyUsers_0; "HKEY_USERS\\"
0x1800948b4  call    ?StringCat@@YAJPEBG0PEAPEAG@Z; StringCat(ushort const *,ushort const *,ushort * *)
0x1800948b9  mov     edi, eax
0x1800948bb  test    eax, eax
0x1800948bd  jns     short loc_1800948E5
0x1800948bf  mov     r9d, eax
0x1800948c2  lea     r8, aStringcat; "StringCat"
0x1800948c9  lea     rdx, aNgcstatusstora_4; "NgcStatusStorage::Delete"
0x1800948d0  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x1800948d7  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800948dc  mov     r13, [rbp+57h+var_50]
0x1800948e0  jmp     loc_180094C8A
0x1800948e5  mov     r13, [rbp+57h+var_50]
0x1800948e9  mov     rsi, r13
0x1800948ec  lea     r8, [rbp+57h+lpMem]; unsigned __int16 **
0x1800948f0  xor     ecx, ecx; unsigned __int16 *
0x1800948f2  lea     rdx, aSoftwareMicros_0; "\\SOFTWARE\\Microsoft\\Windows NT\\Curr"...
0x1800948f9  call    ?StringCat@@YAJPEBG0PEAPEAG@Z; StringCat(ushort const *,ushort const *,ushort * *)
0x1800948fe  mov     [rbp+57h+var_5C], eax
0x180094901  mov     edi, eax
0x180094903  test    eax, eax
0x180094905  jns     short loc_180094929
0x180094907  mov     r9d, eax
0x18009490a  lea     r8, aStringcat; "StringCat"
0x180094911  lea     rdx, aNgcstatusstora_4; "NgcStatusStorage::Delete"
0x180094918  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18009491f  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180094924  jmp     loc_180094C86
0x180094929  lea     rax, [rbp+57h+hKey]
0x18009492d  mov     r9d, 20019h; samDesired
0x180094933  lea     r14, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18009493a  mov     [rsp+0C0h+phkResult], rax; phkResult
0x18009493f  mov     rdx, r14; lpSubKey
0x180094942  xor     r8d, r8d; ulOptions
0x180094945  mov     rcx, rbx; hKey
0x180094948  call    cs:__imp_RegOpenKeyExW
0x18009494e  mov     ebx, eax
0x180094950  cmp     eax, 2
0x180094953  jnz     short loc_180094970
0x180094955  mov     r8, rsi
0x180094958  lea     rdx, aNgcstatusstora_4; "NgcStatusStorage::Delete"
0x18009495f  lea     rcx, aSTheRegistryKe_8; "%s: The registry key \"%s\" does not ex"...
0x180094966  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x18009496b  jmp     loc_180094CE0
0x180094970  mov     [rbp+57h+arg_8], r15d
0x180094974  test    ebx, ebx
0x180094976  jz      short loc_1800949A7
0x180094978  mov     r8, rsi; unsigned __int16 *
0x18009497b  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x180094982  mov     ecx, ebx; unsigned int
0x180094984  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG0@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *)
0x180094989  mov     r9d, ebx
0x18009498c  lea     rcx, aSCannotOpenReg_4; "%s: Cannot open registry key \"%s\". Wi"...
0x180094993  mov     r8, rsi
0x180094996  lea     rdx, aNgcstatusstora_4; "NgcStatusStorage::Delete"
0x18009499d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800949a2  jmp     loc_180094C59
0x1800949a7  mov     rcx, [rbp+57h+hKey]; hKey
0x1800949ab  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x1800949af  mov     [rsp+0C0h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800949b4  xor     r9d, r9d; lpReserved
0x1800949b7  mov     [rsp+0C0h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1800949bc  xor     r8d, r8d; lpcchClass
0x1800949bf  mov     [rsp+0C0h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1800949c4  xor     edx, edx; lpClass
0x1800949c6  mov     [rsp+0C0h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x1800949cb  mov     [rsp+0C0h+lpcValues], r15; lpcValues
0x1800949d0  mov     [rsp+0C0h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1800949d5  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1800949da  lea     rax, [rbp+57h+cSubKeys]
0x1800949de  mov     [rsp+0C0h+phkResult], rax; lpcSubKeys
0x1800949e3  call    cs:__imp_RegQueryInfoKeyW
0x1800949e9  mov     ebx, eax
0x1800949eb  test    eax, eax
0x1800949ed  jz      short loc_180094A22
0x1800949ef  mov     r8, rsi; unsigned __int16 *
0x1800949f2  lea     rdx, aRegqueryinfoke; "RegQueryInfoKeyW"
0x1800949f9  mov     ecx, eax; unsigned int
0x1800949fb  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG0@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *)
0x180094a00  mov     r9, r14
0x180094a03  mov     dword ptr [rsp+0C0h+phkResult], ebx
0x180094a07  mov     r8, rsi
0x180094a0a  lea     rdx, aNgcstatusstora_4; "NgcStatusStorage::Delete"
0x180094a11  lea     rcx, aSCannotQueryVa; "%s: Cannot query values of registry key"...
0x180094a18  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180094a1d  jmp     loc_180094C59
0x180094a22  cmp     [rbp+57h+cSubKeys], r15d
0x180094a26  jz      loc_180094CCD
0x180094a2c  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x180094a2f  test    eax, eax
0x180094a31  jz      loc_180094CCD
0x180094a37  lea     ecx, [rax+1]
0x180094a3a  add     rcx, rcx; unsigned __int64
0x180094a3d  call    ?SafeAlloc@@YAPEAX_K@Z; SafeAlloc(unsigned __int64)
0x180094a42  mov     r12, rax
0x180094a45  test    rax, rax
0x180094a48  jnz     short loc_180094A67
0x180094a4a  lea     rdx, aNgcstatusstora_4; "NgcStatusStorage::Delete"
0x180094a51  mov     edi, 8007000Eh
0x180094a56  lea     rcx, aSOutOfMemoryAl_0; "%s: Out of memory. Allocation failed."
0x180094a5d  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x180094a62  jmp     loc_180094C86
0x180094a67  mov     eax, r15d
0x180094a6a  mov     r14d, r15d
0x180094a6d  mov     r15d, [rbp+57h+cSubKeys]
0x180094a71  mov     dword ptr [rbp+57h+cchName], eax
0x180094a74  test    r15d, r15d
0x180094a77  jz      loc_180094C0D
0x180094a7d  mov     r13d, eax
0x180094a80  mov     edi, eax
0x180094a82  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x180094a85  lea     r9, [rbp+57h+cchName]; lpcchName
0x180094a89  mov     rcx, [rbp+57h+hKey]; hKey
0x180094a8d  xor     ebx, ebx
0x180094a8f  inc     eax
0x180094a91  mov     [rsp+0C0h+lpcValues], rbx; lpftLastWriteTime
0x180094a96  mov     dword ptr [rbp+57h+cchName], eax
0x180094a99  mov     r8, r12; lpName
0x180094a9c  lea     eax, [r15-1]
0x180094aa0  mov     [rsp+0C0h+lpcbMaxClassLen], rbx; lpcchClass
0x180094aa5  mov     edx, eax; dwIndex
0x180094aa7  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rbx; lpClass
0x180094aac  mov     [rbp+57h+arg_8], eax
0x180094aaf  mov     [rsp+0C0h+phkResult], rbx; lpReserved
0x180094ab4  call    cs:__imp_RegEnumKeyExW
0x180094aba  mov     ebx, eax
0x180094abc  test    eax, eax
0x180094abe  jz      short loc_180094B1F
0x180094ac0  test    edi, edi
0x180094ac2  jnz     short loc_180094ADA
0x180094ac4  mov     r8, rsi; unsigned __int16 *
0x180094ac7  lea     rdx, aRegenumkeyexw; "RegEnumKeyExW"
0x180094ace  mov     ecx, eax; unsigned int
0x180094ad0  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG0@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *)
0x180094ad5  mov     edi, 1
0x180094ada  mov     r8, [rbp+57h+arg_10]; unsigned __int16 *
0x180094ade  mov     rdx, r12; unsigned __int16 *
0x180094ae1  mov     ecx, ebx; unsigned int
0x180094ae3  call    ?WriteNgcDeleteStatusFailureEvent@Logger@@SAJKPEBG0@Z; Logger::WriteNgcDeleteStatusFailureEvent(ulong,ushort const *,ushort const *)
0x180094ae8  mov     dword ptr [rsp+0C0h+lpcbMaxSubKeyLen], ebx
0x180094aec  lea     rcx, aSCannotEnumera_1; "%s: Cannot enumerate keys under registr"...
0x180094af3  mov     dword ptr [rsp+0C0h+phkResult], r15d
0x180094af8  lea     rdx, aNgcstatusstora_4; "NgcStatusStorage::Delete"
0x180094aff  mov     r8, rsi
0x180094b02  lea     r9, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180094b09  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180094b0e  test    r14d, r14d
0x180094b11  jnz     loc_180094BEF
0x180094b17  mov     r14d, ebx
0x180094b1a  jmp     loc_180094BEF
0x180094b1f  mov     rcx, [rbp+57h+hKey]; hKey
0x180094b23  xor     r9d, r9d; Reserved
0x180094b26  xor     r8d, r8d; samDesired
0x180094b29  mov     rdx, r12; lpSubKey
0x180094b2c  call    cs:__imp_RegDeleteKeyExW
0x180094b32  mov     ebx, eax
0x180094b34  test    eax, eax
0x180094b36  jz      short loc_180094B8D
0x180094b38  test    edi, edi
0x180094b3a  jnz     short loc_180094B6A
0x180094b3c  lea     rax, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180094b43  mov     [rsp+0C0h+lpcbMaxSubKeyLen], r12
0x180094b48  mov     r9, rsi
0x180094b4b  mov     [rsp+0C0h+phkResult], rax
0x180094b50  lea     r8, aSSS; "%s\\%s\\%s"
0x180094b57  mov     ecx, ebx; unsigned int
0x180094b59  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x180094b60  call    ?WriteRegistryFailureEventEx@Logger@@SAJKPEBG0ZZ; Logger::WriteRegistryFailureEventEx(ulong,ushort const *,ushort const *,...)
0x180094b65  mov     edi, 1
0x180094b6a  mov     r8, [rbp+57h+arg_10]; unsigned __int16 *
0x180094b6e  mov     rdx, r12; unsigned __int16 *
0x180094b71  mov     ecx, ebx; unsigned int
0x180094b73  call    ?WriteNgcDeleteStatusFailureEvent@Logger@@SAJKPEBG0@Z; Logger::WriteNgcDeleteStatusFailureEvent(ulong,ushort const *,ushort const *)
0x180094b78  mov     dword ptr [rsp+0C0h+lpcbMaxSubKeyLen], ebx
0x180094b7c  lea     rcx, aSCannotDeleteR; "%s: Cannot delete registry key \"%s\\%s"...
0x180094b83  mov     [rsp+0C0h+phkResult], r12
0x180094b88  jmp     loc_180094AF8
0x180094b8d  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 1
0x180094b94  jz      short loc_180094BCA
0x180094b96  mov     r9, [rbp+57h+arg_10]
0x180094b9a  lea     rdx, NgcDeleteStatusSuccessEvent
0x180094ba1  mov     r8, r12
0x180094ba4  call    McTemplateU0zz_EventWriteTransfer
0x180094ba9  test    eax, eax
0x180094bab  jz      short loc_180094BCA
0x180094bad  mov     r9d, eax
0x180094bb0  lea     r8, aEventwritengcd_7; "EventWriteNgcDeleteStatusSuccessEvent"
0x180094bb7  lea     rdx, aLoggerWritengc_32; "Logger::WriteNgcDeleteStatusSuccessEven"...
0x180094bbe  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x180094bc5  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180094bca  lea     r9, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180094bd1  mov     [rsp+0C0h+phkResult], r12
0x180094bd6  mov     r8, rsi
0x180094bd9  lea     rdx, aNgcstatusstora_4; "NgcStatusStorage::Delete"
0x180094be0  lea     rcx, aSNgcKeyStatusD; "%s: NGC key status deleted from registr"...
0x180094be7  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x180094bec  inc     r13d
0x180094bef  mov     r15d, [rbp+57h+arg_8]
0x180094bf3  test    r15d, r15d
0x180094bf6  jnz     loc_180094A82
0x180094bfc  mov     dword ptr [rbp+57h+cchName], r13d
0x180094c00  mov     r13, [rbp+57h+var_50]
0x180094c04  mov     eax, dword ptr [rbp+57h+cchName]
0x180094c07  mov     [rbp+57h+arg_8], edi
0x180094c0a  mov     edi, [rbp+57h+var_5C]
0x180094c0d  mov     r8d, eax
0x180094c10  lea     rdx, aNgcstatusstora_4; "NgcStatusStorage::Delete"
0x180094c17  lea     rcx, aSUKeySDeleted; "%s: %u key(s) deleted."
0x180094c1e  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180094c23  xor     r15d, r15d
0x180094c26  cmp     dword ptr [rbp+57h+cchName], r15d
0x180094c2a  jbe     short loc_180094C55
0x180094c2c  mov     rdx, [rbp+57h+lpMem]; unsigned __int16 *
0x180094c30  mov     rcx, [rbp+57h+hKey]; HKEY
0x180094c34  call    ?RegFlush@@YAKPEAUHKEY__@@PEBG@Z; RegFlush(HKEY__ *,ushort const *)
0x180094c39  mov     ebx, eax
0x180094c3b  test    eax, eax
0x180094c3d  jz      short loc_180094C66
0x180094c3f  mov     r9d, eax
0x180094c42  lea     r8, aRegflush; "RegFlush"
0x180094c49  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x180094c50  jmp     loc_180094996
0x180094c55  test    ebx, ebx
0x180094c57  jz      short loc_180094C66
0x180094c59  test    ebx, ebx
0x180094c5b  jg      short loc_180094C61
0x180094c5d  mov     edi, ebx
0x180094c5f  jmp     short loc_180094C7C
0x180094c61  movzx   edi, bx
0x180094c64  jmp     short loc_180094C76
0x180094c66  test    r14d, r14d
0x180094c69  jz      short loc_180094CE0
0x180094c6b  jg      short loc_180094C72
0x180094c6d  mov     edi, r14d
0x180094c70  jmp     short loc_180094C7C
0x180094c72  movzx   edi, r14w
0x180094c76  or      edi, 80070000h
0x180094c7c  test    edi, edi
0x180094c7e  jns     short loc_180094CE0
0x180094c80  cmp     [rbp+57h+arg_8], r15d
0x180094c84  jnz     short loc_180094CE0
0x180094c86  mov     rsi, [rbp+57h+arg_10]
0x180094c8a  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x180094c91  jz      short loc_180094CE0
0x180094c93  xor     r9d, r9d
0x180094c96  mov     [rsp+0C0h+phkResult], rsi
0x180094c9b  mov     r8d, edi
0x180094c9e  lea     rdx, NgcDeleteStatusFailureEvent
0x180094ca5  call    McTemplateU0dzz_EventWriteTransfer
0x180094caa  test    eax, eax
0x180094cac  jz      short loc_180094CE0
0x180094cae  mov     r9d, eax
0x180094cb1  lea     r8, aEventwritengcd_4; "EventWriteNgcDeleteStatusFailureEvent"
0x180094cb8  lea     rdx, aLoggerWritengc_37; "Logger::WriteNgcDeleteStatusFailureEven"...
0x180094cbf  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x180094cc6  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180094ccb  jmp     short loc_180094CE0
0x180094ccd  lea     rdx, aNgcstatusstora_4; "NgcStatusStorage::Delete"
0x180094cd4  lea     rcx, aSThereIsNoVali; "%s: There is no valid key registry."
  ... truncated ...
```
