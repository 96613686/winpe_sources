# ProcessGPORegistryPolicy(_GPOINFO *,_GROUP_POLICY_OBJECTW *,long *)

- ea: `0x1800a1e20`
- end: `0x1800a3ad7`
- name: `?ProcessGPORegistryPolicy@@YAHPEAU_GPOINFO@@PEAU_GROUP_POLICY_OBJECTW@@PEAJ@Z`
- size: `7351`
- prototype: `__int64 __fastcall(struct _GPOINFO *, struct _GROUP_POLICY_OBJECTW *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `45`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18006a2e0`

## callees

- `0x180001008`
- `0x1800010bc`
- `0x180003770`
- `0x18000a504`
- `0x18000a52c`
- `0x18001ee6c`
- `0x18002adcc`
- `0x18002b170`
- `0x18002c690`
- `0x180030bcc`
- `0x180039148`
- `0x18003d630`
- `0x18003d8d0`
- `0x180050084`
- `0x1800575fc`
- `0x180065928`
- `0x180067d58`
- `0x180068650`
- `0x18006f958`
- `0x18006fac0`
- `0x18006fb0c`
- `0x180073984`
- `0x180075ec0`
- `0x18007d320`
- `0x18007de08`
- `0x180086324`
- `0x180086364`
- `0x180086ee4`
- `0x18008708c`
- `0x1800870d0`
- `0x180088ef8`
- `0x18009c758`
- `0x18009f49c`
- `0x18009f4d4`
- `0x18009fe1c`
- `0x18009fe98`
- `0x18009ff54`
- `0x1800a1e20`
- `0x1800a41bc`
- `0x1800acb14`
- `0x1800ada3c`
- `0x1800b3bd0`
- `0x1800ba464`
- `0x1800bb8e0`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800a2dc0`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800a2fc8`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800a30ab`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800a2dc0`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800a2fc8`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800a30ab`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a3a17`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a3a17`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a39f2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a39f2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a3a9d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a3a9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1f0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a211c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a23b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a28db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a28f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a292d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a29ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a29eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2a1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2b1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2b4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2b84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2d6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2d8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a300a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3039`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3239`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3320`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3392`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3411`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3492`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a34ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3513`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a353f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3551`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3576`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a35a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a35fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a362d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a36a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a36d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a37ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a37e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a38bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a397e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a39ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1f0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a211c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a23b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a28db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a28f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a292d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a29ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a29eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2a1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2b1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2b4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2b84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2d6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2d8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a300a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3039`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3239`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3320`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3392`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3411`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3492`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a34ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3513`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a353f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3551`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3576`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a35a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a35fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a362d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a36a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a36d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a37ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a37e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a38bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a397e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a39ad`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a238f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a2dd8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a3074`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a238f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a2dd8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a3074`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a2a3a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a2ad4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a2ebf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a328d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a3a3c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a2a3a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a2ad4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a2ebf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a328d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a3a3c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800a24bc`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800a24bc`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800a2bc2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800a2bc2`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a36fb`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a3778`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a36fb`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a3778`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800a25f7`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800a310e`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800a25f7`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800a310e`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800a270c`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800a3284`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800a270c`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800a3284`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800a2cef`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800a2d34`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800a2cef`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800a2d34`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800a2886`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800a2886`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a2ab6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a2b01`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a2ab6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a2b01`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x1800a31ae`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x1800a31ae`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800a27cf`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800a27cf`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800a36f2`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800a376f`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800a378b`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800a3846`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800a3863`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800a3871`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800a3963`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800a39dd`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800a36f2`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800a376f`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800a378b`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800a3846`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800a3863`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800a3871`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800a3963`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800a39dd`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800a26fa`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800a325d`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800a26fa`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800a325d`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800a3888`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800a3888`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x1800a2feb`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x1800a2feb`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800a29bc`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800a29bc`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x1800a210b`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x1800a210b`

## string_xrefs

- `0x1800a2f11`: `registry.pol`
- `0x1800a2141`: `ProcessGPORegistryPolicy: Failed to get path to profile root`
- `0x1800a2175`: `ProcessGPORegistryPolicy: Failed to get path to profile root`
- `0x1800a21cf`: `ProcessGPORegistryPolicy: Failed to concatenate <%ls> and <Microsoft\GroupPolicy\Users>`
- `0x1800a220b`: `ProcessGPORegistryPolicy: Failed to concatenate <%ls> and <Microsoft\GroupPolicy\Users>`
- `0x1800a2273`: `ProcessGPORegistryPolicy: Failed to concatenate (%ls) to (%ls)`
- `0x1800a22b6`: `ProcessGPORegistryPolicy: Failed to concatenate (%ls) to (%ls)`
- `0x1800a22fe`: `ProcessGPORegistryPolicy: SecureDirectory failed (%ls)`
- `0x1800a2324`: `ProcessGPORegistryPolicy: SecureDirectory failed (%ls)`
- `0x1800a234d`: `ProcessGPORegistryPolicy: After concatenation path is (%ls)`
- `0x1800a2378`: `ProcessGPORegistryPolicy: After concatenation path is (%ls)`
- `0x1800a23d1`: `ProcessGPORegistryPolicy: Failed to allocate memory to store path to temporary archive file`
- `0x1800a23f7`: `ProcessGPORegistryPolicy: Failed to allocate memory to store path to temporary archive file`
- `0x1800a243f`: `ProcessGPORegistryPolicy: Failed to copy archive file path (%ls)`
- `0x1800a2470`: `ProcessGPORegistryPolicy: Failed to copy archive file path (%ls)`
- `0x1800a256b`: `ProcessGPORegistryPolicy: Failed to append "%ls" to %ls (buffer size: %d characters)`
- `0x1800a25ae`: `ProcessGPORegistryPolicy: Failed to append "%ls" to %ls (buffer size: %d characters)`
- `0x1800a294c`: `ProcessGPORegistryPolicy: ResetPolicies failed.`
- `0x1800a2975`: `ProcessGPORegistryPolicy: ResetPolicies failed.`
- `0x1800a29f4`: `ProcessGPORegistryPolicy: ConvertStringSecurityDescriptorToSecurityDescriptor failed %d`
- `0x1800a2a23`: `ProcessGPORegistryPolicy: ConvertStringSecurityDescriptorToSecurityDescriptor failed %d`
- `0x1800a2b50`: `ProcessGPORegistryPolicy: Failed to create archive file with %d`
- `0x1800a2b8a`: `ProcessGPORegistryPolicy: Failed to create archive file with %d`
- `0x1800a2c60`: `ProcessGPORegistryPolicy: File Already Exists %d`
- `0x1800a2c86`: `ProcessGPORegistryPolicy: File Already Exists %d`
- `0x1800a357c`: `ProcessGPORegistryPolicy: Failed to write signature with %d`
- `0x1800a35a8`: `ProcessGPORegistryPolicy: Failed to write signature with %d`
- `0x1800a3519`: `ProcessGPORegistryPolicy: Failed to write version number with %d`
- `0x1800a3545`: `ProcessGPORegistryPolicy: Failed to write version number with %d`
- `0x1800a2e21`: `**Comment:GPO Name: `
- `0x1800a2e8a`: `ProcessGPORegistryPolicy: ArchiveRegistryValue returned false.`
- `0x1800a2ead`: `ProcessGPORegistryPolicy: ArchiveRegistryValue returned false.`
- `0x1800a33b3`: `ProcessGPORegistryPolicy: ParseRegistryFile failed.`
- `0x1800a33ce`: `ProcessGPORegistryPolicy: ParseRegistryFile failed.`
- `0x1800a3013`: `ProcessGPORegistryPolicy: Couldn't get the computer Name with error %d.`
- `0x1800a3042`: `ProcessGPORegistryPolicy: Couldn't get the computer Name with error %d.`
- `0x1800a3341`: `ProcessGPORegistryPolicy: ParseRegistryFile failed to allocate memory.`
- `0x1800a3364`: `ProcessGPORegistryPolicy: ParseRegistryFile failed to allocate memory.`
- `0x1800a31fe`: `ProcessGPORegistryPolicy: AddAdmFile failed.`
- `0x1800a3221`: `ProcessGPORegistryPolicy: AddAdmFile failed.`
- `0x1800a330c`: `ProcessGPOs: Error when logging Registry Rsop data. Continuing.`
- `0x1800a33f9`: `ProcessGPOs: Error when logging Registry Rsop data. Continuing.`
- `0x1800a27aa`: `ProcessGPORegistryPolicy: Resetting policies set in the current processing cycle.`
- `0x1800a35c6`: `ProcessGPORegistryPolicy: Resetting policies set in the current processing cycle.`
- `0x1800a3607`: `ProcessGPORegistryPolicy: Encountered error %d when resetting policies set in current processing cycle.`
- `0x1800a3636`: `ProcessGPORegistryPolicy: Encountered error %d when resetting policies set in current processing cycle.`
- `0x1800a36ac`: `ProcessGPORegistryPolicy: Encountered error %d when populating registry with settings in temporary archive file.`
- `0x1800a36db`: `ProcessGPORegistryPolicy: Encountered error %d when populating registry with settings in temporary archive file.`
- `0x1800a37ba`: `ProcessGPORegistryPolicy: Failed to remove %ls due to error: %d.`
- `0x1800a37f1`: `ProcessGPORegistryPolicy: Failed to remove %ls due to error: %d.`
- `0x1800a3987`: `ProcessGPORegistryPolicy: Failed to move latest applied user policy file to "ntuser.pol" due to error: %d.`
- `0x1800a39b6`: `ProcessGPORegistryPolicy: Failed to move latest applied user policy file to "ntuser.pol" due to error: %d.`

