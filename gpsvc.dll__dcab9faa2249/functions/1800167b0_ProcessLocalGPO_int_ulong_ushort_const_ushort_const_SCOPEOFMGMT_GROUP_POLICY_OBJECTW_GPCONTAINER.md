# ProcessLocalGPO(int,ulong,ushort const *,ushort const *,_SCOPEOFMGMT *,_GROUP_POLICY_OBJECTW * *,_GPCONTAINER * *)

- ea: `0x1800167b0`
- end: `0x1800183ce`
- name: `?ProcessLocalGPO@@YAHHKPEBG0PEAU_SCOPEOFMGMT@@PEAPEAU_GROUP_POLICY_OBJECTW@@PEAPEAU_GPCONTAINER@@@Z`
- size: `7198`
- prototype: `__int64 __fastcall(__int64, int, const unsigned __int16 *, const unsigned __int16 *, struct _SCOPEOFMGMT *, struct _GROUP_POLICY_OBJECTW **, struct _GPCONTAINER **)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800147b0`

## callees

- `0x180003770`
- `0x1800167b0`
- `0x1800184b4`
- `0x180018ed4`
- `0x18002a5a0`
- `0x18003d630`
- `0x180075ec0`
- `0x18007d320`
- `0x18009c63c`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180016a13`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180016ef3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180016f97`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800176d3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180017866`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180017979`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180016a13`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180016ef3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180016f97`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800176d3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180017866`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180017979`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180016a02`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180016ee2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180016f85`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180016a02`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180016ee2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180016f85`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800169df`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180016ebf`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180016f61`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800169df`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180016ebf`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180016f61`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016c4c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800171c8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001813c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016c4c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800171c8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001813c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016840`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017139`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017258`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001729d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001738c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800173bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017401`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017447`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800174f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017519`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017557`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800176d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017702`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001772a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800177a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800177cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800177ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001786c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017895`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800178b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800178dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001791e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001797f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800179a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800179e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017a3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017a7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017ab8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017afa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017b1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017dc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017f1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017fda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001805c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800180e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018142`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800182f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001836d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800183a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016840`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017139`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017258`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001729d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001738c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800173bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017401`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017447`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800174f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017519`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017557`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800176d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017702`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001772a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800177a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800177cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800177ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001786c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017895`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800178b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800178dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001791e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001797f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800179a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800179e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017a3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017a7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017ab8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017afa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017b1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017dc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017f1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017fda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001805c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800180e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018142`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800182f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001836d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800183a8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001688c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800169bd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180016a28`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180016de0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180016e9d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180016f3f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180016fe4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017302`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017330`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017fae`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001688c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800169bd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180016a28`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180016de0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180016e9d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180016f3f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180016fe4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017302`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017330`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017fae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016c42`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016c5b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016c6e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016c7d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016c8c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016c9b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016caa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016cb9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016e73`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017a03`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017a12`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017f93`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018074`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001815a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800182ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016c42`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016c5b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016c6e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016c7d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016c8c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016c9b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016caa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016cb9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016e73`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017a03`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017a12`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017f93`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018074`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001815a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800182ed`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180016991`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180016991`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180016f27`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180016f27`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180017017`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180017017`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180017025`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180017025`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800168c6`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800168c6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180016e54`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180017498`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180016e54`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180017498`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileIntW` at `0x180016d11`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileIntW` at `0x180016d3d`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileIntW` at `0x180016da2`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileIntW` at `0x180017e83`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileIntW` at `0x180016d11`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileIntW` at `0x180016d3d`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileIntW` at `0x180016da2`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileIntW` at `0x180017e83`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x180016e35`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x180016e35`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180016f09`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180016f09`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180017374`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180017374`

## string_xrefs

- `0x1800169d8`: `gpsvc.dll`
- `0x180016eb8`: `gpsvc.dll`
- `0x180016f5a`: `gpsvc.dll`
- `0x1800168b6`: `%SystemRoot%\System32\GroupPolicy`
- `0x180016df6`: `gPCUserExtensionNames`
- `0x180016dfd`: `gPCMachineExtensionNames`
- `0x1800168bf`: `%SystemRoot%\System32\GroupPolicyUsers`
- `0x1800173eb`: `ProcessLocalGPO:  Failed to allocate memory for GPO path (size = %Iu).`
- `0x1800174de`: `ProcessLocalGPO:  Failed to allocate memory for GPO path (size = %Iu).`
- `0x180017522`: `ProcessLocalGPO:  Failed to expand local gpo path with error %d. Exiting`
- `0x180017560`: `ProcessLocalGPO:  Failed to expand local gpo path with error %d. Exiting`
- `0x18001759c`: `ProcessLocalGPO:  Failed to expand local gpo path with error %d. Exiting`
- `0x1800175d1`: `ProcessLocalGPO:  Failed to expand local gpo path with error %d. Exiting`
- `0x180016c09`: `ProcessLocalGPO: Could not copy SID string %ls (hr=0x%x) to path buffer`
- `0x18001762b`: `ProcessLocalGPO: Could not copy SID string %ls (hr=0x%x) to path buffer`
- `0x180017650`: `ProcessLocalGPO:  Local GPO's gpt.ini is not accessible at %s, assuming default state.`
- `0x180017685`: `ProcessLocalGPO:  Local GPO's gpt.ini is not accessible at %s, assuming default state.`
- `0x1800177d4`: `ProcessLocalGPO:  Failed to copy GPO id to buffer error=0x%x`
- `0x180018376`: `ProcessLocalGPO:  Failed to copy GPO id to buffer error=0x%x`
- `0x1800178e9`: `ProcessLocalGPO: ConvertStringSidToSid() failed (err=0x%x) for SID %ls.`
- `0x18001792b`: `ProcessLocalGPO: ConvertStringSidToSid() failed (err=0x%x) for SID %ls.`
- `0x180017ac5`: `ProcessLocalGPO: LookupAccountSid() failed (err=0x%x), for SID %ls`
- `0x180017b07`: `ProcessLocalGPO: LookupAccountSid() failed (err=0x%x), for SID %ls`
- `0x180017a47`: `ProcessLocalGPO: LookupAccountSid() failed (err=0x%x), but NOT with the expected error code of ERROR_INSUFFICIENT_BUFFER to lookup SID %ls. Invalid SID perhaps?`
- `0x180017a89`: `ProcessLocalGPO: LookupAccountSid() failed (err=0x%x), but NOT with the expected error code of ERROR_INSUFFICIENT_BUFFER to lookup SID %ls. Invalid SID perhaps?`
- `0x180017cec`: `ProcessLocalGPO: Could not copy SID string %ls (hr=0x%x) to GPOId buffer`
- `0x180017d24`: `ProcessLocalGPO: Could not copy SID string %ls (hr=0x%x) to GPOId buffer`
- `0x180017e1a`: `ProcessLocalGPO:  GPO %s was created by an old version of the Group Policy Editor.  It will be skipped.`
- `0x180017e4f`: `ProcessLocalGPO:  GPO %s was created by an old version of the Group Policy Editor.  It will be skipped.`
- `0x180018014`: `ProcessLocalGPO: No client side extensions are configured.`
- `0x180018046`: `ProcessLocalGPO: No client side extensions are configured.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ProcessLocalGPO(
        __int64 a1,
        int a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        struct _SCOPEOFMGMT *a5,
        struct _GROUP_POLICY_OBJECTW **a6,
        struct _GPCONTAINER **a7)
{
  WCHAR *v8; // rdi
  unsigned __int16 *v9; // rsi
  unsigned __int16 *v10; // r13
  HLOCAL v11; // r14
  unsigned __int16 *v12; // r15
  DWORD LastError; // r12d
  __int64 v14; // rax
  WCHAR *v15; // rbx
  const WCHAR *v16; // rcx
  DWORD v17; // eax
  const unsigned __int16 *v18; // rdx
  __int64 v19; // rax
  WCHAR *v20; // r8
  __int64 v21; // rax
  unsigned __int64 v22; // r9
  __int64 v23; // rcx
  int v24; // r10d
  unsigned __int16 v25; // ax
  HMODULE Library; // rax
  HMODULE v27; // rbx
  __int64 v28; // rbx
  __int64 v29; // rcx
  const wchar_t *v30; // rdx
  unsigned __int64 v31; // r8
  unsigned __int16 *v32; // r9
  int v33; // r10d
  wchar_t v34; // ax
  __int64 v35; // rax
  WCHAR *v36; // rbx
  __int64 v37; // rax
  unsigned __int64 v38; // r10
  __int64 v39; // rcx
  const wchar_t *v40; // rdx
  __int64 v41; // r8
  WCHAR *v42; // r9
  int v43; // r11d
  wchar_t v44; // ax
  int v45; // edx
  int v46; // r9d
  __int64 v47; // r8
  const wchar_t *v48; // rcx
  wchar_t v49; // ax
  char PrivateProfileIntW; // cl
  UINT v52; // eax
  int v53; // ecx
  WCHAR *v54; // rcx
  const WCHAR *v55; // rax
  DWORD i; // eax
  HMODULE v57; // rax
  HMODULE v58; // rbx
  PSID v59; // rbx
  HMODULE v60; // rax
  __int64 v61; // rax
  __int64 v62; // rcx
  unsigned __int16 *v63; // rax
  int v64; // eax
  PUCHAR SidSubAuthorityCount; // rax
  DWORD v66; // ebx
  __int64 v67; // rax
  int v68; // eax
  unsigned __int16 *v69; // r8
  __int64 v70; // rcx
  unsigned __int64 v71; // r11
  __int64 v72; // rcx
  const unsigned __int16 *v73; // rbx
  const unsigned __int16 *v74; // rdx
  int v75; // r10d
  unsigned __int16 v76; // ax
  int v77; // ebx
  struct _GPLINK *v78; // rcx
  struct _SCOPEOFMGMT *v79; // rdx
  DWORD v80; // ebx
  __int64 v81; // rcx
  _QWORD *v82; // rdx
  const wchar_t *v83; // rcx
  wchar_t v84; // ax
  DWORD v85; // eax
  WCHAR *v86; // rax
  void *v87; // rax
  void (*v88)(unsigned int, const unsigned __int16 *, ...); // rbx
  DWORD v89; // eax
  DWORD v90; // eax
  void (*v91)(unsigned int, const unsigned __int16 *, ...); // rbx
  DWORD v92; // eax
  void (*v93)(unsigned int, const unsigned __int16 *, ...); // rbx
  DWORD v94; // eax
  void (*v95)(unsigned int, const unsigned __int16 *, ...); // rbx
  DWORD v96; // eax
  void (*v97)(unsigned int, const unsigned __int16 *, ...); // rbx
  DWORD v98; // eax
  DWORD v99; // eax
  void (*v100)(unsigned int, const unsigned __int16 *, ...); // rbx
  DWORD v101; // eax
  DWORD v102; // eax
  void (*v103)(unsigned int, const unsigned __int16 *, ...); // rbx
  DWORD v104; // eax
  DWORD v105; // eax
  void (*v106)(unsigned int, const unsigned __int16 *, ...); // rbx
  DWORD v107; // eax
  DWORD v108; // eax
  DWORD v109; // eax
  void (*v110)(unsigned int, const unsigned __int16 *, ...); // rax
  const unsigned __int16 *v111; // rdx
  WCHAR *v112; // rax
  DWORD v113; // eax
  DWORD v114; // eax
  DWORD nSize[2]; // [rsp+20h] [rbp-110h]
  LPCWSTR v116; // [rsp+28h] [rbp-108h]
  __int64 v117; // [rsp+60h] [rbp-D0h]
  int v118; // [rsp+68h] [rbp-C8h]
  int v119; // [rsp+98h] [rbp-98h]
  const WCHAR *lpFileName; // [rsp+B0h] [rbp-80h]
  int StringSida; // [rsp+C0h] [rbp-70h]
  const WCHAR *StringSidb; // [rsp+C0h] [rbp-70h]
  int v124; // [rsp+C8h] [rbp-68h]
  int j; // [rsp+C8h] [rbp-68h]
  unsigned __int64 lpString1; // [rsp+D0h] [rbp-60h]
  WCHAR *lpString1a; // [rsp+D0h] [rbp-60h]
  HMODULE hLibModule; // [rsp+D8h] [rbp-58h]
  HMODULE hLibModulea; // [rsp+D8h] [rbp-58h]
  HMODULE hLibModuleb; // [rsp+D8h] [rbp-58h]
  WCHAR *hLibModulec; // [rsp+D8h] [rbp-58h]
  DWORD cchReferencedDomainName; // [rsp+E0h] [rbp-50h] BYREF
  DWORD cchName; // [rsp+E4h] [rbp-4Ch] BYREF
  int v134; // [rsp+E8h] [rbp-48h]
  int v135; // [rsp+ECh] [rbp-44h]
  int v136; // [rsp+F0h] [rbp-40h]
  int v137; // [rsp+F4h] [rbp-3Ch]
  unsigned int v138; // [rsp+F8h] [rbp-38h]
  unsigned __int64 v139; // [rsp+100h] [rbp-30h]
  int v140; // [rsp+108h] [rbp-28h]
  __int64 v141; // [rsp+110h] [rbp-20h]
  enum _SID_NAME_USE peUse; // [rsp+118h] [rbp-18h] BYREF
  HLOCAL v143; // [rsp+120h] [rbp-10h]
  PSID Sid; // [rsp+128h] [rbp-8h] BYREF
  WCHAR *v145; // [rsp+130h] [rbp+0h]
  struct _SCOPEOFMGMT *v146; // [rsp+138h] [rbp+8h]
  HLOCAL hMem; // [rsp+140h] [rbp+10h]
  WCHAR *v148; // [rsp+148h] [rbp+18h]
  unsigned __int16 *v149; // [rsp+150h] [rbp+20h]
  unsigned __int16 *v150; // [rsp+158h] [rbp+28h]
  unsigned __int16 *v151; // [rsp+160h] [rbp+30h]
  struct _GPCONTAINER **v152; // [rsp+168h] [rbp+38h]
  int v153[2]; // [rsp+170h] [rbp+40h]
  _OWORD FileInformation[2]; // [rsp+178h] [rbp+48h] BYREF
  int v155; // [rsp+198h] [rbp+68h]

  v136 = a2;
  v146 = a5;
  *(_QWORD *)v153 = a6;
  v152 = a7;
  v8 = 0;
  v148 = 0;
  v9 = 0;
  v149 = 0;
  v10 = 0;
  v151 = 0;
  v11 = 0;
  v145 = 0;
  v143 = 0;
  v12 = 0;
  v150 = 0;
  cchName = 0;
  cchReferencedDomainName = 0;
  memset(FileInformation, 0, sizeof(FileInformation));
  v155 = 0;
  LastError = GetLastError();
  v138 = 0;
  hMem = 0;
  peUse = SidTypeUnknown;
  if ( a3 )
  {
    v14 = -1;
    do
      ++v14;
    while ( a3[v14] );
    lpString1 = v14 + 10;
  }
  else
  {
    lpString1 = 9;
  }
  v15 = (WCHAR *)LocalAlloc(0x40u, 0x208u);
  lpFileName = v15;
  if ( !v15 )
  {
    LastError = GetLastError();
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"ProcessLocalGPO:  Failed to allocate memory for GPO path (size = %Iu).", 520);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"ProcessLocalGPO:  Failed to allocate memory for GPO path (size = %Iu).", 520);
      }
    }
    goto LABEL_69;
  }
  v141 = 260;
  v16 = L"%SystemRoot%\\System32\\GroupPolicy";
  if ( a3 )
    v16 = L"%SystemRoot%\\System32\\GroupPolicyUsers";
  v17 = ExpandEnvironmentStringsW(v16, v15, 0x104u);
  if ( !v17 )
  {
    LastError = GetLastError();
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      v88 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        v89 = GetLastError();
        v88(2u, L"ProcessLocalGPO:  Failed to expand local gpo path with error %d. Exiting", v89);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        v90 = GetLastError();
        RedirectDebugMsg(2u, L"ProcessLocalGPO:  Failed to expand local gpo path with error %d. Exiting", v90);
      }
      goto LABEL_68;
    }
    goto LABEL_69;
  }
  if ( v17 > 0x104 )
  {
    LastError = 122;
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"ProcessLocalGPO:  Failed to expand local gpo path with error %d. Exiting", 122);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"ProcessLocalGPO:  Failed to expand local gpo path with error %d. Exiting", 122);
      }
    }
    goto LABEL_69;
  }
  v18 = a3;
  if ( a3 )
  {
    v19 = -1;
    do
      ++v19;
    while ( v15[v19] );
    v20 = &v15[v19];
    if ( *(v20 - 1) != 92 )
    {
      *v20++ = 92;
      *v20 = 0;
    }
    v21 = v20 - v15;
    v22 = 260 - v21;
    if ( v21 == 260 )
    {
      v24 = -2147024809;
      if ( !v22 )
        goto LABEL_62;
    }
    else
    {
      if ( v22 <= 0x7FFFFFFF )
      {
        v23 = 2147483646;
        v24 = 0;
        while ( v23 )
        {
          v25 = *v18;
          if ( !*v18 )
          {
            if ( !v22 )
            {
LABEL_21:
              --v20;
              v24 = -2147024774;
              break;
            }
            break;
          }
          ++v18;
          *v20++ = v25;
          --v23;
          if ( !--v22 )
            goto LABEL_21;
        }
        *v20 = 0;
        if ( v24 >= 0 )
          goto LABEL_24;
        v18 = a3;
LABEL_62:
        LastError = 122;
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(
              2u,
              L"ProcessLocalGPO: Could not copy SID string %ls (hr=0x%x) to path buffer",
              v18,
              (unsigned int)v24);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(
              2u,
              L"ProcessLocalGPO: Could not copy SID string %ls (hr=0x%x) to path buffer",
              v18,
              (unsigned int)v24);
          }
        }
        goto LABEL_69;
      }
      v24 = -2147024809;
    }
    *v20 = 0;
    goto LABEL_62;
  }
LABEL_24:
  if ( GetFileAttributesExW(v15, GetFileExInfoStandard, FileInformation) && (FileInformation[0] & 0x10) != 0 )
  {
    v134 = 1;
  }
  else
  {
    v134 = 0;
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"ProcessLocalGPO:  Local GPO's gpt.ini is not accessible at %s, assuming default state.", v15);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(
          4u,
          L"ProcessLocalGPO:  Local GPO's gpt.ini is not accessible at %s, assuming default state.",
          v15);
      }
    }
  }
  v8 = (WCHAR *)LocalAlloc(0x40u, 0x64u);
  v148 = v8;
  if ( v8 )
  {
    Library = LoadLibraryExW(L"gpsvc.dll", 0, 0);
    v27 = Library;
    if ( Library )
    {
      if ( LoadStringW(Library, 0x67u, v8, 50) )
      {
        FreeLibrary(v27);
        v28 = 2 * lpString1;
        v9 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * lpString1);
        v149 = v9;
        if ( !v9 )
        {
          LastError = GetLastError();
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(2u, L"ProcessLocalGPO:  Failed to allocate memory for GPO id (size = %Iu).", v28);
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(2u, L"ProcessLocalGPO:  Failed to allocate memory for GPO id (size = %Iu).", v28);
            }
          }
          goto LABEL_68;
        }
        if ( lpString1 )
        {
          if ( lpString1 > 0x7FFFFFFF )
          {
            *v9 = 0;
          }
          else
          {
            v29 = 2147483646;
            v30 = L"LocalGPO";
            v31 = lpString1;
            v32 = v9;
            v33 = 0;
            while ( v29 )
            {
              v34 = *v30;
              if ( !*v30 )
                break;
              ++v30;
              *v32++ = v34;
              --v29;
              if ( !--v31 )
              {
                --v32;
                v33 = -2147024774;
                break;
              }
            }
            *v32 = 0;
            if ( v33 >= 0 )
            {
              if ( !a3 )
              {
                hLibModule = (HMODULE)v8;
LABEL_40:
                v35 = -1;
                do
                  ++v35;
                while ( lpFileName[v35] );
                v36 = (WCHAR *)&lpFileName[v35];
                if ( *(v36 - 1) != 92 )
                {
                  *v36++ = 92;
                  *v36 = 0;
                }
                v37 = v36 - lpFileName;
                v38 = 260 - v37;
                v139 = 260 - v37;
                if ( v37 != 260 )
                {
                  if ( v38 > 0x7FFFFFFF )
                  {
                    *v36 = 0;
                  }
                  else
                  {
                    v39 = 2147483646;
                    v40 = L"gpt.ini";
                    v41 = 260 - v37;
                    v42 = v36;
                    v43 = 0;
                    while ( v39 )
                    {
                      v44 = *v40;
                      if ( !*v40 )
                      {
                        if ( !v41 )
                        {
LABEL_50:
                          --v42;
                          v43 = -2147024774;
                          break;
                        }
                        break;
                      }
                      ++v40;
                      *v42++ = v44;
                      --v39;
                      if ( !--v41 )
                        goto LABEL_50;
                    }
                    v45 = 0;
                    *v42 = 0;
                    if ( v43 >= 0 )
                    {
                      v140 = 0;
                      v137 = 0;
                      v46 = v134;
                      if ( !v134 )
                      {
                        lpString1a = 0;
                        v124 = 0;
                        v135 = 1;
LABEL_55:
                        v47 = 2147483646;
                        if ( (v136 & 1) != 0 )
                        {
                          v83 = L"Machine";
                          while ( v47 )
                          {
                            v84 = *v83;
                            if ( !*v83 )
                            {
                              if ( !v38 )
                              {
LABEL_60:
                                --v36;
                                v45 = -2147024774;
                                break;
                              }
                              break;
                            }
                            ++v83;
                            *v36++ = v84;
                            --v47;
                            if ( !--v38 )
                              goto LABEL_60;
                          }
                        }
                        else
                        {
                          v48 = L"User";
                          while ( v47 )
                          {
                            v49 = *v48;
                            if ( !*v48 )
                            {
                              if ( !v38 )
                                goto LABEL_60;
                              break;
                            }
                            ++v48;
                            *v36++ = v49;
                            --v47;
                            if ( !--v38 )
                              goto LABEL_60;
                          }
                        }
                        *v36 = 0;
                        if ( v45 < 0 )
                        {
                          LastError = (unsigned __int16)v45;
LABEL_68:
                          v15 = (WCHAR *)lpFileName;
                          goto LABEL_69;
                        }
                        v77 = 1;
                        if ( v146 && v46 )
                        {
                          v78 = AllocGpLink(v9, 0);
                          if ( !v78 )
                          {
                            LastError = GetLastError();
                            if ( lpString1a )
                              LocalFree(lpString1a);
                            if ( !*(_DWORD *)&g_dwDebugLevel )
                              goto LABEL_68;
                            v110 = g_lpDebugMsg;
                            if ( !g_lpDebugMsg )
                            {
                              if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                                RedirectDebugMsg(2u, L"ProcessLocalGPO: Failed to log Rsop data.");
                              goto LABEL_68;
                            }
                            v111 = L"ProcessLocalGPO: Failed to log Rsop data.";
                            goto LABEL_321;
                          }
                          v79 = v146;
                          *((_QWORD *)v78 + 2) = *((_QWORD *)v146 + 3);
                          *((_QWORD *)v79 + 3) = v78;
                          v80 = GetLastError();
                          v81 = AllocGpContainer(
                                  v136,
                                  1,
                                  1,
                                  v137,
                                  v124,
                                  v9,
                                  (__int64)lpFileName,
                                  (__int64)hLibModule,
                                  (__int64)v8,
                                  0,
                                  0,
                                  1,
                                  0,
                                  (__int64)L"Local",
                                  0,
                                  (__int64)lpString1a);
                          if ( !v81 )
                          {
                            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_GpupdateCrash_gptmodify>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_GpupdateCrash_gptmodify>::GetImpl'::`2'::impl) )
                              v80 = GetLastError();
                            if ( *(_DWORD *)&g_dwDebugLevel )
                            {
                              if ( g_lpDebugMsg )
                              {
                                g_lpDebugMsg(4u, L"AddGPO: Failed to allocate memory for Gp Container.");
                              }
                              else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                              {
                                RedirectDebugMsg(4u, L"AddGPO: Failed to allocate memory for Gp Container.");
                              }
                            }
                            SetLastError(v80);
                            LastError = GetLastError();
                            if ( lpString1a )
                              LocalFree(lpString1a);
                            if ( !*(_DWORD *)&g_dwDebugLevel )
                              goto LABEL_68;
                            v110 = g_lpDebugMsg;
                            if ( !g_lpDebugMsg )
                            {
                              if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                                RedirectDebugMsg(2u, L"ProcessLocalGPO:  Failed to log Rsop data.");
                              goto LABEL_68;
                            }
                            v111 = L"ProcessLocalGPO:  Failed to log Rsop data.";
                            goto LABEL_321;
                          }
                          v82 = v152;
                          *(_QWORD *)(v81 + 112) = *v152;
                          *v82 = v81;
                          SetLastError(v80);
                          v77 = 1;
                          if ( *(_DWORD *)&g_dwDebugLevel )
                          {
                            if ( g_lpDebugMsg )
                            {
                              g_lpDebugMsg(4u, L"ProcessLocalGPO:  Added Local GPO to RSOP list.");
                            }
                            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                            {
                              RedirectDebugMsg(4u, L"ProcessLocalGPO:  Added Local GPO to RSOP list.");
                            }
                          }
                        }
                        if ( !v140 && !v137 && !v135 )
                        {
                          if ( *(_DWORD *)&g_dwDebugLevel )
                          {
                            if ( g_lpDebugMsg )
                            {
                              g_lpDebugMsg(4u, L"ProcessLocalGPO:  Added Local GPO to GPO List.");
                            }
                            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                            {
                              RedirectDebugMsg(4u, L"ProcessLocalGPO:  Added Local GPO to GPO List.");
                            }
                          }
                          v77 = AddGPO(
                                  v153[0],
                                  v136,
                                  v47,
                                  v46,
                                  nSize[0],
                                  0,
                                  v124,
                                  v9,
                                  (__int64)lpFileName,
                                  (__int64)hLibModule,
                                  (__int64)v8,
                                  lpString1a,
                                  v117,
                                  v118,
                                  1,
                                  (__int64)L"Local",
                                  0,
                                  1,
                                  0,
                                  v119,
                                  1);
                        }
                        if ( lpString1a )
                          LocalFree(lpString1a);
                        if ( v77 )
                        {
                          v138 = 1;
                          goto LABEL_68;
                        }
                        LastError = GetLastError();
                        if ( !*(_DWORD *)&g_dwDebugLevel )
                          goto LABEL_68;
                        v110 = g_lpDebugMsg;
                        if ( !g_lpDebugMsg )
                        {
                          if ( g_lpDebugMsgContextInstance && (char *)g_lpDebugMsgContext != (char *)g_lpDebugMsg )
                            RedirectDebugMsg(
                              2u,
                              L"ProcessLocalGPO:  Failed to add local group policy object to the list.");
                          goto LABEL_68;
                        }
                        v111 = L"ProcessLocalGPO:  Failed to add local group policy object to the list.";
