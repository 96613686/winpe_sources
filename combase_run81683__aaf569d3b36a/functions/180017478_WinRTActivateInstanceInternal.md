# WinRTActivateInstanceInternal

- ea: `0x180017478`
- end: `0x180017ba2`
- name: `WinRTActivateInstanceInternal`
- size: `1834`
- prototype: `HRESULT __fastcall(HSTRING__ *activatableClassId, Windows::Foundation::IExtensionRegistration *pExtensionInformation, IWinRTRuntimeClassInfo *pRuntimeClassInfo, unsigned __int64 userContext, Windows::Foundation::IActivationContext *activationContext, IInspectable **instance)`
- caller_count: `4`
- callee_count: `17`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180016260`
- `0x180017d68`
- `0x1800d3a70`
- `0x180205610`

## callees

- `0x18000712c`
- `0x18000b408`
- `0x1800167d8`
- `0x180016970`
- `0x180017478`
- `0x18003a8bc`
- `0x1800450a0`
- `0x180055270`
- `0x1800c1034`
- `0x1800d0e28`
- `0x1800df33c`
- `0x180138e74`
- `0x180182ff4`
- `0x1801999b0`
- `0x18019c75c`
- `0x18019c9fc`
- `0x180255010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180017a50`
- `ntdll!RtlNtStatusToDosError` at `0x180017a50`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001765c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001765c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001764e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001764e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180017816`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180017816`
- `ext-ms-win-com-psmregister-l1-1-0!PsmQueryBackgroundActivationType` at `0x180017a1b`
- `ext-ms-win-com-psmregister-l1-1-0!PsmQueryBackgroundActivationType` at `0x180017a1b`
- `ext-ms-win-core-winrt-remote-l1-1-0!RemoteWinRTActivation` at `0x180017b8c`
- `ext-ms-win-core-winrt-remote-l1-1-0!RemoteWinRTActivation` at `0x180017b8c`

## string_xrefs

- `0x18001768b`: `onecore\com\combase\winrtbase\winrtbase.cpp`

## pseudocode

```c

```