## pseudocode

```c
__int64 __fastcall ProcessGPORegistryPolicy(
        struct _GPOINFO *a1,
        struct _GROUP_POLICY_OBJECTW *a2,
        unsigned __int16 *a3)
{
  DWORD LastError; // ebx
  unsigned __int16 *v6; // rdi
  unsigned int v7; // r15d
  const unsigned __int16 *v8; // rcx
  void (*v9)(unsigned int, const unsigned __int16 *, ...); // rax
  const wchar_t *v10; // rdx
  const unsigned __int16 *v11; // rdx
  int v12; // r15d
  void (*v13)(unsigned int, const unsigned __int16 *, ...); // rax
  const wchar_t *v14; // rdx
  const unsigned __int16 *v15; // rdx
  unsigned int v16; // edx
  HLOCAL v17; // rax
  HANDLE FirstFileW; // rbx
  int v19; // eax
  DWORD v20; // r14d
  struct _GPOINFO *v21; // rsi
  unsigned int v22; // r15d
  DWORD FileAttributesW; // esi
  __int64 v24; // r9
  __int64 v25; // rbx
  unsigned __int64 v26; // rcx
  WCHAR *v27; // rbx
  struct _REGHASHTABLE *v28; // rax
  signed int v29; // eax
  void (*v30)(unsigned int, const unsigned __int16 *, ...); // rsi
  DWORD v31; // eax
  DWORD v32; // eax
  __int64 v33; // rcx
  struct _SECURITY_ATTRIBUTES *p_SecurityAttributes; // rax
  HANDLE v35; // rax
  HANDLE FileW; // rax
  HANDLE v37; // rsi
  DWORD v38; // eax
  void (*v39)(unsigned int, const unsigned __int16 *, ...); // rsi
  DWORD v40; // eax
  const wchar_t *v41; // rdx
  DWORD v42; // eax
  __int64 v43; // r15
  int v44; // esi
  DWORD v45; // r14d
  int v46; // esi
  unsigned int GPSourceFileId; // eax
  int *v48; // r8
  struct _REGHASHTABLE *v49; // r15
  signed int v50; // eax
  struct _GROUP_POLICY_OBJECTW *pNext; // rax
  unsigned __int16 *v52; // r14
  struct _GROUP_POLICY_OBJECTW *v53; // r14
  int v54; // eax
  unsigned __int16 *v55; // rax
  struct _GPOINFO *v56; // r14
  size_t v57; // rax
  DWORD dwLowDateTime; // r14d
  void (*v59)(unsigned int, const unsigned __int16 *, ...); // r14
  DWORD v60; // eax
  DWORD v61; // eax
  unsigned __int16 *v62; // r14
  size_t v63; // rax
  unsigned __int16 *v64; // r14
  WCHAR *v65; // r14
  HANDLE v66; // rax
  void *v67; // rdi
  unsigned __int16 *v68; // rbx
  struct _GROUP_POLICY_OBJECTW *v69; // rsi
  signed int v70; // eax
  struct IWbemServices *v71; // r9
  void (*v72)(unsigned int, const unsigned __int16 *, ...); // rax
  const wchar_t *v73; // rdx
  signed int v74; // eax
  signed int v75; // eax
  DWORD v76; // eax
  DWORD v77; // eax
  void (*v78)(unsigned int, const unsigned __int16 *, ...); // rsi
  DWORD v79; // eax
  DWORD v80; // eax
  void (*v81)(unsigned int, const unsigned __int16 *, ...); // rsi
  DWORD v82; // eax
  DWORD v83; // eax
  __int64 v84; // r15
  __int64 v85; // rdi
  int v86; // ebx
  DWORD v87; // r14d
  const WCHAR *p_FileInformation; // rsi
  DWORD v89; // eax
  DWORD v90; // eax
  bool v91; // zf
  DWORD v92; // esi
  void (*v93)(unsigned int, const unsigned __int16 *, ...); // rdi
  DWORD v94; // eax
  DWORD v95; // eax
  unsigned int v96; // edx
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-11B8h]
  DWORD dwCreationDispositiona[2]; // [rsp+20h] [rbp-11B8h]
  const unsigned __int16 *dwCreationDispositionb; // [rsp+20h] [rbp-11B8h]
  DWORD dwFlagsAndAttributes[2]; // [rsp+28h] [rbp-11B0h]
  const unsigned __int16 *dwFlagsAndAttributesa; // [rsp+28h] [rbp-11B0h]
  DWORD v103; // [rsp+60h] [rbp-1178h]
  DWORD nSize; // [rsp+64h] [rbp-1174h] BYREF
  DWORD v105; // [rsp+68h] [rbp-1170h]
  struct _GPOINFO *v106; // [rsp+70h] [rbp-1168h]
  FILETIME FileTime2; // [rsp+78h] [rbp-1160h] BYREF
  HLOCAL v108; // [rsp+80h] [rbp-1158h] BYREF
  DWORD dwFileAttributes; // [rsp+88h] [rbp-1150h]
  LPCWSTR lpFileName; // [rsp+90h] [rbp-1148h] BYREF
  struct _GROUP_POLICY_OBJECTW *v111; // [rsp+98h] [rbp-1140h]
  int Buffer; // [rsp+A0h] [rbp-1138h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+A4h] [rbp-1134h] BYREF
  int v114; // [rsp+A8h] [rbp-1130h]
  unsigned __int16 *v115; // [rsp+B0h] [rbp-1128h] BYREF
  int v116; // [rsp+B8h] [rbp-1120h]
  int v117; // [rsp+BCh] [rbp-111Ch]
  int v118; // [rsp+C0h] [rbp-1118h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+C8h] [rbp-1110h] BYREF
  HANDLE hFile; // [rsp+D0h] [rbp-1108h] BYREF
  int IsDomainIncapableSystem; // [rsp+D8h] [rbp-1100h]
  unsigned __int16 *v122; // [rsp+E0h] [rbp-10F8h]
  FILETIME FileTime1; // [rsp+E8h] [rbp-10F0h] BYREF
  __int128 v124; // [rsp+F0h] [rbp-10E8h] BYREF
  __int64 v125; // [rsp+100h] [rbp-10D8h]
  unsigned int *v126; // [rsp+110h] [rbp-10C8h]
  HLOCAL hMem; // [rsp+118h] [rbp-10C0h] BYREF
  struct _GP_POLICY_SECTION_CONTEXT *v128; // [rsp+120h] [rbp-10B8h]
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+128h] [rbp-10B0h] BYREF
  _QWORD v130[2]; // [rsp+140h] [rbp-1098h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+150h] [rbp-1088h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+160h] [rbp-1078h] BYREF
  __int128 FileInformation; // [rsp+3B0h] [rbp-E28h] BYREF
  struct _FILETIME v134[2]; // [rsp+3C0h] [rbp-E18h] BYREF
  unsigned __int16 **v135; // [rsp+3D0h] [rbp-E08h]
  __int64 v136; // [rsp+3D8h] [rbp-E00h]
  HLOCAL *v137; // [rsp+3E0h] [rbp-DF8h]
  __int64 v138; // [rsp+3E8h] [rbp-DF0h]
  WCHAR v139[56]; // [rsp+3F0h] [rbp-DE8h] BYREF
  WCHAR NewFileName[264]; // [rsp+460h] [rbp-D78h] BYREF
  unsigned __int16 v141[104]; // [rsp+670h] [rbp-B68h] BYREF
  unsigned __int16 v142[264]; // [rsp+740h] [rbp-A98h] BYREF
  unsigned __int16 v143[264]; // [rsp+950h] [rbp-888h] BYREF
  unsigned __int16 v144[264]; // [rsp+B60h] [rbp-678h] BYREF
  unsigned __int16 v145[264]; // [rsp+D70h] [rbp-468h] BYREF
  WCHAR FileName[264]; // [rsp+F80h] [rbp-258h] BYREF

  v122 = a3;
  v111 = a2;
  v126 = (unsigned int *)a1;
  v130[1] = a1;
  v106 = a1;
  v128 = (struct _GP_POLICY_SECTION_CONTEXT *)a2;
  v115 = a3;
  memset_0(FileName, 0, 0x208u);
  memset_0(v142, 0, 0x208u);
  memset_0(v143, 0, 0x208u);
  memset_0(v145, 0, 0x208u);
  hFile = 0;
  Buffer = 0;
  NumberOfBytesWritten = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  hMem = 0;
  LastError = GetLastError();
  v105 = LastError;
  v114 = 0;
  v6 = 0;
  lpFileName = 0;
  v7 = *(_DWORD *)a1;
  LODWORD(v108) = *(_DWORD *)a1;
  dwFileAttributes = 0;
  v116 = 0;
  v117 = 0;
  v103 = 0;
  nSize = 0;
  v118 = 0;
  v124 = 0;
  v125 = 0;
  IsDomainIncapableSystem = CSKU::IsDomainIncapableSystem();
  SecurityDescriptor = 0;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  *(_DWORD *)v122 = 0;
  if ( (unsigned int)dword_180128000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180128000, 0x400000000000LL) )
  {
    v130[0] = 0x2000000;
    v135 = (unsigned __int16 **)v130;
    v136 = 8;
    tlgWriteTransfer_EventWriteTransfer(&dword_180128000, &dword_18011867C, 0, 0, 3, &FileInformation);
  }
  v8 = 0;
  if ( (*(_BYTE *)a1 & 1) == 0 )
    v8 = (const unsigned __int16 *)*((_QWORD *)a1 + 9);
  v128 = (struct _GP_POLICY_SECTION_CONTEXT *)GPLockPolicySection(
                                                v8,
                                                0xEA60u,
                                                (*(_DWORD *)a1 & 0x10000 | 0x800u) >> 10,
                                                *((void **)a1 + 4));
  if ( !v128 )
    goto LABEL_77;
  RegisterTelemetryProviderIfNeeded(*((_DWORD *)a1 + 1) != 0, *(_DWORD *)a1 & 1, *((const unsigned __int16 **)a1 + 9));
  NewFileName[0] = 0;
  GetBasicProfileFolderPath(4, 0, NewFileName, 260);
  if ( !NewFileName[0] )
  {
    LastError = GetLastError();
    v105 = LastError;
    if ( !*(_DWORD *)&g_dwDebugLevel )
    {
LABEL_77:
      v20 = 0;
      goto LABEL_78;
    }
    v9 = g_lpDebugMsg;
    if ( g_lpDebugMsg )
    {
      v10 = L"ProcessGPORegistryPolicy: Failed to get path to profile root";
LABEL_11:
      v9(2u, v10);
      goto LABEL_77;
    }
    if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
      goto LABEL_77;
    v11 = L"ProcessGPORegistryPolicy: Failed to get path to profile root";
    goto LABEL_15;
  }
  v12 = v7 & 1;
  if ( !v12 )
  {
    if ( (int)StringCchCatW(NewFileName, 0x104u, L"\\Microsoft\\GroupPolicy\\Users\\") < 0 )
    {
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_77;
      v13 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        v14 = L"ProcessGPORegistryPolicy: Failed to concatenate <%ls> and <Microsoft\\GroupPolicy\\Users>";
LABEL_21:
        v13(2u, v14, NewFileName);
        goto LABEL_77;
      }
      if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
        goto LABEL_77;
      v15 = L"ProcessGPORegistryPolicy: Failed to concatenate <%ls> and <Microsoft\\GroupPolicy\\Users>";
      goto LABEL_25;
    }
    if ( (int)StringCchCatW(NewFileName, 0x104u, *((const unsigned __int16 **)a1 + 9)) < 0 )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(
            2u,
            L"ProcessGPORegistryPolicy: Failed to concatenate (%ls) to (%ls)",
            *((_QWORD *)a1 + 26),
            NewFileName);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(
            2u,
            L"ProcessGPORegistryPolicy: Failed to concatenate (%ls) to (%ls)",
            *((_QWORD *)a1 + 26),
            NewFileName);
        }
      }
      goto LABEL_77;
    }
    if ( (SetSecureDirectory(NewFileName, v16, *((void **)a1 + 1)) & 0x80000000) != 0 )
    {
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_77;
      v13 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        v14 = L"ProcessGPORegistryPolicy: SecureDirectory failed (%ls)";
        goto LABEL_21;
      }
      if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
        goto LABEL_77;
      v15 = L"ProcessGPORegistryPolicy: SecureDirectory failed (%ls)";
LABEL_25:
      RedirectDebugMsg(2u, v15, NewFileName);
      goto LABEL_77;
    }
  }
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"ProcessGPORegistryPolicy: After concatenation path is (%ls)", NewFileName);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"ProcessGPORegistryPolicy: After concatenation path is (%ls)", NewFileName);
    }
  }
  v17 = LocalAlloc(0x40u, 0x208u);
  XPtrLF<unsigned short>::operator=(&lpFileName, v17);
  v6 = (unsigned __int16 *)lpFileName;
  if ( !lpFileName )
  {
    GetLastError();
    if ( !*(_DWORD *)&g_dwDebugLevel )
      goto LABEL_77;
    v9 = g_lpDebugMsg;
    if ( g_lpDebugMsg )
    {
      v10 = L"ProcessGPORegistryPolicy: Failed to allocate memory to store path to temporary archive file";
      goto LABEL_11;
    }
    if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
      goto LABEL_77;
    v11 = L"ProcessGPORegistryPolicy: Failed to allocate memory to store path to temporary archive file";
LABEL_15:
    RedirectDebugMsg(2u, v11);
    goto LABEL_77;
  }
  if ( (int)StringCchCopyW((unsigned __int16 *)lpFileName, 0x104u, NewFileName) < 0 )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"ProcessGPORegistryPolicy: Failed to copy archive file path (%ls)", NewFileName);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"ProcessGPORegistryPolicy: Failed to copy archive file path (%ls)", NewFileName);
      }
    }
LABEL_60:
    XPtrLF<unsigned short>::operator=(&lpFileName, 0);
    v6 = (unsigned __int16 *)lpFileName;
    goto LABEL_77;
  }
  SystemTime = 0;
  GetSystemTime(&SystemTime);
  dwFlagsAndAttributes[0] = SystemTime.wHour;
  dwCreationDisposition[0] = SystemTime.wDay;
  swprintf_s<260>(
    v143,
    L"\\ntuser_%04d%02d%02d%02d%02d%02d%04d.pol",
    SystemTime.wYear,
    SystemTime.wMonth,
    *(_QWORD *)dwCreationDisposition,
    *(_QWORD *)dwFlagsAndAttributes,
    SystemTime.wMinute,
    SystemTime.wSecond,
    SystemTime.wMilliseconds);
  if ( (int)StringCchCatW(v6, 0x104u, v143) < 0 )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        dwCreationDispositiona[0] = 260;
        g_lpDebugMsg(
          2u,
          L"ProcessGPORegistryPolicy: Failed to append \"%ls\" to %ls (buffer size: %d characters)",
          v143,
          v6,
          *(_QWORD *)dwCreationDispositiona);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        dwCreationDispositiona[0] = 260;
        RedirectDebugMsg(
          2u,
          L"ProcessGPORegistryPolicy: Failed to append \"%ls\" to %ls (buffer size: %d characters)",
          v143,
          v6,
          *(_QWORD *)dwCreationDispositiona);
      }
    }
    goto LABEL_60;
  }
  StringCchPrintfW(FileName, 0x104u, L"%ls\\ntuser_*.pol", NewFileName);
  FirstFileW = FindFirstFileW(FileName, &FindFileData);
  if ( FirstFileW != (HANDLE)-1LL )
  {
    StringCchPrintfW(v142, 0x104u, L"%ls\\%ls", NewFileName, FindFileData.cFileName);
    if ( !(unsigned int)IsOwnedBySystemOrAdminOnly(v142) )
      goto LABEL_73;
LABEL_72:
    std::wstring::wstring(&FileInformation, v142);
    std::vector<std::wstring>::push_back(&v124, &FileInformation);
    std::wstring::_Tidy_deallocate(&FileInformation);
LABEL_73:
    while ( FindNextFileW(FirstFileW, &FindFileData) )
    {
      StringCchPrintfW(v142, 0x104u, L"%ls\\%ls", NewFileName, FindFileData.cFileName);
      if ( (unsigned int)IsOwnedBySystemOrAdminOnly(v142) )
        goto LABEL_72;
    }
    FindClose(FirstFileW);
  }
  v19 = StringCchCatW(NewFileName, 0x104u, L"\\ntuser.pol");
  if ( v19 < 0 )
  {
    LastError = (unsigned __int16)v19;
    v105 = (unsigned __int16)v19;
    goto LABEL_77;
  }
  v108 = 0;
  FileAttributesW = GetFileAttributesW(NewFileName);
  v20 = FileAttributesW != -1;
  v103 = v20;
  v25 = *((_QWORD *)&v124 + 1);
  v26 = (__int64)(*((_QWORD *)&v124 + 1) - v124) >> 5;
  if ( !v26 )
    goto LABEL_96;
  if ( v26 > 1 )
  {
    LOBYTE(v24) = 0;
    std::_Sort_unchecked<std::wstring *,std::less<void>>(
      v124,
      *((_QWORD *)&v124 + 1),
      (__int64)(*((_QWORD *)&v124 + 1) - v124) >> 5,
      v24);
    v25 = *((_QWORD *)&v124 + 1);
  }
  v27 = (WCHAR *)(v25 - 32);
  if ( *((_QWORD *)v27 + 3) > 7u )
    v27 = *(WCHAR **)v27;
  if ( FileAttributesW != -1 )
  {
    FileTime1 = 0;
    FileTime2 = 0;
    if ( GetFileCreationTime(NewFileName, &FileTime1) )
    {
      if ( GetFileCreationTime(v27, &FileTime2) && CompareFileTime(&FileTime1, &FileTime2) == 1 )
      {
        v118 = 1;
LABEL_96:
        v27 = NewFileName;
      }
    }
  }
  StringCchCopyW(v145, 0x104u, v27);
  dwFileAttributes = 7;
  if ( *((_QWORD *)a1 + 24) )
  {
    v28 = AllocHashTable();
    v108 = v28;
    if ( !v28 )
    {
      v29 = GetLastError();
      if ( v29 > 0 )
        v29 = (unsigned __int16)v29 | 0x80070000;
      *(_DWORD *)v122 = v29;
      LastError = GetLastError();
      v105 = LastError;
      nSize = FileAttributesW != -1;
      goto LABEL_78;
    }
  }
  else
  {
    v28 = 0;
  }
  if ( !(unsigned int)ResetPolicies(a1, v145, v28) )
  {
    v105 = GetLastError();
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"ProcessGPORegistryPolicy: ResetPolicies failed.");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"ProcessGPORegistryPolicy: ResetPolicies failed.");
      }
    }
  }
  v116 = 1;
  if ( v12 )
  {
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
            L"D:P(A;;FA;;;SY)(A;;FA;;;BA)",
            1u,
            &SecurityDescriptor,
            0) )
    {
      LastError = GetLastError();
      v105 = LastError;
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        v30 = g_lpDebugMsg;
        if ( g_lpDebugMsg )
        {
          v31 = GetLastError();
          v30(2u, L"ProcessGPORegistryPolicy: ConvertStringSecurityDescriptorToSecurityDescriptor failed %d", v31);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          v32 = GetLastError();
          RedirectDebugMsg(
            2u,
            L"ProcessGPORegistryPolicy: ConvertStringSecurityDescriptorToSecurityDescriptor failed %d",
            v32);
        }
      }
      LocalFree(SecurityDescriptor);
      SecurityDescriptor = 0;
      goto LABEL_119;
    }
    v33 = 24;
    p_SecurityAttributes = &SecurityAttributes;
    do
    {
      LOBYTE(p_SecurityAttributes->nLength) = 0;
      p_SecurityAttributes = (struct _SECURITY_ATTRIBUTES *)((char *)p_SecurityAttributes + 1);
      --v33;
    }
    while ( v33 );
    SecurityAttributes.nLength = 24;
    SecurityAttributes.lpSecurityDescriptor = SecurityDescriptor;
    SecurityAttributes.bInheritHandle = 0;
    v35 = CreateFileW(v6, 0x40000000u, 0, &SecurityAttributes, 2u, 0x8000007u, 0);
    XHandle::operator=(&hFile, v35);
    LocalFree(SecurityDescriptor);
    SecurityDescriptor = 0;
  }
  else
  {
    FileW = CreateFileW(v6, 0x40000000u, 0, 0, 2u, 0x8000007u, 0);
    XHandle::operator=(&hFile, FileW);
  }
  v37 = hFile;
  v38 = GetLastError();
  LastError = v38;
  if ( v37 == (HANDLE)-1LL )
  {
    v105 = v38;
    if ( !*(_DWORD *)&g_dwDebugLevel )
      goto LABEL_119;
    v39 = g_lpDebugMsg;
    if ( !g_lpDebugMsg )
    {
      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        v42 = GetLastError();
        RedirectDebugMsg(2u, L"ProcessGPORegistryPolicy: Failed to create archive file with %d", v42);
      }
      goto LABEL_119;
    }
    v40 = GetLastError();
    v41 = L"ProcessGPORegistryPolicy: Failed to create archive file with %d";
    goto LABEL_128;
  }
  v105 = v38;
  if ( v38 == 183 )
  {
    v43 = *((_QWORD *)v106 + 33);
    v44 = *((_DWORD *)v106 + 64);
    v45 = GetTickCount() - v44;
    v46 = *((_DWORD *)v106 + 70);
    GPSourceFileId = GetGPSourceFileId(L"ds\\grouppolicy\\client\\gpsvc\\engine\\gpreg.cpp");
    CGPAdminEventGPOFileFailure::CGPAdminEventGPOFileFailure(
      v139,
      gpEvent_FILE_CREATION_FAILED,
      GPSourceFileId,
      3128,
      v46,
      v45,
      183,
      v43,
      &DomainName,
      v6,
      &DomainName);
    v21 = v106;
    CGPPolicyEventReporting::Report(*((CGPPolicyEventReporting **)v106 + 34), (struct CGPEventInfo *)v139, v48);
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"ProcessGPORegistryPolicy: File Already Exists %d", LastError);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"ProcessGPORegistryPolicy: File Already Exists %d", LastError);
      }
    }
    *(_QWORD *)v139 = &CGPAdminEventLdapFailure::`vftable';
    CGPAdminEventInitFailure::~CGPAdminEventInitFailure((CGPAdminEventInitFailure *)v139);
    v20 = v103;