LABEL_321:
                        v110(2u, v111);
                        goto LABEL_68;
                      }
                      v135 = 0;
                      if ( GetPrivateProfileIntW(L"General", L"gPCFunctionalityVersion", 2, lpFileName) < 2 )
                      {
                        v140 = 1;
                        if ( *(_DWORD *)&g_dwDebugLevel )
                        {
                          if ( g_lpDebugMsg )
                          {
                            g_lpDebugMsg(
                              4u,
                              L"ProcessLocalGPO:  GPO %s was created by an old version of the Group Policy Editor.  It will be skipped.",
                              v8);
                          }
                          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                          {
                            RedirectDebugMsg(
                              4u,
                              L"ProcessLocalGPO:  GPO %s was created by an old version of the Group Policy Editor.  It will be skipped.",
                              v8);
                          }
                        }
                      }
                      PrivateProfileIntW = GetPrivateProfileIntW(L"General", L"Options", a3 != 0 ? 2 : 0, lpFileName);
                      StringSida = v136 & 1;
                      if ( (v136 & 1) != 0 )
                      {
                        if ( (PrivateProfileIntW & 2) == 0 )
                        {
                          LOWORD(v52) = GetPrivateProfileIntW(L"General", L"Version", 0, lpFileName);
                          goto LABEL_94;
                        }
                      }
                      else if ( (PrivateProfileIntW & 1) == 0 )
                      {
                        goto LABEL_93;
                      }
                      v137 = 1;
                      if ( *(_DWORD *)&g_dwDebugLevel )
                      {
                        if ( g_lpDebugMsg )
                        {
                          g_lpDebugMsg(4u, L"ProcessLocalGPO:  GPO %s is disabled.  It will be skipped.", v8);
                        }
                        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                        {
                          RedirectDebugMsg(4u, L"ProcessLocalGPO:  GPO %s is disabled.  It will be skipped.", v8);
                        }
                      }
