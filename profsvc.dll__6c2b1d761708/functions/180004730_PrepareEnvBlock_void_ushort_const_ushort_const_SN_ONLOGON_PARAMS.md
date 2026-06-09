# PrepareEnvBlock(void *,ushort const *,ushort const *,_SN_ONLOGON_PARAMS *)

- ea: `0x180004730`
- end: `0x180005327`
- name: `?PrepareEnvBlock@@YAJPEAXPEBG1PEAU_SN_ONLOGON_PARAMS@@@Z`
- size: `3063`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, const unsigned __int16 *, const unsigned __int16 *, struct _SN_ONLOGON_PARAMS *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18001ce78`

## callees

- `0x180004730`
- `0x180005330`
- `0x180005370`
- `0x1800053c0`
- `0x1800054cc`
- `0x180005c80`
- `0x18000e1a0`
- `0x180011c00`
- `0x18001214c`
- `0x180024260`
- `0x180024be0`
- `0x180030628`
- `0x180030ad0`
- `0x180030af8`
- `0x180031060`
- `0x18003fff4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004799`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004814`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004b3d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004799`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004814`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004b3d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004867`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800048c9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004a9e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004afb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004dec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004e21`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005008`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005032`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005067`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000509c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800050f9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004867`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800048c9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004a9e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004afb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004dec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004e21`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005008`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005032`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005067`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000509c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800050f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000477f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800047fd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004853`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800048b5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004a8a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004ae7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004b25`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004dd8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004e0d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004ff4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000501e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005053`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005088`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800050e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000477f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800047fd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004853`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800048b5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004a8a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004ae7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004b25`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004dd8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004e0d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004ff4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000501e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005053`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005088`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800050e5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004905`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004905`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004abf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004ad5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004c4f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004c65`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004e42`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004fbc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004fd2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800050bd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800050d3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004abf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004ad5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004c4f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004c65`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004e42`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004fbc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004fd2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800050bd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800050d3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180004951`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180004951`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180004835`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180004835`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800047ec`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800047ec`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800047cf`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004cc7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800047cf`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004cc7`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180004891`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180004891`
- `profapi!__imp_GetBasicProfileFolderPathAlloc` at `0x180004a17`
- `profapi!__imp_GetBasicProfileFolderPathAlloc` at `0x180004d65`
- `profapi!__imp_GetBasicProfileFolderPathAlloc` at `0x180004e8b`
- `profapi!__imp_GetBasicProfileFolderPathAlloc` at `0x180004a17`
- `profapi!__imp_GetBasicProfileFolderPathAlloc` at `0x180004d65`
- `profapi!__imp_GetBasicProfileFolderPathAlloc` at `0x180004e8b`

## string_xrefs

- `0x18000496d`: `HOMEDIRECTORY`
- `0x180004978`: `PROFILEPATH`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall PrepareEnvBlock(
        HANDLE TokenHandle,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct _SN_ONLOGON_PARAMS *a4)
{
  WCHAR *v6; // r15
  HANDLE ProcessHeap; // rax
  WCHAR *v8; // rdi
  void *v9; // rsi
  int Error; // ebx
  DWORD LengthSid; // ebx
  HANDLE v12; // rax
  void *v13; // rax
  void *v14; // r14
  HANDLE v15; // rax
  HANDLE v16; // rax
  unsigned int v17; // eax
  unsigned int v18; // eax
  HKEY v19; // r12
  WCHAR *v20; // rdi
  __int64 v21; // rax
  unsigned __int64 v22; // rbx
  SIZE_T v23; // rsi
  __int64 v24; // rax
  int BasicProfileFolderPathAlloc; // ebx
  LPVOID v26; // rdi
  int v27; // eax
  void *v28; // rdi
  HANDLE v29; // rax
  HKEY v30; // rcx
  HANDLE v31; // rax
  HANDLE v33; // rax
  WCHAR *v34; // rax
  WCHAR *v35; // r14
  __int64 v36; // rcx
  WCHAR *v37; // rdx
  WCHAR *v38; // r8
  WCHAR v39; // ax
  WCHAR *v40; // rcx
  const unsigned __int16 *v41; // rbx
  WCHAR v42; // ax
  WCHAR *v43; // rcx
  unsigned int i; // esi
  __int64 v45; // rdx
  HKEY v46; // rcx
  HKEY v47; // rcx
  BOOL TokenInformation; // eax
  int v49; // eax
  unsigned __int16 *v50; // rdi
  int v51; // eax
  unsigned __int16 *v52; // rdi
  HANDLE v53; // rax
  void *v54; // rdi
  HANDLE v55; // rax
  unsigned __int16 *v56; // rdi
  int v57; // eax
  __int64 v58; // rdx
  int UserDomainName; // eax
  unsigned __int16 *v60; // rbx
  int v61; // eax
  unsigned int v62; // edi
  HANDLE v63; // rax
  unsigned __int16 *v64; // rbx
  HANDLE v65; // rax
  unsigned __int16 *v66; // rbx
  HANDLE v67; // rax
  void *v68; // rbx
  HANDLE v69; // rax
  HANDLE v70; // rax
  __int64 v71; // rcx
  __int64 v72; // rcx
  __int64 v73; // rcx
  __int64 v74; // rcx
  int ReturnLength; // [rsp+20h] [rbp-A9h]
  unsigned int ReturnLengtha; // [rsp+20h] [rbp-A9h]
  unsigned int ReturnLengthb; // [rsp+20h] [rbp-A9h]
  int ReturnLengthc; // [rsp+20h] [rbp-A9h]
  int ReturnLengthd; // [rsp+20h] [rbp-A9h]
  int ReturnLengthe; // [rsp+20h] [rbp-A9h]
  HKEY hKey; // [rsp+50h] [rbp-79h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-71h] BYREF
  LPWSTR StringSid; // [rsp+60h] [rbp-69h] BYREF
  DWORD TokenInformationLength[2]; // [rsp+68h] [rbp-61h] BYREF
  LPVOID lpMem; // [rsp+70h] [rbp-59h] BYREF
  __int64 v86; // [rsp+78h] [rbp-51h]
  __int64 v87; // [rsp+80h] [rbp-49h]
  unsigned __int16 *v88; // [rsp+88h] [rbp-41h] BYREF
  __int64 v89; // [rsp+90h] [rbp-39h]
  __int64 v90; // [rsp+98h] [rbp-31h]
  _QWORD v91[3]; // [rsp+A0h] [rbp-29h] BYREF
  unsigned __int16 *v92; // [rsp+B8h] [rbp-11h] BYREF
  __int64 v93; // [rsp+C0h] [rbp-9h]
  __int64 v94; // [rsp+C8h] [rbp-1h]
  unsigned __int16 *v95; // [rsp+D0h] [rbp+7h] BYREF
  __int64 v96; // [rsp+D8h] [rbp+Fh]
  __int64 v97; // [rsp+E0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  v6 = 0;
  v91[0] = 0;
  v91[1] = -1;
  v91[2] = -1;
  TokenInformationLength[0] = 200;
  ProcessHeap = GetProcessHeap();
  v8 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, 0xC8u);
  StringSid = v8;
  if ( !v8 )
  {
    Error = -2147024882;
    goto LABEL_19;
  }
  v9 = 0;
  if ( GetTokenInformation(TokenHandle, TokenUser, v8, TokenInformationLength[0], TokenInformationLength) )
  {
    Error = 0;
  }
  else
  {
    Error = ResultFromKnownLastError();
    if ( Error == -2147024774 )
    {
      Error = ResultFromHeapReAlloc(v8, TokenInformationLength[0], (void **)&StringSid);
      v8 = StringSid;
      if ( Error < 0 )
        goto LABEL_9;
      TokenInformation = GetTokenInformation(
                           TokenHandle,
                           TokenUser,
                           StringSid,
                           TokenInformationLength[0],
                           TokenInformationLength);
      Error = ResultFromWin32Bool(TokenInformation);
    }
  }
  if ( Error >= 0 )
  {
    LengthSid = GetLengthSid(*(PSID *)v8);
    TokenInformationLength[0] = LengthSid;
    v12 = GetProcessHeap();
    v13 = HeapAlloc(v12, 8u, LengthSid);
    v14 = v13;
    if ( !v13 )
    {
      Error = -2147024882;
      goto LABEL_9;
    }
    if ( CopySid(TokenInformationLength[0], v13, *(PSID *)v8) )
    {
      Error = 0;
    }
    else
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
      {
        ResultFromHeapFree(v14);
        goto LABEL_9;
      }
    }
    v9 = v14;
  }
LABEL_9:
  if ( v8 )
  {
    v15 = GetProcessHeap();
    if ( !HeapFree(v15, 0, v8) )
      ResultFromKnownLastError();
  }
  if ( Error >= 0 )
  {
    StringSid = 0;
    if ( ConvertSidToStringSidW(v9, &StringSid) )
    {
      Error = 0;
    }
    else
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
        goto LABEL_16;
    }
    v6 = StringSid;
    v91[0] = StringSid;
LABEL_16:
    if ( v9 )
    {
      v16 = GetProcessHeap();
      if ( !HeapFree(v16, 0, v9) )
        ResultFromKnownLastError();
    }
  }
LABEL_19:
  if ( Error < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x32D,
      (unsigned int)`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.SubAuthority,
      (const char *)(unsigned int)Error,
      ReturnLength);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v91);
    return (unsigned int)Error;
  }
  phkResult = 0;
  v17 = RegOpenKeyExW(HKEY_USERS, v6, 0, 0x20006u, &phkResult);
  if ( v17 )
  {
    BasicProfileFolderPathAlloc = wil::details::in1diag3::Return_Win32(
                                    retaddr,
                                    (void *)0x331,
                                    (unsigned int)`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.SubAuthority,
                                    (const char *)v17,
                                    ReturnLengtha);
    v47 = phkResult;
    if ( !phkResult )
      goto LABEL_68;
    goto LABEL_67;
  }
  hKey = 0;
  v18 = RegCreateKeyExW(phkResult, L"Volatile Environment", 0, 0, 1u, 0x20006u, 0, &hKey, 0);
  if ( v18 )
  {
    BasicProfileFolderPathAlloc = wil::details::in1diag3::Return_Win32(
                                    retaddr,
                                    (void *)0x334,
                                    (unsigned int)`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.SubAuthority,
                                    (const char *)v18,
                                    ReturnLengthb);
    v46 = hKey;
    if ( !hKey )
    {
LABEL_66:
      v47 = phkResult;
      if ( !phkResult )
      {
LABEL_68:
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v91);
        return (unsigned int)BasicProfileFolderPathAlloc;
      }
LABEL_67:
      RegCloseKey(v47);
      goto LABEL_68;
    }