LABEL_140:
    v103 = v20;
    nSize = v20;
    goto LABEL_79;
  }
  Buffer = 1734693456;
  if ( !WriteFile(v37, &Buffer, 4u, &NumberOfBytesWritten, 0) || NumberOfBytesWritten != 4 )
  {
    LastError = GetLastError();
    v105 = LastError;
    if ( !*(_DWORD *)&g_dwDebugLevel )
      goto LABEL_119;
    v39 = g_lpDebugMsg;
    if ( !g_lpDebugMsg )
    {
      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        v77 = GetLastError();
        RedirectDebugMsg(2u, L"ProcessGPORegistryPolicy: Failed to write signature with %d", v77);
      }
      goto LABEL_119;
    }
    v40 = GetLastError();
    v41 = L"ProcessGPORegistryPolicy: Failed to write signature with %d";
LABEL_128:
    v39(2u, v41, v40);
    goto LABEL_119;
  }
  Buffer = 1;
  if ( !WriteFile(v37, &Buffer, 4u, &NumberOfBytesWritten, 0) || NumberOfBytesWritten != 4 )
  {
    LastError = GetLastError();
    v105 = LastError;
    if ( !*(_DWORD *)&g_dwDebugLevel )
      goto LABEL_119;
    v39 = g_lpDebugMsg;
    if ( !g_lpDebugMsg )
    {
      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        v76 = GetLastError();
        RedirectDebugMsg(2u, L"ProcessGPORegistryPolicy: Failed to write version number with %d", v76);
      }
      goto LABEL_119;
    }
    v40 = GetLastError();
    v41 = L"ProcessGPORegistryPolicy: Failed to write version number with %d";
    goto LABEL_128;
  }
  v49 = 0;
  if ( *((_QWORD *)v106 + 24) )
  {
    v49 = AllocHashTable();
    if ( !v49 )
    {
      v50 = GetLastError();
      if ( v50 > 0 )
        v50 = (unsigned __int16)v50 | 0x80070000;
      *(_DWORD *)v122 = v50;
      LastError = GetLastError();
      v105 = LastError;
      goto LABEL_119;
    }
  }
  v117 = 1;
  pNext = v111;
  if ( !v111 )
  {
LABEL_197:
    v21 = v106;
    v71 = (struct IWbemServices *)*((_QWORD *)v106 + 24);
    if ( v71 )
    {
      if ( !(unsigned int)LogRegistryRsopData(*v126, v49, (struct _REGHASHTABLE *)v108, v71) )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(2u, L"ProcessGPOs: Error when logging Registry Rsop data. Continuing.");
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(2u, L"ProcessGPOs: Error when logging Registry Rsop data. Continuing.");
          }
        }
        if ( !*((_DWORD *)v49 + 194) )
        {
          v74 = GetLastError();
          if ( v74 > 0 )
            v74 = (unsigned __int16)v74 | 0x80070000;
          *((_DWORD *)v49 + 194) = v74;
        }
      }
      if ( !(unsigned int)LogAdmRsopData((struct _ADMFILEINFO *)hMem, *((struct IWbemServices **)v21 + 24)) )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(2u, L"ProcessGPOs: Error when logging Adm Rsop data. Continuing.");
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(2u, L"ProcessGPOs: Error when logging Adm Rsop data. Continuing.");
          }
        }
        if ( !*((_DWORD *)v49 + 194) )
        {
          v75 = GetLastError();
          if ( v75 > 0 )
            v75 = (unsigned __int16)v75 | 0x80070000;
          *((_DWORD *)v49 + 194) = v75;
        }
      }
      *(_DWORD *)v122 = *((_DWORD *)v49 + 194);
    }
    FreeHashTable(v49);
    FreeHashTable(v108);
    FreeAdmFileCache(hMem);
    v114 = 1;
    goto LABEL_140;
  }
  while ( 1 )
  {
    FileTime2 = (FILETIME)(wcsnlen(pNext->lpDisplayName, 0x104u) + 25);
    v52 = (unsigned __int16 *)LocalAlloc(0x40u, 2LL * *(_QWORD *)&FileTime2);
    if ( v52 )
    {
      StringCchCopyW(v141, 0x64u, L"Software\\Policies\\Microsoft\\Windows\\Group Policy Objects\\");
      StringCchCatW(v141, 0x64u, v111->szGPOName);
      StringCchCopyW(v52, *(_QWORD *)&FileTime2, L"**Comment:GPO Name: ");
      StringCchCatW(v52, *(_QWORD *)&FileTime2, v111->lpDisplayName);
      if ( !(unsigned int)ArchiveRegistryValue(v37, v141, v52, 1u, 0, 0) && *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"ProcessGPORegistryPolicy: ArchiveRegistryValue returned false.");
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"ProcessGPORegistryPolicy: ArchiveRegistryValue returned false.");
        }
      }
      LocalFree(v52);
    }
    v53 = v111;
    v54 = StringCchCopyW(v144, 0x104u, v111->lpFileSysPath);
    if ( v54 < 0 )
    {
      LastError = (unsigned __int16)v54;
      goto LABEL_217;
    }
    v55 = CheckSlash(v144);
    if ( (int)StringCchCopyW(v55, 260 - (v55 - v144), L"registry.pol") < 0 )
    {
      LastError = 122;
LABEL_217:
      v105 = LastError;
      goto LABEL_209;
    }
    dwFlagsAndAttributesa = v53->lpLink;
    dwCreationDispositionb = v53->lpDSPath;
    v56 = v106;
    if ( !ParseRegistryFile(
            v106,
            v144,
            (int (*)(struct _GPOINFO *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int, unsigned __int8 *, const unsigned __int16 *, const unsigned __int16 *, struct _REGHASHTABLE *, struct _REGHASHTABLE *))SetRegistryValue,
            v37,
            dwCreationDispositionb,
            dwFlagsAndAttributesa,
            v49,
            (struct _REGHASHTABLE *)v108,
            0,
            1,
            IsDomainIncapableSystem) )
      break;
    if ( *((_QWORD *)v56 + 24) )
    {
      FileInformation = 0;
      *(_OWORD *)&v134[0].dwLowDateTime = 0;
      LODWORD(v135) = 0;
      v57 = wcsnlen(v111->lpFileSysPath, 0x104u);
      dwLowDateTime = v57;
      FileTime2 = (FILETIME)v57;
      nSize = 46;
      if ( !GetComputerNameW(v139, &nSize) )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          v59 = g_lpDebugMsg;
          if ( g_lpDebugMsg )
          {
            v60 = GetLastError();
            v59(2u, L"ProcessGPORegistryPolicy: Couldn't get the computer Name with error %d.", v60);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            v61 = GetLastError();
            RedirectDebugMsg(2u, L"ProcessGPORegistryPolicy: Couldn't get the computer Name with error %d.", v61);
          }
          dwLowDateTime = FileTime2.dwLowDateTime;
        }
        v139[0] = 0;
      }
      nSize = dwLowDateTime + 260;
      v62 = (unsigned __int16 *)LocalAlloc(0x40u, 2LL * (dwLowDateTime + 260));
      FileTime2 = (FILETIME)v62;
      if ( !v62 )
      {
        LastError = GetLastError();
        v105 = LastError;
        if ( !*(_DWORD *)&g_dwDebugLevel )
          goto LABEL_209;
        v72 = g_lpDebugMsg;
        if ( g_lpDebugMsg )
        {
          v73 = L"ProcessGPORegistryPolicy: ParseRegistryFile failed to allocate memory.";
LABEL_205:
          v72(2u, v73);
          goto LABEL_209;
        }
        if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          RedirectDebugMsg(2u, L"ProcessGPORegistryPolicy: ParseRegistryFile failed to allocate memory.");
        goto LABEL_209;
      }
      StringCchCopyW(v62, nSize, v111->lpFileSysPath);
      v63 = wcsnlen(v62, 0x104u);
      v64 = (unsigned __int16 *)((char *)&v62[v63] - ((*v126 & 1) != 0 ? 14LL : 8LL));
      StringCchCopyW(v64, nSize - (((__int64)v64 - *(_QWORD *)&FileTime2) >> 1), L"Adm\\*.adm");
      v115 = v64 + 4;
      v65 = (WCHAR *)FileTime2;
      v66 = FindFirstFileW(*(LPCWSTR *)&FileTime2, &FindFileData);
      FileTime2 = (FILETIME)v66;
      if ( v66 != (HANDLE)-1LL )
      {
        v67 = v66;
        v68 = v115;
        v69 = v111;
        do
        {
          if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
          {
            if ( (int)StringCchCopyW(v68, nSize - (v68 - v65), FindFileData.cFileName) >= 0 )
            {
              FileInformation = 0;
              *(_OWORD *)&v134[0].dwLowDateTime = 0;
              LODWORD(v135) = 0;
              if ( GetFileAttributesExW(v65, GetFileExInfoStandard, &FileInformation)
                && !(unsigned int)AddAdmFile(
                                    v65,
                                    v69->lpDSPath,
                                    (struct _FILETIME *)&v134[0].dwHighDateTime,
                                    v139,
                                    (struct _ADMFILEINFO **)&hMem) )
              {
                if ( *(_DWORD *)&g_dwDebugLevel )
                {
                  if ( g_lpDebugMsg )
                  {
                    g_lpDebugMsg(2u, L"ProcessGPORegistryPolicy: AddAdmFile failed.");
                  }
                  else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                  {
                    RedirectDebugMsg(2u, L"ProcessGPORegistryPolicy: AddAdmFile failed.");
                  }
                }
                if ( !*((_DWORD *)v49 + 194) )
                {
                  v70 = GetLastError();
                  if ( v70 > 0 )
                    v70 = (unsigned __int16)v70 | 0x80070000;
                  *((_DWORD *)v49 + 194) = v70;
                }
              }
            }
            else if ( !*((_DWORD *)v49 + 194) )
            {
              *((_DWORD *)v49 + 194) = 122;
            }
          }
        }
        while ( FindNextFileW(v67, &FindFileData) );
        LastError = v105;
        v6 = (unsigned __int16 *)lpFileName;
        v37 = hFile;
        FindClose(*(HANDLE *)&FileTime2);
      }
      LocalFree(v65);
    }
    pNext = v111->pNext;
    v111 = pNext;
    if ( !pNext )
    {
      v20 = v103;
      goto LABEL_197;
    }
  }
  LastError = GetLastError();
  v105 = LastError;
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    v72 = g_lpDebugMsg;
    if ( g_lpDebugMsg )
    {
      v73 = L"ProcessGPORegistryPolicy: ParseRegistryFile failed.";
      goto LABEL_205;
    }
    if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      RedirectDebugMsg(2u, L"ProcessGPORegistryPolicy: ParseRegistryFile failed.");
  }
