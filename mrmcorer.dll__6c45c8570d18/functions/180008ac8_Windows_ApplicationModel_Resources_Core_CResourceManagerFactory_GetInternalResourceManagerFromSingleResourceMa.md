# Windows::ApplicationModel::Resources::Core::CResourceManagerFactory::_GetInternalResourceManagerFromSingleResourceManager(Microsoft::Resources::Runtime::CResourceManagerInternal * *)

- ea: `0x180008ac8`
- end: `0x180008bd0`
- name: `?_GetInternalResourceManagerFromSingleResourceManager@CResourceManagerFactory@Core@Resources@ApplicationModel@Windows@@AEAAJPEAPEAVCResourceManagerInternal@Runtime@3Microsoft@@@Z`
- size: `264`
- prototype: `__int64 __fastcall(Windows::ApplicationModel::Resources::Core::CResourceManagerFactory *__hidden this, struct Microsoft::Resources::Runtime::CResourceManagerInternal **)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180008958`

## callees

- `0x18000892c`
- `0x180008ac8`
- `0x18000a070`
- `0x18002c8d0`
- `0x1800c5010`

## import_xrefs

- `ntdll!RtlAcquireSRWLockShared` at `0x180008ae1`
- `ntdll!RtlAcquireSRWLockShared` at `0x180008ae1`
- `ntdll!RtlReleaseSRWLockShared` at `0x180008b3e`
- `ntdll!RtlReleaseSRWLockShared` at `0x180008b3e`

## string_xrefs

- `0x180008b83`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcemanager.cpp`
- `0x180008bab`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcemanager.cpp`

## pseudocode

```c

```