LABEL_65:
    RegCloseKey(v46);
    goto LABEL_66;
  }
  v19 = hKey;
  v20 = (WCHAR *)*((_QWORD *)a4 + 4);
  v95 = L"HOMEDIRECTORY";
  v96 = (__int64)L"PROFILEPATH";
  while ( *v20 )
  {
    StringSid = 0;
    v21 = -1;
    do
      ++v21;
    while ( v20[v21] );
    v22 = v21 + 1;
    *(_QWORD *)TokenInformationLength = 0;
    v23 = 2 * (v21 + 1);
    if ( is_mul_ok(v21 + 1, 2u) )
    {
      v33 = GetProcessHeap();
      v34 = (WCHAR *)HeapAlloc(v33, 8u, v23);
      v35 = v34;
      if ( v34 )
      {
        if ( v22 )
        {
          if ( v22 > 0x7FFFFFFF )
          {
            *v34 = 0;
          }
          else
          {
            v36 = 2147483646;
            v37 = v20;
            v38 = v34;
            do
            {
              if ( !v36 )
                break;
              v39 = *v37;
              if ( !*v37 )
                break;
              ++v37;
              *v38++ = v39;
              --v36;
              --v22;
            }
            while ( v22 );
            v40 = v38 - 1;
            if ( v22 )
              v40 = v38;
            *v40 = 0;
            if ( v22 )
            {
              StringSid = v35;
              v41 = 0;
              v42 = *v35;
              if ( *v35 )
              {
                v43 = v35;
                do
                {
                  if ( v42 == 61 )
                  {
                    *v43 = 0;
                    v41 = v43 + 1;
                  }
                  v42 = *++v43;
                }
                while ( *v43 );
              }
              if ( *v35 && v41 && *v41 )
              {
                for ( i = 0; i < 2; ++i )
                {
                  if ( StringIsEqual(v35, (&v95)[i]) )
                    goto LABEL_26;
                }
                _SetEnvVar(v19, v35, v41);
              }
              goto LABEL_26;
            }
          }
        }
        ResultFromHeapFree(v35);
      }
    }
LABEL_26:
    v24 = -1;
    do
      ++v24;
    while ( v20[v24] );
    v20 += v24 + 1;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
  }
  lpMem = 0;
  v86 = -1;
  v87 = -1;
  BasicProfileFolderPathAlloc = GetBasicProfileFolderPathAlloc(5, v6, &lpMem);
  if ( BasicProfileFolderPathAlloc < 0 )
  {
    v45 = 827;
LABEL_63:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v45,
      (unsigned int)`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.SubAuthority,
      (const char *)(unsigned int)BasicProfileFolderPathAlloc,
      ReturnLengthb);
    goto LABEL_64;
  }
  v26 = lpMem;
  v27 = SHRegSetString(hKey, 0, L"USERPROFILE", (const unsigned __int16 *)lpMem);
  BasicProfileFolderPathAlloc = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x64,
      (unsigned int)`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.SubAuthority,
      (const char *)(unsigned int)v27,
      ReturnLengthb);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x33C,
      (unsigned int)`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.SubAuthority,
      (const char *)(unsigned int)BasicProfileFolderPathAlloc,
      ReturnLengthc);
    v28 = lpMem;
    if ( lpMem )
    {
      v29 = GetProcessHeap();
      HeapFree(v29, 0, v28);
      lpMem = 0;
    }
    v86 = 0;
    v87 = 0;
    if ( hKey )
      RegCloseKey(hKey);
    v30 = phkResult;
    if ( !phkResult )
      goto LABEL_37;
    goto LABEL_36;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
    && Microsoft_Windows_User_Profiles_ServiceEnableBits < 0 )
  {
    McTemplateU0zz_EtwEventWriteTransfer(v71, EVENT_SET_ENV, L"USERPROFILE", v26);
  }
  BasicProfileFolderPathAlloc = SetHomeDirectory(
                                  *((unsigned __int16 **)a4 + 4),
                                  TokenHandle,
                                  (const unsigned __int16 *)lpMem,
                                  hKey,
                                  a2,
                                  a3);
  if ( BasicProfileFolderPathAlloc < 0 )
  {
    v45 = 831;
    goto LABEL_63;
  }
  v88 = 0;
  v89 = -1;
  v90 = -1;
  v49 = GetBasicProfileFolderPathAlloc(7, v6, &v88);
  BasicProfileFolderPathAlloc = v49;
  if ( v49 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x345,
      (unsigned int)`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.SubAuthority,
      (const char *)(unsigned int)v49,
      ReturnLengthb);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v88);
