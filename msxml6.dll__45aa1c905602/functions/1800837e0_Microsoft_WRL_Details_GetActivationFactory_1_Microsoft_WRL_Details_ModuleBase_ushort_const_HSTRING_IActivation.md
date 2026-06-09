# Microsoft::WRL::Details::GetActivationFactory<1>(Microsoft::WRL::Details::ModuleBase *,ushort const *,HSTRING__ *,IActivationFactory * *)

- ea: `0x1800837e0`
- end: `0x18008396f`
- name: `??$GetActivationFactory@$00@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBGPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z`
- size: `399`
- prototype: `HRESULT __fastcall(Microsoft::WRL::Details::ModuleBase *modulePtr, const wchar_t *activatibleClassId, HSTRING__ *ppFactory, IActivationFactory **modulePtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18009b3c0`

## callees

- `0x1800837e0`
- `0x180083978`
- `0x1800cc6c0`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18008381a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18008381a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180083836`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180083836`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008385a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008385a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18008393f`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18008393f`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800838fa`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800838fa`

## string_xrefs

- `0x180083908`: `activatibleClassId`

## pseudocode

```c

```