LABEL_93:
                      v52 = GetPrivateProfileIntW(L"General", L"Version", 0, lpFileName);
                      if ( !StringSida )
                      {
                        v53 = HIWORD(v52);
                        v52 &= 0xFFFF0000;
                        goto LABEL_95;
                      }
LABEL_94:
                      v52 = (unsigned __int16)v52;
                      v53 = (unsigned __int16)v52 << 16;
LABEL_95:
                      v124 = v52 | v53;
                      if ( !(v52 | v53) )
                      {
                        v135 = 1;
                        if ( *(_DWORD *)&g_dwDebugLevel )
                        {
                          if ( g_lpDebugMsg )
                          {
                            g_lpDebugMsg(
                              4u,
                              L"ProcessLocalGPO:  GPO %s doesn't contain any data since the version number is 0.  It will be skipped.",
                              v8);
                          }
                          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                          {
                            RedirectDebugMsg(
                              4u,
                              L"ProcessLocalGPO:  GPO %s doesn't contain any data since the version number is 0.  It will be skipped.",
                              v8);
                          }
                        }
                      }
                      v54 = (WCHAR *)LocalAlloc(0x40u, 0x208u);
                      lpString1a = v54;
                      if ( v54 )
                      {
                        v55 = L"gPCMachineExtensionNames";
                        if ( !StringSida )
                          v55 = L"gPCUserExtensionNames";
                        StringSidb = v55;
                        for ( i = GetPrivateProfileStringW(L"General", v55, &DomainName, v54, 0x104u, lpFileName);
                              ;
                              i = GetPrivateProfileStringW(L"General", StringSidb, &DomainName, v112, v141, lpFileName) )
                        {
                          if ( i != (_DWORD)v141 - 1 )
                          {
                            if ( lstrcmpiW(lpString1a, &DomainName) && lstrcmpiW(lpString1a, L" ") )
                            {
                              v45 = 0;
                            }
                            else
                            {
                              if ( *(_DWORD *)&g_dwDebugLevel )
                              {
                                if ( g_lpDebugMsg )
                                {
                                  g_lpDebugMsg(4u, L"ProcessLocalGPO: No client side extensions are configured.");
                                }
                                else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                                {
                                  RedirectDebugMsg(4u, L"ProcessLocalGPO: No client side extensions are configured.");
                                }
                              }
                              LocalFree(lpString1a);
                              v45 = 0;
                              lpString1a = 0;
                              v135 = 1;
                            }
                            v46 = v134;
                            v38 = v139;
                            goto LABEL_55;
                          }
                          LocalFree(lpString1a);
                          v141 = (unsigned int)(2 * v141);
                          v112 = (WCHAR *)LocalAlloc(0x40u, 2LL * (unsigned int)v141);
                          lpString1a = v112;
                          if ( !v112 )
                            break;
                        }
                        LastError = GetLastError();
                        if ( !*(_DWORD *)&g_dwDebugLevel )
                          goto LABEL_68;
                        v110 = g_lpDebugMsg;
                        if ( g_lpDebugMsg )
                        {
LABEL_319:
                          v111 = L"ProcessLocalGPO:  Failed to allocate memory.";
                          goto LABEL_321;
                        }
                      }
                      else
                      {
                        LastError = GetLastError();
                        if ( !*(_DWORD *)&g_dwDebugLevel )
                          goto LABEL_68;
                        v110 = g_lpDebugMsg;
                        if ( g_lpDebugMsg )
                          goto LABEL_319;
                      }
                      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                        RedirectDebugMsg(2u, L"ProcessLocalGPO:  Failed to allocate memory.");
                      goto LABEL_68;
                    }
                  }
                }
                LastError = 122;
                goto LABEL_68;
              }
              v12 = (unsigned __int16 *)LocalAlloc(0x40u, 0x90u);
              v150 = v12;
              if ( !v12 )
              {
                LastError = GetLastError();
                if ( *(_DWORD *)&g_dwDebugLevel )
                {
                  if ( g_lpDebugMsg )
                  {
                    g_lpDebugMsg(
                      2u,
                      L"ProcessLocalGPO:  Failed to allocate memory for GPO display name Format String (size = %Iu).",
                      144);
                  }
                  else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                  {
                    RedirectDebugMsg(
                      2u,
                      L"ProcessLocalGPO:  Failed to allocate memory for GPO display name Format String (size = %Iu).",
                      144);
                  }
                }
                goto LABEL_68;
              }
              v57 = LoadLibraryExW(L"gpsvc.dll", 0, 0);
              v58 = v57;
              if ( v57 )
              {
                if ( LoadStringW(v57, 0x70u, v12, 72) )
                {
                  FreeLibrary(v58);
                  Sid = 0;
                  if ( !ConvertStringSidToSidW(a3, &Sid) )
                  {
                    LastError = GetLastError();
                    if ( *(_DWORD *)&g_dwDebugLevel )
                    {
                      v97 = g_lpDebugMsg;
                      if ( g_lpDebugMsg )
                      {
                        v98 = GetLastError();
                        v97(2u, L"ProcessLocalGPO: ConvertStringSidToSid() failed (err=0x%x) for SID %ls.", v98, a3);
                      }
                      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                      {
                        v99 = GetLastError();
                        RedirectDebugMsg(
                          2u,
                          L"ProcessLocalGPO: ConvertStringSidToSid() failed (err=0x%x) for SID %ls.",
                          v99,
                          a3);
                      }
                    }
                    goto LABEL_68;
                  }
                  v59 = Sid;
                  hMem = Sid;
                  if ( !IsWellKnownSid(Sid, WinBuiltinUsersSid) )
                  {
                    v85 = 32;
                    cchName = 32;
                    cchReferencedDomainName = 128;
                    for ( j = 0; ; ++j )
                    {
                      v86 = (WCHAR *)LocalAlloc(0x40u, 2LL * v85);
                      hLibModulec = v86;
                      if ( v11 )
                      {
                        LocalFree(v11);
                        v86 = hLibModulec;
                      }
                      v11 = v86;
                      v145 = v86;
                      if ( !v86 )
                        break;
                      v87 = LocalAlloc(0x40u, 2LL * cchReferencedDomainName);
                      v139 = (unsigned __int64)v87;
                      if ( v143 )
                      {
                        LocalFree(v143);
                        v87 = (void *)v139;
                      }
                      v143 = v87;
                      if ( !v87 )
                      {
                        LastError = GetLastError();
                        if ( *(_DWORD *)&g_dwDebugLevel )
                        {
                          if ( g_lpDebugMsg )
                          {
                            g_lpDebugMsg(
                              2u,
                              L"ProcessLocalGPO:  Failed to allocate memory for domain name (size = %Iu).",
                              2LL * cchReferencedDomainName);
                          }
                          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                          {
                            RedirectDebugMsg(
                              2u,
                              L"ProcessLocalGPO:  Failed to allocate memory for domain name (size = %Iu).",
                              2LL * cchReferencedDomainName);
                          }
                        }
                        goto LABEL_68;
                      }
                      if ( LookupAccountSidLocalW(
                             v59,
                             hLibModulec,
                             &cchName,
                             (LPWSTR)v87,
                             &cchReferencedDomainName,
                             &peUse) )
                      {
                        goto LABEL_115;
                      }
                      if ( j == 1 )
                      {
                        if ( *(_DWORD *)&g_dwDebugLevel )
                        {
                          v106 = g_lpDebugMsg;
                          if ( g_lpDebugMsg )
                          {
                            v107 = GetLastError();
                            v106(2u, L"ProcessLocalGPO: LookupAccountSid() failed (err=0x%x), for SID %ls", v107, a3);
                          }
                          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                          {
                            v108 = GetLastError();
                            RedirectDebugMsg(
                              2u,
                              L"ProcessLocalGPO: LookupAccountSid() failed (err=0x%x), for SID %ls",
                              v108,
                              a3);
                          }
                        }
                        goto LABEL_68;
                      }
                      if ( GetLastError() != 122 )
                      {
                        if ( *(_DWORD *)&g_dwDebugLevel )
                        {
                          v103 = g_lpDebugMsg;
                          if ( g_lpDebugMsg )
                          {
                            v104 = GetLastError();
                            v103(
                              2u,
                              L"ProcessLocalGPO: LookupAccountSid() failed (err=0x%x), but NOT with the expected error cod"
                               "e of ERROR_INSUFFICIENT_BUFFER to lookup SID %ls. Invalid SID perhaps?",
                              v104,
                              a3);
                          }
                          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                          {
                            v105 = GetLastError();
                            RedirectDebugMsg(
                              2u,
                              L"ProcessLocalGPO: LookupAccountSid() failed (err=0x%x), but NOT with the expected error cod"
                               "e of ERROR_INSUFFICIENT_BUFFER to lookup SID %ls. Invalid SID perhaps?",
                              v105,
                              a3);
                          }
                        }
                        goto LABEL_68;
                      }
                      v85 = cchName;
                    }
                    LastError = GetLastError();
                    if ( *(_DWORD *)&g_dwDebugLevel )
                    {
                      if ( g_lpDebugMsg )
                      {
                        g_lpDebugMsg(
                          2u,
                          L"ProcessLocalGPO:  Failed to allocate memory for account name (size = %Iu).",
                          2LL * cchName);
                      }
                      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                      {
                        RedirectDebugMsg(
                          2u,
                          L"ProcessLocalGPO:  Failed to allocate memory for account name (size = %Iu).",
                          2LL * cchName);
                      }
                    }
                    goto LABEL_68;
                  }
                  v11 = LocalAlloc(0x40u, 0xC8u);
                  v145 = (WCHAR *)v11;
                  if ( !v11 )
                  {
                    LastError = GetLastError();
                    if ( *(_DWORD *)&g_dwDebugLevel )
                    {
                      if ( g_lpDebugMsg )
                      {
                        g_lpDebugMsg(
                          2u,
                          L"ProcessLocalGPO:  Failed to allocate memory for Users group display name (size = %Iu).",
                          200);
                      }
                      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                      {
                        RedirectDebugMsg(
                          2u,
                          L"ProcessLocalGPO:  Failed to allocate memory for Users group display name (size = %Iu).",
                          200);
                      }
                    }
                    goto LABEL_68;
                  }
                  v60 = LoadLibraryExW(L"gpsvc.dll", 0, 0);
                  hLibModulea = v60;
                  if ( v60 )
                  {
                    if ( LoadStringW(v60, 0x71u, (LPWSTR)v11, 100) )
                    {
                      FreeLibrary(hLibModulea);
LABEL_115:
                      v61 = -1;
                      v62 = -1;
                      do
                        ++v62;
                      while ( *((_WORD *)v11 + v62) );
                      do
                        ++v61;
                      while ( v12[v61] );
                      v139 = v62 + v61 + 1;
                      hLibModuleb = (HMODULE)(2 * v139);
                      v63 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v139);
                      v10 = v63;
                      v151 = v63;
                      if ( !v63 )
                      {
                        LastError = GetLastError();
                        if ( *(_DWORD *)&g_dwDebugLevel )
                        {
                          if ( g_lpDebugMsg )
                          {
                            g_lpDebugMsg(
                              2u,
                              L"ProcessLocalGPO:  Failed to allocate memory for user/group display name (size = %Iu).",
                              hLibModuleb);
                          }
                          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                          {
                            RedirectDebugMsg(
                              2u,
                              L"ProcessLocalGPO:  Failed to allocate memory for user/group display name (size = %Iu).",
                              hLibModuleb);
                          }
                        }
                        goto LABEL_68;
                      }
                      v64 = StringCchPrintfW(v63, v139, v12, v11);
                      if ( v64 < 0 )
                      {
                        LastError = (unsigned __int16)v64;
                        if ( *(_DWORD *)&g_dwDebugLevel )
                        {
                          if ( g_lpDebugMsg )
                          {
                            g_lpDebugMsg(
                              2u,
                              L"ProcessLocalGPO: StringCcchPrintf failed with hr=0x%x for format string=%ls, account name=%ls",
                              (unsigned int)v64,
                              v12,
                              v11);
                          }
                          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                          {
                            RedirectDebugMsg(
                              2u,
                              L"ProcessLocalGPO: StringCcchPrintf failed with hr=0x%x for format string=%ls, account name=%ls",
                              (unsigned int)v64,
                              v12,
                              v11);
                          }
                        }
                        goto LABEL_68;
                      }
                      SidSubAuthorityCount = GetSidSubAuthorityCount(v59);
                      v66 = *GetSidSubAuthority(v59, (unsigned int)*SidSubAuthorityCount - 1);
                      v67 = -1;
                      do
                        ++v67;
                      while ( v8[v67] );
                      v68 = StringCchPrintfW(&v8[v67], 50 - v67, L"-%lu", v66);
                      if ( v68 < 0 )
                      {
                        LastError = 122;
                        if ( *(_DWORD *)&g_dwDebugLevel )
                        {
                          if ( g_lpDebugMsg )
                          {
                            LODWORD(v116) = 50;
                            nSize[0] = v68;
                            g_lpDebugMsg(
                              2u,
                              L"ProcessLocalGPO: Could not append RID %lu to string %ls (hr=0x%x) of size=%d chars",
                              v66,
                              v8,
                              *(_QWORD *)nSize,
                              v116);
                          }
                          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                          {
                            LODWORD(v116) = 50;
                            nSize[0] = v68;
                            RedirectDebugMsg(
                              2u,
                              L"ProcessLocalGPO: Could not append RID %lu to string %ls (hr=0x%x) of size=%d chars",
                              v66,
                              v8,
                              *(_QWORD *)nSize,
                              v116);
                          }
                        }
                        goto LABEL_68;
                      }
                      v69 = CheckSlash(v9);
                      *(v69 - 1) = 45;
                      v70 = v69 - v9;
                      v71 = lpString1 - v70;
                      if ( lpString1 == v70 )
                      {
                        v75 = -2147024809;
                        if ( !v71 )
                        {
LABEL_283:
                          v73 = a3;
                          goto LABEL_284;
                        }
                      }
                      else
                      {
                        if ( v71 <= 0x7FFFFFFF )
                        {
                          v72 = 2147483646;
                          v73 = a3;
                          v74 = a3;
                          v75 = 0;
                          while ( v72 )
                          {
                            v76 = *v74;
                            if ( !*v74 )
                            {
                              if ( !v71 )
                              {
LABEL_129:
                                --v69;
                                v75 = -2147024774;
                                break;
                              }
                              break;
                            }
                            ++v74;
                            *v69++ = v76;
                            --v72;
                            if ( !--v71 )
                              goto LABEL_129;
                          }
                          *v69 = 0;
                          if ( v75 >= 0 )
                          {
                            hLibModule = (HMODULE)v10;
                            goto LABEL_40;
                          }
LABEL_284:
                          LastError = 122;
                          if ( *(_DWORD *)&g_dwDebugLevel )
                          {
                            if ( g_lpDebugMsg )
                            {
                              g_lpDebugMsg(
                                2u,
                                L"ProcessLocalGPO: Could not copy SID string %ls (hr=0x%x) to GPOId buffer",
                                v73,
                                (unsigned int)v75);
                            }
                            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                            {
                              RedirectDebugMsg(
                                2u,
                                L"ProcessLocalGPO: Could not copy SID string %ls (hr=0x%x) to GPOId buffer",
                                v73,
                                (unsigned int)v75);
                            }
                          }
                          goto LABEL_68;
                        }
                        v75 = -2147024809;
                      }
                      *v69 = 0;
                      goto LABEL_283;
                    }
                    FreeLibrary(hLibModulea);
                  }
                  LastError = GetLastError();
                  if ( *(_DWORD *)&g_dwDebugLevel )
                  {
                    v100 = g_lpDebugMsg;
                    if ( g_lpDebugMsg )
                    {
                      v101 = GetLastError();
                      v100(
                        2u,
                        L"ProcessLocalGPO:  Failed to load \"Users\" group lgpo display name string (id=%d) with error %d. Exiting",
                        113,
                        v101);
                    }
                    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                    {
                      v102 = GetLastError();
                      RedirectDebugMsg(
                        2u,
                        L"ProcessLocalGPO:  Failed to load \"Users\" group lgpo display name string (id=%d) with error %d. Exiting",
                        113,
                        v102);
                    }
                  }
                  goto LABEL_68;
                }
                FreeLibrary(v58);
              }
              LastError = GetLastError();
              if ( *(_DWORD *)&g_dwDebugLevel )
              {
                v95 = g_lpDebugMsg;
                if ( g_lpDebugMsg )
                {
                  v96 = GetLastError();
                  v95(
                    2u,
                    L"ProcessLocalGPO:  Failed to load gpo display name format string with error %d. Exiting",
                    v96);
                }
                else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                {
                  v109 = GetLastError();
                  RedirectDebugMsg(
                    2u,
                    L"ProcessLocalGPO:  Failed to load gpo display name format string with error %d. Exiting",
                    v109);
                }
              }
              goto LABEL_68;
            }
          }
        }
        LastError = GetLastError();
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          v93 = g_lpDebugMsg;
          if ( g_lpDebugMsg )
          {
            v94 = GetLastError();
            v93(2u, L"ProcessLocalGPO:  Failed to copy GPO id to buffer error=0x%x", v94);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            v113 = GetLastError();
            RedirectDebugMsg(2u, L"ProcessLocalGPO:  Failed to copy GPO id to buffer error=0x%x", v113);
          }
        }
        goto LABEL_68;
      }
      FreeLibrary(v27);
    }
    LastError = GetLastError();
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      v91 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        v92 = GetLastError();
        v91(2u, L"ProcessLocalGPO:  Failed to load local gpo name (id=%d) with error %d. Exiting", 103, v92);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        v114 = GetLastError();
        RedirectDebugMsg(
          2u,
          L"ProcessLocalGPO:  Failed to load local gpo name (id=%d) with error %d. Exiting",
          103,
          v114);
      }
    }
    goto LABEL_68;
  }
  LastError = GetLastError();
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(2u, L"ProcessLocalGPO:  Failed to allocate memory for GPO name (size = %Iu).", 100);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(2u, L"ProcessLocalGPO:  Failed to allocate memory for GPO name (size = %Iu).", 100);
    }
  }
