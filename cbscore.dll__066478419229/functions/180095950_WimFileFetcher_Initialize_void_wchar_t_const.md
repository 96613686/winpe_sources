# WimFileFetcher::Initialize(void *,wchar_t const *)

- ea: `0x180095950`
- end: `0x180095e2b`
- name: `?Initialize@WimFileFetcher@@UEAAJPEAXPEB_W@Z`
- size: `1243`
- prototype: `__int64 __fastcall(WimFileFetcher *__hidden this, void *, const wchar_t *)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180010cc0`
- `0x180016d40`
- `0x18004142c`
- `0x180057c28`
- `0x18005a548`
- `0x18005ffc8`
- `0x180095950`
- `0x180095e34`
- `0x180095e58`
- `0x180096e44`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800eb920`
- `0x18012bc30`
- `0x1802d5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800959ff`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800959ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095c2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095c2f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180095c1b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180095c1b`

## string_xrefs

- `0x180095c4e`: `Failed to create strong security descriptor`
- `0x180095b4a`: `Failed to create file sandbox subdirectory`
- `0x180095ab6`: `Could not create sandbox environment`
- `0x180095d0f`: `Failed to create new file source sandbox process`
- `0x18009599c`: `No working path specified`

## pseudocode

```c

```