LABEL_209:
  FreeHashTable(v49);
  FreeHashTable(v108);
  v20 = v103;
LABEL_119:
  v103 = v20;
  nSize = v20;
LABEL_78:
  v21 = v106;
LABEL_79:
  XHandle::operator=(&hFile, 0);
  v22 = v114;
  if ( v114 || !v116 )
  {
    LODWORD(v108) = 1;
    v84 = v124;
    if ( (_QWORD)v124 == *((_QWORD *)&v124 + 1) )
      goto LABEL_284;
    v85 = *((_QWORD *)&v124 + 1);
    v86 = (int)v108;
    v87 = dwFileAttributes;
    do
    {
      std::wstring::wstring(&FileInformation, v84);
      p_FileInformation = (const WCHAR *)&FileInformation;
      if ( *(_QWORD *)&v134[1] > 7u )
        p_FileInformation = (const WCHAR *)FileInformation;
      SetFileAttributesW(p_FileInformation, 0x80u);
      if ( !DeleteFileW(p_FileInformation) )
      {
        v86 = 0;
        SetFileAttributesW(p_FileInformation, v87);
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          v115 = (unsigned __int16 *)g_lpDebugMsg;
          if ( g_lpDebugMsg )
          {
            v89 = GetLastError();
            ((void (*)(__int64, const unsigned __int16 *, ...))v115)(
              2,
              L"ProcessGPORegistryPolicy: Failed to remove %ls due to error: %d.",
              p_FileInformation,
              v89);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            v90 = GetLastError();
            RedirectDebugMsg(
              2u,
              L"ProcessGPORegistryPolicy: Failed to remove %ls due to error: %d.",
              p_FileInformation,
              v90);
          }
        }
      }
      std::wstring::_Tidy_deallocate(&FileInformation);
      v84 += 32;
    }
    while ( v84 != v85 );
    v91 = v86 == 0;
    LastError = v105;
    v6 = (unsigned __int16 *)lpFileName;
    v20 = v103;
    if ( !v91 || v118 )
    {
LABEL_284:
      if ( v20 )
        SetFileAttributesW(NewFileName, 0x80u);
      SetFileAttributesW(v6, 0x80u);
      if ( MoveFileExW(v6, NewFileName, 1u) )
      {
        v92 = dwFileAttributes;
      }
      else
      {
        if ( (unsigned int)dword_180128000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180128000, 0x400000000000LL) )
        {
          LODWORD(v108) = GetLastError();
          v115 = (unsigned __int16 *)0x2000000;
          v137 = &v108;
          v138 = 4;
          v135 = &v115;
          v136 = 8;
          tlgWriteTransfer_EventWriteTransfer(&dword_180128000, word_18011863A, 0, 0, 4, &FileInformation);
        }
        v92 = dwFileAttributes;
        SetFileAttributesW(v6, dwFileAttributes);
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          v93 = g_lpDebugMsg;
          if ( g_lpDebugMsg )
          {
            v94 = GetLastError();
            v93(
              2u,
              L"ProcessGPORegistryPolicy: Failed to move latest applied user policy file to \"ntuser.pol\" due to error: %d.",
              v94);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            v95 = GetLastError();
            RedirectDebugMsg(
              2u,
              L"ProcessGPORegistryPolicy: Failed to move latest applied user policy file to \"ntuser.pol\" due to error: %d.",
              v95);
          }
        }
      }
    }
    else
    {
      v92 = dwFileAttributes;
      SetFileAttributesW(lpFileName, dwFileAttributes);
    }
    if ( v20 )
      SetFileAttributesW(NewFileName, v92);
    v22 = v114;
  }
  else if ( v6 )
  {
    if ( v117 )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(v114 + 4, L"ProcessGPORegistryPolicy: Resetting policies set in the current processing cycle.");
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(4u, L"ProcessGPORegistryPolicy: Resetting policies set in the current processing cycle.");
        }
      }
      if ( !(unsigned int)ResetPolicies(v21, v6, 0) && *(_DWORD *)&g_dwDebugLevel )
      {
        v78 = g_lpDebugMsg;
        if ( g_lpDebugMsg )
        {
          v79 = GetLastError();
          v78(
            2u,
            L"ProcessGPORegistryPolicy: Encountered error %d when resetting policies set in current processing cycle.",
            v79);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          v80 = GetLastError();
          RedirectDebugMsg(
            2u,
            L"ProcessGPORegistryPolicy: Encountered error %d when resetting policies set in current processing cycle.",
            v80);
        }
      }
    }
    if ( !ParseRegistryFile(
            v106,
            v145,
            (int (*)(struct _GPOINFO *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int, unsigned __int8 *, const unsigned __int16 *, const unsigned __int16 *, struct _REGHASHTABLE *, struct _REGHASHTABLE *))SetRegistryValue,
            0,
            0,
            0,
            0,
            0,
            0,
            0,
            IsDomainIncapableSystem)
      && *(_DWORD *)&g_dwDebugLevel )
    {
      v81 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        v82 = GetLastError();
        v81(
          2u,
          L"ProcessGPORegistryPolicy: Encountered error %d when populating registry with settings in temporary archive file.",
          v82);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        v83 = GetLastError();
        RedirectDebugMsg(
          2u,
          L"ProcessGPORegistryPolicy: Encountered error %d when populating registry with settings in temporary archive file.",
          v83);
      }
    }
    SetFileAttributesW(v6, 0x80u);
    DeleteFileW(v6);
  }
  AcquireSRWLockExclusive(&SRWLock);
  if ( qword_18012A218 )
  {
    CGPRegistryTelemetry::`scalar deleting destructor'(qword_18012A218, v96);
    qword_18012A218 = 0;
  }
  ReleaseSRWLockExclusive(&SRWLock);
  if ( v128 )
    GPUnLockPolicySection(v128);
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  if ( (_QWORD)v124 )
  {
    std::_Destroy_range<std::allocator<std::wstring>>(v124, *((_QWORD *)&v124 + 1));
    std::_Deallocate<16>(v124, (v125 - v124) & 0xFFFFFFFFFFFFFFE0uLL);
    v124 = 0;
    v125 = 0;
  }
  XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(&lpFileName);
  SetLastError(LastError);
  XHandle::~XHandle((XHandle *)&hFile);
  return v22;
}

```

## disassembly

```asm
0x1800a1e20  push    rbx
0x1800a1e22  push    rsi
0x1800a1e23  push    rdi
0x1800a1e24  push    r12
0x1800a1e26  push    r13
0x1800a1e28  push    r14
0x1800a1e2a  push    r15
0x1800a1e2c  mov     eax, 11A0h
0x1800a1e31  call    _alloca_probe
0x1800a1e36  sub     rsp, rax
0x1800a1e39  mov     rax, cs:__security_cookie
0x1800a1e40  xor     rax, rsp
0x1800a1e43  mov     [rsp+11D8h+var_48], rax
0x1800a1e4b  mov     [rsp+11D8h+var_10F8], r8
0x1800a1e53  mov     rax, rdx
0x1800a1e56  mov     [rsp+11D8h+var_1140], rdx
0x1800a1e5e  mov     r14, rcx
0x1800a1e61  mov     [rsp+11D8h+var_10C8], rcx
0x1800a1e69  mov     [rsp+11D8h+var_1090], rcx
0x1800a1e71  mov     r13, rcx
0x1800a1e74  mov     [rsp+11D8h+var_1168], rcx
0x1800a1e79  mov     [rsp+11D8h+var_10B8], rdx
0x1800a1e81  mov     [rsp+11D8h+var_1128], r8
0x1800a1e89  mov     esi, 208h
0x1800a1e8e  mov     r8d, esi; Size
0x1800a1e91  xor     edx, edx; Val
0x1800a1e93  lea     rcx, [rsp+11D8h+FileName]; void *
0x1800a1e9b  call    memset_0
0x1800a1ea0  mov     r8d, esi; Size
0x1800a1ea3  xor     edx, edx; Val
0x1800a1ea5  lea     rcx, [rsp+11D8h+var_A98]; void *
0x1800a1ead  call    memset_0
0x1800a1eb2  mov     r8d, esi; Size
0x1800a1eb5  xor     edx, edx; Val
0x1800a1eb7  lea     rcx, [rsp+11D8h+var_888]; void *
0x1800a1ebf  call    memset_0
0x1800a1ec4  mov     r8d, esi; Size
0x1800a1ec7  xor     edx, edx; Val
0x1800a1ec9  lea     rcx, [rsp+11D8h+var_468]; void *
0x1800a1ed1  call    memset_0
0x1800a1ed6  xor     r12d, r12d
0x1800a1ed9  mov     [rsp+11D8h+hFile], r12
0x1800a1ee1  mov     [rsp+11D8h+Buffer], r12d
0x1800a1ee9  mov     [rsp+11D8h+NumberOfBytesWritten], r12d
0x1800a1ef1  xor     edx, edx; Val
0x1800a1ef3  lea     r8d, [rsi+48h]; Size
0x1800a1ef7  lea     rcx, [rsp+11D8h+FindFileData]; void *
0x1800a1eff  call    memset_0
0x1800a1f04  mov     [rsp+11D8h+hMem], r12
0x1800a1f0c  call    cs:__imp_GetLastError
0x1800a1f12  mov     ebx, eax
0x1800a1f14  mov     [rsp+11D8h+var_1170], eax
0x1800a1f18  mov     [rsp+11D8h+var_1130], r12d
0x1800a1f20  mov     edi, r12d
0x1800a1f23  mov     [rsp+11D8h+lpFileName], r12
0x1800a1f2b  mov     r15d, [r13+0]
0x1800a1f2f  mov     dword ptr [rsp+11D8h+var_1158], r15d
0x1800a1f37  mov     [rsp+11D8h+dwFileAttributes], r12d
0x1800a1f3f  mov     [rsp+11D8h+var_1120], r12d
0x1800a1f47  mov     [rsp+11D8h+var_111C], r12d
0x1800a1f4f  mov     eax, r12d
0x1800a1f52  mov     [rsp+11D8h+var_1178], eax
0x1800a1f56  mov     [rsp+11D8h+nSize], eax
0x1800a1f5a  mov     [rsp+11D8h+var_1118], r12d
0x1800a1f62  xorps   xmm0, xmm0
0x1800a1f65  movdqu  [rsp+11D8h+var_10E8], xmm0
0x1800a1f6e  mov     [rsp+11D8h+var_10D8], r12
0x1800a1f76  call    ?IsDomainIncapableSystem@CSKU@@SAHXZ; CSKU::IsDomainIncapableSystem(void)
0x1800a1f7b  mov     [rsp+11D8h+var_1100], eax
0x1800a1f82  mov     [rsp+11D8h+SecurityDescriptor], r12
0x1800a1f8a  xorps   xmm0, xmm0
0x1800a1f8d  xor     eax, eax
0x1800a1f8f  movups  xmmword ptr [rsp+11D8h+SecurityAttributes.nLength], xmm0
0x1800a1f97  mov     qword ptr [rsp+11D8h+SecurityAttributes.bInheritHandle], rax
0x1800a1f9f  mov     rax, [rsp+11D8h+var_10F8]
0x1800a1fa7  mov     [rax], r12d
0x1800a1faa  mov     ecx, cs:dword_180128000
0x1800a1fb0  cmp     ecx, 5
0x1800a1fb3  jbe     short loc_1800A2026
0x1800a1fb5  mov     rdx, 400000000000h
0x1800a1fbf  lea     rcx, dword_180128000
0x1800a1fc6  call    _tlgKeywordOn
0x1800a1fcb  test    al, al
0x1800a1fcd  jz      short loc_1800A2026
0x1800a1fcf  mov     [rsp+11D8h+var_1098], 2000000h
0x1800a1fdb  lea     rax, [rsp+11D8h+var_1098]
0x1800a1fe3  mov     [rsp+11D8h+var_E08], rax
0x1800a1feb  mov     [rsp+11D8h+var_E00], 8
0x1800a1ff7  lea     rax, [rsp+11D8h+FileInformation]
0x1800a1fff  mov     qword ptr [rsp+11D8h+dwFlagsAndAttributes], rax
0x1800a2004  mov     [rsp+11D8h+dwCreationDisposition], 3
0x1800a200c  xor     r9d, r9d
0x1800a200f  xor     r8d, r8d
0x1800a2012  lea     rdx, dword_18011867C
0x1800a2019  lea     rcx, dword_180128000
0x1800a2020  call    _tlgWriteTransfer_EventWriteTransfer
0x1800a2025  nop
0x1800a2026  jmp     short loc_1800A2093
0x1800a2028  mov     esi, 208h
0x1800a202d  xor     r12d, r12d
0x1800a2030  mov     ebx, [rsp+11D8h+var_1170]
0x1800a2034  mov     rdi, [rsp+11D8h+lpFileName]
0x1800a203c  mov     eax, r12d
0x1800a203f  mov     [rsp+11D8h+var_1120], eax
0x1800a2046  mov     [rsp+11D8h+var_111C], eax
0x1800a204d  mov     [rsp+11D8h+var_1178], eax
0x1800a2051  mov     [rsp+11D8h+var_1118], eax
0x1800a2058  mov     r14, [rsp+11D8h+var_1090]
0x1800a2060  mov     [rsp+11D8h+var_10C8], r14
0x1800a2068  mov     r15d, dword ptr [rsp+11D8h+var_1158]
0x1800a2070  mov     rax, [rsp+11D8h+var_10B8]
0x1800a2078  mov     [rsp+11D8h+var_1140], rax
0x1800a2080  mov     rax, [rsp+11D8h+var_1128]
0x1800a2088  mov     [rsp+11D8h+var_10F8], rax
0x1800a2090  mov     r13, r14
0x1800a2093  mov     r8d, [r14]
0x1800a2096  and     r8d, 10000h
0x1800a209d  bts     r8d, 0Bh
0x1800a20a2  shr     r8d, 0Ah; unsigned int
0x1800a20a6  test    byte ptr [r14], 1
0x1800a20aa  mov     rcx, r12
0x1800a20ad  jnz     short loc_1800A20B3
0x1800a20af  mov     rcx, [r13+48h]; unsigned __int16 *
0x1800a20b3  mov     r9, [r13+20h]; void *
0x1800a20b7  mov     edx, 0EA60h; unsigned int
0x1800a20bc  call    ?GPLockPolicySection@@YAPEAXPEBGKKPEAX@Z; GPLockPolicySection(ushort const *,ulong,ulong,void *)
0x1800a20c1  mov     [rsp+11D8h+var_10B8], rax
0x1800a20c9  test    rax, rax
0x1800a20cc  jz      loc_1800A2738
0x1800a20d2  mov     edx, [r14]
0x1800a20d5  and     edx, 1; int
0x1800a20d8  mov     ecx, r12d
0x1800a20db  cmp     [r13+4], r12d
0x1800a20df  setnz   cl; int
0x1800a20e2  mov     r8, [r13+48h]; unsigned __int16 *
0x1800a20e6  call    ?RegisterTelemetryProviderIfNeeded@@YAXHHPEBG@Z; RegisterTelemetryProviderIfNeeded(int,int,ushort const *)
0x1800a20eb  mov     [rsp+11D8h+NewFileName], r12w
0x1800a20f4  mov     r9d, 104h
0x1800a20fa  lea     r8, [rsp+11D8h+NewFileName]
0x1800a2102  xor     edx, edx
0x1800a2104  lea     r14d, [rdx+4]
0x1800a2108  mov     ecx, r14d
0x1800a210b  call    cs:__imp_GetBasicProfileFolderPath
0x1800a2111  cmp     [rsp+11D8h+NewFileName], r12w
0x1800a211a  jnz     short loc_1800A218F
0x1800a211c  call    cs:__imp_GetLastError
0x1800a2122  mov     ebx, eax
0x1800a2124  mov     [rsp+11D8h+var_1170], eax
0x1800a2128  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800a212f  jz      loc_1800A2738
0x1800a2135  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800a213c  test    rax, rax
0x1800a213f  jz      short loc_1800A215B
0x1800a2141  lea     rdx, aProcessgporegi_16; "ProcessGPORegistryPolicy: Failed to get"...
0x1800a2148  mov     r13d, 2
0x1800a214e  mov     ecx, r13d
0x1800a2151  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2156  jmp     loc_1800A273E
0x1800a215b  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800a2162  jz      loc_1800A2738
0x1800a2168  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800a216f  jz      loc_1800A2738
0x1800a2175  lea     rdx, aProcessgporegi_16; "ProcessGPORegistryPolicy: Failed to get"...
0x1800a217c  mov     r13d, 2
0x1800a2182  mov     ecx, r13d; unsigned int
0x1800a2185  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800a218a  jmp     loc_1800A273E
0x1800a218f  and     r15d, 1
0x1800a2193  jnz     loc_1800A2330
0x1800a2199  lea     r8, aMicrosoftGroup; "\\Microsoft\\GroupPolicy\\Users\\"
0x1800a21a0  mov     edx, 104h; unsigned __int64
0x1800a21a5  lea     rcx, [rsp+11D8h+NewFileName]; unsigned __int16 *
0x1800a21ad  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800a21b2  test    eax, eax
0x1800a21b4  jns     short loc_1800A222D
0x1800a21b6  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800a21bd  jz      loc_1800A2738
0x1800a21c3  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800a21ca  test    rax, rax
0x1800a21cd  jz      short loc_1800A21F1
0x1800a21cf  lea     rdx, aProcessgporegi_8; "ProcessGPORegistryPolicy: Failed to con"...
0x1800a21d6  lea     r8, [rsp+11D8h+NewFileName]
0x1800a21de  mov     r13d, 2
0x1800a21e4  mov     ecx, r13d
0x1800a21e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a21ec  jmp     loc_1800A273E
0x1800a21f1  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800a21f8  jz      loc_1800A2738
0x1800a21fe  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800a2205  jz      loc_1800A2738
0x1800a220b  lea     rdx, aProcessgporegi_8; "ProcessGPORegistryPolicy: Failed to con"...
0x1800a2212  lea     r8, [rsp+11D8h+NewFileName]
0x1800a221a  mov     r13d, 2
0x1800a2220  mov     ecx, r13d; unsigned int
0x1800a2223  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800a2228  jmp     loc_1800A273E
0x1800a222d  mov     r8, [r13+48h]; unsigned __int16 *
0x1800a2231  mov     edx, 104h; unsigned __int64
0x1800a2236  lea     rcx, [rsp+11D8h+NewFileName]; unsigned __int16 *
0x1800a223e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800a2243  test    eax, eax
0x1800a2245  jns     loc_1800A22D0
0x1800a224b  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800a2252  jz      loc_1800A2738
0x1800a2258  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800a225f  test    rax, rax
0x1800a2262  jz      short loc_1800A228D
0x1800a2264  lea     r9, [rsp+11D8h+NewFileName]
0x1800a226c  mov     r8, [r13+0D0h]
0x1800a2273  lea     rdx, aProcessgporegi_19; "ProcessGPORegistryPolicy: Failed to con"...
0x1800a227a  mov     r13d, 2
0x1800a2280  mov     ecx, r13d
0x1800a2283  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2288  jmp     loc_1800A273E
0x1800a228d  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800a2294  jz      loc_1800A2738
0x1800a229a  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800a22a1  jz      loc_1800A2738
0x1800a22a7  lea     r9, [rsp+11D8h+NewFileName]
0x1800a22af  mov     r8, [r13+0D0h]
0x1800a22b6  lea     rdx, aProcessgporegi_19; "ProcessGPORegistryPolicy: Failed to con"...
0x1800a22bd  mov     r13d, 2
0x1800a22c3  mov     ecx, r13d; unsigned int
0x1800a22c6  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800a22cb  jmp     loc_1800A273E
0x1800a22d0  mov     r8, [r13+8]; void *
0x1800a22d4  lea     rcx, [rsp+11D8h+NewFileName]; unsigned __int16 *
0x1800a22dc  call    ?SetSecureDirectory@@YAKPEBGKPEAX@Z; SetSecureDirectory(ushort const *,ulong,void *)
0x1800a22e1  test    eax, eax
0x1800a22e3  jns     short loc_1800A2330
0x1800a22e5  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800a22ec  jz      loc_1800A2738
0x1800a22f2  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800a22f9  test    rax, rax
0x1800a22fc  jz      short loc_1800A230A
0x1800a22fe  lea     rdx, aProcessgporegi_14; "ProcessGPORegistryPolicy: SecureDirecto"...
0x1800a2305  jmp     loc_1800A21D6
0x1800a230a  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800a2311  jz      loc_1800A2738
0x1800a2317  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800a231e  jz      loc_1800A2738
0x1800a2324  lea     rdx, aProcessgporegi_14; "ProcessGPORegistryPolicy: SecureDirecto"...
0x1800a232b  jmp     loc_1800A2212
0x1800a2330  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800a2337  jz      short loc_1800A2387
0x1800a2339  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800a2340  test    rax, rax
0x1800a2343  jz      short loc_1800A235E
0x1800a2345  lea     r8, [rsp+11D8h+NewFileName]
0x1800a234d  lea     rdx, aProcessgporegi_9; "ProcessGPORegistryPolicy: After concate"...
0x1800a2354  mov     ecx, r14d
0x1800a2357  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a235c  jmp     short loc_1800A2387
0x1800a235e  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800a2365  jz      short loc_1800A2387
0x1800a2367  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800a236e  jz      short loc_1800A2387
0x1800a2370  lea     r8, [rsp+11D8h+NewFileName]
0x1800a2378  lea     rdx, aProcessgporegi_9; "ProcessGPORegistryPolicy: After concate"...
0x1800a237f  mov     ecx, r14d; unsigned int
0x1800a2382  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800a2387  mov     rdx, rsi; uBytes
0x1800a238a  mov     ecx, 40h ; '@'; uFlags
0x1800a238f  call    cs:__imp_LocalAlloc
0x1800a2395  mov     rdx, rax
0x1800a2398  lea     rcx, [rsp+11D8h+lpFileName]
0x1800a23a0  call    ??4?$XPtrLF@G@@QEAAPEAGPEAG@Z; XPtrLF<ushort>::operator=(ushort *)
0x1800a23a5  mov     rdi, [rsp+11D8h+lpFileName]
0x1800a23ad  test    rdi, rdi
0x1800a23b0  jnz     short loc_1800A2403
0x1800a23b2  call    cs:__imp_GetLastError
0x1800a23b8  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800a23bf  jz      loc_1800A2738
0x1800a23c5  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800a23cc  test    rax, rax
0x1800a23cf  jz      short loc_1800A23DD
0x1800a23d1  lea     rdx, aProcessgporegi_4; "ProcessGPORegistryPolicy: Failed to all"...
0x1800a23d8  jmp     loc_1800A2148
0x1800a23dd  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800a23e4  jz      loc_1800A2738
0x1800a23ea  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800a23f1  jz      loc_1800A2738
0x1800a23f7  lea     rdx, aProcessgporegi_4; "ProcessGPORegistryPolicy: Failed to all"...
0x1800a23fe  jmp     loc_1800A217C
0x1800a2403  lea     r8, [rsp+11D8h+NewFileName]; unsigned __int16 *
0x1800a240b  mov     esi, 104h
0x1800a2410  mov     edx, esi; unsigned __int64
0x1800a2412  mov     rcx, rdi; unsigned __int16 *
0x1800a2415  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800a241a  test    eax, eax
0x1800a241c  jns     loc_1800A24A9
0x1800a2422  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800a2429  jz      short loc_1800A2487
0x1800a242b  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800a2432  test    rax, rax
0x1800a2435  jz      short loc_1800A2456
0x1800a2437  lea     r8, [rsp+11D8h+NewFileName]
0x1800a243f  lea     rdx, aProcessgporegi_15; "ProcessGPORegistryPolicy: Failed to cop"...
0x1800a2446  mov     r13d, 2
0x1800a244c  mov     ecx, r13d
  ... truncated ...
```