LABEL_69:
  if ( hMem )
    LocalFree(hMem);
  SetLastError(LastError);
  if ( v12 )
    LocalFree(v12);
  if ( v143 )
    LocalFree(v143);
  if ( v11 )
    LocalFree(v11);
  if ( v10 )
    LocalFree(v10);
  if ( v9 )
    LocalFree(v9);
  if ( v8 )
    LocalFree(v8);
  if ( v15 )
    LocalFree(v15);
  return v138;
}

```

## disassembly

```asm
0x1800167b0  mov     [rsp-8+arg_0], rbx
0x1800167b5  push    rbp
0x1800167b6  push    rsi
0x1800167b7  push    rdi
0x1800167b8  push    r12
0x1800167ba  push    r13
0x1800167bc  push    r14
0x1800167be  push    r15
0x1800167c0  lea     rbp, [rsp-80h]
0x1800167c5  sub     rsp, 1B0h
0x1800167cc  mov     rax, cs:__security_cookie
0x1800167d3  xor     rax, rsp
0x1800167d6  mov     [rbp+0B0h+var_40], rax
0x1800167da  mov     rbx, r8
0x1800167dd  mov     [rbp+0B0h+StringSid], rbx
0x1800167e1  mov     [rbp+0B0h+var_F0], edx
0x1800167e4  mov     rax, [rbp+0B0h+arg_20]
0x1800167eb  mov     [rbp+0B0h+var_A8], rax
0x1800167ef  mov     rax, [rbp+0B0h+arg_28]
0x1800167f6  mov     qword ptr [rbp+0B0h+var_70], rax
0x1800167fa  mov     rax, [rbp+0B0h+arg_30]
0x180016801  mov     [rbp+0B0h+var_78], rax
0x180016805  xor     eax, eax
0x180016807  mov     edi, eax
0x180016809  mov     [rbp+0B0h+var_98], rax
0x18001680d  mov     esi, eax
0x18001680f  mov     [rbp+0B0h+var_90], rax
0x180016813  mov     r13d, eax
0x180016816  mov     [rbp+0B0h+var_80], rax
0x18001681a  mov     r14d, eax
0x18001681d  mov     [rbp+0B0h+var_B0], rax
0x180016821  mov     [rbp+0B0h+var_C0], rax
0x180016825  mov     r15d, eax
0x180016828  mov     [rbp+0B0h+var_88], rax
0x18001682c  mov     [rbp+0B0h+cchName], eax
0x18001682f  mov     [rbp+0B0h+cchReferencedDomainName], eax
0x180016832  xorps   xmm0, xmm0
0x180016835  movups  [rbp+0B0h+FileInformation], xmm0
0x180016839  movups  [rbp+0B0h+var_58], xmm0
0x18001683d  mov     [rbp+0B0h+var_48], eax
0x180016840  call    cs:__imp_GetLastError
0x180016846  mov     r12d, eax
0x180016849  mov     [rbp+0B0h+var_128], eax
0x18001684c  xor     eax, eax
0x18001684e  mov     [rbp+0B0h+var_E8], eax
0x180016851  mov     [rbp+0B0h+hMem], rax
0x180016855  mov     [rbp+0B0h+peUse], 8
0x18001685c  test    rbx, rbx
0x18001685f  jz      loc_180016CE9
0x180016865  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001686c  nop     dword ptr [rax+00h]
0x180016870  inc     rax
0x180016873  cmp     word ptr [rbx+rax*2], 0
0x180016878  jnz     short loc_180016870
0x18001687a  add     rax, 0Ah
0x18001687e  mov     [rbp+0B0h+lpString1], rax
0x180016882  mov     edx, 208h; uBytes
0x180016887  mov     ecx, 40h ; '@'; uFlags
0x18001688c  call    cs:__imp_LocalAlloc
0x180016892  mov     rbx, rax
0x180016895  mov     [rbp+0B0h+lpFileName], rax
0x180016899  test    rax, rax
0x18001689c  jz      loc_1800173BC
0x1800168a2  mov     eax, 104h
0x1800168a7  mov     rdx, rbx; lpDst
0x1800168aa  mov     [rbp+0B0h+var_D0], rax
0x1800168ae  mov     r8d, eax; nSize
0x1800168b1  cmp     [rbp+0B0h+StringSid], 0
0x1800168b6  lea     rcx, aSystemrootSyst; "%SystemRoot%\\System32\\GroupPolicy"
0x1800168bd  jz      short loc_1800168C6
0x1800168bf  lea     rcx, Src; "%SystemRoot%\\System32\\GroupPolicyUser"...
0x1800168c6  call    cs:__imp_ExpandEnvironmentStringsW
0x1800168cc  test    eax, eax
0x1800168ce  jz      loc_1800174F4
0x1800168d4  mov     ecx, 104h
0x1800168d9  cmp     eax, ecx
0x1800168db  ja      loc_180017576
0x1800168e1  mov     rdx, [rbp+0B0h+StringSid]
0x1800168e5  test    rdx, rdx
0x1800168e8  jz      loc_180016988
0x1800168ee  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800168f5  lea     rax, [rax+1]
0x1800168f9  cmp     word ptr [rbx+rax*2], 0
0x1800168fe  jnz     short loc_1800168F5
0x180016900  lea     r8, [rbx+rax*2]
0x180016904  cmp     word ptr [r8-2], 5Ch ; '\'
0x18001690a  jz      short loc_18001691C
0x18001690c  mov     word ptr [r8], 5Ch ; '\'
0x180016912  add     r8, 2
0x180016916  xor     eax, eax
0x180016918  mov     [r8], ax
0x18001691c  mov     rax, r8
0x18001691f  sub     rax, rbx
0x180016922  sar     rax, 1
0x180016925  mov     r9, rcx
0x180016928  sub     r9, rax
0x18001692b  jz      loc_1800175EF
0x180016931  cmp     r9, 7FFFFFFFh
0x180016938  ja      loc_1800175E7
0x18001693e  mov     ecx, 7FFFFFFEh
0x180016943  xor     r10d, r10d
0x180016946  test    rcx, rcx
0x180016949  jz      short loc_180016979
0x18001694b  movzx   eax, word ptr [rdx]
0x18001694e  test    ax, ax
0x180016951  jz      short loc_180016974
0x180016953  add     rdx, 2
0x180016957  mov     [r8], ax
0x18001695b  add     r8, 2
0x18001695f  dec     rcx
0x180016962  sub     r9, 1
0x180016966  jnz     short loc_180016946
0x180016968  sub     r8, 2
0x18001696c  mov     r10d, 8007007Ah
0x180016972  jmp     short loc_180016979
0x180016974  test    r9, r9
0x180016977  jz      short loc_180016968
0x180016979  xor     eax, eax
0x18001697b  mov     [r8], ax
0x18001697f  test    r10d, r10d
0x180016982  js      loc_180016BDC
0x180016988  lea     r8, [rbp+0B0h+FileInformation]; lpFileInformation
0x18001698c  xor     edx, edx; fInfoLevelId
0x18001698e  mov     rcx, rbx; lpFileName
0x180016991  call    cs:__imp_GetFileAttributesExW
0x180016997  test    eax, eax
0x180016999  jnz     loc_1800173A6
0x18001699f  mov     [rbp+0B0h+var_F8], 0
0x1800169a6  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x1800169ad  jnz     loc_180017641
0x1800169b3  mov     edx, 64h ; 'd'; uBytes
0x1800169b8  mov     ecx, 40h ; '@'; uFlags
0x1800169bd  call    cs:__imp_LocalAlloc
0x1800169c3  mov     rdi, rax
0x1800169c6  mov     [rbp+0B0h+var_98], rax
0x1800169ca  test    rax, rax
0x1800169cd  jz      loc_18001729D
0x1800169d3  xor     r8d, r8d; dwFlags
0x1800169d6  xor     edx, edx; hFile
0x1800169d8  lea     rcx, LibFileName; "gpsvc.dll"
0x1800169df  call    cs:__imp_LoadLibraryExW
0x1800169e5  mov     rbx, rax
0x1800169e8  test    rax, rax
0x1800169eb  jz      loc_1800176D9
0x1800169f1  mov     r9d, 32h ; '2'; cchBufferMax
0x1800169f7  mov     r8, rdi; lpBuffer
0x1800169fa  mov     edx, 67h ; 'g'; uID
0x1800169ff  mov     rcx, rax; hInstance
0x180016a02  call    cs:__imp_LoadStringW
0x180016a08  mov     rcx, rbx; hLibModule
0x180016a0b  test    eax, eax
0x180016a0d  jz      loc_1800176D3
0x180016a13  call    cs:__imp_FreeLibrary
0x180016a19  mov     rbx, [rbp+0B0h+lpString1]
0x180016a1d  add     rbx, rbx
0x180016a20  mov     rdx, rbx; uBytes
0x180016a23  mov     ecx, 40h ; '@'; uFlags
0x180016a28  call    cs:__imp_LocalAlloc
0x180016a2e  mov     rsi, rax
0x180016a31  mov     [rbp+0B0h+var_90], rax
0x180016a35  test    rax, rax
0x180016a38  jz      loc_18001772A
0x180016a3e  mov     rax, [rbp+0B0h+lpString1]
0x180016a42  test    rax, rax
0x180016a45  jz      loc_1800177A2
0x180016a4b  cmp     rax, 7FFFFFFFh
0x180016a51  ja      loc_18001779D
0x180016a57  mov     ecx, 7FFFFFFEh
0x180016a5c  lea     rdx, aLocalgpo; "LocalGPO"
0x180016a63  mov     r8, rax
0x180016a66  mov     r9, rsi
0x180016a69  xor     r10d, r10d
0x180016a6c  nop     dword ptr [rax+00h]
0x180016a70  test    rcx, rcx
0x180016a73  jz      short loc_180016AA3
0x180016a75  movzx   eax, word ptr [rdx]
0x180016a78  test    ax, ax
0x180016a7b  jz      short loc_180016A9E
0x180016a7d  add     rdx, 2
0x180016a81  mov     [r9], ax
0x180016a85  add     r9, 2
0x180016a89  dec     rcx
0x180016a8c  sub     r8, 1
0x180016a90  jnz     short loc_180016A70
0x180016a92  sub     r9, 2
0x180016a96  mov     r10d, 8007007Ah
0x180016a9c  jmp     short loc_180016AA3
0x180016a9e  test    r8, r8
0x180016aa1  jz      short loc_180016A92
0x180016aa3  xor     eax, eax
0x180016aa5  mov     [r9], ax
0x180016aa9  test    r10d, r10d
0x180016aac  js      loc_1800177A2
0x180016ab2  cmp     [rbp+0B0h+StringSid], rax
0x180016ab6  jnz     loc_180016E93
0x180016abc  mov     [rbp+0B0h+hLibModule], rdi
0x180016ac0  mov     r9d, 7FFFFFFEh
0x180016ac6  mov     rcx, [rbp+0B0h+lpFileName]
0x180016aca  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180016ad1  lea     rax, [rax+1]
0x180016ad5  cmp     word ptr [rcx+rax*2], 0
0x180016ada  jnz     short loc_180016AD1
0x180016adc  lea     rbx, [rcx+rax*2]
0x180016ae0  cmp     word ptr [rbx-2], 5Ch ; '\'
0x180016ae5  jz      short loc_180016AF5
0x180016ae7  mov     word ptr [rbx], 5Ch ; '\'
0x180016aec  add     rbx, 2
0x180016af0  xor     eax, eax
0x180016af2  mov     [rbx], ax
0x180016af5  mov     rax, rbx
0x180016af8  sub     rax, rcx
0x180016afb  sar     rax, 1
0x180016afe  mov     r10d, 104h
0x180016b04  sub     r10, rax
0x180016b07  mov     [rbp+0B0h+var_E0], r10
0x180016b0b  jz      loc_180017DEC
0x180016b11  cmp     r10, 7FFFFFFFh
0x180016b18  ja      loc_180017DE7
0x180016b1e  mov     rcx, r9
0x180016b21  lea     rdx, aGptIni; "gpt.ini"
0x180016b28  mov     r8, r10
0x180016b2b  mov     r9, rbx
0x180016b2e  xor     r11d, r11d
0x180016b31  test    rcx, rcx
0x180016b34  jz      short loc_180016B64
0x180016b36  movzx   eax, word ptr [rdx]
0x180016b39  test    ax, ax
0x180016b3c  jz      short loc_180016B5F
0x180016b3e  add     rdx, 2
0x180016b42  mov     [r9], ax
0x180016b46  add     r9, 2
0x180016b4a  dec     rcx
0x180016b4d  sub     r8, 1
0x180016b51  jnz     short loc_180016B31
0x180016b53  sub     r9, 2
0x180016b57  mov     r11d, 8007007Ah
0x180016b5d  jmp     short loc_180016B64
0x180016b5f  test    r8, r8
0x180016b62  jz      short loc_180016B53
0x180016b64  xor     edx, edx
0x180016b66  mov     [r9], dx
0x180016b6a  test    r11d, r11d
0x180016b6d  js      loc_180017DEC
0x180016b73  mov     [rbp+0B0h+var_D8], edx
0x180016b76  mov     [rbp+0B0h+var_EC], edx
0x180016b79  mov     r9d, [rbp+0B0h+var_F8]
0x180016b7d  test    r9d, r9d
0x180016b80  jnz     loc_180016CF6
0x180016b86  mov     [rbp+0B0h+lpString1], rdx
0x180016b8a  mov     [rbp+0B0h+var_118], edx
0x180016b8d  mov     [rbp+0B0h+var_F4], 1
0x180016b94  mov     r8d, 7FFFFFFEh
0x180016b9a  test    byte ptr [rbp+0B0h+var_F0], 1
0x180016b9e  jnz     loc_180017212
0x180016ba4  lea     rcx, aUser; "User"
0x180016bab  nop     dword ptr [rax+rax+00h]
0x180016bb0  test    r8, r8
0x180016bb3  jz      short loc_180016C21
0x180016bb5  movzx   eax, word ptr [rcx]
0x180016bb8  test    ax, ax
0x180016bbb  jz      short loc_180016C1C
0x180016bbd  add     rcx, 2
0x180016bc1  mov     [rbx], ax
0x180016bc4  add     rbx, 2
0x180016bc8  dec     r8
0x180016bcb  sub     r10, 1
0x180016bcf  jnz     short loc_180016BB0
0x180016bd1  sub     rbx, 2
0x180016bd5  mov     edx, 8007007Ah
0x180016bda  jmp     short loc_180016C21
0x180016bdc  mov     rdx, [rbp+0B0h+StringSid]
0x180016be0  mov     r12d, 7Ah ; 'z'
0x180016be6  mov     [rbp+0B0h+var_128], r12d
0x180016bea  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x180016bf1  jz      short loc_180016C36
0x180016bf3  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180016bfa  test    rax, rax
0x180016bfd  jz      loc_180017609
0x180016c03  mov     r9d, r10d
0x180016c06  mov     r8, rdx
0x180016c09  lea     rdx, aProcesslocalgp_21; "ProcessLocalGPO: Could not copy SID str"...
0x180016c10  mov     ecx, 2
0x180016c15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c1a  jmp     short loc_180016C36
0x180016c1c  test    r10, r10
0x180016c1f  jz      short loc_180016BD1
0x180016c21  xor     eax, eax
0x180016c23  mov     [rbx], ax
0x180016c26  test    edx, edx
0x180016c28  jns     loc_1800170F3
0x180016c2e  movzx   r12d, dx
0x180016c32  mov     rbx, [rbp+0B0h+lpFileName]
0x180016c36  mov     rax, [rbp+0B0h+hMem]
0x180016c3a  test    rax, rax
0x180016c3d  jz      short loc_180016C49
0x180016c3f  mov     rcx, rax; hMem
0x180016c42  call    cs:__imp_LocalFree
0x180016c48  nop
0x180016c49  mov     ecx, r12d; dwErrCode
0x180016c4c  call    cs:__imp_SetLastError
  ... truncated ...
```