LABEL_64:
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpMem);
    v46 = hKey;
    if ( !hKey )
      goto LABEL_66;
    goto LABEL_65;
  }
  v50 = v88;
  v51 = SHRegSetString(hKey, 0, L"APPDATA", v88);
  BasicProfileFolderPathAlloc = v51;
  if ( v51 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x64,
      (unsigned int)`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.SubAuthority,
      (const char *)(unsigned int)v51,
      ReturnLengthb);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x346,
      (unsigned int)`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.SubAuthority,
      (const char *)(unsigned int)BasicProfileFolderPathAlloc,
      ReturnLengthd);
    v52 = v88;
    if ( v88 )
    {
      v53 = GetProcessHeap();
      HeapFree(v53, 0, v52);
      v88 = 0;
    }
    v89 = 0;
    v90 = 0;
    v54 = lpMem;
    if ( lpMem )
    {
      v55 = GetProcessHeap();
      HeapFree(v55, 0, v54);
      lpMem = 0;
    }
    v86 = 0;
    v87 = 0;
    if ( hKey )
      RegCloseKey(hKey);
    v30 = phkResult;
    if ( !phkResult )
      goto LABEL_37;
LABEL_36:
    RegCloseKey(v30);
LABEL_37:
    if ( v6 )
    {
      v31 = GetProcessHeap();
      HeapFree(v31, 0, v6);
    }
    return (unsigned int)BasicProfileFolderPathAlloc;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
    && Microsoft_Windows_User_Profiles_ServiceEnableBits < 0 )
  {
    McTemplateU0zz_EtwEventWriteTransfer(v72, EVENT_SET_ENV, L"APPDATA", v50);
  }
  v92 = 0;
  v93 = -1;
  v94 = -1;
  BasicProfileFolderPathAlloc = GetBasicProfileFolderPathAlloc(6, v6, &v92);
  if ( BasicProfileFolderPathAlloc < 0 )
  {
    v58 = 841;
    goto LABEL_91;
  }
  v56 = v92;
  v57 = SHRegSetString(hKey, 0, L"LOCALAPPDATA", v92);
  BasicProfileFolderPathAlloc = v57;
  if ( v57 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x64,
      (unsigned int)`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.SubAuthority,
      (const char *)(unsigned int)v57,
      ReturnLengthb);
    v58 = 842;
LABEL_91:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v58,
      (unsigned int)`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.SubAuthority,
      (const char *)(unsigned int)BasicProfileFolderPathAlloc,
      ReturnLengthb);
LABEL_92:
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v92);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v88);
    goto LABEL_64;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
    && Microsoft_Windows_User_Profiles_ServiceEnableBits < 0 )
  {
    McTemplateU0zz_EtwEventWriteTransfer(v73, EVENT_SET_ENV, L"LOCALAPPDATA", v56);
  }
  v95 = 0;
  v96 = -1;
  v97 = -1;
  UserDomainName = GetUserDomainName(TokenHandle, &v95);
  BasicProfileFolderPathAlloc = UserDomainName;
  if ( UserDomainName < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x34D,
      (unsigned int)`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.SubAuthority,
      (const char *)(unsigned int)UserDomainName,
      ReturnLengthb);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v95);
    goto LABEL_92;
  }
  v60 = v95;
  v61 = SHRegSetString(hKey, 0, L"USERDOMAIN_ROAMINGPROFILE", v95);
  v62 = v61;
  if ( v61 >= 0 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
      && Microsoft_Windows_User_Profiles_ServiceEnableBits < 0 )
    {
      McTemplateU0zz_EtwEventWriteTransfer(v74, EVENT_SET_ENV, L"USERDOMAIN_ROAMINGPROFILE", v60);
    }
    if ( v60 )
    {
      v63 = GetProcessHeap();
      HeapFree(v63, 0, v60);
    }
    v64 = v92;
    if ( v92 )
    {
      v65 = GetProcessHeap();
      HeapFree(v65, 0, v64);
      v92 = 0;
    }
    v93 = 0;
    v94 = 0;
    v66 = v88;
    if ( v88 )
    {
      v67 = GetProcessHeap();
      HeapFree(v67, 0, v66);
      v88 = 0;
    }
    v89 = 0;
    v90 = 0;
    v68 = lpMem;
    if ( lpMem )
    {
      v69 = GetProcessHeap();
      HeapFree(v69, 0, v68);
      lpMem = 0;
    }
    v86 = 0;
    v87 = 0;
    if ( hKey )
      RegCloseKey(hKey);
    if ( phkResult )
      RegCloseKey(phkResult);
    if ( v6 )
    {
      v70 = GetProcessHeap();
      HeapFree(v70, 0, v6);
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x64,
      (unsigned int)`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.SubAuthority,
      (const char *)(unsigned int)v61,
      ReturnLengthb);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x34E,
      (unsigned int)`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.SubAuthority,
      (const char *)v62,
      ReturnLengthe);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v95);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v92);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v88);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpMem);
    if ( hKey )
      RegCloseKey(hKey);
    if ( phkResult )
      RegCloseKey(phkResult);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v91);
    return v62;
  }
}

```

## disassembly

```asm
0x180004730  mov     [rsp-8+arg_18], rbx
0x180004735  mov     [rsp-8+arg_10], r8
0x18000473a  mov     [rsp-8+arg_8], rdx
0x18000473f  mov     [rsp-8+arg_0], rcx
0x180004744  push    rbp
0x180004745  push    rsi
0x180004746  push    rdi
0x180004747  push    r12
0x180004749  push    r13
0x18000474b  push    r14
0x18000474d  push    r15
0x18000474f  lea     rbp, [rsp-27h]
0x180004754  sub     rsp, 0F0h
0x18000475b  mov     r13, r9
0x18000475e  mov     r14, rcx
0x180004761  xor     r15d, r15d
0x180004764  mov     [rbp+57h+var_80], r15
0x180004768  mov     [rbp+57h+var_78], 0FFFFFFFFFFFFFFFFh
0x180004770  mov     [rbp+57h+var_70], 0FFFFFFFFFFFFFFFFh
0x180004778  mov     [rbp+57h+TokenInformationLength], 0C8h
0x18000477f  call    cs:__imp_GetProcessHeap
0x180004786  nop     dword ptr [rax+rax+00h]
0x18000478b  mov     rcx, rax; hHeap
0x18000478e  mov     edx, 8; dwFlags
0x180004793  mov     r8d, 0C8h; dwBytes
0x180004799  call    cs:__imp_HeapAlloc
0x1800047a0  nop     dword ptr [rax+rax+00h]
0x1800047a5  mov     rdi, rax
0x1800047a8  mov     [rbp+57h+StringSid], rax
0x1800047ac  test    rax, rax
0x1800047af  jz      loc_180005164
0x1800047b5  xor     esi, esi
0x1800047b7  lea     rax, [rbp+57h+TokenInformationLength]
0x1800047bb  mov     [rsp+120h+ReturnLength], rax; int
0x1800047c0  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x1800047c4  mov     r8, rdi; TokenInformation
0x1800047c7  mov     edx, 1; TokenInformationClass
0x1800047cc  mov     rcx, r14; TokenHandle
0x1800047cf  call    cs:__imp_GetTokenInformation
0x1800047d6  nop     dword ptr [rax+rax+00h]
0x1800047db  test    eax, eax
0x1800047dd  jz      loc_180004C80
0x1800047e3  xor     ebx, ebx
0x1800047e5  test    ebx, ebx
0x1800047e7  js      short loc_18000484E
0x1800047e9  mov     rcx, [rdi]; pSid
0x1800047ec  call    cs:__imp_GetLengthSid
0x1800047f3  nop     dword ptr [rax+rax+00h]
0x1800047f8  mov     ebx, eax
0x1800047fa  mov     [rbp+57h+TokenInformationLength], ebx
0x1800047fd  call    cs:__imp_GetProcessHeap
0x180004804  nop     dword ptr [rax+rax+00h]
0x180004809  mov     rcx, rax; hHeap
0x18000480c  mov     r8d, ebx; dwBytes
0x18000480f  mov     edx, 8; dwFlags
0x180004814  call    cs:__imp_HeapAlloc
0x18000481b  nop     dword ptr [rax+rax+00h]
0x180004820  mov     r14, rax
0x180004823  test    rax, rax
0x180004826  jz      loc_180005171
0x18000482c  mov     r8, [rdi]; pSourceSid
0x18000482f  mov     rdx, rax; pDestinationSid
0x180004832  mov     ecx, [rbp+57h+TokenInformationLength]; nDestinationSidLength
0x180004835  call    cs:__imp_CopySid
0x18000483c  nop     dword ptr [rax+rax+00h]
0x180004841  test    eax, eax
0x180004843  jz      loc_180004CF5
0x180004849  xor     ebx, ebx
0x18000484b  mov     rsi, r14
0x18000484e  test    rdi, rdi
0x180004851  jz      short loc_18000487B
0x180004853  call    cs:__imp_GetProcessHeap
0x18000485a  nop     dword ptr [rax+rax+00h]
0x18000485f  mov     rcx, rax; hHeap
0x180004862  mov     r8, rdi; lpMem
0x180004865  xor     edx, edx; dwFlags
0x180004867  call    cs:__imp_HeapFree
0x18000486e  nop     dword ptr [rax+rax+00h]
0x180004873  test    eax, eax
0x180004875  jz      loc_18000517B
0x18000487b  test    ebx, ebx
0x18000487d  js      loc_180005169
0x180004883  xor     r14d, r14d
0x180004886  mov     [rbp+57h+StringSid], r14
0x18000488a  lea     rdx, [rbp+57h+StringSid]; StringSid
0x18000488e  mov     rcx, rsi; Sid
0x180004891  call    cs:__imp_ConvertSidToStringSidW
0x180004898  nop     dword ptr [rax+rax+00h]
0x18000489d  test    eax, eax
0x18000489f  jz      loc_180004CE1
0x1800048a5  mov     ebx, r14d
0x1800048a8  mov     r15, [rbp+57h+StringSid]
0x1800048ac  mov     [rbp+57h+var_80], r15
0x1800048b0  test    rsi, rsi
0x1800048b3  jz      short loc_1800048DD
0x1800048b5  call    cs:__imp_GetProcessHeap
0x1800048bc  nop     dword ptr [rax+rax+00h]
0x1800048c1  mov     rcx, rax; hHeap
0x1800048c4  mov     r8, rsi; lpMem
0x1800048c7  xor     edx, edx; dwFlags
0x1800048c9  call    cs:__imp_HeapFree
0x1800048d0  nop     dword ptr [rax+rax+00h]
0x1800048d5  test    eax, eax
0x1800048d7  jz      loc_180005185
0x1800048dd  test    ebx, ebx
0x1800048df  js      loc_18000518F
0x1800048e5  mov     [rbp+57h+phkResult], r14
0x1800048e9  lea     rax, [rbp+57h+phkResult]
0x1800048ed  mov     [rsp+120h+ReturnLength], rax; unsigned int
0x1800048f2  mov     r9d, 20006h; samDesired
0x1800048f8  xor     r8d, r8d; ulOptions
0x1800048fb  mov     rdx, r15; lpSubKey
0x1800048fe  mov     rcx, 0FFFFFFFF80000003h; hKey
0x180004905  call    cs:__imp_RegOpenKeyExW
0x18000490c  nop     dword ptr [rax+rax+00h]
0x180004911  test    eax, eax
0x180004913  jnz     loc_18000510C
0x180004919  mov     [rbp+57h+hKey], r14
0x18000491d  mov     [rsp+120h+lpdwDisposition], r14; lpdwDisposition
0x180004922  lea     rax, [rbp+57h+hKey]
0x180004926  mov     [rsp+120h+var_E8], rax; phkResult
0x18000492b  mov     [rsp+120h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180004930  mov     [rsp+120h+samDesired], 20006h; samDesired
0x180004938  mov     dword ptr [rsp+120h+ReturnLength], 1; unsigned int
0x180004940  xor     r9d, r9d; lpClass
0x180004943  xor     r8d, r8d; Reserved
0x180004946  lea     rdx, SubKey; "Volatile Environment"
0x18000494d  mov     rcx, [rbp+57h+phkResult]; hKey
0x180004951  call    cs:__imp_RegCreateKeyExW
0x180004958  nop     dword ptr [rax+rax+00h]
0x18000495d  test    eax, eax
0x18000495f  jnz     loc_180005138
0x180004965  mov     r12, [rbp+57h+hKey]
0x180004969  mov     rdi, [r13+20h]
0x18000496d  lea     rax, aHomedirectory; "HOMEDIRECTORY"
0x180004974  mov     [rbp+57h+var_50], rax
0x180004978  lea     rax, aProfilepath; "PROFILEPATH"
0x18000497f  mov     [rbp+57h+var_48], rax
0x180004983  cmp     word ptr [rdi], 0
0x180004987  jz      short loc_1800049F7
0x180004989  nop     dword ptr [rax+00000000h]
0x180004990  mov     [rbp+57h+StringSid], 0
0x180004998  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000499f  nop
0x1800049a0  lea     rax, [rax+1]
0x1800049a4  cmp     word ptr [rdi+rax*2], 0
0x1800049a9  jnz     short loc_1800049A0
0x1800049ab  lea     rbx, [rax+1]
0x1800049af  mov     qword ptr [rbp+57h+TokenInformationLength], 0
0x1800049b7  mov     eax, 2
0x1800049bc  mul     rbx
0x1800049bf  mov     rsi, rax
0x1800049c2  test    rdx, rdx
0x1800049c5  jz      loc_180004B25
0x1800049cb  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800049d2  lea     rax, [rax+1]
0x1800049d6  cmp     word ptr [rdi+rax*2], 0
0x1800049db  jnz     short loc_1800049D2
0x1800049dd  lea     rdi, [rdi+rax*2]
0x1800049e1  add     rdi, 2
0x1800049e5  lea     rcx, [rbp+57h+StringSid]
0x1800049e9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800049ee  cmp     word ptr [rdi], 0
0x1800049f2  jnz     short loc_180004990
0x1800049f4  xor     r14d, r14d
0x1800049f7  mov     [rbp+57h+lpMem], r14
0x1800049fb  mov     [rbp+57h+var_A8], 0FFFFFFFFFFFFFFFFh
0x180004a03  mov     [rbp+57h+var_A0], 0FFFFFFFFFFFFFFFFh
0x180004a0b  lea     r8, [rbp+57h+lpMem]
0x180004a0f  mov     rdx, r15
0x180004a12  mov     ecx, 5
0x180004a17  call    cs:__imp_GetBasicProfileFolderPathAlloc
0x180004a1e  nop     dword ptr [rax+rax+00h]
0x180004a23  mov     ebx, eax
0x180004a25  test    eax, eax
0x180004a27  js      loc_180004C23
0x180004a2d  mov     rdi, [rbp+57h+lpMem]
0x180004a31  mov     r9, rdi; unsigned __int16 *
0x180004a34  lea     r8, aUserprofile; "USERPROFILE"
0x180004a3b  xor     edx, edx; unsigned __int16 *
0x180004a3d  mov     rcx, [rbp+57h+hKey]; hKey
0x180004a41  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x180004a46  mov     ebx, eax
0x180004a48  test    eax, eax
0x180004a4a  jns     loc_1800051DE
0x180004a50  mov     rcx, [rbp+5Fh]; this
0x180004a54  mov     r9d, eax; char *
0x180004a57  lea     r8, ?AppPackageAuthority@?1??DaclContainsPackageAndLpacCapabilitySid_@@YAHPEAX@Z@4U_SID_IDENTIFIER_AUTHORITY@@B.SubAuthority; unsigned int
0x180004a5e  mov     edx, 64h ; 'd'; void *
0x180004a63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004a68  mov     rcx, [rbp+5Fh]; this
0x180004a6c  mov     r9d, ebx; char *
0x180004a6f  lea     r8, ?AppPackageAuthority@?1??DaclContainsPackageAndLpacCapabilitySid_@@YAHPEAX@Z@4U_SID_IDENTIFIER_AUTHORITY@@B.SubAuthority; unsigned int
0x180004a76  mov     edx, 33Ch; void *
0x180004a7b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004a80  nop
0x180004a81  mov     rdi, [rbp+57h+lpMem]
0x180004a85  test    rdi, rdi
0x180004a88  jz      short loc_180004AAE
0x180004a8a  call    cs:__imp_GetProcessHeap
0x180004a91  nop     dword ptr [rax+rax+00h]
0x180004a96  mov     rcx, rax; hHeap
0x180004a99  mov     r8, rdi; lpMem
0x180004a9c  xor     edx, edx; dwFlags
0x180004a9e  call    cs:__imp_HeapFree
0x180004aa5  nop     dword ptr [rax+rax+00h]
0x180004aaa  mov     [rbp+57h+lpMem], r14
0x180004aae  mov     [rbp+57h+var_A8], r14
0x180004ab2  mov     [rbp+57h+var_A0], r14
0x180004ab6  mov     rcx, [rbp+57h+hKey]; hKey
0x180004aba  test    rcx, rcx
0x180004abd  jz      short loc_180004ACC
0x180004abf  call    cs:__imp_RegCloseKey
0x180004ac6  nop     dword ptr [rax+rax+00h]
0x180004acb  nop
0x180004acc  mov     rcx, [rbp+57h+phkResult]; hKey
0x180004ad0  test    rcx, rcx
0x180004ad3  jz      short loc_180004AE2
0x180004ad5  call    cs:__imp_RegCloseKey
0x180004adc  nop     dword ptr [rax+rax+00h]
0x180004ae1  nop
0x180004ae2  test    r15, r15
0x180004ae5  jz      short loc_180004B07
0x180004ae7  call    cs:__imp_GetProcessHeap
0x180004aee  nop     dword ptr [rax+rax+00h]
0x180004af3  mov     rcx, rax; hHeap
0x180004af6  mov     r8, r15; lpMem
0x180004af9  xor     edx, edx; dwFlags
0x180004afb  call    cs:__imp_HeapFree
0x180004b02  nop     dword ptr [rax+rax+00h]
0x180004b07  mov     eax, ebx
0x180004b09  mov     rbx, [rsp+120h+arg_18]
0x180004b11  add     rsp, 0F0h
0x180004b18  pop     r15
0x180004b1a  pop     r14
0x180004b1c  pop     r13
0x180004b1e  pop     r12
0x180004b20  pop     rdi
0x180004b21  pop     rsi
0x180004b22  pop     rbp
0x180004b23  retn
0x180004b25  call    cs:__imp_GetProcessHeap
0x180004b2c  nop     dword ptr [rax+rax+00h]
0x180004b31  nop
0x180004b32  mov     rcx, rax; hHeap
0x180004b35  mov     r8, rsi; dwBytes
0x180004b38  mov     edx, 8; dwFlags
0x180004b3d  call    cs:__imp_HeapAlloc
0x180004b44  nop     dword ptr [rax+rax+00h]
0x180004b49  mov     r14, rax
0x180004b4c  test    rax, rax
0x180004b4f  jz      loc_1800049CB
0x180004b55  test    rbx, rbx
0x180004b58  jz      loc_1800051BE
0x180004b5e  cmp     rbx, 7FFFFFFFh
0x180004b65  ja      loc_1800051B8
0x180004b6b  mov     ecx, 7FFFFFFEh
0x180004b70  mov     rdx, rdi
0x180004b73  mov     r8, rax
0x180004b76  test    rcx, rcx
0x180004b79  jz      short loc_180004B98
0x180004b7b  movzx   eax, word ptr [rdx]
0x180004b7e  test    ax, ax
0x180004b81  jz      short loc_180004B98
0x180004b83  add     rdx, 2
0x180004b87  mov     [r8], ax
0x180004b8b  add     r8, 2
0x180004b8f  dec     rcx
0x180004b92  sub     rbx, 1
0x180004b96  jnz     short loc_180004B76
0x180004b98  lea     rcx, [r8-2]
0x180004b9c  test    rbx, rbx
0x180004b9f  cmovnz  rcx, r8
0x180004ba3  xor     eax, eax
0x180004ba5  mov     [rcx], ax
0x180004ba8  test    rbx, rbx
0x180004bab  jz      loc_1800051BE
0x180004bb1  mov     [rbp+57h+StringSid], r14
0x180004bb5  xor     ebx, ebx
0x180004bb7  movzx   eax, word ptr [r14]
0x180004bbb  test    ax, ax
0x180004bbe  jz      short loc_180004BDE
0x180004bc0  mov     rcx, r14
0x180004bc3  cmp     ax, 3Dh ; '='
0x180004bc7  jnz     short loc_180004BD2
0x180004bc9  xor     eax, eax
0x180004bcb  mov     [rcx], ax
0x180004bce  lea     rbx, [rcx+2]
0x180004bd2  add     rcx, 2
0x180004bd6  movzx   eax, word ptr [rcx]
0x180004bd9  test    ax, ax
0x180004bdc  jnz     short loc_180004BC3
0x180004bde  cmp     word ptr [r14], 0
0x180004be3  jz      loc_1800049CB
0x180004be9  test    rbx, rbx
0x180004bec  jz      loc_1800049CB
0x180004bf2  cmp     word ptr [rbx], 0
0x180004bf6  jz      loc_1800049CB
0x180004bfc  xor     esi, esi
0x180004bfe  cmp     esi, 2
  ... truncated ...
```
